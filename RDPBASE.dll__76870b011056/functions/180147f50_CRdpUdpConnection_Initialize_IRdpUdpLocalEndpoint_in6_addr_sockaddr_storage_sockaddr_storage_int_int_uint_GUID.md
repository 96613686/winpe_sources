# CRdpUdpConnection::Initialize(IRdpUdpLocalEndpoint *,in6_addr *,sockaddr_storage &,sockaddr_storage &,int,int,uint,_GUID *,ComPlainSmartPtr<IRdpStateTransitionEventLogCallbacks>,ComPlainSmartPtr<IRdpClientStateTransitionEventLogCallbacks>,SecurityCookieHash *,int)

- ea: `0x180147f50`
- end: `0x180148884`
- name: `?Initialize@CRdpUdpConnection@@UEAAJPEAUIRdpUdpLocalEndpoint@@PEAUin6_addr@@AEAUsockaddr_storage@@2HHIPEAU_GUID@@V?$ComPlainSmartPtr@VIRdpStateTransitionEventLogCallbacks@@@@V?$ComPlainSmartPtr@VIRdpClientStateTransitionEventLogCallbacks@@@@PEAUSecurityCookieHash@@H@Z`
- size: `2356`
- prototype: `__int64 __usercall@<rax>(CRdpUdpConnection *this@<rcx>, __int64, int, int, int, __int64, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006ae14`

## callees

- `0x180001aa0`
- `0x1800035d0`
- `0x1800039dc`
- `0x180004b3c`
- `0x180005090`
- `0x180008338`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x180046590`
- `0x18004a014`
- `0x18004c01c`
- `0x18004eb40`
- `0x180078c20`
- `0x180147f50`
- `0x1801489a4`
- `0x1801614b8`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801480cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180148267`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801480cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180148267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801485bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801485bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801485a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801485a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18014856b`
- `OLEAUT32!__imp_SysAllocString` at `0x18014858d`
- `OLEAUT32!__imp_SysAllocString` at `0x18014856b`
- `OLEAUT32!__imp_SysAllocString` at `0x18014858d`

## string_xrefs

- `0x1801485e3`: `Failed to create event`
- `0x18014817a`: `Failed to create the connection UUID`

## pseudocode

```c
__int64 __fastcall CRdpUdpConnection::Initialize(
        CRdpUdpConnection *this,
        __int64 a2,
        const IN6_ADDR *a3,
        SOCKADDR *a4,
        _OWORD *a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        void *a10,
        _QWORD *a11,
        __int64 a12,
        int a13)
{
  _QWORD *v17; // r15
  __int128 v18; // xmm0
  unsigned int v19; // eax
  _OWORD *v20; // r13
  _QWORD *v21; // rdi
  IN6_ADDR v22; // xmm0
  _QWORD *v23; // rsi
  const char *v24; // rsi
  signed int PortFromAddr; // edi
  int ConstrainedGuid; // eax
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  const char *v32; // rax
  __int64 *v33; // rdx
  _DWORD *v34; // r15
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char **v38; // rsi
  const char *v39; // rax
  char *v40; // rdx
  int *v41; // r12
  const char **v42; // r15
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v45; // edx
  int v47; // [rsp+70h] [rbp-89h] BYREF
  int v48; // [rsp+74h] [rbp-85h] BYREF
  const char *v49; // [rsp+78h] [rbp-81h] BYREF
  const char *p_Buf1; // [rsp+80h] [rbp-79h] BYREF
  const char *v51; // [rsp+88h] [rbp-71h] BYREF
  const char *v52; // [rsp+90h] [rbp-69h] BYREF
  const char *v53; // [rsp+98h] [rbp-61h] BYREF
  void *v54; // [rsp+A0h] [rbp-59h]
  GUID v55; // [rsp+B0h] [rbp-49h] BYREF
  const char *v56; // [rsp+C0h] [rbp-39h] BYREF
  const char *v57; // [rsp+C8h] [rbp-31h] BYREF
  void *v58; // [rsp+D0h] [rbp-29h]
  __int128 Buf1; // [rsp+D8h] [rbp-21h] BYREF
  GUID ActivityId; // [rsp+E8h] [rbp-11h] BYREF

  v58 = a11;
  v54 = a10;
  v17 = (_QWORD *)((char *)this + 296);
  v18 = (__int128)*RdpActivityId::GetCurrentActivityId(&v55);
  v19 = CRdpUdpConnection::m_nextConnID + 1;
  *((_DWORD *)this + 80) = CRdpUdpConnection::m_nextConnID;
  CRdpUdpConnection::m_nextConnID = v19;
  Buf1 = v18;
  if ( a2 != *((_QWORD *)this + 37) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 296);
    *v17 = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 296);
  }
  v20 = (_OWORD *)((char *)this + 80);
  if ( !a3 )
    a3 = &in6addr_any;
  v21 = (_QWORD *)((char *)this + 7080);
  v22 = *a3;
  v23 = v54;
  *((IN6_ADDR *)this + 13) = v22;
  *v20 = *a5;
  *((_OWORD *)this + 6) = a5[1];
  *((_OWORD *)this + 7) = a5[2];
  *((_OWORD *)this + 8) = a5[3];
  *((_OWORD *)this + 9) = a5[4];
  *((_OWORD *)this + 10) = a5[5];
  *((_OWORD *)this + 11) = a5[6];
  *((_OWORD *)this + 12) = a5[7];
  if ( *v23 != *((_QWORD *)this + 885) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(v21);
    *v21 = *v23;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 7080);
  }
  if ( *a11 != *((_QWORD *)this + 886) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 7088);
    *((_QWORD *)this + 886) = *a11;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 7088);
  }
  *((_DWORD *)this + 67) = a6;
  *((_DWORD *)this + 104) = a7;
  *((_DWORD *)this + 68) = a8;
  *((_DWORD *)this + 66) = a6 != 0 ? 3 : 1;
  EventActivityIdControl(1u, &ActivityId);
  if ( a12 )
  {
    *(_OWORD *)((char *)this + 7096) = *(_OWORD *)a12;
    *(_OWORD *)((char *)this + 7112) = *(_OWORD *)(a12 + 16);
    *(_OWORD *)((char *)this + 7128) = *(_OWORD *)(a12 + 32);
    *((_DWORD *)this + 1786) = *(_DWORD *)(a12 + 48);
  }
  if ( !a9 || *(_QWORD *)a9 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)(a9 + 8) == *(_QWORD *)GUID_NULL.Data4 )
  {
    v24 = (char *)this + 7048;
    ConstrainedGuid = GenerateConstrainedGuid((GUID *)((char *)this + 7048), 0xF4500000);
    PortFromAddr = ConstrainedGuid;
    if ( ConstrainedGuid < 0 && (unsigned int)CallbackContext > 3 )
    {
      v47 = ConstrainedGuid;
      p_Buf1 = "Initialize";
      v49 = "Failed to create the connection UUID";
      v51 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&dword_1801D6B44,
        v27,
        v28,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v47,
        (__int64)&p_Buf1);
    }
  }
  else
  {
    v24 = (char *)this + 7048;
    PortFromAddr = 0;
    *(_OWORD *)((char *)this + 7048) = *(_OWORD *)a9;
  }
  (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v17 + 136LL))(*v17, (char *)this + 452);
  *((_DWORD *)this + 81) = a4->sa_family;
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) || *(_QWORD *)v24 == (_QWORD)Buf1 && *((_DWORD *)v24 + 2) == DWORD2(Buf1) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v49 = v24;
      p_Buf1 = (const char *)&Buf1;
      v51 = "CRdpUdpConnection::Initialize: Overriding ActivityId by m_ConnectionUUID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        v29,
        (unsigned int)byte_1801D716B,
        v30,
        v31,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&p_Buf1);
    }
    v55 = *(GUID *)v24;
    EventActivityIdControl(2u, &v55);
  }
  if ( !a9 || *(_QWORD *)a9 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)(a9 + 8) == *(_QWORD *)GUID_NULL.Data4 )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_32;
    v32 = "CRdpUdpConnection::Initialize: new-AP";
    v33 = qword_1801D7018;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_32;
    v32 = "CRdpUdpConnection::Initialize: explicit AP.";
    v33 = (__int64 *)&dword_1801D713C;
  }
  v49 = v32;
  p_Buf1 = v24;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
    v29,
    (_DWORD)v33,
    v30,
    v31,
    (__int64)&v49,
    (__int64)&p_Buf1);
LABEL_32:
  v34 = (_DWORD *)((char *)this + 328);
  if ( a13 )
  {
    *v34 = 0;
    v38 = (const char **)((char *)this + 336);
    v41 = (int *)((char *)this + 332);
    *((_QWORD *)this + 42) = SysAllocString(&word_18016FF08);
    *((_DWORD *)this + 83) = 0;
    v42 = (const char **)((char *)this + 344);
    *((_QWORD *)this + 43) = SysAllocString(&word_18016FF08);
  }
  else
  {
    PortFromAddr = RDPENCHLPWS_GetPortFromAddr(a4, 128, (char *)this + 328);
    if ( PortFromAddr < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v47 = 221;
        p_Buf1 = "Failed to get the local port";
        v51 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpconnection.cpp";
        v49 = "Initialize";
        v52 = "Error HResult failed";
        v48 = PortFromAddr;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v35,
          (unsigned int)qword_1801D7278,
          v36,
          v37,
          (__int64)&v52,
          (__int64)&v48,
          (__int64)&v51,
          (__int64)&v47,
          (__int64)&v49,
          (__int64)&p_Buf1);
      }
      v38 = (const char **)((char *)this + 336);
      goto LABEL_57;
    }
    v38 = (const char **)((char *)this + 336);
    PortFromAddr = RDPENCHLPWS_GetIPFromAddr(a4, 128);
    if ( PortFromAddr < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_57:
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v51) = *v34;
          v53 = *v38;
          v48 = *((_DWORD *)this + 83);
          v52 = (const char *)*((_QWORD *)this + 43);
          v47 = *((_DWORD *)this + 80);
          v56 = "Initialize";
          *(_QWORD *)&v55.Data1 = "UDP connection failed to initialize";
          LODWORD(v49) = 277;
          v57 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpconnection.cpp";
          LODWORD(p_Buf1) = PortFromAddr;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)&word_1801D6EE6,
            v36,
            v37,
            (__int64)&v55,
            (__int64)&p_Buf1,
            (__int64)&v57,
            (__int64)&v49,
            (__int64)&v56,
            (__int64)&v47,
            (__int64)&v52,
            (__int64)&v48,
            (__int64)&v53,
            (__int64)&v51);
        }
        v45 = *((_DWORD *)this + 104);
        *((_DWORD *)this + 66) = 0;
        *((_DWORD *)this + 81) = 0;
        *v34 = 0;
        *((_DWORD *)this + 83) = 0;
        CRdpUdpConnection::LogUDPStateTransition(this, v45, v45 != 0 ? 1 : 3, v45 != 0 ? 6 : 8, 8, PortFromAddr);
        goto LABEL_60;
      }
      v39 = "Failed to get the local IP string";
      v48 = 224;
      v40 = byte_1801D690B;
LABEL_40:
      v52 = v39;
      p_Buf1 = "Initialize";
      v51 = "Error HResult failed";
      v47 = PortFromAddr;
      v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpconnection.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (_DWORD)v40,
        v36,
        v37,
        (__int64)&v51,
        (__int64)&v47,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&p_Buf1,
        (__int64)&v52);
      goto LABEL_57;
    }
    v41 = (int *)((char *)this + 332);
    PortFromAddr = RDPENCHLPWS_GetPortFromAddr((char *)this + 80, 128, (char *)this + 332);
    if ( PortFromAddr < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_57;
      v39 = "Failed to get the remote port";
      v48 = 230;
      v40 = &byte_1801D72FF;
      goto LABEL_40;
    }
    v42 = (const char **)((char *)this + 344);
    PortFromAddr = RDPENCHLPWS_GetIPFromAddr((SOCKADDR *)this + 5, 128);
    if ( PortFromAddr < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v48 = 233;
        v52 = "Failed to get the remote IP string";
        v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpconnection.cpp";
        p_Buf1 = "Initialize";
        v51 = "Error HResult failed";
        v47 = PortFromAddr;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v35,
          (unsigned int)&word_1801D771E,
          v36,
          v37,
          (__int64)&v51,
          (__int64)&v47,
          (__int64)&v49,
          (__int64)&v48,
          (__int64)&p_Buf1,
          (__int64)&v52);
      }
LABEL_56:
      v34 = (_DWORD *)((char *)this + 328);
      goto LABEL_57;
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 39) = EventW;
  if ( EventW )
  {
    *((_DWORD *)this + 7) |= 2u;
    *((_QWORD *)this + 28) = v20;
    *((_QWORD *)this + 29) = 128;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v48 = *((_DWORD *)this + 82);
      v52 = *v38;
      v47 = *v41;
      p_Buf1 = *v42;
      LODWORD(v51) = *((_DWORD *)this + 80);
      v53 = "UDP connection initialized";
      v49 = (const char *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)byte_1801D65D5,
        v36,
        v37,
        (__int64)&v53,
        (__int64)&v49,
        (__int64)&v51,
        (__int64)&p_Buf1,
        (__int64)&v47,
        (__int64)&v52,
        (__int64)&v48);
    }
  }
  else
  {
    LastError = GetLastError();
    PortFromAddr = LastError;
    if ( LastError > 0 )
      PortFromAddr = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v48 = 247;
      v52 = "Failed to create event";
      v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpconnection.cpp";
      p_Buf1 = "Initialize";
      v51 = "Error condition failed";
      v47 = PortFromAddr;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)byte_1801D69C9,
        v36,
        v37,
        (__int64)&v51,
        (__int64)&v47,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&p_Buf1,
        (__int64)&v52);
    }
  }
  if ( PortFromAddr < 0 )
    goto LABEL_56;
LABEL_60:
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(v54);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(v58);
  return (unsigned int)PortFromAddr;
}

```

## disassembly

```asm
0x180147f50  mov     [rsp-8+arg_8], rbx
0x180147f55  push    rbp
0x180147f56  push    rsi
0x180147f57  push    rdi
0x180147f58  push    r12
0x180147f5a  push    r13
0x180147f5c  push    r14
0x180147f5e  push    r15
0x180147f60  lea     rbp, [rsp-7]
0x180147f65  sub     rsp, 100h
0x180147f6c  mov     rax, cs:__security_cookie
0x180147f73  xor     rax, rsp
0x180147f76  mov     [rbp+37h+var_38], rax
0x180147f7a  mov     rax, [rbp+37h+arg_48]
0x180147f81  mov     rbx, rcx
0x180147f84  mov     r14, [rbp+37h+arg_50]
0x180147f8b  lea     rcx, [rbp+37h+var_80]; ActivityId
0x180147f8f  mov     [rbp+37h+var_60], r14
0x180147f93  mov     r12, r9
0x180147f96  mov     [rbp+37h+var_90], rax
0x180147f9a  mov     rsi, r8
0x180147f9d  mov     rdi, rdx
0x180147fa0  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x180147fa5  mov     ecx, cs:?m_nextConnID@CRdpUdpConnection@@1IA; uint CRdpUdpConnection::m_nextConnID
0x180147fab  lea     r15, [rbx+128h]
0x180147fb2  movups  xmm0, xmmword ptr [rax]
0x180147fb5  lea     eax, [rcx+1]
0x180147fb8  mov     [rbx+140h], ecx
0x180147fbe  mov     cs:?m_nextConnID@CRdpUdpConnection@@1IA, eax; uint CRdpUdpConnection::m_nextConnID
0x180147fc4  movdqu  [rbp+37h+Buf1], xmm0
0x180147fc9  cmp     rdi, [r15]
0x180147fcc  jz      short loc_180147FE1
0x180147fce  mov     rcx, r15; void *
0x180147fd1  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180147fd6  mov     rcx, r15
0x180147fd9  mov     [r15], rdi
0x180147fdc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180147fe1  lea     r13, [rbx+50h]
0x180147fe5  test    rsi, rsi
0x180147fe8  lea     rax, in6addr_any
0x180147fef  cmovz   rsi, rax
0x180147ff3  lea     rdi, [rbx+1BA8h]
0x180147ffa  mov     rax, [rbp+37h+arg_20]
0x180147ffe  movups  xmm0, xmmword ptr [rsi]
0x180148001  mov     rsi, [rbp+37h+var_90]
0x180148005  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x18014800d  movups  xmm0, xmmword ptr [rax]
0x180148010  movups  xmmword ptr [r13+0], xmm0
0x180148015  movups  xmm1, xmmword ptr [rax+10h]
0x180148019  movups  xmmword ptr [r13+10h], xmm1
0x18014801e  movups  xmm0, xmmword ptr [rax+20h]
0x180148022  movups  xmmword ptr [r13+20h], xmm0
0x180148027  movups  xmm1, xmmword ptr [rax+30h]
0x18014802b  movups  xmmword ptr [r13+30h], xmm1
0x180148030  movups  xmm0, xmmword ptr [rax+40h]
0x180148034  movups  xmmword ptr [r13+40h], xmm0
0x180148039  movups  xmm1, xmmword ptr [rax+50h]
0x18014803d  movups  xmmword ptr [r13+50h], xmm1
0x180148042  movups  xmm0, xmmword ptr [rax+60h]
0x180148046  movups  xmmword ptr [r13+60h], xmm0
0x18014804b  movups  xmm1, xmmword ptr [rax+70h]
0x18014804f  movups  xmmword ptr [r13+70h], xmm1
0x180148054  mov     rax, [rdi]
0x180148057  cmp     [rsi], rax
0x18014805a  jz      short loc_180148072
0x18014805c  mov     rcx, rdi; void *
0x18014805f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180148064  mov     rax, [rsi]
0x180148067  mov     rcx, rdi
0x18014806a  mov     [rdi], rax
0x18014806d  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180148072  lea     rdi, [rbx+1BB0h]
0x180148079  mov     rax, [rdi]
0x18014807c  cmp     [r14], rax
0x18014807f  jz      short loc_180148097
0x180148081  mov     rcx, rdi; void *
0x180148084  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180148089  mov     rax, [r14]
0x18014808c  mov     rcx, rdi
0x18014808f  mov     [rdi], rax
0x180148092  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180148097  mov     edx, [rbp+37h+arg_28]
0x18014809a  mov     eax, edx
0x18014809c  neg     eax
0x18014809e  mov     [rbx+10Ch], edx
0x1801480a4  mov     eax, [rbp+37h+arg_30]
0x1801480a7  lea     rdx, [rbp+37h+ActivityId]; ActivityId
0x1801480ab  sbb     ecx, ecx
0x1801480ad  mov     [rbx+1A0h], eax
0x1801480b3  mov     eax, [rbp+37h+arg_38]
0x1801480b6  and     ecx, 2
0x1801480b9  inc     ecx
0x1801480bb  mov     [rbx+110h], eax
0x1801480c1  mov     [rbx+108h], ecx
0x1801480c7  mov     ecx, 1; ControlCode
0x1801480cc  call    cs:__imp_EventActivityIdControl
0x1801480d2  mov     rax, [rbp+37h+arg_58]
0x1801480d9  test    rax, rax
0x1801480dc  jz      short loc_180148107
0x1801480de  movups  xmm0, xmmword ptr [rax]
0x1801480e1  movups  xmmword ptr [rbx+1BB8h], xmm0
0x1801480e8  movups  xmm1, xmmword ptr [rax+10h]
0x1801480ec  movups  xmmword ptr [rbx+1BC8h], xmm1
0x1801480f3  movups  xmm0, xmmword ptr [rax+20h]
0x1801480f7  movups  xmmword ptr [rbx+1BD8h], xmm0
0x1801480fe  mov     eax, [rax+30h]
0x180148101  mov     [rbx+1BE8h], eax
0x180148107  mov     r14, [rbp+37h+arg_40]
0x18014810e  test    r14, r14
0x180148111  jz      short loc_18014813F
0x180148113  mov     rax, [r14]
0x180148116  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18014811d  jnz     short loc_18014812C
0x18014811f  mov     rax, [r14+8]
0x180148123  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18014812a  jz      short loc_18014813F
0x18014812c  movups  xmm0, xmmword ptr [r14]
0x180148130  lea     rsi, [rbx+1B88h]
0x180148137  xor     edi, edi
0x180148139  movdqu  xmmword ptr [rsi], xmm0
0x18014813d  jmp     short loc_1801481BC
0x18014813f  lea     rsi, [rbx+1B88h]
0x180148146  mov     edx, 0F4500000h; unsigned int
0x18014814b  mov     rcx, rsi; pguid
0x18014814e  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x180148153  mov     edi, eax
0x180148155  test    eax, eax
0x180148157  jns     short loc_1801481BC
0x180148159  mov     ecx, cs:CallbackContext
0x18014815f  cmp     ecx, 3
0x180148162  jbe     short loc_1801481BC
0x180148164  lea     rax, aInitialize; "Initialize"
0x18014816b  mov     [rsp+130h+var_C0], edi
0x18014816f  mov     [rbp+37h+var_B0], rax
0x180148173  lea     rdx, dword_1801D6B44
0x18014817a  lea     rax, aFailedToCreate_25; "Failed to create the connection UUID"
0x180148181  mov     [rsp+130h+var_B8], rax
0x180148186  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18014818d  mov     [rbp+37h+var_A8], rax
0x180148191  lea     rax, [rbp+37h+var_B0]
0x180148195  mov     [rsp+130h+var_F8], rax
0x18014819a  lea     rax, [rsp+130h+var_C0]
0x18014819f  mov     [rsp+130h+var_100], rax
0x1801481a4  lea     rax, [rsp+130h+var_B8]
0x1801481a9  mov     qword ptr [rsp+130h+var_108], rax
0x1801481ae  lea     rax, [rbp+37h+var_A8]
0x1801481b2  mov     qword ptr [rsp+130h+var_110], rax
0x1801481b7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801481bc  mov     rcx, [r15]
0x1801481bf  lea     rdx, [rbx+1C4h]
0x1801481c6  mov     rax, [rcx]
0x1801481c9  mov     rax, [rax+88h]
0x1801481d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801481d5  movzx   eax, word ptr [r12]
0x1801481da  lea     rdx, GUID_NULL; Buf2
0x1801481e1  mov     r8d, 10h; Size
0x1801481e7  mov     [rbx+144h], eax
0x1801481ed  lea     rcx, [rbp+37h+Buf1]; Buf1
0x1801481f1  call    memcmp_0
0x1801481f6  test    eax, eax
0x1801481f8  jz      short loc_18014820B
0x1801481fa  mov     rax, [rsi]
0x1801481fd  cmp     rax, qword ptr [rbp+37h+Buf1]
0x180148201  jnz     short loc_18014826D
0x180148203  mov     eax, [rsi+8]
0x180148206  cmp     eax, dword ptr [rbp+37h+Buf1+8]
0x180148209  jnz     short loc_18014826D
0x18014820b  mov     eax, cs:CallbackContext
0x180148211  cmp     eax, 4
0x180148214  jbe     short loc_180148256
0x180148216  lea     rax, [rbp+37h+Buf1]
0x18014821a  mov     [rsp+130h+var_B8], rsi
0x18014821f  mov     [rbp+37h+var_B0], rax
0x180148223  lea     rdx, byte_1801D716B
0x18014822a  lea     rax, aCrdpudpconnect_12; "CRdpUdpConnection::Initialize: Overridi"...
0x180148231  mov     [rbp+37h+var_A8], rax
0x180148235  lea     rax, [rbp+37h+var_B0]
0x180148239  mov     [rsp+130h+var_100], rax
0x18014823e  lea     rax, [rsp+130h+var_B8]
0x180148243  mov     qword ptr [rsp+130h+var_108], rax
0x180148248  lea     rax, [rbp+37h+var_A8]
0x18014824c  mov     qword ptr [rsp+130h+var_110], rax
0x180148251  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x180148256  movups  xmm0, xmmword ptr [rsi]
0x180148259  lea     rdx, [rbp+37h+var_80]; ActivityId
0x18014825d  mov     ecx, 2; ControlCode
0x180148262  movdqu  xmmword ptr [rbp+37h+var_80.Data1], xmm0
0x180148267  call    cs:__imp_EventActivityIdControl
0x18014826d  test    r14, r14
0x180148270  jz      short loc_1801482A6
0x180148272  mov     rax, [r14]
0x180148275  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18014827c  jnz     short loc_18014828B
0x18014827e  mov     rax, [r14+8]
0x180148282  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180148289  jz      short loc_1801482A6
0x18014828b  mov     eax, cs:CallbackContext
0x180148291  cmp     eax, 4
0x180148294  jbe     short loc_1801482E0
0x180148296  lea     rax, aCrdpudpconnect_6; "CRdpUdpConnection::Initialize: explicit"...
0x18014829d  lea     rdx, dword_1801D713C
0x1801482a4  jmp     short loc_1801482BF
0x1801482a6  mov     eax, cs:CallbackContext
0x1801482ac  cmp     eax, 4
0x1801482af  jbe     short loc_1801482E0
0x1801482b1  lea     rax, aCrdpudpconnect_2; "CRdpUdpConnection::Initialize: new-AP"
0x1801482b8  lea     rdx, qword_1801D7018
0x1801482bf  mov     [rsp+130h+var_B8], rax
0x1801482c4  lea     rax, [rbp+37h+var_B0]
0x1801482c8  mov     qword ptr [rsp+130h+var_108], rax
0x1801482cd  lea     rax, [rsp+130h+var_B8]
0x1801482d2  mov     qword ptr [rsp+130h+var_110], rax
0x1801482d7  mov     [rbp+37h+var_B0], rsi
0x1801482db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x1801482e0  xor     r14d, r14d
0x1801482e3  lea     r15, [rbx+148h]
0x1801482ea  cmp     [rbp+37h+arg_60], r14d
0x1801482f1  jnz     loc_18014855A
0x1801482f7  mov     r8, r15
0x1801482fa  mov     edx, 80h
0x1801482ff  mov     rcx, r12
0x180148302  call    RDPENCHLPWS_GetPortFromAddr
0x180148307  mov     edi, eax
0x180148309  test    eax, eax
0x18014830b  jns     loc_1801483A6
0x180148311  mov     eax, cs:CallbackContext
0x180148317  lea     r14, aOnecoreTermsrv_40; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18014831e  cmp     eax, 2
0x180148321  jbe     short loc_18014839A
0x180148323  lea     rax, aFailedToGetThe_1; "Failed to get the local port"
0x18014832a  mov     [rsp+130h+var_C0], 0DDh
0x180148332  mov     [rbp+37h+var_B0], rax
0x180148336  lea     rdx, qword_1801D7278
0x18014833d  lea     rax, aInitialize; "Initialize"
0x180148344  mov     [rbp+37h+var_A8], r14
0x180148348  mov     [rsp+130h+var_B8], rax
0x18014834d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180148354  mov     [rbp+37h+var_A0], rax
0x180148358  lea     rax, [rbp+37h+var_B0]
0x18014835c  mov     [rsp+130h+var_E8], rax
0x180148361  lea     rax, [rsp+130h+var_B8]
0x180148366  mov     [rsp+130h+var_F0], rax
0x18014836b  lea     rax, [rsp+130h+var_C0]
0x180148370  mov     [rsp+130h+var_F8], rax
0x180148375  lea     rax, [rbp+37h+var_A8]
0x180148379  mov     [rsp+130h+var_100], rax
0x18014837e  lea     rax, [rsp+130h+var_BC]
0x180148383  mov     qword ptr [rsp+130h+var_108], rax
0x180148388  lea     rax, [rbp+37h+var_A0]
0x18014838c  mov     qword ptr [rsp+130h+var_110], rax
0x180148391  mov     [rsp+130h+var_BC], edi
0x180148395  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18014839a  lea     rsi, [rbx+150h]
0x1801483a1  jmp     loc_18014871A
0x1801483a6  lea     rsi, [rbx+150h]
0x1801483ad  mov     edx, 80h; SockaddrLength
0x1801483b2  mov     r8, rsi
0x1801483b5  mov     rcx, r12; pSockaddr
0x1801483b8  call    RDPENCHLPWS_GetIPFromAddr
0x1801483bd  mov     edi, eax
0x1801483bf  test    eax, eax
0x1801483c1  jns     loc_180148459
0x1801483c7  mov     eax, cs:CallbackContext
0x1801483cd  lea     r14, aOnecoreTermsrv_40; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801483d4  cmp     eax, 2
0x1801483d7  jbe     loc_18014871A
0x1801483dd  lea     rax, aFailedToGetThe_20; "Failed to get the local IP string"
0x1801483e4  mov     [rsp+130h+var_BC], 0E0h
0x1801483ec  lea     rdx, byte_1801D690B
0x1801483f3  mov     [rbp+37h+var_A0], rax
0x1801483f7  lea     rax, aInitialize; "Initialize"
0x1801483fe  mov     [rbp+37h+var_B0], rax
0x180148402  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180148409  mov     [rbp+37h+var_A8], rax
0x18014840d  lea     rax, [rbp+37h+var_A0]
0x180148411  mov     [rsp+130h+var_E8], rax
0x180148416  lea     rax, [rbp+37h+var_B0]
0x18014841a  mov     [rsp+130h+var_F0], rax
0x18014841f  lea     rax, [rsp+130h+var_BC]
0x180148424  mov     [rsp+130h+var_F8], rax
0x180148429  lea     rax, [rsp+130h+var_B8]
0x18014842e  mov     [rsp+130h+var_100], rax
0x180148433  lea     rax, [rsp+130h+var_C0]
0x180148438  mov     qword ptr [rsp+130h+var_108], rax
0x18014843d  lea     rax, [rbp+37h+var_A8]
0x180148441  mov     qword ptr [rsp+130h+var_110], rax
0x180148446  mov     [rsp+130h+var_C0], edi
0x18014844a  mov     [rsp+130h+var_B8], r14
0x18014844f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180148454  jmp     loc_18014871A
0x180148459  lea     r12, [rbx+14Ch]
0x180148460  mov     edx, 80h
0x180148465  mov     r8, r12
0x180148468  mov     rcx, r13
0x18014846b  call    RDPENCHLPWS_GetPortFromAddr
0x180148470  mov     edi, eax
0x180148472  test    eax, eax
0x180148474  jns     short loc_1801484A7
0x180148476  mov     eax, cs:CallbackContext
0x18014847c  lea     r14, aOnecoreTermsrv_40; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
  ... truncated ...
```
