# WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)

- ea: `0x18009545c`
- end: `0x180095918`
- name: `?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext, unsigned int, struct _WINHTTP_ASYNC_RESULT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098b14`

## callees

- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008baec`
- `0x18008bcc0`
- `0x18008c42c`
- `0x180095164`
- `0x18009545c`
- `0x180097698`
- `0x180097858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095831`
- `WINHTTP!WinHttpSetOption` at `0x180095827`
- `WINHTTP!WinHttpSetOption` at `0x180095827`
- `WINHTTP!WinHttpGetProxyResult` at `0x180095729`
- `WINHTTP!WinHttpGetProxyResult` at `0x180095729`

## string_xrefs

- `0x1800957e1`: `EventWriteWinhttpProxyNoMoreEntriesEvent`
- `0x1800957e8`: `Logger::WriteWinhttpProxyNoMoreEntriesEvent`
- `0x1800956d2`: `EventWriteWinhttpProxySendFailureEvent`
- `0x1800956d9`: `Logger::WriteWinhttpProxySendFailureEvent`
- `0x180095617`: `EventWriteWinhttpProxyWPADFailedEvent`
- `0x18009561e`: `Logger::WriteWinhttpProxyWPADFailedEvent`
- `0x180095770`: `EventWriteWinhttpProxyWPADSuccessEvent`
- `0x180095777`: `Logger::WriteWinhttpProxyWPADSuccessEvent`
- `0x180095569`: `EventWriteWinhttpProxyUnknownFailureEvent`
- `0x180095570`: `Logger::WriteWinhttpProxyUnknownFailureEvent`
- `0x1800958b6`: `EventWriteWinhttpProxySetForRequestEvent`
- `0x1800958bd`: `Logger::WriteWinhttpProxySetForRequestEvent`
- `0x18009578d`: `%s: Proxy configuration discovered: Proxy count: %d`
- `0x18009546b`: `WinHttpRequest::CompleteAutoProxySendRequest`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::CompleteAutoProxySendRequest(
        DWORD_PTR dwContext,
        unsigned int a2,
        struct _WINHTTP_ASYNC_RESULT *a3)
{
  signed int v6; // ebx
  const unsigned __int16 *WinHttpCallbackStatus; // r14
  const unsigned __int16 *WinHttpErrorResultName; // rbp
  unsigned int v9; // ecx
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  const WCHAR *v13; // rdx
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  unsigned int *v20; // rsi
  signed int ProxyResult; // eax
  __int64 v22; // rcx
  __int64 v23; // r9
  const wchar_t *v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // eax
  signed int LastError; // eax
  __int64 v29; // rcx
  const wchar_t *v30; // r8
  __int64 v31; // rdx
  const wchar_t *v32; // r9
  unsigned int v33; // eax
  int v34; // eax
  __int64 v36; // [rsp+30h] [rbp-48h]

  Logger::TraceVerbose(L"%s started", L"WinHttpRequest::CompleteAutoProxySendRequest");
  if ( a2 == 0x1000000 )
  {
    v20 = (unsigned int *)(dwContext + 72);
    ProxyResult = WinHttpGetProxyResult(
                    *(HINTERNET *)(*(_QWORD *)(dwContext + 120) + 8LL),
                    (WINHTTP_PROXY_RESULT *)(dwContext + 72));
    v6 = ProxyResult;
    if ( ProxyResult > 0 )
      v6 = (unsigned __int16)ProxyResult | 0x80070000;
    if ( v6 < 0 )
    {
      v23 = (unsigned int)v6;
      v24 = L"WinHttpGetProxyResult";
      goto LABEL_74;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v25 = McTemplateU0q_EventWriteTransfer(v22, WinhttpProxyWPADSuccessEvent, *v20);
      if ( v25 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpProxyWPADSuccessEvent",
          L"EventWriteWinhttpProxyWPADSuccessEvent",
          v25);
    }
    Logger::TraceInformation(
      L"%s: Proxy configuration discovered: Proxy count: %d",
      L"WinHttpRequest::CompleteAutoProxySendRequest",
      *v20);
    if ( *v20 )
      *(_DWORD *)(dwContext + 64) = 1;
  }
  else
  {
    if ( !a3 )
    {
      v6 = -2147024809;
      Logger::TraceError(L"%s: Invalid arguments. Code: %d", L"WinHttpRequest::CompleteAutoProxySendRequest", a2);
      goto LABEL_75;
    }
    WinHttpCallbackStatus = WinHttpRequest::GetWinHttpCallbackStatus(a2);
    WinHttpErrorResultName = WinHttpRequest::GetWinHttpErrorResultName(*(_QWORD *)a3);
    if ( *(_QWORD *)a3 == 6 )
    {
      v9 = *((_DWORD *)a3 + 2);
      if ( v9 > 0x2EF1 )
      {
        if ( v9 != 12166 && v9 != 12167 && v9 != 12178 && v9 != 12180 )
          goto LABEL_12;
      }
      else if ( v9 != 12017 && v9 && v9 != 87 && v9 != 12002 && v9 != 12006 && v9 != 12015 )
      {
LABEL_12:
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
        {
          v10 = &base;
          v11 = &base;
          if ( WinHttpErrorResultName )
            v11 = WinHttpErrorResultName;
          if ( WinHttpCallbackStatus )
            v10 = WinHttpCallbackStatus;
          v12 = McTemplateU0qxqzz_EventWriteTransfer(
                  *((_DWORD *)a3 + 2),
                  (unsigned int)WinhttpProxyUnknownFailureEvent,
                  a2,
                  *(_QWORD *)a3,
                  *((_DWORD *)a3 + 2),
                  (__int64)v10,
                  (__int64)v11);
          if ( v12 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteWinhttpProxyUnknownFailureEvent",
              L"EventWriteWinhttpProxyUnknownFailureEvent",
              v12);
        }
        LODWORD(v36) = *((_DWORD *)a3 + 2);
        Logger::TraceError(
          L"%s: Unexpected error. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
          L"WinHttpRequest::CompleteAutoProxySendRequest",
          a2,
          WinHttpCallbackStatus,
          *(_QWORD *)a3,
          WinHttpErrorResultName,
          v36);
        v6 = -2147467259;
        goto LABEL_75;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v13 = &base;
        v14 = &base;
        if ( WinHttpErrorResultName )
          v14 = WinHttpErrorResultName;
        if ( WinHttpCallbackStatus )
          v13 = WinHttpCallbackStatus;
        v15 = McTemplateU0qxqzz_EventWriteTransfer(
                v9,
                (unsigned int)WinhttpProxyWPADFailedEvent,
                a2,
                6,
                v9,
                (__int64)v13,
                (__int64)v14);
        if ( v15 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpProxyWPADFailedEvent",
            L"EventWriteWinhttpProxyWPADFailedEvent",
            v15);
      }
      LODWORD(v36) = *((_DWORD *)a3 + 2);
      Logger::TraceInformation(
        L"%s: Proxy discovery did not find proxy. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
        L"WinHttpRequest::CompleteAutoProxySendRequest",
        a2,
        WinHttpCallbackStatus,
        *(_QWORD *)a3,
        WinHttpErrorResultName,
        v36);
    }
    else
    {
      if ( *(_QWORD *)a3 != 5
        || *((_DWORD *)a3 + 2) != 12002
        && *((_DWORD *)a3 + 2) != 12007
        && (unsigned int)(*((_DWORD *)a3 + 2) - 12029) > 1 )
      {
        goto LABEL_12;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v17 = &base;
        v18 = &base;
        if ( WinHttpErrorResultName )
          v18 = WinHttpErrorResultName;
        if ( WinHttpCallbackStatus )
          v17 = WinHttpCallbackStatus;
        v19 = McTemplateU0qxqzz_EventWriteTransfer(
                *((_DWORD *)a3 + 2),
                (unsigned int)WinhttpProxySendFailureEvent,
                a2,
                5,
                *((_DWORD *)a3 + 2),
                (__int64)v17,
                (__int64)v18);
        if ( v19 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpProxySendFailureEvent",
            L"EventWriteWinhttpProxySendFailureEvent",
            v19);
      }
      LODWORD(v36) = *((_DWORD *)a3 + 2);
      Logger::TraceError(
        L"%s: Proxy send error. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
        L"WinHttpRequest::CompleteAutoProxySendRequest",
        a2,
        WinHttpCallbackStatus,
        *(_QWORD *)a3,
        WinHttpErrorResultName,
        v36);
    }
  }
  if ( !*(_DWORD *)(dwContext + 64) )
  {
LABEL_72:
    v34 = WinHttpRequest::BeginSendRequest(dwContext);
    v6 = v34;
    if ( v34 >= 0 )
      goto LABEL_75;
    v23 = (unsigned int)v34;
    v24 = L"BeginSendRequest";
LABEL_74:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpRequest::CompleteAutoProxySendRequest",
      v24,
      v23);
    goto LABEL_75;
  }
  v26 = *(unsigned int *)(dwContext + 68);
  if ( *(_DWORD *)(dwContext + 72) > (unsigned int)v26 )
  {
    if ( !WinHttpSetOption(
            *(HINTERNET *)(dwContext + 8),
            0x27u,
            (LPVOID)(*(_QWORD *)(dwContext + 80) + 32 * v26),
            0x20u) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        v23 = (unsigned int)v6;
        v24 = L"WinHttpSetOption";
        goto LABEL_74;
      }
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v29 = *(_QWORD *)(dwContext + 80);
      v30 = L"TRUE";
      v31 = 32LL * *(unsigned int *)(dwContext + 68);
      v32 = L"TRUE";
      if ( !*(_DWORD *)(v31 + v29 + 4) )
        v32 = L"FALSE";
      if ( !*(_DWORD *)(v31 + v29) )
        v30 = L"FALSE";
      v33 = McTemplateU0zzqzq_EventWriteTransfer(
              v29,
              v31,
              (_DWORD)v30,
              (_DWORD)v32,
              *(_DWORD *)(v31 + v29 + 8),
              *(_QWORD *)(v31 + v29 + 16),
              *(_WORD *)(v31 + v29 + 24));
      if ( v33 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpProxySetForRequestEvent",
          L"EventWriteWinhttpProxySetForRequestEvent",
          v33);
    }
    ++*(_DWORD *)(dwContext + 68);
    goto LABEL_72;
  }
  v6 = -2147024637;
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v27 = McTemplateU0q_EventWriteTransfer(v16, WinhttpProxyNoMoreEntriesEvent, 2147942659LL);
    if ( v27 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteWinhttpProxyNoMoreEntriesEvent",
        L"EventWriteWinhttpProxyNoMoreEntriesEvent",
        v27);
  }
  Logger::TraceError(
    L"%s: No more out-bound proxy servers are available for this request.",
    L"WinHttpRequest::CompleteAutoProxySendRequest");
LABEL_75:
  Logger::TraceVerbose(L"%s finished", L"WinHttpRequest::CompleteAutoProxySendRequest");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009545c  push    rbx
0x18009545e  push    rbp
0x18009545f  push    rsi
0x180095460  push    rdi
0x180095461  push    r14
0x180095463  push    r15
0x180095465  sub     rsp, 48h
0x180095469  mov     esi, edx
0x18009546b  lea     r15, aWinhttprequest_15; "WinHttpRequest::CompleteAutoProxySendRe"...
0x180095472  mov     rdi, rcx
0x180095475  mov     rdx, r15
0x180095478  lea     rcx, aSStarted; "%s started"
0x18009547f  mov     rbx, r8
0x180095482  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180095487  cmp     esi, 1000000h
0x18009548d  jz      loc_18009571A
0x180095493  test    rbx, rbx
0x180095496  jnz     short loc_1800954B4
0x180095498  mov     r8d, esi
0x18009549b  lea     rcx, aSInvalidArgume; "%s: Invalid arguments. Code: %d"
0x1800954a2  mov     rdx, r15
0x1800954a5  mov     ebx, 80070057h
0x1800954aa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800954af  jmp     loc_1800958FA
0x1800954b4  mov     ecx, esi; unsigned int
0x1800954b6  call    ?GetWinHttpCallbackStatus@WinHttpRequest@@SAPEBGK@Z; WinHttpRequest::GetWinHttpCallbackStatus(ulong)
0x1800954bb  mov     rcx, [rbx]; unsigned __int64
0x1800954be  mov     r14, rax
0x1800954c1  call    ?GetWinHttpErrorResultName@WinHttpRequest@@SAPEBG_K@Z; WinHttpRequest::GetWinHttpErrorResultName(unsigned __int64)
0x1800954c6  mov     r9d, 6
0x1800954cc  mov     rbp, rax
0x1800954cf  cmp     [rbx], r9
0x1800954d2  jnz     loc_18009565F
0x1800954d8  mov     ecx, [rbx+8]
0x1800954db  mov     eax, 2EF1h
0x1800954e0  cmp     ecx, eax
0x1800954e2  ja      loc_1800955B6
0x1800954e8  jz      loc_1800955D2
0x1800954ee  mov     eax, ecx
0x1800954f0  test    ecx, ecx
0x1800954f2  jz      loc_1800955D2
0x1800954f8  sub     eax, 57h ; 'W'
0x1800954fb  jz      loc_1800955D2
0x180095501  sub     eax, 2E8Bh
0x180095506  jz      loc_1800955D2
0x18009550c  sub     eax, 4
0x18009550f  jz      loc_1800955D2
0x180095515  cmp     eax, 9
0x180095518  jz      loc_1800955D2
0x18009551e  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180095525  jz      short loc_180095583
0x180095527  mov     ecx, [rbx+8]
0x18009552a  lea     rdx, base
0x180095531  mov     r9, [rbx]
0x180095534  mov     rax, rdx
0x180095537  test    rbp, rbp
0x18009553a  mov     r8d, esi
0x18009553d  cmovnz  rax, rbp
0x180095541  test    r14, r14
0x180095544  mov     [rsp+78h+var_48], rax
0x180095549  cmovnz  rdx, r14
0x18009554d  mov     [rsp+78h+var_50], rdx
0x180095552  lea     rdx, WinhttpProxyUnknownFailureEvent
0x180095559  mov     dword ptr [rsp+78h+var_58], ecx
0x18009555d  call    McTemplateU0qxqzz_EventWriteTransfer
0x180095562  test    eax, eax
0x180095564  jz      short loc_180095583
0x180095566  mov     r9d, eax
0x180095569  lea     r8, aEventwritewinh_6; "EventWriteWinhttpProxyUnknownFailureEve"...
0x180095570  lea     rdx, aLoggerWritewin_12; "Logger::WriteWinhttpProxyUnknownFailure"...
0x180095577  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009557e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095583  mov     eax, [rbx+8]
0x180095586  lea     rcx, aSUnexpectedErr; "%s: Unexpected error. dwInternetStatus:"...
0x18009558d  mov     dword ptr [rsp+78h+var_48], eax
0x180095591  mov     r9, r14
0x180095594  mov     rax, [rbx]
0x180095597  mov     r8d, esi
0x18009559a  mov     [rsp+78h+var_50], rbp
0x18009559f  mov     rdx, r15
0x1800955a2  mov     [rsp+78h+var_58], rax
0x1800955a7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800955ac  mov     ebx, 80004005h
0x1800955b1  jmp     loc_1800958FA
0x1800955b6  mov     eax, ecx
0x1800955b8  sub     eax, 2F86h
0x1800955bd  jz      short loc_1800955D2
0x1800955bf  sub     eax, 1
0x1800955c2  jz      short loc_1800955D2
0x1800955c4  sub     eax, 0Bh
0x1800955c7  jz      short loc_1800955D2
0x1800955c9  cmp     eax, 2
0x1800955cc  jnz     loc_18009551E
0x1800955d2  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x1800955d9  jz      short loc_180095631
0x1800955db  lea     rdx, base
0x1800955e2  test    rbp, rbp
0x1800955e5  mov     rax, rdx
0x1800955e8  mov     r8d, esi
0x1800955eb  cmovnz  rax, rbp
0x1800955ef  test    r14, r14
0x1800955f2  mov     [rsp+78h+var_48], rax
0x1800955f7  cmovnz  rdx, r14
0x1800955fb  mov     [rsp+78h+var_50], rdx
0x180095600  lea     rdx, WinhttpProxyWPADFailedEvent
0x180095607  mov     dword ptr [rsp+78h+var_58], ecx
0x18009560b  call    McTemplateU0qxqzz_EventWriteTransfer
0x180095610  test    eax, eax
0x180095612  jz      short loc_180095631
0x180095614  mov     r9d, eax
0x180095617  lea     r8, aEventwritewinh_3; "EventWriteWinhttpProxyWPADFailedEvent"
0x18009561e  lea     rdx, aLoggerWritewin_10; "Logger::WriteWinhttpProxyWPADFailedEven"...
0x180095625  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18009562c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095631  mov     eax, [rbx+8]
0x180095634  lea     rcx, aSProxyDiscover; "%s: Proxy discovery did not find proxy."...
0x18009563b  mov     dword ptr [rsp+78h+var_48], eax
0x18009563f  mov     r9, r14
0x180095642  mov     rax, [rbx]
0x180095645  mov     r8d, esi
0x180095648  mov     [rsp+78h+var_50], rbp
0x18009564d  mov     rdx, r15
0x180095650  mov     [rsp+78h+var_58], rax
0x180095655  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009565a  jmp     loc_1800957A8
0x18009565f  mov     r9d, 5
0x180095665  cmp     [rbx], r9
0x180095668  jnz     loc_18009551E
0x18009566e  mov     ecx, [rbx+8]
0x180095671  mov     eax, ecx
0x180095673  sub     eax, 2EE2h
0x180095678  jz      short loc_18009568D
0x18009567a  sub     eax, r9d
0x18009567d  jz      short loc_18009568D
0x18009567f  sub     eax, 16h
0x180095682  jz      short loc_18009568D
0x180095684  cmp     eax, 1
0x180095687  jnz     loc_18009551E
0x18009568d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180095694  jz      short loc_1800956EC
0x180095696  lea     rdx, base
0x18009569d  test    rbp, rbp
0x1800956a0  mov     rax, rdx
0x1800956a3  mov     r8d, esi
0x1800956a6  cmovnz  rax, rbp
0x1800956aa  test    r14, r14
0x1800956ad  mov     [rsp+78h+var_48], rax
0x1800956b2  cmovnz  rdx, r14
0x1800956b6  mov     [rsp+78h+var_50], rdx
0x1800956bb  lea     rdx, WinhttpProxySendFailureEvent
0x1800956c2  mov     dword ptr [rsp+78h+var_58], ecx
0x1800956c6  call    McTemplateU0qxqzz_EventWriteTransfer
0x1800956cb  test    eax, eax
0x1800956cd  jz      short loc_1800956EC
0x1800956cf  mov     r9d, eax
0x1800956d2  lea     r8, aEventwritewinh_15; "EventWriteWinhttpProxySendFailureEvent"
0x1800956d9  lea     rdx, aLoggerWritewin_3; "Logger::WriteWinhttpProxySendFailureEve"...
0x1800956e0  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800956e7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800956ec  mov     eax, [rbx+8]
0x1800956ef  lea     rcx, aSProxySendErro; "%s: Proxy send error. dwInternetStatus:"...
0x1800956f6  mov     dword ptr [rsp+78h+var_48], eax
0x1800956fa  mov     r9, r14
0x1800956fd  mov     rax, [rbx]
0x180095700  mov     r8d, esi
0x180095703  mov     [rsp+78h+var_50], rbp
0x180095708  mov     rdx, r15
0x18009570b  mov     [rsp+78h+var_58], rax
0x180095710  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095715  jmp     loc_1800957A8
0x18009571a  mov     rcx, [rdi+78h]
0x18009571e  lea     rsi, [rdi+48h]
0x180095722  mov     rdx, rsi; pProxyResult
0x180095725  mov     rcx, [rcx+8]; hResolver
0x180095729  call    cs:__imp_WinHttpGetProxyResult
0x18009572f  mov     ebx, eax
0x180095731  test    eax, eax
0x180095733  jle     short loc_18009573E
0x180095735  movzx   ebx, ax
0x180095738  or      ebx, 80070000h
0x18009573e  test    ebx, ebx
0x180095740  jns     short loc_180095751
0x180095742  mov     r9d, ebx
0x180095745  lea     r8, aWinhttpgetprox_1; "WinHttpGetProxyResult"
0x18009574c  jmp     loc_1800958EB
0x180095751  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180095758  jz      short loc_18009578A
0x18009575a  mov     r8d, [rsi]
0x18009575d  lea     rdx, WinhttpProxyWPADSuccessEvent
0x180095764  call    McTemplateU0q_EventWriteTransfer
0x180095769  test    eax, eax
0x18009576b  jz      short loc_18009578A
0x18009576d  mov     r9d, eax
0x180095770  lea     r8, aEventwritewinh_9; "EventWriteWinhttpProxyWPADSuccessEvent"
0x180095777  lea     rdx, aLoggerWritewin_15; "Logger::WriteWinhttpProxyWPADSuccessEve"...
0x18009577e  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180095785  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009578a  mov     r8d, [rsi]
0x18009578d  lea     rcx, aSProxyConfigur; "%s: Proxy configuration discovered: Pro"...
0x180095794  mov     rdx, r15
0x180095797  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009579c  cmp     dword ptr [rsi], 0
0x18009579f  jbe     short loc_1800957A8
0x1800957a1  mov     dword ptr [rdi+40h], 1
0x1800957a8  cmp     dword ptr [rdi+40h], 0
0x1800957ac  jz      loc_1800958D3
0x1800957b2  mov     eax, [rdi+44h]
0x1800957b5  cmp     [rdi+48h], eax
0x1800957b8  ja      short loc_18009580F
0x1800957ba  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800957c1  mov     ebx, 80070103h
0x1800957c6  jz      short loc_1800957FB
0x1800957c8  mov     r8d, 80070103h
0x1800957ce  lea     rdx, WinhttpProxyNoMoreEntriesEvent
0x1800957d5  call    McTemplateU0q_EventWriteTransfer
0x1800957da  test    eax, eax
0x1800957dc  jz      short loc_1800957FB
0x1800957de  mov     r9d, eax
0x1800957e1  lea     r8, aEventwritewinh_0; "EventWriteWinhttpProxyNoMoreEntriesEven"...
0x1800957e8  lea     rdx, aLoggerWritewin_13; "Logger::WriteWinhttpProxyNoMoreEntriesE"...
0x1800957ef  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800957f6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800957fb  mov     rdx, r15
0x1800957fe  lea     rcx, aSNoMoreOutBoun; "%s: No more out-bound proxy servers are"...
0x180095805  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009580a  jmp     loc_1800958FA
0x18009580f  mov     rcx, [rdi+8]; hInternet
0x180095813  mov     edx, 27h ; '''; dwOption
0x180095818  mov     r8, rax
0x18009581b  shl     r8, 5
0x18009581f  add     r8, [rdi+50h]; lpBuffer
0x180095823  lea     r9d, [rdx-7]; dwBufferLength
0x180095827  call    cs:__imp_WinHttpSetOption
0x18009582d  test    eax, eax
0x18009582f  jnz     short loc_180095859
0x180095831  call    cs:__imp_GetLastError
0x180095837  mov     ebx, eax
0x180095839  test    eax, eax
0x18009583b  jle     short loc_180095846
0x18009583d  movzx   ebx, ax
0x180095840  or      ebx, 80070000h
0x180095846  test    ebx, ebx
0x180095848  jns     short loc_180095859
0x18009584a  mov     r9d, ebx
0x18009584d  lea     r8, aWinhttpsetopti_0; "WinHttpSetOption"
0x180095854  jmp     loc_1800958EB
0x180095859  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180095860  jz      short loc_1800958D0
0x180095862  mov     rcx, [rdi+50h]
0x180095866  lea     r10, aFalse_0; "FALSE"
0x18009586d  mov     edx, [rdi+44h]
0x180095870  lea     r8, aTrue_0; "TRUE"
0x180095877  shl     rdx, 5
0x18009587b  mov     r9, r8
0x18009587e  cmp     dword ptr [rdx+rcx+4], 0
0x180095883  movzx   eax, word ptr [rdx+rcx+18h]
0x180095888  mov     dword ptr [rsp+78h+var_48], eax
0x18009588c  cmovz   r9, r10
0x180095890  mov     rax, [rdx+rcx+10h]
0x180095895  cmp     dword ptr [rdx+rcx], 0
0x180095899  mov     [rsp+78h+var_50], rax
0x18009589e  mov     eax, [rdx+rcx+8]
0x1800958a2  cmovz   r8, r10
0x1800958a6  mov     dword ptr [rsp+78h+var_58], eax
0x1800958aa  call    McTemplateU0zzqzq_EventWriteTransfer
0x1800958af  test    eax, eax
0x1800958b1  jz      short loc_1800958D0
0x1800958b3  mov     r9d, eax
0x1800958b6  lea     r8, aEventwritewinh_13; "EventWriteWinhttpProxySetForRequestEven"...
0x1800958bd  lea     rdx, aLoggerWritewin_14; "Logger::WriteWinhttpProxySetForRequestE"...
0x1800958c4  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800958cb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800958d0  inc     dword ptr [rdi+44h]
0x1800958d3  mov     rcx, rdi; dwContext
0x1800958d6  call    ?BeginSendRequest@WinHttpRequest@@AEAAJXZ; WinHttpRequest::BeginSendRequest(void)
0x1800958db  mov     ebx, eax
0x1800958dd  test    eax, eax
0x1800958df  jns     short loc_1800958FA
0x1800958e1  mov     r9d, eax
0x1800958e4  lea     r8, aBeginsendreque; "BeginSendRequest"
0x1800958eb  mov     rdx, r15
0x1800958ee  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800958f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800958fa  mov     rdx, r15
0x1800958fd  lea     rcx, aSFinished; "%s finished"
0x180095904  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180095909  mov     eax, ebx
0x18009590b  add     rsp, 48h
0x18009590f  pop     r15
0x180095911  pop     r14
0x180095913  pop     rdi
0x180095914  pop     rsi
0x180095915  pop     rbp
0x180095916  pop     rbx
0x180095917  retn
```
