# NGenTask.TaskExecutive::SetRegistryTimeValue

- ea: `0x24a0`
- end: `0x24e2`
- name: `NGenTask.TaskExecutive::SetRegistryTimeValue`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1d80`

## callees

- `0x24a0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x24a0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x24a5  ldarg.1
0x24a6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x24ab  stloc.0
0x24ac  ldloc.0
0x24ad  brtrue.s loc_24B1
0x24af  leave.s  loc_24E1
0x24b1  ldloc.0
0x24b2  ldarg.2
0x24b3  ldarga.s 3
0x24b5  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x24ba  box      [mscorlib]System.Int64
0x24bf  ldc.i4.s 0xB
0x24c1  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x24c6  leave.s  loc_24E1
0x24c8  stloc.1
0x24c9  ldc.i4.0
0x24ca  ldloc.1
0x24cb  ldstr    aErrorSettingTi// "Error setting time value {0}"
0x24d0  ldc.i4.1
0x24d1  newarr   [mscorlib]System.Object
0x24d6  dup
0x24d7  ldc.i4.0
0x24d8  ldarg.2
0x24d9  stelem.ref
0x24da  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x24df  leave.s  loc_24E1
0x24e1  ret
```
