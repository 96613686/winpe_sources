# SystemSettings::DataModel::CMagnifierVoicesSetting::_RetrieveHighQualityVoiceList(void)

- ea: `0x18007c654`
- end: `0x18007cb95`
- name: `?_RetrieveHighQualityVoiceList@CMagnifierVoicesSetting@DataModel@SystemSettings@@AEAAJXZ`
- size: `1345`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CMagnifierVoicesSetting *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007cb9c`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x18001098c`
- `0x18001ecfc`
- `0x18002012c`
- `0x1800236e0`
- `0x18002373c`
- `0x18002a990`
- `0x18002be5c`
- `0x18002db80`
- `0x1800496fc`
- `0x180065f28`
- `0x18006617c`
- `0x180077fbc`
- `0x1800787dc`
- `0x1800788f4`
- `0x180078efc`
- `0x18007b930`
- `0x18007c654`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c871`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ca05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c871`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ca05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c90b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c93e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c9af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c90b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c93e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c9af`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007c6bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007c6bc`

## string_xrefs

- `0x18007cac3`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cad8`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007caed`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb02`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb17`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb2c`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb44`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb59`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb6e`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007cb82`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`
- `0x18007c700`: `com.microsoft.voice.model.1`
- `0x18007c694`: `Windows.ApplicationModel.AppExtensions.AppExtensionCatalog`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall SystemSettings::DataModel::CMagnifierVoicesSetting::_RetrieveHighQualityVoiceList(
        SystemSettings::DataModel::CMagnifierVoicesSetting *this)
{
  int ActivationFactory; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 **); // rbx
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  int v9; // eax
  unsigned int i; // esi
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rdi
  int v17; // eax
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  PCWSTR StringRawBuffer; // rax
  int v21; // eax
  PCWSTR v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  _QWORD *v25; // rdx
  PCWSTR v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  const char *v29; // r9
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-118h] BYREF
  HSTRING string; // [rsp+28h] [rbp-110h] BYREF
  __int64 v33; // [rsp+30h] [rbp-108h] BYREF
  __int64 *v34; // [rsp+38h] [rbp-100h] BYREF
  __int64 *v35; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v36; // [rsp+48h] [rbp-F0h] BYREF
  __int64 *v37; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v38; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v39; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v41[64]; // [rsp+70h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-70h]
  _BYTE v44[64]; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v38 = 0;
  v43 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.AppExtensions.AppExtensionCatalog",
    0x3Bu,
    0x3Au);
  ActivationFactory = RoGetActivationFactory(v43, &GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11, &v38);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v31);
    v37 = 0;
    v3 = v38;
    v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v38 + 48LL);
    v37 = 0;
    v43 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"com.microsoft.voice.model.1",
      0x1Cu,
      0x1Bu);
    v5 = v4(v3, v43, &v37);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
        (const char *)(unsigned int)v5,
        v31);
    v36 = 0;
    v6 = *v37;
    v36 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 48))(v37, &v36);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
        (const char *)(unsigned int)v7,
        v31);
    v35 = 0;
    v8 = v36;
    if ( (int)wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(v36) >= 0 )
      (*(void (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v8 + 64LL))(v8, &v35);
    v31 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v35 + 56))(v35, &v31);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
        (const char *)(unsigned int)v9,
        v31);
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v41);
    for ( i = 0; i < v31; ++i )
    {
      v34 = 0;
      v11 = *v35;
      v34 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v11 + 48))(v35, i, &v34);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
          (const char *)(unsigned int)v12,
          v31);
      v33 = 0;
      v13 = *v34;
      v33 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 72))(v34, &v33);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E2,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
          (const char *)(unsigned int)v14,
          v31);
      wil::com_ptr_t<Windows::ApplicationModel::IPackage,wil::err_exception_policy>::try_query<Windows::ApplicationModel::IPackage2>(
        &v33,
        &v40);
      v15 = v40;
      if ( !v40 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E5,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
          (const char *)0x8000FFFFLL,
          v31);
      string = 0;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, &string);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
          (const char *)(unsigned int)v17,
          v31);
      v18 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v19 = v18;
      v39 = v18;
      if ( v18 )
      {
        memset_0(v18, 0, 0x50u);
        *v19 = 0;
        v19[1] = 0;
        v19[2] = 0;
        v19[3] = 0;
        v19[4] = 0;
        v19[5] = 0;
        v19[6] = 0;
        v19[7] = 0;
        v19[8] = 0;
      }
      else
      {
        v19 = 0;
      }
      v39 = v19;
      if ( v19 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v19 + 3,
                StringRawBuffer,
                -1);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1F2,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
            (const char *)(unsigned int)v21,
            v31);
        v22 = WindowsGetStringRawBuffer(string, 0);
        v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v19,
                v22,
                -1);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1F3,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
            (const char *)(unsigned int)v23,
            v31);
        v39 = 0;
        v24 = *((_QWORD *)this + 38);
        if ( v24 != *((_QWORD *)this + 40)
          || (int)CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(
                    (char *)this + 296,
                    v24 + 1) >= 0 )
        {
          v25 = (_QWORD *)(*((_QWORD *)this + 37) + 8 * (*((_QWORD *)this + 38))++);
          if ( v25 )
            *v25 = v19;
        }
        v26 = WindowsGetStringRawBuffer(string, 0);
        std::wstring::wstring(v44, v26);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
          v41,
          &hstringHeader,
          v44);
        std::wstring::_Tidy_deallocate(v44);
      }
      std::unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>::~unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>(&v39);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v33);
      wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v34);
    }
    v27 = std::unordered_set<std::wstring>::unordered_set<std::wstring>(v44, v41);
    SystemSettings::DataModel::CMagnifierVoicesSingleton::SetNeuralVoices(v28, v27);
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v41);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v35);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v36);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v38);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1FC,
                           (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
                           v29);
  }
  return result;
}

```

## disassembly

```asm
0x18007c654  mov     r11, rsp
0x18007c657  mov     [r11+10h], rbx
0x18007c65b  mov     [r11+18h], rsi
0x18007c65f  push    rdi
0x18007c660  push    r14
0x18007c662  push    r15
0x18007c664  sub     rsp, 120h
0x18007c66b  mov     rax, cs:__security_cookie
0x18007c672  xor     rax, rsp
0x18007c675  mov     [rsp+138h+var_28], rax
0x18007c67d  mov     r14, rcx
0x18007c680  xor     r15d, r15d
0x18007c683  mov     [rsp+138h+var_E0], r15
0x18007c688  mov     [r11-70h], r15
0x18007c68c  lea     r9d, [r15+3Ah]; unsigned int
0x18007c690  lea     r8d, [r15+3Bh]; unsigned int
0x18007c694  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppExtensions_AppExtensionCatalog@@3QBGB; "Windows.ApplicationModel.AppExtensions."...
0x18007c69b  lea     rcx, [r11-88h]; hstringHeader
0x18007c6a2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007c6a7  nop
0x18007c6a8  lea     r8, [rsp+138h+var_E0]
0x18007c6ad  lea     rdx, _GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11
0x18007c6b4  mov     rcx, [rsp+138h+var_70]
0x18007c6bc  call    cs:__imp_RoGetActivationFactory
0x18007c6c3  nop     dword ptr [rax+rax+00h]
0x18007c6c8  mov     rcx, [rsp+138h]; this
0x18007c6d0  test    eax, eax
0x18007c6d2  js      loc_18007CAC0
0x18007c6d8  mov     [rsp+138h+var_E8], r15
0x18007c6dd  mov     rdi, [rsp+138h+var_E0]
0x18007c6e2  mov     rax, [rdi]
0x18007c6e5  mov     rbx, [rax+30h]
0x18007c6e9  mov     [rsp+138h+var_E8], r15
0x18007c6ee  mov     [rsp+138h+var_70], r15
0x18007c6f6  mov     r9d, 1Bh; unsigned int
0x18007c6fc  lea     r8d, [r9+1]; unsigned int
0x18007c700  lea     rdx, aComMicrosoftVo; "com.microsoft.voice.model.1"
0x18007c707  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18007c70f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007c714  nop
0x18007c715  lea     r8, [rsp+138h+var_E8]
0x18007c71a  mov     rdx, [rsp+138h+var_70]
0x18007c722  mov     rcx, rdi
0x18007c725  mov     rax, rbx
0x18007c728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c72d  mov     rcx, [rsp+138h]; this
0x18007c735  test    eax, eax
0x18007c737  js      loc_18007CAD5
0x18007c73d  mov     [rsp+138h+var_F0], r15
0x18007c742  mov     rcx, [rsp+138h+var_E8]
0x18007c747  mov     rax, [rcx]
0x18007c74a  mov     [rsp+138h+var_F0], r15
0x18007c74f  lea     rdx, [rsp+138h+var_F0]
0x18007c754  mov     rax, [rax+30h]
0x18007c758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c75d  mov     rcx, [rsp+138h]; this
0x18007c765  test    eax, eax
0x18007c767  js      loc_18007CAEA
0x18007c76d  mov     [rsp+138h+var_F8], r15
0x18007c772  mov     rbx, [rsp+138h+var_F0]
0x18007c777  mov     rcx, rbx
0x18007c77a  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18007c77f  test    eax, eax
0x18007c781  js      short loc_18007C798
0x18007c783  mov     rax, [rbx]
0x18007c786  lea     rdx, [rsp+138h+var_F8]
0x18007c78b  mov     rcx, rbx
0x18007c78e  mov     rax, [rax+40h]
0x18007c792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c797  nop
0x18007c798  mov     [rsp+138h+var_118], r15d; int
0x18007c79d  mov     rcx, [rsp+138h+var_F8]
0x18007c7a2  mov     rax, [rcx]
0x18007c7a5  lea     rdx, [rsp+138h+var_118]
0x18007c7aa  mov     rax, [rax+38h]
0x18007c7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c7b3  mov     rcx, [rsp+138h]; this
0x18007c7bb  test    eax, eax
0x18007c7bd  js      loc_18007CAFF
0x18007c7c3  lea     rcx, [rsp+138h+var_C8]
0x18007c7c8  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18007c7cd  nop
0x18007c7ce  mov     esi, r15d
0x18007c7d1  cmp     esi, [rsp+138h+var_118]
0x18007c7d5  jnb     loc_18007CA3D
0x18007c7db  mov     [rsp+138h+var_100], r15
0x18007c7e0  mov     rcx, [rsp+138h+var_F8]
0x18007c7e5  mov     rax, [rcx]
0x18007c7e8  mov     [rsp+138h+var_100], r15
0x18007c7ed  lea     r8, [rsp+138h+var_100]
0x18007c7f2  mov     edx, esi
0x18007c7f4  mov     rax, [rax+30h]
0x18007c7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c7fd  mov     rcx, [rsp+138h]; this
0x18007c805  test    eax, eax
0x18007c807  js      loc_18007CB14
0x18007c80d  mov     [rsp+138h+var_108], r15
0x18007c812  mov     rcx, [rsp+138h+var_100]
0x18007c817  mov     rax, [rcx]
0x18007c81a  mov     [rsp+138h+var_108], r15
0x18007c81f  lea     rdx, [rsp+138h+var_108]
0x18007c824  mov     rax, [rax+48h]
0x18007c828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c82d  mov     rcx, [rsp+138h]; this
0x18007c835  test    eax, eax
0x18007c837  js      loc_18007CB29
0x18007c83d  lea     rdx, [rsp+138h+var_D0]
0x18007c842  lea     rcx, [rsp+138h+var_108]
0x18007c847  call    ??$try_query@UIPackage2@ApplicationModel@Windows@@@?$com_ptr_t@UIPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackage2@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::ApplicationModel::IPackage,wil::err_exception_policy>::try_query<Windows::ApplicationModel::IPackage2>(void)
0x18007c84c  nop
0x18007c84d  mov     rcx, [rsp+138h]; this
0x18007c855  mov     rbx, [rsp+138h+var_D0]
0x18007c85a  test    rbx, rbx
0x18007c85d  jz      loc_18007CB3E
0x18007c863  mov     [rsp+138h+string], r15
0x18007c868  mov     rax, [rbx]
0x18007c86b  mov     rdi, [rax+30h]
0x18007c86f  xor     ecx, ecx; string
0x18007c871  call    cs:__imp_WindowsDeleteString
0x18007c878  nop     dword ptr [rax+rax+00h]
0x18007c87d  mov     [rsp+138h+string], r15
0x18007c882  lea     rdx, [rsp+138h+string]
0x18007c887  mov     rcx, rbx
0x18007c88a  mov     rax, rdi
0x18007c88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c892  mov     rcx, [rsp+138h]; this
0x18007c89a  test    eax, eax
0x18007c89c  js      loc_18007CB56
0x18007c8a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007c8a9  mov     ecx, 50h ; 'P'; unsigned __int64
0x18007c8ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007c8b3  mov     rbx, rax
0x18007c8b6  mov     [rsp+138h+var_D8], rax
0x18007c8bb  test    rax, rax
0x18007c8be  jz      short loc_18007C8F3
0x18007c8c0  xor     edx, edx; Val
0x18007c8c2  lea     r8d, [rdx+50h]; Size
0x18007c8c6  mov     rcx, rax; void *
0x18007c8c9  call    memset_0
0x18007c8ce  mov     [rbx], r15
0x18007c8d1  mov     [rbx+8], r15
0x18007c8d5  mov     [rbx+10h], r15
0x18007c8d9  mov     [rbx+18h], r15
0x18007c8dd  mov     [rbx+20h], r15
0x18007c8e1  mov     [rbx+28h], r15
0x18007c8e5  mov     [rbx+30h], r15
0x18007c8e9  mov     [rbx+38h], r15
0x18007c8ed  mov     [rbx+40h], r15
0x18007c8f1  jmp     short loc_18007C8F6
0x18007c8f3  mov     rbx, r15
0x18007c8f6  mov     [rsp+138h+var_D8], rbx
0x18007c8fb  test    rbx, rbx
0x18007c8fe  jz      loc_18007C9F5
0x18007c904  xor     edx, edx; length
0x18007c906  mov     rcx, [rsp+138h+string]; string
0x18007c90b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c912  nop     dword ptr [rax+rax+00h]
0x18007c917  lea     rcx, [rbx+18h]
0x18007c91b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007c91f  mov     rdx, rax
0x18007c922  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18007c927  mov     rcx, [rsp+138h]; this
0x18007c92f  test    eax, eax
0x18007c931  js      loc_18007CB6B
0x18007c937  xor     edx, edx; length
0x18007c939  mov     rcx, [rsp+138h+string]; string
0x18007c93e  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c945  nop     dword ptr [rax+rax+00h]
0x18007c94a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007c94e  mov     rdx, rax
0x18007c951  mov     rcx, rbx
0x18007c954  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18007c959  mov     rcx, [rsp+138h]; this
0x18007c961  test    eax, eax
0x18007c963  js      loc_18007CB7F
0x18007c969  lea     rdi, [r14+128h]
0x18007c970  mov     [rsp+138h+var_D8], r15
0x18007c975  mov     rdx, [rdi+8]
0x18007c979  cmp     rdx, [rdi+18h]
0x18007c97d  jnz     short loc_18007C98E
0x18007c97f  inc     rdx
0x18007c982  mov     rcx, rdi
0x18007c985  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18007c98a  test    eax, eax
0x18007c98c  js      short loc_18007C9A8
0x18007c98e  inc     qword ptr [rdi+8]
0x18007c992  mov     rdx, [rdi+8]
0x18007c996  mov     rax, [rdi]
0x18007c999  dec     rdx
0x18007c99c  lea     rdx, [rax+rdx*8]
0x18007c9a0  test    rdx, rdx
0x18007c9a3  jz      short loc_18007C9A8
0x18007c9a5  mov     [rdx], rbx
0x18007c9a8  xor     edx, edx; length
0x18007c9aa  mov     rcx, [rsp+138h+string]; string
0x18007c9af  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c9b6  nop     dword ptr [rax+rax+00h]
0x18007c9bb  mov     rdx, rax
0x18007c9be  lea     rcx, [rsp+138h+var_68]
0x18007c9c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007c9cb  nop
0x18007c9cc  lea     r8, [rsp+138h+var_68]
0x18007c9d4  lea     rdx, [rsp+138h+hstringHeader]
0x18007c9dc  lea     rcx, [rsp+138h+var_C8]
0x18007c9e1  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x18007c9e6  nop
0x18007c9e7  lea     rcx, [rsp+138h+var_68]
0x18007c9ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007c9f4  nop
0x18007c9f5  lea     rcx, [rsp+138h+var_D8]
0x18007c9fa  call    ??1?$unique_ptr@USSpeechVoice@CMagnifierVoicesSetting@DataModel@SystemSettings@@U?$default_delete@USSpeechVoice@CMagnifierVoicesSetting@DataModel@SystemSettings@@@std@@@std@@QEAA@XZ; std::unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>::~unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>(void)
0x18007c9ff  nop
0x18007ca00  mov     rcx, [rsp+138h+string]; string
0x18007ca05  call    cs:__imp_WindowsDeleteString
0x18007ca0c  nop     dword ptr [rax+rax+00h]
0x18007ca11  mov     [rsp+138h+string], r15
0x18007ca16  lea     rcx, [rsp+138h+var_D0]
0x18007ca1b  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca20  nop
0x18007ca21  lea     rcx, [rsp+138h+var_108]
0x18007ca26  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca2b  nop
0x18007ca2c  lea     rcx, [rsp+138h+var_100]
0x18007ca31  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca36  inc     esi
0x18007ca38  jmp     loc_18007C7D1
0x18007ca3d  lea     rdx, [rsp+138h+var_C8]
0x18007ca42  lea     rcx, [rsp+138h+var_68]
0x18007ca4a  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::unordered_set<std::wstring>::unordered_set<std::wstring>(std::unordered_set<std::wstring> const &)
0x18007ca4f  mov     rdx, rax
0x18007ca52  call    ?SetNeuralVoices@CMagnifierVoicesSingleton@DataModel@SystemSettings@@QEAAXV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SystemSettings::DataModel::CMagnifierVoicesSingleton::SetNeuralVoices(std::unordered_set<std::wstring>)
0x18007ca57  nop
0x18007ca58  lea     rcx, [rsp+138h+var_C8]
0x18007ca5d  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18007ca62  nop
0x18007ca63  lea     rcx, [rsp+138h+var_F8]
0x18007ca68  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca6d  nop
0x18007ca6e  lea     rcx, [rsp+138h+var_F0]
0x18007ca73  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca78  nop
0x18007ca79  lea     rcx, [rsp+138h+var_E8]
0x18007ca7e  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca83  nop
0x18007ca84  lea     rcx, [rsp+138h+var_E0]
0x18007ca89  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x18007ca8e  xor     eax, eax
0x18007ca90  jmp     short loc_18007CA96
0x18007ca92  mov     eax, [rsp+138h+var_118]
0x18007ca96  mov     rcx, [rsp+138h+var_28]
0x18007ca9e  xor     rcx, rsp; StackCookie
0x18007caa1  call    __security_check_cookie
0x18007caa6  lea     r11, [rsp+138h+var_18]
0x18007caae  mov     rbx, [r11+28h]
0x18007cab2  mov     rsi, [r11+30h]
0x18007cab6  mov     rsp, r11
0x18007cab9  pop     r15
0x18007cabb  pop     r14
0x18007cabd  pop     rdi
0x18007cabe  retn
0x18007cac0  mov     r9d, eax; char *
0x18007cac3  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007caca  mov     edx, 1C6h; void *
0x18007cacf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cad5  mov     r9d, eax; char *
0x18007cad8  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cadf  mov     edx, 1CAh; void *
0x18007cae4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007caea  mov     r9d, eax; char *
0x18007caed  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007caf4  mov     edx, 1CEh; void *
0x18007caf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007caff  mov     r9d, eax; char *
0x18007cb02  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb09  mov     edx, 1D5h; void *
0x18007cb0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb14  mov     r9d, eax; char *
0x18007cb17  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb1e  mov     edx, 1DFh; void *
0x18007cb23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb29  mov     r9d, eax; char *
0x18007cb2c  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb33  mov     edx, 1E2h; void *
0x18007cb38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb3e  mov     r9d, 8000FFFFh; char *
0x18007cb44  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb4b  mov     edx, 1E5h; void *
0x18007cb50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb56  mov     r9d, eax; char *
0x18007cb59  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb60  mov     edx, 1ECh; void *
0x18007cb65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb6b  mov     r9d, eax; char *
0x18007cb6e  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb75  mov     edx, 1F2h; void *
0x18007cb7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb7f  mov     r9d, eax; char *
0x18007cb82  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007cb89  mov     edx, 1F3h; void *
0x18007cb8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
