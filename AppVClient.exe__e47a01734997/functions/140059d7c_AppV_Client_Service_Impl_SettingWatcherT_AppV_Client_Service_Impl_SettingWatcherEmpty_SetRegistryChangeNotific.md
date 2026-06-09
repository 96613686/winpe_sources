# AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification(AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData *,unsigned __int64)

- ea: `0x140059d7c`
- end: `0x140059f6a`
- name: `?SetRegistryChangeNotification@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJPEAUEventData@12345@_K@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140058b9c`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140059d7c`
- `0x140059f70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140059e14`
- `ADVAPI32!RegCloseKey` at `0x140059e14`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140059dfc`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140059e56`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140059dfc`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140059e56`
- `KERNEL32!ResetEvent` at `0x140059dd5`
- `KERNEL32!ResetEvent` at `0x140059dd5`
- `KERNEL32!WaitForSingleObject` at `0x140059dc3`
- `KERNEL32!WaitForSingleObject` at `0x140059dc3`

## string_xrefs

- `0x140059f09`: `RegistryNotify`
- `0x140059ec6`: `failure during inital setting of notifychangekeyvalue event, error = %1%`
- `0x140059e95`: `AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryChangeNotification(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned int v7; // eax
  HKEY v8; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // [rsp+30h] [rbp-69h] BYREF
  _OWORD v15[2]; // [rsp+38h] [rbp-61h] BYREF
  _OWORD v16[2]; // [rsp+58h] [rbp-41h] BYREF
  char *v17[4]; // [rsp+78h] [rbp-21h] BYREF
  int v18; // [rsp+98h] [rbp-1h]
  void **v19; // [rsp+A0h] [rbp+7h] BYREF
  char *v20; // [rsp+B0h] [rbp+17h] BYREF

  v5 = 0;
  if ( !a3 )
    return 0;
  while ( 1 )
  {
    v6 = a2 + 72 * v5;
    if ( !WaitForSingleObject(*(HANDLE *)(v6 + 24), 0) )
    {
      ResetEvent(*(HANDLE *)(v6 + 24));
      v7 = RegNotifyChangeKeyValue(
             *(HKEY *)v6,
             *(unsigned __int8 *)(v6 + 32),
             (*(_BYTE *)(v6 + 32) != 0) + 4,
             *(HANDLE *)(v6 + 24),
             1);
      v14 = v7;
      if ( v7 == 1018 )
      {
        v8 = *(HKEY *)v6;
        if ( *(_QWORD *)v6 )
        {
          RegCloseKey(v8);
          *(_QWORD *)v6 = 0;
        }
        v7 = AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(
               (__int64)v8,
               (const WCHAR *)(v6 + 40),
               *(_BYTE *)(v6 + 32),
               a2 + 72 * v5);
        if ( !v7 )
          v7 = RegNotifyChangeKeyValue(
                 *(HKEY *)v6,
                 *(unsigned __int8 *)(v6 + 32),
                 (*(_BYTE *)(v6 + 32) != 0) + 4,
                 *(HANDLE *)(v6 + 24),
                 1);
        v14 = v7;
      }
      if ( v7 )
        break;
    }
    if ( ++v5 >= a3 )
      return 0;
  }
  std::string::string(
    v17,
    "AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryCh"
    "angeNotification");
  v18 = 300;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v10);
  memset(v16, 0, sizeof(v16));
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)v16,
    L"failure during inital setting of notifychangekeyvalue event, error = %1%",
    0x48u);
  v12 = AppV::Log::fmt(v11, &v19, v16);
  v13 = AppV::LogFormatter::operator%<long>(v12, (__int64)&v14);
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,wchar_t const *>((char **)v15, L"RegistryNotify", 0xEu);
  AppV::DecoratedLog::operator()((char *)v17, 1, (int)v15, v13);
  std::wstring::~wstring((char **)v15);
  v19 = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(&v20);
  std::wstring::~wstring((char **)v16);
  std::string::~string(v17);
  return v14;
}

```

## disassembly

```asm
0x140059d7c  mov     [rsp-8+arg_0], rbx
0x140059d81  mov     [rsp-8+arg_10], rsi
0x140059d86  push    rbp
0x140059d87  push    rdi
0x140059d88  push    r14
0x140059d8a  lea     rbp, [rsp-47h]
0x140059d8f  sub     rsp, 0E0h
0x140059d96  mov     rax, cs:__security_cookie
0x140059d9d  xor     rax, rsp
0x140059da0  mov     [rbp+57h+var_20], rax
0x140059da4  mov     rsi, r8
0x140059da7  mov     r14, rdx
0x140059daa  xor     edi, edi
0x140059dac  test    r8, r8
0x140059daf  jz      loc_140059E6F
0x140059db5  lea     rax, [rdi+rdi*8]
0x140059db9  lea     rbx, [r14+rax*8]
0x140059dbd  xor     edx, edx; dwMilliseconds
0x140059dbf  mov     rcx, [rbx+18h]; hHandle
0x140059dc3  call    cs:__imp_WaitForSingleObject
0x140059dc9  test    eax, eax
0x140059dcb  jnz     loc_140059E63
0x140059dd1  mov     rcx, [rbx+18h]; hEvent
0x140059dd5  call    cs:__imp_ResetEvent
0x140059ddb  movzx   edx, byte ptr [rbx+20h]; bWatchSubtree
0x140059ddf  mov     al, dl
0x140059de1  neg     al
0x140059de3  sbb     r8d, r8d
0x140059de6  neg     r8d
0x140059de9  add     r8d, 4; dwNotifyFilter
0x140059ded  mov     [rsp+0F0h+fAsynchronous], 1; fAsynchronous
0x140059df5  mov     r9, [rbx+18h]; hEvent
0x140059df9  mov     rcx, [rbx]; hKey
0x140059dfc  call    cs:__imp_RegNotifyChangeKeyValue
0x140059e02  mov     [rbp+57h+var_C0], eax
0x140059e05  cmp     eax, 3FAh
0x140059e0a  jnz     short loc_140059E5F
0x140059e0c  mov     rcx, [rbx]; hKey
0x140059e0f  test    rcx, rcx
0x140059e12  jz      short loc_140059E21
0x140059e14  call    cs:__imp_RegCloseKey
0x140059e1a  mov     qword ptr [rbx], 0
0x140059e21  lea     rdx, [rbx+28h]
0x140059e25  mov     r9, rbx
0x140059e28  mov     r8b, [rbx+20h]
0x140059e2c  call    ?SetRegistryNotificationEventData@?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@Impl@Service@Client@AppV@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NAEAUEventData@12345@@Z; AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::SetRegistryNotificationEventData(std::wstring const &,bool,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>::EventData &)
0x140059e31  test    eax, eax
0x140059e33  jnz     short loc_140059E5C
0x140059e35  movzx   edx, byte ptr [rbx+20h]; bWatchSubtree
0x140059e39  mov     al, dl
0x140059e3b  neg     al
0x140059e3d  sbb     r8d, r8d
0x140059e40  neg     r8d
0x140059e43  add     r8d, 4; dwNotifyFilter
0x140059e47  mov     [rsp+0F0h+fAsynchronous], 1; fAsynchronous
0x140059e4f  mov     r9, [rbx+18h]; hEvent
0x140059e53  mov     rcx, [rbx]; hKey
0x140059e56  call    cs:__imp_RegNotifyChangeKeyValue
0x140059e5c  mov     [rbp+57h+var_C0], eax
0x140059e5f  test    eax, eax
0x140059e61  jnz     short loc_140059E95
0x140059e63  inc     rdi
0x140059e66  cmp     rdi, rsi
0x140059e69  jb      loc_140059DB5
0x140059e6f  xor     eax, eax
0x140059e71  mov     rcx, [rbp+57h+var_20]
0x140059e75  xor     rcx, rsp; StackCookie
0x140059e78  call    __security_check_cookie
0x140059e7d  lea     r11, [rsp+0F0h+var_10]
0x140059e85  mov     rbx, [r11+20h]
0x140059e89  mov     rsi, [r11+30h]
0x140059e8d  mov     rsp, r11
0x140059e90  pop     r14
0x140059e92  pop     rdi
0x140059e93  pop     rbp
0x140059e94  retn
0x140059e95  lea     rdx, aAppvClientServ_49; "AppV::Client::Service::Impl::SettingWat"...
0x140059e9c  lea     rcx, [rbp+57h+var_78]
0x140059ea0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140059ea5  mov     [rbp+57h+var_58], 12Ch
0x140059eac  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140059eb1  xorps   xmm0, xmm0
0x140059eb4  movups  [rbp+57h+var_98], xmm0
0x140059eb8  xorps   xmm1, xmm1
0x140059ebb  movdqu  [rbp+57h+var_88], xmm1
0x140059ec0  mov     r8d, 48h ; 'H'
0x140059ec6  lea     rdx, aFailureDuringI; "failure during inital setting of notify"...
0x140059ecd  lea     rcx, [rbp+57h+var_98]
0x140059ed1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140059ed6  nop
0x140059ed7  lea     r8, [rbp+57h+var_98]
0x140059edb  lea     rdx, [rbp+57h+var_50]
0x140059edf  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140059ee4  nop
0x140059ee5  lea     rdx, [rbp+57h+var_C0]
0x140059ee9  mov     rcx, rax
0x140059eec  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x140059ef1  mov     rbx, rax
0x140059ef4  xorps   xmm0, xmm0
0x140059ef7  movups  [rbp+57h+var_B8], xmm0
0x140059efb  xorps   xmm1, xmm1
0x140059efe  movdqu  [rbp+57h+var_A8], xmm1
0x140059f03  mov     r8d, 0Eh
0x140059f09  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140059f10  lea     rcx, [rbp+57h+var_B8]
0x140059f14  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140059f19  nop
0x140059f1a  mov     r9, rbx
0x140059f1d  lea     r8, [rbp+57h+var_B8]
0x140059f21  mov     edx, 1
0x140059f26  lea     rcx, [rbp+57h+var_78]
0x140059f2a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140059f2f  nop
0x140059f30  lea     rcx, [rbp+57h+var_B8]
0x140059f34  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140059f39  nop
0x140059f3a  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140059f41  mov     [rbp+57h+var_50], rax
0x140059f45  lea     rcx, [rbp+57h+var_40]
0x140059f49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140059f4e  nop
0x140059f4f  lea     rcx, [rbp+57h+var_98]
0x140059f53  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140059f58  nop
0x140059f59  lea     rcx, [rbp+57h+var_78]
0x140059f5d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140059f62  mov     eax, [rbp+57h+var_C0]
0x140059f65  jmp     loc_140059E71
```
