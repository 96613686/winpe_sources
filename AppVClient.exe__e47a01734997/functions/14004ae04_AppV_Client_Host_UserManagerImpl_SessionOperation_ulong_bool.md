# AppV::Client::Host::UserManagerImpl::SessionOperation(ulong,bool)

- ea: `0x14004ae04`
- end: `0x14004b340`
- name: `?SessionOperation@UserManagerImpl@Host@Client@AppV@@AEAA_KK_N@Z`
- size: `1340`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004a580`
- `0x14004a5a0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x1400094bc`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14004ae04`
- `0x140052c90`
- `0x140052d90`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x14004b06a`
- `KERNEL32!CreateThreadpoolWork` at `0x14004b06a`
- `KERNEL32!SubmitThreadpoolWork` at `0x14004b07b`
- `KERNEL32!SubmitThreadpoolWork` at `0x14004b07b`
- `KERNEL32!GetLastError` at `0x14004b0d6`
- `KERNEL32!GetLastError` at `0x14004b0d6`
- `KERNEL32!GetCurrentThreadId` at `0x14004ae5f`
- `KERNEL32!GetCurrentThreadId` at `0x14004ae5f`
- `KERNEL32!LeaveCriticalSection` at `0x14004b0c1`
- `KERNEL32!LeaveCriticalSection` at `0x14004b310`
- `KERNEL32!LeaveCriticalSection` at `0x14004b0c1`
- `KERNEL32!LeaveCriticalSection` at `0x14004b310`
- `KERNEL32!EnterCriticalSection` at `0x14004ae50`
- `KERNEL32!EnterCriticalSection` at `0x14004ae50`
- `KERNEL32!CloseThreadpoolWork` at `0x14004b084`
- `KERNEL32!CloseThreadpoolWork` at `0x14004b084`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004af19`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004b29f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004af19`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004b29f`

## string_xrefs

- `0x14004af12`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004af29`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004b298`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004b2af`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004b11a`: `UserManager failed to queue a work item to the thread pool to process asynchronous session %1% logon, error = %2%`
- `0x14004b1e5`: `UserManager failed to queue a work item to the thread pool to process asynchronous session %1% logoff, error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
unsigned __int64 __fastcall AppV::Client::Host::UserManagerImpl::SessionOperation(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        char a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  char *v6; // rax
  const char *v7; // rax
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  bool v10; // zf
  int v11; // ebx
  ULONG_PTR SpinCount; // rax
  HANDLE LockSemaphore; // r13
  volatile signed __int32 *v14; // r15
  _QWORD *v15; // rax
  char *v16; // r8
  void (__stdcall *v17)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK); // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v19; // rbx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  char *v26; // rax
  const char *v27; // rax
  unsigned __int64 FileId; // rax
  unsigned int v29; // [rsp+20h] [rbp-B9h] BYREF
  PVOID pv; // [rsp+28h] [rbp-B1h] BYREF
  _QWORD *v31; // [rsp+30h] [rbp-A9h] BYREF
  _QWORD v32[2]; // [rsp+38h] [rbp-A1h] BYREF
  char v33; // [rsp+48h] [rbp-91h]
  struct _RTL_CRITICAL_SECTION *v34; // [rsp+50h] [rbp-89h]
  __int128 v35; // [rsp+58h] [rbp-81h] BYREF
  HANDLE v36; // [rsp+68h] [rbp-71h]
  volatile signed __int32 *v37; // [rsp+70h] [rbp-69h]
  __int128 v38; // [rsp+78h] [rbp-61h] BYREF
  __int64 v39; // [rsp+88h] [rbp-51h]
  __int64 v40; // [rsp+90h] [rbp-49h]
  char *v41[4]; // [rsp+98h] [rbp-41h] BYREF
  int v42; // [rsp+B8h] [rbp-21h]
  void **v43; // [rsp+C0h] [rbp-19h] BYREF
  char *v44; // [rsp+D0h] [rbp-9h] BYREF

  v29 = a2;
  v32[1] = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v5 = this + 1;
  v34 = this + 1;
  EnterCriticalSection(this + 1);
  if ( ++LODWORD(v5[1].DebugInfo) == 1 )
    HIDWORD(v5[1].DebugInfo) = GetCurrentThreadId();
  v33 = 1;
  if ( this[2].LockCount != 1 )
  {
    std::string::string(v41, "AppV::Client::Host::UserManagerImpl::SessionOperation");
    v42 = 355;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v35,
      L"UserManager recevied an operational request when not initialized",
      0x40u);
    v38 = 0;
    v39 = 0;
    v40 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v38, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v41, 1, (int)&v38, (__int64)&v35);
    std::wstring::~wstring((char **)&v38);
    std::wstring::~wstring((char **)&v35);
    std::string::~string(v41);
    v6 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v6 )
      v7 = v6 + 1;
    else
      v7 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    v8 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v7) << 52)
       | 0x2C0E00000302LL;
LABEL_39:
    v10 = LODWORD(v5[1].DebugInfo)-- == 1;
    if ( v10 )
      HIDWORD(v5[1].DebugInfo) = 0;
LABEL_41:
    LeaveCriticalSection(v5);
    return v8;
  }
  LODWORD(pv) = 0;
  v9 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, PVOID *))(*(_QWORD *)this->LockSemaphore + 8LL))(
         this->LockSemaphore,
         v29,
         &pv);
  if ( (v9 & 0x8000000000LL) == 0 )
  {
    v10 = LODWORD(v5[1].DebugInfo)-- == 1;
    if ( v10 )
      HIDWORD(v5[1].DebugInfo) = 0;
    v8 = v9;
    goto LABEL_41;
  }
  *(_QWORD *)&v35 =  AppV::Client::Service::NotificationManager::`vcall'{16,{flat}};
  v11 = (int)pv;
  DWORD2(v35) = (_DWORD)pv;
  SpinCount = this->SpinCount;
  if ( SpinCount )
    _InterlockedIncrement((volatile signed __int32 *)(SpinCount + 8));
  LockSemaphore = this->LockSemaphore;
  v36 = LockSemaphore;
  v37 = (volatile signed __int32 *)this->SpinCount;
  v14 = v37;
  v15 = operator new(0x28u);
  v31 = v15;
  *v15 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionQueue::*)(unsigned long),std::shared_ptr<AppV::Client::Host::SessionQueue> &,unsigned long &>>::`vftable';
  v15[1] =  AppV::Client::Service::NotificationManager::`vcall'{16,{flat}};
  *((_DWORD *)v15 + 4) = v11;
  v15[3] = 0;
  v15[4] = 0;
  if ( v14 )
    _InterlockedIncrement(v14 + 2);
  v15[3] = LockSemaphore;
  v15[4] = v14;
  v32[0] = v15;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v16 = (char *)this[2].LockSemaphore;
  v17 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))AppV::Client::Host::UserManagerImpl::LogonAsync;
  if ( !a3 )
    v17 = AppV::Client::Host::UserManagerImpl::LogoffAsync;
  if ( !*(_QWORD *)v16
    || (ThreadpoolWork = CreateThreadpoolWork(v17, (PVOID)(unsigned int)pv, (PTP_CALLBACK_ENVIRON)(v16 + 8)),
        (v19 = ThreadpoolWork) == 0) )
  {
    LODWORD(v31) = GetLastError();
    std::string::string(v41, "AppV::Client::Host::UserManagerImpl::SessionOperation");
    if ( a3 )
    {
      v42 = 374;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v38 = 0;
      v39 = 0;
      v40 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v38,
        L"UserManager failed to queue a work item to the thread pool to process asynchronous session %1% logon, error = %2%",
        0x71u);
    }
    else
    {
      v42 = 380;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v38 = 0;
      v39 = 0;
      v40 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v38,
        L"UserManager failed to queue a work item to the thread pool to process asynchronous session %1% logoff, error = %2%",
        0x72u);
    }
    v23 = AppV::Log::fmt(v22, &v43, &v38);
    v24 = AppV::LogFormatter::operator%<unsigned long>(v23, (__int64)&v29);
    v25 = AppV::LogFormatter::operator%<unsigned long>(v24, (__int64)&v31);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v35, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v41, 1, (int)&v35, v25);
    std::wstring::~wstring((char **)&v35);
    v43 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v44);
    std::wstring::~wstring((char **)&v38);
    std::string::~string(v41);
    v26 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v26 )
      v27 = v26 + 1;
    else
      v27 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v27);
    v8 = (unsigned int)v31 | (FileId << 52) | 0x2F2E00000000LL;
    if ( a3 )
      AppV::Client::Host::Session::ReportPublicLogonError(v29, v8);
    else
      AppV::Client::Host::Session::ReportPublicLogoffError(v29, v8);
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)v32);
    goto LABEL_39;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v19);
  v20 = (void (__fastcall ***)(_QWORD, __int64))v32[0];
  v32[0] = 0;
  if ( v20 )
    (**v20)(v20, 1);
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)v32);
  v10 = LODWORD(v5[1].DebugInfo)-- == 1;
  if ( v10 )
    HIDWORD(v5[1].DebugInfo) = 0;
  LeaveCriticalSection(v5);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14004ae04  mov     [rsp-8+arg_10], rbx
0x14004ae09  push    rbp
0x14004ae0a  push    rsi
0x14004ae0b  push    rdi
0x14004ae0c  push    r12
0x14004ae0e  push    r13
0x14004ae10  push    r14
0x14004ae12  push    r15
0x14004ae14  lea     rbp, [rsp-27h]
0x14004ae19  sub     rsp, 100h
0x14004ae20  mov     rax, cs:__security_cookie
0x14004ae27  xor     rax, rsp
0x14004ae2a  mov     [rbp+57h+var_40], rax
0x14004ae2e  mov     r12b, r8b
0x14004ae31  mov     r14, rcx
0x14004ae34  mov     [rsp+130h+var_110], edx
0x14004ae38  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004ae3f  mov     [rsp+130h+var_F0], rax
0x14004ae44  lea     rdi, [rcx+28h]
0x14004ae48  mov     [rsp+130h+var_E0], rdi
0x14004ae4d  mov     rcx, rdi; lpCriticalSection
0x14004ae50  call    cs:__imp_EnterCriticalSection
0x14004ae56  inc     dword ptr [rdi+28h]
0x14004ae59  cmp     dword ptr [rdi+28h], 1
0x14004ae5d  jnz     short loc_14004AE68
0x14004ae5f  call    cs:__imp_GetCurrentThreadId
0x14004ae65  mov     [rdi+2Ch], eax
0x14004ae68  mov     [rsp+130h+var_E8], 1
0x14004ae6d  cmp     dword ptr [r14+58h], 1
0x14004ae72  jz      loc_14004AF58
0x14004ae78  lea     rdx, aAppvClientHost_16; "AppV::Client::Host::UserManagerImpl::Se"...
0x14004ae7f  lea     rcx, [rbp+57h+var_98]
0x14004ae83  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004ae88  mov     [rbp+57h+var_78], 163h
0x14004ae8f  xorps   xmm0, xmm0
0x14004ae92  movups  [rsp+130h+var_D8], xmm0
0x14004ae97  xor     esi, esi
0x14004ae99  mov     [rbp+57h+var_C8], rsi
0x14004ae9d  mov     [rbp+57h+var_C0], rsi
0x14004aea1  lea     r8d, [rsi+40h]
0x14004aea5  lea     rdx, aUsermanagerRec; "UserManager recevied an operational req"...
0x14004aeac  lea     rcx, [rsp+130h+var_D8]
0x14004aeb1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004aeb6  nop
0x14004aeb7  xorps   xmm0, xmm0
0x14004aeba  movups  [rbp+57h+var_B8], xmm0
0x14004aebe  mov     [rbp+57h+var_A8], rsi
0x14004aec2  mov     [rbp+57h+var_A0], rsi
0x14004aec6  lea     r8d, [rsi+6]
0x14004aeca  lea     rdx, aClient; "Client"
0x14004aed1  lea     rcx, [rbp+57h+var_B8]
0x14004aed5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004aeda  nop
0x14004aedb  lea     r9, [rsp+130h+var_D8]
0x14004aee0  lea     r8, [rbp+57h+var_B8]
0x14004aee4  lea     edx, [rsi+1]
0x14004aee7  lea     rcx, [rbp+57h+var_98]
0x14004aeeb  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004aef0  nop
0x14004aef1  lea     rcx, [rbp+57h+var_B8]
0x14004aef5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004aefa  nop
0x14004aefb  lea     rcx, [rsp+130h+var_D8]
0x14004af00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004af05  nop
0x14004af06  lea     rcx, [rbp+57h+var_98]
0x14004af0a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004af0f  lea     edx, [rsi+5Ch]; Ch
0x14004af12  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004af19  call    cs:__imp_strrchr
0x14004af1f  test    rax, rax
0x14004af22  jz      short loc_14004AF29
0x14004af24  inc     rax
0x14004af27  jmp     short loc_14004AF30
0x14004af29  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004af30  mov     rdx, rax; char *
0x14004af33  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004af3a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004af3f  mov     rbx, rax
0x14004af42  shl     rbx, 34h
0x14004af46  mov     rax, 2C0E00000302h
0x14004af50  or      rbx, rax
0x14004af53  jmp     loc_14004B304
0x14004af58  xor     esi, esi
0x14004af5a  mov     dword ptr [rsp+130h+pv], esi
0x14004af5e  mov     rcx, [r14+18h]
0x14004af62  mov     rax, [rcx]
0x14004af65  lea     r8, [rsp+130h+pv]
0x14004af6a  mov     edx, [rsp+130h+var_110]
0x14004af6e  mov     rax, [rax+8]
0x14004af72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004af77  bt      rax, 27h ; '''
0x14004af7c  jb      short loc_14004AF8F
0x14004af7e  sub     dword ptr [rdi+28h], 1
0x14004af82  jnz     short loc_14004AF87
0x14004af84  mov     [rdi+2Ch], esi
0x14004af87  mov     rbx, rax
0x14004af8a  jmp     loc_14004B30D
0x14004af8f  lea     rax, ??_9NotificationManager@Service@Client@AppV@@$BBA@AA; [thunk]: AppV::Client::Service::NotificationManager::`vcall'{16,{flat}}
0x14004af96  mov     qword ptr [rsp+130h+var_D8], rax
0x14004af9b  mov     ebx, dword ptr [rsp+130h+pv]
0x14004af9f  mov     dword ptr [rbp+57h+var_D8+8], ebx
0x14004afa2  mov     rax, [r14+20h]
0x14004afa6  test    rax, rax
0x14004afa9  jz      short loc_14004AFAF
0x14004afab  lock inc dword ptr [rax+8]
0x14004afaf  mov     r13, [r14+18h]
0x14004afb3  mov     [rbp+57h+var_C8], r13
0x14004afb7  mov     r15, [r14+20h]
0x14004afbb  mov     [rbp+57h+var_C0], r15
0x14004afbf  mov     ecx, 28h ; '('; Size
0x14004afc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004afc9  mov     [rsp+130h+var_100], rax
0x14004afce  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P8SessionQueue@Host@Client@AppV@@EAA_KK@ZAEAV?$shared_ptr@VSessionQueue@Host@Client@AppV@@@2@AEAK@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionQueue::*)(ulong),std::shared_ptr<AppV::Client::Host::SessionQueue> &,ulong &>>::`vftable'
0x14004afd5  mov     [rax], rcx
0x14004afd8  lea     rcx, ??_9NotificationManager@Service@Client@AppV@@$BBA@AA; [thunk]: AppV::Client::Service::NotificationManager::`vcall'{16,{flat}}
0x14004afdf  mov     [rax+8], rcx
0x14004afe3  mov     [rax+10h], ebx
0x14004afe6  mov     [rax+18h], rsi
0x14004afea  mov     [rax+20h], rsi
0x14004afee  mov     rbx, r15
0x14004aff1  test    r15, r15
0x14004aff4  jz      short loc_14004AFFB
0x14004aff6  lock inc dword ptr [r15+8]
0x14004affb  mov     [rax+18h], r13
0x14004afff  mov     [rax+20h], r15
0x14004b003  mov     [rsp+130h+var_F8], rax
0x14004b008  test    rbx, rbx
0x14004b00b  jz      short loc_14004B044
0x14004b00d  or      eax, 0FFFFFFFFh
0x14004b010  lock xadd [rbx+8], eax
0x14004b015  cmp     eax, 1
0x14004b018  jnz     short loc_14004B044
0x14004b01a  mov     rax, [rbx]
0x14004b01d  mov     rcx, rbx
0x14004b020  mov     rax, [rax]
0x14004b023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b028  or      eax, 0FFFFFFFFh
0x14004b02b  lock xadd [rbx+0Ch], eax
0x14004b030  cmp     eax, 1
0x14004b033  jnz     short loc_14004B044
0x14004b035  mov     rax, [rbx]
0x14004b038  mov     rcx, rbx
0x14004b03b  mov     rax, [rax+8]
0x14004b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b044  mov     r8, [r14+68h]
0x14004b048  lea     rcx, ?LogonAsync@UserManagerImpl@Host@Client@AppV@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; AppV::Client::Host::UserManagerImpl::LogonAsync(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x14004b04f  lea     rax, ?LogoffAsync@UserManagerImpl@Host@Client@AppV@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; AppV::Client::Host::UserManagerImpl::LogoffAsync(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x14004b056  test    r12b, r12b
0x14004b059  cmovz   rcx, rax; pfnwk
0x14004b05d  cmp     [r8], rsi
0x14004b060  jz      short loc_14004B0D6
0x14004b062  add     r8, 8; pcbe
0x14004b066  mov     edx, dword ptr [rsp+130h+pv]; pv
0x14004b06a  call    cs:__imp_CreateThreadpoolWork
0x14004b070  mov     rbx, rax
0x14004b073  test    rax, rax
0x14004b076  jz      short loc_14004B0D6
0x14004b078  mov     rcx, rax; pwk
0x14004b07b  call    cs:__imp_SubmitThreadpoolWork
0x14004b081  mov     rcx, rbx; pwk
0x14004b084  call    cs:__imp_CloseThreadpoolWork
0x14004b08a  mov     rcx, [rsp+130h+var_F8]
0x14004b08f  mov     [rsp+130h+var_F8], rsi
0x14004b094  test    rcx, rcx
0x14004b097  jz      short loc_14004B0AA
0x14004b099  mov     rax, [rcx]
0x14004b09c  mov     edx, 1
0x14004b0a1  mov     rax, [rax]
0x14004b0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b0a9  nop
0x14004b0aa  lea     rcx, [rsp+130h+var_F8]; this
0x14004b0af  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14004b0b4  nop
0x14004b0b5  sub     dword ptr [rdi+28h], 1
0x14004b0b9  jnz     short loc_14004B0BE
0x14004b0bb  mov     [rdi+2Ch], esi
0x14004b0be  mov     rcx, rdi; lpCriticalSection
0x14004b0c1  call    cs:__imp_LeaveCriticalSection
0x14004b0c7  mov     rax, 8000000000h
0x14004b0d1  jmp     loc_14004B319
0x14004b0d6  call    cs:__imp_GetLastError
0x14004b0dc  mov     dword ptr [rsp+130h+var_100], eax
0x14004b0e0  lea     rdx, aAppvClientHost_16; "AppV::Client::Host::UserManagerImpl::Se"...
0x14004b0e7  lea     rcx, [rbp+57h+var_98]
0x14004b0eb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004b0f0  test    r12b, r12b
0x14004b0f3  jz      loc_14004B1C4
0x14004b0f9  mov     [rbp+57h+var_78], 176h
0x14004b100  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004b105  xorps   xmm0, xmm0
0x14004b108  movups  [rbp+57h+var_B8], xmm0
0x14004b10c  mov     [rbp+57h+var_A8], rsi
0x14004b110  mov     [rbp+57h+var_A0], rsi
0x14004b114  mov     r8d, 71h ; 'q'
0x14004b11a  lea     rdx, aUsermanagerFai_2; "UserManager failed to queue a work item"...
0x14004b121  lea     rcx, [rbp+57h+var_B8]
0x14004b125  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004b12a  nop
0x14004b12b  lea     r8, [rbp+57h+var_B8]
0x14004b12f  lea     rdx, [rbp+57h+var_70]
0x14004b133  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004b138  nop
0x14004b139  lea     rdx, [rsp+130h+var_110]
0x14004b13e  mov     rcx, rax
0x14004b141  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004b146  lea     rdx, [rsp+130h+var_100]
0x14004b14b  mov     rcx, rax
0x14004b14e  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004b153  mov     rbx, rax
0x14004b156  xorps   xmm0, xmm0
0x14004b159  movups  [rsp+130h+var_D8], xmm0
0x14004b15e  mov     [rbp+57h+var_C8], rsi
0x14004b162  mov     [rbp+57h+var_C0], rsi
0x14004b166  mov     r8d, 6
0x14004b16c  lea     rdx, aClient; "Client"
0x14004b173  lea     rcx, [rsp+130h+var_D8]
0x14004b178  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004b17d  nop
0x14004b17e  mov     r9, rbx
0x14004b181  lea     r8, [rsp+130h+var_D8]
0x14004b186  mov     edx, 1
0x14004b18b  lea     rcx, [rbp+57h+var_98]
0x14004b18f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004b194  nop
0x14004b195  lea     rcx, [rsp+130h+var_D8]
0x14004b19a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b19f  nop
0x14004b1a0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004b1a7  mov     [rbp+57h+var_70], rax
0x14004b1ab  lea     rcx, [rbp+57h+var_60]
0x14004b1af  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b1b4  nop
0x14004b1b5  lea     rcx, [rbp+57h+var_B8]
0x14004b1b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b1be  nop
0x14004b1bf  jmp     loc_14004B28A
0x14004b1c4  mov     [rbp+57h+var_78], 17Ch
0x14004b1cb  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004b1d0  xorps   xmm0, xmm0
0x14004b1d3  movups  [rbp+57h+var_B8], xmm0
0x14004b1d7  mov     [rbp+57h+var_A8], rsi
0x14004b1db  mov     [rbp+57h+var_A0], rsi
0x14004b1df  mov     r8d, 72h ; 'r'
0x14004b1e5  lea     rdx, aUsermanagerFai_4; "UserManager failed to queue a work item"...
0x14004b1ec  lea     rcx, [rbp+57h+var_B8]
0x14004b1f0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004b1f5  nop
0x14004b1f6  lea     r8, [rbp+57h+var_B8]
0x14004b1fa  lea     rdx, [rbp+57h+var_70]
0x14004b1fe  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004b203  nop
0x14004b204  lea     rdx, [rsp+130h+var_110]
0x14004b209  mov     rcx, rax
0x14004b20c  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004b211  lea     rdx, [rsp+130h+var_100]
0x14004b216  mov     rcx, rax
0x14004b219  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004b21e  mov     rbx, rax
0x14004b221  xorps   xmm0, xmm0
0x14004b224  movups  [rsp+130h+var_D8], xmm0
0x14004b229  mov     [rbp+57h+var_C8], rsi
0x14004b22d  mov     [rbp+57h+var_C0], rsi
0x14004b231  mov     r8d, 6
0x14004b237  lea     rdx, aClient; "Client"
0x14004b23e  lea     rcx, [rsp+130h+var_D8]
0x14004b243  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004b248  nop
0x14004b249  mov     r9, rbx
0x14004b24c  lea     r8, [rsp+130h+var_D8]
0x14004b251  mov     edx, 1
0x14004b256  lea     rcx, [rbp+57h+var_98]
0x14004b25a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004b25f  nop
0x14004b260  lea     rcx, [rsp+130h+var_D8]
0x14004b265  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b26a  nop
0x14004b26b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004b272  mov     [rbp+57h+var_70], rax
0x14004b276  lea     rcx, [rbp+57h+var_60]
0x14004b27a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b27f  nop
0x14004b280  lea     rcx, [rbp+57h+var_B8]
0x14004b284  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004b289  nop
0x14004b28a  lea     rcx, [rbp+57h+var_98]
0x14004b28e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004b293  mov     edx, 5Ch ; '\'; Ch
0x14004b298  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004b29f  call    cs:__imp_strrchr
0x14004b2a5  test    rax, rax
0x14004b2a8  jz      short loc_14004B2AF
0x14004b2aa  inc     rax
0x14004b2ad  jmp     short loc_14004B2B6
0x14004b2af  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004b2b6  mov     rdx, rax; char *
0x14004b2b9  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004b2c0  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004b2c5  mov     rbx, rax
0x14004b2c8  shl     rbx, 34h
  ... truncated ...
```
