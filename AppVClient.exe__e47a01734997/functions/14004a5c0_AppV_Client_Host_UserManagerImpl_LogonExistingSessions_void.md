# AppV::Client::Host::UserManagerImpl::LogonExistingSessions(void)

- ea: `0x14004a5c0`
- end: `0x14004a8b3`
- name: `?LogonExistingSessions@UserManagerImpl@Host@Client@AppV@@UEAA_KXZ`
- size: `755`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `12`
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
- `0x14004a5c0`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x14004a71a`
- `KERNEL32!CreateThreadpoolWork` at `0x14004a71a`
- `KERNEL32!SubmitThreadpoolWork` at `0x14004a72b`
- `KERNEL32!SubmitThreadpoolWork` at `0x14004a72b`
- `KERNEL32!GetLastError` at `0x14004a757`
- `KERNEL32!GetLastError` at `0x14004a757`
- `KERNEL32!GetCurrentThreadId` at `0x14004a60d`
- `KERNEL32!GetCurrentThreadId` at `0x14004a60d`
- `KERNEL32!LeaveCriticalSection` at `0x14004a889`
- `KERNEL32!LeaveCriticalSection` at `0x14004a889`
- `KERNEL32!EnterCriticalSection` at `0x14004a5fe`
- `KERNEL32!EnterCriticalSection` at `0x14004a5fe`
- `KERNEL32!CloseThreadpoolWork` at `0x14004a734`
- `KERNEL32!CloseThreadpoolWork` at `0x14004a734`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a6c7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a839`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a6c7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a839`

## string_xrefs

- `0x14004a6c0`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a6d7`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a832`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a849`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a791`: `UserManager failed to queue a work item to the thread pool to process asynchronous session enumeration, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppV::Client::Host::UserManagerImpl::LogonExistingSessions(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  char *v3; // rax
  const char *v4; // rax
  unsigned __int64 v5; // rbx
  __int64 v6; // rax
  char *LockSemaphore; // r8
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v9; // rbx
  bool v10; // zf
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 FileId; // rax
  DWORD LastError; // [rsp+20h] [rbp-69h] BYREF
  void **v20; // [rsp+28h] [rbp-61h]
  char v21; // [rsp+30h] [rbp-59h]
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+38h] [rbp-51h]
  __int128 v23; // [rsp+40h] [rbp-49h] BYREF
  __int128 v24; // [rsp+50h] [rbp-39h]
  __int128 v25; // [rsp+60h] [rbp-29h] BYREF
  __int128 v26; // [rsp+70h] [rbp-19h]
  char *v27[4]; // [rsp+80h] [rbp-9h] BYREF
  int v28; // [rsp+A0h] [rbp+17h]
  void **v29; // [rsp+A8h] [rbp+1Fh] BYREF
  char *v30; // [rsp+B8h] [rbp+2Fh] BYREF

  v20 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v2 = this + 1;
  v22 = this + 1;
  EnterCriticalSection(this + 1);
  if ( ++LODWORD(v2[1].DebugInfo) == 1 )
    HIDWORD(v2[1].DebugInfo) = GetCurrentThreadId();
  v21 = 1;
  if ( this[2].LockCount != 1 )
  {
    std::string::string(v27, "AppV::Client::Host::UserManagerImpl::LogonExistingSessions");
    v28 = 98;
    v25 = 0;
    v26 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v25,
      L"UserManager recevied an operational request when not initialized",
      0x40u);
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v23, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v27, 1, (int)&v23, (__int64)&v25);
    std::wstring::~wstring((char **)&v23);
    std::wstring::~wstring((char **)&v25);
    std::string::~string(v27);
    v3 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v3 )
      v4 = v3 + 1;
    else
      v4 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    v5 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v4) << 52;
    v6 = 0xC0E00000302LL;
LABEL_17:
    v11 = v6 | v5;
    v10 = LODWORD(v2[1].DebugInfo)-- == 1;
    if ( v10 )
      HIDWORD(v2[1].DebugInfo) = 0;
    goto LABEL_19;
  }
  LockSemaphore = (char *)this[2].LockSemaphore;
  if ( !*(_QWORD *)LockSemaphore
    || (ThreadpoolWork = CreateThreadpoolWork(
                           AppV::Client::Host::UserManagerImpl::EnumSessionsAsync,
                           0,
                           (PTP_CALLBACK_ENVIRON)(LockSemaphore + 8)),
        (v9 = ThreadpoolWork) == 0) )
  {
    LastError = GetLastError();
    std::string::string(v27, "AppV::Client::Host::UserManagerImpl::LogonExistingSessions");
    v28 = 105;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v23,
      L"UserManager failed to queue a work item to the thread pool to process asynchronous session enumeration, error = %1%",
      0x73u);
    v13 = AppV::Log::fmt(v12, &v29, &v23);
    v14 = AppV::LogFormatter::operator%<unsigned long>(v13, (__int64)&LastError);
    v25 = 0;
    v26 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v25, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v27, 1, (int)&v25, v14);
    std::wstring::~wstring((char **)&v25);
    v29 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v30);
    std::wstring::~wstring((char **)&v23);
    std::string::~string(v27);
    v15 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v15 )
      v16 = v15 + 1;
    else
      v16 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
    v5 = LastError | (FileId << 52);
    v6 = 0xD2E00000000LL;
    goto LABEL_17;
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(v9);
  v10 = LODWORD(v2[1].DebugInfo)-- == 1;
  if ( v10 )
    HIDWORD(v2[1].DebugInfo) = 0;
  v11 = 0x8000000000LL;
LABEL_19:
  LeaveCriticalSection(v2);
  return v11;
}

```

## disassembly

```asm
0x14004a5c0  mov     [rsp-8+arg_8], rbx
0x14004a5c5  mov     [rsp-8+arg_10], rdi
0x14004a5ca  push    rbp
0x14004a5cb  lea     rbp, [rsp-57h]
0x14004a5d0  sub     rsp, 0E0h
0x14004a5d7  mov     rax, cs:__security_cookie
0x14004a5de  xor     rax, rsp
0x14004a5e1  mov     [rbp+57h+var_8], rax
0x14004a5e5  mov     rbx, rcx
0x14004a5e8  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004a5ef  mov     [rbp+57h+var_B8], rax
0x14004a5f3  lea     rdi, [rcx+28h]
0x14004a5f7  mov     [rbp+57h+var_A8], rdi
0x14004a5fb  mov     rcx, rdi; lpCriticalSection
0x14004a5fe  call    cs:__imp_EnterCriticalSection
0x14004a604  inc     dword ptr [rdi+28h]
0x14004a607  cmp     dword ptr [rdi+28h], 1
0x14004a60b  jnz     short loc_14004A616
0x14004a60d  call    cs:__imp_GetCurrentThreadId
0x14004a613  mov     [rdi+2Ch], eax
0x14004a616  mov     [rbp+57h+var_B0], 1
0x14004a61a  cmp     dword ptr [rbx+58h], 1
0x14004a61e  jz      loc_14004A703
0x14004a624  lea     rdx, aAppvClientHost_4; "AppV::Client::Host::UserManagerImpl::Lo"...
0x14004a62b  lea     rcx, [rbp+57h+var_60]
0x14004a62f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004a634  mov     [rbp+57h+var_40], 62h ; 'b'
0x14004a63b  xorps   xmm0, xmm0
0x14004a63e  movups  [rbp+57h+var_80], xmm0
0x14004a642  xorps   xmm1, xmm1
0x14004a645  movdqu  [rbp+57h+var_70], xmm1
0x14004a64a  mov     r8d, 40h ; '@'
0x14004a650  lea     rdx, aUsermanagerRec; "UserManager recevied an operational req"...
0x14004a657  lea     rcx, [rbp+57h+var_80]
0x14004a65b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a660  nop
0x14004a661  xorps   xmm0, xmm0
0x14004a664  movups  [rbp+57h+var_A0], xmm0
0x14004a668  xorps   xmm1, xmm1
0x14004a66b  movdqu  [rbp+57h+var_90], xmm1
0x14004a670  mov     r8d, 6
0x14004a676  lea     rdx, aClient; "Client"
0x14004a67d  lea     rcx, [rbp+57h+var_A0]
0x14004a681  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a686  nop
0x14004a687  lea     r9, [rbp+57h+var_80]
0x14004a68b  lea     r8, [rbp+57h+var_A0]
0x14004a68f  mov     edx, 1
0x14004a694  lea     rcx, [rbp+57h+var_60]
0x14004a698  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004a69d  nop
0x14004a69e  lea     rcx, [rbp+57h+var_A0]
0x14004a6a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a6a7  nop
0x14004a6a8  lea     rcx, [rbp+57h+var_80]
0x14004a6ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a6b1  nop
0x14004a6b2  lea     rcx, [rbp+57h+var_60]
0x14004a6b6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a6bb  mov     edx, 5Ch ; '\'; Ch
0x14004a6c0  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a6c7  call    cs:__imp_strrchr
0x14004a6cd  test    rax, rax
0x14004a6d0  jz      short loc_14004A6D7
0x14004a6d2  inc     rax
0x14004a6d5  jmp     short loc_14004A6DE
0x14004a6d7  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a6de  mov     rdx, rax; char *
0x14004a6e1  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004a6e8  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004a6ed  mov     rbx, rax
0x14004a6f0  shl     rbx, 34h
0x14004a6f4  mov     rax, 0C0E00000302h
0x14004a6fe  jmp     loc_14004A876
0x14004a703  mov     r8, [rbx+68h]
0x14004a707  cmp     qword ptr [r8], 0
0x14004a70b  jz      short loc_14004A757
0x14004a70d  add     r8, 8; pcbe
0x14004a711  xor     edx, edx; pv
0x14004a713  lea     rcx, ?EnumSessionsAsync@UserManagerImpl@Host@Client@AppV@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14004a71a  call    cs:__imp_CreateThreadpoolWork
0x14004a720  mov     rbx, rax
0x14004a723  test    rax, rax
0x14004a726  jz      short loc_14004A757
0x14004a728  mov     rcx, rax; pwk
0x14004a72b  call    cs:__imp_SubmitThreadpoolWork
0x14004a731  mov     rcx, rbx; pwk
0x14004a734  call    cs:__imp_CloseThreadpoolWork
0x14004a73a  nop
0x14004a73b  sub     dword ptr [rdi+28h], 1
0x14004a73f  jnz     short loc_14004A748
0x14004a741  mov     dword ptr [rdi+2Ch], 0
0x14004a748  mov     rbx, 8000000000h
0x14004a752  jmp     loc_14004A886
0x14004a757  call    cs:__imp_GetLastError
0x14004a75d  mov     [rbp+57h+var_C0], eax
0x14004a760  lea     rdx, aAppvClientHost_4; "AppV::Client::Host::UserManagerImpl::Lo"...
0x14004a767  lea     rcx, [rbp+57h+var_60]
0x14004a76b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004a770  mov     [rbp+57h+var_40], 69h ; 'i'
0x14004a777  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004a77c  xorps   xmm0, xmm0
0x14004a77f  movups  [rbp+57h+var_A0], xmm0
0x14004a783  xorps   xmm1, xmm1
0x14004a786  movdqu  [rbp+57h+var_90], xmm1
0x14004a78b  mov     r8d, 73h ; 's'
0x14004a791  lea     rdx, aUsermanagerFai_9; "UserManager failed to queue a work item"...
0x14004a798  lea     rcx, [rbp+57h+var_A0]
0x14004a79c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a7a1  nop
0x14004a7a2  lea     r8, [rbp+57h+var_A0]
0x14004a7a6  lea     rdx, [rbp+57h+var_38]
0x14004a7aa  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004a7af  nop
0x14004a7b0  lea     rdx, [rbp+57h+var_C0]
0x14004a7b4  mov     rcx, rax
0x14004a7b7  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004a7bc  mov     rbx, rax
0x14004a7bf  xorps   xmm0, xmm0
0x14004a7c2  movups  [rbp+57h+var_80], xmm0
0x14004a7c6  xorps   xmm1, xmm1
0x14004a7c9  movdqu  [rbp+57h+var_70], xmm1
0x14004a7ce  mov     r8d, 6
0x14004a7d4  lea     rdx, aClient; "Client"
0x14004a7db  lea     rcx, [rbp+57h+var_80]
0x14004a7df  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a7e4  nop
0x14004a7e5  mov     r9, rbx
0x14004a7e8  lea     r8, [rbp+57h+var_80]
0x14004a7ec  mov     edx, 1
0x14004a7f1  lea     rcx, [rbp+57h+var_60]
0x14004a7f5  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004a7fa  nop
0x14004a7fb  lea     rcx, [rbp+57h+var_80]
0x14004a7ff  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a804  nop
0x14004a805  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004a80c  mov     [rbp+57h+var_38], rax
0x14004a810  lea     rcx, [rbp+57h+var_28]
0x14004a814  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a819  nop
0x14004a81a  lea     rcx, [rbp+57h+var_A0]
0x14004a81e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a823  nop
0x14004a824  lea     rcx, [rbp+57h+var_60]
0x14004a828  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a82d  mov     edx, 5Ch ; '\'; Ch
0x14004a832  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a839  call    cs:__imp_strrchr
0x14004a83f  test    rax, rax
0x14004a842  jz      short loc_14004A849
0x14004a844  inc     rax
0x14004a847  jmp     short loc_14004A850
0x14004a849  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a850  mov     rdx, rax; char *
0x14004a853  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004a85a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004a85f  mov     rbx, rax
0x14004a862  shl     rbx, 34h
0x14004a866  mov     ecx, [rbp+57h+var_C0]
0x14004a869  or      rbx, rcx
0x14004a86c  mov     rax, 0D2E00000000h
0x14004a876  or      rbx, rax
0x14004a879  sub     dword ptr [rdi+28h], 1
0x14004a87d  jnz     short loc_14004A886
0x14004a87f  mov     dword ptr [rdi+2Ch], 0
0x14004a886  mov     rcx, rdi; lpCriticalSection
0x14004a889  call    cs:__imp_LeaveCriticalSection
0x14004a88f  mov     rax, rbx
0x14004a892  mov     rcx, [rbp+57h+var_8]
0x14004a896  xor     rcx, rsp; StackCookie
0x14004a899  call    __security_check_cookie
0x14004a89e  lea     r11, [rsp+0E0h+var_s0]
0x14004a8a6  mov     rbx, [r11+18h]
0x14004a8aa  mov     rdi, [r11+20h]
0x14004a8ae  mov     rsp, r11
0x14004a8b1  pop     rbp
0x14004a8b2  retn
```
