# BaseRegEnumKeyOld

- ea: `0x1800600c0`
- end: `0x180060f3c`
- name: `BaseRegEnumKeyOld`
- size: `3708`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG Index@<edx>, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051430`
- `0x1800fc9a0`

## callees

- `0x18005d2c0`
- `0x18005f0f8`
- `0x18005f5a0`
- `0x18005f5f0`
- `0x1800600c0`
- `0x180060f50`
- `0x180061268`
- `0x180061560`
- `0x180061588`
- `0x18012d578`
- `0x180188eb9`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800602d2`
- `ntdll!RtlEnterCriticalSection` at `0x180060728`
- `ntdll!RtlEnterCriticalSection` at `0x1800602d2`
- `ntdll!RtlEnterCriticalSection` at `0x180060728`
- `ntdll!RtlLeaveCriticalSection` at `0x1800608b9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800608c6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800608b9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800608c6`
- `ntdll!RtlNtStatusToDosError` at `0x180060214`
- `ntdll!RtlNtStatusToDosError` at `0x180060214`
- `ntdll!NtEnumerateKey` at `0x180060175`
- `ntdll!NtEnumerateKey` at `0x1800605ac`
- `ntdll!NtEnumerateKey` at `0x1800607a0`
- `ntdll!NtEnumerateKey` at `0x180060bef`
- `ntdll!NtEnumerateKey` at `0x180060d6d`
- `ntdll!NtEnumerateKey` at `0x180060e1c`
- `ntdll!NtEnumerateKey` at `0x180060175`
- `ntdll!NtEnumerateKey` at `0x1800605ac`
- `ntdll!NtEnumerateKey` at `0x1800607a0`
- `ntdll!NtEnumerateKey` at `0x180060bef`
- `ntdll!NtEnumerateKey` at `0x180060d6d`
- `ntdll!NtEnumerateKey` at `0x180060e1c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800602bc`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180060ee3`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800602bc`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180060ee3`
- `ntdll!RtlCompareUnicodeString` at `0x1800604b5`
- `ntdll!RtlCompareUnicodeString` at `0x1800604b5`
- `ntdll!RtlFreeHeap` at `0x18006020c`
- `ntdll!RtlFreeHeap` at `0x180060542`
- `ntdll!RtlFreeHeap` at `0x180060823`
- `ntdll!RtlFreeHeap` at `0x18006092b`
- `ntdll!RtlFreeHeap` at `0x18006020c`
- `ntdll!RtlFreeHeap` at `0x180060542`
- `ntdll!RtlFreeHeap` at `0x180060823`
- `ntdll!RtlFreeHeap` at `0x18006092b`
- `ntdll!RtlAllocateHeap` at `0x180060285`
- `ntdll!RtlAllocateHeap` at `0x180060d2e`
- `ntdll!RtlAllocateHeap` at `0x180060d92`
- `ntdll!RtlAllocateHeap` at `0x180060285`
- `ntdll!RtlAllocateHeap` at `0x180060d2e`
- `ntdll!RtlAllocateHeap` at `0x180060d92`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegEnumKey` at `0x180060267`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegEnumKey` at `0x180060267`

## pseudocode

```c

```
