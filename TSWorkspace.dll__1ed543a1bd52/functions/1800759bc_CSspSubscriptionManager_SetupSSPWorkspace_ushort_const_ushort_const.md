# CSspSubscriptionManager::SetupSSPWorkspace(ushort const *,ushort const *)

- ea: `0x1800759bc`
- end: `0x180075d29`
- name: `?SetupSSPWorkspace@CSspSubscriptionManager@@QEAAJPEBG0@Z`
- size: `877`
- prototype: `__int64 __fastcall(CSspSubscriptionManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180076c00`

## callees

- `0x180005500`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000eed0`
- `0x18002eae0`
- `0x18002f810`
- `0x1800301c4`
- `0x18003246c`
- `0x1800387e4`
- `0x1800759bc`
- `0x180078650`

## import_xrefs

- `USER32!TranslateMessage` at `0x180075ca5`
- `USER32!TranslateMessage` at `0x180075ca5`
- `USER32!PostQuitMessage` at `0x180075cb9`
- `USER32!PostQuitMessage` at `0x180075cb9`
- `USER32!GetMessageW` at `0x180075c85`
- `USER32!GetMessageW` at `0x180075c85`
- `USER32!DispatchMessageW` at `0x180075caf`
- `USER32!DispatchMessageW` at `0x180075caf`

## string_xrefs

- `0x180075bab`: `Could not delete the workspace `

## pseudocode

```c

```
