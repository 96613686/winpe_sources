# TelemetryProvider::FullSyncRequestedByOneSettings(ushort const *,unsigned __int64 &)

- ea: `0x1800bf0c4`
- end: `0x1800bf28d`
- name: `?FullSyncRequestedByOneSettings@TelemetryProvider@@CA_NPEBGAEA_K@Z`
- size: `457`
- prototype: `bool __fastcall(LPCWSTR lpValue, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bf5d8`

## callees

- `0x180003100`
- `0x18000543c`
- `0x1800152d0`
- `0x1800bf0c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800bf20a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800bf20a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf159`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf1de`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf159`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bf1de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bf246`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bf246`

## string_xrefs

- `0x1800bf13a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderFullSync`
- `0x1800bf1bf`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\ProviderFullSync`

## pseudocode

```c

```
