# <GetLogDirectories>d__7::MoveNext

- ea: `0x45f0`
- end: `0x4874`
- name: `<GetLogDirectories>d__7::MoveNext`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x2c30`
- `0x2c60`
- `0x3d90`
- `0x3e00`
- `0x3fb0`
- `0x4000`
- `0x45d0`
- `0x45f0`
- `0x4880`

## string_xrefs

- `0x462a`: `DirectoryOverride`
- `0x4648`: `No usage log directory specified on command line.`
- `0x467f`: `Processing log directory {0}`
- `0x47fd`: `Processing log directory {0}`
- `0x46c9`: `Log directory {0} does not exist`
- `0x47bb`: `Log directory {0} does not exist`
- `0x474e`: `Log directory {0} is reparse point with attributes...{1}`
- `0x47de`: `Unable to locate usage log directory`

## pseudocode

```c

```

## disassembly

```asm
0x45f0  ldarg.0
0x45f1  ldfld    int32 <GetLogDirectories>d__7::<>1__state
0x45f6  stloc.1
0x45f7  ldarg.0
0x45f8  ldfld    class NGenTask.AppDataDirectoryWalker <GetLogDirectories>d__7::<>4__this
0x45fd  stloc.2
0x45fe  ldloc.1
0x45ff  switch   loc_4617, loc_46BC, loc_4831
0x4610  ldc.i4.0
0x4611  stloc.0
0x4612  leave    loc_4872
0x4617  ldarg.0
0x4618  ldc.i4.m1
0x4619  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x461e  ldloc.2
0x461f  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x4624  brfalse  loc_46F1
0x4629  ldc.i4.3
0x462a  ldstr    aDirectoryoverr// "DirectoryOverride"
0x462f  ldc.i4.0
0x4630  newarr   [mscorlib]System.Object
0x4635  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x463a  ldloc.2
0x463b  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x4640  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4645  brtrue.s loc_465D
0x4647  ldc.i4.0
0x4648  ldstr    aNoUsageLogDire// "No usage log directory specified on com"...
0x464d  ldc.i4.0
0x464e  newarr   [mscorlib]System.Object
0x4653  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x4658  br       loc_4867
0x465d  ldloc.2
0x465e  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x4663  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4668  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x466d  brfalse.s loc_46C8
0x466f  ldloc.2
0x4670  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x4675  brfalse.s loc_467E
0x4677  ldc.i4.0
0x4678  stloc.0
0x4679  leave    loc_4872
0x467e  ldc.i4.3
0x467f  ldstr    aProcessingLogD// "Processing log directory {0}"
0x4684  ldc.i4.1
0x4685  newarr   [mscorlib]System.Object
0x468a  dup
0x468b  ldc.i4.0
0x468c  ldloc.2
0x468d  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x4692  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4697  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x469c  stelem.ref
0x469d  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x46a2  ldarg.0
0x46a3  ldloc.2
0x46a4  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x46a9  stfld    class NGenTask.ContainerDirectoryInfo <GetLogDirectories>d__7::<>2__current
0x46ae  ldarg.0
0x46af  ldc.i4.1
0x46b0  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x46b5  ldc.i4.1
0x46b6  stloc.0
0x46b7  leave    loc_4872
0x46bc  ldarg.0
0x46bd  ldc.i4.m1
0x46be  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x46c3  br       loc_4867
0x46c8  ldc.i4.3
0x46c9  ldstr    aLogDirectory0D// "Log directory {0} does not exist"
0x46ce  ldc.i4.1
0x46cf  newarr   [mscorlib]System.Object
0x46d4  dup
0x46d5  ldc.i4.0
0x46d6  ldloc.2
0x46d7  ldfld    class NGenTask.ContainerDirectoryInfo NGenTask.AppDataDirectoryWalker::m_logDirectoryOverride
0x46dc  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x46e1  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x46e6  stelem.ref
0x46e7  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x46ec  br       loc_4867
0x46f1  ldloc.2
0x46f2  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.AppDataDirectoryWalker::GetUserProfileAppDataDirectories()
0x46f7  stloc.3
0x46f8  ldarg.0
0x46f9  ldstr    aMicrosoftClr// "Microsoft\\CLR_"
0x46fe  ldloc.2
0x46ff  ldfld    string NGenTask.AppDataDirectoryWalker::m_version
0x4704  ldstr    aUsagelogs// "\\UsageLogs"
0x4709  call     string [mscorlib]System.String::Concat(string, string, string)
0x470e  stfld    string <GetLogDirectories>d__7::<pathTail>5__2
0x4713  ldarg.0
0x4714  ldloc.3
0x4715  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x471a  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x471f  ldarg.0
0x4720  ldc.i4.s 0xFD
0x4722  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x4727  br       loc_4839
0x472c  ldarg.0
0x472d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x4732  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x4737  stloc.s  4
0x4739  ldloc.s  4
0x473b  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4740  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x4745  ldc.i4   0x400
0x474a  and
0x474b  brfalse.s loc_4790
0x474d  ldc.i4.3
0x474e  ldstr    aLogDirectory0I// "Log directory {0} is reparse point with"...
0x4753  ldc.i4.2
0x4754  newarr   [mscorlib]System.Object
0x4759  dup
0x475a  ldc.i4.0
0x475b  ldloc.s  4
0x475d  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4762  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4767  stelem.ref
0x4768  dup
0x4769  ldc.i4.1
0x476a  ldloc.s  4
0x476c  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x4771  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x4776  stloc.s  6
0x4778  ldloca.s 6
0x477a  constrained. [mscorlib]System.IO.FileAttributes
0x4780  callvirt instance string [mscorlib]System.Object::ToString()
0x4785  stelem.ref
0x4786  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x478b  br       loc_4839
0x4790  ldnull
0x4791  stloc.s  5
0x4793  ldloc.s  4
0x4795  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x479a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x479f  ldarg.0
0x47a0  ldfld    string <GetLogDirectories>d__7::<pathTail>5__2
0x47a5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x47aa  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x47af  stloc.s  5
0x47b1  ldloc.s  5
0x47b3  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x47b8  brtrue.s loc_47D7
0x47ba  ldc.i4.3
0x47bb  ldstr    aLogDirectory0D// "Log directory {0} does not exist"
0x47c0  ldc.i4.1
0x47c1  newarr   [mscorlib]System.Object
0x47c6  dup
0x47c7  ldc.i4.0
0x47c8  ldloc.s  5
0x47ca  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x47cf  stelem.ref
0x47d0  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x47d5  leave.s  loc_4839
0x47d7  leave.s  loc_47F0
0x47d9  stloc.s  7
0x47db  ldc.i4.0
0x47dc  ldloc.s  7
0x47de  ldstr    aUnableToLocate_0// "Unable to locate usage log directory"
0x47e3  ldc.i4.0
0x47e4  newarr   [mscorlib]System.Object
0x47e9  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x47ee  leave.s  loc_4839
0x47f0  ldloc.2
0x47f1  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x47f6  brfalse.s loc_47FC
0x47f8  ldc.i4.0
0x47f9  stloc.0
0x47fa  br.s     loc_4851
0x47fc  ldc.i4.3
0x47fd  ldstr    aProcessingLogD// "Processing log directory {0}"
0x4802  ldc.i4.1
0x4803  newarr   [mscorlib]System.Object
0x4808  dup
0x4809  ldc.i4.0
0x480a  ldloc.s  5
0x480c  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x4811  stelem.ref
0x4812  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x4817  ldarg.0
0x4818  ldloc.s  4
0x481a  ldloc.s  5
0x481c  newobj   instance void NGenTask.ContainerDirectoryInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.DirectoryInfo logDir)
0x4821  stfld    class NGenTask.ContainerDirectoryInfo <GetLogDirectories>d__7::<>2__current
0x4826  ldarg.0
0x4827  ldc.i4.2
0x4828  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x482d  ldc.i4.1
0x482e  stloc.0
0x482f  leave.s  loc_4872
0x4831  ldarg.0
0x4832  ldc.i4.s 0xFD
0x4834  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x4839  ldarg.0
0x483a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x483f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4844  brtrue   loc_472C
0x4849  ldarg.0
0x484a  call     instance void <GetLogDirectories>d__7::<>m__Finally1()
0x484f  br.s     loc_4859
0x4851  ldarg.0
0x4852  call     instance void <GetLogDirectories>d__7::<>m__Finally1()
0x4857  leave.s  loc_4872
0x4859  ldarg.0
0x485a  ldnull
0x485b  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <GetLogDirectories>d__7::<>7__wrap2
0x4860  ldarg.0
0x4861  ldnull
0x4862  stfld    string <GetLogDirectories>d__7::<pathTail>5__2
0x4867  ldc.i4.0
0x4868  stloc.0
0x4869  leave.s  loc_4872
0x486b  ldarg.0
0x486c  call     instance void <GetLogDirectories>d__7::System.IDisposable.Dispose()
0x4871  endfinally
0x4872  ldloc.0
0x4873  ret
```
