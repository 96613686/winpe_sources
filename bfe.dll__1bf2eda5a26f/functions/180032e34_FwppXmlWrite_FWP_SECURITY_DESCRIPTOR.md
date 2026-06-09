# FwppXmlWrite_FWP_SECURITY_DESCRIPTOR

- ea: `0x180032e34`
- end: `0x180032eeb`
- name: `FwppXmlWrite_FWP_SECURITY_DESCRIPTOR`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003189c`
- `0x180031bcc`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x180032494`
- `0x180032e34`
- `0x180056bf4`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ebb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ebb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180032e73`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180032e73`

## string_xrefs

- `0x180032e86`: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- `0x180032ec6`: `FwppXmlWrite_FWP_SECURITY_DESCRIPTOR`

## pseudocode

```c
__int64 __fastcall FwppXmlWrite_FWP_SECURITY_DESCRIPTOR(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax
  LPWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-18h] BYREF

  StringSecurityDescriptor = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         *(PSECURITY_DESCRIPTOR *)(a3 + 8),
         1u,
         0xFu,
         &StringSecurityDescriptor,
         0) )
  {
    v7 = FwppConvertUnicodeToUtf8Unsafe(StringSecurityDescriptor);
    v6 = FwppXmlWriteElementUnsafe(a1, "sd", v7);
    LocalFree(StringSecurityDescriptor);
  }
  else
  {
    LastError = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v5, "ConvertSecurityDescriptorToStringSecurityDescriptorW", LastError);
  }
  if ( v6 )
    WfpReportError(v6, "FwppXmlWrite_FWP_SECURITY_DESCRIPTOR");
  return v6;
}

```

## disassembly

```asm
0x180032e34  push    rbx
0x180032e36  sub     rsp, 40h
0x180032e3a  mov     rax, cs:__security_cookie
0x180032e41  xor     rax, rsp
0x180032e44  mov     [rsp+48h+var_10], rax
0x180032e49  mov     rax, r8
0x180032e4c  mov     [rsp+48h+StringSecurityDescriptor], 0
0x180032e55  mov     edx, 1; RequestedStringSDRevision
0x180032e5a  mov     [rsp+48h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180032e63  mov     rbx, rcx
0x180032e66  lea     r9, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180032e6b  mov     rcx, [rax+8]; SecurityDescriptor
0x180032e6f  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180032e73  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180032e79  test    eax, eax
0x180032e7b  jnz     short loc_180032E97
0x180032e7d  call    cs:__imp_GetLastError
0x180032e83  mov     r8d, eax
0x180032e86  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x180032e8d  call    WfpReportSysErrorAsWinError
0x180032e92  mov     rbx, rax
0x180032e95  jmp     short loc_180032EC1
0x180032e97  mov     rcx, [rsp+48h+StringSecurityDescriptor]
0x180032e9c  call    FwppConvertUnicodeToUtf8Unsafe
0x180032ea1  mov     r8, rax
0x180032ea4  lea     rdx, aSd; "sd"
0x180032eab  mov     rcx, rbx
0x180032eae  call    FwppXmlWriteElementUnsafe
0x180032eb3  mov     rcx, [rsp+48h+StringSecurityDescriptor]; hMem
0x180032eb8  mov     rbx, rax
0x180032ebb  call    cs:__imp_LocalFree
0x180032ec1  test    rbx, rbx
0x180032ec4  jz      short loc_180032ED5
0x180032ec6  lea     rdx, aFwppxmlwriteFw; "FwppXmlWrite_FWP_SECURITY_DESCRIPTOR"
0x180032ecd  mov     rcx, rbx
0x180032ed0  call    WfpReportError
0x180032ed5  mov     rax, rbx
0x180032ed8  mov     rcx, [rsp+48h+var_10]
0x180032edd  xor     rcx, rsp; StackCookie
0x180032ee0  call    __security_check_cookie
0x180032ee5  add     rsp, 40h
0x180032ee9  pop     rbx
0x180032eea  retn
```
