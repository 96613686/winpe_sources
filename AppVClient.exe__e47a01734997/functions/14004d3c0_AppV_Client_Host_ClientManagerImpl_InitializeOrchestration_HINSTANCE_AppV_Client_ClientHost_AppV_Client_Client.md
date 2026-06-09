# AppV::Client::Host::ClientManagerImpl::InitializeOrchestration(HINSTANCE__ *,AppV::Client::ClientHost &,AppV::Client::ClientEventSink &)

- ea: `0x14004d3c0`
- end: `0x14004d89b`
- name: `?InitializeOrchestration@ClientManagerImpl@Host@Client@AppV@@MEAA_KPEAUHINSTANCE__@@AEAVClientHost@34@AEAVClientEventSink@34@@Z`
- size: `1243`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::ClientManagerImpl *__hidden this, HINSTANCE, struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x1400094bc`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14004d3c0`
- `0x14004dbf0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14004d43a`
- `KERNEL32!LoadLibraryW` at `0x14004d43a`
- `KERNEL32!FreeLibrary` at `0x14004d5a3`
- `KERNEL32!FreeLibrary` at `0x14004d80a`
- `KERNEL32!FreeLibrary` at `0x14004d867`
- `KERNEL32!FreeLibrary` at `0x14004d5a3`
- `KERNEL32!FreeLibrary` at `0x14004d80a`
- `KERNEL32!FreeLibrary` at `0x14004d867`
- `KERNEL32!GetLastError` at `0x14004d451`
- `KERNEL32!GetLastError` at `0x14004d451`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d4c3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d4c3`

## string_xrefs

- `0x14004d4bc`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004d4d3`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004d756`: `Orchestration DLL GetControllerRequests() failed, error = %1%`
- `0x14004d653`: `Orchestration DLL GetControllerComponent() failed, error = %1%`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::InitializeOrchestration(
        AppV::Client::Host::ClientManagerImpl *this,
        HINSTANCE a2,
        struct AppV::Client::ClientHost *a3,
        struct AppV::Client::ClientEventSink *a4)
{
  unsigned __int64 v7; // rbx
  const WCHAR *v8; // rcx
  HMODULE LibraryW; // rbx
  DWORD LastError; // eax
  __int64 v11; // rbx
  LPCWSTR *v12; // r8
  LPCWSTR *v13; // r8
  char *v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rsi
  __int64 v18; // r9
  LPCWSTR *v19; // r8
  LPCWSTR *v20; // r8
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdi
  HMODULE *v28; // rsi
  HMODULE v29; // rax
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  _QWORD *v32; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall *v35)(__int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v36)(__int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE v39; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h]
  unsigned __int64 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  __int128 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  _BYTE v49[32]; // [rsp+D0h] [rbp-30h] BYREF
  int v50; // [rsp+F0h] [rbp-10h]
  _QWORD v51[2]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v52[32]; // [rsp+108h] [rbp+8h] BYREF

  *(_OWORD *)lpLibFileName = 0;
  v41 = 0;
  v42 = 7;
  LOWORD(lpLibFileName[0]) = 0;
  v7 = (*(__int64 (__fastcall **)(AppV::Client::Host::ClientManagerImpl *, HINSTANCE, LPCWSTR *))(*(_QWORD *)this + 56LL))(
         this,
         a2,
         lpLibFileName);
  if ( (v7 & 0x8000000000LL) == 0 )
    goto LABEL_42;
  v8 = (const WCHAR *)lpLibFileName;
  if ( v42 > 7 )
    v8 = lpLibFileName[0];
  LibraryW = LoadLibraryW(v8);
  v39 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( (Microsoft_AppV_ClientEnableBits & 4) != 0 )
    {
      v12 = lpLibFileName;
      if ( v42 > 7 )
        v12 = (LPCWSTR *)lpLibFileName[0];
      McTemplateU0zq_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        APPV_CLIENT_Evt_CmpLoadFailed,
        v12,
        LastError);
    }
    if ( (Microsoft_AppV_ClientISVEnableBits & 4) != 0 )
    {
      v13 = lpLibFileName;
      if ( v42 > 7 )
        v13 = (LPCWSTR *)lpLibFileName[0];
      McTemplateU0zq_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENTISV_Context,
        APPV_CLIENTISV_Evt_CmpLoadFailed,
        v13,
        (unsigned int)v11);
    }
    v14 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v14 )
      v15 = v14 + 1;
    else
      v15 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v15) << 52)
       | v11
       | 0x102E00000000LL;
    goto LABEL_42;
  }
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v16 = (*(__int64 (__fastcall **)(AppV::Client::Host::ClientManagerImpl *, HMODULE, __int64 *, __int64 (__fastcall **)(__int64 *), __int64 (__fastcall **)(__int64 *)))(*(_QWORD *)this + 64LL))(
          this,
          LibraryW,
          &v34,
          &v35,
          &v36);
  v17 = v16;
  if ( (v16 & 0x8000000000LL) == 0 )
  {
    v18 = (unsigned int)v16;
    if ( (Microsoft_AppV_ClientEnableBits & 4) != 0 )
    {
      v19 = lpLibFileName;
      if ( v42 > 7 )
        v19 = (LPCWSTR *)lpLibFileName[0];
      McTemplateU0zq_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        APPV_CLIENT_Evt_CmpLoadFailed,
        v19,
        (unsigned int)v16);
      v18 = (unsigned int)v17;
    }
    if ( (Microsoft_AppV_ClientISVEnableBits & 4) != 0 )
    {
      v20 = lpLibFileName;
      if ( v42 > 7 )
        v20 = (LPCWSTR *)lpLibFileName[0];
      McTemplateU0zq_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENTISV_Context,
        APPV_CLIENTISV_Evt_CmpLoadFailed,
        v20,
        v18);
    }
    goto LABEL_26;
  }
  v17 = (*(__int64 (__fastcall **)(AppV::Client::Host::ClientManagerImpl *, HMODULE, struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *))(*(_QWORD *)this + 72LL))(
          this,
          LibraryW,
          a3,
          a4);
  if ( (v17 & 0x8000000000LL) == 0 )
  {
LABEL_26:
    FreeLibrary(LibraryW);
    v7 = v17;
    goto LABEL_42;
  }
  v21 = operator new(0x10u);
  v33 = v21;
  *v21 = &appv::utility::scope_guard_func_impl<unsigned __int64 (*)(void)>::`vftable';
  v21[1] = v34;
  v32 = v21;
  v37 = 0;
  v17 = v35(&v37);
  if ( (v17 & 0x8000000000LL) == 0 )
  {
    std::string::string(v49, "AppV::Client::Host::ClientManagerImpl::InitializeOrchestration");
    v50 = 157;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v46 = 0;
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v46,
      L"Orchestration DLL GetControllerComponent() failed, error = %1%",
      62);
    v23 = AppV::Log::fmt(v22, v51, &v46);
    v33 = (_QWORD *)v17;
    v24 = AppV::LogFormatter::operator%(v23, &v33);
    v43 = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v43, L"Client", 6);
    AppV::DecoratedLog::operator()(v49, 1, &v43, v24);
    std::wstring::~wstring(&v43);
    v51[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v46);
LABEL_30:
    std::string::~string(v49);
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v32);
    goto LABEL_26;
  }
  v38 = 0;
  v17 = v36(&v38);
  if ( (v17 & 0x8000000000LL) == 0 )
  {
    std::string::string(v49, "AppV::Client::Host::ClientManagerImpl::InitializeOrchestration");
    v50 = 164;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v43 = 0;
    v44 = 0;
    v45 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v43,
      L"Orchestration DLL GetControllerRequests() failed, error = %1%",
      61);
    v26 = AppV::Log::fmt(v25, v51, &v43);
    v33 = (_QWORD *)v17;
    v27 = AppV::LogFormatter::operator%(v26, &v33);
    v46 = 0;
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v46, L"Client", 6);
    AppV::DecoratedLog::operator()(v49, 1, &v46, v27);
    std::wstring::~wstring(&v46);
    v51[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v43);
    goto LABEL_30;
  }
  v28 = (HMODULE *)((char *)this + 72);
  if ( (HMODULE *)((char *)this + 72) != &v39 )
  {
    if ( *v28 )
      FreeLibrary(*v28);
    v29 = LibraryW;
    LibraryW = 0;
    *v28 = v29;
  }
  *((_QWORD *)this + 10) = v34;
  *((_QWORD *)this + 11) = v37;
  *((_QWORD *)this + 12) = v38;
  v30 = (void (__fastcall ***)(_QWORD, __int64))v32;
  v32 = 0;
  if ( v30 )
    (**v30)(v30, 1);
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v32);
  if ( LibraryW )
    FreeLibrary(LibraryW);
  v7 = 0x8000000000LL;
LABEL_42:
  std::wstring::~wstring(lpLibFileName);
  return v7;
}

```

## disassembly

```asm
0x14004d3c0  push    rbp
0x14004d3c2  push    rbx
0x14004d3c3  push    rsi
0x14004d3c4  push    rdi
0x14004d3c5  push    r12
0x14004d3c7  push    r14
0x14004d3c9  push    r15
0x14004d3cb  lea     rbp, [rsp-30h]
0x14004d3d0  sub     rsp, 130h
0x14004d3d7  mov     rax, cs:__security_cookie
0x14004d3de  xor     rax, rsp
0x14004d3e1  mov     [rbp+60h+var_38], rax
0x14004d3e5  mov     r15, r9
0x14004d3e8  mov     r14, r8
0x14004d3eb  mov     rdi, rcx
0x14004d3ee  xorps   xmm0, xmm0
0x14004d3f1  movups  xmmword ptr [rsp+160h+lpLibFileName], xmm0
0x14004d3f6  xor     r12d, r12d
0x14004d3f9  mov     [rbp+60h+var_E0], r12
0x14004d3fd  mov     [rbp+60h+var_D8], 7
0x14004d405  mov     word ptr [rsp+160h+lpLibFileName], r12w
0x14004d40b  mov     rax, [rcx]
0x14004d40e  lea     r8, [rsp+160h+lpLibFileName]
0x14004d413  mov     rax, [rax+38h]
0x14004d417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d41c  mov     rbx, rax
0x14004d41f  bt      rax, 27h ; '''
0x14004d424  jnb     loc_14004D870
0x14004d42a  lea     rcx, [rsp+160h+lpLibFileName]
0x14004d42f  cmp     [rbp+60h+var_D8], 7
0x14004d434  cmova   rcx, [rsp+160h+lpLibFileName]; lpLibFileName
0x14004d43a  call    cs:__imp_LoadLibraryW
0x14004d440  mov     rbx, rax
0x14004d443  mov     [rsp+160h+var_F8], rax
0x14004d448  test    rax, rax
0x14004d44b  jnz     loc_14004D502
0x14004d451  call    cs:__imp_GetLastError
0x14004d457  mov     ebx, eax
0x14004d459  test    cs:Microsoft_AppV_ClientEnableBits, 4
0x14004d460  jz      short loc_14004D488
0x14004d462  lea     r8, [rsp+160h+lpLibFileName]
0x14004d467  cmp     [rbp+60h+var_D8], 7
0x14004d46c  cmova   r8, [rsp+160h+lpLibFileName]
0x14004d472  mov     r9d, ebx
0x14004d475  lea     rdx, APPV_CLIENT_Evt_CmpLoadFailed
0x14004d47c  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14004d483  call    McTemplateU0zq_EventWriteTransfer
0x14004d488  test    cs:Microsoft_AppV_ClientISVEnableBits, 4
0x14004d48f  jz      short loc_14004D4B7
0x14004d491  lea     r8, [rsp+160h+lpLibFileName]
0x14004d496  cmp     [rbp+60h+var_D8], 7
0x14004d49b  cmova   r8, [rsp+160h+lpLibFileName]
0x14004d4a1  mov     r9d, ebx
0x14004d4a4  lea     rdx, APPV_CLIENTISV_Evt_CmpLoadFailed
0x14004d4ab  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENTISV_Context
0x14004d4b2  call    McTemplateU0zq_EventWriteTransfer
0x14004d4b7  mov     edx, 5Ch ; '\'; Ch
0x14004d4bc  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d4c3  call    cs:__imp_strrchr
0x14004d4c9  test    rax, rax
0x14004d4cc  jz      short loc_14004D4D3
0x14004d4ce  inc     rax
0x14004d4d1  jmp     short loc_14004D4DA
0x14004d4d3  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d4da  mov     rdx, rax; char *
0x14004d4dd  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004d4e4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004d4e9  shl     rax, 34h
0x14004d4ed  or      rbx, rax
0x14004d4f0  mov     rcx, 102E00000000h
0x14004d4fa  or      rbx, rcx
0x14004d4fd  jmp     loc_14004D870
0x14004d502  mov     [rsp+160h+var_120], r12
0x14004d507  mov     [rsp+160h+var_118], r12
0x14004d50c  mov     [rsp+160h+var_110], r12
0x14004d511  mov     rax, [rdi]
0x14004d514  lea     rcx, [rsp+160h+var_110]
0x14004d519  mov     [rsp+160h+var_140], rcx
0x14004d51e  lea     r9, [rsp+160h+var_118]
0x14004d523  lea     r8, [rsp+160h+var_120]
0x14004d528  mov     rdx, rbx
0x14004d52b  mov     rcx, rdi
0x14004d52e  mov     rax, [rax+40h]
0x14004d532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d537  mov     rsi, rax
0x14004d53a  bt      rax, 27h ; '''
0x14004d53f  jb      short loc_14004D5B1
0x14004d541  mov     r9d, esi
0x14004d544  test    cs:Microsoft_AppV_ClientEnableBits, 4
0x14004d54b  jz      short loc_14004D573
0x14004d54d  lea     r8, [rsp+160h+lpLibFileName]
0x14004d552  cmp     [rbp+60h+var_D8], 7
0x14004d557  cmova   r8, [rsp+160h+lpLibFileName]
0x14004d55d  lea     rdx, APPV_CLIENT_Evt_CmpLoadFailed
0x14004d564  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14004d56b  call    McTemplateU0zq_EventWriteTransfer
0x14004d570  mov     r9d, esi
0x14004d573  test    cs:Microsoft_AppV_ClientISVEnableBits, 4
0x14004d57a  jz      short loc_14004D5A0
0x14004d57c  lea     r8, [rsp+160h+lpLibFileName]
0x14004d581  cmp     [rbp+60h+var_D8], 7
0x14004d586  cmova   r8, [rsp+160h+lpLibFileName]
0x14004d58c  lea     rdx, APPV_CLIENTISV_Evt_CmpLoadFailed
0x14004d593  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENTISV_Context
0x14004d59a  call    McTemplateU0zq_EventWriteTransfer
0x14004d59f  nop
0x14004d5a0  mov     rcx, rbx; hLibModule
0x14004d5a3  call    cs:__imp_FreeLibrary
0x14004d5a9  mov     rbx, rsi
0x14004d5ac  jmp     loc_14004D870
0x14004d5b1  mov     rax, [rdi]
0x14004d5b4  mov     r9, r15
0x14004d5b7  mov     r8, r14
0x14004d5ba  mov     rdx, rbx
0x14004d5bd  mov     rcx, rdi
0x14004d5c0  mov     rax, [rax+48h]
0x14004d5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d5c9  mov     rsi, rax
0x14004d5cc  mov     r14, 8000000000h
0x14004d5d6  test    r14, rax
0x14004d5d9  jz      short loc_14004D5A0
0x14004d5db  mov     ecx, 10h; Size
0x14004d5e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004d5e5  mov     [rsp+160h+var_128], rax
0x14004d5ea  lea     rcx, ??_7?$scope_guard_func_impl@P6A_KXZ@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<unsigned __int64 (*)(void)>::`vftable'
0x14004d5f1  mov     [rax], rcx
0x14004d5f4  mov     rcx, [rsp+160h+var_120]
0x14004d5f9  mov     [rax+8], rcx
0x14004d5fd  mov     [rsp+160h+var_130], rax
0x14004d602  mov     [rsp+160h+var_108], r12
0x14004d607  lea     rcx, [rsp+160h+var_108]
0x14004d60c  mov     rax, [rsp+160h+var_118]
0x14004d611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d616  mov     rsi, rax
0x14004d619  test    r14, rax
0x14004d61c  jnz     loc_14004D705
0x14004d622  lea     rdx, aAppvClientHost_17; "AppV::Client::Host::ClientManagerImpl::"...
0x14004d629  lea     rcx, [rbp+60h+var_90]
0x14004d62d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d632  mov     [rbp+60h+var_70], 9Dh
0x14004d639  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004d63e  xorps   xmm0, xmm0
0x14004d641  movups  [rbp+60h+var_B0], xmm0
0x14004d645  mov     [rbp+60h+var_A0], r12
0x14004d649  mov     [rbp+60h+var_98], r12
0x14004d64d  mov     r8d, 3Eh ; '>'
0x14004d653  lea     rdx, aOrchestrationD; "Orchestration DLL GetControllerComponen"...
0x14004d65a  lea     rcx, [rbp+60h+var_B0]
0x14004d65e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d663  nop
0x14004d664  lea     r8, [rbp+60h+var_B0]
0x14004d668  lea     rdx, [rbp+60h+var_68]
0x14004d66c  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004d671  nop
0x14004d672  mov     [rsp+160h+var_128], rsi
0x14004d677  lea     rdx, [rsp+160h+var_128]
0x14004d67c  mov     rcx, rax
0x14004d67f  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14004d684  mov     rdi, rax
0x14004d687  xorps   xmm0, xmm0
0x14004d68a  movups  [rbp+60h+var_D0], xmm0
0x14004d68e  mov     [rbp+60h+var_C0], r12
0x14004d692  mov     [rbp+60h+var_B8], r12
0x14004d696  mov     r8d, 6
0x14004d69c  lea     rdx, aClient; "Client"
0x14004d6a3  lea     rcx, [rbp+60h+var_D0]
0x14004d6a7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d6ac  nop
0x14004d6ad  mov     r9, rdi
0x14004d6b0  lea     r8, [rbp+60h+var_D0]
0x14004d6b4  mov     edx, 1
0x14004d6b9  lea     rcx, [rbp+60h+var_90]
0x14004d6bd  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004d6c2  nop
0x14004d6c3  lea     rcx, [rbp+60h+var_D0]
0x14004d6c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d6cc  nop
0x14004d6cd  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004d6d4  mov     [rbp+60h+var_68], rax
0x14004d6d8  lea     rcx, [rbp+60h+var_58]
0x14004d6dc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d6e1  nop
0x14004d6e2  lea     rcx, [rbp+60h+var_B0]
0x14004d6e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d6eb  nop
0x14004d6ec  lea     rcx, [rbp+60h+var_90]
0x14004d6f0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004d6f5  nop
0x14004d6f6  lea     rcx, [rsp+160h+var_130]; this
0x14004d6fb  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14004d700  jmp     loc_14004D5A0
0x14004d705  mov     [rsp+160h+var_100], r12
0x14004d70a  lea     rcx, [rsp+160h+var_100]
0x14004d70f  mov     rax, [rsp+160h+var_110]
0x14004d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d719  mov     rsi, rax
0x14004d71c  test    r14, rax
0x14004d71f  jnz     loc_14004D7F4
0x14004d725  lea     rdx, aAppvClientHost_17; "AppV::Client::Host::ClientManagerImpl::"...
0x14004d72c  lea     rcx, [rbp+60h+var_90]
0x14004d730  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d735  mov     [rbp+60h+var_70], 0A4h
0x14004d73c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004d741  xorps   xmm0, xmm0
0x14004d744  movups  [rbp+60h+var_D0], xmm0
0x14004d748  mov     [rbp+60h+var_C0], r12
0x14004d74c  mov     [rbp+60h+var_B8], r12
0x14004d750  mov     r8d, 3Dh ; '='
0x14004d756  lea     rdx, aOrchestrationD_2; "Orchestration DLL GetControllerRequests"...
0x14004d75d  lea     rcx, [rbp+60h+var_D0]
0x14004d761  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d766  nop
0x14004d767  lea     r8, [rbp+60h+var_D0]
0x14004d76b  lea     rdx, [rbp+60h+var_68]
0x14004d76f  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004d774  nop
0x14004d775  mov     [rsp+160h+var_128], rsi
0x14004d77a  lea     rdx, [rsp+160h+var_128]
0x14004d77f  mov     rcx, rax
0x14004d782  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14004d787  mov     rdi, rax
0x14004d78a  xorps   xmm0, xmm0
0x14004d78d  movups  [rbp+60h+var_B0], xmm0
0x14004d791  mov     [rbp+60h+var_A0], r12
0x14004d795  mov     [rbp+60h+var_98], r12
0x14004d799  mov     r8d, 6
0x14004d79f  lea     rdx, aClient; "Client"
0x14004d7a6  lea     rcx, [rbp+60h+var_B0]
0x14004d7aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d7af  nop
0x14004d7b0  mov     r9, rdi
0x14004d7b3  lea     r8, [rbp+60h+var_B0]
0x14004d7b7  mov     edx, 1
0x14004d7bc  lea     rcx, [rbp+60h+var_90]
0x14004d7c0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004d7c5  nop
0x14004d7c6  lea     rcx, [rbp+60h+var_B0]
0x14004d7ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d7cf  nop
0x14004d7d0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004d7d7  mov     [rbp+60h+var_68], rax
0x14004d7db  lea     rcx, [rbp+60h+var_58]
0x14004d7df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d7e4  nop
0x14004d7e5  lea     rcx, [rbp+60h+var_D0]
0x14004d7e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d7ee  nop
0x14004d7ef  jmp     loc_14004D6EC
0x14004d7f4  lea     rsi, [rdi+48h]
0x14004d7f8  lea     rax, [rsp+160h+var_F8]
0x14004d7fd  cmp     rsi, rax
0x14004d800  jz      short loc_14004D819
0x14004d802  mov     rcx, [rsi]; hLibModule
0x14004d805  test    rcx, rcx
0x14004d808  jz      short loc_14004D810
0x14004d80a  call    cs:__imp_FreeLibrary
0x14004d810  mov     rax, rbx
0x14004d813  mov     rbx, r12
0x14004d816  mov     [rsi], rax
0x14004d819  mov     rax, [rsp+160h+var_120]
0x14004d81e  mov     [rdi+50h], rax
0x14004d822  mov     rax, [rsp+160h+var_108]
0x14004d827  mov     [rdi+58h], rax
0x14004d82b  mov     rax, [rsp+160h+var_100]
0x14004d830  mov     [rdi+60h], rax
0x14004d834  mov     rcx, [rsp+160h+var_130]
0x14004d839  mov     [rsp+160h+var_130], r12
0x14004d83e  test    rcx, rcx
0x14004d841  jz      short loc_14004D854
0x14004d843  mov     rax, [rcx]
0x14004d846  mov     edx, 1
0x14004d84b  mov     rax, [rax]
0x14004d84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d853  nop
0x14004d854  lea     rcx, [rsp+160h+var_130]; this
0x14004d859  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14004d85e  nop
0x14004d85f  test    rbx, rbx
0x14004d862  jz      short loc_14004D86D
0x14004d864  mov     rcx, rbx; hLibModule
0x14004d867  call    cs:__imp_FreeLibrary
0x14004d86d  mov     rbx, r14
0x14004d870  lea     rcx, [rsp+160h+lpLibFileName]
0x14004d875  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d87a  mov     rax, rbx
0x14004d87d  mov     rcx, [rbp+60h+var_38]
0x14004d881  xor     rcx, rsp; StackCookie
0x14004d884  call    __security_check_cookie
0x14004d889  add     rsp, 130h
0x14004d890  pop     r15
0x14004d892  pop     r14
0x14004d894  pop     r12
0x14004d896  pop     rdi
0x14004d897  pop     rsi
0x14004d898  pop     rbx
0x14004d899  pop     rbp
0x14004d89a  retn
```
