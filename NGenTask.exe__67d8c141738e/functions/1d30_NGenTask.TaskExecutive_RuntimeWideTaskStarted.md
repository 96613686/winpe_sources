# NGenTask.TaskExecutive::RuntimeWideTaskStarted

- ea: `0x1d30`
- end: `0x1d74`
- name: `NGenTask.TaskExecutive::RuntimeWideTaskStarted`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x310`
- `0x1ad0`

## callees

- `0x1d30`
- `0x20a0`
- `0x2330`
- `0x23a0`
- `0x2420`

## string_xrefs

- `0x1d50`: `Attempts`
- `0x1d60`: `Attempts`

## pseudocode

```c

```

## disassembly

```asm
0x1d30  ldarg.0
0x1d31  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x1d36  ldstr    aState// "State"
0x1d3b  call     string [mscorlib]System.String::Concat(string, string)
0x1d40  stloc.0
0x1d41  ldarg.0
0x1d42  ldloc.0
0x1d43  ldstr    aLastsuccess// "LastSuccess"
0x1d48  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> NGenTask.TaskExecutive::GetRegistryTimeValue(string keyName, string valueName)
0x1d4d  stloc.1
0x1d4e  ldarg.0
0x1d4f  ldloc.0
0x1d50  ldstr    aAttempts// "Attempts"
0x1d55  call     instance valuetype [mscorlib]System.Nullable`1<int32> NGenTask.TaskExecutive::GetRegistryIntValue(string keyName, string valueName)
0x1d5a  stloc.2
0x1d5b  ldarg.1
0x1d5c  brtrue.s loc_1D73
0x1d5e  ldarg.0
0x1d5f  ldloc.0
0x1d60  ldstr    aAttempts// "Attempts"
0x1d65  ldloca.s 2
0x1d67  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1d6c  ldc.i4.1
0x1d6d  add
0x1d6e  call     instance void NGenTask.TaskExecutive::SetRegistryIntValue(string keyName, string valueName, int32 value)
0x1d73  ret
```
