# CabUtils::GetWinTrustDataForFileInCatalog(void *,ushort const *,_WINTRUST_DATA *,_GUID *)

- ea: `0x1800c21fc`
- end: `0x1800c250b`
- name: `?GetWinTrustDataForFileInCatalog@CabUtils@@CAJPEAXPEBGPEAU_WINTRUST_DATA@@PEAU_GUID@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(HANDLE hFile, const unsigned __int16 *, struct _WINTRUST_DATA *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c264c`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x1800c21fc`

## import_xrefs

- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c2265`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800c2265`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1800c233e`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1800c233e`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800c22ac`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800c22ac`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800c22da`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800c22da`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c2295`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c2320`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c247a`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c24e4`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c2295`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c2320`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c247a`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800c24e4`
- `WINTRUST!WinVerifyTrust` at `0x1800c2419`
- `WINTRUST!WinVerifyTrust` at `0x1800c2437`
- `WINTRUST!WinVerifyTrust` at `0x1800c2419`
- `WINTRUST!WinVerifyTrust` at `0x1800c2437`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c230e`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c2468`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c24d2`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c230e`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c2468`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x1800c24d2`

## string_xrefs

- `0x1800c227b`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c22f0`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c234f`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c2444`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`

## pseudocode

```c

```
