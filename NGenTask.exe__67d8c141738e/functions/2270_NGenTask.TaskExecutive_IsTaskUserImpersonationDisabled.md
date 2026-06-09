# NGenTask.TaskExecutive::IsTaskUserImpersonationDisabled

- ea: `0x2270`
- end: `0x2285`
- name: `NGenTask.TaskExecutive::IsTaskUserImpersonationDisabled`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x1560`

## callees

- `0x22e0`

## string_xrefs

- `0x2276`: `AssemblyUsageLogImpersonateUser`

## pseudocode

```c

```

## disassembly

```asm
0x2270  ldarg.0
0x2271  ldstr    aSoftwareMicros_5// "Software\\Microsoft\\.NETFramework"
0x2276  ldstr    aAssemblyusagel// "AssemblyUsageLogImpersonateUser"
0x227b  ldc.i4.1
0x227c  call     instance int32 NGenTask.TaskExecutive::GetRegistryFlagValue(string keyName, string valueName, [opt] int32 defaultValue)
0x2281  ldc.i4.0
0x2282  ceq
0x2284  ret
```
