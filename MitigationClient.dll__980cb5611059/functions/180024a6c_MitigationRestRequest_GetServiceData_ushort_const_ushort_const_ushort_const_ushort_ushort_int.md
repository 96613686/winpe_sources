# MitigationRestRequest::GetServiceData(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,int &)

- ea: `0x180024a6c`
- end: `0x180024d2d`
- name: `?GetServiceData@MitigationRestRequest@@AEAAJPEBG00PEAPEAG1AEAH@Z`
- size: `705`
- prototype: `__int64 __fastcall(MitigationRestRequest *this, MitigationRequestPayload *, const unsigned __int16 *, const unsigned __int16 *, RTL_SRWLOCK *SRWLock, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18001da18`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x1800156b8`
- `0x18002407c`
- `0x180024918`
- `0x180024a6c`
- `0x180026c1c`
- `0x180026cc8`
- `0x180027acc`
- `0x180028480`
- `0x18002a488`
- `0x180042ac8`
- `0x180042edc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024c78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024c78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024d15`

## pseudocode

```c

```
