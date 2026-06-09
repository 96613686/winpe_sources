# IkeextSaDbSetSecurityInfo0

- ea: `0x18000f240`
- end: `0x18000f36c`
- name: `IkeextSaDbSetSecurityInfo0`
- size: `300`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x180008480`
- `0x1800086fc`
- `0x180008f10`
- `0x18000f240`
- `0x18000fe2c`
- `0x180011cb0`
- `0x1800203c0`

## import_xrefs

- `msrpc!NdrClientCall3` at `0x18000f31a`
- `msrpc!NdrClientCall3` at `0x18000f31a`

## string_xrefs

- `0x18000f2a3`: `IkeextSaDbSetSecurityInfo0`
- `0x18000f32d`: `FwppProxyIkeSaDbSetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IkeextSaDbSetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        const SID *sidOwner,
        const SID *sidGroup,
        const ACL *dacl,
        const ACL *sacl)
{
  int v9; // r8d
  const char *v10; // rdx
  __int64 IkeBinding; // rbx
  int Pointer; // eax
  PACL Dacl; // [rsp+20h] [rbp-60h]
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  PVOID v16; // [rsp+38h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  int v18; // [rsp+48h] [rbp-38h]
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h]

  v18 = 0;
  v17 = 0;
  v15 = 0;
  v20 = 0;
  v16 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !engineHandle )
  {
    v9 = -1071513572;
    v10 = "IkeextSaDbSetSecurityInfo0";
LABEL_8:
    IkeBinding = WfpReportSysErrorAsNtStatus((__int64)engineHandle, (int)v10, v9);
    goto LABEL_9;
  }
  IkeBinding = FwppSessionGetIkeBinding(engineHandle, &v15);
  if ( !IkeBinding )
  {
    IkeBinding = FwppSecurityDescriptorSetInfo(
                   SecurityDescriptor,
                   securityInfo,
                   (void *)sidOwner,
                   (void *)sidGroup,
                   (PACL)dacl,
                   (PACL)sacl);
    if ( !IkeBinding )
    {
      IkeBinding = BfeSecurityDescriptorEncode(SecurityDescriptor, (__int64)&v17, &v16);
      if ( !IkeBinding )
      {
        LODWORD(Dacl) = securityInfo;
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180033240, 7u, 0, v15, Dacl, &v17).Pointer;
        if ( Pointer < 0 )
        {
          v9 = Pointer;
          v10 = "FwppProxyIkeSaDbSetSecurityInfo";
          goto LABEL_8;
        }
      }
    }
  }
LABEL_9:
  WfpNamedPoolFree((__int64)engineHandle, &v16);
  return WfpErrorToFwpErr(IkeBinding);
}

```

## disassembly

```asm
0x18000f240  push    rbp
0x18000f242  push    rbx
0x18000f243  push    rsi
0x18000f244  push    rdi
0x18000f245  push    r12
0x18000f247  push    r14
0x18000f249  push    r15
0x18000f24b  mov     rbp, rsp
0x18000f24e  sub     rsp, 80h
0x18000f255  mov     rax, cs:__security_cookie
0x18000f25c  xor     rax, rsp
0x18000f25f  mov     [rbp+var_8], rax
0x18000f263  mov     r15, [rbp+dacl]
0x18000f267  xor     eax, eax
0x18000f269  mov     r12, [rbp+sacl]
0x18000f26d  xorps   xmm0, xmm0
0x18000f270  mov     [rbp+var_3C], rax
0x18000f274  mov     r14, r9
0x18000f277  mov     [rbp-40h], rax
0x18000f27b  mov     rsi, r8
0x18000f27e  mov     [rbp+var_50], 0
0x18000f286  mov     edi, edx
0x18000f288  mov     [rbp+var_10], rax
0x18000f28c  mov     [rbp+var_48], rax
0x18000f290  movups  [rbp+SecurityDescriptor], xmm0
0x18000f294  movups  [rbp+var_20], xmm0
0x18000f298  test    rcx, rcx
0x18000f29b  jnz     short loc_18000F2AF
0x18000f29d  mov     r8d, 0C022001Ch
0x18000f2a3  lea     rdx, aIkeextsadbsets; "IkeextSaDbSetSecurityInfo0"
0x18000f2aa  jmp     loc_18000F334
0x18000f2af  lea     rdx, [rbp+var_50]
0x18000f2b3  call    FwppSessionGetIkeBinding
0x18000f2b8  mov     rbx, rax
0x18000f2bb  test    rax, rax
0x18000f2be  jnz     short loc_18000F33C
0x18000f2c0  mov     [rsp+80h+Sacl], r12; Sacl
0x18000f2c5  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000f2c9  mov     r9, r14
0x18000f2cc  mov     [rsp+80h+Dacl], r15; Dacl
0x18000f2d1  mov     r8, rsi
0x18000f2d4  mov     edx, edi
0x18000f2d6  call    FwppSecurityDescriptorSetInfo
0x18000f2db  mov     rbx, rax
0x18000f2de  test    rax, rax
0x18000f2e1  jnz     short loc_18000F33C
0x18000f2e3  lea     r8, [rbp+var_48]
0x18000f2e7  lea     rdx, [rbp+var_40]
0x18000f2eb  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18000f2ef  call    BfeSecurityDescriptorEncode
0x18000f2f4  mov     rbx, rax
0x18000f2f7  test    rax, rax
0x18000f2fa  jnz     short loc_18000F33C
0x18000f2fc  mov     r9, [rbp+var_50]
0x18000f300  lea     rax, [rbp+var_40]
0x18000f304  mov     [rsp+80h+Sacl], rax
0x18000f309  lea     edx, [rbx+7]; nProcNum
0x18000f30c  xor     r8d, r8d; pReturnValue
0x18000f30f  mov     dword ptr [rsp+80h+Dacl], edi
0x18000f313  lea     rcx, stru_180033240; pProxyInfo
0x18000f31a  call    cs:__imp_NdrClientCall3
0x18000f321  nop     dword ptr [rax+rax+00h]
0x18000f326  test    eax, eax
0x18000f328  jns     short loc_18000F33C
0x18000f32a  mov     r8d, eax
0x18000f32d  lea     rdx, aFwppproxyikesa_3; "FwppProxyIkeSaDbSetSecurityInfo"
0x18000f334  call    WfpReportSysErrorAsNtStatus
0x18000f339  mov     rbx, rax
0x18000f33c  lea     rdx, [rbp+var_48]
0x18000f340  call    WfpNamedPoolFree
0x18000f345  mov     rcx, rbx
0x18000f348  call    WfpErrorToFwpErr
0x18000f34d  mov     rcx, [rbp+var_8]
0x18000f351  xor     rcx, rsp; StackCookie
0x18000f354  call    __security_check_cookie
0x18000f359  add     rsp, 80h
0x18000f360  pop     r15
0x18000f362  pop     r14
0x18000f364  pop     r12
0x18000f366  pop     rdi
0x18000f367  pop     rsi
0x18000f368  pop     rbx
0x18000f369  pop     rbp
0x18000f36a  retn
```
