<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Campus Hub — Airyonas x YOXNAS</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            400: '#38bdf8',
                            500: '#06b6d4',
                            600: '#0891b2',
                            700: '#0e7490',
                        },
                        yoxnas: {
                            purple: '#a855f7',
                            pink: '#ec4899',
                            glow: 'rgba(168, 85, 247, 0.25)'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap');
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: #090d16;
        }
        .glass-card {
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        .glass-card:hover {
            border-color: rgba(56, 189, 248, 0.3);
        }
        .glow-yoxnas {
            box-shadow: 0 0 25px rgba(168, 85, 247, 0.25);
        }
        .custom-scrollbar::-webkit-scrollbar {
            width: 5px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #334155;
            border-radius: 10px;
        }
    </style>
</head>
<body class="text-slate-100 min-h-screen flex flex-col md:flex-row antialiased custom-scrollbar">

    <!-- Sidebar Navigation -->
    <aside class="w-full md:w-72 bg-slate-950/80 border-b md:border-b-0 md:border-r border-slate-800/80 flex flex-col justify-between flex-shrink-0">
        <div>
            <!-- Header & Brand Credit -->
            <div class="p-5 border-b border-slate-800/80">
                <div class="flex items-center space-x-3 mb-3">
                    <div class="bg-gradient-to-tr from-brand-500 to-yoxnas-purple text-white p-2.5 rounded-xl shadow-lg shadow-brand-500/20">
                        <i class="fa-solid fa-graduation-cap text-xl"></i>
                    </div>
                    <div>
                        <h1 class="font-extrabold text-lg tracking-tight bg-gradient-to-r from-white via-slate-200 to-brand-400 bg-clip-text text-transparent">
                            Campus Hub
                        </h1>
                        <p class="text-[11px] font-medium text-slate-400 flex items-center gap-1">
                            <span>Project Assignment</span>
                            <span class="text-slate-600">•</span>
                            <span class="text-brand-400 font-semibold">v2.0</span>
                        </p>
                    </div>
                </div>

                <!-- Owner Credit Badge -->
                <div class="mt-4 p-2.5 rounded-lg bg-slate-900/90 border border-slate-800 flex items-center justify-between">
                    <div class="flex items-center space-x-2">
                        <div class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></div>
                        <span class="text-xs text-slate-400">Developed by</span>
                    </div>
                    <span class="text-xs font-bold text-slate-200 tracking-wide bg-slate-800 px-2 py-0.5 rounded border border-slate-700">Airyonas</span>
                </div>
            </div>

            <!-- Navigation Links -->
            <nav class="p-4 space-y-1.5">
                <button onclick="switchTab('dashboard')" id="nav-dashboard" class="nav-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-semibold transition bg-brand-500 text-slate-950 shadow-lg shadow-brand-500/20">
                    <i class="fa-solid fa-chart-pie w-5"></i>
                    <span>Dashboard</span>
                </button>
                <button onclick="switchTab('study-groups')" id="nav-study-groups" class="nav-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-semibold text-slate-400 hover:bg-slate-900 hover:text-slate-200 transition">
                    <i class="fa-solid fa-users-viewfinder w-5"></i>
                    <span>Study Groups</span>
                </button>
                <button onclick="switchTab('club-events')" id="nav-club-events" class="nav-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-semibold text-slate-400 hover:bg-slate-900 hover:text-slate-200 transition">
                    <i class="fa-solid fa-calendar-star w-5"></i>
                    <span>Club Events</span>
                </button>
                <button onclick="switchTab('task-tracker')" id="nav-task-tracker" class="nav-btn w-full flex items-center space-x-3 px-4 py-3 rounded-xl text-sm font-semibold text-slate-400 hover:bg-slate-900 hover:text-slate-200 transition">
                    <i class="fa-solid fa-list-check w-5"></i>
                    <span>Task Tracker</span>
                </button>
            </nav>
        </div>

        <!-- YOXNAS Powered Footer Badge -->
        <div class="p-4 border-t border-slate-800/80">
            <div class="p-3 rounded-xl bg-gradient-to-r from-yoxnas-purple/10 to-yoxnas-pink/10 border border-yoxnas-purple/30 text-center">
                <p class="text-[10px] uppercase font-bold tracking-widest text-slate-400 mb-0.5">Powered By</p>
                <p class="text-sm font-black tracking-wider bg-gradient-to-r from-yoxnas-purple via-yoxnas-pink to-brand-400 bg-clip-text text-transparent">
                    YOXNAS
                </p>
            </div>
        </div>
    </aside>

    <!-- Main Content Area -->
    <main class="flex-1 p-4 md:p-8 overflow-y-auto custom-scrollbar">

        <!-- DASHBOARD TAB -->
        <section id="tab-dashboard" class="space-y-6">
            <header class="flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                <div>
                    <div class="flex items-center space-x-2">
                        <h2 class="text-2xl font-black text-slate-100">Project Overview</h2>
                        <span class="text-xs font-bold px-2 py-0.5 rounded bg-yoxnas-purple/20 text-yoxnas-purple border border-yoxnas-purple/40">Airyonas Edition</span>
                    </div>
                    <p class="text-slate-400 text-xs sm:text-sm mt-0.5">Academic portal built for course assignment evaluation.</p>
                </div>
                <div class="flex items-center space-x-3 bg-slate-900 px-3 py-1.5 rounded-xl border border-slate-800 w-fit">
                    <div class="text-right">
                        <p class="text-[10px] text-slate-400 uppercase font-bold">Engine</p>
                        <p class="text-xs font-bold text-yoxnas-pink">YOXNAS Core</p>
                    </div>
                    <i class="fa-solid fa-bolt text-yoxnas-purple text-lg"></i>
                </div>
            </header>

            <!-- Stats Grid -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
                <div class="glass-card p-4 rounded-2xl flex items-center space-x-4">
                    <div class="p-3 bg-brand-500/10 text-brand-400 rounded-xl border border-brand-500/20">
                        <i class="fa-solid fa-clock-rotate-left text-xl"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">Pending Assignments</p>
                        <p id="stat-pending-tasks" class="text-2xl font-black text-slate-100">0</p>
                    </div>
                </div>
                <div class="glass-card p-4 rounded-2xl flex items-center space-x-4">
                    <div class="p-3 bg-emerald-500/10 text-emerald-400 rounded-xl border border-emerald-500/20">
                        <i class="fa-solid fa-user-group text-xl"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">Active Study Groups</p>
                        <p id="stat-joined-groups" class="text-2xl font-black text-slate-100">0</p>
                    </div>
                </div>
                <div class="glass-card p-4 rounded-2xl flex items-center space-x-4">
                    <div class="p-3 bg-yoxnas-purple/10 text-yoxnas-purple rounded-xl border border-yoxnas-purple/20">
                        <i class="fa-solid fa-ticket text-xl"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">RSVPed Events</p>
                        <p id="stat-attending-events" class="text-2xl font-black text-slate-100">0</p>
                    </div>
                </div>
                <div class="glass-card p-4 rounded-2xl flex items-center space-x-4">
                    <div class="p-3 bg-amber-500/10 text-amber-400 rounded-xl border border-amber-500/20">
                        <i class="fa-solid fa-circle-check text-xl"></i>
                    </div>
                    <div>
                        <p class="text-xs text-slate-400 font-medium">Completion Rate</p>
                        <p id="stat-task-progress" class="text-2xl font-black text-slate-100">0%</p>
                    </div>
                </div>
            </div>

            <!-- Analytics Chart & Deadlines -->
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                <div class="lg:col-span-2 glass-card p-5 rounded-2xl">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="font-bold text-slate-200 text-sm sm:text-base">Productivity Velocity</h3>
                        <span class="text-[11px] font-semibold text-slate-400 bg-slate-900 px-2 py-1 rounded border border-slate-800">Weekly Log</span>
                    </div>
                    <div class="h-60">
                        <canvas id="productivityChart"></canvas>
                    </div>
                </div>
                <div class="glass-card p-5 rounded-2xl flex flex-col justify-between">
                    <div>
                        <h3 class="font-bold text-slate-200 text-sm sm:text-base mb-4">Priority Deliverables</h3>
                        <div id="dashboard-deadlines" class="space-y-3">
                            <!-- Populated dynamically -->
                        </div>
                    </div>
                    <div class="mt-4 pt-3 border-t border-slate-800 text-center">
                        <p class="text-[11px] text-slate-500">System architecture configured by <span class="text-slate-300 font-semibold">Airyonas</span></p>
                    </div>
                </div>
            </div>
        </section>

        <!-- STUDY GROUPS TAB -->
        <section id="tab-study-groups" class="hidden space-y-6">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                <div>
                    <h2 class="text-2xl font-black text-slate-100">Study Group Finder</h2>
                    <p class="text-slate-400 text-xs sm:text-sm">Connect with peers for course projects and exam revisions.</p>
                </div>
                <button onclick="openModal('group-modal')" class="bg-gradient-to-r from-brand-500 to-brand-600 hover:from-brand-400 hover:to-brand-500 text-slate-950 font-bold px-4 py-2.5 rounded-xl text-xs sm:text-sm transition flex items-center space-x-2 w-fit shadow-lg shadow-brand-500/20">
                    <i class="fa-solid fa-plus"></i>
                    <span>Create Group</span>
                </button>
            </div>

            <div class="flex flex-wrap gap-3 glass-card p-3 rounded-2xl">
                <input type="text" id="group-search" oninput="filterGroups()" placeholder="Filter by course code or topic..." class="bg-slate-900/90 border border-slate-800 rounded-xl px-3.5 py-2 text-xs sm:text-sm text-slate-200 focus:outline-none focus:border-brand-500 flex-1 min-w-[200px]">
                <select id="group-format-filter" onchange="filterGroups()" class="bg-slate-900/90 border border-slate-800 rounded-xl px-3.5 py-2 text-xs sm:text-sm text-slate-200 focus:outline-none focus:border-brand-500">
                    <option value="All">All Formats</option>
                    <option value="In-Person">In-Person</option>
                    <option value="Online">Online</option>
                    <option value="Hybrid">Hybrid</option>
                </select>
            </div>

            <div id="groups-list" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                <!-- Dynamic Content -->
            </div>
        </section>

        <!-- CLUB EVENTS TAB -->
        <section id="tab-club-events" class="hidden space-y-6">
            <div>
                <h2 class="text-2xl font-black text-slate-100">Campus Events & Clubs</h2>
                <p class="text-slate-400 text-xs sm:text-sm">Explore extracurricular workshops and student showcase meetings.</p>
            </div>
            <div id="events-list" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Dynamic Content -->
            </div>
        </section>

        <!-- TASK TRACKER TAB -->
        <section id="tab-task-tracker" class="hidden space-y-6">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4">
                <div>
                    <h2 class="text-2xl font-black text-slate-100">Assignment Task Tracker</h2>
                    <p class="text-slate-400 text-xs sm:text-sm">Manage assignment milestones and deadlines efficiently.</p>
                </div>
                <button onclick="openModal('task-modal')" class="bg-gradient-to-r from-brand-500 to-brand-600 hover:from-brand-400 hover:to-brand-500 text-slate-950 font-bold px-4 py-2.5 rounded-xl text-xs sm:text-sm transition flex items-center space-x-2 w-fit shadow-lg shadow-brand-500/20">
                    <i class="fa-solid fa-plus"></i>
                    <span>Add Task</span>
                </button>
            </div>

            <div class="glass-card rounded-2xl overflow-hidden">
                <div id="tasks-list" class="divide-y divide-slate-800/80">
                    <!-- Dynamic Content -->
                </div>
            </div>
        </section>

    </main>

    <!-- Create Group Modal -->
    <div id="group-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-md hidden flex items-center justify-center p-4 z-50">
        <div class="glass-card border border-slate-700 rounded-2xl w-full max-w-md p-6 space-y-4">
            <div class="flex justify-between items-center border-b border-slate-800 pb-3">
                <h3 class="text-base font-bold text-slate-100">Create Study Group</h3>
                <button onclick="closeModal('group-modal')" class="text-slate-400 hover:text-white"><i class="fa-solid fa-xmark text-base"></i></button>
            </div>
            <form id="group-form" onsubmit="handleCreateGroup(event)" class="space-y-3">
                <div>
                    <label class="block text-xs font-semibold text-slate-400 mb-1">Course Code</label>
                    <input type="text" id="g-course" required placeholder="e.g. CS101" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-400 mb-1">Topic / Title</label>
                    <input type="text" id="g-title" required placeholder="e.g. Exam Practice & Peer Review" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1">Format</label>
                        <select id="g-format" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                            <option value="In-Person">In-Person</option>
                            <option value="Online">Online</option>
                            <option value="Hybrid">Hybrid</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1">Max Seats</label>
                        <input type="number" id="g-seats" required min="2" max="20" value="6" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                    </div>
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-400 mb-1">Location / Discord Link</label>
                    <input type="text" id="g-location" required placeholder="e.g. Science Library Room 4B" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                </div>
                <button type="submit" class="w-full bg-brand-500 hover:bg-brand-400 text-slate-950 font-bold py-2.5 rounded-xl text-xs transition mt-2">Create Group</button>
            </form>
        </div>
    </div>

    <!-- Create Task Modal -->
    <div id="task-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-md hidden flex items-center justify-center p-4 z-50">
        <div class="glass-card border border-slate-700 rounded-2xl w-full max-w-md p-6 space-y-4">
            <div class="flex justify-between items-center border-b border-slate-800 pb-3">
                <h3 class="text-base font-bold text-slate-100">Add Assignment Task</h3>
                <button onclick="closeModal('task-modal')" class="text-slate-400 hover:text-white"><i class="fa-solid fa-xmark text-base"></i></button>
            </div>
            <form id="task-form" onsubmit="handleCreateTask(event)" class="space-y-3">
                <div>
                    <label class="block text-xs font-semibold text-slate-400 mb-1">Task Title</label>
                    <input type="text" id="t-title" required placeholder="e.g. Complete Lab Report" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                </div>
                <div>
                    <label class="block text-xs font-semibold text-slate-400 mb-1">Subject</label>
                    <input type="text" id="t-subject" required placeholder="e.g. PHYS102" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                </div>
                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1">Due Date</label>
                        <input type="date" id="t-duedate" required class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                    </div>
                    <div>
                        <label class="block text-xs font-semibold text-slate-400 mb-1">Priority</label>
                        <select id="t-priority" class="w-full bg-slate-900 border border-slate-800 rounded-xl px-3 py-2 text-xs text-slate-200 focus:outline-none focus:border-brand-500">
                            <option value="High">High</option>
                            <option value="Medium" selected>Medium</option>
                            <option value="Low">Low</option>
                        </select>
                    </div>
                </div>
                <button type="submit" class="w-full bg-brand-500 hover:bg-brand-400 text-slate-950 font-bold py-2.5 rounded-xl text-xs transition mt-2">Add Assignment</button>
            </form>
        </div>
    </div>

    <!-- Application Script Engine -->
    <script>
        let state = {
            groups: [
                { id: 1, course: 'CS101', title: 'Data Structures & Algorithms Prep', format: 'In-Person', location: 'Tech Lab 202', filled: 4, max: 6, joined: true },
                { id: 2, course: 'MATH201', title: 'Calculus III Problem Solving', format: 'Online', location: 'Discord #math-hub', filled: 5, max: 5, joined: false },
                { id: 3, course: 'ENG105', title: 'Academic Essay Peer Review', format: 'Hybrid', location: 'Library Room B', filled: 2, max: 4, joined: false }
            ],
            events: [
                { id: 1, club: 'Robotics Club', title: 'AI Autonomous Systems Demo', category: 'Tech', date: 'Oct 28, 2026', time: '4:00 PM', location: 'Innovation Atrium', rsvp: true, attendees: 42 },
                { id: 2, club: 'Creative Arts', title: 'UI/UX Interactive Workshop', category: 'Design', date: 'Oct 30, 2026', time: '5:30 PM', location: 'Studio 3B', rsvp: false, attendees: 29 },
                { id: 3, club: 'Debate Club', title: 'Inter-College Campus Debate', category: 'Academic', date: 'Nov 02, 2026', time: '6:00 PM', location: 'Main Auditorium', rsvp: false, attendees: 61 }
            ],
            tasks: [
                { id: 1, title: 'Calculus Assignment #4', subject: 'MATH201', dueDate: '2026-10-24', priority: 'High', completed: false },
                { id: 2, title: 'Read Systems Architecture Ch 3', subject: 'CS101', dueDate: '2026-10-26', priority: 'Medium', completed: true },
                { id: 3, title: 'Draft Research Proposal Outline', subject: 'ENG105', dueDate: '2026-10-29', priority: 'Low', completed: false }
            ]
        };

        function switchTab(tabId) {
            document.querySelectorAll('main > section').forEach(sec => sec.classList.add('hidden'));
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('bg-brand-500', 'text-slate-950', 'shadow-lg', 'shadow-brand-500/20');
                btn.classList.add('text-slate-400');
            });

            document.getElementById(`tab-${tabId}`).classList.remove('hidden');
            const activeBtn = document.getElementById(`nav-${tabId}`);
            activeBtn.classList.add('bg-brand-500', 'text-slate-950', 'shadow-lg', 'shadow-brand-500/20');
            activeBtn.classList.remove('text-slate-400');

            if (tabId === 'dashboard') updateDashboard();
        }

        function openModal(id) { document.getElementById(id).classList.remove('hidden'); }
        function closeModal(id) { document.getElementById(id).classList.add('hidden'); }

        function renderGroups(groupsToRender = state.groups) {
            const container = document.getElementById('groups-list');
            container.innerHTML = groupsToRender.map(g => `
                <div class="glass-card p-5 rounded-2xl flex flex-col justify-between space-y-4">
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-brand-500/10 text-brand-400 border border-brand-500/20">${g.course}</span>
                            <span class="text-xs text-slate-400">${g.format}</span>
                        </div>
                        <h3 class="font-bold text-slate-100 text-sm">${g.title}</h3>
                        <p class="text-xs text-slate-400 mt-1"><i class="fa-solid fa-location-dot mr-1 text-slate-500"></i>${g.location}</p>
                    </div>
                    <div>
                        <div class="flex justify-between text-xs text-slate-400 mb-1">
                            <span>Capacity</span>
                            <span>${g.filled}/${g.max}</span>
                        </div>
                        <div class="w-full bg-slate-900 rounded-full h-1.5 mb-4">
                            <div class="bg-brand-500 h-1.5 rounded-full" style="width: ${(g.filled / g.max) * 100}%"></div>
                        </div>
                        <button onclick="toggleGroupJoin(${g.id})" class="w-full py-2 rounded-xl text-xs font-bold transition ${g.joined ? 'bg-slate-800 text-slate-200 border border-slate-700' : (g.filled >= g.max ? 'bg-slate-900 text-slate-600 cursor-not-allowed' : 'bg-brand-500 text-slate-950 hover:bg-brand-400')}">
                            ${g.joined ? 'Leave Group' : (g.filled >= g.max ? 'Full' : 'Join Group')}
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function filterGroups() {
            const query = document.getElementById('group-search').value.toLowerCase();
            const format = document.getElementById('group-format-filter').value;
            const filtered = state.groups.filter(g => {
                const matchesSearch = g.course.toLowerCase().includes(query) || g.title.toLowerCase().includes(query);
                const matchesFormat = format === 'All' || g.format === format;
                return matchesSearch && matchesFormat;
            });
            renderGroups(filtered);
        }

        function toggleGroupJoin(id) {
            const group = state.groups.find(g => g.id === id);
            if (!group) return;

            if (group.joined) { group.joined = false; group.filled--; }
            else if (group.filled < group.max) { group.joined = true; group.filled++; }
            renderGroups();
            updateStats();
        }

        function handleCreateGroup(e) {
            e.preventDefault();
            const newGroup = {
                id: Date.now(),
                course: document.getElementById('g-course').value.toUpperCase(),
                title: document.getElementById('g-title').value,
                format: document.getElementById('g-format').value,
                location: document.getElementById('g-location').value,
                filled: 1,
                max: parseInt(document.getElementById('g-seats').value),
                joined: true
            };
            state.groups.unshift(newGroup);
            renderGroups();
            updateStats();
            closeModal('group-modal');
            document.getElementById('group-form').reset();
        }

        function renderEvents() {
            const container = document.getElementById('events-list');
            container.innerHTML = state.events.map(ev => `
                <div class="glass-card rounded-2xl overflow-hidden flex flex-col justify-between">
                    <div class="p-5 space-y-3">
                        <div class="flex items-center justify-between">
                            <span class="text-[10px] font-bold px-2 py-0.5 rounded bg-yoxnas-purple/20 text-yoxnas-purple border border-yoxnas-purple/30">${ev.category}</span>
                            <span class="text-xs text-slate-400"><i class="fa-solid fa-users text-slate-500 mr-1"></i>${ev.attendees}</span>
                        </div>
                        <h3 class="font-bold text-slate-100 text-sm sm:text-base">${ev.title}</h3>
                        <p class="text-xs font-semibold text-brand-400">${ev.club}</p>
                        <div class="space-y-1 text-xs text-slate-400">
                            <p><i class="fa-regular fa-calendar mr-2 text-slate-500"></i>${ev.date} at ${ev.time}</p>
                            <p><i class="fa-solid fa-location-dot mr-2 text-slate-500"></i>${ev.location}</p>
                        </div>
                    </div>
                    <div class="p-5 pt-0">
                        <button onclick="toggleRSVP(${ev.id})" class="w-full py-2.5 rounded-xl text-xs font-bold transition ${ev.rsvp ? 'bg-emerald-500/20 border border-emerald-500/30 text-emerald-400' : 'bg-brand-500 text-slate-950 hover:bg-brand-400'}">
                            ${ev.rsvp ? '<i class="fa-solid fa-check mr-1"></i> RSVPed' : 'RSVP Event'}
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function toggleRSVP(id) {
            const ev = state.events.find(e => e.id === id);
            if (!ev) return;
            ev.rsvp = !ev.rsvp;
            ev.attendees += ev.rsvp ? 1 : -1;
            renderEvents();
            updateStats();
        }

        function renderTasks() {
            const container = document.getElementById('tasks-list');
            if (state.tasks.length === 0) {
                container.innerHTML = `<div class="p-6 text-center text-slate-500 text-xs font-medium">No tasks found. Click Add Task to create one.</div>`;
                return;
            }

            container.innerHTML = state.tasks.map(t => `
                <div class="p-4 flex items-center justify-between hover:bg-slate-900/60 transition">
                    <div class="flex items-center space-x-3">
                        <input type="checkbox" ${t.completed ? 'checked' : ''} onchange="toggleTaskStatus(${t.id})" class="w-4 h-4 rounded text-brand-500 focus:ring-0 bg-slate-900 border-slate-700 cursor-pointer">
                        <div>
                            <p class="text-xs sm:text-sm font-semibold ${t.completed ? 'line-through text-slate-500' : 'text-slate-200'}">${t.title}</p>
                            <div class="flex items-center space-x-2 mt-0.5">
                                <span class="text-[10px] font-bold text-slate-400">${t.subject}</span>
                                <span class="text-slate-600">•</span>
                                <span class="text-[10px] text-slate-400">Due ${t.dueDate}</span>
                            </div>
                        </div>
                    </div>
                    <div class="flex items-center space-x-3">
                        <span class="text-[10px] font-bold px-2 py-0.5 rounded ${t.priority === 'High' ? 'bg-red-500/10 text-red-400 border border-red-500/20' : t.priority === 'Medium' ? 'bg-amber-500/10 text-amber-400 border border-amber-500/20' : 'bg-slate-800 text-slate-400 border border-slate-700'}">${t.priority}</span>
                        <button onclick="deleteTask(${t.id})" class="text-slate-500 hover:text-red-400 text-xs transition"><i class="fa-solid fa-trash-can"></i></button>
                    </div>
                </div>
            `).join('');
        }

        function toggleTaskStatus(id) {
            const t = state.tasks.find(task => task.id === id);
            if (!t) return;
            t.completed = !t.completed;
            renderTasks();
            updateStats();
        }

        function deleteTask(id) {
            state.tasks = state.tasks.filter(t => t.id !== id);
            renderTasks();
            updateStats();
        }

        function handleCreateTask(e) {
            e.preventDefault();
            const newTask = {
                id: Date.now(),
                title: document.getElementById('t-title').value,
                subject: document.getElementById('t-subject').value.toUpperCase(),
                dueDate: document.getElementById('t-duedate').value,
                priority: document.getElementById('t-priority').value,
                completed: false
            };
            state.tasks.unshift(newTask);
            renderTasks();
            updateStats();
            closeModal('task-modal');
            document.getElementById('task-form').reset();
        }

        function updateStats() {
            const pending = state.tasks.filter(t => !t.completed).length;
            const completed = state.tasks.filter(t => t.completed).length;
            const total = state.tasks.length;
            const progress = total > 0 ? Math.round((completed / total) * 100) : 0;

            document.getElementById('stat-pending-tasks').innerText = pending;
            document.getElementById('stat-joined-groups').innerText = state.groups.filter(g => g.joined).length;
            document.getElementById('stat-attending-events').innerText = state.events.filter(e => e.rsvp).length;
            document.getElementById('stat-task-progress').innerText = `${progress}%`;
        }

        function updateDashboard() {
            updateStats();
            const deadlineContainer = document.getElementById('dashboard-deadlines');
            const pendingTasks = state.tasks.filter(t => !t.completed).slice(0, 3);

            if (pendingTasks.length === 0) {
                deadlineContainer.innerHTML = `<p class="text-xs text-slate-500">No active assignment deadlines pending.</p>`;
            } else {
                deadlineContainer.innerHTML = pendingTasks.map(t => `
                    <div class="p-3 bg-slate-900/90 rounded-xl flex items-center justify-between border border-slate-800">
                        <div>
                            <p class="text-xs font-bold text-slate-200">${t.title}</p>
                            <p class="text-[10px] text-slate-400 mt-0.5">${t.subject} • Due ${t.dueDate}</p>
                        </div>
                        <span class="text-[10px] font-bold px-2 py-0.5 rounded ${t.priority === 'High' ? 'bg-red-500/10 text-red-400 border border-red-500/20' : 'bg-slate-800 text-slate-300'}">${t.priority}</span>
                    </div>
                `).join('');
            }
        }

        function initChart() {
            const ctx = document.getElementById('productivityChart').getContext('2d');
            new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
                    datasets: [
                        {
                            label: 'Study Hours',
                            data: [4, 5, 3, 6, 4, 7, 3],
                            backgroundColor: '#06b6d4',
                            borderRadius: 6
                        },
                        {
                            label: 'Tasks Cleared',
                            data: [2, 3, 1, 5, 3, 4, 2],
                            backgroundColor: '#a855f7',
                            borderRadius: 6
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { labels: { color: '#94a3b8', font: { size: 10, weight: 'bold' } } }
                    },
                    scales: {
                        x: { ticks: { color: '#64748b' }, grid: { display: false } },
                        y: { ticks: { color: '#64748b' }, grid: { color: 'rgba(255,255,255,0.05)' } }
                    }
                }
            });
        }

        window.onload = function() {
            renderGroups();
            renderEvents();
            renderTasks();
            updateDashboard();
            initChart();
        };
    </script>
</body>
</html>
