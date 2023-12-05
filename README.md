# form-to-google-sheets

1. open your google sheet in your browser make sure to login with your account
2. create new sheet by clicking the add button in corner
3. and name your sheets as you wanna
4. create table depending on your needs
5. make sure to name it the coloums of this table exactly like you name it in html, example (<input type="text" id="name" name="Name" required>), so in this case you just name it the coloums "Name"
6. click on extention in your google sheets and choose the app script
7. change the name to exactly like your sheet name
8. remove the function and paste it with code that i put in file name "google-app-script.js".
9. save and run
10. wait till the process done and it would be appears a pop up about authorization, you just click review permissions
11. you need to login with google account but make sure the account is the same as you login in before
12. click advance and go with unsafe
13. after that click deploy button in right corner of the top and choose new deployment
14. click setting button and go with web app
15. just one change on that step but you just change the access to anyone
16. after that copy the link url and paste it in file script
    
const scriptURL = '<put script here>'
const form = document.forms['submit-to-google-sheet']
const msg = document.getElementById("msg")

form.addEventListener('submit', e => {
    e.preventDefault()
    fetch(scriptURL, { method: 'POST', body: new FormData(form) })
        .then(response => {
            msg.innerHTML = "Message Sent Successfully"
            setTimeout(function () {
                msg.innerHTML = ""
            }, 5000)
            form.reset()
        })
        .catch(error => console.error('Error!', error.message))
})

17. nah you done my brothersss keep it up
