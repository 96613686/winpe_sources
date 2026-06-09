# CRdpUdpStream::CloseStream(long)

- ea: `0x18011fb90`
- end: `0x180120533`
- name: `?CloseStream@CRdpUdpStream@@QEAAXJ@Z`
- size: `2467`
- prototype: `void(CRdpUdpStream *__hidden this, int)`
- caller_count: `6`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180068e70`
- `0x1800693f0`
- `0x18011fb20`
- `0x180123560`
- `0x1801241a0`
- `0x180124370`

## callees

- `0x1800020cc`
- `0x1800027ec`
- `0x180003000`
- `0x180003158`
- `0x180004a94`
- `0x18000552c`
- `0x180018930`
- `0x180018974`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x18004c01c`
- `0x180068cb0`
- `0x180078c20`
- `0x18011fb90`
- `0x180123300`
- `0x1801233cc`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18011fbde`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18011fbde`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011fc5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011fc5f`

## string_xrefs

- `0x18011fd04`: `UDP closing errorCode replaced`
- `0x18011fdcb`: `UDP Transport closed due to winsock post write incomplete`
- `0x18011fe27`: `UDP Transport closed due to write thread hang`
- `0x18011fe0f`: `Side transport received a network drop on peer leg error - Rendezvous connection was dropped between the gateway and the peer.`
- `0x18011fdb3`: `UDP Transport dummy packet write to winsock failed`
- `0x18011fe1b`: `UDP Transport receives no response from the peer during normal close process, possibly due to the peer already exit at this point`
- `0x18011fe33`: `UDP Transport closed due to transport read thread hang`
- `0x18012007b`: `SMILES channel transport closed due to no direct access`
- `0x18011ff1e`: `SMILES channel transport closed due to HTTP service unavailable`

## pseudocode

```c
void __fastcall CRdpUdpStream::CloseStream(CRdpUdpStream *this, int a2)
{
  GUID v2; // xmm0
  __int64 v3; // rdi
  __int64 v6; // rbx
  int v7; // r12d
  __int64 v8; // r14
  void *v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  const char *v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // r14d
  const char *v18; // r14
  __int128 v19; // xmm0
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  GUID v23; // xmm0
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // eax
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  const char *v31; // [rsp+70h] [rbp-90h] BYREF
  const char *v32; // [rsp+78h] [rbp-88h] BYREF
  GUID *v33; // [rsp+80h] [rbp-80h] BYREF
  const char *v34; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  __int64 v36; // [rsp+98h] [rbp-68h] BYREF
  GUID v37; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-50h] BYREF
  GUID v39; // [rsp+C0h] [rbp-40h] BYREF
  GUID ActivityId; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v41[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v42; // [rsp+110h] [rbp+10h]

  v2 = *(GUID *)((char *)this + 628);
  v3 = 0;
  v36 = 0;
  v6 = 0;
  v35 = 0;
  ActivityId = v2;
  EventActivityIdControl(4u, &ActivityId);
  CTSReaderWriterLock::WriteLock((CRdpUdpStream *)((char *)this + 156));
  v7 = *((_DWORD *)this + 38);
  if ( *((_QWORD *)this + 14) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v36);
    v3 = *((_QWORD *)this + 14);
    v36 = v3;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v36);
  }
  if ( *((_QWORD *)this + 17) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v35);
    v35 = *((_QWORD *)this + 17);
    v6 = v35;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v35);
    v8 = v6;
  }
  else
  {
    v8 = 0;
  }
  if ( v7 )
  {
    v9 = (void *)*((_QWORD *)this + 56);
    *((_DWORD *)this + 38) = 0;
    SetEvent(v9);
  }
  CTSReaderWriterLock::WriteUnlock((CRdpUdpStream *)((char *)this + 156));
  if ( v7 )
  {
    v13 = *((_QWORD *)this + 85);
    v14 = 0;
    if ( v13 )
      *(_QWORD *)(v13 + 32) = 1;
    v15 = *((_QWORD *)this + 55);
    if ( v15 )
    {
      if ( *((_DWORD *)this + 74) )
      {
        v42 = 0;
        memset(v41, 0, sizeof(v41));
        (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v15 + 48LL))(v15, v41);
        v14 = *(const char **)&v41[0];
      }
      (***((void (__fastcall ****)(_QWORD))this + 55))(*((_QWORD *)this + 55));
    }
    v16 = *((_QWORD *)this + 85);
    if ( v16 )
    {
      v17 = *(_DWORD *)(v16 + 36);
      *(_DWORD *)(v16 + 32) = 0;
      if ( v17 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v30) = v17;
          v31 = "UDP closing errorCode replaced";
          LODWORD(v29) = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v15,
            (unsigned int)qword_1801CDB88,
            v11,
            v12,
            (__int64)&v31,
            (__int64)&v29,
            (__int64)&v30);
        }
        a2 = v17;
      }
    }
    if ( a2 > -1950808877 )
    {
      if ( a2 <= -1950798108 )
      {
        if ( a2 == -1950798108 )
        {
          v18 = "SMILES channel transport closed due to internal error";
          goto LABEL_120;
        }
        if ( a2 > -1950800054 )
        {
          switch ( a2 )
          {
            case -1950800052:
              v18 = "SMILES channel transport closed due to WSAE timeout";
              goto LABEL_120;
            case -1950800051:
              v18 = "SMILES channel transport closed due to WSAE connection refused";
              goto LABEL_120;
            case -1950800048:
              v18 = "SMILES channel transport closed due to WSAE host down";
              goto LABEL_120;
            case -1950800047:
              v18 = "SMILES channel transport closed due to WSAE host unreachable";
              goto LABEL_120;
            case -1950798110:
              v18 = "SMILES channel transport closed due to internet timeout";
              goto LABEL_120;
          }
        }
        else
        {
          switch ( a2 )
          {
            case -1950800054:
              v18 = "SMILES channel transport closed due to WSAE shutdown";
              goto LABEL_120;
            case -1950800061:
              v18 = "SMILES channel transport closed due to WSAE network unreachable";
              goto LABEL_120;
            case -1950800060:
              v18 = "SMILES channel transport closed due to WSAE network reset";
              goto LABEL_120;
            case -1950800059:
              v18 = "SMILES channel transport closed due to WSAE connection aborted";
              goto LABEL_120;
            case -1950800058:
              v18 = "SMILES channel transport closed due to WSAE connection reset";
              goto LABEL_120;
            case -1950800055:
              v18 = "SMILES channel transport closed due to WSAE not connected";
              goto LABEL_120;
          }
        }
        goto LABEL_112;
      }
      if ( a2 <= -1950798081 )
      {
        switch ( a2 )
        {
          case -1950798081:
            v18 = "SMILES channel transport closed due to connection reset";
            goto LABEL_120;
          case -1950798107:
            v18 = "SMILES channel transport closed due to invalid URL";
            goto LABEL_120;
          case -1950798096:
            v18 = "SMILES channel transport closed due to invalid operation";
            goto LABEL_120;
          case -1950798095:
            v18 = "SMILES channel transport closed due to operation cancelled";
            goto LABEL_120;
          case -1950798089:
            v18 = "SMILES channel transport closed due to no direct access";
            goto LABEL_120;
          case -1950798082:
            v18 = "SMILES channel transport closed due to connection aborted";
            goto LABEL_120;
        }
        goto LABEL_112;
      }
      if ( a2 == -1950744577 )
      {
        v18 = "SMILES channel transport closed due to an unexpected or unknown error";
        goto LABEL_120;
      }
      if ( a2 == -1950666888 )
      {
        v18 = "SMILES channel transport closed due to WebSocket generic error in Rendezvous transport";
        goto LABEL_120;
      }
      if ( a2 )
      {
        if ( a2 != 196620030 )
          goto LABEL_112;
        v18 = "UDP Transport closed gracefully by peer";
LABEL_114:
        if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
        {
          v32 = v14;
          v19 = (__int128)*RdpActivityId::GetCurrentActivityId(&v39);
          v29 = 0x1000000;
          v34 = (const char *)&v38;
          v33 = (GUID *)"Udp";
          v31 = "Stack";
          v30 = (__int64)"Checkpoint";
          v38 = v19;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
            v20,
            (unsigned int)byte_1801CE9E1,
            v21,
            v22,
            (__int64)&v30,
            (__int64)&v29,
            (__int64)&v31,
            (__int64)&v33,
            (__int64)&v34,
            (__int64)&v32);
        }
        goto LABEL_123;
      }
    }
    else
    {
      if ( a2 == -1950808877 )
      {
        v18 = "SMILES channel transport closed due to request aborted";
        goto LABEL_120;
      }
      if ( a2 > -1950809712 )
      {
        if ( a2 > -1950809611 )
        {
          switch ( a2 )
          {
            case -1950809609:
              v18 = "SMILES channel transport closed due to HTTP service unavailable";
              goto LABEL_120;
            case -1950809608:
              v18 = "SMILES channel transport closed due to HTTP gateway timeout";
              goto LABEL_120;
            case -1950808880:
              v18 = "SMILES channel transport closed due to host unreachable";
              goto LABEL_120;
            case -1950808878:
              v18 = "SMILES channel transport closed due to port unreachable";
              goto LABEL_120;
          }
        }
        else
        {
          switch ( a2 )
          {
            case -1950809611:
              v18 = "SMILES channel transport closed due to HTTP not supported";
              goto LABEL_120;
            case -1950809711:
              v18 = "SMILES channel transport closed due to HTTP denied";
              goto LABEL_120;
            case -1950809709:
              v18 = "SMILES channel transport closed due to HTTP forbidden";
              goto LABEL_120;
            case -1950809708:
              v18 = "SMILES channel transport closed due to HTTP not found";
              goto LABEL_120;
            case -1950809704:
              v18 = "SMILES channel transport closed due to HTTP request timeout";
              goto LABEL_120;
            case -1950809612:
              v18 = "SMILES channel transport closed due to HTTP server error";
              goto LABEL_120;
          }
        }
        goto LABEL_112;
      }
      if ( a2 == -1950809712 )
      {
        v18 = "SMILES channel transport closed due to a bad HTTP request";
        goto LABEL_120;
      }
      if ( a2 > -1950863645 )
      {
        switch ( a2 )
        {
          case -1950863625:
            v18 = "UDP Transport closed due to network drop";
            goto LABEL_120;
          case -1950863623:
            v18 = "UDP Transport closed due to transport read thread hang";
            goto LABEL_120;
          case -1950863601:
            v18 = "UDP Transport closed due to write thread hang";
            goto LABEL_120;
          case -1950863485:
            v18 = "UDP Transport receives no response from the peer during normal close process, possibly due to the peer"
                  " already exit at this point";
            goto LABEL_120;
          case -1950863484:
            v18 = "Side transport received a network drop on peer leg error - Rendezvous connection was dropped between t"
                  "he gateway and the peer.";
            goto LABEL_120;
        }
        goto LABEL_112;
      }
      if ( a2 == -1950863645 )
      {
        v18 = "UDP Transport closed due to network error in winsock";
        goto LABEL_120;
      }
      if ( a2 != -2147467260 )
      {
        switch ( a2 )
        {
          case -1950874652:
            v18 = "UDP Transport closed due to winsock post write incomplete";
            goto LABEL_120;
          case -1950874533:
            v18 = "UDP Transport closed due to TURN server shuting down";
            goto LABEL_120;
          case -1950874478:
            v18 = "UDP Transport dummy packet write to winsock failed";
            goto LABEL_120;
          case -1950863646:
            v18 = "UDP Transport closed due to UDP rate controller timeout";
LABEL_120:
            if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
            {
              v32 = v18;
              v34 = v14;
              v23 = *RdpActivityId::GetCurrentActivityId(&v37);
              v30 = 0x1000000;
              v33 = &v39;
              v31 = "Udp";
              v29 = (__int64)"Stack";
              *(_QWORD *)&v38 = "Checkpoint";
              v39 = v23;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                v24,
                (unsigned int)&byte_1801CE887,
                v25,
                v26,
                (__int64)&v38,
                (__int64)&v30,
                (__int64)&v29,
                (__int64)&v31,
                (__int64)&v33,
                (__int64)&v34,
                (__int64)&v32);
            }
LABEL_123:
            if ( (unsigned int)CallbackContext > 4 )
            {
              LODWORD(v30) = *((_DWORD *)this + 48);
              v32 = "UDP stream closing";
              *(_QWORD *)&v38 = v18;
              LODWORD(v29) = a2;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v15,
                (unsigned int)qword_1801CF588,
                v11,
                v12,
                (__int64)&v32,
                (__int64)&v30,
                (__int64)&v29,
                (__int64)&v38);
            }
            v27 = a2;
            if ( a2 == -2147467260 )
              v27 = 0;
            if ( *((_DWORD *)this + 64) )
              CRdpUdpStream::LogUDPClientStateTransition(this, 6);
            else
              CRdpUdpStream::LogUDPStateTransition(this, 7, 9, 14, v27);
            if ( v6 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
            if ( *((_DWORD *)this + 63) )
            {
              CRdpUdpStream::ProcessDecoupledNetworkNotification((CRdpUdpStream *)((char *)this + 56), 1u, a2, 0);
            }
            else if ( v3 )
            {
              v28 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 40LL))(
                      v3,
                      ((unsigned __int64)this + 56) & -(__int64)(this != 0),
                      1,
                      (unsigned int)a2,
                      0);
              if ( v28 < 0 )
              {
                v10 = (int)CallbackContext;
                if ( (unsigned int)CallbackContext > 3 )
                {
                  LODWORD(v29) = v28;
                  *(_QWORD *)&v38 = "Failed to decouple close event";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    (_DWORD)CallbackContext,
                    (unsigned int)byte_1801CE2D1,
                    v11,
                    v12,
                    (__int64)&v38,
                    (__int64)&v29);
                }
              }
            }
            goto LABEL_140;
        }
LABEL_112:
        v18 = "UDP Transport closed due to an unknown error";
        goto LABEL_120;
      }
    }
    v18 = "UDP Transport closed from the top layers";
    goto LABEL_114;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
LABEL_140:
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v29) = *((_DWORD *)this + 48);
    *(_QWORD *)&v38 = "UDP stream closed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_1801CE11D,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v29);
  }
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v35);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v36);
}

```

## disassembly

```asm
0x18011fb90  mov     [rsp-8+arg_10], rbx
0x18011fb95  push    rbp
0x18011fb96  push    rsi
0x18011fb97  push    rdi
0x18011fb98  push    r12
0x18011fb9a  push    r13
0x18011fb9c  push    r14
0x18011fb9e  push    r15
0x18011fba0  lea     rbp, [rsp-20h]
0x18011fba5  sub     rsp, 120h
0x18011fbac  mov     rax, cs:__security_cookie
0x18011fbb3  xor     rax, rsp
0x18011fbb6  mov     [rbp+50h+var_38], rax
0x18011fbba  movups  xmm0, xmmword ptr [rcx+274h]
0x18011fbc1  xor     edi, edi
0x18011fbc3  mov     esi, edx
0x18011fbc5  mov     r15, rcx
0x18011fbc8  mov     [rbp+50h+var_B8], rdi
0x18011fbcc  xor     ebx, ebx
0x18011fbce  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x18011fbd2  mov     [rbp+50h+var_C0], rbx
0x18011fbd6  lea     ecx, [rdi+4]; ControlCode
0x18011fbd9  movdqu  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x18011fbde  call    cs:__imp_EventActivityIdControl
0x18011fbe4  lea     r13, [r15+9Ch]
0x18011fbeb  mov     rcx, r13; this
0x18011fbee  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x18011fbf3  mov     r12d, [r15+98h]
0x18011fbfa  cmp     [r15+70h], rbx
0x18011fbfe  jz      short loc_18011FC1A
0x18011fc00  lea     rcx, [rbp+50h+var_B8]; void *
0x18011fc04  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18011fc09  mov     rdi, [r15+70h]
0x18011fc0d  lea     rcx, [rbp+50h+var_B8]
0x18011fc11  mov     [rbp+50h+var_B8], rdi
0x18011fc15  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18011fc1a  cmp     [r15+88h], rbx
0x18011fc21  jnz     short loc_18011FC28
0x18011fc23  xor     r14d, r14d
0x18011fc26  jmp     short loc_18011FC48
0x18011fc28  lea     rcx, [rbp+50h+var_C0]; void *
0x18011fc2c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18011fc31  mov     rbx, [r15+88h]
0x18011fc38  lea     rcx, [rbp+50h+var_C0]
0x18011fc3c  mov     [rbp+50h+var_C0], rbx
0x18011fc40  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18011fc45  mov     r14, rbx
0x18011fc48  test    r12d, r12d
0x18011fc4b  jz      short loc_18011FC65
0x18011fc4d  mov     rcx, [r15+1C0h]; hEvent
0x18011fc54  mov     dword ptr [r15+98h], 0
0x18011fc5f  call    cs:__imp_SetEvent
0x18011fc65  mov     rcx, r13; this
0x18011fc68  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18011fc6d  xor     r13d, r13d
0x18011fc70  test    r12d, r12d
0x18011fc73  jz      loc_18012049D
0x18011fc79  mov     rax, [r15+2A8h]
0x18011fc80  mov     r12d, r13d
0x18011fc83  test    rax, rax
0x18011fc86  jz      short loc_18011FC90
0x18011fc88  mov     qword ptr [rax+20h], 1
0x18011fc90  mov     rcx, [r15+1B8h]
0x18011fc97  test    rcx, rcx
0x18011fc9a  jz      short loc_18011FCE0
0x18011fc9c  cmp     [r15+128h], r13d
0x18011fca3  jz      short loc_18011FCCE
0x18011fca5  xorps   xmm0, xmm0
0x18011fca8  lea     rdx, [rbp+50h+var_70]
0x18011fcac  xor     eax, eax
0x18011fcae  mov     [rbp+50h+var_40], rax
0x18011fcb2  movups  [rbp+50h+var_70], xmm0
0x18011fcb6  movups  [rbp+50h+var_60], xmm0
0x18011fcba  movups  [rbp+50h+var_50], xmm0
0x18011fcbe  mov     rax, [rcx]
0x18011fcc1  mov     rax, [rax+30h]
0x18011fcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fcca  mov     r12, qword ptr [rbp+50h+var_70]
0x18011fcce  mov     rcx, [r15+1B8h]
0x18011fcd5  mov     rax, [rcx]
0x18011fcd8  mov     rax, [rax]
0x18011fcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fce0  mov     rax, [r15+2A8h]
0x18011fce7  test    rax, rax
0x18011fcea  jz      short loc_18011FD46
0x18011fcec  mov     r14d, [rax+24h]
0x18011fcf0  mov     [rax+20h], r13d
0x18011fcf4  test    r14d, r14d
0x18011fcf7  jz      short loc_18011FD46
0x18011fcf9  mov     eax, cs:CallbackContext
0x18011fcff  cmp     eax, 4
0x18011fd02  jbe     short loc_18011FD43
0x18011fd04  lea     rax, aUdpClosingErro; "UDP closing errorCode replaced"
0x18011fd0b  mov     dword ptr [rsp+150h+var_E8], r14d
0x18011fd10  mov     [rsp+150h+var_E0], rax
0x18011fd15  lea     rdx, qword_1801CDB88
0x18011fd1c  lea     rax, [rsp+150h+var_E8]
0x18011fd21  mov     dword ptr [rsp+150h+var_F0], esi
0x18011fd25  mov     [rsp+150h+var_120], rax
0x18011fd2a  lea     rax, [rsp+150h+var_F0]
0x18011fd2f  mov     [rsp+150h+var_128], rax
0x18011fd34  lea     rax, [rsp+150h+var_E0]
0x18011fd39  mov     [rsp+150h+var_130], rax
0x18011fd3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18011fd43  mov     esi, r14d
0x18011fd46  mov     eax, 8BB904D3h
0x18011fd4b  cmp     esi, eax
0x18011fd4d  jg      loc_18011FF36
0x18011fd53  jz      loc_18011FF2A
0x18011fd59  mov     eax, 8BB90190h
0x18011fd5e  cmp     esi, eax
0x18011fd60  jg      loc_18011FE57
0x18011fd66  jz      loc_18011FE4B
0x18011fd6c  mov     eax, 8BB82EE3h
0x18011fd71  cmp     esi, eax
0x18011fd73  jg      short loc_18011FDE3
0x18011fd75  jz      short loc_18011FDD7
0x18011fd77  cmp     esi, 80004004h
0x18011fd7d  jz      loc_1801201B4
0x18011fd83  cmp     esi, 8BB803E4h
0x18011fd89  jz      short loc_18011FDCB
0x18011fd8b  cmp     esi, 8BB8045Bh
0x18011fd91  jz      short loc_18011FDBF
0x18011fd93  cmp     esi, 8BB80492h
0x18011fd99  jz      short loc_18011FDB3
0x18011fd9b  cmp     esi, 8BB82EE2h
0x18011fda1  jnz     loc_1801200DF
0x18011fda7  lea     r14, aUdpTransportCl_8; "UDP Transport closed due to UDP rate co"...
0x18011fdae  jmp     loc_18012028A
0x18011fdb3  lea     r14, aUdpTransportDu; "UDP Transport dummy packet write to win"...
0x18011fdba  jmp     loc_18012028A
0x18011fdbf  lea     r14, aUdpTransportCl_5; "UDP Transport closed due to TURN server"...
0x18011fdc6  jmp     loc_18012028A
0x18011fdcb  lea     r14, aUdpTransportCl_2; "UDP Transport closed due to winsock pos"...
0x18011fdd2  jmp     loc_18012028A
0x18011fdd7  lea     r14, aUdpTransportCl_7; "UDP Transport closed due to network err"...
0x18011fdde  jmp     loc_18012028A
0x18011fde3  cmp     esi, 8BB82EF7h
0x18011fde9  jz      short loc_18011FE3F
0x18011fdeb  cmp     esi, 8BB82EF9h
0x18011fdf1  jz      short loc_18011FE33
0x18011fdf3  cmp     esi, 8BB82F0Fh
0x18011fdf9  jz      short loc_18011FE27
0x18011fdfb  cmp     esi, 8BB82F83h
0x18011fe01  jz      short loc_18011FE1B
0x18011fe03  cmp     esi, 8BB82F84h
0x18011fe09  jnz     loc_1801200DF
0x18011fe0f  lea     r14, aSideTransportR; "Side transport received a network drop "...
0x18011fe16  jmp     loc_18012028A
0x18011fe1b  lea     r14, aUdpTransportRe; "UDP Transport receives no response from"...
0x18011fe22  jmp     loc_18012028A
0x18011fe27  lea     r14, aUdpTransportCl_1; "UDP Transport closed due to write threa"...
0x18011fe2e  jmp     loc_18012028A
0x18011fe33  lea     r14, aUdpTransportCl_4; "UDP Transport closed due to transport r"...
0x18011fe3a  jmp     loc_18012028A
0x18011fe3f  lea     r14, aUdpTransportCl; "UDP Transport closed due to network dro"...
0x18011fe46  jmp     loc_18012028A
0x18011fe4b  lea     r14, aSmilesChannelT_12; "SMILES channel transport closed due to "...
0x18011fe52  jmp     loc_18012028A
0x18011fe57  mov     eax, 8BB901F5h
0x18011fe5c  cmp     esi, eax
0x18011fe5e  jg      short loc_18011FED6
0x18011fe60  jz      short loc_18011FECA
0x18011fe62  cmp     esi, 8BB90191h
0x18011fe68  jz      short loc_18011FEBE
0x18011fe6a  cmp     esi, 8BB90193h
0x18011fe70  jz      short loc_18011FEB2
0x18011fe72  cmp     esi, 8BB90194h
0x18011fe78  jz      short loc_18011FEA6
0x18011fe7a  cmp     esi, 8BB90198h
0x18011fe80  jz      short loc_18011FE9A
0x18011fe82  cmp     esi, 8BB901F4h
0x18011fe88  jnz     loc_1801200DF
0x18011fe8e  lea     r14, aSmilesChannelT_21; "SMILES channel transport closed due to "...
0x18011fe95  jmp     loc_18012028A
0x18011fe9a  lea     r14, aSmilesChannelT_15; "SMILES channel transport closed due to "...
0x18011fea1  jmp     loc_18012028A
0x18011fea6  lea     r14, aSmilesChannelT_16; "SMILES channel transport closed due to "...
0x18011fead  jmp     loc_18012028A
0x18011feb2  lea     r14, aSmilesChannelT_29; "SMILES channel transport closed due to "...
0x18011feb9  jmp     loc_18012028A
0x18011febe  lea     r14, aSmilesChannelT_7; "SMILES channel transport closed due to "...
0x18011fec5  jmp     loc_18012028A
0x18011feca  lea     r14, aSmilesChannelT_25; "SMILES channel transport closed due to "...
0x18011fed1  jmp     loc_18012028A
0x18011fed6  cmp     esi, 8BB901F7h
0x18011fedc  jz      short loc_18011FF1E
0x18011fede  cmp     esi, 8BB901F8h
0x18011fee4  jz      short loc_18011FF12
0x18011fee6  cmp     esi, 8BB904D0h
0x18011feec  jz      short loc_18011FF06
0x18011feee  cmp     esi, 8BB904D2h
0x18011fef4  jnz     loc_1801200DF
0x18011fefa  lea     r14, aSmilesChannelT_1; "SMILES channel transport closed due to "...
0x18011ff01  jmp     loc_18012028A
0x18011ff06  lea     r14, aSmilesChannelT_8; "SMILES channel transport closed due to "...
0x18011ff0d  jmp     loc_18012028A
0x18011ff12  lea     r14, aSmilesChannelT_10; "SMILES channel transport closed due to "...
0x18011ff19  jmp     loc_18012028A
0x18011ff1e  lea     r14, aSmilesChannelT_5; "SMILES channel transport closed due to "...
0x18011ff25  jmp     loc_18012028A
0x18011ff2a  lea     r14, aSmilesChannelT_24; "SMILES channel transport closed due to "...
0x18011ff31  jmp     loc_18012028A
0x18011ff36  mov     eax, 8BB92EE4h
0x18011ff3b  cmp     esi, eax
0x18011ff3d  jg      loc_18012003C
0x18011ff43  jz      loc_180120030
0x18011ff49  mov     eax, 8BB9274Ah
0x18011ff4e  cmp     esi, eax
0x18011ff50  jg      short loc_18011FFC8
0x18011ff52  jz      short loc_18011FFBC
0x18011ff54  cmp     esi, 8BB92743h
0x18011ff5a  jz      short loc_18011FFB0
0x18011ff5c  cmp     esi, 8BB92744h
0x18011ff62  jz      short loc_18011FFA4
0x18011ff64  cmp     esi, 8BB92745h
0x18011ff6a  jz      short loc_18011FF98
0x18011ff6c  cmp     esi, 8BB92746h
0x18011ff72  jz      short loc_18011FF8C
0x18011ff74  cmp     esi, 8BB92749h
0x18011ff7a  jnz     loc_1801200DF
0x18011ff80  lea     r14, aSmilesChannelT_28; "SMILES channel transport closed due to "...
0x18011ff87  jmp     loc_18012028A
0x18011ff8c  lea     r14, aSmilesChannelT_14; "SMILES channel transport closed due to "...
0x18011ff93  jmp     loc_18012028A
0x18011ff98  lea     r14, aSmilesChannelT_2; "SMILES channel transport closed due to "...
0x18011ff9f  jmp     loc_18012028A
0x18011ffa4  lea     r14, aSmilesChannelT_13; "SMILES channel transport closed due to "...
0x18011ffab  jmp     loc_18012028A
0x18011ffb0  lea     r14, aSmilesChannelT_30; "SMILES channel transport closed due to "...
0x18011ffb7  jmp     loc_18012028A
0x18011ffbc  lea     r14, aSmilesChannelT_9; "SMILES channel transport closed due to "...
0x18011ffc3  jmp     loc_18012028A
0x18011ffc8  cmp     esi, 8BB9274Ch
0x18011ffce  jz      short loc_180120024
0x18011ffd0  cmp     esi, 8BB9274Dh
0x18011ffd6  jz      short loc_180120018
0x18011ffd8  cmp     esi, 8BB92750h
0x18011ffde  jz      short loc_18012000C
0x18011ffe0  cmp     esi, 8BB92751h
0x18011ffe6  jz      short loc_180120000
0x18011ffe8  cmp     esi, 8BB92EE2h
0x18011ffee  jnz     loc_1801200DF
0x18011fff4  lea     r14, aSmilesChannelT_17; "SMILES channel transport closed due to "...
0x18011fffb  jmp     loc_18012028A
0x180120000  lea     r14, aSmilesChannelT_23; "SMILES channel transport closed due to "...
0x180120007  jmp     loc_18012028A
0x18012000c  lea     r14, aSmilesChannelT_26; "SMILES channel transport closed due to "...
0x180120013  jmp     loc_18012028A
0x180120018  lea     r14, aSmilesChannelT_18; "SMILES channel transport closed due to "...
0x18012001f  jmp     loc_18012028A
0x180120024  lea     r14, aSmilesChannelT_19; "SMILES channel transport closed due to "...
0x18012002b  jmp     loc_18012028A
0x180120030  lea     r14, aSmilesChannelT; "SMILES channel transport closed due to "...
0x180120037  jmp     loc_18012028A
0x18012003c  mov     eax, 8BB92EFFh
0x180120041  cmp     esi, eax
0x180120043  jg      short loc_1801200B7
0x180120045  jz      short loc_1801200AB
0x180120047  cmp     esi, 8BB92EE5h
0x18012004d  jz      short loc_18012009F
0x18012004f  cmp     esi, 8BB92EF0h
0x180120055  jz      short loc_180120093
0x180120057  cmp     esi, 8BB92EF1h
0x18012005d  jz      short loc_180120087
0x18012005f  cmp     esi, 8BB92EF7h
0x180120065  jz      short loc_18012007B
0x180120067  cmp     esi, 8BB92EFEh
0x18012006d  jnz     short loc_1801200DF
0x18012006f  lea     r14, aSmilesChannelT_0; "SMILES channel transport closed due to "...
0x180120076  jmp     loc_18012028A
0x18012007b  lea     r14, aSmilesChannelT_27; "SMILES channel transport closed due to "...
0x180120082  jmp     loc_18012028A
0x180120087  lea     r14, aSmilesChannelT_3; "SMILES channel transport closed due to "...
0x18012008e  jmp     loc_18012028A
0x180120093  lea     r14, aSmilesChannelT_20; "SMILES channel transport closed due to "...
0x18012009a  jmp     loc_18012028A
0x18012009f  lea     r14, aSmilesChannelT_6; "SMILES channel transport closed due to "...
0x1801200a6  jmp     loc_18012028A
0x1801200ab  lea     r14, aSmilesChannelT_22; "SMILES channel transport closed due to "...
0x1801200b2  jmp     loc_18012028A
0x1801200b7  cmp     esi, 8BB9FFFFh
0x1801200bd  jz      loc_180120283
0x1801200c3  cmp     esi, 8BBB2F78h
0x1801200c9  jz      loc_18012027A
0x1801200cf  test    esi, esi
0x1801200d1  jz      loc_1801201B4
0x1801200d7  cmp     esi, 0BB82EFEh
0x1801200dd  jz      short loc_1801200EB
0x1801200df  lea     r14, aUdpTransportCl_3; "UDP Transport closed due to an unknown "...
0x1801200e6  jmp     loc_18012028A
0x1801200eb  lea     r14, aUdpTransportCl_0; "UDP Transport closed gracefully by peer"
0x1801200f2  mov     eax, cs:CallbackContext
0x1801200f8  cmp     eax, 4
0x1801200fb  jbe     loc_180120354
0x180120101  mov     rdx, 470000000000h
0x18012010b  lea     rcx, CallbackContext
0x180120112  call    _tlgKeywordOn
0x180120117  test    al, al
0x180120119  jz      loc_180120354
  ... truncated ...
```
