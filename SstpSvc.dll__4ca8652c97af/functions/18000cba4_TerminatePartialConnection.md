# TerminatePartialConnection

- ea: `0x18000cba4`
- end: `0x18000cdd1`
- name: `TerminatePartialConnection`
- size: `557`
- prototype: `__int64 __fastcall(HTTP_REQUEST_ID RequestId, LPOVERLAPPED Overlapped)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a448`

## callees

- `0x180002d70`
- `0x18000827c`
- `0x180008360`
- `0x18000cba4`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000cd40`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000cd40`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000cc85`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000cc85`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000ccda`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000ccda`

## pseudocode

```c
__int64 __fastcall TerminatePartialConnection(HTTP_REQUEST_ID RequestId, LPOVERLAPPED Overlapped)
{
  PTP_IO *v4; // rcx
  ULONG v5; // eax
  ULONG v6; // ebx
  struct _HTTP_CACHE_POLICY CachePolicy; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v10[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  CachePolicy = 0;
  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Entering %ws", L"TerminatePartialConnection");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v9);
  }
  *(_OWORD *)&Overlapped->Internal = 0;
  *(_OWORD *)&Overlapped->Offset = 0;
  LODWORD(Overlapped[1].Internal) = 17768;
  memset_0(&Overlapped[3], 0, 0x238u);
  v4 = (PTP_IO *)SstpSvcGlobals;
  HIDWORD(Overlapped[3].Internal) = 65537;
  LOWORD(Overlapped[3].InternalHigh) = 401;
  StartThreadpoolIo(v4[21]);
  CachePolicy.Policy = HttpCachePolicyNocache;
  v5 = HttpSendHttpResponse(
         *((HANDLE *)SstpSvcGlobals + 8),
         RequestId,
         1u,
         (PHTTP_RESPONSE)&Overlapped[3],
         &CachePolicy,
         0,
         0,
         0,
         Overlapped,
         0);
  v6 = v5;
  if ( v5 != 997 && v5 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString((wchar_t *)&v9, L"Terminate: SendResponse fails with error %d", v5);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v9);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    FreeBufferToPool((__int64)SstpSvcGlobals + 424, (__int64)Overlapped, 1);
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"LEaving %ws", L"TerminatePartialConnection");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cba4  mov     [rsp-8+arg_10], rbx
0x18000cba9  mov     [rsp-8+arg_18], rsi
0x18000cbae  push    rbp
0x18000cbaf  push    rdi
0x18000cbb0  push    r13
0x18000cbb2  lea     rbp, [rsp-770h]
0x18000cbba  sub     rsp, 870h
0x18000cbc1  mov     rax, cs:__security_cookie
0x18000cbc8  xor     rax, rsp
0x18000cbcb  mov     [rbp+780h+var_20], rax
0x18000cbd2  mov     rdi, rdx
0x18000cbd5  mov     qword ptr [rsp+880h+var_830.Policy], 0
0x18000cbde  mov     rsi, rcx
0x18000cbe1  xor     eax, eax
0x18000cbe3  xor     edx, edx; Val
0x18000cbe5  mov     [rsp+880h+var_820], eax
0x18000cbe9  lea     rcx, [rsp+880h+var_81C]; void *
0x18000cbee  mov     r8d, 7FCh; Size
0x18000cbf4  call    memset_0
0x18000cbf9  test    cs:byte_18002D803, 10h
0x18000cc00  jz      short loc_18000CC42
0x18000cc02  xor     eax, eax
0x18000cc04  lea     r8, aTerminateparti_0; "TerminatePartialConnection"
0x18000cc0b  lea     rdx, aEnteringWs; "Entering %ws"
0x18000cc12  mov     word ptr [rsp+880h+var_820], ax
0x18000cc17  lea     rcx, [rsp+880h+var_820]
0x18000cc1c  call    FormatRRASErrorString
0x18000cc21  test    cs:byte_18002D803, 10h
0x18000cc28  jz      short loc_18000CC42
0x18000cc2a  lea     r8, [rsp+880h+var_820]
0x18000cc2f  lea     rdx, RasSSTPSvcTraceInfo
0x18000cc36  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cc3d  call    McTemplateU0z_EventWriteTransfer
0x18000cc42  xorps   xmm0, xmm0
0x18000cc45  lea     rcx, [rdi+60h]; void *
0x18000cc49  movups  xmmword ptr [rdi], xmm0
0x18000cc4c  xor     edx, edx; Val
0x18000cc4e  mov     r8d, 238h; Size
0x18000cc54  movups  xmmword ptr [rdi+10h], xmm0
0x18000cc58  mov     dword ptr [rdi+20h], 4568h
0x18000cc5f  call    memset_0
0x18000cc64  mov     rcx, cs:SstpSvcGlobals
0x18000cc6b  mov     r13d, 1
0x18000cc71  mov     dword ptr [rdi+64h], 10001h
0x18000cc78  mov     word ptr [rdi+68h], 191h
0x18000cc7e  mov     rcx, [rcx+0A8h]; pio
0x18000cc85  call    cs:__imp_StartThreadpoolIo
0x18000cc8b  mov     rcx, cs:SstpSvcGlobals
0x18000cc92  lea     rax, [rsp+880h+var_830]
0x18000cc97  mov     [rsp+880h+LogData], 0; LogData
0x18000cca0  lea     r9, [rdi+60h]; HttpResponse
0x18000cca4  mov     [rsp+880h+Overlapped], rdi; Overlapped
0x18000cca9  mov     r8d, r13d; Flags
0x18000ccac  mov     [rsp+880h+Reserved2], 0; Reserved2
0x18000ccb4  mov     rdx, rsi; RequestId
0x18000ccb7  mov     [rsp+880h+var_830.Policy], 0
0x18000ccbf  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000ccc3  mov     [rsp+880h+Reserved1], 0; Reserved1
0x18000cccc  mov     [rsp+880h+BytesSent], 0; BytesSent
0x18000ccd5  mov     [rsp+880h+CachePolicy], rax; CachePolicy
0x18000ccda  call    cs:__imp_HttpSendHttpResponse
0x18000cce0  mov     ebx, eax
0x18000cce2  cmp     eax, 3E5h
0x18000cce7  jz      short loc_18000CD5F
0x18000cce9  test    eax, eax
0x18000cceb  jz      short loc_18000CD5F
0x18000cced  test    cs:byte_18002D803, 8
0x18000ccf4  jz      short loc_18000CD32
0x18000ccf6  xor     ecx, ecx
0x18000ccf8  lea     rdx, aTerminateSendr; "Terminate: SendResponse fails with erro"...
0x18000ccff  mov     word ptr [rsp+880h+var_820], cx
0x18000cd04  mov     r8d, eax
0x18000cd07  lea     rcx, [rsp+880h+var_820]
0x18000cd0c  call    FormatRRASErrorString
0x18000cd11  test    cs:byte_18002D803, 8
0x18000cd18  jz      short loc_18000CD32
0x18000cd1a  lea     r8, [rsp+880h+var_820]
0x18000cd1f  lea     rdx, RasSSTPSvcTraceError
0x18000cd26  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cd2d  call    McTemplateU0z_EventWriteTransfer
0x18000cd32  mov     rcx, cs:SstpSvcGlobals
0x18000cd39  mov     rcx, [rcx+0A8h]; pio
0x18000cd40  call    cs:__imp_CancelThreadpoolIo
0x18000cd46  mov     rcx, cs:SstpSvcGlobals
0x18000cd4d  mov     r8b, r13b
0x18000cd50  add     rcx, 1A8h
0x18000cd57  mov     rdx, rdi
0x18000cd5a  call    FreeBufferToPool
0x18000cd5f  test    cs:byte_18002D803, 10h
0x18000cd66  jz      short loc_18000CDA8
0x18000cd68  xor     eax, eax
0x18000cd6a  lea     r8, aTerminateparti_0; "TerminatePartialConnection"
0x18000cd71  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000cd78  mov     word ptr [rsp+880h+var_820], ax
0x18000cd7d  lea     rcx, [rsp+880h+var_820]
0x18000cd82  call    FormatRRASErrorString
0x18000cd87  test    cs:byte_18002D803, 10h
0x18000cd8e  jz      short loc_18000CDA8
0x18000cd90  lea     r8, [rsp+880h+var_820]
0x18000cd95  lea     rdx, RasSSTPSvcTraceInfo
0x18000cd9c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000cda3  call    McTemplateU0z_EventWriteTransfer
0x18000cda8  mov     eax, ebx
0x18000cdaa  mov     rcx, [rbp+780h+var_20]
0x18000cdb1  xor     rcx, rsp; StackCookie
0x18000cdb4  call    __security_check_cookie
0x18000cdb9  lea     r11, [rsp+880h+var_10]
0x18000cdc1  mov     rbx, [r11+30h]
0x18000cdc5  mov     rsi, [r11+38h]
0x18000cdc9  mov     rsp, r11
0x18000cdcc  pop     r13
0x18000cdce  pop     rdi
0x18000cdcf  pop     rbp
0x18000cdd0  retn
```
