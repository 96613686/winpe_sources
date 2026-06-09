# PostNewHttpRequest

- ea: `0x18000bc78`
- end: `0x18000bf5f`
- name: `PostNewHttpRequest`
- size: `743`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000a620`
- `0x18000b2e0`

## callees

- `0x180002d40`
- `0x180002d70`
- `0x180004530`
- `0x18000827c`
- `0x180008360`
- `0x1800093ac`
- `0x18000bc78`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000becc`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000becc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000be1a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000be1a`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000be5b`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000be5b`

## pseudocode

```c
__int64 PostNewHttpRequest()
{
  unsigned int v0; // ebx
  __int64 BufferFromPool; // rax
  __int64 v2; // rdi
  __int64 Overlapped; // rsi
  ULONG v4; // eax
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v8[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v6 = 0;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString((wchar_t *)&v7, L"Entering %ws", L"PostNewHttpRequest");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v7);
  }
  v0 = AllocateAndInitializeCallContext(0, &v6);
  if ( v0 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v7) = 0;
      FormatRRASErrorString((wchar_t *)&v7, L"CoId=%hs:Failure to allocate the callctx", v6 + 552);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v7);
    }
  }
  else
  {
    BufferFromPool = GetBufferFromPool((char *)SstpSvcGlobals + 424);
    v2 = v6;
    Overlapped = BufferFromPool;
    if ( BufferFromPool )
    {
      *(_QWORD *)(v6 + 256) = BufferFromPool;
      *(_DWORD *)(BufferFromPool + 32) = 17767;
      *(_OWORD *)BufferFromPool = 0;
      *(_OWORD *)(BufferFromPool + 16) = 0;
      *(_DWORD *)(BufferFromPool + 92) = 0;
      *(_QWORD *)(BufferFromPool + 56) = v2;
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 208));
      StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      memset_0((void *)(Overlapped + 96), 0, 0x360u);
      v4 = HttpReceiveHttpRequest(
             *((HANDLE *)SstpSvcGlobals + 8),
             0,
             0,
             (PHTTP_REQUEST)(Overlapped + 96),
             0x4000u,
             0,
             (LPOVERLAPPED)Overlapped);
      v0 = v4;
      if ( v4 == 997 || !v4 )
      {
        v0 = 0;
        goto LABEL_21;
      }
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString((wchar_t *)&v7, L"CoId=%hs:HttpReceiveRequest fails with %d", v2 + 552, v4);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v7);
      }
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      FreeBufferToPool((__int64)SstpSvcGlobals + 424, Overlapped, 1);
    }
    else
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString((wchar_t *)&v7, L"CoId=%hs:Unable to allocate memory for the recv buffer", v6 + 552);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            (const wchar_t *)&v7);
      }
      v0 = 8;
    }
    DereferenceRefCount(v2 + 208);
  }
LABEL_21:
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString((wchar_t *)&v7, L"LEaving %ws", L"PostNewHttpRequest");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v7);
  }
  return v0;
}

```

## disassembly

```asm
0x18000bc78  push    rbp
0x18000bc7a  push    rbx
0x18000bc7b  push    rsi
0x18000bc7c  push    rdi
0x18000bc7d  push    r15
0x18000bc7f  lea     rbp, [rsp-760h]
0x18000bc87  sub     rsp, 860h
0x18000bc8e  mov     rax, cs:__security_cookie
0x18000bc95  xor     rax, rsp
0x18000bc98  mov     [rbp+780h+var_30], rax
0x18000bc9f  xor     eax, eax
0x18000bca1  mov     [rsp+880h+var_840], 0
0x18000bcaa  xor     edx, edx; Val
0x18000bcac  mov     [rsp+880h+var_830], eax
0x18000bcb0  mov     r8d, 7FCh; Size
0x18000bcb6  lea     rcx, [rsp+880h+var_82C]; void *
0x18000bcbb  call    memset_0
0x18000bcc0  test    cs:byte_18002D803, 10h
0x18000bcc7  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bcce  jz      short loc_18000BD0C
0x18000bcd0  xor     eax, eax
0x18000bcd2  lea     r8, aPostnewhttpreq; "PostNewHttpRequest"
0x18000bcd9  lea     rdx, aEnteringWs; "Entering %ws"
0x18000bce0  mov     word ptr [rsp+880h+var_830], ax
0x18000bce5  lea     rcx, [rsp+880h+var_830]
0x18000bcea  call    FormatRRASErrorString
0x18000bcef  test    cs:byte_18002D803, 10h
0x18000bcf6  jz      short loc_18000BD0C
0x18000bcf8  lea     r8, [rsp+880h+var_830]
0x18000bcfd  mov     rcx, r15
0x18000bd00  lea     rdx, RasSSTPSvcTraceInfo
0x18000bd07  call    McTemplateU0z_EventWriteTransfer
0x18000bd0c  lea     rdx, [rsp+880h+var_840]
0x18000bd11  xor     ecx, ecx
0x18000bd13  call    AllocateAndInitializeCallContext
0x18000bd18  mov     ebx, eax
0x18000bd1a  test    eax, eax
0x18000bd1c  jz      short loc_18000BD75
0x18000bd1e  test    cs:byte_18002D803, 8
0x18000bd25  jz      loc_18000BEFB
0x18000bd2b  mov     r8, [rsp+880h+var_840]
0x18000bd30  lea     rdx, aCoidHsFailureT; "CoId=%hs:Failure to allocate the callct"...
0x18000bd37  xor     ecx, ecx
0x18000bd39  add     r8, 228h
0x18000bd40  mov     word ptr [rsp+880h+var_830], cx
0x18000bd45  lea     rcx, [rsp+880h+var_830]
0x18000bd4a  call    FormatRRASErrorString
0x18000bd4f  test    cs:byte_18002D803, 8
0x18000bd56  jz      loc_18000BEFB
0x18000bd5c  lea     r8, [rsp+880h+var_830]
0x18000bd61  mov     rcx, r15
0x18000bd64  lea     rdx, RasSSTPSvcTraceError
0x18000bd6b  call    McTemplateU0z_EventWriteTransfer
0x18000bd70  jmp     loc_18000BEFB
0x18000bd75  mov     rcx, cs:SstpSvcGlobals
0x18000bd7c  add     rcx, 1A8h
0x18000bd83  call    GetBufferFromPool
0x18000bd88  mov     rdi, [rsp+880h+var_840]
0x18000bd8d  mov     rsi, rax
0x18000bd90  test    rax, rax
0x18000bd93  jnz     short loc_18000BDE2
0x18000bd95  test    cs:byte_18002D803, 8
0x18000bd9c  jz      short loc_18000BDD8
0x18000bd9e  lea     r8, [rdi+228h]
0x18000bda5  mov     word ptr [rsp+880h+var_830], ax
0x18000bdaa  lea     rdx, aCoidHsUnableTo_0; "CoId=%hs:Unable to allocate memory for "...
0x18000bdb1  lea     rcx, [rsp+880h+var_830]
0x18000bdb6  call    FormatRRASErrorString
0x18000bdbb  test    cs:byte_18002D803, 8
0x18000bdc2  jz      short loc_18000BDD8
0x18000bdc4  lea     r8, [rsp+880h+var_830]
0x18000bdc9  mov     rcx, r15
0x18000bdcc  lea     rdx, RasSSTPSvcTraceError
0x18000bdd3  call    McTemplateU0z_EventWriteTransfer
0x18000bdd8  mov     ebx, 8
0x18000bddd  jmp     loc_18000BEEB
0x18000bde2  mov     [rdi+100h], rsi
0x18000bde9  xorps   xmm0, xmm0
0x18000bdec  mov     dword ptr [rax+20h], 4567h
0x18000bdf3  movups  xmmword ptr [rax], xmm0
0x18000bdf6  movups  xmmword ptr [rax+10h], xmm0
0x18000bdfa  mov     dword ptr [rax+5Ch], 0
0x18000be01  mov     [rax+38h], rdi
0x18000be05  lock inc dword ptr [rdi+0D0h]
0x18000be0c  mov     rcx, cs:SstpSvcGlobals
0x18000be13  mov     rcx, [rcx+0A8h]; pio
0x18000be1a  call    cs:__imp_StartThreadpoolIo
0x18000be20  xor     edx, edx; Val
0x18000be22  lea     rcx, [rsi+60h]; void *
0x18000be26  mov     r8d, 360h; Size
0x18000be2c  call    memset_0
0x18000be31  mov     rcx, cs:SstpSvcGlobals
0x18000be38  lea     r9, [rsi+60h]; RequestBuffer
0x18000be3c  mov     [rsp+880h+Overlapped], rsi; Overlapped
0x18000be41  xor     r8d, r8d; Flags
0x18000be44  mov     [rsp+880h+BytesReturned], 0; BytesReturned
0x18000be4d  xor     edx, edx; RequestId
0x18000be4f  mov     [rsp+880h+RequestBufferLength], 4000h; RequestBufferLength
0x18000be57  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000be5b  call    cs:__imp_HttpReceiveHttpRequest
0x18000be61  mov     ebx, eax
0x18000be63  cmp     eax, 3E5h
0x18000be68  jz      loc_18000BEF9
0x18000be6e  test    eax, eax
0x18000be70  jz      loc_18000BEF9
0x18000be76  test    cs:byte_18002D803, 8
0x18000be7d  jz      short loc_18000BEBE
0x18000be7f  xor     eax, eax
0x18000be81  lea     r8, [rdi+228h]
0x18000be88  mov     r9d, ebx
0x18000be8b  mov     word ptr [rsp+880h+var_830], ax
0x18000be90  lea     rdx, aCoidHsHttprece; "CoId=%hs:HttpReceiveRequest fails with "...
0x18000be97  lea     rcx, [rsp+880h+var_830]
0x18000be9c  call    FormatRRASErrorString
0x18000bea1  test    cs:byte_18002D803, 8
0x18000bea8  jz      short loc_18000BEBE
0x18000beaa  lea     r8, [rsp+880h+var_830]
0x18000beaf  mov     rcx, r15
0x18000beb2  lea     rdx, RasSSTPSvcTraceError
0x18000beb9  call    McTemplateU0z_EventWriteTransfer
0x18000bebe  mov     rcx, cs:SstpSvcGlobals
0x18000bec5  mov     rcx, [rcx+0A8h]; pio
0x18000becc  call    cs:__imp_CancelThreadpoolIo
0x18000bed2  mov     rcx, cs:SstpSvcGlobals
0x18000bed9  mov     r8b, 1
0x18000bedc  add     rcx, 1A8h
0x18000bee3  mov     rdx, rsi
0x18000bee6  call    FreeBufferToPool
0x18000beeb  lea     rcx, [rdi+0D0h]
0x18000bef2  call    DereferenceRefCount
0x18000bef7  jmp     short loc_18000BEFB
0x18000bef9  xor     ebx, ebx
0x18000befb  test    cs:byte_18002D803, 10h
0x18000bf02  jz      short loc_18000BF40
0x18000bf04  xor     eax, eax
0x18000bf06  lea     r8, aPostnewhttpreq; "PostNewHttpRequest"
0x18000bf0d  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000bf14  mov     word ptr [rsp+880h+var_830], ax
0x18000bf19  lea     rcx, [rsp+880h+var_830]
0x18000bf1e  call    FormatRRASErrorString
0x18000bf23  test    cs:byte_18002D803, 10h
0x18000bf2a  jz      short loc_18000BF40
0x18000bf2c  lea     r8, [rsp+880h+var_830]
0x18000bf31  mov     rcx, r15
0x18000bf34  lea     rdx, RasSSTPSvcTraceInfo
0x18000bf3b  call    McTemplateU0z_EventWriteTransfer
0x18000bf40  mov     eax, ebx
0x18000bf42  mov     rcx, [rbp+780h+var_30]
0x18000bf49  xor     rcx, rsp; StackCookie
0x18000bf4c  call    __security_check_cookie
0x18000bf51  add     rsp, 860h
0x18000bf58  pop     r15
0x18000bf5a  pop     rdi
0x18000bf5b  pop     rsi
0x18000bf5c  pop     rbx
0x18000bf5d  pop     rbp
0x18000bf5e  retn
```
