
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Facts & Pictures · random facts app</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: system-ui, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
    }

    body {
      min-height: 100vh;
      background: linear-gradient(145deg, #0b1a2e 0%, #1b2f44 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 1.5rem;
    }

    .app-card {
      max-width: 1200px;
      width: 100%;
      background: rgba(255, 255, 255, 0.06);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-radius: 3.5rem;
      padding: 2rem 2rem 2.5rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), 0 0 0 1px rgba(255, 255, 255, 0.05);
      transition: all 0.2s;
    }

    h1 {
      text-align: center;
      font-weight: 500;
      font-size: 2.6rem;
      letter-spacing: -0.02em;
      color: #f0f9ff;
      text-shadow: 0 4px 12px rgba(0, 180, 255, 0.4);
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
    }

    h1 span {
      background: #ffd966;
      color: #0b1a2e;
      font-size: 1.8rem;
      padding: 0.2rem 1rem;
      border-radius: 100px;
      font-weight: 600;
      box-shadow: 0 0 15px #ffd96688;
    }

    .subhead {
      text-align: center;
      color: #b4d0e7;
      margin-bottom: 2.5rem;
      font-size: 1.2rem;
      font-weight: 300;
      letter-spacing: 0.5px;
    }

    .fact-box {
      background: #0f212f;
      border-radius: 2.8rem;
      padding: 2.2rem 2.2rem 1.8rem;
      box-shadow: inset 0 0 18px #00000055, 0 15px 30px #00000040;
      border: 1px solid #ffffff14;
      margin-bottom: 2.5rem;
      transition: all 0.3s ease;
    }

    .fact-text {
      font-size: 1.9rem;
      line-height: 1.5;
      font-weight: 400;
      color: #e5f2ff;
      text-shadow: 0 2px 5px black;
      min-height: 9rem;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 0.5rem 0.5rem 1rem;
      word-break: break-word;
      transition: opacity 0.3s ease;
    }

    .fact-text i {
      font-style: normal;
      background: #1e3b4f;
      padding: 0.2rem 0.8rem;
      border-radius: 40px;
      font-size: 1.3rem;
      margin-right: 10px;
      color: #8bb9e0;
      vertical-align: middle;
    }

    .image-container {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 1.8rem 0 1rem;
      border-radius: 2rem;
      overflow: hidden;
      background: #09131c;
      box-shadow: 0 20px 30px -10px black;
      border: 2px solid #ffffff0d;
      transition: all 0.3s ease;
      min-height: 280px;
    }

    .fact-image {
      display: block;
      width: 100%;
      height: auto;
      max-height: 380px;
      object-fit: cover;
      transition: transform 0.45s cubic-bezier(0.2, 0.9, 0.3, 1), opacity 0.3s;
      background: #142837;
    }

    .fact-image:hover {
      transform: scale(1.02);
    }

    .btn-wrapper {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin-top: 2rem;
    }

    .fact-btn {
      background: linear-gradient(135deg, #1f8ea9, #1d6d8f);
      border: none;
      color: white;
      font-weight: 600;
      font-size: 1.5rem;
      padding: 1.2rem 3rem;
      border-radius: 60px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      cursor: pointer;
      box-shadow: 0 20px 30px -8px #00000099, 0 0 0 2px #5ec8ff33, 0 0 20px #1d9adf66;
      transition: all 0.2s ease;
      letter-spacing: 0.5px;
      backdrop-filter: blur(5px);
      min-width: 260px;
    }

    .fact-btn:hover {
      background: linear-gradient(135deg, #2aa3c2, #19738f);
      box-shadow: 0 18px 35px -6px #000000cc, 0 0 0 3px #88d6ff66, 0 0 30px #43b4ff;
      transform: scale(1.02);
    }

    .fact-btn:active {
      transform: scale(0.98);
      box-shadow: 0 8px 18px -4px black;
    }

    .fact-btn i {
      font-size: 2rem;
      line-height: 1;
      filter: drop-shadow(0 2px 3px black);
    }

    .counter-badge {
      background: #223e52;
      padding: 0.7rem 2rem;
      border-radius: 40px;
      color: #b9defa;
      font-size: 1.1rem;
      font-weight: 500;
      letter-spacing: 0.3px;
      box-shadow: inset 0 1px 5px #00000066;
      border: 1px solid #ffffff1a;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .counter-badge span {
      background: #3b6e8f;
      padding: 0.2rem 0.9rem;
      border-radius: 30px;
      color: white;
      font-weight: 700;
      margin-left: 6px;
    }

    .footer-note {
      text-align: center;
      color: #6f8fa8;
      margin-top: 2rem;
      font-size: 0.95rem;
      font-style: italic;
      opacity: 0.8;
    }

    /* Loading state */
    .loading-shimmer {
      background: linear-gradient(90deg, #142837 0%, #1e3f52 50%, #142837 100%);
      background-size: 200% 100%;
      animation: shimmer 1.4s infinite;
      color: transparent !important;
    }

    @keyframes shimmer {
      0% { background-position: 200% 0; }
      100% { background-position: -200% 0; }
    }

    /* Responsive */
    @media (max-width: 600px) {
      .app-card { padding: 1.5rem 1rem 2rem; border-radius: 2rem; }
      h1 { font-size: 1.8rem; }
      h1 span { font-size: 1.2rem; padding: 0.2rem 0.8rem; }
      .fact-text { font-size: 1.4rem; min-height: 7rem; }
      .fact-btn { font-size: 1.3rem; padding: 1rem 1.8rem; min-width: 200px; }
      .image-container { min-height: 200px; }
      .fact-image { max-height: 260px; }
    }
  </style>
</head>
<body>
  <div class="app-card">
    <h1>
      📚 Fact<span>Pics</span>
    </h1>
    <div class="subhead">✦ one fact · one picture ✦</div>

    <!-- Fact display area -->
    <div class="fact-box">
      <div id="factDisplay" class="fact-text">
        <!-- fact will appear here -->
      </div>

      <!-- Image container -->
      <div class="image-container">
        <img id="factImage" class="fact-image" src="" alt="Illustration for the fact" loading="lazy">
      </div>

      <!-- counter + button -->
      <div class="btn-wrapper">
        <button id="newFactBtn" class="fact-btn">
          <i>🎲</i> New fact
        </button>
        <div class="counter-badge">
          🧠 Facts seen <span id="factCounter">0</span>
        </div>
      </div>
    </div>
    <div class="footer-note">
      click the button — every fact comes with a unique picture
    </div>
  </div>

  <script>
    (function(){
      // --------------------------------------------------------------
      // DATASET: 12 facts, each with a descriptive image from Unsplash
      // (using source.unsplash.com for reliable, keyword-based images)
      // --------------------------------------------------------------
      const factsData = [
        {
          fact: "Octopuses have three hearts. Two pump blood to the gills, while the third pumps it to the rest of the body.",
          imageQuery: "octopus,underwater"
        },
        {
          fact: "The Eiffel Tower can be 15 cm taller during the summer, as the iron expands in the heat.",
          imageQuery: "eiffel,tower,paris"
        },
        {
          fact: "Honey never spoils. Archaeologists have found pots of honey in ancient Egyptian tombs that are over 3,000 years old and still perfectly edible.",
          imageQuery: "honey,jar,nature"
        },
        {
          fact: "A day on Venus is longer than a year on Venus. It takes Venus 243 Earth days to rotate once on its axis, but only 225 Earth days to orbit the Sun.",
          imageQuery: "venus,planet,space"
        },
        {
          fact: "Bananas are berries, but strawberries are not. Botanically, a berry is a fleshy fruit produced from a single ovary.",
          imageQuery: "banana,fruit,healthy"
        },
        {
          fact: "The human brain uses about 20% of the body's total oxygen and energy, despite being only about 2% of its weight.",
          imageQuery: "brain,neuroscience,mind"
        },
        {
          fact: "Sharks existed before trees. Sharks have been around for about 400 million years, while trees appeared around 350 million years ago.",
          imageQuery: "shark,ocean,underwater"
        },
        {
          fact: "A cloud can weigh more than a million pounds. The average cumulus cloud weighs about 1.1 million pounds (500,000 kg).",
          imageQuery: "clouds,sky,weather"
        },
        {
          fact: "There are more possible iterations of a game of chess than there are atoms in the known universe.",
          imageQuery: "chess,board,strategy"
        },
        {
          fact: "The unicorn is the national animal of Scotland. It was chosen because it symbolizes purity, innocence, and power.",
          imageQuery: "unicorn,scotland,statue"
        },
        {
          fact: "Wombat poop is cube-shaped. This prevents it from rolling away and helps mark territory.",
          imageQuery: "wombat,animal,australia"
        },
        {
          fact: "The first oranges weren't orange. The original oranges from Southeast Asia were actually green, and they were a hybrid of mandarin and pomelo.",
          imageQuery: "orange,fruit,citrus"
        }
      ];

      // --------------------------------------------------------------
      // DOM elements
      // --------------------------------------------------------------
      const factDisplay = document.getElementById('factDisplay');
      const factImage = document.getElementById('factImage');
      const newFactBtn = document.getElementById('newFactBtn');
      const factCounterSpan = document.getElementById('factCounter');

      // Track how many facts have been viewed (starting at 0)
      let viewedCount = 0;
      // Keep last displayed index to avoid immediate repetition (optional)
      let lastIndex = -1;

      // --------------------------------------------------------------
      // Helper: pick a random fact (avoid repeating the same one if possible)
      // --------------------------------------------------------------
      function pickRandomFact() {
        let newIndex;
        // if we have more than 1 fact, try to avoid repeating the last one
        if (factsData.length > 1) {
          do {
            newIndex = Math.floor(Math.random() * factsData.length);
          } while (newIndex === lastIndex);
        } else {
          newIndex = 0;
        }
        lastIndex = newIndex;
        return factsData[newIndex];
      }

      // --------------------------------------------------------------
      // Build image URL using Unsplash Source (reliable, keyword based)
      // Using a fixed width/height to keep layout stable
      // --------------------------------------------------------------
      function getImageUrl(query) {
        // Format: keywords separated by comma (already in our data)
        // Use a fixed size 800x600 for consistent look
        return `https://source.unsplash.com/featured/800x600/?${encodeURIComponent(query)}`;
      }

      // --------------------------------------------------------------
      // Update the UI with a new fact + picture
      // --------------------------------------------------------------
      function displayNewFact() {
        const factObj = pickRandomFact();

        // 1. Update fact text (with a tiny icon prefix)
        factDisplay.innerHTML = `<i>✨</i>${factObj.fact}`;

        // 2. Update image
        //   – set a subtle loading state on image
        factImage.style.opacity = '0.6';
        factImage.src = getImageUrl(factObj.imageQuery);
        // when image loads, bring back full opacity
        factImage.onload = () => {
          factImage.style.opacity = '1';
        };
        // fallback in case of error (show a neutral placeholder)
        factImage.onerror = () => {
          factImage.src = 'https://source.unsplash.com/featured/800x600/?question,mark,abstract';
          factImage.style.opacity = '1';
        };

        // 3. Update counter and increment
        viewedCount++;
        factCounterSpan.textContent = viewedCount;
      }

      // --------------------------------------------------------------
      // Initialize the app with first fact (without incrementing counter)
      // but we want the counter to show 1 after first fact is shown.
      // So we set viewedCount to 0, display fact, then it becomes 1.
      // --------------------------------------------------------------
      function initApp() {
        // First fact:
        const firstFact = pickRandomFact();
        factDisplay.innerHTML = `<i>✨</i>${firstFact.fact}`;
        factImage.src = getImageUrl(firstFact.imageQuery);
        factImage.style.opacity = '1';
        // set counter to 1 (first fact)
        viewedCount = 1;
        factCounterSpan.textContent = viewedCount;
      }

      // --------------------------------------------------------------
      // Event listener for button
      // --------------------------------------------------------------
      newFactBtn.addEventListener('click', displayNewFact);

      // Start the app
      initApp();

      // Preload a few images in background for smoother experience (optional)
      // (just for better UX, no direct impact)
      window.addEventListener('load', () => {
        // gentle preload of a couple of images? not necessary but fine.
      });

      // ensure that if image fails, we keep UI clean
      factImage.addEventListener('error', function handleImageError() {
        // fallback image (abstract)
        this.src = 'https://source.unsplash.com/featured/800x600/?abstract,color';
        this.style.opacity = '1';
      });
    })();
  </script>
</body>
</html>