# MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable(ushort const *,int &)

- ea: `0x18005d2a8`
- end: `0x18005d66c`
- name: `?IsPackageApplicable@PackageSource@Library@Provisioning@MsixPackage@@AEAAJPEBGAEAH@Z`
- size: `964`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::PackageSource *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005647c`
- `0x180056d60`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003aba8`
- `0x180040400`
- `0x18005d2a8`
- `0x18006a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18005d3e3`
- `msvcrt!_wcsicmp` at `0x18005d3e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d3ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d3ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d3b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d3b4`

## string_xrefs

- `0x18005d5fe`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18005d4cf`: `MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable(
        MsixPackage::Provisioning::Library::PackageSource *this,
        wchar_t *a2,
        int *a3)
{
  _QWORD *v5; // rcx
  unsigned int v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rcx
  int v11; // ebx
  __int64 v12; // r12
  __int64 (__fastcall *v13)(_QWORD, _QWORD); // rax
  void *v14; // r15
  DWORD LastError; // ebx
  int v16; // eax
  void *v17; // rbx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-20h]
  char *v21; // [rsp+28h] [rbp-18h]
  __int64 (__fastcall *v22)(_QWORD, _QWORD); // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp+48h]
  __int64 v26; // [rsp+98h] [rbp+58h] BYREF

  String2 = a2;
  if ( !*((_QWORD *)this + 14) )
  {
    *a3 = 1;
    return 0;
  }
  *a3 = 0;
  v5 = (_QWORD *)*((_QWORD *)this + 14);
  if ( !(unsigned int)((__int64)(v5[3] - v5[2]) >> 3) )
    goto LABEL_28;
  v6 = 0;
  while ( 1 )
  {
    v26 = 0;
    pv = 0;
    if ( (unsigned __int64)v6 >= v5[5] )
    {
      v11 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
        (const char *)0x80070057LL,
        v20);
      LODWORD(v21) = v6;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2BA,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
        (const char *)0x80070057LL,
        (int)"Failed to get bundled package info at index %d.",
        v21,
        0);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      return (unsigned int)v11;
    }
    v7 = v5[2];
    if ( (v5[3] - v7) >> 3 <= (unsigned __int64)v6 )
      std::vector<wil::com_ptr_t<IAppxFile,wil::err_returncode_policy>>::_Xran();
    _mm_lfence();
    v8 = *(_QWORD *)(v7 + 8LL * v6);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 32LL);
    v10 = v26;
    v26 = 0;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v11 = v9(v8, &v26);
    if ( v11 < 0 )
    {
      LODWORD(v21) = v6;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2BF,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
        (const char *)(unsigned int)v11,
        (int)"Failed to get package id at index %d.",
        v21,
        v8);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_39:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)v11;
    }
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v26 + 72LL);
    v22 = v13;
    v14 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v14);
      SetLastError(LastError);
      v13 = v22;
    }
    pv = 0;
    v11 = v13(v12, &pv);
    if ( v11 < 0 )
    {
      LODWORD(v21) = v6;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2C4,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
        (const char *)(unsigned int)v11,
        (int)"Failed to get package full name at index %d.",
        v21,
        v8);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      goto LABEL_39;
    }
    if ( !_wcsicmp((const wchar_t *)pv, String2) )
      break;
    if ( pv )
      CoTaskMemFree(pv);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    ++v6;
    v5 = (_QWORD *)*((_QWORD *)this + 14);
    if ( v6 >= (unsigned int)((__int64)(v5[3] - v5[2]) >> 3) )
      goto LABEL_27;
  }
  *a3 = 1;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_27:
  if ( *a3 )
    return 0;
LABEL_28:
  pv = 0;
  v16 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (char *)&pv,
          L"Package '%s' excluded as not applicable.",
          String2);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D6,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
      (const char *)(unsigned int)v16);
  v17 = pv;
  v18 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
          pv,
          L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
          L"MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable",
          734);
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DE,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
      (const char *)(unsigned int)v18);
  if ( v17 )
    CoTaskMemFree(v17);
  return 0;
}

```

## disassembly

```asm
0x18005d2a8  mov     [rsp-38h+arg_10], rbx
0x18005d2ad  mov     [rsp-38h+String2], rdx
0x18005d2b2  push    rbp
0x18005d2b3  push    rsi
0x18005d2b4  push    rdi
0x18005d2b5  push    r12
0x18005d2b7  push    r13
0x18005d2b9  push    r14
0x18005d2bb  push    r15
0x18005d2bd  mov     rbp, rsp
0x18005d2c0  sub     rsp, 40h
0x18005d2c4  mov     rsi, r8
0x18005d2c7  mov     r13, rcx
0x18005d2ca  xor     r15d, r15d
0x18005d2cd  cmp     [rcx+70h], r15
0x18005d2d1  jnz     short loc_18005D2DF
0x18005d2d3  mov     dword ptr [r8], 1
0x18005d2da  jmp     loc_18005D511
0x18005d2df  mov     [r8], r15d
0x18005d2e2  mov     rcx, [rcx+70h]
0x18005d2e6  mov     rax, [rcx+18h]
0x18005d2ea  sub     rax, [rcx+10h]
0x18005d2ee  sar     rax, 3
0x18005d2f2  test    eax, eax
0x18005d2f4  jz      loc_18005D486
0x18005d2fa  mov     r14d, r15d
0x18005d2fd  mov     [rbp+arg_18], r15
0x18005d301  mov     [rbp+pv], r15
0x18005d305  mov     [rbp+var_10], r15
0x18005d309  mov     edi, r14d
0x18005d30c  cmp     rdi, [rcx+28h]
0x18005d310  jnb     loc_18005D5F2
0x18005d316  mov     rdx, [rcx+10h]
0x18005d31a  mov     rax, [rcx+18h]
0x18005d31e  sub     rax, rdx
0x18005d321  sar     rax, 3
0x18005d325  cmp     rax, rdi
0x18005d328  jbe     loc_18005D666
0x18005d32e  lfence
0x18005d331  mov     rdi, [rdx+rdi*8]
0x18005d335  test    rdi, rdi
0x18005d338  jz      short loc_18005D34A
0x18005d33a  mov     rax, [rdi]
0x18005d33d  mov     rcx, rdi
0x18005d340  mov     rax, [rax+8]
0x18005d344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d349  nop
0x18005d34a  mov     [rbp+var_10], rdi
0x18005d34e  mov     rax, [rdi]
0x18005d351  mov     rbx, [rax+20h]
0x18005d355  mov     rcx, [rbp+arg_18]
0x18005d359  mov     [rbp+arg_18], r15
0x18005d35d  test    rcx, rcx
0x18005d360  jz      short loc_18005D36F
0x18005d362  mov     rdx, [rcx]
0x18005d365  mov     rax, [rdx+10h]
0x18005d369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d36e  nop
0x18005d36f  lea     rdx, [rbp+arg_18]
0x18005d373  mov     rcx, rdi
0x18005d376  mov     rax, rbx
0x18005d379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d37e  mov     ebx, eax
0x18005d380  test    eax, eax
0x18005d382  js      loc_18005D590
0x18005d388  mov     r12, [rbp+arg_18]
0x18005d38c  mov     rax, [r12]
0x18005d390  mov     rax, [rax+48h]
0x18005d394  mov     [rbp+var_8], rax
0x18005d398  mov     r15, [rbp+pv]
0x18005d39c  test    r15, r15
0x18005d39f  jz      short loc_18005D3BE
0x18005d3a1  call    cs:__imp_GetLastError
0x18005d3a7  mov     ebx, eax
0x18005d3a9  mov     rcx, r15; pv
0x18005d3ac  call    cs:__imp_CoTaskMemFree
0x18005d3b2  mov     ecx, ebx; dwErrCode
0x18005d3b4  call    cs:__imp_SetLastError
0x18005d3ba  mov     rax, [rbp+var_8]
0x18005d3be  xor     r15d, r15d
0x18005d3c1  mov     [rbp+pv], r15
0x18005d3c5  lea     rdx, [rbp+pv]
0x18005d3c9  mov     rcx, r12
0x18005d3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3d1  mov     ebx, eax
0x18005d3d3  test    eax, eax
0x18005d3d5  js      loc_18005D52B
0x18005d3db  mov     rdx, [rbp+String2]; String2
0x18005d3df  mov     rcx, [rbp+pv]; String1
0x18005d3e3  call    cs:__imp__wcsicmp
0x18005d3e9  test    eax, eax
0x18005d3eb  jz      short loc_18005D441
0x18005d3ed  mov     rcx, [rbp+pv]; pv
0x18005d3f1  test    rcx, rcx
0x18005d3f4  jz      short loc_18005D3FD
0x18005d3f6  call    cs:__imp_CoTaskMemFree
0x18005d3fc  nop
0x18005d3fd  mov     rcx, [rbp+arg_18]
0x18005d401  test    rcx, rcx
0x18005d404  jz      short loc_18005D413
0x18005d406  mov     rax, [rcx]
0x18005d409  mov     rax, [rax+10h]
0x18005d40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d412  nop
0x18005d413  mov     rax, [rdi]
0x18005d416  mov     rcx, rdi
0x18005d419  mov     rax, [rax+10h]
0x18005d41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d422  nop
0x18005d423  inc     r14d
0x18005d426  mov     rcx, [r13+70h]
0x18005d42a  mov     rax, [rcx+18h]
0x18005d42e  sub     rax, [rcx+10h]
0x18005d432  sar     rax, 3
0x18005d436  cmp     r14d, eax
0x18005d439  jb      loc_18005D2FD
0x18005d43f  jmp     short loc_18005D47D
0x18005d441  mov     dword ptr [rsi], 1
0x18005d447  mov     rcx, [rbp+pv]; pv
0x18005d44b  test    rcx, rcx
0x18005d44e  jz      short loc_18005D457
0x18005d450  call    cs:__imp_CoTaskMemFree
0x18005d456  nop
0x18005d457  mov     rcx, [rbp+arg_18]
0x18005d45b  test    rcx, rcx
0x18005d45e  jz      short loc_18005D46D
0x18005d460  mov     rax, [rcx]
0x18005d463  mov     rax, [rax+10h]
0x18005d467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d46c  nop
0x18005d46d  mov     rax, [rdi]
0x18005d470  mov     rcx, rdi
0x18005d473  mov     rax, [rax+10h]
0x18005d477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d47c  nop
0x18005d47d  cmp     [rsi], r15d
0x18005d480  jnz     loc_18005D511
0x18005d486  mov     [rbp+pv], r15
0x18005d48a  mov     r8, [rbp+String2]
0x18005d48e  lea     rdx, aPackageSExclud; "Package '%s' excluded as not applicable"...
0x18005d495  lea     rcx, [rbp+pv]
0x18005d499  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005d49e  mov     rcx, [rbp+38h]; this
0x18005d4a2  test    eax, eax
0x18005d4a4  jns     short loc_18005D4BA
0x18005d4a6  mov     r9d, eax; char *
0x18005d4a9  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d4b0  mov     edx, 2D6h; void *
0x18005d4b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d4ba  mov     dword ptr [rsp+40h+var_18], r15d
0x18005d4bf  mov     [rsp+40h+var_20], 2; int
0x18005d4c7  mov     edi, 2DEh
0x18005d4cc  mov     r9d, edi
0x18005d4cf  lea     r8, aMsixpackagePro_10; "MsixPackage::Provisioning::Library::Pac"...
0x18005d4d6  lea     rdx, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d4dd  mov     rbx, [rbp+pv]
0x18005d4e1  mov     rcx, rbx
0x18005d4e4  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18005d4e9  mov     rcx, [rbp+38h]; this
0x18005d4ed  test    eax, eax
0x18005d4ef  jns     short loc_18005D503
0x18005d4f1  mov     r9d, eax; char *
0x18005d4f4  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d4fb  mov     edx, edi; void *
0x18005d4fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d502  nop
0x18005d503  test    rbx, rbx
0x18005d506  jz      short loc_18005D511
0x18005d508  mov     rcx, rbx; pv
0x18005d50b  call    cs:__imp_CoTaskMemFree
0x18005d511  xor     eax, eax
0x18005d513  mov     rbx, [rsp+40h+arg_10]
0x18005d51b  add     rsp, 40h
0x18005d51f  pop     r15
0x18005d521  pop     r14
0x18005d523  pop     r13
0x18005d525  pop     r12
0x18005d527  pop     rdi
0x18005d528  pop     rsi
0x18005d529  pop     rbp
0x18005d52a  retn
0x18005d52b  mov     rcx, [rbp+38h]; this
0x18005d52f  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x18005d534  lea     rax, aFailedToGetPac; "Failed to get package full name at inde"...
0x18005d53b  mov     qword ptr [rsp+40h+var_20], rax; int
0x18005d540  mov     r9d, ebx; char *
0x18005d543  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d54a  mov     edx, 2C4h; void *
0x18005d54f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005d554  nop
0x18005d555  mov     rcx, [rbp+pv]; pv
0x18005d559  test    rcx, rcx
0x18005d55c  jz      short loc_18005D565
0x18005d55e  call    cs:__imp_CoTaskMemFree
0x18005d564  nop
0x18005d565  mov     rcx, [rbp+arg_18]
0x18005d569  test    rcx, rcx
0x18005d56c  jz      short loc_18005D57B
0x18005d56e  mov     rax, [rcx]
0x18005d571  mov     rax, [rax+10h]
0x18005d575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d57a  nop
0x18005d57b  mov     rax, [rdi]
0x18005d57e  mov     rcx, rdi
0x18005d581  mov     rax, [rax+10h]
0x18005d585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d58a  nop
0x18005d58b  jmp     loc_18005D65F
0x18005d590  mov     rcx, [rbp+38h]; this
0x18005d594  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x18005d599  lea     rax, aFailedToGetPac_7; "Failed to get package id at index %d."
0x18005d5a0  mov     qword ptr [rsp+40h+var_20], rax; int
0x18005d5a5  mov     r9d, ebx; char *
0x18005d5a8  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d5af  mov     edx, 2BFh; void *
0x18005d5b4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005d5b9  nop
0x18005d5ba  mov     rcx, [rbp+pv]; pv
0x18005d5be  test    rcx, rcx
0x18005d5c1  jz      short loc_18005D5CA
0x18005d5c3  call    cs:__imp_CoTaskMemFree
0x18005d5c9  nop
0x18005d5ca  mov     rcx, [rbp+arg_18]
0x18005d5ce  test    rcx, rcx
0x18005d5d1  jz      short loc_18005D5E0
0x18005d5d3  mov     rax, [rcx]
0x18005d5d6  mov     rax, [rax+10h]
0x18005d5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5df  nop
0x18005d5e0  mov     rax, [rdi]
0x18005d5e3  mov     rcx, rdi
0x18005d5e6  mov     rax, [rax+10h]
0x18005d5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5ef  nop
0x18005d5f0  jmp     short loc_18005D65F
0x18005d5f2  mov     rcx, [rbp+38h]; this
0x18005d5f6  mov     ebx, 80070057h
0x18005d5fb  mov     r9d, ebx; char *
0x18005d5fe  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d605  mov     edx, 1C7h; void *
0x18005d60a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d60f  mov     rcx, [rbp+38h]; this
0x18005d613  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x18005d618  lea     rax, aFailedToGetBun_1; "Failed to get bundled package info at i"...
0x18005d61f  mov     qword ptr [rsp+40h+var_20], rax; int
0x18005d624  mov     r9d, ebx; char *
0x18005d627  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005d62e  mov     edx, 2BAh; void *
0x18005d633  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005d638  nop
0x18005d639  mov     rcx, [rbp+pv]; pv
0x18005d63d  test    rcx, rcx
0x18005d640  jz      short loc_18005D649
0x18005d642  call    cs:__imp_CoTaskMemFree
0x18005d648  nop
0x18005d649  mov     rcx, [rbp+arg_18]
0x18005d64d  test    rcx, rcx
0x18005d650  jz      short loc_18005D65F
0x18005d652  mov     rdx, [rcx]
0x18005d655  mov     rax, [rdx+10h]
0x18005d659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d65e  nop
0x18005d65f  mov     eax, ebx
0x18005d661  jmp     loc_18005D513
0x18005d666  call    ?_Xran@?$vector@V?$com_ptr_t@UIAppxFile@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAppxFile@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@IEBAXXZ; std::vector<wil::com_ptr_t<IAppxFile,wil::err_returncode_policy>>::_Xran(void)
```
