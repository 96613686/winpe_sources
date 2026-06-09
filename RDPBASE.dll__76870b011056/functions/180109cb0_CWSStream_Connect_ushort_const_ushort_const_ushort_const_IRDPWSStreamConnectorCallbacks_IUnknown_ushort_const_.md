# CWSStream::Connect(ushort const *,ushort const *,ushort const *,IRDPWSStreamConnectorCallbacks *,IUnknown *,ushort const *,ushort const *)

- ea: `0x180109cb0`
- end: `0x18010af9d`
- name: `?Connect@CWSStream@@UEAAJPEBG00PEAUIRDPWSStreamConnectorCallbacks@@PEAUIUnknown@@00@Z`
- size: `4845`
- prototype: `int(CWSStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IRDPWSStreamConnectorCallbacks *, struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001508`
- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x1800028d8`
- `0x1800034bc`
- `0x180003b24`
- `0x180005090`
- `0x18000552c`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x18002058c`
- `0x18002b248`
- `0x180038984`
- `0x180040750`
- `0x18004a888`
- `0x1800787c8`
- `0x180078814`
- `0x180078c20`
- `0x180088810`
- `0x1800888d8`
- `0x180108d8c`
- `0x180109768`
- `0x180109cb0`
- `0x18010afa4`
- `0x18010ba90`
- `0x18010bb54`
- `0x18010d744`
- `0x18010ff04`
- `0x1801106d4`
- `0x180162010`

## string_xrefs

- `0x180109dbf`: `fullUri is NULL`
- `0x180109ebc`: `StringCchCopy of correlation ID failed`
- `0x18010a1cb`: `RdpX_CreateObject RdpXInterfaceProxyResolver failed to create proxy resolver object. Continuing without supplying a proxy resolver.`
- `0x18010a2e1`: `spUriComponents allocation failed`
- `0x18010a410`: `spUriComponents->GetHostName() failed`
- `0x18010a527`: `spUriComponents->GetHostName(wszHostName) failed`
- `0x18010a635`: `m_pwszReverseConnectGatewayUri allocation failed`
- `0x18010a701`: `StringCchLength of HostPoolArmPath failed`
- `0x18010a679`: `StringCchCopy of wszHostName failed`
- `0x18010a7e4`: `StringCchCopy of wszHostPoolArmPath failed`
- `0x18010a7a1`: `m_pwszHostPoolArmPath allocation failed`
- `0x18010a8e9`: `wszResourcePath allocation failed`
- `0x18010a869`: `spUriComponents->GetUrlPath() failed`
- `0x18010a9a2`: `spUriComponents->GetUrlPath(wszResourcePath) failed`
- `0x18010ab1c`: `pSession->CreateConnection (OUT channel) failed`
- `0x18010aa9f`: `spUriComponents->GetPort() failed`
- `0x18010abd2`: `spUriComponents->GetInternetSchemeType() failed`
- `0x18010ac58`: `spConnection->CreateRequest failed`

## pseudocode

```c
__int64 __fastcall CWSStream::Connect(
        CWSStream *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const char *a4,
        struct IRDPWSStreamConnectorCallbacks *a5,
        struct IUnknown *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8)
{
  _QWORD *v8; // rdi
  int v11; // r8d
  int v12; // r9d
  const struct std::nothrow_t *v13; // rdx
  bool v14; // di
  int v15; // ebx
  unsigned __int16 *v16; // r12
  unsigned __int16 *v17; // r13
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // r11d
  int v22; // r9d
  int v23; // r8d
  const char *v24; // rax
  CWSStream *v25; // r14
  int v26; // ecx
  __int64 v27; // rdx
  CWSStream *v28; // rcx
  const char *v29; // rax
  __int16 *v30; // rdx
  const char *v31; // rax
  unsigned int Object; // eax
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // rdx
  int v38; // ecx
  unsigned __int16 *v39; // rax
  unsigned __int64 v40; // r11
  int v41; // ecx
  const char *v42; // rax
  char *v43; // rdx
  const char *v44; // rax
  int v45; // eax
  const struct std::nothrow_t *v46; // rdx
  unsigned __int64 v47; // rbx
  unsigned __int16 *v48; // rax
  int v49; // eax
  int v50; // r8d
  int v51; // r9d
  const struct std::nothrow_t *v52; // rdx
  unsigned __int64 v53; // rbx
  unsigned __int16 *v54; // rax
  int v55; // eax
  int v56; // r8d
  int v57; // r9d
  int v58; // eax
  unsigned __int16 *v59; // rax
  int v60; // ecx
  __int16 *v61; // rdx
  const char *v62; // rax
  int v63; // eax
  int v64; // r8d
  int v65; // r9d
  int v66; // ecx
  const char *v67; // rax
  char *v68; // rdx
  const char **v69; // rax
  char *v70; // rax
  const wchar_t *v71; // r8
  _QWORD *v72; // rsi
  _QWORD *v73; // rsi
  const struct std::nothrow_t *v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rcx
  int v78; // [rsp+28h] [rbp-D8h]
  const char **v79; // [rsp+30h] [rbp-D0h]
  const char **v80; // [rsp+40h] [rbp-C0h]
  const char **v81; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v82; // [rsp+60h] [rbp-A0h] BYREF
  const char *v83; // [rsp+68h] [rbp-98h] BYREF
  const char *v84; // [rsp+70h] [rbp-90h] BYREF
  const char *v85; // [rsp+78h] [rbp-88h] BYREF
  __int64 v86; // [rsp+80h] [rbp-80h] BYREF
  const char *v87; // [rsp+88h] [rbp-78h] BYREF
  CWSStream *v88; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v89; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v90; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v91; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v92; // [rsp+B0h] [rbp-50h]
  const char *v93; // [rsp+B8h] [rbp-48h] BYREF
  struct RdpXInterfaceHttpSession *v94; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v95; // [rsp+C8h] [rbp-38h] BYREF
  int v96; // [rsp+D0h] [rbp-30h] BYREF
  struct RdpXInterfaceHttpRequest *v97; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v98; // [rsp+E0h] [rbp-20h]
  __int64 v99; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v100; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v101; // [rsp+F8h] [rbp-8h] BYREF
  void *v102; // [rsp+100h] [rbp+0h]
  void *v103; // [rsp+108h] [rbp+8h]
  GUID ActivityId; // [rsp+110h] [rbp+10h] BYREF

  v8 = (_QWORD *)((char *)this + 168);
  v93 = a4;
  v95 = a2;
  v94 = 0;
  v99 = 0;
  v97 = 0;
  v98 = 0;
  v92 = 0;
  v89 = 0;
  v90 = 0;
  v102 = (char *)this + 168;
  if ( a5 != *((struct IRDPWSStreamConnectorCallbacks **)this + 21) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 168);
    *v8 = a5;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(v8);
  }
  v103 = (char *)this + 176;
  if ( a6 != *((struct IUnknown **)this + 22) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 176);
    *((_QWORD *)this + 22) = a6;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 176);
  }
  v88 = (CWSStream *)((char *)this - 8);
  CWSStream::CreateTransitionEventLogCallback((CWSStream *)((char *)this - 8), a7);
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1140));
  v13 = (const struct std::nothrow_t *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
  if ( !a3 )
  {
    v14 = 0;
    v15 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
    {
      v16 = 0;
      v17 = 0;
      goto LABEL_123;
    }
    v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v95 = (unsigned __int16 *)"fullUri is NULL";
    v87 = "Connect";
    v83 = "Error condition failed";
    LODWORD(v86) = 287;
    LODWORD(v82) = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"Connect",
      (unsigned int)&byte_1801CA6C7,
      v11,
      v12,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v84,
      (__int64)&v86,
      (__int64)&v87,
      (__int64)&v95);
    goto LABEL_8;
  }
  CWSStream::LogStateTransition((char *)this - 8, *((unsigned int *)this + 284), 1);
  *((_DWORD *)this + 284) = 1;
  if ( a7 )
  {
    if ( *a7 )
    {
      v21 = StringCchCopyW((unsigned __int16 *)this + 578, 0x28u, a7);
      if ( v21 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v82) = v21;
        v83 = "Connect";
        v87 = "HResult failed but continue";
        v84 = "StringCchCopy of correlation ID failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v18,
          (unsigned int)qword_1801CA718,
          v19,
          v20,
          (__int64)&v87,
          (__int64)&v84,
          (__int64)&v82,
          (__int64)&v83);
      }
    }
  }
  v14 = !IsWindowsVersionOrGreater(v18, 2u, v19);
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
  {
    v84 = (char *)this + 1140;
    v86 = 0x1000000;
    v24 = "RdpNano";
    if ( !v14 )
      v24 = "HttpIo";
    v83 = v24;
    v87 = "WebSocket";
    v82 = (unsigned __int64)"Stack";
    v85 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      (unsigned int)"HttpIo",
      (unsigned int)&byte_1801CA637,
      v23,
      v22,
      (__int64)&v85,
      (__int64)&v86,
      (__int64)&v82,
      (__int64)&v87,
      (__int64)&v84,
      (__int64)&v83);
  }
  if ( v14 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v85 = "WebSocket connecting using nano stack.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)word_1801CA6A2,
        0,
        v22,
        (__int64)&v85);
    }
    v25 = v88;
    v15 = CWSStream::ConnectUsingRdpNanoStack(v88, v95, a3, a7);
    if ( v15 >= 0 || (unsigned int)CallbackContext <= 2 )
    {
      v16 = 0;
      v17 = 0;
      if ( v15 >= 0 )
        goto LABEL_132;
    }
    else
    {
      LODWORD(v82) = 325;
      v85 = "Connect";
      LODWORD(v86) = v15;
      v83 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v84 = "ConnectUsingRdpNanoStack failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)byte_1801CA59D,
        v11,
        v12,
        (__int64)&v84,
        (__int64)&v86,
        (__int64)&v83,
        (__int64)&v82,
        (__int64)&v85);
      v16 = 0;
      v17 = 0;
    }
    v13 = (const struct std::nothrow_t *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    goto LABEL_124;
  }
  v15 = CWSStream::CreateHttpSession((CWSStream *)((char *)this - 8), &v94);
  if ( v15 >= 0 )
  {
    Object = RdpX_CreateObject(v28, v27, 121);
    v33 = MapXResultToHR(Object);
    if ( v33 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v82) = v33;
      v83 = "Connect";
      v85 = (char *)this - 8;
      v84 = "RdpX_CreateObject RdpXInterfaceProxyResolver failed to create proxy resolver object. Continuing without supp"
            "lying a proxy resolver.";
      v87 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v34,
        (unsigned int)&byte_1801CA557,
        v35,
        v36,
        (__int64)&v87,
        (__int64)&v84,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)&v85);
    }
    v15 = (*(__int64 (__fastcall **)(struct RdpXInterfaceHttpSession *, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v94 + 24LL))(
            v94,
            L"MS-RDGateway/1.0",
            v98,
            0);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_34;
      v29 = "spSession->Initialize failed";
      LODWORD(v82) = 353;
      v30 = (__int16 *)byte_1801CA4B5;
      goto LABEL_32;
    }
    v15 = CWSStream::SetSessionTimeouts(v28, v94);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_34;
      v29 = "SetSessionTimeouts failed";
      LODWORD(v82) = 356;
      v30 = &word_1801CA506;
      goto LABEL_32;
    }
    RdpX_CreateObject(v28, v37, 129);
    LODWORD(v28) = v92;
    if ( !v92 )
    {
      v15 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_34;
      LODWORD(v86) = -2147024882;
      v85 = "spUriComponents allocation failed";
      v30 = &word_1801CA40E;
      LODWORD(v82) = 365;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v31 = "Error condition failed";
      goto LABEL_33;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v92 + 24LL))(v92, a3);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v85 = (const char *)a3;
        v83 = "CrackUrl failed";
        LODWORD(v82) = 368;
        v84 = "Connect";
        v87 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v95 = (unsigned __int16 *)"Error HResult failed";
        LODWORD(v86) = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v38,
          (unsigned int)&byte_1801CA45F,
          v11,
          v12,
          (__int64)&v95,
          (__int64)&v86,
          (__int64)&v87,
          (__int64)&v82,
          (__int64)&v84,
          (__int64)&v83,
          (__int64)&v85);
      }
      goto LABEL_34;
    }
    v100 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v92 + 48LL))(v92, 0, &v100);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_34;
      v29 = "spUriComponents->GetHostName() failed";
      LODWORD(v82) = 373;
      v30 = (__int16 *)byte_1801CA3BD;
      goto LABEL_32;
    }
    v39 = (unsigned __int16 *)operator new[](saturated_mul(v100, 2u));
    LOBYTE(v40) = 0;
    v89 = v39;
    if ( !v39 )
    {
      v41 = (int)CallbackContext;
      v15 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_58:
        v16 = v89;
        v14 = v40;
        v17 = v90;
        goto LABEL_9;
      }
      LODWORD(v86) = -2147024882;
      v42 = "wszHostName allocation failed";
      v43 = byte_1801CA31B;
      LODWORD(v82) = 376;
      goto LABEL_56;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v92 + 48LL))(
            v92,
            v39,
            &v100);
    LOBYTE(v40) = 0;
    v15 = v45;
    if ( v45 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_58;
      LODWORD(v82) = 379;
      v85 = "spUriComponents->GetHostName(wszHostName) failed";
      v43 = (char *)&dword_1801CA36C;
      LODWORD(v86) = v45;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v44 = "Error HResult failed";
      goto LABEL_57;
    }
    v82 = 0;
    v15 = StringCchLengthW(v89, 0x7FFFFFFFu, &v82);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_58;
      LODWORD(v82) = 386;
      v85 = "StringCchLength of wszHostName failed";
      v43 = byte_1801CA279;
      LODWORD(v86) = v15;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v44 = "Error HResult failed";
      goto LABEL_57;
    }
    v47 = v82 + 1;
    if ( v82 + 1 >= v82 )
    {
      operator delete(*((void **)this + 155), v46);
      v48 = (unsigned __int16 *)operator new[](saturated_mul(v47, 2u));
      LOBYTE(v40) = 0;
      *((_QWORD *)this + 155) = v48;
      if ( !v48 )
      {
        v15 = -2147024882;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_58;
        LODWORD(v86) = -2147024882;
        v42 = "m_pwszReverseConnectGatewayUri allocation failed";
        v43 = (char *)word_1801CA2CA;
        LODWORD(v82) = 394;
        goto LABEL_56;
      }
      v49 = StringCchCopyW(v48, v47, v89);
      if ( v49 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v82) = v49;
        v85 = "Connect";
        v83 = "StringCchCopy of wszHostName failed";
        v84 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)"Connect",
          (unsigned int)byte_1801CA1E9,
          v50,
          v51,
          (__int64)&v84,
          (__int64)&v83,
          (__int64)&v82,
          (__int64)&v85);
        v40 = 0;
      }
    }
    if ( a8 )
    {
      v82 = v40;
      v15 = StringCchLengthW(a8, 0x7FFFFFFFu, &v82);
      if ( v15 < 0 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_58;
        LODWORD(v82) = 410;
        v85 = "StringCchLength of HostPoolArmPath failed";
        v43 = (char *)qword_1801CA228;
        LODWORD(v86) = v15;
        v83 = "Connect";
        v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v44 = "Error HResult failed";
        goto LABEL_57;
      }
      v53 = v82 + 1;
      if ( v82 + 1 >= v82 )
      {
        operator delete(*((void **)this + 156), v52);
        v54 = (unsigned __int16 *)operator new[](saturated_mul(v53, 2u));
        LOBYTE(v40) = 0;
        *((_QWORD *)this + 156) = v54;
        if ( !v54 )
        {
          v15 = -2147024882;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_58;
          LODWORD(v86) = -2147024882;
          v42 = "m_pwszHostPoolArmPath allocation failed";
          v43 = byte_1801CA159;
          LODWORD(v82) = 418;
LABEL_56:
          v85 = v42;
          v83 = "Connect";
          v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
          v44 = "Error condition failed";
LABEL_57:
          v87 = v44;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v41,
            (_DWORD)v43,
            v11,
            v12,
            (__int64)&v87,
            (__int64)&v86,
            (__int64)&v84,
            (__int64)&v82,
            (__int64)&v83,
            (__int64)&v85);
          LOBYTE(v40) = 0;
          goto LABEL_58;
        }
        v55 = StringCchCopyW(v54, v53, a8);
        if ( v55 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v82) = v55;
          v85 = "Connect";
          v83 = "StringCchCopy of wszHostPoolArmPath failed";
          v84 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)"Connect",
            (unsigned int)word_1801CA1AA,
            v56,
            v57,
            (__int64)&v84,
            (__int64)&v83,
            (__int64)&v82,
            (__int64)&v85);
          v40 = 0;
        }
      }
    }
    v101 = v40;
    v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v92 + 56LL))(v92, 0, &v101);
    LOBYTE(v40) = 0;
    v15 = v58;
    if ( v58 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_58;
      LODWORD(v82) = 431;
      v85 = "spUriComponents->GetUrlPath() failed";
      v43 = &byte_1801CA0B7;
      LODWORD(v86) = v58;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v44 = "Error HResult failed";
      goto LABEL_57;
    }
    v59 = (unsigned __int16 *)operator new[](saturated_mul(v101, 2u));
    v17 = v59;
    if ( !v59 )
    {
      v60 = (int)CallbackContext;
      v15 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_90:
        v16 = v89;
        v14 = 0;
        goto LABEL_9;
      }
      LODWORD(v86) = -2147024882;
      v85 = "wszResourcePath allocation failed";
      v61 = (__int16 *)qword_1801CA108;
      LODWORD(v82) = 434;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v62 = "Error condition failed";
LABEL_89:
      v87 = v62;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v60,
        (_DWORD)v61,
        v11,
        v12,
        (__int64)&v87,
        (__int64)&v86,
        (__int64)&v84,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)&v85);
      goto LABEL_90;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v92 + 56LL))(
            v92,
            v59,
            &v101);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_90;
      LODWORD(v82) = 437;
      v85 = "spUriComponents->GetUrlPath(wszResourcePath) failed";
      v61 = &word_1801CA066;
      LODWORD(v86) = v15;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v62 = "Error HResult failed";
      goto LABEL_89;
    }
    v63 = (*(__int64 (__fastcall **)(struct RdpXInterfaceHttpSession *, const unsigned __int16 *))(*(_QWORD *)v94 + 40LL))(
            v94,
            a3);
    if ( v63 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v82) = v63;
      LODWORD(v86) = v63;
      v85 = "Connect";
      v83 = "pSession->ResolveProxy failed; trying direct connection";
      v84 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"Connect",
        (unsigned int)&word_1801C9FCE,
        v64,
        v65,
        (__int64)&v84,
        (__int64)&v83,
        (__int64)&v86,
        (__int64)&v85,
        (__int64)&v82);
    }
    v91 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v92 + 64LL))(v92, &v91);
    if ( v15 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_90;
      LODWORD(v82) = 447;
      v85 = "spUriComponents->GetPort() failed";
      v61 = (__int16 *)byte_1801CA015;
      LODWORD(v86) = v15;
      v83 = "Connect";
      v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v62 = "Error HResult failed";
      goto LABEL_89;
    }
    v16 = v89;
    v15 = (*(__int64 (__fastcall **)(struct RdpXInterfaceHttpSession *, __int64 *, unsigned __int16 *, _QWORD))(*(_QWORD *)v94 + 48LL))(
            v94,
            &v99,
            v89,
            v91);
    if ( v15 >= 0 )
    {
      v96 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v92 + 32LL))(v92, &v96);
      if ( v15 >= 0 )
      {
        v70 = (char *)this + 8;
        if ( this == (CWSStream *)8 )
          v70 = 0;
        v71 = (const wchar_t *)v93;
        if ( !v93 )
          v71 = L"GET";
        LOBYTE(v78) = v96 == 2;
        v15 = (*(__int64 (__fastcall **)(__int64, struct RdpXInterfaceHttpRequest **, const wchar_t *, unsigned __int16 *, char *, int, __int64))(*(_QWORD *)v99 + 24LL))(
                v99,
                &v97,
                v71,
                v17,
                v70,
                v78,
                -1);
        if ( v15 >= 0 )
        {
          RdpXSPtr<RdpXInterfaceHttpConnection>::operator=((char *)this + 1256, &v94);
          RdpXSPtr<RdpXInterfaceHttpConnection>::operator=((char *)this + 1264, &v99);
          RdpXSPtr<RdpXInterfaceHttpConnection>::operator=((char *)this + 1272, &v97);
          v15 = (*(__int64 (__fastcall **)(struct RdpXInterfaceHttpRequest *))(*(_QWORD *)v97 + 80LL))(v97);
          if ( v15 >= 0 )
          {
            v15 = CWSStream::SendHttpRequest((CWSStream *)((char *)this - 8), v97, v95, a7);
            if ( v15 >= 0 )
              goto LABEL_132;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_105;
            LODWORD(v82) = 487;
            v93 = "SendHttpRequest failed - OUT channel";
            v68 = (char *)qword_1801C9DF0;
            v85 = "Connect";
            v83 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            v84 = "Error HResult failed";
            v81 = &v93;
            v80 = &v85;
            v79 = &v83;
            v69 = &v84;
          }
          else
          {
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_105;
            LODWORD(v82) = 477;
            v93 = "SetCertRevocation failed";
            v68 = byte_1801C9EDB;
            v85 = "Connect";
            v83 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            v84 = "Error HResult failed";
            v81 = &v93;
            v80 = &v85;
            v79 = &v83;
            v69 = &v84;
          }
        }
        else
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_105;
          LODWORD(v82) = 470;
          v93 = "spConnection->CreateRequest failed";
          v68 = (char *)word_1801C9E8A;
          v85 = "Connect";
          v83 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
          v84 = "Error HResult failed";
          v81 = &v93;
          v80 = &v85;
          v79 = &v83;
          v69 = &v84;
        }
        goto LABEL_104;
      }
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_105;
      v67 = "spUriComponents->GetInternetSchemeType() failed";
      LODWORD(v82) = 461;
      v68 = (char *)&dword_1801C9F2C;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_105:
        v14 = 0;
        goto LABEL_9;
      }
      v67 = "pSession->CreateConnection (OUT channel) failed";
      LODWORD(v82) = 457;
      v68 = byte_1801C9F7D;
    }
    v85 = v67;
    v83 = "Connect";
    v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v87 = "Error HResult failed";
    v81 = &v85;
    v80 = &v83;
    v79 = &v84;
    v69 = &v87;
LABEL_104:
    LODWORD(v86) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v66,
      (_DWORD)v68,
      v11,
      v12,
      (__int64)v69,
      (__int64)&v86,
      (__int64)v79,
      (__int64)&v82,
      (__int64)v80,
      (__int64)v81);
    goto LABEL_105;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v29 = "Creating Http session instance failed";
    LODWORD(v82) = 335;
    v30 = &word_1801CA5E6;
LABEL_32:
    v85 = v29;
    v83 = "Connect";
    v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v31 = "Error HResult failed";
    LODWORD(v86) = v15;
LABEL_33:
    v87 = v31;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)v28,
      (_DWORD)v30,
      v11,
      v12,
      (__int64)&v87,
      (__int64)&v86,
      (__int64)&v84,
      (__int64)&v82,
      (__int64)&v83,
      (__int64)&v85);
  }
LABEL_34:
  v14 = 0;
LABEL_8:
  v16 = v89;
  v17 = v89;
LABEL_9:
  v13 = (const struct std::nothrow_t *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
LABEL_123:
  v25 = v88;
LABEL_124:
  if ( (unsigned int)CallbackContext > 2 )
  {
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
    v83 = "Websocket Transport ConnectToServer Failed";
    v93 = "Connect";
    LODWORD(v82) = 493;
    LODWORD(v86) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)"Connect",
      (unsigned int)byte_1801C9E41,
      v11,
      v12,
      (__int64)&v83,
      (__int64)&v86,
      (__int64)&v85,
      (__int64)&v82,
      (__int64)&v93);
  }
  v72 = v102;
  if ( *(_QWORD *)v102 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(v102);
    *v72 = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(v72);
  }
  v73 = v103;
  if ( *(_QWORD *)v103 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(v103);
    *v73 = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(v73);
  }
  if ( !v14 )
    CWSStream::CloseHttpSession(v25, 0, 0);
LABEL_132:
  operator delete(v16, v13);
  operator delete(v17, v74);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  v75 = v92;
  if ( v92 )
  {
    v92 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 8LL))(v75);
  }
  v76 = v98;
  if ( v98 )
  {
    v98 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 8LL))(v76);
  }
  RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v97);
  RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v99);
  RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v94);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180109cb0  push    rbp
0x180109cb2  push    rbx
0x180109cb3  push    rsi
0x180109cb4  push    rdi
0x180109cb5  push    r12
0x180109cb7  push    r13
0x180109cb9  push    r14
0x180109cbb  push    r15
0x180109cbd  lea     rbp, [rsp-38h]
0x180109cc2  sub     rsp, 138h
0x180109cc9  mov     rax, cs:__security_cookie
0x180109cd0  xor     rax, rsp
0x180109cd3  mov     [rbp+70h+var_50], rax
0x180109cd7  mov     rbx, [rbp+70h+arg_20]
0x180109cde  lea     rdi, [rcx+0A8h]
0x180109ce5  mov     r15, [rbp+70h+arg_30]
0x180109cec  xor     eax, eax
0x180109cee  mov     r12, r8
0x180109cf1  mov     r13, [rbp+70h+arg_38]
0x180109cf8  mov     r14, rcx
0x180109cfb  mov     [rbp+70h+var_B8], r9
0x180109cff  mov     [rbp+70h+var_A8], rdx
0x180109d03  mov     [rbp+70h+var_B0], rax
0x180109d07  mov     [rbp+70h+var_88], rax
0x180109d0b  mov     [rbp+70h+var_98], rax
0x180109d0f  mov     [rbp+70h+var_90], rax
0x180109d13  mov     [rbp+70h+var_C0], rax
0x180109d17  mov     [rbp+70h+var_D8], rax
0x180109d1b  mov     [rbp+70h+var_D0], rax
0x180109d1f  mov     [rbp+70h+var_70], rdi
0x180109d23  cmp     rbx, [rdi]
0x180109d26  jz      short loc_180109D3B
0x180109d28  mov     rcx, rdi; void *
0x180109d2b  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180109d30  mov     rcx, rdi
0x180109d33  mov     [rdi], rbx
0x180109d36  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180109d3b  mov     rbx, [rbp+70h+arg_28]
0x180109d42  lea     rdi, [r14+0B0h]
0x180109d49  mov     [rbp+70h+var_68], rdi
0x180109d4d  cmp     rbx, [rdi]
0x180109d50  jz      short loc_180109D65
0x180109d52  mov     rcx, rdi; void *
0x180109d55  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180109d5a  mov     rcx, rdi
0x180109d5d  mov     [rdi], rbx
0x180109d60  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180109d65  lea     rdi, [r14-8]
0x180109d69  mov     rdx, r15; unsigned __int16 *
0x180109d6c  mov     rcx, rdi; this
0x180109d6f  mov     [rbp+70h+var_E0], rdi
0x180109d73  call    ?CreateTransitionEventLogCallback@CWSStream@@AEAAJPEBG@Z; CWSStream::CreateTransitionEventLogCallback(ushort const *)
0x180109d78  lea     rbx, [r14+474h]
0x180109d7f  mov     rdx, rbx; struct _GUID *
0x180109d82  lea     rcx, [rbp+70h+ActivityId]; ActivityId
0x180109d86  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180109d8b  xor     r11d, r11d
0x180109d8e  lea     rcx, aConnect; "Connect"
0x180109d95  lea     rdx, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180109d9c  test    r12, r12
0x180109d9f  jnz     loc_180109E49
0x180109da5  mov     eax, cs:CallbackContext
0x180109dab  lea     esi, [r11+2]
0x180109daf  mov     dil, r11b
0x180109db2  mov     ebx, 80070057h
0x180109db7  cmp     eax, esi
0x180109db9  jbe     loc_18010AE49
0x180109dbf  lea     rax, aFulluriIsNull; "fullUri is NULL"
0x180109dc6  mov     [rsp+170h+var_100], rdx
0x180109dcb  mov     [rbp+70h+var_A8], rax
0x180109dcf  lea     rdx, byte_1801CA6C7
0x180109dd6  lea     rax, aErrorCondition; "Error condition failed"
0x180109ddd  mov     [rbp+70h+var_E8], rcx
0x180109de1  mov     [rsp+170h+var_108], rax
0x180109de6  lea     rax, [rbp+70h+var_A8]
0x180109dea  mov     [rsp+170h+var_128], rax
0x180109def  lea     rax, [rbp+70h+var_E8]
0x180109df3  mov     [rsp+170h+var_130], rax
0x180109df8  lea     rax, [rbp+70h+var_F0]
0x180109dfc  mov     [rsp+170h+var_138], rax
0x180109e01  lea     rax, [rsp+170h+var_100]
0x180109e06  mov     [rsp+170h+var_140], rax
0x180109e0b  lea     rax, [rsp+170h+var_110]
0x180109e10  mov     [rsp+170h+var_148], rax
0x180109e15  lea     rax, [rsp+170h+var_108]
0x180109e1a  mov     [rsp+170h+var_150], rax
0x180109e1f  mov     dword ptr [rbp+70h+var_F0], 11Fh
0x180109e26  mov     dword ptr [rsp+170h+var_110], ebx
0x180109e2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180109e2f  mov     r12, [rbp+70h+var_D8]
0x180109e33  mov     r13, r12
0x180109e36  lea     rcx, aConnect; "Connect"
0x180109e3d  lea     rdx, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180109e44  jmp     loc_18010AE4F
0x180109e49  mov     edx, [r14+470h]
0x180109e50  mov     esi, 1
0x180109e55  mov     r8d, esi
0x180109e58  mov     dword ptr [rsp+170h+var_150], r11d
0x180109e5d  mov     rcx, rdi
0x180109e60  call    ?LogStateTransition@CWSStream@@AEAAXW4RdpWSStreamState@@0W4RdpWSStreamEvent@@J@Z; CWSStream::LogStateTransition(RdpWSStreamState,RdpWSStreamState,RdpWSStreamEvent,long)
0x180109e65  xor     edi, edi
0x180109e67  mov     [r14+470h], esi
0x180109e6e  lea     rsi, aHresultFailedB; "HResult failed but continue"
0x180109e75  test    r15, r15
0x180109e78  jz      short loc_180109EF8
0x180109e7a  cmp     [r15], di
0x180109e7e  jz      short loc_180109EF8
0x180109e80  lea     rcx, [r14+484h]; unsigned __int16 *
0x180109e87  mov     r8, r15; unsigned __int16 *
0x180109e8a  lea     edx, [rdi+28h]; unsigned __int64
0x180109e8d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180109e92  mov     r11d, eax
0x180109e95  test    eax, eax
0x180109e97  jns     short loc_180109EF8
0x180109e99  mov     eax, cs:CallbackContext
0x180109e9f  cmp     eax, 3
0x180109ea2  jbe     short loc_180109EF8
0x180109ea4  lea     rax, aConnect; "Connect"
0x180109eab  mov     dword ptr [rsp+170h+var_110], r11d
0x180109eb0  mov     [rsp+170h+var_108], rax
0x180109eb5  lea     rdx, qword_1801CA718
0x180109ebc  lea     rax, aStringcchcopyO_3; "StringCchCopy of correlation ID failed"
0x180109ec3  mov     [rbp+70h+var_E8], rsi
0x180109ec7  mov     [rsp+170h+var_100], rax
0x180109ecc  lea     rax, [rsp+170h+var_108]
0x180109ed1  mov     [rsp+170h+var_138], rax
0x180109ed6  lea     rax, [rsp+170h+var_110]
0x180109edb  mov     [rsp+170h+var_140], rax
0x180109ee0  lea     rax, [rsp+170h+var_100]
0x180109ee5  mov     [rsp+170h+var_148], rax
0x180109eea  lea     rax, [rbp+70h+var_E8]
0x180109eee  mov     [rsp+170h+var_150], rax
0x180109ef3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180109ef8  mov     esi, 2
0x180109efd  mov     edx, esi; unsigned __int16
0x180109eff  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180109f04  mov     dil, al
0x180109f07  mov     eax, cs:CallbackContext
0x180109f0d  xor     dil, 1
0x180109f11  cmp     eax, 4
0x180109f14  jbe     loc_180109FC8
0x180109f1a  mov     rdx, 470000000000h
0x180109f24  lea     rcx, CallbackContext
0x180109f2b  call    _tlgKeywordOn
0x180109f30  test    al, al
0x180109f32  jz      loc_180109FC8
0x180109f38  test    dil, dil
0x180109f3b  mov     [rsp+170h+var_100], rbx
0x180109f40  lea     rcx, aHttpio; "HttpIo"
0x180109f47  mov     [rbp+70h+var_F0], 1000000h
0x180109f4f  lea     rax, aRdpnano; "RdpNano"
0x180109f56  cmovz   rax, rcx
0x180109f5a  lea     rdx, byte_1801CA637
0x180109f61  mov     [rsp+170h+var_108], rax
0x180109f66  lea     rax, aWebsocket; "WebSocket"
0x180109f6d  mov     [rbp+70h+var_E8], rax
0x180109f71  lea     rax, aStack; "Stack"
0x180109f78  mov     [rsp+170h+var_110], rax
0x180109f7d  lea     rax, aCheckpoint; "Checkpoint"
0x180109f84  mov     [rsp+170h+var_F8], rax
0x180109f89  lea     rax, [rsp+170h+var_108]
0x180109f8e  mov     [rsp+170h+var_128], rax
0x180109f93  lea     rax, [rsp+170h+var_100]
0x180109f98  mov     [rsp+170h+var_130], rax
0x180109f9d  lea     rax, [rbp+70h+var_E8]
0x180109fa1  mov     [rsp+170h+var_138], rax
0x180109fa6  lea     rax, [rsp+170h+var_110]
0x180109fab  mov     [rsp+170h+var_140], rax
0x180109fb0  lea     rax, [rbp+70h+var_F0]
0x180109fb4  mov     [rsp+170h+var_148], rax
0x180109fb9  lea     rax, [rsp+170h+var_F8]
0x180109fbe  mov     [rsp+170h+var_150], rax
0x180109fc3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180109fc8  test    dil, dil
0x180109fcb  jz      loc_18010A0CE
0x180109fd1  mov     eax, cs:CallbackContext
0x180109fd7  cmp     eax, 4
0x180109fda  jbe     short loc_18010A008
0x180109fdc  lea     rax, aWebsocketConne; "WebSocket connecting using nano stack."
0x180109fe3  xor     r8d, r8d
0x180109fe6  mov     [rsp+170h+var_F8], rax
0x180109feb  lea     rdx, word_1801CA6A2
0x180109ff2  lea     rax, [rsp+170h+var_F8]
0x180109ff7  lea     rcx, CallbackContext
0x180109ffe  mov     [rsp+170h+var_150], rax
0x18010a003  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010a008  mov     r14, [rbp+70h+var_E0]
0x18010a00c  mov     r9, r15; unsigned __int16 *
0x18010a00f  mov     rdx, [rbp+70h+var_A8]; unsigned __int16 *
0x18010a013  mov     rcx, r14; this
0x18010a016  mov     r8, r12; unsigned __int16 *
0x18010a019  call    ?ConnectUsingRdpNanoStack@CWSStream@@AEAAJPEBG00@Z; CWSStream::ConnectUsingRdpNanoStack(ushort const *,ushort const *,ushort const *)
0x18010a01e  xor     r11d, r11d
0x18010a021  mov     ebx, eax
0x18010a023  test    eax, eax
0x18010a025  jns     loc_18010A0BE
0x18010a02b  mov     eax, cs:CallbackContext
0x18010a031  cmp     eax, esi
0x18010a033  jbe     loc_18010A0BE
0x18010a039  lea     rax, aConnect; "Connect"
0x18010a040  mov     dword ptr [rsp+170h+var_110], 145h
0x18010a048  mov     [rsp+170h+var_F8], rax
0x18010a04d  lea     rdx, byte_1801CA59D
0x18010a054  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010a05b  mov     dword ptr [rbp+70h+var_F0], ebx
0x18010a05e  mov     [rsp+170h+var_108], rax
0x18010a063  lea     rax, aConnectusingrd_0; "ConnectUsingRdpNanoStack failed."
0x18010a06a  mov     [rsp+170h+var_100], rax
0x18010a06f  lea     rax, [rsp+170h+var_F8]
0x18010a074  mov     [rsp+170h+var_130], rax
0x18010a079  lea     rax, [rsp+170h+var_110]
0x18010a07e  mov     [rsp+170h+var_138], rax
0x18010a083  lea     rax, [rsp+170h+var_108]
0x18010a088  mov     [rsp+170h+var_140], rax
0x18010a08d  lea     rax, [rbp+70h+var_F0]
0x18010a091  mov     [rsp+170h+var_148], rax
0x18010a096  lea     rax, [rsp+170h+var_100]
0x18010a09b  mov     [rsp+170h+var_150], rax
0x18010a0a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010a0a5  xor     r12d, r12d
0x18010a0a8  xor     r13d, r13d
0x18010a0ab  lea     rcx, aConnect; "Connect"
0x18010a0b2  lea     rdx, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010a0b9  jmp     loc_18010AE53
0x18010a0be  mov     r12, r11
0x18010a0c1  mov     r13, r11
0x18010a0c4  test    ebx, ebx
0x18010a0c6  jns     loc_18010AF0D
0x18010a0cc  jmp     short loc_18010A0AB
0x18010a0ce  lea     rdi, [r14-8]
0x18010a0d2  mov     rcx, rdi; this
0x18010a0d5  lea     rdx, [rbp+70h+var_B0]; struct RdpXInterfaceHttpSession **
0x18010a0d9  call    ?CreateHttpSession@CWSStream@@AEAAJPEAPEAURdpXInterfaceHttpSession@@@Z; CWSStream::CreateHttpSession(RdpXInterfaceHttpSession * *)
0x18010a0de  xor     r11d, r11d
0x18010a0e1  mov     ebx, eax
0x18010a0e3  test    eax, eax
0x18010a0e5  jns     loc_18010A184
0x18010a0eb  mov     eax, cs:CallbackContext
0x18010a0f1  cmp     eax, esi
0x18010a0f3  jbe     loc_18010A17C
0x18010a0f9  lea     rax, aCreatingHttpSe; "Creating Http session instance failed"
0x18010a100  mov     dword ptr [rsp+170h+var_110], 14Fh
0x18010a108  lea     rdx, word_1801CA5E6
0x18010a10f  mov     [rsp+170h+var_F8], rax
0x18010a114  lea     rax, aConnect; "Connect"
0x18010a11b  mov     [rsp+170h+var_108], rax
0x18010a120  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010a127  mov     [rsp+170h+var_100], rax
0x18010a12c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010a133  mov     dword ptr [rbp+70h+var_F0], ebx
0x18010a136  mov     [rbp+70h+var_E8], rax
0x18010a13a  lea     rax, [rsp+170h+var_F8]
0x18010a13f  mov     [rsp+170h+var_128], rax
0x18010a144  lea     rax, [rsp+170h+var_108]
0x18010a149  mov     [rsp+170h+var_130], rax
0x18010a14e  lea     rax, [rsp+170h+var_110]
0x18010a153  mov     [rsp+170h+var_138], rax
0x18010a158  lea     rax, [rsp+170h+var_100]
0x18010a15d  mov     [rsp+170h+var_140], rax
0x18010a162  lea     rax, [rbp+70h+var_F0]
0x18010a166  mov     [rsp+170h+var_148], rax
0x18010a16b  lea     rax, [rbp+70h+var_E8]
0x18010a16f  mov     [rsp+170h+var_150], rax
0x18010a174  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010a179  xor     r11d, r11d
0x18010a17c  mov     dil, r11b
0x18010a17f  jmp     loc_180109E2F
0x18010a184  mov     r9d, 9Ch
0x18010a18a  lea     rax, [rbp+70h+var_90]
0x18010a18e  mov     [rsp+170h+var_150], rax
0x18010a193  lea     r8d, [r9-23h]
0x18010a197  call    ?RdpX_CreateObject@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XObjectId32@@W4_XInterfaceId32@@PEAPEAX@Z; RdpX_CreateObject(RdpXInterface *,uint,_XObjectId32,_XInterfaceId32,void * *)
0x18010a19c  mov     ecx, eax
0x18010a19e  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18010a1a3  mov     edx, eax
0x18010a1a5  test    eax, eax
0x18010a1a7  jns     short loc_18010A21D
0x18010a1a9  mov     eax, cs:CallbackContext
0x18010a1af  cmp     eax, 3
0x18010a1b2  jbe     short loc_18010A21D
0x18010a1b4  lea     rax, aConnect; "Connect"
0x18010a1bb  mov     dword ptr [rsp+170h+var_110], edx
0x18010a1bf  mov     [rsp+170h+var_108], rax
0x18010a1c4  lea     rdx, byte_1801CA557
0x18010a1cb  lea     rax, aRdpxCreateobje; "RdpX_CreateObject RdpXInterfaceProxyRes"...
0x18010a1d2  mov     [rsp+170h+var_F8], rdi
0x18010a1d7  mov     [rsp+170h+var_100], rax
0x18010a1dc  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18010a1e3  mov     [rbp+70h+var_E8], rax
0x18010a1e7  lea     rax, [rsp+170h+var_F8]
0x18010a1ec  mov     [rsp+170h+var_130], rax
0x18010a1f1  lea     rax, [rsp+170h+var_108]
0x18010a1f6  mov     [rsp+170h+var_138], rax
0x18010a1fb  lea     rax, [rsp+170h+var_110]
0x18010a200  mov     [rsp+170h+var_140], rax
0x18010a205  lea     rax, [rsp+170h+var_100]
0x18010a20a  mov     [rsp+170h+var_148], rax
0x18010a20f  lea     rax, [rbp+70h+var_E8]
0x18010a213  mov     [rsp+170h+var_150], rax
0x18010a218  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
  ... truncated ...
```
