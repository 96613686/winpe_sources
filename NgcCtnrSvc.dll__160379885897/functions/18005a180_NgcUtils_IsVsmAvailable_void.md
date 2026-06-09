# NgcUtils::IsVsmAvailable(void)

- ea: `0x18005a180`
- end: `0x18005a388`
- name: `?IsVsmAvailable@NgcUtils@@YA_NXZ`
- size: `520`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005a124`

## callees

- `0x180013c88`
- `0x18001ced8`
- `0x18002c640`
- `0x180037348`
- `0x18005a180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005a28b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005a2e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005a28b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005a2e1`
- `ntdll!NtQuerySystemInformation` at `0x18005a1d3`
- `ntdll!NtQuerySystemInformation` at `0x18005a1d3`

## string_xrefs

- `0x18005a1e7`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18005a2ae`: `EnableVirtualizationBasedSecurity`

## pseudocode

```c

```
