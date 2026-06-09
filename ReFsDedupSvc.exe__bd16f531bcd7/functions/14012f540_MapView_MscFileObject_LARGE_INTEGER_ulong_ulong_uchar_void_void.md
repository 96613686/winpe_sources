# MapView(MscFileObject *,_LARGE_INTEGER *,ulong,ulong,uchar *,void * *,void * *)

- ea: `0x14012f540`
- end: `0x14012f79f`
- name: `?MapView@@YAEPEAUMscFileObject@@PEAT_LARGE_INTEGER@@KKPEAEPEAPEAX3@Z`
- size: `607`
- prototype: `unsigned __int8(struct MscFileObject *, union _LARGE_INTEGER *, unsigned int, unsigned int, unsigned __int8 *, void **, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14012f97c`
- `0x14012fc10`

## callees

- `0x140004c1c`
- `0x14007fe5c`
- `0x14012f42c`
- `0x14012f4f4`
- `0x14012f540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14012f693`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14012f693`
- `ntdll!RtlFillMemoryNonTemporal` at `0x14012f665`
- `ntdll!RtlFillMemoryNonTemporal` at `0x14012f665`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012f5b4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012f674`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012f5b4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012f674`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f5e7`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f628`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f6c2`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f6f9`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f73d`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f5e7`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f628`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f6c2`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f6f9`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012f73d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f5f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f636`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f6d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f707`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f74b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f5f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f636`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f6d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f707`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012f74b`
- `ntdll!RtlAcquireSRWLockShared` at `0x14012f608`
- `ntdll!RtlAcquireSRWLockShared` at `0x14012f6df`
- `ntdll!RtlAcquireSRWLockShared` at `0x14012f608`
- `ntdll!RtlAcquireSRWLockShared` at `0x14012f6df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14012f720`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14012f720`

## pseudocode

```c

```
