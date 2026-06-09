# System.Deployment.Application.FileDownloader::GetPatchSourceStream

- ea: `0x15110`
- end: `0x15179`
- name: `System.Deployment.Application.FileDownloader::GetPatchSourceStream`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x15400`

## callees

- `0x15110`
- `0x17c80`
- `0x17cd0`
- `0x23020`

## string_xrefs

- `0x15135`: `Ex_PatchSourceOpenFailed`
- `0x15157`: `Ex_PatchSourceOpenFailed`

## pseudocode

```c

```

## disassembly

```asm
0x15110  ldstr    aGetpatchsource// "GetPatchSourceStream("
0x15115  ldarg.0
0x15116  ldstr    aCalled// ") called."
0x1511b  call     string [mscorlib]System.String::Concat(string, string, string)
0x15120  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x15125  ldnull
0x15126  stloc.0
0x15127  ldarg.0
0x15128  ldc.i4.3
0x15129  ldc.i4.1
0x1512a  ldc.i4.1
0x1512b  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x15130  stloc.0
0x15131  leave.s  loc_15177
0x15133  stloc.1
0x15134  ldloc.1
0x15135  ldstr    aExPatchsourceo// "Ex_PatchSourceOpenFailed"
0x1513a  call     string System.Deployment.Application.Resources::GetString(string s)
0x1513f  ldc.i4.1
0x15140  newarr   [mscorlib]System.Object
0x15145  dup
0x15146  ldc.i4.0
0x15147  ldarg.0
0x15148  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1514d  stelem.ref
0x1514e  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0x15153  leave.s  loc_15177
0x15155  stloc.2
0x15156  ldloc.2
0x15157  ldstr    aExPatchsourceo// "Ex_PatchSourceOpenFailed"
0x1515c  call     string System.Deployment.Application.Resources::GetString(string s)
0x15161  ldc.i4.1
0x15162  newarr   [mscorlib]System.Object
0x15167  dup
0x15168  ldc.i4.0
0x15169  ldarg.0
0x1516a  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1516f  stelem.ref
0x15170  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0x15175  leave.s  loc_15177
0x15177  ldloc.0
0x15178  ret
```
