// create a in memory Hospital.   
// Hospital backend 

const express = require('express'); 
const app = express();

const users = [{
    name : "John",
    kidneys :[{
        healthy :false ,  
    }]

}];

app.use(express.json());
app.get("/", (req,res) => {
    
    const johnKidneys = users[0].kidneys;
    const numberOfKidneys = johnKidneys.length;  
    let numberOfHealthyKidneys = 0;  
    for (let i = 0; i<numberOfKidneys; i++) {
        if(johnKidneys[i].healthy){
            numberOfHealthyKidneys = numberOfHealthyKidneys + 1;

        }        
    }
    const numberOfUnHealthyKidneys = numberOfKidneys - numberOfHealthyKidneys;

    res.json({
        numberOfKidneys,  
        numberOfHealthyKidneys,     
        numberOfUnHealthyKidneys     
    })

})

app.post("/", (req,res) => {
    const ishealthy = req.body.ishealthy;   
    users[0].kidneys.push({
        healthy:ishealthy   
    })

    res.json({
        msg:"done"
    })
} )

// user can replace all kidney make it healthy 
app.put("/", (req, res) =>{
    for (let i = 0; i < users[0].kidneys.length; i++) {
        users[0].kidneys[i].healthy = true;

        res.json({
            msg:"success"

        });

    }
})

// for delete all unhealthykidneys
app.delete("/", (req,res) => {
    for(let i = 0; i<users[0].kidneys.length;i++){
        const newKidneys = [];
        if(users[0].kidneys[i].healthy){
            newKidneys.push({
                healthy:true
            })
        }
        users[0].kidneys = newKidneys;

        res.json({
            msg:"all healthy kidneys"
        })

    }
}) 



app.listen(3000);  


