# AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(void)

- ea: `0x14005a230`
- end: `0x14005a4d1`
- name: `?ShutdownWatcherThread@?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@AEAA_KXZ`
- size: `673`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x14005607c`
- `0x140057770`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14005a230`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14005a257`
- `KERNEL32!SetEvent` at `0x14005a257`
- `KERNEL32!GetLastError` at `0x14005a266`
- `KERNEL32!GetLastError` at `0x14005a266`
- `KERNEL32!WaitForSingleObject` at `0x14005a38b`
- `KERNEL32!WaitForSingleObject` at `0x14005a38b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005a348`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005a475`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005a348`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005a475`

## string_xrefs

- `0x14005a2e3`: `RegistryNotify`
- `0x14005a410`: `RegistryNotify`
- `0x14005a341`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x14005a358`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x14005a46e`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x14005a485`: `admin\appman\appv\client\host\service\registrynotification\SettingManager.h`
- `0x14005a3cd`: `WaitForSingleObject() failure while waiting for the reg. notify thread to terminate, retcode = %1%`
- `0x14005a2a0`: `SetEvent() failed setting the event that shuts down the reg notify thread, error = %1%`
- `0x14005a26f`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::ShutdownWatcherThread`
- `0x14005a39c`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::ShutdownWatcherThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rbx
  char *v6; // rax
  const char *v7; // rax
  unsigned __int64 FileId; // rax
  __int64 v9; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rax
  DWORD LastError; // [rsp+20h] [rbp-59h] BYREF
  DWORD v18; // [rsp+24h] [rbp-55h] BYREF
  __int128 v19; // [rsp+28h] [rbp-51h] BYREF
  __int128 v20; // [rsp+38h] [rbp-41h]
  __int128 v21; // [rsp+48h] [rbp-31h] BYREF
  __int128 v22; // [rsp+58h] [rbp-21h]
  char *v23[4]; // [rsp+68h] [rbp-11h] BYREF
  int v24; // [rsp+88h] [rbp+Fh]
  _QWORD v25[2]; // [rsp+90h] [rbp+17h] BYREF
  char *v26[4]; // [rsp+A0h] [rbp+27h] BYREF

  if ( !SetEvent(*(HANDLE *)(a1 + 96)) )
  {
    LastError = GetLastError();
    std::string::string(
      v23,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::ShutdownWatcherThread");
    v24 = 186;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v2);
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v21,
      L"SetEvent() failed setting the event that shuts down the reg notify thread, error = %1%",
      0x56u);
    v4 = AppV::Log::fmt(v3, v25, &v21);
    v5 = AppV::LogFormatter::operator%<unsigned long>(v4, (__int64)&LastError);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v23, 1, (int)&v19, v5);
    std::wstring::~wstring((char **)&v19);
    v25[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v26);
    std::wstring::~wstring((char **)&v21);
    std::string::~string(v23);
    v6 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
    if ( v6 )
      v7 = v6 + 1;
    else
      v7 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v7);
    v9 = 0x170F00000004LL;
    return v9 | (FileId << 52);
  }
  v18 = WaitForSingleObject(*(HANDLE *)(a1 + 104), 0xFFFFFFFF);
  if ( v18 )
  {
    std::string::string(
      v23,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::ShutdownWatcherThread");
    v24 = 196;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v11);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v19,
      L"WaitForSingleObject() failure while waiting for the reg. notify thread to terminate, retcode = %1%",
      0x62u);
    v13 = AppV::Log::fmt(v12, v25, &v19);
    v14 = AppV::LogFormatter::operator%<unsigned long>(v13, (__int64)&v18);
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v21, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()((char *)v23, 1, (int)&v21, v14);
    std::wstring::~wstring((char **)&v21);
    v25[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v26);
    std::wstring::~wstring((char **)&v19);
    std::string::~string(v23);
    v15 = strrchr("admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h", 92);
    if ( v15 )
      v16 = v15 + 1;
    else
      v16 = "admin\\appman\\appv\\client\\host\\service\\registrynotification\\SettingManager.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
    v9 = 0x180F00000004LL;
    return v9 | (FileId << 52);
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14005a230  mov     [rsp-8+arg_8], rbx
0x14005a235  push    rbp
0x14005a236  lea     rbp, [rsp-57h]
0x14005a23b  sub     rsp, 0D0h
0x14005a242  mov     rax, cs:__security_cookie
0x14005a249  xor     rax, rsp
0x14005a24c  mov     [rbp+57h+var_10], rax
0x14005a250  mov     rbx, rcx
0x14005a253  mov     rcx, [rcx+60h]; hEvent
0x14005a257  call    cs:__imp_SetEvent
0x14005a25d  cmp     eax, 1
0x14005a260  jz      loc_14005A384
0x14005a266  call    cs:__imp_GetLastError
0x14005a26c  mov     [rbp+57h+var_B0], eax
0x14005a26f  lea     rdx, aAppvClientServ_9; "AppV::Client::Service::Impl::SettingMan"...
0x14005a276  lea     rcx, [rbp+57h+var_68]
0x14005a27a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005a27f  mov     [rbp+57h+var_48], 0BAh
0x14005a286  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005a28b  xorps   xmm0, xmm0
0x14005a28e  movups  [rbp+57h+var_88], xmm0
0x14005a292  xorps   xmm1, xmm1
0x14005a295  movdqu  [rbp+57h+var_78], xmm1
0x14005a29a  mov     r8d, 56h ; 'V'
0x14005a2a0  lea     rdx, aSeteventFailed; "SetEvent() failed setting the event tha"...
0x14005a2a7  lea     rcx, [rbp+57h+var_88]
0x14005a2ab  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a2b0  nop
0x14005a2b1  lea     r8, [rbp+57h+var_88]
0x14005a2b5  lea     rdx, [rbp+57h+var_40]
0x14005a2b9  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005a2be  nop
0x14005a2bf  lea     rdx, [rbp+57h+var_B0]
0x14005a2c3  mov     rcx, rax
0x14005a2c6  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14005a2cb  mov     rbx, rax
0x14005a2ce  xorps   xmm0, xmm0
0x14005a2d1  movups  [rbp+57h+var_A8], xmm0
0x14005a2d5  xorps   xmm1, xmm1
0x14005a2d8  movdqu  [rbp+57h+var_98], xmm1
0x14005a2dd  mov     r8d, 0Eh
0x14005a2e3  lea     rdx, aRegistrynotify; "RegistryNotify"
0x14005a2ea  lea     rcx, [rbp+57h+var_A8]
0x14005a2ee  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a2f3  nop
0x14005a2f4  mov     r9, rbx
0x14005a2f7  lea     r8, [rbp+57h+var_A8]
0x14005a2fb  mov     edx, 1
0x14005a300  lea     rcx, [rbp+57h+var_68]
0x14005a304  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005a309  nop
0x14005a30a  lea     rcx, [rbp+57h+var_A8]
0x14005a30e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a313  nop
0x14005a314  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005a31b  mov     [rbp+57h+var_40], rax
0x14005a31f  lea     rcx, [rbp+57h+var_30]
0x14005a323  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a328  nop
0x14005a329  lea     rcx, [rbp+57h+var_88]
0x14005a32d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a332  nop
0x14005a333  lea     rcx, [rbp+57h+var_68]
0x14005a337  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005a33c  mov     edx, 5Ch ; '\'; Ch
0x14005a341  lea     rcx, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x14005a348  call    cs:__imp_strrchr
0x14005a34e  test    rax, rax
0x14005a351  jz      short loc_14005A358
0x14005a353  inc     rax
0x14005a356  jmp     short loc_14005A35F
0x14005a358  lea     rax, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x14005a35f  mov     rdx, rax; char *
0x14005a362  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005a369  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005a36e  mov     rcx, 170F00000004h
0x14005a378  shl     rax, 34h
0x14005a37c  or      rax, rcx
0x14005a37f  jmp     loc_14005A4B4
0x14005a384  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14005a387  mov     rcx, [rbx+68h]; hHandle
0x14005a38b  call    cs:__imp_WaitForSingleObject
0x14005a391  mov     [rbp+57h+var_AC], eax
0x14005a394  test    eax, eax
0x14005a396  jz      loc_14005A4AA
0x14005a39c  lea     rdx, aAppvClientServ_9; "AppV::Client::Service::Impl::SettingMan"...
0x14005a3a3  lea     rcx, [rbp+57h+var_68]
0x14005a3a7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005a3ac  mov     [rbp+57h+var_48], 0C4h
0x14005a3b3  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005a3b8  xorps   xmm0, xmm0
0x14005a3bb  movups  [rbp+57h+var_A8], xmm0
0x14005a3bf  xorps   xmm1, xmm1
0x14005a3c2  movdqu  [rbp+57h+var_98], xmm1
0x14005a3c7  mov     r8d, 62h ; 'b'
0x14005a3cd  lea     rdx, aWaitforsingleo; "WaitForSingleObject() failure while wai"...
0x14005a3d4  lea     rcx, [rbp+57h+var_A8]
0x14005a3d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a3dd  nop
0x14005a3de  lea     r8, [rbp+57h+var_A8]
0x14005a3e2  lea     rdx, [rbp+57h+var_40]
0x14005a3e6  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005a3eb  nop
0x14005a3ec  lea     rdx, [rbp+57h+var_AC]
0x14005a3f0  mov     rcx, rax
0x14005a3f3  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14005a3f8  mov     rbx, rax
0x14005a3fb  xorps   xmm0, xmm0
0x14005a3fe  movups  [rbp+57h+var_88], xmm0
0x14005a402  xorps   xmm1, xmm1
0x14005a405  movdqu  [rbp+57h+var_78], xmm1
0x14005a40a  mov     r8d, 0Eh
0x14005a410  lea     rdx, aRegistrynotify; "RegistryNotify"
0x14005a417  lea     rcx, [rbp+57h+var_88]
0x14005a41b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005a420  nop
0x14005a421  mov     r9, rbx
0x14005a424  lea     r8, [rbp+57h+var_88]
0x14005a428  mov     edx, 1
0x14005a42d  lea     rcx, [rbp+57h+var_68]
0x14005a431  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005a436  nop
0x14005a437  lea     rcx, [rbp+57h+var_88]
0x14005a43b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a440  nop
0x14005a441  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005a448  mov     [rbp+57h+var_40], rax
0x14005a44c  lea     rcx, [rbp+57h+var_30]
0x14005a450  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a455  nop
0x14005a456  lea     rcx, [rbp+57h+var_A8]
0x14005a45a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005a45f  nop
0x14005a460  lea     rcx, [rbp+57h+var_68]
0x14005a464  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005a469  mov     edx, 5Ch ; '\'; Ch
0x14005a46e  lea     rcx, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x14005a475  call    cs:__imp_strrchr
0x14005a47b  test    rax, rax
0x14005a47e  jz      short loc_14005A485
0x14005a480  inc     rax
0x14005a483  jmp     short loc_14005A48C
0x14005a485  lea     rax, aAdminAppmanApp_21; "admin\\appman\\appv\\client\\host\\serv"...
0x14005a48c  mov     rdx, rax; char *
0x14005a48f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005a496  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005a49b  mov     rcx, 180F00000004h
0x14005a4a5  jmp     loc_14005A378
0x14005a4aa  mov     rax, 8000000000h
0x14005a4b4  mov     rcx, [rbp+57h+var_10]
0x14005a4b8  xor     rcx, rsp; StackCookie
0x14005a4bb  call    __security_check_cookie
0x14005a4c0  mov     rbx, [rsp+0D0h+arg_8]
0x14005a4c8  add     rsp, 0D0h
0x14005a4cf  pop     rbp
0x14005a4d0  retn
```
