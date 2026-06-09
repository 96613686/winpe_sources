# CRdpDynVCMgr::InitializeInstance(IRDPWDUMX_StackEx *,IRdpMTListener *,ulong)

- ea: `0x18013f3d0`
- end: `0x1801403d8`
- name: `?InitializeInstance@CRdpDynVCMgr@@UEAAJPEAUIRDPWDUMX_StackEx@@PEAUIRdpMTListener@@K@Z`
- size: `4104`
- prototype: `int(CRdpDynVCMgr *__hidden this, struct IRDPWDUMX_StackEx *, struct IRdpMTListener *, unsigned int)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x1800023e4`
- `0x180002568`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000e4ec`
- `0x18000e998`
- `0x18000f660`
- `0x18000fddc`
- `0x18002aafc`
- `0x18002b14c`
- `0x180044000`
- `0x18004aa3c`
- `0x180076a74`
- `0x18007f42c`
- `0x18013e978`
- `0x18013f0c0`
- `0x18013f3d0`
- `0x1801403e0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014009e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013f5f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014009e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140154`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18013faef`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18013faef`
- `RDPBASE!RdpTaskTrigger_CreateInstance` at `0x18013fdb1`
- `RDPBASE!RdpTaskTrigger_CreateInstance` at `0x18013fdb1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180140088`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014013e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180140088`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014013e`
- `OLEAUT32!__imp_VariantInit` at `0x1801401ec`
- `OLEAUT32!__imp_VariantInit` at `0x1801401ec`
- `OLEAUT32!__imp_VariantClear` at `0x180140270`
- `OLEAUT32!__imp_VariantClear` at `0x180140270`

## string_xrefs

- `0x18013f84b`: `ReplaceCustomRdpScheduler`
- `0x18013f877`: `Failed to get property whether to replace custom RDP scheduler from platform context`
- `0x18013fdcc`: `Failed to create task trigger instance`
- `0x18013f7d9`: `UserConfiguredTransportMode`
- `0x18013fcda`: `Failed to get thread pool handle. Using default system pool.`
- `0x18013f616`: `m_CompletionQueueLock.Initialize`
- `0x18013f56e`: `m_WriteQueueLock.Initialize`
- `0x18013f80e`: `Read PROPERTY..TRANSPORT`
- `0x18013fec0`: `Failed to create VC WriteQueue Pool`
- `0x18014017c`: `Failed CreateEvent call for m_hFlushCompleteEvent Event`
- `0x1801400c6`: `Failed CreateEvent call for m_hFlushAfterCloseCompleteEvent Event`
- `0x1801402bd`: `CreateInst for ConnMonitor failed`

## pseudocode

```c
__int64 __fastcall CRdpDynVCMgr::InitializeInstance(
        CRdpDynVCMgr *this,
        struct IRDPWDUMX_StackEx *a2,
        struct IRdpMTListener *a3,
        unsigned int a4)
{
  signed int LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  signed int Instance; // ebx
  __int64 *v12; // rdx
  const char **v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  int v16; // eax
  int v17; // r9d
  struct IRDPCollection **v18; // rbx
  struct IRDPCollection *v19; // rcx
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // rbx
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
  int v35; // r8d
  int v36; // r9d
  int v37; // eax
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  int v41; // r8d
  int v42; // r9d
  int v43; // r14d
  int v44; // eax
  const struct _GUID *v45; // rdx
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  BOOL v49; // eax
  RdpVCETWEvents *v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // rcx
  int v52; // eax
  int v53; // r8d
  int v54; // r9d
  int v55; // eax
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // rcx
  int v59; // eax
  int v60; // r8d
  int v61; // r9d
  int v62; // r8d
  int v63; // r9d
  const char *v64; // rcx
  const char *v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  CRdpDynVCMgr *v68; // r14
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  int v75; // r8d
  int v76; // r9d
  HANDLE EventW; // rax
  signed int v78; // eax
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  HANDLE v82; // rax
  signed int v83; // eax
  int v84; // ecx
  int v85; // r8d
  int v86; // r9d
  __int64 v87; // rcx
  __int64 i; // r8
  __int64 v89; // rdx
  int v90; // eax
  int v91; // r8d
  int v92; // r9d
  struct IRDPCollection *v93; // rcx
  int v94; // ecx
  int v95; // r8d
  int v96; // r9d
  __int64 v97; // rcx
  const char **v99; // [rsp+30h] [rbp-69h]
  const char **v100; // [rsp+40h] [rbp-59h]
  const char **v101; // [rsp+48h] [rbp-51h]
  const char *v102; // [rsp+50h] [rbp-49h] BYREF
  const char *v103; // [rsp+58h] [rbp-41h] BYREF
  const char *v104; // [rsp+60h] [rbp-39h] BYREF
  const char *v105; // [rsp+68h] [rbp-31h] BYREF
  __int64 v106; // [rsp+70h] [rbp-29h] BYREF
  const char *v107; // [rsp+78h] [rbp-21h] BYREF
  const char *v108; // [rsp+80h] [rbp-19h] BYREF
  struct IRDPCollection *v109; // [rsp+88h] [rbp-11h] BYREF
  int v110; // [rsp+90h] [rbp-9h] BYREF
  int v111; // [rsp+94h] [rbp-5h] BYREF
  __int64 v112; // [rsp+98h] [rbp-1h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp+7h] BYREF
  int v114; // [rsp+100h] [rbp+67h] BYREF
  struct IRDPWDUMX_StackEx *v115; // [rsp+108h] [rbp+6Fh]

  v115 = a2;
  v109 = 0;
  v112 = 0;
  v111 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (unsigned int)CallbackContext > 4 )
  {
    v114 = a4;
    v103 = "CRdpDynVCMgr: In InitializeInstance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)word_180299842,
      (_DWORD)a3,
      a4,
      (__int64)&v103,
      (__int64)&v114);
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpDynVCMgr *)((char *)this + 152)) )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    if ( Instance < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_131;
      v114 = 998;
      v103 = "m_objLock.Initialize";
      v105 = "InitializeInstance";
      v104 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
      v12 = qword_1802997A0;
      v102 = "Error HResult failed";
      v101 = &v103;
      v100 = &v105;
      v99 = &v104;
      v13 = &v102;
      goto LABEL_9;
    }
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpDynVCMgr *)((char *)this + 544))
    || !(unsigned int)CTSCriticalSection::Initialize((CRdpDynVCMgr *)((char *)this + 19800)) )
  {
    Instance = -2147024882;
    goto LABEL_131;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRdpDynVCMgr *)((char *)this + 1864)) )
  {
    v14 = GetLastError();
    Instance = v14;
    if ( v14 > 0 )
      Instance = (unsigned __int16)v14 | 0x80070000;
    if ( Instance < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v114 = 1017;
        v102 = "m_WriteQueueLock.Initialize";
        v104 = "InitializeInstance";
        v103 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
        v12 = (__int64 *)byte_1802997F1;
        v105 = "Error HResult failed";
        v101 = &v102;
        v100 = &v104;
        v99 = &v103;
        v13 = &v105;
LABEL_9:
        LODWORD(v106) = Instance;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v8,
          (_DWORD)v12,
          v9,
          v10,
          (__int64)v13,
          (__int64)&v106,
          (__int64)v99,
          (__int64)&v114,
          (__int64)v100,
          (__int64)v101);
        goto LABEL_131;
      }
      goto LABEL_131;
    }
  }
  if ( (unsigned int)CTSCriticalSection::Initialize((CRdpDynVCMgr *)((char *)this + 1880)) )
    goto LABEL_25;
  v15 = GetLastError();
  Instance = v15;
  if ( v15 > 0 )
    Instance = (unsigned __int16)v15 | 0x80070000;
  if ( Instance >= 0 )
  {
LABEL_25:
    memset_0((char *)this + 192, 0, 0x140u);
    v16 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IRDPCollection **))this + 14))(
            *((_QWORD *)this + 14),
            &IID_IRDPCollection,
            &v109);
    if ( v16 < 0 && (unsigned int)CallbackContext > 3 )
    {
      v114 = v16;
      v103 = "HResult failed but continue";
      v102 = "InitializeInstance";
      v104 = "Failed to QI for IRDPENCPlatformContext";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_180299761,
        (unsigned int)"Failed to QI for IRDPENCPlatformContext",
        v17,
        (__int64)&v103,
        (__int64)&v104,
        (__int64)&v114,
        (__int64)&v102);
    }
    if ( v109 )
    {
      v18 = (struct IRDPCollection **)((char *)this + 136);
      if ( v109 != *((struct IRDPCollection **)this + 17) )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 136);
        *v18 = v109;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 136);
      }
      v19 = *v18;
      v114 = 0;
      if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v19 + 32LL))(
             v19,
             L"EnableDirectStream",
             &v114) >= 0
        && v114 )
      {
        v20 = CRdpDynVCMgr::InitializeQOEController((CRdpDynVCMgr *)((char *)this - 48), *v18);
        if ( v20 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v105) = v20;
          v102 = "CRdpDynVCMgr::InitializeInstance - Failed to initialize QOE controller";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_1802996E3,
            v21,
            v22,
            (__int64)&v102,
            (__int64)&v105);
        }
        *(_BYTE *)(*((_QWORD *)this + 2500) + 438624LL) = 1;
      }
      LODWORD(v106) = 0;
      v23 = (_DWORD *)((char *)this + 19904);
      v24 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, __int64 *))(*(_QWORD *)v109 + 40LL))(
              v109,
              L"UserConfiguredTransportMode",
              &v106);
      if ( v24 >= 0 )
      {
        v25 = v106;
        *v23 = v106;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v105) = *v23;
        v102 = "Read PROPERTY..TRANSPORT";
        LODWORD(v103) = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)qword_180299668,
          v26,
          v27,
          (__int64)&v102,
          (__int64)&v103,
          (__int64)&v105);
      }
      v28 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v109 + 32LL))(
              v109,
              L"ReplaceCustomRdpScheduler",
              &v111);
      if ( v28 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v103) = v28;
        v102 = "InitializeInstance";
        v104 = "Failed to get property whether to replace custom RDP scheduler from platform context";
        v105 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_1802996A4,
          v29,
          v30,
          (__int64)&v105,
          (__int64)&v104,
          (__int64)&v103,
          (__int64)&v102);
      }
      v31 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v109 + 48LL))(
              v109,
              L"RdpSqmLoggerInterface",
              &IID_IRdpSQMLogger,
              &v112);
      if ( v31 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v103) = v31;
        v102 = "InitializeInstance";
        v104 = "Failed to Get SqmLogger from platform context";
        v105 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_1802995EA,
          v32,
          v33,
          (__int64)&v105,
          (__int64)&v104,
          (__int64)&v103,
          (__int64)&v102);
      }
      if ( v112 )
      {
        v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v112 + 24LL))(
                v112,
                a4,
                (char *)this + 19864);
        if ( v34 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v103) = v34;
          v102 = "InitializeInstance";
          v104 = "Failed to get a Sqm log session";
          v105 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_180299629,
            v35,
            v36,
            (__int64)&v105,
            (__int64)&v104,
            (__int64)&v103,
            (__int64)&v102);
        }
      }
      v37 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, char *))(*(_QWORD *)v109 + 48LL))(
              v109,
              L"RDP::EventLog::Session",
              &IID_IRdpTransportEventLogCallbacks,
              (char *)this + 96);
      if ( v37 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v103) = v37;
        v102 = "InitializeInstance";
        v104 = "The eventlog session does not exsit";
        v105 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_18029956C,
          v38,
          v39,
          (__int64)&v105,
          (__int64)&v104,
          (__int64)&v103,
          (__int64)&v102);
      }
      v40 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, GUID *, char *))(*(_QWORD *)v109 + 48LL))(
              v109,
              L"RDP::EventLog::Session",
              &IID_IRdpStateTransitionEventLogCallbacks,
              (char *)this + 104);
      if ( v40 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v103) = v40;
        v102 = "InitializeInstance";
        v104 = "The state transition eventlog session does not exsit";
        v105 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_1802995AB,
          v41,
          v42,
          (__int64)&v105,
          (__int64)&v104,
          (__int64)&v103,
          (__int64)&v102);
      }
    }
    else
    {
      v23 = (_DWORD *)((char *)this + 19904);
    }
    *((_DWORD *)this + 52) = 1;
    if ( a3 )
    {
      v43 = 1;
      if ( *v23 != 1 )
      {
        v44 = 1;
LABEL_63:
        *((_DWORD *)this + 72) = v44;
        v110 = 1;
        v49 = (unsigned int)RDPENCHLPREG_ReadValueDWORD(
                              -2147483646,
                              L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                              L"ForceDisableUDPL",
                              &v110)
           && !v110
           && v43
           && *v23 != 1;
        *((_DWORD *)this + 112) = v49;
        *((_DWORD *)this + 92) = 0;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v114 = *((_DWORD *)this + 92);
          LODWORD(v103) = *((_DWORD *)this + 112);
          LODWORD(v105) = *((_DWORD *)this + 72);
          LODWORD(v106) = *((_DWORD *)this + 52);
          v102 = "Tunnel-fServerSupported flags";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v46,
            (unsigned int)&dword_180299524,
            v47,
            v48,
            (__int64)&v102,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v103,
            (__int64)&v114);
        }
        *((_DWORD *)this + 4981) = a4;
        *((_DWORD *)this + 62) = -1;
        *((_DWORD *)this + 82) = -1;
        *((_DWORD *)this + 122) = -1;
        *((_DWORD *)this + 102) = -1;
        *((_DWORD *)this + 63) = -1;
        *((_DWORD *)this + 83) = -1;
        *((_DWORD *)this + 123) = -1;
        *((_DWORD *)this + 103) = -1;
        RdpVCETWEvents_CreateInstance(a4, v45, (void **)this + 11);
        v50 = (RdpVCETWEvents *)*((_QWORD *)this + 11);
        if ( v50 )
          RdpVCETWEvents::Enable(v50);
        if ( a3 != *((struct IRdpMTListener **)this + 21) )
        {
          TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 168);
          *((_QWORD *)this + 21) = a3;
          TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 168);
        }
        TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 200, v115);
        if ( v111 )
        {
          v51 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 14);
          v106 = 0;
          v105 = 0;
          v52 = (**v51)(v51, &IID_IRDPENCPlatformContext, &v106);
          if ( v52 < 0 && (unsigned int)CallbackContext > 3 )
          {
            v114 = v52;
            v102 = "InitializeInstance";
            v104 = "Failed to QI for IRDPENCPlatformContext";
            v103 = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              (_DWORD)CallbackContext,
              (unsigned int)byte_1802994E5,
              v53,
              v54,
              (__int64)&v103,
              (__int64)&v104,
              (__int64)&v114,
              (__int64)&v102);
          }
          if ( v106 )
          {
            v55 = (*(__int64 (__fastcall **)(__int64, __int64, const char **))(*(_QWORD *)v106 + 184LL))(v106, 1, &v105);
            if ( v55 < 0 && (unsigned int)CallbackContext > 3 )
            {
              v114 = v55;
              v102 = "InitializeInstance";
              v104 = "Failed to get thread pool handle. Using default system pool.";
              v103 = "HResult failed but continue";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (_DWORD)CallbackContext,
                (unsigned int)byte_18029946D,
                v56,
                v57,
                (__int64)&v103,
                (__int64)&v104,
                (__int64)&v114,
                (__int64)&v102);
            }
          }
          v58 = *((_QWORD *)this + 17);
          if ( v58 )
          {
            v59 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v58 + 32LL))(
                    v58,
                    L"EnableVirtualChannelStats",
                    (char *)this + 184);
            if ( v59 < 0 && (unsigned int)CallbackContext > 3 )
            {
              v114 = v59;
              v102 = "InitializeInstance";
              v104 = "Failed to get enable VC stats property. Not critical, stats will not be enabled.";
              v103 = "HResult failed but continue";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                (_DWORD)CallbackContext,
                (unsigned int)&word_1802994A6,
                v60,
                v61,
                (__int64)&v103,
                (__int64)&v104,
                (__int64)&v114,
                (__int64)&v102);
            }
          }
          Instance = RdpTaskTrigger_CreateInstance(v105, (char *)this + 80, (char *)this + 19792);
          if ( Instance < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v104 = "InitializeInstance";
              v102 = "Failed to create task trigger instance";
              v114 = 1205;
              v107 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              v108 = "Error HResult failed";
              LODWORD(v103) = Instance;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                (_DWORD)CallbackContext,
                (unsigned int)&dword_18029941C,
                v62,
                v63,
                (__int64)&v108,
                (__int64)&v103,
                (__int64)&v107,
                (__int64)&v114,
                (__int64)&v104,
                (__int64)&v102);
            }
            v64 = v105;
            if ( v105 )
            {
              v105 = 0;
              (*(void (__fastcall **)(const char *))(*(_QWORD *)v64 + 16LL))(v64);
            }
            TCntPtr<IRdpVCMgr>::SafeRelease(&v106);
            goto LABEL_131;
          }
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2474) + 24LL))(*((_QWORD *)this + 2474), 0);
          v65 = v105;
          if ( v105 )
          {
            v105 = 0;
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v65 + 16LL))(v65);
          }
          TCntPtr<IRdpVCMgr>::SafeRelease(&v106);
          v68 = (CRdpDynVCMgr *)((char *)this - 48);
        }
        else
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 128LL))(
                       *((_QWORD *)this + 16),
                       (char *)this + 19776);
          if ( Instance < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v107 = "InitializeInstance";
              v108 = "Failed to get scheduler";
              v114 = 1212;
              v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              v104 = "Error HResult failed";
              LODWORD(v103) = Instance;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v72,
                (unsigned int)word_18029937A,
                v73,
                v74,
                (__int64)&v104,
                (__int64)&v103,
                (__int64)&v102,
                (__int64)&v114,
                (__int64)&v107,
                (__int64)&v108);
            }
            goto LABEL_131;
          }
          v68 = (CRdpDynVCMgr *)((char *)this - 48);
          Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 2472) + 40LL))(
                       *((_QWORD *)this + 2472),
                       ((unsigned __int64)this + 8)
                     & ((unsigned __int128)-(__int128)((unsigned __int64)this - 48) >> 64),
                       (char *)this + 19784);
          if ( Instance < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              v107 = "InitializeInstance";
              v108 = "Failed to register VCMgr with Scheduler";
              v114 = 1215;
              v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              v104 = "Error HResult failed";
              LODWORD(v103) = Instance;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v67,
                (unsigned int)byte_1802993CB,
                v75,
                v76,
                (__int64)&v104,
                (__int64)&v103,
                (__int64)&v102,
                (__int64)&v114,
                (__int64)&v107,
                (__int64)&v108);
            }
            goto LABEL_131;
          }
        }
        Instance = CTSObjectPool<CRdpDynVCWorkitemClass>::CreateInstance(v67, v66, (char *)this + 1896);
        if ( Instance >= 0 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 2478) = EventW;
          if ( EventW )
            goto LABEL_111;
          v78 = GetLastError();
          Instance = v78;
          if ( v78 > 0 )
            Instance = (unsigned __int16)v78 | 0x80070000;
          if ( Instance >= 0 )
          {
LABEL_111:
            v82 = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)this + 2480) = v82;
            if ( v82 )
              goto LABEL_117;
            v83 = GetLastError();
            Instance = v83;
            if ( v83 > 0 )
              Instance = (unsigned __int16)v83 | 0x80070000;
            if ( Instance >= 0 )
            {
LABEL_117:
              VariantInit(&pvarg);
              v87 = *((_QWORD *)this + 16);
              pvarg.vt = 11;
              if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v87 + 24LL))(
                     v87,
                     L"RDPWDUMX::CollabLimitStackBuffer",
                     &pvarg) >= 0
                && pvarg.vt == 11
                && pvarg.iVal == -1 )
              {
                *((_DWORD *)this + 4986) = 16256;
                CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 1864));
                for ( i = 0; i != 4; ++i )
                {
                  v89 = 320 * i;
                  *(_DWORD *)((char *)this + v89 + 896) = *((_DWORD *)this + 4986);
                }
                CTSCriticalSection::UnLock((CRdpDynVCMgr *)((char *)this + 1864));
              }
              VariantClear(&pvarg);
              CRdpDynVCMgr::SetChannelPriorityCharges(v68);
              CRdpDynVCMgr::InitPerfMonSession(v68);
              v90 = RDPSERVERBASE_CreateInstance(
                      *((struct IUnknown **)this + 14),
                      &CLSID_RDPEncConnectionMonitor,
                      &IID_IRDPEncConnectionMonitor,
                      (void **)this + 2496);
              if ( v90 < 0 && (unsigned int)CallbackContext > 3 )
              {
                v114 = v90;
                v108 = "InitializeInstance";
                v107 = "CreateInst for ConnMonitor failed";
                v102 = "HResult failed but continue";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (_DWORD)CallbackContext,
                  (unsigned int)qword_180299248,
                  v91,
                  v92,
                  (__int64)&v102,
                  (__int64)&v107,
                  (__int64)&v114,
                  (__int64)&v108);
              }
              *((_DWORD *)this - 5) |= 2u;
              v93 = (struct IRDPCollection *)*((_QWORD *)this + 17);
              if ( v93 && (Instance = InitializeDynVCLogsForConnection(v93), Instance < 0) )
              {
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v107 = "InitializeInstance";
                  v108 = "InitializeDynVCLogsForConnection failed";
                  v114 = 1277;
                  v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
                  v104 = "Error HResult failed";
                  LODWORD(v103) = Instance;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v94,
                    (unsigned int)byte_1802991C5,
                    v95,
                    v96,
                    (__int64)&v104,
                    (__int64)&v103,
                    (__int64)&v102,
                    (__int64)&v114,
                    (__int64)&v107,
                    (__int64)&v108);
                }
              }
              else
              {
                Instance = 0;
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              v107 = "InitializeInstance";
              v108 = "Failed CreateEvent call for m_hFlushCompleteEvent Event";
              v114 = 1232;
              v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
              v104 = "Error HResult failed";
              LODWORD(v103) = Instance;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v84,
                (unsigned int)&byte_180299287,
                v85,
                v86,
                (__int64)&v104,
                (__int64)&v103,
                (__int64)&v102,
                (__int64)&v114,
                (__int64)&v107,
                (__int64)&v108);
            }
          }
          else if ( (unsigned int)CallbackContext > 2 )
          {
            v107 = "InitializeInstance";
            v108 = "Failed CreateEvent call for m_hFlushAfterCloseCompleteEvent Event";
            v114 = 1225;
            v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
            v104 = "Error HResult failed";
            LODWORD(v103) = Instance;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v79,
              (unsigned int)byte_180299329,
              v80,
              v81,
              (__int64)&v104,
              (__int64)&v103,
              (__int64)&v102,
              (__int64)&v114,
              (__int64)&v107,
              (__int64)&v108);
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v107 = "InitializeInstance";
          v108 = "Failed to create VC WriteQueue Pool";
          v114 = 1219;
          v102 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
          v104 = "Error HResult failed";
          LODWORD(v103) = Instance;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v69,
            (unsigned int)qword_1802992D8,
            v70,
            v71,
            (__int64)&v104,
            (__int64)&v103,
            (__int64)&v102,
            (__int64)&v114,
            (__int64)&v107,
            (__int64)&v108);
        }
        goto LABEL_131;
      }
    }
    else
    {
      v43 = 0;
    }
    v44 = 0;
    goto LABEL_63;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v114 = 1024;
    v102 = "m_CompletionQueueLock.Initialize";
    v104 = "InitializeInstance";
    v103 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    v12 = qword_180299710;
    v105 = "Error HResult failed";
    v101 = &v102;
    v100 = &v104;
    v99 = &v103;
    v13 = &v105;
    goto LABEL_9;
  }
LABEL_131:
  v97 = v112;
  if ( v112 )
  {
    v112 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v109);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18013f3d0  mov     [rsp-8+arg_10], rbx
0x18013f3d5  mov     [rsp-8+arg_8], rdx
0x18013f3da  push    rbp
0x18013f3db  push    rsi
0x18013f3dc  push    rdi
0x18013f3dd  push    r12
0x18013f3df  push    r13
0x18013f3e1  push    r14
0x18013f3e3  push    r15
0x18013f3e5  lea     rbp, [rsp-27h]
0x18013f3ea  sub     rsp, 0C0h
0x18013f3f1  xor     r13d, r13d
0x18013f3f4  xor     eax, eax
0x18013f3f6  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18013f3fa  xorps   xmm0, xmm0
0x18013f3fd  mov     eax, cs:CallbackContext
0x18013f403  mov     r15d, r9d
0x18013f406  mov     [rbp+57h+var_68], r13
0x18013f40a  mov     r12, r8
0x18013f40d  mov     [rbp+57h+var_58], r13
0x18013f411  mov     rdi, rcx
0x18013f414  mov     [rbp+57h+var_5C], r13d
0x18013f418  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18013f41c  cmp     eax, 4
0x18013f41f  jbe     short loc_18013F44E
0x18013f421  lea     rax, aCrdpdynvcmgrIn_6; "CRdpDynVCMgr: In InitializeInstance"
0x18013f428  mov     [rbp+57h+arg_0], r9d
0x18013f42c  mov     [rbp+57h+var_98], rax
0x18013f430  lea     rdx, word_180299842
0x18013f437  lea     rax, [rbp+57h+arg_0]
0x18013f43b  mov     [rsp+0F0h+var_C8], rax
0x18013f440  lea     rax, [rbp+57h+var_98]
0x18013f444  mov     [rsp+0F0h+var_D0], rax
0x18013f449  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013f44e  lea     rcx, [rdi+98h]; this
0x18013f455  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18013f45a  mov     esi, 80070000h
0x18013f45f  test    eax, eax
0x18013f461  jnz     loc_18013F50C
0x18013f467  call    cs:__imp_GetLastError
0x18013f46d  mov     ebx, eax
0x18013f46f  test    eax, eax
0x18013f471  jle     short loc_18013F478
0x18013f473  movzx   ebx, ax
0x18013f476  or      ebx, esi
0x18013f478  test    ebx, ebx
0x18013f47a  jns     loc_18013F50C
0x18013f480  mov     eax, cs:CallbackContext
0x18013f486  cmp     eax, 2
0x18013f489  jbe     loc_180140399
0x18013f48f  lea     rax, aMObjlockInitia; "m_objLock.Initialize"
0x18013f496  mov     [rbp+57h+arg_0], 3E6h
0x18013f49d  mov     [rbp+57h+var_98], rax
0x18013f4a1  lea     rsi, aInitializeinst_0; "InitializeInstance"
0x18013f4a8  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013f4af  mov     [rbp+57h+var_88], rsi
0x18013f4b3  mov     [rbp+57h+var_90], rax
0x18013f4b7  lea     rdx, qword_1802997A0
0x18013f4be  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013f4c5  mov     [rbp+57h+var_A0], rax
0x18013f4c9  lea     rax, [rbp+57h+var_98]
0x18013f4cd  mov     [rsp+0F0h+var_A8], rax
0x18013f4d2  lea     rax, [rbp+57h+var_88]
0x18013f4d6  mov     [rsp+0F0h+var_B0], rax
0x18013f4db  lea     rax, [rbp+57h+arg_0]
0x18013f4df  mov     [rsp+0F0h+var_B8], rax
0x18013f4e4  lea     rax, [rbp+57h+var_90]
0x18013f4e8  mov     [rsp+0F0h+var_C0], rax
0x18013f4ed  lea     rax, [rbp+57h+var_80]
0x18013f4f1  mov     [rsp+0F0h+var_C8], rax
0x18013f4f6  lea     rax, [rbp+57h+var_A0]
0x18013f4fa  mov     dword ptr [rbp+57h+var_80], ebx
0x18013f4fd  mov     [rsp+0F0h+var_D0], rax
0x18013f502  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18013f507  jmp     loc_180140399
0x18013f50c  lea     rcx, [rdi+220h]; this
0x18013f513  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18013f518  test    eax, eax
0x18013f51a  jnz     short loc_18013F526
0x18013f51c  mov     ebx, 8007000Eh
0x18013f521  jmp     loc_180140399
0x18013f526  lea     rcx, [rdi+4D58h]; this
0x18013f52d  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18013f532  test    eax, eax
0x18013f534  jz      short loc_18013F51C
0x18013f536  lea     rcx, [rdi+748h]; this
0x18013f53d  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18013f542  test    eax, eax
0x18013f544  jnz     loc_18013F5DE
0x18013f54a  call    cs:__imp_GetLastError
0x18013f550  mov     ebx, eax
0x18013f552  test    eax, eax
0x18013f554  jle     short loc_18013F55B
0x18013f556  movzx   ebx, ax
0x18013f559  or      ebx, esi
0x18013f55b  test    ebx, ebx
0x18013f55d  jns     short loc_18013F5DE
0x18013f55f  mov     eax, cs:CallbackContext
0x18013f565  cmp     eax, 2
0x18013f568  jbe     loc_180140399
0x18013f56e  lea     rax, aMWritequeueloc; "m_WriteQueueLock.Initialize"
0x18013f575  mov     [rbp+57h+arg_0], 3F9h
0x18013f57c  mov     [rbp+57h+var_A0], rax
0x18013f580  lea     rsi, aInitializeinst_0; "InitializeInstance"
0x18013f587  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013f58e  mov     [rbp+57h+var_90], rsi
0x18013f592  mov     [rbp+57h+var_98], rax
0x18013f596  lea     rdx, byte_1802997F1
0x18013f59d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013f5a4  mov     [rbp+57h+var_88], rax
0x18013f5a8  lea     rax, [rbp+57h+var_A0]
0x18013f5ac  mov     [rsp+0F0h+var_A8], rax
0x18013f5b1  lea     rax, [rbp+57h+var_90]
0x18013f5b5  mov     [rsp+0F0h+var_B0], rax
0x18013f5ba  lea     rax, [rbp+57h+arg_0]
0x18013f5be  mov     [rsp+0F0h+var_B8], rax
0x18013f5c3  lea     rax, [rbp+57h+var_98]
0x18013f5c7  mov     [rsp+0F0h+var_C0], rax
0x18013f5cc  lea     rax, [rbp+57h+var_80]
0x18013f5d0  mov     [rsp+0F0h+var_C8], rax
0x18013f5d5  lea     rax, [rbp+57h+var_88]
0x18013f5d9  jmp     loc_18013F4FA
0x18013f5de  lea     rcx, [rdi+758h]; this
0x18013f5e5  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18013f5ea  test    eax, eax
0x18013f5ec  jnz     loc_18013F686
0x18013f5f2  call    cs:__imp_GetLastError
0x18013f5f8  mov     ebx, eax
0x18013f5fa  test    eax, eax
0x18013f5fc  jle     short loc_18013F603
0x18013f5fe  movzx   ebx, ax
0x18013f601  or      ebx, esi
0x18013f603  test    ebx, ebx
0x18013f605  jns     short loc_18013F686
0x18013f607  mov     eax, cs:CallbackContext
0x18013f60d  cmp     eax, 2
0x18013f610  jbe     loc_180140399
0x18013f616  lea     rax, aMCompletionque; "m_CompletionQueueLock.Initialize"
0x18013f61d  mov     [rbp+57h+arg_0], 400h
0x18013f624  mov     [rbp+57h+var_A0], rax
0x18013f628  lea     rsi, aInitializeinst_0; "InitializeInstance"
0x18013f62f  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013f636  mov     [rbp+57h+var_90], rsi
0x18013f63a  mov     [rbp+57h+var_98], rax
0x18013f63e  lea     rdx, qword_180299710
0x18013f645  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013f64c  mov     [rbp+57h+var_88], rax
0x18013f650  lea     rax, [rbp+57h+var_A0]
0x18013f654  mov     [rsp+0F0h+var_A8], rax
0x18013f659  lea     rax, [rbp+57h+var_90]
0x18013f65d  mov     [rsp+0F0h+var_B0], rax
0x18013f662  lea     rax, [rbp+57h+arg_0]
0x18013f666  mov     [rsp+0F0h+var_B8], rax
0x18013f66b  lea     rax, [rbp+57h+var_98]
0x18013f66f  mov     [rsp+0F0h+var_C0], rax
0x18013f674  lea     rax, [rbp+57h+var_80]
0x18013f678  mov     [rsp+0F0h+var_C8], rax
0x18013f67d  lea     rax, [rbp+57h+var_88]
0x18013f681  jmp     loc_18013F4FA
0x18013f686  lea     r13, [rdi+0C0h]
0x18013f68d  xor     edx, edx; Val
0x18013f68f  mov     rcx, r13; void *
0x18013f692  mov     r8d, 140h; Size
0x18013f698  call    memset_0
0x18013f69d  mov     rcx, [rdi+70h]
0x18013f6a1  lea     r8, [rbp+57h+var_68]
0x18013f6a5  lea     rdx, IID_IRDPCollection
0x18013f6ac  mov     rax, [rcx]
0x18013f6af  mov     rax, [rax]
0x18013f6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f6b7  lea     rsi, aInitializeinst_0; "InitializeInstance"
0x18013f6be  lea     r8, aFailedToQiForI_0; "Failed to QI for IRDPENCPlatformContext"
0x18013f6c5  lea     rdx, aHresultFailedB; "HResult failed but continue"
0x18013f6cc  test    eax, eax
0x18013f6ce  jns     short loc_18013F71A
0x18013f6d0  mov     ecx, cs:CallbackContext
0x18013f6d6  cmp     ecx, 3
0x18013f6d9  jbe     short loc_18013F71A
0x18013f6db  mov     [rbp+57h+arg_0], eax
0x18013f6de  lea     rax, [rbp+57h+var_A0]
0x18013f6e2  mov     [rsp+0F0h+var_B8], rax
0x18013f6e7  lea     rax, [rbp+57h+arg_0]
0x18013f6eb  mov     [rsp+0F0h+var_C0], rax
0x18013f6f0  lea     rax, [rbp+57h+var_90]
0x18013f6f4  mov     [rsp+0F0h+var_C8], rax
0x18013f6f9  lea     rax, [rbp+57h+var_98]
0x18013f6fd  mov     [rbp+57h+var_98], rdx
0x18013f701  lea     rdx, byte_180299761
0x18013f708  mov     [rsp+0F0h+var_D0], rax
0x18013f70d  mov     [rbp+57h+var_A0], rsi
0x18013f711  mov     [rbp+57h+var_90], r8
0x18013f715  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18013f71a  mov     rax, [rbp+57h+var_68]
0x18013f71e  test    rax, rax
0x18013f721  jz      loc_18013FA9E
0x18013f727  lea     rbx, [rdi+88h]
0x18013f72e  cmp     rax, [rbx]
0x18013f731  jz      short loc_18013F74A
0x18013f733  mov     rcx, rbx
0x18013f736  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18013f73b  mov     rax, [rbp+57h+var_68]
0x18013f73f  mov     rcx, rbx
0x18013f742  mov     [rbx], rax
0x18013f745  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18013f74a  mov     rcx, [rbx]
0x18013f74d  lea     r8, [rbp+57h+arg_0]
0x18013f751  mov     [rbp+57h+arg_0], 0
0x18013f758  lea     rdx, aEnabledirectst; "EnableDirectStream"
0x18013f75f  mov     rax, [rcx]
0x18013f762  mov     rax, [rax+20h]
0x18013f766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f76b  test    eax, eax
0x18013f76d  js      short loc_18013F7CA
0x18013f76f  cmp     [rbp+57h+arg_0], 0
0x18013f773  jz      short loc_18013F7CA
0x18013f775  mov     rdx, [rbx]; struct IRDPCollection *
0x18013f778  lea     rcx, [rdi-30h]; this
0x18013f77c  call    ?InitializeQOEController@CRdpDynVCMgr@@IEAAJPEAUIRDPCollection@@@Z; CRdpDynVCMgr::InitializeQOEController(IRDPCollection *)
0x18013f781  test    eax, eax
0x18013f783  jns     short loc_18013F7BC
0x18013f785  mov     ecx, cs:CallbackContext
0x18013f78b  cmp     ecx, 3
0x18013f78e  jbe     short loc_18013F7BC
0x18013f790  mov     dword ptr [rbp+57h+var_88], eax
0x18013f793  lea     rdx, byte_1802996E3
0x18013f79a  lea     rax, aCrdpdynvcmgrIn_0; "CRdpDynVCMgr::InitializeInstance - Fail"...
0x18013f7a1  mov     [rbp+57h+var_A0], rax
0x18013f7a5  lea     rax, [rbp+57h+var_88]
0x18013f7a9  mov     [rsp+0F0h+var_C8], rax
0x18013f7ae  lea     rax, [rbp+57h+var_A0]
0x18013f7b2  mov     [rsp+0F0h+var_D0], rax
0x18013f7b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013f7bc  mov     rax, [rdi+4E20h]
0x18013f7c3  mov     byte ptr [rax+6B160h], 1
0x18013f7ca  mov     rcx, [rbp+57h+var_68]
0x18013f7ce  lea     r8, [rbp+57h+var_80]
0x18013f7d2  mov     dword ptr [rbp+57h+var_80], 0
0x18013f7d9  lea     rdx, aUserconfigured; "UserConfiguredTransportMode"
0x18013f7e0  mov     rax, [rcx]
0x18013f7e3  mov     rax, [rax+28h]
0x18013f7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f7ec  lea     rbx, [rdi+4DC0h]
0x18013f7f3  mov     edx, eax
0x18013f7f5  test    eax, eax
0x18013f7f7  js      short loc_18013F7FE
0x18013f7f9  mov     ecx, dword ptr [rbp+57h+var_80]
0x18013f7fc  mov     [rbx], ecx
0x18013f7fe  mov     eax, cs:CallbackContext
0x18013f804  cmp     eax, 4
0x18013f807  jbe     short loc_18013F843
0x18013f809  mov     eax, [rbx]
0x18013f80b  mov     dword ptr [rbp+57h+var_88], eax
0x18013f80e  lea     rax, aReadPropertyTr; "Read PROPERTY..TRANSPORT"
0x18013f815  mov     [rbp+57h+var_A0], rax
0x18013f819  lea     rax, [rbp+57h+var_88]
0x18013f81d  mov     [rsp+0F0h+var_C0], rax
0x18013f822  lea     rax, [rbp+57h+var_98]
0x18013f826  mov     [rsp+0F0h+var_C8], rax
0x18013f82b  lea     rax, [rbp+57h+var_A0]
0x18013f82f  mov     dword ptr [rbp+57h+var_98], edx
0x18013f832  lea     rdx, qword_180299668
0x18013f839  mov     [rsp+0F0h+var_D0], rax
0x18013f83e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013f843  mov     rcx, [rbp+57h+var_68]
0x18013f847  lea     r8, [rbp+57h+var_5C]
0x18013f84b  lea     rdx, aReplacecustomr; "ReplaceCustomRdpScheduler"
0x18013f852  mov     rax, [rcx]
0x18013f855  mov     rax, [rax+20h]
0x18013f859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f85e  test    eax, eax
0x18013f860  jns     short loc_18013F8BC
0x18013f862  mov     ecx, cs:CallbackContext
0x18013f868  cmp     ecx, 3
0x18013f86b  jbe     short loc_18013F8BC
0x18013f86d  mov     dword ptr [rbp+57h+var_98], eax
0x18013f870  lea     r14, aHresultFailedB; "HResult failed but continue"
0x18013f877  lea     rax, aFailedToGetPro_5; "Failed to get property whether to repla"...
0x18013f87e  mov     [rbp+57h+var_A0], rsi
0x18013f882  mov     [rbp+57h+var_90], rax
0x18013f886  lea     rdx, dword_1802996A4
0x18013f88d  lea     rax, [rbp+57h+var_A0]
0x18013f891  mov     [rbp+57h+var_88], r14
0x18013f895  mov     [rsp+0F0h+var_B8], rax
0x18013f89a  lea     rax, [rbp+57h+var_98]
0x18013f89e  mov     [rsp+0F0h+var_C0], rax
0x18013f8a3  lea     rax, [rbp+57h+var_90]
0x18013f8a7  mov     [rsp+0F0h+var_C8], rax
0x18013f8ac  lea     rax, [rbp+57h+var_88]
0x18013f8b0  mov     [rsp+0F0h+var_D0], rax
0x18013f8b5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18013f8ba  jmp     short loc_18013F8C3
0x18013f8bc  lea     r14, aHresultFailedB; "HResult failed but continue"
0x18013f8c3  mov     rcx, [rbp+57h+var_68]
0x18013f8c7  lea     r9, [rbp+57h+var_58]
0x18013f8cb  lea     r8, IID_IRdpSQMLogger
0x18013f8d2  lea     rdx, aRdpsqmloggerin; "RdpSqmLoggerInterface"
0x18013f8d9  mov     rax, [rcx]
0x18013f8dc  mov     rax, [rax+30h]
0x18013f8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f8e5  test    eax, eax
  ... truncated ...
```
