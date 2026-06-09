# AppV::Client::Personation::Deimpersonate(void)

- ea: `0x140046e30`
- end: `0x140046ea1`
- name: `?Deimpersonate@Personation@Client@AppV@@MEAA_KXZ`
- size: `113`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Personation *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140046da0`

## callees

- `0x140018bec`
- `0x140046e30`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x140046e36`
- `ADVAPI32!RevertToSelf` at `0x140046e36`
- `KERNEL32!GetLastError` at `0x140046e77`
- `KERNEL32!GetLastError` at `0x140046e77`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046e4a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140046e4a`

## string_xrefs

- `0x140046e43`: `admin\appman\appv\client\common\impersonator.cpp`
- `0x140046e5a`: `admin\appman\appv\client\common\impersonator.cpp`

## pseudocode

```c

```
