# WebSocketServer::WebSocketReceiveLoop(WebSocketServer::WEB_SOCKET_SHARED_HANDLE *,unsigned __int64,int)

- ea: `0x180137c30`
- end: `0x180138799`
- name: `?WebSocketReceiveLoop@WebSocketServer@@AEAAJPEAUWEB_SOCKET_SHARED_HANDLE@1@_KH@Z`
- size: `2921`
- prototype: `__int64 __fastcall(WebSocketServer *__hidden this, struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *, unsigned __int64, int)`
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180134d94`
- `0x180134fac`
- `0x180136270`
- `0x180137c30`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180002170`
- `0x180002294`
- `0x180007660`
- `0x18002aafc`
- `0x18002b14c`
- `0x18007a664`
- `0x18007e9e0`
- `0x18007f348`
- `0x18007f390`
- `0x18007f42c`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x180133f50`
- `0x180134280`
- `0x180137c30`
- `0x1801387a0`
- `0x180138ee0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137d31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137dc7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137f2f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138030`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138335`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138357`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801384f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801386c7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137d31`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137dc7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180137f2f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138030`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138335`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180138357`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801384f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801386c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180137e2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180137f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138024`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801381a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18013827b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180137e2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180137f10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180138024`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801381a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18013827b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180137dd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180137dd5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801386b8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801386b8`
- `websocket!WebSocketGetAction` at `0x180137cde`
- `websocket!WebSocketGetAction` at `0x180137cde`
- `websocket!WebSocketReceive` at `0x1801381b5`
- `websocket!WebSocketReceive` at `0x1801381b5`
- `websocket!WebSocketCompleteAction` at `0x180137f52`
- `websocket!WebSocketCompleteAction` at `0x180138295`
- `websocket!WebSocketCompleteAction` at `0x180137f52`
- `websocket!WebSocketCompleteAction` at `0x180138295`
- `websocket!WebSocketAbortHandle` at `0x180138415`
- `websocket!WebSocketAbortHandle` at `0x180138415`

## string_xrefs

- `0x180137d62`: `WEB_SOCKET_INDICATE_RECEIVE_COMPLETE_ACTION has no buffers`
- `0x18013810e`: `Copy received WebSocket data failed.`
- `0x1801382a6`: `WebSocketReceiveLoop - WEB_SOCKET_INDICATE_RECEIVE_COMPLETE_ACTION - recursive WebSocketReceiveLoop to get WEB_SOCKET_NO_ACTION before OnReceiveDataComplete`
- `0x18013817b`: `WebSocket - Received less data than minimum. Issuing another read.`
- `0x18013843e`: `WebSocketReceiveLoop - WEB_SOCKET_INDICATE_SEND_COMPLETE_ACTION, context: %p`

## pseudocode

```c
__int64 __fastcall WebSocketServer::WebSocketReceiveLoop(
        WebSocketServer *this,
        struct WebSocketServer::WEB_SOCKET_SHARED_HANDLE *a2,
        unsigned __int64 a3,
        int a4)
{
  unsigned __int64 v4; // rdi
  WebSocketServer *v6; // r12
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int Action; // r13d
  char *v12; // rbx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // esi
  int v17; // r12d
  WebSocketServer *v18; // rdi
  __int64 NextOf; // r15
  const wchar_t *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned int v27; // edi
  unsigned __int64 v28; // r9
  __int64 v29; // rcx
  unsigned int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned int v34; // edi
  __int64 v35; // rsi
  __int64 v36; // r15
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  char *v40; // rax
  char *v41; // rdi
  struct _OVERLAPPED *v42; // rbx
  unsigned __int64 v43; // rdx
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  char *v47; // rax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  char *v51; // rbx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  _QWORD *v55; // rax
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  const char *v58; // [rsp+58h] [rbp-A8h] BYREF
  const char *v59; // [rsp+60h] [rbp-A0h] BYREF
  const char *v60; // [rsp+68h] [rbp-98h] BYREF
  GUID v61; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v62; // [rsp+80h] [rbp-80h] BYREF
  const char *v63; // [rsp+88h] [rbp-78h] BYREF
  int v64; // [rsp+90h] [rbp-70h] BYREF
  int v65; // [rsp+94h] [rbp-6Ch] BYREF
  WebSocketServer *v66; // [rsp+98h] [rbp-68h]
  unsigned __int64 v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h]
  ULONG_PTR v69; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+B8h] [rbp-48h] BYREF
  void *Source[2]; // [rsp+C0h] [rbp-40h] BYREF
  GUID ActivityId; // [rsp+D0h] [rbp-30h] BYREF
  GUID v73; // [rsp+E0h] [rbp-20h] BYREF
  GUID v74; // [rsp+F0h] [rbp-10h] BYREF

  v68 = a4;
  *(_OWORD *)Source = 0;
  v4 = a3;
  v67 = a3;
  v66 = this;
  v6 = this;
  Block = 0;
  v69 = 0;
  while ( 1 )
  {
    v7 = *((_QWORD *)a2 + 6);
    v65 = 0;
    v62 = 1;
    v64 = 0;
    Action = WebSocketGetAction(v7, 2, Source, &v62, &v65, &v64, &Block, &v69);
    if ( Action < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
        v59 = "WebSocketGetAction failed";
        LODWORD(v58) = 931;
        v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
        v57 = Action;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)byte_18029394D,
          v9,
          v10,
          (__int64)&v59,
          (__int64)&v57,
          (__int64)&v60,
          (__int64)&v58,
          (__int64)&v61);
      }
LABEL_77:
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 4) + 16LL))(*((_QWORD *)a2 + 4));
      return (unsigned int)Action;
    }
    switch ( v65 )
    {
      case 0:
        goto LABEL_77;
      case 1:
        v47 = (char *)operator new(0xC0u);
        v51 = v47;
        if ( !v47 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
            v59 = "Allocation of pOverlap for pong buffer failed.";
            LODWORD(v58) = 1295;
            v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
            v57 = -2147467259;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v48,
              (unsigned int)byte_18029369D,
              v49,
              v50,
              (__int64)&v59,
              (__int64)&v57,
              (__int64)&v60,
              (__int64)&v58,
              (__int64)&v61);
          }
          goto LABEL_26;
        }
        memset_0(v47 + 52, 0, 0x8Cu);
        *(_OWORD *)v51 = 0;
        *((_OWORD *)v51 + 1) = 0;
        *((_DWORD *)v51 + 8) = 0;
        *(_OWORD *)(v51 + 36) = 0;
        v61 = 0;
        EventActivityIdControl(2u, &v61);
        *((_QWORD *)v51 + 20) = a2;
        *((_QWORD *)v51 + 21) = v69;
        *((_QWORD *)v51 + 22) = v4;
        *((_QWORD *)v51 + 17) = 0xDEADCA11DEADCA11uLL;
        Action = WebSocketServer::WebSocketSendRawData(
                   v6,
                   v4,
                   (union _WEB_SOCKET_BUFFER *)Source,
                   v62,
                   (struct WebSocketServer::SEND_DATA_OVERLAPPED *)v51);
        if ( Action >= 0 )
          return (unsigned int)Action;
        operator delete(v51);
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v58) = Action;
          v59 = "WebSocketSendRawData failed";
          *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
          v57 = 1326;
          v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          LODWORD(v63) = Action;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v52,
            (unsigned int)byte_1802936E5,
            v53,
            v54,
            (__int64)&v59,
            (__int64)&v63,
            (__int64)&v60,
            (__int64)&v57,
            (__int64)&v61,
            (__int64)&v58);
        }
        goto LABEL_62;
      case 2:
        if ( (unsigned int)CallbackContext > 2 )
        {
          *(_QWORD *)&v61.Data1 = Block;
          v63 = "WebSocketReceiveLoop - WEB_SOCKET_INDICATE_SEND_COMPLETE_ACTION, context: %p";
          v60 = "WebSocketReceiveLoop";
          LODWORD(v58) = 1344;
          v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          v57 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v8,
            (unsigned int)word_18029364A,
            v9,
            v10,
            (__int64)&v63,
            (__int64)&v57,
            (__int64)&v59,
            (__int64)&v58,
            (__int64)&v60,
            (__int64)&v61);
        }
        goto LABEL_26;
      case 3:
        v42 = (struct _OVERLAPPED *)Block;
        v73 = *(GUID *)((char *)Block + 36);
        EventActivityIdControl(2u, &v73);
        v42[5].Internal = (ULONG_PTR)a2;
        v42[5].InternalHigh = v69;
        v42[5].Pointer = (PVOID)v4;
        Action = WebSocketServer::WebSocketReceiveRawData(v6, v43, (union _WEB_SOCKET_BUFFER *)Source, v62, v42);
        if ( Action >= 0 )
          return (unsigned int)Action;
        if ( (unsigned int)CallbackContext > 2 )
        {
          *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
          v59 = "WebSocketReceiveRawData failed";
          LODWORD(v58) = 982;
          v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          v57 = Action;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v44,
            (unsigned int)byte_1802938BD,
            v45,
            v46,
            (__int64)&v59,
            (__int64)&v57,
            (__int64)&v60,
            (__int64)&v58,
            (__int64)&v61);
        }
LABEL_62:
        WebSocketAbortHandle(*((_QWORD *)a2 + 6));
        goto LABEL_26;
    }
    if ( v65 == 4 )
      break;
LABEL_26:
    WebSocketCompleteAction(*((_QWORD *)a2 + 6), v69, 0);
    if ( !v65 )
      return (unsigned int)Action;
  }
  v12 = (char *)Block;
  ActivityId = *(GUID *)((char *)Block + 36);
  EventActivityIdControl(2u, &ActivityId);
  if ( v62 )
  {
    v16 = (unsigned int)Source[1];
    v17 = 0;
  }
  else
  {
    v16 = 0;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v58 = "WebSocketReceiveLoop";
      v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      LODWORD(v63) = 1021;
      v60 = "WEB_SOCKET_INDICATE_RECEIVE_COMPLETE_ACTION has no buffers";
      v57 = Action;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)byte_180293905,
        v14,
        v15,
        (__int64)&v60,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v63,
        (__int64)&v58);
    }
    v17 = 1;
  }
  EventActivityIdControl(1u, &v74);
  v18 = v66;
  AcquireSRWLockShared((PSRWLOCK)v66 + 8);
  NextOf = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx((char *)v18 + 176, 0);
  if ( !NextOf )
  {
LABEL_17:
    v6 = v18;
    ReleaseSRWLockShared((PSRWLOCK)v18 + 8);
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v58) = 1059;
      *(_QWORD *)&v61.Data1 = v12 + 56;
      v60 = "WebSocketReceiveLoop";
      v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v57 = -2147467259;
      v63 = "Unable to find connection object for %s";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v24,
        (unsigned int)byte_180293809,
        v25,
        v26,
        (__int64)&v63,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60,
        (__int64)&v61);
    }
    operator delete(v12);
    EventActivityIdControl(2u, &v74);
    v4 = v67;
    goto LABEL_26;
  }
  v20 = (const wchar_t *)(v12 + 56);
  while ( wcsicmp((const wchar_t *)(NextOf + 48), v20) )
  {
    NextOf = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx((char *)v18 + 176, NextOf);
    v20 = (const wchar_t *)(v12 + 56);
    if ( !NextOf )
      goto LABEL_17;
  }
  if ( v64 == -2147483644 )
  {
    v27 = 0;
    if ( !v17 && WORD2(Source[1]) != 1000 )
    {
      v27 = 1226;
      if ( WORD2(Source[1]) == 1006 )
        v27 = 1236;
    }
    v6 = v66;
    *(_DWORD *)(NextOf + 152) = 0;
    ReleaseSRWLockShared((PSRWLOCK)v6 + 8);
    WebSocketServer::HandleDisconnected(v6, (struct WebSocketServer::CONNECTION_OVERLAPPED *)v12, v27, v28);
LABEL_25:
    EventActivityIdControl(2u, &v74);
    v4 = v67;
    goto LABEL_26;
  }
  if ( (unsigned int)(v64 + 2147483646) > 1 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v57 = v64;
      LODWORD(v63) = 1124;
      v60 = "WebSocketReceiveLoop";
      *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop unexpected buffer type %d";
      v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      LODWORD(v58) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&word_180293866,
        v22,
        v23,
        (__int64)&v61,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v63,
        (__int64)&v60,
        (__int64)&v57);
    }
    *(_DWORD *)(NextOf + 152) = 0;
    v6 = v18;
    ReleaseSRWLockShared((PSRWLOCK)v18 + 8);
    EventActivityIdControl(2u, &v74);
    v4 = v67;
    goto LABEL_26;
  }
  if ( !v16 || v17 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v58) = 1134;
      *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
      v57 = -2147467259;
      v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v59 = "WebSocketReceiveLoop - ERROR_NO_DATA";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v21,
        (unsigned int)byte_180293779,
        v22,
        v23,
        (__int64)&v59,
        (__int64)&v57,
        (__int64)&v60,
        (__int64)&v58,
        (__int64)&v61);
    }
    goto LABEL_48;
  }
  v29 = *((unsigned int *)v12 + 47);
  v30 = *((_DWORD *)v12 + 38) - v29;
  if ( v30 < v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_b1a8cc76119c395613772ef098e23945_Traceguids);
    }
LABEL_48:
    v34 = 232;
    goto LABEL_49;
  }
  if ( memcpy_s((void *const)(*((_QWORD *)v12 + 18) + v29), v30, Source[0], v16) )
  {
    v34 = 232;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v58) = 1164;
      *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop";
      v57 = -2147467259;
      v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      v59 = "Copy received WebSocket data failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v31,
        (unsigned int)byte_1802937C1,
        v32,
        v33,
        (__int64)&v59,
        (__int64)&v57,
        (__int64)&v60,
        (__int64)&v58,
        (__int64)&v61);
    }
  }
  else
  {
    *((_DWORD *)v12 + 47) += v16;
    v34 = 0;
    if ( *((_DWORD *)v12 + 47) < *((_DWORD *)v12 + 46) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        *(_QWORD *)&v61.Data1 = "WebSocket - Received less data than minimum. Issuing another read.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v31,
          (unsigned int)byte_180293755,
          v32,
          v33,
          (__int64)&v61);
      }
      v6 = v66;
      ReleaseSRWLockShared((PSRWLOCK)v66 + 8);
      Action = WebSocketReceive(*((_QWORD *)a2 + 6), 0, v12);
      goto LABEL_25;
    }
  }
LABEL_49:
  v35 = *(_QWORD *)(NextOf + 144);
  *(_DWORD *)(NextOf + 152) = 0;
  v36 = *((_QWORD *)v12 + 17);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  v6 = v66;
  ReleaseSRWLockShared((PSRWLOCK)v66 + 8);
  if ( !v35 )
    goto LABEL_25;
  WebSocketCompleteAction(*((_QWORD *)a2 + 6), v69, 0);
  if ( (unsigned int)CallbackContext > 5 )
  {
    *(_QWORD *)&v61.Data1 = "WebSocketReceiveLoop - WEB_SOCKET_INDICATE_RECEIVE_COMPLETE_ACTION - recursive WebSocketRece"
                            "iveLoop to get WEB_SOCKET_NO_ACTION before OnReceiveDataComplete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v37,
      (unsigned int)byte_180293731,
      v38,
      v39,
      (__int64)&v61);
  }
  WebSocketServer::WebSocketReceiveLoop(v6, a2, v67, v68);
  if ( v68 || v34 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 32LL))(v35, v34, *((unsigned int *)v12 + 47));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  else
  {
    v40 = (char *)operator new(0x38u);
    v41 = v40;
    if ( v40 )
    {
      *(_QWORD *)v40 = 0;
      *((_QWORD *)v40 + 1) = 0;
      *((_QWORD *)v40 + 2) = 0;
      *(GUID *)(v40 + 24) = GUID_NULL;
    }
    else
    {
      v41 = 0;
    }
    *(_QWORD *)v41 = v35;
    *((_QWORD *)v41 + 1) = v36;
    *((_DWORD *)v41 + 4) = *((_DWORD *)v12 + 47);
    *((_DWORD *)v41 + 5) = 0;
    *(_OWORD *)(v41 + 24) = *(_OWORD *)(v12 + 36);
    CTSCriticalSection::Lock((WebSocketServer *)((char *)v6 + 376));
    v55 = (_QWORD *)*((_QWORD *)v6 + 46);
    *((_QWORD *)v41 + 5) = (char *)v6 + 360;
    *((_QWORD *)v41 + 6) = v55;
    *v55 = v41 + 40;
    ++*((_DWORD *)v6 + 88);
    *((_QWORD *)v6 + 46) = v41 + 40;
    CTSCriticalSection::UnLock((WebSocketServer *)((char *)v6 + 376));
    SubmitThreadpoolWork(*((PTP_WORK *)v6 + 21));
  }
  EventActivityIdControl(2u, &v74);
  return (unsigned int)Action;
}

```

## disassembly

```asm
0x180137c30  push    rbp
0x180137c32  push    rbx
0x180137c33  push    rsi
0x180137c34  push    rdi
0x180137c35  push    r12
0x180137c37  push    r13
0x180137c39  push    r14
0x180137c3b  push    r15
0x180137c3d  lea     rbp, [rsp-18h]
0x180137c42  sub     rsp, 118h
0x180137c49  mov     rax, cs:__security_cookie
0x180137c50  xor     rax, rsp
0x180137c53  mov     [rbp+50h+var_50], rax
0x180137c57  xorps   xmm0, xmm0
0x180137c5a  mov     [rbp+50h+var_A8], r9d
0x180137c5e  movdqu  xmmword ptr [rbp+50h+Source], xmm0
0x180137c63  mov     rdi, r8
0x180137c66  mov     [rbp+50h+var_B0], r8
0x180137c6a  mov     r14, rdx
0x180137c6d  mov     [rbp+50h+var_B8], rcx
0x180137c71  mov     r12, rcx
0x180137c74  mov     [rbp+50h+Block], 0
0x180137c7c  mov     [rbp+50h+var_A0], 0
0x180137c84  lea     r15, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x180137c8b  mov     esi, 2
0x180137c90  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137c97  mov     rcx, [r14+30h]
0x180137c9b  lea     rax, [rbp+50h+var_A0]
0x180137c9f  mov     [rsp+150h+var_118], rax
0x180137ca4  lea     r9, [rbp+50h+var_D0]
0x180137ca8  lea     rax, [rbp+50h+Block]
0x180137cac  mov     [rbp+50h+var_BC], 0
0x180137cb3  mov     [rsp+150h+var_120], rax
0x180137cb8  lea     r8, [rbp+50h+Source]
0x180137cbc  lea     rax, [rbp+50h+var_C0]
0x180137cc0  mov     [rbp+50h+var_D0], 1
0x180137cc7  mov     [rsp+150h+var_128], rax
0x180137ccc  mov     edx, esi
0x180137cce  lea     rax, [rbp+50h+var_BC]
0x180137cd2  mov     [rbp+50h+var_C0], 0
0x180137cd9  mov     [rsp+150h+var_130], rax
0x180137cde  call    cs:__imp_WebSocketGetAction
0x180137ce4  mov     r13d, eax
0x180137ce7  test    eax, eax
0x180137ce9  js      loc_1801386FB
0x180137cef  mov     edx, [rbp+50h+var_BC]
0x180137cf2  test    edx, edx
0x180137cf4  jz      loc_180138766
0x180137cfa  sub     edx, 1
0x180137cfd  jz      loc_1801384A8
0x180137d03  sub     edx, 1
0x180137d06  jz      loc_180138420
0x180137d0c  sub     edx, 1
0x180137d0f  jz      loc_180138344
0x180137d15  cmp     edx, 1
0x180137d18  jnz     loc_180137F47
0x180137d1e  mov     rbx, [rbp+50h+Block]
0x180137d22  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x180137d26  mov     ecx, esi; ControlCode
0x180137d28  movups  xmm0, xmmword ptr [rbx+24h]
0x180137d2c  movdqu  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x180137d31  call    cs:__imp_EventActivityIdControl
0x180137d37  cmp     [rbp+50h+var_D0], 0
0x180137d3b  jnz     short loc_180137DB8
0x180137d3d  mov     eax, cs:CallbackContext
0x180137d43  xor     esi, esi
0x180137d45  cmp     eax, 2
0x180137d48  jbe     short loc_180137DB0
0x180137d4a  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137d51  mov     [rsp+150h+var_F8], r15
0x180137d56  mov     [rsp+150h+var_F0], rax
0x180137d5b  lea     rdx, byte_180293905
0x180137d62  lea     rax, aWebSocketIndic; "WEB_SOCKET_INDICATE_RECEIVE_COMPLETE_AC"...
0x180137d69  mov     dword ptr [rbp+50h+var_C8], 3FDh
0x180137d70  mov     [rsp+150h+var_E8], rax
0x180137d75  lea     rax, [rsp+150h+var_F8]
0x180137d7a  mov     [rsp+150h+var_110], rax
0x180137d7f  lea     rax, [rbp+50h+var_C8]
0x180137d83  mov     [rsp+150h+var_118], rax
0x180137d88  lea     rax, [rsp+150h+var_F0]
0x180137d8d  mov     [rsp+150h+var_120], rax
0x180137d92  lea     rax, [rsp+150h+var_100]
0x180137d97  mov     [rsp+150h+var_128], rax
0x180137d9c  lea     rax, [rsp+150h+var_E8]
0x180137da1  mov     [rsp+150h+var_130], rax
0x180137da6  mov     [rsp+150h+var_100], r13d
0x180137dab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180137db0  mov     r12d, 1
0x180137db6  jmp     short loc_180137DBE
0x180137db8  mov     esi, dword ptr [rbp+50h+Source+8]
0x180137dbb  xor     r12d, r12d
0x180137dbe  lea     rdx, [rbp+50h+var_60]; ActivityId
0x180137dc2  mov     ecx, 1; ControlCode
0x180137dc7  call    cs:__imp_EventActivityIdControl
0x180137dcd  mov     rdi, [rbp+50h+var_B8]
0x180137dd1  lea     rcx, [rdi+40h]; SRWLock
0x180137dd5  call    cs:__imp_AcquireSRWLockShared
0x180137ddb  xor     edx, edx
0x180137ddd  lea     rcx, [rdi+0B0h]
0x180137de4  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x180137de9  mov     r15, rax
0x180137dec  test    rax, rax
0x180137def  jz      short loc_180137E24
0x180137df1  lea     rax, [rbx+38h]
0x180137df5  lea     rcx, [r15+30h]; String1
0x180137df9  mov     rdx, rax; String2
0x180137dfc  call    _wcsicmp
0x180137e01  test    eax, eax
0x180137e03  jz      loc_180137ECC
0x180137e09  mov     rdx, r15
0x180137e0c  lea     rcx, [rdi+0B0h]
0x180137e13  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x180137e18  mov     r15, rax
0x180137e1b  test    rax, rax
0x180137e1e  lea     rax, [rbx+38h]
0x180137e22  jnz     short loc_180137DF5
0x180137e24  lea     rcx, [rdi+40h]; SRWLock
0x180137e28  mov     r12, rdi
0x180137e2b  call    cs:__imp_ReleaseSRWLockShared
0x180137e31  mov     eax, cs:CallbackContext
0x180137e37  mov     esi, 2
0x180137e3c  cmp     eax, esi
0x180137e3e  jbe     loc_180138320
0x180137e44  lea     rax, [rbx+38h]
0x180137e48  mov     dword ptr [rsp+150h+var_F8], 423h
0x180137e50  mov     qword ptr [rsp+150h+var_E0.Data1], rax
0x180137e55  lea     r15, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x180137e5c  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137e63  mov     [rsp+150h+var_E8], r15
0x180137e68  mov     [rsp+150h+var_F0], rax
0x180137e6d  lea     rdx, byte_180293809
0x180137e74  lea     rax, aUnableToFindCo_0; "Unable to find connection object for %s"
0x180137e7b  mov     [rsp+150h+var_100], 80004005h
0x180137e83  mov     [rbp+50h+var_C8], rax
0x180137e87  lea     rax, [rsp+150h+var_E0]
0x180137e8c  mov     [rsp+150h+var_108], rax
0x180137e91  lea     rax, [rsp+150h+var_E8]
0x180137e96  mov     [rsp+150h+var_110], rax
0x180137e9b  lea     rax, [rsp+150h+var_F8]
0x180137ea0  mov     [rsp+150h+var_118], rax
0x180137ea5  lea     rax, [rsp+150h+var_F0]
0x180137eaa  mov     [rsp+150h+var_120], rax
0x180137eaf  lea     rax, [rsp+150h+var_100]
0x180137eb4  mov     [rsp+150h+var_128], rax
0x180137eb9  lea     rax, [rbp+50h+var_C8]
0x180137ebd  mov     [rsp+150h+var_130], rax
0x180137ec2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180137ec7  jmp     loc_180138327
0x180137ecc  mov     eax, [rbp+50h+var_C0]
0x180137ecf  cmp     eax, 80000004h
0x180137ed4  jnz     loc_180137F67
0x180137eda  xor     edi, edi
0x180137edc  test    r12d, r12d
0x180137edf  jnz     short loc_180137EFC
0x180137ee1  movzx   ecx, word ptr [rbp+50h+Source+0Ch]
0x180137ee5  sub     ecx, 3E8h
0x180137eeb  jz      short loc_180137EFC
0x180137eed  mov     edi, 4CAh
0x180137ef2  cmp     ecx, 6
0x180137ef5  jnz     short loc_180137EFC
0x180137ef7  mov     edi, 4D4h
0x180137efc  mov     r12, [rbp+50h+var_B8]
0x180137f00  mov     dword ptr [r15+98h], 0
0x180137f0b  lea     rcx, [r12+40h]; SRWLock
0x180137f10  call    cs:__imp_ReleaseSRWLockShared
0x180137f16  mov     r8d, edi; unsigned int
0x180137f19  mov     rdx, rbx; struct WebSocketServer::CONNECTION_OVERLAPPED *
0x180137f1c  mov     rcx, r12; this
0x180137f1f  call    ?HandleDisconnected@WebSocketServer@@AEAAXPEAUCONNECTION_OVERLAPPED@1@K_K@Z; WebSocketServer::HandleDisconnected(WebSocketServer::CONNECTION_OVERLAPPED *,ulong,unsigned __int64)
0x180137f24  mov     esi, 2
0x180137f29  lea     rdx, [rbp+50h+var_60]; ActivityId
0x180137f2d  mov     ecx, esi; ControlCode
0x180137f2f  call    cs:__imp_EventActivityIdControl
0x180137f35  mov     rdi, [rbp+50h+var_B0]
0x180137f39  lea     r15, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x180137f40  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137f47  mov     rdx, [rbp+50h+var_A0]
0x180137f4b  xor     r8d, r8d
0x180137f4e  mov     rcx, [r14+30h]
0x180137f52  call    cs:__imp_WebSocketCompleteAction
0x180137f58  cmp     [rbp+50h+var_BC], 0
0x180137f5c  jnz     loc_180137C97
0x180137f62  jmp     loc_180138776
0x180137f67  add     eax, 7FFFFFFEh
0x180137f6c  cmp     eax, 1
0x180137f6f  jbe     loc_180138046
0x180137f75  mov     eax, cs:CallbackContext
0x180137f7b  mov     esi, 2
0x180137f80  cmp     eax, esi
0x180137f82  jbe     loc_18013800B
0x180137f88  mov     eax, [rbp+50h+var_C0]
0x180137f8b  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180137f92  mov     [rsp+150h+var_100], eax
0x180137f96  lea     rdx, word_180293866
0x180137f9d  lea     rax, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x180137fa4  mov     dword ptr [rbp+50h+var_C8], 464h
0x180137fab  mov     [rsp+150h+var_E8], rax
0x180137fb0  lea     rax, aWebsocketrecei_2; "WebSocketReceiveLoop unexpected buffer "...
0x180137fb7  mov     qword ptr [rsp+150h+var_E0.Data1], rax
0x180137fbc  lea     rax, [rsp+150h+var_100]
0x180137fc1  mov     [rsp+150h+var_108], rax
0x180137fc6  lea     rax, [rsp+150h+var_E8]
0x180137fcb  mov     [rsp+150h+var_110], rax
0x180137fd0  lea     rax, [rbp+50h+var_C8]
0x180137fd4  mov     [rsp+150h+var_118], rax
0x180137fd9  lea     rax, [rsp+150h+var_F0]
0x180137fde  mov     [rsp+150h+var_120], rax
0x180137fe3  lea     rax, [rsp+150h+var_F8]
0x180137fe8  mov     [rsp+150h+var_128], rax
0x180137fed  lea     rax, [rsp+150h+var_E0]
0x180137ff2  mov     [rsp+150h+var_130], rax
0x180137ff7  mov     [rsp+150h+var_F0], rbx
0x180137ffc  mov     dword ptr [rsp+150h+var_F8], 80004005h
0x180138004  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180138009  jmp     short loc_180138012
0x18013800b  lea     rbx, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138012  lea     rcx, [rdi+40h]; SRWLock
0x180138016  mov     dword ptr [r15+98h], 0
0x180138021  mov     r12, rdi
0x180138024  call    cs:__imp_ReleaseSRWLockShared
0x18013802a  lea     rdx, [rbp+50h+var_60]; ActivityId
0x18013802e  mov     ecx, esi; ControlCode
0x180138030  call    cs:__imp_EventActivityIdControl
0x180138036  mov     rdi, [rbp+50h+var_B0]
0x18013803a  lea     r15, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x180138041  jmp     loc_180137F47
0x180138046  test    esi, esi
0x180138048  jz      loc_1801381C3
0x18013804e  test    r12d, r12d
0x180138051  jnz     loc_1801381C3
0x180138057  mov     ecx, [rbx+0BCh]
0x18013805d  mov     eax, [rbx+98h]
0x180138063  sub     eax, ecx
0x180138065  cmp     eax, esi
0x180138067  jnb     short loc_1801380AE
0x180138069  mov     rcx, cs:WPP_GLOBAL_Control
0x180138070  lea     rax, WPP_GLOBAL_Control
0x180138077  cmp     rcx, rax
0x18013807a  jz      loc_180138240
0x180138080  test    byte ptr [rcx+1Ch], 1
0x180138084  jz      loc_180138240
0x18013808a  cmp     byte ptr [rcx+19h], 1
0x18013808e  jb      loc_180138240
0x180138094  mov     rcx, [rcx+10h]
0x180138098  lea     edx, [r12+23h]
0x18013809d  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x1801380a4  call    WPP_SF_
0x1801380a9  jmp     loc_180138240
0x1801380ae  add     rcx, [rbx+90h]; Destination
0x1801380b5  mov     r8, [rbp+50h+Source]; Source
0x1801380b9  mov     r9d, esi; SourceSize
0x1801380bc  mov     edx, eax; DestinationSize
0x1801380be  call    memcpy_s
0x1801380c3  test    eax, eax
0x1801380c5  jz      loc_180138156
0x1801380cb  mov     eax, cs:CallbackContext
0x1801380d1  mov     edi, 0E8h
0x1801380d6  cmp     eax, 2
0x1801380d9  jbe     loc_180138245
0x1801380df  lea     rax, aWebsocketrecei_5; "WebSocketReceiveLoop"
0x1801380e6  mov     dword ptr [rsp+150h+var_F8], 48Ch
0x1801380ee  mov     qword ptr [rsp+150h+var_E0.Data1], rax
0x1801380f3  lea     rdx, byte_1802937C1
0x1801380fa  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180138101  mov     [rsp+150h+var_100], 80004005h
0x180138109  mov     [rsp+150h+var_E8], rax
0x18013810e  lea     rax, aCopyReceivedWe; "Copy received WebSocket data failed."
0x180138115  mov     [rsp+150h+var_F0], rax
0x18013811a  lea     rax, [rsp+150h+var_E0]
0x18013811f  mov     [rsp+150h+var_110], rax
0x180138124  lea     rax, [rsp+150h+var_F8]
0x180138129  mov     [rsp+150h+var_118], rax
0x18013812e  lea     rax, [rsp+150h+var_E8]
0x180138133  mov     [rsp+150h+var_120], rax
0x180138138  lea     rax, [rsp+150h+var_100]
0x18013813d  mov     [rsp+150h+var_128], rax
0x180138142  lea     rax, [rsp+150h+var_F0]
0x180138147  mov     [rsp+150h+var_130], rax
0x18013814c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180138151  jmp     loc_180138245
0x180138156  add     [rbx+0BCh], esi
0x18013815c  xor     edi, edi
0x18013815e  mov     eax, [rbx+0BCh]
0x180138164  cmp     eax, [rbx+0B8h]
0x18013816a  jnb     loc_180138245
0x180138170  mov     eax, cs:CallbackContext
0x180138176  cmp     eax, 4
0x180138179  jbe     short loc_18013819D
0x18013817b  lea     rax, aWebsocketRecei; "WebSocket - Received less data than min"...
0x180138182  mov     qword ptr [rsp+150h+var_E0.Data1], rax
0x180138187  lea     rdx, byte_180293755
0x18013818e  lea     rax, [rsp+150h+var_E0]
0x180138193  mov     [rsp+150h+var_130], rax
0x180138198  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18013819d  mov     r12, [rbp+50h+var_B8]
0x1801381a1  lea     rcx, [r12+40h]; SRWLock
0x1801381a6  call    cs:__imp_ReleaseSRWLockShared
0x1801381ac  mov     rcx, [r14+30h]
0x1801381b0  mov     r8, rbx
0x1801381b3  xor     edx, edx
  ... truncated ...
```
