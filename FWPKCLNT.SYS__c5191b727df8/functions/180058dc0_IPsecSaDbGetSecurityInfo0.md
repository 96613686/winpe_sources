# IPsecSaDbGetSecurityInfo0

- ea: `0x180058dc0`
- end: `0x180058ecb`
- name: `IPsecSaDbGetSecurityInfo0`
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
- `0x180010c98`
- `0x1800203c0`
- `0x180058dc0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180058e09`
- `ntoskrnl!KeGetCurrentIrql` at `0x180058e09`

## string_xrefs

- `0x180058e1f`: `IPsecSaDbGetSecurityInfo0`
- `0x180058e5a`: `FwppProxyBfeIPsecSaDbGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IPsecSaDbGetSecurityInfo0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"IPsecSaDbGetSecurityInfo0", v12);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = FwppProxyBfeIPsecSaDbGetSecurityInfo(
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
  v13 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyBfeIPsecSaDbGetSecurityInfo", v14);
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
0x180058dc0  push    rbx
0x180058dc2  push    rbp
0x180058dc3  push    rsi
0x180058dc4  push    rdi
0x180058dc5  push    r12
0x180058dc7  push    r14
0x180058dc9  push    r15
0x180058dcb  sub     rsp, 50h
0x180058dcf  mov     rax, cs:__security_cookie
0x180058dd6  xor     rax, rsp
0x180058dd9  mov     [rsp+88h+var_48], rax
0x180058dde  mov     r15, [rsp+88h+dacl]
0x180058de6  xorps   xmm0, xmm0
0x180058de9  mov     r12, [rsp+88h+sacl]
0x180058df1  mov     r14, r9
0x180058df4  mov     rdi, [rsp+88h+securityDescriptor]
0x180058dfc  mov     rbp, r8
0x180058dff  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x180058e04  mov     esi, edx
0x180058e06  mov     rbx, rcx
0x180058e09  call    cs:__imp_KeGetCurrentIrql
0x180058e10  nop     dword ptr [rax+rax+00h]
0x180058e15  test    al, al
0x180058e17  jz      short loc_180058E2D
0x180058e19  mov     r8d, 0C00000BBh
0x180058e1f  lea     rdx, aIpsecsadbgetse; "IPsecSaDbGetSecurityInfo0"
0x180058e26  call    WfpReportAppErrorAsNtStatus
0x180058e2b  jmp     short loc_180058E66
0x180058e2d  test    rbx, rbx
0x180058e30  jnz     short loc_180058E3A
0x180058e32  mov     r8d, 0C022001Ch
0x180058e38  jmp     short loc_180058E1F
0x180058e3a  test    rdi, rdi
0x180058e3d  jz      short loc_180058E32
0x180058e3f  mov     rdx, [rbx+8]
0x180058e43  lea     r9, [rsp+88h+SecurityDescriptor]
0x180058e48  mov     rcx, [rbx]
0x180058e4b  mov     r8d, esi
0x180058e4e  call    FwppProxyBfeIPsecSaDbGetSecurityInfo
0x180058e53  test    eax, eax
0x180058e55  jns     short loc_180058E9D
0x180058e57  mov     r8d, eax
0x180058e5a  lea     rdx, aFwppproxybfeip_26; "FwppProxyBfeIPsecSaDbGetSecurityInfo"
0x180058e61  call    WfpReportSysErrorAsNtStatus
0x180058e66  mov     rbx, rax
0x180058e69  test    rax, rax
0x180058e6c  jz      short loc_180058E78
0x180058e6e  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x180058e73  call    FwppDeepFree_GUID
0x180058e78  mov     rcx, rbx
0x180058e7b  call    WfpErrorToFwpErr
0x180058e80  mov     rcx, [rsp+88h+var_48]
0x180058e85  xor     rcx, rsp; StackCookie
0x180058e88  call    __security_check_cookie
0x180058e8d  add     rsp, 50h
0x180058e91  pop     r15
0x180058e93  pop     r14
0x180058e95  pop     r12
0x180058e97  pop     rdi
0x180058e98  pop     rsi
0x180058e99  pop     rbp
0x180058e9a  pop     rbx
0x180058e9b  retn
0x180058e9d  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x180058ea2  mov     r9, r14
0x180058ea5  mov     [rsp+88h+Sacl], r12; Sacl
0x180058eaa  mov     r8, rbp
0x180058ead  mov     edx, esi
0x180058eaf  mov     [rsp+88h+Dacl], r15; Dacl
0x180058eb4  call    FwppSecurityDescriptorGetInfo
0x180058eb9  mov     rbx, rax
0x180058ebc  test    rax, rax
0x180058ebf  jnz     short loc_180058E6E
0x180058ec1  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x180058ec6  mov     [rdi], rax
0x180058ec9  jmp     short loc_180058E78
```
