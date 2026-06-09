# TaskbarList::SetOverlayIcon(HWND__ *,HICON__ *,ushort const *)

- ea: `0x1800b9760`
- end: `0x1800b992c`
- name: `?SetOverlayIcon@TaskbarList@@UEAAJPEAUHWND__@@PEAUHICON__@@PEBG@Z`
- size: `460`
- prototype: `int(TaskbarList *__hidden this, HWND, HICON, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800b9760`

## import_xrefs

- `SHCORE!__imp_SHAllocShared` at `0x1800b9859`
- `SHCORE!__imp_SHAllocShared` at `0x1800b9859`
- `SHCORE!__imp_SHFreeShared` at `0x1800b98a9`
- `SHCORE!__imp_SHFreeShared` at `0x1800b98a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98b3`
- `USER32!CopyIcon` at `0x1800b97b4`
- `USER32!CopyIcon` at `0x1800b97b4`
- `USER32!IsWindow` at `0x1800b9796`
- `USER32!IsWindow` at `0x1800b9796`
- `USER32!GetPropW` at `0x1800b9903`
- `USER32!GetPropW` at `0x1800b9903`
- `USER32!SendNotifyMessageW` at `0x1800b991d`
- `USER32!SendNotifyMessageW` at `0x1800b991d`
- `USER32!FindWindowW` at `0x1800b98ea`
- `USER32!FindWindowW` at `0x1800b98ea`
- `USER32!SendMessageTimeoutW` at `0x1800b97ea`
- `USER32!SendMessageTimeoutW` at `0x1800b988f`
- `USER32!SendMessageTimeoutW` at `0x1800b97ea`
- `USER32!SendMessageTimeoutW` at `0x1800b988f`
- `USER32!GetWindowThreadProcessId` at `0x1800b9833`
- `USER32!GetWindowThreadProcessId` at `0x1800b9833`
- `USER32!DestroyIcon` at `0x1800b9808`
- `USER32!DestroyIcon` at `0x1800b9808`

## string_xrefs

- `0x1800b98f9`: `TaskbandHWND`

## pseudocode

```c

```
