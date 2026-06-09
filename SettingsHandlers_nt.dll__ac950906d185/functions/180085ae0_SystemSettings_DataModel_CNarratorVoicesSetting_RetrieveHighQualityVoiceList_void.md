# SystemSettings::DataModel::CNarratorVoicesSetting::_RetrieveHighQualityVoiceList(void)

- ea: `0x180085ae0`
- end: `0x180085ff2`
- name: `?_RetrieveHighQualityVoiceList@CNarratorVoicesSetting@DataModel@SystemSettings@@AEAAJXZ`
- size: `1298`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CNarratorVoicesSetting *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180085ff8`

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
- `0x180084800`
- `0x180085ae0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085d73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085d73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085ee1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085b48`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085b48`

## string_xrefs

- `0x180085b20`: `Windows.ApplicationModel.AppExtensions.AppExtensionCatalog`
- `0x180085b63`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085bd9`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085c1a`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085c81`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085cdb`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085d1b`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085d54`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085da3`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085e48`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085e8a`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`
- `0x180085b9d`: `com.microsoft.voice.model.1`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall SystemSettings::DataModel::CNarratorVoicesSetting::_RetrieveHighQualityVoiceList(
        SystemSettings::DataModel::CNarratorVoicesSetting *this)
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
  int v30; // [rsp+20h] [rbp-118h] BYREF
  HSTRING string; // [rsp+28h] [rbp-110h] BYREF
  __int64 v32; // [rsp+30h] [rbp-108h] BYREF
  __int64 *v33; // [rsp+38h] [rbp-100h] BYREF
  __int64 *v34; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-F0h] BYREF
  __int64 *v36; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v38; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v39; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v40[64]; // [rsp+70h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-70h]
  _BYTE v43[64]; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v37 = 0;
  v42 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.AppExtensions.AppExtensionCatalog",
    0x3Bu,
    0x3Au);
  ActivationFactory = RoGetActivationFactory(v42, &GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11, &v37);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v30);
  v36 = 0;
  v3 = v37;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v37 + 48LL);
  v36 = 0;
  v42 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"com.microsoft.voice.model.1",
    0x1Cu,
    0x1Bu);
  v5 = v4(v3, v42, &v36);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)v5,
      v30);
  v35 = 0;
  v6 = *v36;
  v35 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 48))(v36, &v35);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)v7,
      v30);
  v34 = 0;
  v8 = v35;
  if ( (int)wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(v35) >= 0 )
    (*(void (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v8 + 64LL))(v8, &v34);
  v30 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v34 + 56))(v34, &v30);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)v9,
      v30);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v40);
  for ( i = 0; i < v30; ++i )
  {
    v33 = 0;
    v11 = *v34;
    v33 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v11 + 48))(v34, i, &v33);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2BE,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
        (const char *)(unsigned int)v12,
        v30);
    v32 = 0;
    v13 = *v33;
    v32 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 72))(v33, &v32);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
        (const char *)(unsigned int)v14,
        v30);
    wil::com_ptr_t<Windows::ApplicationModel::IPackage,wil::err_exception_policy>::try_query<Windows::ApplicationModel::IPackage2>(
      &v32,
      &v39);
    v15 = v39;
    if ( !v39 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C4,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
        (const char *)0x8000FFFFLL,
        v30);
    string = 0;
    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v17 = v16(v15, &string);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
        (const char *)(unsigned int)v17,
        v30);
    v18 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v18;
    v38 = v18;
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
    v38 = v19;
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
          (void *)0x2D1,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
          (const char *)(unsigned int)v21,
          v30);
      v22 = WindowsGetStringRawBuffer(string, 0);
      v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v19,
              v22,
              -1);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D2,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
          (const char *)(unsigned int)v23,
          v30);
      v38 = 0;
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
      std::wstring::wstring(v43, v26);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        v40,
        &hstringHeader,
        v43);
      std::wstring::_Tidy_deallocate(v43);
    }
    std::unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>::~unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>(&v38);
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v39);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v33);
  }
  v27 = std::unordered_set<std::wstring>::unordered_set<std::wstring>(v43, v40);
  SystemSettings::DataModel::CNarratorVoicesSingleton::SetNeuralVoices(v28, v27);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v40);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v35);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v36);
  wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v37);
  return 0;
}

```

## disassembly

```asm
0x180085ae0  mov     r11, rsp
0x180085ae3  mov     [r11+10h], rbx
0x180085ae7  mov     [r11+18h], rsi
0x180085aeb  push    rdi
0x180085aec  push    r14
0x180085aee  push    r15
0x180085af0  sub     rsp, 120h
0x180085af7  mov     rax, cs:__security_cookie
0x180085afe  xor     rax, rsp
0x180085b01  mov     [rsp+138h+var_28], rax
0x180085b09  mov     r14, rcx
0x180085b0c  xor     r15d, r15d
0x180085b0f  mov     [rsp+138h+var_E0], r15
0x180085b14  mov     [r11-70h], r15
0x180085b18  lea     r9d, [r15+3Ah]; unsigned int
0x180085b1c  lea     r8d, [r15+3Bh]; unsigned int
0x180085b20  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_AppExtensions_AppExtensionCatalog@@3QBGB; "Windows.ApplicationModel.AppExtensions."...
0x180085b27  lea     rcx, [r11-88h]; hstringHeader
0x180085b2e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085b33  nop
0x180085b34  lea     r8, [rsp+138h+var_E0]
0x180085b39  lea     rdx, _GUID_3c36668a_5f18_4f0b_9ce5_cab61d196f11
0x180085b40  mov     rcx, [rsp+138h+var_70]
0x180085b48  call    cs:__imp_RoGetActivationFactory
0x180085b4f  nop     dword ptr [rax+rax+00h]
0x180085b54  mov     rcx, [rsp+138h]; this
0x180085b5c  test    eax, eax
0x180085b5e  jns     short loc_180085B75
0x180085b60  mov     r9d, eax; char *
0x180085b63  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085b6a  mov     edx, 2A5h; void *
0x180085b6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085b75  mov     [rsp+138h+var_E8], r15
0x180085b7a  mov     rdi, [rsp+138h+var_E0]
0x180085b7f  mov     rax, [rdi]
0x180085b82  mov     rbx, [rax+30h]
0x180085b86  mov     [rsp+138h+var_E8], r15
0x180085b8b  mov     [rsp+138h+var_70], r15
0x180085b93  mov     r9d, 1Bh; unsigned int
0x180085b99  lea     r8d, [r9+1]; unsigned int
0x180085b9d  lea     rdx, aComMicrosoftVo_0; "com.microsoft.voice.model.1"
0x180085ba4  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x180085bac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180085bb1  nop
0x180085bb2  lea     r8, [rsp+138h+var_E8]
0x180085bb7  mov     rdx, [rsp+138h+var_70]
0x180085bbf  mov     rcx, rdi
0x180085bc2  mov     rax, rbx
0x180085bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bca  mov     rcx, [rsp+138h]; this
0x180085bd2  test    eax, eax
0x180085bd4  jns     short loc_180085BEB
0x180085bd6  mov     r9d, eax; char *
0x180085bd9  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085be0  mov     edx, 2A9h; void *
0x180085be5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085beb  mov     [rsp+138h+var_F0], r15
0x180085bf0  mov     rcx, [rsp+138h+var_E8]
0x180085bf5  mov     rax, [rcx]
0x180085bf8  mov     [rsp+138h+var_F0], r15
0x180085bfd  lea     rdx, [rsp+138h+var_F0]
0x180085c02  mov     rax, [rax+30h]
0x180085c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c0b  mov     rcx, [rsp+138h]; this
0x180085c13  test    eax, eax
0x180085c15  jns     short loc_180085C2C
0x180085c17  mov     r9d, eax; char *
0x180085c1a  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085c21  mov     edx, 2ADh; void *
0x180085c26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085c2c  mov     [rsp+138h+var_F8], r15
0x180085c31  mov     rbx, [rsp+138h+var_F0]
0x180085c36  mov     rcx, rbx
0x180085c39  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180085c3e  test    eax, eax
0x180085c40  js      short loc_180085C57
0x180085c42  mov     rax, [rbx]
0x180085c45  lea     rdx, [rsp+138h+var_F8]
0x180085c4a  mov     rcx, rbx
0x180085c4d  mov     rax, [rax+40h]
0x180085c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c56  nop
0x180085c57  mov     [rsp+138h+var_118], r15d; int
0x180085c5c  mov     rcx, [rsp+138h+var_F8]
0x180085c61  mov     rax, [rcx]
0x180085c64  lea     rdx, [rsp+138h+var_118]
0x180085c69  mov     rax, [rax+38h]
0x180085c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c72  mov     rcx, [rsp+138h]; this
0x180085c7a  test    eax, eax
0x180085c7c  jns     short loc_180085C92
0x180085c7e  mov     r9d, eax; char *
0x180085c81  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085c88  mov     edx, 2B4h; void *
0x180085c8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085c92  lea     rcx, [rsp+138h+var_C8]
0x180085c97  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180085c9c  nop
0x180085c9d  mov     esi, r15d
0x180085ca0  cmp     esi, [rsp+138h+var_118]
0x180085ca4  jnb     loc_180085F6F
0x180085caa  mov     [rsp+138h+var_100], r15
0x180085caf  mov     rcx, [rsp+138h+var_F8]
0x180085cb4  mov     rax, [rcx]
0x180085cb7  mov     [rsp+138h+var_100], r15
0x180085cbc  lea     r8, [rsp+138h+var_100]
0x180085cc1  mov     edx, esi
0x180085cc3  mov     rax, [rax+30h]
0x180085cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ccc  mov     rcx, [rsp+138h]; this
0x180085cd4  test    eax, eax
0x180085cd6  jns     short loc_180085CEC
0x180085cd8  mov     r9d, eax; char *
0x180085cdb  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085ce2  mov     edx, 2BEh; void *
0x180085ce7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085cec  mov     [rsp+138h+var_108], r15
0x180085cf1  mov     rcx, [rsp+138h+var_100]
0x180085cf6  mov     rax, [rcx]
0x180085cf9  mov     [rsp+138h+var_108], r15
0x180085cfe  lea     rdx, [rsp+138h+var_108]
0x180085d03  mov     rax, [rax+48h]
0x180085d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d0c  mov     rcx, [rsp+138h]; this
0x180085d14  test    eax, eax
0x180085d16  jns     short loc_180085D2C
0x180085d18  mov     r9d, eax; char *
0x180085d1b  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085d22  mov     edx, 2C1h; void *
0x180085d27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085d2c  lea     rdx, [rsp+138h+var_D0]
0x180085d31  lea     rcx, [rsp+138h+var_108]
0x180085d36  call    ??$try_query@UIPackage2@ApplicationModel@Windows@@@?$com_ptr_t@UIPackage@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackage2@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::ApplicationModel::IPackage,wil::err_exception_policy>::try_query<Windows::ApplicationModel::IPackage2>(void)
0x180085d3b  nop
0x180085d3c  mov     rcx, [rsp+138h]; this
0x180085d44  mov     rbx, [rsp+138h+var_D0]
0x180085d49  test    rbx, rbx
0x180085d4c  jnz     short loc_180085D65
0x180085d4e  mov     r9d, 8000FFFFh; char *
0x180085d54  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085d5b  mov     edx, 2C4h; void *
0x180085d60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085d65  mov     [rsp+138h+string], r15
0x180085d6a  mov     rax, [rbx]
0x180085d6d  mov     rdi, [rax+30h]
0x180085d71  xor     ecx, ecx; string
0x180085d73  call    cs:__imp_WindowsDeleteString
0x180085d7a  nop     dword ptr [rax+rax+00h]
0x180085d7f  mov     [rsp+138h+string], r15
0x180085d84  lea     rdx, [rsp+138h+string]
0x180085d89  mov     rcx, rbx
0x180085d8c  mov     rax, rdi
0x180085d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d94  mov     rcx, [rsp+138h]; this
0x180085d9c  test    eax, eax
0x180085d9e  jns     short loc_180085DB4
0x180085da0  mov     r9d, eax; char *
0x180085da3  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085daa  mov     edx, 2CBh; void *
0x180085daf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085db4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085dbb  mov     ecx, 50h ; 'P'; unsigned __int64
0x180085dc0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180085dc5  mov     rbx, rax
0x180085dc8  mov     [rsp+138h+var_D8], rax
0x180085dcd  test    rax, rax
0x180085dd0  jz      short loc_180085E05
0x180085dd2  xor     edx, edx; Val
0x180085dd4  lea     r8d, [rdx+50h]; Size
0x180085dd8  mov     rcx, rax; void *
0x180085ddb  call    memset_0
0x180085de0  mov     [rbx], r15
0x180085de3  mov     [rbx+8], r15
0x180085de7  mov     [rbx+10h], r15
0x180085deb  mov     [rbx+18h], r15
0x180085def  mov     [rbx+20h], r15
0x180085df3  mov     [rbx+28h], r15
0x180085df7  mov     [rbx+30h], r15
0x180085dfb  mov     [rbx+38h], r15
0x180085dff  mov     [rbx+40h], r15
0x180085e03  jmp     short loc_180085E08
0x180085e05  mov     rbx, r15
0x180085e08  mov     [rsp+138h+var_D8], rbx
0x180085e0d  test    rbx, rbx
0x180085e10  jz      loc_180085F27
0x180085e16  xor     edx, edx; length
0x180085e18  mov     rcx, [rsp+138h+string]; string
0x180085e1d  call    cs:__imp_WindowsGetStringRawBuffer
0x180085e24  nop     dword ptr [rax+rax+00h]
0x180085e29  lea     rcx, [rbx+18h]
0x180085e2d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180085e31  mov     rdx, rax
0x180085e34  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180085e39  mov     rcx, [rsp+138h]; this
0x180085e41  test    eax, eax
0x180085e43  jns     short loc_180085E59
0x180085e45  mov     r9d, eax; char *
0x180085e48  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085e4f  mov     edx, 2D1h; void *
0x180085e54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085e59  xor     edx, edx; length
0x180085e5b  mov     rcx, [rsp+138h+string]; string
0x180085e60  call    cs:__imp_WindowsGetStringRawBuffer
0x180085e67  nop     dword ptr [rax+rax+00h]
0x180085e6c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180085e70  mov     rdx, rax
0x180085e73  mov     rcx, rbx
0x180085e76  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180085e7b  mov     rcx, [rsp+138h]; this
0x180085e83  test    eax, eax
0x180085e85  jns     short loc_180085E9B
0x180085e87  mov     r9d, eax; char *
0x180085e8a  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180085e91  mov     edx, 2D2h; void *
0x180085e96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085e9b  lea     rdi, [r14+128h]
0x180085ea2  mov     [rsp+138h+var_D8], r15
0x180085ea7  mov     rdx, [rdi+8]
0x180085eab  cmp     rdx, [rdi+18h]
0x180085eaf  jnz     short loc_180085EC0
0x180085eb1  inc     rdx
0x180085eb4  mov     rcx, rdi
0x180085eb7  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180085ebc  test    eax, eax
0x180085ebe  js      short loc_180085EDA
0x180085ec0  inc     qword ptr [rdi+8]
0x180085ec4  mov     rdx, [rdi+8]
0x180085ec8  mov     rax, [rdi]
0x180085ecb  dec     rdx
0x180085ece  lea     rdx, [rax+rdx*8]
0x180085ed2  test    rdx, rdx
0x180085ed5  jz      short loc_180085EDA
0x180085ed7  mov     [rdx], rbx
0x180085eda  xor     edx, edx; length
0x180085edc  mov     rcx, [rsp+138h+string]; string
0x180085ee1  call    cs:__imp_WindowsGetStringRawBuffer
0x180085ee8  nop     dword ptr [rax+rax+00h]
0x180085eed  mov     rdx, rax
0x180085ef0  lea     rcx, [rsp+138h+var_68]
0x180085ef8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085efd  nop
0x180085efe  lea     r8, [rsp+138h+var_68]
0x180085f06  lea     rdx, [rsp+138h+hstringHeader]
0x180085f0e  lea     rcx, [rsp+138h+var_C8]
0x180085f13  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x180085f18  nop
0x180085f19  lea     rcx, [rsp+138h+var_68]
0x180085f21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085f26  nop
0x180085f27  lea     rcx, [rsp+138h+var_D8]
0x180085f2c  call    ??1?$unique_ptr@USSpeechVoice@CMagnifierVoicesSetting@DataModel@SystemSettings@@U?$default_delete@USSpeechVoice@CMagnifierVoicesSetting@DataModel@SystemSettings@@@std@@@std@@QEAA@XZ; std::unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>::~unique_ptr<SystemSettings::DataModel::CMagnifierVoicesSetting::SSpeechVoice>(void)
0x180085f31  nop
0x180085f32  mov     rcx, [rsp+138h+string]; string
0x180085f37  call    cs:__imp_WindowsDeleteString
0x180085f3e  nop     dword ptr [rax+rax+00h]
0x180085f43  mov     [rsp+138h+string], r15
0x180085f48  lea     rcx, [rsp+138h+var_D0]
0x180085f4d  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085f52  nop
0x180085f53  lea     rcx, [rsp+138h+var_108]
0x180085f58  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085f5d  nop
0x180085f5e  lea     rcx, [rsp+138h+var_100]
0x180085f63  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085f68  inc     esi
0x180085f6a  jmp     loc_180085CA0
0x180085f6f  lea     rdx, [rsp+138h+var_C8]
0x180085f74  lea     rcx, [rsp+138h+var_68]
0x180085f7c  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::unordered_set<std::wstring>::unordered_set<std::wstring>(std::unordered_set<std::wstring> const &)
0x180085f81  mov     rdx, rax
0x180085f84  call    ?SetNeuralVoices@CNarratorVoicesSingleton@DataModel@SystemSettings@@QEAAXV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SystemSettings::DataModel::CNarratorVoicesSingleton::SetNeuralVoices(std::unordered_set<std::wstring>)
0x180085f89  nop
0x180085f8a  lea     rcx, [rsp+138h+var_C8]
0x180085f8f  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180085f94  nop
0x180085f95  lea     rcx, [rsp+138h+var_F8]
0x180085f9a  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085f9f  nop
0x180085fa0  lea     rcx, [rsp+138h+var_F0]
0x180085fa5  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085faa  nop
0x180085fab  lea     rcx, [rsp+138h+var_E8]
0x180085fb0  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085fb5  nop
0x180085fb6  lea     rcx, [rsp+138h+var_E0]
0x180085fbb  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180085fc0  xor     eax, eax
0x180085fc2  jmp     short loc_180085FC8
0x180085fc4  mov     eax, [rsp+138h+var_118]
0x180085fc8  mov     rcx, [rsp+138h+var_28]
0x180085fd0  xor     rcx, rsp; StackCookie
0x180085fd3  call    __security_check_cookie
0x180085fd8  lea     r11, [rsp+138h+var_18]
0x180085fe0  mov     rbx, [r11+28h]
0x180085fe4  mov     rsi, [r11+30h]
0x180085fe8  mov     rsp, r11
0x180085feb  pop     r15
0x180085fed  pop     r14
0x180085fef  pop     rdi
0x180085ff0  retn
  ... truncated ...
```
