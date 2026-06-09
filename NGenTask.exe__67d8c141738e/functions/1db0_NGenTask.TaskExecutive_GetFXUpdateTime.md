# NGenTask.TaskExecutive::GetFXUpdateTime

- ea: `0x1db0`
- end: `0x1df1`
- name: `NGenTask.TaskExecutive::GetFXUpdateTime`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x1db0`
- `0x2020`
- `0x2c60`

## string_xrefs

- `0x1db6`: `FXUpdate.dat`
- `0x1dd7`: `Error retrieving timestamp of FXUpdate.dat`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.0
0x1db1  call     instance string NGenTask.TaskExecutive::GetFrameworkPath()
0x1db6  ldstr    aFxupdateDat// "FXUpdate.dat"
0x1dbb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1dc0  stloc.0
0x1dc1  ldloc.0
0x1dc2  call     bool [mscorlib]System.IO.File::Exists(string)
0x1dc7  brfalse.s loc_1DD2
0x1dc9  ldloc.0
0x1dca  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0x1dcf  stloc.1
0x1dd0  leave.s  loc_1DEF
0x1dd2  leave.s  loc_1DE9
0x1dd4  stloc.2
0x1dd5  ldc.i4.0
0x1dd6  ldloc.2
0x1dd7  ldstr    aErrorRetrievin// "Error retrieving timestamp of FXUpdate."...
0x1ddc  ldc.i4.0
0x1ddd  newarr   [mscorlib]System.Object
0x1de2  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1de7  leave.s  loc_1DE9
0x1de9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1dee  ret
0x1def  ldloc.1
0x1df0  ret
```
