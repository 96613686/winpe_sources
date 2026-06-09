# FwpmConnectionSetSecurityInfo0

- ea: `0x18000e6a0`
- end: `0x18000e7e6`
- name: `FwpmConnectionSetSecurityInfo0`
- size: `326`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x180008480`
- `0x1800086fc`
- `0x180008f10`
- `0x18000e6a0`
- `0x18000fe2c`
- `0x1800203c0`
- `0x1800674e4`
- `0x180068238`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000e6f5`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000e6f5`
- `msrpc!NdrClientCall3` at `0x18000e794`
- `msrpc!NdrClientCall3` at `0x18000e794`

## string_xrefs

- `0x18000e70b`: `FwpmConnectionSetSecurityInfo0`
- `0x18000e7a7`: `FwppProxyConnectionSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall FwpmConnectionSetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        const SID *sidOwner,
        const SID *sidGroup,
        const ACL *dacl,
        const ACL *sacl)
{
  __int64 v10; // rcx
  int v11; // r8d
  const char *v12; // rdx
  __int64 v13; // rbx
  __int64 Engine; // rax
  __int64 v15; // rcx
  __int64 BfeBinding; // rax
  __int64 v17; // rdx
  int Pointer; // eax
  PACL Sacl; // [rsp+28h] [rbp-51h]
  PVOID v21; // [rsp+40h] [rbp-39h] BYREF
  __int64 v22; // [rsp+48h] [rbp-31h] BYREF
  int v23; // [rsp+50h] [rbp-29h]
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1h]

  v23 = 0;
  v22 = 0;
  v25 = 0;
  v21 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( KeGetCurrentIrql() )
  {
    v11 = -1073741637;
LABEL_3:
    v12 = "FwpmConnectionSetSecurityInfo0";
LABEL_10:
    v13 = WfpReportSysErrorAsNtStatus(v10, (int)v12, v11);
    goto LABEL_11;
  }
  if ( !engineHandle )
  {
    v11 = -1071513572;
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
    v13 = BfeSecurityDescriptorEncode(SecurityDescriptor, (__int64)&v22, &v21);
    if ( !v13 )
    {
      Engine = FwppSessionGetEngine(engineHandle);
      BfeBinding = FwppSessionGetBfeBinding(v15, Engine);
      LODWORD(Sacl) = securityInfo;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x81u,
                                0,
                                BfeBinding,
                                v17,
                                Sacl,
                                &v22).Pointer;
      if ( Pointer < 0 )
      {
        v11 = Pointer;
        v12 = "FwppProxyConnectionSetSecurityInfo";
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  WfpNamedPoolFree(v10, &v21);
  return WfpErrorToFwpErr(v13);
}

```

## disassembly

```asm
0x18000e6a0  push    rbp
0x18000e6a2  push    rbx
0x18000e6a3  push    rsi
0x18000e6a4  push    rdi
0x18000e6a5  push    r12
0x18000e6a7  push    r14
0x18000e6a9  push    r15
0x18000e6ab  lea     rbp, [rsp-17h]
0x18000e6b0  sub     rsp, 90h
0x18000e6b7  mov     rax, cs:__security_cookie
0x18000e6be  xor     rax, rsp
0x18000e6c1  mov     [rbp+47h+var_40], rax
0x18000e6c5  mov     r15, [rbp+47h+dacl]
0x18000e6c9  xor     eax, eax
0x18000e6cb  mov     r12, [rbp+47h+sacl]
0x18000e6cf  xorps   xmm0, xmm0
0x18000e6d2  mov     [rbp+47h+var_74], rax
0x18000e6d6  mov     r14, r9
0x18000e6d9  mov     [rbp-31h], rax
0x18000e6dd  mov     rbx, r8
0x18000e6e0  mov     esi, edx
0x18000e6e2  mov     [rbp+47h+var_48], rax
0x18000e6e6  mov     rdi, rcx
0x18000e6e9  mov     [rbp+47h+var_80], rax
0x18000e6ed  movups  [rbp+47h+SecurityDescriptor], xmm0
0x18000e6f1  movups  [rbp+47h+var_58], xmm0
0x18000e6f5  call    cs:__imp_KeGetCurrentIrql
0x18000e6fc  nop     dword ptr [rax+rax+00h]
0x18000e701  test    al, al
0x18000e703  jz      short loc_18000E717
0x18000e705  mov     r8d, 0C00000BBh
0x18000e70b  lea     rdx, aFwpmconnection_6; "FwpmConnectionSetSecurityInfo0"
0x18000e712  jmp     loc_18000E7AE
0x18000e717  test    rdi, rdi
0x18000e71a  jnz     short loc_18000E724
0x18000e71c  mov     r8d, 0C022001Ch
0x18000e722  jmp     short loc_18000E70B
0x18000e724  mov     [rsp+0C0h+Sacl], r12; Sacl
0x18000e729  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18000e72d  mov     r9, r14
0x18000e730  mov     [rsp+0C0h+Dacl], r15; Dacl
0x18000e735  mov     r8, rbx
0x18000e738  mov     edx, esi
0x18000e73a  call    FwppSecurityDescriptorSetInfo
0x18000e73f  mov     rbx, rax
0x18000e742  test    rax, rax
0x18000e745  jnz     short loc_18000E7B6
0x18000e747  lea     r8, [rbp+47h+var_80]
0x18000e74b  lea     rdx, [rbp+47h+var_78]
0x18000e74f  lea     rcx, [rbp+47h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18000e753  call    BfeSecurityDescriptorEncode
0x18000e758  mov     rbx, rax
0x18000e75b  test    rax, rax
0x18000e75e  jnz     short loc_18000E7B6
0x18000e760  mov     rcx, rdi
0x18000e763  call    FwppSessionGetEngine
0x18000e768  mov     rdx, rax
0x18000e76b  call    FwppSessionGetBfeBinding
0x18000e770  lea     rcx, [rbp+47h+var_78]
0x18000e774  mov     r9, rax
0x18000e777  mov     [rsp+0C0h+var_90], rcx
0x18000e77c  xor     r8d, r8d; pReturnValue
0x18000e77f  mov     dword ptr [rsp+0C0h+Sacl], esi
0x18000e783  lea     rcx, pProxyInfo; pProxyInfo
0x18000e78a  mov     [rsp+0C0h+Dacl], rdx
0x18000e78f  mov     edx, 81h; nProcNum
0x18000e794  call    cs:__imp_NdrClientCall3
0x18000e79b  nop     dword ptr [rax+rax+00h]
0x18000e7a0  test    eax, eax
0x18000e7a2  jns     short loc_18000E7B6
0x18000e7a4  mov     r8d, eax
0x18000e7a7  lea     rdx, aFwppproxyconne_1; "FwppProxyConnectionSetSecurityInfo"
0x18000e7ae  call    WfpReportSysErrorAsNtStatus
0x18000e7b3  mov     rbx, rax
0x18000e7b6  lea     rdx, [rbp+47h+var_80]
0x18000e7ba  call    WfpNamedPoolFree
0x18000e7bf  mov     rcx, rbx
0x18000e7c2  call    WfpErrorToFwpErr
0x18000e7c7  mov     rcx, [rbp+47h+var_40]
0x18000e7cb  xor     rcx, rsp; StackCookie
0x18000e7ce  call    __security_check_cookie
0x18000e7d3  add     rsp, 90h
0x18000e7da  pop     r15
0x18000e7dc  pop     r14
0x18000e7de  pop     r12
0x18000e7e0  pop     rdi
0x18000e7e1  pop     rsi
0x18000e7e2  pop     rbx
0x18000e7e3  pop     rbp
0x18000e7e4  retn
```
