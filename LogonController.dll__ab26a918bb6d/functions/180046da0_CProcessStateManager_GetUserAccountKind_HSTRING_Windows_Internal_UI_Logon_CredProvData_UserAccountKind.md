# CProcessStateManager::GetUserAccountKind(HSTRING__ *,Windows::Internal::UI::Logon::CredProvData::UserAccountKind *)

- ea: `0x180046da0`
- end: `0x180046e52`
- name: `?GetUserAccountKind@CProcessStateManager@@UEAAJPEAUHSTRING__@@PEAW4UserAccountKind@CredProvData@Logon@UI@Internal@Windows@@@Z`
- size: `178`
- prototype: `int(CProcessStateManager *__hidden this, HSTRING, enum Windows::Internal::UI::Logon::CredProvData::UserAccountKind *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180046da0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180046dff`
- `KERNEL32!LocalFree` at `0x180046dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046dc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046dd4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046dd4`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180046df0`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180046df0`

## pseudocode

```c

```
