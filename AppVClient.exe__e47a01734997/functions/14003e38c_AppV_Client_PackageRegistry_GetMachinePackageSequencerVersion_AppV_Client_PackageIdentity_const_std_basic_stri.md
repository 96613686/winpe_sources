# AppV::Client::PackageRegistry::GetMachinePackageSequencerVersion(AppV::Client::PackageIdentity const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x14003e38c`
- end: `0x14003e4d6`
- name: `?GetMachinePackageSequencerVersion@PackageRegistry@Client@AppV@@SA_KAEBUPackageIdentity@23@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14002b460`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140018bec`
- `0x14003e264`
- `0x14003e38c`
- `0x140040750`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003e424`
- `ADVAPI32!RegCloseKey` at `0x14003e4a2`
- `ADVAPI32!RegCloseKey` at `0x14003e424`
- `ADVAPI32!RegCloseKey` at `0x14003e4a2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003e453`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003e453`

## string_xrefs

- `0x14003e44c`: `admin\appman\appv\shared\client\packageregistry\packageregistry.cpp`
- `0x14003e463`: `admin\appman\appv\shared\client\packageregistry\packageregistry.cpp`

## pseudocode

```c

```
