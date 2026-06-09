# SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::FinalizeSettings(void)

- ea: `0x14006a198`
- end: `0x14006a944`
- name: `?FinalizeSettings@SecureAssessmentAdminFlowHandler@SecureAssessment@SystemSettings@@SAJXZ`
- size: `1964`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140020120`
- `0x14006a94c`

## callees

- `0x140005f30`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140029eb8`
- `0x14002a2c0`
- `0x14002a3e8`
- `0x1400408ac`
- `0x1400408dc`
- `0x140062ac4`
- `0x140063e9c`
- `0x140069e70`
- `0x140069f24`
- `0x140069fa0`
- `0x14006a198`
- `0x14006ad1c`
- `0x14006aebc`
- `0x14006b130`
- `0x14006ba78`
- `0x14006bb9c`
- `0x14006bd10`
- `0x14007d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14006a69e`
- `KERNEL32!CompareStringOrdinal` at `0x14006a69e`
- `ole32!CoUninitialize` at `0x14006a2a4`
- `ole32!CoUninitialize` at `0x14006a910`
- `ole32!CoUninitialize` at `0x14006a2a4`
- `ole32!CoUninitialize` at `0x14006a910`
- `ole32!CoInitializeEx` at `0x14006a1c0`
- `ole32!CoInitializeEx` at `0x14006a1c0`
- `ole32!CoCreateInstance` at `0x14006a2ec`
- `ole32!CoCreateInstance` at `0x14006a2ec`
- `OLEAUT32!__imp_VariantInit` at `0x14006a4e3`
- `OLEAUT32!__imp_VariantInit` at `0x14006a4e3`

## string_xrefs

- `0x14006a400`: `./Vendor/MSFT/SecureAssessment/LaunchURI`
- `0x14006a742`: `LaunchURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::FinalizeSettings(void)
{
  HRESULT v0; // eax
  int AssignedAccessSingleAppInfo; // eax
  int TemporarySingleAppSid; // eax
  unsigned int v3; // ebx
  HRESULT Instance; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  struct IConfigManager2 *v8; // rdi
  __int64 (__fastcall *v9)(struct IConfigManager2 *, __int64, __int64 *); // rbx
  int v10; // eax
  struct IConfigManager2 *v11; // rdi
  __int64 (__fastcall *v12)(struct IConfigManager2 *, __int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  LONGLONG *bstr; // rax
  LONGLONG v17; // rcx
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  const WCHAR *v24; // rcx
  const WCHAR *v25; // r8
  __int64 v26; // rdx
  struct IConfigManager2 *v27; // rdi
  __int64 (__fastcall *v28)(struct IConfigManager2 *, __int64, __int64 *); // rbx
  int v29; // eax
  int v30; // eax
  __int16 v31; // r8
  int v32; // eax
  __int16 v33; // r8
  __int16 v34; // r8
  int v35; // eax
  int ppv; // [rsp+20h] [rbp-158h]
  int ppva; // [rsp+20h] [rbp-158h]
  int v38; // [rsp+30h] [rbp-148h] BYREF
  struct IConfigManager2 *v39; // [rsp+38h] [rbp-140h] BYREF
  __int64 v40; // [rsp+40h] [rbp-138h] BYREF
  __int64 v41; // [rsp+48h] [rbp-130h] BYREF
  __int64 v42; // [rsp+50h] [rbp-128h] BYREF
  __int64 v43; // [rsp+58h] [rbp-120h] BYREF
  __int64 v44; // [rsp+60h] [rbp-118h] BYREF
  __int64 v45; // [rsp+68h] [rbp-110h] BYREF
  __int64 v46; // [rsp+70h] [rbp-108h]
  __int64 v47; // [rsp+78h] [rbp-100h]
  char v48; // [rsp+81h] [rbp-F7h]
  LPCWCH lpString1; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v50; // [rsp+90h] [rbp-E8h]
  __int64 v51; // [rsp+98h] [rbp-E0h]
  __int64 v52; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-D0h] BYREF
  _QWORD v54[2]; // [rsp+B0h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-B8h] BYREF
  VARIANTARG v56; // [rsp+E0h] [rbp-98h] BYREF
  VARIANTARG v57; // [rsp+100h] [rbp-78h] BYREF
  _BYTE v58[32]; // [rsp+120h] [rbp-58h] BYREF
  _BYTE v59[32]; // [rsp+140h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
      (const char *)(unsigned int)v0,
      ppv);
  v48 = 1;
  v38 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  lpString1 = 0;
  v50 = 0;
  v51 = 0;
  AssignedAccessSingleAppInfo = GetAssignedAccessSingleAppInfo(&v45, &lpString1);
  if ( AssignedAccessSingleAppInfo < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
      (const char *)(unsigned int)AssignedAccessSingleAppInfo,
      ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v45);
  if ( v46
    || (TemporarySingleAppSid = SystemSettings::SecureAssessment::GetTemporarySingleAppSid(&v45),
        v3 = TemporarySingleAppSid,
        TemporarySingleAppSid >= 0) )
  {
    SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::GetTargetAppId(v59);
    v39 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Instance = CoCreateInstance(
                 &GUID_66d0db14_5638_475f_a386_629522d8c461,
                 0,
                 1u,
                 &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                 (LPVOID *)&v39);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
    wil::make_bstr(v54, L"OMADM::AccountID");
    _variant_t::_variant_t((_variant_t *)&v56, v6);
    pvarg = v56;
    v7 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, _QWORD, VARIANTARG *))(*(_QWORD *)v39 + 104LL))(
           v39,
           v54[0],
           &pvarg);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v7,
        ppva);
    wil::make_bstr(&v53, L"./Vendor/MSFT/SecureAssessment/TesterAccount");
    v41 = 0;
    v8 = v39;
    v9 = *(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, __int64 *))(*(_QWORD *)v39 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v10 = v9(v8, v53, &v41);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v10,
        ppva);
    wil::make_bstr(&v52, L"./Vendor/MSFT/SecureAssessment/LaunchURI");
    v40 = 0;
    v11 = v39;
    v12 = *(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, __int64 *))(*(_QWORD *)v39 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    v13 = v12(v11, v52, &v40);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v13,
        ppva);
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 224LL))(v40, &v38);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v14,
        ppva);
    if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&v45)
      && (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&lpString1) )
    {
      Windows::Internal::Management::SecureAssessment::Helpers::ConfigHelper::ConvertSidToUserAccount((__int64)v58, v45);
      VariantInit(&pvarg);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
      bstr = (LONGLONG *)wil::make_bstr(&v44, v15);
      v17 = *bstr;
      *bstr = 0;
      pvarg.llVal = v17;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
      pvarg.vt = 8;
      v57 = pvarg;
      v18 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v41 + 96LL))(v41, &v57, 1);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v18,
          ppva);
      v19 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)v39 + 24LL))(v39);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB9,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v19,
          ppva);
      v21 = SystemSettings::SecureAssessment::SetTemporarySingleAppSid(retaddr, v20);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v21,
          ppva);
      v22 = GetAssignedAccessSingleAppInfo(&v45, &lpString1);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v22,
          ppva);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      std::wstring::_Tidy_deallocate(v58);
    }
    if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(&v45) )
      goto LABEL_41;
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    v24 = &Data;
    v25 = &Data;
    if ( v23 )
      v25 = (const WCHAR *)v23;
    v26 = v50;
    if ( v50 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v26;
        while ( lpString1[v26] );
      }
      else
      {
        LODWORD(v26) = 0;
      }
    }
    if ( lpString1 )
      v24 = lpString1;
    if ( CompareStringOrdinal(v24, v26, v25, -(v23 != 0), 1) != 2 || !v38 )
    {
LABEL_41:
      wil::make_bstr(&v44, L"./Vendor/MSFT/SecureAssessment");
      v42 = 0;
      v27 = v39;
      v28 = *(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, __int64 *))(*(_QWORD *)v39 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      v29 = v28(v27, v44, &v42);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCB,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v29,
          ppva);
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 224LL))(v40, &v38) >= 0 && v38 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        wil::make_bstr(&v43, L"LaunchURI");
        v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 72LL))(v42, v43);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD5,
            (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
            (const char *)(unsigned int)v30,
            ppva);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      }
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 224LL))(v41, &v38) >= 0 && v38 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        wil::make_bstr(&v43, L"TesterAccount");
        v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 72LL))(v42, v43);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDF,
            (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
            (const char *)(unsigned int)v32,
            ppva);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
      }
      SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetCapabilityNode(
        v39,
        L"./Vendor/MSFT/SecureAssessment/AllowScreenMonitoring",
        v31);
      SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetCapabilityNode(
        v39,
        L"./Vendor/MSFT/SecureAssessment/RequirePrinting",
        v33);
      SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetCapabilityNode(
        v39,
        L"./Vendor/MSFT/SecureAssessment/AllowTextSuggestions",
        v34);
      v35 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)v39 + 24LL))(v39);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
          (const char *)(unsigned int)v35,
          ppva);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
    _variant_t::~_variant_t((_variant_t *)&v56);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v54);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    std::wstring::_Tidy_deallocate(v59);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v45);
    CoUninitialize();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
      (const char *)(unsigned int)TemporarySingleAppSid,
      ppv);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v45);
    CoUninitialize();
    return v3;
  }
}

```

## disassembly

```asm
0x14006a198  mov     [rsp+arg_0], rbx
0x14006a19d  mov     [rsp+arg_8], rsi
0x14006a1a2  push    rdi
0x14006a1a3  sub     rsp, 170h
0x14006a1aa  mov     rax, cs:__security_cookie
0x14006a1b1  xor     rax, rsp
0x14006a1b4  mov     [rsp+178h+var_18], rax
0x14006a1bc  xor     edx, edx; dwCoInit
0x14006a1be  xor     ecx, ecx; pvReserved
0x14006a1c0  call    cs:__imp_CoInitializeEx
0x14006a1c6  mov     rcx, [rsp+178h]; this
0x14006a1ce  xor     esi, esi
0x14006a1d0  test    eax, eax
0x14006a1d2  jns     short loc_14006A1E8
0x14006a1d4  mov     r9d, eax; char *
0x14006a1d7  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a1de  mov     edx, 85h; void *
0x14006a1e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a1e8  mov     [rsp+178h+var_F7], 1
0x14006a1f0  mov     [rsp+178h+var_148], esi
0x14006a1f4  mov     [rsp+178h+var_110], rsi
0x14006a1f9  mov     [rsp+178h+var_108], rsi
0x14006a1fe  mov     [rsp+178h+var_100], rsi
0x14006a203  mov     [rsp+178h+lpString1], rsi
0x14006a20b  mov     [rsp+178h+var_E8], rsi
0x14006a213  mov     [rsp+178h+var_E0], rsi
0x14006a21b  lea     rdx, [rsp+178h+lpString1]
0x14006a223  lea     rcx, [rsp+178h+var_110]
0x14006a228  call    GetAssignedAccessSingleAppInfo
0x14006a22d  mov     rcx, [rsp+178h]; this
0x14006a235  test    eax, eax
0x14006a237  jns     short loc_14006A24D
0x14006a239  mov     r9d, eax; char *
0x14006a23c  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a243  mov     edx, 8Eh; void *
0x14006a248  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a24d  lea     rcx, [rsp+178h+var_110]
0x14006a252  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x14006a257  cmp     [rsp+178h+var_108], rsi
0x14006a25c  jnz     short loc_14006A2B1
0x14006a25e  lea     rcx, [rsp+178h+var_110]
0x14006a263  call    ?GetTemporarySingleAppSid@SecureAssessment@SystemSettings@@YAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; SystemSettings::SecureAssessment::GetTemporarySingleAppSid(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x14006a268  mov     ebx, eax
0x14006a26a  test    eax, eax
0x14006a26c  jns     short loc_14006A2B1
0x14006a26e  mov     rcx, [rsp+178h]; this
0x14006a276  mov     r9d, eax; char *
0x14006a279  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a280  mov     edx, 91h; void *
0x14006a285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006a28a  nop
0x14006a28b  lea     rcx, [rsp+178h+lpString1]
0x14006a293  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006a298  nop
0x14006a299  lea     rcx, [rsp+178h+var_110]
0x14006a29e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14006a2a3  nop
0x14006a2a4  call    cs:__imp_CoUninitialize
0x14006a2aa  mov     eax, ebx
0x14006a2ac  jmp     loc_14006A91E
0x14006a2b1  lea     rcx, [rsp+178h+var_38]
0x14006a2b9  call    ?GetTargetAppId@SecureAssessmentAdminFlowHandler@SecureAssessment@SystemSettings@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::GetTargetAppId(void)
0x14006a2be  nop
0x14006a2bf  mov     [rsp+178h+var_140], rsi
0x14006a2c4  lea     rcx, [rsp+178h+var_140]
0x14006a2c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006a2ce  lea     rax, [rsp+178h+var_140]
0x14006a2d3  mov     qword ptr [rsp+178h+ppv], rax; int
0x14006a2d8  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x14006a2df  xor     edx, edx; pUnkOuter
0x14006a2e1  lea     r8d, [rdx+1]; dwClsContext
0x14006a2e5  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x14006a2ec  call    cs:__imp_CoCreateInstance
0x14006a2f2  mov     rcx, [rsp+178h]; this
0x14006a2fa  test    eax, eax
0x14006a2fc  jns     short loc_14006A312
0x14006a2fe  mov     r9d, eax; char *
0x14006a301  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a308  mov     edx, 98h; void *
0x14006a30d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a312  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x14006a319  lea     rcx, [rsp+178h+var_C8]
0x14006a321  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006a326  nop
0x14006a327  lea     rcx, [rsp+178h+var_98]; this
0x14006a32f  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14006a334  nop
0x14006a335  mov     rcx, [rsp+178h+var_140]
0x14006a33a  movups  xmm0, [rsp+178h+var_98]
0x14006a342  movsd   xmm1, [rsp+178h+var_88]
0x14006a34b  movaps  xmmword ptr [rsp+178h+pvarg], xmm0
0x14006a353  movsd   qword ptr [rsp+178h+pvarg+10h], xmm1
0x14006a35c  mov     rax, [rcx]
0x14006a35f  lea     r8, [rsp+178h+pvarg]
0x14006a367  mov     rdx, [rsp+178h+var_C8]
0x14006a36f  mov     rax, [rax+68h]
0x14006a373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a378  mov     rcx, [rsp+178h]; this
0x14006a380  test    eax, eax
0x14006a382  jns     short loc_14006A398
0x14006a384  mov     r9d, eax; char *
0x14006a387  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a38e  mov     edx, 9Eh; void *
0x14006a393  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a398  lea     rdx, aVendorMsftSecu_3; "./Vendor/MSFT/SecureAssessment/TesterAc"...
0x14006a39f  lea     rcx, [rsp+178h+var_D0]
0x14006a3a7  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006a3ac  nop
0x14006a3ad  mov     [rsp+178h+var_130], rsi
0x14006a3b2  mov     rdi, [rsp+178h+var_140]
0x14006a3b7  mov     rax, [rdi]
0x14006a3ba  mov     rbx, [rax+50h]
0x14006a3be  lea     rcx, [rsp+178h+var_130]
0x14006a3c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006a3c8  lea     r8, [rsp+178h+var_130]
0x14006a3cd  mov     rdx, [rsp+178h+var_D0]
0x14006a3d5  mov     rcx, rdi
0x14006a3d8  mov     rax, rbx
0x14006a3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a3e0  mov     rcx, [rsp+178h]; this
0x14006a3e8  test    eax, eax
0x14006a3ea  jns     short loc_14006A400
0x14006a3ec  mov     r9d, eax; char *
0x14006a3ef  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a3f6  mov     edx, 0A3h; void *
0x14006a3fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a400  lea     rdx, aVendorMsftSecu_1; "./Vendor/MSFT/SecureAssessment/LaunchUR"...
0x14006a407  lea     rcx, [rsp+178h+var_D8]
0x14006a40f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006a414  nop
0x14006a415  mov     [rsp+178h+var_138], rsi
0x14006a41a  mov     rdi, [rsp+178h+var_140]
0x14006a41f  mov     rax, [rdi]
0x14006a422  mov     rbx, [rax+50h]
0x14006a426  lea     rcx, [rsp+178h+var_138]
0x14006a42b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006a430  lea     r8, [rsp+178h+var_138]
0x14006a435  mov     rdx, [rsp+178h+var_D8]
0x14006a43d  mov     rcx, rdi
0x14006a440  mov     rax, rbx
0x14006a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a448  mov     rcx, [rsp+178h]; this
0x14006a450  test    eax, eax
0x14006a452  jns     short loc_14006A468
0x14006a454  mov     r9d, eax; char *
0x14006a457  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a45e  mov     edx, 0A8h; void *
0x14006a463  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a468  mov     rcx, [rsp+178h+var_138]
0x14006a46d  mov     rax, [rcx]
0x14006a470  lea     rdx, [rsp+178h+var_148]
0x14006a475  mov     rax, [rax+0E0h]
0x14006a47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a481  mov     rcx, [rsp+178h]; this
0x14006a489  test    eax, eax
0x14006a48b  jns     short loc_14006A4A1
0x14006a48d  mov     r9d, eax; char *
0x14006a490  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a497  mov     edx, 0A9h; void *
0x14006a49c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a4a1  lea     rcx, [rsp+178h+var_110]
0x14006a4a6  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x14006a4ab  test    al, al
0x14006a4ad  jnz     loc_14006A62E
0x14006a4b3  lea     rcx, [rsp+178h+lpString1]
0x14006a4bb  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x14006a4c0  test    al, al
0x14006a4c2  jz      loc_14006A62E
0x14006a4c8  mov     rdx, [rsp+178h+var_110]
0x14006a4cd  lea     rcx, [rsp+178h+var_58]
0x14006a4d5  call    ?ConvertSidToUserAccount@ConfigHelper@Helpers@SecureAssessment@Management@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::Management::SecureAssessment::Helpers::ConfigHelper::ConvertSidToUserAccount(ushort const *)
0x14006a4da  nop
0x14006a4db  lea     rcx, [rsp+178h+pvarg]; pvarg
0x14006a4e3  call    cs:__imp_VariantInit
0x14006a4e9  nop
0x14006a4ea  lea     rcx, [rsp+178h+var_58]
0x14006a4f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006a4f7  mov     rdx, rax
0x14006a4fa  lea     rcx, [rsp+178h+var_118]
0x14006a4ff  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006a504  mov     rcx, [rax]
0x14006a507  mov     [rax], rsi
0x14006a50a  mov     qword ptr [rsp+178h+pvarg+8], rcx
0x14006a512  lea     rcx, [rsp+178h+var_118]
0x14006a517  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006a51c  mov     eax, 8
0x14006a521  mov     word ptr [rsp+178h+pvarg], ax
0x14006a529  mov     rcx, [rsp+178h+var_130]
0x14006a52e  movups  xmm0, xmmword ptr [rsp+178h+pvarg]
0x14006a536  movaps  [rsp+178h+var_78], xmm0
0x14006a53e  movsd   xmm1, qword ptr [rsp+178h+pvarg+10h]
0x14006a547  movsd   [rsp+178h+var_68], xmm1
0x14006a550  mov     rax, [rcx]
0x14006a553  mov     r8d, 1
0x14006a559  lea     rdx, [rsp+178h+var_78]
0x14006a561  mov     rax, [rax+60h]
0x14006a565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a56a  mov     rcx, [rsp+178h]; this
0x14006a572  test    eax, eax
0x14006a574  jns     short loc_14006A58A
0x14006a576  mov     r9d, eax; char *
0x14006a579  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a580  mov     edx, 0B6h; void *
0x14006a585  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a58a  mov     rcx, [rsp+178h+var_140]
0x14006a58f  mov     rax, [rcx]
0x14006a592  mov     rax, [rax+18h]
0x14006a596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a59b  mov     rcx, [rsp+178h]; this
0x14006a5a3  test    eax, eax
0x14006a5a5  jns     short loc_14006A5BB
0x14006a5a7  mov     r9d, eax; char *
0x14006a5aa  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a5b1  mov     edx, 0B9h; void *
0x14006a5b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a5bb  call    ?SetTemporarySingleAppSid@SecureAssessment@SystemSettings@@YAJPEBG@Z; SystemSettings::SecureAssessment::SetTemporarySingleAppSid(ushort const *)
0x14006a5c0  mov     rcx, [rsp+178h]; this
0x14006a5c8  test    eax, eax
0x14006a5ca  jns     short loc_14006A5E0
0x14006a5cc  mov     r9d, eax; char *
0x14006a5cf  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a5d6  mov     edx, 0BDh; void *
0x14006a5db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a5e0  lea     rdx, [rsp+178h+lpString1]
0x14006a5e8  lea     rcx, [rsp+178h+var_110]
0x14006a5ed  call    GetAssignedAccessSingleAppInfo
0x14006a5f2  mov     rcx, [rsp+178h]; this
0x14006a5fa  test    eax, eax
0x14006a5fc  jns     short loc_14006A613
0x14006a5fe  mov     r9d, eax; char *
0x14006a601  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a608  mov     edx, 0C0h; void *
0x14006a60d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a613  lea     rcx, [rsp+178h+pvarg]; this
0x14006a61b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14006a620  nop
0x14006a621  lea     rcx, [rsp+178h+var_58]
0x14006a629  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006a62e  lea     rcx, [rsp+178h+var_110]
0x14006a633  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x14006a638  test    al, al
0x14006a63a  jnz     short loc_14006A6B3
0x14006a63c  lea     rcx, [rsp+178h+var_38]
0x14006a644  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006a649  mov     rcx, rax
0x14006a64c  neg     rcx
0x14006a64f  sbb     r9d, r9d; cchCount2
0x14006a652  lea     rcx, Data
0x14006a659  mov     r8, rcx
0x14006a65c  test    rax, rax
0x14006a65f  cmovnz  r8, rax; lpString2
0x14006a663  mov     rdx, [rsp+178h+var_E8]
0x14006a66b  mov     rax, [rsp+178h+lpString1]
0x14006a673  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14006a677  jnz     short loc_14006A68F
0x14006a679  test    rax, rax
0x14006a67c  jz      short loc_14006A68C
0x14006a67e  or      rdx, rdx
0x14006a681  inc     rdx
0x14006a684  cmp     [rax+rdx*2], si
0x14006a688  jnz     short loc_14006A681
0x14006a68a  jmp     short loc_14006A68F
0x14006a68c  mov     rdx, rsi; cchCount1
0x14006a68f  test    rax, rax
0x14006a692  cmovnz  rcx, rax; lpString1
0x14006a696  mov     [rsp+178h+ppv], 1; int
0x14006a69e  call    cs:__imp_CompareStringOrdinal
0x14006a6a4  cmp     eax, 2
0x14006a6a7  jnz     short loc_14006A6B3
0x14006a6a9  cmp     [rsp+178h+var_148], esi
0x14006a6ad  jnz     loc_14006A890
0x14006a6b3  lea     rdx, aVendorMsftSecu_4; "./Vendor/MSFT/SecureAssessment"
0x14006a6ba  lea     rcx, [rsp+178h+var_118]
0x14006a6bf  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006a6c4  nop
0x14006a6c5  mov     [rsp+178h+var_128], rsi
0x14006a6ca  mov     rdi, [rsp+178h+var_140]
0x14006a6cf  mov     rax, [rdi]
0x14006a6d2  mov     rbx, [rax+50h]
0x14006a6d6  lea     rcx, [rsp+178h+var_128]
0x14006a6db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006a6e0  lea     r8, [rsp+178h+var_128]
0x14006a6e5  mov     rdx, [rsp+178h+var_118]
0x14006a6ea  mov     rcx, rdi
0x14006a6ed  mov     rax, rbx
0x14006a6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a6f5  mov     rcx, [rsp+178h]; this
0x14006a6fd  test    eax, eax
0x14006a6ff  jns     short loc_14006A715
0x14006a701  mov     r9d, eax; char *
0x14006a704  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006a70b  mov     edx, 0CBh; void *
0x14006a710  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006a715  mov     rcx, [rsp+178h+var_138]
0x14006a71a  mov     rax, [rcx]
0x14006a71d  lea     rdx, [rsp+178h+var_148]
0x14006a722  mov     rax, [rax+0E0h]
0x14006a729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a72e  test    eax, eax
0x14006a730  js      short loc_14006A795
  ... truncated ...
```
