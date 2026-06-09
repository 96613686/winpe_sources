# CPipeManager::Initialize(IUnknown *)

- ea: `0x180093580`
- end: `0x180094a4f`
- name: `?Initialize@CPipeManager@@UEAAJPEAUIUnknown@@@Z`
- size: `5327`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a0a9c`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x180001574`
- `0x180001f84`
- `0x18000202c`
- `0x180002d3c`
- `0x18000305c`
- `0x180003184`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000f660`
- `0x18003b118`
- `0x180046e98`
- `0x18004d52c`
- `0x180076090`
- `0x180079724`
- `0x180079770`
- `0x18007e9e0`
- `0x18008718c`
- `0x180093580`
- `0x18009a8e8`
- `0x1800a29bc`
- `0x1800ab6e0`
- `0x1800ad250`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1800948ca`
- `RDPBASE!RDPServerStackDiagnostics_LogContext` at `0x1800948ca`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800946b3`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800948e0`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800946b3`
- `RDPBASE!RDPServerStackDiagnostics_LogCheckpoint` at `0x1800948e0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093dab`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ddc`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e0d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e3e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e6f`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ea0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ed1`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f02`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f33`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f64`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f95`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093fc6`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ff7`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180094028`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180094059`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009408a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800940bb`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800940ec`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009411d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009414e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009417f`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800941b0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800941e0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093dab`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ddc`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e0d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e3e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093e6f`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ea0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ed1`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f02`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f33`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f64`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093f95`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093fc6`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180093ff7`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180094028`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180094059`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009408a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800940bb`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800940ec`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009411d`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009414e`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x18009417f`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800941b0`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800941e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800944f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800944f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094a20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800944b8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800938fe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800938fe`
- `OLEAUT32!__imp_SysStringLen` at `0x180093814`
- `OLEAUT32!__imp_SysStringLen` at `0x180093814`
- `OLEAUT32!__imp_VariantInit` at `0x1800935d0`
- `OLEAUT32!__imp_VariantInit` at `0x1800935d0`
- `OLEAUT32!__imp_VariantClear` at `0x180093910`
- `OLEAUT32!__imp_VariantClear` at `0x180093910`

## string_xrefs

- `0x1800944aa`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18009375b`: `CRdpUT_CreateInstance failed!`
- `0x180093a75`: `RdpSurfaceManager::CreateInstance`
- `0x180093dca`: `RDV::RDP::GraphicsPipeline::PipelineLoopEnd`
- `0x180093dfb`: `RDV::RDP::GraphicsPipeline::PipelineProcessGfxSourceUpdatesStart`
- `0x180093e2c`: `RDV::RDP::GraphicsPipeline::PipelineProcessGfxSourceUpdatesEnd`
- `0x180093e5d`: `RDV::RDP::GraphicsPipeline::FlushSurfaceCommandsStart`
- `0x180093e8e`: `RDV::RDP::GraphicsPipeline::FlushSurfaceCommandsEnd`
- `0x180093f21`: `RDV::RDP::GraphicsPipeline::PipelineCheckForNewGfxSourceUpdatesStart`
- `0x180093f52`: `RDV::RDP::GraphicsPipeline::PipelineCheckForNewGfxSourceUpdatesEnd`
- `0x180093fe5`: `RDV::RDP::GraphicsPipeline::PipelineCommitSurfacesStart`
- `0x180094016`: `RDV::RDP::GraphicsPipeline::PipelineCommitSurfacesEnd`
- `0x180094279`: `ReplaceCustomRdpScheduler`
- `0x1800942b6`: `Failed to get property whether to replace custom RDP scheduler from platform context`
- `0x180094419`: `QOEAccumulator_CreateInstance Failed. Not critical`
- `0x180094434`: `Skipping QOEAccumulator creation inside CPipeManager since DirectStream is enabled`
- `0x1800946de`: `Failed to ReadWatermarkSettings`

## pseudocode

```c
__int64 __fastcall CPipeManager::Initialize(CPipeManager *this, struct IUnknown *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  signed int Instance; // edi
  struct IUnknown **v7; // rsi
  const struct _GUID *v8; // rdx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  _WORD *v14; // rdi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // r11
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // rdx
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  int v62; // eax
  char v63; // di
  unsigned int v64; // eax
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  _QWORD *v68; // rdi
  struct IUnknown *v69; // rcx
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  const char *v73; // rax
  char *v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  int v77; // ecx
  int v78; // r8d
  int v79; // r9d
  int v80; // ecx
  __int64 v81; // r8
  __int64 v82; // r9
  int v83; // r8d
  int v84; // r9d
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  int v88; // ecx
  __int64 v89; // r8
  __int64 v90; // r9
  unsigned int v91; // edi
  int v92; // ecx
  int v93; // r8d
  int v94; // r9d
  struct CpuInfo *CpuInfo; // rax
  int v96; // ecx
  int v97; // r8d
  int v98; // r9d
  int v99; // ecx
  int v100; // r8d
  int v101; // r9d
  const char *v103; // [rsp+60h] [rbp-69h] BYREF
  DWORD nSize; // [rsp+68h] [rbp-61h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-5Dh] BYREF
  const char *v106; // [rsp+70h] [rbp-59h] BYREF
  const char *v107; // [rsp+78h] [rbp-51h] BYREF
  DWORD Type[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v109; // [rsp+88h] [rbp-41h] BYREF
  const char *v110; // [rsp+90h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-31h] BYREF
  int v112; // [rsp+A8h] [rbp-21h] BYREF
  int v113; // [rsp+ACh] [rbp-1Dh] BYREF
  int v114; // [rsp+B0h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v117; // [rsp+D8h] [rbp+Fh] BYREF

  v114 = 0;
  hKey = 0;
  v112 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeManager *)((char *)this + 48896)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 17;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147467259);
LABEL_7:
    Instance = -2147467259;
    goto LABEL_138;
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeManager *)((char *)this + 12960)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 18;
    goto LABEL_6;
  }
  v7 = (struct IUnknown **)((char *)this + 13016);
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IRDPENCPlatformContext,
               (char *)this + 13016);
  if ( Instance < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_DWORD *)Data = 450;
      v106 = "QueryInterface(IID_IRDPENCPlatformContext) failed!";
      nSize = Instance;
      v107 = "Initialize";
      *(_QWORD *)Type = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v103 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&byte_18027C437,
        v9,
        v10,
        (__int64)&v103,
        (__int64)&nSize,
        (__int64)Type,
        (__int64)Data,
        (__int64)&v107,
        (__int64)&v106);
    }
    goto LABEL_138;
  }
  Instance = CRdpUT_CreateInstance(*v7, v8, (void **)this + 1625);
  if ( Instance < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      nSize = 457;
      v103 = "CRdpUT_CreateInstance failed!";
      *(_DWORD *)Data = Instance;
      v106 = "Initialize";
      v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      *(_QWORD *)Type = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_18027C3E9,
        v12,
        v13,
        (__int64)Type,
        (__int64)Data,
        (__int64)&v107,
        (__int64)&nSize,
        (__int64)&v106,
        (__int64)&v103);
    }
    goto LABEL_138;
  }
  v14 = (_WORD *)((char *)this + 53532);
  *((_WORD *)this + 26766) = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, const wchar_t *, VARIANTARG *))(*v7)->lpVtbl[1].QueryInterface)(
         *v7,
         L"GfxPipeline::ServerName",
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    if ( SysStringLen(pvarg.bstrVal) - 1 <= 0x63 )
    {
      v18 = StringCchCopyW((unsigned __int16 *)this + 26766, 0x65u, pvarg.bstrVal);
      if ( v18 >= 0 )
      {
        *((_WORD *)this + v22 + 26766) = 0;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v103 = (char *)this + 53532;
          v106 = "The server name property is available.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v19,
            (unsigned int)&byte_18027C36F,
            v20,
            v21,
            (__int64)&v106,
            (__int64)&v103);
        }
      }
      else
      {
        *v14 = 0;
        if ( (unsigned int)CallbackContext > 3 )
        {
          nSize = v18;
          v103 = "The server name property could not be retrieved.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_18027C39D,
            v20,
            v21,
            (__int64)&v103,
            (__int64)&nSize);
        }
      }
    }
  }
  else
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v103 = "The server name property is not available. Using localhost";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v15,
        (unsigned int)&byte_18027C3C7,
        v16,
        v17,
        (__int64)&v103);
    }
    nSize = 101;
    if ( !GetComputerNameW((LPWSTR)this + 26766, &nSize) )
      *v14 = 0;
  }
  VariantClear(&pvarg);
  if ( ((int (__fastcall *)(struct IUnknown *, const wchar_t *, GUID *, char *))(*v7)->lpVtbl[2].QueryInterface)(
         *v7,
         L"RDP::EventLog::Session",
         &IID_IGfxPipelineEventLogCallback,
         (char *)this + 13104) < 0
    && (unsigned int)CallbackContext > 4 )
  {
    v103 = "The pipeline event log callback interface is not available. Events won't be logged.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v23,
      (unsigned int)byte_18027C34D,
      v24,
      v25,
      (__int64)&v103);
  }
  if ( ((int (__fastcall *)(struct IUnknown *, const wchar_t *, GUID *, char *))(*v7)->lpVtbl[2].QueryInterface)(
         *v7,
         L"RDP::EventLog::Session",
         &IID_IRdpStateTransitionEventLogCallbacks,
         (char *)this + 13112) < 0
    && (unsigned int)CallbackContext > 4 )
  {
    v103 = "The pipeline event log callback interface is not available. Events won't be logged.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v26,
      (unsigned int)byte_18027C32B,
      v27,
      v28,
      (__int64)&v103);
  }
  if ( !(unsigned int)CTSCriticalSection::Initialize((CPipeManager *)((char *)this + 53080)) )
  {
    Instance = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      nSize = 526;
      v103 = "DFSS.Initialized";
      *(_DWORD *)Data = -2147024882;
      v106 = "Initialize";
      v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      *(_QWORD *)Type = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v29,
        (unsigned int)byte_18027C2DD,
        v30,
        v31,
        (__int64)Type,
        (__int64)Data,
        (__int64)&v107,
        (__int64)&nSize,
        (__int64)&v106,
        (__int64)&v103);
    }
    goto LABEL_138;
  }
  Instance = RdpSurfaceManager::CreateInstance((struct IRdpSurfaceManager **)this + 1633);
  if ( Instance < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      nSize = 529;
      v103 = "RdpSurfaceManager::CreateInstance";
      *(_DWORD *)Data = Instance;
      v106 = "Initialize";
      v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      *(_QWORD *)Type = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v32,
        (unsigned int)&byte_18027C28F,
        v33,
        v34,
        (__int64)Type,
        (__int64)Data,
        (__int64)&v107,
        (__int64)&nSize,
        (__int64)&v106,
        (__int64)&v103);
    }
    goto LABEL_138;
  }
  *((_QWORD *)this + 6180) = 0;
  *((_QWORD *)this + 6129) = (char *)this + 49048;
  *((_DWORD *)this + 12260) = 10;
  v35 = 0;
  *((_QWORD *)this + 6131) = 0;
  do
  {
    v36 = v35 + 2 * v35 + 1;
    ++v35;
    v37 = *((_QWORD *)this + 6129) + 8 * v36;
    *(_QWORD *)(v37 + 8) = *((_QWORD *)this + 6128);
    *((_QWORD *)this + 6128) = v37;
  }
  while ( v35 != 16 );
  *((_QWORD *)this + 6236) = 0;
  *((_QWORD *)this + 6185) = (char *)this + 49496;
  v38 = 0;
  *((_DWORD *)this + 12372) = 10;
  *((_QWORD *)this + 6187) = 0;
  do
  {
    v39 = v38 + 2 * v38 + 1;
    ++v38;
    v40 = *((_QWORD *)this + 6185) + 8 * v39;
    *(_QWORD *)(v40 + 8) = *((_QWORD *)this + 6184);
    *((_QWORD *)this + 6184) = v40;
  }
  while ( v38 != 16 );
  *((_QWORD *)this + 6292) = 0;
  *((_QWORD *)this + 6241) = (char *)this + 49944;
  v41 = 0;
  *((_DWORD *)this + 12484) = 10;
  *((_QWORD *)this + 6243) = 0;
  do
  {
    v42 = v41 + 2 * v41 + 1;
    ++v41;
    v43 = *((_QWORD *)this + 6241) + 8 * v42;
    *(_QWORD *)(v43 + 8) = *((_QWORD *)this + 6240);
    *((_QWORD *)this + 6240) = v43;
  }
  while ( v41 != 16 );
  *((_QWORD *)this + 6404) = 0;
  *((_QWORD *)this + 6353) = (char *)this + 50840;
  v44 = 0;
  *((_DWORD *)this + 12708) = 10;
  *((_QWORD *)this + 6355) = 0;
  do
  {
    v45 = v44 + 2 * v44 + 1;
    ++v44;
    v46 = *((_QWORD *)this + 6353) + 8 * v45;
    *(_QWORD *)(v46 + 8) = *((_QWORD *)this + 6352);
    *((_QWORD *)this + 6352) = v46;
  }
  while ( v44 != 16 );
  *((_QWORD *)this + 6460) = 0;
  *((_QWORD *)this + 6409) = (char *)this + 51288;
  v47 = 0;
  *((_DWORD *)this + 12820) = 10;
  *((_QWORD *)this + 6411) = 0;
  do
  {
    v48 = v47 + 2 * v47 + 1;
    ++v47;
    v49 = *((_QWORD *)this + 6409) + 8 * v48;
    *(_QWORD *)(v49 + 8) = *((_QWORD *)this + 6408);
    *((_QWORD *)this + 6408) = v49;
  }
  while ( v47 != 16 );
  *((_QWORD *)this + 6516) = 0;
  *((_QWORD *)this + 6465) = (char *)this + 51736;
  v50 = 0;
  *((_DWORD *)this + 12932) = 10;
  *((_QWORD *)this + 6467) = 0;
  do
  {
    v51 = v50 + 2 * v50 + 1;
    ++v50;
    v52 = *((_QWORD *)this + 6465) + 8 * v51;
    *(_QWORD *)(v52 + 8) = *((_QWORD *)this + 6464);
    *((_QWORD *)this + 6464) = v52;
  }
  while ( v50 != 16 );
  *((_QWORD *)this + 6572) = 0;
  *((_QWORD *)this + 6521) = (char *)this + 52184;
  v53 = 0;
  *((_DWORD *)this + 13044) = 10;
  *((_QWORD *)this + 6523) = 0;
  do
  {
    v54 = v53 + 2 * v53 + 1;
    ++v53;
    v55 = *((_QWORD *)this + 6521) + 8 * v54;
    *(_QWORD *)(v55 + 8) = *((_QWORD *)this + 6520);
    *((_QWORD *)this + 6520) = v55;
  }
  while ( v53 != 16 );
  *((_QWORD *)this + 6348) = 0;
  *((_QWORD *)this + 6297) = (char *)this + 50392;
  v56 = 0;
  *((_DWORD *)this + 12596) = 10;
  *((_QWORD *)this + 6299) = 0;
  do
  {
    v57 = v56 + 2 * v56 + 1;
    ++v56;
    v58 = *((_QWORD *)this + 6297) + 8 * v57;
    *(_QWORD *)(v58 + 8) = *((_QWORD *)this + 6296);
    *((_QWORD *)this + 6296) = v58;
  }
  while ( v56 != 16 );
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineLoopStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52768);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineLoopEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52776);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineProcessGfxSourceUpdatesStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52784);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineProcessGfxSourceUpdatesEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52792);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::FlushSurfaceCommandsStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52800);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::FlushSurfaceCommandsEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52808);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineOverallFrameStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52816);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineOverallFrameEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52824);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineCheckForNewGfxSourceUpdatesStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52880);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineCheckForNewGfxSourceUpdatesEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52888);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineProcessSurfacesStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52832);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineProcessSurfacesEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52840);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineCommitSurfacesStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52848);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineCommitSurfacesEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52856);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineRunWorkitemsStart",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52864);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineRunWorkitemsEnd",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52872);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineThrottle",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52896);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineNewFrameId",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52912);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::EstimatedClientFrameInterval",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52920);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::ProgressiveIntraframeRefinement",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52928);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineNewFrame",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52952);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::RDP::GraphicsPipeline::PipelineEndFrameReport",
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52960);
  if ( Instance < 0 )
    goto LABEL_138;
  Instance = RDPAPI_GetGenericCounter(
               L"RDV::CLOUDDV::QOE::QOEServerFrameAckd",
               0,
               0,
               0xFFFFFFFFLL,
               4,
               (char *)this + 52968);
  if ( Instance < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      nSize = 569;
      v103 = "RDPAPI_GetGenericCounter QOEServerFrameAckd failed";
      *(_DWORD *)Data = Instance;
      v106 = "Initialize";
      v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      *(_QWORD *)Type = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v59,
        (unsigned int)byte_18027C241,
        v60,
        v61,
        (__int64)Type,
        (__int64)Data,
        (__int64)&v107,
        (__int64)&nSize,
        (__int64)&v106,
        (__int64)&v103);
    }
    goto LABEL_138;
  }
  v62 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, int *))(*v7)->lpVtbl[1].AddRef)(
          *v7,
          L"ReplaceCustomRdpScheduler",
          &v112);
  v63 = v62;
  if ( v62 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v64 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v64,
      (__int64)"Failed to get property whether to replace custom RDP scheduler from platform context",
      v63);
  }
  if ( !v112 )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, char *))(*v7)->lpVtbl[4].Release)(*v7, (char *)this + 12976);
    if ( Instance < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        nSize = 577;
        v103 = "GetScheduler failed!";
        *(_DWORD *)Data = Instance;
        v106 = "Initialize";
        v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        *(_QWORD *)Type = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v65,
          (unsigned int)byte_18027C1F3,
          v66,
          v67,
          (__int64)Type,
          (__int64)Data,
          (__int64)&v107,
          (__int64)&nSize,
          (__int64)&v106,
          (__int64)&v103);
      }
      goto LABEL_138;
    }
  }
  v68 = (_QWORD *)((char *)this + 13120);
  ((void (__fastcall *)(struct IUnknown *, char *))(*v7)->lpVtbl[5].QueryInterface)(*v7, (char *)this + 13120);
  if ( *((_QWORD *)this + 1640)
    && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1640) + 64LL))(*((_QWORD *)this + 1640))
    && *v68 )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13120);
    *v68 = 0;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 13120);
  }
  v69 = *v7;
  v113 = 0;
  ((void (__fastcall *)(struct IUnknown *, const wchar_t *, int *))v69->lpVtbl[1].AddRef)(
    v69,
    L"EnableDirectStream",
    &v113);
  if ( v113 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v73 = "Skipping QOEAccumulator creation inside CPipeManager since DirectStream is enabled";
      v74 = &byte_18027C1AF;
      goto LABEL_104;
    }
  }
  else if ( (int)QOEAccumulator_CreateInstance((struct QOEAccumulator **)this + 6576) < 0
         && (unsigned int)CallbackContext > 3 )
  {
    v73 = "QOEAccumulator_CreateInstance Failed. Not critical";
    v74 = byte_18027C1D1;
LABEL_104:
    v103 = v73;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v70,
      (_DWORD)v74,
      v71,
      v72,
      (__int64)&v103);
  }
  if ( ((int (__fastcall *)(struct IUnknown *, const wchar_t *, int *))(*v7)->lpVtbl[1].Release)(
         *v7,
         L"ReverseConnectMode",
         &v114) >= 0 )
  {
    if ( v114 )
    {
      *((_DWORD *)this + 12234) = 1;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
              0,
              0x20019u,
              &hKey) )
      {
        *(_DWORD *)Data = 0;
        nSize = 4;
        Type[0] = 0;
        if ( !RegQueryValueExW(hKey, L"fEnableScreenCaptureProtect", 0, Type, Data, &nSize) )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            LODWORD(v107) = *(_DWORD *)Data;
            v103 = "Using ScreenCaptureProtectionMode (0=Off, 1=On)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v77,
              (unsigned int)&dword_18027C16C,
              v78,
              v79,
              (__int64)&v103,
              (__int64)&v107);
          }
          *((_DWORD *)this + 13439) = *(_DWORD *)Data;
        }
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, _QWORD))(*v7)->lpVtbl[3].QueryInterface)(
                     *v7,
                     L"EnableScreenCaptureProtection",
                     *((unsigned int *)this + 13439));
        if ( Instance < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v107) = 660;
            v103 = "Failed to set CONN_PROPERTY_ENABLE_SCREEN_CAPTURE_PROTECTION property";
            LODWORD(v106) = Instance;
            v109 = (__int64)"Initialize";
            v110 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            *(_QWORD *)&ActivityId.Data1 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v80,
              (unsigned int)word_18027C11A,
              v81,
              v82,
              (__int64)&ActivityId,
              (__int64)&v106,
              (__int64)&v110,
              (__int64)&v107,
              (__int64)&v109,
              (__int64)&v103);
          }
          goto LABEL_138;
        }
        if ( (unsigned int)CallbackContext > 4
          && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v81, v82) )
        {
          LODWORD(v106) = *((_DWORD *)this + 13439);
          v103 = (const char *)0x1000000;
          *(_QWORD *)&ActivityId.Data1 = (char *)this + 13552;
          v110 = "PipeMgr";
          v109 = (__int64)"Stack";
          *(_QWORD *)&v117 = "Checkpoint";
          LODWORD(v107) = (_DWORD)v106 != 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v107,
            (unsigned int)byte_18027C08B,
            v83,
            v84,
            (__int64)&v117,
            (__int64)&v103,
            (__int64)&v109,
            (__int64)&v110,
            (__int64)&ActivityId,
            (__int64)&v107,
            (__int64)&v106);
        }
        if ( *((_DWORD *)this + 13439) )
          RDPServerStackDiagnostics_LogCheckpoint((char *)this + 13552, 780);
        Instance = CPipeManager::ReadWatermarkSettings(this, hKey);
        if ( Instance < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v106) = 678;
            *(_QWORD *)&v117 = "Failed to ReadWatermarkSettings";
            LODWORD(v107) = Instance;
            *(_QWORD *)&ActivityId.Data1 = "Initialize";
            v110 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v109 = (__int64)"Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v85,
              (unsigned int)byte_18027C039,
              v86,
              v87,
              (__int64)&v109,
              (__int64)&v107,
              (__int64)&v110,
              (__int64)&v106,
              (__int64)&ActivityId,
              (__int64)&v117);
          }
          goto LABEL_138;
        }
        v106 = (const char *)*v7;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v106);
        Instance = DisplayProtectionManager::Initialize((CPipeManager *)((char *)this + 13136));
        if ( Instance < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v106) = 684;
            *(_QWORD *)&v117 = "Failed to initialize displayProtectionManager";
            LODWORD(v107) = Instance;
            *(_QWORD *)&ActivityId.Data1 = "Initialize";
            v110 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
            v109 = (__int64)"Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v88,
              (unsigned int)&byte_18027BFE7,
              v89,
              v90,
              (__int64)&v109,
              (__int64)&v107,
              (__int64)&v110,
              (__int64)&v106,
              (__int64)&ActivityId,
              (__int64)&v117);
          }
          goto LABEL_138;
        }
        v91 = *((_DWORD *)this + 3286);
        if ( (unsigned int)CallbackContext > 4
          && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v89, v90) )
        {
          LODWORD(v106) = v91;
          v109 = 0x1000000;
          LODWORD(v107) = v91 != 0;
          *(_QWORD *)&v117 = (char *)this + 13552;
          *(_QWORD *)&ActivityId.Data1 = "PipeMgr";
          v110 = "Stack";
          v103 = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v92,
            (unsigned int)byte_18027BF55,
            v93,
            v94,
            (__int64)&v103,
            (__int64)&v109,
            (__int64)&v110,
            (__int64)&ActivityId,
            (__int64)&v117,
            (__int64)&v107,
            (__int64)&v106);
        }
        v117 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
        RDPServerStackDiagnostics_LogContext(&v117, 8, v91);
        if ( v91 )
          RDPServerStackDiagnostics_LogCheckpoint((char *)this + 13552, 783);
      }
    }
  }
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v75, v76) )
  {
    CpuInfo = GetCpuInfo();
    *(_QWORD *)&ActivityId.Data1 = "PipeMgr";
    v110 = "Stack";
    v103 = "Checkpoint";
    v96 = *(_DWORD *)CpuInfo;
    *(_QWORD *)&v117 = (char *)this + 13552;
    LODWORD(v106) = v96;
    v109 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v96,
      (unsigned int)byte_18027BEE3,
      v97,
      v98,
      (__int64)&v103,
      (__int64)&v109,
      (__int64)&v110,
      (__int64)&ActivityId,
      (__int64)&v117,
      (__int64)&v106);
  }
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v75, v76) )
  {
    *(_QWORD *)&ActivityId.Data1 = "PipeMgr";
    *(_QWORD *)&v117 = (char *)this + 13552;
    v110 = "Stack";
    v109 = 0x1000000;
    v103 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v99,
      (unsigned int)byte_18027BE83,
      v100,
      v101,
      (__int64)&v103,
      (__int64)&v109,
      (__int64)&v110,
      (__int64)&ActivityId,
      (__int64)&v117);
  }
  Instance = 0;
LABEL_138:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180093580  mov     [rsp-8+arg_10], rbx
0x180093585  push    rbp
0x180093586  push    rsi
0x180093587  push    rdi
0x180093588  push    r12
0x18009358a  push    r13
0x18009358c  push    r14
0x18009358e  push    r15
0x180093590  lea     rbp, [rsp-27h]
0x180093595  sub     rsp, 0F0h
0x18009359c  mov     rax, cs:__security_cookie
0x1800935a3  xor     rax, rsp
0x1800935a6  mov     [rbp+57h+var_38], rax
0x1800935aa  xor     r15d, r15d
0x1800935ad  mov     rbx, rcx
0x1800935b0  xorps   xmm0, xmm0
0x1800935b3  mov     [rbp+57h+var_70], r15d
0x1800935b7  xor     eax, eax
0x1800935b9  mov     [rbp+57h+hKey], r15
0x1800935bd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800935c1  mov     [rbp+57h+var_78], r15d
0x1800935c5  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800935c9  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800935cd  mov     rdi, rdx
0x1800935d0  call    cs:__imp_VariantInit
0x1800935d6  lea     rcx, [rbx+0BF00h]; this
0x1800935dd  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800935e2  test    eax, eax
0x1800935e4  jnz     short loc_18009363E
0x1800935e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800935ed  lea     rax, WPP_GLOBAL_Control
0x1800935f4  cmp     rcx, rax
0x1800935f7  jz      short loc_180093634
0x1800935f9  lea     r14d, [r15+8]
0x1800935fd  test    [rcx+1Ch], r14b
0x180093601  jz      short loc_180093634
0x180093603  cmp     byte ptr [rcx+19h], 2
0x180093607  jb      short loc_180093634
0x180093609  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009360e  lea     edx, [r15+11h]
0x180093612  mov     rcx, cs:WPP_GLOBAL_Control
0x180093619  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180093620  mov     r9d, eax
0x180093623  mov     dword ptr [rsp+120h+phkResult], 80004005h
0x18009362b  mov     rcx, [rcx+10h]
0x18009362f  call    WPP_SF_Dd
0x180093634  mov     edi, 80004005h
0x180093639  jmp     loc_180094A17
0x18009363e  lea     rcx, [rbx+32A0h]; this
0x180093645  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18009364a  test    eax, eax
0x18009364c  jnz     short loc_18009367E
0x18009364e  mov     rcx, cs:WPP_GLOBAL_Control
0x180093655  lea     rax, WPP_GLOBAL_Control
0x18009365c  cmp     rcx, rax
0x18009365f  jz      short loc_180093634
0x180093661  mov     r14d, 8
0x180093667  test    [rcx+1Ch], r14b
0x18009366b  jz      short loc_180093634
0x18009366d  cmp     byte ptr [rcx+19h], 2
0x180093671  jb      short loc_180093634
0x180093673  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180093678  lea     edx, [r14+0Ah]
0x18009367c  jmp     short loc_180093612
0x18009367e  mov     rax, [rdi]
0x180093681  lea     rsi, [rbx+32D8h]
0x180093688  mov     r8, rsi
0x18009368b  lea     rdx, IID_IRDPENCPlatformContext
0x180093692  mov     rcx, rdi
0x180093695  mov     rax, [rax]
0x180093698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009369d  mov     edi, eax
0x18009369f  test    eax, eax
0x1800936a1  jns     loc_180093733
0x1800936a7  mov     ecx, cs:CallbackContext
0x1800936ad  cmp     ecx, 2
0x1800936b0  jbe     loc_180094A17
0x1800936b6  lea     rax, aQueryinterface_6; "QueryInterface(IID_IRDPENCPlatformConte"...
0x1800936bd  mov     dword ptr [rbp+57h+Data], 1C2h
0x1800936c4  mov     [rbp+57h+var_B0], rax
0x1800936c8  lea     rdx, byte_18027C437
0x1800936cf  lea     rax, aInitialize; "Initialize"
0x1800936d6  mov     [rbp+57h+nSize], edi
0x1800936d9  mov     [rbp+57h+var_A8], rax
0x1800936dd  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800936e4  mov     qword ptr [rbp+57h+Type], rax
0x1800936e8  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800936ef  mov     [rbp+57h+var_C0], rax
0x1800936f3  lea     rax, [rbp+57h+var_B0]
0x1800936f7  mov     [rsp+120h+var_D8], rax
0x1800936fc  lea     rax, [rbp+57h+var_A8]
0x180093700  mov     [rsp+120h+var_E0], rax
0x180093705  lea     rax, [rbp+57h+Data]
0x180093709  mov     [rsp+120h+var_E8], rax
0x18009370e  lea     rax, [rbp+57h+Type]
0x180093712  mov     [rsp+120h+var_F0], rax
0x180093717  lea     rax, [rbp+57h+nSize]
0x18009371b  mov     [rsp+120h+lpcbData], rax
0x180093720  lea     rax, [rbp+57h+var_C0]
0x180093724  mov     [rsp+120h+phkResult], rax
0x180093729  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009372e  jmp     loc_180094A17
0x180093733  mov     rcx, [rsi]; struct IUnknown *
0x180093736  lea     r8, [rbx+32C8h]; void **
0x18009373d  call    ?CRdpUT_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CRdpUT_CreateInstance(IUnknown *,_GUID const &,void * *)
0x180093742  mov     edi, eax
0x180093744  test    eax, eax
0x180093746  jns     loc_1800937CE
0x18009374c  mov     eax, cs:CallbackContext
0x180093752  cmp     eax, 2
0x180093755  jbe     loc_180094A17
0x18009375b  lea     rax, aCrdputCreatein; "CRdpUT_CreateInstance failed!"
0x180093762  mov     [rbp+57h+nSize], 1C9h
0x180093769  mov     [rbp+57h+var_C0], rax
0x18009376d  lea     rdx, byte_18027C3E9
0x180093774  lea     rax, aInitialize; "Initialize"
0x18009377b  mov     dword ptr [rbp+57h+Data], edi
0x18009377e  mov     [rbp+57h+var_B0], rax
0x180093782  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180093789  mov     [rbp+57h+var_A8], rax
0x18009378d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180093794  mov     qword ptr [rbp+57h+Type], rax
0x180093798  lea     rax, [rbp+57h+var_C0]
0x18009379c  mov     [rsp+120h+var_D8], rax
0x1800937a1  lea     rax, [rbp+57h+var_B0]
0x1800937a5  mov     [rsp+120h+var_E0], rax
0x1800937aa  lea     rax, [rbp+57h+nSize]
0x1800937ae  mov     [rsp+120h+var_E8], rax
0x1800937b3  lea     rax, [rbp+57h+var_A8]
0x1800937b7  mov     [rsp+120h+var_F0], rax
0x1800937bc  lea     rax, [rbp+57h+Data]
0x1800937c0  mov     [rsp+120h+lpcbData], rax
0x1800937c5  lea     rax, [rbp+57h+Type]
0x1800937c9  jmp     loc_180093724
0x1800937ce  lea     rdi, [rbx+0D11Ch]
0x1800937d5  mov     [rdi], r15w
0x1800937d9  lea     r8, [rbp+57h+pvarg]
0x1800937dd  mov     rcx, [rsi]
0x1800937e0  lea     rdx, aGfxpipelineSer; "GfxPipeline::ServerName"
0x1800937e7  mov     rax, [rcx]
0x1800937ea  mov     rax, [rax+18h]
0x1800937ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800937f3  mov     r13d, 4
0x1800937f9  lea     r14d, [r13+4]
0x1800937fd  test    eax, eax
0x1800937ff  js      loc_1800938C5
0x180093805  cmp     word ptr [rbp+57h+pvarg], r14w
0x18009380a  jnz     loc_1800938C5
0x180093810  mov     rcx, qword ptr [rbp+57h+pvarg+8]; pbstr
0x180093814  call    cs:__imp_SysStringLen
0x18009381a  mov     r11d, eax
0x18009381d  lea     ecx, [r11-1]
0x180093821  cmp     ecx, 63h ; 'c'
0x180093824  ja      loc_18009390C
0x18009382a  mov     r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18009382e  lea     edx, [r13+61h]; unsigned __int64
0x180093832  mov     rcx, rdi; unsigned __int16 *
0x180093835  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009383a  test    eax, eax
0x18009383c  jns     short loc_180093882
0x18009383e  mov     [rdi], r15w
0x180093842  mov     ecx, cs:CallbackContext
0x180093848  cmp     ecx, 3
0x18009384b  jbe     loc_18009390C
0x180093851  mov     [rbp+57h+nSize], eax
0x180093854  lea     rdx, byte_18027C39D
0x18009385b  lea     rax, aTheServerNameP; "The server name property could not be r"...
0x180093862  mov     [rbp+57h+var_C0], rax
0x180093866  lea     rax, [rbp+57h+nSize]
0x18009386a  mov     [rsp+120h+lpcbData], rax
0x18009386f  lea     rax, [rbp+57h+var_C0]
0x180093873  mov     [rsp+120h+phkResult], rax
0x180093878  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009387d  jmp     loc_18009390C
0x180093882  mov     [rbx+r11*2+0D11Ch], r15w
0x18009388b  mov     eax, cs:CallbackContext
0x180093891  cmp     eax, r13d
0x180093894  jbe     short loc_18009390C
0x180093896  lea     rax, aTheServerNameP_1; "The server name property is available."
0x18009389d  mov     [rbp+57h+var_C0], rdi
0x1800938a1  mov     [rbp+57h+var_B0], rax
0x1800938a5  lea     rdx, byte_18027C36F
0x1800938ac  lea     rax, [rbp+57h+var_C0]
0x1800938b0  mov     [rsp+120h+lpcbData], rax
0x1800938b5  lea     rax, [rbp+57h+var_B0]
0x1800938b9  mov     [rsp+120h+phkResult], rax
0x1800938be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800938c3  jmp     short loc_18009390C
0x1800938c5  mov     eax, cs:CallbackContext
0x1800938cb  cmp     eax, r13d
0x1800938ce  jbe     short loc_1800938F0
0x1800938d0  lea     rax, aTheServerNameP_0; "The server name property is not availab"...
0x1800938d7  mov     [rbp+57h+var_C0], rax
0x1800938db  lea     rdx, byte_18027C3C7
0x1800938e2  lea     rax, [rbp+57h+var_C0]
0x1800938e6  mov     [rsp+120h+phkResult], rax
0x1800938eb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800938f0  lea     rdx, [rbp+57h+nSize]; nSize
0x1800938f4  mov     [rbp+57h+nSize], 65h ; 'e'
0x1800938fb  mov     rcx, rdi; lpBuffer
0x1800938fe  call    cs:__imp_GetComputerNameW
0x180093904  test    eax, eax
0x180093906  jnz     short loc_18009390C
0x180093908  mov     [rdi], r15w
0x18009390c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180093910  call    cs:__imp_VariantClear
0x180093916  mov     rcx, [rsi]
0x180093919  lea     r9, [rbx+3330h]
0x180093920  lea     r8, IID_IGfxPipelineEventLogCallback
0x180093927  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18009392e  mov     rax, [rcx]
0x180093931  mov     rax, [rax+30h]
0x180093935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009393a  lea     rdi, aThePipelineEve; "The pipeline event log callback interfa"...
0x180093941  test    eax, eax
0x180093943  jns     short loc_180093969
0x180093945  mov     eax, cs:CallbackContext
0x18009394b  cmp     eax, r13d
0x18009394e  jbe     short loc_180093969
0x180093950  lea     rax, [rbp+57h+var_C0]
0x180093954  mov     [rbp+57h+var_C0], rdi
0x180093958  lea     rdx, byte_18027C34D
0x18009395f  mov     [rsp+120h+phkResult], rax
0x180093964  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180093969  mov     rcx, [rsi]
0x18009396c  lea     r9, [rbx+3338h]
0x180093973  lea     r8, IID_IRdpStateTransitionEventLogCallbacks
0x18009397a  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x180093981  mov     rax, [rcx]
0x180093984  mov     rax, [rax+30h]
0x180093988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009398d  test    eax, eax
0x18009398f  jns     short loc_1800939B5
0x180093991  mov     eax, cs:CallbackContext
0x180093997  cmp     eax, r13d
0x18009399a  jbe     short loc_1800939B5
0x18009399c  lea     rax, [rbp+57h+var_C0]
0x1800939a0  mov     [rbp+57h+var_C0], rdi
0x1800939a4  lea     rdx, byte_18027C32B
0x1800939ab  mov     [rsp+120h+phkResult], rax
0x1800939b0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800939b5  lea     rcx, [rbx+0CF58h]; this
0x1800939bc  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800939c1  test    eax, eax
0x1800939c3  jnz     loc_180093A50
0x1800939c9  mov     eax, cs:CallbackContext
0x1800939cf  mov     edi, 8007000Eh
0x1800939d4  cmp     eax, 2
0x1800939d7  jbe     loc_180094A17
0x1800939dd  lea     rax, aDfssInitialize; "DFSS.Initialized"
0x1800939e4  mov     [rbp+57h+nSize], 20Eh
0x1800939eb  mov     [rbp+57h+var_C0], rax
0x1800939ef  lea     rdx, byte_18027C2DD
0x1800939f6  lea     rax, aInitialize; "Initialize"
0x1800939fd  mov     dword ptr [rbp+57h+Data], edi
0x180093a00  mov     [rbp+57h+var_B0], rax
0x180093a04  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180093a0b  mov     [rbp+57h+var_A8], rax
0x180093a0f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180093a16  mov     qword ptr [rbp+57h+Type], rax
0x180093a1a  lea     rax, [rbp+57h+var_C0]
0x180093a1e  mov     [rsp+120h+var_D8], rax
0x180093a23  lea     rax, [rbp+57h+var_B0]
0x180093a27  mov     [rsp+120h+var_E0], rax
0x180093a2c  lea     rax, [rbp+57h+nSize]
0x180093a30  mov     [rsp+120h+var_E8], rax
0x180093a35  lea     rax, [rbp+57h+var_A8]
0x180093a39  mov     [rsp+120h+var_F0], rax
0x180093a3e  lea     rax, [rbp+57h+Data]
0x180093a42  mov     [rsp+120h+lpcbData], rax
0x180093a47  lea     rax, [rbp+57h+Type]
0x180093a4b  jmp     loc_180093724
0x180093a50  lea     rcx, [rbx+3308h]; struct IRdpSurfaceManager **
0x180093a57  call    ?CreateInstance@RdpSurfaceManager@@SAJPEAPEAVIRdpSurfaceManager@@@Z; RdpSurfaceManager::CreateInstance(IRdpSurfaceManager * *)
0x180093a5c  mov     edi, eax
0x180093a5e  test    eax, eax
0x180093a60  jns     loc_180093AE8
0x180093a66  mov     eax, cs:CallbackContext
0x180093a6c  cmp     eax, 2
0x180093a6f  jbe     loc_180094A17
0x180093a75  lea     rax, aRdpsurfacemana_4; "RdpSurfaceManager::CreateInstance"
0x180093a7c  mov     [rbp+57h+nSize], 211h
0x180093a83  mov     [rbp+57h+var_C0], rax
0x180093a87  lea     rdx, byte_18027C28F
0x180093a8e  lea     rax, aInitialize; "Initialize"
0x180093a95  mov     dword ptr [rbp+57h+Data], edi
0x180093a98  mov     [rbp+57h+var_B0], rax
0x180093a9c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180093aa3  mov     [rbp+57h+var_A8], rax
0x180093aa7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180093aae  mov     qword ptr [rbp+57h+Type], rax
0x180093ab2  lea     rax, [rbp+57h+var_C0]
0x180093ab6  mov     [rsp+120h+var_D8], rax
0x180093abb  lea     rax, [rbp+57h+var_B0]
0x180093abf  mov     [rsp+120h+var_E0], rax
0x180093ac4  lea     rax, [rbp+57h+nSize]
0x180093ac8  mov     [rsp+120h+var_E8], rax
0x180093acd  lea     rax, [rbp+57h+var_A8]
0x180093ad1  mov     [rsp+120h+var_F0], rax
0x180093ad6  lea     rax, [rbp+57h+Data]
  ... truncated ...
```
