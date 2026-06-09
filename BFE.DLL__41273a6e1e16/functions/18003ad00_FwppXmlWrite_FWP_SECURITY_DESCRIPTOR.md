# FwppXmlWrite_FWP_SECURITY_DESCRIPTOR

- ea: `0x18003ad00`
- end: `0x18003adca`
- name: `FwppXmlWrite_FWP_SECURITY_DESCRIPTOR`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003bfb0`
- `0x18003c2e4`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18003ad00`
- `0x18003cbd0`
- `0x180058abc`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ad93`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18003ad3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18003ad3f`

## string_xrefs

- `0x18003ad5e`: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- `0x18003ada4`: `FwppXmlWrite_FWP_SECURITY_DESCRIPTOR`

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
0x18003ad00  push    rbx
0x18003ad02  sub     rsp, 40h
0x18003ad06  mov     rax, cs:__security_cookie
0x18003ad0d  xor     rax, rsp
0x18003ad10  mov     [rsp+48h+var_10], rax
0x18003ad15  mov     rax, r8
0x18003ad18  mov     [rsp+48h+StringSecurityDescriptor], 0
0x18003ad21  mov     edx, 1; RequestedStringSDRevision
0x18003ad26  mov     [rsp+48h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x18003ad2f  mov     rbx, rcx
0x18003ad32  lea     r9, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18003ad37  mov     rcx, [rax+8]; SecurityDescriptor
0x18003ad3b  lea     r8d, [rdx+0Eh]; SecurityInformation
0x18003ad3f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18003ad46  nop     dword ptr [rax+rax+00h]
0x18003ad4b  test    eax, eax
0x18003ad4d  jnz     short loc_18003AD6F
0x18003ad4f  call    cs:__imp_GetLastError
0x18003ad56  nop     dword ptr [rax+rax+00h]
0x18003ad5b  mov     r8d, eax
0x18003ad5e  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x18003ad65  call    WfpReportSysErrorAsWinError
0x18003ad6a  mov     rbx, rax
0x18003ad6d  jmp     short loc_18003AD9F
0x18003ad6f  mov     rcx, [rsp+48h+StringSecurityDescriptor]
0x18003ad74  call    FwppConvertUnicodeToUtf8Unsafe
0x18003ad79  mov     r8, rax
0x18003ad7c  lea     rdx, aSd; "sd"
0x18003ad83  mov     rcx, rbx
0x18003ad86  call    FwppXmlWriteElementUnsafe
0x18003ad8b  mov     rcx, [rsp+48h+StringSecurityDescriptor]; hMem
0x18003ad90  mov     rbx, rax
0x18003ad93  call    cs:__imp_LocalFree
0x18003ad9a  nop     dword ptr [rax+rax+00h]
0x18003ad9f  test    rbx, rbx
0x18003ada2  jz      short loc_18003ADB3
0x18003ada4  lea     rdx, aFwppxmlwriteFw; "FwppXmlWrite_FWP_SECURITY_DESCRIPTOR"
0x18003adab  mov     rcx, rbx
0x18003adae  call    WfpReportError
0x18003adb3  mov     rax, rbx
0x18003adb6  mov     rcx, [rsp+48h+var_10]
0x18003adbb  xor     rcx, rsp; StackCookie
0x18003adbe  call    __security_check_cookie
0x18003adc3  add     rsp, 40h
0x18003adc7  pop     rbx
0x18003adc8  retn
```
