# MaybeCreateDocWindow(ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x18007b3d0`
- end: `0x18007b648`
- name: `?MaybeCreateDocWindow@@YAJGGPEAUHWND__@@0@Z`
- size: `632`
- prototype: `HRESULT __fastcall(unsigned __int16 aClass, unsigned __int16 aFile, HWND__ *hwndDdeServer, HWND__ *hwndSender)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007b8b8`

## callees

- `0x180052390`
- `0x180073ac8`
- `0x18007b3d0`
- `0x18007c644`
- `0x18007dcf0`
- `0x18007dfa4`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007b460`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18007b460`
- `USER32!GetWindowLongPtrW` at `0x18007b57c`
- `USER32!GetWindowLongPtrW` at `0x18007b57c`
- `USER32!SendMessageW` at `0x18007b4f4`
- `USER32!SendMessageW` at `0x18007b56d`
- `USER32!SendMessageW` at `0x18007b5d5`
- `USER32!SendMessageW` at `0x18007b4f4`
- `USER32!SendMessageW` at `0x18007b56d`
- `USER32!SendMessageW` at `0x18007b5d5`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x18007b4c6`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x18007b4d9`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x18007b4c6`
- `api-ms-win-core-com-private-l1-1-0!InternalCCGetClassInformationForDde` at `0x18007b4d9`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007b48d`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007b48d`

## pseudocode

```c

```
