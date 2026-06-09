# CFsm::Run(_INTERNET_THREAD_INFO *,ulong *,void *,ulong *)

- ea: `0x180060650`
- end: `0x180060d1f`
- name: `?Run@CFsm@@QEAAKPEAU_INTERNET_THREAD_INFO@@PEAKPEAX1@Z`
- size: `1743`
- prototype: `unsigned int __fastcall(CFsm *__hidden this, struct _INTERNET_THREAD_INFO *, unsigned int *, void *, unsigned int *)`
- caller_count: `10`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800393e0`
- `0x18003990c`
- `0x18004b698`
- `0x180053934`
- `0x18005f360`
- `0x18005fa40`
- `0x18005fc70`
- `0x1800d30c8`
- `0x18011e2f4`
- `0x1801a2a70`

## callees

- `0x180060650`
- `0x180064060`
- `0x1800641c0`
- `0x1800c60c8`
- `0x180102904`
- `0x18014a7a0`
- `0x1801b13f8`
- `0x1801c9c31`
- `0x1801e1790`
- `0x1801e5e10`
- `0x1801e8948`
- `0x1801e99c4`
- `0x1801ea814`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006090a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006090a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800608be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800608be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800609c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800609c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180060950`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180060950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180060958`
- `ntdll!EtwEventActivityIdControl` at `0x180060793`
- `ntdll!EtwEventActivityIdControl` at `0x1800607d7`
- `ntdll!EtwEventActivityIdControl` at `0x1800608ee`
- `ntdll!EtwEventActivityIdControl` at `0x180060793`
- `ntdll!EtwEventActivityIdControl` at `0x1800607d7`
- `ntdll!EtwEventActivityIdControl` at `0x1800608ee`
- `ntdll!RtlGetLastNtStatus` at `0x1800609d3`
- `ntdll!RtlGetLastNtStatus` at `0x1800609d3`

## pseudocode

```c

```
