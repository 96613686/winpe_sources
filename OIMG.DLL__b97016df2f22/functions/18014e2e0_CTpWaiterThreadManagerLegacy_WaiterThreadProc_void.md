# CTpWaiterThreadManagerLegacy::WaiterThreadProc(void *)

- ea: `0x18014e2e0`
- end: `0x18014e901`
- name: `?WaiterThreadProc@CTpWaiterThreadManagerLegacy@@CAKPEAX@Z`
- size: `1569`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180013080`
- `0x18001373c`
- `0x180130fa8`
- `0x1801473fc`
- `0x18014d6dc`
- `0x18014e2e0`
- `0x18014eb98`
- `0x18014ec48`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18014e57f`
- `KERNEL32!LeaveCriticalSection` at `0x18014e57f`
- `KERNEL32!GetTickCount64` at `0x18014e593`
- `KERNEL32!GetTickCount64` at `0x18014e70e`
- `KERNEL32!GetTickCount64` at `0x18014e593`
- `KERNEL32!GetTickCount64` at `0x18014e70e`
- `KERNEL32!WaitForSingleObject` at `0x18014e7f7`
- `KERNEL32!WaitForSingleObject` at `0x18014e7f7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014e62e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014e62e`
- `USER32!PeekMessageW` at `0x18014e7c4`
- `USER32!PeekMessageW` at `0x18014e7c4`
- `USER32!TranslateMessage` at `0x18014e7a4`
- `USER32!TranslateMessage` at `0x18014e7a4`
- `USER32!DispatchMessageW` at `0x18014e7ae`
- `USER32!DispatchMessageW` at `0x18014e7ae`
- `USER32!MsgWaitForMultipleObjects` at `0x18014e5c6`
- `USER32!MsgWaitForMultipleObjects` at `0x18014e5c6`
- `ADVAPI32!RevertToSelf` at `0x18014e3ab`
- `ADVAPI32!RevertToSelf` at `0x18014e3ab`

## pseudocode

```c

```
