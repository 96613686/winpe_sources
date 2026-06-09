# FwppSecurityDescriptorSetInfo

- ea: `0x18000fe2c`
- end: `0x18000ff38`
- name: `FwppSecurityDescriptorSetInfo`
- size: `268`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PACL Dacl, PACL Sacl)`
- caller_count: `13`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e6a0`
- `0x18000f240`
- `0x180053660`
- `0x180053db0`
- `0x180054000`
- `0x180054d50`
- `0x180056260`
- `0x180056770`
- `0x180057050`
- `0x1800573a0`
- `0x180057880`
- `0x180057c30`
- `0x180058ee0`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x18000fe2c`

## import_xrefs

- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x18000fef5`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x18000fef5`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x18000fec7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x18000fec7`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x18000fe9b`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x18000fe9b`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x18000fe70`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x18000fe70`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18000fe45`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18000fe45`

## string_xrefs

- `0x18000fe55`: `RtlCreateSecurityDescriptor`
- `0x18000fe80`: `RtlSetOwnerSecurityDescriptor`
- `0x18000feab`: `RtlSetGroupSecurityDescriptor`
- `0x18000fed7`: `RtlSetDaclSecurityDescriptor`
- `0x18000ff05`: `RtlSetSaclSecurityDescriptor`
- `0x18000ff1c`: `FwppSecurityDescriptorSetInfo`

## pseudocode

```c
__int64 __fastcall FwppSecurityDescriptorSetInfo(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        char a2,
        void *a3,
        void *a4,
        PACL Dacl,
        PACL Sacl)
{
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax

  v10 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v10 >= 0 )
  {
    if ( (a2 & 1) != 0 && (v10 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0), v10 < 0) )
    {
      v12 = "RtlSetOwnerSecurityDescriptor";
    }
    else if ( (a2 & 2) != 0 && (v10 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0), v10 < 0) )
    {
      v12 = "RtlSetGroupSecurityDescriptor";
    }
    else if ( (a2 & 4) != 0 && (v10 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0), v10 < 0) )
    {
      v12 = "RtlSetDaclSecurityDescriptor";
    }
    else
    {
      v13 = 0;
      if ( (a2 & 8) == 0 )
        return v13;
      v10 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0);
      if ( v10 >= 0 )
        return v13;
      v12 = "RtlSetSaclSecurityDescriptor";
    }
  }
  else
  {
    v12 = "RtlCreateSecurityDescriptor";
  }
  v14 = WfpReportSysErrorAsNtStatus(v11, (int)v12, v10);
  v13 = v14;
  if ( v14 )
    WfpReportError(v14, (int)"FwppSecurityDescriptorSetInfo");
  return v13;
}

```

## disassembly

```asm
0x18000fe2c  push    rbx
0x18000fe2e  push    rbp
0x18000fe2f  push    rsi
0x18000fe30  push    rdi
0x18000fe31  sub     rsp, 28h
0x18000fe35  mov     edi, edx
0x18000fe37  mov     rbp, r9
0x18000fe3a  mov     edx, 1; Revision
0x18000fe3f  mov     rbx, r8
0x18000fe42  mov     rsi, rcx
0x18000fe45  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000fe4c  nop     dword ptr [rax+rax+00h]
0x18000fe51  test    eax, eax
0x18000fe53  jns     short loc_18000FE61
0x18000fe55  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x18000fe5c  jmp     loc_18000FF0C
0x18000fe61  test    dil, 1
0x18000fe65  jz      short loc_18000FE8C
0x18000fe67  xor     r8d, r8d; OwnerDefaulted
0x18000fe6a  mov     rdx, rbx; Owner
0x18000fe6d  mov     rcx, rsi; SecurityDescriptor
0x18000fe70  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000fe77  nop     dword ptr [rax+rax+00h]
0x18000fe7c  test    eax, eax
0x18000fe7e  jns     short loc_18000FE8C
0x18000fe80  lea     rdx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor"
0x18000fe87  jmp     loc_18000FF0C
0x18000fe8c  test    dil, 2
0x18000fe90  jz      short loc_18000FEB4
0x18000fe92  xor     r8d, r8d; GroupDefaulted
0x18000fe95  mov     rdx, rbp; Group
0x18000fe98  mov     rcx, rsi; SecurityDescriptor
0x18000fe9b  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18000fea2  nop     dword ptr [rax+rax+00h]
0x18000fea7  test    eax, eax
0x18000fea9  jns     short loc_18000FEB4
0x18000feab  lea     rdx, aRtlsetgroupsec; "RtlSetGroupSecurityDescriptor"
0x18000feb2  jmp     short loc_18000FF0C
0x18000feb4  test    dil, 4
0x18000feb8  jz      short loc_18000FEE0
0x18000feba  mov     r8, [rsp+48h+Dacl]; Dacl
0x18000febf  xor     r9d, r9d; DaclDefaulted
0x18000fec2  mov     dl, 1; DaclPresent
0x18000fec4  mov     rcx, rsi; SecurityDescriptor
0x18000fec7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000fece  nop     dword ptr [rax+rax+00h]
0x18000fed3  test    eax, eax
0x18000fed5  jns     short loc_18000FEE0
0x18000fed7  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x18000fede  jmp     short loc_18000FF0C
0x18000fee0  xor     ebx, ebx
0x18000fee2  test    dil, 8
0x18000fee6  jz      short loc_18000FF2B
0x18000fee8  mov     r8, [rsp+48h+Sacl]; Sacl
0x18000feed  xor     r9d, r9d; SaclDefaulted
0x18000fef0  mov     dl, 1; SaclPresent
0x18000fef2  mov     rcx, rsi; SecurityDescriptor
0x18000fef5  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18000fefc  nop     dword ptr [rax+rax+00h]
0x18000ff01  test    eax, eax
0x18000ff03  jns     short loc_18000FF2B
0x18000ff05  lea     rdx, aRtlsetsaclsecu; "RtlSetSaclSecurityDescriptor"
0x18000ff0c  mov     r8d, eax
0x18000ff0f  call    WfpReportSysErrorAsNtStatus
0x18000ff14  mov     rbx, rax
0x18000ff17  test    rax, rax
0x18000ff1a  jz      short loc_18000FF2B
0x18000ff1c  lea     rdx, aFwppsecurityde_0; "FwppSecurityDescriptorSetInfo"
0x18000ff23  mov     rcx, rax
0x18000ff26  call    WfpReportError
0x18000ff2b  mov     rax, rbx
0x18000ff2e  add     rsp, 28h
0x18000ff32  pop     rdi
0x18000ff33  pop     rsi
0x18000ff34  pop     rbp
0x18000ff35  pop     rbx
0x18000ff36  retn
```
