# wWinMain

- ea: `0x1400148f0`
- end: `0x140014bfa`
- name: `wWinMain`
- size: `778`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400040d0`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x14000bbc4`
- `0x140011674`
- `0x1400147a8`
- `0x1400147cc`
- `0x1400147fc`
- `0x1400148f0`
- `0x14003c034`
- `0x14003c258`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400149fc`
- `ADVAPI32!EventActivityIdControl` at `0x1400149fc`
- `ADVAPI32!EventUnregister` at `0x140014bd1`
- `ADVAPI32!EventUnregister` at `0x140014bd1`
- `ADVAPI32!EventSetInformation` at `0x1400149ac`
- `ADVAPI32!EventSetInformation` at `0x1400149ac`
- `ADVAPI32!EventRegister` at `0x140014989`
- `ADVAPI32!EventRegister` at `0x140014989`
- `ADVAPI32!RegDisablePredefinedCacheEx` at `0x140014936`
- `ADVAPI32!RegDisablePredefinedCacheEx` at `0x140014936`
- `KERNEL32!HeapSetInformation` at `0x140014921`
- `KERNEL32!HeapSetInformation` at `0x140014921`
- `KERNEL32!GetLastError` at `0x14001492b`
- `KERNEL32!GetLastError` at `0x14001492b`

## string_xrefs

- `0x140014a60`: `Client service executable started`
- `0x140014af9`: `Client service executable exiting normally`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int result; // eax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ebx
  __int64 v10; // r8
  REGHANDLE v11; // rcx
  GUID ProviderId; // [rsp+30h] [rbp-29h] BYREF
  __int128 v13; // [rsp+40h] [rbp-19h]
  __int128 v14; // [rsp+50h] [rbp-9h] BYREF
  __int128 v15; // [rsp+60h] [rbp+7h]
  char *v16[4]; // [rsp+70h] [rbp+17h] BYREF
  int v17; // [rsp+90h] [rbp+37h]
  GUID ActivityId; // [rsp+98h] [rbp+3Fh] BYREF

  if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
    return GetLastError();
  result = RegDisablePredefinedCacheEx();
  if ( !result )
  {
    ProviderId = (GUID)*((_OWORD *)off_1400AA2F0 - 1);
    if ( RegHandle )
      __fastfail(5u);
    xmmword_1400AA310 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_1400AA2E8, &RegHandle) )
      EventSetInformation(RegHandle, 2, off_1400AA2F0, *(unsigned __int16 *)off_1400AA2F0);
    McGenEventRegister_EventRegister(
      PROVIDER_MICROSOFT_APPV_CLIENT,
      v5,
      PROVIDER_MICROSOFT_APPV_CLIENT_Context,
      PROVIDER_MICROSOFT_APPV_CLIENT_Context);
    McGenEventRegister_EventRegister(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS,
      v6,
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs();
    ActivityId = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_startupCorrelationID;
    EventActivityIdControl(2u, &ActivityId);
    McGenEventRegister_EventRegister(AppVClientDbg, v7, AppVClientDbg_Context, AppVClientDbg_Context);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        Service_StartupBegin,
        v8,
        1,
        &ProviderId);
    std::string::string(v16, "wWinMain");
    v17 = 39;
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v14, L"Client service executable started", 0x21u);
    ProviderId = 0;
    v13 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&ProviderId, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v16, 8, (int)&ProviderId, (__int64)&v14);
    std::wstring::~wstring((char **)&ProviderId);
    std::wstring::~wstring((char **)&v14);
    std::string::~string(v16);
    v9 = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run();
    std::string::string(v16, "wWinMain");
    v17 = 43;
    ProviderId = 0;
    v13 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&ProviderId,
      L"Client service executable exiting normally",
      0x2Au);
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v14, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v16, 8, (int)&v14, (__int64)&ProviderId);
    std::wstring::~wstring((char **)&v14);
    std::wstring::~wstring((char **)&ProviderId);
    std::string::~string(v16);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        Service_ShutdownEnd,
        v10,
        1,
        &ProviderId);
    McGenEventUnregister_EventUnregister(AppVClientDbg_Context);
    McGenEventUnregister_EventUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
    McGenEventUnregister_EventUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_Context);
    v11 = RegHandle;
    dword_1400AA2E8 = 0;
    RegHandle = 0;
    EventUnregister(v11);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400148f0  mov     [rsp-8+arg_0], rbx
0x1400148f5  mov     [rsp-8+arg_8], r15
0x1400148fa  push    rbp
0x1400148fb  lea     rbp, [rsp-57h]
0x140014900  sub     rsp, 0B0h
0x140014907  mov     rax, cs:__security_cookie
0x14001490e  xor     rax, rsp
0x140014911  mov     [rbp+57h+var_8], rax
0x140014915  xor     r9d, r9d; HeapInformationLength
0x140014918  xor     r8d, r8d; HeapInformation
0x14001491b  xor     ecx, ecx; HeapHandle
0x14001491d  lea     edx, [r9+1]; HeapInformationClass
0x140014921  call    cs:__imp_HeapSetInformation
0x140014927  test    eax, eax
0x140014929  jnz     short loc_140014936
0x14001492b  call    cs:__imp_GetLastError
0x140014931  jmp     loc_140014BD9
0x140014936  call    cs:__imp_RegDisablePredefinedCacheEx
0x14001493c  test    eax, eax
0x14001493e  jnz     loc_140014BD9
0x140014944  cmp     cs:RegHandle, 0
0x14001494c  mov     rax, cs:off_1400AA2F0
0x140014953  movups  xmm0, xmmword ptr [rax-10h]
0x140014957  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x14001495c  jz      short loc_140014965
0x14001495e  mov     ecx, 5
0x140014963  int     29h; Win8: RtlFailFast(ecx)
0x140014965  xorps   xmm0, xmm0
0x140014968  lea     r9, RegHandle; RegHandle
0x14001496f  lea     r8, dword_1400AA2E8; CallbackContext
0x140014976  lea     rdx, _tlgEnableCallback; EnableCallback
0x14001497d  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x140014981  movdqu  cs:xmmword_1400AA310, xmm0
0x140014989  call    cs:__imp_EventRegister
0x14001498f  mov     ebx, 2
0x140014994  test    eax, eax
0x140014996  jnz     short loc_1400149B2
0x140014998  mov     r8, cs:off_1400AA2F0
0x14001499f  mov     edx, ebx
0x1400149a1  mov     rcx, cs:RegHandle
0x1400149a8  movzx   r9d, word ptr [r8]
0x1400149ac  call    cs:__imp_EventSetInformation
0x1400149b2  lea     r9, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1400149b9  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1400149c0  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT
0x1400149c7  call    McGenEventRegister_EventRegister
0x1400149cc  lea     r15, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400149d3  mov     r9, r15
0x1400149d6  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS
0x1400149dd  mov     r8, r15
0x1400149e0  call    McGenEventRegister_EventRegister
0x1400149e5  call    ?GenerateCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs(void)
0x1400149ea  movups  xmm0, xmmword ptr cs:?st_startupCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A.Data1; _GUID AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_startupCorrelationID ...
0x1400149f1  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400149f5  mov     ecx, ebx; ControlCode
0x1400149f7  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1400149fc  call    cs:__imp_EventActivityIdControl
0x140014a02  lea     r9, AppVClientDbg_Context
0x140014a09  lea     r8, AppVClientDbg_Context
0x140014a10  lea     rcx, AppVClientDbg
0x140014a17  call    McGenEventRegister_EventRegister
0x140014a1c  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014a23  jz      short loc_140014A43
0x140014a25  lea     rax, [rbp+57h+ProviderId]
0x140014a29  mov     r9d, 1
0x140014a2f  lea     rdx, Service_StartupBegin
0x140014a36  mov     [rsp+0B0h+var_90], rax
0x140014a3b  mov     rcx, r15
0x140014a3e  call    McGenEventWrite_EventWriteTransfer
0x140014a43  lea     rdx, aWwinmain; "wWinMain"
0x140014a4a  lea     rcx, [rbp+57h+var_40]
0x140014a4e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140014a53  xorps   xmm0, xmm0
0x140014a56  mov     [rbp+57h+var_20], 27h ; '''
0x140014a5d  xorps   xmm1, xmm1
0x140014a60  lea     rdx, aClientServiceE; "Client service executable started"
0x140014a67  mov     r8d, 21h ; '!'
0x140014a6d  lea     rcx, [rbp+57h+var_60]
0x140014a71  movups  [rbp+57h+var_60], xmm0
0x140014a75  movdqu  [rbp+57h+var_50], xmm1
0x140014a7a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140014a7f  xorps   xmm0, xmm0
0x140014a82  lea     rdx, aClient; "Client"
0x140014a89  xorps   xmm1, xmm1
0x140014a8c  lea     rcx, [rbp+57h+ProviderId]
0x140014a90  mov     r8d, 6
0x140014a96  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140014a9a  movdqu  [rbp+57h+var_70], xmm1
0x140014a9f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140014aa4  lea     r9, [rbp+57h+var_60]
0x140014aa8  mov     edx, 8
0x140014aad  lea     r8, [rbp+57h+ProviderId]
0x140014ab1  lea     rcx, [rbp+57h+var_40]
0x140014ab5  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140014aba  lea     rcx, [rbp+57h+ProviderId]
0x140014abe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014ac3  lea     rcx, [rbp+57h+var_60]
0x140014ac7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014acc  lea     rcx, [rbp+57h+var_40]
0x140014ad0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140014ad5  call    ?Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run(HINSTANCE__ *,wchar_t *)
0x140014ada  lea     rdx, aWwinmain; "wWinMain"
0x140014ae1  mov     ebx, eax
0x140014ae3  lea     rcx, [rbp+57h+var_40]
0x140014ae7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140014aec  xorps   xmm0, xmm0
0x140014aef  mov     [rbp+57h+var_20], 2Bh ; '+'
0x140014af6  xorps   xmm1, xmm1
0x140014af9  lea     rdx, aClientServiceE_0; "Client service executable exiting norma"...
0x140014b00  mov     r8d, 2Ah ; '*'
0x140014b06  lea     rcx, [rbp+57h+ProviderId]
0x140014b0a  movups  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140014b0e  movdqu  [rbp+57h+var_70], xmm1
0x140014b13  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140014b18  xorps   xmm0, xmm0
0x140014b1b  lea     rdx, aClient; "Client"
0x140014b22  xorps   xmm1, xmm1
0x140014b25  lea     rcx, [rbp+57h+var_60]
0x140014b29  mov     r8d, 6
0x140014b2f  movups  [rbp+57h+var_60], xmm0
0x140014b33  movdqu  [rbp+57h+var_50], xmm1
0x140014b38  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140014b3d  lea     r9, [rbp+57h+ProviderId]
0x140014b41  mov     edx, 8
0x140014b46  lea     r8, [rbp+57h+var_60]
0x140014b4a  lea     rcx, [rbp+57h+var_40]
0x140014b4e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140014b53  lea     rcx, [rbp+57h+var_60]
0x140014b57  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014b5c  lea     rcx, [rbp+57h+ProviderId]
0x140014b60  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140014b65  lea     rcx, [rbp+57h+var_40]
0x140014b69  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140014b6e  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014b75  jz      short loc_140014B95
0x140014b77  lea     rax, [rbp+57h+ProviderId]
0x140014b7b  mov     r9d, 1
0x140014b81  lea     rdx, Service_ShutdownEnd
0x140014b88  mov     [rsp+0B0h+var_90], rax
0x140014b8d  mov     rcx, r15
0x140014b90  call    McGenEventWrite_EventWriteTransfer
0x140014b95  lea     rcx, AppVClientDbg_Context
0x140014b9c  call    McGenEventUnregister_EventUnregister
0x140014ba1  mov     rcx, r15
0x140014ba4  call    McGenEventUnregister_EventUnregister
0x140014ba9  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x140014bb0  call    McGenEventUnregister_EventUnregister
0x140014bb5  mov     rcx, cs:RegHandle; RegHandle
0x140014bbc  mov     cs:dword_1400AA2E8, 0
0x140014bc6  mov     cs:RegHandle, 0
0x140014bd1  call    cs:__imp_EventUnregister
0x140014bd7  mov     eax, ebx
0x140014bd9  mov     rcx, [rbp+57h+var_8]
0x140014bdd  xor     rcx, rsp; StackCookie
0x140014be0  call    __security_check_cookie
0x140014be5  lea     r11, [rsp+0B0h+var_s0]
0x140014bed  mov     rbx, [r11+10h]
0x140014bf1  mov     r15, [r11+18h]
0x140014bf5  mov     rsp, r11
0x140014bf8  pop     rbp
0x140014bf9  retn
```
