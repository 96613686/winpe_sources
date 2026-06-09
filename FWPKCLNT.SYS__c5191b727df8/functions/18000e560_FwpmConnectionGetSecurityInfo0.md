# FwpmConnectionGetSecurityInfo0

- ea: `0x18000e560`
- end: `0x18000e693`
- name: `FwpmConnectionGetSecurityInfo0`
- size: `307`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x180008440`
- `0x180008f10`
- `0x18000e560`
- `0x18000fccc`
- `0x1800203c0`
- `0x1800674e4`
- `0x180068238`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000e5a9`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000e5a9`
- `msrpc!NdrClientCall3` at `0x18000e60f`
- `msrpc!NdrClientCall3` at `0x18000e60f`

## string_xrefs

- `0x18000e5bf`: `FwpmConnectionGetSecurityInfo0`
- `0x18000e622`: `FwppProxyConnectionGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpmConnectionGetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        PSID *sidOwner,
        PSID *sidGroup,
        PACL *dacl,
        PACL *sacl,
        PSECURITY_DESCRIPTOR *securityDescriptor)
{
  __int64 v11; // rcx
  int v12; // r8d
  const char *v13; // rdx
  __int64 Engine; // rax
  __int64 v15; // rcx
  __int64 BfeBinding; // rax
  __int64 v17; // rdx
  int Pointer; // eax
  __int64 Info; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+40h] [rbp-58h] BYREF

  *(_OWORD *)SecurityDescriptor = 0;
  if ( KeGetCurrentIrql() )
  {
    v12 = -1073741637;
LABEL_3:
    v13 = "FwpmConnectionGetSecurityInfo0";
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v12 = -1071513572;
    goto LABEL_3;
  }
  Engine = FwppSessionGetEngine(engineHandle);
  BfeBinding = FwppSessionGetBfeBinding(v15, Engine);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x80u,
                            0,
                            BfeBinding,
                            v17,
                            securityInfo,
                            SecurityDescriptor).Pointer;
  if ( Pointer >= 0 )
  {
    Info = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], securityInfo, sidOwner, sidGroup, dacl, sacl);
    if ( !Info )
    {
      *securityDescriptor = SecurityDescriptor[1];
      return WfpErrorToFwpErr(Info);
    }
    goto LABEL_10;
  }
  v12 = Pointer;
  v13 = "FwppProxyConnectionGetSecurityInfo";
LABEL_9:
  Info = WfpReportSysErrorAsNtStatus(v11, (int)v13, v12);
  if ( Info )
LABEL_10:
    FwppDeepFree_GUID(SecurityDescriptor[1]);
  return WfpErrorToFwpErr(Info);
}

```

## disassembly

```asm
0x18000e560  push    rbx
0x18000e562  push    rbp
0x18000e563  push    rsi
0x18000e564  push    rdi
0x18000e565  push    r12
0x18000e567  push    r14
0x18000e569  push    r15
0x18000e56b  sub     rsp, 60h
0x18000e56f  mov     rax, cs:__security_cookie
0x18000e576  xor     rax, rsp
0x18000e579  mov     [rsp+98h+var_48], rax
0x18000e57e  mov     r15, [rsp+98h+dacl]
0x18000e586  xorps   xmm0, xmm0
0x18000e589  mov     r12, [rsp+98h+sacl]
0x18000e591  mov     r14, r9
0x18000e594  mov     rdi, [rsp+98h+securityDescriptor]
0x18000e59c  mov     rbp, r8
0x18000e59f  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x18000e5a4  mov     esi, edx
0x18000e5a6  mov     rbx, rcx
0x18000e5a9  call    cs:__imp_KeGetCurrentIrql
0x18000e5b0  nop     dword ptr [rax+rax+00h]
0x18000e5b5  test    al, al
0x18000e5b7  jz      short loc_18000E5C8
0x18000e5b9  mov     r8d, 0C00000BBh
0x18000e5bf  lea     rdx, aFwpmconnection_4; "FwpmConnectionGetSecurityInfo0"
0x18000e5c6  jmp     short loc_18000E629
0x18000e5c8  test    rbx, rbx
0x18000e5cb  jnz     short loc_18000E5D5
0x18000e5cd  mov     r8d, 0C022001Ch
0x18000e5d3  jmp     short loc_18000E5BF
0x18000e5d5  test    rdi, rdi
0x18000e5d8  jz      short loc_18000E5CD
0x18000e5da  mov     rcx, rbx
0x18000e5dd  call    FwppSessionGetEngine
0x18000e5e2  mov     rdx, rax
0x18000e5e5  call    FwppSessionGetBfeBinding
0x18000e5ea  lea     rcx, [rsp+98h+SecurityDescriptor]
0x18000e5ef  mov     r9, rax
0x18000e5f2  mov     [rsp+98h+var_68], rcx
0x18000e5f7  xor     r8d, r8d; pReturnValue
0x18000e5fa  mov     dword ptr [rsp+98h+Sacl], esi
0x18000e5fe  lea     rcx, pProxyInfo; pProxyInfo
0x18000e605  mov     [rsp+98h+Dacl], rdx
0x18000e60a  mov     edx, 80h; nProcNum
0x18000e60f  call    cs:__imp_NdrClientCall3
0x18000e616  nop     dword ptr [rax+rax+00h]
0x18000e61b  test    eax, eax
0x18000e61d  jns     short loc_18000E665
0x18000e61f  mov     r8d, eax
0x18000e622  lea     rdx, aFwppproxyconne_2; "FwppProxyConnectionGetSecurityInfo"
0x18000e629  call    WfpReportSysErrorAsNtStatus
0x18000e62e  mov     rbx, rax
0x18000e631  test    rax, rax
0x18000e634  jz      short loc_18000E640
0x18000e636  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x18000e63b  call    FwppDeepFree_GUID
0x18000e640  mov     rcx, rbx
0x18000e643  call    WfpErrorToFwpErr
0x18000e648  mov     rcx, [rsp+98h+var_48]
0x18000e64d  xor     rcx, rsp; StackCookie
0x18000e650  call    __security_check_cookie
0x18000e655  add     rsp, 60h
0x18000e659  pop     r15
0x18000e65b  pop     r14
0x18000e65d  pop     r12
0x18000e65f  pop     rdi
0x18000e660  pop     rsi
0x18000e661  pop     rbp
0x18000e662  pop     rbx
0x18000e663  retn
0x18000e665  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x18000e66a  mov     r9, r14
0x18000e66d  mov     [rsp+98h+Sacl], r12; Sacl
0x18000e672  mov     r8, rbp
0x18000e675  mov     edx, esi
0x18000e677  mov     [rsp+98h+Dacl], r15; Dacl
0x18000e67c  call    FwppSecurityDescriptorGetInfo
0x18000e681  mov     rbx, rax
0x18000e684  test    rax, rax
0x18000e687  jnz     short loc_18000E636
0x18000e689  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x18000e68e  mov     [rdi], rax
0x18000e691  jmp     short loc_18000E640
```
