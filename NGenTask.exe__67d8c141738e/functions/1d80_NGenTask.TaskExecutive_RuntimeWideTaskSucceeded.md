# NGenTask.TaskExecutive::RuntimeWideTaskSucceeded

- ea: `0x1d80`
- end: `0x1db0`
- name: `NGenTask.TaskExecutive::RuntimeWideTaskSucceeded`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x20a0`
- `0x23a0`
- `0x24a0`

## string_xrefs

- `0x1da4`: `Attempts`

## pseudocode

```c

```

## disassembly

```asm
0x1d80  ldarg.0
0x1d81  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x1d86  ldstr    aState// "State"
0x1d8b  call     string [mscorlib]System.String::Concat(string, string)
0x1d90  stloc.0
0x1d91  ldarg.0
0x1d92  ldloc.0
0x1d93  ldstr    aLastsuccess// "LastSuccess"
0x1d98  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1d9d  call     instance void NGenTask.TaskExecutive::SetRegistryTimeValue(string keyName, string valueName, valuetype [mscorlib]System.DateTime value)
0x1da2  ldarg.0
0x1da3  ldloc.0
0x1da4  ldstr    aAttempts// "Attempts"
0x1da9  ldc.i4.0
0x1daa  call     instance void NGenTask.TaskExecutive::SetRegistryIntValue(string keyName, string valueName, int32 value)
0x1daf  ret
```
