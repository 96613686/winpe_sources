# AppV::Client::Service::Impl::SettingCacheT<AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings(std::shared_ptr<std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>>>)

- ea: `0x140058258`
- end: `0x140058b93`
- name: `?LoadSettings@?$SettingCacheT@USettingCacheEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAXV?$shared_ptr@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@2@@std@@@std@@@Z`
- size: `2363`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x140057aa0`
- `0x140059880`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x1400165b4`
- `0x14001f0d0`
- `0x140038eb8`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x140042454`
- `0x1400424d8`
- `0x140042a88`
- `0x140042bc0`
- `0x140042c74`
- `0x140042d28`
- `0x140045328`
- `0x140055b84`
- `0x140055df4`
- `0x140058258`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400582b1`
- `KERNEL32!GetLastError` at `0x140058a55`
- `KERNEL32!GetLastError` at `0x1400582b1`
- `KERNEL32!GetLastError` at `0x140058a55`
- `USERENV!LeaveCriticalPolicySection` at `0x140058a47`
- `USERENV!LeaveCriticalPolicySection` at `0x140058a47`
- `USERENV!EnterCriticalPolicySection` at `0x140058298`
- `USERENV!EnterCriticalPolicySection` at `0x140058298`

## string_xrefs

- `0x14005832c`: `RegistryNotify`
- `0x1400585d5`: `RegistryNotify`
- `0x1400587cd`: `RegistryNotify`
- `0x1400589bb`: `RegistryNotify`
- `0x140058ad7`: `RegistryNotify`
- `0x1400582bb`: `AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings`
- `0x14005854c`: `AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings`
- `0x140058744`: `AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings`
- `0x140058932`: `AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings`
- `0x140058a5f`: `AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings`
- `0x14005857d`: `Failed loading configuration value '%2%' with error code: %1%`
- `0x140058775`: `Failed loading configuration value '%2%' with error code: %1%`
- `0x140058963`: `Failed loading configuration value '%2%' with error code: %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall AppV::Client::Service::Impl::SettingCacheT<AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings(
        __int64 a1,
        __int64 a2)
{
  HANDLE v3; // r12
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 i; // rbx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 *v13; // r14
  _DWORD *v14; // rsi
  _DWORD *v15; // rdi
  volatile signed __int32 *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 ConfigurationValue; // rdi
  __int64 *v22; // r14
  _DWORD *v23; // rsi
  _DWORD *v24; // rdi
  volatile signed __int32 *v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rdi
  __int64 *v31; // r14
  _DWORD *v32; // rsi
  int v33; // ecx
  _DWORD *v34; // rdi
  volatile signed __int32 *v35; // rdi
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rbx
  volatile signed __int32 *v44; // rbx
  char v45[8]; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD *v46; // [rsp+28h] [rbp-D8h] BYREF
  DWORD LastError; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v49; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h]
  __int128 v51; // [rsp+50h] [rbp-B0h]
  __int128 v52; // [rsp+60h] [rbp-A0h]
  __int128 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  _DWORD *v55; // [rsp+88h] [rbp-78h]
  _DWORD *v56; // [rsp+90h] [rbp-70h]
  _BYTE v57[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v58[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v59[16]; // [rsp+B8h] [rbp-48h] BYREF
  char *v60[2]; // [rsp+C8h] [rbp-38h] BYREF
  char *v61; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v62; // [rsp+E8h] [rbp-18h]
  volatile signed __int32 *v63; // [rsp+F0h] [rbp-10h]
  __int128 v64; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h]
  __int128 v67; // [rsp+118h] [rbp+18h] BYREF
  __int64 v68; // [rsp+128h] [rbp+28h]
  __int64 v69; // [rsp+130h] [rbp+30h]
  int v70; // [rsp+138h] [rbp+38h]
  __int128 v71; // [rsp+140h] [rbp+40h] BYREF
  __int64 v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]
  __int128 v74; // [rsp+160h] [rbp+60h] BYREF
  __int64 v75; // [rsp+170h] [rbp+70h]
  __int64 v76; // [rsp+178h] [rbp+78h]
  _QWORD v77[2]; // [rsp+180h] [rbp+80h] BYREF
  char *v78[4]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v79[112]; // [rsp+1B0h] [rbp+B0h] BYREF

  v54 = a2;
  LastError = 0;
  v3 = EnterCriticalPolicySection(1);
  if ( !v3 )
  {
    LastError = GetLastError();
    std::string::string(
      &v67,
      "AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings");
    v70 = 207;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v4);
    v71 = 0;
    v72 = 0;
    v73 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v71,
      L"Failed to enter critical policy section with error: %1% \n",
      0x39u);
    v6 = AppV::Log::fmt(v5, v60, &v71);
    v7 = AppV::LogFormatter::operator%<unsigned long>(v6, (__int64)&LastError);
    v74 = 0;
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v74, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)&v67, 8, (int)&v74, v7);
    std::wstring::~wstring((char **)&v74);
    v60[0] = (char *)&AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v61);
    std::wstring::~wstring((char **)&v71);
    std::string::~string((char **)&v67);
  }
  for ( i = *(_QWORD *)(Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance() + 24);
        i != *(_QWORD *)(Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance() + 32);
        i += 40 )
  {
    std::wstring::wstring((__int64)&v71, i);
    v9 = *(_DWORD *)(i + 32);
    v48 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 7;
    LOWORD(v74) = 0;
    v49 = 0;
    v50 = 0;
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = (unsigned int)(v10 - 1);
      if ( (_DWORD)v11 )
      {
        if ( (_DWORD)v11 != 1 )
          goto LABEL_32;
        LODWORD(v46) = 0;
        v45[0] = 0;
        v12 = AppV::ClientConfiguration::Impl::ValueNameT<AppV::ClientConfiguration::Impl::ValueNameEmpty>::ValidateName(
                v11,
                &v71,
                3,
                v45);
        if ( (v12 & 0x8000000000LL) != 0 )
        {
          AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>(
            (__int64)v79,
            (__int64)&v71,
            v45[0]);
          v12 = AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::Get(
                  v79,
                  &v49,
                  &v46);
          AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::~RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>((__int64)v79);
        }
        if ( (v12 & 0x8000000000LL) != 0 )
        {
          v13 = *(__int64 **)a2;
          v14 = operator new(0x28u);
          v55 = v14;
          v14[2] = 3;
          *(_QWORD *)v14 = &AppV::Client::Service::Impl::MultistringValue::`vftable';
          std::vector<std::wstring>::vector<std::wstring>(v14 + 4, &v49);
          v46 = v14;
          v15 = operator new(0x18u);
          v46 = v15;
          *(_OWORD *)v15 = 0;
          v15[2] = 1;
          v15[3] = 1;
          *(_QWORD *)v15 = &std::_Ref_count<AppV::Client::Service::Impl::MultistringValue>::`vftable';
          *((_QWORD *)v15 + 2) = v14;
          *(_QWORD *)&v51 = v14;
          *((_QWORD *)&v51 + 1) = v15;
          std::wstring::wstring((__int64)v60, (__int64)&v71);
          v62 = v14;
          v63 = v15;
          v51 = 0;
          std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>,0>>::insert<0,0>(
            v13,
            (__int64)v57,
            (const wchar_t *)v60);
          v16 = v63;
          if ( v63 && _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
LABEL_22:
          std::wstring::~wstring(v60);
          goto LABEL_32;
        }
        std::string::string(
          v60,
          "AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings");
        LODWORD(v62) = 254;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v17);
        v67 = 0;
        v68 = 0;
        v69 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v67,
          L"Failed loading configuration value '%2%' with error code: %1%",
          0x3Du);
        v19 = AppV::Log::fmt(v18, v77, &v67);
        v46 = (_DWORD *)v12;
        v20 = AppV::LogFormatter::operator%(v19, (__int64 *)&v46);
        AppV::LogFormatter::perform_substitution<std::wstring>(v20, &v71);
        v64 = 0;
        v65 = 0;
        v66 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v64, L"RegistryNotify", 0xEu);
        AppV::DecoratedLog::operator()((char *)v60, 8, (int)&v64, v20);
        std::wstring::~wstring((char **)&v64);
        v77[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v78);
        std::wstring::~wstring((char **)&v67);
      }
      else
      {
        ConfigurationValue = AppV::ClientConfiguration::GetConfigurationValue(&v71, &v74);
        if ( (ConfigurationValue & 0x8000000000LL) != 0 )
        {
          v22 = *(__int64 **)a2;
          v23 = operator new(0x30u);
          v56 = v23;
          v23[2] = 2;
          *(_QWORD *)v23 = &AppV::Client::Service::Impl::StringValue::`vftable';
          std::wstring::wstring((__int64)(v23 + 4), (__int64)&v74);
          v46 = v23;
          v24 = operator new(0x18u);
          v46 = v24;
          *(_OWORD *)v24 = 0;
          v24[2] = 1;
          v24[3] = 1;
          *(_QWORD *)v24 = &std::_Ref_count<AppV::Client::Service::Impl::StringValue>::`vftable';
          *((_QWORD *)v24 + 2) = v23;
          *(_QWORD *)&v52 = v23;
          *((_QWORD *)&v52 + 1) = v24;
          std::wstring::wstring((__int64)v60, (__int64)&v71);
          v62 = v23;
          v63 = v24;
          v52 = 0;
          std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>,0>>::insert<0,0>(
            v22,
            (__int64)v58,
            (const wchar_t *)v60);
          v25 = v63;
          if ( v63 )
          {
            if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
              if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          goto LABEL_22;
        }
        std::string::string(
          v60,
          "AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings");
        LODWORD(v62) = 242;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v26);
        v64 = 0;
        v65 = 0;
        v66 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v64,
          L"Failed loading configuration value '%2%' with error code: %1%",
          0x3Du);
        v28 = AppV::Log::fmt(v27, v77, &v64);
        v46 = (_DWORD *)ConfigurationValue;
        v29 = AppV::LogFormatter::operator%(v28, (__int64 *)&v46);
        AppV::LogFormatter::perform_substitution<std::wstring>(v29, &v71);
        v67 = 0;
        v68 = 0;
        v69 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v67, L"RegistryNotify", 0xEu);
        AppV::DecoratedLog::operator()((char *)v60, 8, (int)&v67, v29);
        std::wstring::~wstring((char **)&v67);
        v77[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v78);
        std::wstring::~wstring((char **)&v64);
      }
    }
    else
    {
      v30 = AppV::ClientConfiguration::GetConfigurationValue(&v71, &v48);
      if ( (v30 & 0x8000000000LL) != 0 )
      {
        v31 = *(__int64 **)a2;
        v32 = operator new(0x18u);
        v33 = v48;
        v32[2] = 1;
        *(_QWORD *)v32 = &AppV::Client::Service::Impl::DwordValue::`vftable';
        v32[4] = v33;
        v46 = v32;
        v34 = operator new(0x18u);
        v46 = v34;
        *(_OWORD *)v34 = 0;
        v34[2] = 1;
        v34[3] = 1;
        *(_QWORD *)v34 = &std::_Ref_count<AppV::Client::Service::Impl::DwordValue>::`vftable';
        *((_QWORD *)v34 + 2) = v32;
        *(_QWORD *)&v53 = v32;
        *((_QWORD *)&v53 + 1) = v34;
        operator delete(0);
        std::wstring::wstring((__int64)v60, (__int64)&v71);
        v62 = v32;
        v63 = v34;
        v53 = 0;
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>,0>>::insert<0,0>(
          v31,
          (__int64)v59,
          (const wchar_t *)v60);
        v35 = v63;
        if ( v63 )
        {
          if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
            if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
          }
        }
        goto LABEL_22;
      }
      std::string::string(
        v60,
        "AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings");
      LODWORD(v62) = 230;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v36);
      v64 = 0;
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v64,
        L"Failed loading configuration value '%2%' with error code: %1%",
        0x3Du);
      v38 = AppV::Log::fmt(v37, v77, &v64);
      v46 = (_DWORD *)v30;
      v39 = AppV::LogFormatter::operator%(v38, (__int64 *)&v46);
      AppV::LogFormatter::perform_substitution<std::wstring>(v39, &v71);
      v67 = 0;
      v68 = 0;
      v69 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v67, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v60, 8, (int)&v67, v39);
      std::wstring::~wstring((char **)&v67);
      v77[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v78);
      std::wstring::~wstring((char **)&v64);
    }
    std::string::~string(v60);
LABEL_32:
    std::vector<std::wstring>::_Tidy(&v49);
    std::wstring::~wstring((char **)&v74);
    std::wstring::~wstring((char **)&v71);
  }
  if ( v3 && !LeaveCriticalPolicySection(v3) )
  {
    LastError = GetLastError();
    std::string::string(
      v60,
      "AppV::Client::Service::Impl::SettingCacheT<struct AppV::Client::Service::Impl::SettingCacheEmpty>::LoadSettings");
    LODWORD(v62) = 272;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v40);
    v64 = 0;
    v65 = 0;
    v66 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v64,
      L"Failed to leave critical policy section with error: %1% \n",
      0x39u);
    v42 = AppV::Log::fmt(v41, v77, &v64);
    v43 = AppV::LogFormatter::operator%<unsigned long>(v42, (__int64)&LastError);
    v67 = 0;
    v68 = 0;
    v69 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v67, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v60, 8, (int)&v67, v43);
    std::wstring::~wstring((char **)&v67);
    v77[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v78);
    std::wstring::~wstring((char **)&v64);
    std::string::~string(v60);
  }
  v44 = *(volatile signed __int32 **)(a2 + 8);
  if ( v44 )
  {
    if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
      if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
    }
  }
}

```

## disassembly

```asm
0x140058258  push    rbp
0x14005825a  push    rbx
0x14005825b  push    rsi
0x14005825c  push    rdi
0x14005825d  push    r12
0x14005825f  push    r13
0x140058261  push    r14
0x140058263  push    r15
0x140058265  lea     rbp, [rsp-138h]
0x14005826d  sub     rsp, 238h
0x140058274  mov     rax, cs:__security_cookie
0x14005827b  xor     rax, rsp
0x14005827e  mov     [rbp+170h+var_50], rax
0x140058285  mov     r15, rdx
0x140058288  mov     [rbp+170h+var_1F0], rdx
0x14005828c  xor     r13d, r13d
0x14005828f  mov     [rsp+270h+var_240], r13d
0x140058294  lea     ecx, [r13+1]; bMachine
0x140058298  call    cs:__imp_EnterCriticalPolicySection
0x14005829e  mov     r12, rax
0x1400582a1  lea     r14, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400582a8  test    rax, rax
0x1400582ab  jnz     loc_14005837D
0x1400582b1  call    cs:__imp_GetLastError
0x1400582b7  mov     [rsp+270h+var_240], eax
0x1400582bb  lea     rdx, aAppvClientServ_61; "AppV::Client::Service::Impl::SettingCac"...
0x1400582c2  lea     rcx, [rbp+170h+var_158]
0x1400582c6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400582cb  mov     [rbp+170h+var_138], 0CFh
0x1400582d2  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400582d7  xorps   xmm0, xmm0
0x1400582da  movups  [rbp+170h+var_130], xmm0
0x1400582de  mov     [rbp+170h+var_120], r13
0x1400582e2  mov     [rbp+170h+var_118], r13
0x1400582e6  lea     r8d, [r13+39h]
0x1400582ea  lea     rdx, aFailedToEnterC; "Failed to enter critical policy section"...
0x1400582f1  lea     rcx, [rbp+170h+var_130]
0x1400582f5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400582fa  nop
0x1400582fb  lea     r8, [rbp+170h+var_130]
0x1400582ff  lea     rdx, [rbp+170h+var_1A8]
0x140058303  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140058308  nop
0x140058309  lea     rdx, [rsp+270h+var_240]
0x14005830e  mov     rcx, rax
0x140058311  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140058316  mov     rbx, rax
0x140058319  xorps   xmm0, xmm0
0x14005831c  movups  [rbp+170h+var_110], xmm0
0x140058320  mov     [rbp+170h+var_100], r13
0x140058324  mov     [rbp+170h+var_F8], r13
0x140058328  lea     r8d, [r13+0Eh]
0x14005832c  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140058333  lea     rcx, [rbp+170h+var_110]
0x140058337  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005833c  nop
0x14005833d  mov     r9, rbx
0x140058340  lea     r8, [rbp+170h+var_110]
0x140058344  lea     edx, [r13+8]
0x140058348  lea     rcx, [rbp+170h+var_158]
0x14005834c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140058351  nop
0x140058352  lea     rcx, [rbp+170h+var_110]
0x140058356  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005835b  nop
0x14005835c  mov     [rbp+170h+var_1A8], r14
0x140058360  lea     rcx, [rbp+170h+var_198]
0x140058364  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058369  nop
0x14005836a  lea     rcx, [rbp+170h+var_130]
0x14005836e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058373  nop
0x140058374  lea     rcx, [rbp+170h+var_158]
0x140058378  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005837d  call    ?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ; Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)
0x140058382  mov     rbx, [rax+18h]
0x140058386  mov     rsi, 8000000000h
0x140058390  call    ?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ; Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)
0x140058395  cmp     rbx, [rax+20h]
0x140058399  jz      loc_140058A3B
0x14005839f  mov     rdx, rbx
0x1400583a2  lea     rcx, [rbp+170h+var_130]
0x1400583a6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400583ab  nop
0x1400583ac  mov     ecx, [rbx+20h]
0x1400583af  mov     [rsp+270h+var_23C], r13d
0x1400583b4  xorps   xmm0, xmm0
0x1400583b7  movups  [rbp+170h+var_110], xmm0
0x1400583bb  mov     [rbp+170h+var_100], r13
0x1400583bf  mov     [rbp+170h+var_F8], 7
0x1400583c7  mov     word ptr [rbp+170h+var_110], r13w
0x1400583cc  movdqu  [rsp+270h+var_238], xmm0
0x1400583d2  mov     [rsp+270h+var_228], r13
0x1400583d7  sub     ecx, 1
0x1400583da  jz      loc_140058821
0x1400583e0  sub     ecx, 1
0x1400583e3  jz      loc_140058629
0x1400583e9  cmp     ecx, 1
0x1400583ec  jnz     loc_140058A14
0x1400583f2  mov     dword ptr [rsp+270h+var_248], r13d
0x1400583f7  mov     [rsp+270h+var_250], r13b
0x1400583fc  lea     r9, [rsp+270h+var_250]
0x140058401  lea     r8d, [rcx+2]
0x140058405  lea     rdx, [rbp+170h+var_130]
0x140058409  call    ?ValidateName@?$ValueNameT@UValueNameEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ConfigurationType@34@AEA_N@Z; AppV::ClientConfiguration::Impl::ValueNameT<AppV::ClientConfiguration::Impl::ValueNameEmpty>::ValidateName(std::wstring const &,AppV::ClientConfiguration::ConfigurationType,bool &)
0x14005840e  mov     rdi, rax
0x140058411  test    rsi, rax
0x140058414  jz      short loc_140058451
0x140058416  mov     r8b, [rsp+270h+var_250]
0x14005841b  lea     rdx, [rbp+170h+var_130]
0x14005841f  lea     rcx, [rbp+170h+var_C0]
0x140058426  call    ??0?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>(std::wstring const &,bool)
0x14005842b  nop
0x14005842c  lea     r8, [rsp+270h+var_248]
0x140058431  lea     rdx, [rsp+270h+var_238]
0x140058436  lea     rcx, [rbp+170h+var_C0]
0x14005843d  call    ?Get@?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@QEAA_KAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAW4ConfigurationControlType@34@@Z; AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::Get(std::vector<std::wstring> &,AppV::ClientConfiguration::ConfigurationControlType &)
0x140058442  mov     rdi, rax
0x140058445  lea     rcx, [rbp+170h+var_C0]
0x14005844c  call    ??1?$RegistryValueT@URegistryValueEmpty@Impl@ClientConfiguration@AppV@@@Impl@ClientConfiguration@AppV@@QEAA@XZ; AppV::ClientConfiguration::Impl::RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>::~RegistryValueT<AppV::ClientConfiguration::Impl::RegistryValueEmpty>(void)
0x140058451  test    rsi, rdi
0x140058454  jz      loc_14005854C
0x14005845a  mov     r14, [r15]
0x14005845d  mov     ecx, 28h ; '('; Size
0x140058462  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140058467  mov     rsi, rax
0x14005846a  mov     [rbp+170h+var_1E8], rax
0x14005846e  mov     dword ptr [rax+8], 3
0x140058475  lea     rax, ??_7MultistringValue@Impl@Service@Client@AppV@@6B@; const AppV::Client::Service::Impl::MultistringValue::`vftable'
0x14005847c  mov     [rsi], rax
0x14005847f  lea     rcx, [rsi+10h]
0x140058483  lea     rdx, [rsp+270h+var_238]
0x140058488  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x14005848d  nop
0x14005848e  mov     [rsp+270h+var_248], rsi
0x140058493  mov     ecx, 18h; Size
0x140058498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005849d  mov     rdi, rax
0x1400584a0  mov     [rsp+270h+var_248], rax
0x1400584a5  xorps   xmm0, xmm0
0x1400584a8  movups  xmmword ptr [rax], xmm0
0x1400584ab  mov     eax, 1
0x1400584b0  mov     [rdi+8], eax
0x1400584b3  mov     [rdi+0Ch], eax
0x1400584b6  lea     rax, ??_7?$_Ref_count@VMultistringValue@Impl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::Impl::MultistringValue>::`vftable'
0x1400584bd  mov     [rdi], rax
0x1400584c0  mov     [rdi+10h], rsi
0x1400584c4  mov     qword ptr [rsp+270h+var_220], rsi
0x1400584c9  mov     qword ptr [rsp+270h+var_220+8], rdi
0x1400584ce  lea     rdx, [rbp+170h+var_130]
0x1400584d2  lea     rcx, [rbp+170h+var_1A8]
0x1400584d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400584db  mov     [rbp+170h+var_188], rsi
0x1400584df  mov     [rbp+170h+var_180], rdi
0x1400584e3  xorps   xmm0, xmm0
0x1400584e6  movdqu  [rsp+270h+var_220], xmm0
0x1400584ec  lea     r8, [rbp+170h+var_1A8]
0x1400584f0  lea     rdx, [rbp+170h+var_1D8]
0x1400584f4  mov     rcx, r14
0x1400584f7  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>,0>>::insert<0,0>(std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>> &&)
0x1400584fc  nop
0x1400584fd  mov     rdi, [rbp+170h+var_180]
0x140058501  test    rdi, rdi
0x140058504  jz      short loc_14005853D
0x140058506  or      eax, 0FFFFFFFFh
0x140058509  lock xadd [rdi+8], eax
0x14005850e  cmp     eax, 1
0x140058511  jnz     short loc_14005853D
0x140058513  mov     rax, [rdi]
0x140058516  mov     rcx, rdi
0x140058519  mov     rax, [rax]
0x14005851c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058521  or      eax, 0FFFFFFFFh
0x140058524  lock xadd [rdi+0Ch], eax
0x140058529  cmp     eax, 1
0x14005852c  jnz     short loc_14005853D
0x14005852e  mov     rax, [rdi]
0x140058531  mov     rcx, rdi
0x140058534  mov     rax, [rax+8]
0x140058538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005853d  lea     rcx, [rbp+170h+var_1A8]
0x140058541  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058546  nop
0x140058547  jmp     loc_14005872E
0x14005854c  lea     rdx, aAppvClientServ_61; "AppV::Client::Service::Impl::SettingCac"...
0x140058553  lea     rcx, [rbp+170h+var_1A8]
0x140058557  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005855c  mov     dword ptr [rbp+170h+var_188], 0FEh
0x140058563  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140058568  xorps   xmm0, xmm0
0x14005856b  movups  [rbp+170h+var_158], xmm0
0x14005856f  mov     [rbp+170h+var_148], r13
0x140058573  mov     [rbp+170h+var_140], r13
0x140058577  mov     r8d, 3Dh ; '='
0x14005857d  lea     rdx, aFailedLoadingC; "Failed loading configuration value '%2%"...
0x140058584  lea     rcx, [rbp+170h+var_158]
0x140058588  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005858d  nop
0x14005858e  lea     r8, [rbp+170h+var_158]
0x140058592  lea     rdx, [rbp+170h+var_F0]
0x140058599  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005859e  nop
0x14005859f  mov     [rsp+270h+var_248], rdi
0x1400585a4  lea     rdx, [rsp+270h+var_248]
0x1400585a9  mov     rcx, rax
0x1400585ac  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x1400585b1  mov     rdi, rax
0x1400585b4  lea     rdx, [rbp+170h+var_130]
0x1400585b8  mov     rcx, rax
0x1400585bb  call    ??$perform_substitution@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogFormatter@AppV@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::LogFormatter::perform_substitution<std::wstring>(std::wstring const &)
0x1400585c0  xorps   xmm0, xmm0
0x1400585c3  movups  [rbp+170h+var_178], xmm0
0x1400585c7  mov     [rbp+170h+var_168], r13
0x1400585cb  mov     [rbp+170h+var_160], r13
0x1400585cf  mov     r8d, 0Eh
0x1400585d5  lea     rdx, aRegistrynotify; "RegistryNotify"
0x1400585dc  lea     rcx, [rbp+170h+var_178]
0x1400585e0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400585e5  nop
0x1400585e6  mov     r9, rdi
0x1400585e9  lea     r8, [rbp+170h+var_178]
0x1400585ed  mov     edx, 8
0x1400585f2  lea     rcx, [rbp+170h+var_1A8]
0x1400585f6  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400585fb  nop
0x1400585fc  lea     rcx, [rbp+170h+var_178]
0x140058600  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058605  nop
0x140058606  mov     [rbp+170h+var_F0], r14
0x14005860d  lea     rcx, [rbp+170h+var_E0]
0x140058614  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058619  nop
0x14005861a  lea     rcx, [rbp+170h+var_158]
0x14005861e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058623  nop
0x140058624  jmp     loc_140058A0A
0x140058629  lea     rdx, [rbp+170h+var_110]
0x14005862d  lea     rcx, [rbp+170h+var_130]
0x140058631  call    ?GetConfigurationValue@ClientConfiguration@AppV@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z; AppV::ClientConfiguration::GetConfigurationValue(std::wstring const &,std::wstring &)
0x140058636  mov     rdi, rax
0x140058639  test    rsi, rax
0x14005863c  jz      loc_140058744
0x140058642  mov     r14, [r15]
0x140058645  mov     ecx, 30h ; '0'; Size
0x14005864a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005864f  mov     rsi, rax
0x140058652  mov     [rbp+170h+var_1E0], rax
0x140058656  mov     dword ptr [rax+8], 2
0x14005865d  lea     rax, ??_7StringValue@Impl@Service@Client@AppV@@6B@; const AppV::Client::Service::Impl::StringValue::`vftable'
0x140058664  mov     [rsi], rax
0x140058667  lea     rcx, [rsi+10h]
0x14005866b  lea     rdx, [rbp+170h+var_110]
0x14005866f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140058674  nop
0x140058675  mov     [rsp+270h+var_248], rsi
0x14005867a  mov     ecx, 18h; Size
0x14005867f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140058684  mov     rdi, rax
0x140058687  mov     [rsp+270h+var_248], rax
0x14005868c  xorps   xmm0, xmm0
0x14005868f  movups  xmmword ptr [rax], xmm0
0x140058692  mov     eax, 1
0x140058697  mov     [rdi+8], eax
0x14005869a  mov     [rdi+0Ch], eax
0x14005869d  lea     rax, ??_7?$_Ref_count@VStringValue@Impl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::Impl::StringValue>::`vftable'
0x1400586a4  mov     [rdi], rax
0x1400586a7  mov     [rdi+10h], rsi
0x1400586ab  mov     qword ptr [rsp+270h+var_210], rsi
0x1400586b0  mov     qword ptr [rsp+270h+var_210+8], rdi
0x1400586b5  lea     rdx, [rbp+170h+var_130]
0x1400586b9  lea     rcx, [rbp+170h+var_1A8]
0x1400586bd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400586c2  mov     [rbp+170h+var_188], rsi
0x1400586c6  mov     [rbp+170h+var_180], rdi
0x1400586ca  xorps   xmm0, xmm0
0x1400586cd  movdqu  [rsp+270h+var_210], xmm0
0x1400586d3  lea     r8, [rbp+170h+var_1A8]
0x1400586d7  lea     rdx, [rbp+170h+var_1C8]
0x1400586db  mov     rcx, r14
0x1400586de  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UConfigValue@Impl@Service@Client@AppV@@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>>>,0>>::insert<0,0>(std::pair<std::wstring const,std::shared_ptr<AppV::Client::Service::Impl::ConfigValue>> &&)
0x1400586e3  nop
0x1400586e4  mov     rdi, [rbp+170h+var_180]
0x1400586e8  test    rdi, rdi
0x1400586eb  jz      short loc_140058724
0x1400586ed  or      eax, 0FFFFFFFFh
0x1400586f0  lock xadd [rdi+8], eax
0x1400586f5  cmp     eax, 1
0x1400586f8  jnz     short loc_140058724
0x1400586fa  mov     rax, [rdi]
0x1400586fd  mov     rcx, rdi
0x140058700  mov     rax, [rax]
0x140058703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058708  or      eax, 0FFFFFFFFh
0x14005870b  lock xadd [rdi+0Ch], eax
0x140058710  cmp     eax, 1
0x140058713  jnz     short loc_140058724
0x140058715  mov     rax, [rdi]
0x140058718  mov     rcx, rdi
0x14005871b  mov     rax, [rax+8]
0x14005871f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
