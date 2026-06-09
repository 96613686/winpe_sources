# AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor(void)

- ea: `0x140058b9c`
- end: `0x14005957f`
- name: `?Monitor@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAIXZ`
- size: `2531`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140059590`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x140004910`
- `0x14000491c`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x14001d6e4`
- `0x14001f9f0`
- `0x140020010`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c5d4`
- `0x14003c660`
- `0x140042d28`
- `0x14005531c`
- `0x1400554ac`
- `0x140058b9c`
- `0x140059afc`
- `0x140059d7c`
- `0x140059f70`
- `0x14006a010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x14005901d`
- `KERNEL32!WaitForMultipleObjects` at `0x1400590a8`
- `KERNEL32!WaitForMultipleObjects` at `0x14005901d`
- `KERNEL32!WaitForMultipleObjects` at `0x1400590a8`
- `KERNEL32!GetLastError` at `0x140059139`
- `KERNEL32!GetLastError` at `0x1400593e0`
- `KERNEL32!GetLastError` at `0x140059139`
- `KERNEL32!GetLastError` at `0x1400593e0`
- `KERNEL32!WaitForSingleObject` at `0x140059051`
- `KERNEL32!WaitForSingleObject` at `0x140059051`

## string_xrefs

- `0x1400591cd`: `RegistryNotify`
- `0x140059274`: `RegistryNotify`
- `0x140059307`: `RegistryNotify`
- `0x140059474`: `RegistryNotify`
- `0x140059143`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor`
- `0x140059222`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor`
- `0x1400592b5`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor`
- `0x1400593ea`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor`
- `0x1400592e1`: `Setting Watcher thread normal shutdown`
- `0x140059174`: `WaitForSingleObject() - unexpected return value during backoff time. reason = %1%, last error: %2%`
- `0x14005924e`: `Setting Watcher thread normal shutdown during backoff wait`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor(
        __int64 a1)
{
  _QWORD *v1; // rdi
  unsigned __int64 v2; // r15
  __int64 v3; // rax
  bool v4; // cf
  unsigned __int64 v5; // rax
  unsigned __int64 *v6; // rax
  __int64 v7; // r13
  void *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r12
  __int64 i; // rbx
  char v13; // si
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edi
  __int64 *v18; // rdi
  HANDLE *v19; // r12
  _QWORD *v20; // rcx
  unsigned __int64 v21; // rbx
  HANDLE *v22; // rdx
  __int64 v23; // rbx
  _QWORD *v24; // rsi
  void *v25; // rdi
  _QWORD *v26; // rdx
  __int64 v27; // rsi
  DWORD j; // eax
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  char v41; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int LastError; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v43; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE *lpHandles[2]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE *v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  unsigned __int64 v49; // [rsp+80h] [rbp-80h]
  void *v50; // [rsp+88h] [rbp-78h]
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-60h]
  __int128 Src; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  __int128 v56; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v57; // [rsp+E0h] [rbp-20h]
  char *v58[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v59; // [rsp+110h] [rbp+10h]
  _QWORD v60[2]; // [rsp+118h] [rbp+18h] BYREF
  char *v61[4]; // [rsp+128h] [rbp+28h] BYREF

  v46 = a1;
  v1 = (_QWORD *)Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance();
  v43 = v1;
  v2 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v1[1] - *v1) >> 3) + 1;
  v49 = v2;
  v3 = 72 * v2;
  if ( !is_mul_ok(v2, 0x48u) )
    v3 = -1;
  v4 = __CFADD__(v3, 8);
  v5 = v3 + 8;
  if ( v4 )
    v5 = -1;
  v6 = (unsigned __int64 *)operator new[](v5);
  *v6 = v2;
  v7 = (__int64)(v6 + 1);
  `eh vector constructor iterator'(
    v6 + 1,
    0x48u,
    v2,
    (void (*)(void *))AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData::EventData,
    (void (*)(void *))AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData::~EventData);
  *(_QWORD *)&v56 = v7;
  *((_QWORD *)&v56 + 1) = &v41;
  LOBYTE(v57) = 1;
  v8 = operator new(0x18u);
  *(_QWORD *)&v56 = v8;
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_resource<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData *,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::ArrayDeleter<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData>>::`vftable';
  *((_QWORD *)v8 + 2) = v7;
  v49 = v7;
  v50 = v8;
  v51 = 0;
  v52 = 0u;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"SOFTWARE\\Policies\\Microsoft\\AppV\\Client", 0x27u);
  LastError = AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(
                v9,
                (const WCHAR *)&v51,
                1,
                v7);
  std::wstring::~wstring((char **)&v51);
  v10 = LastError;
  if ( LastError )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) != 1 )
      return v10;
    goto LABEL_59;
  }
  v11 = 1;
  for ( i = *v1; i != v1[1]; i += 40 )
  {
    v13 = *(_BYTE *)(i + 32);
    Src = 0;
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&Src, L"SOFTWARE\\Microsoft\\AppV", 0x17u);
    v14 = std::wstring::append(&Src, (void *)L"\\");
    v51 = 0;
    v52 = 0u;
    v51 = *(_OWORD *)v14;
    v52 = *(_OWORD *)(v14 + 16);
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 7;
    *(_WORD *)v14 = 0;
    v15 = std::wstring::append(&v51);
    v56 = 0;
    v57 = 0u;
    v56 = *(_OWORD *)v15;
    v57 = *(_OWORD *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    LastError = AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(
                  0,
                  (const WCHAR *)&v56,
                  v13,
                  v7 + 72 * v11);
    std::wstring::~wstring((char **)&v56);
    std::wstring::~wstring((char **)&v51);
    std::wstring::~wstring((char **)&Src);
    v16 = LastError;
    if ( LastError )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v8)(v8);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      return v16;
    }
    ++v11;
    v1 = v43;
  }
  *(_OWORD *)lpHandles = 0;
  v45 = 0;
  v18 = (__int64 *)v46;
  v19 = (HANDLE *)(v46 + 8);
  std::vector<void *>::_Emplace_reallocate<void * const &>(lpHandles, 0, v46 + 8);
  v21 = 0;
  if ( v2 )
  {
    v22 = lpHandles[1];
    do
    {
      v20 = *(_QWORD **)(v7 + 72 * v21 + 24);
      v43 = v20;
      if ( v22 == v45 )
      {
        std::vector<void *>::_Emplace_reallocate<void * const &>(lpHandles, v22, &v43);
        v22 = lpHandles[1];
      }
      else
      {
        *v22 = v20;
        v22 = ++lpHandles[1];
      }
      ++v21;
    }
    while ( v21 < v2 );
  }
  v10 = AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification(
          v20,
          v7,
          v2);
  LastError = v10;
  if ( v10 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(lpHandles);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
      goto LABEL_24;
    return v10;
  }
  v47 = 0;
  v48 = 0;
  v23 = *v18;
  v24 = operator new(0x10u);
  *v24 = &AppV::Client::Service::Impl::SettingSenderT<AppV::Client::Service::Impl::SettingSenderEmpty>::`vftable';
  v24[1] = v23;
  *(_QWORD *)&v56 = v24;
  v25 = operator new(0x18u);
  *(_OWORD *)v25 = 0;
  *((_DWORD *)v25 + 2) = 1;
  *((_DWORD *)v25 + 3) = 1;
  *(_QWORD *)v25 = &std::_Ref_count<AppV::Client::Service::Impl::SettingSenderT<AppV::Client::Service::Impl::SettingSenderEmpty>>::`vftable';
  *((_QWORD *)v25 + 2) = v24;
  *(_QWORD *)&v56 = v24;
  *((_QWORD *)&v56 + 1) = v25;
  operator delete(0);
  v26 = (_QWORD *)*((_QWORD *)&v47 + 1);
  if ( *((_QWORD *)&v47 + 1) == v48 )
  {
    std::vector<std::shared_ptr<AppV::Client::Service::Impl::ISettingSender>>::_Emplace_reallocate<std::shared_ptr<AppV::Client::Service::Impl::ISettingSender> const &>(
      (char **)&v47,
      *((char **)&v47 + 1),
      &v56);
    v25 = (void *)*((_QWORD *)&v56 + 1);
  }
  else
  {
    **((_QWORD **)&v47 + 1) = 0;
    v26[1] = 0;
    _InterlockedIncrement((volatile signed __int32 *)v25 + 2);
    *v26 = v24;
    v26[1] = v25;
    *((_QWORD *)&v47 + 1) += 16LL;
  }
  v27 = v46;
  AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::ProcessChangedRegistrySettings(
    v46,
    &v47);
  for ( j = WaitForMultipleObjects(lpHandles[1] - lpHandles[0], lpHandles[0], 0, 0xFFFFFFFF);
        ;
        j = WaitForMultipleObjects(lpHandles[1] - lpHandles[0], lpHandles[0], 0, 0xFFFFFFFF) )
  {
    LODWORD(v46) = j;
    if ( j >= (unsigned __int64)(lpHandles[1] - lpHandles[0]) )
    {
      LastError = GetLastError();
      std::string::string(
        v58,
        "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor");
      v59 = 180;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v36);
      v51 = 0;
      v52 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v51,
        L"WaitForMultipleObject() - unexpected return value waiting for setting changes. reason = %1%, last error: %2%",
        0x6Cu);
      v38 = AppV::Log::fmt(v37, v60, &v51);
      v39 = AppV::LogFormatter::operator%<unsigned long>(v38, (__int64)&v46);
      v40 = AppV::LogFormatter::operator%<long>(v39, (__int64)&LastError);
      Src = 0;
      v54 = 0;
      v55 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&Src, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v58, 1, (int)&Src, v40);
      std::wstring::~wstring((char **)&Src);
      v60[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v61);
      std::wstring::~wstring((char **)&v51);
      goto LABEL_54;
    }
    if ( !j )
    {
      std::string::string(
        v58,
        "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor");
      v59 = 188;
      v51 = 0;
      v52 = 0u;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Setting Watcher thread normal shutdown", 0x26u);
      Src = 0;
      v54 = 0;
      v55 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&Src, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v58, 4, (int)&Src, (__int64)&v51);
      std::wstring::~wstring((char **)&Src);
      std::wstring::~wstring((char **)&v51);
LABEL_45:
      std::string::~string(v58);
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v25)(v25);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
      std::vector<std::shared_ptr<AppV::Policy::PackageInfo>>::~vector<std::shared_ptr<AppV::Policy::PackageInfo>>(&v47);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(lpHandles);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v8)(v8);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      return 0;
    }
    v29 = WaitForSingleObject(*v19, 0xFAu);
    LODWORD(v43) = v29;
    if ( !v29 )
    {
      std::string::string(
        v58,
        "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor");
      v59 = 201;
      v51 = 0;
      v52 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v51,
        L"Setting Watcher thread normal shutdown during backoff wait",
        0x3Au);
      Src = 0;
      v54 = 0;
      v55 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&Src, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v58, 4, (int)&Src, (__int64)&v51);
      std::wstring::~wstring((char **)&Src);
      std::wstring::~wstring((char **)&v51);
      goto LABEL_45;
    }
    if ( v29 != 258 )
    {
      LastError = GetLastError();
      std::string::string(
        v58,
        "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor");
      v59 = 223;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v31);
      v51 = 0;
      v52 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v51,
        L"WaitForSingleObject() - unexpected return value during backoff time. reason = %1%, last error: %2%",
        0x62u);
      v33 = AppV::Log::fmt(v32, v60, &v51);
      v34 = AppV::LogFormatter::operator%<unsigned long>(v33, (__int64)&v43);
      v35 = AppV::LogFormatter::operator%<long>(v34, (__int64)&LastError);
      Src = 0;
      v54 = 0;
      v55 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&Src, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v58, 1, (int)&Src, v35);
      std::wstring::~wstring((char **)&Src);
      v60[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v61);
      std::wstring::~wstring((char **)&v51);
LABEL_54:
      std::string::~string(v58);
      v10 = LastError;
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v25)(v25);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
      std::vector<std::shared_ptr<AppV::Policy::PackageInfo>>::~vector<std::shared_ptr<AppV::Policy::PackageInfo>>(&v47);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(lpHandles);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) != 1 )
        return v10;
LABEL_59:
      (**(void (__fastcall ***)(void *))v8)(v8);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
        goto LABEL_60;
      return v10;
    }
    v10 = AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification(
            v30,
            v7,
            v2);
    LastError = v10;
    if ( v10 )
      break;
    AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::ProcessChangedRegistrySettings(
      v27,
      &v47);
  }
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v25)(v25);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  std::vector<std::shared_ptr<AppV::Policy::PackageInfo>>::~vector<std::shared_ptr<AppV::Policy::PackageInfo>>(&v47);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(lpHandles);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) != 1 )
    return v10;
LABEL_24:
  (**(void (__fastcall ***)(void *))v8)(v8);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 3, 0xFFFFFFFF) == 1 )
LABEL_60:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x140058b9c  push    rbp
0x140058b9e  push    rbx
0x140058b9f  push    rsi
0x140058ba0  push    rdi
0x140058ba1  push    r12
0x140058ba3  push    r13
0x140058ba5  push    r14
0x140058ba7  push    r15
0x140058ba9  lea     rbp, [rsp-58h]
0x140058bae  sub     rsp, 158h
0x140058bb5  mov     rax, cs:__security_cookie
0x140058bbc  xor     rax, rsp
0x140058bbf  mov     [rbp+90h+var_48], rax
0x140058bc3  mov     [rsp+190h+var_130], rcx
0x140058bc8  xor     r12d, r12d
0x140058bcb  call    ?Instance@?$Singleton@VConfigurationValuesClass@ClientConfiguration@AppV@@@@SAAEAVConfigurationValuesClass@ClientConfiguration@AppV@@XZ; Singleton<AppV::ClientConfiguration::ConfigurationValuesClass>::Instance(void)
0x140058bd0  mov     rdi, rax
0x140058bd3  mov     [rsp+190h+var_150], rax
0x140058bd8  mov     r15, [rax+8]
0x140058bdc  sub     r15, [rax]
0x140058bdf  sar     r15, 3
0x140058be3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140058bed  imul    r15, rax
0x140058bf1  inc     r15
0x140058bf4  mov     [rbp+90h+var_110], r15
0x140058bf8  lea     ebx, [r12+48h]
0x140058bfd  mov     eax, ebx
0x140058bff  mul     r15
0x140058c02  lea     rsi, [rbx-49h]
0x140058c06  cmovb   rax, rsi
0x140058c0a  add     rax, 8
0x140058c0e  cmovb   rax, rsi
0x140058c12  mov     rcx, rax; unsigned __int64
0x140058c15  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140058c1a  mov     qword ptr [rbp+90h+var_C0], rax
0x140058c1e  mov     [rax], r15
0x140058c21  lea     r13, [rax+8]
0x140058c25  lea     rax, ??1EventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@QEAA@XZ; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData::~EventData(void)
0x140058c2c  mov     [rsp+190h+var_170], rax; void (*)(void *)
0x140058c31  lea     r9, ??0EventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@QEAA@XZ; void (*)(void *)
0x140058c38  mov     r8, r15; unsigned __int64
0x140058c3b  mov     edx, ebx; unsigned __int64
0x140058c3d  mov     rcx, r13; void *
0x140058c40  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140058c45  nop
0x140058c46  mov     al, [rsp+190h+var_160]
0x140058c4a  mov     [rsp+190h+var_160], al
0x140058c4e  mov     qword ptr [rbp+90h+var_C0], r13
0x140058c52  lea     rax, [rsp+190h+var_160]
0x140058c57  mov     qword ptr [rbp+90h+var_C0+8], rax
0x140058c5b  mov     byte ptr [rbp+90h+var_B0], 1
0x140058c5f  lea     ecx, [rbx-30h]; Size
0x140058c62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140058c67  mov     r14, rax
0x140058c6a  mov     qword ptr [rbp+90h+var_C0], rax
0x140058c6e  xorps   xmm0, xmm0
0x140058c71  movups  xmmword ptr [rax], xmm0
0x140058c74  mov     dword ptr [rax+8], 1
0x140058c7b  mov     dword ptr [rax+0Ch], 1
0x140058c82  lea     rax, ??_7?$_Ref_count_resource@PEAUEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@U?$ArrayDeleter@UEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@@23456@@std@@6B@; const std::_Ref_count_resource<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData *,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::ArrayDeleter<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData>>::`vftable'
0x140058c89  mov     [r14], rax
0x140058c8c  mov     [r14+10h], r13
0x140058c90  mov     [rbp+90h+var_110], r13
0x140058c94  mov     [rbp+90h+var_108], r14
0x140058c98  movups  [rbp+90h+var_100], xmm0
0x140058c9c  mov     qword ptr [rbp+90h+var_F0], r12
0x140058ca0  mov     qword ptr [rbp+90h+var_F0+8], r12
0x140058ca4  lea     r8d, [r12+27h]
0x140058ca9  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\AppV\\Cl"...
0x140058cb0  lea     rcx, [rbp+90h+var_100]
0x140058cb4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140058cb9  nop
0x140058cba  mov     r9, r13
0x140058cbd  mov     r8b, 1
0x140058cc0  lea     rdx, [rbp+90h+var_100]
0x140058cc4  call    ?SetRegistryNotificationEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NAEAUEventData@12345@@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(std::wstring const &,bool,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData &)
0x140058cc9  mov     [rsp+190h+var_158], eax
0x140058ccd  lea     rcx, [rbp+90h+var_100]
0x140058cd1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058cd6  mov     ebx, [rsp+190h+var_158]
0x140058cda  test    ebx, ebx
0x140058cdc  jz      short loc_140058D0B
0x140058cde  mov     eax, esi
0x140058ce0  lock xadd [r14+8], eax
0x140058ce6  add     eax, esi
0x140058ce8  jnz     loc_14005955D
0x140058cee  mov     rax, [r14]
0x140058cf1  mov     rcx, r14
0x140058cf4  mov     rax, [rax]
0x140058cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058cfc  mov     ecx, esi
0x140058cfe  lock xadd [r14+0Ch], ecx
0x140058d04  add     ecx, esi
0x140058d06  jmp     loc_14005954C
0x140058d0b  mov     r12d, 1
0x140058d11  mov     rbx, [rdi]
0x140058d14  xorps   xmm0, xmm0
0x140058d17  cmp     rbx, [rdi+8]
0x140058d1b  jz      loc_140058E62
0x140058d21  lea     rax, [r12+r12*8]
0x140058d25  lea     rdi, ds:0[rax*8]
0x140058d2d  add     rdi, r13
0x140058d30  mov     sil, [rbx+20h]
0x140058d34  movups  [rbp+90h+Src], xmm0
0x140058d38  mov     [rbp+90h+var_D0], 0
0x140058d40  mov     [rbp+90h+var_C8], 0
0x140058d48  mov     r8d, 17h
0x140058d4e  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\AppV"
0x140058d55  lea     rcx, [rbp+90h+Src]
0x140058d59  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140058d5e  nop
0x140058d5f  lea     rdx, psz; "\\"
0x140058d66  lea     rcx, [rbp+90h+Src]; Src
0x140058d6a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x140058d6f  xorps   xmm0, xmm0
0x140058d72  movups  [rbp+90h+var_100], xmm0
0x140058d76  xor     ecx, ecx
0x140058d78  mov     qword ptr [rbp+90h+var_F0], rcx
0x140058d7c  mov     qword ptr [rbp+90h+var_F0+8], rcx
0x140058d80  movups  xmm0, xmmword ptr [rax]
0x140058d83  movups  [rbp+90h+var_100], xmm0
0x140058d87  movups  xmm1, xmmword ptr [rax+10h]
0x140058d8b  movups  [rbp+90h+var_F0], xmm1
0x140058d8f  mov     [rax+10h], rcx
0x140058d93  mov     qword ptr [rax+18h], 7
0x140058d9b  mov     [rax], cx
0x140058d9e  mov     rdx, rbx
0x140058da1  lea     rcx, [rbp+90h+var_100]; Src
0x140058da5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x140058daa  xorps   xmm0, xmm0
0x140058dad  movups  [rbp+90h+var_C0], xmm0
0x140058db1  xor     ecx, ecx
0x140058db3  mov     qword ptr [rbp+90h+var_B0], rcx
0x140058db7  mov     qword ptr [rbp+90h+var_B0+8], rcx
0x140058dbb  movups  xmm0, xmmword ptr [rax]
0x140058dbe  movups  [rbp+90h+var_C0], xmm0
0x140058dc2  movups  xmm1, xmmword ptr [rax+10h]
0x140058dc6  movups  [rbp+90h+var_B0], xmm1
0x140058dca  mov     [rax+10h], rcx
0x140058dce  mov     qword ptr [rax+18h], 7
0x140058dd6  mov     [rax], cx
0x140058dd9  mov     r9, rdi
0x140058ddc  mov     r8b, sil
0x140058ddf  lea     rdx, [rbp+90h+var_C0]
0x140058de3  call    ?SetRegistryNotificationEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NAEAUEventData@12345@@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(std::wstring const &,bool,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData &)
0x140058de8  mov     [rsp+190h+var_158], eax
0x140058dec  lea     rcx, [rbp+90h+var_C0]
0x140058df0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058df5  nop
0x140058df6  lea     rcx, [rbp+90h+var_100]
0x140058dfa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058dff  nop
0x140058e00  lea     rcx, [rbp+90h+Src]
0x140058e04  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140058e09  mov     edi, [rsp+190h+var_158]
0x140058e0d  test    edi, edi
0x140058e0f  jnz     short loc_140058E22
0x140058e11  inc     r12
0x140058e14  add     rbx, 28h ; '('
0x140058e18  mov     rdi, [rsp+190h+var_150]
0x140058e1d  jmp     loc_140058D14
0x140058e22  or      eax, 0FFFFFFFFh
0x140058e25  lock xadd [r14+8], eax
0x140058e2b  cmp     eax, 1
0x140058e2e  jnz     short loc_140058E5B
0x140058e30  mov     rax, [r14]
0x140058e33  mov     rcx, r14
0x140058e36  mov     rax, [rax]
0x140058e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058e3e  or      ecx, 0FFFFFFFFh
0x140058e41  lock xadd [r14+0Ch], ecx
0x140058e47  cmp     ecx, 1
0x140058e4a  jnz     short loc_140058E5B
0x140058e4c  mov     rcx, [r14]
0x140058e4f  mov     rax, [rcx+8]
0x140058e53  mov     rcx, r14
0x140058e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058e5b  mov     eax, edi
0x140058e5d  jmp     loc_14005955F
0x140058e62  movdqu  xmmword ptr [rsp+190h+lpHandles], xmm0
0x140058e68  mov     [rsp+190h+var_138], 0
0x140058e71  mov     rdi, [rsp+190h+var_130]
0x140058e76  lea     r12, [rdi+8]
0x140058e7a  mov     r8, r12
0x140058e7d  xor     edx, edx
0x140058e7f  lea     rcx, [rsp+190h+lpHandles]
0x140058e84  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x140058e89  xor     ebx, ebx
0x140058e8b  test    r15, r15
0x140058e8e  jz      short loc_140058ED9
0x140058e90  mov     rdx, [rsp+190h+lpHandles+8]
0x140058e95  lea     rax, [rbx+rbx*8]
0x140058e99  mov     rcx, [r13+rax*8+18h]
0x140058e9e  mov     [rsp+190h+var_150], rcx
0x140058ea3  cmp     rdx, [rsp+190h+var_138]
0x140058ea8  jz      short loc_140058EBD
0x140058eaa  mov     [rdx], rcx
0x140058ead  mov     rdx, [rsp+190h+lpHandles+8]
0x140058eb2  add     rdx, 8
0x140058eb6  mov     [rsp+190h+lpHandles+8], rdx
0x140058ebb  jmp     short loc_140058ED1
0x140058ebd  lea     r8, [rsp+190h+var_150]
0x140058ec2  lea     rcx, [rsp+190h+lpHandles]
0x140058ec7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x140058ecc  mov     rdx, [rsp+190h+lpHandles+8]
0x140058ed1  inc     rbx
0x140058ed4  cmp     rbx, r15
0x140058ed7  jb      short loc_140058E95
0x140058ed9  mov     r8, r15
0x140058edc  mov     rdx, r13
0x140058edf  call    ?SetRegistryChangeNotification@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJPEAUEventData@12345@_K@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification(AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData *,unsigned __int64)
0x140058ee4  mov     ebx, eax
0x140058ee6  mov     [rsp+190h+var_158], eax
0x140058eea  test    eax, eax
0x140058eec  jz      short loc_140058F37
0x140058eee  lea     rcx, [rsp+190h+lpHandles]
0x140058ef3  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::vector<std::wstring>>>>>>>(void)
0x140058ef8  nop
0x140058ef9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140058efd  mov     ecx, esi
0x140058eff  lock xadd [r14+8], ecx
0x140058f05  add     ecx, esi
0x140058f07  jnz     loc_14005955D
0x140058f0d  mov     rax, [r14]
0x140058f10  mov     rcx, r14
0x140058f13  mov     rax, [rax]
0x140058f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058f1b  mov     eax, esi
0x140058f1d  lock xadd [r14+0Ch], eax
0x140058f23  add     eax, esi
0x140058f25  jnz     loc_14005955D
0x140058f2b  mov     rax, [r14]
0x140058f2e  mov     rax, [rax+8]
0x140058f32  jmp     loc_140059555
0x140058f37  xorps   xmm0, xmm0
0x140058f3a  movdqu  [rsp+190h+var_128], xmm0
0x140058f40  mov     [rsp+190h+var_118], 0
0x140058f49  mov     rbx, [rdi]
0x140058f4c  mov     ecx, 10h; Size
0x140058f51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140058f56  mov     rsi, rax
0x140058f59  mov     qword ptr [rbp+90h+var_C0], rax
0x140058f5d  lea     rax, ??_7?$SettingSenderT@USettingSenderEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@6B@; const AppV::Client::Service::Impl::SettingSenderT<AppV::Client::Service::Impl::SettingSenderEmpty>::`vftable'
0x140058f64  mov     [rsi], rax
0x140058f67  mov     [rsi+8], rbx
0x140058f6b  mov     qword ptr [rbp+90h+var_C0], rsi
0x140058f6f  mov     ecx, 18h; Size
0x140058f74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140058f79  mov     rdi, rax
0x140058f7c  mov     qword ptr [rbp+90h+var_C0], rax
0x140058f80  xorps   xmm0, xmm0
0x140058f83  movups  xmmword ptr [rax], xmm0
0x140058f86  mov     dword ptr [rax+8], 1
0x140058f8d  mov     dword ptr [rax+0Ch], 1
0x140058f94  lea     rax, ??_7?$_Ref_count@V?$SettingSenderT@USettingSenderEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::Impl::SettingSenderT<AppV::Client::Service::Impl::SettingSenderEmpty>>::`vftable'
0x140058f9b  mov     [rdi], rax
0x140058f9e  mov     [rdi+10h], rsi
0x140058fa2  mov     qword ptr [rbp+90h+var_C0], rsi
0x140058fa6  mov     qword ptr [rbp+90h+var_C0+8], rdi
0x140058faa  mov     edx, 10h
0x140058faf  xor     ecx, ecx; Block
0x140058fb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140058fb6  nop
0x140058fb7  mov     rdx, qword ptr [rsp+190h+var_128+8]
0x140058fbc  cmp     rdx, [rsp+190h+var_118]
0x140058fc1  jz      short loc_140058FDF
0x140058fc3  xor     ebx, ebx
0x140058fc5  mov     [rdx], rbx
0x140058fc8  mov     [rdx+8], rbx
0x140058fcc  lock inc dword ptr [rdi+8]
0x140058fd0  mov     [rdx], rsi
0x140058fd3  mov     [rdx+8], rdi
0x140058fd7  add     qword ptr [rsp+190h+var_128+8], 10h
0x140058fdd  jmp     short loc_140058FF3
0x140058fdf  lea     r8, [rbp+90h+var_C0]
0x140058fe3  lea     rcx, [rsp+190h+var_128]
0x140058fe8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@std@@@?$vector@V?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<AppV::Client::Service::Impl::ISettingSender>>::_Emplace_reallocate<std::shared_ptr<AppV::Client::Service::Impl::ISettingSender> const &>(std::shared_ptr<AppV::Client::Service::Impl::ISettingSender> * const,std::shared_ptr<AppV::Client::Service::Impl::ISettingSender> const &)
0x140058fed  mov     rdi, qword ptr [rbp+90h+var_C0+8]
0x140058ff1  xor     ebx, ebx
0x140058ff3  lea     rdx, [rsp+190h+var_128]
0x140058ff8  mov     rsi, [rsp+190h+var_130]
0x140058ffd  mov     rcx, rsi
0x140059000  call    ?ProcessChangedRegistrySettings@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAXAEAV?$vector@V?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VISettingSender@Impl@Service@Client@AppV@@@std@@@2@@std@@@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::ProcessChangedRegistrySettings(std::vector<std::shared_ptr<AppV::Client::Service::Impl::ISettingSender>> &)
0x140059005  mov     rdx, [rsp+190h+lpHandles]; lpHandles
0x14005900a  mov     rcx, [rsp+190h+lpHandles+8]
0x14005900f  sub     rcx, rdx
0x140059012  sar     rcx, 3; nCount
0x140059016  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14005901a  xor     r8d, r8d; bWaitAll
0x14005901d  call    cs:__imp_WaitForMultipleObjects
0x140059023  mov     dword ptr [rsp+190h+var_130], eax
0x140059027  mov     rdx, [rsp+190h+lpHandles+8]
0x14005902c  sub     rdx, [rsp+190h+lpHandles]
0x140059031  sar     rdx, 3
0x140059035  mov     ecx, eax
0x140059037  cmp     rcx, rdx
0x14005903a  jnb     loc_1400593E0
0x140059040  test    eax, eax
0x140059042  jz      loc_1400592B5
0x140059048  mov     edx, 0FAh; dwMilliseconds
  ... truncated ...
```
