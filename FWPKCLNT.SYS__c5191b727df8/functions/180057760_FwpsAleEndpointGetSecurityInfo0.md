# FwpsAleEndpointGetSecurityInfo0

- ea: `0x180057760`
- end: `0x18005786b`
- name: `FwpsAleEndpointGetSecurityInfo0`
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
- `0x1800105a0`
- `0x1800203c0`
- `0x180057760`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800577a9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800577a9`

## string_xrefs

- `0x1800577bf`: `FwpsAleEndpointGetSecurityInfo0`
- `0x1800577fa`: `FwppProxyAleEndpointGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpsAleEndpointGetSecurityInfo0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpsAleEndpointGetSecurityInfo0", v12);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = FwppProxyAleEndpointGetSecurityInfo(
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
  v13 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyAleEndpointGetSecurityInfo", v14);
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
0x180057760  push    rbx
0x180057762  push    rbp
0x180057763  push    rsi
0x180057764  push    rdi
0x180057765  push    r12
0x180057767  push    r14
0x180057769  push    r15
0x18005776b  sub     rsp, 50h
0x18005776f  mov     rax, cs:__security_cookie
0x180057776  xor     rax, rsp
0x180057779  mov     [rsp+88h+var_48], rax
0x18005777e  mov     r15, [rsp+88h+dacl]
0x180057786  xorps   xmm0, xmm0
0x180057789  mov     r12, [rsp+88h+sacl]
0x180057791  mov     r14, r9
0x180057794  mov     rdi, [rsp+88h+securityDescriptor]
0x18005779c  mov     rbp, r8
0x18005779f  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x1800577a4  mov     esi, edx
0x1800577a6  mov     rbx, rcx
0x1800577a9  call    cs:__imp_KeGetCurrentIrql
0x1800577b0  nop     dword ptr [rax+rax+00h]
0x1800577b5  test    al, al
0x1800577b7  jz      short loc_1800577CD
0x1800577b9  mov     r8d, 0C00000BBh
0x1800577bf  lea     rdx, aFwpsaleendpoin_2; "FwpsAleEndpointGetSecurityInfo0"
0x1800577c6  call    WfpReportAppErrorAsNtStatus
0x1800577cb  jmp     short loc_180057806
0x1800577cd  test    rbx, rbx
0x1800577d0  jnz     short loc_1800577DA
0x1800577d2  mov     r8d, 0C022001Ch
0x1800577d8  jmp     short loc_1800577BF
0x1800577da  test    rdi, rdi
0x1800577dd  jz      short loc_1800577D2
0x1800577df  mov     rdx, [rbx+8]
0x1800577e3  lea     r9, [rsp+88h+SecurityDescriptor]
0x1800577e8  mov     rcx, [rbx]
0x1800577eb  mov     r8d, esi
0x1800577ee  call    FwppProxyAleEndpointGetSecurityInfo
0x1800577f3  test    eax, eax
0x1800577f5  jns     short loc_18005783D
0x1800577f7  mov     r8d, eax
0x1800577fa  lea     rdx, aFwppproxyaleen; "FwppProxyAleEndpointGetSecurityInfo"
0x180057801  call    WfpReportSysErrorAsNtStatus
0x180057806  mov     rbx, rax
0x180057809  test    rax, rax
0x18005780c  jz      short loc_180057818
0x18005780e  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x180057813  call    FwppDeepFree_GUID
0x180057818  mov     rcx, rbx
0x18005781b  call    WfpErrorToFwpErr
0x180057820  mov     rcx, [rsp+88h+var_48]
0x180057825  xor     rcx, rsp; StackCookie
0x180057828  call    __security_check_cookie
0x18005782d  add     rsp, 50h
0x180057831  pop     r15
0x180057833  pop     r14
0x180057835  pop     r12
0x180057837  pop     rdi
0x180057838  pop     rsi
0x180057839  pop     rbp
0x18005783a  pop     rbx
0x18005783b  retn
0x18005783d  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x180057842  mov     r9, r14
0x180057845  mov     [rsp+88h+Sacl], r12; Sacl
0x18005784a  mov     r8, rbp
0x18005784d  mov     edx, esi
0x18005784f  mov     [rsp+88h+Dacl], r15; Dacl
0x180057854  call    FwppSecurityDescriptorGetInfo
0x180057859  mov     rbx, rax
0x18005785c  test    rax, rax
0x18005785f  jnz     short loc_18005780E
0x180057861  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x180057866  mov     [rdi], rax
0x180057869  jmp     short loc_180057818
```
