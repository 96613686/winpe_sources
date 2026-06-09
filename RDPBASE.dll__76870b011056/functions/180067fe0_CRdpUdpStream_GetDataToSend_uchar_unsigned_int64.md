# CRdpUdpStream::GetDataToSend(uchar * *,unsigned __int64 *)

- ea: `0x180067fe0`
- end: `0x180068b1c`
- name: `?GetDataToSend@CRdpUdpStream@@UEAAJPEAPEAEPEA_K@Z`
- size: `2876`
- prototype: `__int64 __fastcall(CRdpUdpStream *__hidden this, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update`

## callees

- `0x180001aa0`
- `0x180002c8c`
- `0x180004714`
- `0x180004848`
- `0x180004970`
- `0x180018660`
- `0x18002edec`
- `0x1800302bc`
- `0x180031a38`
- `0x180036690`
- `0x1800367c0`
- `0x180036900`
- `0x180036b30`
- `0x180036bec`
- `0x180048bb0`
- `0x18004a090`
- `0x18004a584`
- `0x180051118`
- `0x180067fe0`
- `0x18006ea00`
- `0x180078c20`
- `0x180124f00`
- `0x180142550`
- `0x1801435a8`
- `0x1801446a0`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180068120`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180068241`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180068120`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180068241`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800689bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800689bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068067`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068067`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068aea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068aea`
- `WS2_32!__imp_htonl` at `0x180068636`
- `WS2_32!__imp_htonl` at `0x18006864c`
- `WS2_32!__imp_htonl` at `0x1800687c6`
- `WS2_32!__imp_htonl` at `0x1800687d3`
- `WS2_32!__imp_htonl` at `0x1800687f4`
- `WS2_32!__imp_htonl` at `0x180068801`
- `WS2_32!__imp_htonl` at `0x180068636`
- `WS2_32!__imp_htonl` at `0x18006864c`
- `WS2_32!__imp_htonl` at `0x1800687c6`
- `WS2_32!__imp_htonl` at `0x1800687d3`
- `WS2_32!__imp_htonl` at `0x1800687f4`
- `WS2_32!__imp_htonl` at `0x180068801`
- `WS2_32!__imp_htons` at `0x18006865a`
- `WS2_32!__imp_htons` at `0x1800687a2`
- `WS2_32!__imp_htons` at `0x18006865a`
- `WS2_32!__imp_htons` at `0x1800687a2`

## pseudocode

```c
__int64 __fastcall CRdpUdpStream::GetDataToSend(CRdpUdpStream *this, unsigned __int8 **a2, unsigned __int64 *a3)
{
  __int64 v3; // r12
  unsigned __int64 v6; // r15
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  int v8; // r14d
  int v9; // eax
  int HaveDataToSend; // ebx
  __int64 v11; // rcx
  unsigned int v12; // eax
  int v13; // r8d
  int v14; // r9d
  unsigned __int8 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned __int8 **v21; // rcx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // edx
  CFecDecoder *v26; // rcx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rbx
  u_long v31; // r13d
  __int64 v32; // rsi
  unsigned int v33; // edx
  int AckVectorFeedback; // eax
  unsigned __int16 v35; // bx
  u_long v36; // eax
  u_short v37; // cx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  u_long v41; // r14d
  int v42; // r8d
  int v43; // r9d
  _DWORD *v44; // rcx
  DWORD TickCount; // esi
  int v46; // eax
  CFecEncoder *v47; // rcx
  struct _RTL_CRITICAL_SECTION *v48; // rcx
  unsigned int v50; // [rsp+40h] [rbp-C0h]
  u_long v51[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v52[4]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v53; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v54[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v55; // [rsp+88h] [rbp-78h] BYREF
  u_long v56; // [rsp+8Ch] [rbp-74h] BYREF
  u_long v57; // [rsp+90h] [rbp-70h] BYREF
  u_long hostlong[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int8 **v59; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v60; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v61[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v62; // [rsp+B8h] [rbp-48h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR v64; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v65; // [rsp+E0h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-10h] BYREF
  char *v67; // [rsp+100h] [rbp+0h]
  int v68; // [rsp+108h] [rbp+8h]
  int v69; // [rsp+10Ch] [rbp+Ch]
  const char *v70; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  struct _EVENT_DATA_DESCRIPTOR v72; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v73; // [rsp+130h] [rbp+30h]
  int v74; // [rsp+138h] [rbp+38h]
  int v75; // [rsp+13Ch] [rbp+3Ch]
  const char *v76; // [rsp+140h] [rbp+40h]
  __int64 v77; // [rsp+148h] [rbp+48h]
  u_long *v78; // [rsp+150h] [rbp+50h]
  __int64 v79; // [rsp+158h] [rbp+58h]
  const char *v80; // [rsp+160h] [rbp+60h]
  __int64 v81; // [rsp+168h] [rbp+68h]
  unsigned int *v82; // [rsp+170h] [rbp+70h]
  __int64 v83; // [rsp+178h] [rbp+78h]
  const char *v84; // [rsp+180h] [rbp+80h]
  __int64 v85; // [rsp+188h] [rbp+88h]
  const char *v86; // [rsp+190h] [rbp+90h]
  __int64 v87; // [rsp+198h] [rbp+98h]

  v3 = *((_QWORD *)this + 68);
  *(_QWORD *)&v64.Id = a3;
  v59 = a2;
  v6 = 0;
  v62 = 0;
  v57 = 0;
  v56 = 0;
  v60 = 0;
  v52[0] = 0;
  LOWORD(v53) = 0;
  hostlong[0] = 0;
  v51[0] = 0;
  LOWORD(v55) = 0;
  v61[0] = 0;
  if ( *((_DWORD *)this + 6) )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      EnterCriticalSection(v7);
      a2 = v59;
    }
  }
  *a2 = 0;
  *a3 = 0;
  v8 = 1;
  if ( (unsigned int)CallbackContext > 5 )
  {
    EventDescriptor.Keyword = 0;
    v70 = "CRdpUdpStream::GetDataToSend called";
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_1801E7010;
    v71 = 36;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_1801E7010;
    v67 = byte_1801CF345;
    UserData.Reserved = 2;
    v68 = 19;
    v69 = 1;
    v54[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v9 = CRdpUdpStream::OnTransportTimer(this);
  HaveDataToSend = v9;
  if ( v9 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v51[0] = v9;
      v54[0] = 2804;
      v86 = "OnTimer failed";
      v87 = 15;
      v84 = "GetDataToSend";
      v85 = 14;
      v82 = v54;
      v80 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      v78 = v51;
      v76 = "Error HResult failed";
      *(_DWORD *)&v64.Level = 2;
      v72.Ptr = (ULONGLONG)off_1801E7010;
      v83 = 4;
      v81 = 76;
      v79 = 4;
      v77 = 21;
      *(_DWORD *)&v64.Id = 184549376;
      v64.Keyword = 0;
      v72.Size = *(unsigned __int16 *)off_1801E7010;
      v73 = qword_1801CF8B0;
      v72.Reserved = 2;
      v74 = 63;
      v75 = 1;
      *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v64, 0, 0, 8u, &v72);
    }
    goto LABEL_56;
  }
  v11 = *((_QWORD *)this + 33);
  if ( v11 )
  {
    *(_QWORD *)v54 = 0;
    *(_QWORD *)v51 = 0;
    v12 = CUDPRateController::OnBufferAvailable(v11, v54, v51);
    if ( v12 )
    {
      HaveDataToSend = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v54[0] = v12;
        v51[0] = *((_DWORD *)this + 30);
        v62 = (unsigned __int64)"GetDataToSend";
        v59 = (unsigned __int8 **)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
        *(_QWORD *)v61 = "UDP Stream: RateController returned error OnBufferAvailable";
        *(_DWORD *)&EventDescriptor.Id = 2817;
        hostlong[0] = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)&word_1801CEE06,
          v13,
          v14,
          (__int64)v61,
          (__int64)hostlong,
          (__int64)&v59,
          (__int64)&EventDescriptor,
          (__int64)&v62,
          (__int64)v51,
          (__int64)v54);
      }
      goto LABEL_56;
    }
    v15 = *(unsigned __int8 **)v54;
    if ( *(_QWORD *)v54 && *(_QWORD *)v51 )
    {
      *a3 = *(_QWORD *)v51;
      HaveDataToSend = 0;
      *v59 = v15;
      goto LABEL_56;
    }
LABEL_29:
    HaveDataToSend = 1;
    goto LABEL_56;
  }
  v16 = *((_QWORD *)this + 46);
  if ( v16 )
  {
    v17 = *((_QWORD *)this + 68);
    *(_QWORD *)hostlong = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, u_long *))(*(_QWORD *)v16 + 16LL))(v16, v17, hostlong) )
    {
      HaveDataToSend = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v54[0] = *((_DWORD *)this + 30);
        v62 = (unsigned __int64)"GetDataToSend";
        v59 = (unsigned __int8 **)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
        *(_QWORD *)v61 = "UDP Stream: UDPNanoWrapper returned error OnBufferAvailable";
        v51[0] = 2841;
        *(_DWORD *)&EventDescriptor.Id = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v18,
          (unsigned int)&word_1801CE16E,
          v19,
          v20,
          (__int64)v61,
          (__int64)&EventDescriptor,
          (__int64)&v59,
          (__int64)v51,
          (__int64)&v62,
          (__int64)v54);
        RdpUdpETWEvents::OutgoingPacketProcessed(*((RdpUdpETWEvents **)this + 13));
        goto LABEL_56;
      }
    }
    else
    {
      if ( !*(_QWORD *)hostlong )
      {
        HaveDataToSend = 1;
        RdpUdpETWEvents::OutgoingPacketProcessed(*((RdpUdpETWEvents **)this + 13));
        goto LABEL_56;
      }
      v21 = v59;
      HaveDataToSend = 0;
      *a3 = *(_QWORD *)hostlong;
      *v21 = (unsigned __int8 *)*((_QWORD *)this + 68);
    }
    RdpUdpETWEvents::OutgoingPacketProcessed(*((RdpUdpETWEvents **)this + 13));
    goto LABEL_56;
  }
  HaveDataToSend = CFecEncoder::HaveDataToSend(*((CFecEncoder **)this + 30), &v56, &v60, (int *)v61);
  if ( HaveDataToSend < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v54[0] = 2860;
      v62 = (unsigned __int64)"FecEncoder in error, need to disconnect";
      v51[0] = HaveDataToSend;
      v59 = (unsigned __int8 **)"GetDataToSend";
      *(_QWORD *)&EventDescriptor.Id = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      *(_QWORD *)hostlong = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v22,
        (unsigned int)qword_1801CECE8,
        v23,
        v24,
        (__int64)hostlong,
        (__int64)v51,
        (__int64)&EventDescriptor,
        (__int64)v54,
        (__int64)&v59,
        (__int64)&v62);
    }
    goto LABEL_56;
  }
  if ( !v61[0] && !(unsigned int)CFecDecoder::HasNewFeedback(*((CFecDecoder **)this + 31)) )
    goto LABEL_29;
  v25 = *((_DWORD *)this + 42);
  v26 = (CFecDecoder *)*((_QWORD *)this + 31);
  *(_DWORD *)&EventDescriptor.Id = 0;
  HaveDataToSend = CFecDecoder::GetAckVector(
                     v26,
                     v25 + 2042,
                     (unsigned __int8 *)(v3 + 8),
                     (unsigned int *)&EventDescriptor.Id,
                     v51,
                     (unsigned __int16 *)&v55,
                     (unsigned __int16 *)&v53);
  if ( HaveDataToSend < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v54[0] = 2883;
      v62 = (unsigned __int64)"Get Ack Vector failed";
      v51[0] = HaveDataToSend;
      v59 = (unsigned __int8 **)"GetDataToSend";
      *(_QWORD *)&EventDescriptor.Id = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      *(_QWORD *)hostlong = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v27,
        (unsigned int)&byte_1801CDC1F,
        v28,
        v29,
        (__int64)hostlong,
        (__int64)v51,
        (__int64)&EventDescriptor,
        (__int64)v54,
        (__int64)&v59,
        (__int64)&v62);
    }
    goto LABEL_56;
  }
  v30 = *(unsigned int *)&EventDescriptor.Id;
  v31 = v51[0];
  RdpUdpETWEvents::OnAckVectSend(
    *((RdpUdpETWEvents **)this + 13),
    v51[0],
    (unsigned __int8 *)(v3 + 8),
    *(unsigned int *)&EventDescriptor.Id);
  v32 = v30 + 8;
  AckVectorFeedback = CFecEncoder::GetAckVectorFeedback(*((CFecEncoder **)this + 30), v33, hostlong);
  v35 = v53;
  if ( AckVectorFeedback )
  {
    v8 = 0;
  }
  else
  {
    v35 = v53 | 0x100;
    LOWORD(v53) = v53 | 0x100;
    *(_DWORD *)(v32 + v3) = htonl(hostlong[0]);
    v32 += 4;
  }
  v36 = htonl(v31);
  v37 = v55;
  *(_DWORD *)v3 = v36;
  *(_WORD *)(v3 + 4) = htons(v37);
  if ( v61[0] )
  {
    HaveDataToSend = CFecEncoder::PullCodedPacket(
                       *((CFecEncoder **)this + 30),
                       (unsigned __int8 *)(v3 + v32),
                       &v62,
                       &v56,
                       &v60,
                       &v57,
                       v52,
                       (unsigned __int16 *)&v53);
    if ( HaveDataToSend < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v54[0] = 2923;
        v62 = (unsigned __int64)"PullCodedPacket failed";
        v51[0] = HaveDataToSend;
        v59 = (unsigned __int8 **)"GetDataToSend";
        *(_QWORD *)&EventDescriptor.Id = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
        *(_QWORD *)hostlong = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v38,
          (unsigned int)&dword_1801CE594,
          v39,
          v40,
          (__int64)hostlong,
          (__int64)v51,
          (__int64)&EventDescriptor,
          (__int64)v54,
          (__int64)&v59,
          (__int64)&v62);
      }
      goto LABEL_56;
    }
    v6 = v62;
    v35 = v53;
  }
  RdpUdpETWEvents::OnAckSent(*((RdpUdpETWEvents **)this + 13), v31, (unsigned __int16)v55, v35);
  CFecDecoder::SentFeedback(*((CFecDecoder **)this + 31));
  if ( v8 )
    CFecEncoder::SentAckVectorFeedback(*((CFecEncoder **)this + 30), hostlong[0]);
  if ( v6 )
  {
    v35 |= 8u;
    if ( v56 != v60 )
      v35 |= 0x10u;
  }
  *(_WORD *)(v3 + 6) = htons(v35);
  if ( v6 )
  {
    v41 = v57;
    if ( v56 == v60 )
    {
      *(_DWORD *)(v3 + v32) = htonl(v57);
      *(_DWORD *)(v3 + v32 + 4) = htonl(v56);
      v32 += 8;
      RdpUdpETWEvents::OnSrcPacketSent(*((RdpUdpETWEvents **)this + 13), v56, v32 + v6);
    }
    else
    {
      *(_DWORD *)(v3 + v32) = htonl(v57);
      *(_DWORD *)(v3 + v32 + 4) = htonl(v56);
      *(_BYTE *)(v3 + v32 + 8) = v60 - v56;
      *(_BYTE *)(v3 + v32 + 9) = v52[0];
      v32 += 12;
      RdpUdpETWEvents::OnFecPacketSent(*((RdpUdpETWEvents **)this + 13), v41, v32 + v6, v56, v60 - v56);
    }
  }
  else
  {
    RdpUdpETWEvents::OnAckPktSent(*((RdpUdpETWEvents **)this + 13), v31, v32);
    v41 = v57;
  }
  HaveDataToSend = 0;
  *v59 = (unsigned __int8 *)*((_QWORD *)this + 68);
  v44 = *(_DWORD **)&v64.Id;
  **(_QWORD **)&v64.Id = v6 + v32;
  if ( v6 )
  {
    if ( (unsigned int)CallbackContext > 5 )
    {
      *(_DWORD *)&EventDescriptor.Id = *v44;
      hostlong[0] = (unsigned __int16)v55;
      v57 = v60;
      v55 = v56;
      LODWORD(v59) = *((_DWORD *)this + 30);
      *(_QWORD *)&v64.Id = "Sent";
      v54[0] = v6;
      v51[0] = v32;
      v61[0] = v31;
      v53 = v41;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v44,
        (unsigned int)word_1801CE74A,
        v42,
        v43,
        (__int64)&v64,
        (__int64)&v59,
        (__int64)&v53,
        (__int64)&v55,
        (__int64)&v57,
        (__int64)v61,
        (__int64)hostlong,
        (__int64)&EventDescriptor,
        (__int64)v51,
        (__int64)v54);
    }
  }
  else if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v59) = (unsigned __int16)v55;
    v51[0] = *((_DWORD *)this + 30);
    *(_QWORD *)&v64.Id = "Sent";
    v54[0] = v31;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v44,
      (unsigned int)byte_1801CF015,
      v42,
      v43,
      (__int64)&v64,
      (__int64)v51,
      (__int64)v54,
      (__int64)&v59);
  }
LABEL_56:
  RdpUdpETWEvents::OutgoingPacketProcessed(*((RdpUdpETWEvents **)this + 13));
  CRdpUdpStream::UpdatePerfMonCounters((CRdpUdpStream *)((char *)this - 72));
  if ( *((_QWORD *)this + 14) && *((_QWORD *)this + 30) && *((_QWORD *)this + 31) )
  {
    TickCount = GetTickCount();
    v46 = *((_DWORD *)this + 138);
    if ( !v46 )
    {
LABEL_64:
      *((_DWORD *)this + 138) = TickCount;
      goto LABEL_65;
    }
    if ( TickCount - v46 >= 0x2BF20 )
    {
      v47 = (CFecEncoder *)*((_QWORD *)this + 30);
      v54[0] = 0;
      v53 = 0;
      v55 = 0;
      v57 = 0;
      v61[0] = 0;
      v64 = 0;
      hostlong[0] = 0;
      v65 = 0;
      *(_DWORD *)&EventDescriptor.Id = 0;
      v51[0] = 0;
      if ( (unsigned int)CFecEncoder::RefreshTrafficStats(
                           v47,
                           TickCount - v46,
                           v54,
                           &v53,
                           &v55,
                           &v57,
                           v61,
                           (unsigned int *)&v64.Id,
                           v50)
        && (unsigned int)CFecDecoder::RefreshTrafficStats(
                           *((CFecDecoder **)this + 31),
                           TickCount - *((_DWORD *)this + 138),
                           hostlong,
                           (unsigned int *)&EventDescriptor.Id,
                           v51) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, u_long, unsigned int, EVENT_DESCRIPTOR *, int, u_long, _DWORD, u_long))(**((_QWORD **)this + 14) + 48LL))(
          *((_QWORD *)this + 14),
          v54[0],
          v53,
          v55,
          v57,
          v61[0],
          &v64,
          8,
          hostlong[0],
          *(_DWORD *)&EventDescriptor.Id,
          v51[0]);
      }
      goto LABEL_64;
    }
  }
LABEL_65:
  if ( this != (CRdpUdpStream *)-16LL )
  {
    if ( *((_DWORD *)this + 6) )
    {
      v48 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 2);
      if ( v48 )
        LeaveCriticalSection(v48);
    }
  }
  return (unsigned int)HaveDataToSend;
}

```

## disassembly

```asm
0x180067fe0  mov     [rsp-8+arg_18], rbx
0x180067fe5  push    rbp
0x180067fe6  push    rsi
0x180067fe7  push    rdi
0x180067fe8  push    r12
0x180067fea  push    r13
0x180067fec  push    r14
0x180067fee  push    r15
0x180067ff0  lea     rbp, [rsp-0B0h]
0x180067ff8  sub     rsp, 1B0h
0x180067fff  mov     rax, cs:__security_cookie
0x180068006  xor     rax, rsp
0x180068009  mov     [rbp+0E0h+var_40], rax
0x180068010  mov     r12, [rcx+220h]
0x180068017  mov     rsi, r8
0x18006801a  mov     qword ptr [rbp+0E0h+var_110.Id], r8
0x18006801e  mov     rdi, rcx
0x180068021  xor     r8d, r8d
0x180068024  mov     [rbp+0E0h+var_140], rdx
0x180068028  mov     r15d, r8d
0x18006802b  mov     [rbp+0E0h+var_128], r8
0x18006802f  mov     [rbp+0E0h+var_150], r8d
0x180068033  mov     [rbp+0E0h+var_154], r8d
0x180068037  mov     [rbp+0E0h+var_138], r8d
0x18006803b  mov     [rsp+1E0h+var_168], r8b
0x180068040  mov     word ptr [rsp+1E0h+var_164], r8w
0x180068046  mov     [rbp+0E0h+hostlong], r8d
0x18006804a  mov     [rsp+1E0h+var_170], r8d
0x18006804f  mov     word ptr [rbp+0E0h+var_158], r8w
0x180068054  mov     [rbp+0E0h+var_130], r8d
0x180068058  cmp     [rcx+18h], r8d
0x18006805c  jz      short loc_180068074
0x18006805e  mov     rcx, [rcx+10h]; lpCriticalSection
0x180068062  test    rcx, rcx
0x180068065  jz      short loc_180068074
0x180068067  call    cs:__imp_EnterCriticalSection
0x18006806d  mov     rdx, [rbp+0E0h+var_140]
0x180068071  xor     r8d, r8d
0x180068074  mov     [rdx], r8
0x180068077  lea     r13, _TraceLoggingMetadataEnd
0x18006807e  mov     [rsi], r8
0x180068081  lea     rcx, _TraceLoggingMetadata
0x180068088  mov     eax, cs:CallbackContext
0x18006808e  mov     r14d, 1
0x180068094  cmp     eax, 5
0x180068097  jbe     loc_180068126
0x18006809d  mov     [rbp+0E0h+EventDescriptor.Keyword], r8
0x1800680a1  lea     rax, aCrdpudpstreamG; "CRdpUdpStream::GetDataToSend called"
0x1800680a8  mov     [rbp+0E0h+var_D0], rax
0x1800680ac  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x1800680b0  movzx   eax, cs:word_1801CF33B
0x1800680b7  xor     r9d, r9d; RelatedActivityId
0x1800680ba  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x1800680bd  xor     r8d, r8d; ActivityId
0x1800680c0  mov     rax, cs:off_1801E7010
0x1800680c7  mov     [rbp+0E0h+var_F0.Ptr], rax
0x1800680cb  mov     [rbp+0E0h+var_C8], 24h ; '$'
0x1800680d3  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x1800680da  movzx   eax, word ptr [rax]
0x1800680dd  mov     [rbp+0E0h+var_F0.Size], eax
0x1800680e0  lea     rax, byte_1801CF345
0x1800680e7  mov     [rbp+0E0h+var_E0], rax
0x1800680eb  mov     rax, r13
0x1800680ee  sub     eax, ecx
0x1800680f0  mov     dword ptr [rbp+0E0h+var_F0.0Ch], 2
0x1800680f7  mov     [rbp+0E0h+var_D8], 13h
0x1800680fe  mov     [rbp+0E0h+var_D4], r14d
0x180068102  mov     [rbp+0E0h+var_160], eax
0x180068105  mov     eax, [rbp+0E0h+var_160]
0x180068108  mov     rcx, cs:RegHandle; RegHandle
0x18006810f  lea     rax, [rbp+0E0h+var_F0]
0x180068113  mov     [rsp+1E0h+UserData], rax; UserData
0x180068118  mov     [rsp+1E0h+UserDataCount], 3; UserDataCount
0x180068120  call    cs:__imp_EventWriteTransfer
0x180068126  mov     rcx, rdi; this
0x180068129  call    ?OnTransportTimer@CRdpUdpStream@@UEAAJXZ; CRdpUdpStream::OnTransportTimer(void)
0x18006812e  mov     ebx, eax
0x180068130  test    eax, eax
0x180068132  jns     loc_18006824C
0x180068138  mov     ecx, cs:CallbackContext
0x18006813e  cmp     ecx, 2
0x180068141  jbe     loc_180068986
0x180068147  mov     [rsp+1E0h+var_170], eax
0x18006814b  lea     rdx, [rbp+0E0h+var_110]; EventDescriptor
0x18006814f  mov     [rbp+0E0h+var_160], 0AF4h
0x180068156  lea     rax, aOntimerFailed; "OnTimer failed"
0x18006815d  mov     [rbp+0E0h+var_50], rax
0x180068164  xor     r9d, r9d; RelatedActivityId
0x180068167  mov     [rbp+0E0h+var_48], 0Fh
0x180068172  lea     rax, aGetdatatosend; "GetDataToSend"
0x180068179  mov     [rbp+0E0h+var_60], rax
0x180068180  xor     r8d, r8d; ActivityId
0x180068183  mov     [rbp+0E0h+var_58], 0Eh
0x18006818e  lea     rax, [rbp+0E0h+var_160]
0x180068192  mov     [rbp+0E0h+var_70], rax
0x180068196  lea     rax, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006819d  mov     [rbp+0E0h+var_80], rax
0x1800681a1  lea     rax, [rsp+1E0h+var_170]
0x1800681a6  mov     [rbp+0E0h+var_90], rax
0x1800681aa  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800681b1  mov     [rbp+0E0h+var_A0], rax
0x1800681b5  movzx   eax, cs:word_1801CF8A6
0x1800681bc  mov     dword ptr [rbp+0E0h+var_110.Level], eax
0x1800681bf  mov     rax, cs:off_1801E7010
0x1800681c6  mov     [rbp+0E0h+var_C0.Ptr], rax
0x1800681ca  mov     [rbp+0E0h+var_68], 4
0x1800681d2  mov     [rbp+0E0h+var_78], 4Ch ; 'L'
0x1800681da  mov     [rbp+0E0h+var_88], 4
0x1800681e2  mov     [rbp+0E0h+var_98], 15h
0x1800681ea  mov     dword ptr [rbp+0E0h+var_110.Id], 0B000000h
0x1800681f1  mov     [rbp+0E0h+var_110.Keyword], r15
0x1800681f5  movzx   eax, word ptr [rax]
0x1800681f8  mov     [rbp+0E0h+var_C0.Size], eax
0x1800681fb  lea     rax, qword_1801CF8B0
0x180068202  mov     [rbp+0E0h+var_B0], rax
0x180068206  lea     rax, _TraceLoggingMetadata
0x18006820d  sub     r13d, eax
0x180068210  mov     dword ptr [rbp+0E0h+var_C0.0Ch], 2
0x180068217  mov     [rbp+0E0h+var_A8], 3Fh ; '?'
0x18006821e  mov     [rbp+0E0h+var_A4], r14d
0x180068222  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], r13d
0x180068226  mov     eax, dword ptr [rbp+0E0h+EventDescriptor.Id]
0x180068229  mov     rcx, cs:RegHandle; RegHandle
0x180068230  lea     rax, [rbp+0E0h+var_C0]
0x180068234  mov     [rsp+1E0h+UserData], rax; UserData
0x180068239  mov     [rsp+1E0h+UserDataCount], 8; UserDataCount
0x180068241  call    cs:__imp_EventWriteTransfer
0x180068247  jmp     loc_180068986
0x18006824c  mov     rcx, [rdi+108h]
0x180068253  test    rcx, rcx
0x180068256  jz      loc_180068342
0x18006825c  lea     r8, [rsp+1E0h+var_170]
0x180068261  mov     qword ptr [rbp+0E0h+var_160], r15
0x180068265  lea     rdx, [rbp+0E0h+var_160]
0x180068269  mov     qword ptr [rsp+1E0h+var_170], r15
0x18006826e  call    ?OnBufferAvailable@CUDPRateController@@UEAA?AW4_XResult32@@PEAPEAEPEA_K@Z; CUDPRateController::OnBufferAvailable(uchar * *,unsigned __int64 *)
0x180068273  test    eax, eax
0x180068275  jz      loc_180068315
0x18006827b  mov     ecx, cs:CallbackContext
0x180068281  mov     ebx, 80004005h
0x180068286  cmp     ecx, 2
0x180068289  jbe     loc_180068986
0x18006828f  mov     [rbp+0E0h+var_160], eax
0x180068292  lea     rdx, word_1801CEE06
0x180068299  mov     eax, [rdi+78h]
0x18006829c  mov     [rsp+1E0h+var_170], eax
0x1800682a0  lea     rax, aGetdatatosend; "GetDataToSend"
0x1800682a7  mov     [rbp+0E0h+var_128], rax
0x1800682ab  lea     rax, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800682b2  mov     [rbp+0E0h+var_140], rax
0x1800682b6  lea     rax, aUdpStreamRatec_0; "UDP Stream: RateController returned err"...
0x1800682bd  mov     qword ptr [rbp+0E0h+var_130], rax
0x1800682c1  lea     rax, [rbp+0E0h+var_160]
0x1800682c5  mov     [rsp+1E0h+var_190], rax
0x1800682ca  lea     rax, [rsp+1E0h+var_170]
0x1800682cf  mov     [rsp+1E0h+var_198], rax
0x1800682d4  lea     rax, [rbp+0E0h+var_128]
0x1800682d8  mov     [rsp+1E0h+var_1A0], rax
0x1800682dd  lea     rax, [rbp+0E0h+EventDescriptor]
0x1800682e1  mov     [rsp+1E0h+var_1A8], rax
0x1800682e6  lea     rax, [rbp+0E0h+var_140]
0x1800682ea  mov     [rsp+1E0h+var_1B0], rax
0x1800682ef  lea     rax, [rbp+0E0h+hostlong]
0x1800682f3  mov     [rsp+1E0h+UserData], rax
0x1800682f8  lea     rax, [rbp+0E0h+var_130]
0x1800682fc  mov     qword ptr [rsp+1E0h+UserDataCount], rax
0x180068301  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B01h
0x180068308  mov     [rbp+0E0h+hostlong], ebx
0x18006830b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180068310  jmp     loc_180068986
0x180068315  mov     rax, qword ptr [rbp+0E0h+var_160]
0x180068319  test    rax, rax
0x18006831c  jz      loc_18006850E
0x180068322  mov     rcx, qword ptr [rsp+1E0h+var_170]
0x180068327  test    rcx, rcx
0x18006832a  jz      loc_18006850E
0x180068330  mov     [rsi], rcx
0x180068333  mov     ebx, r15d
0x180068336  mov     rcx, [rbp+0E0h+var_140]
0x18006833a  mov     [rcx], rax
0x18006833d  jmp     loc_180068986
0x180068342  mov     rcx, [rdi+170h]
0x180068349  test    rcx, rcx
0x18006834c  jz      loc_180068448
0x180068352  mov     rdx, [rdi+220h]
0x180068359  lea     r8, [rbp+0E0h+hostlong]
0x18006835d  mov     qword ptr [rbp+0E0h+hostlong], r15
0x180068361  mov     rax, [rcx]
0x180068364  mov     rax, [rax+10h]
0x180068368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006836d  test    eax, eax
0x18006836f  jz      loc_18006840C
0x180068375  mov     eax, cs:CallbackContext
0x18006837b  mov     ebx, 80004005h
0x180068380  cmp     eax, 2
0x180068383  jbe     loc_18006843A
0x180068389  mov     eax, [rdi+78h]
0x18006838c  lea     rdx, word_1801CE16E
0x180068393  mov     [rbp+0E0h+var_160], eax
0x180068396  lea     rax, aGetdatatosend; "GetDataToSend"
0x18006839d  mov     [rbp+0E0h+var_128], rax
0x1800683a1  lea     rax, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800683a8  mov     [rbp+0E0h+var_140], rax
0x1800683ac  lea     rax, aUdpStreamUdpna; "UDP Stream: UDPNanoWrapper returned err"...
0x1800683b3  mov     qword ptr [rbp+0E0h+var_130], rax
0x1800683b7  lea     rax, [rbp+0E0h+var_160]
0x1800683bb  mov     [rsp+1E0h+var_198], rax
0x1800683c0  lea     rax, [rbp+0E0h+var_128]
0x1800683c4  mov     [rsp+1E0h+var_1A0], rax
0x1800683c9  lea     rax, [rsp+1E0h+var_170]
0x1800683ce  mov     [rsp+1E0h+var_1A8], rax
0x1800683d3  lea     rax, [rbp+0E0h+var_140]
0x1800683d7  mov     [rsp+1E0h+var_1B0], rax
0x1800683dc  lea     rax, [rbp+0E0h+EventDescriptor]
0x1800683e0  mov     [rsp+1E0h+UserData], rax
0x1800683e5  lea     rax, [rbp+0E0h+var_130]
0x1800683e9  mov     qword ptr [rsp+1E0h+UserDataCount], rax
0x1800683ee  mov     [rsp+1E0h+var_170], 0B19h
0x1800683f6  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], ebx
0x1800683f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800683fe  mov     rcx, [rdi+68h]; this
0x180068402  call    ?OutgoingPacketProcessed@RdpUdpETWEvents@@QEAAXXZ; RdpUdpETWEvents::OutgoingPacketProcessed(void)
0x180068407  jmp     loc_180068986
0x18006840c  mov     rax, qword ptr [rbp+0E0h+hostlong]
0x180068410  test    rax, rax
0x180068413  jnz     short loc_180068426
0x180068415  mov     rcx, [rdi+68h]; this
0x180068419  mov     ebx, r14d
0x18006841c  call    ?OutgoingPacketProcessed@RdpUdpETWEvents@@QEAAXXZ; RdpUdpETWEvents::OutgoingPacketProcessed(void)
0x180068421  jmp     loc_180068986
0x180068426  mov     rcx, [rbp+0E0h+var_140]
0x18006842a  mov     ebx, r15d
0x18006842d  mov     [rsi], rax
0x180068430  mov     rax, [rdi+220h]
0x180068437  mov     [rcx], rax
0x18006843a  mov     rcx, [rdi+68h]; this
0x18006843e  call    ?OutgoingPacketProcessed@RdpUdpETWEvents@@QEAAXXZ; RdpUdpETWEvents::OutgoingPacketProcessed(void)
0x180068443  jmp     loc_180068986
0x180068448  mov     rcx, [rdi+0F0h]; this
0x18006844f  lea     r9, [rbp+0E0h+var_130]; int *
0x180068453  lea     r8, [rbp+0E0h+var_138]; unsigned int *
0x180068457  lea     rdx, [rbp+0E0h+var_154]; unsigned int *
0x18006845b  call    ?HaveDataToSend@CFecEncoder@@QEAAJPEAI0PEAH@Z; CFecEncoder::HaveDataToSend(uint *,uint *,int *)
0x180068460  mov     ebx, eax
0x180068462  test    eax, eax
0x180068464  jns     loc_1800684F8
0x18006846a  mov     eax, cs:CallbackContext
0x180068470  cmp     eax, 2
0x180068473  jbe     loc_180068986
0x180068479  lea     rax, aFecencoderInEr; "FecEncoder in error, need to disconnect"
0x180068480  mov     [rbp+0E0h+var_160], 0B2Ch
0x180068487  mov     [rbp+0E0h+var_128], rax
0x18006848b  lea     rdx, qword_1801CECE8
0x180068492  lea     rax, aGetdatatosend; "GetDataToSend"
0x180068499  mov     [rsp+1E0h+var_170], ebx
0x18006849d  mov     [rbp+0E0h+var_140], rax
0x1800684a1  lea     rax, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800684a8  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], rax
0x1800684ac  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800684b3  mov     qword ptr [rbp+0E0h+hostlong], rax
0x1800684b7  lea     rax, [rbp+0E0h+var_128]
0x1800684bb  mov     [rsp+1E0h+var_198], rax
0x1800684c0  lea     rax, [rbp+0E0h+var_140]
0x1800684c4  mov     [rsp+1E0h+var_1A0], rax
0x1800684c9  lea     rax, [rbp+0E0h+var_160]
0x1800684cd  mov     [rsp+1E0h+var_1A8], rax
0x1800684d2  lea     rax, [rbp+0E0h+EventDescriptor]
0x1800684d6  mov     [rsp+1E0h+var_1B0], rax
0x1800684db  lea     rax, [rsp+1E0h+var_170]
0x1800684e0  mov     [rsp+1E0h+UserData], rax
0x1800684e5  lea     rax, [rbp+0E0h+hostlong]
0x1800684e9  mov     qword ptr [rsp+1E0h+UserDataCount], rax
0x1800684ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800684f3  jmp     loc_180068986
0x1800684f8  cmp     [rbp+0E0h+var_130], r15d
0x1800684fc  jnz     short loc_180068516
0x1800684fe  mov     rcx, [rdi+0F8h]; this
0x180068505  call    ?HasNewFeedback@CFecDecoder@@QEAAHXZ; CFecDecoder::HasNewFeedback(void)
0x18006850a  test    eax, eax
0x18006850c  jnz     short loc_180068516
0x18006850e  mov     ebx, r14d
0x180068511  jmp     loc_180068986
0x180068516  mov     edx, [rdi+0A8h]
0x18006851c  lea     rax, [rsp+1E0h+var_164]
0x180068521  mov     rcx, [rdi+0F8h]; this
0x180068528  lea     r9, [rbp+0E0h+EventDescriptor]; unsigned int *
0x18006852c  mov     [rsp+1E0h+var_1B0], rax; unsigned __int16 *
0x180068531  lea     r8, [r12+8]; unsigned __int8 *
0x180068536  lea     rax, [rbp+0E0h+var_158]
0x18006853a  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], r15d
0x18006853e  mov     [rsp+1E0h+UserData], rax; unsigned __int16 *
0x180068543  add     edx, 7FAh; unsigned int
0x180068549  lea     rax, [rsp+1E0h+var_170]
0x18006854e  mov     qword ptr [rsp+1E0h+UserDataCount], rax; unsigned int *
0x180068553  call    ?GetAckVector@CFecDecoder@@QEAAJKPEAEPEAKPEAIPEAG3@Z; CFecDecoder::GetAckVector(ulong,uchar *,ulong *,uint *,ushort *,ushort *)
0x180068558  mov     ebx, eax
0x18006855a  test    eax, eax
0x18006855c  jns     loc_1800685F0
0x180068562  mov     eax, cs:CallbackContext
0x180068568  cmp     eax, 2
  ... truncated ...
```
