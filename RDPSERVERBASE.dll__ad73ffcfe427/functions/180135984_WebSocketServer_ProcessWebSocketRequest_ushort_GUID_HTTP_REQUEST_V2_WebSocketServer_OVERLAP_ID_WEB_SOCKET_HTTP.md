# WebSocketServer::ProcessWebSocketRequest(ushort *,_GUID,_HTTP_REQUEST_V2 *,WebSocketServer::OVERLAP_ID *,_WEB_SOCKET_HTTP_HEADER * *,ulong *)

- ea: `0x180135984`
- end: `0x180136260`
- name: `?ProcessWebSocketRequest@WebSocketServer@@AEAAJPEAGU_GUID@@PEAU_HTTP_REQUEST_V2@@PEAW4OVERLAP_ID@1@PEAPEAU_WEB_SOCKET_HTTP_HEADER@@PEAK@Z`
- size: `2268`
- prototype: `__int64 __usercall@<rax>(WebSocketServer *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct _GUID *__struct_ptr@<r8>, struct _HTTP_REQUEST_V2 *@<r9>, enum WebSocketServer::OVERLAP_ID *, struct _WEB_SOCKET_HTTP_HEADER **, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1801344cc`

## callees

- `0x180001574`
- `0x180002294`
- `0x18003b118`
- `0x180076090`
- `0x180077aa0`
- `0x18007f348`
- `0x18007f390`
- `0x18007f42c`
- `0x18007f6b0`
- `0x180132e60`
- `0x18013352c`
- `0x180133f50`
- `0x180133f8c`
- `0x180135400`
- `0x180135984`
- `0x180137838`
- `0x1801391d0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801359b9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801359b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180136023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180136023`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135b55`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135bf7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135c78`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135cfd`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135d58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135ddf`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135e4a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135eae`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135f61`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013600c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136210`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135b55`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135bf7`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135c78`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135cfd`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135d58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135ddf`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135e4a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135eae`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180135f61`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18013600c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180136210`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180136033`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180136033`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180135a16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180135a16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801360c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180136173`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801360c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180136173`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801359d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1801359d0`
- `websocket!WebSocketCreateServerHandle` at `0x180135e77`
- `websocket!WebSocketCreateServerHandle` at `0x180135e77`

## string_xrefs

- `0x180135c83`: `StringCchCopy failed`
- `0x180135eb9`: `WebSocketCreateServerHandle failed`
- `0x180136197`: `Created new connection object %s for WebSocket channel`

## pseudocode

```c
__int64 __fastcall WebSocketServer::ProcessWebSocketRequest(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        struct _HTTP_REQUEST_V2 *a4,
        enum WebSocketServer::OVERLAP_ID *a5,
        struct _WEB_SOCKET_HTTP_HEADER **a6,
        unsigned int *a7)
{
  enum WebSocketServer::OVERLAP_ID *v11; // rdi
  __int64 i; // rbx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  int WebSocketResponseHeaders; // edi
  WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  char *v21; // rax
  char *v22; // rdi
  int ActivityIdPrefix; // eax
  int v24; // edx
  const char *v25; // rcx
  char *v26; // rax
  char *v27; // rdi
  GUID v28; // xmm0
  __int64 v29; // rax
  unsigned __int64 v30; // r11
  int v31; // eax
  int v32; // edx
  const char *v33; // rcx
  unsigned __int64 v34; // r11
  PSOCKADDR pLocalAddress; // r8
  rsize_t v36; // rdi
  rsize_t v37; // r9
  __int64 v38; // rdx
  int v39; // eax
  int v40; // edx
  __int64 v41; // rdx
  WebSocketServer *v42; // rcx
  __int64 v43; // rdx
  _DWORD *v44; // rax
  void **v45; // rdx
  const char *v46; // rcx
  int v47; // eax
  __int64 v48; // r8
  struct _WEB_SOCKET_HTTP_HEADER **v49; // r9
  unsigned int *v50; // rax
  __int64 v51; // rdx
  __int64 *v52; // rsi
  _QWORD *Ptr; // rax
  char IsEnabled; // al
  HTTP_CONNECTION_ID ConnectionId; // r9
  unsigned __int16 *v56; // rdx
  __int64 *v57; // rax
  __int64 v58; // rdx
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  int v62; // ecx
  int v63; // r8d
  int v64; // r9d
  int v65; // eax
  const char *v67; // [rsp+50h] [rbp-20h] BYREF
  const char *v68; // [rsp+58h] [rbp-18h] BYREF
  GUID ActivityId; // [rsp+60h] [rbp-10h] BYREF
  const char *v70; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v71; // [rsp+C0h] [rbp+50h] BYREF

  ActivityId = *a3;
  EventActivityIdControl(2u, &ActivityId);
  v11 = a5;
  *(_DWORD *)a5 = 7;
  AcquireSRWLockShared(this + 8);
  for ( i = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(&this[22], 0);
        i;
        i = CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(&this[22], i) )
  {
    if ( !wcsicmp((const wchar_t *)(i + 48), a2) )
      break;
  }
  ReleaseSRWLockShared(this + 8);
  if ( i )
  {
    v16 = (unsigned int)CallbackContext;
    *(_DWORD *)v11 = 2;
    WebSocketResponseHeaders = -2147467259;
    if ( v16 > 2 )
    {
      v71 = a2;
      v67 = "ProcessWebSocketRequest";
      LODWORD(a5) = 2986;
      v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
      *(_QWORD *)&ActivityId.Data1 = "Duplicate OUT channel request";
      LODWORD(v70) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v13,
        (unsigned int)qword_180292DD8,
        v14,
        v15,
        (__int64)&ActivityId,
        (__int64)&v70,
        (__int64)&v68,
        (__int64)&a5,
        (__int64)&v67,
        (__int64)&v71);
    }
    return (unsigned int)WebSocketResponseHeaders;
  }
  v18 = (WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)operator new(0x210u);
  if ( v18
    && (v19 = WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO::HTTP_TRANSPORT_CONNECTION_INFO(v18), (v20 = v19) != 0) )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v19 + 32) + 8LL))(*(_QWORD *)(v19 + 32));
    v21 = (char *)operator new(0xC0u);
    v22 = v21;
    if ( v21 )
    {
      memset_0(v21 + 52, 0, 0x8Cu);
      *(_OWORD *)v22 = 0;
      *((_OWORD *)v22 + 1) = 0;
      *((_DWORD *)v22 + 8) = 0;
      *(_OWORD *)(v22 + 36) = 0;
    }
    else
    {
      v22 = 0;
    }
    *(_QWORD *)(v20 + 160) = v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 2);
      v24 = 51;
      v25 = "RECV_DATA_OVERLAPPED";
LABEL_17:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        ActivityIdPrefix,
        (__int64)v25);
LABEL_18:
      WebSocketResponseHeaders = -2147024882;
LABEL_89:
      WebSocketServer::CleanupConnInfo(
        (WebSocketServer *)this,
        (struct WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)v20);
LABEL_82:
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 16LL))(*(_QWORD *)(v20 + 32));
      return (unsigned int)WebSocketResponseHeaders;
    }
    v26 = (char *)operator new(0xC0u);
    v27 = v26;
    if ( v26 )
    {
      memset_0(v26 + 52, 0, 0x8Cu);
      *(_OWORD *)v27 = 0;
      *((_OWORD *)v27 + 1) = 0;
      *((_DWORD *)v27 + 8) = 0;
      *(_OWORD *)(v27 + 36) = 0;
    }
    else
    {
      v27 = 0;
    }
    *(_QWORD *)(v20 + 176) = v27;
    if ( !v27 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 2);
      v24 = 52;
      v25 = "SEND_DATA_OVERLAPPED";
      goto LABEL_17;
    }
    v28 = *a3;
    v29 = *(_QWORD *)(v20 + 160);
    *(struct _GUID *)(v20 + 128) = *a3;
    *(GUID *)(v29 + 36) = v28;
    *(GUID *)(*(_QWORD *)(v20 + 176) + 36LL) = v28;
    WebSocketResponseHeaders = StringCchCopyW((unsigned __int16 *)(v20 + 48), 0x28u, a2);
    if ( WebSocketResponseHeaders < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < (unsigned __int8)(v30 - 38) )
      {
        goto LABEL_89;
      }
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, (unsigned int)(v30 - 38));
      v32 = 53;
      goto LABEL_32;
    }
    WebSocketResponseHeaders = StringCchCopyW((unsigned __int16 *)(*(_QWORD *)(v20 + 160) + 56LL), v30, a2);
    if ( WebSocketResponseHeaders < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 2);
      v32 = 54;
      goto LABEL_32;
    }
    WebSocketResponseHeaders = StringCchCopyW((unsigned __int16 *)(*(_QWORD *)(v20 + 176) + 56LL), v34, a2);
    if ( WebSocketResponseHeaders < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 2);
      v32 = 55;
LABEL_32:
      v33 = "StringCchCopy failed";
LABEL_33:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v32,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        v31,
        (__int64)v33,
        WebSocketResponseHeaders);
      goto LABEL_89;
    }
    pLocalAddress = a4->Address.pLocalAddress;
    v36 = 16;
    v37 = 16;
    if ( pLocalAddress->sa_family == 23 )
      v37 = 28;
    if ( a4->Address.pRemoteAddress->sa_family == 23 )
      v36 = 28;
    if ( memcpy_s((void *const)(v20 + 272), 0x80u, pLocalAddress, v37) )
    {
      WebSocketResponseHeaders = -2147418113;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v39 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v38);
      v40 = 56;
      goto LABEL_53;
    }
    if ( memcpy_s((void *const)(v20 + 400), 0x80u, a4->Address.pRemoteAddress, v36) )
    {
      WebSocketResponseHeaders = -2147418113;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_89;
      }
      v39 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v41);
      v40 = 57;
LABEL_53:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v40,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        v39,
        (__int64)"memcpy failed",
        255);
      goto LABEL_89;
    }
    if ( (unsigned int)WebSocketServer::IsWebSocketRequest(v42, a4) )
    {
      v70 = 0;
      WebSocketResponseHeaders = WebSocketCreateServerHandle(0, 0, &v70);
      if ( WebSocketResponseHeaders < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_89;
        }
        v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v43);
        v32 = 58;
        v33 = "WebSocketCreateServerHandle failed";
        goto LABEL_33;
      }
      v44 = operator new(0x38u);
      if ( v44 )
      {
        v46 = v70;
        v44[6] = -607474739;
        *((_QWORD *)v44 + 2) = "WEB_SOCKET_SHARED_HANDLE";
        v44[7] = 1;
        *(_QWORD *)v44 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
        *((_QWORD *)v44 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
        *(_QWORD *)v44 = &CTSAsyncResultImpl::`vftable'{for `INonDelegatingUnknown'};
        v45 = &WebSocketServer::WEB_SOCKET_SHARED_HANDLE::`vftable'{for `CTSObject'};
        *((_QWORD *)v44 + 1) = &WebSocketServer::WEB_SOCKET_SHARED_HANDLE::`vftable'{for `CTSObject'};
        v44[10] = 0;
        *((_QWORD *)v44 + 4) = v44;
        *((_QWORD *)v44 + 6) = v46;
      }
      *(_QWORD *)(v20 + 216) = v44;
      if ( !v44 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v47 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v45);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
            v47,
            (__int64)"WEB_SOCKET_SHARED_HANDLE");
        }
        goto LABEL_18;
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 + 4) + 8LL))(*((_QWORD *)v44 + 4));
      v48 = *(_QWORD *)(v20 + 216);
      v49 = a6;
      *(_DWORD *)(v20 + 224) = 1;
      *(_QWORD *)(v20 + 200) = a4->RequestId;
      *(_QWORD *)(v20 + 184) = a4->ConnectionId;
      *(_QWORD *)(v20 + 192) = a4->RawConnectionId;
      v50 = a7;
      *(_DWORD *)(v20 + 208) = 1;
      WebSocketResponseHeaders = WebSocketServer::GetWebSocketResponseHeaders(
                                   (WebSocketServer *)1,
                                   a4,
                                   *(struct WEB_SOCKET_HANDLE__ **)(v48 + 48),
                                   v49,
                                   v50);
      if ( WebSocketResponseHeaders < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_89;
        }
        v31 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v51);
        v32 = 60;
        v33 = "GetWebSocketResponseHeaders failed";
        goto LABEL_33;
      }
    }
    *(_QWORD *)(v20 + 248) = GetTickCount64();
    AcquireSRWLockExclusive(this + 8);
    v52 = (__int64 *)(v20 + 232);
    Ptr = this[24].Ptr;
    *(_QWORD *)(v20 + 240) = Ptr;
    *(_QWORD *)(v20 + 232) = this + 23;
    *Ptr = v20 + 232;
    ++LODWORD(this[22].Ptr);
    this[24].Ptr = (PVOID)(v20 + 232);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 8LL))(*(_QWORD *)(v20 + 32));
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MSRC95012>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MSRC95012>::GetImpl'::`2'::impl);
    ConnectionId = a4->ConnectionId;
    v56 = (unsigned __int16 *)(v20 + 48);
    ActivityId = *(GUID *)(v20 + 128);
    if ( IsEnabled )
    {
      WebSocketResponseHeaders = WebSocketServer::SubscribeForDisconnect(
                                   (WebSocketServer *)this,
                                   v56,
                                   &ActivityId,
                                   ConnectionId);
      if ( WebSocketResponseHeaders < 0 )
      {
        --LODWORD(this[22].Ptr);
        v57 = *(__int64 **)(v20 + 240);
        v58 = *v52;
        *v57 = *v52;
        *(_QWORD *)(v58 + 8) = v57;
        ReleaseSRWLockExclusive(this + 8);
        if ( (unsigned int)CallbackContext > 2 )
        {
          v71 = a2;
          *(_QWORD *)&ActivityId.Data1 = "ProcessWebSocketRequest";
          LODWORD(a5) = 3120;
          v68 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketserver\\websocketserver.cpp";
          v67 = "SubscribeForDisconnect failed. Cleaning up the connection structures.";
          LODWORD(v70) = WebSocketResponseHeaders;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v59,
            (unsigned int)&byte_180292D4F,
            v60,
            v61,
            (__int64)&v67,
            (__int64)&v70,
            (__int64)&v68,
            (__int64)&a5,
            (__int64)&ActivityId,
            (__int64)&v71);
        }
        *(_QWORD *)(v20 + 200) = 0;
        goto LABEL_82;
      }
    }
    else
    {
      WebSocketServer::SubscribeForDisconnect((WebSocketServer *)this, v56, &ActivityId, ConnectionId);
    }
    ReleaseSRWLockExclusive(this + 8);
    if ( !*(_DWORD *)(v20 + 224) )
    {
      WebSocketResponseHeaders = -2147467259;
      goto LABEL_89;
    }
    *(_DWORD *)a5 = 3;
    if ( (unsigned int)CallbackContext > 5 )
    {
      a5 = (enum WebSocketServer::OVERLAP_ID *)a2;
      v70 = "Created new connection object %s for WebSocket channel";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v62,
        (unsigned int)byte_180292DA5,
        v63,
        v64,
        (__int64)&v70,
        (__int64)&a5);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v20 + 32) + 16LL))(*(_QWORD *)(v20 + 32));
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v65 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 2);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_b1a8cc76119c395613772ef098e23945_Traceguids,
        v65,
        (__int64)"HTTP_TRANSPORT_CONNECTION_INFO");
    }
    return (unsigned int)-2147024882;
  }
}

```

## disassembly

```asm
0x180135984  mov     [rsp-38h+arg_8], rbx
0x180135989  push    rbp
0x18013598a  push    rsi
0x18013598b  push    rdi
0x18013598c  push    r12
0x18013598e  push    r13
0x180135990  push    r14
0x180135992  push    r15
0x180135994  mov     rbp, rsp
0x180135997  sub     rsp, 70h
0x18013599b  movups  xmm0, xmmword ptr [r8]
0x18013599f  mov     r14, rdx
0x1801359a2  mov     r13, rcx
0x1801359a5  lea     rdx, [rbp+ActivityId]; ActivityId
0x1801359a9  mov     ecx, 2; ControlCode
0x1801359ae  movdqu  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1801359b3  mov     r15, r9
0x1801359b6  mov     rsi, r8
0x1801359b9  call    cs:__imp_EventActivityIdControl
0x1801359bf  mov     rdi, [rbp+arg_20]
0x1801359c3  lea     r12, [r13+40h]
0x1801359c7  mov     rcx, r12; SRWLock
0x1801359ca  mov     dword ptr [rdi], 7
0x1801359d0  call    cs:__imp_AcquireSRWLockShared
0x1801359d6  lea     rcx, [r13+0B0h]
0x1801359dd  xor     edx, edx
0x1801359df  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x1801359e4  mov     rbx, rax
0x1801359e7  test    rax, rax
0x1801359ea  jz      short loc_180135A13
0x1801359ec  lea     rcx, [rbx+30h]; String1
0x1801359f0  mov     rdx, r14; String2
0x1801359f3  call    _wcsicmp
0x1801359f8  test    eax, eax
0x1801359fa  jz      short loc_180135A13
0x1801359fc  mov     rdx, rbx
0x1801359ff  lea     rcx, [r13+0B0h]
0x180135a06  call    ?GetNextOfEx@?$CTEntryList@UHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@$0OI@@@QEAAPEAUHTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@PEAU23@@Z; CTEntryList<WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO,232>::GetNextOfEx(WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO *)
0x180135a0b  mov     rbx, rax
0x180135a0e  test    rax, rax
0x180135a11  jnz     short loc_1801359EC
0x180135a13  mov     rcx, r12; SRWLock
0x180135a16  call    cs:__imp_ReleaseSRWLockShared
0x180135a1c  test    rbx, rbx
0x180135a1f  jz      loc_180135AB5
0x180135a25  mov     eax, cs:CallbackContext
0x180135a2b  mov     edx, 2
0x180135a30  mov     [rdi], edx
0x180135a32  mov     edi, 80004005h
0x180135a37  cmp     eax, edx
0x180135a39  jbe     loc_180136246
0x180135a3f  lea     rax, aProcesswebsock_0; "ProcessWebSocketRequest"
0x180135a46  mov     [rbp+arg_10], r14
0x180135a4a  mov     [rbp+var_20], rax
0x180135a4e  lea     rdx, qword_180292DD8
0x180135a55  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180135a5c  mov     dword ptr [rbp+arg_20], 0BAAh
0x180135a63  mov     [rbp+var_18], rax
0x180135a67  lea     rax, aDuplicateOutCh; "Duplicate OUT channel request"
0x180135a6e  mov     qword ptr [rbp+ActivityId.Data1], rax
0x180135a72  lea     rax, [rbp+arg_10]
0x180135a76  mov     [rsp+70h+var_28], rax
0x180135a7b  lea     rax, [rbp+var_20]
0x180135a7f  mov     [rsp+70h+var_30], rax
0x180135a84  lea     rax, [rbp+arg_20]
0x180135a88  mov     [rsp+70h+var_38], rax
0x180135a8d  lea     rax, [rbp+var_18]
0x180135a91  mov     [rsp+70h+var_40], rax
0x180135a96  lea     rax, [rbp+arg_0]
0x180135a9a  mov     [rsp+70h+var_48], rax
0x180135a9f  lea     rax, [rbp+ActivityId]
0x180135aa3  mov     [rsp+70h+var_50], rax
0x180135aa8  mov     dword ptr [rbp+arg_0], edi
0x180135aab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180135ab0  jmp     loc_180136246
0x180135ab5  mov     ecx, 210h; Size
0x180135aba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180135abf  test    rax, rax
0x180135ac2  jz      loc_1801361ED
0x180135ac8  mov     rcx, rax; this
0x180135acb  call    ??0HTTP_TRANSPORT_CONNECTION_INFO@WebSocketServer@@QEAA@XZ; WebSocketServer::HTTP_TRANSPORT_CONNECTION_INFO::HTTP_TRANSPORT_CONNECTION_INFO(void)
0x180135ad0  mov     rbx, rax
0x180135ad3  test    rax, rax
0x180135ad6  jz      loc_1801361ED
0x180135adc  mov     rcx, [rax+20h]
0x180135ae0  mov     rdx, [rcx]
0x180135ae3  mov     rax, [rdx+8]
0x180135ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135aec  mov     ecx, 0C0h; Size
0x180135af1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180135af6  mov     rdi, rax
0x180135af9  test    rax, rax
0x180135afc  jz      short loc_180135B26
0x180135afe  lea     rcx, [rax+34h]; void *
0x180135b02  xor     edx, edx; Val
0x180135b04  mov     r8d, 8Ch; Size
0x180135b0a  call    memset_0
0x180135b0f  xorps   xmm0, xmm0
0x180135b12  movups  xmmword ptr [rdi], xmm0
0x180135b15  movups  xmmword ptr [rdi+10h], xmm0
0x180135b19  mov     dword ptr [rdi+20h], 0
0x180135b20  movups  xmmword ptr [rdi+24h], xmm0
0x180135b24  jmp     short loc_180135B28
0x180135b26  xor     edi, edi
0x180135b28  mov     [rbx+0A0h], rdi
0x180135b2f  test    rdi, rdi
0x180135b32  jnz     short loc_180135B8E
0x180135b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180135b3b  lea     rax, WPP_GLOBAL_Control
0x180135b42  cmp     rcx, rax
0x180135b45  jz      short loc_180135B84
0x180135b47  test    byte ptr [rcx+1Ch], 8
0x180135b4b  jz      short loc_180135B84
0x180135b4d  lea     edx, [rdi+2]
0x180135b50  cmp     [rcx+19h], dl
0x180135b53  jb      short loc_180135B84
0x180135b55  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135b5b  lea     edx, [rdi+33h]
0x180135b5e  lea     rcx, aRecvDataOverla; "RECV_DATA_OVERLAPPED"
0x180135b65  mov     [rsp+70h+var_50], rcx
0x180135b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180135b71  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180135b78  mov     r9d, eax
0x180135b7b  mov     rcx, [rcx+10h]
0x180135b7f  call    WPP_SF_Ds
0x180135b84  mov     edi, 8007000Eh
0x180135b89  jmp     loc_1801361DD
0x180135b8e  mov     ecx, 0C0h; Size
0x180135b93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180135b98  mov     rdi, rax
0x180135b9b  test    rax, rax
0x180135b9e  jz      short loc_180135BC8
0x180135ba0  lea     rcx, [rax+34h]; void *
0x180135ba4  xor     edx, edx; Val
0x180135ba6  mov     r8d, 8Ch; Size
0x180135bac  call    memset_0
0x180135bb1  xorps   xmm0, xmm0
0x180135bb4  movups  xmmword ptr [rdi], xmm0
0x180135bb7  movups  xmmword ptr [rdi+10h], xmm0
0x180135bbb  mov     dword ptr [rdi+20h], 0
0x180135bc2  movups  xmmword ptr [rdi+24h], xmm0
0x180135bc6  jmp     short loc_180135BCA
0x180135bc8  xor     edi, edi
0x180135bca  mov     [rbx+0B0h], rdi
0x180135bd1  test    rdi, rdi
0x180135bd4  jnz     short loc_180135C0C
0x180135bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180135bdd  lea     rax, WPP_GLOBAL_Control
0x180135be4  cmp     rcx, rax
0x180135be7  jz      short loc_180135B84
0x180135be9  test    byte ptr [rcx+1Ch], 8
0x180135bed  jz      short loc_180135B84
0x180135bef  lea     edx, [rdi+2]
0x180135bf2  cmp     [rcx+19h], dl
0x180135bf5  jb      short loc_180135B84
0x180135bf7  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135bfd  lea     edx, [rdi+34h]
0x180135c00  lea     rcx, aSendDataOverla; "SEND_DATA_OVERLAPPED"
0x180135c07  jmp     loc_180135B65
0x180135c0c  movups  xmm0, xmmword ptr [rsi]
0x180135c0f  mov     rax, [rbx+0A0h]
0x180135c16  lea     rcx, [rbx+30h]; unsigned __int16 *
0x180135c1a  mov     r11d, 28h ; '('
0x180135c20  mov     r8, r14; unsigned __int16 *
0x180135c23  movdqu  xmmword ptr [rbx+80h], xmm0
0x180135c2b  mov     edx, r11d; unsigned __int64
0x180135c2e  movdqu  xmmword ptr [rax+24h], xmm0
0x180135c33  mov     rax, [rbx+0B0h]
0x180135c3a  movdqu  xmmword ptr [rax+24h], xmm0
0x180135c3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180135c44  mov     edi, eax
0x180135c46  test    eax, eax
0x180135c48  jns     short loc_180135CB2
0x180135c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180135c51  lea     rax, WPP_GLOBAL_Control
0x180135c58  cmp     rcx, rax
0x180135c5b  jz      loc_1801361DD
0x180135c61  test    byte ptr [rcx+1Ch], 8
0x180135c65  jz      loc_1801361DD
0x180135c6b  lea     edx, [r11-26h]
0x180135c6f  cmp     [rcx+19h], dl
0x180135c72  jb      loc_1801361DD
0x180135c78  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135c7e  mov     edx, 35h ; '5'
0x180135c83  lea     rcx, aStringcchcopyF_0; "StringCchCopy failed"
0x180135c8a  mov     dword ptr [rsp+70h+var_48], edi
0x180135c8e  mov     [rsp+70h+var_50], rcx
0x180135c93  lea     r8, WPP_b1a8cc76119c395613772ef098e23945_Traceguids
0x180135c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180135ca1  mov     r9d, eax
0x180135ca4  mov     rcx, [rcx+10h]
0x180135ca8  call    WPP_SF_DsD
0x180135cad  jmp     loc_1801361DD
0x180135cb2  mov     rcx, [rbx+0A0h]
0x180135cb9  mov     r8, r14; unsigned __int16 *
0x180135cbc  add     rcx, 38h ; '8'; unsigned __int16 *
0x180135cc0  mov     rdx, r11; unsigned __int64
0x180135cc3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180135cc8  mov     edi, eax
0x180135cca  test    eax, eax
0x180135ccc  jns     short loc_180135D0D
0x180135cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180135cd5  lea     rax, WPP_GLOBAL_Control
0x180135cdc  cmp     rcx, rax
0x180135cdf  jz      loc_1801361DD
0x180135ce5  test    byte ptr [rcx+1Ch], 8
0x180135ce9  jz      loc_1801361DD
0x180135cef  mov     edx, 2
0x180135cf4  cmp     [rcx+19h], dl
0x180135cf7  jb      loc_1801361DD
0x180135cfd  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135d03  mov     edx, 36h ; '6'
0x180135d08  jmp     loc_180135C83
0x180135d0d  mov     rcx, [rbx+0B0h]
0x180135d14  mov     r8, r14; unsigned __int16 *
0x180135d17  add     rcx, 38h ; '8'; unsigned __int16 *
0x180135d1b  mov     rdx, r11; unsigned __int64
0x180135d1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180135d23  mov     edi, eax
0x180135d25  test    eax, eax
0x180135d27  jns     short loc_180135D68
0x180135d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180135d30  lea     rax, WPP_GLOBAL_Control
0x180135d37  cmp     rcx, rax
0x180135d3a  jz      loc_1801361DD
0x180135d40  test    byte ptr [rcx+1Ch], 8
0x180135d44  jz      loc_1801361DD
0x180135d4a  mov     edx, 2
0x180135d4f  cmp     [rcx+19h], dl
0x180135d52  jb      loc_1801361DD
0x180135d58  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135d5e  mov     edx, 37h ; '7'
0x180135d63  jmp     loc_180135C83
0x180135d68  mov     r8, [r15+70h]; Source
0x180135d6c  mov     ecx, 1Ch
0x180135d71  lea     esi, [rcx-1Ah]
0x180135d74  lea     edi, [rcx-0Ch]
0x180135d77  mov     r9d, edi
0x180135d7a  cmp     [r8], si
0x180135d7e  jz      short loc_180135D89
0x180135d80  cmp     word ptr [r8], 17h
0x180135d85  cmovz   r9d, ecx; SourceSize
0x180135d89  mov     rax, [r15+68h]
0x180135d8d  cmp     [rax], si
0x180135d90  jz      short loc_180135D9A
0x180135d92  cmp     word ptr [rax], 17h
0x180135d96  cmovz   rdi, rcx
0x180135d9a  lea     rcx, [rbx+110h]; Destination
0x180135da1  mov     edx, 80h; DestinationSize
0x180135da6  call    memcpy_s
0x180135dab  test    eax, eax
0x180135dad  jz      short loc_180135DFE
0x180135daf  mov     edi, 8000FFFFh
0x180135db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180135dbb  lea     rax, WPP_GLOBAL_Control
0x180135dc2  cmp     rcx, rax
0x180135dc5  jz      loc_1801361DD
0x180135dcb  test    byte ptr [rcx+1Ch], 8
0x180135dcf  jz      loc_1801361DD
0x180135dd5  cmp     [rcx+19h], sil
0x180135dd9  jb      loc_1801361DD
0x180135ddf  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135de5  mov     edx, 38h ; '8'
0x180135dea  mov     dword ptr [rsp+70h+var_48], 8000FFFFh
0x180135df2  lea     rcx, aMemcpyFailed; "memcpy failed"
0x180135df9  jmp     loc_180135C8E
0x180135dfe  mov     r8, [r15+68h]; Source
0x180135e02  lea     rcx, [rbx+190h]; Destination
0x180135e09  mov     r9, rdi; SourceSize
0x180135e0c  mov     edx, 80h; DestinationSize
0x180135e11  call    memcpy_s
0x180135e16  test    eax, eax
0x180135e18  jz      short loc_180135E57
0x180135e1a  mov     edi, 8000FFFFh
0x180135e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180135e26  lea     rax, WPP_GLOBAL_Control
0x180135e2d  cmp     rcx, rax
0x180135e30  jz      loc_1801361DD
0x180135e36  test    byte ptr [rcx+1Ch], 8
0x180135e3a  jz      loc_1801361DD
0x180135e40  cmp     [rcx+19h], sil
0x180135e44  jb      loc_1801361DD
0x180135e4a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180135e50  mov     edx, 39h ; '9'
0x180135e55  jmp     short loc_180135DEA
0x180135e57  mov     rdx, r15; struct _HTTP_REQUEST_V2 *
0x180135e5a  call    ?IsWebSocketRequest@WebSocketServer@@AEAAHPEAU_HTTP_REQUEST_V2@@@Z; WebSocketServer::IsWebSocketRequest(_HTTP_REQUEST_V2 *)
0x180135e5f  test    eax, eax
0x180135e61  jz      loc_180136023
0x180135e67  lea     r8, [rbp+arg_0]
0x180135e6b  mov     [rbp+arg_0], 0
0x180135e73  xor     edx, edx
0x180135e75  xor     ecx, ecx
0x180135e77  call    cs:__imp_WebSocketCreateServerHandle
0x180135e7d  mov     edi, eax
0x180135e7f  test    eax, eax
0x180135e81  jns     short loc_180135EC5
0x180135e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180135e8a  lea     rax, WPP_GLOBAL_Control
0x180135e91  cmp     rcx, rax
  ... truncated ...
```
