# NGenTask.TaskExecutive::IsPendingUpdateFlagSet

- ea: `0x2220`
- end: `0x2240`
- name: `NGenTask.TaskExecutive::IsPendingUpdateFlagSet`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x20a0`
- `0x22e0`

## string_xrefs

- `0x2231`: `PendingUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x2220  ldarg.0
0x2221  ldarg.0
0x2222  call     instance string NGenTask.TaskExecutive::NGenServiceRegistryRoot()
0x2227  ldstr    aState// "State"
0x222c  call     string [mscorlib]System.String::Concat(string, string)
0x2231  ldstr    aPendingupdate// "PendingUpdate"
0x2236  ldc.i4.0
0x2237  call     instance int32 NGenTask.TaskExecutive::GetRegistryFlagValue(string keyName, string valueName, [opt] int32 defaultValue)
0x223c  ldc.i4.0
0x223d  cgt.un
0x223f  ret
```
