# SideTransportStream::ConnectionRequest(IRdpSideTransportConnectorCallback *,uchar *,ulong,ulong,IUnknown *,uint *)

- ea: `0x180151840`
- end: `0x1801523f0`
- name: `?ConnectionRequest@SideTransportStream@@UEAAJPEAUIRdpSideTransportConnectorCallback@@PEAEKKPEAUIUnknown@@PEAI@Z`
- size: `2992`
- prototype: `int(SideTransportStream *__hidden this, struct IRdpSideTransportConnectorCallback *, unsigned __int8 *, unsigned int, unsigned int, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x18000146c`
- `0x18000202c`
- `0x180002d3c`
- `0x180006250`
- `0x18004d52c`
- `0x18007e9e0`
- `0x1800a3474`
- `0x1800d4788`
- `0x180150ef0`
- `0x180151840`
- `0x1801523f8`
- `0x18015262c`
- `0x180153370`
- `0x1801536d0`
- `0x180156838`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18015202e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18015202e`

## string_xrefs

- `0x180151b82`: `StartDirectlyWithSideTransport`
- `0x1801519ed`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180151a86`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180151d30`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180151d94`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015208a`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180152323`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180151a6b`: `Invalid security cookie size`
- `0x180151c86`: `SideTransportCreationParams`
- `0x180151d15`: `Invalid spSideTransportCreationParams`
- `0x180151ca7`: `Failed to get CONN_PROPERTY_SIDE_TRANSPORT_CREATION_PARAMS property.`
- `0x180151e5b`: `ConvertToUTF8 for rendezvousUri failed`
- `0x180151d79`: `Invalid pSideTransportCreationParams`
- `0x180151eda`: `ConvertToUTF8 for aadIdAuthToken failed`
- `0x18015206f`: `Nano side transport pointer is null`
- `0x180152117`: `spNanoSideTransport->InitializeInstance failed`
- `0x1801520be`: `SideTransportStream: Connecting`
- `0x180152308`: `spNanoSideTransport->Connect failed`
- `0x18015223c`: `SideTransportStream: directUDP/STUN/TURN are disabled`

## pseudocode

```c
__int64 __fastcall SideTransportStream::ConnectionRequest(
        SideTransportStream *this,
        struct IRdpSideTransportConnectorCallback *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int a5,
        struct IUnknown *a6,
        unsigned int *a7)
{
  unsigned int v11; // eax
  DWORD v12; // edx
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r9
  struct IRDPENCPlatformContext *v16; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int HashFromMTCookie_LocalImpl; // esi
  char *v20; // rdx
  const char *v21; // rax
  const char *v22; // rax
  __int64 v23; // rdi
  __int128 v24; // xmm0
  __int64 v25; // rdi
  __int64 (__fastcall ***v26)(_QWORD, GUID *, char *); // rbx
  __int64 (__fastcall **v27)(_QWORD, GUID *, char *); // rax
  __int64 v28; // rcx
  __int64 (__fastcall *v29)(_QWORD, GUID *, char *); // rsi
  int v30; // eax
  int v31; // r8d
  int v32; // r9d
  void (__fastcall ***v33)(_QWORD, GUID *, const char **); // rcx
  struct IRDPENCPlatformContext *v34; // rbx
  __int64 v35; // rax
  __int64 (__fastcall *v36)(struct IRDPENCPlatformContext *, const wchar_t *, GUID *, void (__fastcall ****)(_QWORD, GUID *, const char **)); // rdi
  const char *v37; // rbx
  _QWORD *v38; // rax
  _QWORD *v39; // rdi
  __int64 v40; // rax
  const WCHAR *v41; // rcx
  int v42; // eax
  int v43; // r8d
  int v44; // r9d
  const WCHAR *v45; // rcx
  int v46; // eax
  int v47; // r8d
  int v48; // r9d
  const WCHAR *v49; // rcx
  int v50; // eax
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rax
  unsigned int v54; // r12d
  int v55; // ecx
  __int64 v56; // rbx
  GUID v57; // xmm0
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 (__fastcall *v63)(__int64, GUID *, _OWORD *, int *, _QWORD, int *, int *, int *); // rsi
  bool v64; // di
  GUID *CurrentActivityId; // rax
  int *v66; // r8
  int *v67; // rdx
  int v69; // [rsp+50h] [rbp-B0h] BYREF
  const char *p_ActivityId; // [rsp+58h] [rbp-A8h] BYREF
  const char *v71; // [rsp+60h] [rbp-A0h] BYREF
  const char *v72; // [rsp+68h] [rbp-98h] BYREF
  const char *v73; // [rsp+70h] [rbp-90h] BYREF
  __int64 v74; // [rsp+78h] [rbp-88h] BYREF
  struct IRDPENCPlatformContext *v75; // [rsp+80h] [rbp-80h] BYREF
  int v76; // [rsp+88h] [rbp-78h] BYREF
  void (__fastcall ***v77)(_QWORD, GUID *, const char **); // [rsp+90h] [rbp-70h] BYREF
  __int64 v78; // [rsp+98h] [rbp-68h] BYREF
  int v79; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v80; // [rsp+A8h] [rbp-58h]
  int v81; // [rsp+B0h] [rbp-50h]
  __int64 v82; // [rsp+B8h] [rbp-48h]
  int v83; // [rsp+C0h] [rbp-40h]
  __int64 v84; // [rsp+C8h] [rbp-38h]
  int v85; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-28h]
  __int16 v87; // [rsp+E0h] [rbp-20h]
  int v88; // [rsp+E4h] [rbp-1Ch]
  __int64 v89; // [rsp+E8h] [rbp-18h]
  const char *v90; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v91; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v92; // [rsp+100h] [rbp+0h]
  _BYTE v93[16]; // [rsp+108h] [rbp+8h] BYREF
  int v94; // [rsp+118h] [rbp+18h] BYREF
  __int64 v95; // [rsp+120h] [rbp+20h]
  __int128 v96; // [rsp+128h] [rbp+28h]
  __int64 v97; // [rsp+138h] [rbp+38h]
  int v98; // [rsp+140h] [rbp+40h] BYREF
  __int64 v99; // [rsp+148h] [rbp+48h]
  __int64 v100; // [rsp+150h] [rbp+50h]
  _QWORD v101[2]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v102[16]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v103[2]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v104[16]; // [rsp+188h] [rbp+88h] BYREF
  GUID v105; // [rsp+198h] [rbp+98h] BYREF
  GUID ActivityId; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v107; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v108; // [rsp+1C8h] [rbp+C8h]
  _OWORD v109[2]; // [rsp+1CCh] [rbp+CCh] BYREF

  v91 = v93;
  v75 = 0;
  v78 = 0;
  v92 = v93;
  v90 = 0;
  v77 = 0;
  v103[0] = v104;
  v103[1] = v104;
  v76 = 0;
  v101[0] = v102;
  v108 = 0;
  v101[1] = v102;
  v11 = SideTransportStream::m_requestId + 1;
  v93[0] = 0;
  v104[0] = 0;
  v102[0] = 0;
  v85 = 1;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v79 = 1;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v98 = 3;
  v99 = 0;
  v100 = 0;
  v94 = 1;
  v95 = 0;
  v97 = 0;
  ++SideTransportStream::m_requestId;
  memset(v109, 0, sizeof(v109));
  v107 = 0;
  v96 = 0;
  if ( a7 )
    *a7 = v11;
  *((struct _GUID *)this + 8) = *RdpActivityId::GetCurrentActivityId(&ActivityId);
  if ( a6 )
  {
    v16 = v75;
    lpVtbl = a6->lpVtbl;
    v75 = 0;
    QueryInterface = lpVtbl->QueryInterface;
    if ( v16 )
      (*(void (__fastcall **)(struct IRDPENCPlatformContext *))(*(_QWORD *)v16 + 16LL))(v16);
    HashFromMTCookie_LocalImpl = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IRDPENCPlatformContext **))QueryInterface)(
                                   a6,
                                   &IID_IRDPENCPlatformContext,
                                   &v75);
    if ( HashFromMTCookie_LocalImpl < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v69 = 115;
        v74 = (__int64)"pPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) failed";
        v73 = "ConnectionRequest";
        v72 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        LODWORD(v71) = HashFromMTCookie_LocalImpl;
        p_ActivityId = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_18029B57A,
          v14,
          v15,
          (__int64)&p_ActivityId,
          (__int64)&v71,
          (__int64)&v72,
          (__int64)&v69,
          (__int64)&v73,
          (__int64)&v74);
      }
      goto LABEL_118;
    }
  }
  if ( a4 != 16 )
  {
    HashFromMTCookie_LocalImpl = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    LODWORD(v71) = 118;
    p_ActivityId = "Invalid security cookie size";
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v20 = byte_18029C5F5;
    v21 = "Error condition failed";
    goto LABEL_116;
  }
  HashFromMTCookie_LocalImpl = CreateHashFromMTCookie_LocalImpl(a3, v12, (BYTE *)&v107, v15);
  if ( HashFromMTCookie_LocalImpl < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    v22 = "Unexpected for child listener to be null";
    LODWORD(v71) = 121;
    v20 = (char *)qword_18029BBB8;
    goto LABEL_115;
  }
  v23 = *((_QWORD *)this + 6);
  v108 = SideTransportStream::m_requestId;
  v24 = *((_OWORD *)this + 8);
  *((_QWORD *)this + 6) = a2;
  v107 = v24;
  if ( a2 )
    (*(void (__fastcall **)(struct IRdpSideTransportConnectorCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v25 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = a6;
  if ( a6 )
    ((void (__fastcall *)(struct IUnknown *))a6->lpVtbl->AddRef)(a6);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  SideTransportStream::InitPerfMonSession((SideTransportStream *)((char *)this - 16), v75);
  if ( (*(int (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, int *))(*(_QWORD *)v75 + 32LL))(
         v75,
         L"StartDirectlyWithSideTransport",
         &v76) < 0
    || !v76 )
  {
    v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
    if ( v26 )
    {
      v27 = *v26;
      v28 = *((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = 0;
      v29 = *v27;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v30 = v29(v26, &IID_IRdpIceToStackCallback, (char *)this + 56);
      if ( v30 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v71) = v30;
        p_ActivityId = "ConnectionRequest";
        v72 = "Failed to get IRdpIceToStackCallback interface";
        v73 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_18029C219,
          v31,
          v32,
          (__int64)&v73,
          (__int64)&v72,
          (__int64)&v71,
          (__int64)&p_ActivityId);
      }
    }
  }
  v33 = v77;
  v34 = v75;
  v35 = *(_QWORD *)v75;
  v77 = 0;
  v36 = *(__int64 (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, GUID *, void (__fastcall ****)(_QWORD, GUID *, const char **)))(v35 + 48);
  if ( v33 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, const char **)))(*v33)[2])(v33);
  HashFromMTCookie_LocalImpl = v36(v34, L"SideTransportCreationParams", &IID_IUnknown, &v77);
  if ( HashFromMTCookie_LocalImpl < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    v22 = "Failed to get CONN_PROPERTY_SIDE_TRANSPORT_CREATION_PARAMS property.";
    LODWORD(v71) = 153;
    v20 = byte_18029B453;
    goto LABEL_115;
  }
  v71 = 0;
  (**v77)(v77, &GUID_3942b544_2536_4680_919b_362c63b75246, &v71);
  v37 = v71;
  v90 = v71;
  v71 = 0;
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v71);
  if ( !v37 )
  {
    v13 = -2147418113;
    HashFromMTCookie_LocalImpl = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    LODWORD(v71) = 156;
    p_ActivityId = "Invalid spSideTransportCreationParams";
    v20 = (char *)&dword_18029CC4C;
    v69 = -2147418113;
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error condition failed";
LABEL_117:
    v74 = (__int64)v21;
    v72 = "ConnectionRequest";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v13,
      (_DWORD)v20,
      v14,
      v15,
      (__int64)&v74,
      (__int64)&v69,
      (__int64)&v73,
      (__int64)&v71,
      (__int64)&v72,
      (__int64)&p_ActivityId);
    goto LABEL_118;
  }
  v38 = (_QWORD *)(*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v37 + 24LL))(v37);
  v39 = v38;
  if ( !v38 )
  {
    v13 = -2147418113;
    HashFromMTCookie_LocalImpl = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    LODWORD(v71) = 159;
    p_ActivityId = "Invalid pSideTransportCreationParams";
    v20 = byte_18029CEB9;
    v69 = -2147418113;
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error condition failed";
    goto LABEL_117;
  }
  if ( *v38 )
  {
    v40 = v82;
    if ( *((_DWORD *)v39 + 2) )
      v40 = *v39;
    v82 = v40;
  }
  if ( (*((_BYTE *)v39 + 12) & 1) != 0 )
    v80 = (unsigned int)v80 | 1LL;
  if ( (*((_BYTE *)v39 + 12) & 2) != 0 )
    v80 = (unsigned int)v80 | 2LL;
  if ( (*((_BYTE *)v39 + 12) & 0x10) != 0 )
    v80 = (unsigned int)v80 | 0x10LL;
  if ( (*((_BYTE *)v39 + 12) & 0x20) != 0 )
    v80 = (unsigned int)v80 | 0x20LL;
  if ( (*((_BYTE *)v39 + 12) & 0x40) != 0 )
    v80 = (unsigned int)v80 | 0x40LL;
  if ( (*((_DWORD *)v39 + 3) & 0x100) != 0 )
    v80 = (unsigned int)v80 | 0x100LL;
  v41 = (const WCHAR *)v39[3];
  if ( v41 != (const WCHAR *)v39[4] )
  {
    v42 = ConvertToUTF8(v41);
    if ( v42 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v71) = v42;
      p_ActivityId = "ConnectionRequest";
      v72 = "ConvertToUTF8 for rendezvousUri failed";
      v73 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)qword_18029C9C8,
        v43,
        v44,
        (__int64)&v73,
        (__int64)&v72,
        (__int64)&v71,
        (__int64)&p_ActivityId);
    }
    *(_QWORD *)&v96 = v91;
  }
  v45 = (const WCHAR *)v39[7];
  if ( v45 != (const WCHAR *)v39[8] )
  {
    v46 = ConvertToUTF8(v45);
    if ( v46 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v71) = v46;
      p_ActivityId = "ConnectionRequest";
      v72 = "ConvertToUTF8 for aadIdAuthToken failed";
      v73 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&byte_18029C3D7,
        v47,
        v48,
        (__int64)&v73,
        (__int64)&v72,
        (__int64)&v71,
        (__int64)&p_ActivityId);
    }
    *((_QWORD *)&v96 + 1) = v103[0];
  }
  v49 = (const WCHAR *)v39[11];
  if ( v49 != (const WCHAR *)v39[12] )
  {
    v50 = ConvertToUTF8(v49);
    if ( v50 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v71) = v50;
      p_ActivityId = "ConnectionRequest";
      v72 = "ConvertToUTF8 for activityHint failed";
      v73 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)word_18029B9FA,
        v51,
        v52,
        (__int64)&v73,
        (__int64)&v72,
        (__int64)&v71,
        (__int64)&p_ActivityId);
    }
    v97 = v101[0];
  }
  v53 = v95;
  if ( *((_BYTE *)v39 + 120) )
  {
    v53 = v95 | 2;
    v95 |= 2uLL;
  }
  if ( *((_BYTE *)v39 + 121) )
    v95 = v53 | 4;
  v54 = *((_DWORD *)v39 + 32);
  v98 = v54;
  if ( v54 >= 3 )
    *((_BYTE *)this + 122) = 1;
  if ( *((_BYTE *)v39 + 132) )
    v99 |= 2uLL;
  HashFromMTCookie_LocalImpl = SideTransportStream::InitializeRdpNanoTransport((SideTransportStream *)((char *)this - 16));
  if ( HashFromMTCookie_LocalImpl < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    v22 = "InitializeRdpNanoTransport failed";
    LODWORD(v71) = 261;
    v20 = byte_18029C6F5;
    goto LABEL_115;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 14);
  p_ActivityId = (char *)this + 112;
  wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&v78, (char *)this + 96);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&p_ActivityId);
  v56 = v78;
  if ( !v78 )
  {
    v13 = -2147418113;
    HashFromMTCookie_LocalImpl = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    LODWORD(v71) = 268;
    p_ActivityId = "Nano side transport pointer is null";
    v20 = (char *)&word_18029CF8E;
    v69 = -2147418113;
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error condition failed";
    goto LABEL_117;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    p_ActivityId = (char *)this + 128;
    v72 = "SideTransportStream: Connecting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v55,
      (unsigned int)&dword_18029C534,
      v14,
      v15,
      (__int64)&v72,
      (__int64)&p_ActivityId);
  }
  HashFromMTCookie_LocalImpl = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v56 + 24LL))(
                                 v56,
                                 ((unsigned __int64)this + 24) & -(__int64)(this != (SideTransportStream *)16));
  if ( HashFromMTCookie_LocalImpl < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_118;
    v22 = "spNanoSideTransport->InitializeInstance failed";
    LODWORD(v71) = 273;
    v20 = byte_18029D05D;
    goto LABEL_115;
  }
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v14, v15) )
  {
    v57 = *RdpActivityId::GetCurrentActivityId(&v105);
    v74 = 0x1000000;
    p_ActivityId = (const char *)&ActivityId;
    v72 = "Udp";
    v73 = "Stack";
    v71 = "Checkpoint";
    ActivityId = v57;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v58,
      (unsigned int)byte_18029B51B,
      v59,
      v60,
      (__int64)&v71,
      (__int64)&v74,
      (__int64)&v73,
      (__int64)&v72,
      (__int64)&p_ActivityId);
  }
  v61 = v86;
  if ( *((_BYTE *)v39 + 140) )
  {
    v61 = v86 | 2;
    v86 |= 2uLL;
  }
  if ( *((_BYTE *)v39 + 141) )
  {
    v61 |= 0x10uLL;
    v86 = v61;
  }
  if ( *((_DWORD *)v39 + 37) > 1u )
    v86 = v61 | 4;
  v88 = *((_DWORD *)v39 + 36);
  if ( (v80 & 0x31) == 0x31 && (unsigned int)CallbackContext > 4 )
  {
    p_ActivityId = "SideTransportStream: directUDP/STUN/TURN are disabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v13,
      (unsigned int)&byte_18029CF6F,
      v14,
      v15,
      (__int64)&p_ActivityId);
  }
  if ( v39[19] )
  {
    v62 = v89;
    if ( *((_DWORD *)v39 + 40) )
      v62 = v39[19];
    v89 = v62;
  }
  v63 = *(__int64 (__fastcall **)(__int64, GUID *, _OWORD *, int *, _QWORD, int *, int *, int *))(*(_QWORD *)v56 + 40LL);
  v64 = v91 == v92;
  CurrentActivityId = RdpActivityId::GetCurrentActivityId(&v105);
  v66 = &v94;
  v67 = &v98;
  if ( v64 )
    v66 = 0;
  ActivityId = *CurrentActivityId;
  if ( v54 != 3 )
    v67 = 0;
  HashFromMTCookie_LocalImpl = v63(v56, &ActivityId, v109, &v85, 0, v67, &v79, v66);
  if ( HashFromMTCookie_LocalImpl < 0 && (unsigned int)CallbackContext > 2 )
  {
    v22 = "spNanoSideTransport->Connect failed";
    LODWORD(v71) = 324;
    v20 = (char *)word_18029BCCA;
LABEL_115:
    p_ActivityId = v22;
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error HResult failed";
LABEL_116:
    v69 = HashFromMTCookie_LocalImpl;
    goto LABEL_117;
  }
LABEL_118:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v101);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v103);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v91);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v77);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v90);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v78);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v75);
  return (unsigned int)HashFromMTCookie_LocalImpl;
}

```

## disassembly

```asm
0x180151840  mov     [rsp-8+arg_8], rbx
0x180151845  push    rbp
0x180151846  push    rsi
0x180151847  push    rdi
0x180151848  push    r12
0x18015184a  push    r13
0x18015184c  push    r14
0x18015184e  push    r15
0x180151850  lea     rbp, [rsp-100h]
0x180151858  sub     rsp, 200h
0x18015185f  mov     rax, cs:__security_cookie
0x180151866  xor     rax, rsp
0x180151869  mov     [rbp+130h+var_40], rax
0x180151870  mov     rbx, [rbp+130h+arg_28]
0x180151877  lea     rax, [rbp+130h+var_128]
0x18015187b  xor     esi, esi
0x18015187d  mov     [rbp+130h+var_138], rax
0x180151881  xorps   xmm0, xmm0
0x180151884  mov     [rbp+130h+var_1B0], rsi
0x180151888  lea     rax, [rbp+130h+var_128]
0x18015188c  mov     [rbp+130h+var_198], rsi
0x180151890  mov     [rbp+130h+var_130], rax
0x180151894  mov     r14, rdx
0x180151897  lea     edx, [rsi+1]
0x18015189a  mov     [rbp+130h+var_140], rsi
0x18015189e  lea     rax, [rbp+130h+var_A8]
0x1801518a5  mov     [rbp+130h+var_1A0], rsi
0x1801518a9  mov     [rbp+130h+var_B8], rax
0x1801518ad  mov     r15, rcx
0x1801518b0  mov     rcx, [rbp+130h+arg_30]
0x1801518b7  lea     rax, [rbp+130h+var_A8]
0x1801518be  mov     [rbp+130h+var_B0], rax
0x1801518c5  mov     r12d, r9d
0x1801518c8  lea     rax, [rbp+130h+var_C8]
0x1801518cc  mov     [rbp+130h+var_1A8], esi
0x1801518cf  mov     [rbp+130h+var_D8], rax
0x1801518d3  mov     r13, r8
0x1801518d6  lea     rax, [rbp+130h+var_C8]
0x1801518da  mov     [rbp+130h+var_68], esi
0x1801518e0  mov     [rbp+130h+var_D0], rax
0x1801518e4  mov     eax, cs:?m_requestId@SideTransportStream@@0IA; uint SideTransportStream::m_requestId
0x1801518ea  add     eax, edx
0x1801518ec  mov     [rbp+130h+var_128], sil
0x1801518f0  mov     [rbp+130h+var_A8], sil
0x1801518f7  mov     [rbp+130h+var_C8], sil
0x1801518fb  mov     [rbp+130h+var_160], edx
0x1801518fe  mov     [rbp+130h+var_158], rsi
0x180151902  mov     [rbp+130h+var_150], si
0x180151906  mov     [rbp+130h+var_14C], esi
0x180151909  mov     [rbp+130h+var_148], rsi
0x18015190d  mov     [rbp+130h+var_190], edx
0x180151910  mov     [rbp+130h+var_188], rsi
0x180151914  mov     [rbp+130h+var_180], esi
0x180151917  mov     [rbp+130h+var_178], rsi
0x18015191b  mov     [rbp+130h+var_170], esi
0x18015191e  mov     [rbp+130h+var_168], rsi
0x180151922  mov     [rbp+130h+var_F0], 3
0x180151929  mov     [rbp+130h+var_E8], rsi
0x18015192d  mov     [rbp+130h+var_E0], rsi
0x180151931  mov     [rbp+130h+var_118], edx
0x180151934  mov     [rbp+130h+var_110], rsi
0x180151938  mov     [rbp+130h+var_F8], rsi
0x18015193c  mov     cs:?m_requestId@SideTransportStream@@0IA, eax; uint SideTransportStream::m_requestId
0x180151942  movups  [rbp+130h+var_64], xmm0
0x180151949  movups  [rbp+130h+var_54], xmm0
0x180151950  movups  [rbp+130h+var_78], xmm0
0x180151957  movdqu  [rbp+130h+var_108], xmm0
0x18015195c  test    rcx, rcx
0x18015195f  jz      short loc_180151963
0x180151961  mov     [rcx], eax
0x180151963  lea     rcx, [rbp+130h+ActivityId]; ActivityId
0x18015196a  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x18015196f  movups  xmm0, xmmword ptr [rax]
0x180151972  movdqu  xmmword ptr [r15+80h], xmm0
0x18015197b  test    rbx, rbx
0x18015197e  jz      loc_180151A51
0x180151984  mov     rcx, [rbp+130h+var_1B0]
0x180151988  mov     rax, [rbx]
0x18015198b  mov     [rbp+130h+var_1B0], rsi
0x18015198f  mov     rdi, [rax]
0x180151992  test    rcx, rcx
0x180151995  jz      short loc_1801519A3
0x180151997  mov     rdx, [rcx]
0x18015199a  mov     rax, [rdx+10h]
0x18015199e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801519a3  lea     r8, [rbp+130h+var_1B0]
0x1801519a7  mov     rcx, rbx
0x1801519aa  lea     rdx, IID_IRDPENCPlatformContext
0x1801519b1  mov     rax, rdi
0x1801519b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801519b9  mov     esi, eax
0x1801519bb  test    eax, eax
0x1801519bd  jns     loc_180151A51
0x1801519c3  mov     ecx, cs:CallbackContext
0x1801519c9  cmp     ecx, 2
0x1801519cc  jbe     loc_180152385
0x1801519d2  lea     rax, aPplatformconte_1; "pPlatformContext->QueryInterface(IID_IR"...
0x1801519d9  mov     [rsp+230h+var_1E0], 73h ; 's'
0x1801519e1  mov     [rsp+230h+var_1B8], rax
0x1801519e6  lea     r14, aConnectionrequ; "ConnectionRequest"
0x1801519ed  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801519f4  mov     [rsp+230h+var_1C0], r14
0x1801519f9  mov     [rsp+230h+var_1C8], rax
0x1801519fe  lea     rdx, word_18029B57A
0x180151a05  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180151a0c  mov     dword ptr [rsp+230h+var_1D0], esi
0x180151a10  mov     [rsp+230h+var_1D8], rax
0x180151a15  lea     rax, [rsp+230h+var_1B8]
0x180151a1a  mov     [rsp+230h+var_1E8], rax
0x180151a1f  lea     rax, [rsp+230h+var_1C0]
0x180151a24  mov     [rsp+230h+var_1F0], rax
0x180151a29  lea     rax, [rsp+230h+var_1E0]
0x180151a2e  mov     [rsp+230h+var_1F8], rax
0x180151a33  lea     rax, [rsp+230h+var_1C8]
0x180151a38  mov     [rsp+230h+var_200], rax
0x180151a3d  lea     rax, [rsp+230h+var_1D0]
0x180151a42  mov     [rsp+230h+var_208], rax
0x180151a47  lea     rax, [rsp+230h+var_1D8]
0x180151a4c  jmp     loc_18015237B
0x180151a51  cmp     r12d, 10h
0x180151a55  jz      short loc_180151AA5
0x180151a57  mov     eax, cs:CallbackContext
0x180151a5d  mov     esi, 80070057h
0x180151a62  cmp     eax, 2
0x180151a65  jbe     loc_180152385
0x180151a6b  lea     rax, aInvalidSecurit; "Invalid security cookie size"
0x180151a72  mov     dword ptr [rsp+230h+var_1D0], 76h ; 'v'
0x180151a7a  mov     [rsp+230h+var_1D8], rax
0x180151a7f  lea     r14, aConnectionrequ; "ConnectionRequest"
0x180151a86  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180151a8d  mov     [rsp+230h+var_1C0], rax
0x180151a92  lea     rdx, byte_18029C5F5
0x180151a99  lea     rax, aErrorCondition; "Error condition failed"
0x180151aa0  jmp     loc_180152336
0x180151aa5  lea     r8, [rbp+130h+var_78]; struct SecurityCookieHash *
0x180151aac  mov     rcx, r13; pbData
0x180151aaf  call    ?CreateHashFromMTCookie_LocalImpl@@YAJPEAEIPEAUSecurityCookieHash@@@Z; CreateHashFromMTCookie_LocalImpl(uchar *,uint,SecurityCookieHash *)
0x180151ab4  xor     r12d, r12d
0x180151ab7  mov     esi, eax
0x180151ab9  test    eax, eax
0x180151abb  jns     short loc_180151AEE
0x180151abd  mov     eax, cs:CallbackContext
0x180151ac3  cmp     eax, 2
0x180151ac6  jbe     loc_180152385
0x180151acc  lea     rax, aUnexpectedForC; "Unexpected for child listener to be nul"...
0x180151ad3  mov     dword ptr [rsp+230h+var_1D0], 79h ; 'y'
0x180151adb  lea     r14, aConnectionrequ; "ConnectionRequest"
0x180151ae2  lea     rdx, qword_18029BBB8
0x180151ae9  jmp     loc_18015231E
0x180151aee  mov     eax, cs:?m_requestId@SideTransportStream@@0IA; uint SideTransportStream::m_requestId
0x180151af4  mov     rdi, [r15+30h]
0x180151af8  mov     [rbp+130h+var_68], eax
0x180151afe  movups  xmm0, xmmword ptr [r15+80h]
0x180151b06  mov     [r15+30h], r14
0x180151b0a  movdqu  [rbp+130h+var_78], xmm0
0x180151b12  test    r14, r14
0x180151b15  jz      short loc_180151B26
0x180151b17  mov     rax, [r14]
0x180151b1a  mov     rcx, r14
0x180151b1d  mov     rax, [rax+8]
0x180151b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b26  test    rdi, rdi
0x180151b29  jz      short loc_180151B3A
0x180151b2b  mov     rax, [rdi]
0x180151b2e  mov     rcx, rdi
0x180151b31  mov     rax, [rax+10h]
0x180151b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b3a  mov     rdi, [r15+48h]
0x180151b3e  mov     [r15+48h], rbx
0x180151b42  test    rbx, rbx
0x180151b45  jz      short loc_180151B56
0x180151b47  mov     rax, [rbx]
0x180151b4a  mov     rcx, rbx
0x180151b4d  mov     rax, [rax+8]
0x180151b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b56  test    rdi, rdi
0x180151b59  jz      short loc_180151B6A
0x180151b5b  mov     rax, [rdi]
0x180151b5e  mov     rcx, rdi
0x180151b61  mov     rax, [rax+10h]
0x180151b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b6a  mov     rdx, [rbp+130h+var_1B0]; struct IRDPENCPlatformContext *
0x180151b6e  lea     r13, [r15-10h]
0x180151b72  mov     rcx, r13; this
0x180151b75  call    ?InitPerfMonSession@SideTransportStream@@IEAAJPEAUIRDPENCPlatformContext@@@Z; SideTransportStream::InitPerfMonSession(IRDPENCPlatformContext *)
0x180151b7a  mov     rcx, [rbp+130h+var_1B0]
0x180151b7e  lea     r8, [rbp+130h+var_1A8]
0x180151b82  lea     rdx, aStartdirectlyw; "StartDirectlyWithSideTransport"
0x180151b89  mov     rax, [rcx]
0x180151b8c  mov     rax, [rax+20h]
0x180151b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151b95  lea     r14, aConnectionrequ; "ConnectionRequest"
0x180151b9c  test    eax, eax
0x180151b9e  js      short loc_180151BAA
0x180151ba0  cmp     [rbp+130h+var_1A8], r12d
0x180151ba4  jnz     loc_180151C51
0x180151baa  mov     rbx, [r15+30h]
0x180151bae  test    rbx, rbx
0x180151bb1  jz      loc_180151C51
0x180151bb7  mov     rax, [rbx]
0x180151bba  lea     rdi, [r15+38h]
0x180151bbe  mov     rcx, [rdi]
0x180151bc1  mov     [rdi], r12
0x180151bc4  mov     rsi, [rax]
0x180151bc7  test    rcx, rcx
0x180151bca  jz      short loc_180151BD8
0x180151bcc  mov     rdx, [rcx]
0x180151bcf  mov     rax, [rdx+10h]
0x180151bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151bd8  mov     r8, rdi
0x180151bdb  lea     rdx, IID_IRdpIceToStackCallback
0x180151be2  mov     rcx, rbx
0x180151be5  mov     rax, rsi
0x180151be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151bed  test    eax, eax
0x180151bef  jns     short loc_180151C51
0x180151bf1  mov     ecx, cs:CallbackContext
0x180151bf7  cmp     ecx, 3
0x180151bfa  jbe     short loc_180151C51
0x180151bfc  mov     dword ptr [rsp+230h+var_1D0], eax
0x180151c00  lea     rdx, byte_18029C219
0x180151c07  lea     rax, aFailedToGetIrd_1; "Failed to get IRdpIceToStackCallback in"...
0x180151c0e  mov     [rsp+230h+var_1D8], r14
0x180151c13  mov     [rsp+230h+var_1C8], rax
0x180151c18  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180151c1f  mov     [rsp+230h+var_1C0], rax
0x180151c24  lea     rax, [rsp+230h+var_1D8]
0x180151c29  mov     [rsp+230h+var_1F8], rax
0x180151c2e  lea     rax, [rsp+230h+var_1D0]
0x180151c33  mov     [rsp+230h+var_200], rax
0x180151c38  lea     rax, [rsp+230h+var_1C8]
0x180151c3d  mov     [rsp+230h+var_208], rax
0x180151c42  lea     rax, [rsp+230h+var_1C0]
0x180151c47  mov     [rsp+230h+var_210], rax
0x180151c4c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180151c51  mov     rcx, [rbp+130h+var_1A0]
0x180151c55  mov     rbx, [rbp+130h+var_1B0]
0x180151c59  mov     rax, [rbx]
0x180151c5c  mov     [rbp+130h+var_1A0], r12
0x180151c60  mov     rdi, [rax+30h]
0x180151c64  test    rcx, rcx
0x180151c67  jz      short loc_180151C75
0x180151c69  mov     rdx, [rcx]
0x180151c6c  mov     rax, [rdx+10h]
0x180151c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151c75  lea     r9, [rbp+130h+var_1A0]
0x180151c79  mov     rcx, rbx
0x180151c7c  lea     r8, IID_IUnknown
0x180151c83  mov     rax, rdi
0x180151c86  lea     rdx, aSidetransportc; "SideTransportCreationParams"
0x180151c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151c92  mov     esi, eax
0x180151c94  test    eax, eax
0x180151c96  jns     short loc_180151CC2
0x180151c98  mov     eax, cs:CallbackContext
0x180151c9e  cmp     eax, 2
0x180151ca1  jbe     loc_180152385
0x180151ca7  lea     rax, aFailedToGetCon_8; "Failed to get CONN_PROPERTY_SIDE_TRANSP"...
0x180151cae  mov     dword ptr [rsp+230h+var_1D0], 99h
0x180151cb6  lea     rdx, byte_18029B453
0x180151cbd  jmp     loc_18015231E
0x180151cc2  mov     rcx, [rbp+130h+var_1A0]
0x180151cc6  lea     r8, [rsp+230h+var_1D0]
0x180151ccb  mov     [rsp+230h+var_1D0], r12
0x180151cd0  lea     rdx, _GUID_3942b544_2536_4680_919b_362c63b75246
0x180151cd7  mov     rax, [rcx]
0x180151cda  mov     rax, [rax]
0x180151cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151ce2  mov     rbx, [rsp+230h+var_1D0]
0x180151ce7  lea     rcx, [rsp+230h+var_1D0]
0x180151cec  mov     [rbp+130h+var_140], rbx
0x180151cf0  mov     [rsp+230h+var_1D0], r12
0x180151cf5  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180151cfa  test    rbx, rbx
0x180151cfd  jnz     short loc_180151D4C
0x180151cff  mov     eax, cs:CallbackContext
0x180151d05  mov     ecx, 8000FFFFh
0x180151d0a  mov     esi, ecx
0x180151d0c  cmp     eax, 2
0x180151d0f  jbe     loc_180152385
0x180151d15  lea     rax, aInvalidSpsidet; "Invalid spSideTransportCreationParams"
0x180151d1c  mov     dword ptr [rsp+230h+var_1D0], 9Ch
0x180151d24  mov     [rsp+230h+var_1D8], rax
0x180151d29  lea     rdx, dword_18029CC4C
0x180151d30  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180151d37  mov     [rsp+230h+var_1E0], ecx
0x180151d3b  mov     [rsp+230h+var_1C0], rax
0x180151d40  lea     rax, aErrorCondition; "Error condition failed"
0x180151d47  jmp     loc_18015233A
0x180151d4c  mov     rax, [rbx]
0x180151d4f  mov     rcx, rbx
0x180151d52  mov     rax, [rax+18h]
0x180151d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151d5b  mov     rdi, rax
0x180151d5e  test    rax, rax
0x180151d61  jnz     short loc_180151DB0
0x180151d63  mov     eax, cs:CallbackContext
0x180151d69  mov     ecx, 8000FFFFh
0x180151d6e  mov     esi, ecx
0x180151d70  cmp     eax, 2
  ... truncated ...
```
