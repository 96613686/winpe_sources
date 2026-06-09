# FwpmEngineGetSecurityInfo0

- ea: `0x180053c00`
- end: `0x180053d0b`
- name: `FwpmEngineGetSecurityInfo0`
- size: `267`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008440`
- `0x180008f10`
- `0x18000fccc`
- `0x180011070`
- `0x1800203c0`
- `0x180053c00`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180053c49`
- `ntoskrnl!KeGetCurrentIrql` at `0x180053c49`

## string_xrefs

- `0x180053c5f`: `FwpmEngineGetSecurityInfo0`
- `0x180053c9a`: `FwppProxyEngineGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpmEngineGetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        PSID *sidOwner,
        PSID *sidGroup,
        PACL *dacl,
        PACL *sacl,
        PSECURITY_DESCRIPTOR *securityDescriptor)
{
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  __int64 Info; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+30h] [rbp-58h] BYREF

  *(_OWORD *)SecurityDescriptor = 0;
  if ( KeGetCurrentIrql() )
  {
    v12 = 3221225659LL;
LABEL_3:
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmEngineGetSecurityInfo0", v12);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = FwppProxyEngineGetSecurityInfo(
          *(_QWORD *)engineHandle,
          *((_QWORD *)engineHandle + 1),
          securityInfo,
          SecurityDescriptor);
  if ( v14 >= 0 )
  {
    Info = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], securityInfo, sidOwner, sidGroup, dacl, sacl);
    if ( !Info )
    {
      *securityDescriptor = SecurityDescriptor[1];
      return WfpErrorToFwpErr(Info);
    }
    goto LABEL_10;
  }
  v13 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyEngineGetSecurityInfo", v14);
LABEL_9:
  Info = v13;
  if ( v13 )
LABEL_10:
    FwppDeepFree_GUID(SecurityDescriptor[1]);
  return WfpErrorToFwpErr(Info);
}

```

## disassembly

```asm
0x180053c00  push    rbx
0x180053c02  push    rbp
0x180053c03  push    rsi
0x180053c04  push    rdi
0x180053c05  push    r12
0x180053c07  push    r14
0x180053c09  push    r15
0x180053c0b  sub     rsp, 50h
0x180053c0f  mov     rax, cs:__security_cookie
0x180053c16  xor     rax, rsp
0x180053c19  mov     [rsp+88h+var_48], rax
0x180053c1e  mov     r15, [rsp+88h+dacl]
0x180053c26  xorps   xmm0, xmm0
0x180053c29  mov     r12, [rsp+88h+sacl]
0x180053c31  mov     r14, r9
0x180053c34  mov     rdi, [rsp+88h+securityDescriptor]
0x180053c3c  mov     rbp, r8
0x180053c3f  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x180053c44  mov     esi, edx
0x180053c46  mov     rbx, rcx
0x180053c49  call    cs:__imp_KeGetCurrentIrql
0x180053c50  nop     dword ptr [rax+rax+00h]
0x180053c55  test    al, al
0x180053c57  jz      short loc_180053C6D
0x180053c59  mov     r8d, 0C00000BBh
0x180053c5f  lea     rdx, aFwpmenginegets; "FwpmEngineGetSecurityInfo0"
0x180053c66  call    WfpReportAppErrorAsNtStatus
0x180053c6b  jmp     short loc_180053CA6
0x180053c6d  test    rbx, rbx
0x180053c70  jnz     short loc_180053C7A
0x180053c72  mov     r8d, 0C022001Ch
0x180053c78  jmp     short loc_180053C5F
0x180053c7a  test    rdi, rdi
0x180053c7d  jz      short loc_180053C72
0x180053c7f  mov     rdx, [rbx+8]
0x180053c83  lea     r9, [rsp+88h+SecurityDescriptor]
0x180053c88  mov     rcx, [rbx]
0x180053c8b  mov     r8d, esi
0x180053c8e  call    FwppProxyEngineGetSecurityInfo
0x180053c93  test    eax, eax
0x180053c95  jns     short loc_180053CDD
0x180053c97  mov     r8d, eax
0x180053c9a  lea     rdx, aFwppproxyengin_2; "FwppProxyEngineGetSecurityInfo"
0x180053ca1  call    WfpReportSysErrorAsNtStatus
0x180053ca6  mov     rbx, rax
0x180053ca9  test    rax, rax
0x180053cac  jz      short loc_180053CB8
0x180053cae  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x180053cb3  call    FwppDeepFree_GUID
0x180053cb8  mov     rcx, rbx
0x180053cbb  call    WfpErrorToFwpErr
0x180053cc0  mov     rcx, [rsp+88h+var_48]
0x180053cc5  xor     rcx, rsp; StackCookie
0x180053cc8  call    __security_check_cookie
0x180053ccd  add     rsp, 50h
0x180053cd1  pop     r15
0x180053cd3  pop     r14
0x180053cd5  pop     r12
0x180053cd7  pop     rdi
0x180053cd8  pop     rsi
0x180053cd9  pop     rbp
0x180053cda  pop     rbx
0x180053cdb  retn
0x180053cdd  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x180053ce2  mov     r9, r14
0x180053ce5  mov     [rsp+88h+Sacl], r12; Sacl
0x180053cea  mov     r8, rbp
0x180053ced  mov     edx, esi
0x180053cef  mov     [rsp+88h+Dacl], r15; Dacl
0x180053cf4  call    FwppSecurityDescriptorGetInfo
0x180053cf9  mov     rbx, rax
0x180053cfc  test    rax, rax
0x180053cff  jnz     short loc_180053CAE
0x180053d01  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x180053d06  mov     [rdi], rax
0x180053d09  jmp     short loc_180053CB8
```
