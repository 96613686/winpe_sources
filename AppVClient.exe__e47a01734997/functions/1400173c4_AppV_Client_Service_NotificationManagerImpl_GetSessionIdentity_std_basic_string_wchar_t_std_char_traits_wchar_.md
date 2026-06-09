# AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ATL::CHandle &)

- ea: `0x1400173c4`
- end: `0x1400179b7`
- name: `?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z`
- size: `1523`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140014c00`
- `0x140014f4c`
- `0x140015500`
- `0x140015850`
- `0x140015ba0`
- `0x140015eec`
- `0x140017d40`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x1400173c4`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x1400418a0`
- `0x140046b2c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140017803`
- `ADVAPI32!GetTokenInformation` at `0x140017803`
- `ADVAPI32!OpenThreadToken` at `0x140017413`
- `ADVAPI32!OpenThreadToken` at `0x140017413`
- `KERNEL32!CloseHandle` at `0x140017527`
- `KERNEL32!CloseHandle` at `0x140017955`
- `KERNEL32!CloseHandle` at `0x140017981`
- `KERNEL32!CloseHandle` at `0x140017527`
- `KERNEL32!CloseHandle` at `0x140017955`
- `KERNEL32!CloseHandle` at `0x140017981`
- `KERNEL32!GetCurrentThread` at `0x1400173fc`
- `KERNEL32!GetCurrentThread` at `0x1400173fc`
- `KERNEL32!GetLastError` at `0x140017421`
- `KERNEL32!GetLastError` at `0x14001769c`
- `KERNEL32!GetLastError` at `0x140017811`
- `KERNEL32!GetLastError` at `0x140017421`
- `KERNEL32!GetLastError` at `0x14001769c`
- `KERNEL32!GetLastError` at `0x140017811`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400174e3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001760e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017785`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400178fa`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400174e3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001760e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017785`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400178fa`

## string_xrefs

- `0x14001742b`: `AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity`
- `0x1400176a6`: `AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity`
- `0x14001781b`: `AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity`
- `0x140017464`: `NotificationManager could not register a subscriber because the thread was not impersonating the caller`
- `0x14001755d`: `NotificationManager could not get thread token to ID a subscriber, error = %1%`
- `0x1400176d7`: `NotificationManager could not get the SID for a subscriber, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(__int64 a1, HANDLE *a2)
{
  HANDLE CurrentThread; // rax
  char *v5; // rax
  DWORD *SubAuthority; // rax
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  char *v14; // rax
  DWORD *v15; // rax
  unsigned __int64 FileId; // rax
  __int64 UserTokenSID; // rax
  __int64 v18; // xmm6_8
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  char *v22; // rax
  DWORD *v23; // rax
  unsigned __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  char *v29; // rax
  DWORD *v30; // rax
  HANDLE v31; // rax
  __int64 v32; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  __int64 TokenInformation; // [rsp+48h] [rbp-C0h] BYREF
  __int128 TokenInformation_8; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A8h]
  __int128 v37; // [rsp+70h] [rbp-98h] BYREF
  __int128 v38; // [rsp+80h] [rbp-88h]
  __int128 v39; // [rsp+90h] [rbp-78h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-68h]
  int v41; // [rsp+B0h] [rbp-58h]
  char *v42[2]; // [rsp+B8h] [rbp-50h] BYREF
  char *v43; // [rsp+C8h] [rbp-40h] BYREF
  int v44; // [rsp+D8h] [rbp-30h]
  _QWORD v45[2]; // [rsp+E8h] [rbp-20h] BYREF
  char *v46[4]; // [rsp+F8h] [rbp-10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LODWORD(v32) = GetLastError();
    if ( (_DWORD)v32 == 1008 )
    {
      std::string::string(&v39, "AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity");
      v41 = 284;
      TokenInformation_8 = 0;
      v36 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&TokenInformation_8,
        L"NotificationManager could not register a subscriber because the thread was not impersonating the caller",
        0x67u);
      v37 = 0;
      v38 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v37, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)&v39, 8, (int)&v37, (__int64)&TokenInformation_8);
      std::wstring::~wstring((char **)&v37);
      std::wstring::~wstring((char **)&TokenInformation_8);
      std::string::~string((char **)&v39);
      v5 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
      if ( v5 )
        SubAuthority = (DWORD *)(v5 + 1);
      else
        SubAuthority = ATL::Sids::SecurityNTAuthority.SubAuthority;
      v7 = AppV::FileLookUp::getFileId(
             (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
             (const char *)SubAuthority) << 52;
      v8 = 0x230300000204LL;
    }
    else
    {
      std::string::string(&v39, "AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity");
      v41 = 288;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
      v37 = 0;
      v38 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v37,
        L"NotificationManager could not get thread token to ID a subscriber, error = %1%",
        0x4Eu);
      v12 = AppV::Log::fmt(v11, v42, &v37);
      v13 = AppV::LogFormatter::operator%<unsigned long>(v12, (__int64)&v32);
      TokenInformation_8 = 0;
      v36 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&TokenInformation_8, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)&v39, 8, (int)&TokenInformation_8, v13);
      std::wstring::~wstring((char **)&TokenInformation_8);
      v42[0] = (char *)&AppV::LogFormatter::`vftable';
      std::wstring::~wstring(&v43);
      std::wstring::~wstring((char **)&v37);
      std::string::~string((char **)&v39);
      v14 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
      if ( v14 )
        v15 = (DWORD *)(v14 + 1);
      else
        v15 = ATL::Sids::SecurityNTAuthority.SubAuthority;
      FileId = AppV::FileLookUp::getFileId(
                 (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
                 (const char *)v15);
      v7 = (unsigned int)v32 | (FileId << 52);
      v8 = 0x242300000000LL;
    }
    v9 = v8 | v7;
    goto LABEL_8;
  }
  UserTokenSID = AppUtils::getUserTokenSID(&v39, TokenHandle);
  v37 = *(_OWORD *)UserTokenSID;
  v38 = *(_OWORD *)(UserTokenSID + 16);
  v18 = v38;
  *(_QWORD *)(UserTokenSID + 16) = 0;
  *(_QWORD *)(UserTokenSID + 24) = 7;
  *(_WORD *)UserTokenSID = 0;
  std::wstring::~wstring((char **)&v39);
  if ( !v18 )
  {
    LODWORD(v32) = GetLastError();
    std::string::string(v42, "AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity");
    v44 = 296;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v39 = 0;
    v40 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v39,
      L"NotificationManager could not get the SID for a subscriber, error = %1%",
      0x47u);
    v20 = AppV::Log::fmt(v19, v45, &v39);
    v21 = AppV::LogFormatter::operator%<unsigned long>(v20, (__int64)&v32);
    TokenInformation_8 = 0;
    v36 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&TokenInformation_8, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v42, 8, (int)&TokenInformation_8, v21);
    std::wstring::~wstring((char **)&TokenInformation_8);
    v45[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v46);
    std::wstring::~wstring((char **)&v39);
    std::string::~string(v42);
    v22 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v22 )
      v23 = (DWORD *)(v22 + 1);
    else
      v23 = ATL::Sids::SecurityNTAuthority.SubAuthority;
    v24 = AppV::FileLookUp::getFileId(
            (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
            (const char *)v23);
    v25 = 0x252300000000LL;
LABEL_20:
    v9 = v25 | (unsigned int)v32 | (v24 << 52);
    std::wstring::~wstring((char **)&v37);
LABEL_8:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v9;
  }
  TokenInformation = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, (PDWORD)&TokenInformation + 1) )
  {
    LODWORD(v32) = GetLastError();
    std::string::string(v42, "AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity");
    v44 = 306;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    TokenInformation_8 = 0;
    v36 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&TokenInformation_8,
      L"NotificationManager could not get the session ID for a subscriber, error = %1%",
      0x4Eu);
    v27 = AppV::Log::fmt(v26, v45, &TokenInformation_8);
    v28 = AppV::LogFormatter::operator%<unsigned long>(v27, (__int64)&v32);
    v39 = 0;
    v40 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v39, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v42, 8, (int)&v39, v28);
    std::wstring::~wstring((char **)&v39);
    v45[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v46);
    std::wstring::~wstring((char **)&TokenInformation_8);
    std::string::~string(v42);
    v29 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v29 )
      v30 = (DWORD *)(v29 + 1);
    else
      v30 = ATL::Sids::SecurityNTAuthority.SubAuthority;
    v24 = AppV::FileLookUp::getFileId(
            (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
            (const char *)v30);
    v25 = 0x262300000000LL;
    goto LABEL_20;
  }
  AppV::Client::ClientSession::BuildKey(&v37, (unsigned int)TokenInformation, a1);
  if ( a2 != &TokenHandle )
  {
    if ( *a2 )
      CloseHandle(*a2);
    v31 = TokenHandle;
    TokenHandle = 0;
    *a2 = v31;
  }
  std::wstring::~wstring((char **)&v37);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x1400173c4  mov     rax, rsp
0x1400173c7  mov     [rax+18h], rbx
0x1400173cb  mov     [rax+20h], rdi
0x1400173cf  push    rbp
0x1400173d0  lea     rbp, [rax-38h]
0x1400173d4  sub     rsp, 130h
0x1400173db  movaps  xmmword ptr [rax-18h], xmm6
0x1400173df  mov     rax, cs:__security_cookie
0x1400173e6  xor     rax, rsp
0x1400173e9  mov     [rbp+30h+var_20], rax
0x1400173ed  mov     rbx, rdx
0x1400173f0  mov     rdi, rcx
0x1400173f3  mov     [rsp+130h+TokenHandle], 0
0x1400173fc  call    cs:__imp_GetCurrentThread
0x140017402  mov     rcx, rax; ThreadHandle
0x140017405  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x14001740a  mov     edx, 0Ch; DesiredAccess
0x14001740f  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x140017413  call    cs:__imp_OpenThreadToken
0x140017419  test    eax, eax
0x14001741b  jnz     loc_140017651
0x140017421  call    cs:__imp_GetLastError
0x140017427  mov     dword ptr [rsp+130h+var_100], eax
0x14001742b  lea     rdx, aAppvClientServ_36; "AppV::Client::Service::NotificationMana"...
0x140017432  lea     rcx, [rbp+30h+var_A8]
0x140017436  cmp     eax, 3F0h
0x14001743b  jnz     loc_140017535
0x140017441  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140017446  mov     [rbp+30h+var_88], 11Ch
0x14001744d  xorps   xmm0, xmm0
0x140017450  movups  [rsp+130h+TokenInformation+8], xmm0
0x140017455  xorps   xmm1, xmm1
0x140017458  movdqu  [rsp+130h+var_E0+8], xmm1
0x14001745e  mov     r8d, 67h ; 'g'
0x140017464  lea     rdx, aNotificationma_1; "NotificationManager could not register "...
0x14001746b  lea     rcx, [rsp+130h+TokenInformation+8]
0x140017470  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140017475  nop
0x140017476  xorps   xmm0, xmm0
0x140017479  movups  [rsp+130h+var_D0+8], xmm0
0x14001747e  xorps   xmm1, xmm1
0x140017481  movdqu  xmmword ptr [rsp+130h+var_C0+8], xmm1
0x140017487  mov     r8d, 6
0x14001748d  lea     rdx, aClient; "Client"
0x140017494  lea     rcx, [rsp+130h+var_D0+8]
0x140017499  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001749e  nop
0x14001749f  lea     r9, [rsp+130h+TokenInformation+8]
0x1400174a4  lea     r8, [rsp+130h+var_D0+8]
0x1400174a9  mov     edx, 8
0x1400174ae  lea     rcx, [rbp+30h+var_A8]
0x1400174b2  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400174b7  nop
0x1400174b8  lea     rcx, [rsp+130h+var_D0+8]
0x1400174bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400174c2  nop
0x1400174c3  lea     rcx, [rsp+130h+TokenInformation+8]
0x1400174c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400174cd  nop
0x1400174ce  lea     rcx, [rbp+30h+var_A8]
0x1400174d2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400174d7  mov     edx, 5Ch ; '\'; Ch
0x1400174dc  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x1400174e3  call    cs:__imp_strrchr
0x1400174e9  test    rax, rax
0x1400174ec  jz      short loc_1400174F3
0x1400174ee  inc     rax
0x1400174f1  jmp     short loc_1400174FA
0x1400174f3  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x1400174fa  mov     rdx, rax; char *
0x1400174fd  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140017504  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140017509  mov     rbx, rax
0x14001750c  shl     rbx, 34h
0x140017510  mov     rax, 230300000204h
0x14001751a  or      rbx, rax
0x14001751d  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x140017522  test    rcx, rcx
0x140017525  jz      short loc_14001752D
0x140017527  call    cs:__imp_CloseHandle
0x14001752d  mov     rax, rbx
0x140017530  jmp     loc_140017991
0x140017535  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001753a  mov     [rbp+30h+var_88], 120h
0x140017541  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140017546  xorps   xmm0, xmm0
0x140017549  movups  [rsp+130h+var_D0+8], xmm0
0x14001754e  xorps   xmm1, xmm1
0x140017551  movdqu  xmmword ptr [rsp+130h+var_C0+8], xmm1
0x140017557  mov     r8d, 4Eh ; 'N'
0x14001755d  lea     rdx, aNotificationma_3; "NotificationManager could not get threa"...
0x140017564  lea     rcx, [rsp+130h+var_D0+8]
0x140017569  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001756e  nop
0x14001756f  lea     r8, [rsp+130h+var_D0+8]
0x140017574  lea     rdx, [rbp+30h+var_80]
0x140017578  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001757d  nop
0x14001757e  lea     rdx, [rsp+130h+var_100]
0x140017583  mov     rcx, rax
0x140017586  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14001758b  mov     rbx, rax
0x14001758e  xorps   xmm0, xmm0
0x140017591  movups  [rsp+130h+TokenInformation+8], xmm0
0x140017596  xorps   xmm1, xmm1
0x140017599  movdqu  [rsp+130h+var_E0+8], xmm1
0x14001759f  mov     r8d, 6
0x1400175a5  lea     rdx, aClient; "Client"
0x1400175ac  lea     rcx, [rsp+130h+TokenInformation+8]
0x1400175b1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400175b6  nop
0x1400175b7  mov     r9, rbx
0x1400175ba  lea     r8, [rsp+130h+TokenInformation+8]
0x1400175bf  mov     edx, 8
0x1400175c4  lea     rcx, [rbp+30h+var_A8]
0x1400175c8  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400175cd  nop
0x1400175ce  lea     rcx, [rsp+130h+TokenInformation+8]
0x1400175d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400175d8  nop
0x1400175d9  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400175e0  mov     [rbp+30h+var_80], rax
0x1400175e4  lea     rcx, [rbp+30h+var_70]
0x1400175e8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400175ed  nop
0x1400175ee  lea     rcx, [rsp+130h+var_D0+8]
0x1400175f3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400175f8  nop
0x1400175f9  lea     rcx, [rbp+30h+var_A8]
0x1400175fd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140017602  mov     edx, 5Ch ; '\'; Ch
0x140017607  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x14001760e  call    cs:__imp_strrchr
0x140017614  test    rax, rax
0x140017617  jz      short loc_14001761E
0x140017619  inc     rax
0x14001761c  jmp     short loc_140017625
0x14001761e  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x140017625  mov     rdx, rax; char *
0x140017628  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001762f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140017634  mov     rbx, rax
0x140017637  shl     rbx, 34h
0x14001763b  mov     ecx, dword ptr [rsp+130h+var_100]
0x14001763f  or      rbx, rcx
0x140017642  mov     rax, 242300000000h
0x14001764c  jmp     loc_14001751A
0x140017651  mov     rdx, [rsp+130h+TokenHandle]
0x140017656  lea     rcx, [rbp+30h+var_A8]
0x14001765a  call    ?getUserTokenSID@AppUtils@@SA?AV?$extended_string@_W@shared@softricity@@PEAX@Z; AppUtils::getUserTokenSID(void *)
0x14001765f  movups  xmm0, xmmword ptr [rax]
0x140017662  movups  [rsp+130h+var_D0+8], xmm0
0x140017667  movups  xmm6, xmmword ptr [rax+10h]
0x14001766b  movups  xmmword ptr [rsp+130h+var_C0+8], xmm6
0x140017670  mov     qword ptr [rax+10h], 0
0x140017678  mov     qword ptr [rax+18h], 7
0x140017680  xor     ecx, ecx
0x140017682  mov     [rax], cx
0x140017685  lea     rcx, [rbp+30h+var_A8]
0x140017689  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001768e  movq    rax, xmm6
0x140017693  test    rax, rax
0x140017696  jnz     loc_1400177D5
0x14001769c  call    cs:__imp_GetLastError
0x1400176a2  mov     dword ptr [rsp+130h+var_100], eax
0x1400176a6  lea     rdx, aAppvClientServ_36; "AppV::Client::Service::NotificationMana"...
0x1400176ad  lea     rcx, [rbp+30h+var_80]
0x1400176b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400176b6  mov     [rbp+30h+var_60], 128h
0x1400176bd  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400176c2  xorps   xmm0, xmm0
0x1400176c5  movups  [rbp+30h+var_A8], xmm0
0x1400176c9  xorps   xmm1, xmm1
0x1400176cc  movdqu  [rbp+30h+var_98], xmm1
0x1400176d1  mov     r8d, 47h ; 'G'
0x1400176d7  lea     rdx, aNotificationma; "NotificationManager could not get the S"...
0x1400176de  lea     rcx, [rbp+30h+var_A8]
0x1400176e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400176e7  nop
0x1400176e8  lea     r8, [rbp+30h+var_A8]
0x1400176ec  lea     rdx, [rbp+30h+var_50]
0x1400176f0  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400176f5  nop
0x1400176f6  lea     rdx, [rsp+130h+var_100]
0x1400176fb  mov     rcx, rax
0x1400176fe  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140017703  mov     rbx, rax
0x140017706  xorps   xmm0, xmm0
0x140017709  movups  [rsp+130h+TokenInformation+8], xmm0
0x14001770e  xorps   xmm1, xmm1
0x140017711  movdqu  [rsp+130h+var_E0+8], xmm1
0x140017717  mov     r8d, 6
0x14001771d  lea     rdx, aClient; "Client"
0x140017724  lea     rcx, [rsp+130h+TokenInformation+8]
0x140017729  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001772e  nop
0x14001772f  mov     r9, rbx
0x140017732  lea     r8, [rsp+130h+TokenInformation+8]
0x140017737  mov     edx, 8
0x14001773c  lea     rcx, [rbp+30h+var_80]
0x140017740  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140017745  nop
0x140017746  lea     rcx, [rsp+130h+TokenInformation+8]
0x14001774b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017750  nop
0x140017751  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140017758  mov     [rbp+30h+var_50], rax
0x14001775c  lea     rcx, [rbp+30h+var_40]
0x140017760  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017765  nop
0x140017766  lea     rcx, [rbp+30h+var_A8]
0x14001776a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001776f  nop
0x140017770  lea     rcx, [rbp+30h+var_80]
0x140017774  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140017779  mov     edx, 5Ch ; '\'; Ch
0x14001777e  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140017785  call    cs:__imp_strrchr
0x14001778b  test    rax, rax
0x14001778e  jz      short loc_140017795
0x140017790  inc     rax
0x140017793  jmp     short loc_14001779C
0x140017795  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x14001779c  mov     rdx, rax; char *
0x14001779f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400177a6  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400177ab  mov     rbx, rax
0x1400177ae  mov     rax, 252300000000h
0x1400177b8  mov     ecx, dword ptr [rsp+130h+var_100]
0x1400177bc  shl     rbx, 34h
0x1400177c0  or      rbx, rcx
0x1400177c3  or      rbx, rax
0x1400177c6  lea     rcx, [rsp+130h+var_D0+8]
0x1400177cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400177d0  jmp     loc_14001751D
0x1400177d5  mov     dword ptr [rsp+130h+TokenInformation], 0
0x1400177dd  mov     dword ptr [rsp+130h+TokenInformation+4], 0
0x1400177e5  lea     rax, [rsp+130h+TokenInformation+4]
0x1400177ea  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x1400177ef  mov     r9d, 4; TokenInformationLength
0x1400177f5  lea     r8, [rsp+130h+TokenInformation]; TokenInformation
0x1400177fa  lea     edx, [r9+8]; TokenInformationClass
0x1400177fe  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x140017803  call    cs:__imp_GetTokenInformation
0x140017809  test    eax, eax
0x14001780b  jnz     loc_140017932
0x140017811  call    cs:__imp_GetLastError
0x140017817  mov     dword ptr [rsp+130h+var_100], eax
0x14001781b  lea     rdx, aAppvClientServ_36; "AppV::Client::Service::NotificationMana"...
0x140017822  lea     rcx, [rbp+30h+var_80]
0x140017826  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001782b  mov     [rbp+30h+var_60], 132h
0x140017832  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140017837  xorps   xmm0, xmm0
0x14001783a  movups  [rsp+130h+TokenInformation+8], xmm0
0x14001783f  xorps   xmm1, xmm1
0x140017842  movdqu  [rsp+130h+var_E0+8], xmm1
0x140017848  mov     r8d, 4Eh ; 'N'
0x14001784e  lea     rdx, aNotificationma_0; "NotificationManager could not get the s"...
0x140017855  lea     rcx, [rsp+130h+TokenInformation+8]
0x14001785a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001785f  nop
0x140017860  lea     r8, [rsp+130h+TokenInformation+8]
0x140017865  lea     rdx, [rbp+30h+var_50]
0x140017869  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001786e  nop
0x14001786f  lea     rdx, [rsp+130h+var_100]
0x140017874  mov     rcx, rax
0x140017877  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14001787c  mov     rbx, rax
0x14001787f  xorps   xmm0, xmm0
0x140017882  movups  [rbp+30h+var_A8], xmm0
0x140017886  xorps   xmm1, xmm1
0x140017889  movdqu  [rbp+30h+var_98], xmm1
0x14001788e  mov     r8d, 6
0x140017894  lea     rdx, aClient; "Client"
0x14001789b  lea     rcx, [rbp+30h+var_A8]
0x14001789f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400178a4  nop
0x1400178a5  mov     r9, rbx
0x1400178a8  lea     r8, [rbp+30h+var_A8]
0x1400178ac  mov     edx, 8
0x1400178b1  lea     rcx, [rbp+30h+var_80]
0x1400178b5  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400178ba  nop
0x1400178bb  lea     rcx, [rbp+30h+var_A8]
0x1400178bf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400178c4  nop
0x1400178c5  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400178cc  mov     [rbp+30h+var_50], rax
0x1400178d0  lea     rcx, [rbp+30h+var_40]
0x1400178d4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400178d9  nop
0x1400178da  lea     rcx, [rsp+130h+TokenInformation+8]
0x1400178df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400178e4  nop
0x1400178e5  lea     rcx, [rbp+30h+var_80]
0x1400178e9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400178ee  mov     edx, 5Ch ; '\'; Ch
0x1400178f3  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
  ... truncated ...
```
