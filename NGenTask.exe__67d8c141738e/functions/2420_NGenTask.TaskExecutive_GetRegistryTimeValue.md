# NGenTask.TaskExecutive::GetRegistryTimeValue

- ea: `0x2420`
- end: `0x2494`
- name: `NGenTask.TaskExecutive::GetRegistryTimeValue`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1d30`

## callees

- `0x2420`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2420  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x2425  ldarg.1
0x2426  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x242b  stloc.0
0x242c  ldloc.0
0x242d  brtrue.s loc_243B
0x242f  ldloca.s 2
0x2431  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2437  ldloc.2
0x2438  stloc.2
0x2439  leave.s  loc_2492
0x243b  ldloc.0
0x243c  ldarg.2
0x243d  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2442  stloc.1
0x2443  ldloc.1
0x2444  brfalse.s loc_244E
0x2446  ldloc.1
0x2447  isinst   [mscorlib]System.Int64
0x244c  brtrue.s loc_245A
0x244e  ldloca.s 3
0x2450  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x2456  ldloc.3
0x2457  stloc.2
0x2458  leave.s  loc_2492
0x245a  ldloc.1
0x245b  unbox.any [mscorlib]System.Int64
0x2460  newobj   instance void [mscorlib]System.DateTime::.ctor(int64)
0x2465  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x246a  stloc.2
0x246b  leave.s  loc_2492
0x246d  stloc.s  4
0x246f  ldc.i4.0
0x2470  ldloc.s  4
0x2472  ldstr    aErrorRetrievin_1// "Error retrieving time value {0}"
0x2477  ldc.i4.1
0x2478  newarr   [mscorlib]System.Object
0x247d  dup
0x247e  ldc.i4.0
0x247f  ldarg.2
0x2480  stelem.ref
0x2481  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2486  ldloca.s 3
0x2488  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x248e  ldloc.3
0x248f  stloc.2
0x2490  leave.s  loc_2492
0x2492  ldloc.2
0x2493  ret
```
