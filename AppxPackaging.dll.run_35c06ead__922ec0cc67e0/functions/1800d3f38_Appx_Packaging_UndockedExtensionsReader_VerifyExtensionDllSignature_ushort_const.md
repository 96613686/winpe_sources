# Appx::Packaging::UndockedExtensionsReader::VerifyExtensionDllSignature(ushort const *)

- ea: `0x1800d3f38`
- end: `0x1800d412c`
- name: `?VerifyExtensionDllSignature@UndockedExtensionsReader@Packaging@Appx@@SAJPEBG@Z`
- size: `500`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800b5298`

## callees

- `0x1800133fc`
- `0x18006a900`
- `0x1800992a0`
- `0x180099e38`
- `0x1800d3f38`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800d4067`
- `ntdll!NtQuerySystemInformation` at `0x1800d4067`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800d3fe7`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1800d3fe7`
- `WINTRUST!WinVerifyTrust` at `0x1800d3fc9`
- `WINTRUST!WinVerifyTrust` at `0x1800d4100`
- `WINTRUST!WinVerifyTrust` at `0x1800d3fc9`
- `WINTRUST!WinVerifyTrust` at `0x1800d4100`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800d401f`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800d401f`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800d40ac`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x1800d40ac`

## string_xrefs

- `0x1800d4001`: `onecore\printscan\appxpackaging\undockedextensions\src\undockedextensionsreader.cpp`
- `0x1800d40d5`: `onecore\printscan\appxpackaging\undockedextensions\src\undockedextensionsreader.cpp`

## pseudocode

```c

```
