# ResponseWaitTimeout

- ea: `0x18000d1a0`
- end: `0x18000d31c`
- name: `ResponseWaitTimeout`
- size: `380`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002d40`
- `0x18000827c`
- `0x180008360`
- `0x18000d1a0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d23d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d23d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d2aa`
- `webio!__imp_WebCancelHttpRequest` at `0x18000d255`
- `webio!__imp_WebCancelHttpRequest` at `0x18000d255`

## string_xrefs

- `0x18000d272`: `CoId=%hs:WebCancelHttpRequest(timeout) completes with %d`

## pseudocode

```c
void __fastcall ResponseWaitTimeout(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_TIMER Timer)
{
  unsigned int v4; // eax
  int v5; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString((wchar_t *)&v5, L"Entering %ws", L"ResponseWaitTimeout");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
  _InterlockedIncrement((volatile signed __int32 *)Context + 52);
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  if ( !Context[464] )
  {
    v4 = WebCancelHttpRequest(*((_QWORD *)Context + 56), 0);
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v5,
        L"CoId=%hs:WebCancelHttpRequest(timeout) completes with %d",
        Context + 552,
        v4);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v5);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  DereferenceRefCount((__int64)(Context + 208));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString((wchar_t *)&v5, L"LEaving %ws", L"ResponseWaitTimeout");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
}

```

## disassembly

```asm
0x18000d1a0  push    rbp
0x18000d1a2  push    rbx
0x18000d1a3  push    rsi
0x18000d1a4  push    rdi
0x18000d1a5  lea     rbp, [rsp-738h]
0x18000d1ad  sub     rsp, 838h
0x18000d1b4  mov     rax, cs:__security_cookie
0x18000d1bb  xor     rax, rsp
0x18000d1be  mov     [rbp+750h+var_30], rax
0x18000d1c5  mov     rbx, rdx
0x18000d1c8  lea     rcx, [rsp+850h+var_82C]; void *
0x18000d1cd  xor     eax, eax
0x18000d1cf  xor     edx, edx; Val
0x18000d1d1  mov     r8d, 7FCh; Size
0x18000d1d7  mov     [rsp+850h+var_830], eax
0x18000d1db  call    memset_0
0x18000d1e0  test    cs:byte_18002D803, 10h
0x18000d1e7  jz      short loc_18000D229
0x18000d1e9  xor     eax, eax
0x18000d1eb  lea     r8, aResponsewaitti; "ResponseWaitTimeout"
0x18000d1f2  lea     rdx, aEnteringWs; "Entering %ws"
0x18000d1f9  mov     word ptr [rsp+850h+var_830], ax
0x18000d1fe  lea     rcx, [rsp+850h+var_830]
0x18000d203  call    FormatRRASErrorString
0x18000d208  test    cs:byte_18002D803, 10h
0x18000d20f  jz      short loc_18000D229
0x18000d211  lea     r8, [rsp+850h+var_830]
0x18000d216  lea     rdx, RasSSTPSvcTraceInfo
0x18000d21d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d224  call    McTemplateU0z_EventWriteTransfer
0x18000d229  lea     rdi, [rbx+0D0h]
0x18000d230  lock inc dword ptr [rdi]
0x18000d233  lea     rsi, [rbx+120h]
0x18000d23a  mov     rcx, rsi; lpCriticalSection
0x18000d23d  call    cs:__imp_EnterCriticalSection
0x18000d243  cmp     byte ptr [rbx+1D0h], 0
0x18000d24a  jnz     short loc_18000D2A7
0x18000d24c  mov     rcx, [rbx+1C0h]
0x18000d253  xor     edx, edx
0x18000d255  call    cs:__imp_WebCancelHttpRequest
0x18000d25b  test    cs:byte_18002D803, 8
0x18000d262  jz      short loc_18000D2A7
0x18000d264  xor     ecx, ecx
0x18000d266  lea     r8, [rbx+228h]
0x18000d26d  mov     word ptr [rsp+850h+var_830], cx
0x18000d272  lea     rdx, aCoidHsWebcance_0; "CoId=%hs:WebCancelHttpRequest(timeout) "...
0x18000d279  lea     rcx, [rsp+850h+var_830]
0x18000d27e  mov     r9d, eax
0x18000d281  call    FormatRRASErrorString
0x18000d286  test    cs:byte_18002D803, 8
0x18000d28d  jz      short loc_18000D2A7
0x18000d28f  lea     r8, [rsp+850h+var_830]
0x18000d294  lea     rdx, RasSSTPSvcTraceError
0x18000d29b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d2a2  call    McTemplateU0z_EventWriteTransfer
0x18000d2a7  mov     rcx, rsi; lpCriticalSection
0x18000d2aa  call    cs:__imp_LeaveCriticalSection
0x18000d2b0  mov     rcx, rdi
0x18000d2b3  call    DereferenceRefCount
0x18000d2b8  test    cs:byte_18002D803, 10h
0x18000d2bf  jz      short loc_18000D301
0x18000d2c1  xor     eax, eax
0x18000d2c3  lea     r8, aResponsewaitti; "ResponseWaitTimeout"
0x18000d2ca  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000d2d1  mov     word ptr [rsp+850h+var_830], ax
0x18000d2d6  lea     rcx, [rsp+850h+var_830]
0x18000d2db  call    FormatRRASErrorString
0x18000d2e0  test    cs:byte_18002D803, 10h
0x18000d2e7  jz      short loc_18000D301
0x18000d2e9  lea     r8, [rsp+850h+var_830]
0x18000d2ee  lea     rdx, RasSSTPSvcTraceInfo
0x18000d2f5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d2fc  call    McTemplateU0z_EventWriteTransfer
0x18000d301  mov     rcx, [rbp+750h+var_30]
0x18000d308  xor     rcx, rsp; StackCookie
0x18000d30b  call    __security_check_cookie
0x18000d310  add     rsp, 838h
0x18000d317  pop     rdi
0x18000d318  pop     rsi
0x18000d319  pop     rbx
0x18000d31a  pop     rbp
0x18000d31b  retn
```
