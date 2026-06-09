# FwpmSubLayerGetSecurityInfoByKey0

- ea: `0x180056f20`
- end: `0x180057040`
- name: `FwpmSubLayerGetSecurityInfoByKey0`
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
- `0x1800119ac`
- `0x1800203c0`
- `0x180056f20`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180056f74`
- `ntoskrnl!KeGetCurrentIrql` at `0x180056f74`

## string_xrefs

- `0x180056f8a`: `FwpmSubLayerGetSecurityInfoByKey0`
- `0x180056fcd`: `FwppProxySubLayerGetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmSubLayerGetSecurityInfoByKey0(
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
    v14 = WfpReportAppErrorAsNtStatus(v12, (__int64)"FwpmSubLayerGetSecurityInfoByKey0", v13);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v13 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfoByKey = FwppProxySubLayerGetSecurityInfoByKey(
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
  v14 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxySubLayerGetSecurityInfoByKey", SecurityInfoByKey);
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
0x180056f20  push    rbx
0x180056f22  push    rbp
0x180056f23  push    rsi
0x180056f24  push    rdi
0x180056f25  push    r12
0x180056f27  push    r13
0x180056f29  push    r14
0x180056f2b  push    r15
0x180056f2d  sub     rsp, 58h
0x180056f31  mov     rax, cs:__security_cookie
0x180056f38  xor     rax, rsp
0x180056f3b  mov     [rsp+98h+var_58], rax
0x180056f40  mov     r14, [rsp+98h+sidGroup]
0x180056f48  xorps   xmm0, xmm0
0x180056f4b  mov     r15, [rsp+98h+dacl]
0x180056f53  mov     rbp, r9
0x180056f56  mov     r12, [rsp+98h+sacl]
0x180056f5e  mov     esi, r8d
0x180056f61  mov     rdi, [rsp+98h+securityDescriptor]
0x180056f69  mov     r13, rdx
0x180056f6c  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x180056f71  mov     rbx, rcx
0x180056f74  call    cs:__imp_KeGetCurrentIrql
0x180056f7b  nop     dword ptr [rax+rax+00h]
0x180056f80  test    al, al
0x180056f82  jz      short loc_180056F98
0x180056f84  mov     r8d, 0C00000BBh
0x180056f8a  lea     rdx, aFwpmsublayerge_0; "FwpmSubLayerGetSecurityInfoByKey0"
0x180056f91  call    WfpReportAppErrorAsNtStatus
0x180056f96  jmp     short loc_180056FD9
0x180056f98  test    rbx, rbx
0x180056f9b  jnz     short loc_180056FA5
0x180056f9d  mov     r8d, 0C022001Ch
0x180056fa3  jmp     short loc_180056F8A
0x180056fa5  test    rdi, rdi
0x180056fa8  jz      short loc_180056F9D
0x180056faa  mov     rdx, [rbx+8]
0x180056fae  lea     rax, [rsp+98h+SecurityDescriptor]
0x180056fb3  mov     rcx, [rbx]
0x180056fb6  mov     r9d, esi
0x180056fb9  mov     r8, r13
0x180056fbc  mov     [rsp+98h+Dacl], rax
0x180056fc1  call    FwppProxySubLayerGetSecurityInfoByKey
0x180056fc6  test    eax, eax
0x180056fc8  jns     short loc_180057012
0x180056fca  mov     r8d, eax
0x180056fcd  lea     rdx, aFwppproxysubla_0; "FwppProxySubLayerGetSecurityInfoByKey"
0x180056fd4  call    WfpReportSysErrorAsNtStatus
0x180056fd9  mov     rbx, rax
0x180056fdc  test    rax, rax
0x180056fdf  jz      short loc_180056FEB
0x180056fe1  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x180056fe6  call    FwppDeepFree_GUID
0x180056feb  mov     rcx, rbx
0x180056fee  call    WfpErrorToFwpErr
0x180056ff3  mov     rcx, [rsp+98h+var_58]
0x180056ff8  xor     rcx, rsp; StackCookie
0x180056ffb  call    __security_check_cookie
0x180057000  add     rsp, 58h
0x180057004  pop     r15
0x180057006  pop     r14
0x180057008  pop     r13
0x18005700a  pop     r12
0x18005700c  pop     rdi
0x18005700d  pop     rsi
0x18005700e  pop     rbp
0x18005700f  pop     rbx
0x180057010  retn
0x180057012  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x180057017  mov     r9, r14
0x18005701a  mov     [rsp+98h+Sacl], r12; Sacl
0x18005701f  mov     r8, rbp
0x180057022  mov     edx, esi
0x180057024  mov     [rsp+98h+Dacl], r15; Dacl
0x180057029  call    FwppSecurityDescriptorGetInfo
0x18005702e  mov     rbx, rax
0x180057031  test    rax, rax
0x180057034  jnz     short loc_180056FE1
0x180057036  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x18005703b  mov     [rdi], rax
0x18005703e  jmp     short loc_180056FEB
```
