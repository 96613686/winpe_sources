# Microsoft.VisualStudio.Setup.Installer.NgenHelper::ExecuteNgenOperation

- ea: `0x30930`
- end: `0x30aae`
- name: `Microsoft.VisualStudio.Setup.Installer.NgenHelper::ExecuteNgenOperation`
- size: `382`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x308a0`
- `0x30900`
- `0x30910`
- `0x30920`

## callees

- `0x11df0`
- `0x11e10`
- `0x30930`
- `0x30ab0`
- `0x314b0`
- `0x315c0`
- `0x315e0`
- `0x31620`
- `0x31630`

## string_xrefs

- `0x30931`: `serviceProvider`
- `0x309a8`: `Running 'ngen.exe {0}' for architecture {1} in the background, except for synchronous NGEN tasks`
- `0x30a24`: `' timed out during execution`

## pseudocode

```c

```

## disassembly

```asm
0x30930  ldarg.0
0x30931  ldstr    aServiceprovide// "serviceProvider"
0x30936  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x3093b  ldarg.1
0x3093c  ldstr    aArchitectures// "architectures"
0x30941  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x30946  ldarg.0
0x30947  ldc.i4.1
0x30948  call     T0x2B000001
0x3094d  stloc.0
0x3094e  ldarg.0
0x3094f  ldc.i4.0
0x30950  call     T0x2B00000C
0x30955  dup
0x30956  brtrue.s loc_3095E
0x30958  pop
0x30959  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x3095e  stloc.1
0x3095f  ldc.i4.1
0x30960  stloc.2
0x30961  ldarg.1
0x30962  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::GetEnumerator()
0x30967  stloc.3
0x30968  br       loc_30A92
0x3096d  ldloc.3
0x3096e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture>::get_Current()
0x30973  stloc.s  4
0x30975  ldarga.s 3
0x30977  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x3097c  brfalse.s loc_30996
0x3097e  ldloc.0
0x3097f  ldstr    aUserRequestedC// "User requested cancellation"
0x30984  call     T0x2B000003
0x30989  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3098e  ldloc.2
0x3098f  stloc.s  6
0x30991  leave    loc_30AAB
0x30996  ldloc.1
0x30997  ldloc.s  4
0x30999  call     string Microsoft.VisualStudio.Setup.Installer.NgenHelper::GetNgenPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture arch)
0x3099e  stloc.s  5
0x309a0  ldloc.s  5
0x309a2  brfalse  loc_30A75
0x309a7  ldloc.0
0x309a8  ldstr    aRunningNgenExe// "Running 'ngen.exe {0}' for architecture"...
0x309ad  ldarg.2
0x309ae  ldloc.s  4
0x309b0  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture
0x309b5  call     string [mscorlib]System.String::Format(string, object, object)
0x309ba  call     T0x2B000003
0x309bf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x309c4  ldarg.0
0x309c5  ldloc.s  5
0x309c7  ldarg.2
0x309c8  ldc.i4.1
0x309c9  ldc.i4.0
0x309ca  ldc.i4.1
0x309cb  ldc.i4.0
0x309cc  ldc.i4.1
0x309cd  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Tool::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, string toolFile, string arguments, [opt] bool redirectOutput, [opt] bool checkSignature, [opt] bool killOnTimeout, [opt] bool processWillBeElevating, [opt] bool isInRoot)
0x309d2  dup
0x309d3  ldsfld   int32 Microsoft.VisualStudio.Setup.Installer.NgenHelper::NgenActivitiesTimeoutInSeconds
0x309d8  conv.r8
0x309d9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x309de  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::.ctor(var<u1>)
0x309e3  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Tool::set_Timeout(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan> value)
0x309e8  dup
0x309e9  ldc.i4.2
0x309ea  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Tool::set_NumberOfRetries(int32 value)
0x309ef  dup
0x309f0  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x309f5  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Tool::set_WorkingDirectory(string value)
0x309fa  ldarg.3
0x309fb  callvirt instance class Microsoft.VisualStudio.Setup.Result Microsoft.VisualStudio.Setup.Installer.Tool::Run([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x30a00  stloc.s  7
0x30a02  ldloc.0
0x30a03  ldloc.s  7
0x30a05  callvirt instance string [mscorlib]System.Object::ToString()
0x30a0a  call     T0x2B000003
0x30a0f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x30a14  ldloc.s  7
0x30a16  callvirt instance bool Microsoft.VisualStudio.Setup.Result::get_TimedOut()
0x30a1b  brfalse.s loc_30A3C
0x30a1d  ldloc.0
0x30a1e  ldstr    aNgenExe// "'ngen.exe "
0x30a23  ldarg.2
0x30a24  ldstr    aTimedOutDuring// "' timed out during execution"
0x30a29  call     string [mscorlib]System.String::Concat(string, string, string)
0x30a2e  call     T0x2B000003
0x30a33  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x30a38  ldc.i4.0
0x30a39  stloc.2
0x30a3a  br.s     loc_30A92
0x30a3c  ldloc.s  7
0x30a3e  callvirt instance int32 Microsoft.VisualStudio.Setup.Result::get_ExitCode()
0x30a43  brfalse.s loc_30A92
0x30a45  ldloc.0
0x30a46  ldstr    aNgenExe0Failed// "'ngen.exe {0}' failed with exit code {1"...
0x30a4b  ldarg.2
0x30a4c  ldc.i4.0
0x30a4d  box      [mscorlib]System.Int32
0x30a52  call     string [mscorlib]System.String::Format(string, object, object)
0x30a57  ldc.i4.1
0x30a58  newarr   [mscorlib]System.Object
0x30a5d  dup
0x30a5e  ldc.i4.0
0x30a5f  ldloc.s  7
0x30a61  callvirt instance int32 Microsoft.VisualStudio.Setup.Result::get_ExitCode()
0x30a66  box      [mscorlib]System.Int32
0x30a6b  stelem.ref
0x30a6c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x30a71  ldc.i4.0
0x30a72  stloc.2
0x30a73  br.s     loc_30A92
0x30a75  ldloc.0
0x30a76  ldstr    aFailedToFindNg// "Failed to find ngen.exe for architectur"...
0x30a7b  ldc.i4.1
0x30a7c  newarr   [mscorlib]System.Object
0x30a81  dup
0x30a82  ldc.i4.0
0x30a83  ldloc.s  4
0x30a85  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture
0x30a8a  stelem.ref
0x30a8b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x30a90  ldc.i4.0
0x30a91  stloc.2
0x30a92  ldloc.3
0x30a93  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30a98  brtrue   loc_3096D
0x30a9d  leave.s  loc_30AA9
0x30a9f  ldloc.3
0x30aa0  brfalse.s loc_30AA8
0x30aa2  ldloc.3
0x30aa3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30aa8  endfinally
0x30aa9  ldloc.2
0x30aaa  ret
0x30aab  ldloc.s  6
0x30aad  ret
```
