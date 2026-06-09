# FwpmCalloutGetSecurityInfoByKey0

- ea: `0x180053530`
- end: `0x180053650`
- name: `FwpmCalloutGetSecurityInfoByKey0`
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
- `0x180010edc`
- `0x1800203c0`
- `0x180053530`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180053584`
- `ntoskrnl!KeGetCurrentIrql` at `0x180053584`

## string_xrefs

- `0x18005359a`: `FwpmCalloutGetSecurityInfoByKey0`
- `0x1800535dd`: `FwppProxyCalloutGetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmCalloutGetSecurityInfoByKey0(
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
    v14 = WfpReportAppErrorAsNtStatus(v12, (__int64)"FwpmCalloutGetSecurityInfoByKey0", v13);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v13 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfoByKey = FwppProxyCalloutGetSecurityInfoByKey(
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
  v14 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyCalloutGetSecurityInfoByKey", SecurityInfoByKey);
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
0x180053530  push    rbx
0x180053532  push    rbp
0x180053533  push    rsi
0x180053534  push    rdi
0x180053535  push    r12
0x180053537  push    r13
0x180053539  push    r14
0x18005353b  push    r15
0x18005353d  sub     rsp, 58h
0x180053541  mov     rax, cs:__security_cookie
0x180053548  xor     rax, rsp
0x18005354b  mov     [rsp+98h+var_58], rax
0x180053550  mov     r14, [rsp+98h+sidGroup]
0x180053558  xorps   xmm0, xmm0
0x18005355b  mov     r15, [rsp+98h+dacl]
0x180053563  mov     rbp, r9
0x180053566  mov     r12, [rsp+98h+sacl]
0x18005356e  mov     esi, r8d
0x180053571  mov     rdi, [rsp+98h+securityDescriptor]
0x180053579  mov     r13, rdx
0x18005357c  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x180053581  mov     rbx, rcx
0x180053584  call    cs:__imp_KeGetCurrentIrql
0x18005358b  nop     dword ptr [rax+rax+00h]
0x180053590  test    al, al
0x180053592  jz      short loc_1800535A8
0x180053594  mov     r8d, 0C00000BBh
0x18005359a  lea     rdx, aFwpmcalloutget; "FwpmCalloutGetSecurityInfoByKey0"
0x1800535a1  call    WfpReportAppErrorAsNtStatus
0x1800535a6  jmp     short loc_1800535E9
0x1800535a8  test    rbx, rbx
0x1800535ab  jnz     short loc_1800535B5
0x1800535ad  mov     r8d, 0C022001Ch
0x1800535b3  jmp     short loc_18005359A
0x1800535b5  test    rdi, rdi
0x1800535b8  jz      short loc_1800535AD
0x1800535ba  mov     rdx, [rbx+8]
0x1800535be  lea     rax, [rsp+98h+SecurityDescriptor]
0x1800535c3  mov     rcx, [rbx]
0x1800535c6  mov     r9d, esi
0x1800535c9  mov     r8, r13
0x1800535cc  mov     [rsp+98h+Dacl], rax
0x1800535d1  call    FwppProxyCalloutGetSecurityInfoByKey
0x1800535d6  test    eax, eax
0x1800535d8  jns     short loc_180053622
0x1800535da  mov     r8d, eax
0x1800535dd  lea     rdx, aFwppproxycallo_2; "FwppProxyCalloutGetSecurityInfoByKey"
0x1800535e4  call    WfpReportSysErrorAsNtStatus
0x1800535e9  mov     rbx, rax
0x1800535ec  test    rax, rax
0x1800535ef  jz      short loc_1800535FB
0x1800535f1  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x1800535f6  call    FwppDeepFree_GUID
0x1800535fb  mov     rcx, rbx
0x1800535fe  call    WfpErrorToFwpErr
0x180053603  mov     rcx, [rsp+98h+var_58]
0x180053608  xor     rcx, rsp; StackCookie
0x18005360b  call    __security_check_cookie
0x180053610  add     rsp, 58h
0x180053614  pop     r15
0x180053616  pop     r14
0x180053618  pop     r13
0x18005361a  pop     r12
0x18005361c  pop     rdi
0x18005361d  pop     rsi
0x18005361e  pop     rbp
0x18005361f  pop     rbx
0x180053620  retn
0x180053622  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x180053627  mov     r9, r14
0x18005362a  mov     [rsp+98h+Sacl], r12; Sacl
0x18005362f  mov     r8, rbp
0x180053632  mov     edx, esi
0x180053634  mov     [rsp+98h+Dacl], r15; Dacl
0x180053639  call    FwppSecurityDescriptorGetInfo
0x18005363e  mov     rbx, rax
0x180053641  test    rax, rax
0x180053644  jnz     short loc_1800535F1
0x180053646  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x18005364b  mov     [rdi], rax
0x18005364e  jmp     short loc_1800535FB
```
