# CRdpDynVCMgr::HandleIncomingDvcData(uchar *,ulong)

- ea: `0x18006c264`
- end: `0x18006cafc`
- name: `?HandleIncomingDvcData@CRdpDynVCMgr@@IEAAJPEAEK@Z`
- size: `2200`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *this, struct _DYNVC_HEADER *, unsigned int)`
- caller_count: `2`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006cc30`
- `0x18006ced0`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180001f84`
- `0x18000202c`
- `0x180002170`
- `0x180002568`
- `0x180006164`
- `0x18000c52c`
- `0x18000cdac`
- `0x18000ce04`
- `0x18000ce34`
- `0x180029044`
- `0x18002aafc`
- `0x18002ab1c`
- `0x180041460`
- `0x180041484`
- `0x180046508`
- `0x18004d63c`
- `0x18004db78`
- `0x18004f5bc`
- `0x180052dac`
- `0x18006c264`
- `0x18006cc30`
- `0x18006d118`
- `0x18013e574`
- `0x1801414b0`
- `0x1801429d4`
- `0x18014dfac`
- `0x18019c010`

## string_xrefs

- `0x18006c56f`: `DynVCMgr has already Terminated, quitting`
- `0x18006c30d`: `Incomplete data read, expecting DYNVC_HEADER`
- `0x18006c39e`: `Incomplete data read, expecting DYNVC_HEADER`
- `0x18006c2d9`: `HandleIncomingDvcData`
- `0x18006c69a`: `HandleIncomingDvcData`
- `0x18006c841`: `HandleIncomingDvcData`
- `0x18006c85f`: `HandleIncomingDvcData`
- `0x18006c9fc`: `HandleIncomingDvcData`
- `0x18006c42b`: `DVC incoming data`
- `0x18006c621`: `Attempting to process DVC data for "fake" channel. Ignoring the packet.`
- `0x18006ca0d`: `Incomplete data read, expecting CREATE_REPLY`
- `0x18006c9a8`: `DVC CreateReply PDU for Channel`
- `0x18006c800`: `GetDecompressor failed!`
- `0x18006c7c7`: `Decompress failed!`
- `0x18006c8d4`: `DVCMgr ready after DVC caps`
- `0x18006c6dd`: `HandleIncomingDvcData failed. Setting the stack shutdown flag.`

## pseudocode

```c
__int64 __fastcall CRdpDynVCMgr::HandleIncomingDvcData(CRdpDynVCMgr *this, struct _DYNVC_HEADER *a2, unsigned int a3)
{
  unsigned __int64 v3; // r9
  struct CRdpDynVC *v4; // rbx
  CRdpDynVCMgr *v6; // rsi
  int v7; // edi
  const char *v8; // r10
  const char **v9; // rax
  __int16 *v10; // rdx
  __int64 OffsetFromHeader; // r15
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  unsigned int ChannelId; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  CTSAutoLock *v27; // rcx
  unsigned int Length; // r12d
  int v29; // ecx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  int v33; // ecx
  struct IRdpPipeDecompress *Decompressor; // rdi
  int v35; // r8d
  int v36; // r9d
  const char *v37; // rax
  char *v38; // rdx
  unsigned int v39; // r8d
  __int16 v40; // bx
  int TunnelTypeForVC; // eax
  int v42; // eax
  __int64 v43; // rdx
  const char **v45; // [rsp+40h] [rbp-29h]
  const char *v46; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 *v47; // [rsp+58h] [rbp-11h] BYREF
  struct CRdpDynVC *v48; // [rsp+60h] [rbp-9h] BYREF
  const char *v49; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v50[10]; // [rsp+70h] [rbp+7h] BYREF
  const char *v51; // [rsp+D0h] [rbp+67h] BYREF
  char *v52; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v53; // [rsp+E0h] [rbp+77h] BYREF
  const char *v54; // [rsp+E8h] [rbp+7Fh] BYREF

  v53 = a3;
  LODWORD(v3) = a3;
  v4 = 0;
  v6 = this;
  v48 = 0;
  v47 = 0;
  if ( *((_DWORD *)this + 5000) )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v51 = "Ignoring packet in error state.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&dword_180295ABC,
        a3,
        a3,
        (__int64)&v51);
    }
    v7 = 1;
    goto LABEL_82;
  }
  v8 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
  if ( a3 < 2 )
  {
    v7 = -2147024883;
    if ( (unsigned int)CallbackContext <= 2 )
    {
LABEL_43:
      v46 = (char *)v6 + 200;
      CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)v6 + 200));
      if ( (*((_BYTE *)v6 + 28) & 4) == 0 )
        *((_DWORD *)v6 + 4999) = 1;
      *((_DWORD *)v6 + 5000) = 1;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v54 = "HandleIncomingDvcData";
        v49 = "HandleIncomingDvcData failed. Setting the stack shutdown flag.";
        LODWORD(v51) = 5721;
        v50[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
        LODWORD(v52) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v30,
          (unsigned int)qword_180295780,
          v31,
          v32,
          (__int64)&v49,
          (__int64)&v52,
          (__int64)v50,
          (__int64)&v51,
          (__int64)&v54);
      }
      v27 = (CTSAutoLock *)&v46;
      goto LABEL_30;
    }
    LODWORD(v51) = v53;
    v50[0] = "Incomplete data read, expecting DYNVC_HEADER";
    v45 = &v46;
    v9 = (const char **)v50;
    LODWORD(v54) = -2147024883;
    v10 = &word_180295A1E;
    v46 = "HandleIncomingDvcData";
    LODWORD(v52) = 5466;
LABEL_8:
    v49 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (_DWORD)v10,
      a3,
      v3,
      (__int64)v9,
      (__int64)&v54,
      (__int64)&v49,
      (__int64)&v52,
      (__int64)v45,
      (__int64)&v51);
    goto LABEL_43;
  }
  OffsetFromHeader = GetOffsetFromHeader(a2);
  if ( v3 < OffsetFromHeader + 2 )
  {
    v7 = -2147024883;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_43;
    v46 = "Incomplete data read, expecting DYNVC_HEADER";
    LODWORD(this) = OffsetFromHeader + v53;
    LODWORD(v54) = -2147024883;
    v10 = (__int16 *)byte_180295A6D;
    LODWORD(v51) = OffsetFromHeader + v53;
    v45 = (const char **)v50;
    v9 = &v46;
    v50[0] = "HandleIncomingDvcData";
    LODWORD(v52) = 5474;
    goto LABEL_8;
  }
  if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v51) = GetChannelId(a2);
    LODWORD(v52) = *((unsigned __int16 *)v6 + 280);
    LODWORD(v54) = *(unsigned __int8 *)a2 >> 4;
    LODWORD(v46) = v53;
    v50[0] = "DVC incoming data";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)&byte_18029597F,
      v13,
      v14,
      (__int64)v50,
      (__int64)&v46,
      (__int64)&v54,
      (__int64)&v52,
      (__int64)&v51);
  }
  if ( (*(_BYTE *)a2 & 0xF0) != 0x50 )
  {
    if ( !*((_WORD *)v6 + 280) )
    {
      if ( !(unsigned int)CRdpDynVCMgr::IsSkipLegacyProtocolEnabled(v6) )
        goto LABEL_81;
      *((_WORD *)v6 + 280) = 3;
      CRdpDynVCMgr::OnDVCMgrReady(v6);
    }
    if ( (*(_BYTE *)a2 & 0xF0) == 0x90 )
    {
      v7 = CRdpDynVCMgr::ProcessSoftSyncPDUFromClient(v6, (unsigned __int8 *)a2, v53);
      if ( v7 >= 0 )
        goto LABEL_82;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v50[0] = "HandleIncomingDvcData";
        v54 = "Failed to process soft sync pdu from client";
        LODWORD(v51) = 5511;
        v46 = "Error HResult failed";
        v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
        LODWORD(v52) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_1802959CD,
          v15,
          v16,
          (__int64)&v46,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v51,
          (__int64)v50,
          (__int64)&v54);
      }
      goto LABEL_43;
    }
    v52 = (char *)v6 + 200;
    CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)v6 + 200));
    if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v51 = "DynVCMgr has already Terminated, quitting";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (unsigned int)word_18029592A,
          v18,
          v19,
          (__int64)&v51);
      }
      v7 = -2147467259;
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v52);
      goto LABEL_43;
    }
    ChannelId = GetChannelId(a2);
    CRdpDynVCMgr::GetChannel(v6, ChannelId, &v48);
    v4 = v48;
    if ( !v48 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v51) = GetChannelId(a2);
        v54 = "Channel not found";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)&byte_18029594F,
          v25,
          v26,
          (__int64)&v54,
          (__int64)&v51);
      }
LABEL_29:
      v7 = 0;
      v27 = (CTSAutoLock *)&v52;
LABEL_30:
      CTSAutoLock::~CTSAutoLock(v27);
      goto LABEL_82;
    }
    if ( *((_DWORD *)v48 + 30) )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v51 = "Attempting to process DVC data for \"fake\" channel. Ignoring the packet.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v21,
          (unsigned int)&byte_1802958CF,
          v22,
          v23,
          (__int64)&v51);
      }
      goto LABEL_29;
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v52);
  }
  Length = 0;
  switch ( *(unsigned __int8 *)a2 >> 4 )
  {
    case 1:
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v51) = *((_DWORD *)v4 + 34);
        v52 = (char *)*((_QWORD *)v4 + 14);
        v54 = "DVC CreateReply PDU for Channel";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0,
          (unsigned int)&dword_1802958F4,
          a3,
          v3,
          (__int64)&v54,
          (__int64)&v52,
          (__int64)&v51);
      }
      if ( v53 < (unsigned __int64)(OffsetFromHeader + 6) )
      {
        v7 = -2147024883;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v51) = v53;
          LODWORD(v54) = -2147024883;
          v46 = "Incomplete data read, expecting CREATE_REPLY";
          v50[0] = "HandleIncomingDvcData";
          LODWORD(v52) = 5572;
          v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            OffsetFromHeader + 6,
            (unsigned int)qword_180295880,
            a3,
            v3,
            (__int64)&v46,
            (__int64)&v54,
            (__int64)&v49,
            (__int64)&v52,
            (__int64)v50,
            (__int64)&v51);
        }
        goto LABEL_43;
      }
      if ( *((_DWORD *)v6 + 4991) )
      {
        TunnelTypeForVC = CRdpDynVCMgr::GetTunnelTypeForVC(v6, v4);
        CRdpDynVC::OnBandwidthUpdate(v4, *((_DWORD *)v6 + 20 * TunnelTypeForVC + 74));
        v42 = CRdpDynVCMgr::GetTunnelTypeForVC(v6, v4);
        CRdpDynVC::OnRTTUpdate(v4, *((_DWORD *)v6 + 20 * v42 + 75));
      }
      v43 = *(unsigned int *)((char *)a2 + OffsetFromHeader + 2);
      LODWORD(v43) = v43 | 0x10000000;
      CRdpDynVC::OnClientBound(v4, v43, *((unsigned int *)v4 + 43));
      goto LABEL_81;
    case 2:
      Length = GetLength(a2);
      goto LABEL_68;
    case 3:
LABEL_68:
      v7 = 0;
      v39 = -2 - OffsetFromHeader + v53;
      v53 = v39;
      v47 = (unsigned __int8 *)a2 + OffsetFromHeader + 2;
      goto LABEL_69;
    case 4:
      CRdpDynVC::OnClose(v4);
      goto LABEL_81;
  }
  v29 = (*(unsigned __int8 *)a2 >> 4) - 5;
  switch ( *(unsigned __int8 *)a2 >> 4 )
  {
    case 5:
      v40 = *((_WORD *)v6 + 280);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v51 = "DVC Caps Received from Client ";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          0,
          (unsigned int)word_180295812,
          a3,
          v3,
          (__int64)&v51);
      }
      if ( v53 < 4 )
      {
        v7 = -2147024883;
        goto LABEL_43;
      }
      *((_WORD *)v6 + 280) = *((_WORD *)a2 + 1);
      if ( (unsigned int)CallbackContext > 4 )
      {
        v51 = "DVCMgr ready after DVC caps";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v29,
          (unsigned int)byte_18029575B,
          a3,
          v3,
          (__int64)&v51);
      }
      if ( !v40 )
        CRdpDynVCMgr::OnDVCMgrReady(v6);
LABEL_81:
      v7 = 0;
      goto LABEL_82;
    case 6:
      Length = GetLength(a2);
      break;
    case 7:
      break;
    default:
      v7 = -805306355;
      goto LABEL_43;
  }
  v54 = 0;
  v53 += -2 - OffsetFromHeader;
  v47 = (unsigned __int8 *)a2 + OffsetFromHeader + 2;
  Decompressor = CRdpDynVC::GetDecompressor(v4);
  if ( !Decompressor )
  {
    v7 = -2147467261;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v51) = 5639;
      v37 = "GetDecompressor failed!";
      v38 = byte_1802957C9;
      goto LABEL_56;
    }
LABEL_57:
    TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
    goto LABEL_43;
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
  v54 = (const char *)Decompressor;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v54);
  v7 = (*(__int64 (__fastcall **)(struct IRdpPipeDecompress *, unsigned __int8 *, _QWORD, unsigned __int8 **, unsigned int *))(*(_QWORD *)Decompressor + 24LL))(
         Decompressor,
         v47,
         v53,
         &v47,
         &v53);
  if ( v7 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v51) = 5632;
      v37 = "Decompress failed!";
      v38 = &byte_180295837;
LABEL_56:
      v46 = v37;
      v50[0] = "HandleIncomingDvcData";
      LODWORD(v52) = v7;
      v49 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v33,
        (_DWORD)v38,
        v35,
        v36,
        (__int64)&v46,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&v51,
        (__int64)v50);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
  v39 = v53;
LABEL_69:
  if ( (*((_DWORD *)v4 + 40) & 0x100) != 0 && v39 )
  {
    CRdpDynVCMgr::OnRDPChannelDataReceived((char *)v6 + 80, 0x74706E69706472LL, 0, 0);
    v39 = v53;
  }
  CRdpDynVC::OnDataReceived(v4, v47, v39, Length);
LABEL_82:
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v48);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006c264  mov     [rsp-8+arg_10], r8d
0x18006c269  push    rbp
0x18006c26a  push    rbx
0x18006c26b  push    rsi
0x18006c26c  push    rdi
0x18006c26d  push    r12
0x18006c26f  push    r13
0x18006c271  push    r14
0x18006c273  push    r15
0x18006c275  lea     rbp, [rsp-1Fh]
0x18006c27a  sub     rsp, 88h
0x18006c281  xor     r13d, r13d
0x18006c284  mov     r9d, r8d
0x18006c287  mov     ebx, r13d
0x18006c28a  mov     r14, rdx
0x18006c28d  mov     rsi, rcx
0x18006c290  mov     [rbp+57h+var_60], rbx
0x18006c294  mov     [rbp+57h+var_68], r13
0x18006c298  cmp     [rcx+4E20h], r13d
0x18006c29f  jz      short loc_18006C2D9
0x18006c2a1  mov     eax, cs:CallbackContext
0x18006c2a7  lea     edi, [r13+3]
0x18006c2ab  cmp     eax, edi
0x18006c2ad  jbe     short loc_18006C2CF
0x18006c2af  lea     rax, aIgnoringPacket; "Ignoring packet in error state."
0x18006c2b6  mov     [rbp+57h+arg_0], rax
0x18006c2ba  lea     rdx, dword_180295ABC
0x18006c2c1  lea     rax, [rbp+57h+arg_0]
0x18006c2c5  mov     [rsp+0C0h+var_A0], rax
0x18006c2ca  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006c2cf  mov     edi, 1
0x18006c2d4  jmp     loc_18006CADD
0x18006c2d9  lea     r12, aHandleincoming; "HandleIncomingDvcData"
0x18006c2e0  lea     r10, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006c2e7  cmp     r9d, 2
0x18006c2eb  jnb     loc_18006C371
0x18006c2f1  mov     eax, cs:CallbackContext
0x18006c2f7  mov     edx, 8007000Dh
0x18006c2fc  mov     edi, edx
0x18006c2fe  cmp     eax, 2
0x18006c301  jbe     loc_18006C6A1
0x18006c307  mov     eax, [rbp+57h+arg_10]
0x18006c30a  mov     dword ptr [rbp+57h+arg_0], eax
0x18006c30d  lea     rax, aIncompleteData_0; "Incomplete data read, expecting DYNVC_H"...
0x18006c314  mov     [rbp+57h+var_50], rax
0x18006c318  lea     rax, [rbp+57h+arg_0]
0x18006c31c  mov     [rsp+0C0h+var_78], rax
0x18006c321  lea     rax, [rbp+57h+var_70]
0x18006c325  mov     [rsp+0C0h+var_80], rax
0x18006c32a  lea     rax, [rbp+57h+arg_8]
0x18006c32e  mov     [rsp+0C0h+var_88], rax
0x18006c333  lea     rax, [rbp+57h+var_58]
0x18006c337  mov     [rsp+0C0h+var_90], rax
0x18006c33c  lea     rax, [rbp+57h+arg_18]
0x18006c340  mov     [rsp+0C0h+var_98], rax
0x18006c345  lea     rax, [rbp+57h+var_50]
0x18006c349  mov     dword ptr [rbp+57h+arg_18], edx
0x18006c34c  lea     rdx, word_180295A1E
0x18006c353  mov     [rbp+57h+var_70], r12
0x18006c357  mov     dword ptr [rbp+57h+arg_8], 155Ah
0x18006c35e  mov     [rsp+0C0h+var_A0], rax
0x18006c363  mov     [rbp+57h+var_58], r10
0x18006c367  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006c36c  jmp     loc_18006C6A1
0x18006c371  mov     rcx, r14; struct _DYNVC_HEADER *
0x18006c374  call    ?GetOffsetFromHeader@@YAKPEAU_DYNVC_HEADER@@@Z; GetOffsetFromHeader(_DYNVC_HEADER *)
0x18006c379  mov     r15d, eax
0x18006c37c  mov     eax, cs:CallbackContext
0x18006c382  lea     rcx, [r15+2]
0x18006c386  cmp     r9, rcx
0x18006c389  jnb     short loc_18006C3FA
0x18006c38b  mov     edx, 8007000Dh
0x18006c390  mov     edi, edx
0x18006c392  cmp     eax, 2
0x18006c395  jbe     loc_18006C6A1
0x18006c39b  mov     ecx, [rbp+57h+arg_10]
0x18006c39e  lea     rax, aIncompleteData_0; "Incomplete data read, expecting DYNVC_H"...
0x18006c3a5  mov     [rbp+57h+var_70], rax
0x18006c3a9  add     ecx, r15d
0x18006c3ac  lea     rax, [rbp+57h+arg_0]
0x18006c3b0  mov     dword ptr [rbp+57h+arg_18], edx
0x18006c3b3  mov     [rsp+0C0h+var_78], rax
0x18006c3b8  lea     rdx, byte_180295A6D
0x18006c3bf  lea     rax, [rbp+57h+var_50]
0x18006c3c3  mov     dword ptr [rbp+57h+arg_0], ecx
0x18006c3c6  mov     [rsp+0C0h+var_80], rax
0x18006c3cb  lea     rax, [rbp+57h+arg_8]
0x18006c3cf  mov     [rsp+0C0h+var_88], rax
0x18006c3d4  lea     rax, [rbp+57h+var_58]
0x18006c3d8  mov     [rsp+0C0h+var_90], rax
0x18006c3dd  lea     rax, [rbp+57h+arg_18]
0x18006c3e1  mov     [rsp+0C0h+var_98], rax
0x18006c3e6  lea     rax, [rbp+57h+var_70]
0x18006c3ea  mov     [rbp+57h+var_50], r12
0x18006c3ee  mov     dword ptr [rbp+57h+arg_8], 1562h
0x18006c3f5  jmp     loc_18006C35E
0x18006c3fa  cmp     eax, 5
0x18006c3fd  jbe     short loc_18006C468
0x18006c3ff  mov     rcx, r14; struct _DYNVC_HEADER *
0x18006c402  call    ?GetChannelId@@YAIPEAU_DYNVC_HEADER@@@Z; GetChannelId(_DYNVC_HEADER *)
0x18006c407  mov     dword ptr [rbp+57h+arg_0], eax
0x18006c40a  lea     rdx, byte_18029597F
0x18006c411  movzx   eax, word ptr [rsi+230h]
0x18006c418  mov     dword ptr [rbp+57h+arg_8], eax
0x18006c41b  movzx   eax, byte ptr [r14]
0x18006c41f  shr     eax, 4
0x18006c422  mov     dword ptr [rbp+57h+arg_18], eax
0x18006c425  mov     eax, [rbp+57h+arg_10]
0x18006c428  mov     dword ptr [rbp+57h+var_70], eax
0x18006c42b  lea     rax, aDvcIncomingDat; "DVC incoming data"
0x18006c432  mov     [rbp+57h+var_50], rax
0x18006c436  lea     rax, [rbp+57h+arg_0]
0x18006c43a  mov     [rsp+0C0h+var_80], rax
0x18006c43f  lea     rax, [rbp+57h+arg_8]
0x18006c443  mov     [rsp+0C0h+var_88], rax
0x18006c448  lea     rax, [rbp+57h+arg_18]
0x18006c44c  mov     [rsp+0C0h+var_90], rax
0x18006c451  lea     rax, [rbp+57h+var_70]
0x18006c455  mov     [rsp+0C0h+var_98], rax
0x18006c45a  lea     rax, [rbp+57h+var_50]
0x18006c45e  mov     [rsp+0C0h+var_A0], rax
0x18006c463  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006c468  mov     al, [r14]
0x18006c46b  and     al, 0F0h
0x18006c46d  cmp     al, 50h ; 'P'
0x18006c46f  jz      loc_18006C64C
0x18006c475  mov     edi, 3
0x18006c47a  cmp     r13w, [rsi+230h]
0x18006c482  jnz     short loc_18006C4A3
0x18006c484  mov     rcx, rsi; this
0x18006c487  call    ?IsSkipLegacyProtocolEnabled@CRdpDynVCMgr@@IEAAHXZ; CRdpDynVCMgr::IsSkipLegacyProtocolEnabled(void)
0x18006c48c  test    eax, eax
0x18006c48e  jz      loc_18006CADA
0x18006c494  mov     rcx, rsi; this
0x18006c497  mov     [rsi+230h], di
0x18006c49e  call    ?OnDVCMgrReady@CRdpDynVCMgr@@IEAAJXZ; CRdpDynVCMgr::OnDVCMgrReady(void)
0x18006c4a3  mov     al, [r14]
0x18006c4a6  and     al, 0F0h
0x18006c4a8  cmp     al, 90h
0x18006c4aa  jnz     loc_18006C54E
0x18006c4b0  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x18006c4b4  mov     rdx, r14; unsigned __int8 *
0x18006c4b7  mov     rcx, rsi; this
0x18006c4ba  call    ?ProcessSoftSyncPDUFromClient@CRdpDynVCMgr@@IEAAJPEAEK@Z; CRdpDynVCMgr::ProcessSoftSyncPDUFromClient(uchar *,ulong)
0x18006c4bf  mov     edi, eax
0x18006c4c1  test    eax, eax
0x18006c4c3  jns     loc_18006CADD
0x18006c4c9  mov     ecx, cs:CallbackContext
0x18006c4cf  cmp     ecx, 2
0x18006c4d2  jbe     loc_18006C6A1
0x18006c4d8  lea     rax, aFailedToProces_4; "Failed to process soft sync pdu from cl"...
0x18006c4df  mov     [rbp+57h+var_50], r12
0x18006c4e3  mov     [rbp+57h+arg_18], rax
0x18006c4e7  lea     rbx, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006c4ee  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18006c4f5  mov     dword ptr [rbp+57h+arg_0], 1587h
0x18006c4fc  mov     [rbp+57h+var_70], rax
0x18006c500  lea     rdx, byte_1802959CD
0x18006c507  lea     rax, [rbp+57h+arg_18]
0x18006c50b  mov     [rbp+57h+var_58], rbx
0x18006c50f  mov     [rsp+0C0h+var_78], rax
0x18006c514  lea     rax, [rbp+57h+var_50]
0x18006c518  mov     [rsp+0C0h+var_80], rax
0x18006c51d  lea     rax, [rbp+57h+arg_0]
0x18006c521  mov     [rsp+0C0h+var_88], rax
0x18006c526  lea     rax, [rbp+57h+var_58]
0x18006c52a  mov     [rsp+0C0h+var_90], rax
0x18006c52f  lea     rax, [rbp+57h+arg_8]
0x18006c533  mov     [rsp+0C0h+var_98], rax
0x18006c538  lea     rax, [rbp+57h+var_70]
0x18006c53c  mov     [rsp+0C0h+var_A0], rax
0x18006c541  mov     dword ptr [rbp+57h+arg_8], edi
0x18006c544  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006c549  jmp     loc_18006C6A8
0x18006c54e  lea     rcx, [rsi+0C8h]; this
0x18006c555  mov     [rbp+57h+arg_8], rcx
0x18006c559  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006c55e  test    byte ptr [rsi+1Ch], 4
0x18006c562  jz      short loc_18006C5A2
0x18006c564  mov     eax, cs:CallbackContext
0x18006c56a  cmp     eax, 4
0x18006c56d  jbe     short loc_18006C58F
0x18006c56f  lea     rax, aDynvcmgrHasAlr; "DynVCMgr has already Terminated, quitti"...
0x18006c576  mov     [rbp+57h+arg_0], rax
0x18006c57a  lea     rdx, word_18029592A
0x18006c581  lea     rax, [rbp+57h+arg_0]
0x18006c585  mov     [rsp+0C0h+var_A0], rax
0x18006c58a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006c58f  lea     rcx, [rbp+57h+arg_8]; this
0x18006c593  mov     edi, 80004005h
0x18006c598  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006c59d  jmp     loc_18006C6A1
0x18006c5a2  mov     rcx, r14; struct _DYNVC_HEADER *
0x18006c5a5  call    ?GetChannelId@@YAIPEAU_DYNVC_HEADER@@@Z; GetChannelId(_DYNVC_HEADER *)
0x18006c5aa  mov     edx, eax; unsigned int
0x18006c5ac  lea     r8, [rbp+57h+var_60]; struct CRdpDynVC **
0x18006c5b0  mov     rcx, rsi; this
0x18006c5b3  call    ?GetChannel@CRdpDynVCMgr@@IEAAJKPEAPEAVCRdpDynVC@@@Z; CRdpDynVCMgr::GetChannel(ulong,CRdpDynVC * *)
0x18006c5b8  mov     rbx, [rbp+57h+var_60]
0x18006c5bc  test    rbx, rbx
0x18006c5bf  jnz     short loc_18006C611
0x18006c5c1  mov     eax, cs:CallbackContext
0x18006c5c7  cmp     eax, 4
0x18006c5ca  jbe     short loc_18006C600
0x18006c5cc  mov     rcx, r14; struct _DYNVC_HEADER *
0x18006c5cf  call    ?GetChannelId@@YAIPEAU_DYNVC_HEADER@@@Z; GetChannelId(_DYNVC_HEADER *)
0x18006c5d4  mov     dword ptr [rbp+57h+arg_0], eax
0x18006c5d7  lea     rdx, byte_18029594F
0x18006c5de  lea     rax, aChannelNotFoun; "Channel not found"
0x18006c5e5  mov     [rbp+57h+arg_18], rax
0x18006c5e9  lea     rax, [rbp+57h+arg_0]
0x18006c5ed  mov     [rsp+0C0h+var_98], rax
0x18006c5f2  lea     rax, [rbp+57h+arg_18]
0x18006c5f6  mov     [rsp+0C0h+var_A0], rax
0x18006c5fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006c600  mov     edi, r13d
0x18006c603  lea     rcx, [rbp+57h+arg_8]; this
0x18006c607  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006c60c  jmp     loc_18006CADD
0x18006c611  cmp     [rbx+78h], r13d
0x18006c615  jz      short loc_18006C643
0x18006c617  mov     eax, cs:CallbackContext
0x18006c61d  cmp     eax, edi
0x18006c61f  jbe     short loc_18006C600
0x18006c621  lea     rax, aAttemptingToPr; "Attempting to process DVC data for \"fa"...
0x18006c628  mov     [rbp+57h+arg_0], rax
0x18006c62c  lea     rdx, byte_1802958CF
0x18006c633  lea     rax, [rbp+57h+arg_0]
0x18006c637  mov     [rsp+0C0h+var_A0], rax
0x18006c63c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006c641  jmp     short loc_18006C600
0x18006c643  lea     rcx, [rbp+57h+arg_8]; this
0x18006c647  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006c64c  movzx   ecx, byte ptr [r14]
0x18006c650  mov     r12d, r13d
0x18006c653  shr     ecx, 4
0x18006c656  sub     ecx, 1
0x18006c659  jz      loc_18006C985
0x18006c65f  sub     ecx, 1
0x18006c662  jz      loc_18006C917
0x18006c668  sub     ecx, 1
0x18006c66b  jz      loc_18006C922
0x18006c671  sub     ecx, 1
0x18006c674  jz      loc_18006C90A
0x18006c67a  sub     ecx, 1
0x18006c67d  jz      loc_18006C87B
0x18006c683  sub     ecx, 1
0x18006c686  jz      loc_18006C73C
0x18006c68c  cmp     ecx, 1
0x18006c68f  jz      loc_18006C747
0x18006c695  mov     edi, 0D000000Dh
0x18006c69a  lea     r12, aHandleincoming; "HandleIncomingDvcData"
0x18006c6a1  lea     rbx, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006c6a8  lea     rcx, [rsi+0C8h]; this
0x18006c6af  mov     [rbp+57h+var_70], rcx
0x18006c6b3  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006c6b8  test    byte ptr [rsi+1Ch], 4
0x18006c6bc  jnz     short loc_18006C6C8
0x18006c6be  mov     dword ptr [rsi+4E1Ch], 1
0x18006c6c8  mov     dword ptr [rsi+4E20h], 1
0x18006c6d2  mov     eax, cs:CallbackContext
0x18006c6d8  cmp     eax, 2
0x18006c6db  jbe     short loc_18006C733
0x18006c6dd  lea     rax, aHandleincoming_0; "HandleIncomingDvcData failed. Setting t"...
0x18006c6e4  mov     [rbp+57h+arg_18], r12
0x18006c6e8  mov     [rbp+57h+var_58], rax
0x18006c6ec  lea     rdx, qword_180295780
0x18006c6f3  lea     rax, [rbp+57h+arg_18]
0x18006c6f7  mov     dword ptr [rbp+57h+arg_0], 1659h
0x18006c6fe  mov     [rsp+0C0h+var_80], rax
0x18006c703  lea     rax, [rbp+57h+arg_0]
0x18006c707  mov     [rsp+0C0h+var_88], rax
0x18006c70c  lea     rax, [rbp+57h+var_50]
0x18006c710  mov     [rsp+0C0h+var_90], rax
0x18006c715  lea     rax, [rbp+57h+arg_8]
0x18006c719  mov     [rsp+0C0h+var_98], rax
0x18006c71e  lea     rax, [rbp+57h+var_58]
0x18006c722  mov     [rsp+0C0h+var_A0], rax
0x18006c727  mov     [rbp+57h+var_50], rbx
0x18006c72b  mov     dword ptr [rbp+57h+arg_8], edi
0x18006c72e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006c733  lea     rcx, [rbp+57h+var_70]
0x18006c737  jmp     loc_18006C607
0x18006c73c  mov     rcx, r14; struct _DATA_FIRST *
0x18006c73f  call    ?GetLength@@YAKPEAU_DATA_FIRST@@@Z; GetLength(_DATA_FIRST *)
0x18006c744  mov     r12d, eax
0x18006c747  mov     ecx, 0FFFFFFFEh
0x18006c74c  mov     [rbp+57h+arg_18], r13
0x18006c750  sub     ecx, r15d
0x18006c753  add     [rbp+57h+arg_10], ecx
0x18006c756  lea     rcx, [r14+2]
0x18006c75a  add     rcx, r15
0x18006c75d  mov     [rbp+57h+var_68], rcx
0x18006c761  mov     rcx, rbx; this
0x18006c764  call    ?GetDecompressor@CRdpDynVC@@QEAAPEAVIRdpPipeDecompress@@XZ; CRdpDynVC::GetDecompressor(void)
0x18006c769  mov     rdi, rax
0x18006c76c  test    rax, rax
0x18006c76f  jz      short loc_18006C7E9
0x18006c771  lea     rcx, [rbp+57h+arg_18]
0x18006c775  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
  ... truncated ...
```
