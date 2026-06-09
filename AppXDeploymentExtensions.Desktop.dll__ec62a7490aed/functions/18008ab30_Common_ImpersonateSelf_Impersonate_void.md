# Common::ImpersonateSelf::Impersonate(void)

- ea: `0x18008ab30`
- end: `0x18008abed`
- name: `?Impersonate@ImpersonateSelf@Common@@QEAAJXZ`
- size: `189`
- prototype: `int(Common::ImpersonateSelf *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a774`
- `0x18008aa14`
- `0x1800ed294`
- `0x180184d94`

## callees

- `0x180012fc8`
- `0x180022598`
- `0x18008ab30`
- `0x180173890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008abbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008abbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008abaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008abaa`
- `ADVAPI32!ImpersonateSelf` at `0x18008ab92`
- `ADVAPI32!ImpersonateSelf` at `0x18008ab92`
- `ADVAPI32!RevertToSelf` at `0x18008ab77`
- `ADVAPI32!RevertToSelf` at `0x18008ab77`

## string_xrefs

- `0x18008ab5c`: `onecore\admin\appmodel\common\impersonateself.cpp`

## pseudocode

```c

```
