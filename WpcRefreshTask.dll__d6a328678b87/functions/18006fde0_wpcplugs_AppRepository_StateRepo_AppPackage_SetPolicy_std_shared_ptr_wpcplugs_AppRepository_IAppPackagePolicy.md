# wpcplugs::AppRepository::StateRepo::AppPackage::SetPolicy(std::shared_ptr<wpcplugs::AppRepository::IAppPackagePolicy>)

- ea: `0x18006fde0`
- end: `0x18007044c`
- name: `?SetPolicy@AppPackage@StateRepo@AppRepository@wpcplugs@@UEAAXV?$shared_ptr@UIAppPackagePolicy@AppRepository@wpcplugs@@@std@@@Z`
- size: `1644`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060a0`
- `0x180007ec1`
- `0x1800093a0`
- `0x180009a80`
- `0x18001ccf0`
- `0x18002ca60`
- `0x18002eb3c`
- `0x18006b7f4`
- `0x18006e4f4`
- `0x18006fde0`
- `0x180070e70`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fe33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007005f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006fe33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007005f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006fe6d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006fe6d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18007009a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18007009a`

## string_xrefs

- `0x180070287`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180070374`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180070391`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x1800703b4`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x1800703c9`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x1800703e6`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x1800703fb`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180070410`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x180070425`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18007043a`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall wpcplugs::AppRepository::StateRepo::AppPackage::SetPolicy(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  char *v8; // rax
  __int64 v9; // rbx
  unsigned int (__fastcall *v10)(__int64, __int64, _QWORD, PVOID); // rdi
  __int64 v11; // rax
  unsigned int v12; // r8d
  HSTRING_HEADER *v13; // rax
  unsigned int v14; // ebx
  int v15; // edx
  PVOID Reserved1; // rbx
  __int64 (__fastcall *v17)(PVOID, _QWORD, __int64 *); // rdi
  __int64 v18; // rcx
  unsigned int v19; // ebx
  int v20; // r15d
  int v21; // eax
  PVOID v22; // rdi
  __int64 (__fastcall *v23)(PVOID, _QWORD, __int64 *); // r14
  __int64 v24; // rcx
  __int64 v25; // rcx
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  int v29; // ebx
  int v30; // eax
  int v31; // eax
  const WCHAR *v32; // rbx
  __int64 (__fastcall *v33)(const WCHAR *, PVOID); // rdi
  __int64 v34; // rax
  unsigned int v35; // r8d
  HSTRING_HEADER *v36; // rax
  int v37; // ebx
  const WCHAR *v38; // rdi
  __int64 (__fastcall *v39)(const WCHAR *, __int64); // rbx
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // ebx
  __int64 v45; // rax
  __int64 result; // rax
  const WCHAR *v47; // rcx
  PVOID v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  volatile signed __int32 *v51; // rbx
  signed __int32 v52; // eax
  bool v53; // zf
  unsigned int v54; // eax
  int v55; // [rsp+20h] [rbp-69h]
  const WCHAR *v56; // [rsp+30h] [rbp-59h] BYREF
  const WCHAR *v57; // [rsp+38h] [rbp-51h] BYREF
  __int64 v58; // [rsp+40h] [rbp-49h] BYREF
  __int64 v59; // [rsp+48h] [rbp-41h] BYREF
  int v60[2]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD *v61; // [rsp+58h] [rbp-31h]
  HSTRING_HEADER v62; // [rsp+60h] [rbp-29h] BYREF
  __int64 v63; // [rsp+78h] [rbp-11h] BYREF
  __int64 v64; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v61 = a2;
  v58 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackagePolicy", 0x2Eu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e, &v58);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v55);
  v8 = (char *)(*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*a2 + 8LL))(*a2, &hstringHeader);
  anonymous_namespace_::GetUserFromStateRepo(&v59, v8);
  std::wstring::~wstring((char **)&hstringHeader);
  if ( !v59 )
  {
    v54 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v54,
      v55);
  }
  *(_QWORD *)v60 = 0;
  v9 = v58;
  v10 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD, PVOID))(*(_QWORD *)v58 + 440LL);
  v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*a2 + 24LL))(*a2, &v62);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v11 = *(_QWORD *)v11;
  v57 = (const WCHAR *)v11;
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v57, v12);
  v14 = v10(v9, v59, *(_QWORD *)(a1 + 8), v13[1].Reserved.Reserved1) >> 31;
  string = 0;
  std::wstring::~wstring((char **)&v62);
  if ( (unsigned __int8)v14 != 1 )
  {
    v62.Reserved.Reserved1 = *(PVOID *)v60;
    *(_QWORD *)&v62.Reserved.Reserved2[16] = &v63;
    LODWORD(v63) = 0;
    v64 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)v60 + 56LL))(
            *(_QWORD *)v60,
            &v62.Reserved.Reserved2[8]);
    **(_DWORD **)&v62.Reserved.Reserved2[16] = v15;
    if ( v15 >= 0 && *(_DWORD *)&v62.Reserved.Reserved2[8] )
    {
      Reserved1 = v62.Reserved.Reserved1;
      v17 = *(__int64 (__fastcall **)(PVOID, _QWORD, __int64 *))(*(_QWORD *)v62.Reserved.Reserved1 + 48LL);
      v18 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v15 = v17(Reserved1, 0, &v64);
      **(_DWORD **)&v62.Reserved.Reserved2[16] = v15;
    }
    v19 = 0;
    v20 = *(_DWORD *)&v62.Reserved.Reserved2[8];
    while ( v15 >= 0 && v19 != v20 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 72LL))(v58, v64);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v21,
          (int)v60);
      ++v19;
      v15 = **(_DWORD **)&v62.Reserved.Reserved2[16];
      if ( (int)**(_DWORD **)&v62.Reserved.Reserved2[16] < 0 )
        break;
      if ( v19 < *(_DWORD *)&v62.Reserved.Reserved2[8] )
      {
        v22 = v62.Reserved.Reserved1;
        v23 = *(__int64 (__fastcall **)(PVOID, _QWORD, __int64 *))(*(_QWORD *)v62.Reserved.Reserved1 + 48LL);
        v24 = v64;
        if ( v64 )
        {
          v64 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v15 = v23(v22, v19, &v64);
        **(_DWORD **)&v62.Reserved.Reserved2[16] = v15;
      }
    }
    v25 = v64;
    if ( v64 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  v56 = 0;
  string = 0;
  v26 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackagePolicy", 0x2Eu, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
    __debugbreak();
  }
  v56 = 0;
  v57 = 0;
  v29 = RoActivateInstance(string, &v57);
  if ( v29 >= 0 )
  {
    if ( !memcmp_0(&GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v56 = v57;
    }
    else
    {
      v29 = (**(__int64 (__fastcall ***)(const WCHAR *, GUID *, const WCHAR **))v57)(
              v57,
              &GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04,
              &v56);
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v57 + 16LL))(v57);
    }
  }
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v29,
      (int)v60);
  v30 = (*(__int64 (__fastcall **)(const WCHAR *, __int64))(*(_QWORD *)v56 + 104LL))(v56, v59);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v30,
      (int)v60);
  v31 = (*(__int64 (__fastcall **)(const WCHAR *, _QWORD))(*(_QWORD *)v56 + 136LL))(v56, *(_QWORD *)(a1 + 8));
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v31,
      (int)v60);
  v32 = v56;
  v33 = *(__int64 (__fastcall **)(const WCHAR *, PVOID))(*(_QWORD *)v56 + 152LL);
  v34 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*a2 + 24LL))(*a2, &hstringHeader);
  if ( *(_QWORD *)(v34 + 24) > 7u )
    v34 = *(_QWORD *)v34;
  v57 = (const WCHAR *)v34;
  v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v62, &v57, v35);
  v37 = v33(v32, v36[1].Reserved.Reserved1);
  v63 = 0;
  std::wstring::~wstring((char **)&hstringHeader);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v37,
      (int)v60);
  v38 = v56;
  v39 = *(__int64 (__fastcall **)(const WCHAR *, __int64))(*(_QWORD *)v56 + 216LL);
  v40 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 40LL))(*a2);
  v41 = v39(v38, v40);
  if ( v41 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v41,
      (int)v60);
  v57 = v56;
  if ( v56 )
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v56 + 8LL))(v56);
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
  v42 = a2[1];
  if ( v42 )
    _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)a2;
  v43 = wpcplugs::AppRepository::StateRepo::Private::AddMetaDataToPolicy(&hstringHeader, &v57);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v43,
      (int)v60);
  v44 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v58 + 48LL))(v58, v56);
  v45 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*a2 + 24LL))(*a2, &v62);
  if ( *(_QWORD *)(v45 + 24) > 7u )
    v45 = *(_QWORD *)v45;
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x22C,
    (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
    (const char *)v44,
    (int)"%ls",
    (const char *)v45);
  result = std::wstring::~wstring((char **)&v62);
  v47 = v56;
  if ( v56 )
  {
    v56 = 0;
    result = (*(__int64 (__fastcall **)(const WCHAR *))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = *(PVOID *)v60;
  if ( *(_QWORD *)v60 )
  {
    *(_QWORD *)v60 = 0;
    result = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v59;
  if ( v59 )
  {
    v59 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v58;
  if ( v58 )
  {
    v58 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = (volatile signed __int32 *)a2[1];
  if ( v51 )
  {
    v52 = _InterlockedExchangeAdd(v51 + 2, 0xFFFFFFFF);
    v53 = v52 == 1;
    result = (unsigned int)(v52 - 1);
    if ( v53 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
      result = (unsigned int)_InterlockedDecrement(v51 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006fde0  mov     [rsp-8+arg_10], rbx
0x18006fde5  push    rbp
0x18006fde6  push    rsi
0x18006fde7  push    rdi
0x18006fde8  push    r12
0x18006fdea  push    r13
0x18006fdec  push    r14
0x18006fdee  push    r15
0x18006fdf0  lea     rbp, [rsp-27h]
0x18006fdf5  sub     rsp, 0B0h
0x18006fdfc  mov     rax, cs:__security_cookie
0x18006fe03  xor     rax, rsp
0x18006fe06  mov     [rbp+57h+var_38], rax
0x18006fe0a  mov     rsi, rdx
0x18006fe0d  mov     r13, rcx
0x18006fe10  mov     [rbp+57h+var_88], rdx
0x18006fe14  xor     r12d, r12d
0x18006fe17  mov     [rbp+57h+var_A0], r12
0x18006fe1b  mov     [rbp+57h+string], r12
0x18006fe1f  lea     r9, [rbp+57h+string]; string
0x18006fe23  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006fe27  lea     edx, [r12+2Eh]; length
0x18006fe2c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackagePolicy@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006fe33  call    cs:__imp_WindowsCreateStringReference
0x18006fe39  test    eax, eax
0x18006fe3b  js      loc_180070386
0x18006fe41  mov     rbx, [rbp+57h+string]
0x18006fe45  mov     rcx, [rbp+57h+var_A0]
0x18006fe49  test    rcx, rcx
0x18006fe4c  jz      short loc_18006FE5F
0x18006fe4e  mov     [rbp+57h+var_A0], r12
0x18006fe52  mov     rax, [rcx]
0x18006fe55  mov     rax, [rax+10h]
0x18006fe59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe5e  nop
0x18006fe5f  lea     r8, [rbp+57h+var_A0]
0x18006fe63  lea     rdx, _GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e
0x18006fe6a  mov     rcx, rbx
0x18006fe6d  call    cs:__imp_RoGetActivationFactory
0x18006fe73  mov     rcx, [rbp+5Fh]; this
0x18006fe77  test    eax, eax
0x18006fe79  js      loc_18007038E
0x18006fe7f  mov     rcx, [rsi]
0x18006fe82  mov     rax, [rcx]
0x18006fe85  lea     rdx, [rbp+57h+hstringHeader]
0x18006fe89  mov     rax, [rax+8]
0x18006fe8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe92  nop
0x18006fe93  mov     rdx, rax
0x18006fe96  lea     rcx, [rbp+57h+var_98]
0x18006fe9a  call    _anonymous_namespace___GetUserFromStateRepo
0x18006fe9f  nop
0x18006fea0  lea     rcx, [rbp+57h+hstringHeader]
0x18006fea4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006fea9  cmp     [rbp+57h+var_98], r12
0x18006fead  jz      loc_1800703A3
0x18006feb3  mov     qword ptr [rbp+57h+var_90], r12
0x18006feb7  mov     rbx, [rbp+57h+var_A0]
0x18006febb  mov     rax, [rbx]
0x18006febe  mov     rdi, [rax+1B8h]
0x18006fec5  mov     rcx, [rsi]
0x18006fec8  mov     rax, [rcx]
0x18006fecb  lea     rdx, [rbp+57h+var_80]
0x18006fecf  mov     rax, [rax+18h]
0x18006fed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fed8  nop
0x18006fed9  cmp     qword ptr [rax+18h], 7
0x18006fede  jbe     short loc_18006FEE3
0x18006fee0  mov     rax, [rax]
0x18006fee3  mov     [rbp+57h+var_A8], rax
0x18006fee7  lea     rdx, [rbp+57h+var_A8]
0x18006feeb  lea     rcx, [rbp+57h+hstringHeader]
0x18006feef  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006fef4  nop
0x18006fef5  lea     rcx, [rbp+57h+var_90]
0x18006fef9  mov     qword ptr [rsp+0E0h+var_C0], rcx; int
0x18006fefe  mov     r9, [rax+18h]
0x18006ff02  mov     r8, [r13+8]
0x18006ff06  mov     rdx, [rbp+57h+var_98]
0x18006ff0a  mov     rcx, rbx
0x18006ff0d  mov     rax, rdi
0x18006ff10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff15  mov     ebx, eax
0x18006ff17  shr     ebx, 1Fh
0x18006ff1a  mov     [rbp+57h+string], r12
0x18006ff1e  lea     rcx, [rbp+57h+var_80]
0x18006ff22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006ff27  xor     bl, 1
0x18006ff2a  jz      loc_180070043
0x18006ff30  mov     rcx, qword ptr [rbp+57h+var_90]
0x18006ff34  mov     [rbp+57h+var_80], rcx
0x18006ff38  lea     rax, [rbp+57h+var_68]
0x18006ff3c  mov     [rbp+57h+var_70], rax
0x18006ff40  mov     dword ptr [rbp+57h+var_68], r12d
0x18006ff44  mov     [rbp+57h+var_60], r12
0x18006ff48  mov     rax, [rcx]
0x18006ff4b  lea     rdx, [rbp+57h+var_78]
0x18006ff4f  mov     rax, [rax+38h]
0x18006ff53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff58  mov     edx, eax
0x18006ff5a  mov     rax, [rbp+57h+var_70]
0x18006ff5e  mov     [rax], edx
0x18006ff60  test    edx, edx
0x18006ff62  js      short loc_18006FFA8
0x18006ff64  cmp     [rbp+57h+var_78], r12d
0x18006ff68  jbe     short loc_18006FFA8
0x18006ff6a  mov     rbx, [rbp+57h+var_80]
0x18006ff6e  mov     rax, [rbx]
0x18006ff71  mov     rdi, [rax+30h]
0x18006ff75  mov     rcx, [rbp+57h+var_60]
0x18006ff79  test    rcx, rcx
0x18006ff7c  jz      short loc_18006FF8F
0x18006ff7e  mov     [rbp+57h+var_60], r12
0x18006ff82  mov     rdx, [rcx]
0x18006ff85  mov     rax, [rdx+10h]
0x18006ff89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff8e  nop
0x18006ff8f  lea     r8, [rbp+57h+var_60]
0x18006ff93  xor     edx, edx
0x18006ff95  mov     rcx, rbx
0x18006ff98  mov     rax, rdi
0x18006ff9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ffa0  mov     edx, eax
0x18006ffa2  mov     rcx, [rbp+57h+var_70]
0x18006ffa6  mov     [rcx], eax
0x18006ffa8  mov     ebx, r12d
0x18006ffab  mov     r15d, [rbp+57h+var_78]
0x18006ffaf  test    edx, edx
0x18006ffb1  js      short loc_180070029
0x18006ffb3  cmp     ebx, r15d
0x18006ffb6  jz      short loc_180070029
0x18006ffb8  mov     rcx, [rbp+57h+var_A0]
0x18006ffbc  mov     rax, [rcx]
0x18006ffbf  mov     rdx, [rbp+57h+var_60]
0x18006ffc3  mov     rax, [rax+48h]
0x18006ffc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ffcc  mov     rcx, [rbp+5Fh]; this
0x18006ffd0  test    eax, eax
0x18006ffd2  js      loc_1800703C6
0x18006ffd8  inc     ebx
0x18006ffda  mov     rax, [rbp+57h+var_70]
0x18006ffde  mov     edx, [rax]
0x18006ffe0  test    edx, edx
0x18006ffe2  js      short loc_180070029
0x18006ffe4  cmp     ebx, [rbp+57h+var_78]
0x18006ffe7  jnb     short loc_18006FFAF
0x18006ffe9  mov     rdi, [rbp+57h+var_80]
0x18006ffed  mov     rax, [rdi]
0x18006fff0  mov     r14, [rax+30h]
0x18006fff4  mov     rcx, [rbp+57h+var_60]
0x18006fff8  test    rcx, rcx
0x18006fffb  jz      short loc_18007000E
0x18006fffd  mov     [rbp+57h+var_60], r12
0x180070001  mov     rdx, [rcx]
0x180070004  mov     rax, [rdx+10h]
0x180070008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007000d  nop
0x18007000e  lea     r8, [rbp+57h+var_60]
0x180070012  mov     edx, ebx
0x180070014  mov     rcx, rdi
0x180070017  mov     rax, r14
0x18007001a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007001f  mov     edx, eax
0x180070021  mov     rax, [rbp+57h+var_70]
0x180070025  mov     [rax], edx
0x180070027  jmp     short loc_18006FFAF
0x180070029  mov     rcx, [rbp+57h+var_60]
0x18007002d  test    rcx, rcx
0x180070030  jz      short loc_180070043
0x180070032  mov     [rbp+57h+var_60], r12
0x180070036  mov     rax, [rcx]
0x180070039  mov     rax, [rax+10h]
0x18007003d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070042  nop
0x180070043  mov     [rbp+57h+var_B0], r12
0x180070047  mov     [rbp+57h+string], r12
0x18007004b  lea     r9, [rbp+57h+string]; string
0x18007004f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180070053  mov     edx, 2Eh ; '.'; length
0x180070058  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackagePolicy@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18007005f  call    cs:__imp_WindowsCreateStringReference
0x180070065  test    eax, eax
0x180070067  js      loc_1800703DB
0x18007006d  mov     rbx, [rbp+57h+string]
0x180070071  mov     rcx, [rbp+57h+var_B0]
0x180070075  test    rcx, rcx
0x180070078  jz      short loc_18007008B
0x18007007a  mov     [rbp+57h+var_B0], r12
0x18007007e  mov     rax, [rcx]
0x180070081  mov     rax, [rax+10h]
0x180070085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007008a  nop
0x18007008b  mov     [rbp+57h+var_B0], r12
0x18007008f  mov     [rbp+57h+var_A8], r12
0x180070093  lea     rdx, [rbp+57h+var_A8]
0x180070097  mov     rcx, rbx
0x18007009a  call    cs:__imp_RoActivateInstance
0x1800700a0  mov     ebx, eax
0x1800700a2  test    eax, eax
0x1800700a4  js      short loc_1800700F6
0x1800700a6  mov     r8d, 10h; Size
0x1800700ac  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800700b3  lea     rcx, _GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04; Buf1
0x1800700ba  call    memcmp_0
0x1800700bf  mov     rcx, [rbp+57h+var_A8]
0x1800700c3  test    eax, eax
0x1800700c5  jnz     short loc_1800700CD
0x1800700c7  mov     [rbp+57h+var_B0], rcx
0x1800700cb  jmp     short loc_1800700F6
0x1800700cd  mov     rax, [rcx]
0x1800700d0  lea     r8, [rbp+57h+var_B0]
0x1800700d4  lea     rdx, _GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04
0x1800700db  mov     rax, [rax]
0x1800700de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700e3  mov     ebx, eax
0x1800700e5  mov     rcx, [rbp+57h+var_A8]
0x1800700e9  mov     rax, [rcx]
0x1800700ec  mov     rax, [rax+10h]
0x1800700f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800700f5  nop
0x1800700f6  mov     rcx, [rbp+5Fh]; this
0x1800700fa  test    ebx, ebx
0x1800700fc  js      loc_1800703E3
0x180070102  mov     rcx, [rbp+57h+var_B0]
0x180070106  mov     rax, [rcx]
0x180070109  mov     rdx, [rbp+57h+var_98]
0x18007010d  mov     rax, [rax+68h]
0x180070111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070116  mov     rcx, [rbp+5Fh]; this
0x18007011a  test    eax, eax
0x18007011c  js      loc_1800703F8
0x180070122  mov     rcx, [rbp+57h+var_B0]
0x180070126  mov     rax, [rcx]
0x180070129  mov     rdx, [r13+8]
0x18007012d  mov     rax, [rax+88h]
0x180070134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070139  mov     rcx, [rbp+5Fh]; this
0x18007013d  test    eax, eax
0x18007013f  js      loc_18007040D
0x180070145  mov     rbx, [rbp+57h+var_B0]
0x180070149  mov     rax, [rbx]
0x18007014c  mov     rdi, [rax+98h]
0x180070153  mov     rcx, [rsi]
0x180070156  mov     rax, [rcx]
0x180070159  lea     rdx, [rbp+57h+hstringHeader]
0x18007015d  mov     rax, [rax+18h]
0x180070161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070166  nop
0x180070167  cmp     qword ptr [rax+18h], 7
0x18007016c  jbe     short loc_180070171
0x18007016e  mov     rax, [rax]
0x180070171  mov     [rbp+57h+var_A8], rax
0x180070175  lea     rdx, [rbp+57h+var_A8]
0x180070179  lea     rcx, [rbp+57h+var_80]
0x18007017d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180070182  nop
0x180070183  mov     rdx, [rax+18h]
0x180070187  mov     rcx, rbx
0x18007018a  mov     rax, rdi
0x18007018d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070192  mov     ebx, eax
0x180070194  mov     [rbp+57h+var_68], r12
0x180070198  lea     rcx, [rbp+57h+hstringHeader]
0x18007019c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800701a1  mov     rcx, [rbp+5Fh]; this
0x1800701a5  test    ebx, ebx
0x1800701a7  js      loc_180070422
0x1800701ad  mov     rdi, [rbp+57h+var_B0]
0x1800701b1  mov     rax, [rdi]
0x1800701b4  mov     rbx, [rax+0D8h]
0x1800701bb  mov     rcx, [rsi]
0x1800701be  mov     rdx, [rcx]
0x1800701c1  mov     rax, [rdx+28h]
0x1800701c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800701ca  mov     rdx, rax
0x1800701cd  mov     rcx, rdi
0x1800701d0  mov     rax, rbx
0x1800701d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800701d8  mov     rcx, [rbp+5Fh]; this
0x1800701dc  test    eax, eax
0x1800701de  js      loc_180070437
0x1800701e4  mov     rcx, [rbp+57h+var_B0]
0x1800701e8  mov     [rbp+57h+var_A8], rcx
0x1800701ec  test    rcx, rcx
0x1800701ef  jz      short loc_1800701FE
0x1800701f1  mov     rax, [rcx]
0x1800701f4  mov     rax, [rax+8]
0x1800701f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800701fd  nop
0x1800701fe  xorps   xmm0, xmm0
0x180070201  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180070206  mov     rax, [rsi+8]
0x18007020a  test    rax, rax
0x18007020d  jz      short loc_180070213
0x18007020f  lock inc dword ptr [rax+8]
0x180070213  mov     rax, [rsi]
0x180070216  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007021a  mov     rax, [rsi+8]
0x18007021e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x180070222  lea     rdx, [rbp+57h+var_A8]
  ... truncated ...
```
