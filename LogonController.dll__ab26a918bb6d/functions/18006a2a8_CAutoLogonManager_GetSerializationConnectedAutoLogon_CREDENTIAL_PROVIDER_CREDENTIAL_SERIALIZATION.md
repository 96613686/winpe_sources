# CAutoLogonManager::_GetSerializationConnectedAutoLogon(_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)

- ea: `0x18006a2a8`
- end: `0x18006a516`
- name: `?_GetSerializationConnectedAutoLogon@CAutoLogonManager@@AEAAJPEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CAutoLogonManager *__hidden this, struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003e160`

## callees

- `0x18004391c`
- `0x18005d488`
- `0x18005d4e8`
- `0x180062760`
- `0x18006a2a8`
- `0x18006a51c`
- `0x1800919d8`
- `0x1800921d4`

## import_xrefs

- `KERNEL32!LocalSize` at `0x18006a3ff`
- `KERNEL32!LocalSize` at `0x18006a487`
- `KERNEL32!LocalSize` at `0x18006a4cd`
- `KERNEL32!LocalSize` at `0x18006a3ff`
- `KERNEL32!LocalSize` at `0x18006a487`
- `KERNEL32!LocalSize` at `0x18006a4cd`
- `KERNEL32!LocalFree` at `0x18006a41c`
- `KERNEL32!LocalFree` at `0x18006a4ea`
- `KERNEL32!LocalFree` at `0x18006a41c`
- `KERNEL32!LocalFree` at `0x18006a4ea`
- `SspiCli!SspiLocalFree` at `0x18006a479`
- `SspiCli!SspiLocalFree` at `0x18006a479`
- `CRYPT32!CryptUnprotectData` at `0x18006a387`
- `CRYPT32!CryptUnprotectData` at `0x18006a387`

## string_xrefs

- `0x18006a32e`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18006a395`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18006a3e3`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18006a44b`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`

## pseudocode

```c

```
