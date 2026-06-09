# CRDPWDUMXStack::SendChannelData(_RDPWDUMX_CHANNEL_NAME,uchar *,ulong,int,ulong,ulong)

- ea: `0x180127930`
- end: `0x1801282ad`
- name: `?SendChannelData@CRDPWDUMXStack@@UEAAJU_RDPWDUMX_CHANNEL_NAME@@PEAEKHKK@Z`
- size: `2429`
- prototype: `int __high(struct _RDPWDUMX_CHANNEL_NAME, unsigned __int8 *, unsigned int, int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000146c`
- `0x18000202c`
- `0x1800062fc`
- `0x1800068c0`
- `0x18000ce04`
- `0x180046508`
- `0x18004db78`
- `0x180050dbc`
- `0x180053400`
- `0x18007098c`
- `0x18007e9e0`
- `0x18007f324`
- `0x180112e68`
- `0x180113124`
- `0x18011345c`
- `0x180113a04`
- `0x180127930`
- `0x1801284a4`
- `0x180130df8`
- `0x1801877d4`
- `0x18019b31c`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801279d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801279d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180127984`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180127984`

## string_xrefs

- `0x180127a9a`: `Waiting for share creation completion event to send on fake channel...`
- `0x180127a40`: `Attempting to send bytes before share creation is complete.`
- `0x180127b94`: `Share creation completion signalled! Data will now be sent.`
- `0x180127af7`: `Failed to wait for share creation completion event`
- `0x180127c99`: `Sending data on a non-fake channel before share completion is unexpected! Data will be dropped!`
- `0x18012801b`: `Sending VC data total size is larger than write size.`
- `0x18012816a`: `WriteBuffer`
- `0x180128274`: `Failed to write channel data`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::SendChannelData(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7)
{
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ebx
  __int64 v15; // r13
  unsigned int v16; // r12d
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // eax
  int *v20; // rdx
  const char **v21; // rax
  const char *v22; // rax
  __int16 *v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v27; // rdx
  const char *v28; // rax
  ShareClass *v29; // rcx
  int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
  unsigned int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // r15
  __int64 v40; // rcx
  unsigned int v41; // eax
  bool v42; // zf
  unsigned int v43; // eax
  unsigned int v44; // r15d
  __int64 OffsetFromHeader; // r9
  struct _DYNVC_HEADER *v46; // rcx
  unsigned int ChannelId; // eax
  __int64 v48; // r8
  char *v49; // rcx
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // eax
  int v54; // eax
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  const char **v58; // [rsp+30h] [rbp-C1h]
  const char **v59; // [rsp+40h] [rbp-B1h]
  const char **v60; // [rsp+48h] [rbp-A9h]
  int v61; // [rsp+50h] [rbp-A1h] BYREF
  const char *v62; // [rsp+58h] [rbp-99h] BYREF
  const char *v63; // [rsp+60h] [rbp-91h] BYREF
  int v64; // [rsp+68h] [rbp-89h] BYREF
  char *v65; // [rsp+70h] [rbp-81h] BYREF
  const char *v66; // [rsp+78h] [rbp-79h] BYREF
  const char *v67; // [rsp+80h] [rbp-71h] BYREF
  __int16 v68; // [rsp+88h] [rbp-69h]
  const char *v69; // [rsp+90h] [rbp-61h] BYREF
  const char *v70; // [rsp+98h] [rbp-59h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-51h]
  __int128 v72; // [rsp+A8h] [rbp-49h] BYREF
  __int128 v73; // [rsp+B8h] [rbp-39h]
  __int128 v74; // [rsp+C8h] [rbp-29h]
  __int64 v75; // [rsp+D8h] [rbp-19h]
  unsigned __int64 v76; // [rsp+E0h] [rbp-11h] BYREF

  v76 = a2;
  v75 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 104);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  if ( (*(_BYTE *)(a1 - 64 + 108) & 0x10) != 0 )
  {
    v13 = -2147467260;
    if ( (unsigned int)CallbackContext > 3 )
    {
      v62 = "Failing call for disconnected stack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v10,
        (unsigned int)&word_1802885A6,
        v11,
        v12,
        (__int64)&v62);
    }
    goto LABEL_4;
  }
  v15 = *(_QWORD *)(a1 + 88);
  v13 = 0;
  v16 = a6;
  if ( !*(_DWORD *)(a1 + 248) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v64 = *(_DWORD *)(a1 + 600);
      v62 = (const char *)&v76;
      v65 = "Attempting to send bytes before share creation is complete.";
      v61 = a6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&word_1802897F6,
        v11,
        v12,
        (__int64)&v65,
        (__int64)&v61,
        (__int64)&v62,
        (__int64)&v64);
    }
    if ( (unsigned int)IsFakeChannelId(v76) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v62 = "Waiting for share creation completion event to send on fake channel...";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (unsigned int)&dword_18028D93C,
          v18,
          v12,
          (__int64)&v62);
      }
      v19 = CRDPWDUMXStack::WaitForSingleEvent((CRDPWDUMXStack *)(a1 - 64), *(void **)(a1 + 240), 0xFFFFFFFF);
      if ( v19 )
      {
        v13 = NTSTATUS2HR(v19);
        if ( v13 < 0 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_4;
          v61 = 2370;
          v62 = "Failed to wait for share creation completion event";
          v20 = (int *)byte_18028C6CB;
          v65 = "SendChannelData";
          v66 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v63 = "Error HResult failed";
          v60 = &v62;
          v59 = (const char **)&v65;
          v58 = &v66;
          v21 = &v63;
          goto LABEL_17;
        }
      }
      *(_DWORD *)(a1 + 248) = 1;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v22 = "Share creation completion signalled! Data will now be sent.";
        v23 = &word_180291216;
LABEL_23:
        v63 = v22;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v17,
          (_DWORD)v23,
          v18,
          v12,
          (__int64)&v63);
      }
    }
    else
    {
      if ( v17 != 0x6C7274636E6F63LL )
      {
        v13 = -2147418113;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_4;
        v61 = 2390;
        v63 = "Sending data on a non-fake channel before share completion is unexpected! Data will be dropped!";
        v20 = &dword_18028D334;
        v62 = "SendChannelData";
        v65 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v66 = "Error HResult failed";
        v60 = &v63;
        v59 = &v62;
        v58 = (const char **)&v65;
        v21 = &v66;
LABEL_17:
        v64 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v17,
          (_DWORD)v20,
          v18,
          v12,
          (__int64)v21,
          (__int64)&v64,
          (__int64)v58,
          (__int64)&v61,
          (__int64)v59,
          (__int64)v60);
        goto LABEL_4;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v22 = "Early conctrl packet is being sent. This is expected.";
        v23 = (__int16 *)&unk_18028D450;
        goto LABEL_23;
      }
    }
  }
  if ( v76 != 0x78667267706472LL )
  {
    if ( v76 == 0x646D63706472LL )
    {
      v34 = CRDPWDUMXStack::SendCommandChannelData((CRDPWDUMXStack *)(a1 - 64), a3);
    }
    else
    {
      if ( v76 != 0x63696C706472LL )
      {
        if ( v76 == 0x74706E69706472LL )
        {
          v13 = CRDPWDUMXStack::HandleInputStreamPDU((CRDPWDUMXStack *)(a1 - 64), a4, a3, v12);
          if ( v13 >= 0 || (unsigned int)CallbackContext <= 3 )
            goto LABEL_4;
          v63 = "SendChannelData";
          v27 = byte_18028F8BB;
          v28 = "Failed to handle Input stream PDU";
        }
        else
        {
          if ( v76 != 0x636E656C696172LL )
          {
            v35 = *(_DWORD *)(a1 + 412);
            if ( v35 )
            {
              v36 = 0;
              while ( 1 )
              {
                v37 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v36);
                if ( *(_QWORD *)(v37 + 8) == v76 )
                  break;
                v36 = (unsigned int)(v36 + 1);
                if ( (unsigned int)v36 >= v35 )
                  goto LABEL_55;
              }
              v38 = 1;
            }
            else
            {
              v37 = 0;
              v38 = 0;
            }
            v39 = v37 & -(__int64)(v38 != 0);
            if ( v39 )
            {
              v40 = *(_QWORD *)(a1 + 768);
              if ( v40
                && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40)
                && (unsigned int)CallbackContext > 4 )
              {
                v41 = a4;
                if ( a4 >= 0x10 )
                  v41 = 16;
                if ( v41 > 0xFFFF )
                  LOWORD(v41) = -1;
                v42 = *(_DWORD *)(a1 + 528) == 0;
                v68 = v41;
                v43 = a4 + 12;
                if ( v42 )
                  v43 = a4;
                v67 = (const char *)a3;
                v61 = v43;
                v63 = "CRDPWDUMXStack::SendChannelData";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                  0xFFFF,
                  (unsigned int)&dword_180292344,
                  v37,
                  v35,
                  (__int64)&v63,
                  (__int64)&v61,
                  (__int64)&v67);
              }
              if ( *(_DWORD *)(a1 + 528) )
              {
                v44 = *(_DWORD *)(v39 + 16);
                v62 = 0;
                v65 = 0;
                v64 = 0;
                if ( (unsigned int)CallbackContext > 5 )
                {
                  v63 = "Sending VC data over connected stream.";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    v40,
                    (unsigned int)&byte_18028A827,
                    v37,
                    v35,
                    (__int64)&v63);
                }
                if ( a6 > a4 && (unsigned int)CallbackContext > 5 )
                {
                  v63 = "Sending VC data total size is larger than write size.";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    v40,
                    (unsigned int)byte_180291719,
                    v37,
                    v35,
                    (__int64)&v63);
                }
                if ( !(unsigned int)o__stricmp_0(&v76, "DRDYNVC") )
                {
                  OffsetFromHeader = GetOffsetFromHeader((struct _DYNVC_HEADER *)a3);
                  if ( (unsigned __int8)((*a3 >> 4) - 2) <= 1u && !GetChannelId((struct _DYNVC_HEADER *)a3) )
                  {
                    ChannelId = GetChannelId(v46);
                    a3 += v48 + 2;
                    a4 += -2 - v48;
                    v44 = ChannelId;
                    v16 = -2 - v48 + a6;
                  }
                }
                (*(void (__fastcall **)(_QWORD, _QWORD, const char **, __int64))(**(_QWORD **)(a1 + 272) + 24LL))(
                  *(_QWORD *)(a1 + 272),
                  a4 + 12,
                  &v62,
                  OffsetFromHeader);
                (*(void (__fastcall **)(const char *, char **))(*(_QWORD *)v62 + 24LL))(v62, &v65);
                (*(void (__fastcall **)(const char *, int *))(*(_QWORD *)v62 + 56LL))(v62, &v64);
                v65 += v64;
                (*(void (__fastcall **)(const char *, _QWORD))(*(_QWORD *)v62 + 48LL))(v62, a4 + 12);
                *(_DWORD *)v65 = v44;
                v49 = v65;
                *((_DWORD *)v65 + 1) = v16;
                *((_DWORD *)v49 + 2) = a7;
                v65 += 12;
                memcpy_0(v65, a3, a4);
                v13 = (*(__int64 (__fastcall **)(_QWORD, const char *))(**(_QWORD **)(a1 + 272) + 40LL))(
                        *(_QWORD *)(a1 + 272),
                        v62);
                if ( v13 < 0 && (unsigned int)CallbackContext > 2 )
                {
                  v61 = 2507;
                  v63 = "WriteBuffer";
                  LODWORD(v66) = v13;
                  v69 = "SendChannelData";
                  v70 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
                  v67 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v50,
                    (unsigned int)&dword_18028B2FC,
                    v51,
                    v52,
                    (__int64)&v67,
                    (__int64)&v66,
                    (__int64)&v70,
                    (__int64)&v61,
                    (__int64)&v69,
                    (__int64)&v63);
                }
                TCntPtr<IRdpVCMgr>::SafeRelease(&v62);
              }
              else
              {
                LODWORD(v72) = 5;
                v53 = *(_DWORD *)(v39 + 16);
                LOBYTE(v75) = a5 == 0;
                DWORD1(v72) = v53;
                *((_QWORD *)&v73 + 1) = a3;
                LODWORD(v74) = a4;
                *(_QWORD *)((char *)&v74 + 4) = __PAIR64__(a7, a6);
                BYTE8(v72) = 0;
                v54 = WDLIB_ChannelWrite(v15, (__int64)&v72, v37, v35);
                if ( v54 )
                {
                  v13 = NTSTATUS2HR(v54);
                  if ( (unsigned int)CallbackContext > 2 )
                  {
                    LODWORD(v66) = 2530;
                    v67 = "SendChannelData";
                    v61 = v13;
                    v70 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
                    v69 = "Failed to write channel data";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                      v55,
                      (unsigned int)&dword_180288944,
                      v56,
                      v57,
                      (__int64)&v69,
                      (__int64)&v61,
                      (__int64)&v70,
                      (__int64)&v66,
                      (__int64)&v67);
                  }
                }
              }
            }
            else
            {
LABEL_55:
              if ( (unsigned int)CallbackContext > 3 )
              {
                v67 = "Ignoring send for unbound or disabled channel";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  1818845554,
                  (unsigned int)word_18028D22A,
                  v37,
                  v35,
                  (__int64)&v67);
              }
              v13 = 1;
            }
            goto LABEL_4;
          }
          v13 = CRDPWDUMXStack::HandleRailEncoderFakeVCPDU((CRDPWDUMXStack *)(a1 - 64), a4, a3, v12);
          if ( v13 >= 0 || (unsigned int)CallbackContext <= 3 )
            goto LABEL_4;
          v63 = "SendChannelData";
          v27 = byte_1802908C9;
          v28 = "Failed to handle RailEncoder fake VC PDU";
        }
LABEL_29:
        v62 = v28;
        v65 = "HResult failed but continue";
        v61 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v24,
          (_DWORD)v27,
          v25,
          v26,
          (__int64)&v65,
          (__int64)&v62,
          (__int64)&v61,
          (__int64)&v63);
        goto LABEL_4;
      }
      v34 = CRDPWDUMXStack::HandleLicPDU((CRDPWDUMXStack *)(a1 - 64), a3, a4, v12);
    }
    v13 = v34;
    goto LABEL_4;
  }
  if ( (*a3 & 0x30) != 0 )
  {
    v13 = CRDPWDUMXStack::HandleGFXStreamPDU((CRDPWDUMXStack *)(a1 - 64), a4, a3, v12);
    if ( v13 >= 0 || (unsigned int)CallbackContext <= 3 )
      goto LABEL_4;
    v63 = "SendChannelData";
    v27 = byte_18028975B;
    v28 = "Failed to handle reset Stream PDU";
    goto LABEL_29;
  }
  v29 = *(ShareClass **)(v15 + 128);
  if ( v29 )
  {
    v30 = ShareClass::SC_SendEncoderGraphicsPDU(v29, a3, a4);
    if ( !v30 )
      goto LABEL_4;
  }
  else
  {
    v30 = -1073741591;
  }
  v13 = NTSTATUS2HR(v30);
  if ( (unsigned int)CallbackContext > 2 )
  {
    v61 = 2413;
    v63 = "SendChannelData";
    v64 = v13;
    v62 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    v65 = "Failed to send the graphics data";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v31,
      (unsigned int)&word_18028DA6E,
      v32,
      v33,
      (__int64)&v65,
      (__int64)&v64,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v63);
  }
LABEL_4:
  LeaveCriticalSection(lpCriticalSection);
  if ( v13 == -2147467260 )
    return 1;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180127930  push    rbp
0x180127932  push    rbx
0x180127933  push    rsi
0x180127934  push    rdi
0x180127935  push    r12
0x180127937  push    r13
0x180127939  push    r14
0x18012793b  push    r15
0x18012793d  lea     rbp, [rsp-7]
0x180127942  sub     rsp, 0F8h
0x180127949  mov     rax, cs:__security_cookie
0x180127950  xor     rax, rsp
0x180127953  mov     [rbp+3Fh+var_48], rax
0x180127957  xorps   xmm0, xmm0
0x18012795a  mov     [rbp+3Fh+var_50], rdx
0x18012795e  xor     eax, eax
0x180127960  mov     r14, rcx
0x180127963  mov     [rbp+3Fh+var_58], rax
0x180127967  mov     esi, r9d
0x18012796a  lea     rax, [rcx+68h]
0x18012796e  mov     rdi, r8
0x180127971  mov     rcx, rax; lpCriticalSection
0x180127974  mov     [rbp+3Fh+lpCriticalSection], rax
0x180127978  movups  [rbp+3Fh+var_88], xmm0
0x18012797c  movups  [rbp+3Fh+var_78], xmm0
0x180127980  movups  [rbp+3Fh+var_68], xmm0
0x180127984  call    cs:__imp_EnterCriticalSection
0x18012798a  lea     r15, [r14-40h]
0x18012798e  test    byte ptr [r15+6Ch], 10h
0x180127993  jz      short loc_180127A03
0x180127995  mov     eax, cs:CallbackContext
0x18012799b  mov     ebx, 80004004h
0x1801279a0  cmp     eax, 3
0x1801279a3  jbe     short loc_1801279C7
0x1801279a5  lea     rax, aFailingCallFor; "Failing call for disconnected stack"
0x1801279ac  mov     [rsp+130h+var_D8], rax
0x1801279b1  lea     rdx, word_1802885A6
0x1801279b8  lea     rax, [rsp+130h+var_D8]
0x1801279bd  mov     [rsp+130h+var_110], rax
0x1801279c2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801279c7  mov     r13d, 1
0x1801279cd  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x1801279d1  call    cs:__imp_LeaveCriticalSection
0x1801279d7  cmp     ebx, 80004004h
0x1801279dd  cmovz   ebx, r13d
0x1801279e1  mov     eax, ebx
0x1801279e3  mov     rcx, [rbp+3Fh+var_48]
0x1801279e7  xor     rcx, rsp; StackCookie
0x1801279ea  call    __security_check_cookie
0x1801279ef  add     rsp, 0F8h
0x1801279f6  pop     r15
0x1801279f8  pop     r14
0x1801279fa  pop     r13
0x1801279fc  pop     r12
0x1801279fe  pop     rdi
0x1801279ff  pop     rsi
0x180127a00  pop     rbx
0x180127a01  pop     rbp
0x180127a02  retn
0x180127a03  mov     r13, [r14+58h]
0x180127a07  xor     ebx, ebx
0x180127a09  mov     r12d, [rbp+3Fh+arg_28]
0x180127a0d  cmp     [r14+0F8h], ebx
0x180127a14  jnz     loc_180127BE4
0x180127a1a  mov     eax, cs:CallbackContext
0x180127a20  cmp     eax, 4
0x180127a23  jbe     short loc_180127A7E
0x180127a25  mov     eax, [r14+258h]
0x180127a2c  lea     rdx, word_1802897F6
0x180127a33  mov     [rsp+130h+var_C8], eax
0x180127a37  lea     rax, [rbp+3Fh+var_50]
0x180127a3b  mov     [rsp+130h+var_D8], rax
0x180127a40  lea     rax, aAttemptingToSe; "Attempting to send bytes before share c"...
0x180127a47  mov     [rsp+130h+var_C0], rax
0x180127a4c  lea     rax, [rsp+130h+var_C8]
0x180127a51  mov     [rsp+130h+var_F8], rax
0x180127a56  lea     rax, [rsp+130h+var_D8]
0x180127a5b  mov     [rsp+130h+var_100], rax
0x180127a60  lea     rax, [rsp+130h+var_E0]
0x180127a65  mov     [rsp+130h+var_108], rax
0x180127a6a  lea     rax, [rsp+130h+var_C0]
0x180127a6f  mov     [rsp+130h+var_110], rax
0x180127a74  mov     [rsp+130h+var_E0], r12d
0x180127a79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180127a7e  mov     rcx, [rbp+3Fh+var_50]; unsigned __int64
0x180127a82  call    ?IsFakeChannelId@@YAH_K@Z; IsFakeChannelId(unsigned __int64)
0x180127a87  test    eax, eax
0x180127a89  jz      loc_180127BA4
0x180127a8f  mov     eax, cs:CallbackContext
0x180127a95  cmp     eax, 4
0x180127a98  jbe     short loc_180127ABC
0x180127a9a  lea     rax, aWaitingForShar; "Waiting for share creation completion e"...
0x180127aa1  mov     [rsp+130h+var_D8], rax
0x180127aa6  lea     rdx, dword_18028D93C
0x180127aad  lea     rax, [rsp+130h+var_D8]
0x180127ab2  mov     [rsp+130h+var_110], rax
0x180127ab7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180127abc  mov     rdx, [r14+0F0h]; void *
0x180127ac3  or      r8d, 0FFFFFFFFh; unsigned int
0x180127ac7  mov     rcx, r15; this
0x180127aca  call    ?WaitForSingleEvent@CRDPWDUMXStack@@QEAAJPEAXK@Z; CRDPWDUMXStack::WaitForSingleEvent(void *,ulong)
0x180127acf  test    eax, eax
0x180127ad1  jz      loc_180127B7E
0x180127ad7  mov     ecx, eax; int
0x180127ad9  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180127ade  mov     ebx, eax
0x180127ae0  test    eax, eax
0x180127ae2  jns     loc_180127B7E
0x180127ae8  mov     eax, cs:CallbackContext
0x180127aee  cmp     eax, 2
0x180127af1  jbe     loc_1801279C7
0x180127af7  lea     rax, aFailedToWaitFo; "Failed to wait for share creation compl"...
0x180127afe  mov     [rsp+130h+var_E0], 942h
0x180127b06  mov     [rsp+130h+var_D8], rax
0x180127b0b  lea     rdx, byte_18028C6CB
0x180127b12  lea     rax, aSendchanneldat; "SendChannelData"
0x180127b19  mov     [rsp+130h+var_C0], rax
0x180127b1e  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180127b25  mov     [rbp+3Fh+var_B8], rax
0x180127b29  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180127b30  mov     [rsp+130h+var_D0], rax
0x180127b35  lea     rax, [rsp+130h+var_D8]
0x180127b3a  mov     [rsp+130h+var_E8], rax
0x180127b3f  lea     rax, [rsp+130h+var_C0]
0x180127b44  mov     [rsp+130h+var_F0], rax
0x180127b49  lea     rax, [rsp+130h+var_E0]
0x180127b4e  mov     [rsp+130h+var_F8], rax
0x180127b53  lea     rax, [rbp+3Fh+var_B8]
0x180127b57  mov     [rsp+130h+var_100], rax
0x180127b5c  lea     rax, [rsp+130h+var_C8]
0x180127b61  mov     [rsp+130h+var_108], rax
0x180127b66  lea     rax, [rsp+130h+var_D0]
0x180127b6b  mov     [rsp+130h+var_110], rax
0x180127b70  mov     [rsp+130h+var_C8], ebx
0x180127b74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180127b79  jmp     loc_1801279C7
0x180127b7e  mov     dword ptr [r14+0F8h], 1
0x180127b89  mov     eax, cs:CallbackContext
0x180127b8f  cmp     eax, 4
0x180127b92  jbe     short loc_180127BE4
0x180127b94  lea     rax, aShareCreationC; "Share creation completion signalled! Da"...
0x180127b9b  lea     rdx, word_180291216
0x180127ba2  jmp     short loc_180127BD0
0x180127ba4  mov     rax, 6C7274636E6F63h
0x180127bae  cmp     rcx, rax
0x180127bb1  mov     eax, cs:CallbackContext
0x180127bb7  jnz     loc_180127C8B
0x180127bbd  cmp     eax, 4
0x180127bc0  jbe     short loc_180127BE4
0x180127bc2  lea     rax, aEarlyConctrlPa; "Early conctrl packet is being sent. Thi"...
0x180127bc9  lea     rdx, unk_18028D450
0x180127bd0  mov     [rsp+130h+var_D0], rax
0x180127bd5  lea     rax, [rsp+130h+var_D0]
0x180127bda  mov     [rsp+130h+var_110], rax
0x180127bdf  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180127be4  mov     rax, [rbp+3Fh+var_50]
0x180127be8  mov     rcx, 78667267706472h
0x180127bf2  cmp     rax, rcx
0x180127bf5  jnz     loc_180127DC3
0x180127bfb  test    byte ptr [rdi], 30h
0x180127bfe  jz      loc_180127D12
0x180127c04  mov     r8, rdi; unsigned __int8 *
0x180127c07  mov     edx, esi; unsigned int
0x180127c09  mov     rcx, r15; this
0x180127c0c  call    ?HandleGFXStreamPDU@CRDPWDUMXStack@@IEAAJKPEAE@Z; CRDPWDUMXStack::HandleGFXStreamPDU(ulong,uchar *)
0x180127c11  mov     ebx, eax
0x180127c13  test    eax, eax
0x180127c15  jns     loc_1801279C7
0x180127c1b  mov     eax, cs:CallbackContext
0x180127c21  cmp     eax, 3
0x180127c24  jbe     loc_1801279C7
0x180127c2a  lea     rax, aSendchanneldat; "SendChannelData"
0x180127c31  mov     [rsp+130h+var_D0], rax
0x180127c36  lea     rdx, byte_18028975B
0x180127c3d  lea     rax, aFailedToHandle; "Failed to handle reset Stream PDU"
0x180127c44  mov     [rsp+130h+var_D8], rax
0x180127c49  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180127c50  mov     [rsp+130h+var_C0], rax
0x180127c55  lea     rax, [rsp+130h+var_D0]
0x180127c5a  mov     [rsp+130h+var_F8], rax
0x180127c5f  lea     rax, [rsp+130h+var_E0]
0x180127c64  mov     [rsp+130h+var_100], rax
0x180127c69  lea     rax, [rsp+130h+var_D8]
0x180127c6e  mov     [rsp+130h+var_108], rax
0x180127c73  lea     rax, [rsp+130h+var_C0]
0x180127c78  mov     [rsp+130h+var_110], rax
0x180127c7d  mov     [rsp+130h+var_E0], ebx
0x180127c81  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180127c86  jmp     loc_1801279C7
0x180127c8b  mov     ebx, 8000FFFFh
0x180127c90  cmp     eax, 2
0x180127c93  jbe     loc_1801279C7
0x180127c99  lea     rax, aSendingDataOnA; "Sending data on a non-fake channel befo"...
0x180127ca0  mov     [rsp+130h+var_E0], 956h
0x180127ca8  mov     [rsp+130h+var_D0], rax
0x180127cad  lea     rdx, dword_18028D334
0x180127cb4  lea     rax, aSendchanneldat; "SendChannelData"
0x180127cbb  mov     [rsp+130h+var_D8], rax
0x180127cc0  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180127cc7  mov     [rsp+130h+var_C0], rax
0x180127ccc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180127cd3  mov     [rbp+3Fh+var_B8], rax
0x180127cd7  lea     rax, [rsp+130h+var_D0]
0x180127cdc  mov     [rsp+130h+var_E8], rax
0x180127ce1  lea     rax, [rsp+130h+var_D8]
0x180127ce6  mov     [rsp+130h+var_F0], rax
0x180127ceb  lea     rax, [rsp+130h+var_E0]
0x180127cf0  mov     [rsp+130h+var_F8], rax
0x180127cf5  lea     rax, [rsp+130h+var_C0]
0x180127cfa  mov     [rsp+130h+var_100], rax
0x180127cff  lea     rax, [rsp+130h+var_C8]
0x180127d04  mov     [rsp+130h+var_108], rax
0x180127d09  lea     rax, [rbp+3Fh+var_B8]
0x180127d0d  jmp     loc_180127B6B
0x180127d12  mov     rcx, [r13+80h]; this
0x180127d19  test    rcx, rcx
0x180127d1c  jz      short loc_180127D33
0x180127d1e  mov     r8d, esi; unsigned int
0x180127d21  mov     rdx, rdi; unsigned __int8 *
0x180127d24  call    ?SC_SendEncoderGraphicsPDU@ShareClass@@QEAAJPEAEK@Z; ShareClass::SC_SendEncoderGraphicsPDU(uchar *,ulong)
0x180127d29  test    eax, eax
0x180127d2b  jz      loc_1801279C7
0x180127d31  jmp     short loc_180127D38
0x180127d33  mov     eax, 0C00000E9h
0x180127d38  mov     ecx, eax; int
0x180127d3a  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x180127d3f  mov     ebx, eax
0x180127d41  mov     eax, cs:CallbackContext
0x180127d47  cmp     eax, 2
0x180127d4a  jbe     loc_1801279C7
0x180127d50  lea     rax, aSendchanneldat; "SendChannelData"
0x180127d57  mov     [rsp+130h+var_E0], 96Dh
0x180127d5f  mov     [rsp+130h+var_D0], rax
0x180127d64  lea     rdx, word_18028DA6E
0x180127d6b  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180127d72  mov     [rsp+130h+var_C8], ebx
0x180127d76  mov     [rsp+130h+var_D8], rax
0x180127d7b  lea     rax, aFailedToSendTh_4; "Failed to send the graphics data"
0x180127d82  mov     [rsp+130h+var_C0], rax
0x180127d87  lea     rax, [rsp+130h+var_D0]
0x180127d8c  mov     [rsp+130h+var_F0], rax
0x180127d91  lea     rax, [rsp+130h+var_E0]
0x180127d96  mov     [rsp+130h+var_F8], rax
0x180127d9b  lea     rax, [rsp+130h+var_D8]
0x180127da0  mov     [rsp+130h+var_100], rax
0x180127da5  lea     rax, [rsp+130h+var_C8]
0x180127daa  mov     [rsp+130h+var_108], rax
0x180127daf  lea     rax, [rsp+130h+var_C0]
0x180127db4  mov     [rsp+130h+var_110], rax
0x180127db9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180127dbe  jmp     loc_1801279C7
0x180127dc3  mov     rcx, 646D63706472h
0x180127dcd  cmp     rax, rcx
0x180127dd0  jnz     short loc_180127DE4
0x180127dd2  mov     rdx, rdi; unsigned __int8 *
0x180127dd5  mov     rcx, r15; this
0x180127dd8  call    ?SendCommandChannelData@CRDPWDUMXStack@@IEAAJPEAE@Z; CRDPWDUMXStack::SendCommandChannelData(uchar *)
0x180127ddd  mov     ebx, eax
0x180127ddf  jmp     loc_1801279C7
0x180127de4  mov     rcx, 63696C706472h
0x180127dee  cmp     rax, rcx
0x180127df1  jnz     short loc_180127E03
0x180127df3  mov     r8d, esi; unsigned int
0x180127df6  mov     rdx, rdi; unsigned __int8 *
0x180127df9  mov     rcx, r15; this
0x180127dfc  call    ?HandleLicPDU@CRDPWDUMXStack@@IEAAJPEAEK@Z; CRDPWDUMXStack::HandleLicPDU(uchar *,ulong)
0x180127e01  jmp     short loc_180127DDD
0x180127e03  mov     rcx, 74706E69706472h
0x180127e0d  cmp     rax, rcx
0x180127e10  jnz     short loc_180127E57
0x180127e12  mov     r8, rdi; unsigned __int8 *
0x180127e15  mov     edx, esi; unsigned int
0x180127e17  mov     rcx, r15; this
0x180127e1a  call    ?HandleInputStreamPDU@CRDPWDUMXStack@@IEAAJKPEAE@Z; CRDPWDUMXStack::HandleInputStreamPDU(ulong,uchar *)
0x180127e1f  mov     ebx, eax
0x180127e21  test    eax, eax
0x180127e23  jns     loc_1801279C7
0x180127e29  mov     eax, cs:CallbackContext
0x180127e2f  cmp     eax, 3
0x180127e32  jbe     loc_1801279C7
0x180127e38  lea     rax, aSendchanneldat; "SendChannelData"
0x180127e3f  mov     [rsp+130h+var_D0], rax
0x180127e44  lea     rdx, byte_18028F8BB
0x180127e4b  lea     rax, aFailedToHandle_0; "Failed to handle Input stream PDU"
0x180127e52  jmp     loc_180127C44
0x180127e57  mov     rcx, 636E656C696172h
0x180127e61  cmp     rax, rcx
0x180127e64  jnz     short loc_180127EAB
0x180127e66  mov     r8, rdi; unsigned __int8 *
0x180127e69  mov     edx, esi; unsigned int
0x180127e6b  mov     rcx, r15; this
0x180127e6e  call    ?HandleRailEncoderFakeVCPDU@CRDPWDUMXStack@@IEAAJKPEAE@Z; CRDPWDUMXStack::HandleRailEncoderFakeVCPDU(ulong,uchar *)
0x180127e73  mov     ebx, eax
0x180127e75  test    eax, eax
0x180127e77  jns     loc_1801279C7
0x180127e7d  mov     eax, cs:CallbackContext
0x180127e83  cmp     eax, 3
0x180127e86  jbe     loc_1801279C7
0x180127e8c  lea     rax, aSendchanneldat; "SendChannelData"
0x180127e93  mov     [rsp+130h+var_D0], rax
  ... truncated ...
```
