# NGenTask.LogsParser::ParseLog

- ea: `0x3930`
- end: `0x3c0c`
- name: `NGenTask.LogsParser::ParseLog`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x3790`

## callees

- `0x32c0`
- `0x32e0`
- `0x3560`
- `0x3590`
- `0x35e0`
- `0x3930`
- `0x3c10`
- `0x3d40`
- `0x3d60`

## string_xrefs

- `0x3ac1`: `assembly_path`
- `0x3b68`: `assembly_path`
- `0x3b98`: `ni_path`

## pseudocode

```c

```

## disassembly

```asm
0x3930  newobj   instance void NGenTask.ParsedLogsInfo::.ctor()
0x3935  stloc.0
0x3936  ldarg.1
0x3937  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x393c  callvirt instance class [mscorlib]System.IO.StreamReader [mscorlib]System.IO.FileInfo::OpenText()
0x3941  stloc.1
0x3942  ldarg.1
0x3943  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x3948  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastWriteTimeUtc()
0x394d  stloc.2
0x394e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::.ctor()
0x3953  stloc.3
0x3954  ldc.i4.m1
0x3955  stloc.s  5
0x3957  ldc.i4.m1
0x3958  stloc.s  6
0x395a  ldc.i4.0
0x395b  stloc.s  7
0x395d  br       loc_3BF0
0x3962  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_BindingContextRegex
0x3967  ldloc.s  4
0x3969  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x396e  stloc.s  8
0x3970  ldloc.s  8
0x3972  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x3977  brfalse  loc_3AA2
0x397c  ldarg.0
0x397d  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> NGenTask.LogsParser::m_SupportedBinders
0x3982  ldloc.s  8
0x3984  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3989  ldstr    aBinder// "binder"
0x398e  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3993  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3998  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x399d  brfalse  loc_3BF0
0x39a2  ldloc.s  8
0x39a4  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x39a9  ldstr    aBinder// "binder"
0x39ae  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x39b3  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x39b8  ldloc.s  8
0x39ba  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x39bf  ldstr    aBinderParam// "binder_param"
0x39c4  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x39c9  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x39ce  ldarg.1
0x39cf  newobj   instance void NGenTask.BindingContext::.ctor(string binder, string binderParam, class NGenTask.ContainerFileInfo logFile)
0x39d4  stloc.s  9
0x39d6  ldloc.s  9
0x39d8  callvirt instance string NGenTask.BindingContext::get_Container()
0x39dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x39e2  brtrue.s loc_39F7
0x39e4  ldloc.0
0x39e5  ldarg.1
0x39e6  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerFileInfo::get_Root()
0x39eb  ldloc.s  9
0x39ed  callvirt instance string NGenTask.BindingContext::get_Container()
0x39f2  callvirt instance void NGenTask.ParsedLogsInfo::AddNewContainerAssociation(class NGenTask.ContainerRootDirectoryInfo rootDirectory, string containerMoniker)
0x39f7  ldloc.s  8
0x39f9  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x39fe  ldstr    aBinderNum// "binder_num"
0x3a03  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3a08  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3a0d  call     int32 [mscorlib]System.Int32::Parse(string)
0x3a12  stloc.s  0xA
0x3a14  ldloc.s  8
0x3a16  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3a1b  ldstr    aBinder// "binder"
0x3a20  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3a25  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3a2a  ldstr    aFusion// "fusion"
0x3a2f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a34  brtrue.s loc_3A3A
0x3a36  ldloc.s  0xA
0x3a38  stloc.s  5
0x3a3a  ldloc.s  8
0x3a3c  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3a41  ldstr    aBinder// "binder"
0x3a46  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3a4b  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3a50  ldstr    aWinrt// "WinRT"
0x3a55  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a5a  brtrue.s loc_3A60
0x3a5c  ldloc.s  0xA
0x3a5e  stloc.s  6
0x3a60  ldloc.s  8
0x3a62  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3a67  ldstr    aBinder// "binder"
0x3a6c  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3a71  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3a76  ldstr    aApp// "App"
0x3a7b  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a80  brtrue.s loc_3A93
0x3a82  ldarg.s  4
0x3a84  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x3a89  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a8e  brfalse.s loc_3A93
0x3a90  ldc.i4.1
0x3a91  stloc.s  7
0x3a93  ldloc.3
0x3a94  ldloc.s  0xA
0x3a96  ldloc.s  9
0x3a98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::set_Item(var<u1>, !!T0)
0x3a9d  br       loc_3BF0
0x3aa2  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_ILAssemblyRegex
0x3aa7  ldloc.s  4
0x3aa9  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x3aae  stloc.s  8
0x3ab0  ldloc.s  8
0x3ab2  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x3ab7  brfalse.s loc_3AFE
0x3ab9  ldarg.0
0x3aba  ldloc.s  8
0x3abc  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3ac1  ldstr    aAssemblyPath// "assembly_path"
0x3ac6  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3acb  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3ad0  ldloc.s  8
0x3ad2  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3ad7  ldstr    aBinderNum// "binder_num"
0x3adc  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3ae1  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3ae6  call     int32 [mscorlib]System.Int32::Parse(string)
0x3aeb  ldloc.s  5
0x3aed  ldloc.s  6
0x3aef  ldarg.2
0x3af0  ldloc.3
0x3af1  ldloc.0
0x3af2  ldarg.s  5
0x3af4  call     instance void NGenTask.LogsParser::AddNewILAssembly(string assemblyPath, int32 bindingContextNum, int32 fusionBindingContextNum, int32 winRtBindingContextNum, bool frameworkAssemblyOnly, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext> bindingContexts, class NGenTask.ParsedLogsInfo logInfo, class NGenTask.ExcludeList excludeList)
0x3af9  br       loc_3BF0
0x3afe  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_ReinstallRegex
0x3b03  ldloc.s  4
0x3b05  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x3b0a  stloc.s  8
0x3b0c  ldloc.s  8
0x3b0e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x3b13  brtrue   loc_3BF0
0x3b18  ldsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_NIUseRegex
0x3b1d  ldloc.s  4
0x3b1f  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x3b24  stloc.s  8
0x3b26  ldloc.s  8
0x3b28  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x3b2d  brfalse  loc_3BD0
0x3b32  ldloc.s  8
0x3b34  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3b39  ldstr    aBinderNum// "binder_num"
0x3b3e  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3b43  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3b48  call     int32 [mscorlib]System.Int32::Parse(string)
0x3b4d  stloc.s  0xB
0x3b4f  ldloc.3
0x3b50  ldloc.s  0xB
0x3b52  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::ContainsKey(var<u1>)
0x3b57  brfalse  loc_3BF0
0x3b5c  ldloc.s  7
0x3b5e  brfalse.s loc_3B87
0x3b60  ldarg.0
0x3b61  ldloc.s  8
0x3b63  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3b68  ldstr    aAssemblyPath// "assembly_path"
0x3b6d  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3b72  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3b77  ldloc.s  0xB
0x3b79  ldloc.s  5
0x3b7b  ldloc.s  6
0x3b7d  ldarg.2
0x3b7e  ldloc.3
0x3b7f  ldloc.0
0x3b80  ldarg.s  5
0x3b82  call     instance void NGenTask.LogsParser::AddNewILAssembly(string assemblyPath, int32 bindingContextNum, int32 fusionBindingContextNum, int32 winRtBindingContextNum, bool frameworkAssemblyOnly, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext> bindingContexts, class NGenTask.ParsedLogsInfo logInfo, class NGenTask.ExcludeList excludeList)
0x3b87  ldloc.3
0x3b88  ldloc.s  0xB
0x3b8a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class NGenTask.BindingContext>::get_Item(void)
0x3b8f  stloc.s  0xC
0x3b91  ldloc.s  8
0x3b93  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x3b98  ldstr    aNiPath// "ni_path"
0x3b9d  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x3ba2  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x3ba7  stloc.s  0xD
0x3ba9  ldloc.s  0xD
0x3bab  ldloc.s  0xD
0x3bad  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3bb2  ldc.i4.5
0x3bb3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3bb8  brfalse.s loc_3BF0
0x3bba  ldloc.s  0xD
0x3bbc  ldarg.3
0x3bbd  ldc.i4.5
0x3bbe  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3bc3  brfalse.s loc_3BF0
0x3bc5  ldloc.0
0x3bc6  ldloc.s  0xD
0x3bc8  ldloc.2
0x3bc9  callvirt instance void NGenTask.ParsedLogsInfo::AddNewNativeImage(string nativeImageName, valuetype [mscorlib]System.DateTime nativeImageAccessTime)
0x3bce  br.s     loc_3BF0
0x3bd0  ldloc.s  4
0x3bd2  ldstr    asc_8FD6// ""
0x3bd7  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3bdc  brfalse.s loc_3BF0
0x3bde  ldstr    aInvalidLogEntr// "Invalid log entry encountered :"
0x3be3  ldloc.s  4
0x3be5  call     string [mscorlib]System.String::Concat(string, string)
0x3bea  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0x3bef  throw
0x3bf0  ldloc.1
0x3bf1  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x3bf6  dup
0x3bf7  stloc.s  4
0x3bf9  brtrue   loc_3962
0x3bfe  leave.s  loc_3C0A
0x3c00  ldloc.1
0x3c01  brfalse.s loc_3C09
0x3c03  ldloc.1
0x3c04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c09  endfinally
0x3c0a  ldloc.0
0x3c0b  ret
```
