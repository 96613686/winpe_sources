# Mso::Security::EnsureAce(void *,_SE_OBJECT_TYPE,uchar,_SID const &,ushort,uchar,ulong)

- ea: `0x1809c1540`
- end: `0x1809c1da7`
- name: `?EnsureAce@Security@Mso@@YA_NPEAXW4_SE_OBJECT_TYPE@@EAEBU_SID@@GEK@Z`
- size: `2151`
- prototype: `bool __usercall@<al>(HANDLE handle@<rcx>, SE_OBJECT_TYPE ObjectType@<edx>, enum _SE_OBJECT_TYPE@<r8d>, unsigned __int8@<r9b>, const struct _SID *, unsigned __int16, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1809c1388`
- `0x1819d7c84`

## callees

- `0x180405fa8`
- `0x180485240`
- `0x1809c1540`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1809c16c6`
- `KERNEL32!GetLastError` at `0x1809c188f`
- `KERNEL32!GetLastError` at `0x1809c196d`
- `KERNEL32!GetLastError` at `0x1809c1a82`
- `KERNEL32!GetLastError` at `0x1809c1b11`
- `KERNEL32!GetLastError` at `0x1809c1bbf`
- `KERNEL32!GetLastError` at `0x1809c1c7c`
- `KERNEL32!GetLastError` at `0x1809c1c8d`
- `KERNEL32!GetLastError` at `0x1809c16c6`
- `KERNEL32!GetLastError` at `0x1809c188f`
- `KERNEL32!GetLastError` at `0x1809c196d`
- `KERNEL32!GetLastError` at `0x1809c1a82`
- `KERNEL32!GetLastError` at `0x1809c1b11`
- `KERNEL32!GetLastError` at `0x1809c1bbf`
- `KERNEL32!GetLastError` at `0x1809c1c7c`
- `KERNEL32!GetLastError` at `0x1809c1c8d`
- `KERNEL32!LocalFree` at `0x1809c1882`
- `KERNEL32!LocalFree` at `0x1809c1d7e`
- `KERNEL32!LocalFree` at `0x1809c1882`
- `KERNEL32!LocalFree` at `0x1809c1d7e`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c163f`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1706`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1827`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c18cf`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c19af`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1ac5`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1b54`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1c01`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1d04`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c163f`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1706`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1827`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c18cf`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c19af`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1ac5`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1b54`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1c01`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1809c1d04`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1809c1695`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1809c1d57`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1809c1695`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1809c1d57`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809c1d65`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809c1d95`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809c1d65`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1809c1d95`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1809c1596`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1809c1596`
- `ADVAPI32!SetSecurityInfo` at `0x1809c17df`
- `ADVAPI32!SetSecurityInfo` at `0x1809c1cba`
- `ADVAPI32!SetSecurityInfo` at `0x1809c17df`
- `ADVAPI32!SetSecurityInfo` at `0x1809c1cba`
- `ADVAPI32!GetSecurityInfo` at `0x1809c15f6`
- `ADVAPI32!GetSecurityInfo` at `0x1809c15f6`
- `ADVAPI32!AddAce` at `0x1809c1a74`
- `ADVAPI32!AddAce` at `0x1809c1bb5`
- `ADVAPI32!AddAce` at `0x1809c1c6e`
- `ADVAPI32!AddAce` at `0x1809c1a74`
- `ADVAPI32!AddAce` at `0x1809c1bb5`
- `ADVAPI32!AddAce` at `0x1809c1c6e`
- `ADVAPI32!InitializeAcl` at `0x1809c195f`
- `ADVAPI32!InitializeAcl` at `0x1809c195f`
- `ADVAPI32!EqualSid` at `0x1809c178d`
- `ADVAPI32!EqualSid` at `0x1809c178d`
- `ADVAPI32!CopySid` at `0x1809c1a20`
- `ADVAPI32!CopySid` at `0x1809c1a20`
- `ADVAPI32!GetAce` at `0x1809c176e`
- `ADVAPI32!GetAce` at `0x1809c1a45`
- `ADVAPI32!GetAce` at `0x1809c1c4d`
- `ADVAPI32!GetAce` at `0x1809c176e`
- `ADVAPI32!GetAce` at `0x1809c1a45`
- `ADVAPI32!GetAce` at `0x1809c1c4d`
- `ADVAPI32!GetAclInformation` at `0x1809c16b8`
- `ADVAPI32!GetAclInformation` at `0x1809c16b8`

## string_xrefs

- `0x1809c167f`: `Failed to get Object Security`
- `0x1809c19ef`: `Failed to initialize ACL`
- `0x1809c1867`: `Failed to set Object Security`
- `0x1809c1d40`: `Failed to set Object Security`
- `0x1809c1746`: `Failed to get ACL`

## pseudocode

```c

```
