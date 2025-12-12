<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-primary-600">
				<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="w-7 h-7">
					<circle cx="12" cy="12" r="10"/>
					<path d="M12 2v20M2 12h20"/>
					<circle cx="12" cy="12" r="3" fill="currentColor"/>
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Atlas Core</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">Documentation</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Get Started</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.clock}
				<span>AI-Powered Knowledge Capture</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				Capture tribal knowledge. Find it instantly.
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				Screen recording and AI-powered search that turns your team's expertise into searchable, actionable knowledge.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your work email" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-gray-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Start your free trial,<br>No credit card required.
				</div>
			</div>

			<!-- App Screenshot Placeholder -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl bg-white overflow-hidden aspect-[16/10] mb-12 group">
				<!-- This represents the complex app interface -->
				<div class="absolute inset-0 bg-gray-50 flex">
					<!-- Sidebar -->
					<div class="w-64 border-r border-gray-200 bg-white p-4 hidden md:flex flex-col gap-4">
						<div class="h-8 w-full bg-gray-100 rounded animate-pulse"></div>
						<div class="space-y-2">
							<div class="h-4 w-3/4 bg-gray-100 rounded"></div>
							<div class="h-4 w-1/2 bg-gray-100 rounded"></div>
							<div class="h-4 w-5/6 bg-gray-100 rounded"></div>
						</div>
					</div>
					<!-- Main Content -->
					<div class="flex-1 p-6">
						<div class="h-8 w-1/3 bg-gray-100 rounded mb-6"></div>
						<div class="space-y-4">
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm">
								<div class="flex gap-3 mb-3">
									<div class="w-8 h-8 rounded-full bg-gray-200"></div>
									<div class="space-y-1">
										<div class="h-3 w-24 bg-gray-200 rounded"></div>
										<div class="h-3 w-16 bg-gray-100 rounded"></div>
									</div>
								</div>
								<div class="h-2 w-full bg-gray-100 rounded mb-2"></div>
								<div class="h-2 w-5/6 bg-gray-100 rounded"></div>
							</div>
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm"></div>
						</div>
					</div>
				</div>
				
				<!-- Overlay text to indicate it's a screenshot -->
				<div class="absolute inset-0 flex items-center justify-center bg-black/5 opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none">
					<span class="bg-white px-4 py-2 rounded-full shadow-sm text-sm font-medium">App Interface</span>
				</div>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.camera}
					<span>Screen Recording</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.search}
					<span>AI Search</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.memory}
					<span>Knowledge Base</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.shield}
					<span>Compliance Ready</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-lg leading-tight">
				Stop losing critical knowledge. Start building your team's intelligence layer.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.camera}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Instant Recording</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Capture screens, meetings, and workflows with one click</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.search}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">AI-Powered Search</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Find any moment, conversation, or decision in seconds</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Smart Insights</h3>
						<p class="text-sm text-gray-600 leading-relaxed">AI extracts key decisions, action items, and patterns</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Compliance Built-In</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Automated workflows meet regulatory requirements</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.speedometer}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Fast Integration</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Plug-and-play setup, works with your existing tools</p>
					</div>
				</div>
			</div>
		</section>

		<!-- AI Search Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Powered by AI
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Search like you think
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Natural language search that understands context. Find the exact moment, decision, or conversation you need.
				</p>
			</div>

			<div class="bg-primary-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Search Interface -->
					<div class="relative bg-white rounded-2xl shadow-lg p-6 overflow-hidden min-h-[300px]">
						<div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-primary-500 to-primary-600"></div>
						<div class="flex items-center gap-3 mb-6">
							<div class="w-10 h-10 rounded-full bg-primary-600 flex items-center justify-center text-white">
								{@html icons.search}
							</div>
							<div>
								<div class="font-bold text-gray-900">Search Query</div>
								<div class="text-xs text-primary-600 font-medium uppercase tracking-wider">Natural Language</div>
							</div>
						</div>
						<div class="space-y-4 text-sm">
							<div class="bg-gray-50 p-4 rounded-xl text-gray-800 border border-gray-200">
								<p class="font-medium mb-2">"Show me when Sarah explained the new deployment process"</p>
							</div>
							<div class="space-y-2">
								<div class="flex items-center gap-2 text-xs text-gray-600">
									<div class="w-2 h-2 rounded-full bg-primary-500"></div>
									<span>Found in 3 recordings</span>
								</div>
								<div class="flex items-center gap-2 text-xs text-gray-600">
									<div class="w-2 h-2 rounded-full bg-primary-500"></div>
									<span>2 team meetings, 1 demo session</span>
								</div>
								<div class="flex items-center gap-2 text-xs text-gray-600">
									<div class="w-2 h-2 rounded-full bg-primary-500"></div>
									<span>Extracted 5 action items</span>
								</div>
							</div>
						</div>
						<div class="mt-6">
							<button class="w-full py-2 bg-primary-600 text-white font-medium rounded-lg hover:bg-primary-700 transition-colors">
								View Results
							</button>
						</div>
					</div>

					<!-- Right Visual: Results Interface -->
					<div class="bg-white rounded-2xl shadow-lg p-6 min-h-[300px] flex flex-col">
						<div class="flex items-center gap-2 mb-4 text-xs text-gray-400 border-b border-gray-100 pb-2">
							<div class="w-2 h-2 rounded-full bg-primary-500"></div>
							<span>3 results found in 0.3s</span>
						</div>
						<div class="flex-1 space-y-4">
							<div class="border border-gray-100 rounded-lg p-4 hover:border-primary-200 transition-colors cursor-pointer">
								<div class="flex items-center gap-2 mb-2">
									<div class="w-8 h-8 rounded bg-gray-100 flex items-center justify-center text-xs font-bold text-gray-600">
										{@html icons.camera}
									</div>
									<div>
										<h4 class="font-bold text-gray-900 text-sm">Team Standup - Dec 15</h4>
										<div class="text-xs text-gray-500">14:23 - 16:45</div>
									</div>
								</div>
								<p class="text-xs text-gray-600">
									Sarah walks through the new CI/CD pipeline setup, explaining how to deploy to staging and production environments...
								</p>
								<div class="flex gap-2 mt-3">
									<span class="bg-primary-100 text-primary-700 px-2 py-1 rounded text-xs font-medium">deployment</span>
									<span class="bg-primary-100 text-primary-700 px-2 py-1 rounded text-xs font-medium">devops</span>
								</div>
							</div>
							<div class="border border-gray-100 rounded-lg p-4 opacity-60">
								<div class="flex items-center gap-2 mb-2">
									<div class="w-8 h-8 rounded bg-gray-100 flex items-center justify-center text-xs font-bold text-gray-600">
										{@html icons.camera}
									</div>
									<div>
										<h4 class="font-bold text-gray-900 text-sm">Product Demo - Dec 12</h4>
										<div class="text-xs text-gray-500">09:15 - 10:30</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Recording Processing -->
				<div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
					<div class="relative mb-8">
						<div class="w-full bg-gray-50 border-none rounded-xl py-4 pl-12 pr-4 text-gray-700 font-medium">
							Recording: Product Strategy Meeting
						</div>
						<div class="absolute left-4 top-1/2 -translate-y-1/2 text-primary-600">
							{@html icons.camera}
						</div>
						<div class="absolute right-4 top-1/2 -translate-y-1/2 flex gap-2 text-gray-400">
							<div class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></div>
							<span class="text-xs font-medium text-gray-600">45:23</span>
						</div>
					</div>

					<div class="flex justify-center mb-8">
						<span class="bg-primary-100 text-primary-700 text-xs px-3 py-1 rounded-full font-medium">Processing with AI</span>
					</div>

					<div class="bg-primary-50/50 rounded-xl p-6 border border-primary-100">
						<div class="space-y-3">
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-primary-500 animate-pulse"></div>
								<span class="text-sm text-gray-700">Transcribing audio</span>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500 mt-1"></div>
								<div class="text-sm text-gray-700">
									<span class="font-medium">Extracted</span> 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">12 action items</span> 
									and identified 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">3 key decisions</span> 
									from the discussion.
									<p class="text-xs text-gray-500 mt-1 max-w-md">AI detected mentions of Q4 roadmap, feature prioritization, and customer feedback themes.</p>
								</div>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500"></div>
								<span class="text-sm text-gray-700">Tagged with <span class="bg-primary-600 text-white px-2 py-0.5 rounded text-xs font-bold">strategy</span> <span class="bg-primary-600 text-white px-2 py-0.5 rounded text-xs font-bold">product</span></span>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full border-2 border-gray-300 border-t-gray-500 animate-spin"></div>
								<span class="text-sm text-gray-500">Indexing for search...</span>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					AI understands context, extracts insights, and surfaces exactly what you need—turning hours of recordings into searchable, actionable knowledge.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.sparkles}
						<span>Automatic transcription</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.target}
						<span>Extract action items</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.plus}
						<span>Smart tagging & categorization</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.layout}
						<span>Connect related recordings</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.maximize}
						<span>Summarize key decisions</span>
					</div>
					<div class="flex items-center gap-3 text-primary-700 font-medium">
						{@html icons.search}
						<span>Semantic search across all content</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Workflows Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Automation
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Workflows that scale
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Automated compliance workflows, quality checks, and knowledge distribution—built for teams that need to move fast.
				</p>
			</div>

			<div class="bg-gray-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto">
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8">
						<div class="bg-primary-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-primary-800 mb-1">Active</div>
							<div class="text-2xl font-bold text-primary-900">24</div>
						</div>
						<div class="bg-green-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-green-800 mb-1">Completed</div>
							<div class="text-2xl font-bold text-green-900">156</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Pending</div>
							<div class="text-2xl font-bold text-gray-900">8</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Total</div>
							<div class="text-2xl font-bold text-gray-900">188</div>
						</div>
					</div>

					<!-- Workflow List -->
					<div class="space-y-6">
						<div>
							<div class="text-xs font-bold text-primary-600 mb-2 tracking-wide">ACTIVE WORKFLOWS</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-primary-500 flex items-center justify-center cursor-pointer">
									<div class="w-2 h-2 rounded-full bg-primary-500"></div>
								</div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">SOC 2 Compliance Review</h4>
									<p class="text-xs text-gray-500 mt-1">Automated audit trail generation for all system access and changes. Next review in 3 days.</p>
									<div class="text-xs text-primary-600 mt-1 font-medium">IN PROGRESS · 87% COMPLETE</div>
								</div>
							</div>
						</div>

						<div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-primary-500 group-hover:border-primary-600 cursor-pointer">
									<div class="w-2 h-2 rounded-full bg-primary-500 ml-0.5 mt-0.5"></div>
								</div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Onboarding Knowledge Transfer</h4>
									<p class="text-xs text-gray-500 mt-1">Automatically share relevant recordings with new team members based on their role.</p>
									<div class="flex gap-2 text-xs text-gray-400 mt-1">
										<span>3 NEW MEMBERS</span>
										<span>•</span>
										<span class="flex items-center gap-1">{@html icons.repeat} AUTOMATED</span>
									</div>
								</div>
							</div>
						</div>

						<div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-green-500 cursor-pointer">
									{@html icons.check}
								</div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Weekly Team Sync Distribution</h4>
									<p class="text-xs text-gray-500 mt-1">Summaries and action items sent to all stakeholders automatically.</p>
									<div class="text-xs text-green-600 mt-1 font-medium">COMPLETED · SENT TO 12 PEOPLE</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-gray-400 mb-2 tracking-wide">SCHEDULED</div>
							<div class="space-y-3 opacity-60">
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Monthly compliance report generation</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Quarterly knowledge base cleanup</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Customer demo recording archive</span>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						{@html icons.shield}
						<span>Compliance</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.repeat}
						<span>Automation</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.check}
						<span>Quality Checks</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Set it once, let it run forever. Automated workflows ensure compliance, distribute knowledge, and keep your team aligned—without manual effort.
				</p>
			</div>
		</section>

		<!-- Use Cases Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Use cases
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Built for teams that move fast
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					From early-stage startups to manufacturing operations, Atlas Core captures the knowledge that keeps your team aligned and moving forward.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Product Validation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Capture customer interviews and user testing sessions to validate features before building.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Team Onboarding</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">New hires search past recordings to learn processes, decisions, and tribal knowledge.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Compliance Audits</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Automated audit trails for SOC 2, ISO, and regulatory requirements.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Process Documentation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Record workflows once, search and share them forever—no manual documentation needed.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Manufacturing Operations</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Capture equipment setup, troubleshooting, and quality control procedures.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Customer Support</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Record solutions to complex issues and make them searchable for the entire team.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Sales Enablement</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Share winning demos and objection handling techniques across the sales team.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Engineering Handoffs</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Capture technical decisions and architecture discussions for future reference.</p>
				</div>

				<!-- Card 9 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Training Programs</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Build a library of training materials from real work sessions and expert knowledge.</p>
				</div>
				<!-- Card 10 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Quality Assurance</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Document testing procedures and bug reproduction steps with video evidence.</p>
				</div>
				<!-- Card 11 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Remote Collaboration</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Async knowledge sharing for distributed teams across time zones.</p>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="grid grid-cols-2 gap-x-8 gap-y-3 text-xs text-gray-600">
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.sparkles} Getting Started Guide
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.shield} Compliance Documentation
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.download} API Reference
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.target} Integration Guides
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.search} Best Practices
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-primary-400">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="w-full h-full">
							<circle cx="12" cy="12" r="10"/>
							<path d="M12 2v20M2 12h20"/>
							<circle cx="12" cy="12" r="3" fill="currentColor"/>
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 Atlas Core.</p>
						<p>All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-gray-200 text-gray-600 px-3 py-1 rounded text-xs font-medium">
					System Status
				</div>
			</div>
		</footer>

	</main>
</div>

