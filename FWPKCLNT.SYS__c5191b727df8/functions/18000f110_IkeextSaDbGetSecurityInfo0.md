# IkeextSaDbGetSecurityInfo0

- ea: `0x18000f110`
- end: `0x18000f22e`
- name: `IkeextSaDbGetSecurityInfo0`
- size: `286`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x180008440`
- `0x180008f10`
- `0x18000f110`
- `0x18000fccc`
- `0x180011cb0`
- `0x1800203c0`

## import_xrefs

- `msrpc!NdrClientCall3` at `0x18000f1aa`
- `msrpc!NdrClientCall3` at `0x18000f1aa`

## string_xrefs

- `0x18000f16a`: `IkeextSaDbGetSecurityInfo0`
- `0x18000f1bd`: `FwppProxyIkeSaDbGetSecurityInfo`

## pseudocode

```c
NTSTATUS __stdcall IkeextSaDbGetSecurityInfo0(
        HANDLE engineHandle,
        SECURITY_INFORMATION securityInfo,
        PSID *sidOwner,
        PSID *sidGroup,
        PACL *dacl,
        PACL *sacl,
        PSECURITY_DESCRIPTOR *securityDescriptor)
{
  int v10; // r8d
  const char *v11; // rdx
  __int64 IkeBinding; // rbx
  int Pointer; // eax
  __int64 v15; // [rsp+30h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+38h] [rbp-50h] BYREF

  v15 = 0;
  *(_OWORD *)SecurityDescriptor = 0;
  if ( engineHandle && securityDescriptor )
  {
    IkeBinding = FwppSessionGetIkeBinding(engineHandle, &v15);
    if ( IkeBinding )
    {
LABEL_8:
      FwppDeepFree_GUID(SecurityDescriptor[1]);
      return WfpErrorToFwpErr(IkeBinding);
    }
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_180033240,
                              6u,
                              0,
                              v15,
                              securityInfo,
                              SecurityDescriptor).Pointer;
    if ( Pointer >= 0 )
    {
      IkeBinding = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], securityInfo, sidOwner, sidGroup, dacl, sacl);
      if ( !IkeBinding )
      {
        *securityDescriptor = SecurityDescriptor[1];
        return WfpErrorToFwpErr(IkeBinding);
      }
      goto LABEL_8;
    }
    v10 = Pointer;
    v11 = "FwppProxyIkeSaDbGetSecurityInfo";
  }
  else
  {
    v10 = -1071513572;
    v11 = "IkeextSaDbGetSecurityInfo0";
  }
  IkeBinding = WfpReportSysErrorAsNtStatus((__int64)engineHandle, (int)v11, v10);
  if ( IkeBinding )
    goto LABEL_8;
  return WfpErrorToFwpErr(IkeBinding);
}

```

## disassembly

```asm
0x18000f110  push    rbx
0x18000f112  push    rbp
0x18000f113  push    rsi
0x18000f114  push    rdi
0x18000f115  push    r12
0x18000f117  push    r14
0x18000f119  push    r15
0x18000f11b  sub     rsp, 50h
0x18000f11f  mov     rax, cs:__security_cookie
0x18000f126  xor     rax, rsp
0x18000f129  mov     [rsp+88h+var_40], rax
0x18000f12e  mov     r15, [rsp+88h+dacl]
0x18000f136  xorps   xmm0, xmm0
0x18000f139  mov     r12, [rsp+88h+sacl]
0x18000f141  mov     r14, r9
0x18000f144  mov     rdi, [rsp+88h+securityDescriptor]
0x18000f14c  mov     rbp, r8
0x18000f14f  mov     [rsp+88h+var_58], 0
0x18000f158  mov     esi, edx
0x18000f15a  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x18000f15f  test    rcx, rcx
0x18000f162  jnz     short loc_18000F173
0x18000f164  mov     r8d, 0C022001Ch
0x18000f16a  lea     rdx, aIkeextsadbgets; "IkeextSaDbGetSecurityInfo0"
0x18000f171  jmp     short loc_18000F1C4
0x18000f173  test    rdi, rdi
0x18000f176  jz      short loc_18000F164
0x18000f178  lea     rdx, [rsp+88h+var_58]
0x18000f17d  call    FwppSessionGetIkeBinding
0x18000f182  mov     rbx, rax
0x18000f185  test    rax, rax
0x18000f188  jnz     short loc_18000F1D1
0x18000f18a  mov     r9, [rsp+88h+var_58]
0x18000f18f  lea     rax, [rsp+88h+SecurityDescriptor]
0x18000f194  mov     [rsp+88h+Sacl], rax
0x18000f199  lea     edx, [rbx+6]; nProcNum
0x18000f19c  xor     r8d, r8d; pReturnValue
0x18000f19f  mov     dword ptr [rsp+88h+Dacl], esi
0x18000f1a3  lea     rcx, stru_180033240; pProxyInfo
0x18000f1aa  call    cs:__imp_NdrClientCall3
0x18000f1b1  nop     dword ptr [rax+rax+00h]
0x18000f1b6  test    eax, eax
0x18000f1b8  jns     short loc_18000F200
0x18000f1ba  mov     r8d, eax
0x18000f1bd  lea     rdx, aFwppproxyikesa_4; "FwppProxyIkeSaDbGetSecurityInfo"
0x18000f1c4  call    WfpReportSysErrorAsNtStatus
0x18000f1c9  mov     rbx, rax
0x18000f1cc  test    rax, rax
0x18000f1cf  jz      short loc_18000F1DB
0x18000f1d1  mov     rcx, [rsp+88h+SecurityDescriptor+8]
0x18000f1d6  call    FwppDeepFree_GUID
0x18000f1db  mov     rcx, rbx
0x18000f1de  call    WfpErrorToFwpErr
0x18000f1e3  mov     rcx, [rsp+88h+var_40]
0x18000f1e8  xor     rcx, rsp; StackCookie
0x18000f1eb  call    __security_check_cookie
0x18000f1f0  add     rsp, 50h
0x18000f1f4  pop     r15
0x18000f1f6  pop     r14
0x18000f1f8  pop     r12
0x18000f1fa  pop     rdi
0x18000f1fb  pop     rsi
0x18000f1fc  pop     rbp
0x18000f1fd  pop     rbx
0x18000f1fe  retn
0x18000f200  mov     rcx, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x18000f205  mov     r9, r14
0x18000f208  mov     [rsp+88h+Sacl], r12; Sacl
0x18000f20d  mov     r8, rbp
0x18000f210  mov     edx, esi
0x18000f212  mov     [rsp+88h+Dacl], r15; Dacl
0x18000f217  call    FwppSecurityDescriptorGetInfo
0x18000f21c  mov     rbx, rax
0x18000f21f  test    rax, rax
0x18000f222  jnz     short loc_18000F1D1
0x18000f224  mov     rax, [rsp+88h+SecurityDescriptor+8]
0x18000f229  mov     [rdi], rax
0x18000f22c  jmp     short loc_18000F1DB
```
