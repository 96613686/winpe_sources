# CCompDBList::VerifyCompDbCabSignature(wchar_t const * const,bool,bool *)

- ea: `0x180158fdc`
- end: `0x1801597f7`
- name: `?VerifyCompDbCabSignature@CCompDBList@@AEAAJQEB_W_NPEA_N@Z`
- size: `2075`
- prototype: `__int64 __fastcall(CCompDBList *__hidden this, const wchar_t *const, bool, bool *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180156d38`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3bc`
- `0x1800bd064`
- `0x180154ecc`
- `0x180155134`
- `0x18015826c`
- `0x180158fdc`
- `0x180190844`
- `0x1801dd0a0`
- `0x1802b1010`

## import_xrefs

- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1801591ed`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1801591ed`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18015929f`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18015934b`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18015929f`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18015934b`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180159139`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180159139`
- `WINTRUST!WinVerifyTrust` at `0x1801590da`
- `WINTRUST!WinVerifyTrust` at `0x180159123`
- `WINTRUST!WinVerifyTrust` at `0x1801591ce`
- `WINTRUST!WinVerifyTrust` at `0x180159285`
- `WINTRUST!WinVerifyTrust` at `0x180159334`
- `WINTRUST!WinVerifyTrust` at `0x1801593e0`
- `WINTRUST!WinVerifyTrust` at `0x1801594f3`
- `WINTRUST!WinVerifyTrust` at `0x1801595c2`
- `WINTRUST!WinVerifyTrust` at `0x1801596d3`
- `WINTRUST!WinVerifyTrust` at `0x18015977e`
- `WINTRUST!WinVerifyTrust` at `0x1801597ac`
- `WINTRUST!WinVerifyTrust` at `0x1801590da`
- `WINTRUST!WinVerifyTrust` at `0x180159123`
- `WINTRUST!WinVerifyTrust` at `0x1801591ce`
- `WINTRUST!WinVerifyTrust` at `0x180159285`
- `WINTRUST!WinVerifyTrust` at `0x180159334`
- `WINTRUST!WinVerifyTrust` at `0x1801593e0`
- `WINTRUST!WinVerifyTrust` at `0x1801594f3`
- `WINTRUST!WinVerifyTrust` at `0x1801595c2`
- `WINTRUST!WinVerifyTrust` at `0x1801596d3`
- `WINTRUST!WinVerifyTrust` at `0x18015977e`
- `WINTRUST!WinVerifyTrust` at `0x1801597ac`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159413`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159447`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159612`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159413`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159447`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180159612`

## string_xrefs

- `0x1801591a9`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x180159260`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x18015930f`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1801593bb`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1801594c9`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x180159595`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1801596a7`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`

## pseudocode

```c

```
