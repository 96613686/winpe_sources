# AppV::Client::Host::UserManagerImpl::Initialize(AppV::Client::ClientComponent *)

- ea: `0x140049630`
- end: `0x140049bc6`
- name: `?Initialize@UserManagerImpl@Host@Client@AppV@@UEAA_KPEAVClientComponent@34@@Z`
- size: `1430`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this, struct AppV::Client::ClientComponent *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
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
- `0x140049630`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140049a2b`
- `KERNEL32!GetLastError` at `0x140049a2b`
- `KERNEL32!GetCurrentThreadId` at `0x1400496da`
- `KERNEL32!GetCurrentThreadId` at `0x1400496da`
- `KERNEL32!LeaveCriticalSection` at `0x1400497e5`
- `KERNEL32!LeaveCriticalSection` at `0x140049a16`
- `KERNEL32!LeaveCriticalSection` at `0x140049b9d`
- `KERNEL32!LeaveCriticalSection` at `0x1400497e5`
- `KERNEL32!LeaveCriticalSection` at `0x140049a16`
- `KERNEL32!LeaveCriticalSection` at `0x140049b9d`
- `KERNEL32!EnterCriticalSection` at `0x1400496c4`
- `KERNEL32!EnterCriticalSection` at `0x1400496c4`
- `KERNEL32!CreateThreadpool` at `0x14004987d`
- `KERNEL32!CreateThreadpool` at `0x14004987d`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140049894`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140049894`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1400498aa`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1400498aa`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1400498c1`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1400498c1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140049670`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004979c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140049b19`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140049670`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004979c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140049b19`

## string_xrefs

- `0x140049669`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049680`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049795`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x1400497ac`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049b12`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049b29`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049a69`: `UserManager failed to create a thread pool for asynchronous session operations, error = %1%`
- `0x140049722`: `UserManager recevied an Initialize request when already initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AppV::Client::Host::UserManagerImpl::Initialize(
        struct _RTL_CRITICAL_SECTION *this,
        struct AppV::Client::ClientComponent *a2)
{
  char *v4; // rax
  const char *v5; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 v10; // rsi
  bool v11; // zf
  _DWORD *v12; // rbx
  void *v13; // rsi
  struct _TP_POOL *Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  volatile signed __int32 *SpinCount; // r15
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  char *v20; // rax
  const char *v21; // rax
  unsigned __int64 FileId; // rax
  __int64 v23; // r14
  DWORD LastError; // [rsp+20h] [rbp-E0h] BYREF
  void **v25; // [rsp+28h] [rbp-D8h]
  char v26; // [rsp+30h] [rbp-D0h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+38h] [rbp-C8h]
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  char *v38[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v39; // [rsp+C8h] [rbp-38h]
  void **v40; // [rsp+D0h] [rbp-30h] BYREF
  char *v41; // [rsp+E0h] [rbp-20h] BYREF

  if ( a2 )
  {
    v25 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    v7 = this + 1;
    v27 = this + 1;
    EnterCriticalSection(this + 1);
    if ( ++LODWORD(v7[1].DebugInfo) == 1 )
      HIDWORD(v7[1].DebugInfo) = GetCurrentThreadId();
    v26 = 1;
    if ( this[2].LockCount )
    {
      std::string::string(&v31, "AppV::Client::Host::UserManagerImpl::Initialize");
      v34 = 70;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v28,
        L"UserManager recevied an Initialize request when already initialized",
        0x43u);
      v35 = 0;
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v35, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)&v31, 1, (int)&v35, (__int64)&v28);
      std::wstring::~wstring((char **)&v35);
      std::wstring::~wstring((char **)&v28);
      std::string::~string((char **)&v31);
      v8 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
      if ( v8 )
        v9 = v8 + 1;
      else
        v9 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
      v10 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9) << 52)
          | 0x80E00000301LL;
      v11 = LODWORD(v7[1].DebugInfo)-- == 1;
      if ( v11 )
        HIDWORD(v7[1].DebugInfo) = 0;
      LeaveCriticalSection(v7);
      return v10;
    }
    else
    {
      v12 = operator new(0x58u);
      *(_QWORD *)v12 = 0;
      v12[2] = 3;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 5) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 7) = 0;
      v12[16] = 0;
      v12[17] = 1;
      v12[18] = 72;
      *((_QWORD *)v12 + 10) = 0;
      v13 = operator new(0x18u);
      *(_OWORD *)v13 = 0;
      *((_DWORD *)v13 + 2) = 1;
      *((_DWORD *)v13 + 3) = 1;
      *(_QWORD *)v13 = &std::_Ref_count<threading::pool>::`vftable';
      *((_QWORD *)v13 + 2) = v12;
      *(_QWORD *)&v35 = v12;
      *((_QWORD *)&v35 + 1) = v13;
      if ( !*(_QWORD *)v12
        && (Threadpool = CreateThreadpool(0), (*(_QWORD *)v12 = Threadpool) != 0)
        && SetThreadpoolThreadMinimum(Threadpool, 0)
        && (SetThreadpoolThreadMaximum(*(PTP_POOL *)v12, 0x64u),
            *((_QWORD *)v12 + 2) = *(_QWORD *)v12,
            !*((_QWORD *)v12 + 10))
        && (ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(),
            (*((_QWORD *)v12 + 10) = ThreadpoolCleanupGroup) != 0) )
      {
        *((_QWORD *)v12 + 3) = ThreadpoolCleanupGroup;
        *((_QWORD *)v12 + 4) = 0;
        this[2].OwningThread = a2;
        _InterlockedAdd((volatile signed __int32 *)v13 + 2, 1u);
        this[2].LockSemaphore = v12;
        SpinCount = (volatile signed __int32 *)this[2].SpinCount;
        this[2].SpinCount = (ULONG_PTR)v13;
        if ( SpinCount )
        {
          if ( _InterlockedExchangeAdd(SpinCount + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))SpinCount)(SpinCount);
            if ( _InterlockedExchangeAdd(SpinCount + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)SpinCount + 8LL))(SpinCount);
          }
        }
        this[2].LockCount = 1;
        std::string::string(v38, "AppV::Client::Host::UserManagerImpl::Initialize");
        v39 = 87;
        v31 = 0;
        v32 = 0;
        v33 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"UserManager initialized", 0x17u);
        v28 = 0;
        v29 = 0;
        v30 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v28, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v38, 4, (int)&v28, (__int64)&v31);
        std::wstring::~wstring((char **)&v28);
        std::wstring::~wstring((char **)&v31);
        std::string::~string(v38);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v13)(v13);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
        }
        v11 = LODWORD(v7[1].DebugInfo)-- == 1;
        if ( v11 )
          HIDWORD(v7[1].DebugInfo) = 0;
        LeaveCriticalSection(v7);
        return 0x8000000000LL;
      }
      else
      {
        LastError = GetLastError();
        std::string::string(v38, "AppV::Client::Host::UserManagerImpl::Initialize");
        v39 = 79;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
        v28 = 0;
        v29 = 0;
        v30 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v28,
          L"UserManager failed to create a thread pool for asynchronous session operations, error = %1%",
          0x5Bu);
        v18 = AppV::Log::fmt(v17, &v40, &v28);
        v19 = AppV::LogFormatter::operator%<unsigned long>(v18, (__int64)&LastError);
        v31 = 0;
        v32 = 0;
        v33 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v38, 1, (int)&v31, v19);
        std::wstring::~wstring((char **)&v31);
        v40 = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(&v41);
        std::wstring::~wstring((char **)&v28);
        std::string::~string(v38);
        v20 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
        if ( v20 )
          v21 = v20 + 1;
        else
          v21 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v21);
        v23 = LastError | (FileId << 52) | 0xA2E00000000LL;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v13)(v13);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
        }
        v11 = LODWORD(v7[1].DebugInfo)-- == 1;
        if ( v11 )
          HIDWORD(v7[1].DebugInfo) = 0;
        LeaveCriticalSection(v7);
        return v23;
      }
    }
  }
  else
  {
    v4 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v4 )
      v5 = v4 + 1;
    else
      v5 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5) << 52)
         | 0x82E00000057LL;
  }
}

```

## disassembly

```asm
0x140049630  push    rbp
0x140049632  push    rbx
0x140049633  push    rsi
0x140049634  push    rdi
0x140049635  push    r12
0x140049637  push    r13
0x140049639  push    r14
0x14004963b  push    r15
0x14004963d  lea     rbp, [rsp-18h]
0x140049642  sub     rsp, 118h
0x140049649  mov     rax, cs:__security_cookie
0x140049650  xor     rax, rsp
0x140049653  mov     [rbp+50h+var_50], rax
0x140049657  mov     r15, rdx
0x14004965a  mov     r13, rcx
0x14004965d  xor     r12d, r12d
0x140049660  test    rdx, rdx
0x140049663  jnz     short loc_1400496AC
0x140049665  lea     edx, [r15+5Ch]; Ch
0x140049669  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x140049670  call    cs:__imp_strrchr
0x140049676  test    rax, rax
0x140049679  jz      short loc_140049680
0x14004967b  inc     rax
0x14004967e  jmp     short loc_140049687
0x140049680  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x140049687  mov     rdx, rax; char *
0x14004968a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140049691  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140049696  shl     rax, 34h
0x14004969a  mov     rcx, 82E00000057h
0x1400496a4  or      rax, rcx
0x1400496a7  jmp     loc_140049BA6
0x1400496ac  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400496b3  mov     [rsp+150h+var_128], rax
0x1400496b8  lea     rdi, [rcx+28h]
0x1400496bc  mov     [rsp+150h+var_118], rdi
0x1400496c1  mov     rcx, rdi; lpCriticalSection
0x1400496c4  call    cs:__imp_EnterCriticalSection
0x1400496ca  mov     r14d, 1
0x1400496d0  add     [rdi+28h], r14d
0x1400496d4  cmp     [rdi+28h], r14d
0x1400496d8  jnz     short loc_1400496E3
0x1400496da  call    cs:__imp_GetCurrentThreadId
0x1400496e0  mov     [rdi+2Ch], eax
0x1400496e3  mov     [rsp+150h+var_120], r14b
0x1400496e8  cmp     [r13+58h], r12d
0x1400496ec  jz      loc_1400497F3
0x1400496f2  lea     rdx, aAppvClientHost_22; "AppV::Client::Host::UserManagerImpl::In"...
0x1400496f9  lea     rcx, [rsp+150h+var_F0]
0x1400496fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140049703  mov     [rbp+50h+var_D0], 46h ; 'F'
0x14004970a  xorps   xmm0, xmm0
0x14004970d  movups  [rsp+150h+var_110], xmm0
0x140049712  mov     [rsp+150h+var_100], r12
0x140049717  mov     [rsp+150h+var_F8], r12
0x14004971c  mov     r8d, 43h ; 'C'
0x140049722  lea     rdx, aUsermanagerRec_0; "UserManager recevied an Initialize requ"...
0x140049729  lea     rcx, [rsp+150h+var_110]
0x14004972e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049733  nop
0x140049734  xorps   xmm0, xmm0
0x140049737  movups  [rbp+50h+var_C8], xmm0
0x14004973b  mov     [rbp+50h+var_B8], r12
0x14004973f  mov     [rbp+50h+var_B0], r12
0x140049743  mov     r8d, 6
0x140049749  lea     rdx, aClient; "Client"
0x140049750  lea     rcx, [rbp+50h+var_C8]
0x140049754  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049759  nop
0x14004975a  lea     r9, [rsp+150h+var_110]
0x14004975f  lea     r8, [rbp+50h+var_C8]
0x140049763  mov     edx, r14d
0x140049766  lea     rcx, [rsp+150h+var_F0]
0x14004976b  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140049770  nop
0x140049771  lea     rcx, [rbp+50h+var_C8]
0x140049775  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004977a  nop
0x14004977b  lea     rcx, [rsp+150h+var_110]
0x140049780  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049785  nop
0x140049786  lea     rcx, [rsp+150h+var_F0]
0x14004978b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140049790  mov     edx, 5Ch ; '\'; Ch
0x140049795  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004979c  call    cs:__imp_strrchr
0x1400497a2  test    rax, rax
0x1400497a5  jz      short loc_1400497AC
0x1400497a7  add     rax, r14
0x1400497aa  jmp     short loc_1400497B3
0x1400497ac  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x1400497b3  mov     rdx, rax; char *
0x1400497b6  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400497bd  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400497c2  mov     rsi, rax
0x1400497c5  shl     rsi, 34h
0x1400497c9  mov     rax, 80E00000301h
0x1400497d3  or      rsi, rax
0x1400497d6  or      ebx, 0FFFFFFFFh
0x1400497d9  add     [rdi+28h], ebx
0x1400497dc  jnz     short loc_1400497E2
0x1400497de  mov     [rdi+2Ch], r12d
0x1400497e2  mov     rcx, rdi; lpCriticalSection
0x1400497e5  call    cs:__imp_LeaveCriticalSection
0x1400497eb  mov     rax, rsi
0x1400497ee  jmp     loc_140049BA6
0x1400497f3  mov     ecx, 58h ; 'X'; Size
0x1400497f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400497fd  mov     rbx, rax
0x140049800  mov     qword ptr [rbp+50h+var_C8], rax
0x140049804  mov     [rax], r12
0x140049807  mov     dword ptr [rax+8], 3
0x14004980e  mov     [rax+10h], r12
0x140049812  mov     [rax+18h], r12
0x140049816  mov     [rax+20h], r12
0x14004981a  mov     [rax+28h], r12
0x14004981e  mov     [rax+30h], r12
0x140049822  mov     [rax+38h], r12
0x140049826  mov     [rax+40h], r12d
0x14004982a  mov     [rax+44h], r14d
0x14004982e  mov     dword ptr [rax+48h], 48h ; 'H'
0x140049835  mov     [rax+50h], r12
0x140049839  mov     qword ptr [rbp+50h+var_C8], rax
0x14004983d  mov     ecx, 18h; Size
0x140049842  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049847  mov     rsi, rax
0x14004984a  mov     qword ptr [rbp+50h+var_C8], rax
0x14004984e  xorps   xmm0, xmm0
0x140049851  movups  xmmword ptr [rax], xmm0
0x140049854  mov     [rax+8], r14d
0x140049858  mov     [rax+0Ch], r14d
0x14004985c  lea     rax, ??_7?$_Ref_count@Upool@threading@@@std@@6B@; const std::_Ref_count<threading::pool>::`vftable'
0x140049863  mov     [rsi], rax
0x140049866  mov     [rsi+10h], rbx
0x14004986a  mov     qword ptr [rbp+50h+var_C8], rbx
0x14004986e  mov     qword ptr [rbp+50h+var_C8+8], rsi
0x140049872  cmp     [rbx], r12
0x140049875  jnz     loc_140049A2B
0x14004987b  xor     ecx, ecx; reserved
0x14004987d  call    cs:__imp_CreateThreadpool
0x140049883  mov     [rbx], rax
0x140049886  test    rax, rax
0x140049889  jz      loc_140049A2B
0x14004988f  xor     edx, edx; cthrdMic
0x140049891  mov     rcx, rax; ptpp
0x140049894  call    cs:__imp_SetThreadpoolThreadMinimum
0x14004989a  test    eax, eax
0x14004989c  jz      loc_140049A2B
0x1400498a2  mov     edx, 64h ; 'd'; cthrdMost
0x1400498a7  mov     rcx, [rbx]; ptpp
0x1400498aa  call    cs:__imp_SetThreadpoolThreadMaximum
0x1400498b0  mov     rax, [rbx]
0x1400498b3  mov     [rbx+10h], rax
0x1400498b7  cmp     [rbx+50h], r12
0x1400498bb  jnz     loc_140049A2B
0x1400498c1  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1400498c7  mov     [rbx+50h], rax
0x1400498cb  test    rax, rax
0x1400498ce  jz      loc_140049A2B
0x1400498d4  mov     [rbx+18h], rax
0x1400498d8  mov     [rbx+20h], r12
0x1400498dc  mov     [r13+60h], r15
0x1400498e0  lock add [rsi+8], r14d
0x1400498e5  mov     [r13+68h], rbx
0x1400498e9  mov     r15, [r13+70h]
0x1400498ed  mov     [r13+70h], rsi
0x1400498f1  or      ebx, 0FFFFFFFFh
0x1400498f4  test    r15, r15
0x1400498f7  jz      short loc_14004992E
0x1400498f9  mov     eax, ebx
0x1400498fb  lock xadd [r15+8], eax
0x140049901  add     eax, ebx
0x140049903  jnz     short loc_14004992E
0x140049905  mov     rax, [r15]
0x140049908  mov     rcx, r15
0x14004990b  mov     rax, [rax]
0x14004990e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049913  mov     eax, ebx
0x140049915  lock xadd [r15+0Ch], eax
0x14004991b  add     eax, ebx
0x14004991d  jnz     short loc_14004992E
0x14004991f  mov     rax, [r15]
0x140049922  mov     rcx, r15
0x140049925  mov     rax, [rax+8]
0x140049929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004992e  mov     [r13+58h], r14d
0x140049932  lea     rdx, aAppvClientHost_22; "AppV::Client::Host::UserManagerImpl::In"...
0x140049939  lea     rcx, [rbp+50h+var_A8]
0x14004993d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140049942  mov     [rbp+50h+var_88], 57h ; 'W'
0x140049949  xorps   xmm0, xmm0
0x14004994c  movups  [rsp+150h+var_F0], xmm0
0x140049951  mov     [rsp+150h+var_E0], r12
0x140049956  mov     [rsp+150h+var_D8], r12
0x14004995b  mov     r8d, 17h
0x140049961  lea     rdx, aUsermanagerIni; "UserManager initialized"
0x140049968  lea     rcx, [rsp+150h+var_F0]
0x14004996d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049972  nop
0x140049973  xorps   xmm0, xmm0
0x140049976  movups  [rsp+150h+var_110], xmm0
0x14004997b  mov     [rsp+150h+var_100], r12
0x140049980  mov     [rsp+150h+var_F8], r12
0x140049985  mov     r8d, 6
0x14004998b  lea     rdx, aClient; "Client"
0x140049992  lea     rcx, [rsp+150h+var_110]
0x140049997  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004999c  nop
0x14004999d  lea     r9, [rsp+150h+var_F0]
0x1400499a2  lea     r8, [rsp+150h+var_110]
0x1400499a7  mov     edx, 4
0x1400499ac  lea     rcx, [rbp+50h+var_A8]
0x1400499b0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400499b5  nop
0x1400499b6  lea     rcx, [rsp+150h+var_110]
0x1400499bb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400499c0  nop
0x1400499c1  lea     rcx, [rsp+150h+var_F0]
0x1400499c6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400499cb  nop
0x1400499cc  lea     rcx, [rbp+50h+var_A8]
0x1400499d0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400499d5  nop
0x1400499d6  mov     eax, ebx
0x1400499d8  lock xadd [rsi+8], eax
0x1400499dd  add     eax, ebx
0x1400499df  jnz     short loc_140049A0A
0x1400499e1  mov     rax, [rsi]
0x1400499e4  mov     rcx, rsi
0x1400499e7  mov     rax, [rax]
0x1400499ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400499ef  mov     eax, ebx
0x1400499f1  lock xadd [rsi+0Ch], eax
0x1400499f6  add     eax, ebx
0x1400499f8  jnz     short loc_140049A0A
0x1400499fa  mov     rax, [rsi]
0x1400499fd  mov     rcx, rsi
0x140049a00  mov     rax, [rax+8]
0x140049a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049a09  nop
0x140049a0a  add     [rdi+28h], ebx
0x140049a0d  jnz     short loc_140049A13
0x140049a0f  mov     [rdi+2Ch], r12d
0x140049a13  mov     rcx, rdi; lpCriticalSection
0x140049a16  call    cs:__imp_LeaveCriticalSection
0x140049a1c  mov     rax, 8000000000h
0x140049a26  jmp     loc_140049BA6
0x140049a2b  call    cs:__imp_GetLastError
0x140049a31  mov     [rsp+150h+var_130], eax
0x140049a35  lea     rdx, aAppvClientHost_22; "AppV::Client::Host::UserManagerImpl::In"...
0x140049a3c  lea     rcx, [rbp+50h+var_A8]
0x140049a40  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140049a45  mov     [rbp+50h+var_88], 4Fh ; 'O'
0x140049a4c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140049a51  xorps   xmm0, xmm0
0x140049a54  movups  [rsp+150h+var_110], xmm0
0x140049a59  mov     [rsp+150h+var_100], r12
0x140049a5e  mov     [rsp+150h+var_F8], r12
0x140049a63  mov     r8d, 5Bh ; '['
0x140049a69  lea     rdx, aUsermanagerFai_5; "UserManager failed to create a thread p"...
0x140049a70  lea     rcx, [rsp+150h+var_110]
0x140049a75  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049a7a  nop
0x140049a7b  lea     r8, [rsp+150h+var_110]
0x140049a80  lea     rdx, [rbp+50h+var_80]
0x140049a84  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140049a89  nop
0x140049a8a  lea     rdx, [rsp+150h+var_130]
0x140049a8f  mov     rcx, rax
0x140049a92  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140049a97  mov     rbx, rax
0x140049a9a  xorps   xmm0, xmm0
0x140049a9d  movups  [rsp+150h+var_F0], xmm0
0x140049aa2  mov     [rsp+150h+var_E0], r12
0x140049aa7  mov     [rsp+150h+var_D8], r12
0x140049aac  mov     r8d, 6
0x140049ab2  lea     rdx, aClient; "Client"
0x140049ab9  lea     rcx, [rsp+150h+var_F0]
0x140049abe  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049ac3  nop
0x140049ac4  mov     r9, rbx
0x140049ac7  lea     r8, [rsp+150h+var_F0]
0x140049acc  mov     edx, r14d
0x140049acf  lea     rcx, [rbp+50h+var_A8]
0x140049ad3  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140049ad8  nop
0x140049ad9  lea     rcx, [rsp+150h+var_F0]
0x140049ade  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049ae3  nop
0x140049ae4  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140049aeb  mov     [rbp+50h+var_80], rax
0x140049aef  lea     rcx, [rbp+50h+var_70]
0x140049af3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049af8  nop
0x140049af9  lea     rcx, [rsp+150h+var_110]
0x140049afe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049b03  nop
0x140049b04  lea     rcx, [rbp+50h+var_A8]
0x140049b08  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
  ... truncated ...
```
