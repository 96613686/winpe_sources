# FwpmLayerGetSecurityInfoByKey0

- ea: `0x180054c20`
- end: `0x180054d40`
- name: `FwpmLayerGetSecurityInfoByKey0`
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
- `0x18001132c`
- `0x1800203c0`
- `0x180054c20`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180054c74`
- `ntoskrnl!KeGetCurrentIrql` at `0x180054c74`

## string_xrefs

- `0x180054c8a`: `FwpmLayerGetSecurityInfoByKey0`
- `0x180054ccd`: `FwppProxyLayerGetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmLayerGetSecurityInfoByKey0(
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
    v14 = WfpReportAppErrorAsNtStatus(v12, (__int64)"FwpmLayerGetSecurityInfoByKey0", v13);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v13 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfoByKey = FwppProxyLayerGetSecurityInfoByKey(
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
  v14 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyLayerGetSecurityInfoByKey", SecurityInfoByKey);
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
0x180054c20  push    rbx
0x180054c22  push    rbp
0x180054c23  push    rsi
0x180054c24  push    rdi
0x180054c25  push    r12
0x180054c27  push    r13
0x180054c29  push    r14
0x180054c2b  push    r15
0x180054c2d  sub     rsp, 58h
0x180054c31  mov     rax, cs:__security_cookie
0x180054c38  xor     rax, rsp
0x180054c3b  mov     [rsp+98h+var_58], rax
0x180054c40  mov     r14, [rsp+98h+sidGroup]
0x180054c48  xorps   xmm0, xmm0
0x180054c4b  mov     r15, [rsp+98h+dacl]
0x180054c53  mov     rbp, r9
0x180054c56  mov     r12, [rsp+98h+sacl]
0x180054c5e  mov     esi, r8d
0x180054c61  mov     rdi, [rsp+98h+securityDescriptor]
0x180054c69  mov     r13, rdx
0x180054c6c  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x180054c71  mov     rbx, rcx
0x180054c74  call    cs:__imp_KeGetCurrentIrql
0x180054c7b  nop     dword ptr [rax+rax+00h]
0x180054c80  test    al, al
0x180054c82  jz      short loc_180054C98
0x180054c84  mov     r8d, 0C00000BBh
0x180054c8a  lea     rdx, aFwpmlayergetse; "FwpmLayerGetSecurityInfoByKey0"
0x180054c91  call    WfpReportAppErrorAsNtStatus
0x180054c96  jmp     short loc_180054CD9
0x180054c98  test    rbx, rbx
0x180054c9b  jnz     short loc_180054CA5
0x180054c9d  mov     r8d, 0C022001Ch
0x180054ca3  jmp     short loc_180054C8A
0x180054ca5  test    rdi, rdi
0x180054ca8  jz      short loc_180054C9D
0x180054caa  mov     rdx, [rbx+8]
0x180054cae  lea     rax, [rsp+98h+SecurityDescriptor]
0x180054cb3  mov     rcx, [rbx]
0x180054cb6  mov     r9d, esi
0x180054cb9  mov     r8, r13
0x180054cbc  mov     [rsp+98h+Dacl], rax
0x180054cc1  call    FwppProxyLayerGetSecurityInfoByKey
0x180054cc6  test    eax, eax
0x180054cc8  jns     short loc_180054D12
0x180054cca  mov     r8d, eax
0x180054ccd  lea     rdx, aFwppproxylayer_3; "FwppProxyLayerGetSecurityInfoByKey"
0x180054cd4  call    WfpReportSysErrorAsNtStatus
0x180054cd9  mov     rbx, rax
0x180054cdc  test    rax, rax
0x180054cdf  jz      short loc_180054CEB
0x180054ce1  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x180054ce6  call    FwppDeepFree_GUID
0x180054ceb  mov     rcx, rbx
0x180054cee  call    WfpErrorToFwpErr
0x180054cf3  mov     rcx, [rsp+98h+var_58]
0x180054cf8  xor     rcx, rsp; StackCookie
0x180054cfb  call    __security_check_cookie
0x180054d00  add     rsp, 58h
0x180054d04  pop     r15
0x180054d06  pop     r14
0x180054d08  pop     r13
0x180054d0a  pop     r12
0x180054d0c  pop     rdi
0x180054d0d  pop     rsi
0x180054d0e  pop     rbp
0x180054d0f  pop     rbx
0x180054d10  retn
0x180054d12  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x180054d17  mov     r9, r14
0x180054d1a  mov     [rsp+98h+Sacl], r12; Sacl
0x180054d1f  mov     r8, rbp
0x180054d22  mov     edx, esi
0x180054d24  mov     [rsp+98h+Dacl], r15; Dacl
0x180054d29  call    FwppSecurityDescriptorGetInfo
0x180054d2e  mov     rbx, rax
0x180054d31  test    rax, rax
0x180054d34  jnz     short loc_180054CE1
0x180054d36  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x180054d3b  mov     [rdi], rax
0x180054d3e  jmp     short loc_180054CEB
```
