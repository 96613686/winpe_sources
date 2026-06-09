# System.Web.Compilation.StandardDiskBuildResultCache::RemoveOldTempFiles

- ea: `0x17bad0`
- end: `0x17bc3d`
- name: `System.Web.Compilation.StandardDiskBuildResultCache::RemoveOldTempFiles`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1754c0`

## callees

- `0x54620`
- `0x54630`
- `0x54650`
- `0x546c0`
- `0x548e0`
- `0x17b790`
- `0x17bad0`
- `0x17bc40`

## string_xrefs

- `0x17bb7c`: `.delete`
- `0x17bb6c`: `.compiled`

## pseudocode

```c

```

## disassembly

```asm
0x17bad0  ldarg.0
0x17bad1  call     instance void System.Web.Compilation.StandardDiskBuildResultCache::RemoveCodegenResourceDir()
0x17bad6  ldarg.0
0x17bad7  ldfld    string System.Web.Compilation.DiskBuildResultCache::_cacheDir
0x17badc  ldstr    asc_1B3DEA// "\\"
0x17bae1  call     string [mscorlib]System.String::Concat(string, string)
0x17bae6  stloc.0
0x17bae7  ldloc.0
0x17bae8  call     class System.Web.Util.FileEnumerator System.Web.Util.FileEnumerator::Create(string path)
0x17baed  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x17baf2  stloc.1
0x17baf3  br       loc_17BC1B
0x17baf8  ldloc.1
0x17baf9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x17bafe  castclass System.Web.Util.FileData
0x17bb03  stloc.2
0x17bb04  ldloc.2
0x17bb05  callvirt instance bool System.Web.Util.FileData::get_IsDirectory()
0x17bb0a  brtrue   loc_17BC1B
0x17bb0f  ldloc.2
0x17bb10  callvirt instance string System.Web.Util.FileData::get_Name()
0x17bb15  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x17bb1a  stloc.3
0x17bb1b  ldloc.3
0x17bb1c  ldstr    aDll_0// ".dll"
0x17bb21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb26  brtrue   loc_17BC1B
0x17bb2b  ldloc.3
0x17bb2c  ldstr    aPdb// ".pdb"
0x17bb31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb36  brtrue   loc_17BC1B
0x17bb3b  ldloc.3
0x17bb3c  ldstr    aWeb// ".web"
0x17bb41  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb46  brtrue   loc_17BC1B
0x17bb4b  ldloc.3
0x17bb4c  ldstr    aCcu// ".ccu"
0x17bb51  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb56  brtrue   loc_17BC1B
0x17bb5b  ldloc.3
0x17bb5c  ldstr    aProf// ".prof"
0x17bb61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb66  brtrue   loc_17BC1B
0x17bb6b  ldloc.3
0x17bb6c  ldstr    aCompiled// ".compiled"
0x17bb71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17bb76  brtrue   loc_17BC1B
0x17bb7b  ldloc.3
0x17bb7c  ldstr    aDelete_0// ".delete"
0x17bb81  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x17bb86  brfalse.s loc_17BBF7
0x17bb88  ldloc.2
0x17bb89  callvirt instance string System.Web.Util.FileData::get_Name()
0x17bb8e  ldc.i4.s 0x2E
0x17bb90  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x17bb95  stloc.s  4
0x17bb97  ldloc.s  4
0x17bb99  ldc.i4.0
0x17bb9a  ble.s    loc_17BC0A
0x17bb9c  ldloc.2
0x17bb9d  callvirt instance string System.Web.Util.FileData::get_Name()
0x17bba2  ldc.i4.0
0x17bba3  ldloc.s  4
0x17bba5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17bbaa  stloc.s  5
0x17bbac  ldloc.s  5
0x17bbae  ldc.i4.s 0x2E
0x17bbb0  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x17bbb5  stloc.s  6
0x17bbb7  ldloc.s  6
0x17bbb9  ldc.i4.0
0x17bbba  ble.s    loc_17BBC8
0x17bbbc  ldloc.s  5
0x17bbbe  ldc.i4.0
0x17bbbf  ldloc.s  6
0x17bbc1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x17bbc6  stloc.s  5
0x17bbc8  ldloc.0
0x17bbc9  ldloc.s  5
0x17bbcb  ldstr    aDll_0// ".dll"
0x17bbd0  call     string [mscorlib]System.String::Concat(string, string, string)
0x17bbd5  call     bool System.Web.Util.FileUtil::FileExists(string filename)
0x17bbda  brtrue.s loc_17BC1B
0x17bbdc  ldloc.0
0x17bbdd  ldstr    aAppWeb// "App_Web_"
0x17bbe2  ldloc.s  5
0x17bbe4  ldstr    aDll_0// ".dll"
0x17bbe9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x17bbee  call     bool System.Web.Util.FileUtil::FileExists(string filename)
0x17bbf3  brfalse.s loc_17BC0A
0x17bbf5  br.s     loc_17BC1B
0x17bbf7  ldloc.2
0x17bbf8  callvirt instance string System.Web.Util.FileData::get_FullName()
0x17bbfd  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x17bc02  call     bool System.Web.Compilation.DiskBuildResultCache::CheckAndRemoveDotDeleteFile(class [mscorlib]System.IO.FileInfo f)
0x17bc07  pop
0x17bc08  br.s     loc_17BC1B
0x17bc0a  nop
0x17bc0b  ldloc.2
0x17bc0c  callvirt instance string System.Web.Util.FileData::get_FullName()
0x17bc11  call     void [mscorlib]System.IO.File::Delete(string)
0x17bc16  leave.s  loc_17BC1B
0x17bc18  pop
0x17bc19  leave.s  loc_17BC1B
0x17bc1b  ldloc.1
0x17bc1c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17bc21  brtrue   loc_17BAF8
0x17bc26  leave.s  loc_17BC3C
0x17bc28  ldloc.1
0x17bc29  isinst   [mscorlib]System.IDisposable
0x17bc2e  stloc.s  7
0x17bc30  ldloc.s  7
0x17bc32  brfalse.s loc_17BC3B
0x17bc34  ldloc.s  7
0x17bc36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17bc3b  endfinally
0x17bc3c  ret
```
