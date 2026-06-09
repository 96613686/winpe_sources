# NGenTask.TaskExecutive::GetRegistryFlagValue

- ea: `0x22e0`
- end: `0x232c`
- name: `NGenTask.TaskExecutive::GetRegistryFlagValue`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x2150`
- `0x2190`
- `0x2220`
- `0x2270`

## callees

- `0x22e0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x22e5  ldarg.1
0x22e6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x22eb  stloc.0
0x22ec  ldloc.0
0x22ed  brtrue.s loc_22F3
0x22ef  ldarg.3
0x22f0  stloc.2
0x22f1  leave.s  loc_232A
0x22f3  ldloc.0
0x22f4  ldarg.2
0x22f5  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x22fa  stloc.1
0x22fb  ldloc.1
0x22fc  brfalse.s loc_2306
0x22fe  ldloc.1
0x22ff  isinst   [mscorlib]System.Int32
0x2304  brtrue.s loc_230A
0x2306  ldarg.3
0x2307  stloc.2
0x2308  leave.s  loc_232A
0x230a  ldloc.1
0x230b  unbox.any [mscorlib]System.Int32
0x2310  stloc.2
0x2311  leave.s  loc_232A
0x2313  stloc.3
0x2314  ldc.i4.0
0x2315  ldloc.3
0x2316  ldstr    aErrorCheckingF// "Error checking flag"
0x231b  ldc.i4.0
0x231c  newarr   [mscorlib]System.Object
0x2321  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2326  ldarg.3
0x2327  stloc.2
0x2328  leave.s  loc_232A
0x232a  ldloc.2
0x232b  ret
```
