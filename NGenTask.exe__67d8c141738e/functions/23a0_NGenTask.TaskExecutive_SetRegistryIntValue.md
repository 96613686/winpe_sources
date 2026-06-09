# NGenTask.TaskExecutive::SetRegistryIntValue

- ea: `0x23a0`
- end: `0x23da`
- name: `NGenTask.TaskExecutive::SetRegistryIntValue`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1d30`
- `0x1d80`

## callees

- `0x23a0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x23a0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x23a5  ldarg.1
0x23a6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x23ab  stloc.0
0x23ac  ldloc.0
0x23ad  brtrue.s loc_23B1
0x23af  leave.s  loc_23D9
0x23b1  ldloc.0
0x23b2  ldarg.2
0x23b3  ldarg.3
0x23b4  box      [mscorlib]System.Int32
0x23b9  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x23be  leave.s  loc_23D9
0x23c0  stloc.1
0x23c1  ldc.i4.0
0x23c2  ldloc.1
0x23c3  ldstr    aErrorSettingTi// "Error setting time value {0}"
0x23c8  ldc.i4.1
0x23c9  newarr   [mscorlib]System.Object
0x23ce  dup
0x23cf  ldc.i4.0
0x23d0  ldarg.2
0x23d1  stelem.ref
0x23d2  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x23d7  leave.s  loc_23D9
0x23d9  ret
```
