# CUserManagement::s_GetUserSIDEx(ushort const *,CUserManagement::EAccountExists,void * *)

- ea: `0x14006b790`
- end: `0x14006ba88`
- name: `?s_GetUserSIDEx@CUserManagement@@SAJPEBGW4EAccountExists@1@PEAPEAX@Z`
- size: `760`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004e600`
- `0x1400520a0`
- `0x14006ada4`
- `0x14006c590`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006b790`

## import_xrefs

- `ADVAPI32!LookupAccountNameW` at `0x14006b89f`
- `ADVAPI32!LookupAccountNameW` at `0x14006ba28`
- `ADVAPI32!LookupAccountNameW` at `0x14006b89f`
- `ADVAPI32!LookupAccountNameW` at `0x14006ba28`
- `KERNEL32!GetLastError` at `0x14006b8ad`
- `KERNEL32!GetLastError` at `0x14006ba32`
- `KERNEL32!GetLastError` at `0x14006b8ad`
- `KERNEL32!GetLastError` at `0x14006ba32`
- `KERNEL32!IsDebuggerPresent` at `0x14006b815`
- `KERNEL32!IsDebuggerPresent` at `0x14006b90c`
- `KERNEL32!IsDebuggerPresent` at `0x14006b9af`
- `KERNEL32!IsDebuggerPresent` at `0x14006b815`
- `KERNEL32!IsDebuggerPresent` at `0x14006b90c`
- `KERNEL32!IsDebuggerPresent` at `0x14006b9af`

## string_xrefs

- `0x14006b7ef`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b8f0`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b989`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b7dd`: `CUserManagement::s_GetUserSIDEx`
- `0x14006b8e5`: `CUserManagement::s_GetUserSIDEx`
- `0x14006b978`: `CUserManagement::s_GetUserSIDEx`

## pseudocode

```c

```
