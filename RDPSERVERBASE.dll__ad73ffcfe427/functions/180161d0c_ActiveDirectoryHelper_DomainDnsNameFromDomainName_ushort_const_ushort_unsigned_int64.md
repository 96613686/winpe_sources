# ActiveDirectoryHelper::DomainDnsNameFromDomainName(ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x180161d0c`
- end: `0x180162012`
- name: `?DomainDnsNameFromDomainName@ActiveDirectoryHelper@@AEAAJPEBGPEAPEAGPEA_K@Z`
- size: `774`
- prototype: `__int64 __fastcall(ActiveDirectoryHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18016278c`

## callees

- `0x18000202c`
- `0x18003b118`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1800ac9f4`
- `0x180161d0c`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180161fed`
- `netutils!NetApiBufferFree` at `0x180161fed`
- `logoncli!DsGetDcNameW` at `0x180161d52`
- `logoncli!DsGetDcNameW` at `0x180161d52`

## string_xrefs

- `0x180161f6c`: `StringCchCopy failed`
- `0x180161da2`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180161e4a`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180161efc`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180161f90`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`

## pseudocode

```c

```
