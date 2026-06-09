# AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::Deinitialize(void)

- ea: `0x140057770`
- end: `0x14005799c`
- name: `?Deinitialize@?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@UEAA_KXZ`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x140057770`
- `0x14005a230`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400577bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400577bd`
- `KERNEL32!LeaveCriticalSection` at `0x140057972`
- `KERNEL32!LeaveCriticalSection` at `0x140057972`
- `KERNEL32!EnterCriticalSection` at `0x1400577ae`
- `KERNEL32!EnterCriticalSection` at `0x1400577ae`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057928`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140057928`

## string_xrefs

- `0x14005782a`: `RegistryNotify`
- `0x1400578d7`: `RegistryNotify`
- `0x140057921`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057938`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x140057804`: `Registry Notification deinitialized.`
- `0x1400577ca`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Deinitialize`
- `0x1400578b1`: `Registry Notification deinitialized without being initialized.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::Deinitialize(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  bool v4; // zf
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 v7; // rax
  __int128 v9; // [rsp+40h] [rbp-19h] BYREF
  __int128 v10; // [rsp+50h] [rbp-9h]
  __int128 v11; // [rsp+60h] [rbp+7h] BYREF
  __int128 v12; // [rsp+70h] [rbp+17h]
  char *v13[4]; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+A0h] [rbp+47h]

  v2 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(v2 + 40) == 1 )
    *(_DWORD *)(v2 + 44) = GetCurrentThreadId();
  if ( *(_BYTE *)(a1 + 112) )
  {
    *(_BYTE *)(a1 + 112) = 0;
    std::string::string(
      v13,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Deinitialize");
    v14 = 165;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v11, L"Registry Notification deinitialized.", 0x24u);
    v9 = 0;
    v10 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v9, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v13, 4, (int)&v9, (__int64)&v11);
    std::wstring::~wstring((char **)&v9);
    std::wstring::~wstring((char **)&v11);
    std::string::~string(v13);
    v3 = AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(a1);
    v4 = (*(_DWORD *)(v2 + 40))-- == 1;
    if ( v4 )
      *(_DWORD *)(v2 + 44) = 0;
  }
  else
  {
    std::string::string(
      v13,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::Deinitialize");
    v14 = 172;
    v9 = 0;
    v10 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v9,
      L"Registry Notification deinitialized without being initialized.",
      0x3Eu);
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v11, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v13, 1, (int)&v11, (__int64)&v9);
    std::wstring::~wstring((char **)&v11);
    std::wstring::~wstring((char **)&v9);
    std::string::~string(v13);
    v5 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
    v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52)
       | 0x150F00000002LL;
    v4 = (*(_DWORD *)(v2 + 40))-- == 1;
    if ( v4 )
      *(_DWORD *)(v2 + 44) = 0;
    v3 = v7;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v3;
}

```

## disassembly

```asm
0x140057770  mov     [rsp-8+arg_8], rbx
0x140057775  mov     [rsp-8+arg_10], rdi
0x14005777a  push    rbp
0x14005777b  lea     rbp, [rsp-57h]
0x140057780  sub     rsp, 0B0h
0x140057787  mov     rax, cs:__security_cookie
0x14005778e  xor     rax, rsp
0x140057791  mov     [rbp+57h+var_8], rax
0x140057795  mov     rdi, rcx
0x140057798  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14005779f  mov     [rbp+57h+var_88], rax
0x1400577a3  lea     rbx, [rcx+10h]
0x1400577a7  mov     [rbp+57h+var_78], rbx
0x1400577ab  mov     rcx, rbx; lpCriticalSection
0x1400577ae  call    cs:__imp_EnterCriticalSection
0x1400577b4  inc     dword ptr [rbx+28h]
0x1400577b7  cmp     dword ptr [rbx+28h], 1
0x1400577bb  jnz     short loc_1400577C6
0x1400577bd  call    cs:__imp_GetCurrentThreadId
0x1400577c3  mov     [rbx+2Ch], eax
0x1400577c6  mov     [rbp+57h+var_80], 1
0x1400577ca  lea     rdx, aAppvClientServ_40; "AppV::Client::Service::Impl::SettingMan"...
0x1400577d1  lea     rcx, [rbp+57h+var_30]
0x1400577d5  cmp     byte ptr [rdi+70h], 0
0x1400577d9  jz      loc_140057890
0x1400577df  mov     byte ptr [rdi+70h], 0
0x1400577e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400577e8  mov     [rbp+57h+var_10], 0A5h
0x1400577ef  xorps   xmm0, xmm0
0x1400577f2  movups  [rbp+57h+var_50], xmm0
0x1400577f6  xorps   xmm1, xmm1
0x1400577f9  movdqu  [rbp+57h+var_40], xmm1
0x1400577fe  mov     r8d, 24h ; '$'
0x140057804  lea     rdx, aRegistryNotifi_0; "Registry Notification deinitialized."
0x14005780b  lea     rcx, [rbp+57h+var_50]
0x14005780f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140057814  nop
0x140057815  xorps   xmm0, xmm0
0x140057818  movups  [rbp+57h+var_70], xmm0
0x14005781c  xorps   xmm1, xmm1
0x14005781f  movdqu  [rbp+57h+var_60], xmm1
0x140057824  mov     r8d, 0Eh
0x14005782a  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140057831  lea     rcx, [rbp+57h+var_70]
0x140057835  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005783a  nop
0x14005783b  lea     r9, [rbp+57h+var_50]
0x14005783f  lea     r8, [rbp+57h+var_70]
0x140057843  mov     edx, 4
0x140057848  lea     rcx, [rbp+57h+var_30]
0x14005784c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140057851  nop
0x140057852  lea     rcx, [rbp+57h+var_70]
0x140057856  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005785b  nop
0x14005785c  lea     rcx, [rbp+57h+var_50]
0x140057860  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057865  nop
0x140057866  lea     rcx, [rbp+57h+var_30]
0x14005786a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005786f  mov     rcx, rdi
0x140057872  call    ?ShutdownWatcherThread@?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@AEAA_KXZ; AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(void)
0x140057877  mov     rdi, rax
0x14005787a  sub     dword ptr [rbx+28h], 1
0x14005787e  jnz     loc_14005796F
0x140057884  mov     dword ptr [rbx+2Ch], 0
0x14005788b  jmp     loc_14005796F
0x140057890  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140057895  mov     [rbp+57h+var_10], 0ACh
0x14005789c  xorps   xmm0, xmm0
0x14005789f  movups  [rbp+57h+var_70], xmm0
0x1400578a3  xorps   xmm1, xmm1
0x1400578a6  movdqu  [rbp+57h+var_60], xmm1
0x1400578ab  mov     r8d, 3Eh ; '>'
0x1400578b1  lea     rdx, aRegistryNotifi_1; "Registry Notification deinitialized wit"...
0x1400578b8  lea     rcx, [rbp+57h+var_70]
0x1400578bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400578c1  nop
0x1400578c2  xorps   xmm0, xmm0
0x1400578c5  movups  [rbp+57h+var_50], xmm0
0x1400578c9  xorps   xmm1, xmm1
0x1400578cc  movdqu  [rbp+57h+var_40], xmm1
0x1400578d1  mov     r8d, 0Eh
0x1400578d7  lea     rdx, aRegistrynotify; "RegistryNotify"
0x1400578de  lea     rcx, [rbp+57h+var_50]
0x1400578e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400578e7  nop
0x1400578e8  lea     r9, [rbp+57h+var_70]
0x1400578ec  lea     r8, [rbp+57h+var_50]
0x1400578f0  mov     edx, 1
0x1400578f5  lea     rcx, [rbp+57h+var_30]
0x1400578f9  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400578fe  nop
0x1400578ff  lea     rcx, [rbp+57h+var_50]
0x140057903  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057908  nop
0x140057909  lea     rcx, [rbp+57h+var_70]
0x14005790d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140057912  nop
0x140057913  lea     rcx, [rbp+57h+var_30]
0x140057917  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005791c  mov     edx, 5Ch ; '\'; Ch
0x140057921  lea     rcx, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x140057928  call    cs:__imp_strrchr
0x14005792e  test    rax, rax
0x140057931  jz      short loc_140057938
0x140057933  inc     rax
0x140057936  jmp     short loc_14005793F
0x140057938  lea     rax, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x14005793f  mov     rdx, rax; char *
0x140057942  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140057949  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005794e  shl     rax, 34h
0x140057952  mov     rcx, 150F00000002h
0x14005795c  or      rax, rcx
0x14005795f  sub     dword ptr [rbx+28h], 1
0x140057963  jnz     short loc_14005796C
0x140057965  mov     dword ptr [rbx+2Ch], 0
0x14005796c  mov     rdi, rax
0x14005796f  mov     rcx, rbx; lpCriticalSection
0x140057972  call    cs:__imp_LeaveCriticalSection
0x140057978  mov     rax, rdi
0x14005797b  mov     rcx, [rbp+57h+var_8]
0x14005797f  xor     rcx, rsp; StackCookie
0x140057982  call    __security_check_cookie
0x140057987  lea     r11, [rsp+0B0h+var_s0]
0x14005798f  mov     rbx, [r11+18h]
0x140057993  mov     rdi, [r11+20h]
0x140057997  mov     rsp, r11
0x14005799a  pop     rbp
0x14005799b  retn
```
