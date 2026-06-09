# AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::StopDelivery(bool)

- ea: `0x14004fc50`
- end: `0x14005008d`
- name: `?StopDelivery@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@Host@Client@AppV@@UEAA_K_N@Z`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14004e298`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14004fc50`
- `0x140050aa8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14004fd32`
- `KERNEL32!SetEvent` at `0x14004fd32`
- `KERNEL32!ResetEvent` at `0x14004fd02`
- `KERNEL32!ResetEvent` at `0x14004fd02`
- `KERNEL32!CloseHandle` at `0x14004ff28`
- `KERNEL32!CloseHandle` at `0x14004ff28`
- `KERNEL32!GetLastError` at `0x14004fd41`
- `KERNEL32!GetLastError` at `0x14004ff68`
- `KERNEL32!GetLastError` at `0x14004fd41`
- `KERNEL32!GetLastError` at `0x14004ff68`
- `KERNEL32!GetCurrentThreadId` at `0x14004fcf2`
- `KERNEL32!GetCurrentThreadId` at `0x14004fcf2`
- `KERNEL32!WaitForSingleObject` at `0x14004fe77`
- `KERNEL32!WaitForSingleObject` at `0x14004fe77`
- `KERNEL32!LeaveCriticalSection` at `0x14004fd21`
- `KERNEL32!LeaveCriticalSection` at `0x14004fd21`
- `KERNEL32!EnterCriticalSection` at `0x14004fce3`
- `KERNEL32!EnterCriticalSection` at `0x14004fce3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004fc91`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004fe23`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005004a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004fc91`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004fe23`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005004a`

## string_xrefs

- `0x14004fc8a`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004fca1`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004fe1c`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004fe33`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x140050043`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14005005a`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004fd7b`: `Failed to signal the shutdown event for a Client event delivery thread, error = %1%`
- `0x14004feb4`: `While stopping client event delivery, a client event subscriber thread is still active and did not exit within the timeout`
- `0x14004ffa2`: `A Client event delivery thread did not exit when it was signalled to shut down, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
unsigned __int64 __fastcall AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::StopDelivery(
        __int64 a1,
        char a2)
{
  char *v4; // rax
  const char *v5; // rax
  __int64 v7; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  char *v13; // rax
  const char *v14; // rax
  unsigned __int64 FileId; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  DWORD v18; // eax
  void *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rbx
  char *v24; // rax
  const char *v25; // rax
  unsigned __int64 v26; // rax
  DWORD LastError; // [rsp+20h] [rbp-79h] BYREF
  void **v28; // [rsp+28h] [rbp-71h]
  char v29; // [rsp+30h] [rbp-69h]
  __int64 v30; // [rsp+38h] [rbp-61h]
  __int128 v31; // [rsp+40h] [rbp-59h] BYREF
  __int128 v32; // [rsp+50h] [rbp-49h]
  __int128 v33; // [rsp+60h] [rbp-39h] BYREF
  __int128 v34; // [rsp+70h] [rbp-29h]
  char *v35[4]; // [rsp+80h] [rbp-19h] BYREF
  int v36; // [rsp+A0h] [rbp+7h]
  _QWORD v37[2]; // [rsp+A8h] [rbp+Fh] BYREF
  char *v38[4]; // [rsp+B8h] [rbp+1Fh] BYREF

  if ( !*(_QWORD *)(a1 + 112) )
  {
    v4 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5) << 52)
         | 0x2B0E00000202LL;
  }
  v7 = *(_QWORD *)(a1 + 48);
  v28 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v30 = v7;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  if ( ++*(_DWORD *)(v7 + 40) == 1 )
    *(_DWORD *)(v7 + 44) = GetCurrentThreadId();
  ResetEvent(**(HANDLE **)(a1 + 64));
  std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Tidy(*(_QWORD *)(a1 + 80));
  if ( (*(_DWORD *)(v7 + 40))-- == 1 )
    *(_DWORD *)(v7 + 44) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  v29 = 0;
  if ( !SetEvent(**(HANDLE **)(a1 + 96)) )
  {
    LastError = GetLastError();
    std::string::string(
      v35,
      "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliveryP"
      "arameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::StopDelivery");
    v36 = 360;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v9);
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v33,
      L"Failed to signal the shutdown event for a Client event delivery thread, error = %1%",
      0x53u);
    v11 = AppV::Log::fmt(v10, v37, &v33);
    v12 = AppV::LogFormatter::operator%<unsigned long>(v11, (__int64)&LastError);
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v35, 1, (int)&v31, v12);
    std::wstring::~wstring((char **)&v31);
    v37[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v38);
    std::wstring::~wstring((char **)&v33);
    std::string::~string(v35);
    v13 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v13 )
      v14 = v13 + 1;
    else
      v14 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14);
    v16 = LastError | (FileId << 52);
    v17 = 0x2D2E00000000LL;
    return v17 | v16;
  }
  v18 = WaitForSingleObject(*(HANDLE *)(a1 + 112), a2 != 0 ? -1 : 1000);
  if ( v18 == 258 )
  {
    std::string::string(
      v35,
      "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliveryP"
      "arameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::StopDelivery");
    v36 = 368;
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v31,
      L"While stopping client event delivery, a client event subscriber thread is still active and did not exit within the timeout",
      0x7Au);
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v33, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v35, 2, (int)&v33, (__int64)&v31);
    std::wstring::~wstring((char **)&v33);
    std::wstring::~wstring((char **)&v31);
    std::string::~string(v35);
  }
  else if ( v18 )
  {
    LastError = GetLastError();
    std::string::string(
      v35,
      "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliveryP"
      "arameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::StopDelivery");
    v36 = 375;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v20);
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v31,
      L"A Client event delivery thread did not exit when it was signalled to shut down, error = %1%",
      0x5Bu);
    v22 = AppV::Log::fmt(v21, v37, &v31);
    v23 = AppV::LogFormatter::operator%<unsigned long>(v22, (__int64)&LastError);
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v33, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v35, 1, (int)&v33, v23);
    std::wstring::~wstring((char **)&v33);
    v37[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v38);
    std::wstring::~wstring((char **)&v31);
    std::string::~string(v35);
    v24 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v24 )
      v25 = v24 + 1;
    else
      v25 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    v26 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25);
    v16 = LastError | (v26 << 52);
    v17 = 0x2F2E00000000LL;
    return v17 | v16;
  }
  v19 = *(void **)(a1 + 112);
  if ( v19 )
  {
    CloseHandle(v19);
    *(_QWORD *)(a1 + 112) = 0;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14004fc50  mov     [rsp-8+arg_8], rbx
0x14004fc55  mov     [rsp-8+arg_10], rsi
0x14004fc5a  push    rbp
0x14004fc5b  push    rdi
0x14004fc5c  push    r14
0x14004fc5e  lea     rbp, [rsp-47h]
0x14004fc63  sub     rsp, 0E0h
0x14004fc6a  mov     rax, cs:__security_cookie
0x14004fc71  xor     rax, rsp
0x14004fc74  mov     [rbp+57h+var_18], rax
0x14004fc78  mov     r14b, dl
0x14004fc7b  mov     rdi, rcx
0x14004fc7e  cmp     qword ptr [rcx+70h], 0
0x14004fc83  jnz     short loc_14004FCCD
0x14004fc85  mov     edx, 5Ch ; '\'; Ch
0x14004fc8a  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004fc91  call    cs:__imp_strrchr
0x14004fc97  test    rax, rax
0x14004fc9a  jz      short loc_14004FCA1
0x14004fc9c  inc     rax
0x14004fc9f  jmp     short loc_14004FCA8
0x14004fca1  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004fca8  mov     rdx, rax; char *
0x14004fcab  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004fcb2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004fcb7  shl     rax, 34h
0x14004fcbb  mov     rcx, 2B0E00000202h
0x14004fcc5  or      rax, rcx
0x14004fcc8  jmp     loc_14004FF40
0x14004fccd  mov     rbx, [rcx+30h]
0x14004fcd1  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004fcd8  mov     [rbp+57h+var_C8], rax
0x14004fcdc  mov     [rbp+57h+var_B8], rbx
0x14004fce0  mov     rcx, rbx; lpCriticalSection
0x14004fce3  call    cs:__imp_EnterCriticalSection
0x14004fce9  inc     dword ptr [rbx+28h]
0x14004fcec  cmp     dword ptr [rbx+28h], 1
0x14004fcf0  jnz     short loc_14004FCFB
0x14004fcf2  call    cs:__imp_GetCurrentThreadId
0x14004fcf8  mov     [rbx+2Ch], eax
0x14004fcfb  mov     rcx, [rdi+40h]
0x14004fcff  mov     rcx, [rcx]; hEvent
0x14004fd02  call    cs:__imp_ResetEvent
0x14004fd08  mov     rcx, [rdi+50h]
0x14004fd0c  call    ?_Tidy@?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Tidy(void)
0x14004fd11  sub     dword ptr [rbx+28h], 1
0x14004fd15  jnz     short loc_14004FD1E
0x14004fd17  mov     dword ptr [rbx+2Ch], 0
0x14004fd1e  mov     rcx, rbx; lpCriticalSection
0x14004fd21  call    cs:__imp_LeaveCriticalSection
0x14004fd27  mov     [rbp+57h+var_C0], 0
0x14004fd2b  mov     rcx, [rdi+60h]
0x14004fd2f  mov     rcx, [rcx]; hEvent
0x14004fd32  call    cs:__imp_SetEvent
0x14004fd38  cmp     eax, 1
0x14004fd3b  jz      loc_14004FE62
0x14004fd41  call    cs:__imp_GetLastError
0x14004fd47  mov     [rbp+57h+var_D0], eax
0x14004fd4a  lea     rdx, aAppvClientHost_25; "AppV::Client::Host::SubscriberImpl<stru"...
0x14004fd51  lea     rcx, [rbp+57h+var_70]
0x14004fd55  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004fd5a  mov     [rbp+57h+var_50], 168h
0x14004fd61  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004fd66  xorps   xmm0, xmm0
0x14004fd69  movups  [rbp+57h+var_90], xmm0
0x14004fd6d  xorps   xmm1, xmm1
0x14004fd70  movdqu  [rbp+57h+var_80], xmm1
0x14004fd75  mov     r8d, 53h ; 'S'
0x14004fd7b  lea     rdx, aFailedToSignal_0; "Failed to signal the shutdown event for"...
0x14004fd82  lea     rcx, [rbp+57h+var_90]
0x14004fd86  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004fd8b  nop
0x14004fd8c  lea     r8, [rbp+57h+var_90]
0x14004fd90  lea     rdx, [rbp+57h+var_48]
0x14004fd94  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004fd99  nop
0x14004fd9a  lea     rdx, [rbp+57h+var_D0]
0x14004fd9e  mov     rcx, rax
0x14004fda1  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004fda6  mov     rbx, rax
0x14004fda9  xorps   xmm0, xmm0
0x14004fdac  movups  [rbp+57h+var_B0], xmm0
0x14004fdb0  xorps   xmm1, xmm1
0x14004fdb3  movdqu  [rbp+57h+var_A0], xmm1
0x14004fdb8  mov     r8d, 6
0x14004fdbe  lea     rdx, aClient; "Client"
0x14004fdc5  lea     rcx, [rbp+57h+var_B0]
0x14004fdc9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004fdce  nop
0x14004fdcf  mov     r9, rbx
0x14004fdd2  lea     r8, [rbp+57h+var_B0]
0x14004fdd6  mov     edx, 1
0x14004fddb  lea     rcx, [rbp+57h+var_70]
0x14004fddf  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004fde4  nop
0x14004fde5  lea     rcx, [rbp+57h+var_B0]
0x14004fde9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004fdee  nop
0x14004fdef  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004fdf6  mov     [rbp+57h+var_48], rax
0x14004fdfa  lea     rcx, [rbp+57h+var_38]
0x14004fdfe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004fe03  nop
0x14004fe04  lea     rcx, [rbp+57h+var_90]
0x14004fe08  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004fe0d  nop
0x14004fe0e  lea     rcx, [rbp+57h+var_70]
0x14004fe12  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004fe17  mov     edx, 5Ch ; '\'; Ch
0x14004fe1c  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004fe23  call    cs:__imp_strrchr
0x14004fe29  test    rax, rax
0x14004fe2c  jz      short loc_14004FE33
0x14004fe2e  inc     rax
0x14004fe31  jmp     short loc_14004FE3A
0x14004fe33  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004fe3a  mov     rdx, rax; char *
0x14004fe3d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004fe44  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004fe49  shl     rax, 34h
0x14004fe4d  mov     ecx, [rbp+57h+var_D0]
0x14004fe50  or      rax, rcx
0x14004fe53  mov     rcx, 2D2E00000000h
0x14004fe5d  jmp     loc_140050084
0x14004fe62  neg     r14b
0x14004fe65  sbb     edx, edx
0x14004fe67  and     edx, 0FFFFFC17h
0x14004fe6d  add     edx, 3E8h; dwMilliseconds
0x14004fe73  mov     rcx, [rdi+70h]; hHandle
0x14004fe77  call    cs:__imp_WaitForSingleObject
0x14004fe7d  cmp     eax, 102h
0x14004fe82  jnz     loc_14004FF64
0x14004fe88  lea     rdx, aAppvClientHost_25; "AppV::Client::Host::SubscriberImpl<stru"...
0x14004fe8f  lea     rcx, [rbp+57h+var_70]
0x14004fe93  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004fe98  mov     [rbp+57h+var_50], 170h
0x14004fe9f  xorps   xmm0, xmm0
0x14004fea2  movups  [rbp+57h+var_B0], xmm0
0x14004fea6  xorps   xmm1, xmm1
0x14004fea9  movdqu  [rbp+57h+var_A0], xmm1
0x14004feae  mov     r8d, 7Ah ; 'z'
0x14004feb4  lea     rdx, aWhileStoppingC; "While stopping client event delivery, a"...
0x14004febb  lea     rcx, [rbp+57h+var_B0]
0x14004febf  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004fec4  nop
0x14004fec5  xorps   xmm0, xmm0
0x14004fec8  movups  [rbp+57h+var_90], xmm0
0x14004fecc  xorps   xmm1, xmm1
0x14004fecf  movdqu  [rbp+57h+var_80], xmm1
0x14004fed4  mov     r8d, 6
0x14004feda  lea     rdx, aClient; "Client"
0x14004fee1  lea     rcx, [rbp+57h+var_90]
0x14004fee5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004feea  nop
0x14004feeb  lea     r9, [rbp+57h+var_B0]
0x14004feef  lea     r8, [rbp+57h+var_90]
0x14004fef3  mov     edx, 2
0x14004fef8  lea     rcx, [rbp+57h+var_70]
0x14004fefc  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004ff01  nop
0x14004ff02  lea     rcx, [rbp+57h+var_90]
0x14004ff06  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ff0b  nop
0x14004ff0c  lea     rcx, [rbp+57h+var_B0]
0x14004ff10  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ff15  nop
0x14004ff16  lea     rcx, [rbp+57h+var_70]
0x14004ff1a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ff1f  mov     rcx, [rdi+70h]; hObject
0x14004ff23  test    rcx, rcx
0x14004ff26  jz      short loc_14004FF36
0x14004ff28  call    cs:__imp_CloseHandle
0x14004ff2e  mov     qword ptr [rdi+70h], 0
0x14004ff36  mov     rax, 8000000000h
0x14004ff40  mov     rcx, [rbp+57h+var_18]
0x14004ff44  xor     rcx, rsp; StackCookie
0x14004ff47  call    __security_check_cookie
0x14004ff4c  lea     r11, [rsp+0F0h+var_10]
0x14004ff54  mov     rbx, [r11+28h]
0x14004ff58  mov     rsi, [r11+30h]
0x14004ff5c  mov     rsp, r11
0x14004ff5f  pop     r14
0x14004ff61  pop     rdi
0x14004ff62  pop     rbp
0x14004ff63  retn
0x14004ff64  test    eax, eax
0x14004ff66  jz      short loc_14004FF1F
0x14004ff68  call    cs:__imp_GetLastError
0x14004ff6e  mov     [rbp+57h+var_D0], eax
0x14004ff71  lea     rdx, aAppvClientHost_25; "AppV::Client::Host::SubscriberImpl<stru"...
0x14004ff78  lea     rcx, [rbp+57h+var_70]
0x14004ff7c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004ff81  mov     [rbp+57h+var_50], 177h
0x14004ff88  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004ff8d  xorps   xmm0, xmm0
0x14004ff90  movups  [rbp+57h+var_B0], xmm0
0x14004ff94  xorps   xmm1, xmm1
0x14004ff97  movdqu  [rbp+57h+var_A0], xmm1
0x14004ff9c  mov     r8d, 5Bh ; '['
0x14004ffa2  lea     rdx, aAClientEventDe; "A Client event delivery thread did not "...
0x14004ffa9  lea     rcx, [rbp+57h+var_B0]
0x14004ffad  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ffb2  nop
0x14004ffb3  lea     r8, [rbp+57h+var_B0]
0x14004ffb7  lea     rdx, [rbp+57h+var_48]
0x14004ffbb  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004ffc0  nop
0x14004ffc1  lea     rdx, [rbp+57h+var_D0]
0x14004ffc5  mov     rcx, rax
0x14004ffc8  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004ffcd  mov     rbx, rax
0x14004ffd0  xorps   xmm0, xmm0
0x14004ffd3  movups  [rbp+57h+var_90], xmm0
0x14004ffd7  xorps   xmm1, xmm1
0x14004ffda  movdqu  [rbp+57h+var_80], xmm1
0x14004ffdf  mov     r8d, 6
0x14004ffe5  lea     rdx, aClient; "Client"
0x14004ffec  lea     rcx, [rbp+57h+var_90]
0x14004fff0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004fff5  nop
0x14004fff6  mov     r9, rbx
0x14004fff9  lea     r8, [rbp+57h+var_90]
0x14004fffd  mov     edx, 1
0x140050002  lea     rcx, [rbp+57h+var_70]
0x140050006  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005000b  nop
0x14005000c  lea     rcx, [rbp+57h+var_90]
0x140050010  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050015  nop
0x140050016  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005001d  mov     [rbp+57h+var_48], rax
0x140050021  lea     rcx, [rbp+57h+var_38]
0x140050025  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005002a  nop
0x14005002b  lea     rcx, [rbp+57h+var_B0]
0x14005002f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050034  nop
0x140050035  lea     rcx, [rbp+57h+var_70]
0x140050039  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005003e  mov     edx, 5Ch ; '\'; Ch
0x140050043  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14005004a  call    cs:__imp_strrchr
0x140050050  test    rax, rax
0x140050053  jz      short loc_14005005A
0x140050055  inc     rax
0x140050058  jmp     short loc_140050061
0x14005005a  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x140050061  mov     rdx, rax; char *
0x140050064  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005006b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140050070  shl     rax, 34h
0x140050074  mov     ecx, [rbp+57h+var_D0]
0x140050077  or      rax, rcx
0x14005007a  mov     rcx, 2F2E00000000h
0x140050084  or      rax, rcx
0x140050087  jmp     loc_14004FF40
```
