# FwpmFilterGetSecurityInfoByKey0

- ea: `0x180053ed0`
- end: `0x180053ff0`
- name: `FwpmFilterGetSecurityInfoByKey0`
- size: `288`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008440`
- `0x180008f10`
- `0x18000fccc`
- `0x180011124`
- `0x1800203c0`
- `0x180053ed0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180053f24`
- `ntoskrnl!KeGetCurrentIrql` at `0x180053f24`

## string_xrefs

- `0x180053f3a`: `FwpmFilterGetSecurityInfoByKey0`
- `0x180053f7d`: `FwppProxyFilterGetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmFilterGetSecurityInfoByKey0(
        HANDLE engineHandle,
        const GUID *key,
        SECURITY_INFORMATION securityInfo,
        PSID *sidOwner,
        PSID *sidGroup,
        PACL *dacl,
        PACL *sacl,
        PSECURITY_DESCRIPTOR *securityDescriptor)
{
  int v10; // r13d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  int SecurityInfoByKey; // eax
  __int64 v16; // rcx
  __int64 Info; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int)key;
  *(_OWORD *)SecurityDescriptor = 0;
  if ( KeGetCurrentIrql() )
  {
    v13 = 3221225659LL;
LABEL_3:
    v14 = WfpReportAppErrorAsNtStatus(v12, (__int64)"FwpmFilterGetSecurityInfoByKey0", v13);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v13 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfoByKey = FwppProxyFilterGetSecurityInfoByKey(
                        *(_QWORD *)engineHandle,
                        *((_QWORD *)engineHandle + 1),
                        v10,
                        securityInfo,
                        (__int64)SecurityDescriptor);
  if ( SecurityInfoByKey >= 0 )
  {
    Info = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], securityInfo, sidOwner, sidGroup, dacl, sacl);
    if ( !Info )
    {
      *securityDescriptor = SecurityDescriptor[1];
      return WfpErrorToFwpErr(Info);
    }
    goto LABEL_10;
  }
  v14 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyFilterGetSecurityInfoByKey", SecurityInfoByKey);
LABEL_9:
  Info = v14;
  if ( v14 )
LABEL_10:
    FwppDeepFree_GUID(SecurityDescriptor[1]);
  return WfpErrorToFwpErr(Info);
}

```

## disassembly

```asm
0x180053ed0  push    rbx
0x180053ed2  push    rbp
0x180053ed3  push    rsi
0x180053ed4  push    rdi
0x180053ed5  push    r12
0x180053ed7  push    r13
0x180053ed9  push    r14
0x180053edb  push    r15
0x180053edd  sub     rsp, 58h
0x180053ee1  mov     rax, cs:__security_cookie
0x180053ee8  xor     rax, rsp
0x180053eeb  mov     [rsp+98h+var_58], rax
0x180053ef0  mov     r14, [rsp+98h+sidGroup]
0x180053ef8  xorps   xmm0, xmm0
0x180053efb  mov     r15, [rsp+98h+dacl]
0x180053f03  mov     rbp, r9
0x180053f06  mov     r12, [rsp+98h+sacl]
0x180053f0e  mov     esi, r8d
0x180053f11  mov     rdi, [rsp+98h+securityDescriptor]
0x180053f19  mov     r13, rdx
0x180053f1c  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x180053f21  mov     rbx, rcx
0x180053f24  call    cs:__imp_KeGetCurrentIrql
0x180053f2b  nop     dword ptr [rax+rax+00h]
0x180053f30  test    al, al
0x180053f32  jz      short loc_180053F48
0x180053f34  mov     r8d, 0C00000BBh
0x180053f3a  lea     rdx, aFwpmfiltergets; "FwpmFilterGetSecurityInfoByKey0"
0x180053f41  call    WfpReportAppErrorAsNtStatus
0x180053f46  jmp     short loc_180053F89
0x180053f48  test    rbx, rbx
0x180053f4b  jnz     short loc_180053F55
0x180053f4d  mov     r8d, 0C022001Ch
0x180053f53  jmp     short loc_180053F3A
0x180053f55  test    rdi, rdi
0x180053f58  jz      short loc_180053F4D
0x180053f5a  mov     rdx, [rbx+8]
0x180053f5e  lea     rax, [rsp+98h+SecurityDescriptor]
0x180053f63  mov     rcx, [rbx]
0x180053f66  mov     r9d, esi
0x180053f69  mov     r8, r13
0x180053f6c  mov     [rsp+98h+Dacl], rax
0x180053f71  call    FwppProxyFilterGetSecurityInfoByKey
0x180053f76  test    eax, eax
0x180053f78  jns     short loc_180053FC2
0x180053f7a  mov     r8d, eax
0x180053f7d  lea     rdx, aFwppproxyfilte_0; "FwppProxyFilterGetSecurityInfoByKey"
0x180053f84  call    WfpReportSysErrorAsNtStatus
0x180053f89  mov     rbx, rax
0x180053f8c  test    rax, rax
0x180053f8f  jz      short loc_180053F9B
0x180053f91  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x180053f96  call    FwppDeepFree_GUID
0x180053f9b  mov     rcx, rbx
0x180053f9e  call    WfpErrorToFwpErr
0x180053fa3  mov     rcx, [rsp+98h+var_58]
0x180053fa8  xor     rcx, rsp; StackCookie
0x180053fab  call    __security_check_cookie
0x180053fb0  add     rsp, 58h
0x180053fb4  pop     r15
0x180053fb6  pop     r14
0x180053fb8  pop     r13
0x180053fba  pop     r12
0x180053fbc  pop     rdi
0x180053fbd  pop     rsi
0x180053fbe  pop     rbp
0x180053fbf  pop     rbx
0x180053fc0  retn
0x180053fc2  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x180053fc7  mov     r9, r14
0x180053fca  mov     [rsp+98h+Sacl], r12; Sacl
0x180053fcf  mov     r8, rbp
0x180053fd2  mov     edx, esi
0x180053fd4  mov     [rsp+98h+Dacl], r15; Dacl
0x180053fd9  call    FwppSecurityDescriptorGetInfo
0x180053fde  mov     rbx, rax
0x180053fe1  test    rax, rax
0x180053fe4  jnz     short loc_180053F91
0x180053fe6  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x180053feb  mov     [rdi], rax
0x180053fee  jmp     short loc_180053F9B
```
