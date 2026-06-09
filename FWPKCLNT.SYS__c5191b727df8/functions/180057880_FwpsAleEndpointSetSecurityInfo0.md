# FwpsAleEndpointSetSecurityInfo0

- ea: `0x180057880`
- end: `0x180057999`
- name: `FwpsAleEndpointSetSecurityInfo0`
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
- `0x1800105e0`
- `0x1800203c0`
- `0x180057880`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800578d3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800578d3`

## string_xrefs

- `0x1800578e9`: `FwpsAleEndpointSetSecurityInfo0`
- `0x18005795a`: `FwppProxyAleEndpointSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpsAleEndpointSetSecurityInfo0(
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
    v12 = WfpReportAppErrorAsNtStatus(v10, (__int64)"FwpsAleEndpointSetSecurityInfo0", v11);
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
      v14 = FwppProxyAleEndpointSetSecurityInfo(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              securityInfo,
              &v18);
      if ( v14 < 0 )
      {
        v12 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyAleEndpointSetSecurityInfo", v14);
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
0x180057880  push    rbp
0x180057882  push    rbx
0x180057883  push    rsi
0x180057884  push    rdi
0x180057885  push    r12
0x180057887  push    r14
0x180057889  push    r15
0x18005788b  mov     rbp, rsp
0x18005788e  sub     rsp, 80h
0x180057895  mov     rax, cs:__security_cookie
0x18005789c  xor     rax, rsp
0x18005789f  mov     [rbp+var_10], rax
0x1800578a3  mov     r15, [rbp+dacl]
0x1800578a7  xor     eax, eax
0x1800578a9  mov     r12, [rbp+sacl]
0x1800578ad  xorps   xmm0, xmm0
0x1800578b0  mov     [rbp+var_44], rax
0x1800578b4  mov     r14, r9
0x1800578b7  mov     [rbp-48h], rax
0x1800578bb  mov     rbx, r8
0x1800578be  mov     esi, edx
0x1800578c0  mov     [rbp+var_18], rax
0x1800578c4  mov     rdi, rcx
0x1800578c7  mov     [rbp+var_50], rax
0x1800578cb  movups  [rbp+SecurityDescriptor], xmm0
0x1800578cf  movups  [rbp+var_28], xmm0
0x1800578d3  call    cs:__imp_KeGetCurrentIrql
0x1800578da  nop     dword ptr [rax+rax+00h]
0x1800578df  test    al, al
0x1800578e1  jz      short loc_1800578F7
0x1800578e3  mov     r8d, 0C00000BBh
0x1800578e9  lea     rdx, aFwpsaleendpoin; "FwpsAleEndpointSetSecurityInfo0"
0x1800578f0  call    WfpReportAppErrorAsNtStatus
0x1800578f5  jmp     short loc_180057966
0x1800578f7  test    rdi, rdi
0x1800578fa  jnz     short loc_180057904
0x1800578fc  mov     r8d, 0C022001Ch
0x180057902  jmp     short loc_1800578E9
0x180057904  mov     [rsp+80h+Sacl], r12; Sacl
0x180057909  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005790d  mov     r9, r14
0x180057910  mov     [rsp+80h+Dacl], r15; Dacl
0x180057915  mov     r8, rbx
0x180057918  mov     edx, esi
0x18005791a  call    FwppSecurityDescriptorSetInfo
0x18005791f  mov     rbx, rax
0x180057922  test    rax, rax
0x180057925  jnz     short loc_180057969
0x180057927  lea     r8, [rbp+var_50]
0x18005792b  lea     rdx, [rbp+var_48]
0x18005792f  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180057933  call    BfeSecurityDescriptorEncode
0x180057938  mov     rbx, rax
0x18005793b  test    rax, rax
0x18005793e  jnz     short loc_180057969
0x180057940  mov     rdx, [rdi+8]
0x180057944  lea     r9, [rbp+var_48]
0x180057948  mov     rcx, [rdi]
0x18005794b  mov     r8d, esi
0x18005794e  call    FwppProxyAleEndpointSetSecurityInfo
0x180057953  test    eax, eax
0x180057955  jns     short loc_180057969
0x180057957  mov     r8d, eax
0x18005795a  lea     rdx, aFwppproxyaleen_0; "FwppProxyAleEndpointSetSecurityInfo"
0x180057961  call    WfpReportSysErrorAsNtStatus
0x180057966  mov     rbx, rax
0x180057969  lea     rcx, [rbp+var_50]
0x18005796d  call    BfeSecurityDescriptorStorageFree
0x180057972  mov     rcx, rbx
0x180057975  call    WfpErrorToFwpErr
0x18005797a  mov     rcx, [rbp+var_10]
0x18005797e  xor     rcx, rsp; StackCookie
0x180057981  call    __security_check_cookie
0x180057986  add     rsp, 80h
0x18005798d  pop     r15
0x18005798f  pop     r14
0x180057991  pop     r12
0x180057993  pop     rdi
0x180057994  pop     rsi
0x180057995  pop     rbx
0x180057996  pop     rbp
0x180057997  retn
```
