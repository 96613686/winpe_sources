# CloudAPHelper::Initialize(_GUID const &)

- ea: `0x18015a5e4`
- end: `0x18015a975`
- name: `?Initialize@CloudAPHelper@@QEAAJAEBU_GUID@@@Z`
- size: `913`
- prototype: `int(CloudAPHelper *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180159e30`

## callees

- `0x18000146c`
- `0x18000202c`
- `0x18007e9e0`
- `0x18015a5e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18015a69d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18015a69d`
- `SspiCli!LsaConnectUntrusted` at `0x18015a7c7`
- `SspiCli!LsaConnectUntrusted` at `0x18015a7c7`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18015a811`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18015a8a0`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18015a811`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18015a8a0`

## string_xrefs

- `0x18015a6ed`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a8f2`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18015a7a5`: `StringCchCopyN(m_wszCorrelationId) failed`

## pseudocode

```c

```
