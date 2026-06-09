# IPsecDospSetSecurityInfo0

- ea: `0x180057c30`
- end: `0x180057d49`
- name: `IPsecDospSetSecurityInfo0`
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
- `0x180010778`
- `0x1800203c0`
- `0x180057c30`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180057c83`
- `ntoskrnl!KeGetCurrentIrql` at `0x180057c83`

## string_xrefs

- `0x180057c99`: `IPsecDospSetSecurityInfo0`
- `0x180057d0a`: `FwppProxyBfeIPsecDospSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IPsecDospSetSecurityInfo0(
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
    v12 = WfpReportAppErrorAsNtStatus(v10, (__int64)"IPsecDospSetSecurityInfo0", v11);
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
      v14 = FwppProxyBfeIPsecDospSetSecurityInfo(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              securityInfo,
              &v18);
      if ( v14 < 0 )
      {
        v12 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyBfeIPsecDospSetSecurityInfo", v14);
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
0x180057c30  push    rbp
0x180057c32  push    rbx
0x180057c33  push    rsi
0x180057c34  push    rdi
0x180057c35  push    r12
0x180057c37  push    r14
0x180057c39  push    r15
0x180057c3b  mov     rbp, rsp
0x180057c3e  sub     rsp, 80h
0x180057c45  mov     rax, cs:__security_cookie
0x180057c4c  xor     rax, rsp
0x180057c4f  mov     [rbp+var_10], rax
0x180057c53  mov     r15, [rbp+dacl]
0x180057c57  xor     eax, eax
0x180057c59  mov     r12, [rbp+sacl]
0x180057c5d  xorps   xmm0, xmm0
0x180057c60  mov     [rbp+var_44], rax
0x180057c64  mov     r14, r9
0x180057c67  mov     [rbp-48h], rax
0x180057c6b  mov     rbx, r8
0x180057c6e  mov     esi, edx
0x180057c70  mov     [rbp+var_18], rax
0x180057c74  mov     rdi, rcx
0x180057c77  mov     [rbp+var_50], rax
0x180057c7b  movups  [rbp+SecurityDescriptor], xmm0
0x180057c7f  movups  [rbp+var_28], xmm0
0x180057c83  call    cs:__imp_KeGetCurrentIrql
0x180057c8a  nop     dword ptr [rax+rax+00h]
0x180057c8f  test    al, al
0x180057c91  jz      short loc_180057CA7
0x180057c93  mov     r8d, 0C00000BBh
0x180057c99  lea     rdx, aIpsecdospsetse; "IPsecDospSetSecurityInfo0"
0x180057ca0  call    WfpReportAppErrorAsNtStatus
0x180057ca5  jmp     short loc_180057D16
0x180057ca7  test    rdi, rdi
0x180057caa  jnz     short loc_180057CB4
0x180057cac  mov     r8d, 0C022001Ch
0x180057cb2  jmp     short loc_180057C99
0x180057cb4  mov     [rsp+80h+Sacl], r12; Sacl
0x180057cb9  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180057cbd  mov     r9, r14
0x180057cc0  mov     [rsp+80h+Dacl], r15; Dacl
0x180057cc5  mov     r8, rbx
0x180057cc8  mov     edx, esi
0x180057cca  call    FwppSecurityDescriptorSetInfo
0x180057ccf  mov     rbx, rax
0x180057cd2  test    rax, rax
0x180057cd5  jnz     short loc_180057D19
0x180057cd7  lea     r8, [rbp+var_50]
0x180057cdb  lea     rdx, [rbp+var_48]
0x180057cdf  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180057ce3  call    BfeSecurityDescriptorEncode
0x180057ce8  mov     rbx, rax
0x180057ceb  test    rax, rax
0x180057cee  jnz     short loc_180057D19
0x180057cf0  mov     rdx, [rdi+8]
0x180057cf4  lea     r9, [rbp+var_48]
0x180057cf8  mov     rcx, [rdi]
0x180057cfb  mov     r8d, esi
0x180057cfe  call    FwppProxyBfeIPsecDospSetSecurityInfo
0x180057d03  test    eax, eax
0x180057d05  jns     short loc_180057D19
0x180057d07  mov     r8d, eax
0x180057d0a  lea     rdx, aFwppproxybfeip; "FwppProxyBfeIPsecDospSetSecurityInfo"
0x180057d11  call    WfpReportSysErrorAsNtStatus
0x180057d16  mov     rbx, rax
0x180057d19  lea     rcx, [rbp+var_50]
0x180057d1d  call    BfeSecurityDescriptorStorageFree
0x180057d22  mov     rcx, rbx
0x180057d25  call    WfpErrorToFwpErr
0x180057d2a  mov     rcx, [rbp+var_10]
0x180057d2e  xor     rcx, rsp; StackCookie
0x180057d31  call    __security_check_cookie
0x180057d36  add     rsp, 80h
0x180057d3d  pop     r15
0x180057d3f  pop     r14
0x180057d41  pop     r12
0x180057d43  pop     rdi
0x180057d44  pop     rsi
0x180057d45  pop     rbx
0x180057d46  pop     rbp
0x180057d47  retn
```
