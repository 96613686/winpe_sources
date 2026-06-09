# PcapArpKeysPopulate(_PCA_ARP_MONITOR *)

- ea: `0x180034490`
- end: `0x1800347c4`
- name: `?PcapArpKeysPopulate@@YAKPEAU_PCA_ARP_MONITOR@@@Z`
- size: `820`
- prototype: `unsigned int __fastcall(struct _PCA_ARP_MONITOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800340f0`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x1800182e0`
- `0x180018768`
- `0x180022bc8`
- `0x1800236d8`
- `0x180034368`
- `0x180034490`
- `0x1800b81b0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180034606`
- `msvcrt!_wcsnicmp` at `0x180034606`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034691`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034617`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800345db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800345db`

## string_xrefs

- `0x1800344e3`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800346bb`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180034523`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180034563`: `Failed to create Wow64 Arp key [%d]`
- `0x180034510`: `Failed to create Arp key [%d]`
- `0x180034726`: `Failed to create user ARP key %S [%d]`

## pseudocode

```c

```
