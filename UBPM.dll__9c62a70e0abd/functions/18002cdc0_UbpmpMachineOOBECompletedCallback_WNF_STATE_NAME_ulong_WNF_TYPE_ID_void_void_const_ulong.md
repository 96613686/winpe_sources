# UbpmpMachineOOBECompletedCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18002cdc0`
- end: `0x18002ce91`
- name: `?UbpmpMachineOOBECompletedCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800101a0`
- `0x1800103c0`
- `0x18002cdc0`
- `0x180038814`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ce33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002ce33`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ce51`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ce51`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ce69`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ce69`

## pseudocode

```c

```
