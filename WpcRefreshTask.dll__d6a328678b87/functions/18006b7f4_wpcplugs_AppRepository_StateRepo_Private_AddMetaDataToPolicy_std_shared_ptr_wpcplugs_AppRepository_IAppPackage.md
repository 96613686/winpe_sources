# wpcplugs::AppRepository::StateRepo::Private::AddMetaDataToPolicy(std::shared_ptr<wpcplugs::AppRepository::IAppPackagePolicy>,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackagePolicy>)

- ea: `0x18006b7f4`
- end: `0x18006c4c7`
- name: `?AddMetaDataToPolicy@Private@StateRepo@AppRepository@wpcplugs@@YAJV?$shared_ptr@UIAppPackagePolicy@AppRepository@wpcplugs@@@std@@V?$ComPtr@UIPackagePolicy@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `3283`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fde0`

## callees

- `0x1800060a0`
- `0x180007ec1`
- `0x180009a80`
- `0x18000d294`
- `0x18002ca60`
- `0x18002eb3c`
- `0x1800409b4`
- `0x18006b7f4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006bb1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006bdcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006bb1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006bdcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006c072`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006bb58`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006bb58`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18006b898`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18006b898`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c1cf`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c2e1`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c3b6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c1cf`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c2e1`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryFree` at `0x18006c3b6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRPropertySetToDictionary` at `0x18006c19c`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRPropertySetToDictionary` at `0x18006c19c`

## string_xrefs

- `0x18006b90d`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ba2f`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006bb70`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006bcd2`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006be03`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006bf78`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006c0a9`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006c1b4`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006c2c6`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall wpcplugs::AppRepository::StateRepo::Private::AddMetaDataToPolicy(_QWORD *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  unsigned int v7; // r14d
  const WCHAR *v8; // rbx
  _QWORD *v9; // rcx
  const WCHAR *v10; // rcx
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rsi
  __int64 v13; // rcx
  __int64 (__fastcall *v15)(const WCHAR *, GUID *, _QWORD **); // r14
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  const WCHAR *v19; // rcx
  __int64 v20; // rcx
  volatile signed __int32 *v21; // rsi
  __int64 v22; // rcx
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  HSTRING v26; // rbx
  __int64 v27; // rcx
  int ActivationFactory; // eax
  _QWORD *v29; // rcx
  const WCHAR *v30; // rcx
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, PVOID, __int64 *); // r14
  __int64 v36; // rax
  unsigned int v37; // r8d
  HSTRING_HEADER *v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rcx
  const WCHAR *v41; // rcx
  __int64 v42; // rcx
  volatile signed __int32 *v43; // rsi
  __int64 v44; // rcx
  _QWORD *v45; // rbx
  __int64 v46; // r14
  __int64 v47; // r15
  HRESULT v48; // eax
  int v49; // edx
  unsigned int v50; // r8d
  int v51; // eax
  __int64 v52; // rcx
  _QWORD *v53; // rcx
  const WCHAR *v54; // rcx
  __int64 v55; // rcx
  volatile signed __int32 *v56; // rsi
  __int64 v57; // rcx
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, PVOID, __int64 *); // r14
  __int64 v60; // rcx
  __int64 v61; // rax
  unsigned int v62; // r8d
  const WCHAR *p_hstringHeader; // rdx
  HSTRING_HEADER *v64; // rax
  __int64 v65; // rcx
  _QWORD *v66; // rcx
  const WCHAR *v67; // rcx
  __int64 v68; // rcx
  volatile signed __int32 *v69; // rsi
  __int64 v70; // rcx
  _QWORD *v71; // rbx
  __int64 v72; // r14
  __int64 v73; // r15
  HRESULT v74; // eax
  int v75; // edx
  unsigned int v76; // r8d
  int v77; // eax
  __int64 v78; // rcx
  _QWORD *v79; // rcx
  const WCHAR *v80; // rcx
  __int64 v81; // rcx
  volatile signed __int32 *v82; // rsi
  __int64 v83; // rcx
  int v84; // eax
  __int64 v85; // rcx
  _QWORD *v86; // rcx
  const WCHAR *v87; // rcx
  __int64 v88; // rcx
  volatile signed __int32 *v89; // rsi
  __int64 v90; // rcx
  int v91; // eax
  __int64 v92; // rcx
  _QWORD *v93; // rcx
  const WCHAR *v94; // rcx
  __int64 v95; // rcx
  volatile signed __int32 *v96; // rsi
  __int64 v97; // rcx
  __int64 v98; // rcx
  _QWORD *v99; // rcx
  const WCHAR *v100; // rcx
  __int64 v101; // rcx
  volatile signed __int32 *v102; // rsi
  __int64 v103; // rcx
  int v104; // [rsp+20h] [rbp-89h]
  __int64 v105; // [rsp+30h] [rbp-79h] BYREF
  const WCHAR *v106; // [rsp+38h] [rbp-71h] BYREF
  _QWORD *v107; // [rsp+40h] [rbp-69h] BYREF
  __int64 v108; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v109[8]; // [rsp+50h] [rbp-59h] BYREF
  const WCHAR *v110; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v111; // [rsp+60h] [rbp-49h] BYREF
  __int64 v112; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v113[3]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v114[16]; // [rsp+88h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-11h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+7h] BYREF
  HSTRING_HEADER v117; // [rsp+B8h] [rbp+Fh] BYREF
  __int64 v118; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v113[1] = a1;
  v113[2] = a2;
  v108 = 0;
  v106 = 0;
  v107 = 0;
  v105 = 0;
  v109[0] = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  v106 = 0;
  v110 = 0;
  v7 = RoActivateInstance(string, &v110);
  if ( (v7 & 0x80000000) == 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v8 = v110;
      v106 = v110;
      goto LABEL_7;
    }
    v7 = (**(__int64 (__fastcall ***)(const WCHAR *, GUID *, const WCHAR **))v110)(
           v110,
           &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
           &v106);
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v110 + 16LL))(v110);
  }
  v8 = v106;
LABEL_7:
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v104);
    v9 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    v10 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = (volatile signed __int32 *)a1[1];
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v7;
  }
  v15 = **(__int64 (__fastcall ***)(const WCHAR *, GUID *, _QWORD **))v8;
  v16 = v107;
  if ( v107 )
  {
    v107 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
  }
  v17 = v15(v8, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v107);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v17,
      v104);
    v18 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    v19 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = (volatile signed __int32 *)a1[1];
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v22 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v7;
  }
  string = 0;
  v23 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    __debugbreak();
  }
  v26 = string;
  v27 = v108;
  if ( v108 )
  {
    v108 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ActivationFactory = RoGetActivationFactory(v26, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v108);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v104);
    v29 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    v30 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = (volatile signed __int32 *)a1[1];
    if ( v32 )
    {
      if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    v33 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return v7;
  }
  v34 = v108;
  v35 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v108 + 144LL);
  v36 = (*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(*(_QWORD *)*a1 + 56LL))(*a1, &v117);
  if ( *(_QWORD *)(v36 + 24) > 7u )
    v36 = *(_QWORD *)v36;
  v110 = (const WCHAR *)v36;
  v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v110, v37);
  v7 = v35(v34, v38[1].Reserved.Reserved1, &v105);
  string = 0;
  std::wstring::~wstring((char **)&v117);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v104);
    v39 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
    }
    v41 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = (volatile signed __int32 *)a1[1];
    if ( v43 )
    {
      if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
        if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
      }
    }
    v44 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return v7;
  }
  v45 = v107;
  v46 = *v107;
  v47 = v105;
  string = 0;
  v48 = WindowsCreateStringReference(L"Region", 6u, &hstringHeader, &string);
  if ( v48 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v48, v49, v50);
    JUMPOUT(0x18006C4C6LL);
  }
  v51 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v46 + 80))(v45, string, v47, v109);
  v7 = v51;
  if ( v51 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v51,
      v104);
    v52 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v53 + 16LL))(v53);
    }
    v54 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    v56 = (volatile signed __int32 *)a1[1];
    if ( v56 )
    {
      if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    v57 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    return v7;
  }
  v58 = v108;
  v59 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v108 + 144LL);
  v60 = v105;
  if ( v105 )
  {
    v105 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  }
  v61 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 72LL))(*a1, v114);
  DateTime::ToDebugString(v61, &hstringHeader, 0);
  p_hstringHeader = (const WCHAR *)&hstringHeader;
  if ( (unsigned __int64)string > 7 )
    p_hstringHeader = (const WCHAR *)hstringHeader.Reserved.Reserved1;
  v110 = p_hstringHeader;
  v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v117, &v110, v62);
  v7 = v59(v58, v64[1].Reserved.Reserved1, &v105);
  v118 = 0;
  std::wstring::~wstring((char **)&hstringHeader);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v104);
    v65 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v66 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
    }
    v67 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v69 = (volatile signed __int32 *)a1[1];
    if ( v69 )
    {
      if ( _InterlockedExchangeAdd(v69 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
        if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
      }
    }
    v70 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    return v7;
  }
  v71 = v107;
  v72 = *v107;
  v73 = v105;
  string = 0;
  v74 = WindowsCreateStringReference(L"DateTimeModified", 0x10u, &hstringHeader, &string);
  if ( v74 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v74, v75, v76);
    __debugbreak();
  }
  v77 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v72 + 80))(v71, string, v73, v109);
  v7 = v77;
  if ( v77 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v77,
      v104);
    v78 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v79 + 16LL))(v79);
    }
    v80 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v80 + 16LL))(v80);
    }
    v81 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    v82 = (volatile signed __int32 *)a1[1];
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
        if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
      }
    }
    v83 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    return v7;
  }
  v111 = 0;
  v113[0] = 0;
  v112 = 0;
  v84 = SRPropertySetToDictionary(v106, &v112, &v111, v113);
  v7 = v84;
  if ( v84 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v84,
      v104);
    if ( v112 )
      SRDictionaryFree();
    v85 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    v86 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v86 + 16LL))(v86);
    }
    v87 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v87 + 16LL))(v87);
    }
    v88 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    v89 = (volatile signed __int32 *)a1[1];
    if ( v89 )
    {
      if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
        if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
      }
    }
    v90 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    return v7;
  }
  v91 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 248LL))(*a2, v111, v113[0]);
  v7 = v91;
  if ( v91 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v91,
      v104);
    if ( v112 )
      SRDictionaryFree();
    v92 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    }
    v93 = v107;
    if ( v107 )
    {
      v107 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v93 + 16LL))(v93);
    }
    v94 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v94 + 16LL))(v94);
    }
    v95 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    v96 = (volatile signed __int32 *)a1[1];
    if ( v96 )
    {
      if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v96)(v96);
        if ( _InterlockedExchangeAdd(v96 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
      }
    }
    v97 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
    }
    return v7;
  }
  if ( v112 )
    SRDictionaryFree();
  v98 = v105;
  if ( v105 )
  {
    v105 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  }
  v99 = v107;
  if ( v107 )
  {
    v107 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v99 + 16LL))(v99);
  }
  v100 = v106;
  if ( v106 )
  {
    v106 = 0;
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v100 + 16LL))(v100);
  }
  v101 = v108;
  if ( v108 )
  {
    v108 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
  }
  v102 = (volatile signed __int32 *)a1[1];
  if ( v102 )
  {
    if ( _InterlockedExchangeAdd(v102 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v102)(v102);
      if ( _InterlockedExchangeAdd(v102 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v102 + 8LL))(v102);
    }
  }
  v103 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  }
  return 0;
}

```

## disassembly

```asm
0x18006b7f4  mov     [rsp-8+arg_10], rbx
0x18006b7f9  mov     [rsp-8+arg_18], rsi
0x18006b7fe  push    rbp
0x18006b7ff  push    rdi
0x18006b800  push    r12
0x18006b802  push    r14
0x18006b804  push    r15
0x18006b806  lea     rbp, [rsp-37h]
0x18006b80b  sub     rsp, 0E0h
0x18006b812  mov     rax, cs:__security_cookie
0x18006b819  xor     rax, rsp
0x18006b81c  mov     [rbp+57h+var_28], rax
0x18006b820  mov     rdi, rdx
0x18006b823  mov     rsi, rcx
0x18006b826  mov     [rbp+57h+var_88], rcx
0x18006b82a  mov     [rbp+57h+var_80], rdx
0x18006b82e  xor     r12d, r12d
0x18006b831  mov     [rbp+57h+var_B8], r12
0x18006b835  mov     [rbp+57h+var_C8], r12
0x18006b839  mov     [rbp+57h+var_C0], r12
0x18006b83d  mov     [rbp+57h+var_D0], r12
0x18006b841  mov     [rbp+57h+var_B0], r12b
0x18006b845  mov     [rbp+57h+string], r12
0x18006b849  lea     r9, [rbp+57h+string]; string
0x18006b84d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006b851  lea     edx, [r12+2Ah]; length
0x18006b856  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18006b85d  call    cs:__imp_WindowsCreateStringReference
0x18006b863  test    eax, eax
0x18006b865  js      loc_18006C4AF
0x18006b86b  mov     rbx, [rbp+57h+string]
0x18006b86f  mov     rcx, [rbp+57h+var_C8]
0x18006b873  test    rcx, rcx
0x18006b876  jz      short loc_18006B889
0x18006b878  mov     [rbp+57h+var_C8], r12
0x18006b87c  mov     rax, [rcx]
0x18006b87f  mov     rax, [rax+10h]
0x18006b883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b888  nop
0x18006b889  mov     [rbp+57h+var_C8], r12
0x18006b88d  mov     [rbp+57h+var_A8], r12
0x18006b891  lea     rdx, [rbp+57h+var_A8]
0x18006b895  mov     rcx, rbx
0x18006b898  call    cs:__imp_RoActivateInstance
0x18006b89e  mov     r14d, eax
0x18006b8a1  test    eax, eax
0x18006b8a3  js      short loc_18006B8F9
0x18006b8a5  mov     r8d, 10h; Size
0x18006b8ab  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18006b8b2  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18006b8b9  call    memcmp_0
0x18006b8be  test    eax, eax
0x18006b8c0  jnz     short loc_18006B8CC
0x18006b8c2  mov     rbx, [rbp+57h+var_A8]
0x18006b8c6  mov     [rbp+57h+var_C8], rbx
0x18006b8ca  jmp     short loc_18006B8FD
0x18006b8cc  mov     rcx, [rbp+57h+var_A8]
0x18006b8d0  mov     rax, [rcx]
0x18006b8d3  lea     r8, [rbp+57h+var_C8]
0x18006b8d7  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18006b8de  mov     rax, [rax]
0x18006b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8e6  mov     r14d, eax
0x18006b8e9  mov     rcx, [rbp+57h+var_A8]
0x18006b8ed  mov     rax, [rcx]
0x18006b8f0  mov     rax, [rax+10h]
0x18006b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8f9  mov     rbx, [rbp+57h+var_C8]
0x18006b8fd  test    r14d, r14d
0x18006b900  jns     loc_18006B9E7
0x18006b906  mov     rcx, [rbp+5Fh]; this
0x18006b90a  mov     r9d, r14d; char *
0x18006b90d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006b914  mov     edx, 7Ch ; '|'; void *
0x18006b919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b91e  nop
0x18006b91f  mov     rcx, [rbp+57h+var_D0]
0x18006b923  test    rcx, rcx
0x18006b926  jz      short loc_18006B939
0x18006b928  mov     [rbp+57h+var_D0], r12
0x18006b92c  mov     rax, [rcx]
0x18006b92f  mov     rax, [rax+10h]
0x18006b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b938  nop
0x18006b939  mov     rcx, [rbp+57h+var_C0]
0x18006b93d  test    rcx, rcx
0x18006b940  jz      short loc_18006B953
0x18006b942  mov     [rbp+57h+var_C0], r12
0x18006b946  mov     rax, [rcx]
0x18006b949  mov     rax, [rax+10h]
0x18006b94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b952  nop
0x18006b953  mov     rcx, [rbp+57h+var_C8]
0x18006b957  test    rcx, rcx
0x18006b95a  jz      short loc_18006B96D
0x18006b95c  mov     [rbp+57h+var_C8], r12
0x18006b960  mov     rax, [rcx]
0x18006b963  mov     rax, [rax+10h]
0x18006b967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b96c  nop
0x18006b96d  mov     rcx, [rbp+57h+var_B8]
0x18006b971  test    rcx, rcx
0x18006b974  jz      short loc_18006B987
0x18006b976  mov     [rbp+57h+var_B8], r12
0x18006b97a  mov     rax, [rcx]
0x18006b97d  mov     rax, [rax+10h]
0x18006b981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b986  nop
0x18006b987  mov     rsi, [rsi+8]
0x18006b98b  test    rsi, rsi
0x18006b98e  jz      short loc_18006B9C7
0x18006b990  or      ebx, 0FFFFFFFFh
0x18006b993  mov     eax, ebx
0x18006b995  lock xadd [rsi+8], eax
0x18006b99a  add     eax, ebx
0x18006b99c  jnz     short loc_18006B9C7
0x18006b99e  mov     rax, [rsi]
0x18006b9a1  mov     rcx, rsi
0x18006b9a4  mov     rax, [rax]
0x18006b9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9ac  mov     eax, ebx
0x18006b9ae  lock xadd [rsi+0Ch], eax
0x18006b9b3  add     eax, ebx
0x18006b9b5  jnz     short loc_18006B9C7
0x18006b9b7  mov     rax, [rsi]
0x18006b9ba  mov     rcx, rsi
0x18006b9bd  mov     rax, [rax+8]
0x18006b9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9c6  nop
0x18006b9c7  mov     rcx, [rdi]
0x18006b9ca  test    rcx, rcx
0x18006b9cd  jz      short loc_18006B9DF
0x18006b9cf  mov     [rdi], r12
0x18006b9d2  mov     rax, [rcx]
0x18006b9d5  mov     rax, [rax+10h]
0x18006b9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9de  nop
0x18006b9df  mov     eax, r14d
0x18006b9e2  jmp     loc_18006C47F
0x18006b9e7  mov     rax, [rbx]
0x18006b9ea  mov     r14, [rax]
0x18006b9ed  mov     rcx, [rbp+57h+var_C0]
0x18006b9f1  test    rcx, rcx
0x18006b9f4  jz      short loc_18006BA07
0x18006b9f6  mov     [rbp+57h+var_C0], r12
0x18006b9fa  mov     rdx, [rcx]
0x18006b9fd  mov     rax, [rdx+10h]
0x18006ba01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba06  nop
0x18006ba07  lea     r8, [rbp+57h+var_C0]
0x18006ba0b  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18006ba12  mov     rcx, rbx
0x18006ba15  mov     rax, r14
0x18006ba18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba1d  mov     r14d, eax
0x18006ba20  test    eax, eax
0x18006ba22  jns     loc_18006BB06
0x18006ba28  mov     rcx, [rbp+5Fh]; this
0x18006ba2c  mov     r9d, eax; char *
0x18006ba2f  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ba36  mov     edx, 7Eh ; '~'; void *
0x18006ba3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ba40  nop
0x18006ba41  mov     rcx, [rbp+57h+var_D0]
0x18006ba45  test    rcx, rcx
0x18006ba48  jz      short loc_18006BA5B
0x18006ba4a  mov     [rbp+57h+var_D0], r12
0x18006ba4e  mov     rax, [rcx]
0x18006ba51  mov     rax, [rax+10h]
0x18006ba55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba5a  nop
0x18006ba5b  mov     rcx, [rbp+57h+var_C0]
0x18006ba5f  test    rcx, rcx
0x18006ba62  jz      short loc_18006BA75
0x18006ba64  mov     [rbp+57h+var_C0], r12
0x18006ba68  mov     rax, [rcx]
0x18006ba6b  mov     rax, [rax+10h]
0x18006ba6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba74  nop
0x18006ba75  mov     rcx, [rbp+57h+var_C8]
0x18006ba79  test    rcx, rcx
0x18006ba7c  jz      short loc_18006BA8F
0x18006ba7e  mov     [rbp+57h+var_C8], r12
0x18006ba82  mov     rax, [rcx]
0x18006ba85  mov     rax, [rax+10h]
0x18006ba89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba8e  nop
0x18006ba8f  mov     rcx, [rbp+57h+var_B8]
0x18006ba93  test    rcx, rcx
0x18006ba96  jz      short loc_18006BAA9
0x18006ba98  mov     [rbp+57h+var_B8], r12
0x18006ba9c  mov     rax, [rcx]
0x18006ba9f  mov     rax, [rax+10h]
0x18006baa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baa8  nop
0x18006baa9  mov     rsi, [rsi+8]
0x18006baad  test    rsi, rsi
0x18006bab0  jz      short loc_18006BAE9
0x18006bab2  or      ebx, 0FFFFFFFFh
0x18006bab5  mov     eax, ebx
0x18006bab7  lock xadd [rsi+8], eax
0x18006babc  add     eax, ebx
0x18006babe  jnz     short loc_18006BAE9
0x18006bac0  mov     rax, [rsi]
0x18006bac3  mov     rcx, rsi
0x18006bac6  mov     rax, [rax]
0x18006bac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bace  mov     eax, ebx
0x18006bad0  lock xadd [rsi+0Ch], eax
0x18006bad5  add     eax, ebx
0x18006bad7  jnz     short loc_18006BAE9
0x18006bad9  mov     rax, [rsi]
0x18006badc  mov     rcx, rsi
0x18006badf  mov     rax, [rax+8]
0x18006bae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bae8  nop
0x18006bae9  mov     rcx, [rdi]
0x18006baec  test    rcx, rcx
0x18006baef  jz      short loc_18006BB01
0x18006baf1  mov     [rdi], r12
0x18006baf4  mov     rax, [rcx]
0x18006baf7  mov     rax, [rax+10h]
0x18006bafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb00  nop
0x18006bb01  jmp     loc_18006B9DF
0x18006bb06  mov     [rbp+57h+string], r12
0x18006bb0a  lea     r9, [rbp+57h+string]; string
0x18006bb0e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006bb12  mov     edx, 20h ; ' '; length
0x18006bb17  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18006bb1e  call    cs:__imp_WindowsCreateStringReference
0x18006bb24  test    eax, eax
0x18006bb26  js      loc_18006C4B7
0x18006bb2c  mov     rbx, [rbp+57h+string]
0x18006bb30  mov     rcx, [rbp+57h+var_B8]
0x18006bb34  test    rcx, rcx
0x18006bb37  jz      short loc_18006BB4A
0x18006bb39  mov     [rbp+57h+var_B8], r12
0x18006bb3d  mov     rax, [rcx]
0x18006bb40  mov     rax, [rax+10h]
0x18006bb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb49  nop
0x18006bb4a  lea     r8, [rbp+57h+var_B8]
0x18006bb4e  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18006bb55  mov     rcx, rbx
0x18006bb58  call    cs:__imp_RoGetActivationFactory
0x18006bb5e  mov     r14d, eax
0x18006bb61  test    eax, eax
0x18006bb63  jns     loc_18006BC47
0x18006bb69  mov     rcx, [rbp+5Fh]; this
0x18006bb6d  mov     r9d, eax; char *
0x18006bb70  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006bb77  mov     edx, 7Fh; void *
0x18006bb7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bb81  nop
0x18006bb82  mov     rcx, [rbp+57h+var_D0]
0x18006bb86  test    rcx, rcx
0x18006bb89  jz      short loc_18006BB9C
0x18006bb8b  mov     [rbp+57h+var_D0], r12
0x18006bb8f  mov     rax, [rcx]
0x18006bb92  mov     rax, [rax+10h]
0x18006bb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb9b  nop
0x18006bb9c  mov     rcx, [rbp+57h+var_C0]
0x18006bba0  test    rcx, rcx
0x18006bba3  jz      short loc_18006BBB6
0x18006bba5  mov     [rbp+57h+var_C0], r12
0x18006bba9  mov     rax, [rcx]
0x18006bbac  mov     rax, [rax+10h]
0x18006bbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbb5  nop
0x18006bbb6  mov     rcx, [rbp+57h+var_C8]
0x18006bbba  test    rcx, rcx
0x18006bbbd  jz      short loc_18006BBD0
0x18006bbbf  mov     [rbp+57h+var_C8], r12
0x18006bbc3  mov     rax, [rcx]
0x18006bbc6  mov     rax, [rax+10h]
0x18006bbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbcf  nop
0x18006bbd0  mov     rcx, [rbp+57h+var_B8]
0x18006bbd4  test    rcx, rcx
0x18006bbd7  jz      short loc_18006BBEA
0x18006bbd9  mov     [rbp+57h+var_B8], r12
0x18006bbdd  mov     rax, [rcx]
0x18006bbe0  mov     rax, [rax+10h]
0x18006bbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbe9  nop
0x18006bbea  mov     rsi, [rsi+8]
0x18006bbee  test    rsi, rsi
0x18006bbf1  jz      short loc_18006BC2A
0x18006bbf3  or      ebx, 0FFFFFFFFh
0x18006bbf6  mov     eax, ebx
0x18006bbf8  lock xadd [rsi+8], eax
0x18006bbfd  add     eax, ebx
0x18006bbff  jnz     short loc_18006BC2A
0x18006bc01  mov     rax, [rsi]
0x18006bc04  mov     rcx, rsi
0x18006bc07  mov     rax, [rax]
0x18006bc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc0f  mov     eax, ebx
  ... truncated ...
```
