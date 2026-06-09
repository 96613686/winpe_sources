# SdbpCustomDbRegInfoCheckForExePointer

- ea: `0x180216448`
- end: `0x180216a85`
- name: `SdbpCustomDbRegInfoCheckForExePointer`
- size: `1597`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802157d4`

## callees

- `0x180008570`
- `0x1800091bc`
- `0x1800092dc`
- `0x180017f48`
- `0x180019594`
- `0x18001a2f4`
- `0x180216448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180216786`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180216a1e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180216786`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180216a1e`
- `ntdll!NtClose` at `0x1802165c7`
- `ntdll!NtClose` at `0x1802167c1`
- `ntdll!NtClose` at `0x1802167d1`
- `ntdll!NtClose` at `0x1802167e1`
- `ntdll!NtClose` at `0x1802165c7`
- `ntdll!NtClose` at `0x1802167c1`
- `ntdll!NtClose` at `0x1802167d1`
- `ntdll!NtClose` at `0x1802167e1`
- `ntdll!NtQueryKey` at `0x180216572`
- `ntdll!NtQueryKey` at `0x1802166f0`
- `ntdll!NtQueryKey` at `0x180216976`
- `ntdll!NtQueryKey` at `0x180216572`
- `ntdll!NtQueryKey` at `0x1802166f0`
- `ntdll!NtQueryKey` at `0x180216976`
- `ntdll!NtEnumerateKey` at `0x18021660a`
- `ntdll!NtEnumerateKey` at `0x18021660a`
- `ntdll!NtEnumerateValueKey` at `0x180216740`
- `ntdll!NtEnumerateValueKey` at `0x1802169e4`
- `ntdll!NtEnumerateValueKey` at `0x180216740`
- `ntdll!NtEnumerateValueKey` at `0x1802169e4`

## string_xrefs

- `0x18021652c`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x180216525`: `Failed to open key "%ws" [%x]`
- `0x18021669d`: `Failed to open key "%ws" [%x]`
- `0x180216930`: `Failed to open key "%ws" [%x]`
- `0x1802164f8`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x180216657`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x180216875`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x180216898`: `Failed to printf the Custom\Layers key path [%x]`
- `0x1802168d7`: `Failed to printf the Custom EXE key path (index %d) [%x]`

## pseudocode

```c

```
