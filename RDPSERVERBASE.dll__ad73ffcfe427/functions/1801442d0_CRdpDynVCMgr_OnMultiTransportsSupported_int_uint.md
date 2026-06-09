# CRdpDynVCMgr::OnMultiTransportsSupported(int,uint)

- ea: `0x1801442d0`
- end: `0x180144dbf`
- name: `?OnMultiTransportsSupported@CRdpDynVCMgr@@UEAAXHI@Z`
- size: `2799`
- prototype: `void(CRdpDynVCMgr *__hidden this, int, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x1800023e4`
- `0x180002d3c`
- `0x18000ce04`
- `0x18002aafc`
- `0x18004d52c`
- `0x18004f5bc`
- `0x18007e9e0`
- `0x18013cc90`
- `0x18013d5c8`
- `0x1801406a4`
- `0x180141840`
- `0x1801442d0`
- `0x180145164`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1801448ca`
- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1801448ca`
- `RDPBASE!RDPServerStackDiagnostics_LogShortpathFallbackCheckpoint` at `0x1801448f1`
- `RDPBASE!RDPServerStackDiagnostics_LogShortpathFallbackCheckpoint` at `0x1801448f1`

## string_xrefs

- `0x1801443da`: `StartDirectlyWithSideTransport`
- `0x1801443a5`: `DynVCMgr has already Terminated, quitting`
- `0x180144423`: `Start directly with side transport - skipping multitransport initiation since we are already running it.`
- `0x1801447da`: `Setting TransportLinkType`
- `0x1801449eb`: `CRdpDynVCMgr: Tcp Side Tunnel supported by client and server`
- `0x180144a39`: `CRdpDynVCMgr: Tcp Side Tunnel not supported by client`
- `0x180144c2f`: `CRdpDynVCMgr: Initiating Tcp Side Tunnel request to client`
- `0x180144c75`: `CRdpDynVCMgr: InitiateMultiTransport for TCPSIDE failed synchronously`

## pseudocode

```c
void __fastcall CRdpDynVCMgr::OnMultiTransportsSupported(CRdpDynVCMgr *this, int a2, unsigned int a3, int a4)
{
  int v7; // ecx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  BOOL v11; // eax
  BOOL v12; // eax
  int v13; // eax
  int Instance; // eax
  BOOL v15; // eax
  int v16; // eax
  int v17; // r8d
  int v18; // r9d
  __int128 v19; // xmm0
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  BOOL v23; // eax
  int v24; // esi
  BOOL v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // [rsp+50h] [rbp-59h] BYREF
  const char *v33; // [rsp+58h] [rbp-51h] BYREF
  BOOL v34; // [rsp+60h] [rbp-49h] BYREF
  const char *v35; // [rsp+68h] [rbp-41h] BYREF
  const char *v36; // [rsp+70h] [rbp-39h] BYREF
  const char *v37; // [rsp+78h] [rbp-31h] BYREF
  int v38; // [rsp+80h] [rbp-29h] BYREF
  __int64 v39; // [rsp+88h] [rbp-21h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-19h] BYREF
  GUID v41; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v42; // [rsp+B0h] [rbp+7h] BYREF
  __int128 v43; // [rsp+C0h] [rbp+17h] BYREF

  v38 = 0;
  v39 = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v32 = a3;
    v34 = a2 != 0;
    v37 = "CRdpDynVCMgr: OnMultiTransportSupported";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_180297BE1,
      a3,
      a4,
      (__int64)&v37,
      (__int64)&v34,
      (__int64)&v32);
  }
  CRdpDynVCMgr::LogUDPStateTransition((CRdpDynVCMgr *)((char *)this - 80), 0, 0, 2 - (a2 != 0), a2 == 0, 0);
  v37 = (char *)this + 120;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 120));
  if ( (*((_BYTE *)this - 52) & 4) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v33 = "DynVCMgr has already Terminated, quitting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)&byte_180297B97,
        v8,
        v9,
        (__int64)&v33);
    }
LABEL_20:
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v37);
    goto LABEL_113;
  }
  v10 = *((_QWORD *)this + 12);
  if ( v10 )
    (*(void (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v10 + 32LL))(
      v10,
      L"StartDirectlyWithSideTransport",
      &v38);
  if ( v38 )
  {
    *((_DWORD *)this + 4982) = 1;
    *((_DWORD *)this + 4981) = 0;
    *((_DWORD *)this + 4983) = 0;
    *((_DWORD *)this + 4969) = 1;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v33 = "Start directly with side transport - skipping multitransport initiation since we are already running it.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)&dword_180297BBC,
        v8,
        v9,
        (__int64)&v33);
    }
    v11 = a2 && (a3 & 2) != 0;
    *((_DWORD *)this + 85) = v11;
    *(_QWORD *)((char *)this + 348) = 1;
    *((_DWORD *)this + 91) = -2147024846;
    CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147942450LL, 2);
    v12 = a2 && (a3 & 4) != 0;
    *((_DWORD *)this + 105) = v12;
    *(_QWORD *)((char *)this + 428) = 1;
    *((_DWORD *)this + 111) = -2147024846;
    CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147942450LL, 3);
    goto LABEL_20;
  }
  if ( a2 )
  {
    CRdpDynVCMgr::OnSoftSyncProtocolExtensionsSupported((CRdpDynVCMgr *)((char *)this - 80), a3);
    *((_DWORD *)this + 4971) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 480LL))(*((_QWORD *)this + 21));
    if ( (unsigned int)CallbackContext > 4 )
    {
      v32 = *((_DWORD *)this + 4971) != 0;
      v33 = "VCMgr: Autodetect supported?";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&word_180297B66,
        v8,
        v9,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  if ( *((_DWORD *)this + 4971) )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 21) + 472LL))(
            *((_QWORD *)this + 21),
            &v39);
    if ( v13 < 0 )
    {
      LODWORD(v10) = (_DWORD)CallbackContext;
      if ( (unsigned int)CallbackContext > 3 )
      {
        v32 = v13;
        v33 = "OnMultiTransportsSupported";
        v35 = "Failed to get network quality manager";
        *(_QWORD *)&v43 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_180297B02,
          v8,
          v9,
          (__int64)&v43,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v33);
      }
    }
    if ( v39 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v33 = "Creating Listener for TCP main tunnel";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v10,
          (unsigned int)byte_180297B41,
          v8,
          v9,
          (__int64)&v33);
      }
      Instance = CRdpDynVCMgrNetworkListenerCallback::CreateInstance(0, v39, (char *)this - 80, (char *)this + 208);
      if ( Instance < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v34 = Instance;
          v33 = "Failed to register for network quality change notifications!";
          v36 = "Error HResult failed";
          v35 = "OnMultiTransportsSupported";
          v32 = 3502;
          *(_QWORD *)&v43 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
            (unsigned int)&dword_180297A8C,
            v8,
            v9,
            (__int64)&v36,
            (__int64)&v34,
            (__int64)&v43,
            (__int64)&v32,
            (__int64)&v35,
            (__int64)&v33);
        }
        goto LABEL_20;
      }
    }
  }
  if ( a2 && *((_DWORD *)this + 64) && (a3 & 1) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v36 = "CRdpDynVCMgr: UdpFec Tunnel supported by client and server";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)byte_180297ADD,
        v8,
        v9,
        (__int64)&v36);
    }
    *((_DWORD *)this + 65) = 1;
    v32 = 1;
  }
  else
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v43) = a3;
      LODWORD(v35) = a2 != 0;
      v36 = "CRdpDynVCMgr: UdpFec Tunnel not supported on client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&byte_180297A17,
        v8,
        v9,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v43);
    }
    v15 = a2 && (a3 & 1) != 0;
    *((_DWORD *)this + 65) = v15;
    *(_QWORD *)((char *)this + 268) = 1;
    *((_DWORD *)this + 71) = -2147024846;
    CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147942450LL, 1);
    v10 = *((_QWORD *)this + 12);
    v34 = 0;
    v32 = 0;
    if ( v10
      && (*(int (__fastcall **)(__int64, const wchar_t *, BOOL *))(*(_QWORD *)v10 + 40LL))(
           v10,
           L"ReverseConnectMode",
           &v34) >= 0
      && v34
      && ((*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 12) + 32LL))(
            *((_QWORD *)this + 12),
            L"TransportTypeReported",
            &v32) < 0
       || !v32) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v35) = 0;
        v36 = "Setting TransportLinkType";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)&dword_180297A54,
          v8,
          v9,
          (__int64)&v36,
          (__int64)&v35);
      }
      v16 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 12) + 64LL))(
              *((_QWORD *)this + 12),
              L"TransportTypeReported",
              1);
      if ( v16 < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v43) = v16;
          v36 = "Couldn't set CONN_PROPERTY_TRANSPORT_TYPE_REPORTED";
          *(_QWORD *)&v42 = "Error HResult failed";
          v33 = "OnMultiTransportsSupported";
          LODWORD(v35) = 3543;
          *(_QWORD *)&ActivityId.Data1 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
            (unsigned int)&word_1802979C6,
            v17,
            v18,
            (__int64)&v42,
            (__int64)&v43,
            (__int64)&ActivityId,
            (__int64)&v35,
            (__int64)&v33,
            (__int64)&v36);
        }
        goto LABEL_20;
      }
      v42 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
      RDPServerStackDiagnostics_LogContext(&v42, 2, 0);
      v42 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
      RDPServerStackDiagnostics_LogShortpathFallbackCheckpoint(&v42, 714, "NotSupported");
    }
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v8, v9) )
    {
      v19 = (__int128)*RdpActivityId::GetCurrentActivityId(&v41);
      v33 = (const char *)0x1000000;
      *(_QWORD *)&v42 = &v43;
      *(_QWORD *)&ActivityId.Data1 = "Udp";
      v36 = "Stack";
      v35 = "Checkpoint";
      v43 = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v20,
        (unsigned int)&dword_180297944,
        v21,
        v22,
        (__int64)&v35,
        (__int64)&v33,
        (__int64)&v36,
        (__int64)&ActivityId,
        (__int64)&v42);
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "CRdpDynVCMgr: Udp is not supported.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)byte_1802979A1,
        v8,
        v9,
        (__int64)&v42);
    }
    v32 = 0;
    if ( !a2 )
      goto LABEL_69;
  }
  if ( *((_DWORD *)this + 84) && (a3 & 2) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "CRdpDynVCMgr: Tcp Side Tunnel supported by client and server";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)word_1802978E2,
        v8,
        v9,
        (__int64)&v42);
    }
    *((_DWORD *)this + 85) = 1;
    v34 = 1;
    goto LABEL_76;
  }
LABEL_69:
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v35) = a3;
    LODWORD(v43) = a2 != 0;
    *(_QWORD *)&v42 = "CRdpDynVCMgr: Tcp Side Tunnel not supported by client";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)&byte_180297907,
      v8,
      v9,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v35);
  }
  v23 = a2 && (a3 & 2) != 0;
  *((_DWORD *)this + 85) = v23;
  *(_QWORD *)((char *)this + 348) = 1;
  *((_DWORD *)this + 91) = -2147024846;
  CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147942450LL, 2);
  v34 = 0;
  if ( !a2 )
    goto LABEL_81;
LABEL_76:
  if ( !*((_DWORD *)this + 104) || (a3 & 4) == 0 )
  {
LABEL_81:
    LODWORD(v33) = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v35) = a3;
      LODWORD(v43) = a2 != 0;
      *(_QWORD *)&v42 = "CRdpDynVCMgr: UdpFec Lossy Tunnel not supported by client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_1802978A5,
        v8,
        v9,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v35);
    }
    v25 = a2 && (a3 & 4) != 0;
    *((_DWORD *)this + 105) = v25;
    *(_QWORD *)((char *)this + 428) = 1;
    *((_DWORD *)this + 111) = -2147024846;
    CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147942450LL, 3);
    v24 = (int)v33;
    goto LABEL_88;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&v42 = "CRdpDynVCMgr: UdpFec Lossy Tunnel supported by client and server";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (unsigned int)qword_180297880,
      v8,
      v9,
      (__int64)&v42);
  }
  *((_DWORD *)this + 105) = 1;
  v24 = 1;
LABEL_88:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v37);
  if ( v32 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "CRdpDynVCMgr: Initiating UdpFec Tunnel request to client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v26,
        (unsigned int)&word_18029782E,
        v27,
        v28,
        (__int64)&v42);
    }
    v29 = CRdpDynVCMgr::InitiateMultiTransport((CRdpDynVCMgr *)((char *)this - 80), 1u);
    if ( v29 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v33) = v29;
        *(_QWORD *)&v42 = "CRdpDynVCMgr: InitiateMultiTransport for UDPFEC failed synchronously";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_180297853,
          v27,
          v28,
          (__int64)&v42,
          (__int64)&v33);
      }
      *(_QWORD *)((char *)this + 268) = 1;
      *((_DWORD *)this + 71) = -2147467259;
      CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147500037LL, 1);
    }
  }
  if ( v34 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "CRdpDynVCMgr: Initiating Tcp Side Tunnel request to client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v26,
        (unsigned int)&dword_1802977DC,
        v27,
        v28,
        (__int64)&v42);
    }
    v30 = CRdpDynVCMgr::InitiateMultiTransport((CRdpDynVCMgr *)((char *)this - 80), 2u);
    if ( v30 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v33) = v30;
        *(_QWORD *)&v42 = "CRdpDynVCMgr: InitiateMultiTransport for TCPSIDE failed synchronously";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_180297801,
          v27,
          v28,
          (__int64)&v42,
          (__int64)&v33);
      }
      *(_QWORD *)((char *)this + 348) = 1;
      *((_DWORD *)this + 91) = -2147467259;
      CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147500037LL, 2);
    }
  }
  if ( v24 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "CRdpDynVCMgr: Initiating UdpFec Lossy Tunnel request to client";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v26,
        (unsigned int)word_18029778A,
        v27,
        v28,
        (__int64)&v42);
    }
    v31 = CRdpDynVCMgr::InitiateMultiTransport((CRdpDynVCMgr *)((char *)this - 80), 4u);
    if ( v31 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v33) = v31;
        *(_QWORD *)&v42 = "CRdpDynVCMgr: InitiateMultiTransport for UdpFEC Lossy failed synchronously";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)&byte_1802977AF,
          v27,
          v28,
          (__int64)&v42,
          (__int64)&v33);
      }
      *(_QWORD *)((char *)this + 428) = 1;
      *((_DWORD *)this + 111) = -2147467259;
      CRdpDynVCMgr::BroadcastTunnelBoundResult((char *)this - 80, 2147500037LL, 3);
    }
  }
  if ( (a3 & 0x100) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v42 = "UDP first supported ";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v26,
        (unsigned int)byte_18029772D,
        v27,
        v28,
        (__int64)&v42);
    }
    *((_DWORD *)this + 4969) = 1;
  }
LABEL_113:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v39);
}

```

## disassembly

```asm
0x1801442d0  mov     [rsp-8+arg_8], rbx
0x1801442d5  mov     [rsp-8+arg_10], rsi
0x1801442da  push    rbp
0x1801442db  push    rdi
0x1801442dc  push    r12
0x1801442de  push    r14
0x1801442e0  push    r15
0x1801442e2  lea     rbp, [rsp-37h]
0x1801442e7  sub     rsp, 0E0h
0x1801442ee  mov     rax, cs:__security_cookie
0x1801442f5  xor     rax, rsp
0x1801442f8  mov     [rbp+57h+var_30], rax
0x1801442fc  mov     eax, cs:CallbackContext
0x180144302  xor     edi, edi
0x180144304  mov     [rbp+57h+var_80], edi
0x180144307  mov     r14d, r8d
0x18014430a  mov     [rbp+57h+var_78], rdi
0x18014430e  mov     esi, edx
0x180144310  mov     rbx, rcx
0x180144313  cmp     eax, 4
0x180144316  jbe     short loc_180144358
0x180144318  test    edx, edx
0x18014431a  mov     [rbp+57h+var_B0], r8d
0x18014431e  mov     eax, edi
0x180144320  lea     rdx, byte_180297BE1
0x180144327  setnz   al
0x18014432a  mov     [rbp+57h+var_A0], eax
0x18014432d  lea     rax, aCrdpdynvcmgrOn_3; "CRdpDynVCMgr: OnMultiTransportSupported"
0x180144334  mov     [rbp+57h+var_88], rax
0x180144338  lea     rax, [rbp+57h+var_B0]
0x18014433c  mov     [rsp+100h+var_D0], rax
0x180144341  lea     rax, [rbp+57h+var_A0]
0x180144345  mov     qword ptr [rsp+100h+var_D8], rax
0x18014434a  lea     rax, [rbp+57h+var_88]
0x18014434e  mov     qword ptr [rsp+100h+var_E0], rax
0x180144353  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180144358  mov     ecx, edi
0x18014435a  mov     [rsp+100h+var_D8], edi; int
0x18014435e  test    esi, esi
0x180144360  lea     r12, [rbx-50h]
0x180144364  mov     eax, esi
0x180144366  setz    cl
0x180144369  neg     eax
0x18014436b  mov     [rsp+100h+var_E0], ecx; int
0x18014436f  mov     rcx, r12; this
0x180144372  sbb     r9d, r9d
0x180144375  xor     r8d, r8d; int
0x180144378  add     r9d, 2; int
0x18014437c  xor     edx, edx; int
0x18014437e  call    ?LogUDPStateTransition@CRdpDynVCMgr@@IEAAXHJJJJ@Z; CRdpDynVCMgr::LogUDPStateTransition(int,long,long,long,long)
0x180144383  lea     rcx, [rbx+78h]; this
0x180144387  mov     [rbp+57h+var_88], rcx
0x18014438b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180144390  test    byte ptr [rbx-34h], 4
0x180144394  jz      short loc_1801443CA
0x180144396  mov     eax, cs:CallbackContext
0x18014439c  cmp     eax, 4
0x18014439f  jbe     loc_1801444B3
0x1801443a5  lea     rax, aDynvcmgrHasAlr; "DynVCMgr has already Terminated, quitti"...
0x1801443ac  mov     [rbp+57h+var_A8], rax
0x1801443b0  lea     rdx, byte_180297B97
0x1801443b7  lea     rax, [rbp+57h+var_A8]
0x1801443bb  mov     qword ptr [rsp+100h+var_E0], rax
0x1801443c0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801443c5  jmp     loc_1801444B3
0x1801443ca  mov     rcx, [rbx+60h]
0x1801443ce  test    rcx, rcx
0x1801443d1  jz      short loc_1801443EA
0x1801443d3  mov     rax, [rcx]
0x1801443d6  lea     r8, [rbp+57h+var_80]
0x1801443da  lea     rdx, aStartdirectlyw; "StartDirectlyWithSideTransport"
0x1801443e1  mov     rax, [rax+20h]
0x1801443e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801443ea  cmp     [rbp+57h+var_80], edi
0x1801443ed  jz      loc_1801444C1
0x1801443f3  mov     edi, 1
0x1801443f8  mov     [rbx+4DD8h], edi
0x1801443fe  mov     dword ptr [rbx+4DD4h], 0
0x180144408  mov     dword ptr [rbx+4DDCh], 0
0x180144412  mov     [rbx+4DA4h], edi
0x180144418  mov     eax, cs:CallbackContext
0x18014441e  cmp     eax, 4
0x180144421  jbe     short loc_180144443
0x180144423  lea     rax, aStartDirectlyW; "Start directly with side transport - sk"...
0x18014442a  mov     [rbp+57h+var_A8], rax
0x18014442e  lea     rdx, dword_180297BBC
0x180144435  lea     rax, [rbp+57h+var_A8]
0x180144439  mov     qword ptr [rsp+100h+var_E0], rax
0x18014443e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180144443  test    esi, esi
0x180144445  jz      short loc_180144451
0x180144447  test    r14b, 2
0x18014444b  jz      short loc_180144451
0x18014444d  mov     eax, edi
0x18014444f  jmp     short loc_180144453
0x180144451  xor     eax, eax
0x180144453  mov     r15d, 80070032h
0x180144459  mov     [rbx+154h], eax
0x18014445f  mov     edx, r15d
0x180144462  mov     [rbx+15Ch], rdi
0x180144469  mov     r8d, 2
0x18014446f  mov     [rbx+16Ch], r15d
0x180144476  mov     rcx, r12
0x180144479  call    ?BroadcastTunnelBoundResult@CRdpDynVCMgr@@IEAAJJW4DynVCMgrServerTunnels@@@Z; CRdpDynVCMgr::BroadcastTunnelBoundResult(long,DynVCMgrServerTunnels)
0x18014447e  test    esi, esi
0x180144480  jz      short loc_18014448C
0x180144482  test    r14b, 4
0x180144486  jz      short loc_18014448C
0x180144488  mov     eax, edi
0x18014448a  jmp     short loc_18014448E
0x18014448c  xor     eax, eax
0x18014448e  mov     r8d, 3
0x180144494  mov     [rbx+1A4h], eax
0x18014449a  mov     edx, r15d
0x18014449d  mov     [rbx+1ACh], rdi
0x1801444a4  mov     rcx, r12
0x1801444a7  mov     [rbx+1BCh], r15d
0x1801444ae  call    ?BroadcastTunnelBoundResult@CRdpDynVCMgr@@IEAAJJW4DynVCMgrServerTunnels@@@Z; CRdpDynVCMgr::BroadcastTunnelBoundResult(long,DynVCMgrServerTunnels)
0x1801444b3  lea     rcx, [rbp+57h+var_88]; this
0x1801444b7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1801444bc  jmp     loc_180144D8E
0x1801444c1  test    esi, esi
0x1801444c3  jz      short loc_18014452E
0x1801444c5  mov     edx, r14d; unsigned int
0x1801444c8  mov     rcx, r12; this
0x1801444cb  call    ?OnSoftSyncProtocolExtensionsSupported@CRdpDynVCMgr@@IEAAXI@Z; CRdpDynVCMgr::OnSoftSyncProtocolExtensionsSupported(uint)
0x1801444d0  mov     rcx, [rbx+0A8h]
0x1801444d7  mov     rax, [rcx]
0x1801444da  mov     rax, [rax+1E0h]
0x1801444e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801444e6  mov     [rbx+4DACh], eax
0x1801444ec  mov     eax, cs:CallbackContext
0x1801444f2  cmp     eax, 4
0x1801444f5  jbe     short loc_18014452E
0x1801444f7  xor     eax, eax
0x1801444f9  lea     rdx, word_180297B66
0x180144500  cmp     [rbx+4DACh], eax
0x180144506  setnz   al
0x180144509  mov     [rbp+57h+var_B0], eax
0x18014450c  lea     rax, aVcmgrAutodetec; "VCMgr: Autodetect supported?"
0x180144513  mov     [rbp+57h+var_A8], rax
0x180144517  lea     rax, [rbp+57h+var_B0]
0x18014451b  mov     qword ptr [rsp+100h+var_D8], rax
0x180144520  lea     rax, [rbp+57h+var_A8]
0x180144524  mov     qword ptr [rsp+100h+var_E0], rax
0x180144529  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18014452e  cmp     dword ptr [rbx+4DACh], 0
0x180144535  lea     rdi, aOnmultitranspo_3; "OnMultiTransportsSupported"
0x18014453c  jz      loc_180144690
0x180144542  mov     rcx, [rbx+0A8h]
0x180144549  lea     rdx, [rbp+57h+var_78]
0x18014454d  mov     rax, [rcx]
0x180144550  mov     rax, [rax+1D8h]
0x180144557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014455c  test    eax, eax
0x18014455e  jns     short loc_1801445B8
0x180144560  mov     ecx, cs:CallbackContext
0x180144566  cmp     ecx, 3
0x180144569  jbe     short loc_1801445B8
0x18014456b  mov     [rbp+57h+var_B0], eax
0x18014456e  lea     rdx, word_180297B02
0x180144575  lea     rax, aFailedToGetNet; "Failed to get network quality manager"
0x18014457c  mov     [rbp+57h+var_A8], rdi
0x180144580  mov     [rbp+57h+var_98], rax
0x180144584  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18014458b  mov     qword ptr [rbp+57h+var_40], rax
0x18014458f  lea     rax, [rbp+57h+var_A8]
0x180144593  mov     [rsp+100h+var_C8], rax
0x180144598  lea     rax, [rbp+57h+var_B0]
0x18014459c  mov     [rsp+100h+var_D0], rax
0x1801445a1  lea     rax, [rbp+57h+var_98]
0x1801445a5  mov     qword ptr [rsp+100h+var_D8], rax
0x1801445aa  lea     rax, [rbp+57h+var_40]
0x1801445ae  mov     qword ptr [rsp+100h+var_E0], rax
0x1801445b3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801445b8  cmp     [rbp+57h+var_78], 0
0x1801445bd  jz      loc_180144690
0x1801445c3  mov     eax, cs:CallbackContext
0x1801445c9  cmp     eax, 5
0x1801445cc  jbe     short loc_1801445EE
0x1801445ce  lea     rax, aCreatingListen; "Creating Listener for TCP main tunnel"
0x1801445d5  mov     [rbp+57h+var_A8], rax
0x1801445d9  lea     rdx, byte_180297B41
0x1801445e0  lea     rax, [rbp+57h+var_A8]
0x1801445e4  mov     qword ptr [rsp+100h+var_E0], rax
0x1801445e9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801445ee  mov     rdx, [rbp+57h+var_78]
0x1801445f2  lea     r9, [rbx+0D0h]
0x1801445f9  mov     r8, r12
0x1801445fc  xor     ecx, ecx
0x1801445fe  call    ?CreateInstance@CRdpDynVCMgrNetworkListenerCallback@@SAJW4DynVCMgrServerTunnels@@PEAUIRDPNetworkQualityManager@@PEAVCRdpDynVCMgr@@PEAPEAV1@@Z; CRdpDynVCMgrNetworkListenerCallback::CreateInstance(DynVCMgrServerTunnels,IRDPNetworkQualityManager *,CRdpDynVCMgr *,CRdpDynVCMgrNetworkListenerCallback * *)
0x180144603  test    eax, eax
0x180144605  jns     loc_180144690
0x18014460b  mov     ecx, cs:CallbackContext
0x180144611  cmp     ecx, 2
0x180144614  jbe     loc_1801444B3
0x18014461a  mov     [rbp+57h+var_A0], eax
0x18014461d  lea     rcx, aFailedToRegist_6; "Failed to register for network quality "...
0x180144624  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18014462b  mov     [rbp+57h+var_A8], rcx
0x18014462f  mov     [rbp+57h+var_90], rax
0x180144633  lea     rcx, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18014463a  lea     rax, [rbp+57h+var_A8]
0x18014463e  mov     [rbp+57h+var_98], rdi
0x180144642  mov     [rsp+100h+var_B8], rax
0x180144647  lea     rdx, dword_180297A8C
0x18014464e  lea     rax, [rbp+57h+var_98]
0x180144652  mov     [rbp+57h+var_B0], 0DAEh
0x180144659  mov     [rsp+100h+var_C0], rax
0x18014465e  lea     rax, [rbp+57h+var_B0]
0x180144662  mov     [rsp+100h+var_C8], rax
0x180144667  lea     rax, [rbp+57h+var_40]
0x18014466b  mov     [rsp+100h+var_D0], rax
0x180144670  lea     rax, [rbp+57h+var_A0]
0x180144674  mov     qword ptr [rsp+100h+var_D8], rax
0x180144679  lea     rax, [rbp+57h+var_90]
0x18014467d  mov     qword ptr [rbp+57h+var_40], rcx
0x180144681  mov     qword ptr [rsp+100h+var_E0], rax
0x180144686  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18014468b  jmp     loc_1801444B3
0x180144690  mov     edi, 1
0x180144695  mov     r15d, 80070032h
0x18014469b  test    esi, esi
0x18014469d  jz      short loc_1801446E6
0x18014469f  cmp     dword ptr [rbx+100h], 0
0x1801446a6  jz      short loc_1801446E6
0x1801446a8  test    dil, r14b
0x1801446ab  jz      short loc_1801446E6
0x1801446ad  mov     eax, cs:CallbackContext
0x1801446b3  cmp     eax, 4
0x1801446b6  jbe     short loc_1801446D8
0x1801446b8  lea     rax, aCrdpdynvcmgrUd_2; "CRdpDynVCMgr: UdpFec Tunnel supported b"...
0x1801446bf  mov     [rbp+57h+var_90], rax
0x1801446c3  lea     rdx, byte_180297ADD
0x1801446ca  lea     rax, [rbp+57h+var_90]
0x1801446ce  mov     qword ptr [rsp+100h+var_E0], rax
0x1801446d3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801446d8  mov     [rbx+104h], edi
0x1801446de  mov     [rbp+57h+var_B0], edi
0x1801446e1  jmp     loc_1801449D1
0x1801446e6  mov     eax, cs:CallbackContext
0x1801446ec  cmp     eax, 4
0x1801446ef  jbe     short loc_180144731
0x1801446f1  xor     eax, eax
0x1801446f3  mov     dword ptr [rbp+57h+var_40], r14d
0x1801446f7  test    esi, esi
0x1801446f9  lea     rdx, byte_180297A17
0x180144700  setnz   al
0x180144703  mov     dword ptr [rbp+57h+var_98], eax
0x180144706  lea     rax, aCrdpdynvcmgrUd_1; "CRdpDynVCMgr: UdpFec Tunnel not support"...
0x18014470d  mov     [rbp+57h+var_90], rax
0x180144711  lea     rax, [rbp+57h+var_40]
0x180144715  mov     [rsp+100h+var_D0], rax
0x18014471a  lea     rax, [rbp+57h+var_98]
0x18014471e  mov     qword ptr [rsp+100h+var_D8], rax
0x180144723  lea     rax, [rbp+57h+var_90]
0x180144727  mov     qword ptr [rsp+100h+var_E0], rax
0x18014472c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180144731  test    esi, esi
0x180144733  jz      short loc_18014473E
0x180144735  test    dil, r14b
0x180144738  jz      short loc_18014473E
0x18014473a  mov     eax, edi
0x18014473c  jmp     short loc_180144740
0x18014473e  xor     eax, eax
0x180144740  mov     r8d, edi
0x180144743  mov     [rbx+104h], eax
0x180144749  mov     edx, r15d
0x18014474c  mov     [rbx+10Ch], rdi
0x180144753  mov     rcx, r12
0x180144756  mov     [rbx+11Ch], r15d
0x18014475d  call    ?BroadcastTunnelBoundResult@CRdpDynVCMgr@@IEAAJJW4DynVCMgrServerTunnels@@@Z; CRdpDynVCMgr::BroadcastTunnelBoundResult(long,DynVCMgrServerTunnels)
0x180144762  mov     rcx, [rbx+60h]
0x180144766  mov     [rbp+57h+var_A0], 0
0x18014476d  mov     [rbp+57h+var_B0], 0
0x180144774  test    rcx, rcx
0x180144777  jz      loc_1801448F7
0x18014477d  mov     rax, [rcx]
0x180144780  lea     r8, [rbp+57h+var_A0]
0x180144784  lea     rdx, aReverseconnect_1; "ReverseConnectMode"
0x18014478b  mov     rax, [rax+28h]
0x18014478f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144794  test    eax, eax
0x180144796  js      loc_1801448F7
0x18014479c  cmp     [rbp+57h+var_A0], 0
0x1801447a0  jz      loc_1801448F7
0x1801447a6  mov     rcx, [rbx+60h]
0x1801447aa  lea     r8, [rbp+57h+var_B0]
0x1801447ae  lea     rdx, aTransporttyper; "TransportTypeReported"
0x1801447b5  mov     rax, [rcx]
0x1801447b8  mov     rax, [rax+20h]
0x1801447bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801447c1  test    eax, eax
0x1801447c3  js      short loc_1801447CF
0x1801447c5  cmp     [rbp+57h+var_B0], 0
0x1801447c9  jnz     loc_1801448F7
0x1801447cf  mov     eax, cs:CallbackContext
0x1801447d5  cmp     eax, 4
0x1801447d8  jbe     short loc_18014480A
0x1801447da  lea     rax, aSettingTranspo; "Setting TransportLinkType"
  ... truncated ...
```
