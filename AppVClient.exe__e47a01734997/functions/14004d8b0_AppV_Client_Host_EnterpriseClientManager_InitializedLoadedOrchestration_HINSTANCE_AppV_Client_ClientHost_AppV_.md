# AppV::Client::Host::EnterpriseClientManager::InitializedLoadedOrchestration(HINSTANCE__ *,AppV::Client::ClientHost &,AppV::Client::ClientEventSink &)

- ea: `0x14004d8b0`
- end: `0x14004dbaa`
- name: `?InitializedLoadedOrchestration@EnterpriseClientManager@Host@Client@AppV@@MEBA_KPEAUHINSTANCE__@@AEAVClientHost@34@AEAVClientEventSink@34@@Z`
- size: `762`
- prototype: `unsigned __int64(AppV::Client::Host::EnterpriseClientManager *__hidden this, HINSTANCE, struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14003d01c`
- `0x14004bc10`
- `0x14004d8b0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14004d8e6`
- `KERNEL32!GetProcAddress` at `0x14004d8e6`
- `KERNEL32!GetLastError` at `0x14004d8f5`
- `KERNEL32!GetLastError` at `0x14004d8f5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004da4b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004da4b`

## string_xrefs

- `0x14004da44`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004da5b`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004dadf`: `Orchestration DLL Initialize() failed, error = %1%`
- `0x14004d937`: `failed to find/load Orchestration DLL export '%1%', error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppV::Client::Host::EnterpriseClientManager::InitializedLoadedOrchestration(
        AppV::Client::Host::EnterpriseClientManager *this,
        HINSTANCE a2,
        struct AppV::Client::ClientHost *a3,
        struct AppV::Client::ClientEventSink *a4)
{
  FARPROC ProcAddress; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  __int64 v12; // rbx
  char *v13; // rax
  const char *v14; // rax
  unsigned __int64 FileId; // rax
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  DWORD LastError; // [rsp+20h] [rbp-79h] BYREF
  void *Block; // [rsp+28h] [rbp-71h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v25; // [rsp+40h] [rbp-59h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h]
  __int64 v27; // [rsp+58h] [rbp-41h]
  __int128 v28; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h]
  __int64 v30; // [rsp+78h] [rbp-21h]
  char *v31[4]; // [rsp+80h] [rbp-19h] BYREF
  int v32; // [rsp+A0h] [rbp+7h]
  _QWORD v33[2]; // [rsp+A8h] [rbp+Fh] BYREF
  char *v34[4]; // [rsp+B8h] [rbp+1Fh] BYREF

  ProcAddress = GetProcAddress(a2, "Initialize");
  if ( ProcAddress )
  {
    v17 = ((__int64 (__fastcall *)(struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *))ProcAddress)(
            a3,
            a4);
    if ( (v17 & 0x8000000000LL) == 0 )
    {
      std::string::string(v31, "AppV::Client::Host::EnterpriseClientManager::InitializedLoadedOrchestration");
      v32 = 288;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v18);
      v25 = 0;
      v26 = 0;
      v27 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v25,
        L"Orchestration DLL Initialize() failed, error = %1%",
        0x32u);
      v20 = AppV::Log::fmt(v19, v33, &v25);
      Block = (void *)v17;
      v21 = AppV::LogFormatter::operator%(v20, (__int64 *)&Block);
      v28 = 0;
      v29 = 0;
      v30 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v28, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v31, 8, (int)&v28, v21);
      std::wstring::~wstring((char **)&v28);
      v33[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v34);
      std::wstring::~wstring((char **)&v25);
      std::string::~string(v31);
    }
    return v17;
  }
  else
  {
    LastError = GetLastError();
    std::string::string(v31, "AppV::Client::Host::EnterpriseClientManager::InitializedLoadedOrchestration");
    v32 = 281;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v7);
    v28 = 0;
    v29 = 0;
    v30 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v28,
      L"failed to find/load Orchestration DLL export '%1%', error = %2%",
      0x3Fu);
    v9 = AppV::Log::fmt(v8, v33, &v28);
    ++*(_DWORD *)(v9 + 8);
    AppV::LogFormatter::build_substitution_list(v9, &Block);
    v10 = Block;
    if ( Block )
    {
      v24[0] = v9;
      v24[1] = "Initialize";
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(
        &v25,
        Block,
        0,
        v24);
      v10 = Block;
    }
    Block = 0;
    if ( v10 )
    {
      do
      {
        v11 = (_QWORD *)*v10;
        operator delete(v10);
        v10 = v11;
      }
      while ( v11 );
    }
    v12 = AppV::LogFormatter::operator%<unsigned long>(v9, (__int64)&LastError);
    v25 = 0;
    v26 = 0;
    v27 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v25, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v31, 8, (int)&v25, v12);
    std::wstring::~wstring((char **)&v25);
    v33[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v34);
    std::wstring::~wstring((char **)&v28);
    std::string::~string(v31);
    v13 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v13 )
      v14 = v13 + 1;
    else
      v14 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14);
    return (FileId << 52) | LastError | 0x232E00000000LL;
  }
}

```

## disassembly

```asm
0x14004d8b0  mov     [rsp-8+arg_0], rbx
0x14004d8b5  push    rbp
0x14004d8b6  push    rdi
0x14004d8b7  push    r14
0x14004d8b9  lea     rbp, [rsp-47h]
0x14004d8be  sub     rsp, 0E0h
0x14004d8c5  mov     rax, cs:__security_cookie
0x14004d8cc  xor     rax, rsp
0x14004d8cf  mov     [rbp+57h+var_18], rax
0x14004d8d3  mov     rdi, r9
0x14004d8d6  mov     rbx, r8
0x14004d8d9  mov     rcx, rdx; hModule
0x14004d8dc  lea     r14, ?INITIALIZE_ORCHESTRATION@Orchestration@Client@AppV@@3QBDB; "Initialize"
0x14004d8e3  mov     rdx, r14; lpProcName
0x14004d8e6  call    cs:__imp_GetProcAddress
0x14004d8ec  test    rax, rax
0x14004d8ef  jnz     loc_14004DA8D
0x14004d8f5  call    cs:__imp_GetLastError
0x14004d8fb  mov     [rbp+57h+var_D0], eax
0x14004d8fe  lea     rdx, aAppvClientHost_14; "AppV::Client::Host::EnterpriseClientMan"...
0x14004d905  lea     rcx, [rbp+57h+var_70]
0x14004d909  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d90e  mov     [rbp+57h+var_50], 119h
0x14004d915  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004d91a  xorps   xmm0, xmm0
0x14004d91d  movups  [rbp+57h+var_90], xmm0
0x14004d921  mov     [rbp+57h+var_80], 0
0x14004d929  mov     [rbp+57h+var_78], 0
0x14004d931  mov     r8d, 3Fh ; '?'
0x14004d937  lea     rdx, aFailedToFindLo; "failed to find/load Orchestration DLL e"...
0x14004d93e  lea     rcx, [rbp+57h+var_90]
0x14004d942  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d947  nop
0x14004d948  lea     r8, [rbp+57h+var_90]
0x14004d94c  lea     rdx, [rbp+57h+var_48]
0x14004d950  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004d955  mov     rdi, rax
0x14004d958  mov     r8d, [rax+8]
0x14004d95c  lea     ecx, [r8+1]
0x14004d960  mov     [rax+8], ecx
0x14004d963  lea     rdx, [rbp+57h+Block]
0x14004d967  mov     rcx, rax
0x14004d96a  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14004d96f  nop
0x14004d970  mov     rcx, [rbp+57h+Block]
0x14004d974  test    rcx, rcx
0x14004d977  jz      short loc_14004D998
0x14004d979  xor     r8d, r8d
0x14004d97c  mov     [rbp+57h+var_C0], rdi
0x14004d980  mov     [rbp+57h+var_B8], r14
0x14004d984  lea     r9, [rbp+57h+var_C0]
0x14004d988  mov     rdx, rcx
0x14004d98b  lea     rcx, [rbp+57h+var_B0]
0x14004d98f  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_02bb673707fabc1f1b1bff88744e93d0_@@@std@@YA?AV_lambda_02bb673707fabc1f1b1bff88744e93d0_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_)
0x14004d994  mov     rcx, [rbp+57h+Block]; Block
0x14004d998  mov     [rbp+57h+Block], 0
0x14004d9a0  test    rcx, rcx
0x14004d9a3  jz      short loc_14004D9BA
0x14004d9a5  mov     rbx, [rcx]
0x14004d9a8  mov     edx, 20h ; ' '
0x14004d9ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004d9b2  mov     rcx, rbx
0x14004d9b5  test    rbx, rbx
0x14004d9b8  jnz     short loc_14004D9A5
0x14004d9ba  lea     rdx, [rbp+57h+var_D0]
0x14004d9be  mov     rcx, rdi
0x14004d9c1  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004d9c6  mov     rbx, rax
0x14004d9c9  xorps   xmm0, xmm0
0x14004d9cc  movups  [rbp+57h+var_B0], xmm0
0x14004d9d0  mov     [rbp+57h+var_A0], 0
0x14004d9d8  mov     [rbp+57h+var_98], 0
0x14004d9e0  mov     r8d, 6
0x14004d9e6  lea     rdx, aClient; "Client"
0x14004d9ed  lea     rcx, [rbp+57h+var_B0]
0x14004d9f1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d9f6  nop
0x14004d9f7  mov     r9, rbx
0x14004d9fa  lea     r8, [rbp+57h+var_B0]
0x14004d9fe  mov     edx, 8
0x14004da03  lea     rcx, [rbp+57h+var_70]
0x14004da07  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004da0c  nop
0x14004da0d  lea     rcx, [rbp+57h+var_B0]
0x14004da11  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004da16  nop
0x14004da17  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004da1e  mov     [rbp+57h+var_48], rax
0x14004da22  lea     rcx, [rbp+57h+var_38]
0x14004da26  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004da2b  nop
0x14004da2c  lea     rcx, [rbp+57h+var_90]
0x14004da30  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004da35  nop
0x14004da36  lea     rcx, [rbp+57h+var_70]
0x14004da3a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004da3f  mov     edx, 5Ch ; '\'; Ch
0x14004da44  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004da4b  call    cs:__imp_strrchr
0x14004da51  test    rax, rax
0x14004da54  jz      short loc_14004DA5B
0x14004da56  inc     rax
0x14004da59  jmp     short loc_14004DA62
0x14004da5b  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004da62  mov     rdx, rax; char *
0x14004da65  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004da6c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004da71  shl     rax, 34h
0x14004da75  mov     ecx, [rbp+57h+var_D0]
0x14004da78  or      rcx, rax
0x14004da7b  mov     rax, 232E00000000h
0x14004da85  or      rax, rcx
0x14004da88  jmp     loc_14004DB8A
0x14004da8d  mov     rdx, rdi
0x14004da90  mov     rcx, rbx
0x14004da93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004da98  mov     rdi, rax
0x14004da9b  bt      rax, 27h ; '''
0x14004daa0  jb      loc_14004DB87
0x14004daa6  lea     rdx, aAppvClientHost_14; "AppV::Client::Host::EnterpriseClientMan"...
0x14004daad  lea     rcx, [rbp+57h+var_70]
0x14004dab1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004dab6  mov     [rbp+57h+var_50], 120h
0x14004dabd  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004dac2  xorps   xmm0, xmm0
0x14004dac5  movups  [rbp+57h+var_B0], xmm0
0x14004dac9  mov     [rbp+57h+var_A0], 0
0x14004dad1  mov     [rbp+57h+var_98], 0
0x14004dad9  mov     r8d, 32h ; '2'
0x14004dadf  lea     rdx, aOrchestrationD_1; "Orchestration DLL Initialize() failed, "...
0x14004dae6  lea     rcx, [rbp+57h+var_B0]
0x14004daea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004daef  nop
0x14004daf0  lea     r8, [rbp+57h+var_B0]
0x14004daf4  lea     rdx, [rbp+57h+var_48]
0x14004daf8  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004dafd  nop
0x14004dafe  mov     [rbp+57h+Block], rdi
0x14004db02  lea     rdx, [rbp+57h+Block]
0x14004db06  mov     rcx, rax
0x14004db09  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14004db0e  mov     rbx, rax
0x14004db11  xorps   xmm0, xmm0
0x14004db14  movups  [rbp+57h+var_90], xmm0
0x14004db18  mov     [rbp+57h+var_80], 0
0x14004db20  mov     [rbp+57h+var_78], 0
0x14004db28  mov     r8d, 6
0x14004db2e  lea     rdx, aClient; "Client"
0x14004db35  lea     rcx, [rbp+57h+var_90]
0x14004db39  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004db3e  nop
0x14004db3f  mov     r9, rbx
0x14004db42  lea     r8, [rbp+57h+var_90]
0x14004db46  mov     edx, 8
0x14004db4b  lea     rcx, [rbp+57h+var_70]
0x14004db4f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004db54  nop
0x14004db55  lea     rcx, [rbp+57h+var_90]
0x14004db59  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004db5e  nop
0x14004db5f  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004db66  mov     [rbp+57h+var_48], rax
0x14004db6a  lea     rcx, [rbp+57h+var_38]
0x14004db6e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004db73  nop
0x14004db74  lea     rcx, [rbp+57h+var_B0]
0x14004db78  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004db7d  nop
0x14004db7e  lea     rcx, [rbp+57h+var_70]
0x14004db82  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004db87  mov     rax, rdi
0x14004db8a  mov     rcx, [rbp+57h+var_18]
0x14004db8e  xor     rcx, rsp; StackCookie
0x14004db91  call    __security_check_cookie
0x14004db96  mov     rbx, [rsp+0F0h+arg_0]
0x14004db9e  add     rsp, 0E0h
0x14004dba5  pop     r14
0x14004dba7  pop     rdi
0x14004dba8  pop     rbp
0x14004dba9  retn
```
