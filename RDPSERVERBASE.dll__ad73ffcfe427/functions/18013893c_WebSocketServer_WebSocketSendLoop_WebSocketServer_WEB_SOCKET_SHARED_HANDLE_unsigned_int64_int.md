# WebSocketServer::WebSocketSendLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)

- ea: `0x18013893c`
- end: `0x180138ed8`
- name: `?WebSocketSendLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z`
- size: `1436`
- prototype: `__int64 __fastcall(WebSocketServer *__hidden this, struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *, unsigned __int64, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180134fac`
- `0x180136730`
- `0x18013893c`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180002294`
- `0x180076090`
- `0x18007a664`
- `0x18007e9e0`
- `0x18007f348`
- `0x18007f42c`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x180133f50`
- `0x18013893c`
- `0x180138ee0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138a2a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138a8a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138bac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138c5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138cd6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138a2a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138a8a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138bac`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138c5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138cd6`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180138e7f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180138e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138b12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138bbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138b12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138bbd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180138a97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180138a97`
- `websocket!WebSocketGetAction` at `0x1801389e4`
- `websocket!WebSocketGetAction` at `0x1801389e4`
- `websocket!WebSocketCompleteAction` at `0x180138b2c`
- `websocket!WebSocketCompleteAction` at `0x180138dbf`
- `websocket!WebSocketCompleteAction` at `0x180138b2c`
- `websocket!WebSocketCompleteAction` at `0x180138dbf`
- `websocket!WebSocketAbortHandle` at `0x180138da7`
- `websocket!WebSocketAbortHandle` at `0x180138da7`

## string_xrefs

- `0x180138b3d`: `WebSocketSendLoop - WEB_SOCKET_INDICATE_SEND_COMPLETE_ACTION - recursive WebSocketSendLoop to get WEB_SOCKET_NO_ACTION before OnSendDataComplete`

## pseudocode

```c
__int64 __fastcall WebSocketServer::WebSocketSendLoop(
        WebSocketServer *this,
        struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *a2,
        const char *a3,
        int a4)
{
  int v4; // esi
  unsigned __int64 v5; // r15
  WebSocketServer *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int Action; // r13d
  char *v12; // rbx
  RTL_SRWLOCK *v13; // r15
  char *v14; // r12
  __int64 NextOf; // rdi
  __int64 v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  char *v23; // rbx
  char *v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int ActivityIdPrefix; // eax
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  int v37; // [rsp+60h] [rbp-A0h]
  const char *v38; // [rsp+68h] [rbp-98h] BYREF
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+88h] [rbp-78h] BYREF
  GUID v43; // [rsp+90h] [rbp-70h] BYREF
  const char *v44; // [rsp+A0h] [rbp-60h] BYREF
  WebSocketServer *v45; // [rsp+A8h] [rbp-58h]
  char *v46; // [rsp+B0h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-40h] BYREF
  GUID v48[2]; // [rsp+D0h] [rbp-30h] BYREF
  GUID v49; // [rsp+F0h] [rbp-10h] BYREF

  v37 = a4;
  v44 = a3;
  memset(v48, 0, sizeof(v48));
  Block = 0;
  v4 = a4;
  v41 = 0;
  v5 = (unsigned __int64)a3;
  v45 = this;
  v7 = this;
  while ( 1 )
  {
    v8 = *((_QWORD *)a2 + 6);
    v35 = 0;
    v36 = 2;
    v42 = 0;
    Action = WebSocketGetAction(v8, 1, v48, &v36, &v35, &v42, &Block, &v41);
    if ( (Action & 0x80000000) != 0 )
      break;
    switch ( v35 )
    {
      case 0:
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 4) + 16LL))(*((_QWORD *)a2 + 4));
        return Action;
      case 1:
        v23 = (char *)Block;
        if ( Block )
          goto LABEL_28;
        v24 = (char *)operator new(0xC0u);
        v23 = v24;
        if ( v24 )
        {
          memset_0(v24, 0, 0xC0u);
          memset_0(v23, 0, 0xC0u);
          *((_QWORD *)v23 + 17) = 0xDEADCA11DEADCA11uLL;
LABEL_28:
          v43 = *(GUID *)(v23 + 36);
          EventActivityIdControl(2u, &v43);
          *((_QWORD *)v23 + 20) = a2;
          *((_QWORD *)v23 + 21) = v41;
          *((_QWORD *)v23 + 22) = v5;
          Action = WebSocketServer::WebSocketSendRawData(
                     v7,
                     v5,
                     (union _WEB_SOCKET_BUFFER *)v48,
                     v36,
                     (struct WebSocketServer::SEND_DATA_OVERLAPPED *)v23);
          if ( (Action & 0x80000000) == 0 )
            return Action;
          if ( !Block )
            operator delete(v23);
          if ( (unsigned int)CallbackContext > 2 )
          {
            v33 = 546;
            *(_QWORD *)&v43.Data1 = "WebSocketSendLoop";
            v34 = -2147467259;
            v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
            v38 = "WebSocket send data failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v28,
              (unsigned int)byte_180293AFB,
              v29,
              v30,
              (__int64)&v38,
              (__int64)&v34,
              (__int64)&v39,
              (__int64)&v33,
              (__int64)&v43);
          }
          WebSocketAbortHandle(*((_QWORD *)a2 + 6));
          break;
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          v33 = 511;
          *(_QWORD *)&v43.Data1 = "WebSocketSendLoop";
          v34 = -2147467259;
          v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          v38 = "Allocation of pOverlap for pong buffer failed.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v25,
            (unsigned int)byte_180293AB3,
            v26,
            v27,
            (__int64)&v38,
            (__int64)&v34,
            (__int64)&v39,
            (__int64)&v33,
            (__int64)&v43);
        }
        break;
      case 2:
        v12 = (char *)Block;
        ActivityId = *(GUID *)((char *)Block + 36);
        EventActivityIdControl(2u, &ActivityId);
        if ( v4 )
        {
          v33 = *((_DWORD *)v12 + 46);
          EventActivityIdControl(1u, &v49);
          v13 = (RTL_SRWLOCK *)((char *)v7 + 64);
          AcquireSRWLockShared((PSRWLOCK)v7 + 8);
          v14 = (char *)v7 + 176;
          NextOf = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx((char *)v7 + 176, 0);
          if ( !NextOf )
            goto LABEL_21;
          do
          {
            if ( !wcsicmp((const wchar_t *)(NextOf + 48), (const wchar_t *)v12 + 28) )
              break;
            NextOf = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(v14, NextOf);
          }
          while ( NextOf );
          if ( NextOf )
          {
            v16 = *(_QWORD *)(NextOf + 144);
            *(_DWORD *)(NextOf + 168) = 0;
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
            ReleaseSRWLockShared(v13);
            if ( v16 )
            {
              WebSocketCompleteAction(*((_QWORD *)a2 + 6), v41, 0);
              if ( (unsigned int)CallbackContext > 5 )
              {
                v44 = "WebSocketSendLoop - WEB_SOCKET_INDICATE_SEND_COMPLETE_ACTION - recursive WebSocketSendLoop to get "
                      "WEB_SOCKET_NO_ACTION before OnSendDataComplete";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v17,
                  (unsigned int)word_180293A32,
                  v18,
                  v19,
                  (__int64)&v44);
              }
              WebSocketServer::WebSocketSendLoop(v45, a2, 0, v37);
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, v33 == 0 ? 0xE8 : 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              EventActivityIdControl(2u, &v49);
              return Action;
            }
          }
          else
          {
LABEL_21:
            ReleaseSRWLockShared(v13);
            if ( (unsigned int)CallbackContext > 2 )
            {
              v46 = v12 + 56;
              v38 = "WebSocketSendLoop";
              v34 = 618;
              v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
              *(_QWORD *)&v43.Data1 = "Unable to find connection object for Id %s";
              v33 = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                v20,
                (unsigned int)&word_180293A56,
                v21,
                v22,
                (__int64)&v43,
                (__int64)&v33,
                (__int64)&v39,
                (__int64)&v34,
                (__int64)&v38,
                (__int64)&v46);
            }
            operator delete(v12);
          }
          EventActivityIdControl(2u, &v49);
          v7 = v45;
          v4 = v37;
          v5 = (unsigned __int64)v44;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids);
        }
        break;
    }
    WebSocketCompleteAction(*((_QWORD *)a2 + 6), v41, 0);
    if ( !v35 )
      return Action;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v10, v9);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
      ActivityIdPrefix,
      (__int64)"WebSocketGetAction failed",
      Action);
  }
  return Action;
}

```

## disassembly

```asm
0x18013893c  push    rbp
0x18013893e  push    rbx
0x18013893f  push    rsi
0x180138940  push    rdi
0x180138941  push    r12
0x180138943  push    r13
0x180138945  push    r14
0x180138947  push    r15
0x180138949  lea     rbp, [rsp-18h]
0x18013894e  sub     rsp, 118h
0x180138955  mov     rax, cs:__security_cookie
0x18013895c  xor     rax, rsp
0x18013895f  mov     [rbp+50h+var_50], rax
0x180138963  xorps   xmm0, xmm0
0x180138966  mov     [rsp+150h+var_F0], r9d
0x18013896b  xor     r12d, r12d
0x18013896e  mov     [rbp+50h+var_B0], r8
0x180138972  movdqu  [rbp+50h+var_80], xmm0
0x180138977  mov     [rsp+150h+Block], r12
0x18013897c  mov     esi, r9d
0x18013897f  movups  [rbp+50h+var_70], xmm0
0x180138983  mov     [rbp+50h+var_D0], r12
0x180138987  lea     rbx, WPP_GLOBAL_Control
0x18013898e  mov     r15, r8
0x180138991  mov     [rbp+50h+var_A8], rcx
0x180138995  mov     r14, rdx
0x180138998  mov     rdi, rcx
0x18013899b  mov     rcx, [r14+30h]
0x18013899f  lea     rax, [rbp+50h+var_D0]
0x1801389a3  mov     [rsp+150h+var_118], rax
0x1801389a8  lea     r9, [rsp+150h+var_F4]
0x1801389ad  lea     rax, [rsp+150h+Block]
0x1801389b2  mov     [rsp+150h+var_F8], r12d
0x1801389b7  mov     [rsp+150h+var_120], rax
0x1801389bc  lea     r8, [rbp+50h+var_80]
0x1801389c0  lea     rax, [rbp+50h+var_C8]
0x1801389c4  mov     [rsp+150h+var_F4], 2
0x1801389cc  mov     [rsp+150h+var_128], rax
0x1801389d1  mov     edx, 1
0x1801389d6  lea     rax, [rsp+150h+var_F8]
0x1801389db  mov     [rbp+50h+var_C8], r12d
0x1801389df  mov     [rsp+150h+var_130], rax
0x1801389e4  call    cs:__imp_WebSocketGetAction
0x1801389ea  mov     r13d, eax
0x1801389ed  test    eax, eax
0x1801389ef  js      loc_180138E67
0x1801389f5  mov     edx, [rsp+150h+var_F8]
0x1801389f9  test    edx, edx
0x1801389fb  jz      loc_180138E55
0x180138a01  sub     edx, 1
0x180138a04  jz      loc_180138C73
0x180138a0a  cmp     edx, 1
0x180138a0d  jnz     loc_180138DB4
0x180138a13  mov     rbx, [rsp+150h+Block]
0x180138a18  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x180138a1c  mov     ecx, 2; ControlCode
0x180138a21  movups  xmm0, xmmword ptr [rbx+24h]
0x180138a25  movdqu  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x180138a2a  call    cs:__imp_EventActivityIdControl
0x180138a30  test    esi, esi
0x180138a32  jnz     short loc_180138A77
0x180138a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180138a3b  lea     rbx, WPP_GLOBAL_Control
0x180138a42  cmp     rcx, rbx
0x180138a45  jz      loc_180138DB4
0x180138a4b  test    byte ptr [rcx+1Ch], 1
0x180138a4f  jz      loc_180138DB4
0x180138a55  cmp     byte ptr [rcx+19h], 1
0x180138a59  jb      loc_180138DB4
0x180138a5f  mov     rcx, [rcx+10h]
0x180138a63  lea     edx, [rsi+1Fh]
0x180138a66  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180138a6d  call    WPP_SF_
0x180138a72  jmp     loc_180138DB4
0x180138a77  mov     eax, [rbx+0B8h]
0x180138a7d  lea     rdx, [rbp+50h+var_60]; ActivityId
0x180138a81  mov     ecx, 1; ControlCode
0x180138a86  mov     [rsp+150h+var_100], eax
0x180138a8a  call    cs:__imp_EventActivityIdControl
0x180138a90  lea     r15, [rdi+40h]
0x180138a94  mov     rcx, r15; SRWLock
0x180138a97  call    cs:__imp_AcquireSRWLockShared
0x180138a9d  lea     r12, [rdi+0B0h]
0x180138aa4  xor     edx, edx
0x180138aa6  mov     rcx, r12
0x180138aa9  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x180138aae  lea     rsi, [rbx+38h]
0x180138ab2  mov     rdi, rax
0x180138ab5  test    rax, rax
0x180138ab8  jz      loc_180138BB7
0x180138abe  lea     rcx, [rdi+30h]; String1
0x180138ac2  mov     rdx, rsi; String2
0x180138ac5  call    _wcsicmp
0x180138aca  test    eax, eax
0x180138acc  jz      short loc_180138AE1
0x180138ace  mov     rdx, rdi
0x180138ad1  mov     rcx, r12
0x180138ad4  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x180138ad9  mov     rdi, rax
0x180138adc  test    rax, rax
0x180138adf  jnz     short loc_180138ABE
0x180138ae1  xor     r12d, r12d
0x180138ae4  test    rdi, rdi
0x180138ae7  jz      loc_180138BBA
0x180138aed  mov     rbx, [rdi+90h]
0x180138af4  mov     [rdi+0A8h], r12d
0x180138afb  test    rbx, rbx
0x180138afe  jz      short loc_180138B0F
0x180138b00  mov     rax, [rbx]
0x180138b03  mov     rcx, rbx
0x180138b06  mov     rax, [rax+8]
0x180138b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138b0f  mov     rcx, r15; SRWLock
0x180138b12  call    cs:__imp_ReleaseSRWLockShared
0x180138b18  test    rbx, rbx
0x180138b1b  jz      loc_180138C53
0x180138b21  mov     rdx, [rbp+50h+var_D0]
0x180138b25  xor     r8d, r8d
0x180138b28  mov     rcx, [r14+30h]
0x180138b2c  call    cs:__imp_WebSocketCompleteAction
0x180138b32  mov     eax, cs:CallbackContext
0x180138b38  cmp     eax, 5
0x180138b3b  jbe     short loc_180138B5D
0x180138b3d  lea     rax, aWebsocketsendl_0; "WebSocketSendLoop - WEB_SOCKET_INDICATE"...
0x180138b44  mov     [rbp+50h+var_B0], rax
0x180138b48  lea     rdx, word_180293A32
0x180138b4f  lea     rax, [rbp+50h+var_B0]
0x180138b53  mov     [rsp+150h+var_130], rax
0x180138b58  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180138b5d  mov     r9d, [rsp+150h+var_F0]; int
0x180138b62  xor     r8d, r8d; unsigned __int64
0x180138b65  mov     rcx, [rbp+50h+var_A8]; this
0x180138b69  mov     rdx, r14; struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *
0x180138b6c  call    ?WebSocketSendLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z; WebSocketServer::WebSocketSendLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)
0x180138b71  mov     r8d, [rsp+150h+var_100]
0x180138b76  mov     rcx, rbx
0x180138b79  mov     r9, [rbx]
0x180138b7c  mov     eax, r8d
0x180138b7f  neg     eax
0x180138b81  sbb     edx, edx
0x180138b83  mov     rax, [r9+18h]
0x180138b87  not     edx
0x180138b89  and     edx, 0E8h
0x180138b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138b94  mov     rax, [rbx]
0x180138b97  mov     rcx, rbx
0x180138b9a  mov     rax, [rax+10h]
0x180138b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138ba3  lea     rdx, [rbp+50h+var_60]; ActivityId
0x180138ba7  mov     ecx, 2; ControlCode
0x180138bac  call    cs:__imp_EventActivityIdControl
0x180138bb2  jmp     loc_180138EB5
0x180138bb7  xor     r12d, r12d
0x180138bba  mov     rcx, r15; SRWLock
0x180138bbd  call    cs:__imp_ReleaseSRWLockShared
0x180138bc3  mov     eax, cs:CallbackContext
0x180138bc9  cmp     eax, 2
0x180138bcc  jbe     short loc_180138C4B
0x180138bce  lea     rax, aWebsocketsendl_1; "WebSocketSendLoop"
0x180138bd5  mov     [rbp+50h+var_A0], rsi
0x180138bd9  mov     [rsp+150h+var_E8], rax
0x180138bde  lea     rdx, word_180293A56
0x180138be5  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138bec  mov     [rsp+150h+var_FC], 26Ah
0x180138bf4  mov     [rsp+150h+var_E0], rax
0x180138bf9  lea     rax, aUnableToFindCo; "Unable to find connection object for Id"...
0x180138c00  mov     qword ptr [rbp+50h+var_C0.Data1], rax
0x180138c04  lea     rax, [rbp+50h+var_A0]
0x180138c08  mov     [rsp+150h+var_108], rax
0x180138c0d  lea     rax, [rsp+150h+var_E8]
0x180138c12  mov     [rsp+150h+var_110], rax
0x180138c17  lea     rax, [rsp+150h+var_FC]
0x180138c1c  mov     [rsp+150h+var_118], rax
0x180138c21  lea     rax, [rsp+150h+var_E0]
0x180138c26  mov     [rsp+150h+var_120], rax
0x180138c2b  lea     rax, [rsp+150h+var_100]
0x180138c30  mov     [rsp+150h+var_128], rax
0x180138c35  lea     rax, [rbp+50h+var_C0]
0x180138c39  mov     [rsp+150h+var_130], rax
0x180138c3e  mov     [rsp+150h+var_100], 80004005h
0x180138c46  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180138c4b  mov     rcx, rbx; Block
0x180138c4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180138c53  lea     rdx, [rbp+50h+var_60]; ActivityId
0x180138c57  mov     ecx, 2; ControlCode
0x180138c5c  call    cs:__imp_EventActivityIdControl
0x180138c62  mov     rdi, [rbp+50h+var_A8]
0x180138c66  mov     esi, [rsp+150h+var_F0]
0x180138c6a  mov     r15, [rbp+50h+var_B0]
0x180138c6e  jmp     loc_180138DAD
0x180138c73  mov     rbx, [rsp+150h+Block]
0x180138c78  test    rbx, rbx
0x180138c7b  jnz     short loc_180138CC4
0x180138c7d  mov     ecx, 0C0h; Size
0x180138c82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180138c87  mov     rbx, rax
0x180138c8a  test    rax, rax
0x180138c8d  jz      loc_180138DD5
0x180138c93  mov     r13d, 0C0h
0x180138c99  xor     edx, edx; Val
0x180138c9b  mov     r8d, r13d; Size
0x180138c9e  mov     rcx, rax; void *
0x180138ca1  call    memset_0
0x180138ca6  mov     r8d, r13d; Size
0x180138ca9  xor     edx, edx; Val
0x180138cab  mov     rcx, rbx; void *
0x180138cae  call    memset_0
0x180138cb3  mov     rax, 0DEADCA11DEADCA11h
0x180138cbd  mov     [rbx+88h], rax
0x180138cc4  movups  xmm0, xmmword ptr [rbx+24h]
0x180138cc8  lea     rdx, [rbp+50h+var_C0]; ActivityId
0x180138ccc  mov     ecx, 2; ControlCode
0x180138cd1  movdqu  xmmword ptr [rbp+50h+var_C0.Data1], xmm0
0x180138cd6  call    cs:__imp_EventActivityIdControl
0x180138cdc  mov     [rbx+0A0h], r14
0x180138ce3  lea     r8, [rbp+50h+var_80]; union _WEB_SOCKET_BUFFER *
0x180138ce7  mov     rax, [rbp+50h+var_D0]
0x180138ceb  mov     rdx, r15; unsigned __int64
0x180138cee  mov     [rbx+0A8h], rax
0x180138cf5  mov     rcx, rdi; this
0x180138cf8  mov     [rbx+0B0h], r15
0x180138cff  mov     r9d, [rsp+150h+var_F4]; unsigned int
0x180138d04  mov     [rsp+150h+var_130], rbx; struct WebSocketServer::SEND_DATA_OVERLAPPED *
0x180138d09  call    ?WebSocketSendRawData@WebSocketServer@@AEAAJ_KPEAT_WEB_SOCKET_BUFFER@@KPEAUSEND_DATA_OVERLAPPED@1@@Z; WebSocketServer::WebSocketSendRawData(unsigned __int64,_WEB_SOCKET_BUFFER *,ulong,WebSocketServer::SEND_DATA_OVERLAPPED *)
0x180138d0e  mov     r13d, eax
0x180138d11  test    eax, eax
0x180138d13  jns     loc_180138EB5
0x180138d19  cmp     [rsp+150h+Block], r12
0x180138d1e  jnz     short loc_180138D28
0x180138d20  mov     rcx, rbx; Block
0x180138d23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180138d28  mov     eax, cs:CallbackContext
0x180138d2e  cmp     eax, 2
0x180138d31  jbe     short loc_180138DA3
0x180138d33  lea     rax, aWebsocketsendl_1; "WebSocketSendLoop"
0x180138d3a  mov     [rsp+150h+var_100], 222h
0x180138d42  mov     qword ptr [rbp+50h+var_C0.Data1], rax
0x180138d46  lea     rdx, byte_180293AFB
0x180138d4d  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138d54  mov     [rsp+150h+var_FC], 80004005h
0x180138d5c  mov     [rsp+150h+var_E0], rax
0x180138d61  lea     rax, aWebsocketSendD; "WebSocket send data failed"
0x180138d68  mov     [rsp+150h+var_E8], rax
0x180138d6d  lea     rax, [rbp+50h+var_C0]
0x180138d71  mov     [rsp+150h+var_110], rax
0x180138d76  lea     rax, [rsp+150h+var_100]
0x180138d7b  mov     [rsp+150h+var_118], rax
0x180138d80  lea     rax, [rsp+150h+var_E0]
0x180138d85  mov     [rsp+150h+var_120], rax
0x180138d8a  lea     rax, [rsp+150h+var_FC]
0x180138d8f  mov     [rsp+150h+var_128], rax
0x180138d94  lea     rax, [rsp+150h+var_E8]
0x180138d99  mov     [rsp+150h+var_130], rax
0x180138d9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180138da3  mov     rcx, [r14+30h]
0x180138da7  call    cs:__imp_WebSocketAbortHandle
0x180138dad  lea     rbx, WPP_GLOBAL_Control
0x180138db4  mov     rdx, [rbp+50h+var_D0]
0x180138db8  xor     r8d, r8d
0x180138dbb  mov     rcx, [r14+30h]
0x180138dbf  call    cs:__imp_WebSocketCompleteAction
0x180138dc5  cmp     [rsp+150h+var_F8], r12d
0x180138dca  jnz     loc_18013899B
0x180138dd0  jmp     loc_180138EB5
0x180138dd5  mov     eax, cs:CallbackContext
0x180138ddb  cmp     eax, 2
0x180138dde  jbe     short loc_180138DAD
0x180138de0  lea     rax, aWebsocketsendl_1; "WebSocketSendLoop"
0x180138de7  mov     [rsp+150h+var_100], 1FFh
0x180138def  mov     qword ptr [rbp+50h+var_C0.Data1], rax
0x180138df3  lea     rdx, byte_180293AB3
0x180138dfa  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138e01  mov     [rsp+150h+var_FC], 80004005h
0x180138e09  mov     [rsp+150h+var_E0], rax
0x180138e0e  lea     rax, aAllocationOfPo; "Allocation of pOverlap for pong buffer "...
0x180138e15  mov     [rsp+150h+var_E8], rax
0x180138e1a  lea     rax, [rbp+50h+var_C0]
0x180138e1e  mov     [rsp+150h+var_110], rax
0x180138e23  lea     rax, [rsp+150h+var_100]
0x180138e28  mov     [rsp+150h+var_118], rax
0x180138e2d  lea     rax, [rsp+150h+var_E0]
0x180138e32  mov     [rsp+150h+var_120], rax
0x180138e37  lea     rax, [rsp+150h+var_FC]
0x180138e3c  mov     [rsp+150h+var_128], rax
0x180138e41  lea     rax, [rsp+150h+var_E8]
0x180138e46  mov     [rsp+150h+var_130], rax
0x180138e4b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180138e50  jmp     loc_180138DAD
0x180138e55  mov     rcx, [r14+20h]
0x180138e59  mov     rax, [rcx]
0x180138e5c  mov     rax, [rax+10h]
0x180138e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138e65  jmp     short loc_180138EB5
0x180138e67  mov     rax, cs:WPP_GLOBAL_Control
0x180138e6e  cmp     rax, rbx
0x180138e71  jz      short loc_180138EB5
0x180138e73  test    byte ptr [rax+1Ch], 8
0x180138e77  jz      short loc_180138EB5
0x180138e79  cmp     byte ptr [rax+19h], 2
0x180138e7d  jb      short loc_180138EB5
  ... truncated ...
```
