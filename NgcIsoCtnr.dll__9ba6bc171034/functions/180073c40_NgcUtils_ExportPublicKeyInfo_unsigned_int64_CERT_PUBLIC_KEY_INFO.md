# NgcUtils::ExportPublicKeyInfo(unsigned __int64,_CERT_PUBLIC_KEY_INFO * *)

- ea: `0x180073c40`
- end: `0x180073d5b`
- name: `?ExportPublicKeyInfo@NgcUtils@@YAJ_KPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hCryptProvOrNCryptKey, unsigned __int64, struct _CERT_PUBLIC_KEY_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180072218`

## callees

- `0x18000d60c`
- `0x18000d62c`
- `0x1800721d0`
- `0x180073c40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073d3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073d3c`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x180073c87`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x180073d12`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x180073c87`
- `CRYPT32!CryptExportPublicKeyInfoEx` at `0x180073d12`

## string_xrefs

- `0x180073c96`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180073cc9`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180073d21`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c

```
