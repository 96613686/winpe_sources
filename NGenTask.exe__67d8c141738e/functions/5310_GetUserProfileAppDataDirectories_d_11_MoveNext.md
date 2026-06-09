# <GetUserProfileAppDataDirectories>d__11::MoveNext

- ea: `0x5310`
- end: `0x5594`
- name: `<GetUserProfileAppDataDirectories>d__11::MoveNext`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x2c30`
- `0x2c60`
- `0x3ed0`
- `0x3fb0`
- `0x3ff0`
- `0x52e0`
- `0x5310`
- `0x55a0`
- `0x55c0`

## string_xrefs

- `0x5370`: `Processing Logs at user profile path {0}`
- `0x54d5`: `Error accessing profile path {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5310  ldarg.0
0x5311  ldfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x5316  stloc.1
0x5317  ldarg.0
0x5318  ldfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileAppDataDirectories>d__11::<>4__this
0x531d  stloc.2
0x531e  ldloc.1
0x531f  brfalse.s loc_532F
0x5321  ldloc.1
0x5322  ldc.i4.1
0x5323  beq      loc_552F
0x5328  ldc.i4.0
0x5329  stloc.0
0x532a  leave    loc_5592
0x532f  ldarg.0
0x5330  ldc.i4.m1
0x5331  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x5336  ldarg.0
0x5337  ldloc.2
0x5338  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo> NGenTask.AppDataDirectoryWalker::GetUserProfileDirectories()
0x533d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo>::GetEnumerator()
0x5342  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x5347  ldarg.0
0x5348  ldc.i4.s 0xFD
0x534a  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x534f  br       loc_5560
0x5354  ldarg.0
0x5355  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x535a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo>::get_Current()
0x535f  stloc.3
0x5360  ldstr    aAppdata// "AppData\\"
0x5365  stloc.s  4
0x5367  ldloc.3
0x5368  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x536d  stloc.s  5
0x536f  ldc.i4.3
0x5370  ldstr    aProcessingLogs// "Processing Logs at user profile path {0"...
0x5375  ldc.i4.1
0x5376  newarr   [mscorlib]System.Object
0x537b  dup
0x537c  ldc.i4.0
0x537d  ldloc.s  5
0x537f  stelem.ref
0x5380  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x5385  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class NGenTask.ContainerDirectoryInfo>::.ctor()
0x538a  stloc.s  6
0x538c  ldloc.s  5
0x538e  ldloc.s  4
0x5390  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5395  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x539a  stloc.s  7
0x539c  ldloc.s  7
0x539e  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x53a3  brtrue.s loc_53C5
0x53a5  ldc.i4.3
0x53a6  ldstr    aLogsNotFoundAt// "Logs not found at {0}"
0x53ab  ldc.i4.1
0x53ac  newarr   [mscorlib]System.Object
0x53b1  dup
0x53b2  ldc.i4.0
0x53b3  ldloc.s  7
0x53b5  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x53ba  stelem.ref
0x53bb  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x53c0  leave    loc_5560
0x53c5  ldloc.s  7
0x53c7  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x53cc  ldc.i4   0x400
0x53d1  and
0x53d2  brfalse.s loc_53D9
0x53d4  leave    loc_5560
0x53d9  ldloc.s  7
0x53db  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x53e0  ldstr    aLocal// "Local"
0x53e5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x53ea  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x53ef  stloc.s  8
0x53f1  ldloc.s  8
0x53f3  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x53f8  brfalse.s loc_5409
0x53fa  ldloc.s  8
0x53fc  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x5401  ldc.i4   0x400
0x5406  and
0x5407  brfalse.s loc_540E
0x5409  leave    loc_5560
0x540e  ldloc.s  6
0x5410  ldloc.s  8
0x5412  newobj   instance void NGenTask.ContainerRootDirectoryInfo::.ctor(class [mscorlib]System.IO.DirectoryInfo logDir)
0x5417  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class NGenTask.ContainerDirectoryInfo>::Add(var<u1>)
0x541c  ldloc.s  8
0x541e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x5423  ldstr    aPackages// "Packages"
0x5428  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x542d  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x5432  stloc.s  9
0x5434  ldloc.s  9
0x5436  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x543b  brfalse.s loc_544C
0x543d  ldloc.s  9
0x543f  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x5444  ldc.i4   0x400
0x5449  and
0x544a  brfalse.s loc_5451
0x544c  leave    loc_5560
0x5451  ldloc.s  9
0x5453  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo> [mscorlib]System.IO.DirectoryInfo::EnumerateDirectories()
0x5458  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.IO.DirectoryInfo>::GetEnumerator()
0x545d  stloc.s  0xA
0x545f  br.s     loc_54B7
0x5461  ldloc.s  0xA
0x5463  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo>::get_Current()
0x5468  stloc.s  0xB
0x546a  ldloc.2
0x546b  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x5470  brfalse.s loc_5479
0x5472  ldc.i4.0
0x5473  stloc.0
0x5474  leave    loc_5578
0x5479  ldloc.s  0xB
0x547b  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x5480  ldc.i4   0x400
0x5485  and
0x5486  brtrue.s loc_54B7
0x5488  ldloc.s  0xB
0x548a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x548f  ldstr    aAc// "AC"
0x5494  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5499  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x549e  stloc.s  0xC
0x54a0  ldloc.s  0xC
0x54a2  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x54a7  brfalse.s loc_54B7
0x54a9  ldloc.s  6
0x54ab  ldloc.s  0xC
0x54ad  newobj   instance void NGenTask.ContainerRootDirectoryInfo::.ctor(class [mscorlib]System.IO.DirectoryInfo logDir)
0x54b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class NGenTask.ContainerDirectoryInfo>::Add(var<u1>)
0x54b7  ldloc.s  0xA
0x54b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x54be  brtrue.s loc_5461
0x54c0  leave.s  loc_54CE
0x54c2  ldloc.s  0xA
0x54c4  brfalse.s loc_54CD
0x54c6  ldloc.s  0xA
0x54c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54cd  endfinally
0x54ce  leave.s  loc_54EC
0x54d0  stloc.s  0xD
0x54d2  ldc.i4.0
0x54d3  ldloc.s  0xD
0x54d5  ldstr    aErrorAccessing// "Error accessing profile path {0}"
0x54da  ldc.i4.1
0x54db  newarr   [mscorlib]System.Object
0x54e0  dup
0x54e1  ldc.i4.0
0x54e2  ldloc.s  5
0x54e4  stelem.ref
0x54e5  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x54ea  leave.s  loc_5560
0x54ec  ldarg.0
0x54ed  ldloc.s  6
0x54ef  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x54f4  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap2
0x54f9  ldarg.0
0x54fa  ldc.i4.s 0xFC
0x54fc  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x5501  br.s     loc_5537
0x5503  ldarg.0
0x5504  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap2
0x5509  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x550e  stloc.s  0xE
0x5510  ldloc.2
0x5511  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x5516  brfalse.s loc_551C
0x5518  ldc.i4.0
0x5519  stloc.0
0x551a  br.s     loc_554C
0x551c  ldarg.0
0x551d  ldloc.s  0xE
0x551f  stfld    class NGenTask.ContainerDirectoryInfo <GetUserProfileAppDataDirectories>d__11::<>2__current
0x5524  ldarg.0
0x5525  ldc.i4.1
0x5526  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x552b  ldc.i4.1
0x552c  stloc.0
0x552d  leave.s  loc_5592
0x552f  ldarg.0
0x5530  ldc.i4.s 0xFC
0x5532  stfld    int32 <GetUserProfileAppDataDirectories>d__11::<>1__state
0x5537  ldarg.0
0x5538  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap2
0x553d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo>::MoveNext()
0x5542  brtrue.s loc_5503
0x5544  ldarg.0
0x5545  call     instance void <GetUserProfileAppDataDirectories>d__11::<>m__Finally2()
0x554a  br.s     loc_5554
0x554c  ldarg.0
0x554d  call     instance void <GetUserProfileAppDataDirectories>d__11::<>m__Finally2()
0x5552  br.s     loc_5578
0x5554  ldarg.0
0x5555  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap2
0x555a  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class NGenTask.ContainerDirectoryInfo>
0x5560  ldarg.0
0x5561  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x5566  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x556b  brtrue   loc_5354
0x5570  ldarg.0
0x5571  call     instance void <GetUserProfileAppDataDirectories>d__11::<>m__Finally1()
0x5576  br.s     loc_5580
0x5578  ldarg.0
0x5579  call     instance void <GetUserProfileAppDataDirectories>d__11::<>m__Finally1()
0x557e  leave.s  loc_5592
0x5580  ldarg.0
0x5581  ldnull
0x5582  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.IO.DirectoryInfo> <GetUserProfileAppDataDirectories>d__11::<>7__wrap1
0x5587  ldc.i4.0
0x5588  stloc.0
0x5589  leave.s  loc_5592
0x558b  ldarg.0
0x558c  call     instance void <GetUserProfileAppDataDirectories>d__11::System.IDisposable.Dispose()
0x5591  endfinally
0x5592  ldloc.0
0x5593  ret
```
