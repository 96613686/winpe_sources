# LocationCallerInfoHelper::GetAppUserModelIdFromProcessId(ulong,ushort * *)

- ea: `0x18003baf4`
- end: `0x18003bc3c`
- name: `?GetAppUserModelIdFromProcessId@LocationCallerInfoHelper@@SAJKPEAPEAG@Z`
- size: `328`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001fbe8`
- `0x18003ba40`

## callees

- `0x18003baf4`
- `0x18003bc44`
- `0x18003c214`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bc13`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bba9`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb78`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003bb4b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003bb4b`

## pseudocode

```c

```
