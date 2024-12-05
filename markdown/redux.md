
 redux - core library 
 redux-react - like react-dom
 ----------------------------

 centenral store.....like global variable 

 redux-toolkit.... middleware, sliceReducer

 # concepts 

 store
 --------
 reducers 
 -----------
 useSelector 
 useDispatch

 # toolkit - need to use 2 library 

 # store.js 

 import configureStore form redux 

 export const store = configureStore({}); // created a store 

 # next step, make reducer  (slices)

 import {createSlice} form toolkit 

 const initialState = { todos:[{id:1,text:"hello world"}]};

 export const todoSlice = createSlice({
    name:todo, // predefined properties
    initialState,
    reducers:{
        addTodo:(state,action)=>{
          // state - access to state 
          // action - object or payload
          const newTodo = {id:action.payload.id,text:action.payload.text}
          state.todos.push(newTodo);
        },
        removeTodo:(state,action)=>{
            state.todos = state.todos.filter((todo)=>{
                retrun todo.id !== action.payload.id
            });
        }
    }
 });

 export const{addTodo,removeTodo} = todoSlice.actions; 

 # next, store need knowledge of reducers

 import configureStore fr0m redux 
 import todoReducer from 'todoSlice';
 export const store = configureStore({reducer:todoReducer}); // created a store 

 # next, component 
  
function AddTodo(){

    state, txtinput, settxtinput() 
    const dispatch = useDispatch() // from redux-toolkit
    // user reducers to make changes in stores

    dispatch

    return <>
      form
       input 
    </>
}