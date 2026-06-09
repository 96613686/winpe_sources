# NGenTask.TaskExecutive::SetHighPriorityFlag

- ea: `0x21b0`
- end: `0x21d3`
- name: `NGenTask.TaskExecutive::SetHighPriorityFlag`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1ad0`

## callees

- `0x20a0`
- `0x21b0`
- `0x23e0`

## string_xrefs

- `0x21c1`: `TaskHighPriorityMode`

## pseudocode

```c

```

## disassembly

```asm
0x21b0  ldarg.0
0x21b1  ldarg.0
0x21b2  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x21b7  ldstr    aState// "State"
0x21bc  call     string [mscorlib]System.String::Concat(string, string)
0x21c1  ldstr    aTaskhighpriori// "TaskHighPriorityMode"
0x21c6  ldarg.1
0x21c7  brtrue.s loc_21CC
0x21c9  ldc.i4.0
0x21ca  br.s     loc_21CD
0x21cc  ldc.i4.1
0x21cd  call     instance void NGenTask.TaskExecutive::SetRegistryFlagValue(string keyName, string valueName, int32 value)
0x21d2  ret
```
