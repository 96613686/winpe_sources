# WnsListener::Start(void)

- ea: `0x18009e070`
- end: `0x18009e962`
- name: `?Start@WnsListener@@UEAAXXZ`
- size: `2290`
- prototype: `void __fastcall(WnsListener *__hidden this)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002c10`
- `0x180004738`
- `0x18000b7a4`
- `0x18000c70c`
- `0x180012dc0`
- `0x180013b50`
- `0x180017654`
- `0x1800369e4`
- `0x180040b08`
- `0x180046f88`
- `0x180054f0c`
- `0x180054f48`
- `0x180055154`
- `0x1800556e8`
- `0x180055b04`
- `0x180058a98`
- `0x1800593bc`
- `0x18006f1d0`
- `0x1800721e0`
- `0x180075e60`
- `0x1800767e0`
- `0x18008a400`
- `0x18008dc00`
- `0x18009c770`
- `0x18009c7dc`
- `0x18009cd50`
- `0x18009ce80`
- `0x18009cea8`
- `0x18009d06c`
- `0x18009e070`
- `0x18009e968`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e0e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e0e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e84d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e84d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009e5cd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009e5cd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009e3d4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009e4e4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009e3d4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18009e4e4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009e2a1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18009e2a1`

## string_xrefs

- `0x18009e157`: `!_leaseUriRetryTimer.IsValid()`
- `0x18009e1cc`: `_uri.empty()`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall WnsListener::Start(WnsListener *this)
{
  _BYTE *v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // r12
  void *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax
  const char *v7; // r9
  void *v8; // rax
  int v9; // r13d
  int v10; // eax
  int v11; // eax
  HRESULT v12; // eax
  wil *v13; // rbx
  __int64 (__fastcall *v14)(wil *, GUID *, int *); // rdi
  int v15; // eax
  int v16; // eax
  HRESULT v17; // eax
  int v18; // eax
  _QWORD *v19; // rax
  DWORD v20; // eax
  const char *v21; // r9
  __int64 v22; // rcx
  wil *v23; // rcx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  IUnknown *v27; // rcx
  __int128 *v28; // r9
  const char *v29; // r9
  int TokenType; // [rsp+20h] [rbp-188h]
  int TokenTypea; // [rsp+20h] [rbp-188h]
  int TokenTypeb; // [rsp+20h] [rbp-188h]
  IUnknown *pProxy; // [rsp+40h] [rbp-168h] BYREF
  int v34[2]; // [rsp+48h] [rbp-160h] BYREF
  __int64 v35; // [rsp+50h] [rbp-158h] BYREF
  wil *v36; // [rsp+58h] [rbp-150h] BYREF
  __int64 v37; // [rsp+60h] [rbp-148h] BYREF
  __int64 v38; // [rsp+68h] [rbp-140h] BYREF
  void **v39; // [rsp+70h] [rbp-138h] BYREF
  void *phNewToken; // [rsp+78h] [rbp-130h] BYREF
  struct _RTL_CRITICAL_SECTION *v41; // [rsp+80h] [rbp-128h]
  __int64 v42; // [rsp+88h] [rbp-120h] BYREF
  void **v43; // [rsp+90h] [rbp-118h] BYREF
  void *phNewTimer; // [rsp+98h] [rbp-110h] BYREF
  _BYTE *v45; // [rsp+A0h] [rbp-108h]
  WnsListener *v46; // [rsp+A8h] [rbp-100h]
  struct ActiveLease *v47[4]; // [rsp+B0h] [rbp-F8h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-D8h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-C8h]
  unsigned __int64 v50; // [rsp+E8h] [rbp-C0h]
  char *v51; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v52[32]; // [rsp+F8h] [rbp-B0h] BYREF
  _QWORD v53[4]; // [rsp+118h] [rbp-90h] BYREF
  _BYTE v54[12]; // [rsp+138h] [rbp-70h] BYREF
  char *v55; // [rsp+144h] [rbp-64h]
  _BYTE v56[32]; // [rsp+150h] [rbp-58h] BYREF
  __int64 v57; // [rsp+170h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v46 = this;
  v38 = 0;
  v37 = 0;
  v2 = (char *)this + 188;
  v45 = (char *)this + 188;
  if ( !*((_BYTE *)this + 188) )
  {
    GetActiveServiceMonitoredLeases(v47);
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    v41 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v47[3] = (WnsListener *)((char *)this + 16);
    if ( !*v2 )
    {
      if ( *((_QWORD *)this + 11) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x156u,
          "WnsListener::Start",
          (wchar_t *)L"Assert (%s): %s",
          L"0",
          L"_appEndpoint == nullptr");
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      if ( *((_QWORD *)this + 10) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x157u,
          "WnsListener::Start",
          (wchar_t *)L"Assert (%s): %s",
          L"0",
          L"!_leaseUriRetryTimer.IsValid()");
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      if ( *((_QWORD *)this + 18) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x158u,
          "WnsListener::Start",
          (wchar_t *)L"Assert (%s): %s",
          L"0",
          L"_channelId.empty()");
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      if ( *((_QWORD *)this + 14) )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x159u,
          "WnsListener::Start",
          (wchar_t *)L"Assert (%s): %s",
          L"0",
          L"_uri.empty()");
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      *((_BYTE *)this + 189) = 1;
      v39 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      v4 = 0;
      phNewToken = 0;
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((v47[1] - v47[0]) >> 3) )
      {
        ActiveLease::ActiveLease((ActiveLease *)v56, v47[0]);
        v5 = v57;
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v57 + 40LL))(v57) )
        {
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
          if ( !DuplicateTokenEx(
                  *(HANDLE *)(v6 + 8),
                  0x2000Eu,
                  0,
                  SecurityImpersonation,
                  TokenImpersonation,
                  &phNewToken) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x176,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
              v7);
        }
        ActiveLease::~ActiveLease((ActiveLease *)v56);
        v4 = phNewToken;
      }
      v42 = 0;
      if ( v4 )
      {
        v8 = operator new(1u);
        v35 = 0;
        v42 = ThreadTokenScope::ThreadTokenScope(v8, &v39);
        std::unique_ptr<ThreadTokenScope>::~unique_ptr<ThreadTokenScope>(&v35);
      }
      WnsListener::CreateWpnObjects(v4, &v38, &v37);
      try
      {
        v48 = 0;
        v49 = 0;
        v50 = 7;
        LOWORD(v48) = 0;
        pProxy = 0;
        v9 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v37 + 24LL))(
                v37,
                L"Microsoft.Windows.StoreLicenseManager_cw5n1h2txyewy",
                L"3ed497c5-2c9c-41cc-9288-63a5564e901d",
                2304);
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x18F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v10,
            0);
        v11 = (*(__int64 (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v38 + 24LL))(v38, &pProxy);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x191,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v11,
            0);
        v12 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x192,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v12,
            TokenType);
        MakeCom<WnsChannelRequest,>(&v36);
        *(_QWORD *)v34 = 0;
        v13 = v36;
        v14 = **(__int64 (__fastcall ***)(wil *, GUID *, int *))v36;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
        v15 = v14(v13, &GUID_bc0d0f9f_ecd0_4545_b41e_6df5f379bde0, v34);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x196,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v15,
            TokenType);
        v16 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
                pProxy,
                L"Microsoft.Windows.StoreLicenseManager_cw5n1h2txyewy",
                L"3ed497c5-2c9c-41cc-9288-63a5564e901d",
                *(_QWORD *)v34);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x198,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v16,
            TokenType);
        WnsChannelRequest::WaitForResults(v36, &v51);
        if ( (int)v55 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x19A,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v55,
            TokenType);
        if ( (int)v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x19C,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v51,
            TokenType);
        MakeCom<WnsNotificationSink,>(&v35);
        v17 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x19F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v17,
            TokenTypea);
        v18 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, __int64))pProxy->lpVtbl[2].AddRef)(
                pProxy,
                L"Microsoft.Windows.StoreLicenseManager_cw5n1h2txyewy",
                L"3ed497c5-2c9c-41cc-9288-63a5564e901d",
                v35);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            (const char *)(unsigned int)v18,
            TokenTypea);
        v19 = v53;
        if ( v53[3] > 7u )
          v19 = (_QWORD *)v53[0];
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          0x1A1u,
          "WnsListener::Start",
          (wchar_t *)L"Listening for WNS at %s",
          v19);
        std::wstring::operator=(&v48, v52);
        v20 = WnsListener::CalculateTimeToRefreshInMSFromExpirationTime((const struct _WPN_FILE_TIME *)v54);
        v43 = &Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::`vftable';
        phNewTimer = 0;
        if ( !CreateTimerQueueTimer(&phNewTimer, 0, WnsListener::_RegisterChannelTimerCallback, 0, v20, 0, 0x20u) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            v21);
        Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=((char *)this + 88, &pProxy);
        std::wstring::operator=((char *)this + 128, v52);
        std::wstring::operator=((char *)this + 96, v53);
        Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::operator=((char *)this + 56, &v43);
        std::vector<ActiveLease>::operator=((char *)this + 160, v47);
        *((_BYTE *)this + 188) = 1;
        if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 21) - *((_QWORD *)this + 20)) >> 3) )
        {
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
            0x1B8u,
            "WnsListener::Start",
            (wchar_t *)L"Queuing registration of %d leases with WNS");
          WnsListener::ResetLeaseCallbackRegistrationTimer(this, 0);
        }
        v43 = &Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v43);
        v22 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        WnsChannelRequest::Results::~Results((WnsChannelRequest::Results *)&v51);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
        v23 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(wil *))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
      catch ( ... )
      {
        v34[0] = wil::ResultFromCaughtException(v23);
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1BF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          v29);
        v9 = v34[0];
        if ( v34[0] < 0 )
        {
          if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
          {
            v34[0] = v9;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v24,
              (unsigned int)&byte_1800D8577,
              v25,
              v26,
              (__int64)v34);
          }
          if ( !*v45 )
            WnsListener::ScheduleChannelRetryTimerForError(v46, v9);
        }
        v3 = v41;
      }
      v27 = pProxy;
      if ( pProxy )
      {
        ((void (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, _QWORD))pProxy->lpVtbl[2].AddRef)(
          pProxy,
          L"Microsoft.Windows.StoreLicenseManager_cw5n1h2txyewy",
          L"3ed497c5-2c9c-41cc-9288-63a5564e901d",
          0);
        v27 = pProxy;
        if ( v49 )
        {
          v28 = &v48;
          if ( v50 > 7 )
            v28 = (__int128 *)v48;
          ((void (__fastcall *)(IUnknown *, const wchar_t *, const wchar_t *, __int128 *))pProxy->lpVtbl[1].AddRef)(
            pProxy,
            L"Microsoft.Windows.StoreLicenseManager_cw5n1h2txyewy",
            L"3ed497c5-2c9c-41cc-9288-63a5564e901d",
            v28);
          v27 = pProxy;
        }
      }
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1DA,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\wnslistener.cpp",
          (const char *)(unsigned int)v9,
          TokenTypeb);
      if ( v27 )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v27->lpVtbl->Release)(v27);
      }
      ContentIdString::~ContentIdString((ContentIdString *)&v48);
      std::unique_ptr<ThreadTokenScope>::~unique_ptr<ThreadTokenScope>(&v42);
      v39 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v39);
    }
    if ( v3 )
      LeaveCriticalSection(v3);
    std::vector<ActiveLease>::_Tidy(v47);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
}

```

## disassembly

```asm
0x18009e070  mov     [rsp+arg_8], rbx
0x18009e075  mov     [rsp+arg_10], rsi
0x18009e07a  push    rdi
0x18009e07b  push    r12
0x18009e07d  push    r13
0x18009e07f  push    r14
0x18009e081  push    r15
0x18009e083  sub     rsp, 180h
0x18009e08a  mov     rax, cs:__security_cookie
0x18009e091  xor     rax, rsp
0x18009e094  mov     [rsp+1A8h+var_30], rax
0x18009e09c  mov     r15, rcx
0x18009e09f  mov     [rsp+1A8h+var_100], rcx
0x18009e0a7  xor     esi, esi
0x18009e0a9  mov     [rsp+1A8h+var_140], rsi
0x18009e0ae  mov     [rsp+1A8h+var_148], rsi
0x18009e0b3  lea     rbx, [rcx+0BCh]
0x18009e0ba  mov     [rsp+1A8h+var_108], rbx
0x18009e0c2  cmp     [rbx], sil
0x18009e0c5  jnz     loc_18009E862
0x18009e0cb  lea     rcx, [rsp+1A8h+var_F8]
0x18009e0d3  call    ?GetActiveServiceMonitoredLeases@@YA?AV?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@XZ; GetActiveServiceMonitoredLeases(void)
0x18009e0d8  nop
0x18009e0d9  lea     r12, [r15+10h]
0x18009e0dd  mov     [rsp+1A8h+var_128], r12
0x18009e0e5  mov     rcx, r12; lpCriticalSection
0x18009e0e8  call    cs:__imp_EnterCriticalSection
0x18009e0ee  mov     [rsp+1A8h+var_E0], r12
0x18009e0f6  cmp     [rbx], sil
0x18009e0f9  jnz     loc_18009E845
0x18009e0ff  lea     rbx, a0; "0"
0x18009e106  lea     rdi, aAssertSS; "Assert (%s): %s"
0x18009e10d  lea     r14, aOnecoreuapEndu_23; "onecoreuap\\enduser\\winstore\\licensem"...
0x18009e114  lea     r13d, [rsi+1]
0x18009e118  cmp     [r15+58h], rsi
0x18009e11c  jz      short loc_18009E151
0x18009e11e  lea     rax, aAppendpointNul; "_appEndpoint == nullptr"
0x18009e125  mov     [rsp+1A8h+pAuthInfo], rax
0x18009e12a  mov     [rsp+1A8h+phNewToken], rbx
0x18009e12f  mov     qword ptr [rsp+1A8h+TokenType], rdi; Format
0x18009e134  lea     r9, aWnslistenerSta; "WnsListener::Start"
0x18009e13b  mov     r8d, 156h; unsigned int
0x18009e141  mov     rdx, r14; char *
0x18009e144  mov     ecx, r13d; unsigned int
0x18009e147  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18009e14c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e151  cmp     [r15+50h], rsi
0x18009e155  jz      short loc_18009E18A
0x18009e157  lea     rax, aLeaseuriretryt; "!_leaseUriRetryTimer.IsValid()"
0x18009e15e  mov     [rsp+1A8h+pAuthInfo], rax
0x18009e163  mov     [rsp+1A8h+phNewToken], rbx
0x18009e168  mov     qword ptr [rsp+1A8h+TokenType], rdi; Format
0x18009e16d  lea     r9, aWnslistenerSta; "WnsListener::Start"
0x18009e174  mov     r8d, 157h; unsigned int
0x18009e17a  mov     rdx, r14; char *
0x18009e17d  mov     ecx, r13d; unsigned int
0x18009e180  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18009e185  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e18a  cmp     [r15+90h], rsi
0x18009e191  jz      short loc_18009E1C6
0x18009e193  lea     rax, aChannelidEmpty; "_channelId.empty()"
0x18009e19a  mov     [rsp+1A8h+pAuthInfo], rax
0x18009e19f  mov     [rsp+1A8h+phNewToken], rbx
0x18009e1a4  mov     qword ptr [rsp+1A8h+TokenType], rdi; Format
0x18009e1a9  lea     r9, aWnslistenerSta; "WnsListener::Start"
0x18009e1b0  mov     r8d, 158h; unsigned int
0x18009e1b6  mov     rdx, r14; char *
0x18009e1b9  mov     ecx, r13d; unsigned int
0x18009e1bc  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18009e1c1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e1c6  cmp     [r15+70h], rsi
0x18009e1ca  jz      short loc_18009E1FF
0x18009e1cc  lea     rax, aUriEmpty; "_uri.empty()"
0x18009e1d3  mov     [rsp+1A8h+pAuthInfo], rax
0x18009e1d8  mov     [rsp+1A8h+phNewToken], rbx
0x18009e1dd  mov     qword ptr [rsp+1A8h+TokenType], rdi; Format
0x18009e1e2  lea     r9, aWnslistenerSta; "WnsListener::Start"
0x18009e1e9  mov     r8d, 159h; unsigned int
0x18009e1ef  mov     rdx, r14; char *
0x18009e1f2  mov     ecx, r13d; unsigned int
0x18009e1f5  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18009e1fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e1ff  mov     [r15+0BDh], r13b
0x18009e206  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18009e20d  mov     [rsp+1A8h+var_138], rax
0x18009e212  mov     rcx, rsi
0x18009e215  mov     [rsp+1A8h+var_130], rcx
0x18009e21a  mov     rax, [rsp+1A8h+var_F0]
0x18009e222  mov     rdx, [rsp+1A8h+var_F8]; struct ActiveLease *
0x18009e22a  sub     rax, rdx
0x18009e22d  sar     rax, 3
0x18009e231  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18009e23b  imul    rax, r8
0x18009e23f  test    rax, rax
0x18009e242  jz      loc_18009E2C9
0x18009e248  lea     rcx, [rsp+1A8h+var_58]; this
0x18009e250  call    ??0ActiveLease@@QEAA@AEBV0@@Z; ActiveLease::ActiveLease(ActiveLease const &)
0x18009e255  nop
0x18009e256  mov     rbx, [rsp+1A8h+var_38]
0x18009e25e  mov     rax, [rbx]
0x18009e261  mov     rcx, rbx
0x18009e264  mov     rax, [rax+28h]
0x18009e268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e26d  test    al, al
0x18009e26f  jz      short loc_18009E2B7
0x18009e271  mov     rax, [rbx]
0x18009e274  mov     rcx, rbx
0x18009e277  mov     rax, [rax+20h]
0x18009e27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e280  lea     rcx, [rsp+1A8h+var_130]
0x18009e285  mov     [rsp+1A8h+phNewToken], rcx; phNewToken
0x18009e28a  mov     r9d, 2; ImpersonationLevel
0x18009e290  mov     [rsp+1A8h+TokenType], r9d; TokenType
0x18009e295  xor     r8d, r8d; lpTokenAttributes
0x18009e298  mov     edx, 2000Eh; dwDesiredAccess
0x18009e29d  mov     rcx, [rax+8]; hExistingToken
0x18009e2a1  call    cs:__imp_DuplicateTokenEx
0x18009e2a7  mov     rcx, [rsp+1A8h]; this
0x18009e2af  test    eax, eax
0x18009e2b1  jz      loc_18009E8A4
0x18009e2b7  lea     rcx, [rsp+1A8h+var_58]; this
0x18009e2bf  call    ??1ActiveLease@@QEAA@XZ; ActiveLease::~ActiveLease(void)
0x18009e2c4  mov     rcx, [rsp+1A8h+var_130]
0x18009e2c9  mov     [rsp+1A8h+var_120], rsi
0x18009e2d1  test    rcx, rcx
0x18009e2d4  jz      short loc_18009E308
0x18009e2d6  mov     rcx, r13; Size
0x18009e2d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009e2de  mov     [rsp+1A8h+var_158], rax
0x18009e2e3  lea     rdx, [rsp+1A8h+var_138]
0x18009e2e8  mov     rcx, rax
0x18009e2eb  call    ??0ThreadTokenScope@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; ThreadTokenScope::ThreadTokenScope(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18009e2f0  nop
0x18009e2f1  mov     [rsp+1A8h+var_158], rsi
0x18009e2f6  mov     [rsp+1A8h+var_120], rax
0x18009e2fe  lea     rcx, [rsp+1A8h+var_158]
0x18009e303  call    ??1?$unique_ptr@VThreadTokenScope@@U?$default_delete@VThreadTokenScope@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadTokenScope>::~unique_ptr<ThreadTokenScope>(void)
0x18009e308  lea     r8, [rsp+1A8h+var_148]
0x18009e30d  lea     rdx, [rsp+1A8h+var_140]
0x18009e312  call    ?CreateWpnObjects@WnsListener@@AEAAXAEAV?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@AEAV?$ComPtr@UIWpnSystemRegistrationEndpoint@@@34@@Z; WnsListener::CreateWpnObjects(Microsoft::WRL::ComPtr<IWpnPlatform> &,Microsoft::WRL::ComPtr<IWpnSystemRegistrationEndpoint> &)
0x18009e317  xorps   xmm0, xmm0
0x18009e31a  movups  [rsp+1A8h+var_D8], xmm0
0x18009e322  mov     [rsp+1A8h+var_C8], rsi
0x18009e32a  mov     [rsp+1A8h+var_C0], 7
0x18009e336  mov     word ptr [rsp+1A8h+var_D8], si
0x18009e33e  mov     [rsp+1A8h+pProxy], rsi
0x18009e343  mov     r13d, esi
0x18009e346  mov     rcx, [rsp+1A8h+var_148]
0x18009e34b  mov     rax, [rcx]
0x18009e34e  mov     [rsp+1A8h+phNewToken], rsi
0x18009e353  mov     [rsp+1A8h+TokenType], esi; int
0x18009e357  mov     r9d, 900h
0x18009e35d  lea     r8, a3ed497c52c9c41; "3ed497c5-2c9c-41cc-9288-63a5564e901d"
0x18009e364  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.StoreLicenseManager_c"...
0x18009e36b  mov     rax, [rax+18h]
0x18009e36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e374  mov     rcx, [rsp+1A8h]; this
0x18009e37c  test    eax, eax
0x18009e37e  js      loc_18009E8B2
0x18009e384  mov     rcx, [rsp+1A8h+var_140]
0x18009e389  mov     rax, [rcx]
0x18009e38c  lea     rdx, [rsp+1A8h+pProxy]
0x18009e391  mov     rax, [rax+18h]
0x18009e395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e39a  mov     rcx, [rsp+1A8h]; this
0x18009e3a2  test    eax, eax
0x18009e3a4  js      loc_18009E8C2
0x18009e3aa  mov     [rsp+1A8h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18009e3b2  mov     [rsp+1A8h+pAuthInfo], rsi; pAuthInfo
0x18009e3b7  mov     dword ptr [rsp+1A8h+phNewToken], 3; dwImpLevel
0x18009e3bf  mov     [rsp+1A8h+TokenType], esi; int
0x18009e3c3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18009e3c7  or      eax, 0FFFFFFFFh
0x18009e3ca  mov     r8d, eax; dwAuthzSvc
0x18009e3cd  mov     edx, eax; dwAuthnSvc
0x18009e3cf  mov     rcx, [rsp+1A8h+pProxy]; pProxy
0x18009e3d4  call    cs:__imp_CoSetProxyBlanket
0x18009e3da  mov     rcx, [rsp+1A8h]; this
0x18009e3e2  test    eax, eax
0x18009e3e4  js      loc_18009E8D2
0x18009e3ea  lea     rcx, [rsp+1A8h+var_150]
0x18009e3ef  call    ??$MakeCom@VWnsChannelRequest@@$$V@@YA?AV?$ComPtr@VWnsChannelRequest@@@WRL@Microsoft@@XZ; MakeCom<WnsChannelRequest,>(void)
0x18009e3f4  nop
0x18009e3f5  mov     qword ptr [rsp+1A8h+var_160], rsi
0x18009e3fa  mov     rbx, [rsp+1A8h+var_150]
0x18009e3ff  mov     rax, [rbx]
0x18009e402  mov     rdi, [rax]
0x18009e405  lea     rcx, [rsp+1A8h+var_160]
0x18009e40a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e40f  lea     r8, [rsp+1A8h+var_160]
0x18009e414  lea     rdx, _GUID_bc0d0f9f_ecd0_4545_b41e_6df5f379bde0
0x18009e41b  mov     rcx, rbx
0x18009e41e  mov     rax, rdi
0x18009e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e426  nop
0x18009e427  mov     rcx, [rsp+1A8h]; this
0x18009e42f  test    eax, eax
0x18009e431  js      loc_18009E8E3
0x18009e437  mov     rcx, [rsp+1A8h+pProxy]
0x18009e43c  mov     rax, [rcx]
0x18009e43f  mov     r9, qword ptr [rsp+1A8h+var_160]
0x18009e444  lea     r8, a3ed497c52c9c41; "3ed497c5-2c9c-41cc-9288-63a5564e901d"
0x18009e44b  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.StoreLicenseManager_c"...
0x18009e452  mov     rax, [rax+18h]
0x18009e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e45b  mov     rcx, [rsp+1A8h]; this
0x18009e463  test    eax, eax
0x18009e465  js      loc_18009E8F3
0x18009e46b  lea     rdx, [rsp+1A8h+var_B8]
0x18009e473  mov     rcx, [rsp+1A8h+var_150]
0x18009e478  call    ?WaitForResults@WnsChannelRequest@@QEAA?AVResults@1@XZ; WnsChannelRequest::WaitForResults(void)
0x18009e47d  nop
0x18009e47e  mov     r9d, dword ptr [rsp+1A8h+var_64]; char *
0x18009e486  mov     rcx, [rsp+1A8h]; this
0x18009e48e  test    r9d, r9d
0x18009e491  js      loc_18009E904
0x18009e497  mov     r9d, dword ptr [rsp+1A8h+var_B8]; char *
0x18009e49f  mov     rcx, [rsp+1A8h]; this
0x18009e4a7  test    r9d, r9d
0x18009e4aa  js      loc_18009E911
0x18009e4b0  lea     rcx, [rsp+1A8h+var_158]
0x18009e4b5  call    ??$MakeCom@VWnsNotificationSink@@$$V@@YA?AV?$ComPtr@VWnsNotificationSink@@@WRL@Microsoft@@XZ; MakeCom<WnsNotificationSink,>(void)
0x18009e4ba  nop
0x18009e4bb  mov     [rsp+1A8h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18009e4c3  mov     [rsp+1A8h+pAuthInfo], rsi; pAuthInfo
0x18009e4c8  mov     ebx, 3
0x18009e4cd  mov     dword ptr [rsp+1A8h+phNewToken], ebx; dwImpLevel
0x18009e4d1  mov     [rsp+1A8h+TokenType], esi; int
0x18009e4d5  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18009e4d9  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18009e4dc  mov     r8d, edx; dwAuthzSvc
0x18009e4df  mov     rcx, [rsp+1A8h+pProxy]; pProxy
0x18009e4e4  call    cs:__imp_CoSetProxyBlanket
0x18009e4ea  mov     rcx, [rsp+1A8h]; this
0x18009e4f2  test    eax, eax
0x18009e4f4  js      loc_18009E91F
0x18009e4fa  mov     rcx, [rsp+1A8h+pProxy]
0x18009e4ff  mov     rax, [rcx]
0x18009e502  mov     r9, [rsp+1A8h+var_158]
0x18009e507  lea     r8, a3ed497c52c9c41; "3ed497c5-2c9c-41cc-9288-63a5564e901d"
0x18009e50e  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.StoreLicenseManager_c"...
0x18009e515  mov     rax, [rax+38h]
0x18009e519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e51e  mov     rcx, [rsp+1A8h]; this
0x18009e526  test    eax, eax
0x18009e528  js      loc_18009E92F
0x18009e52e  lea     rax, [rsp+1A8h+var_90]
0x18009e536  cmp     [rsp+1A8h+var_78], 7
0x18009e53f  cmova   rax, [rsp+1A8h+var_90]
0x18009e548  mov     [rsp+1A8h+phNewToken], rax
0x18009e54d  lea     rax, aListeningForWn; "Listening for WNS at %s"
0x18009e554  mov     qword ptr [rsp+1A8h+TokenType], rax; Format
0x18009e559  lea     r9, aWnslistenerSta; "WnsListener::Start"
0x18009e560  mov     r8d, 1A1h; unsigned int
0x18009e566  mov     rdx, r14; char *
0x18009e569  mov     ecx, ebx; unsigned int
0x18009e56b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18009e570  lea     rdx, [rsp+1A8h+var_B0]
0x18009e578  lea     rcx, [rsp+1A8h+var_D8]
0x18009e580  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009e585  lea     rcx, [rsp+1A8h+var_70]; struct _WPN_FILE_TIME *
0x18009e58d  call    ?CalculateTimeToRefreshInMSFromExpirationTime@WnsListener@@CAKAEBU_WPN_FILE_TIME@@@Z; WnsListener::CalculateTimeToRefreshInMSFromExpirationTime(_WPN_FILE_TIME const &)
0x18009e592  lea     rdi, ??_7?$HandleT@UTimerQueueTimerTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::`vftable'
0x18009e599  mov     [rsp+1A8h+var_118], rdi
0x18009e5a1  mov     [rsp+1A8h+phNewTimer], rsi
0x18009e5a9  mov     dword ptr [rsp+1A8h+pAuthInfo], 20h ; ' '; Flags
0x18009e5b1  mov     dword ptr [rsp+1A8h+phNewToken], esi; Period
0x18009e5b5  mov     [rsp+1A8h+TokenType], eax; DueTime
0x18009e5b9  xor     r9d, r9d; Parameter
0x18009e5bc  lea     r8, ?_RegisterChannelTimerCallback@WnsListener@@CAXPEAXE@Z; Callback
0x18009e5c3  xor     edx, edx; TimerQueue
0x18009e5c5  lea     rcx, [rsp+1A8h+phNewTimer]; phNewTimer
0x18009e5cd  call    cs:__imp_CreateTimerQueueTimer
0x18009e5d3  mov     rcx, [rsp+1A8h]; this
0x18009e5db  test    eax, eax
0x18009e5dd  jz      loc_18009E940
0x18009e5e3  lea     rdx, [rsp+1A8h+pProxy]
0x18009e5e8  lea     rcx, [r15+58h]
0x18009e5ec  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x18009e5f1  lea     rcx, [r15+80h]
0x18009e5f8  lea     rdx, [rsp+1A8h+var_B0]
0x18009e600  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009e605  lea     rcx, [r15+60h]
0x18009e609  lea     rdx, [rsp+1A8h+var_90]
0x18009e611  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009e616  lea     rcx, [r15+38h]
0x18009e61a  lea     rdx, [rsp+1A8h+var_118]
0x18009e622  call    ??4?$HandleT@UTimerQueueTimerTraits@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<TimerQueueTimerTraits> &&)
0x18009e627  lea     rbx, [r15+0A0h]
0x18009e62e  lea     rdx, [rsp+1A8h+var_F8]
0x18009e636  mov     rcx, rbx
0x18009e639  call    ??4?$vector@VActiveLease@@V?$allocator@VActiveLease@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<ActiveLease>::operator=(std::vector<ActiveLease> &&)
0x18009e63e  mov     byte ptr [r15+0BCh], 1
0x18009e646  mov     rax, [rbx+8]
0x18009e64a  sub     rax, [rbx]
0x18009e64d  sar     rax, 3
0x18009e651  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18009e65b  imul    rax, rcx
0x18009e65f  test    rax, rax
0x18009e662  jz      short loc_18009E69A
  ... truncated ...
```
