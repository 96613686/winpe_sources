# DisableLocalAccount

- ea: `0x1800a6340`
- end: `0x1800a6400`
- name: `DisableLocalAccount`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180099258`

## callees

- `0x180048304`
- `0x1800a6340`

## import_xrefs

- `samcli!NetUserSetInfo` at `0x1800a63a8`
- `samcli!NetUserSetInfo` at `0x1800a63a8`
- `samcli!NetUserGetInfo` at `0x1800a6367`
- `samcli!NetUserGetInfo` at `0x1800a6367`
- `netutils!NetApiBufferFree` at `0x1800a63c3`
- `netutils!NetApiBufferFree` at `0x1800a63f2`
- `netutils!NetApiBufferFree` at `0x1800a63c3`
- `netutils!NetApiBufferFree` at `0x1800a63f2`

## string_xrefs

- `0x1800a63d7`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c

```
