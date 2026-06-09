# CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)

- ea: `0x1800d7cdc`
- end: `0x1800d7d79`
- name: `?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, enum PROCESS_UICONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800ccecc`

## callees

- `0x18003aa84`
- `0x1800d7cdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d7d1b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d7d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7d61`
- `USER32!GetWindowThreadProcessId` at `0x1800d7cfa`
- `USER32!GetWindowThreadProcessId` at `0x1800d7cfa`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7d45`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7d45`

## pseudocode

```c

```
