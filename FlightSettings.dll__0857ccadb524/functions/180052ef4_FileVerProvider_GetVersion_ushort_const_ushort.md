# FileVerProvider::GetVersion(ushort const *,ushort * *)

- ea: `0x180052ef4`
- end: `0x1800530af`
- name: `?GetVersion@FileVerProvider@@SAJPEBGPEAPEAG@Z`
- size: `443`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d9ac`
- `0x180052e40`

## callees

- `0x18000aa48`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18002035c`
- `0x1800254ac`
- `0x18002f830`
- `0x180052ef4`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180052fbd`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180052fbd`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180052f1f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180052f1f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180052f76`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180052f76`

## string_xrefs

- `0x180052f85`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`
- `0x180052fe1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`
- `0x180053049`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`

## pseudocode

```c

```
