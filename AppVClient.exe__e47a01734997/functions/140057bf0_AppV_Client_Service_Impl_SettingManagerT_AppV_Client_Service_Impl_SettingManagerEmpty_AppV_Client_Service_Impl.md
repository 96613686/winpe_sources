# AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::Initialize(AppV::Client::ControllerRequests *)

- ea: `0x140057bf0`
- end: `0x140058252`
- name: `?Initialize@?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@UEAA_KPEAVControllerRequests@45@@Z`
- size: `1634`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003a34c`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14003d01c`
- `0x140056300`
- `0x140057bf0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140057d81`
- `KERNEL32!CreateEventW` at `0x140057d81`
- `KERNEL32!GetLastError` at `0x140057d94`
- `KERNEL32!GetLastError` at `0x140057d94`
- `KERNEL32!GetCurrentThreadId` at `0x140057c50`
- `KERNEL32!GetCurrentThreadId` at `0x140057c50`
- `KERNEL32!LeaveCriticalSection` at `0x140057d5b`
- `KERNEL32!LeaveCriticalSection` at `0x14005821a`
- `KERNEL32!LeaveCriticalSection` at `0x140057d5b`
- `KERNEL32!LeaveCriticalSection` at `0x14005821a`
- `KERNEL32!EnterCriticalSection` at `0x140057c3a`
- `KERNEL32!EnterCriticalSection` at `0x140057c3a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140058051`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140058051`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140057fec`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x140057fec`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057d14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057e80`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005813e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057d14`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057e80`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005813e`

## string_xrefs

- `0x140057cc0`: `RegistryNotify`
- `0x140057e19`: `RegistryNotify`
- `0x1400580d8`: `RegistryNotify`
- `0x1400581c5`: `RegistryNotify`
- `0x140057dd0`: `CreateEvent() failed creating event to sync with reg notify thread, error = %1%`
- `0x140057d0d`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057d24`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057e79`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057e90`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140058137`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x14005814e`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057c97`: `Registry Notification initialized more than once.`
- `0x140057c6b`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize`
- `0x140057d9e`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize`
- `0x140057ff6`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize`
- `0x14005819e`: `Registry Notification initialized.`
- `0x140058030`: `BeginThreadEx() for reg. notify failed. errno = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::Initialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 FileId; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  bool v10; // zf
  HANDLE EventW; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  char *v16; // rax
  const char *v17; // rax
  _QWORD *v18; // r15
  __int64 v19; // rax
  __int64 v20; // rdx
  volatile signed __int32 *v21; // rcx
  __int64 v22; // rax
  volatile signed __int32 *v23; // rbx
  _DWORD *v24; // rbx
  volatile signed __int32 *v25; // r15
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rbx
  _QWORD *v30; // rcx
  _QWORD *v31; // rbx
  char *v32; // rax
  const char *v33; // rax
  void *Block[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  __int128 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  __int128 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  int v46; // [rsp+B0h] [rbp-50h]
  char *v47[2]; // [rsp+B8h] [rbp-48h] BYREF
  char *v48; // [rsp+C8h] [rbp-38h] BYREF
  int v49; // [rsp+D8h] [rbp-28h]
  void **v50; // [rsp+E8h] [rbp-18h] BYREF
  char *v51; // [rsp+F8h] [rbp-8h] BYREF

  Block[1] = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v4 = a1 + 16;
  v36 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(v4 + 40) == 1 )
    *(_DWORD *)(v4 + 44) = GetCurrentThreadId();
  v35 = 1;
  if ( *(_BYTE *)(a1 + 112) )
  {
    std::string::string(
      &v43,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize");
    v46 = 124;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v40,
      L"Registry Notification initialized more than once.",
      0x31u);
    v37 = 0;
    v38 = 0;
    v39 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v37, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)&v43, 1, (int)&v37, (__int64)&v40);
    std::wstring::~wstring((char **)&v37);
    std::wstring::~wstring((char **)&v40);
    std::string::~string((char **)&v43);
    v5 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6);
    v8 = 0xF0F00000001LL;
LABEL_8:
    v9 = v8 | (FileId << 52);
    v10 = (*(_DWORD *)(v4 + 40))-- == 1;
    if ( v10 )
      *(_DWORD *)(v4 + 44) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v4);
    return v9;
  }
  if ( !*(_QWORD *)(a1 + 96) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)(a1 + 96) = EventW;
    if ( !EventW )
    {
      LODWORD(Block[0]) = GetLastError();
      std::string::string(
        &v43,
        "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV:"
        ":Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize");
      v46 = 133;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v40,
        L"CreateEvent() failed creating event to sync with reg notify thread, error = %1%",
        0x4Fu);
      v14 = AppV::Log::fmt(v13, v47, &v40);
      v15 = AppV::LogFormatter::operator%<unsigned long>(v14, (__int64)Block);
      v37 = 0;
      v38 = 0;
      v39 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v37, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)&v43, 1, (int)&v37, v15);
      std::wstring::~wstring((char **)&v37);
      v47[0] = (char *)&AppV::LogFormatter::`vftable';
      std::wstring::~wstring(&v48);
      std::wstring::~wstring((char **)&v40);
      std::string::~string((char **)&v43);
      v16 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
      if ( v16 )
        v17 = v16 + 1;
      else
        v17 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17);
      v8 = 0x100F00000003LL;
      goto LABEL_8;
    }
  }
  v18 = operator new(0x20u);
  Block[0] = v18;
  v19 = *(_QWORD *)(a1 + 72);
  if ( v19 )
    _InterlockedAdd((volatile signed __int32 *)(v19 + 8), 1u);
  v20 = *(_QWORD *)(a1 + 64);
  v21 = *(volatile signed __int32 **)(a1 + 72);
  v22 = *(_QWORD *)(a1 + 96);
  *v18 = a2;
  v18[1] = v22;
  v18[2] = 0;
  v18[3] = 0;
  v23 = v21;
  if ( v21 )
    _InterlockedAdd(v21 + 2, 1u);
  v18[2] = v20;
  v18[3] = v21;
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  v24 = operator new(0x18u);
  *(_OWORD *)v24 = 0;
  v24[2] = 1;
  v24[3] = 1;
  *(_QWORD *)v24 = &std::_Ref_count<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::`vftable';
  *((_QWORD *)v24 + 2) = v18;
  Block[0] = 0;
  std::_Temporary_owner<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::~_Temporary_owner<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>((_QWORD **)Block);
  *(_QWORD *)(a1 + 80) = v18;
  v25 = *(volatile signed __int32 **)(a1 + 88);
  *(_QWORD *)(a1 + 88) = v24;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = _o__beginthreadex(
          0,
          0,
          AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor,
          *(_QWORD *)(a1 + 80),
          0,
          0);
  *(_QWORD *)(a1 + 104) = v26;
  if ( !v26 )
  {
    std::string::string(
      v47,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize");
    v49 = 145;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v43 = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v43,
      L"BeginThreadEx() for reg. notify failed. errno = %1%",
      0x33u);
    v28 = AppV::Log::fmt(v27, &v50, &v43);
    v29 = _o__errno();
    ++*(_DWORD *)(v28 + 8);
    AppV::LogFormatter::build_substitution_list(v28, Block);
    v30 = Block[0];
    if ( Block[0] )
    {
      *(_QWORD *)&v40 = v28;
      *((_QWORD *)&v40 + 1) = v29;
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_54aca1457d10a53ebee800fd4da1c5e8_>(
        &v37,
        Block[0],
        0,
        &v40);
      v30 = Block[0];
    }
    Block[0] = 0;
    if ( v30 )
    {
      do
      {
        v31 = (_QWORD *)*v30;
        operator delete(v30);
        v30 = v31;
      }
      while ( v31 );
    }
    v37 = 0;
    v38 = 0;
    v39 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v37, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v47, 1, (int)&v37, v28);
    std::wstring::~wstring((char **)&v37);
    v50 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v51);
    std::wstring::~wstring((char **)&v43);
    std::string::~string(v47);
    v32 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
    if ( v32 )
      v33 = v32 + 1;
    else
      v33 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v33);
    v8 = 0x120F00000003LL;
    goto LABEL_8;
  }
  *(_BYTE *)(a1 + 112) = 1;
  std::string::string(
    v47,
    "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Cli"
    "ent::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Initialize");
  v49 = 151;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v37, L"Registry Notification initialized.", 0x22u);
  v43 = 0;
  v44 = 0;
  v45 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v43, L"RegistryNotify", 0xEu);
  AppV::DecoratedLog::operator()((char *)v47, 4, (int)&v43, (__int64)&v37);
  std::wstring::~wstring((char **)&v43);
  std::wstring::~wstring((char **)&v37);
  std::string::~string(v47);
  v10 = (*(_DWORD *)(v4 + 40))-- == 1;
  if ( v10 )
    *(_DWORD *)(v4 + 44) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140057bf0  mov     [rsp-8+arg_8], rbx
0x140057bf5  mov     [rsp-8+arg_10], rsi
0x140057bfa  push    rbp
0x140057bfb  push    rdi
0x140057bfc  push    r12
0x140057bfe  push    r13
0x140057c00  push    r15
0x140057c02  lea     rbp, [rsp-20h]
0x140057c07  sub     rsp, 120h
0x140057c0e  mov     rax, cs:__security_cookie
0x140057c15  xor     rax, rsp
0x140057c18  mov     [rbp+40h+var_28], rax
0x140057c1c  mov     rbx, rdx
0x140057c1f  mov     rsi, rcx
0x140057c22  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140057c29  mov     [rsp+140h+var_108], rax
0x140057c2e  lea     rdi, [rcx+10h]
0x140057c32  mov     [rsp+140h+var_F8], rdi
0x140057c37  mov     rcx, rdi; lpCriticalSection
0x140057c3a  call    cs:__imp_EnterCriticalSection
0x140057c40  mov     r13d, 1
0x140057c46  add     [rdi+28h], r13d
0x140057c4a  cmp     [rdi+28h], r13d
0x140057c4e  jnz     short loc_140057C59
0x140057c50  call    cs:__imp_GetCurrentThreadId
0x140057c56  mov     [rdi+2Ch], eax
0x140057c59  mov     [rsp+140h+var_100], r13b
0x140057c5e  xor     r12d, r12d
0x140057c61  cmp     [rsi+70h], r12b
0x140057c65  jz      loc_140057D69
0x140057c6b  lea     rdx, aAppvClientServ_5; "AppV::Client::Service::Impl::SettingMan"...
0x140057c72  lea     rcx, [rbp+40h+var_B0]
0x140057c76  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140057c7b  mov     [rbp+40h+var_90], 7Ch ; '|'
0x140057c82  xorps   xmm0, xmm0
0x140057c85  movups  [rsp+140h+var_D0], xmm0
0x140057c8a  mov     [rbp+40h+var_C0], r12
0x140057c8e  mov     [rbp+40h+var_B8], r12
0x140057c92  lea     r8d, [r12+31h]
0x140057c97  lea     rdx, aRegistryNotifi; "Registry Notification initialized more "...
0x140057c9e  lea     rcx, [rsp+140h+var_D0]
0x140057ca3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140057ca8  nop
0x140057ca9  xorps   xmm0, xmm0
0x140057cac  movups  [rsp+140h+var_F0], xmm0
0x140057cb1  mov     [rsp+140h+var_E0], r12
0x140057cb6  mov     [rsp+140h+var_D8], r12
0x140057cbb  lea     r8d, [r12+0Eh]
0x140057cc0  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140057cc7  lea     rcx, [rsp+140h+var_F0]
0x140057ccc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140057cd1  nop
0x140057cd2  lea     r9, [rsp+140h+var_D0]
0x140057cd7  lea     r8, [rsp+140h+var_F0]
0x140057cdc  mov     edx, r13d
0x140057cdf  lea     rcx, [rbp+40h+var_B0]
0x140057ce3  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140057ce8  nop
0x140057ce9  lea     rcx, [rsp+140h+var_F0]
0x140057cee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057cf3  nop
0x140057cf4  lea     rcx, [rsp+140h+var_D0]
0x140057cf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057cfe  nop
0x140057cff  lea     rcx, [rbp+40h+var_B0]
0x140057d03  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140057d08  lea     edx, [r12+5Ch]; Ch
0x140057d0d  lea     rcx, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x140057d14  call    cs:__imp_strrchr
0x140057d1a  test    rax, rax
0x140057d1d  jz      short loc_140057D24
0x140057d1f  add     rax, r13
0x140057d22  jmp     short loc_140057D2B
0x140057d24  lea     rax, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x140057d2b  mov     rdx, rax; char *
0x140057d2e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140057d35  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140057d3a  mov     rbx, rax
0x140057d3d  mov     rax, 0F0F00000001h
0x140057d47  shl     rbx, 34h
0x140057d4b  or      rbx, rax
0x140057d4e  sub     dword ptr [rdi+28h], 1
0x140057d52  jnz     short loc_140057D58
0x140057d54  mov     [rdi+2Ch], r12d
0x140057d58  mov     rcx, rdi; lpCriticalSection
0x140057d5b  call    cs:__imp_LeaveCriticalSection
0x140057d61  mov     rax, rbx
0x140057d64  jmp     loc_14005822A
0x140057d69  mov     rax, [rsi+60h]
0x140057d6d  test    rax, rax
0x140057d70  jnz     loc_140057EB8
0x140057d76  xor     r9d, r9d; lpName
0x140057d79  xor     r8d, r8d; bInitialState
0x140057d7c  mov     edx, r13d; bManualReset
0x140057d7f  xor     ecx, ecx; lpEventAttributes
0x140057d81  call    cs:__imp_CreateEventW
0x140057d87  mov     [rsi+60h], rax
0x140057d8b  test    rax, rax
0x140057d8e  jnz     loc_140057EB8
0x140057d94  call    cs:__imp_GetLastError
0x140057d9a  mov     dword ptr [rsp+140h+Block], eax
0x140057d9e  lea     rdx, aAppvClientServ_5; "AppV::Client::Service::Impl::SettingMan"...
0x140057da5  lea     rcx, [rbp+40h+var_B0]
0x140057da9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140057dae  mov     [rbp+40h+var_90], 85h
0x140057db5  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140057dba  xorps   xmm0, xmm0
0x140057dbd  movups  [rsp+140h+var_D0], xmm0
0x140057dc2  mov     [rbp+40h+var_C0], r12
0x140057dc6  mov     [rbp+40h+var_B8], r12
0x140057dca  mov     r8d, 4Fh ; 'O'
0x140057dd0  lea     rdx, aCreateeventFai; "CreateEvent() failed creating event to "...
0x140057dd7  lea     rcx, [rsp+140h+var_D0]
0x140057ddc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140057de1  nop
0x140057de2  lea     r8, [rsp+140h+var_D0]
0x140057de7  lea     rdx, [rbp+40h+var_88]
0x140057deb  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140057df0  nop
0x140057df1  lea     rdx, [rsp+140h+Block]
0x140057df6  mov     rcx, rax
0x140057df9  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140057dfe  mov     rbx, rax
0x140057e01  xorps   xmm0, xmm0
0x140057e04  movups  [rsp+140h+var_F0], xmm0
0x140057e09  mov     [rsp+140h+var_E0], r12
0x140057e0e  mov     [rsp+140h+var_D8], r12
0x140057e13  mov     r8d, 0Eh
0x140057e19  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140057e20  lea     rcx, [rsp+140h+var_F0]
0x140057e25  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140057e2a  nop
0x140057e2b  mov     r9, rbx
0x140057e2e  lea     r8, [rsp+140h+var_F0]
0x140057e33  mov     edx, r13d
0x140057e36  lea     rcx, [rbp+40h+var_B0]
0x140057e3a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140057e3f  nop
0x140057e40  lea     rcx, [rsp+140h+var_F0]
0x140057e45  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057e4a  nop
0x140057e4b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140057e52  mov     [rbp+40h+var_88], rax
0x140057e56  lea     rcx, [rbp+40h+var_78]
0x140057e5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057e5f  nop
0x140057e60  lea     rcx, [rsp+140h+var_D0]
0x140057e65  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057e6a  nop
0x140057e6b  lea     rcx, [rbp+40h+var_B0]
0x140057e6f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140057e74  mov     edx, 5Ch ; '\'; Ch
0x140057e79  lea     rcx, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x140057e80  call    cs:__imp_strrchr
0x140057e86  test    rax, rax
0x140057e89  jz      short loc_140057E90
0x140057e8b  add     rax, r13
0x140057e8e  jmp     short loc_140057E97
0x140057e90  lea     rax, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x140057e97  mov     rdx, rax; char *
0x140057e9a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140057ea1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140057ea6  mov     rbx, rax
0x140057ea9  mov     rax, 100F00000003h
0x140057eb3  jmp     loc_140057D47
0x140057eb8  mov     ecx, 20h ; ' '; Size
0x140057ebd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057ec2  mov     r15, rax
0x140057ec5  mov     [rsp+140h+Block], rax
0x140057eca  mov     rax, [rsi+48h]
0x140057ece  test    rax, rax
0x140057ed1  jz      short loc_140057ED8
0x140057ed3  lock add [rax+8], r13d
0x140057ed8  mov     rdx, [rsi+40h]
0x140057edc  mov     rcx, [rsi+48h]
0x140057ee0  mov     rax, [rsi+60h]
0x140057ee4  mov     [r15], rbx
0x140057ee7  mov     [r15+8], rax
0x140057eeb  mov     [r15+10h], r12
0x140057eef  mov     [r15+18h], r12
0x140057ef3  mov     rax, rcx
0x140057ef6  mov     rbx, rcx
0x140057ef9  test    rcx, rcx
0x140057efc  jz      short loc_140057F03
0x140057efe  lock add [rcx+8], r13d
0x140057f03  mov     [r15+10h], rdx
0x140057f07  mov     [r15+18h], rcx
0x140057f0b  test    rax, rax
0x140057f0e  jz      short loc_140057F47
0x140057f10  or      eax, 0FFFFFFFFh
0x140057f13  lock xadd [rbx+8], eax
0x140057f18  cmp     eax, 1
0x140057f1b  jnz     short loc_140057F47
0x140057f1d  mov     rax, [rbx]
0x140057f20  mov     rcx, rbx
0x140057f23  mov     rax, [rax]
0x140057f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057f2b  or      eax, 0FFFFFFFFh
0x140057f2e  lock xadd [rbx+0Ch], eax
0x140057f33  cmp     eax, 1
0x140057f36  jnz     short loc_140057F47
0x140057f38  mov     rax, [rbx]
0x140057f3b  mov     rcx, rbx
0x140057f3e  mov     rax, [rax+8]
0x140057f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057f47  mov     [rsp+140h+Block], r15
0x140057f4c  mov     ecx, 18h; Size
0x140057f51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057f56  mov     rbx, rax
0x140057f59  mov     [rsp+140h+Block], rax
0x140057f5e  xorps   xmm0, xmm0
0x140057f61  movups  xmmword ptr [rax], xmm0
0x140057f64  mov     [rax+8], r13d
0x140057f68  mov     [rax+0Ch], r13d
0x140057f6c  lea     rax, ??_7?$_Ref_count@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::`vftable'
0x140057f73  mov     [rbx], rax
0x140057f76  mov     [rbx+10h], r15
0x140057f7a  mov     [rsp+140h+Block], r12
0x140057f7f  lea     rcx, [rsp+140h+Block]
0x140057f84  call    ??1?$_Temporary_owner@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@@std@@QEAA@XZ; std::_Temporary_owner<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::~_Temporary_owner<AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>(void)
0x140057f89  mov     [rsi+50h], r15
0x140057f8d  mov     r15, [rsi+58h]
0x140057f91  mov     [rsi+58h], rbx
0x140057f95  test    r15, r15
0x140057f98  jz      short loc_140057FD3
0x140057f9a  or      eax, 0FFFFFFFFh
0x140057f9d  lock xadd [r15+8], eax
0x140057fa3  cmp     eax, 1
0x140057fa6  jnz     short loc_140057FD3
0x140057fa8  mov     rax, [r15]
0x140057fab  mov     rcx, r15
0x140057fae  mov     rax, [rax]
0x140057fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057fb6  or      eax, 0FFFFFFFFh
0x140057fb9  lock xadd [r15+0Ch], eax
0x140057fbf  cmp     eax, 1
0x140057fc2  jnz     short loc_140057FD3
0x140057fc4  mov     rax, [r15]
0x140057fc7  mov     rcx, r15
0x140057fca  mov     rax, [rax+8]
0x140057fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057fd3  mov     [rsp+140h+var_118], r12
0x140057fd8  mov     [rsp+140h+var_120], r12d
0x140057fdd  mov     r9, [rsi+50h]
0x140057fe1  lea     r8, ?Monitor@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@SAIPEAX@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::Monitor(void *)
0x140057fe8  xor     edx, edx
0x140057fea  xor     ecx, ecx
0x140057fec  call    cs:__imp__o__beginthreadex
0x140057ff2  mov     [rsi+68h], rax
0x140057ff6  lea     rdx, aAppvClientServ_5; "AppV::Client::Service::Impl::SettingMan"...
0x140057ffd  lea     rcx, [rbp+40h+var_88]
0x140058001  test    rax, rax
0x140058004  jnz     loc_140058176
0x14005800a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005800f  mov     [rbp+40h+var_68], 91h
0x140058016  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005801b  xorps   xmm0, xmm0
0x14005801e  movups  [rbp+40h+var_B0], xmm0
0x140058022  mov     [rbp+40h+var_A0], r12
0x140058026  mov     [rbp+40h+var_98], r12
0x14005802a  mov     r8d, 33h ; '3'
0x140058030  lea     rdx, aBeginthreadexF; "BeginThreadEx() for reg. notify failed."...
0x140058037  lea     rcx, [rbp+40h+var_B0]
0x14005803b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140058040  nop
0x140058041  lea     r8, [rbp+40h+var_B0]
0x140058045  lea     rdx, [rbp+40h+var_58]
0x140058049  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005804e  mov     rsi, rax
0x140058051  call    cs:__imp__o__errno
0x140058057  mov     rbx, rax
0x14005805a  mov     r8d, [rsi+8]
0x14005805e  lea     ecx, [r8+1]
0x140058062  mov     [rsi+8], ecx
0x140058065  lea     rdx, [rsp+140h+Block]
0x14005806a  mov     rcx, rsi
0x14005806d  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x140058072  nop
0x140058073  mov     rcx, [rsp+140h+Block]
0x140058078  test    rcx, rcx
0x14005807b  jz      short loc_1400580A1
0x14005807d  mov     r8, r12
0x140058080  mov     qword ptr [rsp+140h+var_D0], rsi
0x140058085  mov     qword ptr [rsp+140h+var_D0+8], rbx
0x14005808a  lea     r9, [rsp+140h+var_D0]
0x14005808f  mov     rdx, rcx
0x140058092  lea     rcx, [rsp+140h+var_F0]
0x140058097  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_54aca1457d10a53ebee800fd4da1c5e8_@@@std@@YA?AV_lambda_54aca1457d10a53ebee800fd4da1c5e8_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_54aca1457d10a53ebee800fd4da1c5e8_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_54aca1457d10a53ebee800fd4da1c5e8_)
0x14005809c  mov     rcx, [rsp+140h+Block]; Block
0x1400580a1  mov     [rsp+140h+Block], r12
0x1400580a6  test    rcx, rcx
0x1400580a9  jz      short loc_1400580C0
0x1400580ab  mov     rbx, [rcx]
0x1400580ae  mov     edx, 20h ; ' '
0x1400580b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400580b8  mov     rcx, rbx
0x1400580bb  test    rbx, rbx
0x1400580be  jnz     short loc_1400580AB
0x1400580c0  xorps   xmm0, xmm0
0x1400580c3  movups  [rsp+140h+var_F0], xmm0
  ... truncated ...
```
