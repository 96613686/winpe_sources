# Microsoft.VisualStudio.Setup.Engine::Load_0

- ea: `0x8460`
- end: `0x84f9`
- name: `Microsoft.VisualStudio.Setup.Engine::Load_0`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x8380`

## callees

- `0x8460`
- `0x86e0`
- `0x9ba0`
- `0x9d10`
- `0x9fe0`

## string_xrefs

- `0x8488`: `NullManifest`
- `0x84a4`: `Null Uri in Load Catalog`
- `0x84b6`: `manifestUri`

## pseudocode

```c

```

## disassembly

```asm
0x8460  ldarg.0
0x8461  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0x8466  ldarg.1
0x8467  brtrue.s loc_84C1
0x8469  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x846e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x8473  stloc.2
0x8474  dup
0x8475  ldloc.2
0x8476  ldstr    aEngine// "Engine"
0x847b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8480  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x8485  stloc.3
0x8486  dup
0x8487  ldloc.3
0x8488  ldstr    aNullmanifest// "NullManifest"
0x848d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x8492  stloc.1
0x8493  ldarg.0
0x8494  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x8499  dup
0x849a  brtrue.s loc_849F
0x849c  pop
0x849d  br.s     loc_84B6
0x849f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x84a4  ldstr    aNullUriInLoadC// "Null Uri in Load Catalog"
0x84a9  ldloc.1
0x84aa  ldnull
0x84ab  ldnull
0x84ac  ldc.i4.0
0x84ad  ldnull
0x84ae  ldc.i4.0
0x84af  ldnull
0x84b0  ldc.i4.0
0x84b1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x84b6  ldstr    aManifesturi// "manifestUri"
0x84bb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x84c0  throw
0x84c1  ldarg.2
0x84c2  ldnull
0x84c3  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x84c8  brtrue.s loc_84D3
0x84ca  ldarg.3
0x84cb  ldnull
0x84cc  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x84d1  brfalse.s loc_84DE
0x84d3  ldarg.0
0x84d4  ldarg.2
0x84d5  ldarg.3
0x84d6  call     instance string Microsoft.VisualStudio.Setup.Engine::CacheCatalogUsingChannelManager(class [System]System.Uri channelUri, class [System]System.Uri installChannelUri)
0x84db  stloc.0
0x84dc  br.s     loc_84EF
0x84de  ldarg.0
0x84df  ldnull
0x84e0  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Engine::channelPair
0x84e5  ldarg.0
0x84e6  ldarg.1
0x84e7  ldarg.s  4
0x84e9  call     instance string Microsoft.VisualStudio.Setup.Engine::DownloadCatalogUsingManifestUri(class [System]System.Uri manifestUri, valuetype [mscorlib]System.Threading.CancellationToken token)
0x84ee  stloc.0
0x84ef  ldarg.0
0x84f0  ldloc.0
0x84f1  ldarg.s  5
0x84f3  call     instance void Microsoft.VisualStudio.Setup.Engine::Load(string path, [opt] bool skipVerify)
0x84f8  ret
```
