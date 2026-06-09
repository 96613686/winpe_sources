# BfeRelativeSecurityDescriptorValidate

- ea: `0x180026a1c`
- end: `0x180026b51`
- name: `BfeRelativeSecurityDescriptorValidate`
- size: `309`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009220`
- `0x18000a770`
- `0x18000ada0`
- `0x180025a10`
- `0x1800268f0`
- `0x1800305e0`
- `0x180031aa8`
- `0x1800742ec`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180026a1c`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlGetSaclSecurityDescriptor` at `0x180026a6c`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x180026a6c`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180026a4a`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180026a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ac2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180026aab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180026aab`

## string_xrefs

- `0x180026ad6`: `RtlValidRelativeSecurityDescriptor`
- `0x180026b1a`: `RtlGetSaclSecurityDescriptor`
- `0x180026b37`: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- `0x180026b0e`: `BfeRelativeSecurityDescriptorValidate`
- `0x180026b40`: `BfeRelativeSecurityDescriptorValidate`

## pseudocode

```c
__int64 __fastcall BfeRelativeSecurityDescriptorValidate(PSECURITY_DESCRIPTOR SecurityDescriptor, ULONG a2)
{
  __int64 v3; // rcx
  NTSTATUS SaclSecurityDescriptor; // eax
  __int64 v5; // rbx
  __int64 LastError; // r8
  const char *v7; // rdx
  __int64 v8; // rax
  PACL Sacl; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 SaclPresent; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int8 SaclDefaulted[7]; // [rsp+41h] [rbp-17h] BYREF

  SaclPresent = 0;
  SaclDefaulted[0] = 0;
  Sacl = 0;
  if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptor, a2, 0) )
  {
    LastError = 1338;
    v7 = "RtlValidRelativeSecurityDescriptor";
LABEL_7:
    v8 = WfpReportSysErrorAsWinError(v3, v7, LastError);
    goto LABEL_8;
  }
  SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, SaclDefaulted);
  if ( SaclSecurityDescriptor >= 0 )
  {
    if ( Sacl && SaclPresent )
    {
      LastError = 50;
      v7 = "BfeRelativeSecurityDescriptorValidate";
    }
    else
    {
      StringSecurityDescriptor = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
             SecurityDescriptor,
             1u,
             0xFu,
             &StringSecurityDescriptor,
             0) )
      {
        v5 = 0;
        LocalFree(StringSecurityDescriptor);
        return v5;
      }
      LastError = GetLastError();
      v7 = "ConvertSecurityDescriptorToStringSecurityDescriptorW";
    }
    goto LABEL_7;
  }
  v8 = WfpReportSysErrorAsNtStatus(v3, "RtlGetSaclSecurityDescriptor", (unsigned int)SaclSecurityDescriptor);
LABEL_8:
  v5 = v8;
  if ( v8 )
    WfpReportError(v8, "BfeRelativeSecurityDescriptorValidate");
  return v5;
}

```

## disassembly

```asm
0x180026a1c  push    rbx
0x180026a1e  sub     rsp, 50h
0x180026a22  mov     rax, cs:__security_cookie
0x180026a29  xor     rax, rsp
0x180026a2c  mov     [rsp+58h+var_10], rax
0x180026a31  xor     r8d, r8d; RequiredInformation
0x180026a34  mov     [rsp+58h+SaclPresent], 0
0x180026a39  mov     rbx, rcx
0x180026a3c  mov     [rsp+58h+SaclDefaulted], 0
0x180026a41  mov     [rsp+58h+Sacl], 0
0x180026a4a  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180026a51  nop     dword ptr [rax+rax+00h]
0x180026a56  test    al, al
0x180026a58  jz      short loc_180026AD0
0x180026a5a  lea     r9, [rsp+58h+SaclDefaulted]; SaclDefaulted
0x180026a5f  mov     rcx, rbx; SecurityDescriptor
0x180026a62  lea     r8, [rsp+58h+Sacl]; Sacl
0x180026a67  lea     rdx, [rsp+58h+SaclPresent]; SaclPresent
0x180026a6c  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x180026a73  nop     dword ptr [rax+rax+00h]
0x180026a78  test    eax, eax
0x180026a7a  js      loc_180026B17
0x180026a80  cmp     [rsp+58h+Sacl], 0
0x180026a86  jnz     short loc_180026B01
0x180026a88  mov     edx, 1; RequestedStringSDRevision
0x180026a8d  mov     [rsp+58h+StringSecurityDescriptor], 0
0x180026a96  lea     r9, [rsp+58h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180026a9b  mov     [rsp+58h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180026aa4  mov     rcx, rbx; SecurityDescriptor
0x180026aa7  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180026aab  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180026ab2  nop     dword ptr [rax+rax+00h]
0x180026ab7  test    eax, eax
0x180026ab9  jz      short loc_180026B28
0x180026abb  mov     rcx, [rsp+58h+StringSecurityDescriptor]; hMem
0x180026ac0  xor     ebx, ebx
0x180026ac2  call    cs:__imp_LocalFree
0x180026ac9  nop     dword ptr [rax+rax+00h]
0x180026ace  jmp     short loc_180026AEA
0x180026ad0  mov     r8d, 53Ah
0x180026ad6  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x180026add  call    WfpReportSysErrorAsWinError
0x180026ae2  mov     rbx, rax
0x180026ae5  test    rax, rax
0x180026ae8  jnz     short loc_180026B40
0x180026aea  mov     rax, rbx
0x180026aed  mov     rcx, [rsp+58h+var_10]
0x180026af2  xor     rcx, rsp; StackCookie
0x180026af5  call    __security_check_cookie
0x180026afa  add     rsp, 50h
0x180026afe  pop     rbx
0x180026aff  retn
0x180026b01  cmp     [rsp+58h+SaclPresent], 0
0x180026b06  jz      short loc_180026A88
0x180026b08  mov     r8d, 32h ; '2'
0x180026b0e  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x180026b15  jmp     short loc_180026ADD
0x180026b17  mov     r8d, eax
0x180026b1a  lea     rdx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor"
0x180026b21  call    WfpReportSysErrorAsNtStatus
0x180026b26  jmp     short loc_180026AE2
0x180026b28  call    cs:__imp_GetLastError
0x180026b2f  nop     dword ptr [rax+rax+00h]
0x180026b34  mov     r8d, eax
0x180026b37  lea     rdx, aConvertsecurit_0; "ConvertSecurityDescriptorToStringSecuri"...
0x180026b3e  jmp     short loc_180026ADD
0x180026b40  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x180026b47  mov     rcx, rbx
0x180026b4a  call    WfpReportError
0x180026b4f  jmp     short loc_180026AEA
```
