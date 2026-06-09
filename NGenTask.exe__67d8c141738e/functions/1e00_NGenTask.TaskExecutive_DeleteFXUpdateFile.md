# NGenTask.TaskExecutive::DeleteFXUpdateFile

- ea: `0x1e00`
- end: `0x1e2d`
- name: `NGenTask.TaskExecutive::DeleteFXUpdateFile`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x1e00`
- `0x2020`
- `0x2c60`

## string_xrefs

- `0x1e06`: `FXUpdate.dat`
- `0x1e1a`: `Error deleting FXUpdate.dat`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.0
0x1e01  call     instance string NGenTask.TaskExecutive::GetFrameworkPath()
0x1e06  ldstr    aFxupdateDat// "FXUpdate.dat"
0x1e0b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1e10  call     void [mscorlib]System.IO.File::Delete(string)
0x1e15  leave.s  loc_1E2C
0x1e17  stloc.0
0x1e18  ldc.i4.0
0x1e19  ldloc.0
0x1e1a  ldstr    aErrorDeletingF// "Error deleting FXUpdate.dat"
0x1e1f  ldc.i4.0
0x1e20  newarr   [mscorlib]System.Object
0x1e25  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1e2a  leave.s  loc_1E2C
0x1e2c  ret
```
