# WinHttpRequest::OnCallback(ulong,void *,ulong)

- ea: `0x180098b14`
- end: `0x1800990cd`
- name: `?OnCallback@WinHttpRequest@@IEAAJKPEAXK@Z`
- size: `1465`
- prototype: `__int64 __fastcall(WinHttpRequest *__hidden this, unsigned int, char *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180094f80`

## callees

- `0x180003c20`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008b2cc`
- `0x18008bb48`
- `0x18008bc04`
- `0x18008bdc8`
- `0x180095354`
- `0x1800953cc`
- `0x18009545c`
- `0x180097698`
- `0x180097858`
- `0x180097930`
- `0x180098b14`
- `0x18009bbec`
- `0x18009bc78`
- `0x18009be14`
- `0x18009beac`
- `0x18009bfec`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098e0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180098e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c16`
- `WINHTTP!WinHttpReceiveResponse` at `0x180098c08`
- `WINHTTP!WinHttpReceiveResponse` at `0x180098c08`

## string_xrefs

- `0x180098f37`: `EventWriteWinhttpSslFailureEvent`
- `0x180098f3e`: `Logger::WriteWinhttpSslFailureEvent`
- `0x180099062`: `EventWriteWinhttpCallbackFailureEvent`
- `0x180099069`: `Logger::WriteWinhttpCallbackFailureEvent`
- `0x180098fdf`: `EventWriteWinhttpCallbackCancelledEvent`
- `0x180098fe6`: `Logger::WriteWinhttpCallbackCancelledEvent`
- `0x180098d76`: `%s: WinHttpRequest::ReadDataTrigger failed with error code: 0x%08x`
- `0x180098cef`: `%s: Read complete. dwSize: %d`
- `0x180098d27`: `%s: WinHttpRequest::ReadDataComplete failed with error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::OnCallback(WinHttpRequest *this, unsigned int a2, char *a3, unsigned int a4)
{
  unsigned __int64 v8; // r8
  WinHttpRequest *v9; // rcx
  signed int v10; // eax
  signed int StatusCode; // ebx
  bool v12; // sf
  unsigned __int64 v13; // r8
  const wchar_t *WinHttpErrorResultName; // rax
  int v15; // edx
  __int64 v16; // r8
  DWORD v17; // ebx
  WinHttpRequest *v18; // rcx
  int v19; // edx
  int DataTrigger; // eax
  const unsigned __int16 *v21; // rcx
  _DWORD *v22; // r15
  void *v23; // rbp
  bool v24; // sf
  int Header; // eax
  int v26; // eax
  signed int v27; // ecx
  unsigned int v28; // ebx
  int WinhttpSslErrorCodeName; // eax
  int v30; // edx
  int v31; // ecx
  unsigned int v32; // eax
  const unsigned __int16 *WinHttpCallbackStatus; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  const WCHAR *v36; // r9
  unsigned int v37; // eax
  WinHttpRequest *v38; // rcx
  const unsigned __int16 *v39; // rax
  int v40; // edx
  const WCHAR *v41; // rcx
  unsigned int v42; // eax
  void *Block; // [rsp+30h] [rbp-468h] BYREF
  wchar_t Buffer[512]; // [rsp+40h] [rbp-458h] BYREF

  Logger::TraceVerbose(L"%s: dwInternetStatus = %lu", L"WinHttpRequest::OnCallback", a2);
  if ( *((_DWORD *)this + 4) )
  {
    Logger::TraceInformation(L"%s: m_requestCanceled is TRUE.", L"WinHttpRequest::OnCallback");
    WinHttpRequest::CleanupCancelledRequest(v9, a2, a3, a4);
    return 0;
  }
  switch ( a2 )
  {
    case 0x800u:
      (*(void (__fastcall **)(WinHttpRequest *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 40));
      return 0;
    case 0x4000u:
      DataTrigger = (*(__int64 (__fastcall **)(WinHttpRequest *, char *, _QWORD))(*(_QWORD *)this + 40LL))(
                      this,
                      a3,
                      2 * a4);
      StatusCode = DataTrigger;
      if ( DataTrigger >= 0 )
        goto LABEL_78;
      v21 = L"%s: WinHttpRequest::OnRedirect failed with error code: 0x%08x";
      goto LABEL_77;
    case 0x10000u:
      v27 = *(_DWORD *)a3;
      *((_DWORD *)this + 39) = *(_DWORD *)a3;
      if ( (v27 & 2) != 0 )
      {
        v28 = 12169;
      }
      else if ( (v27 & 8) != 0 )
      {
        v28 = 12045;
      }
      else if ( (v27 & 0x10) != 0 )
      {
        v28 = 12038;
      }
      else if ( (v27 & 0x20) != 0 )
      {
        v28 = 12037;
      }
      else if ( (v27 & 4) != 0 )
      {
        v28 = 12170;
      }
      else if ( v27 >= 0 )
      {
        if ( (v27 & 1) != 0 )
        {
          v28 = 12057;
        }
        else if ( (v27 & 0x40) != 0 )
        {
          v28 = 12179;
        }
        else
        {
          v28 = v27 != 0 ? 0x2F8F : 0;
        }
      }
      else
      {
        v28 = 12157;
      }
      WinhttpSslErrorCodeName = WinHttpRequest::GetWinhttpSslErrorCodeName(v27, Buffer, v8);
      if ( WinhttpSslErrorCodeName < 0 )
        Logger::TraceWarning(
          L"%s: WinHttpRequest::GetSslErrorCodeName failed with error code: 0x%08x. Error ignored.",
          L"WinHttpRequest::OnCallback",
          (unsigned int)WinhttpSslErrorCodeName);
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v32 = McTemplateU0qqz_EventWriteTransfer(v31, v30, v28, *((_DWORD *)this + 39), (__int64)Buffer);
        if ( v32 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpSslFailureEvent",
            L"EventWriteWinhttpSslFailureEvent",
            v32);
      }
      Logger::TraceError(
        L"%s: SSL error code: 0x%08x. WinHTTP status: 0x%08x (%s)",
        L"WinHttpRequest::OnCallback",
        v28,
        *((unsigned int *)this + 39),
        Buffer);
      return 0;
    case 0x20000u:
      v22 = (_DWORD *)((char *)this + 140);
      Block = 0;
      v23 = 0;
      StatusCode = WinHttpRequest::QueryStatusCode(this, (unsigned int *)this + 35);
      Logger::TraceVerbose(
        L"%s: dwInternetStatus = %lu, HTTP status = %d",
        L"WinHttpRequest::OnCallback",
        0x20000,
        *((unsigned int *)this + 35));
      v24 = StatusCode < 0;
      if ( StatusCode )
      {
LABEL_44:
        if ( v24 )
          goto LABEL_78;
        Logger::TraceVerbose(L"%s: Triggering the get data.", L"WinHttpRequest::OnCallback");
        goto LABEL_46;
      }
      if ( *v22 == 302 || *v22 == 307 )
      {
        Header = WinHttpRequest::QueryHeader(this, 0x21u, 0, (unsigned __int16 **)&Block);
        StatusCode = Header;
        if ( Header < 0 )
        {
          Logger::TraceError(
            L"%s: WinHttpRequest::QueryHeader failed with error code: 0x%08x",
            L"WinHttpRequest::OnCallback",
            (unsigned int)Header);
LABEL_40:
          v23 = Block;
LABEL_41:
          if ( v23 )
            free(v23);
          v24 = StatusCode < 0;
          goto LABEL_44;
        }
        if ( Header )
          goto LABEL_40;
        v23 = Block;
      }
      v26 = (*(__int64 (__fastcall **)(WinHttpRequest *, _QWORD, void *))(*(_QWORD *)this + 32LL))(
              this,
              (unsigned int)*v22,
              v23);
      StatusCode = v26;
      if ( v26 < 0 )
        Logger::TraceError(
          L"%s: WinHttpRequest::OnHttpStatusReceived failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)v26);
      goto LABEL_41;
    case 0x40000u:
      v17 = *(_DWORD *)a3;
      Logger::TraceVerbose(L"%s: Data available. dwSize: %lu", L"WinHttpRequest::OnCallback", *(unsigned int *)a3);
      v18 = this;
      if ( !v17 )
      {
        v19 = 0;
LABEL_86:
        WinHttpRequest::CloseHandleTrigger(v18, v19);
        return 0;
      }
      DataTrigger = WinHttpRequest::ReadDataTrigger((HINTERNET *)this, v17);
      StatusCode = DataTrigger;
      if ( DataTrigger >= 0 )
      {
LABEL_78:
        if ( StatusCode == -2147023673 )
        {
          WinHttpCallbackStatus = WinHttpRequest::GetWinHttpCallbackStatus(a2);
          if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
          {
            v36 = &base;
            if ( WinHttpCallbackStatus )
              v36 = WinHttpCallbackStatus;
            v37 = McTemplateU0qz_EventWriteTransfer(v35, v34, a2, v36);
            if ( v37 )
              Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"Logger::WriteWinhttpCallbackCancelledEvent",
                L"EventWriteWinhttpCallbackCancelledEvent",
                v37);
          }
          Logger::TraceInformation(L"%s: Exit code was ERROR_CANCELLED.", L"WinHttpRequest::OnCallback");
          *((_DWORD *)this + 4) = 1;
          WinHttpRequest::CleanupCancelledRequest(v38, a2, a3, a4);
          v19 = -2147023673;
        }
        else
        {
          if ( StatusCode >= 0 )
            return 0;
          v39 = WinHttpRequest::GetWinHttpCallbackStatus(a2);
          if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
          {
            v41 = &base;
            if ( v39 )
              v41 = v39;
            v42 = McTemplateU0qdz_EventWriteTransfer((_DWORD)v41, v40, a2, StatusCode, (__int64)v41);
            if ( v42 )
              Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"Logger::WriteWinhttpCallbackFailureEvent",
                L"EventWriteWinhttpCallbackFailureEvent",
                v42);
          }
          Logger::TraceError(
            L"%s: The callback handling failed with error code: 0x%08x",
            L"WinHttpRequest::OnCallback",
            (unsigned int)StatusCode);
          v19 = StatusCode;
        }
        v18 = this;
        goto LABEL_86;
      }
      v21 = L"%s: WinHttpRequest::ReadDataTrigger failed with error code: 0x%08x";
LABEL_77:
      Logger::TraceError(v21, L"WinHttpRequest::OnCallback", (unsigned int)DataTrigger);
      goto LABEL_78;
    case 0x80000u:
      Logger::TraceVerbose(L"%s: Read complete. dwSize: %d", L"WinHttpRequest::OnCallback", a4);
      if ( !a4 )
      {
        StatusCode = 0;
        WinHttpRequest::CloseHandleTrigger(this, 0);
        goto LABEL_78;
      }
      StatusCode = WinHttpRequest::ReadDataComplete(this, a4, a3);
      free(a3);
      if ( StatusCode < 0 )
      {
        Logger::TraceError(
          L"%s: WinHttpRequest::ReadDataComplete failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)StatusCode);
        goto LABEL_78;
      }
LABEL_46:
      v10 = WinHttpRequest::QueryDataTrigger(this);
LABEL_47:
      StatusCode = v10;
      goto LABEL_78;
  }
  if ( a2 != 0x200000 )
  {
    if ( a2 == 0x400000 )
    {
      if ( WinHttpReceiveResponse(*((HINTERNET *)this + 1), 0) )
        return 0;
      StatusCode = GetLastError();
      Logger::WriteWinhttpReadFailureEvent(StatusCode);
      Logger::TraceError(
        L"%s: WinHttpReceiveResponse failed with error code: 0x%08x",
        L"WinHttpRequest::ReceiveResponseTrigger",
        (unsigned int)StatusCode);
      v12 = StatusCode < 0;
      if ( StatusCode > 0 )
      {
        StatusCode = (unsigned __int16)StatusCode | 0x80070000;
        v12 = StatusCode < 0;
      }
      if ( v12 )
        Logger::TraceError(
          L"%s: WinHttpRequest::ReceiveResponseTrigger failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)StatusCode);
      goto LABEL_78;
    }
    if ( a2 != 0x1000000 )
      return 0;
    v10 = WinHttpRequest::CompleteAutoProxySendRequest((DWORD_PTR)this, 0x1000000u, 0);
    goto LABEL_47;
  }
  if ( *((_DWORD *)this + 41)
    || *(_QWORD *)a3 != 6 && (*(_QWORD *)a3 != 5 || *((_DWORD *)this + 16) != 1)
    || (int)WinHttpRequest::CompleteAutoProxySendRequest((DWORD_PTR)this, 0x200000u, (struct _WINHTTP_ASYNC_RESULT *)a3) < 0 )
  {
    v13 = *(_QWORD *)a3;
    *((_QWORD *)this + 18) = *(_QWORD *)a3;
    *((_DWORD *)this + 38) = *((_DWORD *)a3 + 2);
    WinHttpErrorResultName = WinHttpRequest::GetWinHttpErrorResultName(v13);
    if ( !WinHttpErrorResultName || !*WinHttpErrorResultName )
      WinHttpErrorResultName = L"Unknown";
    Logger::TraceError(
      L"%s: WINHTTP_ASYNC_RESULT dwResult: %d (%s), dwError: 0x%08x",
      L"WinHttpRequest::OnCallback",
      v16,
      WinHttpErrorResultName,
      v15);
    v10 = (*(__int64 (__fastcall **)(WinHttpRequest *, _QWORD, _QWORD))(*(_QWORD *)this + 8LL))(
            this,
            *(_QWORD *)a3,
            *((unsigned int *)a3 + 2));
    goto LABEL_47;
  }
  return 0;
}

```

## disassembly

```asm
0x180098b14  push    rbx
0x180098b16  push    rbp
0x180098b17  push    rsi
0x180098b18  push    rdi
0x180098b19  push    r12
0x180098b1b  push    r13
0x180098b1d  push    r14
0x180098b1f  push    r15
0x180098b21  sub     rsp, 458h
0x180098b28  mov     rax, cs:__security_cookie
0x180098b2f  xor     rax, rsp
0x180098b32  mov     [rsp+498h+var_58], rax
0x180098b3a  mov     r14, r8
0x180098b3d  lea     rbp, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x180098b44  mov     r8d, edx
0x180098b47  mov     esi, edx
0x180098b49  mov     rdi, rcx
0x180098b4c  mov     rdx, rbp
0x180098b4f  lea     rcx, aSDwinternetsta_0; "%s: dwInternetStatus = %lu"
0x180098b56  mov     r12d, r9d
0x180098b59  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098b5e  xor     r13d, r13d
0x180098b61  cmp     [rdi+10h], r13d
0x180098b65  jz      short loc_180098B88
0x180098b67  mov     rdx, rbp
0x180098b6a  lea     rcx, aSMRequestcance; "%s: m_requestCanceled is TRUE."
0x180098b71  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180098b76  mov     r9d, r12d; unsigned int
0x180098b79  mov     r8, r14; void *
0x180098b7c  mov     edx, esi; unsigned int
0x180098b7e  call    ?CleanupCancelledRequest@WinHttpRequest@@AEAAXKPEAXK@Z; WinHttpRequest::CleanupCancelledRequest(ulong,void *,ulong)
0x180098b83  jmp     loc_1800990A7
0x180098b88  cmp     esi, 800h
0x180098b8e  jz      loc_180099092
0x180098b94  cmp     esi, 4000h
0x180098b9a  jz      loc_180098F79
0x180098ba0  cmp     esi, 10000h
0x180098ba6  jz      loc_180098E7A
0x180098bac  cmp     esi, 20000h
0x180098bb2  jz      loc_180098D82
0x180098bb8  cmp     esi, 40000h
0x180098bbe  jz      loc_180098D42
0x180098bc4  cmp     esi, 80000h
0x180098bca  jz      loc_180098CEC
0x180098bd0  mov     edx, 200000h; unsigned int
0x180098bd5  cmp     esi, edx
0x180098bd7  jz      loc_180098C5F
0x180098bdd  cmp     esi, 400000h
0x180098be3  jz      short loc_180098C02
0x180098be5  mov     edx, 1000000h; unsigned int
0x180098bea  cmp     esi, edx
0x180098bec  jnz     loc_1800990A7
0x180098bf2  xor     r8d, r8d; struct _WINHTTP_ASYNC_RESULT *
0x180098bf5  mov     rcx, rdi; dwContext
0x180098bf8  call    ?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z; WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)
0x180098bfd  jmp     loc_180098E39
0x180098c02  mov     rcx, [rdi+8]; hRequest
0x180098c06  xor     edx, edx; lpReserved
0x180098c08  call    cs:__imp_WinHttpReceiveResponse
0x180098c0e  test    eax, eax
0x180098c10  jnz     loc_1800990A7
0x180098c16  call    cs:__imp_GetLastError
0x180098c1c  mov     ecx, eax; unsigned int
0x180098c1e  mov     ebx, eax
0x180098c20  call    ?WriteWinhttpReadFailureEvent@Logger@@SAJK@Z; Logger::WriteWinhttpReadFailureEvent(ulong)
0x180098c25  mov     r8d, ebx
0x180098c28  lea     rdx, aWinhttprequest_16; "WinHttpRequest::ReceiveResponseTrigger"
0x180098c2f  lea     rcx, aSWinhttpreceiv; "%s: WinHttpReceiveResponse failed with "...
0x180098c36  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098c3b  test    ebx, ebx
0x180098c3d  jle     short loc_180098C4A
0x180098c3f  movzx   ebx, bx
0x180098c42  or      ebx, 80070000h
0x180098c48  test    ebx, ebx
0x180098c4a  jns     loc_180098FA7
0x180098c50  mov     r8d, ebx
0x180098c53  lea     rcx, aSWinhttpreques_2; "%s: WinHttpRequest::ReceiveResponseTrig"...
0x180098c5a  jmp     loc_180098F9F
0x180098c5f  cmp     [rdi+0A4h], r13d
0x180098c66  jnz     short loc_180098C8D
0x180098c68  cmp     qword ptr [r14], 6
0x180098c6c  jz      short loc_180098C7A
0x180098c6e  cmp     qword ptr [r14], 5
0x180098c72  jnz     short loc_180098C8D
0x180098c74  cmp     dword ptr [rdi+40h], 1
0x180098c78  jnz     short loc_180098C8D
0x180098c7a  mov     r8, r14; struct _WINHTTP_ASYNC_RESULT *
0x180098c7d  mov     rcx, rdi; dwContext
0x180098c80  call    ?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z; WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)
0x180098c85  test    eax, eax
0x180098c87  jns     loc_1800990A7
0x180098c8d  mov     r8, [r14]
0x180098c90  mov     [rdi+90h], r8
0x180098c97  mov     rcx, r8; unsigned __int64
0x180098c9a  mov     edx, [r14+8]
0x180098c9e  mov     [rdi+98h], edx
0x180098ca4  call    ?GetWinHttpErrorResultName@WinHttpRequest@@SAPEBG_K@Z; WinHttpRequest::GetWinHttpErrorResultName(unsigned __int64)
0x180098ca9  test    rax, rax
0x180098cac  jz      short loc_180098CB4
0x180098cae  cmp     [rax], r13w
0x180098cb2  jnz     short loc_180098CBB
0x180098cb4  lea     rax, aUnknown_0; "Unknown"
0x180098cbb  mov     dword ptr [rsp+498h+var_478], edx
0x180098cbf  lea     rcx, aSWinhttpAsyncR; "%s: WINHTTP_ASYNC_RESULT dwResult: %d ("...
0x180098cc6  mov     rdx, rbp
0x180098cc9  mov     r9, rax
0x180098ccc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098cd1  mov     rax, [rdi]
0x180098cd4  mov     rcx, rdi
0x180098cd7  mov     r8d, [r14+8]
0x180098cdb  mov     rdx, [r14]
0x180098cde  mov     rax, [rax+8]
0x180098ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098ce7  jmp     loc_180098E39
0x180098cec  mov     r8d, r12d
0x180098cef  lea     rcx, aSReadCompleteD; "%s: Read complete. dwSize: %d"
0x180098cf6  mov     rdx, rbp
0x180098cf9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098cfe  mov     rcx, rdi; this
0x180098d01  test    r12d, r12d
0x180098d04  jz      short loc_180098D33
0x180098d06  mov     r8, r14; char *
0x180098d09  mov     edx, r12d; unsigned int
0x180098d0c  call    ?ReadDataComplete@WinHttpRequest@@AEAAJKPEAD@Z; WinHttpRequest::ReadDataComplete(ulong,char *)
0x180098d11  mov     rcx, r14; Block
0x180098d14  mov     ebx, eax
0x180098d16  call    cs:__imp_free
0x180098d1c  test    ebx, ebx
0x180098d1e  jns     loc_180098E31
0x180098d24  mov     r8d, ebx
0x180098d27  lea     rcx, aSWinhttpreques_5; "%s: WinHttpRequest::ReadDataComplete fa"...
0x180098d2e  jmp     loc_180098F9F
0x180098d33  xor     edx, edx; int
0x180098d35  mov     ebx, r13d
0x180098d38  call    ?CloseHandleTrigger@WinHttpRequest@@AEAAXJ@Z; WinHttpRequest::CloseHandleTrigger(long)
0x180098d3d  jmp     loc_180098FA7
0x180098d42  mov     ebx, [r14]
0x180098d45  lea     rcx, aSDataAvailable; "%s: Data available. dwSize: %lu"
0x180098d4c  mov     r8d, ebx
0x180098d4f  mov     rdx, rbp
0x180098d52  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098d57  mov     rcx, rdi; this
0x180098d5a  test    ebx, ebx
0x180098d5c  jnz     short loc_180098D65
0x180098d5e  xor     edx, edx
0x180098d60  jmp     loc_180099022
0x180098d65  mov     edx, ebx; unsigned int
0x180098d67  call    ?ReadDataTrigger@WinHttpRequest@@AEAAJK@Z; WinHttpRequest::ReadDataTrigger(ulong)
0x180098d6c  mov     ebx, eax
0x180098d6e  test    eax, eax
0x180098d70  jns     loc_180098FA7
0x180098d76  lea     rcx, aSWinhttpreques_6; "%s: WinHttpRequest::ReadDataTrigger fai"...
0x180098d7d  jmp     loc_180098F9C
0x180098d82  lea     r15, [rdi+8Ch]
0x180098d89  mov     [rsp+498h+Block], r13
0x180098d8e  mov     rdx, r15; unsigned int *
0x180098d91  mov     rcx, rdi; this
0x180098d94  mov     rbp, r13
0x180098d97  call    ?QueryStatusCode@WinHttpRequest@@AEAAJPEAK@Z; WinHttpRequest::QueryStatusCode(ulong *)
0x180098d9c  mov     r9d, [r15]
0x180098d9f  lea     rdx, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x180098da6  mov     r8d, 20000h
0x180098dac  lea     rcx, aSDwinternetsta; "%s: dwInternetStatus = %lu, HTTP status"...
0x180098db3  mov     ebx, eax
0x180098db5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098dba  test    ebx, ebx
0x180098dbc  jnz     short loc_180098E15
0x180098dbe  cmp     dword ptr [r15], 12Eh
0x180098dc5  jz      short loc_180098DD0
0x180098dc7  cmp     dword ptr [r15], 133h
0x180098dce  jnz     short loc_180098E47
0x180098dd0  xor     r8d, r8d; unsigned __int16 *
0x180098dd3  lea     r9, [rsp+498h+Block]; unsigned __int16 **
0x180098dd8  mov     rcx, rdi; this
0x180098ddb  lea     edx, [r8+21h]; unsigned int
0x180098ddf  call    ?QueryHeader@WinHttpRequest@@QEAAJKPEBGPEAPEAG@Z; WinHttpRequest::QueryHeader(ulong,ushort const *,ushort * *)
0x180098de4  mov     ebx, eax
0x180098de6  test    eax, eax
0x180098de8  jns     short loc_180098E40
0x180098dea  mov     r8d, eax
0x180098ded  lea     rdx, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x180098df4  lea     rcx, aSWinhttpreques_3; "%s: WinHttpRequest::QueryHeader failed "...
0x180098dfb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098e00  mov     rbp, [rsp+498h+Block]
0x180098e05  test    rbp, rbp
0x180098e08  jz      short loc_180098E13
0x180098e0a  mov     rcx, rbp; Block
0x180098e0d  call    cs:__imp_free
0x180098e13  test    ebx, ebx
0x180098e15  lea     rbp, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x180098e1c  js      loc_180098FA7
0x180098e22  mov     rdx, rbp
0x180098e25  lea     rcx, aSTriggeringThe; "%s: Triggering the get data."
0x180098e2c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098e31  mov     rcx, rdi; this
0x180098e34  call    ?QueryDataTrigger@WinHttpRequest@@AEAAJXZ; WinHttpRequest::QueryDataTrigger(void)
0x180098e39  mov     ebx, eax
0x180098e3b  jmp     loc_180098FA7
0x180098e40  jnz     short loc_180098E00
0x180098e42  mov     rbp, [rsp+498h+Block]
0x180098e47  mov     rax, [rdi]
0x180098e4a  mov     r8, rbp
0x180098e4d  mov     edx, [r15]
0x180098e50  mov     rcx, rdi
0x180098e53  mov     rax, [rax+20h]
0x180098e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e5c  mov     ebx, eax
0x180098e5e  test    eax, eax
0x180098e60  jns     short loc_180098E05
0x180098e62  mov     r8d, eax
0x180098e65  lea     rdx, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x180098e6c  lea     rcx, aSWinhttpreques_0; "%s: WinHttpRequest::OnHttpStatusReceive"...
0x180098e73  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098e78  jmp     short loc_180098E05
0x180098e7a  mov     ecx, [r14]; unsigned int
0x180098e7d  mov     [rdi+9Ch], ecx
0x180098e83  test    cl, 2
0x180098e86  jz      short loc_180098E8F
0x180098e88  mov     ebx, 2F89h
0x180098e8d  jmp     short loc_180098EEE
0x180098e8f  test    cl, 8
0x180098e92  jz      short loc_180098E9B
0x180098e94  mov     ebx, 2F0Dh
0x180098e99  jmp     short loc_180098EEE
0x180098e9b  test    cl, 10h
0x180098e9e  jz      short loc_180098EA7
0x180098ea0  mov     ebx, 2F06h
0x180098ea5  jmp     short loc_180098EEE
0x180098ea7  test    cl, 20h
0x180098eaa  jz      short loc_180098EB3
0x180098eac  mov     ebx, 2F05h
0x180098eb1  jmp     short loc_180098EEE
0x180098eb3  test    cl, 4
0x180098eb6  jz      short loc_180098EBF
0x180098eb8  mov     ebx, 2F8Ah
0x180098ebd  jmp     short loc_180098EEE
0x180098ebf  test    ecx, ecx
0x180098ec1  jns     short loc_180098ECA
0x180098ec3  mov     ebx, 2F7Dh
0x180098ec8  jmp     short loc_180098EEE
0x180098eca  test    cl, 1
0x180098ecd  jz      short loc_180098ED6
0x180098ecf  mov     ebx, 2F19h
0x180098ed4  jmp     short loc_180098EEE
0x180098ed6  test    cl, 40h
0x180098ed9  jz      short loc_180098EE2
0x180098edb  mov     ebx, 2F93h
0x180098ee0  jmp     short loc_180098EEE
0x180098ee2  mov     eax, ecx
0x180098ee4  neg     eax
0x180098ee6  sbb     ebx, ebx
0x180098ee8  and     ebx, 2F8Fh
0x180098eee  lea     rdx, [rsp+498h+Buffer]; Buffer
0x180098ef3  call    ?GetWinhttpSslErrorCodeName@WinHttpRequest@@SAJKPEAG_K@Z; WinHttpRequest::GetWinhttpSslErrorCodeName(ulong,ushort *,unsigned __int64)
0x180098ef8  test    eax, eax
0x180098efa  jns     short loc_180098F0E
0x180098efc  mov     r8d, eax
0x180098eff  lea     rcx, aSWinhttpreques; "%s: WinHttpRequest::GetSslErrorCodeName"...
0x180098f06  mov     rdx, rbp
0x180098f09  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180098f0e  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180098f15  jz      short loc_180098F51
0x180098f17  mov     r9d, [rdi+9Ch]
0x180098f1e  lea     rax, [rsp+498h+Buffer]
0x180098f23  mov     r8d, ebx
0x180098f26  mov     [rsp+498h+var_478], rax
0x180098f2b  call    McTemplateU0qqz_EventWriteTransfer
0x180098f30  test    eax, eax
0x180098f32  jz      short loc_180098F51
0x180098f34  mov     r9d, eax
0x180098f37  lea     r8, aEventwritewinh_4; "EventWriteWinhttpSslFailureEvent"
0x180098f3e  lea     rdx, aLoggerWritewin_0; "Logger::WriteWinhttpSslFailureEvent"
0x180098f45  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180098f4c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098f51  mov     r9d, [rdi+9Ch]
0x180098f58  lea     rax, [rsp+498h+Buffer]
0x180098f5d  mov     r8d, ebx
0x180098f60  mov     [rsp+498h+var_478], rax
0x180098f65  mov     rdx, rbp
0x180098f68  lea     rcx, aSSslErrorCode0; "%s: SSL error code: 0x%08x. WinHTTP sta"...
0x180098f6f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098f74  jmp     loc_1800990A7
0x180098f79  mov     rax, [rdi]
0x180098f7c  lea     r8d, [r12+r12]
0x180098f80  mov     rdx, r14
0x180098f83  mov     rcx, rdi
0x180098f86  mov     rax, [rax+28h]
0x180098f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f8f  mov     ebx, eax
0x180098f91  test    eax, eax
0x180098f93  jns     short loc_180098FA7
0x180098f95  lea     rcx, aSWinhttpreques_1; "%s: WinHttpRequest::OnRedirect failed w"...
0x180098f9c  mov     r8d, eax
0x180098f9f  mov     rdx, rbp
0x180098fa2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098fa7  mov     r15d, 800704C7h
0x180098fad  cmp     ebx, r15d
0x180098fb0  jnz     short loc_180099029
0x180098fb2  mov     ecx, esi; unsigned int
0x180098fb4  call    ?GetWinHttpCallbackStatus@WinHttpRequest@@SAPEBGK@Z; WinHttpRequest::GetWinHttpCallbackStatus(ulong)
  ... truncated ...
```
