# CCodecFactory::IsCLSIDDisabled(_GUID const &)

- ea: `0x180040b90`
- end: `0x180040c09`
- name: `?IsCLSIDDisabled@CCodecFactory@@SAHAEBU_GUID@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e760`
- `0x18003f614`
- `0x180040788`
- `0x180040ab4`
- `0x180072bd0`
- `0x180073448`
- `0x180073d2c`
- `0x18008fe60`

## callees

- `0x180040b90`
- `0x18007d6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040bbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bac`

## pseudocode

```c

```
