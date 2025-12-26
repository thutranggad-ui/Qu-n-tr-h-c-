<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Management Mastery Portal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; background: #f3f4f6; }
        .glass { background: rgba(255, 255, 255, 0.95); backdrop-filter: blur(10px); }
        .fade-in { animation: fadeIn 0.5s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .option-card:hover { transform: scale(1.01); transition: 0.2s; }
    </style>
</head>
<body class="min-h-screen text-slate-800">

    <nav class="glass sticky top-0 z-50 border-b border-slate-200 px-6 py-4 flex justify-between items-center">
        <div class="flex items-center gap-2">
            <div class="bg-blue-600 p-2 rounded-lg text-white">
                <i class="fas fa-book-open"></i>
            </div>
            <span class="font-bold text-xl tracking-tight text-slate-900">ManagementHub</span>
        </div>
        <div class="space-x-4">
            <button onclick="showSection('home')" class="text-slate-600 hover:text-blue-600 font-medium">Home</button>
            <button onclick="showSection('study')" class="text-slate-600 hover:text-blue-600 font-medium">Study Guide</button>
            <button onclick="startQuiz()" class="bg-blue-600 text-white px-4 py-2 rounded-full hover:bg-blue-700 transition">Take Quiz</button>
        </div>
    </nav>

    <section id="home" class="max-w-6xl mx-auto px-6 py-16 fade-in">
        <div class="grid md:grid-cols-2 gap-12 items-center">
            <div>
                <h1 class="text-5xl font-extrabold text-slate-900 leading-tight mb-6">
                    Master Planning, Leadership & Motivation.
                </h1>
                <p class="text-lg text-slate-600 mb-8">
                    A comprehensive interactive platform built from your course materials. Review key concepts and test your knowledge with high-difficulty scenarios.
                </p>
                <div class="flex gap-4">
                    <button onclick="startQuiz()" class="bg-blue-600 text-white px-8 py-4 rounded-xl text-lg font-bold shadow-lg shadow-blue-200 hover:bg-blue-700">Start 30-Question Quiz</button>
                    <button onclick="showSection('study')" class="bg-white border border-slate-300 px-8 py-4 rounded-xl text-lg font-bold hover:bg-slate-50">Review Guide</button>
                </div>
            </div>
            <div class="grid grid-cols-2 gap-4">
                <div class="bg-blue-50 p-6 rounded-2xl border border-blue-100">
                    <i class="fas fa-chess text-blue-600 text-2xl mb-4"></i>
                    <h3 class="font-bold text-slate-900">Strategy</h3>
                    <p class="text-sm text-slate-500">Chapters 5 & 6</p>
                </div>
                <div class="bg-purple-50 p-6 rounded-2xl border border-purple-100">
                    <i class="fas fa-sitemap text-purple-600 text-2xl mb-4"></i>
                    <h3 class="font-bold text-slate-900">Organizing</h3>
                    <p class="text-sm text-slate-500">Chapter 7</p>
                </div>
                <div class="bg-green-50 p-6 rounded-2xl border border-green-100">
                    <i class="fas fa-fire text-green-600 text-2xl mb-4"></i>
                    <h3 class="font-bold text-slate-900">Motivation</h3>
                    <p class="text-sm text-slate-500">Chapter 8</p>
                </div>
                <div class="bg-orange-50 p-6 rounded-2xl border border-orange-100">
                    <i class="fas fa-users text-orange-600 text-2xl mb-4"></i>
                    <h3 class="font-bold text-slate-900">Leadership</h3>
                    <p class="text-sm text-slate-500">Chapter 9</p>
                </div>
            </div>
        </div>
    </section>

    <section id="study" class="hidden max-w-4xl mx-auto px-6 py-16 fade-in">
        <h2 class="text-3xl font-bold mb-8 text-center">Quick Revision Guide</h2>
        
        <div class="space-y-12">
            <div class="bg-white p-8 rounded-3xl shadow-sm border border-slate-100">
                <h3 class="text-xl font-bold text-blue-600 mb-4">The Strategic Management Process</h3>
                <p class="text-slate-600 mb-6">Strategic management is a six-step process that encompasses strategy planning, implementation, and evaluation. It starts with identifying the mission and ends with evaluating results.</p>
                <div class="bg-slate-50 p-4 rounded-xl text-center italic text-slate-400">
                    

[Image of Strategic Management Process]

                </div>
            </div>

            <div class="bg-white p-8 rounded-3xl shadow-sm border border-slate-100">
                <h3 class="text-xl font-bold text-green-600 mb-4">Maslow's Hierarchy of Needs</h3>
                <p class="text-slate-600 mb-6">According to Maslow, people are motivated by a hierarchy of five needs. Once a lower-level need is substantially satisfied, it no longer motivates, and the next level becomes dominant.</p>
                <div class="bg-slate-50 p-4 rounded-xl text-center italic text-slate-400">
                    

[Image of Maslow's hierarchy of needs]

                </div>
            </div>
        </div>
    </section>

    <section id="quiz" class="hidden max-w-3xl mx-auto px-6 py-16 fade-in">
        <div class="bg-white p-10 rounded-3xl shadow-xl border border-slate-200">
            <div class="flex justify-between items-center mb-8">
                <div id="quiz-progress" class="text-sm font-bold text-blue-600 uppercase tracking-widest">Question 1 of 30</div>
                <div id="quiz-timer" class="text-slate-400"><i class="far fa-clock mr-2"></i>Practice Mode</div>
            </div>
            
            <div class="w-full bg-slate-100 h-2 rounded-full mb-10">
                <div id="progress-bar" class="bg-blue-600 h-2 rounded-full transition-all duration-500" style="width: 3%"></div>
            </div>

            <h2 id="question-text" class="text-2xl font-bold text-slate-900 mb-8 leading-snug">
                Question loading...
            </h2>

            <div id="options-grid" class="grid gap-4">
                </div>

            <div id="feedback" class="mt-8 p-6 rounded-2xl hidden">
                </div>

            <button id="next-btn" onclick="nextQuestion()" class="hidden mt-8 w-full bg-slate-900 text-white py-4 rounded-2xl font-bold hover:bg-black transition">
                Next Question <i class="fas fa-arrow-right ml-2"></i>
            </button>
        </div>
    </section>

    <section id="results" class="hidden max-w-2xl mx-auto px-6 py-16 text-center fade-in">
        <div class="bg-white p-12 rounded-3xl shadow-2xl">
            <div class="w-24 h-24 bg-green-100 text-green-600 rounded-full flex items-center justify-center text-4xl mx-auto mb-6">
                <i class="fas fa-trophy"></i>
            </div>
            <h2 class="text-4xl font-black text-slate-900 mb-2">Quiz Complete!</h2>
            <p class="text-slate-500 mb-8">Here is how you performed on the management chapters.</p>
            
            <div class="text-7xl font-black text-blue-600 mb-4" id="final-score">0/30</div>
            <p id="score-commentary" class="text-lg font-medium text-slate-700 mb-10"></p>

            <div class="flex gap-4 justify-center">
                <button onclick="startQuiz()" class="bg-blue-600 text-white px-8 py-4 rounded-xl font-bold hover:bg-blue-700">Try Again</button>
                <button onclick="showSection('home')" class="bg-slate-100 text-slate-600 px-8 py-4 rounded-xl font-bold hover:bg-slate-200">Back to Home</button>
            </div>
        </div>
    </section>

    <script>
        const questions = [
            { q: "A manager at a tech startup argues that formal planning is detrimental in their fast-paced industry because it creates rigidity. Which criticism supports this?", a: "Formal plans cannot replace intuition and creativity in a changing environment.", options: ["Planning focuses managers' attention on tomorrow's survival.", "Formal planning replaces the need for creative thinking.", "Formal plans cannot replace intuition and creativity in a changing environment.", "Planning reduces uncertainty leading to complacency."] },
            { q: "Why is planning often considered the 'primary' management function?", a: "It establishes the basis for all other management functions like organizing and controlling.", options: ["It is the only function performed by top-level executives.", "It establishes the basis for all other management functions like organizing and controlling.", "It ensures 100% of goals are met without error.", "It focuses solely on the means rather than the ends."] },
            { q: "What is the significance of the '5W1H' framework in planning?", a: "It provides a comprehensive set of answers (Who, What, Where, When, Why, How) to define a plan.", options: ["It is a tool used exclusively for SWOT analysis.", "It provides a comprehensive set of answers (Who, What, Where, When, Why, How) to define a plan.", "It represents the six steps of the strategic management process.", "It is a goal-setting technique used in MBO."] },
            { q: "In a business plan, which section evaluates broad external changes in economic, political-legal, and technological environments?", a: "Analysis of the Context", options: ["Executive Summary", "Analysis of Opportunity", "Analysis of the Context", "Description of the Business"] },
            { q: "Which of the following best describes the relationship between goals and plans?", a: "Goals are the orientation for other items of planning and represent desired outcomes.", options: ["Plans are the outcomes, while goals outline how to achieve them.", "Goals are the orientation for other items of planning and represent desired outcomes.", "Plans are always informal, while goals must be formal.", "Goals and plans are synonymous."] },
            { q: "A company searches for best practices among non-competitors to improve performance. This is:", a: "Benchmarking", options: ["Strategic Maneuvering", "Benchmarking", "Environmental Scanning", "Operational Planning"] },
            { q: "Which strategy is used by functional departments to support overall competitive strategy?", a: "Functional Strategy", options: ["Corporate Strategy", "Functional Strategy", "Growth Strategy", "Stability Strategy"] },
            { q: "When a firm uses outside suppliers for specific components, it is adopting a:", a: "Modular Organization", options: ["Boundaryless Organization", "Learning Organization", "Modular Organization", "Team Structure"] },
            { q: "What is the primary distinction between 'Authority' and 'Power'?", a: "Authority is a right based on position; Power is the individual’s capacity to influence.", options: ["Authority is ability to influence; Power is a right based on position.", "Authority is a right based on position; Power is the individual’s capacity to influence.", "Authority is held by top managers; Power by subordinates.", "There is no distinction."] },
            { q: "A manager has a very narrow span of control. The structure is likely:", a: "Tall with many hierarchical levels", options: ["Relatively flat", "Large number of subordinates per manager", "Tall with many hierarchical levels", "Highly decentralized"] },
            { q: "Which variable suggests an 'Organic' structure is more effective?", a: "High degree of environmental uncertainty", options: ["Organization is very large in size", "Environment is highly stable", "Technology used is routine", "High degree of environmental uncertainty"] },
            { q: "'Formalization' in an organization refers to:", a: "The degree to which jobs within the organization are standardized.", options: ["The number of subordinates a manager can supervise.", "The degree to which jobs within the organization are standardized.", "The grouping of jobs by product or territory.", "Concentration of decision-making at a single point."] },
            { q: "A 'Cross-functional team' is characterized by:", a: "Employees from different functional specialties working together.", options: ["Employees from different functional specialties working together.", "Strict adherence to the chain of command.", "One person reporting to two different managers.", "Focus on minimizing social interaction."] },
            { q: "Which principle states a person should report to only one manager?", a: "Unity of Command", options: ["Span of Control", "Responsibility", "Unity of Command", "Formalization"] },
            { q: "What is 'Division of Labor' primarily intended to achieve?", a: "Improving efficiency by breaking down jobs into narrow tasks.", options: ["Increasing span of control.", "Enhancing employee empowerment.", "Improving efficiency by breaking down jobs into narrow tasks.", "Reducing the need for formal departmentalization."] },
            { q: "In Maslow’s Hierarchy, which need must be satisfied before moving to the next level?", a: "The need immediately below it in the hierarchy.", options: ["Self-actualization", "The need immediately below it in the hierarchy.", "Social needs", "Growth needs"] },
            { q: "According to Herzberg, which of the following is a 'Motivator'?", a: "Achievement and Recognition", options: ["Salary and Benefits", "Working Conditions", "Achievement and Recognition", "Company Policy"] },
            { q: "An employee motivated by influencing others has a high:", a: "Need for Power (nPow)", options: ["Need for Achievement (nAch)", "Need for Power (nPow)", "Need for Affiliation (nAff)", "Need for Security"] },
            { q: "A manager who believes employees are inherently lazy follows:", a: "Theory X", options: ["Theory Y", "Expectancy Theory", "Theory X", "Equity Theory"] },
            { q: "In Expectancy Theory, what does 'Valence' represent?", a: "The importance or attractiveness an individual places on a potential outcome.", options: ["Perceived probability effort leads to performance.", "Belief performance leads to a reward.", "The importance or attractiveness an individual places on a potential outcome.", "Degree of equity perceived."] },
            { q: "Equity Theory suggests employees compare their ratio against:", a: "A 'referent' other (colleague, etc.)", options: ["Own past performance only", "A 'referent' other (colleague, etc.)", "Organization's profit margins", "Absolute value of salary"] },
            { q: "JCM: Which refers to completion of a whole and identifiable piece of work?", a: "Task Identity", options: ["Skill Variety", "Task Identity", "Task Significance", "Autonomy"] },
            { q: "Expectancy Theory: 'Instrumentality' is the probability that:", a: "A specific level of performance will lead to a desired reward.", options: ["Increased effort results in better performance.", "A specific level of performance will lead to a desired reward.", "The reward will be valuable.", "The employee has necessary skills."] },
            { q: "Ohio State studies dimensions of leader behavior:", a: "Initiating Structure and Consideration", options: ["Employee and Production oriented", "Concern for People and Production", "Initiating Structure and Consideration", "Autocratic and Democratic"] },
            { q: "Fiedler’s Contingency Model measures style using:", a: "Least Preferred Coworker (LPC) questionnaire", options: ["Managerial Grid", "Least Preferred Coworker (LPC) questionnaire", "Situational Readiness Scale", "Path-Goal Survey"] },
            { q: "SLT: 'Telling' style is most effective when followers are:", a: "Unable and unwilling (or insecure).", options: ["Able and willing.", "Unable and unwilling (or insecure).", "Able but unwilling.", "Unable but willing."] },
            { q: "Path-Goal Theory: A leader should be 'Supportive' when:", a: "Tasks are ambiguous and stressful.", options: ["Tasks are highly structured, low self-esteem.", "Subordinates are experienced and autonomous.", "Tasks are ambiguous and stressful.", "Subordinates have internal locus of control."] },
            { q: "What is considered the 'essence' or foundation of leadership today?", a: "Trust", options: ["Power", "Control", "Trust", "Intelligence"] },
            { q: "A leader who inspires followers to transcend self-interest is:", a: "Transformational Leader", options: ["Transactional Leader", "Transformational Leader", "Autocratic Leader", "Laissez-faire Leader"] },
            { q: "Power based on possession of unique skills or knowledge:", a: "Expert Power", options: ["Legitimate Power", "Referent Power", "Coercive Power", "Expert Power"] }
        ];

        let currentIndex = 0;
        let score = 0;
        let canAnswer = true;

        function showSection(id) {
            ['home', 'study', 'quiz', 'results'].forEach(s => document.getElementById(s).classList.add('hidden'));
            document.getElementById(id).classList.remove('hidden');
            window.scrollTo(0,0);
        }

        function startQuiz() {
            currentIndex = 0;
            score = 0;
            showSection('quiz');
            loadQuestion();
        }

        function loadQuestion() {
            canAnswer = true;
            const q = questions[currentIndex];
            document.getElementById('question-text').innerText = q.q;
            document.getElementById('quiz-progress').innerText = `Question ${currentIndex + 1} of ${questions.length}`;
            document.getElementById('progress-bar').style.width = `${((currentIndex + 1) / questions.length) * 100}%`;
            document.getElementById('next-btn').classList.add('hidden');
            document.getElementById('feedback').classList.add('hidden');

            const grid = document.getElementById('options-grid');
            grid.innerHTML = '';
            q.options.forEach(opt => {
                const btn = document.createElement('button');
                btn.className = "option-card text-left p-5 rounded-2xl border-2 border-slate-100 hover:border-blue-400 hover:bg-blue-50 transition font-medium flex justify-between items-center";
                btn.innerHTML = `<span>${opt}</span><i class="far fa-circle text-slate-300"></i>`;
                btn.onclick = () => selectOption(opt, btn);
                grid.appendChild(btn);
            });
        }

        function selectOption(opt, btn) {
            if (!canAnswer) return;
            canAnswer = false;
            
            const correct = questions[currentIndex].a;
            const feedback = document.getElementById('feedback');
            feedback.classList.remove('hidden');

            if (opt === correct) {
                score++;
                btn.classList.add('border-green-500', 'bg-green-50');
                btn.innerHTML = `<span>${opt}</span><i class="fas fa-check-circle text-green-500"></i>`;
                feedback.innerHTML = `<p class="text-green-700 font-bold">Excellent! That's correct.</p>`;
                feedback.className = "mt-8 p-6 rounded-2xl bg-green-50 border border-green-100";
            } else {
                btn.classList.add('border-red-500', 'bg-red-50');
                btn.innerHTML = `<span>${opt}</span><i class="fas fa-times-circle text-red-500"></i>`;
                feedback.innerHTML = `<p class="text-red-700 font-bold mb-1">Incorrect</p><p class="text-red-600">The correct answer is: <strong>${correct}</strong></p>`;
                feedback.className = "mt-8 p-6 rounded-2xl bg-red-50 border border-red-100";
                
                // Highlight correct one
                Array.from(document.getElementById('options-grid').children).forEach(b => {
                    if (b.innerText.includes(correct)) {
                        b.classList.add('border-green-500');
                    }
                });
            }
            document.getElementById('next-btn').classList.remove('hidden');
        }

        function nextQuestion() {
            currentIndex++;
            if (currentIndex < questions.length) {
                loadQuestion();
            } else {
                showResults();
            }
        }

        function showResults() {
            showSection('results');
            document.getElementById('final-score').innerText = `${score}/${questions.length}`;
            const pct = (score / questions.length) * 100;
            let msg = "";
            if (pct >= 90) msg = "Visionary Leader! You've mastered the material.";
            else if (pct >= 70) msg = "Great Strategic Thinking! You're almost there.";
            else msg = "Good start. Review the Study Guide to strengthen your knowledge.";
            document.getElementById('score-commentary').innerText = msg;
        }
    </script>
</body>
</html>
