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
  __int64 (__fastcall ***v8)(_QWORD, GUID *, _QWORD **); // rbx
  _QWORD *v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rsi
  __int64 v13; // rcx
  __int64 (__fastcall *v15)(_QWORD, GUID *, _QWORD **); // r14
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rcx
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
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64 *); // r14
  _QWORD *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v41; // rcx
  volatile signed __int32 *v42; // rsi
  __int64 v43; // rcx
  _QWORD *v44; // rbx
  __int64 v45; // r14
  __int64 v46; // r15
  HRESULT v47; // eax
  int v48; // edx
  unsigned int v49; // r8d
  int v50; // eax
  __int64 v51; // rcx
  _QWORD *v52; // rcx
  __int64 (__fastcall ***v53)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v54; // rcx
  volatile signed __int32 *v55; // rsi
  __int64 v56; // rcx
  __int64 v57; // rbx
  __int64 (__fastcall *v58)(__int64, _QWORD, __int64 *); // r14
  __int64 v59; // rcx
  __int64 v60; // rax
  _QWORD *p_hstringHeader; // rdx
  __int64 v62; // rax
  __int64 v63; // rcx
  _QWORD *v64; // rcx
  __int64 (__fastcall ***v65)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v66; // rcx
  volatile signed __int32 *v67; // rsi
  __int64 v68; // rcx
  _QWORD *v69; // rbx
  __int64 v70; // r14
  __int64 v71; // r15
  HRESULT v72; // eax
  int v73; // edx
  unsigned int v74; // r8d
  int v75; // eax
  __int64 v76; // rcx
  _QWORD *v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v79; // rcx
  volatile signed __int32 *v80; // rsi
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  _QWORD *v84; // rcx
  __int64 (__fastcall ***v85)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v86; // rcx
  volatile signed __int32 *v87; // rsi
  __int64 v88; // rcx
  int v89; // eax
  __int64 v90; // rcx
  _QWORD *v91; // rcx
  __int64 (__fastcall ***v92)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v93; // rcx
  volatile signed __int32 *v94; // rsi
  __int64 v95; // rcx
  __int64 v96; // rcx
  _QWORD *v97; // rcx
  __int64 (__fastcall ***v98)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v99; // rcx
  volatile signed __int32 *v100; // rsi
  __int64 v101; // rcx
  int v102; // [rsp+20h] [rbp-89h]
  __int64 v103; // [rsp+30h] [rbp-79h] BYREF
  __int64 (__fastcall ***v104)(_QWORD, GUID *, _QWORD **); // [rsp+38h] [rbp-71h] BYREF
  _QWORD *v105; // [rsp+40h] [rbp-69h] BYREF
  __int64 v106; // [rsp+48h] [rbp-61h] BYREF
  char v107[8]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v108; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v109; // [rsp+60h] [rbp-49h] BYREF
  __int64 v110; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v111[3]; // [rsp+70h] [rbp-39h] BYREF
  char v112[16]; // [rsp+88h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-11h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+7h] BYREF
  _BYTE v115[24]; // [rsp+B8h] [rbp+Fh] BYREF
  __int64 v116; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v111[1] = a1;
  v111[2] = a2;
  v106 = 0;
  v104 = 0;
  v105 = 0;
  v103 = 0;
  v107[0] = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  v104 = 0;
  v108 = 0;
  v7 = RoActivateInstance(string, &v108);
  if ( (v7 & 0x80000000) == 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))v108;
      v104 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))v108;
      goto LABEL_7;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v108)(
           v108,
           &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
           &v104);
    (*(void (__fastcall **)(_QWORD *))(*v108 + 16LL))(v108);
  }
  v8 = v104;
LABEL_7:
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v102);
    v9 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
    }
    v11 = v106;
    if ( v106 )
    {
      v106 = 0;
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
  v15 = **v8;
  v16 = v105;
  if ( v105 )
  {
    v105 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
  }
  v17 = v15(v8, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v105);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v17,
      v102);
    v18 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v19)[2])(v19);
    }
    v20 = v106;
    if ( v106 )
    {
      v106 = 0;
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
  v27 = v106;
  if ( v106 )
  {
    v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ActivationFactory = RoGetActivationFactory(v26, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v106);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v102);
    v29 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
    }
    v31 = v106;
    if ( v106 )
    {
      v106 = 0;
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
  v34 = v106;
  v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v106 + 144LL);
  v36 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a1 + 56LL))(*a1, v115);
  if ( v36[3] > 7u )
    v36 = (_QWORD *)*v36;
  v108 = v36;
  v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v108);
  v7 = v35(v34, *(_QWORD *)(v37 + 24), &v103);
  string = 0;
  std::wstring::~wstring(v115);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v102);
    v38 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
    }
    v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v40)[2])(v40);
    }
    v41 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = (volatile signed __int32 *)a1[1];
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
    v43 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    return v7;
  }
  v44 = v105;
  v45 = *v105;
  v46 = v103;
  string = 0;
  v47 = WindowsCreateStringReference(L"Region", 6u, &hstringHeader, &string);
  if ( v47 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v47, v48, v49);
    JUMPOUT(0x18006C4C6LL);
  }
  v50 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v45 + 80))(v44, string, v46, v107);
  v7 = v50;
  if ( v50 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v50,
      v102);
    v51 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v52 + 16LL))(v52);
    }
    v53 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v53)[2])(v53);
    }
    v54 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = (volatile signed __int32 *)a1[1];
    if ( v55 )
    {
      if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
        if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
      }
    }
    v56 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    return v7;
  }
  v57 = v106;
  v58 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v106 + 144LL);
  v59 = v103;
  if ( v103 )
  {
    v103 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  v60 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*a1 + 72LL))(*a1, v112);
  DateTime::ToDebugString(v60, &hstringHeader, 0);
  p_hstringHeader = &hstringHeader;
  if ( (unsigned __int64)string > 7 )
    p_hstringHeader = hstringHeader.Reserved.Reserved1;
  v108 = p_hstringHeader;
  v62 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v115, &v108);
  v7 = v58(v57, *(_QWORD *)(v62 + 24), &v103);
  v116 = 0;
  std::wstring::~wstring(&hstringHeader);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)v7,
      v102);
    v63 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
    }
    v65 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v65)[2])(v65);
    }
    v66 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = (volatile signed __int32 *)a1[1];
    if ( v67 )
    {
      if ( _InterlockedExchangeAdd(v67 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
        if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
      }
    }
    v68 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    return v7;
  }
  v69 = v105;
  v70 = *v105;
  v71 = v103;
  string = 0;
  v72 = WindowsCreateStringReference(L"DateTimeModified", 0x10u, &hstringHeader, &string);
  if ( v72 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v72, v73, v74);
    __debugbreak();
  }
  v75 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v70 + 80))(v69, string, v71, v107);
  v7 = v75;
  if ( v75 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v75,
      v102);
    v76 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    v77 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
    }
    v78 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v78)[2])(v78);
    }
    v79 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = (volatile signed __int32 *)a1[1];
    if ( v80 )
    {
      if ( _InterlockedExchangeAdd(v80 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
        if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
      }
    }
    v81 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    return v7;
  }
  v109 = 0;
  v111[0] = 0;
  v110 = 0;
  v82 = SRPropertySetToDictionary(v104, &v110, &v109, v111);
  v7 = v82;
  if ( v82 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v82,
      v102);
    if ( v110 )
      SRDictionaryFree();
    v83 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v84 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    }
    v85 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v85)[2])(v85);
    }
    v86 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    }
    v87 = (volatile signed __int32 *)a1[1];
    if ( v87 )
    {
      if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
        if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
      }
    }
    v88 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    return v7;
  }
  v89 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 248LL))(*a2, v109, v111[0]);
  v7 = v89;
  if ( v89 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v89,
      v102);
    if ( v110 )
      SRDictionaryFree();
    v90 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    v91 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v91 + 16LL))(v91);
    }
    v92 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
    if ( v104 )
    {
      v104 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v92)[2])(v92);
    }
    v93 = v106;
    if ( v106 )
    {
      v106 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
    }
    v94 = (volatile signed __int32 *)a1[1];
    if ( v94 )
    {
      if ( _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
        if ( _InterlockedExchangeAdd(v94 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
      }
    }
    v95 = *a2;
    if ( *a2 )
    {
      *a2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
    }
    return v7;
  }
  if ( v110 )
    SRDictionaryFree();
  v96 = v103;
  if ( v103 )
  {
    v103 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  }
  v97 = v105;
  if ( v105 )
  {
    v105 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v97 + 16LL))(v97);
  }
  v98 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v104;
  if ( v104 )
  {
    v104 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v98)[2])(v98);
  }
  v99 = v106;
  if ( v106 )
  {
    v106 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
  }
  v100 = (volatile signed __int32 *)a1[1];
  if ( v100 )
  {
    if ( _InterlockedExchangeAdd(v100 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v100)(v100);
      if ( _InterlockedExchangeAdd(v100 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v100 + 8LL))(v100);
    }
  }
  v101 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
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
