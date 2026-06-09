# CWwanDeviceEnumerator::getDeviceProperties(_GUID const &,PnpDeviceProperties &)

- ea: `0x18001ac1c`
- end: `0x18001ae0d`
- name: `?getDeviceProperties@CWwanDeviceEnumerator@@AEBAKAEBU_GUID@@AEAUPnpDeviceProperties@@@Z`
- size: `497`
- prototype: `unsigned int(CWwanDeviceEnumerator *__hidden this, const struct _GUID *, struct PnpDeviceProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b928`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001a968`
- `0x18001aa1c`
- `0x18001ac1c`
- `0x18001ae14`
- `0x18001afa4`
- `0x18001b328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acb8`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001ade8`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001ade8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001acae`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001acae`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001ac55`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001ac55`

## string_xrefs

- `0x18001ac6a`: `DevObjCreateDeviceInfoList Failure %x`

## pseudocode

```c

```
