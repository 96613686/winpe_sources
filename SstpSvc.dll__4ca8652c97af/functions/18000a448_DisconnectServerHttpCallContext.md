# DisconnectServerHttpCallContext

- ea: `0x18000a448`
- end: `0x18000a60b`
- name: `DisconnectServerHttpCallContext`
- size: `451`
- prototype: `ULONG __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002908`

## callees

- `0x180002908`
- `0x18000827c`
- `0x180008360`
- `0x18000a448`
- `0x18000cba4`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a4ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a502`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a4ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a502`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000a5c2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000a5c2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000a516`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000a516`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000a553`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18000a553`

## string_xrefs

- `0x18000a57f`: `CoId=%hs:SendResponse completes with %d`

## pseudocode

```c
ULONG __fastcall DisconnectServerHttpCallContext(__int64 a1)
{
  int v2; // eax
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  struct _OVERLAPPED *v4; // rbx
  ULONG result; // eax
  int v6; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+54h] [rbp-814h] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v2 = *(_DWORD *)(a1 + 252);
  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
  if ( (v2 & 2) != 0 )
  {
    v4 = *(struct _OVERLAPPED **)(a1 + 256);
    *(_DWORD *)(a1 + 252) = v2 & 0xFFFFFFFD;
    *(_QWORD *)(a1 + 256) = 0;
    v4[1].hEvent = (HANDLE)a1;
    LeaveCriticalSection(v3);
    result = TerminatePartialConnection(*(_QWORD *)(a1 + 272), v4);
    if ( result && result != 997 )
    {
LABEL_11:
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      *(_DWORD *)(a1 + 252) &= ~0x2000u;
      return InitiateCallContextCleanup(a1, 2);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 200) = 17775;
    *(_OWORD *)(a1 + 168) = 0;
    *(_OWORD *)(a1 + 184) = 0;
    LeaveCriticalSection(v3);
    StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    result = HttpSendResponseEntityBody(
               *((HANDLE *)SstpSvcGlobals + 8),
               *(_QWORD *)(a1 + 272),
               1u,
               0,
               0,
               0,
               0,
               0,
               (LPOVERLAPPED)(a1 + 168),
               0);
    if ( result != 997 && result )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v6) = 0;
        FormatRRASErrorString(&v6, L"CoId=%hs:SendResponse completes with %d", a1 + 552, result);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
      }
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      goto LABEL_11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a448  mov     [rsp+arg_8], rbx
0x18000a44d  mov     [rsp+arg_10], rsi
0x18000a452  push    rdi
0x18000a453  sub     rsp, 860h
0x18000a45a  mov     rax, cs:__security_cookie
0x18000a461  xor     rax, rsp
0x18000a464  mov     [rsp+868h+var_18], rax
0x18000a46c  mov     rdi, rcx
0x18000a46f  xor     eax, eax
0x18000a471  lea     rcx, [rsp+868h+var_814]; void *
0x18000a476  mov     [rsp+868h+var_818], eax
0x18000a47a  xor     edx, edx; Val
0x18000a47c  mov     r8d, 7FCh; Size
0x18000a482  call    memset_0
0x18000a487  mov     eax, [rdi+0FCh]
0x18000a48d  lea     rsi, [rdi+120h]
0x18000a494  mov     rcx, rsi; lpCriticalSection
0x18000a497  test    al, 2
0x18000a499  jz      short loc_18000A4E7
0x18000a49b  mov     rbx, [rdi+100h]
0x18000a4a2  and     eax, 0FFFFFFFDh
0x18000a4a5  mov     [rdi+0FCh], eax
0x18000a4ab  mov     qword ptr [rdi+100h], 0
0x18000a4b6  mov     [rbx+38h], rdi
0x18000a4ba  call    cs:__imp_LeaveCriticalSection
0x18000a4c0  mov     rcx, [rdi+110h]; RequestId
0x18000a4c7  mov     rdx, rbx; Overlapped
0x18000a4ca  call    TerminatePartialConnection
0x18000a4cf  test    eax, eax
0x18000a4d1  jz      loc_18000A5E6
0x18000a4d7  cmp     eax, 3E5h
0x18000a4dc  jz      loc_18000A5E6
0x18000a4e2  jmp     loc_18000A5C8
0x18000a4e7  xorps   xmm0, xmm0
0x18000a4ea  mov     dword ptr [rdi+0C8h], 456Fh
0x18000a4f4  lea     rbx, [rdi+0A8h]
0x18000a4fb  movups  xmmword ptr [rbx], xmm0
0x18000a4fe  movups  xmmword ptr [rbx+10h], xmm0
0x18000a502  call    cs:__imp_LeaveCriticalSection
0x18000a508  mov     rcx, cs:SstpSvcGlobals
0x18000a50f  mov     rcx, [rcx+0A8h]; pio
0x18000a516  call    cs:__imp_StartThreadpoolIo
0x18000a51c  mov     rcx, cs:SstpSvcGlobals
0x18000a523  xor     r9d, r9d; EntityChunkCount
0x18000a526  mov     rdx, [rdi+110h]; RequestId
0x18000a52d  mov     [rsp+868h+LogData], r9; LogData
0x18000a532  mov     [rsp+868h+Overlapped], rbx; Overlapped
0x18000a537  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000a53b  lea     r8d, [r9+1]; Flags
0x18000a53f  mov     [rsp+868h+Reserved2], r9d; Reserved2
0x18000a544  mov     [rsp+868h+Reserved1], r9; Reserved1
0x18000a549  mov     [rsp+868h+BytesSent], r9; BytesSent
0x18000a54e  mov     [rsp+868h+EntityChunks], r9; EntityChunks
0x18000a553  call    cs:__imp_HttpSendResponseEntityBody
0x18000a559  cmp     eax, 3E5h
0x18000a55e  jz      loc_18000A5E6
0x18000a564  test    eax, eax
0x18000a566  jz      short loc_18000A5E6
0x18000a568  test    cs:byte_18002D803, 8
0x18000a56f  jz      short loc_18000A5B4
0x18000a571  xor     ecx, ecx
0x18000a573  lea     r8, [rdi+228h]
0x18000a57a  mov     word ptr [rsp+868h+var_818], cx
0x18000a57f  lea     rdx, aCoidHsSendresp; "CoId=%hs:SendResponse completes with %d"
0x18000a586  lea     rcx, [rsp+868h+var_818]
0x18000a58b  mov     r9d, eax
0x18000a58e  call    FormatRRASErrorString
0x18000a593  test    cs:byte_18002D803, 8
0x18000a59a  jz      short loc_18000A5B4
0x18000a59c  lea     r8, [rsp+868h+var_818]
0x18000a5a1  lea     rdx, RasSSTPSvcTraceError
0x18000a5a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a5af  call    McTemplateU0z_EventWriteTransfer
0x18000a5b4  mov     rcx, cs:SstpSvcGlobals
0x18000a5bb  mov     rcx, [rcx+0A8h]; pio
0x18000a5c2  call    cs:__imp_CancelThreadpoolIo
0x18000a5c8  mov     rcx, rsi; lpCriticalSection
0x18000a5cb  call    cs:__imp_EnterCriticalSection
0x18000a5d1  btr     dword ptr [rdi+0FCh], 0Dh
0x18000a5d9  mov     edx, 2
0x18000a5de  mov     rcx, rdi
0x18000a5e1  call    InitiateCallContextCleanup
0x18000a5e6  mov     rcx, [rsp+868h+var_18]
0x18000a5ee  xor     rcx, rsp; StackCookie
0x18000a5f1  call    __security_check_cookie
0x18000a5f6  lea     r11, [rsp+868h+var_8]
0x18000a5fe  mov     rbx, [r11+18h]
0x18000a602  mov     rsi, [r11+20h]
0x18000a606  mov     rsp, r11
0x18000a609  pop     rdi
0x18000a60a  retn
```
