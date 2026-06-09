# CSebHelper::PublishSmsNotification(_GUID,ulong,bool,uint,uchar const *,uint)

- ea: `0x1800654c8`
- end: `0x18006569f`
- name: `?PublishSmsNotification@CSebHelper@@SAJU_GUID@@K_NIPEBEI@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, bool, unsigned int, const unsigned __int8 *Src, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004eea4`

## callees

- `0x180003a60`
- `0x180004980`
- `0x180004998`
- `0x180051628`
- `0x1800654c8`
- `0x1800696fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800655b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800655b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006559b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006559b`

## string_xrefs

- `0x180065588`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c

```
