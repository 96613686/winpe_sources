# CRdpDynVCMgr::Flush(void)

- ea: `0x18006a6e0`
- end: `0x18006b5e5`
- name: `?Flush@CRdpDynVCMgr@@UEAAJXZ`
- size: `3845`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *__hidden this)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18013e1f0`
- `0x18014a3a0`

## callees

- `0x18000116c`
- `0x180001308`
- `0x180001f84`
- `0x18000202c`
- `0x1800023e4`
- `0x1800024a8`
- `0x18000cdac`
- `0x18000cddc`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000e4ec`
- `0x18000e760`
- `0x180028a30`
- `0x1800290c4`
- `0x18002aafc`
- `0x18002ac80`
- `0x18002b14c`
- `0x180034f94`
- `0x1800449b0`
- `0x1800452e0`
- `0x1800454d0`
- `0x18004f5bc`
- `0x18006a6e0`
- `0x18006b5ec`
- `0x18013d860`
- `0x18014b300`
- `0x18014b340`
- `0x18014b9d8`
- `0x18014e1b4`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006a72c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006b4f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006a72c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006b4f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b564`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b579`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b564`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b579`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b247`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b2d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b247`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006b2d9`

## string_xrefs

- `0x18006a7c1`: `Flush Call during or after termination, ignoring`
- `0x18006aca5`: `SendChannelData for conctrl during demand active pending failed`
- `0x18006b1a3`: `Compute Failed`
- `0x18006b31e`: `Failed to set m_hFlushAfterCloseCompleteEvent because it's null`
- `0x18006b285`: `Failed to set m_hFlushCompleteEvent because it's null`

## pseudocode

```c
__int64 __fastcall CRdpDynVCMgr::Flush(CRdpDynVCMgr *this)
{
  __int64 v1; // rbx
  struct IRDPPerfCounterGeneric *v3; // rcx
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rdi
  DWORD TickCount; // eax
  int v8; // r9d
  int v9; // ecx
  DWORD v10; // r8d
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // ebx
  CRdpDynVCMgr *v16; // r12
  int v17; // r12d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rcx
  int v24; // eax
  bool v25; // zf
  int v26; // r8d
  struct CRdpDynVC *v27; // rbx
  unsigned int v28; // r8d
  int v29; // edx
  struct CRdpDynVCWriteChannelsClass *v30; // rbx
  CRdpDynVCWriteQueue *v31; // rcx
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // r8d
  unsigned int v36; // r9d
  unsigned __int8 *v37; // r8
  CRdpDynVC *v38; // rcx
  char *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  int v46; // ebx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  __int64 v50; // rax
  char *v51; // r8
  int v52; // r8d
  int v53; // r9d
  __int64 v54; // rcx
  int v55; // r8d
  int v56; // r9d
  unsigned int v57; // r8d
  int v58; // ebx
  RdpVCETWEvents *v59; // rcx
  int v60; // ecx
  int v61; // r8d
  int v62; // r9d
  int v63; // eax
  int v64; // eax
  int v65; // r8d
  int v66; // r9d
  int v67; // eax
  __int64 v68; // rcx
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  int v72; // eax
  int v73; // r8d
  int v74; // r9d
  int v75; // r8d
  int v76; // r9d
  void *v77; // rcx
  int v78; // r15d
  void *v79; // rcx
  __int64 v80; // rdx
  unsigned int v81; // eax
  __int64 v82; // rcx
  void (__fastcall *v83)(__int64, __int64); // rax
  __int64 v84; // rdx
  unsigned int v85; // eax
  int v86; // ecx
  int v87; // edi
  int v88; // r8d
  int v89; // r9d
  __int64 v90; // rcx
  ULONGLONG TickCount64; // rax
  __int64 v92; // rcx
  int v94; // [rsp+28h] [rbp-91h]
  CRdpDynVCWriteQueue *v95; // [rsp+50h] [rbp-69h] BYREF
  struct CRdpDynVCWorkitemClass *v96; // [rsp+58h] [rbp-61h] BYREF
  char *v97; // [rsp+60h] [rbp-59h] BYREF
  struct CRdpDynVCWriteChannelsClass *v98; // [rsp+68h] [rbp-51h] BYREF
  const char *v99; // [rsp+70h] [rbp-49h] BYREF
  struct CRdpDynVC *v100; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v101[2]; // [rsp+80h] [rbp-39h] BYREF
  const char *v102; // [rsp+88h] [rbp-31h] BYREF
  const char *v103; // [rsp+90h] [rbp-29h] BYREF
  int v104; // [rsp+98h] [rbp-21h]
  __int64 v105; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v106; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v107; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v108; // [rsp+B8h] [rbp-1h] BYREF
  DWORD v109; // [rsp+C0h] [rbp+7h]
  int v110; // [rsp+120h] [rbp+67h] BYREF
  const char *v111; // [rsp+128h] [rbp+6Fh] BYREF
  int v112; // [rsp+130h] [rbp+77h] BYREF
  const char *v113; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = 0;
  v3 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 2481);
  v110 = 0;
  v112 = 0;
  v4 = 0;
  v108 = 0;
  v5 = 0;
  v107 = 0;
  v6 = 0;
  v106 = 0;
  v105 = 0;
  PerfCounterSetRdpIntervalMarker(v3, 0, 0);
  TickCount = GetTickCount();
  v9 = *((_DWORD *)this + 4974);
  v109 = TickCount;
  v10 = TickCount;
  *((_DWORD *)this + 4974) = TickCount;
  v11 = v9 != 0 ? TickCount - v9 : 0;
  v104 = v11;
  if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v111) = v11;
    LODWORD(v113) = v10;
    v98 = (struct CRdpDynVCWriteChannelsClass *)"Flush Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)CallbackContext,
      (unsigned int)&word_180299216,
      v10,
      v8,
      (__int64)&v98,
      (__int64)&v113,
      (__int64)&v111);
  }
  v111 = (char *)this + 152;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 152));
  if ( (*((_BYTE *)this - 20) & 4) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v113 = "Flush Call during or after termination, ignoring";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v12,
        (unsigned int)byte_18029917B,
        v13,
        v14,
        (__int64)&v113);
    }
    v15 = -2147024884;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v111);
    v16 = (CRdpDynVCMgr *)((char *)this - 48);
    goto LABEL_91;
  }
  if ( *((_DWORD *)this + 4987) )
  {
    *((_DWORD *)this + 4987) = 0;
    v17 = 1;
    if ( *((_QWORD *)this + 25) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(&v106);
      v1 = *((_QWORD *)this + 25);
      v106 = v1;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v106);
    }
  }
  else
  {
    v17 = 0;
  }
  *((_DWORD *)this + 4954) = 1;
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v111);
  if ( v17 && v1 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      v111 = "Triggering shutdown on DVC data handling failure";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v18,
        (unsigned int)qword_1802991A0,
        v19,
        v20,
        (__int64)&v111);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 496LL))(v1, 307);
  }
  v21 = 0;
  LODWORD(v111) = 0;
  while ( 1 )
  {
    v22 = 80 * v21;
    *(_QWORD *)v101 = 80 * v21;
    if ( (_DWORD)v21 )
    {
      if ( !*(_DWORD *)((char *)this + v22 + 224) || *(_DWORD *)((char *)this + v22 + 228) )
        *(_DWORD *)((char *)this + v22 + 256) = 0;
      else
        *(_DWORD *)((char *)this + v22 + 256) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)((char *)this
                                                                                                + v22
                                                                                                + 192)
                                                                                  + 80LL))(*(_QWORD *)((char *)this + v22 + 192));
      goto LABEL_39;
    }
    v23 = *(_QWORD *)((char *)this + v22 + 200);
    LODWORD(v113) = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)v23 + 576LL))(v23, &v113);
    v25 = (_DWORD)v113 == 0;
    v26 = v24;
    if ( (_DWORD)v113 )
      v26 = 0;
    *(_DWORD *)((char *)this + v22 + 256) = v26;
    if ( v25
      || !v24
      || !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)((char *)this + v22 + 200) + 568LL))(
            *(_QWORD *)((char *)this + v22 + 200),
            32) )
    {
      goto LABEL_39;
    }
    v100 = 0;
    v96 = (CRdpDynVCMgr *)((char *)this + 544);
    v98 = 0;
    CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 544));
    v16 = (CRdpDynVCMgr *)((char *)this - 48);
    CRdpDynVCMgr::LookupChannel((CRdpDynVCMgr *)((char *)this - 48), "conctrl", &v100);
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v96);
    v27 = v100;
    v96 = (struct CRdpDynVCWorkitemClass *)(320LL * (unsigned int)v111);
    if ( v100 )
    {
      CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
      v28 = *((_DWORD *)v27 + 34);
      v29 = *((_DWORD *)v27 + 42);
      v97 = (char *)v96 + (_QWORD)this;
      CRdpDynVCWriteQueue::RemoveChannelItemById(
        (CRdpDynVCWriteQueue *)((char *)v96 + (_QWORD)this + 584),
        v29,
        v28,
        &v98);
      CTSCriticalSection::UnLock((CRdpDynVCMgr *)((char *)this + 1864));
      v16 = (CRdpDynVCMgr *)((char *)this - 48);
    }
    else
    {
      v97 = (char *)this + 320 * (unsigned int)v111;
    }
    v30 = v98;
    if ( v98 )
      break;
LABEL_34:
    TCntPtr<CFakeGfxProvider>::SafeRelease(&v100);
    v22 = *(_QWORD *)v101;
    LODWORD(v21) = (_DWORD)v111;
LABEL_39:
    v21 = (unsigned int)(v21 + 1);
    *(_DWORD *)((char *)this + v22 + 260) = *(_DWORD *)((char *)this + v22 + 256);
    LODWORD(v111) = v21;
    if ( (int)v21 >= 4 )
    {
      RdpVCETWEvents::OnFlushStart(
        *((RdpVCETWEvents **)this + 11),
        *((_DWORD *)this + 65),
        *((_DWORD *)this + 85),
        *((_DWORD *)this + 125));
      if ( (unsigned int)CallbackContext > 5 )
      {
        LODWORD(v111) = *((_DWORD *)this + 125);
        LODWORD(v113) = *((_DWORD *)this + 85);
        LODWORD(v97) = *((_DWORD *)this + 65);
        v95 = (CRdpDynVCWriteQueue *)"Flush Network Metrics Start";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v42,
          (unsigned int)&byte_1802990B7,
          v43,
          v44,
          (__int64)&v95,
          (__int64)&v97,
          (__int64)&v113,
          (__int64)&v111);
      }
      v98 = (CRdpDynVCMgr *)((char *)this + 1864);
      CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
      v111 = (char *)this + 1864;
      v16 = (CRdpDynVCMgr *)((char *)this - 48);
      CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
      v45 = 0;
      while ( !*((_DWORD *)this + 80 * v45 + 162) || !*((_DWORD *)this + 20 * v45 + 64) )
      {
        v45 = (unsigned int)(v45 + 1);
        if ( (int)v45 >= 4 )
        {
          v46 = 0;
          goto LABEL_47;
        }
      }
      v46 = 1;
LABEL_47:
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v111);
      if ( v46 )
      {
        v50 = 0;
        v51 = (char *)this + 256;
        LODWORD(v97) = 0;
        do
        {
          LODWORD(v111) = 0;
          LODWORD(v113) = 0;
          v101[0] = 0;
          LODWORD(v100) = 0;
          v95 = (CRdpDynVCMgr *)((char *)this + 320 * v50 + 584);
          v15 = CRdpDynVCWriteQueue::Compute(
                  v95,
                  (unsigned int *)&v51[80 * (unsigned int)v50],
                  (unsigned int *)&v111,
                  (unsigned int *)&v113,
                  v101,
                  (unsigned int *)&v100);
          if ( v15 < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v96) = 1547;
              v103 = "Compute Failed";
              v102 = "Flush";
              v99 = "Error HResult failed";
              v95 = (CRdpDynVCWriteQueue *)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              LODWORD(v97) = v15;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
                (unsigned int)&word_180299066,
                v52,
                v53,
                (__int64)&v99,
                (__int64)&v97,
                (__int64)&v95,
                (__int64)&v96,
                (__int64)&v102,
                (__int64)&v103);
            }
            goto LABEL_90;
          }
          v54 = *((_QWORD *)this + 2484);
          if ( v54 )
          {
            (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 32LL))(
              v54,
              112,
              (unsigned int)(8 * (_DWORD)v111));
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 2484) + 32LL))(
              *((_QWORD *)this + 2484),
              113,
              (unsigned int)(8 * (_DWORD)v113));
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 2484) + 32LL))(
              *((_QWORD *)this + 2484),
              114,
              8 * v101[0]);
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 2484) + 32LL))(
              *((_QWORD *)this + 2484),
              115,
              (unsigned int)(8 * (_DWORD)v100));
          }
          v15 = CRdpDynVCWriteQueue::FillTunnelsWithWorkitems(v95, *((_QWORD *)this + 237));
          if ( v15 < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v97) = 1558;
              v95 = (CRdpDynVCWriteQueue *)"FillTunnelsWithWorkitems";
              v99 = "Flush";
              v103 = "Error HResult failed";
              v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              LODWORD(v96) = v15;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
                (unsigned int)byte_180299015,
                v55,
                v56,
                (__int64)&v103,
                (__int64)&v96,
                (__int64)&v102,
                (__int64)&v97,
                (__int64)&v99,
                (__int64)&v95);
            }
LABEL_90:
            CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v98);
            goto LABEL_91;
          }
          v51 = (char *)this + 256;
          v50 = (unsigned int)((_DWORD)v97 + 1);
          LODWORD(v97) = v50;
        }
        while ( (int)v50 < 4 );
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v98);
        v57 = *((_DWORD *)this + 85) - *((_DWORD *)this + 84);
        v58 = *((_DWORD *)this + 125) - *((_DWORD *)this + 124);
        LODWORD(v113) = *((_DWORD *)this + 65) - *((_DWORD *)this + 64);
        v59 = (RdpVCETWEvents *)*((_QWORD *)this + 11);
        LODWORD(v111) = v57;
        RdpVCETWEvents::OnFlushCmplt(v59, (unsigned int)v113, v57, v58);
        if ( (unsigned int)CallbackContext > 5 )
        {
          LODWORD(v100) = (_DWORD)v111;
          v101[0] = (unsigned int)v113;
          v95 = (CRdpDynVCWriteQueue *)"Flush Network Metrics End";
          LODWORD(v97) = v58;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v60,
            (unsigned int)byte_180298F61,
            v61,
            v62,
            (__int64)&v95,
            (__int64)v101,
            (__int64)&v100,
            (__int64)&v97);
        }
        v63 = v104;
        *((_DWORD *)this + 4970) += v104;
        if ( (_DWORD)v111 )
        {
          if ( (_DWORD)v113 )
          {
            if ( v58 )
              *((_DWORD *)this + 4973) += v63;
            else
              *((_DWORD *)this + 4972) += v63;
          }
          else if ( !v58 )
          {
            *((_DWORD *)this + 4971) += v63;
          }
        }
        v64 = 0;
        LODWORD(v111) = 0;
        while ( 1 )
        {
          v15 = CRdpDynVCMgr::FlushOneTunnel((char *)this - 48, (unsigned int)v64);
          if ( v15 < 0 )
            break;
          v67 = v110;
          if ( v15 != 1 )
            v67 = 1;
          v110 = v67;
          v64 = (_DWORD)v111 + 1;
          LODWORD(v111) = v64;
          if ( v64 >= 4 )
          {
            v15 = 1;
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 144LL))(*((_QWORD *)this + 25)) > *((_DWORD *)this + 4986)
              && *((_DWORD *)this + 162)
              && *((_DWORD *)this + 65) != *((_DWORD *)this + 64) )
            {
              if ( (unsigned int)CallbackContext > 5 )
              {
                v68 = *((_QWORD *)this + 25);
                LODWORD(v111) = *((_DWORD *)this + 65) - *((_DWORD *)this + 64);
                v112 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 144LL))(v68);
                v113 = "Ask scheduler to call flush rightaway, can still send data down TcpMain";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v69,
                  (unsigned int)byte_180298F19,
                  v70,
                  v71,
                  (__int64)&v113,
                  (__int64)&v112,
                  (__int64)&v111);
              }
              v15 = 0;
              v112 = 1;
            }
            goto LABEL_81;
          }
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v111) = 1599;
          v95 = (CRdpDynVCWriteQueue *)"FlushOneTunnel";
          v99 = "Flush";
          v96 = (struct CRdpDynVCWorkitemClass *)"Error HResult failed";
          v98 = (struct CRdpDynVCWriteChannelsClass *)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          LODWORD(v113) = v15;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
            (unsigned int)&dword_180298FC4,
            v65,
            v66,
            (__int64)&v96,
            (__int64)&v113,
            (__int64)&v98,
            (__int64)&v111,
            (__int64)&v99,
            (__int64)&v95);
        }
      }
      else
      {
        if ( (unsigned int)CallbackContext > 5 )
        {
          v111 = "No Bytes Available to send.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v47,
            (unsigned int)byte_180299105,
            v48,
            v49,
            (__int64)&v111);
        }
        v15 = 1;
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v98);
LABEL_81:
        v72 = CRdpDynVCMgr::DoSoftSyncProtocol((CRdpDynVCMgr *)((char *)this - 48));
        if ( v72 < 0 && (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v113) = v72;
          v95 = (CRdpDynVCWriteQueue *)"Flush";
          v98 = (struct CRdpDynVCWriteChannelsClass *)"Soft sync failed, fatal.";
          LODWORD(v111) = 1648;
          v99 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
            (unsigned int)&byte_180298E87,
            v73,
            v74,
            (__int64)&v98,
            (__int64)&v113,
            (__int64)&v99,
            (__int64)&v111,
            (__int64)&v95);
        }
      }
      goto LABEL_91;
    }
  }
  v96 = 0;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
  v95 = (CRdpDynVCWriteQueue *)(v97 + 584);
  v31 = (CRdpDynVCWriteQueue *)(v97 + 584);
  while ( 1 )
  {
    CRdpDynVCWriteQueue::DequeueWorkItemFromChannel(v31, v30, &v96);
    CTSCriticalSection::UnLock((CRdpDynVCMgr *)((char *)this + 1864));
    if ( !v96 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v30 + 4) + 16LL))(*((_QWORD *)v30 + 4));
      goto LABEL_34;
    }
    v32 = *((unsigned int *)v96 + 32);
    v94 = *((_DWORD *)v96 + 39);
    v33 = *(_QWORD *)((char *)this + *(_QWORD *)v101 + 200);
    v34 = *((_QWORD *)v96 + 12);
    v35 = *((_DWORD *)v96 + 36);
    v97 = (char *)v96 + 96;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, int, int))(*(_QWORD *)v33 + 48LL))(
            v33,
            *(_QWORD *)(v34 + 144),
            *((_QWORD *)v96 + 15),
            v32,
            v35,
            v94,
            3);
    v36 = *((_DWORD *)v96 + 32);
    v37 = (unsigned __int8 *)*((_QWORD *)v96 + 15);
    v38 = (CRdpDynVC *)*((_QWORD *)v96 + 12);
    v99 = (char *)v96 + 136;
    CRdpDynVC::OnDataSent(v38, (unsigned int)v15 >> 31, v37, v36, *((struct IUnknown **)v96 + 17));
    if ( *(_QWORD *)v97 )
    {
      TCntPtr<CFakeGfxProvider>::SafeRelease(v97);
      v39 = v97;
      *(_QWORD *)v97 = 0;
      TCntPtr<PipePrimitive>::SafeAddRef(v39);
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(v99, 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v96 + 4) + 16LL))(*((_QWORD *)v96 + 4));
    if ( v15 < 0 )
      break;
    v96 = 0;
    CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
    v31 = v95;
    v30 = v98;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v111) = 1482;
    v95 = (CRdpDynVCWriteQueue *)"SendChannelData for conctrl during demand active pending failed";
    v99 = "Flush";
    v96 = (struct CRdpDynVCWorkitemClass *)"Error HResult failed";
    v98 = (struct CRdpDynVCWriteChannelsClass *)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    LODWORD(v97) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp",
      (unsigned int)word_18029912A,
      v40,
      v41,
      (__int64)&v96,
      (__int64)&v97,
      (__int64)&v98,
      (__int64)&v111,
      (__int64)&v99,
      (__int64)&v95);
  }
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v100);
LABEL_91:
  v99 = (char *)this + 152;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 152));
  v77 = (void *)*((_QWORD *)this + 2480);
  v78 = 0;
  *((_DWORD *)v16 + 4966) = 0;
  if ( v77 )
  {
    SetEvent(v77);
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v111) = 1661;
    v103 = "Flush";
    LODWORD(v113) = -2147467261;
    v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    v95 = (CRdpDynVCWriteQueue *)"Failed to set m_hFlushCompleteEvent because it's null";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)qword_180298ED0,
      v75,
      v76,
      (__int64)&v95,
      (__int64)&v113,
      (__int64)&v102,
      (__int64)&v111,
      (__int64)&v103);
  }
  if ( (*((_BYTE *)this - 20) & 4) != 0 )
  {
    v79 = (void *)*((_QWORD *)this + 2478);
    if ( v79 )
    {
      SetEvent(v79);
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v111) = 1674;
      v103 = "Flush";
      LODWORD(v113) = -2147467261;
      v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
      v95 = (CRdpDynVCWriteQueue *)"Failed to set m_hFlushAfterCloseCompleteEvent because it's null";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)&word_180298E3E,
        v75,
        v76,
        (__int64)&v95,
        (__int64)&v113,
        (__int64)&v102,
        (__int64)&v111,
        (__int64)&v103);
    }
  }
  else if ( *((_QWORD *)this + 2496) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v105);
    v6 = *((_QWORD *)this + 2496);
    v105 = v6;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v105);
  }
  if ( *((_DWORD *)this + 4958) )
    *((_DWORD *)this + 4958) = 0;
  v111 = (char *)this + 1864;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
  if ( (unsigned int)CRdpDynVCMgr::WriteQueuesAreEmpty(v16) )
  {
    *((_DWORD *)this + 4980) = 0;
  }
  else
  {
    v110 = 1;
    v78 = 1;
  }
  if ( *((_QWORD *)this + 2473) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v108);
    v4 = *((_QWORD *)this + 2473);
    v108 = v4;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v108);
  }
  if ( *((_QWORD *)this + 2474) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v107);
    v5 = *((_QWORD *)this + 2474);
    v107 = v5;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v107);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v111);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v99);
  if ( v110 )
    CRdpDynVCMgr::SendChannelsMetricsUpdate(v16);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v6);
  if ( v5 )
  {
    if ( v78 )
    {
      v80 = v112 == 0 ? 5 : 0;
      goto LABEL_121;
    }
    if ( v6 )
    {
      v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6);
      v80 = v81;
      if ( v81 <= 0x1F4 )
        v80 = 500;
LABEL_121:
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, v80);
    }
    goto LABEL_132;
  }
  if ( v4 )
  {
    if ( v78 )
    {
      v82 = v4;
      v83 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 24LL);
      if ( v112 )
        v84 = 0;
      else
        v84 = 5;
    }
    else
    {
      if ( !v6 )
        goto LABEL_132;
      v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6);
      v84 = v85;
      v82 = v4;
      if ( v85 <= 0x1F4 )
        v84 = 500;
      v83 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 24LL);
    }
    v83(v82, v84);
LABEL_132:
    RdpVCETWEvents::OnFireSchd(*((RdpVCETWEvents **)this + 11));
  }
  v87 = GetTickCount() - v109;
  if ( (unsigned int)CallbackContext > 5 )
  {
    v110 = v87;
    v111 = "Flush End";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v86,
      (unsigned int)&dword_180298E0C,
      v88,
      v89,
      (__int64)&v111,
      (__int64)&v110);
  }
  v90 = *((_QWORD *)this + 12);
  if ( v90 && (unsigned int)(v87 + v104) > 0x1388 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 192LL))(v90, (unsigned int)v87);
  if ( *((_QWORD *)this + 12) && GetTickCount64() - *((_QWORD *)this + 2497) > 0xEA60 )
  {
    TickCount64 = GetTickCount64();
    v92 = *((_QWORD *)this + 12);
    *((_QWORD *)this + 2497) = TickCount64;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 232LL))(v92);
  }
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)this + 2482), 0, 1u);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v105);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v106);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v107);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v108);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18006a6e0  push    rbp
0x18006a6e2  push    rbx
0x18006a6e3  push    rsi
0x18006a6e4  push    rdi
0x18006a6e5  push    r12
0x18006a6e7  push    r13
0x18006a6e9  push    r14
0x18006a6eb  push    r15
0x18006a6ed  lea     rbp, [rsp-1Fh]
0x18006a6f2  sub     rsp, 0D8h
0x18006a6f9  xor     ebx, ebx
0x18006a6fb  mov     r13, rcx
0x18006a6fe  mov     rcx, [rcx+4D88h]; struct IRDPPerfCounterGeneric *
0x18006a705  xor     r8d, r8d; unsigned int
0x18006a708  xor     edx, edx; unsigned int
0x18006a70a  mov     [rbp+57h+arg_0], ebx
0x18006a70d  mov     [rbp+57h+arg_10], ebx
0x18006a710  mov     esi, ebx
0x18006a712  mov     [rbp+57h+var_58], rbx
0x18006a716  mov     r14d, ebx
0x18006a719  mov     [rbp+57h+var_60], rbx
0x18006a71d  mov     edi, ebx
0x18006a71f  mov     [rbp+57h+var_68], rbx
0x18006a723  mov     [rbp+57h+var_70], rbx
0x18006a727  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18006a72c  call    cs:__imp_GetTickCount
0x18006a732  mov     ecx, [r13+4DB8h]
0x18006a739  mov     edx, eax
0x18006a73b  sub     edx, ecx
0x18006a73d  mov     [rbp+57h+var_50], eax
0x18006a740  neg     ecx
0x18006a742  mov     r8d, eax
0x18006a745  mov     [r13+4DB8h], r8d
0x18006a74c  mov     ecx, cs:CallbackContext
0x18006a752  sbb     eax, eax
0x18006a754  and     eax, edx
0x18006a756  mov     [rbp+57h+var_78], eax
0x18006a759  cmp     ecx, 5
0x18006a75c  jbe     short loc_18006A797
0x18006a75e  mov     dword ptr [rbp+57h+arg_8], eax
0x18006a761  lea     rdx, word_180299216
0x18006a768  lea     rax, aFlushStart; "Flush Start"
0x18006a76f  mov     dword ptr [rbp+57h+arg_18], r8d
0x18006a773  mov     [rbp+57h+var_A8], rax
0x18006a777  lea     rax, [rbp+57h+arg_8]
0x18006a77b  mov     [rsp+110h+var_E0], rax
0x18006a780  lea     rax, [rbp+57h+arg_18]
0x18006a784  mov     [rsp+110h+var_E8], rax
0x18006a789  lea     rax, [rbp+57h+var_A8]
0x18006a78d  mov     [rsp+110h+var_F0], rax
0x18006a792  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a797  lea     r15, [r13+98h]
0x18006a79e  mov     rcx, r15; this
0x18006a7a1  mov     [rbp+57h+arg_8], r15
0x18006a7a5  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a7aa  test    byte ptr [r13-14h], 4
0x18006a7af  mov     eax, 1
0x18006a7b4  jz      short loc_18006A7F8
0x18006a7b6  mov     eax, cs:CallbackContext
0x18006a7bc  cmp     eax, 4
0x18006a7bf  jbe     short loc_18006A7E1
0x18006a7c1  lea     rax, aFlushCallDurin; "Flush Call during or after termination,"...
0x18006a7c8  mov     [rbp+57h+arg_18], rax
0x18006a7cc  lea     rdx, byte_18029917B
0x18006a7d3  lea     rax, [rbp+57h+arg_18]
0x18006a7d7  mov     [rsp+110h+var_F0], rax
0x18006a7dc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006a7e1  lea     rcx, [rbp+57h+arg_8]; this
0x18006a7e5  mov     ebx, 8007000Ch
0x18006a7ea  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006a7ef  lea     r12, [r13-30h]
0x18006a7f3  jmp     loc_18006B224
0x18006a7f8  cmp     [r13+4DECh], ebx
0x18006a7ff  jz      short loc_18006A836
0x18006a801  mov     [r13+4DECh], ebx
0x18006a808  mov     r12d, eax
0x18006a80b  cmp     [r13+0C8h], rbx
0x18006a812  jz      short loc_18006A839
0x18006a814  lea     rcx, [rbp+57h+var_68]
0x18006a818  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18006a81d  mov     rbx, [r13+0C8h]
0x18006a824  lea     rcx, [rbp+57h+var_68]
0x18006a828  mov     [rbp+57h+var_68], rbx
0x18006a82c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18006a831  mov     eax, r12d
0x18006a834  jmp     short loc_18006A839
0x18006a836  mov     r12d, ebx
0x18006a839  lea     rcx, [rbp+57h+arg_8]; this
0x18006a83d  mov     [r13+4D68h], eax
0x18006a844  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006a849  test    r12d, r12d
0x18006a84c  jz      short loc_18006A895
0x18006a84e  test    rbx, rbx
0x18006a851  jz      short loc_18006A895
0x18006a853  mov     eax, cs:CallbackContext
0x18006a859  cmp     eax, 3
0x18006a85c  jbe     short loc_18006A87E
0x18006a85e  lea     rax, aTriggeringShut; "Triggering shutdown on DVC data handlin"...
0x18006a865  mov     [rbp+57h+arg_8], rax
0x18006a869  lea     rdx, qword_1802991A0
0x18006a870  lea     rax, [rbp+57h+arg_8]
0x18006a874  mov     [rsp+110h+var_F0], rax
0x18006a879  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006a87e  mov     rax, [rbx]
0x18006a881  mov     edx, 133h
0x18006a886  mov     rcx, rbx
0x18006a889  mov     rax, [rax+1F0h]
0x18006a890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a895  xor     r12d, r12d
0x18006a898  mov     dword ptr [rbp+57h+arg_8], r12d
0x18006a89c  lea     rbx, [r12+r12*4]
0x18006a8a0  shl     rbx, 4
0x18006a8a4  mov     qword ptr [rbp+57h+var_90], rbx
0x18006a8a8  test    r12d, r12d
0x18006a8ab  jnz     loc_18006AB14
0x18006a8b1  mov     rcx, [rbx+r13+0C8h]
0x18006a8b9  lea     rdx, [rbp+57h+arg_18]
0x18006a8bd  mov     dword ptr [rbp+57h+arg_18], esi
0x18006a8c0  mov     rax, [rcx]
0x18006a8c3  mov     rax, [rax+240h]
0x18006a8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8cf  mov     edx, dword ptr [rbp+57h+arg_18]
0x18006a8d2  xor     ecx, ecx
0x18006a8d4  test    edx, edx
0x18006a8d6  mov     r8d, eax
0x18006a8d9  cmovnz  r8d, ecx
0x18006a8dd  mov     [rbx+r13+100h], r8d
0x18006a8e5  jz      loc_18006AB4E
0x18006a8eb  test    eax, eax
0x18006a8ed  jz      loc_18006AB4E
0x18006a8f3  mov     rcx, [rbx+r13+0C8h]
0x18006a8fb  lea     edx, [r12+20h]
0x18006a900  mov     rax, [rcx]
0x18006a903  mov     rax, [rax+238h]
0x18006a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a90f  test    eax, eax
0x18006a911  jz      loc_18006AB4E
0x18006a917  lea     rcx, [r13+220h]; this
0x18006a91e  mov     [rbp+57h+var_98], rsi
0x18006a922  mov     [rbp+57h+var_B8], rcx
0x18006a926  mov     [rbp+57h+var_A8], rsi
0x18006a92a  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a92f  lea     r12, [r13-30h]
0x18006a933  mov     rcx, r12; this
0x18006a936  lea     r8, [rbp+57h+var_98]; struct CRdpDynVC **
0x18006a93a  lea     rdx, String1; "conctrl"
0x18006a941  call    ?LookupChannel@CRdpDynVCMgr@@IEAAJPEBDPEAPEAVCRdpDynVC@@@Z; CRdpDynVCMgr::LookupChannel(char const *,CRdpDynVC * *)
0x18006a946  lea     rcx, [rbp+57h+var_B8]; this
0x18006a94a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006a94f  mov     ecx, dword ptr [rbp+57h+arg_8]
0x18006a952  mov     rbx, [rbp+57h+var_98]
0x18006a956  lea     rax, [rcx+rcx*4]
0x18006a95a  shl     rax, 6
0x18006a95e  mov     [rbp+57h+var_B8], rax
0x18006a962  test    rbx, rbx
0x18006a965  jz      short loc_18006A9AC
0x18006a967  lea     r12, [r13+748h]
0x18006a96e  mov     rcx, r12; this
0x18006a971  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a976  mov     rax, [rbp+57h+var_B8]
0x18006a97a  lea     r9, [rbp+57h+var_A8]; struct CRdpDynVCWriteChannelsClass **
0x18006a97e  mov     r8d, [rbx+88h]; unsigned int
0x18006a985  add     rax, r13
0x18006a988  mov     edx, [rbx+0A8h]; int
0x18006a98e  mov     [rbp+57h+var_B0], rax
0x18006a992  lea     rcx, [rax+248h]; this
0x18006a999  call    ?RemoveChannelItemById@CRdpDynVCWriteQueue@@QEAAJHIPEAPEAVCRdpDynVCWriteChannelsClass@@@Z; CRdpDynVCWriteQueue::RemoveChannelItemById(int,uint,CRdpDynVCWriteChannelsClass * *)
0x18006a99e  mov     rcx, r12; this
0x18006a9a1  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18006a9a6  lea     r12, [r13-30h]
0x18006a9aa  jmp     short loc_18006A9B3
0x18006a9ac  add     rax, r13
0x18006a9af  mov     [rbp+57h+var_B0], rax
0x18006a9b3  mov     rbx, [rbp+57h+var_A8]
0x18006a9b7  test    rbx, rbx
0x18006a9ba  jz      loc_18006AB01
0x18006a9c0  lea     rcx, [r13+748h]; this
0x18006a9c7  mov     [rbp+57h+var_B8], rsi
0x18006a9cb  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a9d0  mov     rax, [rbp+57h+var_B0]
0x18006a9d4  add     rax, 248h
0x18006a9da  mov     [rbp+57h+var_C0], rax
0x18006a9de  mov     rcx, rax
0x18006a9e1  jmp     loc_18006AACC
0x18006a9e6  mov     r8d, [r10+9Ch]
0x18006a9ed  mov     rax, qword ptr [rbp+57h+var_90]
0x18006a9f1  mov     r9d, [r10+80h]
0x18006a9f8  mov     dword ptr [rsp+110h+var_E0], 3
0x18006aa00  mov     dword ptr [rsp+110h+var_E8], r8d
0x18006aa05  mov     rcx, [rax+r13+0C8h]
0x18006aa0d  lea     rax, [r10+60h]
0x18006aa11  mov     rdx, [rax]
0x18006aa14  mov     r8d, [r10+90h]
0x18006aa1b  mov     [rbp+57h+var_B0], rax
0x18006aa1f  mov     rax, [rcx]
0x18006aa22  mov     rdx, [rdx+90h]
0x18006aa29  mov     dword ptr [rsp+110h+var_F0], r8d
0x18006aa2e  mov     r8, [r10+78h]
0x18006aa32  mov     rax, [rax+30h]
0x18006aa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa3b  mov     rcx, [rbp+57h+var_B8]
0x18006aa3f  mov     ebx, eax
0x18006aa41  mov     edx, ebx
0x18006aa43  shr     edx, 1Fh; int
0x18006aa46  mov     r9d, [rcx+80h]; unsigned int
0x18006aa4d  lea     rax, [rcx+88h]
0x18006aa54  mov     r8, [rcx+78h]; unsigned __int8 *
0x18006aa58  mov     rcx, [rcx+60h]; this
0x18006aa5c  mov     [rbp+57h+var_A0], rax
0x18006aa60  mov     rax, [rax]
0x18006aa63  mov     [rsp+110h+var_F0], rax; struct IUnknown *
0x18006aa68  call    ?OnDataSent@CRdpDynVC@@QEAAJHPEAEKPEAUIUnknown@@@Z; CRdpDynVC::OnDataSent(int,uchar *,ulong,IUnknown *)
0x18006aa6d  mov     rax, [rbp+57h+var_B0]
0x18006aa71  cmp     [rax], rsi
0x18006aa74  jz      short loc_18006AA8D
0x18006aa76  mov     rcx, rax
0x18006aa79  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18006aa7e  mov     rax, [rbp+57h+var_B0]
0x18006aa82  mov     rcx, rax
0x18006aa85  mov     [rax], rsi
0x18006aa88  call    ?SafeAddRef@?$TCntPtr@VPipePrimitive@@@@AEAAXXZ; TCntPtr<PipePrimitive>::SafeAddRef(void)
0x18006aa8d  mov     rcx, [rbp+57h+var_A0]
0x18006aa91  xor     edx, edx
0x18006aa93  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18006aa98  mov     rax, [rbp+57h+var_B8]
0x18006aa9c  mov     rcx, [rax+20h]
0x18006aaa0  mov     rax, [rcx]
0x18006aaa3  mov     rax, [rax+10h]
0x18006aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaac  test    ebx, ebx
0x18006aaae  js      loc_18006AC9A
0x18006aab4  lea     rcx, [r13+748h]; this
0x18006aabb  mov     [rbp+57h+var_B8], rsi
0x18006aabf  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006aac4  mov     rcx, [rbp+57h+var_C0]; this
0x18006aac8  mov     rbx, [rbp+57h+var_A8]
0x18006aacc  lea     r8, [rbp+57h+var_B8]; struct CRdpDynVCWorkitemClass **
0x18006aad0  mov     rdx, rbx; struct CRdpDynVCWriteChannelsClass *
0x18006aad3  call    ?DequeueWorkItemFromChannel@CRdpDynVCWriteQueue@@QEAAJPEAVCRdpDynVCWriteChannelsClass@@PEAPEAVCRdpDynVCWorkitemClass@@@Z; CRdpDynVCWriteQueue::DequeueWorkItemFromChannel(CRdpDynVCWriteChannelsClass *,CRdpDynVCWorkitemClass * *)
0x18006aad8  lea     rcx, [r13+748h]; this
0x18006aadf  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18006aae4  mov     r10, [rbp+57h+var_B8]
0x18006aae8  test    r10, r10
0x18006aaeb  jnz     loc_18006A9E6
0x18006aaf1  mov     rcx, [rbx+20h]
0x18006aaf5  mov     rax, [rcx]
0x18006aaf8  mov     rax, [rax+10h]
0x18006aafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab01  lea     rcx, [rbp+57h+var_98]
0x18006ab05  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18006ab0a  mov     rbx, qword ptr [rbp+57h+var_90]
0x18006ab0e  mov     r12d, dword ptr [rbp+57h+arg_8]
0x18006ab12  jmp     short loc_18006AB4E
0x18006ab14  cmp     [rbx+r13+0E0h], esi
0x18006ab1c  jz      short loc_18006AB46
0x18006ab1e  cmp     [rbx+r13+0E4h], esi
0x18006ab26  jnz     short loc_18006AB46
0x18006ab28  mov     rcx, [rbx+r13+0C0h]
0x18006ab30  mov     rax, [rcx]
0x18006ab33  mov     rax, [rax+50h]
0x18006ab37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab3c  mov     [rbx+r13+100h], eax
0x18006ab44  jmp     short loc_18006AB4E
0x18006ab46  mov     [rbx+r13+100h], esi
0x18006ab4e  mov     eax, [rbx+r13+100h]
0x18006ab56  inc     r12d
0x18006ab59  mov     [rbx+r13+104h], eax
0x18006ab61  mov     dword ptr [rbp+57h+arg_8], r12d
0x18006ab65  cmp     r12d, 4
0x18006ab69  jl      loc_18006A89C
0x18006ab6f  mov     r9d, [r13+1F4h]; char
0x18006ab76  mov     r8d, [r13+154h]; unsigned int
0x18006ab7d  mov     edx, [r13+104h]; unsigned int
0x18006ab84  mov     rcx, [r13+58h]; this
0x18006ab88  call    ?OnFlushStart@RdpVCETWEvents@@UEAAJIII@Z; RdpVCETWEvents::OnFlushStart(uint,uint,uint)
0x18006ab8d  mov     eax, cs:CallbackContext
0x18006ab93  cmp     eax, 5
0x18006ab96  jbe     short loc_18006ABF1
0x18006ab98  mov     eax, [r13+1F4h]
0x18006ab9f  lea     rdx, byte_1802990B7
0x18006aba6  mov     dword ptr [rbp+57h+arg_8], eax
0x18006aba9  mov     eax, [r13+154h]
0x18006abb0  mov     dword ptr [rbp+57h+arg_18], eax
0x18006abb3  mov     eax, [r13+104h]
0x18006abba  mov     dword ptr [rbp+57h+var_B0], eax
0x18006abbd  lea     rax, aFlushNetworkMe_0; "Flush Network Metrics Start"
0x18006abc4  mov     [rbp+57h+var_C0], rax
0x18006abc8  lea     rax, [rbp+57h+arg_8]
0x18006abcc  mov     [rsp+110h+var_D8], rax
0x18006abd1  lea     rax, [rbp+57h+arg_18]
0x18006abd5  mov     [rsp+110h+var_E0], rax
0x18006abda  lea     rax, [rbp+57h+var_B0]
0x18006abde  mov     [rsp+110h+var_E8], rax
0x18006abe3  lea     rax, [rbp+57h+var_C0]
0x18006abe7  mov     [rsp+110h+var_F0], rax
0x18006abec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006abf1  lea     rbx, [r13+748h]
0x18006abf8  mov     rcx, rbx; this
0x18006abfb  mov     [rbp+57h+var_A8], rbx
0x18006abff  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
  ... truncated ...
```
