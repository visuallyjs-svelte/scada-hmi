<script>
    import {
        ControlsComponent,
        DiagramProvider, DiagramComponent, DiagramPaletteComponent, ExportControlsComponent
    } from "@visuallyjs/browser-ui-svelte"

    import diagramOptions from './diagram-options'
    import Inspector from "./Inspector.svelte";
    import './index.css'


    let { url = "/dataset.json" } = $props();


</script>

<div class="vjs-shmi-container">
    <DiagramProvider>
		<div style="display:flex;flex: 1;position:relative">
			<DiagramComponent options={diagramOptions} {url}/>
			<ControlsComponent/>
			<Inspector/>
        	<div class="vjs-palette">
            	<DiagramPaletteComponent showLabels={true} iconSize={{width:120,height:120}}/>
        	</div>
		</div>
    </DiagramProvider>
</div>

<style>
    :global(html, body) {
        margin:0;
        padding:0;
        width:100vw;
        height:100vh;
    }
</style>
