# BrpRpcContextCreate(void *,unsigned __int64,void *,void (*)(unsigned __int64,void *,_BR_EVENT_CALL_REASON),unsigned __int64 *)

- ea: `0x1800692a0`
- end: `0x1800693dc`
- name: `?BrpRpcContextCreate@@YAKPEAX_K0P6AX10W4_BR_EVENT_CALL_REASON@@@ZPEA_K@Z`
- size: `316`
- prototype: `unsigned int __usercall@<eax>(HANDLE ProcessHandle@<rcx>, unsigned __int64@<rdx>, void *@<r8>, void (__high *)(unsigned __int64, void *, enum _BR_EVENT_CALL_REASON)@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003c580`

## callees

- `0x180004998`
- `0x1800691a0`
- `0x1800692a0`
- `0x1800693e4`
- `0x180069458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800692ba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800692ba`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180069354`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180069354`
- `ntdll!TpSetWaitEx` at `0x180069399`
- `ntdll!TpSetWaitEx` at `0x180069399`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800693a2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800693b7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800693a2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800693b7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006936a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006936a`
- `ntdll!NtDuplicateObject` at `0x18006932d`
- `ntdll!NtDuplicateObject` at `0x18006932d`
- `ntdll!TpAllocWait` at `0x180069348`
- `ntdll!TpAllocWait` at `0x180069348`

## pseudocode

```c

```
