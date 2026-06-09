# CSearchServices::_VerifySourceWindowIsForeground(HWND__ *)

- ea: `0x180012544`
- end: `0x18001258c`
- name: `?_VerifySourceWindowIsForeground@CSearchServices@@AEAAJPEAUHWND__@@@Z`
- size: `72`
- prototype: `int(CSearchServices *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000eb10`
- `0x18000fb80`

## callees

- `0x180012544`

## import_xrefs

- `USER32!GetParent` at `0x180012571`
- `USER32!GetParent` at `0x180012571`
- `USER32!GetForegroundWindow` at `0x180012551`
- `USER32!GetForegroundWindow` at `0x180012551`

## pseudocode

```c

```
