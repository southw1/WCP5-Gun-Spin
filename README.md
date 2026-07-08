<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Gun Spinner</title>

    <link rel="stylesheet" href="style.css">

</head>


<body>


<div class="container">


    <div class="title">
        GUN SPINNER
    </div>



    <!-- Tier Selection -->

    <div class="tiers">

        <button class="tier-btn active" data-tier="Tier 0">
            Tier 0
        </button>


        <button class="tier-btn" data-tier="Tier 1">
            Tier 1
        </button>


        <button class="tier-btn" data-tier="Tier 1.5">
            Tier 1.5
        </button>


        <button class="tier-btn" data-tier="Tier 2">
            Tier 2
        </button>

    </div>




    <!-- Spinner Pointer -->

    <div class="pointer"></div>




    <!-- Gun Spinner -->

    <div class="spinner-box">

        <div id="spinner">
            Press Spin
        </div>

    </div>





    <!-- Spin Button -->

    <button id="spin">
        SPIN
    </button>





    <!-- Weapon Card -->

    <div class="weapon-card">


        <div class="weapon-name" id="weaponName">

            No Drop

        </div>



        <div class="weapon-type">

            Selected Weapon

        </div>




        <div class="rarity-bar">


            <div class="rarity-fill"></div>


        </div>


    </div>





    <!-- Result -->

    <div id="result">

        Ready to spin...

    </div>



</div>





<script src="script.js"></script>


</body>

</html>/*
GUN SPINNER
FULL STYLE SHEET
*/


:root {

    --tier-color: #808080;

}



* {

    box-sizing: border-box;

    font-family: Arial, sans-serif;

}



body {

    margin: 0;

    height: 100vh;

    background: #050505;

    display: flex;

    justify-content: center;

    align-items: center;

    color: white;

}



/* Main Container */

.container {

    width: 900px;

    min-height: 600px;

    background: #0b0b0b;

    border: 2px solid var(--tier-color);

    border-radius: 15px;

    padding: 30px;

    overflow: hidden;

    box-shadow:

    0 0 25px var(--tier-color);

    position: relative;

}



/* Title */

.title {

    text-align: center;

    font-size: 38px;

    font-weight: bold;

    letter-spacing: 4px;

    margin-bottom: 25px;

}



/* Tier Buttons */

.tiers {

    display: flex;

    justify-content: center;

    gap: 15px;

    margin-bottom: 30px;

}



.tier-btn {

    padding: 12px 25px;

    background: #111;

    color: white;

    border: 1px solid #333;

    border-radius: 8px;

    cursor: pointer;

    transition: .3s;

}



.tier-btn:hover,

.tier-btn.active {

    border-color: var(--tier-color);

    box-shadow:

    0 0 15px var(--tier-color);

}



/* Spinner Pointer */

.pointer {

    width: 0;

    height: 0;

    margin: auto;

    border-left: 15px solid transparent;

    border-right: 15px solid transparent;

    border-bottom: 25px solid var(--tier-color);

}



/* Spinner Box */

.spinner-box {

    height: 180px;

    background: black;

    border: 2px solid var(--tier-color);

    border-radius: 12px;

    display: flex;

    justify-content: center;

    align-items: center;

    margin-top: 10px;

}



/* Gun Text */

#spinner {

    font-size: 32px;

    font-weight: bold;

    text-align: center;

}



/* Spin Animation */

.spinning {

    animation: spinEffect .1s infinite;

}



@keyframes spinEffect {


    0% {

        transform: translateY(-5px);

    }


    50% {

        transform: translateY(5px);

    }


    100% {

        transform: translateY(-5px);

    }

}



/* Spin Button */

#spin {

    margin-top: 25px;

    width: 100%;

    padding: 15px;

    background: #111;

    color: white;

    font-size: 22px;

    font-weight: bold;

    border-radius: 10px;

    border: 2px solid var(--tier-color);

    cursor: pointer;

    box-shadow:

    0 0 15px var(--tier-color);

}



#spin:hover {

    transform: scale(1.05);

}



/* Weapon Card */

.weapon-card {

    margin-top: 25px;

    padding: 20px;

    background: #111;

    border: 2px solid var(--tier-color);

    border-radius: 12px;

    text-align: center;

    animation: pulseGlow 2s infinite;

}



.weapon-name {

    font-size: 30px;

    font-weight: bold;

}



.weapon-type {

    margin-top: 8px;

    color: #aaa;

    font-size: 18px;

}



/* Rarity Bar */

.rarity-bar {

    height: 10px;

    width: 100%;

    background: #222;

    border-radius: 10px;

    margin-top: 15px;

    overflow: hidden;

}



.rarity-fill {

    height: 100%;

    width: 100%;

    background: var(--tier-color);

    box-shadow:

    0 0 15px var(--tier-color);

}



/* Result Text */

#result {

    margin-top: 20px;

    text-align: center;

    font-size: 24px;

    color: var(--tier-color);

}



/* Glow Animation */

@keyframes pulseGlow {


    0% {

        box-shadow:

        0 0 10px var(--tier-color);

    }


    50% {

        box-shadow:

        0 0 30px var(--tier-color);

    }


    100% {

        box-shadow:

        0 0 10px var(--tier-color);

    }

}/*
GUN SPINNER
FULL SCRIPT
*/


const guns = {


    "Tier 0": [

        "Pistol - Beretta",
        "Pistol Mk II - Glock 45",
        "Combat Pistol - G19x",
        "SNS Pistol - Walter P90",
        "SNS Pistol Mk II - Hellcat",
        "Heavy Pistol - FN",
        "Vintage Pistol - Glock 41",
        "Ceramic Pistol - SigP230"

    ],



    "Tier 1": [

        "Pistol - Beretta",
        "Pistol Mk II - Glock 45",
        "Combat Pistol - G19x",
        "SNS Pistol - Walter P90",
        "SNS Pistol Mk II - Hellcat",
        "Heavy Pistol - FN",
        "Vintage Pistol - Glock 41",
        "Ceramic Pistol - SigP230"

    ],



    "Tier 1.5": [

        "SMG - Banshee ARP",
        "SMG Mk II - 4 Inch ARP (FRT)",
        "Machine Pistol - Tec 9",
        "AP Pistol - G47 Switch",
        "Pistol .50 - FN 57",
        "Heavy Pistol - FN",
        "WM 29 Pistol - Glock 30",
        "Compact Rifle - Micro Draco",
        "Heavy Rifle - Honey Badger"

    ],



    "Tier 2": [

        "Carbine Rifle - 300 Blackout",
        "Carbine Rifle Mk II - Micro ARP",
        "Compact Rifle - Black Draco",
        "AP Pistol - G47 Switch",
        "Micro SMG - Kriss Vector",
        "Tactical SMG - Mac 10",
        "Combat PDW - DDM4"

    ]

};




let selectedTier = "Tier 0";



const tierButtons = document.querySelectorAll(".tier-btn");

const spinButton = document.querySelector("#spin");

const spinnerText = document.querySelector("#spinner");

const resultText = document.querySelector("#result");

const weaponName = document.querySelector("#weaponName");





// Tier Colors

function updateTierColor() {


    let color;


    if (selectedTier === "Tier 0") {

        color = "#808080";

    }


    if (selectedTier === "Tier 1") {

        color = "#00ff66";

    }


    if (selectedTier === "Tier 1.5") {

        color = "#0099ff";

    }


    if (selectedTier === "Tier 2") {

        color = "#ffcc00";

    }


    document.documentElement.style
    .setProperty("--tier-color", color);

}





// Select Tier

tierButtons.forEach(button => {


    button.addEventListener("click", () => {


        selectedTier = button.dataset.tier;


        tierButtons.forEach(btn => {

            btn.classList.remove("active");

        });


        button.classList.add("active");


        weaponName.textContent = "No Drop";


        resultText.textContent = "Ready to spin...";


        updateTierColor();


    });


});






// Save Drop

function saveDrop(gun) {


    localStorage.setItem(

        "lastDrop",

        gun

    );


}





// Load Drop

function loadDrop() {


    const saved = localStorage.getItem("lastDrop");


    if(saved) {


        resultText.textContent =

        `Last Drop: ${saved}`;


    }


}





// Spin Function

spinButton.addEventListener("click", () => {



    const weaponList = guns[selectedTier];



    let count = 0;



    spinnerText.classList.add("spinning");



    const spin = setInterval(() => {



        const randomGun =

        weaponList[

        Math.floor(Math.random() * weaponList.length)

        ];



        spinnerText.textContent = randomGun;



        count++;



        if(count >= 35) {



            clearInterval(spin);



            spinnerText.classList.remove("spinning");



            const finalGun =

            weaponList[

            Math.floor(Math.random() * weaponList.length)

            ];



            spinnerText.textContent = finalGun;



            resultText.textContent =

            `Your Drop: ${finalGun}`;



            weaponName.textContent = finalGun;



            saveDrop(finalGun);



        }



    }, 80);



});






// Start

updateTierColor();

loadDrop();
