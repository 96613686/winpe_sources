# WebSocketServer::SendResponse(unsigned __int64,ushort *,_GUID,WebSocketServer::OVERLAP_ID,_HTTP_RESPONSE_V2 *)

- ea: `0x180136aec`
- end: `0x180136d0a`
- name: `?SendResponse@WebSocketServer@@AEAAJ_KPEAGU_GUID@@W4OVERLAP_ID@1@PEAU_HTTP_RESPONSE_V2@@@Z`
- size: `542`
- prototype: `int __high(unsigned __int64, unsigned __int16 *, struct _GUID, enum WebSocketServer::OVERLAP_ID, struct _HTTP_RESPONSE_V2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1801344cc`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x18003b118`
- `0x18007f42c`
- `0x18007f6b0`
- `0x180136aec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180136bdc`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180136bdc`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180136b72`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180136b72`
- `HTTPAPI!HttpSendHttpResponse` at `0x180136bb5`
- `HTTPAPI!HttpSendHttpResponse` at `0x180136bb5`

## pseudocode

```c
__int64 __fastcall WebSocketServer::SendResponse(
        __int64 a1,
        HTTP_REQUEST_ID a2,
        const unsigned __int16 *a3,
        _OWORD *a4,
        int a5,
        HTTP_RESPONSE *HttpResponse)
{
  char *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  char *Overlapped; // rbx
  ULONG v15; // r8d
  ULONG v16; // eax
  signed int v17; // ebx
  unsigned int v18; // edi
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+50h] [rbp-30h] BYREF
  int v23; // [rsp+54h] [rbp-2Ch] BYREF
  struct _HTTP_CACHE_POLICY CachePolicy; // [rsp+58h] [rbp-28h] BYREF
  const char *v25; // [rsp+60h] [rbp-20h] BYREF
  const char *v26; // [rsp+68h] [rbp-18h] BYREF
  const char *v27; // [rsp+70h] [rbp-10h] BYREF
  const char *v28; // [rsp+78h] [rbp-8h] BYREF

  CachePolicy = 0;
  v10 = (char *)operator new(0x88u);
  Overlapped = v10;
  if ( v10 )
  {
    memset_0(v10 + 52, 0, 0x54u);
    *(_OWORD *)Overlapped = 0;
    *((_OWORD *)Overlapped + 1) = 0;
    *((_DWORD *)Overlapped + 8) = a5;
    *(_OWORD *)(Overlapped + 36) = *a4;
    if ( a3 )
      StringCchCopyW((unsigned __int16 *)Overlapped + 28, 0x28u, a3);
    StartThreadpoolIo(*(PTP_IO *)(a1 + 160));
    v15 = 70;
    if ( a5 != 3 )
      v15 = 0;
    v16 = HttpSendHttpResponse(
            *(HANDLE *)(a1 + 152),
            a2,
            v15,
            HttpResponse,
            &CachePolicy,
            0,
            0,
            0,
            (LPOVERLAPPED)Overlapped,
            0);
    v17 = v16;
    if ( !v16 || v16 == 997 )
    {
      return 0;
    }
    else
    {
      v18 = -2147467259;
      CancelThreadpoolIo(*(PTP_IO *)(a1 + 160));
      if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = 2465;
        v25 = "SendResponse";
        v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        v23 = v17;
        v27 = "HttpSendHttpResponse failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&word_180293016,
          v19,
          v20,
          (__int64)&v27,
          (__int64)&v23,
          (__int64)&v26,
          (__int64)&v22,
          (__int64)&v25);
      }
    }
  }
  else
  {
    v18 = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v23 = 2434;
      v27 = "Failed allocationg CONNECTION_OVERLAPPED";
      v22 = -2147024882;
      v26 = "SendResponse";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v28 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)&word_1802930AE,
        v12,
        v13,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v26,
        (__int64)&v27);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180136aec  push    rbp
0x180136aee  push    rbx
0x180136aef  push    rsi
0x180136af0  push    rdi
0x180136af1  push    r12
0x180136af3  push    r14
0x180136af5  push    r15
0x180136af7  mov     rbp, rsp
0x180136afa  sub     rsp, 80h
0x180136b01  mov     rsi, rcx
0x180136b04  mov     qword ptr [rbp+var_28.Policy], 0
0x180136b0c  mov     ecx, 88h; Size
0x180136b11  mov     r15, r9
0x180136b14  mov     rdi, r8
0x180136b17  mov     r12, rdx
0x180136b1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180136b1f  mov     rbx, rax
0x180136b22  test    rax, rax
0x180136b25  jz      loc_180136C6E
0x180136b2b  xor     edx, edx; Val
0x180136b2d  lea     rcx, [rax+34h]; void *
0x180136b31  lea     r8d, [rdx+54h]; Size
0x180136b35  call    memset_0
0x180136b3a  mov     r14d, [rbp+arg_20]
0x180136b3e  xorps   xmm0, xmm0
0x180136b41  movups  xmmword ptr [rbx], xmm0
0x180136b44  movups  xmmword ptr [rbx+10h], xmm0
0x180136b48  mov     [rbx+20h], r14d
0x180136b4c  movups  xmm0, xmmword ptr [r15]
0x180136b50  movdqu  xmmword ptr [rbx+24h], xmm0
0x180136b55  test    rdi, rdi
0x180136b58  jz      short loc_180136B6B
0x180136b5a  lea     rcx, [rbx+38h]; unsigned __int16 *
0x180136b5e  mov     r8, rdi; unsigned __int16 *
0x180136b61  mov     edx, 28h ; '('; unsigned __int64
0x180136b66  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180136b6b  mov     rcx, [rsi+0A0h]; pio
0x180136b72  call    cs:__imp_StartThreadpoolIo
0x180136b78  mov     r9, [rbp+HttpResponse]; HttpResponse
0x180136b7c  xor     eax, eax
0x180136b7e  mov     rcx, [rsi+98h]; RequestQueueHandle
0x180136b85  cmp     r14d, 3
0x180136b89  mov     [rsp+80h+LogData], rax; LogData
0x180136b8e  mov     rdx, r12; RequestId
0x180136b91  mov     [rsp+80h+Overlapped], rbx; Overlapped
0x180136b96  mov     [rsp+80h+Reserved2], eax; Reserved2
0x180136b9a  lea     r8d, [rax+46h]
0x180136b9e  mov     [rsp+80h+Reserved1], rax; Reserved1
0x180136ba3  cmovnz  r8d, eax; Flags
0x180136ba7  mov     [rsp+80h+BytesSent], rax; BytesSent
0x180136bac  lea     rax, [rbp+var_28]
0x180136bb0  mov     [rsp+80h+CachePolicy], rax; CachePolicy
0x180136bb5  call    cs:__imp_HttpSendHttpResponse
0x180136bbb  mov     ebx, eax
0x180136bbd  test    eax, eax
0x180136bbf  jz      loc_180136C67
0x180136bc5  cmp     eax, 3E5h
0x180136bca  jz      loc_180136C67
0x180136bd0  mov     rcx, [rsi+0A0h]; pio
0x180136bd7  mov     edi, 80004005h
0x180136bdc  call    cs:__imp_CancelThreadpoolIo
0x180136be2  mov     ecx, cs:CallbackContext
0x180136be8  cmp     ecx, 2
0x180136beb  jbe     loc_180136CF6
0x180136bf1  mov     [rbp+var_30], 9A1h
0x180136bf8  lea     rax, aSendresponse; "SendResponse"
0x180136bff  mov     [rbp+var_20], rax
0x180136c03  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180136c0a  mov     [rbp+var_18], rax
0x180136c0e  test    ebx, ebx
0x180136c10  jle     short loc_180136C1B
0x180136c12  movzx   ebx, bx
0x180136c15  or      ebx, 80070000h
0x180136c1b  lea     rax, aHttpsendhttpre_0; "HttpSendHttpResponse failed"
0x180136c22  mov     [rbp+var_2C], ebx
0x180136c25  mov     [rbp+var_10], rax
0x180136c29  lea     rdx, word_180293016
0x180136c30  lea     rax, [rbp+var_20]
0x180136c34  mov     [rsp+80h+Overlapped], rax
0x180136c39  lea     rax, [rbp+var_30]
0x180136c3d  mov     qword ptr [rsp+80h+Reserved2], rax
0x180136c42  lea     rax, [rbp+var_18]
0x180136c46  mov     [rsp+80h+Reserved1], rax
0x180136c4b  lea     rax, [rbp+var_2C]
0x180136c4f  mov     [rsp+80h+BytesSent], rax
0x180136c54  lea     rax, [rbp+var_10]
0x180136c58  mov     [rsp+80h+CachePolicy], rax
0x180136c5d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180136c62  jmp     loc_180136CF6
0x180136c67  xor     edi, edi
0x180136c69  jmp     loc_180136CF6
0x180136c6e  mov     eax, cs:CallbackContext
0x180136c74  mov     edi, 8007000Eh
0x180136c79  cmp     eax, 2
0x180136c7c  jbe     short loc_180136CF6
0x180136c7e  lea     rax, aFailedAllocati; "Failed allocationg CONNECTION_OVERLAPPE"...
0x180136c85  mov     [rbp+var_2C], 982h
0x180136c8c  mov     [rbp+var_10], rax
0x180136c90  lea     rdx, word_1802930AE
0x180136c97  lea     rax, aSendresponse; "SendResponse"
0x180136c9e  mov     [rbp+var_30], edi
0x180136ca1  mov     [rbp+var_18], rax
0x180136ca5  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180136cac  mov     [rbp+var_20], rax
0x180136cb0  lea     rax, aErrorCondition; "Error condition failed"
0x180136cb7  mov     [rbp+var_8], rax
0x180136cbb  lea     rax, [rbp+var_10]
0x180136cbf  mov     [rsp+80h+LogData], rax
0x180136cc4  lea     rax, [rbp+var_18]
0x180136cc8  mov     [rsp+80h+Overlapped], rax
0x180136ccd  lea     rax, [rbp+var_2C]
0x180136cd1  mov     qword ptr [rsp+80h+Reserved2], rax
0x180136cd6  lea     rax, [rbp+var_20]
0x180136cda  mov     [rsp+80h+Reserved1], rax
0x180136cdf  lea     rax, [rbp+var_30]
0x180136ce3  mov     [rsp+80h+BytesSent], rax
0x180136ce8  lea     rax, [rbp+var_8]
0x180136cec  mov     [rsp+80h+CachePolicy], rax
0x180136cf1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180136cf6  mov     eax, edi
0x180136cf8  add     rsp, 80h
0x180136cff  pop     r15
0x180136d01  pop     r14
0x180136d03  pop     r12
0x180136d05  pop     rdi
0x180136d06  pop     rsi
0x180136d07  pop     rbx
0x180136d08  pop     rbp
0x180136d09  retn
```
