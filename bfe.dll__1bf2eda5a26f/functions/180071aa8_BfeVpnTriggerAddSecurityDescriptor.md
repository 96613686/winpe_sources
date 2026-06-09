# BfeVpnTriggerAddSecurityDescriptor

- ea: `0x180071aa8`
- end: `0x180071b9b`
- name: `BfeVpnTriggerAddSecurityDescriptor`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064220`

## callees

- `0x180010360`
- `0x180018b74`
- `0x180024078`
- `0x180058b30`
- `0x18006c338`
- `0x180071aa8`
- `0x18007226c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071b66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071b66`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180071b45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180071b45`

## string_xrefs

- `0x180071b71`: `BfeVpnTriggerAddSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BfeVpnTriggerAddSecurityDescriptor(__int64 a1)
{
  __int64 v2; // rbx
  void *v4; // rcx
  LPWSTR StringSecurityDescriptor[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_OWORD *)StringSecurityDescriptor = 0;
  v2 = BfeAccessCheck((char *)qword_1800F2668[55], 0x400u, 0);
  if ( v2 )
    goto LABEL_14;
  if ( (qword_1800F2668[368] & 0x10) != 0
     ? qword_1800F2668[368] & 1
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
0x180071aa8  mov     [rsp+arg_8], rbx
0x180071aad  push    rdi
0x180071aae  sub     rsp, 50h
0x180071ab2  mov     rax, cs:__security_cookie
0x180071ab9  xor     rax, rsp
0x180071abc  mov     [rsp+58h+var_18], rax
0x180071ac1  mov     rdi, rcx
0x180071ac4  xorps   xmm0, xmm0
0x180071ac7  mov     rcx, cs:qword_1800F2668+1B8h; pSecurityDescriptor
0x180071ace  xor     r8d, r8d
0x180071ad1  mov     edx, 400h
0x180071ad6  movups  xmmword ptr [rsp+58h+StringSecurityDescriptor], xmm0
0x180071adb  call    BfeAccessCheck
0x180071ae0  mov     rbx, rax
0x180071ae3  test    rax, rax
0x180071ae6  jnz     loc_180071B71
0x180071aec  mov     eax, dword ptr cs:qword_1800F2668+0B80h
0x180071af2  test    al, 10h
0x180071af4  jz      short loc_180071AFB
0x180071af6  and     eax, 1
0x180071af9  jmp     short loc_180071B00
0x180071afb  call    Feature_NetSec_SFI_BFE_VpnTrigger_SD_Validation__private_IsEnabledDeviceUsageNoInline
0x180071b00  test    eax, eax
0x180071b02  jz      short loc_180071B25
0x180071b04  test    rdi, rdi
0x180071b07  jz      short loc_180071B80
0x180071b09  mov     edx, [rdi]
0x180071b0b  test    edx, edx
0x180071b0d  jz      short loc_180071B80
0x180071b0f  mov     rcx, [rdi+8]; SecurityDescriptor
0x180071b13  test    rcx, rcx
0x180071b16  jz      short loc_180071B80
0x180071b18  call    BfeRelativeSecurityDescriptorValidate
0x180071b1d  mov     rbx, rax
0x180071b20  test    rax, rax
0x180071b23  jnz     short loc_180071B71
0x180071b25  mov     edx, 1; RequestedStringSDRevision
0x180071b2a  mov     [rsp+58h+StringSecurityDescriptor], rdi
0x180071b2f  mov     rcx, [rdi+8]; SecurityDescriptor
0x180071b33  lea     r9, [rsp+58h+StringSecurityDescriptor+8]; StringSecurityDescriptor
0x180071b38  mov     [rsp+58h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x180071b41  lea     r8d, [rdx+0Eh]; SecurityInformation
0x180071b45  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180071b4b  test    eax, eax
0x180071b4d  jz      short loc_180071B80
0x180071b4f  lea     rcx, [rsp+58h+StringSecurityDescriptor]
0x180071b54  call    BfeDriverAddVpnSecurityDescriptor
0x180071b59  mov     rcx, [rsp+58h+StringSecurityDescriptor+8]; hMem
0x180071b5e  mov     rbx, rax
0x180071b61  test    rcx, rcx
0x180071b64  jz      short loc_180071B6C
0x180071b66  call    cs:__imp_LocalFree
0x180071b6c  test    rbx, rbx
0x180071b6f  jz      short loc_180071B80
0x180071b71  lea     rdx, aBfevpntriggera; "BfeVpnTriggerAddSecurityDescriptor"
0x180071b78  mov     rcx, rbx
0x180071b7b  call    WfpReportError
0x180071b80  mov     rax, rbx
0x180071b83  mov     rcx, [rsp+58h+var_18]
0x180071b88  xor     rcx, rsp; StackCookie
0x180071b8b  call    __security_check_cookie
0x180071b90  mov     rbx, [rsp+58h+arg_8]
0x180071b95  add     rsp, 50h
0x180071b99  pop     rdi
0x180071b9a  retn
```
