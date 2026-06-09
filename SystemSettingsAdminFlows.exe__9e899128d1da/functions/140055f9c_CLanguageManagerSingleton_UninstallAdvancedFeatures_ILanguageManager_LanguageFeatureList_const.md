# CLanguageManagerSingleton::_UninstallAdvancedFeatures(ILanguageManager *,LanguageFeatureList const *)

- ea: `0x140055f9c`
- end: `0x140056902`
- name: `?_UninstallAdvancedFeatures@CLanguageManagerSingleton@@AEAAJPEAUILanguageManager@@PEBULanguageFeatureList@@@Z`
- size: `2406`
- prototype: `__int64 __fastcall(CLanguageManagerSingleton *__hidden this, struct ILanguageManager *, const struct LanguageFeatureList *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004e8b4`

## callees

- `0x140005f30`
- `0x140006d2c`
- `0x140011b68`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x140029eb8`
- `0x14002a3e8`
- `0x140045220`
- `0x140045f64`
- `0x14004aea4`
- `0x14004bbf0`
- `0x14004bcb0`
- `0x14004e1e8`
- `0x140051ab4`
- `0x140051c54`
- `0x14005390c`
- `0x140055d84`
- `0x140055f9c`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005669e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056825`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14005669e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140056825`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CLanguageManagerSingleton::_UninstallAdvancedFeatures(
        CLanguageManagerSingleton *this,
        struct ILanguageManager *a2,
        const struct LanguageFeatureList *a3)
{
  __int64 SerializedLanguageFeatures; // rax
  const struct CbsLanguageFeature *v5; // rsi
  struct CbsLanguageFeature *v6; // r14
  __m128i si128; // xmm6
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, HSTRING, const unsigned __int16 **); // rbx
  int v36; // eax
  unsigned int v37; // ebx
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // [rsp+20h] [rbp-328h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-318h] BYREF
  __int64 v42; // [rsp+48h] [rbp-300h]
  _BYTE v43[32]; // [rsp+50h] [rbp-2F8h] BYREF
  _BYTE v44[8]; // [rsp+70h] [rbp-2D8h] BYREF
  __int64 v45; // [rsp+78h] [rbp-2D0h] BYREF
  __int64 v46; // [rsp+80h] [rbp-2C8h] BYREF
  HSTRING string; // [rsp+88h] [rbp-2C0h] BYREF
  __int64 v48; // [rsp+90h] [rbp-2B8h] BYREF
  __int64 v49; // [rsp+98h] [rbp-2B0h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-2A8h] BYREF
  const unsigned __int16 *v51; // [rsp+A8h] [rbp-2A0h] BYREF
  struct CbsLanguageFeature *v52[3]; // [rsp+B0h] [rbp-298h] BYREF
  _OWORD v53[2]; // [rsp+C8h] [rbp-280h] BYREF
  _BYTE v54[192]; // [rsp+F0h] [rbp-258h] BYREF
  _BYTE v55[336]; // [rsp+1B0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  CLanguageManagerSingleton::_GetAdvancedLanguageFeatures(v52, a3);
  SerializedLanguageFeatures = CLanguageManagerSingleton::_GetSerializedLanguageFeatures(v43, v52);
  v51 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SerializedLanguageFeatures);
  LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::Start<unsigned short const *>(
    (LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55,
    &v51);
  std::wstring::_Tidy_deallocate(v43);
  v5 = v52[0];
  v6 = v52[1];
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v5 != v6 )
  {
    CbsLanguageFeature::CbsLanguageFeature((CbsLanguageFeature *)v54, v5);
    v53[0] = 0;
    v53[1] = si128;
    LOWORD(v53[0]) = 0;
    if ( (int)CLanguageManagerSingleton::_GetPackageFamilyNameForAdvancedFeature(
                (__int64)this,
                (__int64)v54,
                (__int64)v53) >= 0 )
    {
      v46 = 0;
      v42 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Management.Deployment.PackageManager",
        0x2Du,
        0x2Cu);
      v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
             v42,
             &v46);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26F,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
          (const char *)(unsigned int)v8,
          v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        std::wstring::_Tidy_deallocate(v53);
        CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
        LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
        std::vector<CbsLanguageFeature>::_Tidy(v52);
        return v9;
      }
      v48 = 0;
      v11 = v46;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v46 + 160LL);
      v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v49);
      v14 = v12(v11, 0, *(_QWORD *)(v13 + 24), &v48);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x275,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
          (const char *)(unsigned int)v14,
          v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        std::wstring::_Tidy_deallocate(v53);
        CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
        LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
        std::vector<CbsLanguageFeature>::_Tidy(v52);
        return v15;
      }
      v45 = 0;
      v44[0] = 0;
      v16 = v48;
      v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      v18 = v17(v16, &v45);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x279,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
          (const char *)(unsigned int)v18,
          v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        std::wstring::_Tidy_deallocate(v53);
        CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
        LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
        std::vector<CbsLanguageFeature>::_Tidy(v52);
        return v19;
      }
      v20 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 56LL))(v45, v44);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27A,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
          (const char *)(unsigned int)v20,
          v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        std::wstring::_Tidy_deallocate(v53);
        CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
        LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
        std::vector<CbsLanguageFeature>::_Tidy(v52);
        return v21;
      }
      while ( v44[0] )
      {
        v49 = 0;
        v22 = v45;
        v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
        v24 = v23(v22, &v49);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x27E,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
            (const char *)(unsigned int)v24,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          std::wstring::_Tidy_deallocate(v53);
          CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
          LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
          std::vector<CbsLanguageFeature>::_Tidy(v52);
          return v25;
        }
        v50 = 0;
        v26 = v49;
        v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        v28 = v27(v26, &v50);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x280,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
            (const char *)(unsigned int)v28,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          std::wstring::_Tidy_deallocate(v53);
          CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
          LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
          std::vector<CbsLanguageFeature>::_Tidy(v52);
          return v29;
        }
        string = 0;
        v30 = v50;
        v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 96LL);
        WindowsDeleteString(0);
        string = 0;
        v32 = v31(v30, &string);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x283,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
            (const char *)(unsigned int)v32,
            v40);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          std::wstring::_Tidy_deallocate(v53);
          CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
          LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
          std::vector<CbsLanguageFeature>::_Tidy(v52);
          return v33;
        }
        v51 = 0;
        v34 = v46;
        v35 = *(__int64 (__fastcall **)(__int64, HSTRING, const unsigned __int16 **))(*(_QWORD *)v46 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        v36 = v35(v34, string, &v51);
        v37 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x288,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
            (const char *)(unsigned int)v36,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          std::wstring::_Tidy_deallocate(v53);
          CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
          LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
          std::vector<CbsLanguageFeature>::_Tidy(v52);
          return v37;
        }
        v38 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 64LL))(v45, v44);
        v39 = v38;
        if ( v38 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28A,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
            (const char *)(unsigned int)v38,
            v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          std::wstring::_Tidy_deallocate(v53);
          CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
          LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
          std::vector<CbsLanguageFeature>::_Tidy(v52);
          return v39;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    }
    std::wstring::_Tidy_deallocate(v53);
    CbsLanguageFeature::~CbsLanguageFeature((CbsLanguageFeature *)v54);
    v5 = (const struct CbsLanguageFeature *)((char *)v5 + 192);
  }
  wil::ActivityBase<LanguageFeaturesOnDemandSettings,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v55,
    0);
  LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest *)v55);
  std::vector<CbsLanguageFeature>::_Tidy(v52);
  return 0;
}

```

## disassembly

```asm
0x140055f9c  mov     rax, rsp
0x140055f9f  mov     [rax+10h], rbx
0x140055fa3  push    rsi
0x140055fa4  push    rdi
0x140055fa5  push    r12
0x140055fa7  push    r14
0x140055fa9  push    r15
0x140055fab  sub     rsp, 320h
0x140055fb2  movaps  xmmword ptr [rax-38h], xmm6
0x140055fb6  mov     rax, cs:__security_cookie
0x140055fbd  xor     rax, rsp
0x140055fc0  mov     [rsp+348h+var_48], rax
0x140055fc8  mov     r15, rcx
0x140055fcb  mov     rdx, r8
0x140055fce  lea     rcx, [rsp+348h+var_298]
0x140055fd6  call    ?_GetAdvancedLanguageFeatures@CLanguageManagerSingleton@@CA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@PEBULanguageFeatureList@@@Z; CLanguageManagerSingleton::_GetAdvancedLanguageFeatures(LanguageFeatureList const *)
0x140055fdb  nop
0x140055fdc  lea     rdx, [rsp+348h+var_298]
0x140055fe4  lea     rcx, [rsp+348h+var_2F8]
0x140055fe9  call    ?_GetSerializedLanguageFeatures@CLanguageManagerSingleton@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; CLanguageManagerSingleton::_GetSerializedLanguageFeatures(std::vector<CbsLanguageFeature> const &)
0x140055fee  mov     rcx, rax
0x140055ff1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140055ff6  mov     [rsp+348h+var_2A0], rax
0x140055ffe  lea     rdx, [rsp+348h+var_2A0]
0x140056006  lea     rcx, [rsp+348h+var_198]; this
0x14005600e  call    ??$Start@PEBG@UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@SA?AV01@$$QEAPEBG@Z; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::Start<ushort const *>(ushort const * &&)
0x140056013  nop
0x140056014  lea     rcx, [rsp+348h+var_2F8]
0x140056019  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005601e  mov     rsi, [rsp+348h+var_298]
0x140056026  mov     r14, [rsp+348h+var_290]
0x14005602e  xor     r12d, r12d
0x140056031  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140056039  cmp     rsi, r14
0x14005603c  jz      loc_1400568A1
0x140056042  mov     rdx, rsi; struct CbsLanguageFeature *
0x140056045  lea     rcx, [rsp+348h+var_258]; this
0x14005604d  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x140056052  nop
0x140056053  xorps   xmm0, xmm0
0x140056056  movups  [rsp+348h+var_280], xmm0
0x14005605e  movdqu  [rsp+348h+var_270], xmm6
0x140056067  mov     word ptr [rsp+348h+var_280], r12w
0x140056070  lea     r8, [rsp+348h+var_280]
0x140056078  lea     rdx, [rsp+348h+var_258]
0x140056080  mov     rcx, r15
0x140056083  call    ?_GetPackageFamilyNameForAdvancedFeature@CLanguageManagerSingleton@@AEAAJAEBVCbsLanguageFeature@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CLanguageManagerSingleton::_GetPackageFamilyNameForAdvancedFeature(CbsLanguageFeature const &,std::wstring *)
0x140056088  test    eax, eax
0x14005608a  js      loc_14005687A
0x140056090  mov     [rsp+348h+var_2C8], r12
0x140056098  mov     [rsp+348h+var_300], r12
0x14005609d  mov     r9d, 2Ch ; ','; unsigned int
0x1400560a3  lea     r8d, [r9+1]; unsigned int
0x1400560a7  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1400560ae  lea     rcx, [rsp+348h+hstringHeader]; hstringHeader
0x1400560b3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400560b8  lea     rdx, [rsp+348h+var_2C8]
0x1400560c0  mov     rcx, [rsp+348h+var_300]
0x1400560c5  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1400560ca  mov     ebx, eax
0x1400560cc  test    eax, eax
0x1400560ce  jns     short loc_140056139
0x1400560d0  mov     rcx, [rsp+348h]; this
0x1400560d8  mov     r9d, eax; char *
0x1400560db  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400560e2  mov     edx, 26Fh; void *
0x1400560e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400560ec  nop
0x1400560ed  lea     rcx, [rsp+348h+var_2C8]
0x1400560f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400560fa  nop
0x1400560fb  lea     rcx, [rsp+348h+var_280]
0x140056103  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140056108  nop
0x140056109  lea     rcx, [rsp+348h+var_258]; this
0x140056111  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x140056116  nop
0x140056117  lea     rcx, [rsp+348h+var_198]; this
0x14005611f  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x140056124  nop
0x140056125  lea     rcx, [rsp+348h+var_298]
0x14005612d  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140056132  mov     eax, ebx
0x140056134  jmp     loc_1400568D4
0x140056139  mov     [rsp+348h+var_2B8], r12
0x140056141  mov     rdi, [rsp+348h+var_2C8]
0x140056149  mov     rax, [rdi]
0x14005614c  mov     rbx, [rax+0A0h]
0x140056153  lea     rcx, [rsp+348h+var_280]
0x14005615b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140056160  mov     [rsp+348h+var_2B0], rax
0x140056168  lea     rdx, [rsp+348h+var_2B0]
0x140056170  lea     rcx, [rsp+348h+hstringHeader]
0x140056175  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14005617a  nop
0x14005617b  lea     r9, [rsp+348h+var_2B8]
0x140056183  mov     r8, [rax+18h]
0x140056187  xor     edx, edx
0x140056189  mov     rcx, rdi
0x14005618c  mov     rax, rbx
0x14005618f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056194  mov     ebx, eax
0x140056196  test    eax, eax
0x140056198  jns     short loc_140056211
0x14005619a  mov     rcx, [rsp+348h]; this
0x1400561a2  mov     r9d, eax; char *
0x1400561a5  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400561ac  mov     edx, 275h; void *
0x1400561b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400561b6  nop
0x1400561b7  lea     rcx, [rsp+348h+var_2B8]
0x1400561bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400561c4  nop
0x1400561c5  lea     rcx, [rsp+348h+var_2C8]
0x1400561cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400561d2  nop
0x1400561d3  lea     rcx, [rsp+348h+var_280]
0x1400561db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400561e0  nop
0x1400561e1  lea     rcx, [rsp+348h+var_258]; this
0x1400561e9  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x1400561ee  nop
0x1400561ef  lea     rcx, [rsp+348h+var_198]; this
0x1400561f7  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x1400561fc  nop
0x1400561fd  lea     rcx, [rsp+348h+var_298]
0x140056205  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x14005620a  mov     eax, ebx
0x14005620c  jmp     loc_1400568D4
0x140056211  mov     [rsp+348h+var_2D0], r12
0x140056216  mov     [rsp+348h+var_2D8], r12b
0x14005621b  mov     rdi, [rsp+348h+var_2B8]
0x140056223  mov     rax, [rdi]
0x140056226  mov     rbx, [rax+30h]
0x14005622a  lea     rcx, [rsp+348h+var_2D0]
0x14005622f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056234  lea     rdx, [rsp+348h+var_2D0]
0x140056239  mov     rcx, rdi
0x14005623c  mov     rax, rbx
0x14005623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056244  mov     ebx, eax
0x140056246  test    eax, eax
0x140056248  jns     loc_1400562D0
0x14005624e  mov     rcx, [rsp+348h]; this
0x140056256  mov     r9d, eax; char *
0x140056259  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140056260  mov     edx, 279h; void *
0x140056265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005626a  nop
0x14005626b  lea     rcx, [rsp+348h+var_2D0]
0x140056270  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056275  nop
0x140056276  lea     rcx, [rsp+348h+var_2B8]
0x14005627e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056283  nop
0x140056284  lea     rcx, [rsp+348h+var_2C8]
0x14005628c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056291  nop
0x140056292  lea     rcx, [rsp+348h+var_280]
0x14005629a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005629f  nop
0x1400562a0  lea     rcx, [rsp+348h+var_258]; this
0x1400562a8  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x1400562ad  nop
0x1400562ae  lea     rcx, [rsp+348h+var_198]; this
0x1400562b6  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x1400562bb  nop
0x1400562bc  lea     rcx, [rsp+348h+var_298]
0x1400562c4  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x1400562c9  mov     eax, ebx
0x1400562cb  jmp     loc_1400568D4
0x1400562d0  mov     rcx, [rsp+348h+var_2D0]
0x1400562d5  mov     rax, [rcx]
0x1400562d8  lea     rdx, [rsp+348h+var_2D8]
0x1400562dd  mov     rax, [rax+38h]
0x1400562e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400562e6  mov     ebx, eax
0x1400562e8  test    eax, eax
0x1400562ea  jns     loc_140056372
0x1400562f0  mov     rcx, [rsp+348h]; this
0x1400562f8  mov     r9d, eax; char *
0x1400562fb  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140056302  mov     edx, 27Ah; void *
0x140056307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005630c  nop
0x14005630d  lea     rcx, [rsp+348h+var_2D0]
0x140056312  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056317  nop
0x140056318  lea     rcx, [rsp+348h+var_2B8]
0x140056320  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056325  nop
0x140056326  lea     rcx, [rsp+348h+var_2C8]
0x14005632e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140056333  nop
0x140056334  lea     rcx, [rsp+348h+var_280]
0x14005633c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140056341  nop
0x140056342  lea     rcx, [rsp+348h+var_258]; this
0x14005634a  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x14005634f  nop
0x140056350  lea     rcx, [rsp+348h+var_198]; this
0x140056358  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x14005635d  nop
0x14005635e  lea     rcx, [rsp+348h+var_298]
0x140056366  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x14005636b  mov     eax, ebx
0x14005636d  jmp     loc_1400568D4
0x140056372  cmp     [rsp+348h+var_2D8], r12b
0x140056377  jz      loc_140056853
0x14005637d  mov     [rsp+348h+var_2B0], r12
0x140056385  mov     rdi, [rsp+348h+var_2D0]
0x14005638a  mov     rax, [rdi]
0x14005638d  mov     rbx, [rax+30h]
0x140056391  lea     rcx, [rsp+348h+var_2B0]
0x140056399  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005639e  lea     rdx, [rsp+348h+var_2B0]
0x1400563a6  mov     rcx, rdi
0x1400563a9  mov     rax, rbx
0x1400563ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400563b1  mov     ebx, eax
0x1400563b3  test    eax, eax
0x1400563b5  jns     loc_14005644B
0x1400563bb  mov     rcx, [rsp+348h]; this
0x1400563c3  mov     r9d, eax; char *
0x1400563c6  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400563cd  mov     edx, 27Eh; void *
0x1400563d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400563d7  nop
0x1400563d8  lea     rcx, [rsp+348h+var_2B0]
0x1400563e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400563e5  nop
0x1400563e6  lea     rcx, [rsp+348h+var_2D0]
0x1400563eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400563f0  nop
0x1400563f1  lea     rcx, [rsp+348h+var_2B8]
0x1400563f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400563fe  nop
0x1400563ff  lea     rcx, [rsp+348h+var_2C8]
0x140056407  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005640c  nop
0x14005640d  lea     rcx, [rsp+348h+var_280]
0x140056415  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005641a  nop
0x14005641b  lea     rcx, [rsp+348h+var_258]; this
0x140056423  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x140056428  nop
0x140056429  lea     rcx, [rsp+348h+var_198]; this
0x140056431  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x140056436  nop
0x140056437  lea     rcx, [rsp+348h+var_298]
0x14005643f  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140056444  mov     eax, ebx
0x140056446  jmp     loc_1400568D4
0x14005644b  mov     [rsp+348h+var_2A8], r12
0x140056453  mov     rdi, [rsp+348h+var_2B0]
0x14005645b  mov     rax, [rdi]
0x14005645e  mov     rbx, [rax+30h]
0x140056462  lea     rcx, [rsp+348h+var_2A8]
0x14005646a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14005646f  lea     rdx, [rsp+348h+var_2A8]
0x140056477  mov     rcx, rdi
0x14005647a  mov     rax, rbx
0x14005647d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056482  mov     ebx, eax
0x140056484  test    eax, eax
0x140056486  jns     loc_14005652A
0x14005648c  mov     rcx, [rsp+348h]; this
0x140056494  mov     r9d, eax; char *
0x140056497  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x14005649e  mov     edx, 280h; void *
0x1400564a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400564a8  nop
0x1400564a9  lea     rcx, [rsp+348h+var_2A8]
0x1400564b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400564b6  nop
0x1400564b7  lea     rcx, [rsp+348h+var_2B0]
0x1400564bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400564c4  nop
0x1400564c5  lea     rcx, [rsp+348h+var_2D0]
0x1400564ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400564cf  nop
0x1400564d0  lea     rcx, [rsp+348h+var_2B8]
0x1400564d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400564dd  nop
0x1400564de  lea     rcx, [rsp+348h+var_2C8]
0x1400564e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400564eb  nop
0x1400564ec  lea     rcx, [rsp+348h+var_280]
0x1400564f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400564f9  nop
0x1400564fa  lea     rcx, [rsp+348h+var_258]; this
0x140056502  call    ??1CbsLanguageFeature@@QEAA@XZ; CbsLanguageFeature::~CbsLanguageFeature(void)
0x140056507  nop
0x140056508  lea     rcx, [rsp+348h+var_198]; this
0x140056510  call    ??1UninstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::UninstallRequest::~UninstallRequest(void)
0x140056515  nop
0x140056516  lea     rcx, [rsp+348h+var_298]
0x14005651e  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140056523  mov     eax, ebx
0x140056525  jmp     loc_1400568D4
  ... truncated ...
```
