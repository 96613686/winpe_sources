# AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount(void)

- ea: `0x140051534`
- end: `0x1400518b9`
- name: `?IncrementUserProfileRefCount@SessionImpl@Host@Client@AppV@@AEAA_KXZ`
- size: `901`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::SessionImpl *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052220`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x140050bd4`
- `0x140051534`
- `0x1400645ec`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x140051648`
- `ADVAPI32!DuplicateTokenEx` at `0x140051648`
- `KERNEL32!CloseHandle` at `0x14005188c`
- `KERNEL32!CloseHandle` at `0x14005188c`
- `KERNEL32!GetLastError` at `0x140051656`
- `KERNEL32!GetLastError` at `0x140051656`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005166a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005166a`

## string_xrefs

- `0x140051663`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x14005167a`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140051596`: `Warning: SessionImpl::IncrementUserProfileRefCount() ignoring request to load user profile because the user profile handle has already been set.`
- `0x1400516d9`: `Call to ::DuplicateTokenEx() from SessionImpl::IncrementUserProfileRefCount() failed with error %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
unsigned __int64 __fastcall AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount(
        AppV::Client::Host::SessionImpl *this)
{
  __int64 LastError; // rbx
  char *v4; // rax
  const char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rbx
  unsigned __int64 UserProfileExtended; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  unsigned __int64 v16; // [rsp+30h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-71h] BYREF
  void *v18[2]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v19; // [rsp+50h] [rbp-59h] BYREF
  __int128 v20; // [rsp+60h] [rbp-49h]
  __int128 v21; // [rsp+70h] [rbp-39h] BYREF
  __int128 v22; // [rsp+80h] [rbp-29h]
  char *v23[4]; // [rsp+90h] [rbp-19h] BYREF
  int v24; // [rsp+B0h] [rbp+7h]
  _QWORD v25[2]; // [rsp+B8h] [rbp+Fh] BYREF
  char *v26[4]; // [rsp+C8h] [rbp+1Fh] BYREF

  if ( *((_QWORD *)this + 5) == -1 )
  {
    v16 = 0x8000000000LL;
    hObject = 0;
    if ( DuplicateTokenEx(**((HANDLE **)this + 3), 0xEu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
    {
      v10 = hObject;
      v18[1] = hObject;
      v18[0] = 0;
      UserProfileExtended = SWUserInfo::LoadUserProfileExtended(hObject, v18);
      v16 = UserProfileExtended;
      if ( (UserProfileExtended & 0x8000000000LL) != 0 )
      {
        *((void **)this + 5) = v18[0];
      }
      else
      {
        std::string::string(v23, "AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount");
        v24 = 282;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v12);
        v19 = 0;
        v20 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v19,
          L"Call to SWUserInfo::LoadUserProfileExtended() from SessionImpl::IncrementUserProfileRefCount() failed with error %1%",
          0x74u);
        v14 = AppV::Log::fmt(v13, v25, &v19);
        v15 = AppV::LogFormatter::operator%<unsigned __int64>(v14, &v16);
        v21 = 0;
        v22 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v21, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v23, 1, (int)&v21, v15);
        std::wstring::~wstring((char **)&v21);
        v25[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v26);
        std::wstring::~wstring((char **)&v19);
        std::string::~string(v23);
        UserProfileExtended = v16;
      }
      if ( v10 )
        CloseHandle(v10);
      return UserProfileExtended;
    }
    else
    {
      LastError = GetLastError();
      v4 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
      if ( v4 )
        v5 = v4 + 1;
      else
        v5 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
      v16 = LastError
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5) << 52)
          | 0x212E00000000LL;
      std::string::string(v23, "AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount");
      v24 = 269;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v6);
      v19 = 0;
      v20 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v19,
        L"Call to ::DuplicateTokenEx() from SessionImpl::IncrementUserProfileRefCount() failed with error %1%",
        0x63u);
      v8 = AppV::Log::fmt(v7, v25, &v19);
      v9 = AppV::LogFormatter::operator%<unsigned __int64>(v8, &v16);
      v21 = 0;
      v22 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v21, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v23, 1, (int)&v21, v9);
      std::wstring::~wstring((char **)&v21);
      v25[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v26);
      std::wstring::~wstring((char **)&v19);
      std::string::~string(v23);
      return v16;
    }
  }
  else
  {
    std::string::string(v23, "AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount");
    v24 = 258;
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v21,
      L"Warning: SessionImpl::IncrementUserProfileRefCount() ignoring request to load user profile because the user profil"
       "e handle has already been set.",
      0x90u);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v23, 4, (int)&v19, (__int64)&v21);
    std::wstring::~wstring((char **)&v19);
    std::wstring::~wstring((char **)&v21);
    std::string::~string(v23);
    return 0x8000000000LL;
  }
}

```

## disassembly

```asm
0x140051534  mov     [rsp-8+arg_8], rbx
0x140051539  mov     [rsp-8+arg_10], rsi
0x14005153e  push    rbp
0x14005153f  push    rdi
0x140051540  push    r14
0x140051542  lea     rbp, [rsp-47h]
0x140051547  sub     rsp, 0F0h
0x14005154e  mov     rax, cs:__security_cookie
0x140051555  xor     rax, rsp
0x140051558  mov     [rbp+57h+var_18], rax
0x14005155c  mov     rsi, rcx
0x14005155f  cmp     qword ptr [rcx+28h], 0FFFFFFFFFFFFFFFFh
0x140051564  jz      loc_140051610
0x14005156a  lea     rdx, aAppvClientHost_29; "AppV::Client::Host::SessionImpl::Increm"...
0x140051571  lea     rcx, [rbp+57h+var_70]
0x140051575  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005157a  mov     [rbp+57h+var_50], 102h
0x140051581  xorps   xmm0, xmm0
0x140051584  movups  [rbp+57h+var_90], xmm0
0x140051588  xorps   xmm1, xmm1
0x14005158b  movdqu  [rbp+57h+var_80], xmm1
0x140051590  mov     r8d, 90h
0x140051596  lea     rdx, aWarningSession; "Warning: SessionImpl::IncrementUserProf"...
0x14005159d  lea     rcx, [rbp+57h+var_90]
0x1400515a1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400515a6  nop
0x1400515a7  xorps   xmm0, xmm0
0x1400515aa  movups  [rbp+57h+var_B0], xmm0
0x1400515ae  xorps   xmm1, xmm1
0x1400515b1  movdqu  [rbp+57h+var_A0], xmm1
0x1400515b6  mov     r8d, 6
0x1400515bc  lea     rdx, aClient; "Client"
0x1400515c3  lea     rcx, [rbp+57h+var_B0]
0x1400515c7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400515cc  nop
0x1400515cd  lea     r9, [rbp+57h+var_90]
0x1400515d1  lea     r8, [rbp+57h+var_B0]
0x1400515d5  mov     edx, 4
0x1400515da  lea     rcx, [rbp+57h+var_70]
0x1400515de  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400515e3  nop
0x1400515e4  lea     rcx, [rbp+57h+var_B0]
0x1400515e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400515ed  nop
0x1400515ee  lea     rcx, [rbp+57h+var_90]
0x1400515f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400515f7  nop
0x1400515f8  lea     rcx, [rbp+57h+var_70]
0x1400515fc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051601  mov     rax, 8000000000h
0x14005160b  jmp     loc_140051895
0x140051610  mov     r14, 8000000000h
0x14005161a  mov     [rbp+57h+var_D0], r14
0x14005161e  mov     [rbp+57h+hObject], 0
0x140051626  mov     rcx, [rcx+18h]
0x14005162a  lea     rax, [rbp+57h+hObject]
0x14005162e  mov     [rsp+100h+phNewToken], rax; phNewToken
0x140051633  mov     r9d, 2; ImpersonationLevel
0x140051639  mov     [rsp+100h+TokenType], r9d; TokenType
0x14005163e  xor     r8d, r8d; lpTokenAttributes
0x140051641  lea     edx, [r9+0Ch]; dwDesiredAccess
0x140051645  mov     rcx, [rcx]; hExistingToken
0x140051648  call    cs:__imp_DuplicateTokenEx
0x14005164e  test    eax, eax
0x140051650  jnz     loc_14005177E
0x140051656  call    cs:__imp_GetLastError
0x14005165c  mov     ebx, eax
0x14005165e  mov     edx, 5Ch ; '\'; Ch
0x140051663  lea     rcx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x14005166a  call    cs:__imp_strrchr
0x140051670  test    rax, rax
0x140051673  jz      short loc_14005167A
0x140051675  inc     rax
0x140051678  jmp     short loc_140051681
0x14005167a  lea     rax, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x140051681  mov     rdx, rax; char *
0x140051684  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005168b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051690  shl     rax, 34h
0x140051694  or      rax, rbx
0x140051697  mov     rcx, 212E00000000h
0x1400516a1  or      rax, rcx
0x1400516a4  mov     [rbp+57h+var_D0], rax
0x1400516a8  lea     rdx, aAppvClientHost_29; "AppV::Client::Host::SessionImpl::Increm"...
0x1400516af  lea     rcx, [rbp+57h+var_70]
0x1400516b3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400516b8  mov     [rbp+57h+var_50], 10Dh
0x1400516bf  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400516c4  xorps   xmm0, xmm0
0x1400516c7  movups  [rbp+57h+var_B0], xmm0
0x1400516cb  xorps   xmm1, xmm1
0x1400516ce  movdqu  [rbp+57h+var_A0], xmm1
0x1400516d3  mov     r8d, 63h ; 'c'
0x1400516d9  lea     rdx, aCallToDuplicat_0; "Call to ::DuplicateTokenEx() from Sessi"...
0x1400516e0  lea     rcx, [rbp+57h+var_B0]
0x1400516e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400516e9  nop
0x1400516ea  lea     r8, [rbp+57h+var_B0]
0x1400516ee  lea     rdx, [rbp+57h+var_48]
0x1400516f2  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400516f7  nop
0x1400516f8  lea     rdx, [rbp+57h+var_D0]
0x1400516fc  mov     rcx, rax
0x1400516ff  call    ??$?L_K@LogFormatter@AppV@@QEAAAEAV01@AEA_K@Z; AppV::LogFormatter::operator%<unsigned __int64>(unsigned __int64 &)
0x140051704  mov     rbx, rax
0x140051707  xorps   xmm0, xmm0
0x14005170a  movups  [rbp+57h+var_90], xmm0
0x14005170e  xorps   xmm1, xmm1
0x140051711  movdqu  [rbp+57h+var_80], xmm1
0x140051716  mov     r8d, 6
0x14005171c  lea     rdx, aClient; "Client"
0x140051723  lea     rcx, [rbp+57h+var_90]
0x140051727  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005172c  nop
0x14005172d  mov     r9, rbx
0x140051730  lea     r8, [rbp+57h+var_90]
0x140051734  mov     edx, 1
0x140051739  lea     rcx, [rbp+57h+var_70]
0x14005173d  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140051742  nop
0x140051743  lea     rcx, [rbp+57h+var_90]
0x140051747  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005174c  nop
0x14005174d  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140051754  mov     [rbp+57h+var_48], rax
0x140051758  lea     rcx, [rbp+57h+var_38]
0x14005175c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051761  nop
0x140051762  lea     rcx, [rbp+57h+var_B0]
0x140051766  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005176b  nop
0x14005176c  lea     rcx, [rbp+57h+var_70]
0x140051770  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051775  mov     rax, [rbp+57h+var_D0]
0x140051779  jmp     loc_140051895
0x14005177e  mov     rbx, [rbp+57h+hObject]
0x140051782  mov     [rbp+57h+var_B8], rbx
0x140051786  mov     [rbp+57h+var_C0], 0
0x14005178e  lea     rdx, [rbp+57h+var_C0]; void **
0x140051792  mov     rcx, rbx; Token
0x140051795  call    ?LoadUserProfileExtended@SWUserInfo@@SA_KPEAXAEAPEAX@Z; SWUserInfo::LoadUserProfileExtended(void *,void * &)
0x14005179a  mov     rdi, rax
0x14005179d  mov     [rbp+57h+var_D0], rax
0x1400517a1  test    r14, rax
0x1400517a4  jz      short loc_1400517B3
0x1400517a6  mov     rax, [rbp+57h+var_C0]
0x1400517aa  mov     [rsi+28h], rax
0x1400517ae  jmp     loc_140051884
0x1400517b3  lea     rdx, aAppvClientHost_29; "AppV::Client::Host::SessionImpl::Increm"...
0x1400517ba  lea     rcx, [rbp+57h+var_70]
0x1400517be  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400517c3  mov     [rbp+57h+var_50], 11Ah
0x1400517ca  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400517cf  xorps   xmm0, xmm0
0x1400517d2  movups  [rbp+57h+var_B0], xmm0
0x1400517d6  xorps   xmm1, xmm1
0x1400517d9  movdqu  [rbp+57h+var_A0], xmm1
0x1400517de  mov     r8d, 74h ; 't'
0x1400517e4  lea     rdx, aCallToSwuserin; "Call to SWUserInfo::LoadUserProfileExte"...
0x1400517eb  lea     rcx, [rbp+57h+var_B0]
0x1400517ef  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400517f4  nop
0x1400517f5  lea     r8, [rbp+57h+var_B0]
0x1400517f9  lea     rdx, [rbp+57h+var_48]
0x1400517fd  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140051802  nop
0x140051803  lea     rdx, [rbp+57h+var_D0]
0x140051807  mov     rcx, rax
0x14005180a  call    ??$?L_K@LogFormatter@AppV@@QEAAAEAV01@AEA_K@Z; AppV::LogFormatter::operator%<unsigned __int64>(unsigned __int64 &)
0x14005180f  mov     rdi, rax
0x140051812  xorps   xmm0, xmm0
0x140051815  movups  [rbp+57h+var_90], xmm0
0x140051819  xorps   xmm1, xmm1
0x14005181c  movdqu  [rbp+57h+var_80], xmm1
0x140051821  mov     r8d, 6
0x140051827  lea     rdx, aClient; "Client"
0x14005182e  lea     rcx, [rbp+57h+var_90]
0x140051832  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051837  nop
0x140051838  mov     r9, rdi
0x14005183b  lea     r8, [rbp+57h+var_90]
0x14005183f  mov     edx, 1
0x140051844  lea     rcx, [rbp+57h+var_70]
0x140051848  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005184d  nop
0x14005184e  lea     rcx, [rbp+57h+var_90]
0x140051852  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051857  nop
0x140051858  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005185f  mov     [rbp+57h+var_48], rax
0x140051863  lea     rcx, [rbp+57h+var_38]
0x140051867  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005186c  nop
0x14005186d  lea     rcx, [rbp+57h+var_B0]
0x140051871  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051876  nop
0x140051877  lea     rcx, [rbp+57h+var_70]
0x14005187b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051880  mov     rdi, [rbp+57h+var_D0]
0x140051884  test    rbx, rbx
0x140051887  jz      short loc_140051892
0x140051889  mov     rcx, rbx; hObject
0x14005188c  call    cs:__imp_CloseHandle
0x140051892  mov     rax, rdi
0x140051895  mov     rcx, [rbp+57h+var_18]
0x140051899  xor     rcx, rsp; StackCookie
0x14005189c  call    __security_check_cookie
0x1400518a1  lea     r11, [rsp+100h+var_10]
0x1400518a9  mov     rbx, [r11+28h]
0x1400518ad  mov     rsi, [r11+30h]
0x1400518b1  mov     rsp, r11
0x1400518b4  pop     r14
0x1400518b6  pop     rdi
0x1400518b7  pop     rbp
0x1400518b8  retn
```
