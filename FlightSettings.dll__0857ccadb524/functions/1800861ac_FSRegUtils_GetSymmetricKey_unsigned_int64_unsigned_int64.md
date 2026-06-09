# FSRegUtils::GetSymmetricKey(unsigned __int64,unsigned __int64 *)

- ea: `0x1800861ac`
- end: `0x180086260`
- name: `?GetSymmetricKey@FSRegUtils@@CAJ_KPEA_K@Z`
- size: `180`
- prototype: `__int64 __fastcall(HCRYPTPROV hProv, HCRYPTKEY *phKey)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008561c`
- `0x180085778`

## callees

- `0x18000cc6c`
- `0x1800855bc`
- `0x1800861ac`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800861d9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800861d9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800861fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800861fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180086236`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180086236`

## string_xrefs

- `0x180086211`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`

## pseudocode

```c

```
