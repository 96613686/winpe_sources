# SetComSecurity(void)

- ea: `0x140007844`
- end: `0x1400079ed`
- name: `?SetComSecurity@@YAJXZ`
- size: `425`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x140007714`
- `0x140007734`
- `0x140007844`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007941`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140007941`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007886`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140007886`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000798f`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000798f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400078b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400079c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400078b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400079c5`

## pseudocode

```c
__int64 SetComSecurity(void)
{
  const char *v0; // r9
  __int64 v1; // rdx
  unsigned int LastError; // ebx
  HRESULT v4; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwOwnerSize; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwSaclSize; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDaclSize; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pPrimaryGroup[256]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pOwner[256]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE pAbsoluteSecurityDescriptor[512]; // [rsp+280h] [rbp+180h] BYREF
  struct _ACL pDacl; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+698h] [rbp+598h]

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;0x3;;;PS)(A;;0x3;;;SY)(A;;0x3;;;BA)(A;;0x3;;;LS)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    v1 = 315;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v1,
                  (int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                  v0);
LABEL_4:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return LastError;
  }
  dwSaclSize = 0;
  dwAbsoluteSecurityDescriptorSize = 512;
  dwDaclSize = 512;
  dwOwnerSize = 256;
  dwPrimaryGroupSize = 256;
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          &dwAbsoluteSecurityDescriptorSize,
          &pDacl,
          &dwDaclSize,
          0,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v1 = 342;
    goto LABEL_3;
  }
  v4 = CoInitializeSecurity(pAbsoluteSecurityDescriptor, -1, 0, 0, 0, 2u, 0, 0, 0);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
      (const char *)(unsigned int)v4);
    goto LABEL_4;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x140007844  mov     [rsp-8+arg_0], rbx
0x140007849  push    rbp
0x14000784a  lea     rbp, [rsp-590h]
0x140007852  sub     rsp, 690h
0x140007859  mov     rax, cs:__security_cookie
0x140007860  xor     rax, rsp
0x140007863  mov     [rbp+590h+var_10], rax
0x14000786a  xor     r9d, r9d; SecurityDescriptorSize
0x14000786d  mov     [rsp+690h+SecurityDescriptor], 0
0x140007876  lea     r8, [rsp+690h+SecurityDescriptor]; SecurityDescriptor
0x14000787b  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x3;;;PS)(A;;0x3;;;SY)(A;"...
0x140007882  lea     edx, [r9+1]; StringSDRevision
0x140007886  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14000788c  test    eax, eax
0x14000788e  jnz     short loc_1400078C1
0x140007890  mov     edx, 13Bh; void *
0x140007895  mov     rcx, [rbp+598h]; this
0x14000789c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x1400078a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400078a8  mov     ebx, eax
0x1400078aa  mov     rcx, [rsp+690h+SecurityDescriptor]; hMem
0x1400078af  test    rcx, rcx
0x1400078b2  jz      short loc_1400078BA
0x1400078b4  call    cs:__imp_LocalFree
0x1400078ba  mov     eax, ebx
0x1400078bc  jmp     loc_1400079CD
0x1400078c1  mov     rcx, [rsp+690h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x1400078c6  lea     r9, [rbp+590h+pDacl]; pDacl
0x1400078cd  mov     eax, 200h
0x1400078d2  mov     [rsp+690h+dwSaclSize], 0
0x1400078da  mov     [rsp+690h+dwAbsoluteSecurityDescriptorSize], eax
0x1400078de  lea     r8, [rsp+690h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1400078e3  mov     [rsp+690h+dwDaclSize], eax
0x1400078e7  lea     rdx, [rbp+590h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1400078ee  mov     eax, 100h
0x1400078f3  mov     [rsp+690h+dwOwnerSize], eax
0x1400078f7  mov     [rsp+690h+dwPrimaryGroupSize], eax
0x1400078fb  lea     rax, [rsp+690h+dwPrimaryGroupSize]
0x140007900  mov     [rsp+690h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140007905  lea     rax, [rbp+590h+var_610]
0x140007909  mov     [rsp+690h+pPrimaryGroup], rax; pPrimaryGroup
0x14000790e  lea     rax, [rsp+690h+dwOwnerSize]
0x140007913  mov     [rsp+690h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140007918  lea     rax, [rbp+590h+var_510]
0x14000791f  mov     [rsp+690h+pOwner], rax; pOwner
0x140007924  lea     rax, [rsp+690h+dwSaclSize]
0x140007929  mov     [rsp+690h+lpdwSaclSize], rax; lpdwSaclSize
0x14000792e  lea     rax, [rsp+690h+dwDaclSize]
0x140007933  mov     [rsp+690h+pSacl], 0; pSacl
0x14000793c  mov     [rsp+690h+lpdwDaclSize], rax; lpdwDaclSize
0x140007941  call    cs:__imp_MakeAbsoluteSD
0x140007947  test    eax, eax
0x140007949  jnz     short loc_140007955
0x14000794b  mov     edx, 156h
0x140007950  jmp     loc_140007895
0x140007955  mov     [rsp+690h+lpdwOwnerSize], 0; pReserved3
0x14000795e  lea     rcx, [rbp+590h+pAbsoluteSecurityDescriptor]; pSecDesc
0x140007965  mov     dword ptr [rsp+690h+pOwner], 0; dwCapabilities
0x14000796d  xor     r9d, r9d; pReserved1
0x140007970  mov     [rsp+690h+lpdwSaclSize], 0; pAuthList
0x140007979  xor     r8d, r8d; asAuthSvc
0x14000797c  mov     dword ptr [rsp+690h+pSacl], 2; dwImpLevel
0x140007984  or      edx, 0FFFFFFFFh; cAuthSvc
0x140007987  mov     dword ptr [rsp+690h+lpdwDaclSize], 0; int
0x14000798f  call    cs:__imp_CoInitializeSecurity
0x140007995  mov     ebx, eax
0x140007997  test    eax, eax
0x140007999  jns     short loc_1400079BB
0x14000799b  mov     rcx, [rbp+598h]; this
0x1400079a2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x1400079a9  mov     r9d, eax; char *
0x1400079ac  mov     edx, 161h; void *
0x1400079b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400079b6  jmp     loc_1400078AA
0x1400079bb  mov     rcx, [rsp+690h+SecurityDescriptor]; hMem
0x1400079c0  test    rcx, rcx
0x1400079c3  jz      short loc_1400079CB
0x1400079c5  call    cs:__imp_LocalFree
0x1400079cb  xor     eax, eax
0x1400079cd  mov     rcx, [rbp+590h+var_10]
0x1400079d4  xor     rcx, rsp; StackCookie
0x1400079d7  call    __security_check_cookie
0x1400079dc  mov     rbx, [rsp+690h+arg_0]
0x1400079e4  add     rsp, 690h
0x1400079eb  pop     rbp
0x1400079ec  retn
```
