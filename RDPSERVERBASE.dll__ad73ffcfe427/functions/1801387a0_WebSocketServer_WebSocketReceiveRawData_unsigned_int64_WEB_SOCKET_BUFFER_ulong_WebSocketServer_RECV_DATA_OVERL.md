# WebSocketServer::WebSocketReceiveRawData(unsigned __int64,_WEB_SOCKET_BUFFER *,ulong,WebSocketServer::RECV_DATA_OVERLAPPED *)

- ea: `0x1801387a0`
- end: `0x180138933`
- name: `?WebSocketReceiveRawData@WebSocketServer@@AEAAJ_KPEAT_WEB_SOCKET_BUFFER@@KPEAURECV_DATA_OVERLAPPED@1@@Z`
- size: `403`
- prototype: `__int64 __fastcall(WebSocketServer *__hidden this, unsigned __int64, union _WEB_SOCKET_BUFFER *, unsigned int, LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180137c30`

## callees

- `0x18000116c`
- `0x18007a404`
- `0x1801387a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801387de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801387de`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180138896`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180138896`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180138839`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180138839`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180138871`
- `HTTPAPI!HttpReceiveRequestEntityBody` at `0x180138871`

## pseudocode

```c
__int64 __fastcall WebSocketServer::WebSocketReceiveRawData(
        WebSocketServer *this,
        __int64 a2,
        PVOID *a3,
        unsigned int a4,
        LPOVERLAPPED a5)
{
  LPOVERLAPPED Overlapped; // r15
  unsigned int v9; // edi
  ULONG v10; // eax
  signed int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  const char *v16; // [rsp+50h] [rbp-20h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-10h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+38h] BYREF
  int v19; // [rsp+B8h] [rbp+48h] BYREF

  v18 = a2;
  Overlapped = a5;
  ActivityId = *(GUID *)((char *)&a5[1].Internal + 4);
  EventActivityIdControl(2u, &ActivityId);
  if ( a4 != 1
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids, a4);
  }
  v9 = 0;
  if ( a4 )
  {
    while ( 1 )
    {
      LODWORD(Overlapped[1].Internal) = 4;
      StartThreadpoolIo(*((PTP_IO *)this + 20));
      v10 = HttpReceiveRequestEntityBody(
              *((HANDLE *)this + 19),
              (HTTP_REQUEST_ID)Overlapped[5].Pointer,
              0,
              a3[2 * v9],
              (ULONG)a3[2 * v9 + 1],
              0,
              Overlapped);
      v11 = v10;
      if ( v10 )
      {
        if ( v10 != 997 )
          break;
      }
      if ( ++v9 >= a4 )
        return 0;
    }
    CancelThreadpoolIo(*((PTP_IO *)this + 20));
    if ( (unsigned int)CallbackContext > 2 )
    {
      v19 = 1414;
      a5 = (LPOVERLAPPED)"WebSocketReceiveRawData";
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      LODWORD(v18) = v11;
      *(_QWORD *)&ActivityId.Data1 = "HttpReceiveRequestEntityBody (WS) failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)word_180293602,
        v13,
        v14,
        (__int64)&ActivityId,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v19,
        (__int64)&a5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801387a0  mov     [rsp-28h+arg_0], rbx
0x1801387a5  mov     [rsp-28h+arg_10], rsi
0x1801387aa  mov     [rsp-28h+arg_8], rdx
0x1801387af  push    rbp
0x1801387b0  push    rdi
0x1801387b1  push    r12
0x1801387b3  push    r14
0x1801387b5  push    r15
0x1801387b7  mov     rbp, rsp
0x1801387ba  sub     rsp, 70h
0x1801387be  mov     r15, [rbp+arg_20]
0x1801387c2  lea     rdx, [rbp+ActivityId]; ActivityId
0x1801387c6  mov     r14, rcx
0x1801387c9  mov     esi, r9d
0x1801387cc  mov     ecx, 2; ControlCode
0x1801387d1  mov     r12, r8
0x1801387d4  movups  xmm0, xmmword ptr [r15+24h]
0x1801387d9  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1801387de  call    cs:__imp_EventActivityIdControl
0x1801387e4  cmp     esi, 1
0x1801387e7  jz      short loc_180138820
0x1801387e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801387f0  lea     rax, WPP_GLOBAL_Control
0x1801387f7  cmp     rcx, rax
0x1801387fa  jz      short loc_180138820
0x1801387fc  test    byte ptr [rcx+1Ch], 1
0x180138800  jz      short loc_180138820
0x180138802  cmp     byte ptr [rcx+19h], 1
0x180138806  jb      short loc_180138820
0x180138808  mov     rcx, [rcx+10h]
0x18013880c  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180138813  mov     edx, 24h ; '$'
0x180138818  mov     r9d, esi
0x18013881b  call    WPP_SF_d
0x180138820  xor     edi, edi
0x180138822  test    esi, esi
0x180138824  jz      loc_180138918
0x18013882a  mov     dword ptr [r15+20h], 4
0x180138832  mov     rcx, [r14+0A0h]; pio
0x180138839  call    cs:__imp_StartThreadpoolIo
0x18013883f  mov     rdx, [r15+0B0h]; RequestId
0x180138846  xor     r8d, r8d; Flags
0x180138849  mov     rcx, [r14+98h]; RequestQueueHandle
0x180138850  mov     [rsp+70h+Overlapped], r15; Overlapped
0x180138855  mov     r9d, edi
0x180138858  add     r9, r9
0x18013885b  mov     [rsp+70h+BytesReturned], 0; BytesReturned
0x180138864  mov     eax, [r12+r9*8+8]
0x180138869  mov     r9, [r12+r9*8]; EntityBuffer
0x18013886d  mov     [rsp+70h+EntityBufferLength], eax; EntityBufferLength
0x180138871  call    cs:__imp_HttpReceiveRequestEntityBody
0x180138877  mov     ebx, eax
0x180138879  test    eax, eax
0x18013887b  jz      short loc_180138884
0x18013887d  cmp     eax, 3E5h
0x180138882  jnz     short loc_18013888F
0x180138884  inc     edi
0x180138886  cmp     edi, esi
0x180138888  jb      short loc_18013882A
0x18013888a  jmp     loc_180138918
0x18013888f  mov     rcx, [r14+0A0h]; pio
0x180138896  call    cs:__imp_CancelThreadpoolIo
0x18013889c  mov     eax, cs:CallbackContext
0x1801388a2  cmp     eax, 2
0x1801388a5  jbe     short loc_180138918
0x1801388a7  mov     [rbp+arg_18], 586h
0x1801388ae  lea     rax, aWebsocketrecei_0; "WebSocketReceiveRawData"
0x1801388b5  mov     [rbp+arg_20], rax
0x1801388b9  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801388c0  mov     [rbp+var_20], rax
0x1801388c4  test    ebx, ebx
0x1801388c6  jle     short loc_1801388D1
0x1801388c8  movzx   ebx, bx
0x1801388cb  or      ebx, 80070000h
0x1801388d1  lea     rax, aHttpreceivereq_1; "HttpReceiveRequestEntityBody (WS) faile"...
0x1801388d8  mov     dword ptr [rbp+arg_8], ebx
0x1801388db  mov     qword ptr [rbp+ActivityId.Data1], rax
0x1801388df  lea     rdx, word_180293602
0x1801388e6  lea     rax, [rbp+arg_20]
0x1801388ea  mov     [rsp+70h+var_30], rax
0x1801388ef  lea     rax, [rbp+arg_18]
0x1801388f3  mov     [rsp+70h+var_38], rax
0x1801388f8  lea     rax, [rbp+var_20]
0x1801388fc  mov     [rsp+70h+Overlapped], rax
0x180138901  lea     rax, [rbp+arg_8]
0x180138905  mov     [rsp+70h+BytesReturned], rax
0x18013890a  lea     rax, [rbp+ActivityId]
0x18013890e  mov     qword ptr [rsp+70h+EntityBufferLength], rax
0x180138913  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180138918  lea     r11, [rsp+70h+var_s0]
0x18013891d  xor     eax, eax
0x18013891f  mov     rbx, [r11+30h]
0x180138923  mov     rsi, [r11+40h]
0x180138927  mov     rsp, r11
0x18013892a  pop     r15
0x18013892c  pop     r14
0x18013892e  pop     r12
0x180138930  pop     rdi
0x180138931  pop     rbp
0x180138932  retn
```
