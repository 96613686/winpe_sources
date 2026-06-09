# _InitializeCOMSecurity_ForBrokerProcess

- ea: `0x140005110`
- end: `0x14000547e`
- name: `_InitializeCOMSecurity_ForBrokerProcess`
- size: `878`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400054fc`

## callees

- `0x140004a10`
- `0x140004a2c`
- `0x140004c48`
- `0x140004c6c`
- `0x1400050b8`
- `0x140005110`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000514e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000514e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000540a`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000540a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400052cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400052f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005316`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005339`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005360`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400052cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400052f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005316`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005339`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005360`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000544b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000544b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000522c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000522c`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400052a0`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400053bf`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400052a0`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400053bf`

## string_xrefs

- `0x14000515c`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140005191`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x1400051c9`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x1400051fe`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x14000523a`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x1400052ae`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x1400053cd`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`
- `0x140005418`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`

## pseudocode

```c
__int64 InitializeCOMSecurity_ForBrokerProcess()
{
  HRESULT v0; // eax
  int v1; // eax
  int v2; // eax
  int v3; // eax
  const char *v4; // r9
  const char *v5; // r9
  HLOCAL v6; // rbx
  __int64 v7; // r8
  const char *v8; // r9
  ACL *v9; // rsi
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // r8
  const char *v13; // r9
  ACL *pSacl; // r14
  HLOCAL pOwner; // rdi
  __int64 v16; // r8
  const char *v17; // r9
  HLOCAL pPrimaryGroup; // rax
  __int64 v19; // r8
  const char *v20; // r9
  const char *v21; // r9
  HRESULT v22; // eax
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-9h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+64h] [rbp-5h] BYREF
  LPVOID v28; // [rsp+68h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+7h] BYREF
  HLOCAL v30; // [rsp+78h] [rbp+Fh] BYREF
  HLOCAL v31; // [rsp+80h] [rbp+17h] BYREF
  HLOCAL v32[7]; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD dwPrimaryGroupSize; // [rsp+D0h] [rbp+67h] BYREF
  DWORD dwOwnerSize; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = 0;
  v0 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v28);
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      308,
      (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  v1 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v28 + 24LL))(v28, 5, 1);
  if ( v1 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      309,
      (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v28 + 24LL))(v28, 4, 536);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      316,
      (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v28 + 24LL))(v28, 1, 2);
  if ( v3 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      317,
      (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(XA;;0x3;;;PS;(WIN://ISMULTISESSIONSKU))(A;;0x3;;;SY)(XA;;0x3;;;AU;(!(WIN://ISMULTISESSIONSKU)))(XA;"
           ";0x3;;;BG;(!(WIN://ISMULTISESSIONSKU)))(A;;0x3;;;S-1-15-2-3624051433-2125758914-1423191267-1740899205-1073925"
           "389-3782572162-737981194)(A;;0x3;;;S-1-15-3-1024-3623855041-1826999956-3747069818-3525260223-3747374510-17462"
           "72624-950601168-56556331)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x146,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      v4);
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  if ( MakeAbsoluteSD(
         SecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x154,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      v5);
  }
  v6 = LocalAlloc(0x40u, dwAbsoluteSecurityDescriptorSize);
  v32[0] = v6;
  if ( !v6 )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, 344, v7, v8);
  v9 = (ACL *)LocalAlloc(0x40u, dwDaclSize);
  if ( !v9 )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, 347, v10, v11);
  pSacl = (ACL *)LocalAlloc(0x40u, dwSaclSize);
  if ( !pSacl )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, 349, v12, v13);
  pOwner = LocalAlloc(0x40u, dwOwnerSize);
  v31 = pOwner;
  if ( !pOwner )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, 351, v16, v17);
  pPrimaryGroup = LocalAlloc(0x40u, dwPrimaryGroupSize);
  v30 = pPrimaryGroup;
  if ( !pPrimaryGroup )
    wil::details::in1diag3::_FailFast_NullAlloc(retaddr, 353, v19, v20);
  if ( !MakeAbsoluteSD(
          SecurityDescriptor,
          v6,
          &dwAbsoluteSecurityDescriptorSize,
          v9,
          &dwDaclSize,
          pSacl,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x169,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      v21);
  v22 = CoInitializeSecurity(v6, -1, 0, 0, 2u, 3u, 0, 0, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      363,
      (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
      (const char *)(unsigned int)v22,
      ppva);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
  LocalFree(pSacl);
  LocalFree(v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v32);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
  return ATL::CComPtr<IGlobalOptions>::~CComPtr<IGlobalOptions>((__int64 *)&v28);
}

```

## disassembly

```asm
0x140005110  push    rbp
0x140005112  push    rbx
0x140005113  push    rsi
0x140005114  push    rdi
0x140005115  push    r12
0x140005117  push    r14
0x140005119  push    r15
0x14000511b  lea     rbp, [rsp-27h]
0x140005120  sub     rsp, 90h
0x140005127  xor     r15d, r15d
0x14000512a  lea     rax, [rbp+57h+var_58]
0x14000512e  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140005135  mov     [rbp+57h+var_58], r15
0x140005139  xor     edx, edx; pUnkOuter
0x14000513b  mov     [rsp+0C0h+ppv], rax; int
0x140005140  lea     rcx, CLSID_GlobalOptions; rclsid
0x140005147  lea     ebx, [r15+1]
0x14000514b  mov     r8d, ebx; dwClsContext
0x14000514e  call    cs:__imp_CoCreateInstance
0x140005154  test    eax, eax
0x140005156  jns     short loc_140005171
0x140005158  mov     rcx, [rbp+5Fh]; this
0x14000515c  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005163  mov     r9d, eax; char *
0x140005166  mov     edx, 134h; void *
0x14000516b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x140005171  mov     rcx, [rbp+57h+var_58]
0x140005175  mov     r8, rbx
0x140005178  mov     edx, 5
0x14000517d  mov     rax, [rcx]
0x140005180  mov     rax, [rax+18h]
0x140005184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005189  test    eax, eax
0x14000518b  jns     short loc_1400051A6
0x14000518d  mov     rcx, [rbp+5Fh]; this
0x140005191  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005198  mov     r9d, eax; char *
0x14000519b  mov     edx, 135h; void *
0x1400051a0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400051a6  mov     rcx, [rbp+57h+var_58]
0x1400051aa  mov     edx, 4
0x1400051af  mov     r8d, 218h
0x1400051b5  mov     rax, [rcx]
0x1400051b8  mov     rax, [rax+18h]
0x1400051bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051c1  test    eax, eax
0x1400051c3  jns     short loc_1400051DE
0x1400051c5  mov     rcx, [rbp+5Fh]; this
0x1400051c9  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400051d0  mov     r9d, eax; char *
0x1400051d3  mov     edx, 13Ch; void *
0x1400051d8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1400051de  mov     rcx, [rbp+57h+var_58]
0x1400051e2  mov     r8d, 2
0x1400051e8  mov     edx, ebx
0x1400051ea  mov     rax, [rcx]
0x1400051ed  mov     rax, [rax+18h]
0x1400051f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051f6  test    eax, eax
0x1400051f8  jns     short loc_140005213
0x1400051fa  mov     rcx, [rbp+5Fh]; this
0x1400051fe  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005205  mov     r9d, eax; char *
0x140005208  mov     edx, 13Dh; void *
0x14000520d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x140005213  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x140005217  mov     [rbp+57h+SecurityDescriptorSize], r15d
0x14000521b  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000521f  mov     [rbp+57h+SecurityDescriptor], r15
0x140005223  mov     edx, ebx; StringSDRevision
0x140005225  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(XA;;0x3;;;PS;(WIN://ISMULTIS"...
0x14000522c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140005232  test    eax, eax
0x140005234  jnz     short loc_14000524C
0x140005236  mov     rcx, [rbp+5Fh]; this
0x14000523a  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x140005241  mov     edx, 146h; void *
0x140005246  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000524c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140005250  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140005254  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140005259  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14000525d  mov     [rsp+0C0h+pPrimaryGroup], r15; pPrimaryGroup
0x140005262  lea     rax, [rbp+57h+dwOwnerSize]
0x140005266  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x14000526b  xor     r9d, r9d; pDacl
0x14000526e  mov     [rsp+0C0h+pOwner], r15; pOwner
0x140005273  lea     rax, [rbp+57h+dwSaclSize]
0x140005277  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x14000527c  xor     edx, edx; pAbsoluteSecurityDescriptor
0x14000527e  lea     rax, [rbp+57h+dwDaclSize]
0x140005282  mov     [rsp+0C0h+pSacl], r15; pSacl
0x140005287  mov     [rsp+0C0h+ppv], rax; lpdwDaclSize
0x14000528c  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r15d
0x140005290  mov     [rbp+57h+dwDaclSize], r15d
0x140005294  mov     [rbp+57h+dwSaclSize], r15d
0x140005298  mov     [rbp+57h+dwOwnerSize], r15d
0x14000529c  mov     [rbp+57h+dwPrimaryGroupSize], r15d
0x1400052a0  call    cs:__imp_MakeAbsoluteSD
0x1400052a6  test    eax, eax
0x1400052a8  jz      short loc_1400052C0
0x1400052aa  mov     rcx, [rbp+5Fh]; this
0x1400052ae  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400052b5  mov     edx, 154h; void *
0x1400052ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400052c0  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x1400052c3  mov     r12d, 40h ; '@'
0x1400052c9  mov     ecx, r12d; uFlags
0x1400052cc  call    cs:__imp_LocalAlloc
0x1400052d2  mov     rcx, [rbp+5Fh]; this
0x1400052d6  mov     rbx, rax
0x1400052d9  mov     [rbp+57h+var_38], rax
0x1400052dd  test    rax, rax
0x1400052e0  jnz     short loc_1400052ED
0x1400052e2  mov     edx, 158h; void *
0x1400052e7  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1400052ed  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x1400052f0  mov     ecx, r12d; uFlags
0x1400052f3  call    cs:__imp_LocalAlloc
0x1400052f9  mov     rcx, [rbp+5Fh]; this
0x1400052fd  mov     rsi, rax
0x140005300  test    rax, rax
0x140005303  jnz     short loc_140005310
0x140005305  mov     edx, 15Bh; void *
0x14000530a  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x140005310  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x140005313  mov     ecx, r12d; uFlags
0x140005316  call    cs:__imp_LocalAlloc
0x14000531c  mov     rcx, [rbp+5Fh]; this
0x140005320  mov     r14, rax
0x140005323  test    rax, rax
0x140005326  jnz     short loc_140005333
0x140005328  mov     edx, 15Dh; void *
0x14000532d  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x140005333  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x140005336  mov     ecx, r12d; uFlags
0x140005339  call    cs:__imp_LocalAlloc
0x14000533f  mov     rcx, [rbp+5Fh]; this
0x140005343  mov     rdi, rax
0x140005346  mov     [rbp+57h+var_40], rax
0x14000534a  test    rax, rax
0x14000534d  jnz     short loc_14000535A
0x14000534f  mov     edx, 15Fh; void *
0x140005354  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x14000535a  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x14000535d  mov     ecx, r12d; uFlags
0x140005360  call    cs:__imp_LocalAlloc
0x140005366  mov     rcx, [rbp+5Fh]; this
0x14000536a  mov     [rbp+57h+var_48], rax
0x14000536e  test    rax, rax
0x140005371  jnz     short loc_14000537E
0x140005373  mov     edx, 161h; void *
0x140005378  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x14000537e  lea     rcx, [rbp+57h+dwPrimaryGroupSize]
0x140005382  mov     r9, rsi; pDacl
0x140005385  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rcx; lpdwPrimaryGroupSize
0x14000538a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14000538e  mov     rcx, [rbp+57h+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x140005392  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x140005395  mov     [rsp+0C0h+pPrimaryGroup], rax; pPrimaryGroup
0x14000539a  lea     rax, [rbp+57h+dwOwnerSize]
0x14000539e  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1400053a3  lea     rax, [rbp+57h+dwSaclSize]
0x1400053a7  mov     [rsp+0C0h+pOwner], rdi; pOwner
0x1400053ac  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x1400053b1  lea     rax, [rbp+57h+dwDaclSize]
0x1400053b5  mov     [rsp+0C0h+pSacl], r14; pSacl
0x1400053ba  mov     [rsp+0C0h+ppv], rax; lpdwDaclSize
0x1400053bf  call    cs:__imp_MakeAbsoluteSD
0x1400053c5  test    eax, eax
0x1400053c7  jnz     short loc_1400053DF
0x1400053c9  mov     rcx, [rbp+5Fh]; this
0x1400053cd  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400053d4  mov     edx, 169h; void *
0x1400053d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400053df  mov     [rsp+0C0h+lpdwOwnerSize], r15; pReserved3
0x1400053e4  xor     r9d, r9d; pReserved1
0x1400053e7  mov     dword ptr [rsp+0C0h+pOwner], r15d; dwCapabilities
0x1400053ec  xor     r8d, r8d; asAuthSvc
0x1400053ef  mov     [rsp+0C0h+lpdwSaclSize], r15; pAuthList
0x1400053f4  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400053f7  mov     dword ptr [rsp+0C0h+pSacl], 3; dwImpLevel
0x1400053ff  mov     rcx, rbx; pSecDesc
0x140005402  mov     dword ptr [rsp+0C0h+ppv], 2; int
0x14000540a  call    cs:__imp_CoInitializeSecurity
0x140005410  test    eax, eax
0x140005412  jns     short loc_14000542D
0x140005414  mov     rcx, [rbp+5Fh]; this
0x140005418  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x14000541f  mov     r9d, eax; char *
0x140005422  mov     edx, 16Bh; void *
0x140005427  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x14000542d  lea     rcx, [rbp+57h+var_48]
0x140005431  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140005436  lea     rcx, [rbp+57h+var_40]
0x14000543a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000543f  mov     rcx, r14; hMem
0x140005442  call    cs:__imp_LocalFree
0x140005448  mov     rcx, rsi; hMem
0x14000544b  call    cs:__imp_LocalFree
0x140005451  lea     rcx, [rbp+57h+var_38]
0x140005455  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000545a  lea     rcx, [rbp+57h+SecurityDescriptor]
0x14000545e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140005463  lea     rcx, [rbp+57h+var_58]
0x140005467  call    ??1?$CComPtr@UIGlobalOptions@@@ATL@@QEAA@XZ; ATL::CComPtr<IGlobalOptions>::~CComPtr<IGlobalOptions>(void)
0x14000546c  add     rsp, 90h
0x140005473  pop     r15
0x140005475  pop     r14
0x140005477  pop     r12
0x140005479  pop     rdi
0x14000547a  pop     rsi
0x14000547b  pop     rbx
0x14000547c  pop     rbp
0x14000547d  retn
```
