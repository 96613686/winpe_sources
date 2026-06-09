# ImpersonateCore(ImpersonationType,int *,bool *)

- ea: `0x1800831b8`
- end: `0x1800833e6`
- name: `?ImpersonateCore@@YA_NW4ImpersonationType@@PEAHPEA_N@Z`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180083178`
- `0x180146568`

## callees

- `0x1800831b8`
- `0x180157094`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800832b5`
- `ADVAPI32!SetThreadToken` at `0x1800832b5`
- `KERNEL32!LeaveCriticalSection` at `0x1800831fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800832ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800831fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800832ec`
- `KERNEL32!EnterCriticalSection` at `0x1800831e0`
- `KERNEL32!EnterCriticalSection` at `0x1800831e0`
- `KERNEL32!TlsSetValue` at `0x18008326f`
- `KERNEL32!TlsSetValue` at `0x180083327`
- `KERNEL32!TlsSetValue` at `0x180083380`
- `KERNEL32!TlsSetValue` at `0x18008326f`
- `KERNEL32!TlsSetValue` at `0x180083327`
- `KERNEL32!TlsSetValue` at `0x180083380`
- `KERNEL32!TlsGetValue` at `0x180083202`
- `KERNEL32!TlsGetValue` at `0x180083202`
- `KERNEL32!TlsAlloc` at `0x1800832d3`
- `KERNEL32!TlsAlloc` at `0x1800832d3`
- `KERNEL32!ExitProcess` at `0x1800833c3`
- `KERNEL32!ExitProcess` at `0x1800833c3`

## pseudocode

```c

```
