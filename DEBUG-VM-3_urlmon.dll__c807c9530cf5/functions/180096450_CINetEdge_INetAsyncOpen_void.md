# CINetEdge::INetAsyncOpen(void)

- ea: `0x180096450`
- end: `0x180096833`
- name: `?INetAsyncOpen@CINetEdge@@MEAAJXZ`
- size: `995`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007730`
- `0x180008300`
- `0x18000a110`
- `0x18000a270`
- `0x18000cd70`
- `0x18000cef0`
- `0x18001063c`
- `0x1800123e0`
- `0x18003d85c`
- `0x180046cb0`
- `0x180063d8c`
- `0x18007167c`
- `0x1800717bc`
- `0x180073b18`
- `0x18007b1e4`
- `0x18007b48c`
- `0x18007d2a4`
- `0x180083e98`
- `0x180087884`
- `0x1800923a0`
- `0x180096450`
- `0x1800f3064`
- `0x18010bfa8`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180096641`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180096641`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180096637`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180096637`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180096628`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180096628`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800967c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800967c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009650b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009650b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009655e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009655e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009659d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009659d`
- `WININET!InternetSetStatusCallbackA` at `0x180096668`
- `WININET!InternetSetStatusCallbackA` at `0x180096668`
- `WININET!InternetSetOptionA` at `0x180096601`
- `WININET!InternetSetOptionA` at `0x18009661d`
- `WININET!InternetSetOptionA` at `0x180096658`
- `WININET!InternetSetOptionA` at `0x18009667b`
- `WININET!InternetSetOptionA` at `0x180096695`
- `WININET!InternetSetOptionA` at `0x1800966be`
- `WININET!InternetSetOptionA` at `0x1800966da`
- `WININET!InternetSetOptionA` at `0x1800966f6`
- `WININET!InternetSetOptionA` at `0x18009671e`
- `WININET!InternetSetOptionA` at `0x180096759`
- `WININET!InternetSetOptionA` at `0x18009677c`
- `WININET!InternetSetOptionA` at `0x1800967a1`
- `WININET!InternetSetOptionA` at `0x180096601`
- `WININET!InternetSetOptionA` at `0x18009661d`
- `WININET!InternetSetOptionA` at `0x180096658`
- `WININET!InternetSetOptionA` at `0x18009667b`
- `WININET!InternetSetOptionA` at `0x180096695`
- `WININET!InternetSetOptionA` at `0x1800966be`
- `WININET!InternetSetOptionA` at `0x1800966da`
- `WININET!InternetSetOptionA` at `0x1800966f6`
- `WININET!InternetSetOptionA` at `0x18009671e`
- `WININET!InternetSetOptionA` at `0x180096759`
- `WININET!InternetSetOptionA` at `0x18009677c`
- `WININET!InternetSetOptionA` at `0x1800967a1`
- `WININET!InternetOpenW` at `0x18009658f`
- `WININET!InternetOpenW` at `0x18009658f`

## pseudocode

```c
__int64 __fastcall CINetEdge::INetAsyncOpen(CINetEdge *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // r15d
  bool v6; // dl
  unsigned int v7; // edi
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  CINetEdge *v9; // rcx
  const WCHAR *UserAgentString; // rsi
  void *v11; // rsi
  DWORD LastError; // eax
  unsigned int v13; // eax
  CINetEdge *v14; // rcx
  unsigned int v15; // eax
  CINetEdge *v17; // [rsp+30h] [rbp-18h] BYREF
  char v18; // [rsp+38h] [rbp-10h]
  CINetEdge *Buffer; // [rsp+80h] [rbp+38h] BYREF
  int v20; // [rsp+88h] [rbp+40h] BYREF
  BOOL v21; // [rsp+90h] [rbp+48h] BYREF
  struct IInternetBindInfo *v22; // [rsp+98h] [rbp+50h] BYREF

  if ( (unsigned int)dword_180159000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180159000, 32) )
  {
    Buffer = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v2,
      byte_180145346,
      v3,
      v4,
      (__int64)&Buffer);
  }
  v5 = -2147467259;
  v17 = this;
  v18 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v17) )
  {
    v7 = 2;
    goto LABEL_46;
  }
  v7 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 1);
  if ( v7 != 1 )
  {
LABEL_46:
    v15 = CINetEdge::CheckTransitionStatusAndDispatchAbort(this, v7, v5);
    goto LABEL_47;
  }
  if ( !g_hSession )
  {
    v22 = 0;
    RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this, v6);
    Microsoft::WRL::ComPtr<IServiceProvider>::Attach(&v22, RefCountedBindInfo);
    EnterCriticalSection(&g_mxsSession);
    v9 = this;
    if ( !g_hSession )
    {
      CINetEdge::SetINetState(this, 2);
      UserAgentString = CINetEdge::GetUserAgentString(this, v22);
      if ( !UserAgentString )
        UserAgentString = GetCommonDefaultUserAgentW();
      InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
      if ( !byte_18015DE34 )
        CINetEdge::s_SetTransportTimeoutsAndMaxConnections();
      CINetEdge::CheckAndSetINetEdgeState((__int64)this, 2);
      v11 = InternetOpenW(UserAgentString, 0, 0, 0, 0x10000000u);
      if ( !v11 )
      {
        LastError = GetLastError();
        v5 = -2146697213;
        *((_DWORD *)this + 31) = -2146697213;
        CINetEdge::SetBindResult(this, LastError, -2146697213);
        v13 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 4);
LABEL_40:
        v7 = v13;
        LeaveCriticalSection(&g_mxsSession);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        goto LABEL_42;
      }
      LODWORD(Buffer) = 0x2000;
      g_fDoNotTrack = IsDoNotTrackEnabled();
      if ( g_fDoNotTrack )
        g_fDoNotTrackAllowExceptions = AreDoNotTrackExceptionsAllowed();
      InternetSetOptionA(0, 0x7Bu, &g_fDoNotTrack, 4u);
      if ( (unsigned int)IsSpartanApp() )
        InternetSetOptionA(0, 0xAFu, 0, 0);
      if ( ((unsigned int)IEConfiguration_GetDWORD(268435501) != 2 || (unsigned __int8)IEConfiguration_GetBool(536870914))
        && LCIEIsCurrentProcessInPrivate() )
      {
        InternetSetOptionA(0, 0xA4u, 0, 0);
      }
      InternetSetStatusCallbackA(v11, CINetEdge::CINetCallback);
      InternetSetOptionA(v11, 0x6Cu, 0, 0);
      InternetSetOptionA(v11, 0x2Du, &g_dwMagicContext, 8u);
      if ( (int)CFeatureControlKey::_CoInternetFeatureValueInternal(
                  (CFeatureControlKey *)&FCK::FEATURE_URLMON_IQDA_SIZE,
                  (unsigned int *)&Buffer) >= 0 )
        InternetSetOptionA(v11, 0x8Cu, &Buffer, 4u);
      if ( CINetEdge::s_IsInsecureSSL3FallbackDisabled() )
        InternetSetOptionA(0, 0xA0u, 0, 0);
      if ( IsBlockWeakCryptoEnabled() )
        InternetSetOptionA(0, 0xB0u, 0, 0);
      if ( CINetEdge::IsHTTP2EnabledForProcess(v14) )
      {
        CINetEdge::s_fEnableHTTP2 = 1;
        v20 = 2;
        InternetSetOptionA(v11, 0x94u, &v20, 4u);
      }
      if ( (unsigned int)IsABrowserApp() || g_enableHSTSForAppsInEdgeMode )
      {
        g_fHSTSEnabled = 1;
        InternetSetOptionA(v11, 0x9Du, &g_fHSTSEnabled, 4u);
      }
      else
      {
        g_fHSTSEnabled = 0;
      }
      v21 = g_experimentalNetworkFeatures;
      if ( g_experimentalNetworkFeatures )
        InternetSetOptionA(v11, 0xB4u, &v21, 4u);
      if ( g_enableEdgeCookies )
      {
        v20 = 1;
        InternetSetOptionA(v11, 0xA6u, &v20, 4u);
      }
      g_hSession = v11;
      v9 = this;
    }
    v13 = CINetEdge::CheckAndSetINetEdgeState((__int64)v9, 3);
    LOBYTE(v11) = 1;
    goto LABEL_40;
  }
  v7 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 3);
  LOBYTE(v11) = 1;
LABEL_42:
  if ( v7 != 1 )
    goto LABEL_46;
  if ( (_BYTE)v11 )
  {
    v15 = (*(__int64 (__fastcall **)(CINetEdge *))(*(_QWORD *)this + 232LL))(this);
LABEL_47:
    v5 = v15;
  }
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v17);
  return v5;
}

```

## disassembly

```asm
0x180096450  push    rbp
0x180096452  push    rbx
0x180096453  push    rsi
0x180096454  push    rdi
0x180096455  push    r14
0x180096457  push    r15
0x180096459  mov     rbp, rsp
0x18009645c  sub     rsp, 48h
0x180096460  mov     eax, cs:dword_180159000
0x180096466  mov     rbx, rcx
0x180096469  cmp     eax, 5
0x18009646c  jbe     short loc_18009649C
0x18009646e  mov     edx, 20h ; ' '
0x180096473  lea     rcx, dword_180159000
0x18009647a  call    _tlgKeywordOn
0x18009647f  test    al, al
0x180096481  jz      short loc_18009649C
0x180096483  lea     rax, [rbp+Buffer]
0x180096487  mov     [rbp+Buffer], rbx
0x18009648b  lea     rdx, byte_180145346
0x180096492  mov     qword ptr [rsp+48h+dwFlags], rax
0x180096497  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18009649c  mov     r15d, 80004005h
0x1800964a2  mov     [rbp+var_18], rbx
0x1800964a6  mov     [rbp+var_10], 0
0x1800964aa  lock inc dword ptr [rbx+4B0h]
0x1800964b1  lea     rcx, [rbp+var_18]; this
0x1800964b5  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x1800964ba  test    al, al
0x1800964bc  jz      loc_180096805
0x1800964c2  mov     edx, 1
0x1800964c7  mov     rcx, rbx
0x1800964ca  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800964cf  mov     edi, eax
0x1800964d1  cmp     eax, 1
0x1800964d4  jnz     loc_18009680A
0x1800964da  cmp     cs:?g_hSession@@3PEAXEA, 0; void * g_hSession
0x1800964e2  mov     rcx, rbx; this
0x1800964e5  jnz     loc_1800967D8
0x1800964eb  mov     [rbp+arg_18], 0
0x1800964f3  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x1800964f8  mov     rdx, rax
0x1800964fb  lea     rcx, [rbp+arg_18]
0x1800964ff  call    ?Attach@?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@QEAAXPEAUIServiceProvider@@@Z; Microsoft::WRL::ComPtr<IServiceProvider>::Attach(IServiceProvider *)
0x180096504  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x18009650b  call    cs:__imp_EnterCriticalSection
0x180096511  cmp     cs:?g_hSession@@3PEAXEA, 0; void * g_hSession
0x180096519  mov     rcx, rbx
0x18009651c  jnz     loc_1800967B1
0x180096522  mov     edi, 2
0x180096527  mov     edx, edi
0x180096529  call    ?SetINetState@CINetEdge@@IEAA?AW4INetState@@W42@@Z; CINetEdge::SetINetState(INetState)
0x18009652e  mov     rdx, [rbp+arg_18]; struct IInternetBindInfo *
0x180096532  mov     rcx, rbx; this
0x180096535  call    ?GetUserAgentString@CINetEdge@@IEAAPEAGPEAUIInternetBindInfo@@@Z; CINetEdge::GetUserAgentString(IInternetBindInfo *)
0x18009653a  mov     rsi, rax
0x18009653d  test    rax, rax
0x180096540  jnz     short loc_18009654A
0x180096542  call    ?GetCommonDefaultUserAgentW@@YAPEBGXZ; GetCommonDefaultUserAgentW(void)
0x180096547  mov     rsi, rax
0x18009654a  xor     r9d, r9d; Context
0x18009654d  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180096554  xor     r8d, r8d; Parameter
0x180096557  lea     rcx, stru_18015EA38; InitOnce
0x18009655e  call    cs:__imp_InitOnceExecuteOnce
0x180096564  cmp     cs:byte_18015DE34, 0
0x18009656b  jnz     short loc_180096572
0x18009656d  call    ?s_SetTransportTimeoutsAndMaxConnections@CINetEdge@@SAXXZ; CINetEdge::s_SetTransportTimeoutsAndMaxConnections(void)
0x180096572  mov     edx, edi
0x180096574  mov     rcx, rbx
0x180096577  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x18009657c  xor     r9d, r9d; lpszProxyBypass
0x18009657f  mov     [rsp+48h+dwFlags], 10000000h; dwFlags
0x180096587  xor     r8d, r8d; lpszProxy
0x18009658a  xor     edx, edx; dwAccessType
0x18009658c  mov     rcx, rsi; lpszAgent
0x18009658f  call    cs:__imp_InternetOpenW
0x180096595  mov     rsi, rax
0x180096598  test    rax, rax
0x18009659b  jnz     short loc_1800965CA
0x18009659d  call    cs:__imp_GetLastError
0x1800965a3  mov     r15d, 800C0003h
0x1800965a9  mov     rcx, rbx; this
0x1800965ac  mov     r8d, r15d; int
0x1800965af  mov     [rbx+7Ch], r15d
0x1800965b3  mov     edx, eax; unsigned int
0x1800965b5  call    ?SetBindResult@CINetEdge@@MEAAJKJ@Z; CINetEdge::SetBindResult(ulong,long)
0x1800965ba  lea     edx, [rsi+4]
0x1800965bd  mov     rcx, rbx
0x1800965c0  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800965c5  jmp     loc_1800967BE
0x1800965ca  mov     dword ptr [rbp+Buffer], 2000h
0x1800965d1  call    ?IsDoNotTrackEnabled@@YAHXZ; IsDoNotTrackEnabled(void)
0x1800965d6  mov     cs:?g_fDoNotTrack@@3HA, eax; int g_fDoNotTrack
0x1800965dc  test    eax, eax
0x1800965de  jz      short loc_1800965EB
0x1800965e0  call    ?AreDoNotTrackExceptionsAllowed@@YAHXZ; AreDoNotTrackExceptionsAllowed(void)
0x1800965e5  mov     cs:?g_fDoNotTrackAllowExceptions@@3HA, eax; int g_fDoNotTrackAllowExceptions
0x1800965eb  mov     r14d, 4
0x1800965f1  lea     r8, ?g_fDoNotTrack@@3HA; lpBuffer
0x1800965f8  mov     r9d, r14d; dwBufferLength
0x1800965fb  xor     ecx, ecx; hInternet
0x1800965fd  lea     edx, [r14+77h]; dwOption
0x180096601  call    cs:__imp_InternetSetOptionA
0x180096607  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x18009660c  test    eax, eax
0x18009660e  jz      short loc_180096623
0x180096610  xor     r9d, r9d; dwBufferLength
0x180096613  xor     r8d, r8d; lpBuffer
0x180096616  mov     edx, 0AFh; dwOption
0x18009661b  xor     ecx, ecx; hInternet
0x18009661d  call    cs:__imp_InternetSetOptionA
0x180096623  mov     ecx, 1000002Dh
0x180096628  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18009662e  cmp     eax, edi
0x180096630  jnz     short loc_180096641
0x180096632  mov     ecx, 20000002h
0x180096637  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18009663d  test    al, al
0x18009663f  jz      short loc_18009665E
0x180096641  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180096647  test    al, al
0x180096649  jz      short loc_18009665E
0x18009664b  xor     r9d, r9d; dwBufferLength
0x18009664e  xor     r8d, r8d; lpBuffer
0x180096651  mov     edx, 0A4h; dwOption
0x180096656  xor     ecx, ecx; hInternet
0x180096658  call    cs:__imp_InternetSetOptionA
0x18009665e  lea     rdx, ?CINetCallback@CINetEdge@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x180096665  mov     rcx, rsi; hInternet
0x180096668  call    cs:__imp_InternetSetStatusCallbackA
0x18009666e  xor     r9d, r9d; dwBufferLength
0x180096671  xor     r8d, r8d; lpBuffer
0x180096674  mov     rcx, rsi; hInternet
0x180096677  lea     edx, [r9+6Ch]; dwOption
0x18009667b  call    cs:__imp_InternetSetOptionA
0x180096681  mov     r9d, 8; dwBufferLength
0x180096687  lea     r8, ?g_dwMagicContext@@3_KB; lpBuffer
0x18009668e  mov     rcx, rsi; hInternet
0x180096691  lea     edx, [r9+25h]; dwOption
0x180096695  call    cs:__imp_InternetSetOptionA
0x18009669b  lea     rdx, [rbp+Buffer]; unsigned int *
0x18009669f  lea     rcx, ?FEATURE_URLMON_IQDA_SIZE@FCK@@3VCFeatureControlKey@@A; this
0x1800966a6  call    ?_CoInternetFeatureValueInternal@CFeatureControlKey@@QEAAJPEAK@Z; CFeatureControlKey::_CoInternetFeatureValueInternal(ulong *)
0x1800966ab  test    eax, eax
0x1800966ad  js      short loc_1800966C4
0x1800966af  mov     r9d, r14d; dwBufferLength
0x1800966b2  lea     r8, [rbp+Buffer]; lpBuffer
0x1800966b6  mov     edx, 8Ch; dwOption
0x1800966bb  mov     rcx, rsi; hInternet
0x1800966be  call    cs:__imp_InternetSetOptionA
0x1800966c4  call    ?s_IsInsecureSSL3FallbackDisabled@CINetEdge@@KA_NXZ; CINetEdge::s_IsInsecureSSL3FallbackDisabled(void)
0x1800966c9  test    al, al
0x1800966cb  jz      short loc_1800966E0
0x1800966cd  xor     r9d, r9d; dwBufferLength
0x1800966d0  xor     r8d, r8d; lpBuffer
0x1800966d3  mov     edx, 0A0h; dwOption
0x1800966d8  xor     ecx, ecx; hInternet
0x1800966da  call    cs:__imp_InternetSetOptionA
0x1800966e0  call    ?IsBlockWeakCryptoEnabled@@YA_NXZ; IsBlockWeakCryptoEnabled(void)
0x1800966e5  test    al, al
0x1800966e7  jz      short loc_1800966FC
0x1800966e9  xor     r9d, r9d; dwBufferLength
0x1800966ec  xor     r8d, r8d; lpBuffer
0x1800966ef  mov     edx, 0B0h; dwOption
0x1800966f4  xor     ecx, ecx; hInternet
0x1800966f6  call    cs:__imp_InternetSetOptionA
0x1800966fc  call    ?IsHTTP2EnabledForProcess@CINetEdge@@IEAA_NXZ; CINetEdge::IsHTTP2EnabledForProcess(void)
0x180096701  test    al, al
0x180096703  jz      short loc_180096724
0x180096705  mov     r9d, r14d; dwBufferLength
0x180096708  mov     cs:?s_fEnableHTTP2@CINetEdge@@1_NA, 1; bool CINetEdge::s_fEnableHTTP2
0x18009670f  lea     r8, [rbp+arg_8]; lpBuffer
0x180096713  mov     [rbp+arg_8], edi
0x180096716  mov     edx, 94h; dwOption
0x18009671b  mov     rcx, rsi; hInternet
0x18009671e  call    cs:__imp_InternetSetOptionA
0x180096724  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x180096729  test    eax, eax
0x18009672b  jnz     short loc_18009673D
0x18009672d  cmp     cs:?g_enableHSTSForAppsInEdgeMode@@3_NA, al; bool g_enableHSTSForAppsInEdgeMode
0x180096733  jnz     short loc_18009673D
0x180096735  mov     cs:?g_fHSTSEnabled@@3HA, eax; int g_fHSTSEnabled
0x18009673b  jmp     short loc_18009675F
0x18009673d  mov     r9d, r14d; dwBufferLength
0x180096740  mov     cs:?g_fHSTSEnabled@@3HA, 1; int g_fHSTSEnabled
0x18009674a  lea     r8, ?g_fHSTSEnabled@@3HA; lpBuffer
0x180096751  mov     edx, 9Dh; dwOption
0x180096756  mov     rcx, rsi; hInternet
0x180096759  call    cs:__imp_InternetSetOptionA
0x18009675f  movzx   eax, cs:?g_experimentalNetworkFeatures@@3_NA; bool g_experimentalNetworkFeatures
0x180096766  mov     [rbp+arg_10], eax
0x180096769  test    eax, eax
0x18009676b  jz      short loc_180096782
0x18009676d  mov     r9d, r14d; dwBufferLength
0x180096770  lea     r8, [rbp+arg_10]; lpBuffer
0x180096774  mov     edx, 0B4h; dwOption
0x180096779  mov     rcx, rsi; hInternet
0x18009677c  call    cs:__imp_InternetSetOptionA
0x180096782  cmp     cs:?g_enableEdgeCookies@@3_NA, 0; bool g_enableEdgeCookies
0x180096789  jz      short loc_1800967A7
0x18009678b  mov     r9d, r14d; dwBufferLength
0x18009678e  mov     [rbp+arg_8], 1
0x180096795  lea     r8, [rbp+arg_8]; lpBuffer
0x180096799  mov     edx, 0A6h; dwOption
0x18009679e  mov     rcx, rsi; hInternet
0x1800967a1  call    cs:__imp_InternetSetOptionA
0x1800967a7  mov     cs:?g_hSession@@3PEAXEA, rsi; void * g_hSession
0x1800967ae  mov     rcx, rbx
0x1800967b1  mov     edx, 3
0x1800967b6  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800967bb  mov     sil, 1
0x1800967be  lea     rcx, ?g_mxsSession@@3VCMutexSem@@A; lpCriticalSection
0x1800967c5  mov     edi, eax
0x1800967c7  call    cs:__imp_LeaveCriticalSection
0x1800967cd  lea     rcx, [rbp+arg_18]
0x1800967d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800967d6  jmp     short loc_1800967E7
0x1800967d8  mov     edx, 3
0x1800967dd  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x1800967e2  mov     edi, eax
0x1800967e4  mov     sil, 1
0x1800967e7  cmp     edi, 1
0x1800967ea  jnz     short loc_18009680A
0x1800967ec  test    sil, sil
0x1800967ef  jz      short loc_18009681A
0x1800967f1  mov     rax, [rbx]
0x1800967f4  mov     rcx, rbx
0x1800967f7  mov     rax, [rax+0E8h]
0x1800967fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096803  jmp     short loc_180096817
0x180096805  mov     edi, 2
0x18009680a  mov     r8d, r15d
0x18009680d  mov     edx, edi
0x18009680f  mov     rcx, rbx
0x180096812  call    ?CheckTransitionStatusAndDispatchAbort@CINetEdge@@IEAAJW4INetEdgeStateTransition@@J@Z; CINetEdge::CheckTransitionStatusAndDispatchAbort(INetEdgeStateTransition,long)
0x180096817  mov     r15d, eax
0x18009681a  lea     rcx, [rbp+var_18]; this
0x18009681e  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x180096823  mov     eax, r15d
0x180096826  add     rsp, 48h
0x18009682a  pop     r15
0x18009682c  pop     r14
0x18009682e  pop     rdi
0x18009682f  pop     rsi
0x180096830  pop     rbx
0x180096831  pop     rbp
0x180096832  retn
```
