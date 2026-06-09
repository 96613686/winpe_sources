# IPsecDospGetSecurityInfo0

- ea: `0x180057a70`
- end: `0x180057b7b`
- name: `IPsecDospGetSecurityInfo0`
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
- `0x180010704`
- `0x1800203c0`
- `0x180057a70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180057ab9`
- `ntoskrnl!KeGetCurrentIrql` at `0x180057ab9`

## string_xrefs

- `0x180057acf`: `IPsecDospGetSecurityInfo0`
- `0x180057b0a`: `FwppProxyBfeIPsecDospGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IPsecDospGetSecurityInfo0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"IPsecDospGetSecurityInfo0", v12);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = FwppProxyBfeIPsecDospGetSecurityInfo(
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
  v13 = WfpReportSysErrorAsNtStatus(v15, (int)"FwppProxyBfeIPsecDospGetSecurityInfo", v14);
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
0x180057a70  push    rbx
0x180057a72  push    rbp
0x180057a73  push    rsi
0x180057a74  push    rdi
0x180057a75  push    r12
0x180057a77  push    r14
0x180057a79  push    r15
0x180057a7b  sub     rsp, 50h
0x180057a7f  mov     rax, cs:__security_cookie
0x180057a86  xor     rax, rsp
0x180057a89  mov     [rsp+88h+var_48], rax
0x180057a8e  mov     r15, [rsp+88h+dacl]
0x180057a96  xorps   xmm0, xmm0
0x180057a99  mov     r12, [rsp+88h+sacl]
0x180057aa1  mov     r14, r9
0x180057aa4  mov     rdi, [rsp+88h+securityDescriptor]
0x180057aac  mov     rbp, r8
0x180057aaf  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x180057ab4  mov     esi, edx
0x180057ab6  mov     rbx, rcx
0x180057ab9  call    cs:__imp_KeGetCurrentIrql
0x180057ac0  nop     dword ptr [rax+rax+00h]
0x180057ac5  test    al, al
0x180057ac7  jz      short loc_180057ADD
0x180057ac9  mov     r8d, 0C00000BBh
0x180057acf  lea     rdx, aIpsecdospgetse; "IPsecDospGetSecurityInfo0"
0x180057ad6  call    WfpReportAppErrorAsNtStatus
0x180057adb  jmp     short loc_180057B16
0x180057add  test    rbx, rbx
0x180057ae0  jnz     short loc_180057AEA
0x180057ae2  mov     r8d, 0C022001Ch
0x180057ae8  jmp     short loc_180057ACF
0x180057aea  test    rdi, rdi
0x180057aed  jz      short loc_180057AE2
0x180057aef  mov     rdx, [rbx+8]
0x180057af3  lea     r9, [rsp+88h+SecurityDescriptor]
0x180057af8  mov     rcx, [rbx]
0x180057afb  mov     r8d, esi
0x180057afe  call    FwppProxyBfeIPsecDospGetSecurityInfo
0x180057b03  test    eax, eax
0x180057b05  jns     short loc_180057B4D
0x180057b07  mov     r8d, eax
0x180057b0a  lea     rdx, aFwppproxybfeip_21; "FwppProxyBfeIPsecDospGetSecurityInfo"
0x180057b11  call    WfpReportSysErrorAsNtStatus
0x180057b16  mov     rbx, rax
0x180057b19  test    rax, rax
0x180057b1c  jz      short loc_180057B28
0x180057b1e  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x180057b23  call    FwppDeepFree_GUID
0x180057b28  mov     rcx, rbx
0x180057b2b  call    WfpErrorToFwpErr
0x180057b30  mov     rcx, [rsp+88h+var_48]
0x180057b35  xor     rcx, rsp; StackCookie
0x180057b38  call    __security_check_cookie
0x180057b3d  add     rsp, 50h
0x180057b41  pop     r15
0x180057b43  pop     r14
0x180057b45  pop     r12
0x180057b47  pop     rdi
0x180057b48  pop     rsi
0x180057b49  pop     rbp
0x180057b4a  pop     rbx
0x180057b4b  retn
0x180057b4d  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x180057b52  mov     r9, r14
0x180057b55  mov     [rsp+88h+Sacl], r12; Sacl
0x180057b5a  mov     r8, rbp
0x180057b5d  mov     edx, esi
0x180057b5f  mov     [rsp+88h+Dacl], r15; Dacl
0x180057b64  call    FwppSecurityDescriptorGetInfo
0x180057b69  mov     rbx, rax
0x180057b6c  test    rax, rax
0x180057b6f  jnz     short loc_180057B1E
0x180057b71  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x180057b76  mov     [rdi], rax
0x180057b79  jmp     short loc_180057B28
```
