# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x180387324`
- end: `0x1803874b3`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `399`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180353180`

## callees

- `0x180142e10`
- `0x180387324`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803873b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1803873b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387457`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387457`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038739a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18038739a`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1803873cc`
- `USER32!__imp_GetProcessUIContextInformation` at `0x180387438`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1803873cc`
- `USER32!__imp_GetProcessUIContextInformation` at `0x180387438`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180387413`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180387413`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1803873f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1803873f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18038736b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18038736b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x180387473`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x180387473`

## pseudocode

```c

```
