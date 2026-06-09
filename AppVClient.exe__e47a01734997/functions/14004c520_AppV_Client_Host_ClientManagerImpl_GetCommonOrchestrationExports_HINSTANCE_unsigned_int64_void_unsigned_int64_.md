# AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports(HINSTANCE__ *,unsigned __int64 (*&)(void),unsigned __int64 (*&)(AppV::Client::ClientComponent * &),unsigned __int64 (*&)(AppV::Client::ControllerRequests * &))

- ea: `0x14004c520`
- end: `0x14004ca9d`
- name: `?GetCommonOrchestrationExports@ClientManagerImpl@Host@Client@AppV@@MEBA_KPEAUHINSTANCE__@@AEAP6A_KXZAEAP6A_KAEAPEAVClientComponent@34@@ZAEAP6A_KAEAPEAVControllerRequests@34@@Z@Z`
- size: `1405`
- prototype: `unsigned __int64(AppV::Client::Host::ClientManagerImpl *__hidden this, HINSTANCE, unsigned __int64 (**)(void), unsigned __int64 (**)(struct AppV::Client::ClientComponent **), unsigned __int64 (**)(struct AppV::Client::ControllerRequests **))`
- caller_count: `0`
- callee_count: `14`
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
- `0x14003d01c`
- `0x14004bc10`
- `0x14004c520`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14004c55f`
- `KERNEL32!GetProcAddress` at `0x14004c716`
- `KERNEL32!GetProcAddress` at `0x14004c8cc`
- `KERNEL32!GetProcAddress` at `0x14004c55f`
- `KERNEL32!GetProcAddress` at `0x14004c716`
- `KERNEL32!GetProcAddress` at `0x14004c8cc`
- `KERNEL32!GetLastError` at `0x14004c574`
- `KERNEL32!GetLastError` at `0x14004c728`
- `KERNEL32!GetLastError` at `0x14004c8de`
- `KERNEL32!GetLastError` at `0x14004c574`
- `KERNEL32!GetLastError` at `0x14004c728`
- `KERNEL32!GetLastError` at `0x14004c8de`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c6c6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c87f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ca35`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c6c6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c87f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004ca35`

## string_xrefs

- `0x14004c709`: `GetControllerComponent`
- `0x14004c6bf`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004c6d6`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004c878`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004c88f`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004ca2e`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004ca45`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004c57e`: `AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports`
- `0x14004c732`: `AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports`
- `0x14004c8e8`: `AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports`
- `0x14004c5b1`: `failed to find/load Orchestration DLL export '%1%', error = %2%`
- `0x14004c766`: `failed to find/load Orchestration DLL export '%1%', error = %2%`
- `0x14004c91c`: `failed to find/load Orchestration DLL export '%1%', error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports(
        AppV::Client::Host::ClientManagerImpl *this,
        HINSTANCE a2,
        unsigned __int64 (**a3)(void),
        unsigned __int64 (**a4)(struct AppV::Client::ClientComponent **),
        unsigned __int64 (**a5)(struct AppV::Client::ControllerRequests **))
{
  unsigned __int64 (*ProcAddress)(void); // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 FileId; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  unsigned __int64 (*v21)(struct AppV::Client::ClientComponent **); // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdi
  _QWORD *v25; // rcx
  _QWORD *v26; // rbx
  __int64 v27; // rbx
  char *v28; // rax
  const char *v29; // rax
  unsigned __int64 v30; // rax
  unsigned __int64 (*v31)(struct AppV::Client::ControllerRequests **); // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdi
  _QWORD *v35; // rcx
  _QWORD *v36; // rbx
  __int64 v37; // rbx
  char *v38; // rax
  const char *v39; // rax
  unsigned __int64 v40; // rax
  DWORD LastError; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v43; // [rsp+30h] [rbp-D0h] BYREF
  const CHAR *v44; // [rsp+38h] [rbp-C8h]
  __int128 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h]
  __int128 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h]
  int v51; // [rsp+80h] [rbp-80h]
  __int128 v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+98h] [rbp-68h]
  __int64 v54; // [rsp+A0h] [rbp-60h]
  char *v55[2]; // [rsp+A8h] [rbp-58h] BYREF
  char *v56; // [rsp+B8h] [rbp-48h] BYREF
  int v57; // [rsp+C8h] [rbp-38h]
  _QWORD v58[2]; // [rsp+D8h] [rbp-28h] BYREF
  char *v59[4]; // [rsp+E8h] [rbp-18h] BYREF

  ProcAddress = (unsigned __int64 (*)(void))GetProcAddress(a2, "Deinitialize");
  *a3 = ProcAddress;
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    std::string::string(&v48, "AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports");
    v51 = 234;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v9);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v45,
      L"failed to find/load Orchestration DLL export '%1%', error = %2%",
      0x3Fu);
    v11 = AppV::Log::fmt(v10, v55, &v45);
    ++*(_DWORD *)(v11 + 8);
    AppV::LogFormatter::build_substitution_list(v11, &Block);
    v12 = Block;
    if ( Block )
    {
      v43 = v11;
      v44 = "Deinitialize";
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(
        &v52,
        Block,
        0,
        &v43);
      v12 = Block;
    }
    Block = 0;
    if ( v12 )
    {
      do
      {
        v13 = (_QWORD *)*v12;
        operator delete(v12);
        v12 = v13;
      }
      while ( v13 );
    }
    v14 = AppV::LogFormatter::operator%<unsigned long>(v11, (__int64)&LastError);
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v52, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)&v48, 1, (int)&v52, v14);
    std::wstring::~wstring((char **)&v52);
    v55[0] = (char *)&AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v56);
    std::wstring::~wstring((char **)&v45);
    std::string::~string((char **)&v48);
    v15 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v15 )
      v16 = v15 + 1;
    else
      v16 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
    v18 = (FileId << 52) | LastError;
    v19 = 0x1D2E00000000LL;
    return v18 | v19;
  }
  v21 = (unsigned __int64 (*)(struct AppV::Client::ClientComponent **))GetProcAddress(a2, "GetControllerComponent");
  *a4 = v21;
  if ( !v21 )
  {
    LastError = GetLastError();
    std::string::string(v55, "AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports");
    v57 = 245;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v22);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v48,
      L"failed to find/load Orchestration DLL export '%1%', error = %2%",
      0x3Fu);
    v24 = AppV::Log::fmt(v23, v58, &v48);
    ++*(_DWORD *)(v24 + 8);
    AppV::LogFormatter::build_substitution_list(v24, &Block);
    v25 = Block;
    if ( Block )
    {
      v43 = v24;
      v44 = "GetControllerComponent";
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(
        &v52,
        Block,
        0,
        &v43);
      v25 = Block;
    }
    Block = 0;
    if ( v25 )
    {
      do
      {
        v26 = (_QWORD *)*v25;
        operator delete(v25);
        v25 = v26;
      }
      while ( v26 );
    }
    v27 = AppV::LogFormatter::operator%<unsigned long>(v24, (__int64)&LastError);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v45, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v55, 1, (int)&v45, v27);
    std::wstring::~wstring((char **)&v45);
    v58[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v59);
    std::wstring::~wstring((char **)&v48);
    std::string::~string(v55);
    v28 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v28 )
      v29 = v28 + 1;
    else
      v29 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v30 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v29);
    v18 = (v30 << 52) | LastError;
    v19 = 0x1E2E00000000LL;
    return v18 | v19;
  }
  v31 = (unsigned __int64 (*)(struct AppV::Client::ControllerRequests **))GetProcAddress(a2, "GetControllerRequests");
  *a5 = v31;
  if ( !v31 )
  {
    LastError = GetLastError();
    std::string::string(v55, "AppV::Client::Host::ClientManagerImpl::GetCommonOrchestrationExports");
    v57 = 256;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v32);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v45,
      L"failed to find/load Orchestration DLL export '%1%', error = %2%",
      0x3Fu);
    v34 = AppV::Log::fmt(v33, v58, &v45);
    ++*(_DWORD *)(v34 + 8);
    AppV::LogFormatter::build_substitution_list(v34, &Block);
    v35 = Block;
    if ( Block )
    {
      v43 = v34;
      v44 = "GetControllerRequests";
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(
        &v52,
        Block,
        0,
        &v43);
      v35 = Block;
    }
    Block = 0;
    if ( v35 )
    {
      do
      {
        v36 = (_QWORD *)*v35;
        operator delete(v35);
        v35 = v36;
      }
      while ( v36 );
    }
    v37 = AppV::LogFormatter::operator%<unsigned long>(v34, (__int64)&LastError);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v55, 1, (int)&v48, v37);
    std::wstring::~wstring((char **)&v48);
    v58[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v59);
    std::wstring::~wstring((char **)&v45);
    std::string::~string(v55);
    v38 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v38 )
      v39 = v38 + 1;
    else
      v39 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v40 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v39);
    v18 = (v40 << 52) | LastError;
    v19 = 0x202E00000000LL;
    return v18 | v19;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14004c520  push    rbp
0x14004c522  push    rbx
0x14004c523  push    rsi
0x14004c524  push    rdi
0x14004c525  push    r12
0x14004c527  push    r14
0x14004c529  push    r15
0x14004c52b  lea     rbp, [rsp-10h]
0x14004c530  sub     rsp, 110h
0x14004c537  mov     rax, cs:__security_cookie
0x14004c53e  xor     rax, rsp
0x14004c541  mov     [rbp+40h+var_38], rax
0x14004c545  mov     rsi, r9
0x14004c548  mov     rbx, r8
0x14004c54b  mov     rdi, rdx
0x14004c54e  mov     r14, [rbp+40h+arg_20]
0x14004c552  lea     r12, ?DEINITIALIZE_ORCHESTRATION@Orchestration@Client@AppV@@3QBDB; "Deinitialize"
0x14004c559  mov     rdx, r12; lpProcName
0x14004c55c  mov     rcx, rdi; hModule
0x14004c55f  call    cs:__imp_GetProcAddress
0x14004c565  mov     [rbx], rax
0x14004c568  xor     r15d, r15d
0x14004c56b  test    rax, rax
0x14004c56e  jnz     loc_14004C709
0x14004c574  call    cs:__imp_GetLastError
0x14004c57a  mov     [rsp+140h+var_120], eax
0x14004c57e  lea     rdx, aAppvClientHost_10; "AppV::Client::Host::ClientManagerImpl::"...
0x14004c585  lea     rcx, [rsp+140h+var_E0]
0x14004c58a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004c58f  mov     [rbp+40h+var_C0], 0EAh
0x14004c596  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004c59b  xorps   xmm0, xmm0
0x14004c59e  movups  [rsp+140h+var_100], xmm0
0x14004c5a3  mov     [rsp+140h+var_F0], r15
0x14004c5a8  mov     [rsp+140h+var_E8], r15
0x14004c5ad  lea     r8d, [r15+3Fh]
0x14004c5b1  lea     rdx, aFailedToFindLo; "failed to find/load Orchestration DLL e"...
0x14004c5b8  lea     rcx, [rsp+140h+var_100]
0x14004c5bd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c5c2  nop
0x14004c5c3  lea     r8, [rsp+140h+var_100]
0x14004c5c8  lea     rdx, [rbp+40h+var_98]
0x14004c5cc  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004c5d1  mov     rdi, rax
0x14004c5d4  mov     r8d, [rax+8]
0x14004c5d8  lea     ecx, [r8+1]
0x14004c5dc  mov     [rax+8], ecx
0x14004c5df  lea     rdx, [rsp+140h+Block]
0x14004c5e4  mov     rcx, rax
0x14004c5e7  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14004c5ec  nop
0x14004c5ed  mov     rcx, [rsp+140h+Block]
0x14004c5f2  test    rcx, rcx
0x14004c5f5  jz      short loc_14004C61A
0x14004c5f7  mov     r8d, r15d
0x14004c5fa  mov     [rsp+140h+var_110], rdi
0x14004c5ff  mov     [rsp+140h+var_108], r12
0x14004c604  lea     r9, [rsp+140h+var_110]
0x14004c609  mov     rdx, rcx
0x14004c60c  lea     rcx, [rbp+40h+var_B8]
0x14004c610  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_02bb673707fabc1f1b1bff88744e93d0_@@@std@@YA?AV_lambda_02bb673707fabc1f1b1bff88744e93d0_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_)
0x14004c615  mov     rcx, [rsp+140h+Block]; Block
0x14004c61a  mov     [rsp+140h+Block], r15
0x14004c61f  test    rcx, rcx
0x14004c622  jz      short loc_14004C639
0x14004c624  mov     rbx, [rcx]
0x14004c627  mov     edx, 20h ; ' '
0x14004c62c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004c631  mov     rcx, rbx
0x14004c634  test    rbx, rbx
0x14004c637  jnz     short loc_14004C624
0x14004c639  lea     rdx, [rsp+140h+var_120]
0x14004c63e  mov     rcx, rdi
0x14004c641  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004c646  mov     rbx, rax
0x14004c649  xorps   xmm0, xmm0
0x14004c64c  movups  [rbp+40h+var_B8], xmm0
0x14004c650  mov     [rbp+40h+var_A8], r15
0x14004c654  mov     [rbp+40h+var_A0], r15
0x14004c658  mov     r8d, 6
0x14004c65e  lea     rdx, aClient; "Client"
0x14004c665  lea     rcx, [rbp+40h+var_B8]
0x14004c669  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c66e  nop
0x14004c66f  mov     r9, rbx
0x14004c672  lea     r8, [rbp+40h+var_B8]
0x14004c676  mov     edx, 1
0x14004c67b  lea     rcx, [rsp+140h+var_E0]
0x14004c680  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004c685  nop
0x14004c686  lea     rcx, [rbp+40h+var_B8]
0x14004c68a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c68f  nop
0x14004c690  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004c697  mov     [rbp+40h+var_98], rax
0x14004c69b  lea     rcx, [rbp+40h+var_88]
0x14004c69f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c6a4  nop
0x14004c6a5  lea     rcx, [rsp+140h+var_100]
0x14004c6aa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c6af  nop
0x14004c6b0  lea     rcx, [rsp+140h+var_E0]
0x14004c6b5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004c6ba  mov     edx, 5Ch ; '\'; Ch
0x14004c6bf  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c6c6  call    cs:__imp_strrchr
0x14004c6cc  test    rax, rax
0x14004c6cf  jz      short loc_14004C6D6
0x14004c6d1  inc     rax
0x14004c6d4  jmp     short loc_14004C6DD
0x14004c6d6  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c6dd  mov     rdx, rax; char *
0x14004c6e0  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004c6e7  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004c6ec  shl     rax, 34h
0x14004c6f0  mov     ecx, [rsp+140h+var_120]
0x14004c6f4  or      rcx, rax
0x14004c6f7  mov     rax, 1D2E00000000h
0x14004c701  or      rax, rcx
0x14004c704  jmp     loc_14004CA7F
0x14004c709  lea     rbx, ?GET_CONTROLLER_COMPONENT@Orchestration@Client@AppV@@3QBDB; "GetControllerComponent"
0x14004c710  mov     rdx, rbx; lpProcName
0x14004c713  mov     rcx, rdi; hModule
0x14004c716  call    cs:__imp_GetProcAddress
0x14004c71c  mov     [rsi], rax
0x14004c71f  test    rax, rax
0x14004c722  jnz     loc_14004C8BF
0x14004c728  call    cs:__imp_GetLastError
0x14004c72e  mov     [rsp+140h+var_120], eax
0x14004c732  lea     rdx, aAppvClientHost_10; "AppV::Client::Host::ClientManagerImpl::"...
0x14004c739  lea     rcx, [rbp+40h+var_98]
0x14004c73d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004c742  mov     [rbp+40h+var_78], 0F5h
0x14004c749  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004c74e  xorps   xmm0, xmm0
0x14004c751  movups  [rsp+140h+var_E0], xmm0
0x14004c756  mov     [rsp+140h+var_D0], r15
0x14004c75b  mov     [rsp+140h+var_C8], r15
0x14004c760  mov     r8d, 3Fh ; '?'
0x14004c766  lea     rdx, aFailedToFindLo; "failed to find/load Orchestration DLL e"...
0x14004c76d  lea     rcx, [rsp+140h+var_E0]
0x14004c772  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c777  nop
0x14004c778  lea     r8, [rsp+140h+var_E0]
0x14004c77d  lea     rdx, [rbp+40h+var_68]
0x14004c781  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004c786  mov     rdi, rax
0x14004c789  mov     r8d, [rax+8]
0x14004c78d  lea     ecx, [r8+1]
0x14004c791  mov     [rax+8], ecx
0x14004c794  lea     rdx, [rsp+140h+Block]
0x14004c799  mov     rcx, rax
0x14004c79c  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14004c7a1  nop
0x14004c7a2  mov     rcx, [rsp+140h+Block]
0x14004c7a7  test    rcx, rcx
0x14004c7aa  jz      short loc_14004C7CF
0x14004c7ac  mov     r8, r15
0x14004c7af  mov     [rsp+140h+var_110], rdi
0x14004c7b4  mov     [rsp+140h+var_108], rbx
0x14004c7b9  lea     r9, [rsp+140h+var_110]
0x14004c7be  mov     rdx, rcx
0x14004c7c1  lea     rcx, [rbp+40h+var_B8]
0x14004c7c5  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_02bb673707fabc1f1b1bff88744e93d0_@@@std@@YA?AV_lambda_02bb673707fabc1f1b1bff88744e93d0_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_)
0x14004c7ca  mov     rcx, [rsp+140h+Block]; Block
0x14004c7cf  mov     [rsp+140h+Block], r15
0x14004c7d4  test    rcx, rcx
0x14004c7d7  jz      short loc_14004C7EE
0x14004c7d9  mov     rbx, [rcx]
0x14004c7dc  mov     edx, 20h ; ' '
0x14004c7e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004c7e6  mov     rcx, rbx
0x14004c7e9  test    rbx, rbx
0x14004c7ec  jnz     short loc_14004C7D9
0x14004c7ee  lea     rdx, [rsp+140h+var_120]
0x14004c7f3  mov     rcx, rdi
0x14004c7f6  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004c7fb  mov     rbx, rax
0x14004c7fe  xorps   xmm0, xmm0
0x14004c801  movups  [rsp+140h+var_100], xmm0
0x14004c806  mov     [rsp+140h+var_F0], r15
0x14004c80b  mov     [rsp+140h+var_E8], r15
0x14004c810  mov     r8d, 6
0x14004c816  lea     rdx, aClient; "Client"
0x14004c81d  lea     rcx, [rsp+140h+var_100]
0x14004c822  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c827  nop
0x14004c828  mov     r9, rbx
0x14004c82b  lea     r8, [rsp+140h+var_100]
0x14004c830  mov     edx, 1
0x14004c835  lea     rcx, [rbp+40h+var_98]
0x14004c839  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004c83e  nop
0x14004c83f  lea     rcx, [rsp+140h+var_100]
0x14004c844  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c849  nop
0x14004c84a  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004c851  mov     [rbp+40h+var_68], rax
0x14004c855  lea     rcx, [rbp+40h+var_58]
0x14004c859  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c85e  nop
0x14004c85f  lea     rcx, [rsp+140h+var_E0]
0x14004c864  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c869  nop
0x14004c86a  lea     rcx, [rbp+40h+var_98]
0x14004c86e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004c873  mov     edx, 5Ch ; '\'; Ch
0x14004c878  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c87f  call    cs:__imp_strrchr
0x14004c885  test    rax, rax
0x14004c888  jz      short loc_14004C88F
0x14004c88a  inc     rax
0x14004c88d  jmp     short loc_14004C896
0x14004c88f  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c896  mov     rdx, rax; char *
0x14004c899  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004c8a0  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004c8a5  shl     rax, 34h
0x14004c8a9  mov     ecx, [rsp+140h+var_120]
0x14004c8ad  or      rcx, rax
0x14004c8b0  mov     rax, 1E2E00000000h
0x14004c8ba  jmp     loc_14004C701
0x14004c8bf  lea     rbx, ?GET_CONTROLLER_REQUESTS@Orchestration@Client@AppV@@3QBDB; "GetControllerRequests"
0x14004c8c6  mov     rdx, rbx; lpProcName
0x14004c8c9  mov     rcx, rdi; hModule
0x14004c8cc  call    cs:__imp_GetProcAddress
0x14004c8d2  mov     [r14], rax
0x14004c8d5  test    rax, rax
0x14004c8d8  jnz     loc_14004CA75
0x14004c8de  call    cs:__imp_GetLastError
0x14004c8e4  mov     [rsp+140h+var_120], eax
0x14004c8e8  lea     rdx, aAppvClientHost_10; "AppV::Client::Host::ClientManagerImpl::"...
0x14004c8ef  lea     rcx, [rbp+40h+var_98]
0x14004c8f3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004c8f8  mov     [rbp+40h+var_78], 100h
0x14004c8ff  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004c904  xorps   xmm0, xmm0
0x14004c907  movups  [rsp+140h+var_100], xmm0
0x14004c90c  mov     [rsp+140h+var_F0], r15
0x14004c911  mov     [rsp+140h+var_E8], r15
0x14004c916  mov     r8d, 3Fh ; '?'
0x14004c91c  lea     rdx, aFailedToFindLo; "failed to find/load Orchestration DLL e"...
0x14004c923  lea     rcx, [rsp+140h+var_100]
0x14004c928  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c92d  nop
0x14004c92e  lea     r8, [rsp+140h+var_100]
0x14004c933  lea     rdx, [rbp+40h+var_68]
0x14004c937  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004c93c  mov     rdi, rax
0x14004c93f  mov     r8d, [rax+8]
0x14004c943  lea     ecx, [r8+1]
0x14004c947  mov     [rax+8], ecx
0x14004c94a  lea     rdx, [rsp+140h+Block]
0x14004c94f  mov     rcx, rax
0x14004c952  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14004c957  nop
0x14004c958  mov     rcx, [rsp+140h+Block]
0x14004c95d  test    rcx, rcx
0x14004c960  jz      short loc_14004C985
0x14004c962  mov     r8, r15
0x14004c965  mov     [rsp+140h+var_110], rdi
0x14004c96a  mov     [rsp+140h+var_108], rbx
0x14004c96f  lea     r9, [rsp+140h+var_110]
0x14004c974  mov     rdx, rcx
0x14004c977  lea     rcx, [rbp+40h+var_B8]
0x14004c97b  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_02bb673707fabc1f1b1bff88744e93d0_@@@std@@YA?AV_lambda_02bb673707fabc1f1b1bff88744e93d0_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_02bb673707fabc1f1b1bff88744e93d0_)
0x14004c980  mov     rcx, [rsp+140h+Block]; Block
0x14004c985  mov     [rsp+140h+Block], r15
0x14004c98a  test    rcx, rcx
0x14004c98d  jz      short loc_14004C9A4
0x14004c98f  mov     rbx, [rcx]
0x14004c992  mov     edx, 20h ; ' '
0x14004c997  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14004c99c  mov     rcx, rbx
0x14004c99f  test    rbx, rbx
0x14004c9a2  jnz     short loc_14004C98F
0x14004c9a4  lea     rdx, [rsp+140h+var_120]
0x14004c9a9  mov     rcx, rdi
0x14004c9ac  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004c9b1  mov     rbx, rax
0x14004c9b4  xorps   xmm0, xmm0
0x14004c9b7  movups  [rsp+140h+var_E0], xmm0
0x14004c9bc  mov     [rsp+140h+var_D0], r15
0x14004c9c1  mov     [rsp+140h+var_C8], r15
0x14004c9c6  mov     r8d, 6
0x14004c9cc  lea     rdx, aClient; "Client"
0x14004c9d3  lea     rcx, [rsp+140h+var_E0]
0x14004c9d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c9dd  nop
0x14004c9de  mov     r9, rbx
0x14004c9e1  lea     r8, [rsp+140h+var_E0]
0x14004c9e6  mov     edx, 1
0x14004c9eb  lea     rcx, [rbp+40h+var_98]
0x14004c9ef  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004c9f4  nop
0x14004c9f5  lea     rcx, [rsp+140h+var_E0]
0x14004c9fa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c9ff  nop
0x14004ca00  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ca07  mov     [rbp+40h+var_68], rax
  ... truncated ...
```
