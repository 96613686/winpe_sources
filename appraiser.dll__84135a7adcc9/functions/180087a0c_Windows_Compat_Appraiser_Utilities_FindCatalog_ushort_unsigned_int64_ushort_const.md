# Windows::Compat::Appraiser::Utilities::FindCatalog(ushort *,unsigned __int64,ushort const *)

- ea: `0x180087a0c`
- end: `0x180087ca0`
- name: `?FindCatalog@Utilities@Appraiser@Compat@Windows@@SAJPEAG_KPEBG@Z`
- size: `660`
- prototype: `static int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004ba00`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d20`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087a0c`
- `0x18008a488`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180087c64`
- `KERNEL32!GetProcessHeap` at `0x180087c64`
- `KERNEL32!GetLastError` at `0x180087b1d`
- `KERNEL32!GetLastError` at `0x180087b3c`
- `KERNEL32!GetLastError` at `0x180087b7e`
- `KERNEL32!GetLastError` at `0x180087b9d`
- `KERNEL32!GetLastError` at `0x180087b1d`
- `KERNEL32!GetLastError` at `0x180087b3c`
- `KERNEL32!GetLastError` at `0x180087b7e`
- `KERNEL32!GetLastError` at `0x180087b9d`
- `KERNEL32!HeapFree` at `0x180087c74`
- `KERNEL32!HeapFree` at `0x180087c74`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180087c56`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x180087c56`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180087c41`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x180087c41`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180087b0f`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x180087b0f`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180087b74`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180087b74`

## string_xrefs

- `0x180087aa1`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087ae3`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087bb8`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087c28`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087bf0`: `Error copying file path: [0x%x].`
- `0x180087c11`: `Error copying file path: [0x%x].`
- `0x180087aac`: `Windows::Compat::Appraiser::Utilities::FindCatalog`
- `0x180087ad7`: `Windows::Compat::Appraiser::Utilities::FindCatalog`
- `0x180087bc3`: `Windows::Compat::Appraiser::Utilities::FindCatalog`
- `0x180087c1c`: `Windows::Compat::Appraiser::Utilities::FindCatalog`

## pseudocode

```c

```
