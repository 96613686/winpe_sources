# IPsecSaDbSetSecurityInfo0

- ea: `0x180058ee0`
- end: `0x180058ff9`
- name: `IPsecSaDbSetSecurityInfo0`
- size: `281`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x1800083f8`
- `0x1800086fc`
- `0x180008f10`
- `0x18000fe2c`
- `0x180010cd4`
- `0x1800203c0`
- `0x180058ee0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180058f33`
- `ntoskrnl!KeGetCurrentIrql` at `0x180058f33`

## string_xrefs

- `0x180058f49`: `IPsecSaDbSetSecurityInfo0`
- `0x180058fba`: `FwppProxyBfeIPsecSaDbSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IPsecSaDbSetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        const SID *sidOwner,
        const SID *sidGroup,
        const ACL *dacl,
        const ACL *sacl)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rcx
  PVOID v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  int v19; // [rsp+40h] [rbp-40h]
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h]

  v19 = 0;
  v18 = 0;
  v21 = 0;
  v17 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( KeGetCurrentIrql() )
  {
    v11 = 3221225659LL;
LABEL_3:
    v12 = WfpReportAppErrorAsNtStatus(v10, (__int64)"IPsecSaDbSetSecurityInfo0", v11);
LABEL_10:
    v13 = v12;
    goto LABEL_11;
  }
  if ( !engineHandle )
  {
    v11 = 3223453724LL;
    goto LABEL_3;
  }
  v13 = FwppSecurityDescriptorSetInfo(
          SecurityDescriptor,
          securityInfo,
          (void *)sidOwner,
          (void *)sidGroup,
          (PACL)dacl,
          (PACL)sacl);
  if ( !v13 )
  {
    v13 = BfeSecurityDescriptorEncode(SecurityDescriptor, (__int64)&v18, &v17);
    if ( !v13 )
    {
      v14 = FwppProxyBfeIPsecSaDbSetSecurityInfo(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              securityInfo,
              &v18);
      if ( v14 < 0 )
      {
        v12 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyBfeIPsecSaDbSetSecurityInfo", v14);
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  BfeSecurityDescriptorStorageFree(&v17);
  return WfpErrorToFwpErr(v13);
}

```

## disassembly

```asm
0x180058ee0  push    rbp
0x180058ee2  push    rbx
0x180058ee3  push    rsi
0x180058ee4  push    rdi
0x180058ee5  push    r12
0x180058ee7  push    r14
0x180058ee9  push    r15
0x180058eeb  mov     rbp, rsp
0x180058eee  sub     rsp, 80h
0x180058ef5  mov     rax, cs:__security_cookie
0x180058efc  xor     rax, rsp
0x180058eff  mov     [rbp+var_10], rax
0x180058f03  mov     r15, [rbp+dacl]
0x180058f07  xor     eax, eax
0x180058f09  mov     r12, [rbp+sacl]
0x180058f0d  xorps   xmm0, xmm0
0x180058f10  mov     [rbp+var_44], rax
0x180058f14  mov     r14, r9
0x180058f17  mov     [rbp-48h], rax
0x180058f1b  mov     rbx, r8
0x180058f1e  mov     esi, edx
0x180058f20  mov     [rbp+var_18], rax
0x180058f24  mov     rdi, rcx
0x180058f27  mov     [rbp+var_50], rax
0x180058f2b  movups  [rbp+SecurityDescriptor], xmm0
0x180058f2f  movups  [rbp+var_28], xmm0
0x180058f33  call    cs:__imp_KeGetCurrentIrql
0x180058f3a  nop     dword ptr [rax+rax+00h]
0x180058f3f  test    al, al
0x180058f41  jz      short loc_180058F57
0x180058f43  mov     r8d, 0C00000BBh
0x180058f49  lea     rdx, aIpsecsadbsetse; "IPsecSaDbSetSecurityInfo0"
0x180058f50  call    WfpReportAppErrorAsNtStatus
0x180058f55  jmp     short loc_180058FC6
0x180058f57  test    rdi, rdi
0x180058f5a  jnz     short loc_180058F64
0x180058f5c  mov     r8d, 0C022001Ch
0x180058f62  jmp     short loc_180058F49
0x180058f64  mov     [rsp+80h+Sacl], r12; Sacl
0x180058f69  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180058f6d  mov     r9, r14
0x180058f70  mov     [rsp+80h+Dacl], r15; Dacl
0x180058f75  mov     r8, rbx
0x180058f78  mov     edx, esi
0x180058f7a  call    FwppSecurityDescriptorSetInfo
0x180058f7f  mov     rbx, rax
0x180058f82  test    rax, rax
0x180058f85  jnz     short loc_180058FC9
0x180058f87  lea     r8, [rbp+var_50]
0x180058f8b  lea     rdx, [rbp+var_48]
0x180058f8f  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180058f93  call    BfeSecurityDescriptorEncode
0x180058f98  mov     rbx, rax
0x180058f9b  test    rax, rax
0x180058f9e  jnz     short loc_180058FC9
0x180058fa0  mov     rdx, [rdi+8]
0x180058fa4  lea     r9, [rbp+var_48]
0x180058fa8  mov     rcx, [rdi]
0x180058fab  mov     r8d, esi
0x180058fae  call    FwppProxyBfeIPsecSaDbSetSecurityInfo
0x180058fb3  test    eax, eax
0x180058fb5  jns     short loc_180058FC9
0x180058fb7  mov     r8d, eax
0x180058fba  lea     rdx, aFwppproxybfeip_3; "FwppProxyBfeIPsecSaDbSetSecurityInfo"
0x180058fc1  call    WfpReportSysErrorAsNtStatus
0x180058fc6  mov     rbx, rax
0x180058fc9  lea     rcx, [rbp+var_50]
0x180058fcd  call    BfeSecurityDescriptorStorageFree
0x180058fd2  mov     rcx, rbx
0x180058fd5  call    WfpErrorToFwpErr
0x180058fda  mov     rcx, [rbp+var_10]
0x180058fde  xor     rcx, rsp; StackCookie
0x180058fe1  call    __security_check_cookie
0x180058fe6  add     rsp, 80h
0x180058fed  pop     r15
0x180058fef  pop     r14
0x180058ff1  pop     r12
0x180058ff3  pop     rdi
0x180058ff4  pop     rsi
0x180058ff5  pop     rbx
0x180058ff6  pop     rbp
0x180058ff7  retn
```
