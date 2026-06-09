# MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable(ushort const *,int &)

- ea: `0x180061eb8`
- end: `0x1800622b9`
- name: `?IsPackageApplicable@PackageSource@Library@Provisioning@MsixPackage@@AEAAJPEBGAEAH@Z`
- size: `1025`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::PackageSource *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005aaac`
- `0x18005b444`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x18003e278`
- `0x180043fb4`
- `0x180061eb8`
- `0x180070010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180062005`
- `msvcrt!_wcsicmp` at `0x180062005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006201e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006207e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006213f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062199`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006201e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006207e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006213f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062199`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061fd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061fd0`

## string_xrefs

- `0x180062245`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x180062103`: `MsixPackage::Provisioning::Library::PackageSource::IsPackageApplicable`

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
          &pv,
          L"Package '%s' excluded as not applicable.",
          String2);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
      (const char *)(unsigned int)v16,
      v20);
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
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagesource.cpp",
      (const char *)(unsigned int)v18,
      2);
  if ( v17 )
    CoTaskMemFree(v17);
  return 0;
}

```

## disassembly

```asm
0x180061eb8  mov     [rsp-38h+arg_10], rbx
0x180061ebd  mov     [rsp-38h+String2], rdx
0x180061ec2  push    rbp
0x180061ec3  push    rsi
0x180061ec4  push    rdi
0x180061ec5  push    r12
0x180061ec7  push    r13
0x180061ec9  push    r14
0x180061ecb  push    r15
0x180061ecd  mov     rbp, rsp
0x180061ed0  sub     rsp, 40h
0x180061ed4  mov     rsi, r8
0x180061ed7  mov     r13, rcx
0x180061eda  xor     r15d, r15d
0x180061edd  cmp     [rcx+70h], r15
0x180061ee1  jnz     short loc_180061EEF
0x180061ee3  mov     dword ptr [r8], 1
0x180061eea  jmp     loc_18006214B
0x180061eef  mov     [r8], r15d
0x180061ef2  mov     rcx, [rcx+70h]
0x180061ef6  mov     rax, [rcx+18h]
0x180061efa  sub     rax, [rcx+10h]
0x180061efe  sar     rax, 3
0x180061f02  test    eax, eax
0x180061f04  jz      loc_1800620BA
0x180061f0a  mov     r14d, r15d
0x180061f0d  mov     [rbp+arg_18], r15
0x180061f11  mov     [rbp+pv], r15
0x180061f15  mov     [rbp+var_10], r15
0x180061f19  mov     edi, r14d
0x180061f1c  cmp     rdi, [rcx+28h]
0x180061f20  jnb     loc_180062239
0x180061f26  mov     rdx, [rcx+10h]
0x180061f2a  mov     rax, [rcx+18h]
0x180061f2e  sub     rax, rdx
0x180061f31  sar     rax, 3
0x180061f35  cmp     rax, rdi
0x180061f38  jbe     loc_1800622B3
0x180061f3e  lfence
0x180061f41  mov     rdi, [rdx+rdi*8]
0x180061f45  test    rdi, rdi
0x180061f48  jz      short loc_180061F5A
0x180061f4a  mov     rax, [rdi]
0x180061f4d  mov     rcx, rdi
0x180061f50  mov     rax, [rax+8]
0x180061f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f59  nop
0x180061f5a  mov     [rbp+var_10], rdi
0x180061f5e  mov     rax, [rdi]
0x180061f61  mov     rbx, [rax+20h]
0x180061f65  mov     rcx, [rbp+arg_18]
0x180061f69  mov     [rbp+arg_18], r15
0x180061f6d  test    rcx, rcx
0x180061f70  jz      short loc_180061F7F
0x180061f72  mov     rdx, [rcx]
0x180061f75  mov     rax, [rdx+10h]
0x180061f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f7e  nop
0x180061f7f  lea     rdx, [rbp+arg_18]
0x180061f83  mov     rcx, rdi
0x180061f86  mov     rax, rbx
0x180061f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f8e  mov     ebx, eax
0x180061f90  test    eax, eax
0x180061f92  js      loc_1800621D1
0x180061f98  mov     r12, [rbp+arg_18]
0x180061f9c  mov     rax, [r12]
0x180061fa0  mov     rax, [rax+48h]
0x180061fa4  mov     [rbp+var_8], rax
0x180061fa8  mov     r15, [rbp+pv]
0x180061fac  test    r15, r15
0x180061faf  jz      short loc_180061FE0
0x180061fb1  call    cs:__imp_GetLastError
0x180061fb8  nop     dword ptr [rax+rax+00h]
0x180061fbd  mov     ebx, eax
0x180061fbf  mov     rcx, r15; pv
0x180061fc2  call    cs:__imp_CoTaskMemFree
0x180061fc9  nop     dword ptr [rax+rax+00h]
0x180061fce  mov     ecx, ebx; dwErrCode
0x180061fd0  call    cs:__imp_SetLastError
0x180061fd7  nop     dword ptr [rax+rax+00h]
0x180061fdc  mov     rax, [rbp+var_8]
0x180061fe0  xor     r15d, r15d
0x180061fe3  mov     [rbp+pv], r15
0x180061fe7  lea     rdx, [rbp+pv]
0x180061feb  mov     rcx, r12
0x180061fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ff3  mov     ebx, eax
0x180061ff5  test    eax, eax
0x180061ff7  js      loc_180062166
0x180061ffd  mov     rdx, [rbp+String2]; String2
0x180062001  mov     rcx, [rbp+pv]; String1
0x180062005  call    cs:__imp__wcsicmp
0x18006200c  nop     dword ptr [rax+rax+00h]
0x180062011  test    eax, eax
0x180062013  jz      short loc_18006206F
0x180062015  mov     rcx, [rbp+pv]; pv
0x180062019  test    rcx, rcx
0x18006201c  jz      short loc_18006202B
0x18006201e  call    cs:__imp_CoTaskMemFree
0x180062025  nop     dword ptr [rax+rax+00h]
0x18006202a  nop
0x18006202b  mov     rcx, [rbp+arg_18]
0x18006202f  test    rcx, rcx
0x180062032  jz      short loc_180062041
0x180062034  mov     rax, [rcx]
0x180062037  mov     rax, [rax+10h]
0x18006203b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062040  nop
0x180062041  mov     rax, [rdi]
0x180062044  mov     rcx, rdi
0x180062047  mov     rax, [rax+10h]
0x18006204b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062050  nop
0x180062051  inc     r14d
0x180062054  mov     rcx, [r13+70h]
0x180062058  mov     rax, [rcx+18h]
0x18006205c  sub     rax, [rcx+10h]
0x180062060  sar     rax, 3
0x180062064  cmp     r14d, eax
0x180062067  jb      loc_180061F0D
0x18006206d  jmp     short loc_1800620B1
0x18006206f  mov     dword ptr [rsi], 1
0x180062075  mov     rcx, [rbp+pv]; pv
0x180062079  test    rcx, rcx
0x18006207c  jz      short loc_18006208B
0x18006207e  call    cs:__imp_CoTaskMemFree
0x180062085  nop     dword ptr [rax+rax+00h]
0x18006208a  nop
0x18006208b  mov     rcx, [rbp+arg_18]
0x18006208f  test    rcx, rcx
0x180062092  jz      short loc_1800620A1
0x180062094  mov     rax, [rcx]
0x180062097  mov     rax, [rax+10h]
0x18006209b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620a0  nop
0x1800620a1  mov     rax, [rdi]
0x1800620a4  mov     rcx, rdi
0x1800620a7  mov     rax, [rax+10h]
0x1800620ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620b0  nop
0x1800620b1  cmp     [rsi], r15d
0x1800620b4  jnz     loc_18006214B
0x1800620ba  mov     [rbp+pv], r15
0x1800620be  mov     r8, [rbp+String2]
0x1800620c2  lea     rdx, aPackageSExclud; "Package '%s' excluded as not applicable"...
0x1800620c9  lea     rcx, [rbp+pv]
0x1800620cd  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800620d2  mov     rcx, [rbp+38h]; this
0x1800620d6  test    eax, eax
0x1800620d8  jns     short loc_1800620EE
0x1800620da  mov     r9d, eax; char *
0x1800620dd  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800620e4  mov     edx, 2D6h; void *
0x1800620e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800620ee  mov     dword ptr [rsp+40h+var_18], r15d
0x1800620f3  mov     [rsp+40h+var_20], 2; int
0x1800620fb  mov     edi, 2DEh
0x180062100  mov     r9d, edi
0x180062103  lea     r8, aMsixpackagePro_10; "MsixPackage::Provisioning::Library::Pac"...
0x18006210a  lea     rdx, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180062111  mov     rbx, [rbp+pv]
0x180062115  mov     rcx, rbx
0x180062118  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18006211d  mov     rcx, [rbp+38h]; this
0x180062121  test    eax, eax
0x180062123  jns     short loc_180062137
0x180062125  mov     r9d, eax; char *
0x180062128  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18006212f  mov     edx, edi; void *
0x180062131  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062136  nop
0x180062137  test    rbx, rbx
0x18006213a  jz      short loc_18006214B
0x18006213c  mov     rcx, rbx; pv
0x18006213f  call    cs:__imp_CoTaskMemFree
0x180062146  nop     dword ptr [rax+rax+00h]
0x18006214b  xor     eax, eax
0x18006214d  mov     rbx, [rsp+40h+arg_10]
0x180062155  add     rsp, 40h
0x180062159  pop     r15
0x18006215b  pop     r14
0x18006215d  pop     r13
0x18006215f  pop     r12
0x180062161  pop     rdi
0x180062162  pop     rsi
0x180062163  pop     rbp
0x180062164  retn
0x180062166  mov     rcx, [rbp+38h]; this
0x18006216a  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x18006216f  lea     rax, aFailedToGetPac; "Failed to get package full name at inde"...
0x180062176  mov     qword ptr [rsp+40h+var_20], rax; int
0x18006217b  mov     r9d, ebx; char *
0x18006217e  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180062185  mov     edx, 2C4h; void *
0x18006218a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006218f  nop
0x180062190  mov     rcx, [rbp+pv]; pv
0x180062194  test    rcx, rcx
0x180062197  jz      short loc_1800621A6
0x180062199  call    cs:__imp_CoTaskMemFree
0x1800621a0  nop     dword ptr [rax+rax+00h]
0x1800621a5  nop
0x1800621a6  mov     rcx, [rbp+arg_18]
0x1800621aa  test    rcx, rcx
0x1800621ad  jz      short loc_1800621BC
0x1800621af  mov     rax, [rcx]
0x1800621b2  mov     rax, [rax+10h]
0x1800621b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621bb  nop
0x1800621bc  mov     rax, [rdi]
0x1800621bf  mov     rcx, rdi
0x1800621c2  mov     rax, [rax+10h]
0x1800621c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621cb  nop
0x1800621cc  jmp     loc_1800622AC
0x1800621d1  mov     rcx, [rbp+38h]; this
0x1800621d5  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x1800621da  lea     rax, aFailedToGetPac_7; "Failed to get package id at index %d."
0x1800621e1  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800621e6  mov     r9d, ebx; char *
0x1800621e9  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800621f0  mov     edx, 2BFh; void *
0x1800621f5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800621fa  nop
0x1800621fb  mov     rcx, [rbp+pv]; pv
0x1800621ff  test    rcx, rcx
0x180062202  jz      short loc_180062211
0x180062204  call    cs:__imp_CoTaskMemFree
0x18006220b  nop     dword ptr [rax+rax+00h]
0x180062210  nop
0x180062211  mov     rcx, [rbp+arg_18]
0x180062215  test    rcx, rcx
0x180062218  jz      short loc_180062227
0x18006221a  mov     rax, [rcx]
0x18006221d  mov     rax, [rax+10h]
0x180062221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062226  nop
0x180062227  mov     rax, [rdi]
0x18006222a  mov     rcx, rdi
0x18006222d  mov     rax, [rax+10h]
0x180062231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062236  nop
0x180062237  jmp     short loc_1800622AC
0x180062239  mov     rcx, [rbp+38h]; this
0x18006223d  mov     ebx, 80070057h
0x180062242  mov     r9d, ebx; char *
0x180062245  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18006224c  mov     edx, 1C7h; void *
0x180062251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062256  mov     rcx, [rbp+38h]; this
0x18006225a  mov     dword ptr [rsp+40h+var_18], r14d; char *
0x18006225f  lea     rax, aFailedToGetBun_1; "Failed to get bundled package info at i"...
0x180062266  mov     qword ptr [rsp+40h+var_20], rax; int
0x18006226b  mov     r9d, ebx; char *
0x18006226e  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180062275  mov     edx, 2BAh; void *
0x18006227a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006227f  nop
0x180062280  mov     rcx, [rbp+pv]; pv
0x180062284  test    rcx, rcx
0x180062287  jz      short loc_180062296
0x180062289  call    cs:__imp_CoTaskMemFree
0x180062290  nop     dword ptr [rax+rax+00h]
0x180062295  nop
0x180062296  mov     rcx, [rbp+arg_18]
0x18006229a  test    rcx, rcx
0x18006229d  jz      short loc_1800622AC
0x18006229f  mov     rdx, [rcx]
0x1800622a2  mov     rax, [rdx+10h]
0x1800622a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622ab  nop
0x1800622ac  mov     eax, ebx
0x1800622ae  jmp     loc_18006214D
0x1800622b3  call    ?_Xran@?$vector@V?$com_ptr_t@UIAppxFile@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIAppxFile@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@IEBAXXZ; std::vector<wil::com_ptr_t<IAppxFile,wil::err_returncode_policy>>::_Xran(void)
```
