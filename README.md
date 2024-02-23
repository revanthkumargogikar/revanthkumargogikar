<!DOCTYPE html>
<html>
    <head>
      <!-- font awesome logo-->
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
      <title>i-message</title>
        <style>
            body{
              background-color: rgb(249, 246, 246);
              padding: 0;
              margin: 0;
              /* font-family: Arial, Helvetica, sans-serif; */
            }
            #chat-container-1{
              height: 508px;
              max-width: 280px;
              margin: 20px auto;
              border: 2px solid silver;
              border-radius: 20px;
              box-shadow: 2px 2px 5px black;
            }
            #chat-container{
              height: 98%;
              max-width: 290px;
              border: 5px solid black;
              border-radius: 18px;
              overflow: hidden;
            }
            #notch{
              height: 35px;
              background-color: rgb(217, 215, 215); 
              color: white;
              text-align: center;   
              display: flex;
              align-content: center;
              justify-content: space-evenly;
            }
            #notch2{
              margin-top: 8px;
                height: 20px;
                width: 80px;
                background-color: rgb(17, 15, 15);
                border-radius:30px; 
            }
            #header{
              background-color: rgb(217, 215, 215);
              border-bottom: 0.09px solid silver;
              padding: 10px;
              text-align: center;
              font-weight:bold;
              letter-spacing: 0.4px;
              font-size: 13px;
              text-shadow: 0.5px 0.5px 3px rgb(118, 98, 98);
            }
            #profile-logo-bar{
              height: 40px;
              background-color: rgb(217, 215, 215);
              display: flex;
              justify-content: center;
            }
            #profilelogo{
             display: flex;
             /* margin-left: 110px; */
              background-color:silver;
              height: 40px;
              width: 40px;
              border-radius: 60%;
              background-image:url(./IMG_20180622_224558_020.jpg) ;
              background-size: 40px;
              box-shadow:  1px 1px 5px black;
            }
            #message-container{
              height: 325px;
              overflow-y:auto;
              padding: 10px;
              background-color: whitesmoke;
            }
            .message {
            max-width: 70%;
            padding: 10px;
            margin: 10px;
            border-radius: 15px;
            clear: both;
            }
          .my-message {
                float: right;
                background-color: #007bff;
                box-shadow: 1px 1px 5px rgb(74, 134, 190);
                color: #fff;
            }
            
            .other-message {
              float: left;
              background-color: #e0e0e0;
              box-shadow: 1px 1px 5px rgb(15, 20, 25);
            }
            #message-box{
              display: flex;
              align-items: center;
              padding: 10px;
              border-top: 1px solid whitesmoke;
              display: flex;
              justify-content: space-evenly;
            }
            #message-input{
              border-radius: 8px;
              border: 1px solid white;
              box-shadow: 1px 1px 5px rgb(92, 82, 82);
            }
            #send-button{
              background-color: #007bff;
              border-radius: 10px;
              border: 1px solid #007bff ;
              box-shadow: 1px 1px 5px black;
              /* handing pointer */
              cursor: pointer; 
            }
        </style>
    </head>
    <body>
      <div id="chat-container-1">
          <div id="chat-container">
            <div id="notch"><div id="notch2"></div></div>
            <div id="profile-logo-bar"><div id="profilelogo"></div></div>
            <div id="header">Karthik</div>
            <div id="message-container"></div>
            <div id="message-box">
              <div id="image-icon"><i class="fa-solid fa-image"></i></div>
              <input  id="message-input" type="text" placeholder=" iMessage">
               <i class="fa-solid fa-microphone"></i>
              <button id="send-button" onclick="sendMessage()"><i class="fa-regular fa-paper-plane"></i></button>
            </div>
      </div>  
    </div>
    <script>
          i=0;
      function sendMessage(){
        var messageInput=document.getElementById("message-input");
        var messageContainer=document.getElementById("message-container");
          
        if(messageInput.value.trim()!==""){
            var message=document.createElement("div");
            message.className="message my-message";
            message.innerText=messageInput.value;

            messageContainer.appendChild(message);
            messageInput.value="";
            setTimeout(receiveMessage,1000)
        }
        function receiveMessage() {
          var messageContainer=document.getElementById("message-container");
          var message=document.createElement("div");
          message.className="message other-message";
         // message.innerText="user2 reply" 
        
          if(i==0){ message.innerText="hello there !" }
          if(i==1){ message.innerText="how can i help you ?" }
          if(i==2){ message.innerText="yes" }
          if(i==3){ message.innerText="ok then" }
          if(i==4){ message.innerText="no worries" }
          if(i>4){ message.innerText="thanks" }
          i++;
          messageContainer.appendChild(message);

          messageContainer.scrollTop=messageContainer.scrollHeight;
        }
        
      }
    </script>
    </body>
</html>
