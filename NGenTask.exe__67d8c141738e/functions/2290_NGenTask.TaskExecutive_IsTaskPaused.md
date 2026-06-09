# NGenTask.TaskExecutive::IsTaskPaused

- ea: `0x2290`
- end: `0x22d5`
- name: `NGenTask.TaskExecutive::IsTaskPaused`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x24f0`

## callees

- `0x20a0`
- `0x2290`
- `0x2c60`

## string_xrefs

- `0x229b`: `State\TaskPaused`
- `0x22bf`: `Error checking TaskPaused key`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x2295  ldarg.0
0x2296  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x229b  ldstr    aStateTaskpause// "State\\TaskPaused"
0x22a0  call     string [mscorlib]System.String::Concat(string, string)
0x22a5  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x22aa  stloc.0
0x22ab  ldloc.0
0x22ac  ldnull
0x22ad  cgt.un
0x22af  stloc.1
0x22b0  leave.s  loc_22D3
0x22b2  ldloc.0
0x22b3  brfalse.s loc_22BB
0x22b5  ldloc.0
0x22b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22bb  endfinally
0x22bc  stloc.2
0x22bd  ldc.i4.0
0x22be  ldloc.2
0x22bf  ldstr    aErrorCheckingT// "Error checking TaskPaused key"
0x22c4  ldc.i4.0
0x22c5  newarr   [mscorlib]System.Object
0x22ca  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x22cf  ldc.i4.0
0x22d0  stloc.1
0x22d1  leave.s  loc_22D3
0x22d3  ldloc.1
0x22d4  ret
```
