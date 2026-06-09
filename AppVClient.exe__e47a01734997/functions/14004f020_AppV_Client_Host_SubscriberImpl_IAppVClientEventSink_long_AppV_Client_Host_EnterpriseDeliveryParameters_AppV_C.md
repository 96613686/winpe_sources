# AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::QueueEvent(std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &)

- ea: `0x14004f020`
- end: `0x14004f4f0`
- name: `?QueueEvent@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@Host@Client@AppV@@UEAA_KAEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@Z`
- size: `1232`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

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
- `0x14004dc8c`
- `0x14004f020`
- `0x14006a010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14004f32e`
- `KERNEL32!SetEvent` at `0x14004f32e`
- `KERNEL32!GetLastError` at `0x14004f33d`
- `KERNEL32!GetLastError` at `0x14004f33d`
- `KERNEL32!GetCurrentThreadId` at `0x14004f11d`
- `KERNEL32!GetCurrentThreadId` at `0x14004f11d`
- `KERNEL32!WaitForSingleObject` at `0x14004f135`
- `KERNEL32!WaitForSingleObject` at `0x14004f135`
- `KERNEL32!LeaveCriticalSection` at `0x14004f49b`
- `KERNEL32!LeaveCriticalSection` at `0x14004f4bc`
- `KERNEL32!LeaveCriticalSection` at `0x14004f49b`
- `KERNEL32!LeaveCriticalSection` at `0x14004f4bc`
- `KERNEL32!EnterCriticalSection` at `0x14004f107`
- `KERNEL32!EnterCriticalSection` at `0x14004f107`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f060`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f0ae`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f149`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f2e2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f44a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f060`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f0ae`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f149`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f2e2`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004f44a`

## string_xrefs

- `0x14004f059`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f070`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f0a7`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f0be`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f142`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f159`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f2db`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f2f2`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f443`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f45a`: `admin\appman\appv\client\host\common\Subscriber.h`
- `0x14004f382`: `Failed to signal the availability of a new queued event for a Client event delivery thread, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
unsigned __int64 __fastcall AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::QueueEvent(
        __int64 a1,
        _QWORD *a2)
{
  char *v4; // rax
  const char *v5; // rax
  unsigned __int64 FileId; // rax
  __int64 v7; // rcx
  char *v9; // rax
  const char *v10; // rax
  unsigned __int64 v11; // rbx
  __int64 v12; // r14
  _DWORD *v13; // rsi
  char *v14; // rax
  const char *v15; // rax
  bool v16; // zf
  __int64 v17; // rcx
  _QWORD *v18; // rbx
  volatile signed __int32 *v19; // r15
  char *v20; // rax
  const char *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  char *v26; // rax
  const char *v27; // rax
  unsigned __int64 v28; // rax
  __int64 v29; // rax
  struct _RTL_CRITICAL_SECTION *v30; // rcx
  char *v31; // rax
  const char *v32; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-F8h] BYREF
  _DWORD *v34; // [rsp+28h] [rbp-F0h]
  unsigned __int64 v35; // [rsp+30h] [rbp-E8h]
  void **v36; // [rsp+38h] [rbp-E0h]
  char v37; // [rsp+40h] [rbp-D8h]
  __int64 v38; // [rsp+48h] [rbp-D0h]
  __int128 v39; // [rsp+50h] [rbp-C8h] BYREF
  __int128 v40; // [rsp+60h] [rbp-B8h]
  __int128 v41; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v42; // [rsp+80h] [rbp-98h]
  char *v43[4]; // [rsp+90h] [rbp-88h] BYREF
  int v44; // [rsp+B0h] [rbp-68h]
  void **v45; // [rsp+B8h] [rbp-60h] BYREF
  char *v46; // [rsp+C8h] [rbp-50h] BYREF

  if ( !*(_QWORD *)(a1 + 112) )
  {
    v4 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5);
    v7 = 0x300E00000202LL;
    return v7 | (FileId << 52);
  }
  if ( !*a2 )
  {
    v9 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10);
    v7 = 0x302E00000057LL;
    return v7 | (FileId << 52);
  }
  v11 = 0x8000000000LL;
  v12 = *(_QWORD *)(a1 + 48);
  lpCriticalSection = (LPCRITICAL_SECTION)v12;
  v36 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v38 = v12;
  EnterCriticalSection((LPCRITICAL_SECTION)v12);
  v13 = (_DWORD *)(v12 + 40);
  v34 = (_DWORD *)(v12 + 40);
  if ( ++*(_DWORD *)(v12 + 40) == 1 )
    *(_DWORD *)(v12 + 44) = GetCurrentThreadId();
  v37 = 1;
  if ( WaitForSingleObject(**(HANDLE **)(a1 + 96), 0) )
  {
    try
    {
      v17 = *(_QWORD *)(a1 + 80);
      if ( *(_QWORD *)(v17 + 32) < 0x64u )
      {
        std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(
          v17,
          a2);
      }
      else
      {
        std::string::string(
          v43,
          "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliv"
          "eryParameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::QueueEvent");
        v44 = 404;
        v41 = 0;
        v42 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v41,
          L"Subscriber event queue full. An event was lost.",
          0x2Fu);
        v39 = 0;
        v40 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v39, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v43, 2, (int)&v39, (__int64)&v41);
        std::wstring::~wstring((char **)&v39);
        std::wstring::~wstring((char **)&v41);
        std::string::~string(v43);
        v18 = *(_QWORD **)(a1 + 80);
        v19 = *(volatile signed __int32 **)(*(_QWORD *)(v18[1] + 8 * (v18[3] & (v18[2] - 1LL))) + 8LL);
        if ( v19 )
        {
          if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        v16 = v18[4]-- == 1;
        if ( v16 )
          v18[3] = 0;
        else
          ++v18[3];
        std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(
          *(_QWORD *)(a1 + 80),
          a2);
        v20 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
        if ( v20 )
          v21 = v20 + 1;
        else
          v21 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
        v11 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v21) << 52)
            | 0x332E00000054LL;
      }
    }
    catch ( std::bad_alloc )
    {
      v31 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
      if ( v31 )
        v32 = v31 + 1;
      else
        v32 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
      v35 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v32) << 52)
          | 0x342E0000000ELL;
      v16 = (*v34)-- == 1;
      v30 = lpCriticalSection;
      if ( v16 )
        HIDWORD(lpCriticalSection[1].DebugInfo) = 0;
      LeaveCriticalSection(v30);
      return v35;
    }
    if ( !SetEvent(**(HANDLE **)(a1 + 64)) )
    {
      LODWORD(lpCriticalSection) = GetLastError();
      std::string::string(
        v43,
        "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliver"
        "yParameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::QueueEvent");
      v44 = 424;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v22);
      v39 = 0;
      v40 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v39,
        L"Failed to signal the availability of a new queued event for a Client event delivery thread, error = %1%",
        0x67u);
      v24 = AppV::Log::fmt(v23, &v45, &v39);
      v25 = AppV::LogFormatter::operator%<unsigned long>(v24, (__int64)&lpCriticalSection);
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v41, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v43, 2, (int)&v41, v25);
      std::wstring::~wstring((char **)&v41);
      v45 = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(&v46);
      std::wstring::~wstring((char **)&v39);
      std::string::~string(v43);
      v26 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
      if ( v26 )
        v27 = v26 + 1;
      else
        v27 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
      v28 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v27);
      v29 = (unsigned int)lpCriticalSection | (v28 << 52) | 0x352E00000000LL;
      v16 = (*v13)-- == 1;
      if ( v16 )
        *(_DWORD *)(v12 + 44) = 0;
      v11 = v29;
      goto LABEL_41;
    }
  }
  else
  {
    v14 = strrchr("admin\\appman\\appv\\client\\host\\common\\Subscriber.h", 92);
    if ( v14 )
      v15 = v14 + 1;
    else
      v15 = "admin\\appman\\appv\\client\\host\\common\\Subscriber.h";
    v11 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v15) << 52)
        | 0x310E00000202LL;
  }
  v16 = (*v13)-- == 1;
  if ( v16 )
    *(_DWORD *)(v12 + 44) = 0;
LABEL_41:
  LeaveCriticalSection((LPCRITICAL_SECTION)v12);
  return v11;
}

```

## disassembly

```asm
0x14004f020  mov     [rsp+arg_10], rbx
0x14004f025  push    rsi
0x14004f026  push    r12
0x14004f028  push    r13
0x14004f02a  push    r14
0x14004f02c  push    r15
0x14004f02e  sub     rsp, 0F0h
0x14004f035  mov     rax, cs:__security_cookie
0x14004f03c  xor     rax, rsp
0x14004f03f  mov     [rsp+118h+var_30], rax
0x14004f047  mov     r12, rdx
0x14004f04a  mov     r13, rcx
0x14004f04d  cmp     qword ptr [rcx+70h], 0
0x14004f052  jnz     short loc_14004F09C
0x14004f054  mov     edx, 5Ch ; '\'; Ch
0x14004f059  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f060  call    cs:__imp_strrchr
0x14004f066  test    rax, rax
0x14004f069  jz      short loc_14004F070
0x14004f06b  inc     rax
0x14004f06e  jmp     short loc_14004F077
0x14004f070  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f077  mov     rdx, rax; char *
0x14004f07a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004f081  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004f086  mov     rcx, 300E00000202h
0x14004f090  shl     rax, 34h
0x14004f094  or      rax, rcx
0x14004f097  jmp     loc_14004F4C7
0x14004f09c  cmp     qword ptr [rdx], 0
0x14004f0a0  jnz     short loc_14004F0E0
0x14004f0a2  mov     edx, 5Ch ; '\'; Ch
0x14004f0a7  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f0ae  call    cs:__imp_strrchr
0x14004f0b4  test    rax, rax
0x14004f0b7  jz      short loc_14004F0BE
0x14004f0b9  inc     rax
0x14004f0bc  jmp     short loc_14004F0C5
0x14004f0be  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f0c5  mov     rdx, rax; char *
0x14004f0c8  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004f0cf  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004f0d4  mov     rcx, 302E00000057h
0x14004f0de  jmp     short loc_14004F090
0x14004f0e0  mov     rbx, 8000000000h
0x14004f0ea  mov     r14, [rcx+30h]
0x14004f0ee  mov     [rsp+118h+lpCriticalSection], r14
0x14004f0f3  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004f0fa  mov     [rsp+118h+var_E0], rax
0x14004f0ff  mov     [rsp+118h+var_D0], r14
0x14004f104  mov     rcx, r14; lpCriticalSection
0x14004f107  call    cs:__imp_EnterCriticalSection
0x14004f10d  lea     rsi, [r14+28h]
0x14004f111  mov     [rsp+118h+var_F0], rsi
0x14004f116  inc     dword ptr [rsi]
0x14004f118  cmp     dword ptr [rsi], 1
0x14004f11b  jnz     short loc_14004F127
0x14004f11d  call    cs:__imp_GetCurrentThreadId
0x14004f123  mov     [r14+2Ch], eax
0x14004f127  mov     [rsp+118h+var_D8], 1
0x14004f12c  mov     rcx, [r13+60h]
0x14004f130  xor     edx, edx; dwMilliseconds
0x14004f132  mov     rcx, [rcx]; hHandle
0x14004f135  call    cs:__imp_WaitForSingleObject
0x14004f13b  test    eax, eax
0x14004f13d  jnz     short loc_14004F199
0x14004f13f  lea     edx, [rax+5Ch]; Ch
0x14004f142  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f149  call    cs:__imp_strrchr
0x14004f14f  test    rax, rax
0x14004f152  jz      short loc_14004F159
0x14004f154  inc     rax
0x14004f157  jmp     short loc_14004F160
0x14004f159  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f160  mov     rdx, rax; char *
0x14004f163  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004f16a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004f16f  mov     rbx, rax
0x14004f172  shl     rbx, 34h
0x14004f176  mov     rax, 310E00000202h
0x14004f180  or      rbx, rax
0x14004f183  sub     dword ptr [rsi], 1
0x14004f186  jnz     loc_14004F498
0x14004f18c  mov     dword ptr [r14+2Ch], 0
0x14004f194  jmp     loc_14004F498
0x14004f199  mov     rcx, [r13+50h]
0x14004f19d  cmp     qword ptr [rcx+20h], 64h ; 'd'
0x14004f1a2  jb      loc_14004F31E
0x14004f1a8  lea     rdx, aAppvClientHost_20; "AppV::Client::Host::SubscriberImpl<stru"...
0x14004f1af  lea     rcx, [rsp+118h+var_88]
0x14004f1b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004f1bc  mov     [rsp+118h+var_68], 194h
0x14004f1c7  xorps   xmm0, xmm0
0x14004f1ca  movups  [rsp+118h+var_A8], xmm0
0x14004f1cf  xorps   xmm1, xmm1
0x14004f1d2  movdqu  [rsp+118h+var_98], xmm1
0x14004f1db  mov     r8d, 2Fh ; '/'
0x14004f1e1  lea     rdx, aSubscriberEven; "Subscriber event queue full. An event w"...
0x14004f1e8  lea     rcx, [rsp+118h+var_A8]
0x14004f1ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004f1f2  nop
0x14004f1f3  xorps   xmm0, xmm0
0x14004f1f6  movups  [rsp+118h+var_C8], xmm0
0x14004f1fb  xorps   xmm1, xmm1
0x14004f1fe  movdqu  [rsp+118h+var_B8], xmm1
0x14004f204  mov     r8d, 6
0x14004f20a  lea     rdx, aClient; "Client"
0x14004f211  lea     rcx, [rsp+118h+var_C8]
0x14004f216  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004f21b  nop
0x14004f21c  lea     r9, [rsp+118h+var_A8]
0x14004f221  lea     r8, [rsp+118h+var_C8]
0x14004f226  mov     edx, 2
0x14004f22b  lea     rcx, [rsp+118h+var_88]
0x14004f233  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004f238  nop
0x14004f239  lea     rcx, [rsp+118h+var_C8]
0x14004f23e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f243  nop
0x14004f244  lea     rcx, [rsp+118h+var_A8]
0x14004f249  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f24e  nop
0x14004f24f  lea     rcx, [rsp+118h+var_88]
0x14004f257  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004f25c  mov     rbx, [r13+50h]
0x14004f260  mov     rcx, [rbx+10h]
0x14004f264  dec     rcx
0x14004f267  and     rcx, [rbx+18h]
0x14004f26b  mov     rax, [rbx+8]
0x14004f26f  mov     rcx, [rax+rcx*8]
0x14004f273  mov     r15, [rcx+8]
0x14004f277  test    r15, r15
0x14004f27a  jz      short loc_14004F2B5
0x14004f27c  or      eax, 0FFFFFFFFh
0x14004f27f  lock xadd [r15+8], eax
0x14004f285  cmp     eax, 1
0x14004f288  jnz     short loc_14004F2B5
0x14004f28a  mov     rax, [r15]
0x14004f28d  mov     rcx, r15
0x14004f290  mov     rax, [rax]
0x14004f293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f298  or      eax, 0FFFFFFFFh
0x14004f29b  lock xadd [r15+0Ch], eax
0x14004f2a1  cmp     eax, 1
0x14004f2a4  jnz     short loc_14004F2B5
0x14004f2a6  mov     rax, [r15]
0x14004f2a9  mov     rcx, r15
0x14004f2ac  mov     rax, [rax+8]
0x14004f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f2b5  sub     qword ptr [rbx+20h], 1
0x14004f2ba  jnz     short loc_14004F2C6
0x14004f2bc  mov     qword ptr [rbx+18h], 0
0x14004f2c4  jmp     short loc_14004F2CA
0x14004f2c6  inc     qword ptr [rbx+18h]
0x14004f2ca  mov     rdx, r12
0x14004f2cd  mov     rcx, [r13+50h]
0x14004f2d1  call    ??$_Emplace_back_internal@AEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@AEAAXAEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@1@@Z; std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &)
0x14004f2d6  mov     edx, 5Ch ; '\'; Ch
0x14004f2db  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f2e2  call    cs:__imp_strrchr
0x14004f2e8  test    rax, rax
0x14004f2eb  jz      short loc_14004F2F2
0x14004f2ed  inc     rax
0x14004f2f0  jmp     short loc_14004F2F9
0x14004f2f2  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f2f9  mov     rdx, rax; char *
0x14004f2fc  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004f303  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004f308  mov     rbx, rax
0x14004f30b  shl     rbx, 34h
0x14004f30f  mov     rax, 332E00000054h
0x14004f319  or      rbx, rax
0x14004f31c  jmp     short loc_14004F327
0x14004f31e  mov     rdx, r12
0x14004f321  call    ??$_Emplace_back_internal@AEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@AEAAXAEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@1@@Z; std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &)
0x14004f326  nop
0x14004f327  mov     rcx, [r13+40h]
0x14004f32b  mov     rcx, [rcx]; hEvent
0x14004f32e  call    cs:__imp_SetEvent
0x14004f334  cmp     eax, 1
0x14004f337  jz      loc_14004F183
0x14004f33d  call    cs:__imp_GetLastError
0x14004f343  mov     dword ptr [rsp+118h+lpCriticalSection], eax
0x14004f347  lea     rdx, aAppvClientHost_20; "AppV::Client::Host::SubscriberImpl<stru"...
0x14004f34e  lea     rcx, [rsp+118h+var_88]
0x14004f356  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004f35b  mov     [rsp+118h+var_68], 1A8h
0x14004f366  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004f36b  xorps   xmm0, xmm0
0x14004f36e  movups  [rsp+118h+var_C8], xmm0
0x14004f373  xorps   xmm1, xmm1
0x14004f376  movdqu  [rsp+118h+var_B8], xmm1
0x14004f37c  mov     r8d, 67h ; 'g'
0x14004f382  lea     rdx, aFailedToSignal; "Failed to signal the availability of a "...
0x14004f389  lea     rcx, [rsp+118h+var_C8]
0x14004f38e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004f393  nop
0x14004f394  lea     r8, [rsp+118h+var_C8]
0x14004f399  lea     rdx, [rsp+118h+var_60]
0x14004f3a1  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004f3a6  nop
0x14004f3a7  lea     rdx, [rsp+118h+lpCriticalSection]
0x14004f3ac  mov     rcx, rax
0x14004f3af  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004f3b4  mov     rbx, rax
0x14004f3b7  xorps   xmm0, xmm0
0x14004f3ba  movups  [rsp+118h+var_A8], xmm0
0x14004f3bf  xorps   xmm1, xmm1
0x14004f3c2  movdqu  [rsp+118h+var_98], xmm1
0x14004f3cb  mov     r8d, 6
0x14004f3d1  lea     rdx, aClient; "Client"
0x14004f3d8  lea     rcx, [rsp+118h+var_A8]
0x14004f3dd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004f3e2  nop
0x14004f3e3  mov     r9, rbx
0x14004f3e6  lea     r8, [rsp+118h+var_A8]
0x14004f3eb  mov     edx, 2
0x14004f3f0  lea     rcx, [rsp+118h+var_88]
0x14004f3f8  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004f3fd  nop
0x14004f3fe  lea     rcx, [rsp+118h+var_A8]
0x14004f403  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f408  nop
0x14004f409  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004f410  mov     [rsp+118h+var_60], rax
0x14004f418  lea     rcx, [rsp+118h+var_50]
0x14004f420  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f425  nop
0x14004f426  lea     rcx, [rsp+118h+var_C8]
0x14004f42b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f430  nop
0x14004f431  lea     rcx, [rsp+118h+var_88]
0x14004f439  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004f43e  mov     edx, 5Ch ; '\'; Ch
0x14004f443  lea     rcx, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f44a  call    cs:__imp_strrchr
0x14004f450  test    rax, rax
0x14004f453  jz      short loc_14004F45A
0x14004f455  inc     rax
0x14004f458  jmp     short loc_14004F461
0x14004f45a  lea     rax, aAdminAppmanApp_10; "admin\\appman\\appv\\client\\host\\comm"...
0x14004f461  mov     rdx, rax; char *
0x14004f464  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004f46b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004f470  shl     rax, 34h
0x14004f474  mov     ecx, dword ptr [rsp+118h+lpCriticalSection]
0x14004f478  or      rax, rcx
0x14004f47b  mov     rcx, 352E00000000h
0x14004f485  or      rax, rcx
0x14004f488  sub     dword ptr [rsi], 1
0x14004f48b  jnz     short loc_14004F495
0x14004f48d  mov     dword ptr [r14+2Ch], 0
0x14004f495  mov     rbx, rax
0x14004f498  mov     rcx, r14; lpCriticalSection
0x14004f49b  call    cs:__imp_LeaveCriticalSection
0x14004f4a1  mov     rax, rbx
0x14004f4a4  jmp     short loc_14004F4C7
0x14004f4a6  mov     rax, [rsp+118h+var_F0]
0x14004f4ab  sub     dword ptr [rax], 1
0x14004f4ae  mov     rcx, [rsp+118h+lpCriticalSection]; lpCriticalSection
0x14004f4b3  jnz     short loc_14004F4BC
0x14004f4b5  mov     dword ptr [rcx+2Ch], 0
0x14004f4bc  call    cs:__imp_LeaveCriticalSection
0x14004f4c2  mov     rax, [rsp+118h+var_E8]
0x14004f4c7  mov     rcx, [rsp+118h+var_30]
0x14004f4cf  xor     rcx, rsp; StackCookie
0x14004f4d2  call    __security_check_cookie
0x14004f4d7  mov     rbx, [rsp+118h+arg_10]
0x14004f4df  add     rsp, 0F0h
0x14004f4e6  pop     r15
0x14004f4e8  pop     r14
0x14004f4ea  pop     r13
0x14004f4ec  pop     r12
0x14004f4ee  pop     rsi
0x14004f4ef  retn
```
