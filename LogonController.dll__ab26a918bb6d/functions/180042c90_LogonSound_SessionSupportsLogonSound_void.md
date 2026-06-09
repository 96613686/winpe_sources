# LogonSound::_SessionSupportsLogonSound(void)

- ea: `0x180042c90`
- end: `0x180042d5e`
- name: `?_SessionSupportsLogonSound@LogonSound@@AEAA_NXZ`
- size: `206`
- prototype: `bool __fastcall(LogonSound *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180042c18`

## callees

- `0x180042c90`
- `0x18004a788`
- `0x18006c000`
- `0x18006cad0`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x180042cca`
- `KERNEL32!GetVersionExW` at `0x180042cca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042d35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d56`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180042ce7`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180042ce7`

## pseudocode

```c

```
