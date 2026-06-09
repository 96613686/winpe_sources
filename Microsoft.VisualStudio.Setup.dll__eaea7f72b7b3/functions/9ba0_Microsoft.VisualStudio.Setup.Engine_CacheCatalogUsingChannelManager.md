# Microsoft.VisualStudio.Setup.Engine::CacheCatalogUsingChannelManager

- ea: `0x9ba0`
- end: `0x9d06`
- name: `Microsoft.VisualStudio.Setup.Engine::CacheCatalogUsingChannelManager`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x8460`

## callees

- `0x9ba0`
- `0xc970`
- `0x114d0`
- `0x67d00`

## string_xrefs

- `0x9c20`: `services`
- `0x9bdf`: `NullManifest`
- `0x9c0d`: `channelUri`
- `0x9bfb`: `Invalid channels uri in Load Catalog`
- `0x9c7e`: `Unable to cache catalog using channel uri {0}`

## pseudocode

```c

```

## disassembly

```asm
0x9ba0  newobj   instance void <>c__DisplayClass168_0::.ctor()
0x9ba5  dup
0x9ba6  ldarg.0
0x9ba7  stfld    class Microsoft.VisualStudio.Setup.Engine <>c__DisplayClass168_0::<>4__this
0x9bac  ldarg.0
0x9bad  ldarg.1
0x9bae  ldarg.2
0x9baf  call     instance void Microsoft.VisualStudio.Setup.Engine::LoadChannel(class [System]System.Uri channelUri, class [System]System.Uri installChannelUri)
0x9bb4  ldarg.0
0x9bb5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Engine::channelPair
0x9bba  brtrue.s loc_9C18
0x9bbc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9bc1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x9bc6  stloc.s  4
0x9bc8  dup
0x9bc9  ldloc.s  4
0x9bcb  ldstr    aEngine// "Engine"
0x9bd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9bd5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x9bda  stloc.s  5
0x9bdc  dup
0x9bdd  ldloc.s  5
0x9bdf  ldstr    aNullmanifest// "NullManifest"
0x9be4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x9be9  stloc.3
0x9bea  ldarg.0
0x9beb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x9bf0  dup
0x9bf1  brtrue.s loc_9BF6
0x9bf3  pop
0x9bf4  br.s     loc_9C0D
0x9bf6  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x9bfb  ldstr    aInvalidChannel// "Invalid channels uri in Load Catalog"
0x9c00  ldloc.3
0x9c01  ldnull
0x9c02  ldnull
0x9c03  ldc.i4.0
0x9c04  ldnull
0x9c05  ldc.i4.0
0x9c06  ldnull
0x9c07  ldc.i4.0
0x9c08  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x9c0d  ldstr    aChanneluri// "channelUri"
0x9c12  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9c17  throw
0x9c18  ldnull
0x9c19  stloc.0
0x9c1a  ldarg.0
0x9c1b  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x9c20  ldstr    aServices// "services"
0x9c25  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x9c2a  dup
0x9c2b  ldarg.0
0x9c2c  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Engine::services
0x9c31  ldc.i4.1
0x9c32  call     T0x2B000069
0x9c37  stfld    class Microsoft.VisualStudio.Setup.IChannelManager <>c__DisplayClass168_0::channelManager
0x9c3c  dup
0x9c3d  ldfld    class Microsoft.VisualStudio.Setup.IChannelManager <>c__DisplayClass168_0::channelManager
0x9c42  ldarg.0
0x9c43  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Engine::channelPair
0x9c48  ldloca.s 1
0x9c4a  ldloca.s 2
0x9c4c  callvirt instance void Microsoft.VisualStudio.Setup.IChannelManager::GetCatalogPathsForChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, [out] string& channelCatalogFileName, [out] string& installChannelCatalogFileName)
0x9c51  ldarg.0
0x9c52  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Engine::channelPair
0x9c57  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x9c5c  brfalse.s loc_9C62
0x9c5e  ldloc.2
0x9c5f  stloc.0
0x9c60  br.s     loc_9C64
0x9c62  ldloc.1
0x9c63  stloc.0
0x9c64  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> <>c__DisplayClass168_0::<CacheCatalogUsingChannelManager>b__0()
0x9c6a  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x9c6f  call     T0x2B00006A
0x9c74  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<bool>::get_Result()
0x9c79  brtrue   loc_9D04
0x9c7e  ldstr    aUnableToCacheC// "Unable to cache catalog using channel u"...
0x9c83  ldarg.1
0x9c84  call     string [mscorlib]System.String::Format(string, object)
0x9c89  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9c8e  stloc.s  6
0x9c90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x9c95  dup
0x9c96  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::CATALOGURIPROPERTY
0x9c9b  ldarg.1
0x9c9c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9ca1  dup
0x9ca2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x9ca7  ldstr    aEngine// "Engine"
0x9cac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9cb1  dup
0x9cb2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x9cb7  ldstr    aCatalogload// "CatalogLoad"
0x9cbc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x9cc1  stloc.s  7
0x9cc3  ldarg.0
0x9cc4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Engine::telemetry
0x9cc9  dup
0x9cca  brtrue.s loc_9CCF
0x9ccc  pop
0x9ccd  br.s     loc_9CE8
0x9ccf  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x9cd4  ldstr    aLoadCatalogFai// "Load Catalog Failure"
0x9cd9  ldloc.s  7
0x9cdb  ldloc.s  6
0x9cdd  ldnull
0x9cde  ldc.i4.0
0x9cdf  ldnull
0x9ce0  ldc.i4.0
0x9ce1  ldnull
0x9ce2  ldc.i4.0
0x9ce3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x9ce8  ldarg.0
0x9ce9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0x9cee  ldloc.s  6
0x9cf0  ldloc.s  6
0x9cf2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9cf7  call     T0x2B000003
0x9cfc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x9d01  ldloc.s  6
0x9d03  throw
0x9d04  ldloc.0
0x9d05  ret
```
