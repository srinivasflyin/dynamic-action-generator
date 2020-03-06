# dynamic-action-generator

In react we will be having the no of actions to be handled Instead of creating each action we can use the function to generate the actions based on the passing arguments.
        
        
        
        function actionGenerator (type, ...args) {
       return function (...args) {
       const action= {type: type };
           args.forEach((item)=>{
             action[item]  = item
         })
         return action;
       } 
    }
    
    lets say we want to create action of ADD items we define in the following manner:

          function editTodo(id, text) {
        return {
          type: 'EDIT_TODO',
          id,
          text
        }
      }
      
      By using the actionGenerator function we can create N no of functions:
       let add = actionGenerator(type, 'id', 'text'); // it generates the function add with the arguments type, id and text.
       
