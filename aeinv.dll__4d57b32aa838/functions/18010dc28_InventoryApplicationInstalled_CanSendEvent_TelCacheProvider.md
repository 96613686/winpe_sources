# InventoryApplicationInstalled::CanSendEvent(TelCacheProvider &)

- ea: `0x18010dc28`
- end: `0x18010dd02`
- name: `?CanSendEvent@InventoryApplicationInstalled@@CA_NAEAVTelCacheProvider@@@Z`
- size: `218`
- prototype: `bool __fastcall(struct TelCacheProvider *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18010dd68`

## callees

- `0x18010dc28`
- `0x18010dd08`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18010dcac`
- `ADVAPI32!RegGetValueW` at `0x18010dcac`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010dcca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010dcca`

## string_xrefs

- `0x18010dc88`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ApplicationInstalled`
- `0x18010dc6f`: `AeinvInventoryApplicationInstalledEventFrequency`

## pseudocode

```c

```
