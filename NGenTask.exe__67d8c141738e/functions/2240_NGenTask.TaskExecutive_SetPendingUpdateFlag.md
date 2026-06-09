# NGenTask.TaskExecutive::SetPendingUpdateFlag

- ea: `0x2240`
- end: `0x2263`
- name: `NGenTask.TaskExecutive::SetPendingUpdateFlag`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x20a0`
- `0x2240`
- `0x23e0`

## string_xrefs

- `0x2251`: `PendingUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x2240  ldarg.0
0x2241  ldarg.0
0x2242  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x2247  ldstr    aState// "State"
0x224c  call     string [mscorlib]System.String::Concat(string, string)
0x2251  ldstr    aPendingupdate// "PendingUpdate"
0x2256  ldarg.1
0x2257  brtrue.s loc_225C
0x2259  ldc.i4.0
0x225a  br.s     loc_225D
0x225c  ldc.i4.1
0x225d  call     instance void NGenTask.TaskExecutive::SetRegistryFlagValue(string keyName, string valueName, int32 value)
0x2262  ret
```
