# NgcUtils::IsVsmAvailable(void)

- ea: `0x18004a074`
- end: `0x18004a269`
- name: `?IsVsmAvailable@NgcUtils@@YA_NXZ`
- size: `501`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049edc`

## callees

- `0x180023190`
- `0x180038764`
- `0x18004a074`
- `0x18005cee0`
- `0x1800898dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a179`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a1c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a179`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004a1c9`
- `ntdll!NtQuerySystemInformation` at `0x18004a0c7`
- `ntdll!NtQuerySystemInformation` at `0x18004a0c7`

## string_xrefs

- `0x18004a0d5`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18004a196`: `EnableVirtualizationBasedSecurity`

## pseudocode

```c

```
