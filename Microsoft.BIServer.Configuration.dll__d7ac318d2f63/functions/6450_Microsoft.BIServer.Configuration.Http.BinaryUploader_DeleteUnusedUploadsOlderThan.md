# Microsoft.BIServer.Configuration.Http.BinaryUploader::DeleteUnusedUploadsOlderThan

- ea: `0x6450`
- end: `0x64ed`
- name: `Microsoft.BIServer.Configuration.Http.BinaryUploader::DeleteUnusedUploadsOlderThan`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6380`

## callees

- `0x6450`
- `0x7740`

## string_xrefs

- `0x64d1`: `Binary Uploader Cleanup: attempting to continue after unexpected exception`

## pseudocode

```c

```

## disassembly

```asm
0x6450  ldc.i4.2
0x6451  newarr   [mscorlib]System.String
0x6456  dup
0x6457  ldc.i4.0
0x6458  ldstr    aBinaryuploader// "BinaryUploader"
0x645d  stelem.ref
0x645e  dup
0x645f  ldc.i4.1
0x6460  ldstr    aCleanup// "Cleanup"
0x6465  stelem.ref
0x6466  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x646b  stloc.0
0x646c  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x6471  stloc.1
0x6472  ldloc.1
0x6473  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6478  ldarg.1
0x6479  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x647e  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass7_0::deleteThreshold
0x6483  ldarg.0
0x6484  ldfld    string Microsoft.BIServer.Configuration.Http.BinaryUploader::_uploadPath
0x6489  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x648e  ldarg.0
0x648f  ldfld    string Microsoft.BIServer.Configuration.Http.BinaryUploader::_uploadFileSelector
0x6494  call     instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x6499  ldloc.1
0x649a  ldftn    instance bool <>c__DisplayClass7_0::<DeleteUnusedUploadsOlderThan>b__0(class [mscorlib]System.IO.FileInfo fileInfo)
0x64a0  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.IO.FileInfo, bool>::.ctor(object, native int)
0x64a5  call     T0x2B000034
0x64aa  ldsfld   class [mscorlib]System.Action`1<class [mscorlib]System.IO.FileInfo> <>c::<>9__7_1
0x64af  dup
0x64b0  brtrue.s loc_64C9
0x64b2  pop
0x64b3  ldsfld   class <>c <>c::<>9
0x64b8  ldftn    instance void <>c::<DeleteUnusedUploadsOlderThan>b__7_1(class [mscorlib]System.IO.FileInfo fileToDelete)
0x64be  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.IO.FileInfo>::.ctor(object, native int)
0x64c3  dup
0x64c4  stsfld   class [mscorlib]System.Action`1<class [mscorlib]System.IO.FileInfo> <>c::<>9__7_1
0x64c9  call     T0x2B000035
0x64ce  pop
0x64cf  leave.s  loc_64EC
0x64d1  ldstr    aBinaryUploader// "Binary Uploader Cleanup: attempting to "...
0x64d6  call     T0x2B000015
0x64db  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception, string, object[])
0x64e0  leave.s  loc_64EC
0x64e2  ldloc.0
0x64e3  brfalse.s loc_64EB
0x64e5  ldloc.0
0x64e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64eb  endfinally
0x64ec  ret
```
