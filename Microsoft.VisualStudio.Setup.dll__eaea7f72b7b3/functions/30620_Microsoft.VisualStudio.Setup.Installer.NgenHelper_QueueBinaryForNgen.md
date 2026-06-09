# Microsoft.VisualStudio.Setup.Installer.NgenHelper::QueueBinaryForNgen

- ea: `0x30620`
- end: `0x3089b`
- name: `Microsoft.VisualStudio.Setup.Installer.NgenHelper::QueueBinaryForNgen`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5f920`

## callees

- `0x30620`
- `0x3e110`
- `0x3f6e0`

## string_xrefs

- `0x30638`: `registry`
- `0x30621`: `assemblyPath`
- `0x30751`: ` /ExeConfig:"`
- `0x30769`: `install "{0}"{1}{2} /queue:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x30620  ldarg.0
0x30621  ldstr    aAssemblypath// "assemblyPath"
0x30626  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x3062b  ldarg.1
0x3062c  ldstr    aArchitectures// "architectures"
0x30631  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x30636  ldarg.s  5
0x30638  ldstr    aRegistry// "registry"
0x3063d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x30642  ldarg.s  6
0x30644  ldstr    aLogger// "logger"
0x30649  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x3064e  ldarg.s  4
0x30650  call     T0x2B0000B4
0x30655  brfalse.s loc_30667
0x30657  ldc.i4.1
0x30658  newarr   [mscorlib]System.String
0x3065d  dup
0x3065e  ldc.i4.0
0x3065f  ldsfld   string [mscorlib]System.String::Empty
0x30664  stelem.ref
0x30665  starg.s  4
0x30667  ldarg.1
0x30668  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::GetEnumerator()
0x3066d  stloc.0
0x3066e  br       loc_30883
0x30673  ldloc.0
0x30674  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::get_Current()
0x30679  stloc.1
0x3067a  ldnull
0x3067b  stloc.2
0x3067c  ldloc.1
0x3067d  ldc.i4.1
0x3067e  bne.un.s loc_30686
0x30680  ldsfld   string Microsoft.VisualStudio.Setup.Installer.NgenHelper::NgenQueueKey32
0x30685  stloc.2
0x30686  ldloc.1
0x30687  ldc.i4.2
0x30688  bne.un.s loc_306B6
0x3068a  call     bool [mscorlib]System.Environment::get_Is64BitOperatingSystem()
0x3068f  brfalse.s loc_30699
0x30691  ldsfld   string Microsoft.VisualStudio.Setup.Installer.NgenHelper::NgenQueueKey64
0x30696  stloc.2
0x30697  br.s     loc_306B6
0x30699  ldarg.s  6
0x3069b  ldstr    aSkippingNgenOf// "Skipping ngen of file '{0}' for archite"...
0x306a0  ldarg.0
0x306a1  ldloc.1
0x306a2  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture
0x306a7  call     string [mscorlib]System.String::Format(string, object, object)
0x306ac  call     T0x2B000003
0x306b1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x306b6  ldloc.1
0x306b7  ldc.i4.4
0x306b8  bne.un.s loc_306F3
0x306ba  ldarg.s  7
0x306bc  dup
0x306bd  brtrue.s loc_306C6
0x306bf  pop
0x306c0  ldnull
0x306c1  newobj   instance void Microsoft.VisualStudio.Setup.Services.MachineService::.ctor(class [mscorlib]System.IServiceProvider services)
0x306c6  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.MachineArchitecture Microsoft.VisualStudio.Setup.Services.IMachineService::GetMachineArchitecture()
0x306cb  ldc.i4.4
0x306cc  bne.un.s loc_306D6
0x306ce  ldsfld   string Microsoft.VisualStudio.Setup.Installer.NgenHelper::NgenQueueKeyArm64
0x306d3  stloc.2
0x306d4  br.s     loc_306F3
0x306d6  ldarg.s  6
0x306d8  ldstr    aSkippingNgenOf_0// "Skipping ngen of file '{0}' for archite"...
0x306dd  ldarg.0
0x306de  ldloc.1
0x306df  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture
0x306e4  call     string [mscorlib]System.String::Format(string, object, object)
0x306e9  call     T0x2B000003
0x306ee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x306f3  ldloc.2
0x306f4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x306f9  brtrue   loc_30883
0x306fe  ldarg.s  4
0x30700  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x30705  stloc.3
0x30706  br       loc_3086C
0x3070b  ldloc.3
0x3070c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x30711  stloc.s  4
0x30713  ldarg.s  6
0x30715  ldstr    aQueueing0For1N// "Queueing {0} for {1} ngen"
0x3071a  ldarg.0
0x3071b  ldloc.1
0x3071c  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture
0x30721  call     string [mscorlib]System.String::Format(string, object, object)
0x30726  call     T0x2B000003
0x3072b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x30730  ldarg.3
0x30731  brtrue.s loc_3073A
0x30733  ldstr    aNodependencies// " /NoDependencies"
0x30738  br.s     loc_3073F
0x3073a  ldsfld   string [mscorlib]System.String::Empty
0x3073f  stloc.s  5
0x30741  ldloc.s  4
0x30743  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x30748  brfalse.s loc_30751
0x3074a  ldsfld   string [mscorlib]System.String::Empty
0x3074f  br.s     loc_30762
0x30751  ldstr    aExeconfig// " /ExeConfig:\""
0x30756  ldloc.s  4
0x30758  ldstr    asc_8B518// "\""
0x3075d  call     string [mscorlib]System.String::Concat(string, string, string)
0x30762  stloc.s  6
0x30764  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30769  ldstr    aInstall012Queu// "install \"{0}\"{1}{2} /queue:{3}"
0x3076e  ldc.i4.4
0x3076f  newarr   [mscorlib]System.Object
0x30774  dup
0x30775  ldc.i4.0
0x30776  ldarg.0
0x30777  stelem.ref
0x30778  dup
0x30779  ldc.i4.1
0x3077a  ldloc.s  5
0x3077c  stelem.ref
0x3077d  dup
0x3077e  ldc.i4.2
0x3077f  ldloc.s  6
0x30781  stelem.ref
0x30782  dup
0x30783  ldc.i4.3
0x30784  ldarg.2
0x30785  box      [mscorlib]System.Int32
0x3078a  stelem.ref
0x3078b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30790  stloc.s  7
0x30792  ldarg.s  5
0x30794  ldc.i4.2
0x30795  ldc.i4.2
0x30796  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x3079b  stloc.s  8
0x3079d  ldloc.s  8
0x3079f  ldloc.2
0x307a0  ldc.i4.0
0x307a1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x307a6  stloc.s  9
0x307a8  ldc.i4.0
0x307a9  stloc.s  0xA
0x307ab  br       loc_3084B
0x307b0  ldstr    a01_3// "{0}{1}"
0x307b5  ldarg.2
0x307b6  box      [mscorlib]System.Int32
0x307bb  ldsfld   class [mscorlib]System.Random Microsoft.VisualStudio.Setup.Installer.NgenHelper::random
0x307c0  ldc.i4   0x186A0
0x307c5  ldc.i4   0xF4240
0x307ca  callvirt instance int32 [mscorlib]System.Random::Next(int32, int32)
0x307cf  box      [mscorlib]System.Int32
0x307d4  call     string [mscorlib]System.String::Format(string, object, object)
0x307d9  stloc.s  0xB
0x307db  ldsfld   object Microsoft.VisualStudio.Setup.Installer.NgenHelper::RegistryLock
0x307e0  stloc.s  0xC
0x307e2  ldc.i4.0
0x307e3  stloc.s  0xD
0x307e5  ldloc.s  0xC
0x307e7  ldloca.s 0xD
0x307e9  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x307ee  ldloc.s  9
0x307f0  ldloc.s  0xB
0x307f2  ldc.i4.0
0x307f3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x307f8  stloc.s  0xE
0x307fa  ldloc.s  0xE
0x307fc  brtrue.s loc_30831
0x307fe  ldloc.s  9
0x30800  ldloc.s  0xB
0x30802  ldc.i4.0
0x30803  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x30808  stloc.s  0xF
0x3080a  ldloc.s  0xF
0x3080c  ldnull
0x3080d  ldloc.s  7
0x3080f  ldc.i4.1
0x30810  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x30815  ldc.i4.1
0x30816  stloc.s  0xA
0x30818  leave.s  loc_30826
0x3081a  ldloc.s  0xF
0x3081c  brfalse.s loc_30825
0x3081e  ldloc.s  0xF
0x30820  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30825  endfinally
0x30826  ldsflda  int32 Microsoft.VisualStudio.Setup.Installer.NgenHelper::totalNumAssembliesQueuedForNgen
0x3082b  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x30830  pop
0x30831  leave.s  loc_3084B
0x30833  ldloc.s  0xE
0x30835  brfalse.s loc_3083E
0x30837  ldloc.s  0xE
0x30839  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3083e  endfinally
0x3083f  ldloc.s  0xD
0x30841  brfalse.s loc_3084A
0x30843  ldloc.s  0xC
0x30845  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3084a  endfinally
0x3084b  ldloc.s  0xA
0x3084d  brfalse  loc_307B0
0x30852  leave.s  loc_3086C
0x30854  ldloc.s  9
0x30856  brfalse.s loc_3085F
0x30858  ldloc.s  9
0x3085a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3085f  endfinally
0x30860  ldloc.s  8
0x30862  brfalse.s loc_3086B
0x30864  ldloc.s  8
0x30866  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3086b  endfinally
0x3086c  ldloc.3
0x3086d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30872  brtrue   loc_3070B
0x30877  leave.s  loc_30883
0x30879  ldloc.3
0x3087a  brfalse.s loc_30882
0x3087c  ldloc.3
0x3087d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30882  endfinally
0x30883  ldloc.0
0x30884  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30889  brtrue   loc_30673
0x3088e  leave.s  loc_3089A
0x30890  ldloc.0
0x30891  brfalse.s loc_30899
0x30893  ldloc.0
0x30894  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30899  endfinally
0x3089a  ret
```
