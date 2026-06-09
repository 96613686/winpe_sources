# NGenTask.TaskExecutive::GetRegistryIntValue

- ea: `0x2330`
- end: `0x239f`
- name: `NGenTask.TaskExecutive::GetRegistryIntValue`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1d30`

## callees

- `0x2330`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2330  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x2335  ldarg.1
0x2336  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x233b  stloc.0
0x233c  ldloc.0
0x233d  brtrue.s loc_234B
0x233f  ldloca.s 2
0x2341  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2347  ldloc.2
0x2348  stloc.2
0x2349  leave.s  loc_239D
0x234b  ldloc.0
0x234c  ldarg.2
0x234d  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x2352  stloc.1
0x2353  ldloc.1
0x2354  brfalse.s loc_235E
0x2356  ldloc.1
0x2357  isinst   [mscorlib]System.Int32
0x235c  brtrue.s loc_236A
0x235e  ldloca.s 3
0x2360  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2366  ldloc.3
0x2367  stloc.2
0x2368  leave.s  loc_239D
0x236a  ldloc.1
0x236b  unbox.any [mscorlib]System.Int32
0x2370  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x2375  stloc.2
0x2376  leave.s  loc_239D
0x2378  stloc.s  4
0x237a  ldc.i4.0
0x237b  ldloc.s  4
0x237d  ldstr    aErrorRetrievin_1// "Error retrieving time value {0}"
0x2382  ldc.i4.1
0x2383  newarr   [mscorlib]System.Object
0x2388  dup
0x2389  ldc.i4.0
0x238a  ldarg.2
0x238b  stelem.ref
0x238c  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2391  ldloca.s 3
0x2393  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2399  ldloc.3
0x239a  stloc.2
0x239b  leave.s  loc_239D
0x239d  ldloc.2
0x239e  ret
```
