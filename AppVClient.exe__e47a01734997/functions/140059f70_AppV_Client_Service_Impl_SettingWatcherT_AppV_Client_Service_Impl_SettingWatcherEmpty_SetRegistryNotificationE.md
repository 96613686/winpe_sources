# AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData &)

- ea: `0x140059f70`
- end: `0x14005a229`
- name: `?SetRegistryNotificationEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NAEAUEventData@12345@@Z`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x140058b9c`
- `0x140059d7c`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x140010158`
- `0x14001f0d0`
- `0x140020c60`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140059f70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005a001`
- `ADVAPI32!RegCloseKey` at `0x14005a001`
- `ADVAPI32!RegCreateKeyExW` at `0x140059fed`
- `ADVAPI32!RegCreateKeyExW` at `0x140059fed`
- `KERNEL32!CreateEventW` at `0x14005a112`
- `KERNEL32!CreateEventW` at `0x14005a112`
- `KERNEL32!GetLastError` at `0x14005a125`
- `KERNEL32!GetLastError` at `0x14005a125`

## string_xrefs

- `0x14005a09a`: `RegistryNotify`
- `0x14005a1a2`: `RegistryNotify`
- `0x14005a04c`: `failed to create reg key '%2%' for monitoring, error = %1%`
- `0x14005a01b`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData`
- `0x14005a12e`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData`
- `0x14005a15f`: `failed to create event for registry monitoring, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(
        __int64 a1,
        const WCHAR *a2,
        char a3,
        __int64 a4)
{
  const WCHAR *v6; // rdi
  LSTATUS v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  HANDLE EventW; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  DWORD LastError; // [rsp+50h] [rbp-69h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-65h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-61h] BYREF
  __int128 v21; // [rsp+60h] [rbp-59h] BYREF
  __int128 v22; // [rsp+70h] [rbp-49h]
  __int128 v23; // [rsp+80h] [rbp-39h] BYREF
  __int128 v24; // [rsp+90h] [rbp-29h]
  char *v25[4]; // [rsp+A0h] [rbp-19h] BYREF
  int v26; // [rsp+C0h] [rbp+7h]
  _QWORD v27[2]; // [rsp+C8h] [rbp+Fh] BYREF
  char *v28[4]; // [rsp+D8h] [rbp+1Fh] BYREF

  v6 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  dwDisposition = 0;
  phkResult = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 0x20019u, 0, &phkResult, &dwDisposition);
  if ( !v7 )
  {
    if ( *(_QWORD *)a4 )
      v7 = RegCloseKey(*(HKEY *)a4);
    *(_QWORD *)a4 = phkResult;
  }
  LastError = v7;
  if ( v7 )
  {
    std::string::string(
      v25,
      "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistry"
      "NotificationEventData");
    v26 = 245;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v8);
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v23,
      L"failed to create reg key '%2%' for monitoring, error = %1%",
      0x3Au);
    v10 = AppV::Log::fmt(v9, v27, &v23);
    v11 = AppV::LogFormatter::operator%<long>(v10, (__int64)&LastError);
    AppV::LogFormatter::perform_substitution<std::wstring>(v11, v6);
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v21, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v25, 1, (int)&v21, v11);
    std::wstring::~wstring((char **)&v21);
    v27[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v28);
    std::wstring::~wstring((char **)&v23);
LABEL_9:
    std::string::~string(v25);
    return LastError;
  }
  if ( !*(_QWORD *)(a4 + 24) )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *(_QWORD *)(a4 + 24) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      std::string::string(
        v25,
        "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegist"
        "ryNotificationEventData");
      v26 = 259;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v14);
      v21 = 0;
      v22 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v21,
        L"failed to create event for registry monitoring, error = %1%",
        0x3Bu);
      v16 = AppV::Log::fmt(v15, v27, &v21);
      v17 = AppV::LogFormatter::operator%<long>(v16, (__int64)&LastError);
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v23, L"RegistryNotify", 0xEu);
      AppV::DecoratedLog::operator()((char *)v25, 1, (int)&v23, v17);
      std::wstring::~wstring((char **)&v23);
      v27[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v28);
      std::wstring::~wstring((char **)&v21);
      goto LABEL_9;
    }
  }
  *(_BYTE *)(a4 + 32) = a3;
  std::wstring::operator=(a4 + 40, v6);
  return 0;
}

```

## disassembly

```asm
0x140059f70  mov     [rsp-8+arg_0], rbx
0x140059f75  push    rbp
0x140059f76  push    rdi
0x140059f77  push    r14
0x140059f79  lea     rbp, [rsp-47h]
0x140059f7e  sub     rsp, 100h
0x140059f85  mov     rax, cs:__security_cookie
0x140059f8c  xor     rax, rsp
0x140059f8f  mov     [rbp+57h+var_18], rax
0x140059f93  mov     rbx, r9
0x140059f96  mov     r14b, r8b
0x140059f99  mov     rdi, rdx
0x140059f9c  cmp     qword ptr [rdx+18h], 7
0x140059fa1  jbe     short loc_140059FA6
0x140059fa3  mov     rdx, [rdx]; lpSubKey
0x140059fa6  mov     [rbp+57h+dwDisposition], 0
0x140059fad  mov     [rbp+57h+var_B8], 0
0x140059fb5  lea     rax, [rbp+57h+dwDisposition]
0x140059fb9  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x140059fbe  lea     rax, [rbp+57h+var_B8]
0x140059fc2  mov     [rsp+110h+phkResult], rax; phkResult
0x140059fc7  mov     [rsp+110h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140059fd0  mov     [rsp+110h+samDesired], 20019h; samDesired
0x140059fd8  mov     [rsp+110h+dwOptions], 0; dwOptions
0x140059fe0  xor     r9d, r9d; lpClass
0x140059fe3  xor     r8d, r8d; Reserved
0x140059fe6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140059fed  call    cs:__imp_RegCreateKeyExW
0x140059ff3  mov     ecx, eax
0x140059ff5  test    eax, eax
0x140059ff7  jnz     short loc_14005A010
0x140059ff9  cmp     [rbx], rcx
0x140059ffc  jz      short loc_14005A009
0x140059ffe  mov     rcx, [rbx]; hKey
0x14005a001  call    cs:__imp_RegCloseKey
0x14005a007  mov     ecx, eax
0x14005a009  mov     rax, [rbp+57h+var_B8]
0x14005a00d  mov     [rbx], rax
0x14005a010  mov     [rbp+57h+var_C0], ecx
0x14005a013  test    ecx, ecx
0x14005a015  jz      loc_14005A0FB
0x14005a01b  lea     rdx, aAppvClientServ_24; "AppV::Client::Service::Impl::SettingWat"...
0x14005a022  lea     rcx, [rbp+57h+var_70]
0x14005a026  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005a02b  mov     [rbp+57h+var_50], 0F5h
0x14005a032  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005a037  xorps   xmm0, xmm0
0x14005a03a  movups  [rbp+57h+var_90], xmm0
0x14005a03e  xorps   xmm1, xmm1
0x14005a041  movdqu  [rbp+57h+var_80], xmm1
0x14005a046  mov     r8d, 3Ah ; ':'
0x14005a04c  lea     rdx, aFailedToCreate_2; "failed to create reg key '%2%' for moni"...
0x14005a053  lea     rcx, [rbp+57h+var_90]
0x14005a057  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a05c  nop
0x14005a05d  lea     r8, [rbp+57h+var_90]
0x14005a061  lea     rdx, [rbp+57h+var_48]
0x14005a065  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005a06a  nop
0x14005a06b  lea     rdx, [rbp+57h+var_C0]
0x14005a06f  mov     rcx, rax
0x14005a072  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005a077  mov     rbx, rax
0x14005a07a  mov     rdx, rdi
0x14005a07d  mov     rcx, rax
0x14005a080  call    ??$perform_substitution@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogFormatter@AppV@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::LogFormatter::perform_substitution<std::wstring>(std::wstring const &)
0x14005a085  xorps   xmm0, xmm0
0x14005a088  movups  [rbp+57h+var_B0], xmm0
0x14005a08c  xorps   xmm1, xmm1
0x14005a08f  movdqu  [rbp+57h+var_A0], xmm1
0x14005a094  mov     r8d, 0Eh
0x14005a09a  lea     rdx, aRegistrynotify; "RegistryNotify"
0x14005a0a1  lea     rcx, [rbp+57h+var_B0]
0x14005a0a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a0aa  nop
0x14005a0ab  mov     r9, rbx
0x14005a0ae  lea     r8, [rbp+57h+var_B0]
0x14005a0b2  mov     edx, 1
0x14005a0b7  lea     rcx, [rbp+57h+var_70]
0x14005a0bb  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005a0c0  nop
0x14005a0c1  lea     rcx, [rbp+57h+var_B0]
0x14005a0c5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a0ca  nop
0x14005a0cb  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005a0d2  mov     [rbp+57h+var_48], rax
0x14005a0d6  lea     rcx, [rbp+57h+var_38]
0x14005a0da  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a0df  nop
0x14005a0e0  lea     rcx, [rbp+57h+var_90]
0x14005a0e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a0e9  nop
0x14005a0ea  lea     rcx, [rbp+57h+var_70]
0x14005a0ee  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005a0f3  mov     eax, [rbp+57h+var_C0]
0x14005a0f6  jmp     loc_14005A209
0x14005a0fb  cmp     qword ptr [rbx+18h], 0
0x14005a100  jnz     loc_14005A1F7
0x14005a106  xor     r9d, r9d; lpName
0x14005a109  lea     edx, [r9+1]; bManualReset
0x14005a10d  xor     ecx, ecx; lpEventAttributes
0x14005a10f  mov     r8d, edx; bInitialState
0x14005a112  call    cs:__imp_CreateEventW
0x14005a118  mov     [rbx+18h], rax
0x14005a11c  test    rax, rax
0x14005a11f  jnz     loc_14005A1F7
0x14005a125  call    cs:__imp_GetLastError
0x14005a12b  mov     [rbp+57h+var_C0], eax
0x14005a12e  lea     rdx, aAppvClientServ_24; "AppV::Client::Service::Impl::SettingWat"...
0x14005a135  lea     rcx, [rbp+57h+var_70]
0x14005a139  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005a13e  mov     [rbp+57h+var_50], 103h
0x14005a145  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005a14a  xorps   xmm0, xmm0
0x14005a14d  movups  [rbp+57h+var_B0], xmm0
0x14005a151  xorps   xmm1, xmm1
0x14005a154  movdqu  [rbp+57h+var_A0], xmm1
0x14005a159  mov     r8d, 3Bh ; ';'
0x14005a15f  lea     rdx, aFailedToCreate_1; "failed to create event for registry mon"...
0x14005a166  lea     rcx, [rbp+57h+var_B0]
0x14005a16a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a16f  nop
0x14005a170  lea     r8, [rbp+57h+var_B0]
0x14005a174  lea     rdx, [rbp+57h+var_48]
0x14005a178  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005a17d  nop
0x14005a17e  lea     rdx, [rbp+57h+var_C0]
0x14005a182  mov     rcx, rax
0x14005a185  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005a18a  mov     rbx, rax
0x14005a18d  xorps   xmm0, xmm0
0x14005a190  movups  [rbp+57h+var_90], xmm0
0x14005a194  xorps   xmm1, xmm1
0x14005a197  movdqu  [rbp+57h+var_80], xmm1
0x14005a19c  mov     r8d, 0Eh
0x14005a1a2  lea     rdx, aRegistrynotify; "RegistryNotify"
0x14005a1a9  lea     rcx, [rbp+57h+var_90]
0x14005a1ad  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a1b2  nop
0x14005a1b3  mov     r9, rbx
0x14005a1b6  lea     r8, [rbp+57h+var_90]
0x14005a1ba  mov     edx, 1
0x14005a1bf  lea     rcx, [rbp+57h+var_70]
0x14005a1c3  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005a1c8  nop
0x14005a1c9  lea     rcx, [rbp+57h+var_90]
0x14005a1cd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a1d2  nop
0x14005a1d3  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005a1da  mov     [rbp+57h+var_48], rax
0x14005a1de  lea     rcx, [rbp+57h+var_38]
0x14005a1e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a1e7  nop
0x14005a1e8  lea     rcx, [rbp+57h+var_B0]
0x14005a1ec  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a1f1  nop
0x14005a1f2  jmp     loc_14005A0EA
0x14005a1f7  mov     [rbx+20h], r14b
0x14005a1fb  lea     rcx, [rbx+28h]
0x14005a1ff  mov     rdx, rdi
0x14005a202  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14005a207  xor     eax, eax
0x14005a209  mov     rcx, [rbp+57h+var_18]
0x14005a20d  xor     rcx, rsp; StackCookie
0x14005a210  call    __security_check_cookie
0x14005a215  mov     rbx, [rsp+110h+arg_0]
0x14005a21d  add     rsp, 100h
0x14005a224  pop     r14
0x14005a226  pop     rdi
0x14005a227  pop     rbp
0x14005a228  retn
```
