# NGenTask.TaskExecutive::SetRegistryFlagValue

- ea: `0x23e0`
- end: `0x2416`
- name: `NGenTask.TaskExecutive::SetRegistryFlagValue`
- size: `54`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x2170`
- `0x21b0`
- `0x2240`

## callees

- `0x23e0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x23e5  ldarg.1
0x23e6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x23eb  stloc.0
0x23ec  ldloc.0
0x23ed  brtrue.s loc_23F1
0x23ef  leave.s  loc_2415
0x23f1  ldloc.0
0x23f2  ldarg.2
0x23f3  ldarg.3
0x23f4  box      [mscorlib]System.Int32
0x23f9  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x23fe  leave.s  loc_2415
0x2400  stloc.1
0x2401  ldc.i4.0
0x2402  ldloc.1
0x2403  ldstr    aErrorSettingFl// "Error setting flag"
0x2408  ldc.i4.0
0x2409  newarr   [mscorlib]System.Object
0x240e  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2413  leave.s  loc_2415
0x2415  ret
```
