<script lang="ts">
	import { ArrowUpRight, FileUp, Trophy, Calendar, type Icon as IconType } from 'lucide-svelte';
	interface ActionItem {
		caption: string;
		href: string;
		icon: typeof IconType;
	}
	const items: ActionItem[] = [
		{
			caption: 'Attend an event',
			href: '/events',
			icon: Calendar
		},
		{
			caption: 'Apply for a subteam',
			href: 'https://airtable.com/appnQbDvEpMwKK4Ww/paguAHSYAoOhH13CT/form',
			icon: FileUp
		},
		{
			caption: 'See our success',
			href: '/competition',
			icon: Trophy
		}
	];
</script>

<div class="space-x mt-25">
	<h1 class="type-display">Get involved</h1>

	<ul class="sm:flex justify-center m-0 list-none gap-2 p-2">
		{#each items as item}
			{@const Icon = item.icon}
			<li class="flex-1">
				<a
					class="block h-full select-none rounded-sm p-3 decoration-none border-gray-4 dark:border-graydark-4 border border-solid hover:border-gray-5 dark:hover:border-graydark-5 hover:background-3 flex flex-col transition-colors"
					href={item.href}
				>
					<div class="type-heading-1 text text-center hover">
						<Icon size={20} class="mr-1" />
						{item.caption}
						<ArrowUpRight size={20} />
					</div>
				</a>
			</li>
		{/each}
	</ul>
</div>
