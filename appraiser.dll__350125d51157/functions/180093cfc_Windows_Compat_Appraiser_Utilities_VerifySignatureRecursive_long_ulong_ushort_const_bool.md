# Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(long *,ulong *,ushort const *,bool)

- ea: `0x180093cfc`
- end: `0x180094333`
- name: `?VerifySignatureRecursive@Utilities@Appraiser@Compat@Windows@@SAJPEAJPEAKPEBG_N@Z`
- size: `1591`
- prototype: `__int64 __fastcall(int *, unsigned int *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039538`
- `0x18004608c`
- `0x18004ba00`
- `0x1800858c8`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18001a2f4`
- `0x1800301d0`
- `0x18008b878`
- `0x180093cfc`
- `0x1802174b4`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x180093ddb`
- `KERNEL32!InitOnceExecuteOnce` at `0x180093ddb`
- `KERNEL32!GetLastError` at `0x180093f87`
- `KERNEL32!GetLastError` at `0x180093fae`
- `KERNEL32!GetLastError` at `0x180093fcd`
- `KERNEL32!GetLastError` at `0x180094040`
- `KERNEL32!GetLastError` at `0x180094067`
- `KERNEL32!GetLastError` at `0x180094086`
- `KERNEL32!GetLastError` at `0x18009416d`
- `KERNEL32!GetLastError` at `0x180094194`
- `KERNEL32!GetLastError` at `0x1800941b3`
- `KERNEL32!GetLastError` at `0x180093f87`
- `KERNEL32!GetLastError` at `0x180093fae`
- `KERNEL32!GetLastError` at `0x180093fcd`
- `KERNEL32!GetLastError` at `0x180094040`
- `KERNEL32!GetLastError` at `0x180094067`
- `KERNEL32!GetLastError` at `0x180094086`
- `KERNEL32!GetLastError` at `0x18009416d`
- `KERNEL32!GetLastError` at `0x180094194`
- `KERNEL32!GetLastError` at `0x1800941b3`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18009413a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18009413a`
- `WINTRUST!WinVerifyTrust` at `0x180093e61`
- `WINTRUST!WinVerifyTrust` at `0x1800942d0`
- `WINTRUST!WinVerifyTrust` at `0x180093e61`
- `WINTRUST!WinVerifyTrust` at `0x1800942d0`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180093f34`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180093f34`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180094009`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180094009`

## string_xrefs

- `0x180093e9a`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093f0b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093f6c`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093fdc`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800940e2`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800941f8`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180094293`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180093d91`: `Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive`

## pseudocode

```c

```
