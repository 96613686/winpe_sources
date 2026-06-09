# DisableAgentAccount

- ea: `0x180043304`
- end: `0x180043455`
- name: `DisableAgentAccount`
- size: `337`
- prototype: `__int64 __fastcall(LPCWSTR username)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800414dc`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x180043304`

## import_xrefs

- `NETAPI32!NetUserGetInfo` at `0x180043346`
- `NETAPI32!NetUserGetInfo` at `0x180043346`
- `NETAPI32!NetApiBufferFree` at `0x180043396`
- `NETAPI32!NetApiBufferFree` at `0x18004342e`
- `NETAPI32!NetApiBufferFree` at `0x180043396`
- `NETAPI32!NetApiBufferFree` at `0x18004342e`
- `NETAPI32!NetUserSetInfo` at `0x1800433dd`
- `NETAPI32!NetUserSetInfo` at `0x1800433dd`

## string_xrefs

- `0x180043443`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x1800433ad`: `Disabling AU: Account %s already disabled.`

## pseudocode

```c

```
