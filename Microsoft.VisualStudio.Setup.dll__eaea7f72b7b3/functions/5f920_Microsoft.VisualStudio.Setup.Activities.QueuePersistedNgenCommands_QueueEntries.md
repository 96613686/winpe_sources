# Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::QueueEntries

- ea: `0x5f920`
- end: `0x5fbb1`
- name: `Microsoft.VisualStudio.Setup.Activities.QueuePersistedNgenCommands::QueueEntries`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x5f720`

## callees

- `0x305c0`
- `0x30620`
- `0x596d0`
- `0x596f0`
- `0x5f920`
- `0x7c4a0`

## string_xrefs

- `0x5f9cf`: `' resolves outside instance root.`
- `0x5f9df`: `entryPath`
- `0x5fb4e`: `entryPath`
- `0x5fa03`: `Skipping ngen entry '{0}': resolved path is outside instance root.`

## pseudocode

```c

```

## disassembly

```asm
0x5f920  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x5f925  stloc.0
0x5f926  ldloc.0
0x5f927  ldarg.3
0x5f928  stfld    string <>c__DisplayClass3_0::instanceRoot
0x5f92d  ldarg.1
0x5f92e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::get_Count()
0x5f933  brtrue.s loc_5F937
0x5f935  ldc.i4.0
0x5f936  ret
0x5f937  ldarg.0
0x5f938  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f93d  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture> Microsoft.VisualStudio.Setup.Installer.NgenHelper::GetArchitectures(class [mscorlib]System.IServiceProvider serviceProvider)
0x5f942  call     T0x2B0002A1
0x5f947  stloc.1
0x5f948  ldarg.0
0x5f949  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f94e  ldc.i4.0
0x5f94f  call     T0x2B00005B
0x5f954  stloc.2
0x5f955  ldarg.0
0x5f956  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f95b  ldc.i4.0
0x5f95c  call     T0x2B000019
0x5f961  stloc.3
0x5f962  ldarg.0
0x5f963  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f968  ldc.i4.0
0x5f969  call     T0x2B000039
0x5f96e  stloc.s  4
0x5f970  ldc.i4.0
0x5f971  stloc.s  5
0x5f973  ldarg.1
0x5f974  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::GetEnumerator()
0x5f979  stloc.s  6
0x5f97b  br       loc_5FB94
0x5f980  ldloc.s  6
0x5f982  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry>>::get_Current()
0x5f987  ldloca.s 9
0x5f989  ldloca.s 0xA
0x5f98b  call     T0x2B0002A2
0x5f990  ldloc.s  9
0x5f992  stloc.s  7
0x5f994  ldloc.s  0xA
0x5f996  stloc.s  8
0x5f998  ldarga.s 4
0x5f99a  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x5f99f  ldloc.0
0x5f9a0  ldfld    string <>c__DisplayClass3_0::instanceRoot
0x5f9a5  ldloc.s  7
0x5f9a7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5f9ac  stloc.s  0xB
0x5f9ae  ldloc.s  0xB
0x5f9b0  ldloc.0
0x5f9b1  ldfld    string <>c__DisplayClass3_0::instanceRoot
0x5f9b6  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x5f9bb  brtrue.s loc_5FA1D
0x5f9bd  ldloc.s  4
0x5f9bf  brfalse.s loc_5F9F7
0x5f9c1  ldloc.s  4
0x5f9c3  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x5f9c8  ldstr    aNgenEntry// "Ngen entry '"
0x5f9cd  ldloc.s  7
0x5f9cf  ldstr    aResolvesOutsid// "' resolves outside instance root."
0x5f9d4  call     string [mscorlib]System.String::Concat(string, string, string)
0x5f9d9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5f9de  dup
0x5f9df  ldstr    aEntrypath// "entryPath"
0x5f9e4  ldloc.s  7
0x5f9e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5f9eb  ldnull
0x5f9ec  ldnull
0x5f9ed  ldc.i4.0
0x5f9ee  ldnull
0x5f9ef  ldc.i4.0
0x5f9f0  ldnull
0x5f9f1  ldc.i4.0
0x5f9f2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5f9f7  ldarg.0
0x5f9f8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f9fd  dup
0x5f9fe  brtrue.s loc_5FA03
0x5fa00  pop
0x5fa01  br.s     loc_5FA18
0x5fa03  ldstr    aSkippingNgenEn// "Skipping ngen entry '{0}': resolved pat"...
0x5fa08  ldc.i4.1
0x5fa09  newarr   [mscorlib]System.Object
0x5fa0e  dup
0x5fa0f  ldc.i4.0
0x5fa10  ldloc.s  7
0x5fa12  stelem.ref
0x5fa13  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5fa18  leave    loc_5FB94
0x5fa1d  ldloc.s  8
0x5fa1f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry::get_ConfigFiles()
0x5fa24  dup
0x5fa25  brtrue.s loc_5FA2B
0x5fa27  pop
0x5fa28  ldnull
0x5fa29  br.s     loc_5FA77
0x5fa2b  ldloc.0
0x5fa2c  ldfld    class [mscorlib]System.Func`2<string, string> <>c__DisplayClass3_0::<>9__0
0x5fa31  dup
0x5fa32  brtrue.s loc_5FA4C
0x5fa34  pop
0x5fa35  ldloc.0
0x5fa36  ldloc.0
0x5fa37  ldftn    instance string <>c__DisplayClass3_0::<QueueEntries>b__0(string c)
0x5fa3d  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x5fa42  dup
0x5fa43  stloc.s  0xF
0x5fa45  stfld    class [mscorlib]System.Func`2<string, string> <>c__DisplayClass3_0::<>9__0
0x5fa4a  ldloc.s  0xF
0x5fa4c  call     T0x2B000103
0x5fa51  ldloc.0
0x5fa52  ldfld    class [mscorlib]System.Func`2<string, bool> <>c__DisplayClass3_0::<>9__1
0x5fa57  dup
0x5fa58  brtrue.s loc_5FA72
0x5fa5a  pop
0x5fa5b  ldloc.0
0x5fa5c  ldloc.0
0x5fa5d  ldftn    instance bool <>c__DisplayClass3_0::<QueueEntries>b__1(string c)
0x5fa63  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x5fa68  dup
0x5fa69  stloc.s  0x10
0x5fa6b  stfld    class [mscorlib]System.Func`2<string, bool> <>c__DisplayClass3_0::<>9__1
0x5fa70  ldloc.s  0x10
0x5fa72  call     T0x2B0000E4
0x5fa77  stloc.s  0xC
0x5fa79  ldloc.s  8
0x5fa7b  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry::get_Architecture()
0x5fa80  stloc.s  0x12
0x5fa82  ldloc.s  0x12
0x5fa84  brfalse.s loc_5FA8D
0x5fa86  ldloc.s  0x12
0x5fa88  ldc.i4.3
0x5fa89  beq.s    loc_5FA96
0x5fa8b  br.s     loc_5FA9B
0x5fa8d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::.ctor()
0x5fa92  stloc.s  0x11
0x5fa94  br.s     loc_5FAB0
0x5fa96  ldloc.1
0x5fa97  stloc.s  0x11
0x5fa99  br.s     loc_5FAB0
0x5fa9b  ldc.i4.1
0x5fa9c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::.ctor(int32)
0x5faa1  dup
0x5faa2  ldloc.s  8
0x5faa4  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry::get_Architecture()
0x5faa9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::Add(var<u1>)
0x5faae  stloc.s  0x11
0x5fab0  ldloc.s  0x11
0x5fab2  stloc.s  0xD
0x5fab4  ldloc.s  0xD
0x5fab6  call     T0x2B0002A3
0x5fabb  brtrue.s loc_5FAE3
0x5fabd  ldarg.0
0x5fabe  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5fac3  dup
0x5fac4  brtrue.s loc_5FAC9
0x5fac6  pop
0x5fac7  br.s     loc_5FADE
0x5fac9  ldstr    aSkippingNgenEn_0// "Skipping ngen entry '{0}': architecture"...
0x5face  ldc.i4.1
0x5facf  newarr   [mscorlib]System.Object
0x5fad4  dup
0x5fad5  ldc.i4.0
0x5fad6  ldloc.s  7
0x5fad8  stelem.ref
0x5fad9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5fade  leave    loc_5FB94
0x5fae3  ldarg.0
0x5fae4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5fae9  dup
0x5faea  brtrue.s loc_5FAF9
0x5faec  pop
0x5faed  ldarg.0
0x5faee  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5faf3  ldc.i4.1
0x5faf4  call     T0x2B000001
0x5faf9  stloc.s  0xE
0x5fafb  ldloc.s  0xB
0x5fafd  ldloc.s  0xD
0x5faff  ldarg.2
0x5fb00  ldloc.s  8
0x5fb02  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenEntry::get_Dependencies()
0x5fb07  ldloc.s  0xC
0x5fb09  ldloc.2
0x5fb0a  ldloc.s  0xE
0x5fb0c  ldloc.3
0x5fb0d  call     void Microsoft.VisualStudio.Setup.Installer.NgenHelper::QueueBinaryForNgen(string assemblyPath, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture> architectures, int32 ngenPriority, bool ngenDependencies, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> configFilePaths, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, [opt] class Microsoft.VisualStudio.Setup.Services.IMachineService machineService)
0x5fb12  ldloc.s  5
0x5fb14  ldc.i4.1
0x5fb15  add
0x5fb16  stloc.s  5
0x5fb18  leave.s  loc_5FB94
0x5fb1a  pop
0x5fb1b  rethrow
0x5fb1d  stloc.s  0x13
0x5fb1f  ldloc.s  4
0x5fb21  brfalse.s loc_5FB67
0x5fb23  ldloc.s  4
0x5fb25  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x5fb2a  ldloc.s  0x13
0x5fb2c  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x5fb31  dup
0x5fb32  brtrue.s loc_5FB38
0x5fb34  pop
0x5fb35  ldnull
0x5fb36  br.s     loc_5FB3D
0x5fb38  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fb3d  dup
0x5fb3e  brtrue.s loc_5FB48
0x5fb40  pop
0x5fb41  ldloc.s  0x13
0x5fb43  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fb48  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5fb4d  dup
0x5fb4e  ldstr    aEntrypath// "entryPath"
0x5fb53  ldloc.s  7
0x5fb55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fb5a  ldloc.s  0x13
0x5fb5c  ldnull
0x5fb5d  ldc.i4.0
0x5fb5e  ldnull
0x5fb5f  ldc.i4.0
0x5fb60  ldnull
0x5fb61  ldc.i4.0
0x5fb62  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x5fb67  ldarg.0
0x5fb68  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5fb6d  dup
0x5fb6e  brtrue.s loc_5FB73
0x5fb70  pop
0x5fb71  br.s     loc_5FB92
0x5fb73  ldstr    aFailedToQueueP_0// "Failed to queue persisted ngen entry '{"...
0x5fb78  ldc.i4.2
0x5fb79  newarr   [mscorlib]System.Object
0x5fb7e  dup
0x5fb7f  ldc.i4.0
0x5fb80  ldloc.s  7
0x5fb82  stelem.ref
0x5fb83  dup
0x5fb84  ldc.i4.1
0x5fb85  ldloc.s  0x13
0x5fb87  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5fb8c  stelem.ref
0x5fb8d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5fb92  leave.s  loc_5FB94
0x5fb94  ldloc.s  6
0x5fb96  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5fb9b  brtrue   loc_5F980
0x5fba0  leave.s  loc_5FBAE
0x5fba2  ldloc.s  6
0x5fba4  brfalse.s loc_5FBAD
0x5fba6  ldloc.s  6
0x5fba8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fbad  endfinally
0x5fbae  ldloc.s  5
0x5fbb0  ret
```
