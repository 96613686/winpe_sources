# CProcessStateManager::_InitializeFirstLogon(void)

- ea: `0x18000df3c`
- end: `0x18000dff5`
- name: `?_InitializeFirstLogon@CProcessStateManager@@AEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d2c8`

## callees

- `0x18000df3c`
- `0x180044490`
- `0x18004f618`

## import_xrefs

- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18000df45`
- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18000df45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000df90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dfe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dfe9`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000df58`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000df58`

## pseudocode

```c

```
