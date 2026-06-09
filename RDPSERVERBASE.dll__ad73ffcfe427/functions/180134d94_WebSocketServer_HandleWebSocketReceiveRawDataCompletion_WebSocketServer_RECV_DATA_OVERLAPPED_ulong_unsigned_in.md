# WebSocketServer::HandleWebSocketReceiveRawDataCompletion(WebSocketServer::RECV_DATA_OVERLAPPED *,ulong,unsigned __int64)

- ea: `0x180134d94`
- end: `0x180134fa3`
- name: `?HandleWebSocketReceiveRawDataCompletion@WebSocketServer@@AEAAXPEAURECV_DATA_OVERLAPPED@1@K_K@Z`
- size: `527`
- prototype: `void __fastcall(WebSocketServer *__hidden this, struct WebSocketServer::RECV_DATA_OVERLAPPED *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180135290`

## callees

- `0x18000116c`
- `0x180002170`
- `0x180076090`
- `0x180134280`
- `0x180134d94`
- `0x180137c30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134dcc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180134dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134de7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180134f53`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180134f53`
- `websocket!WebSocketCompleteAction` at `0x180134f09`
- `websocket!WebSocketCompleteAction` at `0x180134f09`

## string_xrefs

- `0x180134e39`: `IO receive status (edge): The I/O operation has been aborted because of either a thread exit or an application request.`
- `0x180134e0e`: `HandleWebSocketReceiveRawDataCompletion`
- `0x180134e7d`: `HandleWebSocketReceiveRawDataCompletion`
- `0x180134ea4`: `HandleWebSocketReceiveRawDataCompletion reports IO error: last error=%d`

## pseudocode

```c
void __fastcall WebSocketServer::HandleWebSocketReceiveRawDataCompletion(
        WebSocketServer *this,
        struct WebSocketServer::RECV_DATA_OVERLAPPED *a2,
        unsigned int a3,
        unsigned int a4)
{
  struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *v8; // r14
  __int64 v9; // r12
  unsigned __int64 v10; // r13
  DWORD LastError; // ecx
  int v12; // r8d
  unsigned __int64 v13; // r9
  int v14; // eax
  __int64 v15; // rdx
  char v16; // bl
  int ActivityIdPrefix; // eax
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+C8h] [rbp+48h] BYREF
  int v24; // [rsp+D0h] [rbp+50h] BYREF

  ActivityId = *(GUID *)((char *)a2 + 36);
  EventActivityIdControl(2u, &ActivityId);
  v8 = (struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *)*((_QWORD *)a2 + 20);
  v9 = *((_QWORD *)a2 + 21);
  v10 = *((_QWORD *)a2 + 22);
  LastError = GetLastError();
  if ( a3 )
  {
    if ( a3 == 995 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v24 = 1451;
        v18 = "HandleWebSocketReceiveRawDataCompletion";
        v23 = -2147467259;
        v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
        v20 = "IO receive status (edge): The I/O operation has been aborted because of either a thread exit or an application request.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          LastError,
          (unsigned int)&byte_180293567,
          v12,
          v13,
          (__int64)&v20,
          (__int64)&v23,
          (__int64)&v19,
          (__int64)&v24,
          (__int64)&v18);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v24 = LastError;
      v20 = "HandleWebSocketReceiveRawDataCompletion";
      v23 = 1455;
      v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v21 = "HandleWebSocketReceiveRawDataCompletion reports IO error: last error=%d";
      LODWORD(v18) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        LastError,
        (unsigned int)&byte_1802935AF,
        v12,
        v13,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v24);
    }
    WebSocketServer::HandleDisconnected(this, a2, a3, v13);
  }
  WebSocketCompleteAction(*((_QWORD *)v8 + 6), v9, a4);
  *((_QWORD *)a2 + 21) = 0;
  v14 = WebSocketServer::WebSocketReceiveLoop(this, v8, v10, 1);
  v16 = v14;
  if ( v14 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v15);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
      ActivityIdPrefix,
      (__int64)"WebSocketReceiveLoop failed",
      v16);
  }
}

```

## disassembly

```asm
0x180134d94  mov     [rsp-38h+arg_0], rbx
0x180134d99  push    rbp
0x180134d9a  push    rsi
0x180134d9b  push    rdi
0x180134d9c  push    r12
0x180134d9e  push    r13
0x180134da0  push    r14
0x180134da2  push    r15
0x180134da4  mov     rbp, rsp
0x180134da7  sub     rsp, 80h
0x180134dae  movups  xmm0, xmmword ptr [rdx+24h]
0x180134db2  mov     rbx, rdx
0x180134db5  mov     rsi, rcx
0x180134db8  lea     rdx, [rbp+ActivityId]; ActivityId
0x180134dbc  mov     ecx, 2; ControlCode
0x180134dc1  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x180134dc6  mov     r15, r9
0x180134dc9  mov     edi, r8d
0x180134dcc  call    cs:__imp_EventActivityIdControl
0x180134dd2  mov     r14, [rbx+0A0h]
0x180134dd9  mov     r12, [rbx+0A8h]
0x180134de0  mov     r13, [rbx+0B0h]
0x180134de7  call    cs:__imp_GetLastError
0x180134ded  mov     ecx, eax
0x180134def  test    edi, edi
0x180134df1  jz      loc_180134EFF
0x180134df7  mov     eax, cs:CallbackContext
0x180134dfd  cmp     edi, 3E3h
0x180134e03  jnz     short loc_180134E78
0x180134e05  cmp     eax, 2
0x180134e08  jbe     loc_180134EF1
0x180134e0e  lea     rax, aHandlewebsocke_1; "HandleWebSocketReceiveRawDataCompletion"
0x180134e15  mov     [rbp+arg_10], 5ABh
0x180134e1c  mov     [rbp+var_30], rax
0x180134e20  lea     rdx, byte_180293567
0x180134e27  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134e2e  mov     [rbp+arg_8], 80004005h
0x180134e35  mov     [rbp+var_28], rax
0x180134e39  lea     rax, aIoReceiveStatu; "IO receive status (edge): The I/O opera"...
0x180134e40  mov     [rbp+var_20], rax
0x180134e44  lea     rax, [rbp+var_30]
0x180134e48  mov     [rsp+80h+var_40], rax
0x180134e4d  lea     rax, [rbp+arg_10]
0x180134e51  mov     [rsp+80h+var_48], rax
0x180134e56  lea     rax, [rbp+var_28]
0x180134e5a  mov     [rsp+80h+var_50], rax
0x180134e5f  lea     rax, [rbp+arg_8]
0x180134e63  mov     [rsp+80h+var_58], rax
0x180134e68  lea     rax, [rbp+var_20]
0x180134e6c  mov     [rsp+80h+var_60], rax
0x180134e71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180134e76  jmp     short loc_180134EF1
0x180134e78  cmp     eax, 2
0x180134e7b  jbe     short loc_180134EF1
0x180134e7d  lea     rax, aHandlewebsocke_1; "HandleWebSocketReceiveRawDataCompletion"
0x180134e84  mov     [rbp+arg_10], ecx
0x180134e87  mov     [rbp+var_20], rax
0x180134e8b  lea     rdx, byte_1802935AF
0x180134e92  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180134e99  mov     [rbp+arg_8], 5AFh
0x180134ea0  mov     [rbp+var_28], rax
0x180134ea4  lea     rax, aHandlewebsocke_0; "HandleWebSocketReceiveRawDataCompletion"...
0x180134eab  mov     [rbp+var_18], rax
0x180134eaf  lea     rax, [rbp+arg_10]
0x180134eb3  mov     [rsp+80h+var_38], rax
0x180134eb8  lea     rax, [rbp+var_20]
0x180134ebc  mov     [rsp+80h+var_40], rax
0x180134ec1  lea     rax, [rbp+arg_8]
0x180134ec5  mov     [rsp+80h+var_48], rax
0x180134eca  lea     rax, [rbp+var_28]
0x180134ece  mov     [rsp+80h+var_50], rax
0x180134ed3  lea     rax, [rbp+var_30]
0x180134ed7  mov     [rsp+80h+var_58], rax
0x180134edc  lea     rax, [rbp+var_18]
0x180134ee0  mov     [rsp+80h+var_60], rax
0x180134ee5  mov     dword ptr [rbp+var_30], 80004005h
0x180134eec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180134ef1  mov     r8d, edi; unsigned int
0x180134ef4  mov     rdx, rbx; struct WebSocketServer::CONNECTION_OVERLAPPED *
0x180134ef7  mov     rcx, rsi; this
0x180134efa  call    ?HandleDisconnected@WebSocketServer@@AEAAXPEAUCONNECTION_OVERLAPPED@1@K_K@Z; WebSocketServer::HandleDisconnected(WebSocketServer::CONNECTION_OVERLAPPED *,ulong,unsigned __int64)
0x180134eff  mov     rcx, [r14+30h]
0x180134f03  mov     r8d, r15d
0x180134f06  mov     rdx, r12
0x180134f09  call    cs:__imp_WebSocketCompleteAction
0x180134f0f  mov     r9d, 1; int
0x180134f15  mov     qword ptr [rbx+0A8h], 0
0x180134f20  mov     r8, r13; unsigned __int64
0x180134f23  mov     rdx, r14; struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *
0x180134f26  mov     rcx, rsi; this
0x180134f29  call    ?WebSocketReceiveLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z; WebSocketServer::WebSocketReceiveLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)
0x180134f2e  mov     ebx, eax
0x180134f30  test    eax, eax
0x180134f32  jns     short loc_180134F88
0x180134f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180134f3b  lea     rax, WPP_GLOBAL_Control
0x180134f42  cmp     rcx, rax
0x180134f45  jz      short loc_180134F88
0x180134f47  test    byte ptr [rcx+1Ch], 8
0x180134f4b  jz      short loc_180134F88
0x180134f4d  cmp     byte ptr [rcx+19h], 2
0x180134f51  jb      short loc_180134F88
0x180134f53  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180134f59  lea     rcx, aWebsocketrecei_7; "WebSocketReceiveLoop failed"
0x180134f60  mov     dword ptr [rsp+80h+var_58], ebx
0x180134f64  mov     [rsp+80h+var_60], rcx
0x180134f69  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180134f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180134f77  mov     edx, 25h ; '%'
0x180134f7c  mov     r9d, eax
0x180134f7f  mov     rcx, [rcx+10h]
0x180134f83  call    WPP_SF_DsD
0x180134f88  mov     rbx, [rsp+80h+arg_0]
0x180134f90  add     rsp, 80h
0x180134f97  pop     r15
0x180134f99  pop     r14
0x180134f9b  pop     r13
0x180134f9d  pop     r12
0x180134f9f  pop     rdi
0x180134fa0  pop     rsi
0x180134fa1  pop     rbp
0x180134fa2  retn
```
