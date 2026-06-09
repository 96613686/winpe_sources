# CRDPWDUMXStack::WDShareConnectionWorker(void)

- ea: `0x18012f880`
- end: `0x1801307ba`
- name: `?WDShareConnectionWorker@CRDPWDUMXStack@@IEAAJXZ`
- size: `3898`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180126d70`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000146c`
- `0x18000202c`
- `0x180002170`
- `0x1800023e4`
- `0x18000ce04`
- `0x180050dbc`
- `0x1800523a0`
- `0x180069c48`
- `0x18007e9e0`
- `0x18007f42c`
- `0x180110750`
- `0x180121444`
- `0x18012b69c`
- `0x18012caf8`
- `0x18012d824`
- `0x18012eab0`
- `0x18012f2ac`
- `0x18012f880`
- `0x180130d28`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18012fd8a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18012fd8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180130586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801306e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180130586`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801306e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013033b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013060f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013033b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013060f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18012fd6b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18012fd6b`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffad`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffb7`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffc1`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffad`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffb7`
- `OLEAUT32!__imp_VariantInit` at `0x18012ffc1`
- `OLEAUT32!__imp_VariantClear` at `0x1801301b4`
- `OLEAUT32!__imp_VariantClear` at `0x1801301be`
- `OLEAUT32!__imp_VariantClear` at `0x1801301c8`
- `OLEAUT32!__imp_VariantClear` at `0x1801301b4`
- `OLEAUT32!__imp_VariantClear` at `0x1801301be`
- `OLEAUT32!__imp_VariantClear` at `0x1801301c8`

## string_xrefs

- `0x18012fe6e`: `Failed to QI for Net security stream from connected stream`
- `0x1801304ed`: `Waiting for connection completion`
- `0x18012f9d9`: `Failed to query property CONN_PROPERTY_START_DIRECTLY_WITH_SIDE_TRANSPORT`
- `0x18012f9b5`: `StartDirectlyWithSideTransport`
- `0x18012fb0e`: `Failed to allocate the stream read buffer`
- `0x18012fa6c`: `Failed to open the stream`
- `0x18012fc8b`: `Skip legacy protocol is TRUE. Starting CONCTRL before any packets are sent.`
- `0x18012fbdf`: `Failed to queue a socket read`
- `0x18013000a`: `Setting disconnect reason and HRESULT based on the values from the security stream.`
- `0x18012ff5d`: `Wait for connection sequence timeout, but Security Filter failure was reported`
- `0x1801304c5`: `Security exchange failed`
- `0x180130561`: `Connection completion wait completed`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::WDShareConnectionWorker(CRDPWDUMXStack *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v3; // edi
  int v4; // r14d
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  DWORD v28; // esi
  int v29; // r8d
  int v30; // r9d
  DWORD v31; // ecx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // rcx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int *v56; // rdx
  const char *v57; // rax
  int v58; // eax
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  unsigned int v62; // eax
  unsigned int v63; // r8d
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  int started; // eax
  unsigned int v74; // r8d
  int v75; // r9d
  unsigned int v76; // esi
  int v77; // ecx
  int v78; // r8d
  int v79; // r9d
  __int64 v80; // rcx
  LONG lVal; // [rsp+50h] [rbp-B0h] BYREF
  const char *v83; // [rsp+58h] [rbp-A8h] BYREF
  const char *v84; // [rsp+60h] [rbp-A0h] BYREF
  const char *v85; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-90h] BYREF
  int v87; // [rsp+80h] [rbp-80h] BYREF
  LONG v88; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  int v90; // [rsp+90h] [rbp-70h] BYREF
  LONG v91; // [rsp+94h] [rbp-6Ch] BYREF
  LONG v92; // [rsp+98h] [rbp-68h] BYREF
  __int64 v93; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v94; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v96; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG v97; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v98; // [rsp+F8h] [rbp-8h] BYREF
  HANDLE Handles[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v100[592]; // [rsp+110h] [rbp+10h] BYREF

  v88 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 78);
  v91 = 0;
  v92 = 0;
  v3 = 0;
  v90 = 0;
  v4 = 0;
  v89 = 0;
  v98 = 0;
  v93 = 0;
  v94 = 0;
  *(_OWORD *)Handles = 0;
  if ( !v2 )
    goto LABEL_9;
  v5 = (**v2)(v2, &IID_IRDPCollection, &v94);
  if ( v5 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v84 = "WDShareConnectionWorker";
      v83 = "Failed to QI for RDP Collection from Platfornm Context";
      v87 = 6090;
      *(_QWORD *)&ActivityId.Data1 = "Error HResult failed";
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      lVal = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&word_18028ACE6,
        v6,
        v7,
        (__int64)&ActivityId,
        (__int64)&lVal,
        (__int64)&v85,
        (__int64)&v87,
        (__int64)&v84,
        (__int64)&v83);
    }
    goto LABEL_97;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v94 + 32LL))(
         v94,
         L"StartDirectlyWithSideTransport",
         &v90);
  if ( v8 < 0 && (unsigned int)CallbackContext > 3 )
  {
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    v85 = "Failed to query property CONN_PROPERTY_START_DIRECTLY_WITH_SIDE_TRANSPORT";
    lVal = v8;
    v84 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v8,
      (unsigned int)&byte_180289E97,
      v9,
      v10,
      (__int64)&v84,
      (__int64)&v85,
      (__int64)&lVal,
      (__int64)&ActivityId);
  }
  if ( !v90 )
  {
LABEL_9:
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 42) + 56LL))(
            *((_QWORD *)this + 42),
            ((unsigned __int64)this + 72) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    if ( v11 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v85 = "WDShareConnectionWorker";
        *(_QWORD *)&ActivityId.Data1 = "Failed to open the stream";
        lVal = 6100;
        v83 = "Error HResult failed";
        v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v87 = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)byte_18028A545,
          v12,
          v13,
          (__int64)&v83,
          (__int64)&v87,
          (__int64)&v84,
          (__int64)&lVal,
          (__int64)&v85,
          (__int64)&ActivityId);
      }
      goto LABEL_97;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 42) + 24LL))(
            *((_QWORD *)this + 42),
            1920,
            &v89);
    if ( v14 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v85 = "WDShareConnectionWorker";
        *(_QWORD *)&ActivityId.Data1 = "Failed to allocate the stream read buffer";
        lVal = 6104;
        v83 = "Error HResult failed";
        v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v87 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&word_180288466,
          v15,
          v16,
          (__int64)&v83,
          (__int64)&v87,
          (__int64)&v84,
          (__int64)&lVal,
          (__int64)&v85,
          (__int64)&ActivityId);
      }
      goto LABEL_97;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 48LL))(v89, 1920);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v89 + 64LL))(v89, 0);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v89 + 80LL))(v89, 0);
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42), v89);
    if ( v17 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v85 = "WDShareConnectionWorker";
        *(_QWORD *)&ActivityId.Data1 = "Failed to queue a socket read";
        lVal = 6112;
        v83 = "Error HResult failed";
        v84 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v87 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v17,
          (unsigned int)&unk_1802922A0,
          v18,
          v19,
          (__int64)&v83,
          (__int64)&v87,
          (__int64)&v84,
          (__int64)&lVal,
          (__int64)&v85,
          (__int64)&ActivityId);
      }
      goto LABEL_97;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    v89 = 0;
  }
  if ( *((_DWORD *)this + 148) )
  {
    memset_0(v100, 0, 0x248u);
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&ActivityId.Data1 = "Skip legacy protocol is TRUE. Starting CONCTRL before any packets are sent.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v20,
        (unsigned int)byte_18028F023,
        v21,
        v22,
        (__int64)&ActivityId);
    }
    if ( v90 )
      v23 = *((_QWORD *)this + 42);
    else
      v23 = 0;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 63) + 80LL))(*((_QWORD *)this + 63), v23);
    (*(void (__fastcall **)(char *, _BYTE *))(*((_QWORD *)this + 8) + 72LL))((char *)this + 64, v100);
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&ActivityId.Data1 = "ConnectionControl channel started before any packet is received.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v24,
        (unsigned int)&word_18028CA36,
        v25,
        v26,
        (__int64)&ActivityId);
    }
    v27 = **((_QWORD **)this + 19);
    *(_DWORD *)(v27 + 272) = 34;
    *(_DWORD *)(v27 + 276) = 3;
  }
  Handles[0] = *((HANDLE *)this + 34);
  Handles[1] = *((HANDLE *)this + 35);
  v28 = WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 60) != 0 ? 90000 : 30000);
  ActivityId = *(GUID *)((char *)this + 868);
  EventActivityIdControl(2u, &ActivityId);
  v31 = v28;
  if ( v28 )
  {
    if ( v28 == 1 )
    {
      v3 = -1073086458;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_97;
      *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
      LODWORD(v83) = 6169;
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      lVal = NTSTATUS2HR(-1073086458);
      v56 = (int *)byte_18028A439;
      v57 = "Aborting connection sequence";
    }
    else
    {
      if ( v28 != 258 )
      {
        v3 = -1073741823;
        if ( (unsigned int)CallbackContext > 2 )
        {
          lVal = v28;
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          v87 = 6250;
          v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          LODWORD(v83) = NTSTATUS2HR(-1073741823);
          v84 = "Unexpected wait result";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v32,
            (unsigned int)&dword_18028C364,
            v33,
            v34,
            (__int64)&v84,
            (__int64)&v83,
            (__int64)&v85,
            (__int64)&v87,
            (__int64)&ActivityId,
            (__int64)&lVal);
        }
        goto LABEL_97;
      }
      v35 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 42);
      if ( v35 )
      {
        v36 = (**v35)(v35, &IID_IRDPENCNetSecurityStream, &v93);
        if ( v36 < 0 && (unsigned int)CallbackContext > 3 )
        {
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          v85 = "Failed to QI for Net security stream from connected stream";
          LODWORD(v83) = v36;
          v84 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v36,
            (unsigned int)word_180289292,
            v37,
            v38,
            (__int64)&v84,
            (__int64)&v85,
            (__int64)&v83,
            (__int64)&ActivityId);
        }
      }
      if ( v93
        && (*(int (__fastcall **)(__int64, LONG *, LONG *, LONG *))(*(_QWORD *)v93 + 80LL))(v93, &v88, &v91, &v92) >= 0
        && v88 )
      {
        v3 = -1073086458;
        memset(&pvarg, 0, sizeof(pvarg));
        memset(&v96, 0, sizeof(v96));
        memset(&v97, 0, sizeof(v97));
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v83) = v88;
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          lVal = 6200;
          v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v87 = NTSTATUS2HR(-1073086458);
          v84 = "Wait for connection sequence timeout, but Security Filter failure was reported";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v39,
            (unsigned int)&byte_18028F787,
            v40,
            v41,
            (__int64)&v84,
            (__int64)&v87,
            (__int64)&v85,
            (__int64)&lVal,
            (__int64)&ActivityId,
            (__int64)&v83);
        }
        VariantInit(&pvarg);
        VariantInit(&v96);
        VariantInit(&v97);
        pvarg.lVal = v88;
        v96.lVal = v91;
        v97.lVal = v92;
        pvarg.vt = 19;
        v96.vt = 19;
        v97.vt = 19;
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v83) = v96.lVal;
          lVal = pvarg.lVal;
          *(_QWORD *)&ActivityId.Data1 = "Setting disconnect reason and HRESULT based on the values from the security stream.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            19,
            (unsigned int)&unk_18028F548,
            v42,
            v43,
            (__int64)&ActivityId,
            (__int64)&lVal,
            (__int64)&v83);
        }
        v44 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 88LL))(
                *((_QWORD *)this + 16),
                L"DisconnectReason",
                &pvarg);
        if ( v44 < 0 && (unsigned int)CallbackContext > 3 )
        {
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          v85 = "Failed to set property CONN_PROPERTY_DISCONNECT_REASON";
          LODWORD(v83) = v44;
          v84 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v44,
            (unsigned int)&dword_18028D964,
            v45,
            v46,
            (__int64)&v84,
            (__int64)&v85,
            (__int64)&v83,
            (__int64)&ActivityId);
        }
        v47 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 88LL))(
                *((_QWORD *)this + 16),
                L"DisconnectHresult",
                &v96);
        if ( v47 < 0 && (unsigned int)CallbackContext > 3 )
        {
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          v85 = "Failed to set property CONN_PROPERTY_DISCONNECT_HRESULT";
          LODWORD(v83) = v47;
          v84 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v47,
            (unsigned int)&dword_18028EE44,
            v48,
            v49,
            (__int64)&v84,
            (__int64)&v85,
            (__int64)&v83,
            (__int64)&ActivityId);
        }
        v50 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 88LL))(
                *((_QWORD *)this + 16),
                L"DisconnectSubStatus",
                &v97);
        if ( v50 < 0 && (unsigned int)CallbackContext > 3 )
        {
          *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
          v85 = "Failed to set property CONN_PROPERTY_DISCONNECT_SUBSTATUS";
          LODWORD(v83) = v50;
          v84 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v50,
            (unsigned int)&word_18028E95E,
            v51,
            v52,
            (__int64)&v84,
            (__int64)&v85,
            (__int64)&v83,
            (__int64)&ActivityId);
        }
        VariantClear(&pvarg);
        VariantClear(&v96);
        VariantClear(&v97);
        goto LABEL_97;
      }
      v3 = -1073741643;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_97;
      *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
      LODWORD(v83) = 6243;
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      lVal = NTSTATUS2HR(-1073741643);
      v56 = (int *)byte_18028E5C1;
      v57 = "Wait for connection sequence timeout";
    }
LABEL_63:
    v84 = v57;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v53,
      (_DWORD)v56,
      v54,
      v55,
      (__int64)&v84,
      (__int64)&lVal,
      (__int64)&v85,
      (__int64)&v83,
      (__int64)&ActivityId);
    goto LABEL_97;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&ActivityId.Data1 = "hCPIEvent signaled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      0,
      (unsigned int)&word_18028FFA6,
      v29,
      v30,
      (__int64)&ActivityId);
  }
  v3 = *((_DWORD *)this + 67);
  if ( v3 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_97;
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6160;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(v3);
    v56 = (int *)&word_18028B726;
    v57 = "GCC error processing CPI";
    goto LABEL_63;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&ActivityId.Data1 = "CPI processed ok by GCC";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v31,
      (unsigned int)&byte_18028A7D7,
      v29,
      v30,
      (__int64)&ActivityId);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v4 = 1;
  if ( (*((_BYTE *)this + 108) & 0x10) != 0 )
  {
    v3 = -1073086458;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_97;
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6264;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(-1073086458);
    v56 = &dword_18028DF0C;
    v57 = "The connection is closing";
    goto LABEL_63;
  }
  v58 = CRDPWDUMXStack::WDExchangeUserData(this);
  v3 = v58;
  if ( v58 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_97;
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6272;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(v58);
    v56 = &dword_18028814C;
    v57 = "UserDataExchangeFailed";
    goto LABEL_63;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&ActivityId.Data1 = "Sending connection provider response";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v59,
      (unsigned int)&unk_180292818,
      v60,
      v61,
      (__int64)&ActivityId);
  }
  v62 = CRDPWDUMXStack::WDSendConnectProviderResponse(this);
  v3 = v62;
  if ( v62 )
  {
    CRDPWDUMXStack::LogTCPStateTransitionFailure(this, 3u, v63, 0x20u, v62);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_97;
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6289;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(v3);
    v56 = &dword_180291ADC;
    v57 = "Failed to send the connect response";
    goto LABEL_63;
  }
  CRDPWDUMXStack::LogTCPStateTransitionSuccess(this, 3u, 4u, 3u);
  if ( *((_DWORD *)this + 57) )
  {
    v3 = CRDPWDUMXStack::WDCompleteSecurityExchange(this);
    if ( v3 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_97;
      *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
      LODWORD(v83) = 6302;
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      lVal = NTSTATUS2HR(v3);
      v56 = (int *)&unk_18028C220;
      v57 = "Security exchange failed";
      goto LABEL_63;
    }
  }
  if ( !*((_DWORD *)this + 148) )
    CRDPWDUMXStack::EarlyStartConnectionControlChannel(this);
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&ActivityId.Data1 = "Waiting for connection completion";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v64,
      (unsigned int)byte_1802904AD,
      v65,
      v66,
      (__int64)&ActivityId);
  }
  v3 = CRDPWDUMXStack::WDWaitForConnectionCompletion(this);
  if ( v3 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_97;
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6321;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(v3);
    v56 = (int *)byte_180290575;
    v57 = "The connection event wait failed";
    goto LABEL_63;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    *(_QWORD *)&ActivityId.Data1 = "Connection completion wait completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v67,
      (unsigned int)byte_18028A3C1,
      v68,
      v69,
      (__int64)&ActivityId);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v3 = CRDPWDUMXStack::WDSetExperienceFromNetworkMetrics(this);
  if ( v3 && (unsigned int)CallbackContext > 2 )
  {
    *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
    LODWORD(v83) = 6340;
    v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
    lVal = NTSTATUS2HR(v3);
    v84 = "Failed to detect experience!";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v70,
      (unsigned int)&dword_1802921B4,
      v71,
      v72,
      (__int64)&v84,
      (__int64)&lVal,
      (__int64)&v85,
      (__int64)&v83,
      (__int64)&ActivityId);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  started = CRDPWDUMXStack::StartLicensing(this);
  v76 = started;
  if ( started < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      lVal = started;
      *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
      v84 = "FAILED to Start Licensing";
      LODWORD(v83) = 6350;
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_18028A4AD,
        v74,
        v75,
        (__int64)&v84,
        (__int64)&lVal,
        (__int64)&v85,
        (__int64)&v83,
        (__int64)&ActivityId);
    }
    CRDPWDUMXStack::LogTCPStateTransitionFailure(this, 0xBu, v74, 0x25u, v76);
    v3 = -2147467259;
  }
LABEL_97:
  if ( v89 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 32LL))(*((_QWORD *)this + 42));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
  }
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  if ( v3 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_QWORD *)&ActivityId.Data1 = "WDShareConnectionWorker";
      LODWORD(v83) = 6372;
      v85 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      lVal = NTSTATUS2HR(v3);
      v84 = "Initial connection sequnce failed with status";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v77,
        (unsigned int)&word_180290D36,
        v78,
        v79,
        (__int64)&v84,
        (__int64)&lVal,
        (__int64)&v85,
        (__int64)&v83,
        (__int64)&ActivityId);
    }
    CRDPWDUMXStack::WDHandleStackError(this, v3);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v94);
  v80 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v98);
  return v3;
}

```

## disassembly

```asm
0x18012f880  push    rbp
0x18012f882  push    rbx
0x18012f883  push    rsi
0x18012f884  push    rdi
0x18012f885  push    r12
0x18012f887  push    r13
0x18012f889  push    r14
0x18012f88b  push    r15
0x18012f88d  lea     rbp, [rsp-278h]
0x18012f895  sub     rsp, 378h
0x18012f89c  mov     rax, cs:__security_cookie
0x18012f8a3  xor     rax, rsp
0x18012f8a6  mov     [rbp+2B0h+var_50], rax
0x18012f8ad  xor     r15d, r15d
0x18012f8b0  lea     r12, aWdshareconnect; "WDShareConnectionWorker"
0x18012f8b7  mov     rbx, rcx
0x18012f8ba  mov     [rbp+2B0h+var_32C], r15d
0x18012f8be  mov     rcx, [rcx+270h]
0x18012f8c5  lea     r13, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012f8cc  mov     [rbp+2B0h+var_31C], r15d
0x18012f8d0  xorps   xmm0, xmm0
0x18012f8d3  mov     [rbp+2B0h+var_318], r15d
0x18012f8d7  mov     edi, r15d
0x18012f8da  mov     [rbp+2B0h+var_320], r15d
0x18012f8de  mov     r14d, r15d
0x18012f8e1  mov     [rbp+2B0h+var_328], r15
0x18012f8e5  lea     rsi, aHresultFailedB; "HResult failed but continue"
0x18012f8ec  mov     [rbp+2B0h+var_2B8], r15
0x18012f8f0  mov     [rbp+2B0h+var_310], r15
0x18012f8f4  mov     [rbp+2B0h+var_308], r15
0x18012f8f8  movups  xmmword ptr [rbp+2B0h+Handles], xmm0
0x18012f8fc  test    rcx, rcx
0x18012f8ff  jz      loc_18012FA31
0x18012f905  mov     rax, [rcx]
0x18012f908  lea     r8, [rbp+2B0h+var_308]
0x18012f90c  lea     rdx, IID_IRDPCollection
0x18012f913  mov     rax, [rax]
0x18012f916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f91b  mov     ecx, eax
0x18012f91d  test    eax, eax
0x18012f91f  jns     loc_18012F9AD
0x18012f925  mov     eax, cs:CallbackContext
0x18012f92b  cmp     eax, 2
0x18012f92e  jbe     loc_1801306AC
0x18012f934  lea     rax, aFailedToQiForR_0; "Failed to QI for RDP Collection from Pl"...
0x18012f93b  mov     [rsp+3B0h+var_350], r12
0x18012f940  mov     [rsp+3B0h+var_358], rax
0x18012f945  lea     rdx, word_18028ACE6
0x18012f94c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012f953  mov     [rbp+2B0h+var_330], 17CAh
0x18012f95a  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012f95f  lea     rax, [rsp+3B0h+var_358]
0x18012f964  mov     [rsp+3B0h+var_368], rax
0x18012f969  lea     rax, [rsp+3B0h+var_350]
0x18012f96e  mov     [rsp+3B0h+var_370], rax
0x18012f973  lea     rax, [rbp+2B0h+var_330]
0x18012f977  mov     [rsp+3B0h+var_378], rax
0x18012f97c  lea     rax, [rsp+3B0h+var_348]
0x18012f981  mov     [rsp+3B0h+var_380], rax
0x18012f986  lea     rax, [rsp+3B0h+var_360]
0x18012f98b  mov     [rsp+3B0h+var_388], rax
0x18012f990  lea     rax, [rsp+3B0h+ActivityId]
0x18012f995  mov     [rsp+3B0h+var_348], r13
0x18012f99a  mov     [rsp+3B0h+var_360], ecx
0x18012f99e  mov     qword ptr [rsp+3B0h+var_390], rax
0x18012f9a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18012f9a8  jmp     loc_1801306AC
0x18012f9ad  mov     rcx, [rbp+2B0h+var_308]
0x18012f9b1  lea     r8, [rbp+2B0h+var_320]
0x18012f9b5  lea     rdx, aStartdirectlyw; "StartDirectlyWithSideTransport"
0x18012f9bc  mov     rax, [rcx]
0x18012f9bf  mov     rax, [rax+20h]
0x18012f9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f9c8  mov     ecx, eax
0x18012f9ca  test    eax, eax
0x18012f9cc  jns     short loc_18012FA27
0x18012f9ce  mov     eax, cs:CallbackContext
0x18012f9d4  cmp     eax, 3
0x18012f9d7  jbe     short loc_18012FA27
0x18012f9d9  lea     rax, aFailedToQueryP; "Failed to query property CONN_PROPERTY_"...
0x18012f9e0  mov     qword ptr [rsp+3B0h+ActivityId.Data1], r12
0x18012f9e5  mov     [rsp+3B0h+var_348], rax
0x18012f9ea  lea     rdx, byte_180289E97
0x18012f9f1  lea     rax, [rsp+3B0h+ActivityId]
0x18012f9f6  mov     [rsp+3B0h+var_360], ecx
0x18012f9fa  mov     [rsp+3B0h+var_378], rax
0x18012f9ff  lea     rax, [rsp+3B0h+var_360]
0x18012fa04  mov     [rsp+3B0h+var_380], rax
0x18012fa09  lea     rax, [rsp+3B0h+var_348]
0x18012fa0e  mov     [rsp+3B0h+var_388], rax
0x18012fa13  lea     rax, [rsp+3B0h+var_350]
0x18012fa18  mov     qword ptr [rsp+3B0h+var_390], rax
0x18012fa1d  mov     [rsp+3B0h+var_350], rsi
0x18012fa22  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18012fa27  cmp     [rbp+2B0h+var_320], r15d
0x18012fa2b  jnz     loc_18012FC62
0x18012fa31  mov     r9, [rbx+150h]
0x18012fa38  lea     rcx, [rbx+48h]
0x18012fa3c  mov     rax, rbx
0x18012fa3f  neg     rax
0x18012fa42  mov     r8, [r9]
0x18012fa45  sbb     rdx, rdx
0x18012fa48  and     rdx, rcx
0x18012fa4b  mov     rcx, r9
0x18012fa4e  mov     rax, [r8+38h]
0x18012fa52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fa57  mov     ecx, eax
0x18012fa59  test    eax, eax
0x18012fa5b  jns     short loc_18012FADB
0x18012fa5d  mov     eax, cs:CallbackContext
0x18012fa63  cmp     eax, 2
0x18012fa66  jbe     loc_1801306AC
0x18012fa6c  lea     rax, aFailedToOpenTh; "Failed to open the stream"
0x18012fa73  mov     [rsp+3B0h+var_348], r12
0x18012fa78  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012fa7d  lea     rdx, byte_18028A545
0x18012fa84  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012fa8b  mov     [rsp+3B0h+var_360], 17D4h
0x18012fa93  mov     [rsp+3B0h+var_358], rax
0x18012fa98  lea     rax, [rsp+3B0h+ActivityId]
0x18012fa9d  mov     [rsp+3B0h+var_368], rax
0x18012faa2  lea     rax, [rsp+3B0h+var_348]
0x18012faa7  mov     [rsp+3B0h+var_370], rax
0x18012faac  lea     rax, [rsp+3B0h+var_360]
0x18012fab1  mov     [rsp+3B0h+var_378], rax
0x18012fab6  lea     rax, [rsp+3B0h+var_350]
0x18012fabb  mov     [rsp+3B0h+var_380], rax
0x18012fac0  lea     rax, [rbp+2B0h+var_330]
0x18012fac4  mov     [rsp+3B0h+var_388], rax
0x18012fac9  lea     rax, [rsp+3B0h+var_358]
0x18012face  mov     [rsp+3B0h+var_350], r13
0x18012fad3  mov     [rbp+2B0h+var_330], ecx
0x18012fad6  jmp     loc_18012F99E
0x18012fadb  mov     rcx, [rbx+150h]
0x18012fae2  lea     r8, [rbp+2B0h+var_328]
0x18012fae6  mov     esi, 780h
0x18012faeb  mov     edx, esi
0x18012faed  mov     rax, [rcx]
0x18012faf0  mov     rax, [rax+18h]
0x18012faf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012faf9  mov     ecx, eax
0x18012fafb  test    eax, eax
0x18012fafd  jns     short loc_18012FB7D
0x18012faff  mov     eax, cs:CallbackContext
0x18012fb05  cmp     eax, 2
0x18012fb08  jbe     loc_1801306AC
0x18012fb0e  lea     rax, aFailedToAlloca_2; "Failed to allocate the stream read buff"...
0x18012fb15  mov     [rsp+3B0h+var_348], r12
0x18012fb1a  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012fb1f  lea     rdx, word_180288466
0x18012fb26  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012fb2d  mov     [rsp+3B0h+var_360], 17D8h
0x18012fb35  mov     [rsp+3B0h+var_358], rax
0x18012fb3a  lea     rax, [rsp+3B0h+ActivityId]
0x18012fb3f  mov     [rsp+3B0h+var_368], rax
0x18012fb44  lea     rax, [rsp+3B0h+var_348]
0x18012fb49  mov     [rsp+3B0h+var_370], rax
0x18012fb4e  lea     rax, [rsp+3B0h+var_360]
0x18012fb53  mov     [rsp+3B0h+var_378], rax
0x18012fb58  lea     rax, [rsp+3B0h+var_350]
0x18012fb5d  mov     [rsp+3B0h+var_380], rax
0x18012fb62  lea     rax, [rbp+2B0h+var_330]
0x18012fb66  mov     [rsp+3B0h+var_388], rax
0x18012fb6b  lea     rax, [rsp+3B0h+var_358]
0x18012fb70  mov     [rsp+3B0h+var_350], r13
0x18012fb75  mov     [rbp+2B0h+var_330], ecx
0x18012fb78  jmp     loc_18012F99E
0x18012fb7d  mov     rcx, [rbp+2B0h+var_328]
0x18012fb81  mov     edx, esi
0x18012fb83  mov     rax, [rcx]
0x18012fb86  mov     rax, [rax+30h]
0x18012fb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fb8f  mov     rcx, [rbp+2B0h+var_328]
0x18012fb93  xor     edx, edx
0x18012fb95  mov     rax, [rcx]
0x18012fb98  mov     rax, [rax+40h]
0x18012fb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fba1  mov     rcx, [rbp+2B0h+var_328]
0x18012fba5  xor     edx, edx
0x18012fba7  mov     rax, [rcx]
0x18012fbaa  mov     rax, [rax+50h]
0x18012fbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fbb3  mov     rcx, [rbx+150h]
0x18012fbba  mov     rdx, [rbp+2B0h+var_328]
0x18012fbbe  mov     rax, [rcx]
0x18012fbc1  mov     rax, [rax+30h]
0x18012fbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fbca  mov     ecx, eax
0x18012fbcc  test    eax, eax
0x18012fbce  jns     short loc_18012FC4E
0x18012fbd0  mov     eax, cs:CallbackContext
0x18012fbd6  cmp     eax, 2
0x18012fbd9  jbe     loc_1801306AC
0x18012fbdf  lea     rax, aFailedToQueueA; "Failed to queue a socket read"
0x18012fbe6  mov     [rsp+3B0h+var_348], r12
0x18012fbeb  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012fbf0  lea     rdx, unk_1802922A0
0x18012fbf7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012fbfe  mov     [rsp+3B0h+var_360], 17E0h
0x18012fc06  mov     [rsp+3B0h+var_358], rax
0x18012fc0b  lea     rax, [rsp+3B0h+ActivityId]
0x18012fc10  mov     [rsp+3B0h+var_368], rax
0x18012fc15  lea     rax, [rsp+3B0h+var_348]
0x18012fc1a  mov     [rsp+3B0h+var_370], rax
0x18012fc1f  lea     rax, [rsp+3B0h+var_360]
0x18012fc24  mov     [rsp+3B0h+var_378], rax
0x18012fc29  lea     rax, [rsp+3B0h+var_350]
0x18012fc2e  mov     [rsp+3B0h+var_380], rax
0x18012fc33  lea     rax, [rbp+2B0h+var_330]
0x18012fc37  mov     [rsp+3B0h+var_388], rax
0x18012fc3c  lea     rax, [rsp+3B0h+var_358]
0x18012fc41  mov     [rsp+3B0h+var_350], r13
0x18012fc46  mov     [rbp+2B0h+var_330], ecx
0x18012fc49  jmp     loc_18012F99E
0x18012fc4e  mov     rcx, [rbp+2B0h+var_328]
0x18012fc52  mov     rax, [rcx]
0x18012fc55  mov     rax, [rax+10h]
0x18012fc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fc5e  mov     [rbp+2B0h+var_328], r15
0x18012fc62  cmp     [rbx+250h], r15d
0x18012fc69  jz      loc_18012FD31
0x18012fc6f  xor     edx, edx; Val
0x18012fc71  lea     rcx, [rbp+2B0h+var_2A0]; void *
0x18012fc75  mov     r8d, 248h; Size
0x18012fc7b  call    memset_0
0x18012fc80  mov     eax, cs:CallbackContext
0x18012fc86  cmp     eax, 4
0x18012fc89  jbe     short loc_18012FCAD
0x18012fc8b  lea     rax, aSkipLegacyProt; "Skip legacy protocol is TRUE. Starting "...
0x18012fc92  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012fc97  lea     rdx, byte_18028F023
0x18012fc9e  lea     rax, [rsp+3B0h+ActivityId]
0x18012fca3  mov     qword ptr [rsp+3B0h+var_390], rax
0x18012fca8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18012fcad  mov     rcx, [rbx+1F8h]
0x18012fcb4  mov     rax, [rcx]
0x18012fcb7  cmp     [rbp+2B0h+var_320], r15d
0x18012fcbb  jz      short loc_18012FCC6
0x18012fcbd  mov     rdx, [rbx+150h]
0x18012fcc4  jmp     short loc_18012FCC9
0x18012fcc6  mov     rdx, r15
0x18012fcc9  mov     rax, [rax+50h]
0x18012fccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fcd2  lea     rcx, [rbx+40h]
0x18012fcd6  mov     rax, [rcx]
0x18012fcd9  lea     rdx, [rbp+2B0h+var_2A0]
0x18012fcdd  mov     rax, [rax+48h]
0x18012fce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012fce6  mov     eax, cs:CallbackContext
0x18012fcec  cmp     eax, 4
0x18012fcef  jbe     short loc_18012FD13
0x18012fcf1  lea     rax, aConnectioncont_7; "ConnectionControl channel started befor"...
0x18012fcf8  mov     qword ptr [rsp+3B0h+ActivityId.Data1], rax
0x18012fcfd  lea     rdx, word_18028CA36
0x18012fd04  lea     rax, [rsp+3B0h+ActivityId]
0x18012fd09  mov     qword ptr [rsp+3B0h+var_390], rax
0x18012fd0e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18012fd13  mov     rax, [rbx+98h]
0x18012fd1a  mov     rcx, [rax]
0x18012fd1d  mov     dword ptr [rcx+110h], 22h ; '"'
0x18012fd27  mov     dword ptr [rcx+114h], 3
0x18012fd31  mov     rax, [rbx+110h]
0x18012fd38  lea     rdx, [rbp+2B0h+Handles]; lpHandles
0x18012fd3c  mov     [rbp+2B0h+Handles], rax
0x18012fd40  mov     rax, [rbx+118h]
0x18012fd47  mov     [rbp+2B0h+Handles+8], rax
0x18012fd4b  mov     eax, [rbx+0F0h]
0x18012fd51  neg     eax
0x18012fd53  sbb     r9d, r9d
0x18012fd56  xor     r8d, r8d; bWaitAll
0x18012fd59  and     r9d, 0EA60h
0x18012fd60  add     r9d, 7530h; dwMilliseconds
0x18012fd67  lea     ecx, [r8+2]; nCount
0x18012fd6b  call    cs:__imp_WaitForMultipleObjects
0x18012fd71  movups  xmm0, xmmword ptr [rbx+364h]
0x18012fd78  lea     rdx, [rsp+3B0h+ActivityId]; ActivityId
0x18012fd7d  mov     ecx, 2; ControlCode
0x18012fd82  mov     esi, eax
0x18012fd84  movdqu  xmmword ptr [rsp+3B0h+ActivityId.Data1], xmm0
0x18012fd8a  call    cs:__imp_EventActivityIdControl
0x18012fd90  mov     ecx, esi
0x18012fd92  test    esi, esi
0x18012fd94  jz      loc_180130258
0x18012fd9a  sub     ecx, 1
0x18012fd9d  jz      loc_180130217
0x18012fda3  cmp     ecx, 101h
0x18012fda9  jz      loc_18012FE3B
0x18012fdaf  mov     eax, cs:CallbackContext
0x18012fdb5  mov     edi, 0C0000001h
0x18012fdba  cmp     eax, 2
0x18012fdbd  jbe     loc_1801306AC
0x18012fdc3  mov     ecx, edi; int
0x18012fdc5  mov     [rsp+3B0h+var_360], esi
0x18012fdc9  mov     qword ptr [rsp+3B0h+ActivityId.Data1], r12
0x18012fdce  mov     [rbp+2B0h+var_330], 186Ah
0x18012fdd5  mov     [rsp+3B0h+var_348], r13
0x18012fdda  call    ?NTSTATUS2HR@@YAJJ@Z; NTSTATUS2HR(long)
0x18012fddf  mov     dword ptr [rsp+3B0h+var_358], eax
0x18012fde3  lea     rdx, dword_18028C364
0x18012fdea  lea     rax, aUnexpectedWait; "Unexpected wait result"
  ... truncated ...
```
