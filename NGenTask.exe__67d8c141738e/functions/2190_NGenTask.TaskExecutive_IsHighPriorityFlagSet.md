# NGenTask.TaskExecutive::IsHighPriorityFlagSet

- ea: `0x2190`
- end: `0x21b0`
- name: `NGenTask.TaskExecutive::IsHighPriorityFlagSet`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1ad0`

## callees

- `0x20a0`
- `0x22e0`

## string_xrefs

- `0x21a1`: `TaskHighPriorityMode`

## pseudocode

```c

```

## disassembly

```asm
0x2190  ldarg.0
0x2191  ldarg.0
0x2192  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x2197  ldstr    aState// "State"
0x219c  call     string [mscorlib]System.String::Concat(string, string)
0x21a1  ldstr    aTaskhighpriori// "TaskHighPriorityMode"
0x21a6  ldc.i4.0
0x21a7  call     instance int32 NGenTask.TaskExecutive::GetRegistryFlagValue(string keyName, string valueName, [opt] int32 defaultValue)
0x21ac  ldc.i4.0
0x21ad  cgt.un
0x21af  ret
```
