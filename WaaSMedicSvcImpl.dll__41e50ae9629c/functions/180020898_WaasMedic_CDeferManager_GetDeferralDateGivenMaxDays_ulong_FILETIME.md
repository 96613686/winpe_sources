# WaasMedic::CDeferManager::GetDeferralDateGivenMaxDays(ulong,_FILETIME &)

- ea: `0x180020898`
- end: `0x180020945`
- name: `?GetDeferralDateGivenMaxDays@CDeferManager@WaasMedic@@AEAAXKAEAU_FILETIME@@@Z`
- size: `173`
- prototype: `void(WaasMedic::CDeferManager *__hidden this, unsigned int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800202d8`

## callees

- `0x18002e81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800208cd`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800208cd`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800208c7`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800208c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800208bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800208dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800208bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800208dd`

## string_xrefs

- `0x18002091d`: `Will defer the plugin for after %d days. (Max provided was %d.)`

## pseudocode

```c

```
