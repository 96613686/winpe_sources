# BfeVpnTriggerAddSecurityDescriptor

- ea: `0x1800742ec`
- end: `0x1800743f0`
- name: `BfeVpnTriggerAddSecurityDescriptor`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066580`

## callees

- `0x180010d60`
- `0x1800197d0`
- `0x180026a1c`
- `0x18005aa60`
- `0x18006e9f4`
- `0x1800742ec`
- `0x180074af8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800743b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800743b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18007438d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18007438d`

## string_xrefs

- `0x1800743c5`: `BfeVpnTriggerAddSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BfeVpnTriggerAddSecurityDescriptor(__int64 a1)
{
  __int64 v2; // rbx
  void *v4; // rcx
  LPWSTR StringSecurityDescriptor[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)StringSecurityDescriptor = 0;
  v2 = BfeAccessCheck((char *)gBfeVpnTriggerEventController, 0x400u, 0);
  if ( v2 )
    goto LABEL_14;
  if ( (Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_featureState & 0x10) != 0
     ? Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_featureState & 1
     : Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !a1 )
      return v2;
    if ( !*(_DWORD *)a1 )
      return v2;
    v4 = *(void **)(a1 + 8);
    if ( !v4 )
      return v2;
    v2 = BfeRelativeSecurityDescriptorValidate(v4, *(_DWORD *)a1);
    if ( v2 )
    {
LABEL_14:
      WfpReportError(v2, "BfeVpnTriggerAddSecurityDescriptor");
      return v2;
    }
  }
  StringSecurityDescriptor[0] = (LPWSTR)a1;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         *(PSECURITY_DESCRIPTOR *)(a1 + 8),
         1u,
         0xFu,
         &StringSecurityDescriptor[1],
         0) )
  {
    v2 = BfeDriverAddVpnSecurityDescriptor(StringSecurityDescriptor);
    if ( StringSecurityDescriptor[1] )
      LocalFree(StringSecurityDescriptor[1]);
    if ( v2 )
      goto LABEL_14;
  }
  return v2;
}

```

## disassembly

```asm
0x1800742ec  mov     [rsp+arg_8], rbx
0x1800742f1  push    rdi
0x1800742f2  sub     rsp, 50h
0x1800742f6  mov     rax, cs:__security_cookie
0x1800742fd  xor     rax, rsp
0x180074300  mov     [rsp+58h+var_18], rax
0x180074305  mov     rdi, rcx
0x180074308  xorps   xmm0, xmm0
0x18007430b  mov     rcx, qword ptr cs:gBfeVpnTriggerEventController; pSecurityDescriptor
0x180074312  xor     r8d, r8d
0x180074315  mov     edx, 400h
0x18007431a  movups  xmmword ptr [rsp+58h+StringSecurityDescriptor], xmm0
0x18007431f  call    BfeAccessCheck
0x180074324  mov     rbx, rax
0x180074327  test    rax, rax
0x18007432a  jnz     loc_1800743C5
0x180074330  mov     eax, cs:Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_featureState
0x180074336  test    al, 10h
0x180074338  jz      short loc_18007433F
0x18007433a  and     eax, 1
0x18007433d  jmp     short loc_180074344
0x18007433f  call    Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_IsEnabledDeviceUsageNoInline
0x180074344  test    eax, eax
0x180074346  jz      short loc_18007436D
0x180074348  test    rdi, rdi
0x18007434b  jz      loc_1800743D4
0x180074351  mov     edx, [rdi]
0x180074353  test    edx, edx
0x180074355  jz      short loc_1800743D4
0x180074357  mov     rcx, [rdi+8]; SecurityDescriptor
0x18007435b  test    rcx, rcx
0x18007435e  jz      short loc_1800743D4
0x180074360  call    BfeRelativeSecurityDescriptorValidate
0x180074365  mov     rbx, rax
0x180074368  test    rax, rax
0x18007436b  jnz     short loc_1800743C5
0x18007436d  mov     edx, 1; RequestedStringSDRevision
0x180074372  mov     [rsp+58h+StringSecurityDescriptor], rdi
0x180074377  mov     rcx, [rdi+8]; SecurityDescriptor
0x18007437b  lea     r9, [rsp+58h+StringSecurityDescriptor+8]; StringSecurityDescriptor
0x180074380  mov     [rsp+58h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180074389  lea     r8d, [rdx+0Eh]; SecurityInformation
0x18007438d  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180074394  nop     dword ptr [rax+rax+00h]
0x180074399  test    eax, eax
0x18007439b  jz      short loc_1800743D4
0x18007439d  lea     rcx, [rsp+58h+StringSecurityDescriptor]
0x1800743a2  call    BfeDriverAddVpnSecurityDescriptor
0x1800743a7  mov     rcx, [rsp+58h+StringSecurityDescriptor+8]; hMem
0x1800743ac  mov     rbx, rax
0x1800743af  test    rcx, rcx
0x1800743b2  jz      short loc_1800743C0
0x1800743b4  call    cs:__imp_LocalFree
0x1800743bb  nop     dword ptr [rax+rax+00h]
0x1800743c0  test    rbx, rbx
0x1800743c3  jz      short loc_1800743D4
0x1800743c5  lea     rdx, aBfevpntriggera; "BfeVpnTriggerAddSecurityDescriptor"
0x1800743cc  mov     rcx, rbx
0x1800743cf  call    WfpReportError
0x1800743d4  mov     rax, rbx
0x1800743d7  mov     rcx, [rsp+58h+var_18]
0x1800743dc  xor     rcx, rsp; StackCookie
0x1800743df  call    __security_check_cookie
0x1800743e4  mov     rbx, [rsp+58h+arg_8]
0x1800743e9  add     rsp, 50h
0x1800743ed  pop     rdi
0x1800743ee  retn
```
