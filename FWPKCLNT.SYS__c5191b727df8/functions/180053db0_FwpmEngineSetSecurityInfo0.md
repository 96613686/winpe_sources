# FwpmEngineSetSecurityInfo0

- ea: `0x180053db0`
- end: `0x180053ec9`
- name: `FwpmEngineSetSecurityInfo0`
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
- `0x1800110e8`
- `0x1800203c0`
- `0x180053db0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180053e03`
- `ntoskrnl!KeGetCurrentIrql` at `0x180053e03`

## string_xrefs

- `0x180053e19`: `FwpmEngineSetSecurityInfo0`
- `0x180053e8a`: `FwppProxyEngineSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpmEngineSetSecurityInfo0(
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
    v12 = WfpReportAppErrorAsNtStatus(v10, (__int64)"FwpmEngineSetSecurityInfo0", v11);
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
      v14 = FwppProxyEngineSetSecurityInfo(*(_QWORD *)engineHandle, *((_QWORD *)engineHandle + 1), securityInfo, &v18);
      if ( v14 < 0 )
      {
        v12 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyEngineSetSecurityInfo", v14);
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
0x180053db0  push    rbp
0x180053db2  push    rbx
0x180053db3  push    rsi
0x180053db4  push    rdi
0x180053db5  push    r12
0x180053db7  push    r14
0x180053db9  push    r15
0x180053dbb  mov     rbp, rsp
0x180053dbe  sub     rsp, 80h
0x180053dc5  mov     rax, cs:__security_cookie
0x180053dcc  xor     rax, rsp
0x180053dcf  mov     [rbp+var_10], rax
0x180053dd3  mov     r15, [rbp+dacl]
0x180053dd7  xor     eax, eax
0x180053dd9  mov     r12, [rbp+sacl]
0x180053ddd  xorps   xmm0, xmm0
0x180053de0  mov     [rbp+var_44], rax
0x180053de4  mov     r14, r9
0x180053de7  mov     [rbp-48h], rax
0x180053deb  mov     rbx, r8
0x180053dee  mov     esi, edx
0x180053df0  mov     [rbp+var_18], rax
0x180053df4  mov     rdi, rcx
0x180053df7  mov     [rbp+var_50], rax
0x180053dfb  movups  [rbp+SecurityDescriptor], xmm0
0x180053dff  movups  [rbp+var_28], xmm0
0x180053e03  call    cs:__imp_KeGetCurrentIrql
0x180053e0a  nop     dword ptr [rax+rax+00h]
0x180053e0f  test    al, al
0x180053e11  jz      short loc_180053E27
0x180053e13  mov     r8d, 0C00000BBh
0x180053e19  lea     rdx, aFwpmenginesets; "FwpmEngineSetSecurityInfo0"
0x180053e20  call    WfpReportAppErrorAsNtStatus
0x180053e25  jmp     short loc_180053E96
0x180053e27  test    rdi, rdi
0x180053e2a  jnz     short loc_180053E34
0x180053e2c  mov     r8d, 0C022001Ch
0x180053e32  jmp     short loc_180053E19
0x180053e34  mov     [rsp+80h+Sacl], r12; Sacl
0x180053e39  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180053e3d  mov     r9, r14
0x180053e40  mov     [rsp+80h+Dacl], r15; Dacl
0x180053e45  mov     r8, rbx
0x180053e48  mov     edx, esi
0x180053e4a  call    FwppSecurityDescriptorSetInfo
0x180053e4f  mov     rbx, rax
0x180053e52  test    rax, rax
0x180053e55  jnz     short loc_180053E99
0x180053e57  lea     r8, [rbp+var_50]
0x180053e5b  lea     rdx, [rbp+var_48]
0x180053e5f  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180053e63  call    BfeSecurityDescriptorEncode
0x180053e68  mov     rbx, rax
0x180053e6b  test    rax, rax
0x180053e6e  jnz     short loc_180053E99
0x180053e70  mov     rdx, [rdi+8]
0x180053e74  lea     r9, [rbp+var_48]
0x180053e78  mov     rcx, [rdi]
0x180053e7b  mov     r8d, esi
0x180053e7e  call    FwppProxyEngineSetSecurityInfo
0x180053e83  test    eax, eax
0x180053e85  jns     short loc_180053E99
0x180053e87  mov     r8d, eax
0x180053e8a  lea     rdx, aFwppproxyengin; "FwppProxyEngineSetSecurityInfo"
0x180053e91  call    WfpReportSysErrorAsNtStatus
0x180053e96  mov     rbx, rax
0x180053e99  lea     rcx, [rbp+var_50]
0x180053e9d  call    BfeSecurityDescriptorStorageFree
0x180053ea2  mov     rcx, rbx
0x180053ea5  call    WfpErrorToFwpErr
0x180053eaa  mov     rcx, [rbp+var_10]
0x180053eae  xor     rcx, rsp; StackCookie
0x180053eb1  call    __security_check_cookie
0x180053eb6  add     rsp, 80h
0x180053ebd  pop     r15
0x180053ebf  pop     r14
0x180053ec1  pop     r12
0x180053ec3  pop     rdi
0x180053ec4  pop     rsi
0x180053ec5  pop     rbx
0x180053ec6  pop     rbp
0x180053ec7  retn
```
