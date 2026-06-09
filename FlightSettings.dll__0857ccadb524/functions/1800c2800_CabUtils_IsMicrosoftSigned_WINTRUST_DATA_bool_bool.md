# CabUtils::IsMicrosoftSigned(_WINTRUST_DATA,bool,bool)

- ea: `0x1800c2800`
- end: `0x1800c2a1a`
- name: `?IsMicrosoftSigned@CabUtils@@CAJU_WINTRUST_DATA@@_N1@Z`
- size: `538`
- prototype: `__int64 __fastcall(struct _WINTRUST_DATA *__struct_ptr, bool, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c264c`
- `0x1800c2bb0`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x1800c1ca8`
- `0x1800c2800`

## import_xrefs

- `CRYPT32!CertGetNameStringW` at `0x1800c28ce`
- `CRYPT32!CertGetNameStringW` at `0x1800c28ce`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800c2987`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800c2987`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800c2849`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800c2849`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800c287f`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800c287f`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800c289c`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800c290d`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800c289c`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x1800c290d`

## string_xrefs

- `0x1800c2863`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c28e8`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c29b9`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`

## pseudocode

```c

```
