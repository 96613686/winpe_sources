# AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel(void)

- ea: `0x1400386f0`
- end: `0x1400389c7`
- name: `?VerifyImpersonationLevel@APICaller@AppVClientImpl@Service@Client@AppV@@AEAAJXZ`
- size: `727`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl::APICaller *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140028e00`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x1400147fc`
- `0x1400386f0`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140038862`
- `ADVAPI32!GetTokenInformation` at `0x140038862`
- `ADVAPI32!OpenThreadToken` at `0x14003872e`
- `ADVAPI32!OpenThreadToken` at `0x14003872e`
- `KERNEL32!CloseHandle` at `0x14003882b`
- `KERNEL32!CloseHandle` at `0x14003898c`
- `KERNEL32!CloseHandle` at `0x1400389a2`
- `KERNEL32!CloseHandle` at `0x14003882b`
- `KERNEL32!CloseHandle` at `0x14003898c`
- `KERNEL32!CloseHandle` at `0x1400389a2`
- `KERNEL32!GetCurrentThread` at `0x140038718`
- `KERNEL32!GetCurrentThread` at `0x140038718`
- `KERNEL32!GetLastError` at `0x14003873c`
- `KERNEL32!GetLastError` at `0x140038870`
- `KERNEL32!GetLastError` at `0x14003873c`
- `KERNEL32!GetLastError` at `0x140038870`

## string_xrefs

- `0x140038745`: `AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel`
- `0x140038879`: `AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel`
- `0x140038776`: `Failed to open the thread token after impersonating a COM API caller, error = %1%`
- `0x1400388a8`: `Failed to get the thread token information after impersonating a COM API caller, error = %1%`

## pseudocode

```c
__int64 __fastcall AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel(
        AppV::Client::Service::AppVClientImpl::APICaller *this)
{
  HANDLE CurrentThread; // rax
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx
  unsigned int v5; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  signed int LastError; // [rsp+30h] [rbp-69h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-61h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-59h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-55h] BYREF
  __int128 v15; // [rsp+48h] [rbp-51h] BYREF
  __int128 v16; // [rsp+58h] [rbp-41h]
  _BYTE v17[32]; // [rsp+68h] [rbp-31h] BYREF
  int v18; // [rsp+88h] [rbp-11h]
  _QWORD v19[2]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v21; // [rsp+C0h] [rbp+27h] BYREF
  __int128 v22; // [rsp+D0h] [rbp+37h]

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    std::string::string(v17, "AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel");
    v18 = 501;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v21,
      L"Failed to open the thread token after impersonating a COM API caller, error = %1%",
      81);
    v3 = AppV::Log::fmt(v2, v19, &v21);
    v4 = AppV::LogFormatter::operator%<unsigned long>(v3, &LastError);
    v15 = 0;
    v16 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v15, L"Client", 6);
    AppV::DecoratedLog::operator()(v17, 8, &v15, v4);
    std::wstring::~wstring(&v15);
    v19[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v20);
    std::wstring::~wstring(&v21);
LABEL_3:
    std::string::~string(v17);
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v5;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    std::string::string(v17, "AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel");
    v18 = 510;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
    v15 = 0;
    v16 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &v15,
      L"Failed to get the thread token information after impersonating a COM API caller, error = %1%",
      92);
    v9 = AppV::Log::fmt(v8, v19, &v15);
    v10 = AppV::LogFormatter::operator%<unsigned long>(v9, &LastError);
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v21, L"Client", 6);
    AppV::DecoratedLog::operator()(v17, 8, &v21, v10);
    std::wstring::~wstring(&v21);
    v19[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v20);
    std::wstring::~wstring(&v15);
    goto LABEL_3;
  }
  if ( TokenInformation >= 2 )
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return 0;
  }
  else
  {
    if ( (Microsoft_AppV_ClientEnableBits & 0x40) != 0 )
    {
      LastError = TokenInformation;
      *(_QWORD *)&v22 = &LastError;
      *((_QWORD *)&v22 + 1) = 4;
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        APPV_CLIENT_Evt_APIRequiresMinimumImpersonateLevel,
        v7,
        2,
        &v21);
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return 2147943746LL;
  }
}

```

## disassembly

```asm
0x1400386f0  mov     [rsp-8+arg_0], rbx
0x1400386f5  push    rbp
0x1400386f6  lea     rbp, [rsp-57h]
0x1400386fb  sub     rsp, 0F0h
0x140038702  mov     rax, cs:__security_cookie
0x140038709  xor     rax, rsp
0x14003870c  mov     [rbp+57h+var_10], rax
0x140038710  mov     [rbp+57h+TokenHandle], 0
0x140038718  call    cs:__imp_GetCurrentThread
0x14003871e  mov     rcx, rax; ThreadHandle
0x140038721  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140038725  mov     edx, 8; DesiredAccess
0x14003872a  lea     r8d, [rdx-7]; OpenAsSelf
0x14003872e  call    cs:__imp_OpenThreadToken
0x140038734  test    eax, eax
0x140038736  jnz     loc_140038838
0x14003873c  call    cs:__imp_GetLastError
0x140038742  mov     [rbp+57h+var_C0], eax
0x140038745  lea     rdx, aAppvClientServ_60; "AppV::Client::Service::AppVClientImpl::"...
0x14003874c  lea     rcx, [rbp+57h+var_88]
0x140038750  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140038755  mov     [rbp+57h+var_68], 1F5h
0x14003875c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140038761  xorps   xmm0, xmm0
0x140038764  movups  [rbp+57h+var_30], xmm0
0x140038768  xorps   xmm1, xmm1
0x14003876b  movdqu  [rbp+57h+var_20], xmm1
0x140038770  mov     r8d, 51h ; 'Q'
0x140038776  lea     rdx, aFailedToOpenTh; "Failed to open the thread token after i"...
0x14003877d  lea     rcx, [rbp+57h+var_30]
0x140038781  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140038786  nop
0x140038787  lea     r8, [rbp+57h+var_30]
0x14003878b  lea     rdx, [rbp+57h+var_60]
0x14003878f  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140038794  nop
0x140038795  lea     rdx, [rbp+57h+var_C0]
0x140038799  mov     rcx, rax
0x14003879c  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400387a1  mov     rbx, rax
0x1400387a4  xorps   xmm0, xmm0
0x1400387a7  movups  [rbp+57h+var_A8], xmm0
0x1400387ab  xorps   xmm1, xmm1
0x1400387ae  movdqu  [rbp+57h+var_98], xmm1
0x1400387b3  mov     r8d, 6
0x1400387b9  lea     rdx, aClient; "Client"
0x1400387c0  lea     rcx, [rbp+57h+var_A8]
0x1400387c4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400387c9  nop
0x1400387ca  mov     r9, rbx
0x1400387cd  lea     r8, [rbp+57h+var_A8]
0x1400387d1  mov     edx, 8
0x1400387d6  lea     rcx, [rbp+57h+var_88]
0x1400387da  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400387df  nop
0x1400387e0  lea     rcx, [rbp+57h+var_A8]
0x1400387e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400387e9  nop
0x1400387ea  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400387f1  mov     [rbp+57h+var_60], rax
0x1400387f5  lea     rcx, [rbp+57h+var_50]
0x1400387f9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400387fe  nop
0x1400387ff  lea     rcx, [rbp+57h+var_30]
0x140038803  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038808  nop
0x140038809  lea     rcx, [rbp+57h+var_88]
0x14003880d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140038812  mov     ebx, [rbp+57h+var_C0]
0x140038815  test    ebx, ebx
0x140038817  jle     short loc_140038822
0x140038819  movzx   ebx, bx
0x14003881c  or      ebx, 80070000h
0x140038822  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x140038826  test    rcx, rcx
0x140038829  jz      short loc_140038831
0x14003882b  call    cs:__imp_CloseHandle
0x140038831  mov     eax, ebx
0x140038833  jmp     loc_1400389AA
0x140038838  mov     [rbp+57h+TokenInformation], 0
0x14003883f  mov     [rbp+57h+var_AC], 0
0x140038846  lea     rax, [rbp+57h+var_AC]
0x14003884a  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x14003884f  mov     ebx, 4
0x140038854  mov     r9d, ebx; TokenInformationLength
0x140038857  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14003885b  lea     edx, [rbx+5]; TokenInformationClass
0x14003885e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140038862  call    cs:__imp_GetTokenInformation
0x140038868  test    eax, eax
0x14003886a  jnz     loc_140038940
0x140038870  call    cs:__imp_GetLastError
0x140038876  mov     [rbp+57h+var_C0], eax
0x140038879  lea     rdx, aAppvClientServ_60; "AppV::Client::Service::AppVClientImpl::"...
0x140038880  lea     rcx, [rbp+57h+var_88]
0x140038884  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140038889  mov     [rbp+57h+var_68], 1FEh
0x140038890  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140038895  xorps   xmm0, xmm0
0x140038898  movups  [rbp+57h+var_A8], xmm0
0x14003889c  xorps   xmm1, xmm1
0x14003889f  movdqu  [rbp+57h+var_98], xmm1
0x1400388a4  lea     r8d, [rbx+58h]
0x1400388a8  lea     rdx, aFailedToGetThe_3; "Failed to get the thread token informat"...
0x1400388af  lea     rcx, [rbp+57h+var_A8]
0x1400388b3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400388b8  nop
0x1400388b9  lea     r8, [rbp+57h+var_A8]
0x1400388bd  lea     rdx, [rbp+57h+var_60]
0x1400388c1  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400388c6  nop
0x1400388c7  lea     rdx, [rbp+57h+var_C0]
0x1400388cb  mov     rcx, rax
0x1400388ce  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400388d3  mov     rbx, rax
0x1400388d6  xorps   xmm0, xmm0
0x1400388d9  movups  [rbp+57h+var_30], xmm0
0x1400388dd  xorps   xmm1, xmm1
0x1400388e0  movdqu  [rbp+57h+var_20], xmm1
0x1400388e5  mov     r8d, 6
0x1400388eb  lea     rdx, aClient; "Client"
0x1400388f2  lea     rcx, [rbp+57h+var_30]
0x1400388f6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400388fb  nop
0x1400388fc  mov     r9, rbx
0x1400388ff  lea     r8, [rbp+57h+var_30]
0x140038903  mov     edx, 8
0x140038908  lea     rcx, [rbp+57h+var_88]
0x14003890c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140038911  nop
0x140038912  lea     rcx, [rbp+57h+var_30]
0x140038916  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003891b  nop
0x14003891c  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140038923  mov     [rbp+57h+var_60], rax
0x140038927  lea     rcx, [rbp+57h+var_50]
0x14003892b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038930  nop
0x140038931  lea     rcx, [rbp+57h+var_A8]
0x140038935  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003893a  nop
0x14003893b  jmp     loc_140038809
0x140038940  mov     eax, [rbp+57h+TokenInformation]
0x140038943  mov     r9d, 2
0x140038949  cmp     eax, r9d
0x14003894c  jge     short loc_140038999
0x14003894e  test    cs:Microsoft_AppV_ClientEnableBits, 40h
0x140038955  jz      short loc_140038983
0x140038957  mov     [rbp+57h+var_C0], eax
0x14003895a  lea     rax, [rbp+57h+var_C0]
0x14003895e  mov     qword ptr [rbp+57h+var_20], rax
0x140038962  mov     qword ptr [rbp+57h+var_20+8], rbx
0x140038966  lea     rax, [rbp+57h+var_30]
0x14003896a  mov     [rsp+0F0h+ReturnLength], rax
0x14003896f  lea     rdx, APPV_CLIENT_Evt_APIRequiresMinimumImpersonateLevel
0x140038976  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14003897d  call    McGenEventWrite_EventWriteTransfer
0x140038982  nop
0x140038983  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x140038987  test    rcx, rcx
0x14003898a  jz      short loc_140038992
0x14003898c  call    cs:__imp_CloseHandle
0x140038992  mov     eax, 80070542h
0x140038997  jmp     short loc_1400389AA
0x140038999  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14003899d  test    rcx, rcx
0x1400389a0  jz      short loc_1400389A8
0x1400389a2  call    cs:__imp_CloseHandle
0x1400389a8  xor     eax, eax
0x1400389aa  mov     rcx, [rbp+57h+var_10]
0x1400389ae  xor     rcx, rsp; StackCookie
0x1400389b1  call    __security_check_cookie
0x1400389b6  mov     rbx, [rsp+0F0h+arg_0]
0x1400389be  add     rsp, 0F0h
0x1400389c5  pop     rbp
0x1400389c6  retn
```
