# CPipeManager::InitializeInstance(IRDPCoreVirtualChannel *,IRDPCoreChannelManager *,IRdpGFXSource *,IRdpPipeProtocol *,IRDPCollection *,IRdpGfxPipeLineStateEvents *,IRdpPipeEvents *,IRdpPipeExtensionFactory *)

- ea: `0x180094a60`
- end: `0x18009613e`
- name: `?InitializeInstance@CPipeManager@@UEAAJPEAUIRDPCoreVirtualChannel@@PEAUIRDPCoreChannelManager@@PEAUIRdpGFXSource@@PEAVIRdpPipeProtocol@@PEAUIRDPCollection@@PEAVIRdpGfxPipeLineStateEvents@@PEAVIRdpPipeEvents@@PEAVIRdpPipeExtensionFactory@@@Z`
- size: `5854`
- prototype: `__int64 __usercall@<rax>(CPipeManager *__hidden this@<rcx>, struct IRDPCoreVirtualChannel *@<rdx>, struct IRDPCoreChannelManager *@<r8>, struct IRdpGFXSource *@<r9>, struct IRdpPipeProtocol *, struct IRDPCollection *, struct IRdpGfxPipeLineStateEvents *, struct IRdpPipeEvents *, struct IRdpPipeExtensionFactory *)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x180001f84`
- `0x18000202c`
- `0x180002568`
- `0x180002d3c`
- `0x18000ce04`
- `0x18000ce34`
- `0x180010d6c`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x180089e40`
- `0x180089ef0`
- `0x18008dd80`
- `0x180091920`
- `0x180094a60`
- `0x180096144`
- `0x180097a08`
- `0x18009d364`
- `0x18009f3c0`
- `0x1800ac38c`
- `0x1800ac70c`
- `0x1800d6d90`
- `0x1800d8a50`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RdpTaskTrigger_CreateInstance` at `0x180095e6c`
- `RDPBASE!RdpTaskTrigger_CreateInstance` at `0x180095e6c`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800951bc`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800952a2`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x180095388`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800951bc`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x1800952a2`
- `RDPBASE!RDPAPI_GetLongCounter` at `0x180095388`
- `OLEAUT32!__imp_VariantInit` at `0x180094af1`
- `OLEAUT32!__imp_VariantInit` at `0x180094afb`
- `OLEAUT32!__imp_VariantInit` at `0x180094b05`
- `OLEAUT32!__imp_VariantInit` at `0x180094b0f`
- `OLEAUT32!__imp_VariantInit` at `0x180094b19`
- `OLEAUT32!__imp_VariantInit` at `0x180094af1`
- `OLEAUT32!__imp_VariantInit` at `0x180094afb`
- `OLEAUT32!__imp_VariantInit` at `0x180094b05`
- `OLEAUT32!__imp_VariantInit` at `0x180094b0f`
- `OLEAUT32!__imp_VariantInit` at `0x180094b19`
- `OLEAUT32!__imp_VariantClear` at `0x180095ffe`
- `OLEAUT32!__imp_VariantClear` at `0x180096008`
- `OLEAUT32!__imp_VariantClear` at `0x180096012`
- `OLEAUT32!__imp_VariantClear` at `0x18009601c`
- `OLEAUT32!__imp_VariantClear` at `0x180095ffe`
- `OLEAUT32!__imp_VariantClear` at `0x180096008`
- `OLEAUT32!__imp_VariantClear` at `0x180096012`
- `OLEAUT32!__imp_VariantClear` at `0x18009601c`

## string_xrefs

- `0x180094d4c`: `RdpQrCodeHelperDllHandle`
- `0x180095cfa`: `ReplaceCustomRdpScheduler`
- `0x180095d37`: `Failed to get property whether to replace custom RDP scheduler from platform context`
- `0x180094be3`: `pExtensionFactory`
- `0x180094e0d`: `ReverseConnectGatewayUri`
- `0x180094e34`: `Failed to get CONN_PROPERTY_WVD_GATEWAY_URI property value. Not critical.`
- `0x180094e6e`: `Failed to set reverse connect gateway Uri in QOEAccumulator. Not critical`
- `0x180094e9b`: `ReverseConnectHostPoolArmPath`
- `0x180094ec1`: `Failed to get CONN_PROPERTY_WVD_HOSTPOOL_ARMPATH property value`
- `0x180094f07`: `Failed to set reverse connect hostpool arm path in QOEAccumulator`
- `0x180095008`: `WVD Config - DisableScreenCaptureProtectionDisconnect set by WVD config`
- `0x18009506d`: `WVD Config - EnableDisconnectOnFrameAckTimeout set by WVD config`
- `0x1800950d2`: `WVD Config - frameAckTimeoutThreshold set by WVD config`
- `0x180095147`: `WVD Config - QoEFrameDataLoggingThreshold set by WVD config`
- `0x180095462`: `PipeManagerError_InitInstanceCreateLegacyProtocolFail`
- `0x18009548a`: `Failed to create legacy protocol`
- `0x180095549`: `PipeManagerError_InitInstanceInitUpdateTrackerFail`
- `0x180095571`: `IRdpUpdateTracker::InitializeInstance failed`
- `0x18009560a`: `PipeManagerError_InitInstanceCreateFbrProtocolFail`
- `0x180095632`: `Failed to create FBR protocol`
- `0x180095783`: `PipeManagerError_InitInstanceCreateChannelFail`
- `0x1800957ab`: `CreateChannel(RDPGFX_CHANNEL_NAME) failed!`
- `0x18009585d`: `Test Config - MouseCursor DVC disabled by test config`
- `0x1800958b1`: `CreateChannel(Microsoft::Windows::RDS::MouseCursor) failed.  Non-Fatal.`
- `0x1800958ff`: `CreateChannel(ECHO) failed.  Non-Fatal.`
- `0x180095957`: `Capability: Cache: Cache manager is disabled`
- `0x1800959bd`: `PipeManagerError_InitInstanceInitProtocolFail`
- `0x1800959e5`: `IRdpPipeprotocol::InitializeInstance failed`
- `0x180095a7a`: `PipeManagerError_InitInstanceCreateBindVCFail`
- `0x180095aa2`: `CreateAndBindVideoChannel failed`
- `0x180095daf`: `Failed to get thread pool handle.`
- `0x180095e83`: `Failed to create task trigger instance`
- `0x180095ea2`: `Task trigger instance is initialized.`
- `0x1800960c1`: `Gfx Pluging failed to Register Worker with Scheduler`

## pseudocode

```c
__int64 __fastcall CPipeManager::InitializeInstance(
        CPipeManager *this,
        struct IRDPCoreVirtualChannel *a2,
        struct IUnknown *a3,
        struct IRdpGFXSource *a4,
        struct IRdpPipeProtocol *a5,
        struct IRDPCollection *a6,
        struct IRdpGfxPipeLineStateEvents *a7,
        struct IRdpPipeEvents *a8,
        struct IRdpPipeExtensionFactory *a9)
{
  int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct IRdpPipeExtensionFactory *v13; // r13
  unsigned int v14; // eax
  struct IRdpGfxPipeLineStateEvents *v15; // rsi
  unsigned int v16; // r14d
  unsigned int Lo; // r12d
  struct IRdpPipeProtocol *v18; // rbx
  struct IRdpPipeProtocol **v19; // rsi
  struct IRDPCollection *v20; // r15
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  char *v24; // rdx
  const char **v25; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  const char *v29; // rax
  char *v30; // rdx
  QOEAccumulator *v31; // rcx
  int v32; // ecx
  __int64 v33; // r8
  __int64 v34; // r9
  const char *v35; // rax
  char *v36; // rdx
  QOEAccumulator *v37; // rcx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // r8d
  int v51; // r9d
  __int64 v52; // rcx
  signed int LongCounter; // eax
  signed int v54; // eax
  signed int v55; // eax
  const struct _GUID *v56; // rdx
  signed int Instance; // eax
  __int64 v58; // rcx
  signed int v59; // eax
  signed int v60; // eax
  struct IUnknown v61; // rax
  signed int v62; // eax
  int v63; // ecx
  int v64; // r8d
  int v65; // r9d
  int v66; // ecx
  int v67; // r8d
  int v68; // r9d
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  int v72; // ecx
  int v73; // r8d
  int v74; // r9d
  int v75; // r8d
  int v76; // r9d
  signed int v77; // eax
  int v78; // ecx
  int v79; // r8d
  int v80; // r9d
  signed int v81; // eax
  int v82; // ecx
  int v83; // r8d
  int v84; // r9d
  __int64 v85; // rax
  int *v86; // rbx
  int v87; // eax
  _DWORD *v88; // r14
  unsigned int *v89; // rsi
  int v90; // r8d
  int v91; // r9d
  int v92; // ecx
  int v93; // ecx
  int v94; // r8d
  int v95; // r9d
  int v96; // eax
  char v97; // bl
  unsigned int v98; // eax
  __int64 v99; // rcx
  int v100; // ecx
  int v101; // r8d
  int v102; // r9d
  const char *v103; // rax
  __int64 *v104; // rdx
  const char *v105; // rcx
  const char *v106; // rcx
  int v107; // eax
  __int64 v108; // r8
  __int64 v109; // r9
  char v110; // bl
  unsigned int v111; // eax
  int v112; // ecx
  int v113; // r8d
  int v114; // r9d
  signed int v116; // eax
  int v117; // ecx
  int v118; // r8d
  int v119; // r9d
  int v120; // [rsp+28h] [rbp-E0h]
  int v121; // [rsp+28h] [rbp-E0h]
  int v122; // [rsp+28h] [rbp-E0h]
  int v123; // [rsp+28h] [rbp-E0h]
  int v124; // [rsp+28h] [rbp-E0h]
  const char **v125; // [rsp+38h] [rbp-D0h]
  const char **v126; // [rsp+48h] [rbp-C0h]
  const char **v127; // [rsp+50h] [rbp-B8h]
  const char *v128; // [rsp+58h] [rbp-B0h] BYREF
  const char *v129; // [rsp+60h] [rbp-A8h] BYREF
  const char *v130; // [rsp+68h] [rbp-A0h] BYREF
  const char *v131; // [rsp+70h] [rbp-98h] BYREF
  const char *v132; // [rsp+78h] [rbp-90h] BYREF
  const char *v133; // [rsp+80h] [rbp-88h] BYREF
  int v134; // [rsp+88h] [rbp-80h] BYREF
  int v135; // [rsp+8Ch] [rbp-7Ch] BYREF
  struct IRdpCacheMan *v136; // [rsp+90h] [rbp-78h] BYREF
  int v137[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v138; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v139; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v141; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v142; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v143; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG v144; // [rsp+110h] [rbp+8h] BYREF
  const char *v147; // [rsp+180h] [rbp+78h] BYREF

  v147 = (const char *)a4;
  v139 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v141, 0, sizeof(v141));
  v138 = 0;
  memset(&v142, 0, sizeof(v142));
  *(_QWORD *)v137 = 0;
  memset(&v143, 0, sizeof(v143));
  v136 = 0;
  memset(&v144, 0, sizeof(v144));
  v135 = 0;
  v134 = 0;
  VariantInit(&pvarg);
  VariantInit(&v141);
  VariantInit(&v142);
  VariantInit(&v143);
  VariantInit(&v144);
  if ( !a4 )
  {
    v11 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceNullGfxSource",
      (char *)0x301,
      0x80004003,
      v120);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pGfxSource");
    }
    goto LABEL_164;
  }
  v13 = a9;
  if ( !a9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && ((unsigned __int8)((_BYTE)a9 + 8) & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
        v14,
        (__int64)"pExtensionFactory");
    }
    v11 = -2147467261;
    goto LABEL_164;
  }
  v15 = a7;
  v16 = -1;
  Lo = -1;
  if ( a7 != *((struct IRdpGfxPipeLineStateEvents **)this + 1624) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 12992);
    *((_QWORD *)this + 1624) = v15;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 12992);
  }
  TCntPtr<IRdpPipeEvents>::operator=((char *)this + 13008, a8);
  v18 = a5;
  v19 = (struct IRdpPipeProtocol **)((char *)this + 12960);
  if ( a5 != *((struct IRdpPipeProtocol **)this + 1620) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 12960);
    *v19 = v18;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 12960);
  }
  v20 = a6;
  if ( a6 != *((struct IRDPCollection **)this + 6110) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 48880);
    *((_QWORD *)this + 6110) = v20;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 48880);
  }
  if ( v13 != *((struct IRdpPipeExtensionFactory **)this + 1637) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13096);
    *((_QWORD *)this + 1637) = v13;
    (*(void (__fastcall **)(struct IRdpPipeExtensionFactory *))(*(_QWORD *)v13 + 8LL))(v13);
  }
  pvarg.vt = 23;
  v141.vt = 23;
  if ( v20 )
  {
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v20 + 24LL))(
           v20,
           L"SessionID",
           &v141) >= 0
      && v141.vt == 23 )
    {
      Lo = v141.cyVal.Lo;
    }
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v20 + 24LL))(
           v20,
           L"ConnectionID",
           &pvarg) >= 0
      && pvarg.vt == 23 )
    {
      v16 = pvarg.cyVal.Lo;
    }
    if ( *((_DWORD *)this + 13432) )
    {
      v144.llVal = *((_QWORD *)this + 6718);
      v11 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v20 + 56LL))(
              v20,
              L"RdpQrCodeHelperDllHandle",
              &v144);
      if ( v11 < 0 )
      {
        v23 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_164;
        LODWORD(v147) = 808;
        v131 = "Failed to set RDPAPI_PROP_QRCODEHELPER_HANDLE property";
        v24 = byte_18027BE35;
        v129 = "InitializeInstance";
        v132 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v128 = "Error HResult failed";
        v127 = &v131;
        v126 = &v129;
        v125 = &v132;
        v25 = &v128;
LABEL_31:
        LODWORD(v130) = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v23,
          (_DWORD)v24,
          v21,
          v22,
          (__int64)v25,
          (__int64)&v130,
          (__int64)v125,
          (__int64)&v147,
          (__int64)v126,
          (__int64)v127);
        goto LABEL_164;
      }
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1623) + 24LL))(
         *((_QWORD *)this + 1623),
         L"ReverseConnectGatewayUri",
         &v142) < 0 )
  {
    if ( (unsigned int)CallbackContext <= 3 )
      goto LABEL_42;
    v29 = "Failed to get CONN_PROPERTY_WVD_GATEWAY_URI property value. Not critical.";
    v30 = byte_18027BE13;
    goto LABEL_41;
  }
  if ( v142.vt == 8 )
  {
    v31 = (QOEAccumulator *)*((_QWORD *)this + 6572);
    if ( v31 )
    {
      if ( QOEAccumulator::SetReverseConnGatewayUri(v31, v142.bstrVal) < 0 && (unsigned int)CallbackContext > 3 )
      {
        v29 = "Failed to set reverse connect gateway Uri in QOEAccumulator. Not critical";
        v30 = byte_18027BDF1;
LABEL_41:
        v128 = v29;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v26,
          (_DWORD)v30,
          v27,
          v28,
          (__int64)&v128);
      }
    }
  }
LABEL_42:
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1623) + 24LL))(
         *((_QWORD *)this + 1623),
         L"ReverseConnectHostPoolArmPath",
         &v143) >= 0 )
  {
    if ( v143.vt == 8 )
    {
      v37 = (QOEAccumulator *)*((_QWORD *)this + 6572);
      if ( v37 )
      {
        if ( QOEAccumulator::SetReverseConnectHostPoolArmPath(v37, v143.bstrVal) >= 0 )
        {
          if ( (unsigned int)CallbackContext > 4
            && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v33, v34) )
          {
            v132 = (const char *)0x1000000;
            v128 = (char *)this + 13520;
            v131 = "PipeMgr";
            v129 = "Stack";
            v130 = "Checkpoint";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
              v38,
              (unsigned int)&unk_18027BD38,
              v39,
              v40,
              (__int64)&v130,
              (__int64)&v132,
              (__int64)&v129,
              (__int64)&v131,
              (__int64)&v128);
          }
        }
        else if ( (unsigned int)CallbackContext > 3 )
        {
          v35 = "Failed to set reverse connect hostpool arm path in QOEAccumulator";
          v36 = &byte_18027BD9F;
          goto LABEL_50;
        }
      }
    }
  }
  else if ( (unsigned int)CallbackContext > 3 )
  {
    v35 = "Failed to get CONN_PROPERTY_WVD_HOSTPOOL_ARMPATH property value";
    v36 = (char *)&unk_18027BDC8;
LABEL_50:
    v128 = v35;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v32,
      (_DWORD)v36,
      v33,
      v34,
      (__int64)&v128);
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 1623) + 32LL))(
         *((_QWORD *)this + 1623),
         L"WVD::DisableScreenCaptureProtectionDisconnect",
         (char *)this + 53732) >= 0
    && (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v130) = *((_DWORD *)this + 13433);
    v128 = "WVD Config - DisableScreenCaptureProtectionDisconnect set by WVD config";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v41,
      (unsigned int)&dword_18027BCEC,
      v42,
      v43,
      (__int64)&v128,
      (__int64)&v130);
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 1623) + 32LL))(
         *((_QWORD *)this + 1623),
         L"WVD::EnableDisconnectOnFrameAckTimeout",
         (char *)this + 53736) >= 0
    && (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v130) = *((_DWORD *)this + 13434);
    v128 = "WVD Config - EnableDisconnectOnFrameAckTimeout set by WVD config";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v44,
      (unsigned int)&byte_18027BCA7,
      v45,
      v46,
      (__int64)&v128,
      (__int64)&v130);
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 1623) + 40LL))(
         *((_QWORD *)this + 1623),
         L"WVD::AckTimeoutThreshold",
         (char *)this + 53116) >= 0
    && (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v130) = *((_DWORD *)this + 13279);
    v128 = "WVD Config - frameAckTimeoutThreshold set by WVD config";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v47,
      (unsigned int)byte_18027BC6B,
      v48,
      v49,
      (__int64)&v128,
      (__int64)&v130);
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 1623) + 40LL))(
         *((_QWORD *)this + 1623),
         L"WVD::QoEFrameDataLoggingThreshold",
         &v134) >= 0 )
  {
    v52 = *((_QWORD *)this + 6572);
    if ( v52 )
      *(_DWORD *)(v52 + 438636) = v134;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v130) = v134;
      v128 = "WVD Config - QoEFrameDataLoggingThreshold set by WVD config";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v52,
        (unsigned int)byte_18027BC2B,
        v50,
        v51,
        (__int64)&v128,
        (__int64)&v130);
    }
  }
  if ( a8 )
    (*(void (__fastcall **)(struct IRdpPipeEvents *, _QWORD, _QWORD))(*(_QWORD *)a8 + 24LL))(a8, Lo, v16);
  LongCounter = RDPAPI_GetLongCounter(L"RDV::RDP::MCULatency", Lo, v16, 0xFFFFFFFFLL, 1, 1, 0, (char *)this + 52872);
  v11 = LongCounter;
  if ( LongCounter < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceInitPerfCtrFail",
      (char *)0x386,
      LongCounter,
      v121);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_164;
    LODWORD(v147) = 903;
    v128 = "RDPAPI_GetAutoLongCounter(MCULatency) failed";
    v24 = byte_18027BBDD;
    v131 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    v127 = &v128;
    v126 = &v131;
    v125 = &v129;
    v25 = &v132;
    goto LABEL_31;
  }
  v54 = RDPAPI_GetLongCounter(
          L"RDV::RDP::GraphicsPipeline::PipelineInputFrameRate",
          Lo,
          v16,
          0xFFFFFFFFLL,
          -2147483645,
          1000,
          1000,
          (char *)this + 52904);
  v11 = v54;
  if ( v54 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceInitPerfCtrFail",
      (char *)0x396,
      v54,
      v122);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_164;
    LODWORD(v147) = 919;
    v128 = "RDPAPI_GetLongCounter(PipelineInputFrameRate) failed";
    v24 = &byte_18027BB8F;
    v131 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    v127 = &v128;
    v126 = &v131;
    v125 = &v129;
    v25 = &v132;
    goto LABEL_31;
  }
  v55 = RDPAPI_GetLongCounter(
          L"RDV::RDP::Encoder::TilesEncoded",
          Lo,
          v16,
          0xFFFFFFFFLL,
          -2147483645,
          1000,
          1000,
          (char *)this + 52912);
  v11 = v55;
  if ( v55 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceInitPerfCtrFail",
      (char *)0x3A5,
      v55,
      v123);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_164;
    LODWORD(v147) = 934;
    v128 = "RDPAPI_GetLongCounter(TilesEncoded) failed";
    v24 = byte_18027BB41;
    v131 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    v127 = &v128;
    v126 = &v131;
    v125 = &v129;
    v25 = &v132;
    goto LABEL_31;
  }
  if ( !*v19 )
  {
    Instance = RdpPipeProtocol_CreateInstance(*((struct IUnknown **)this + 1623), v56, (void **)this + 1620);
    v11 = Instance;
    if ( Instance < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateLegacyProtocolFail",
        (char *)0x3AE,
        Instance,
        v123);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_164;
      LODWORD(v147) = 943;
      v128 = "Failed to create legacy protocol";
      v24 = byte_18027BAF3;
      v131 = "InitializeInstance";
      v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v132 = "Error HResult failed";
      v127 = &v128;
      v126 = &v131;
      v125 = &v129;
      v25 = &v132;
      goto LABEL_31;
    }
  }
  v58 = *((_QWORD *)this + 1621);
  if ( v58 )
  {
    v123 = (int)v13;
    v59 = (*(__int64 (__fastcall **)(__int64, const char *, unsigned __int64, struct IRDPCollection *))(*(_QWORD *)v58 + 56LL))(
            v58,
            v147,
            ((unsigned __int64)this - 24) & -(__int64)(this != (CPipeManager *)32),
            v20);
    v11 = v59;
    if ( v59 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceInitUpdateTrackerFail",
        (char *)0x3B5,
        v59,
        (int)v13);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_164;
      LODWORD(v147) = 950;
      v128 = "IRdpUpdateTracker::InitializeInstance failed";
      v24 = byte_18027BAA5;
      v131 = "InitializeInstance";
      v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v132 = "Error HResult failed";
      v127 = &v128;
      v126 = &v131;
      v125 = &v129;
      v25 = &v132;
      goto LABEL_31;
    }
  }
  v60 = CRdpFbrProtocol_CreateInstance(a3);
  v11 = v60;
  if ( v60 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceCreateFbrProtocolFail",
      (char *)0x3C1,
      v60,
      v123);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_164;
    LODWORD(v147) = 962;
    v128 = "Failed to create FBR protocol";
    v24 = &byte_18027BA57;
    v131 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    v127 = &v128;
    v126 = &v131;
    v125 = &v129;
    v25 = &v132;
    goto LABEL_31;
  }
  v11 = CPipeManager::SetupCoreObjects((CPipeManager *)((char *)this - 32));
  if ( v11 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_164;
    LODWORD(v147) = 968;
    v128 = "SetupCoreObjects failed";
    v24 = byte_18027BA09;
    v131 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    v127 = &v128;
    v126 = &v131;
    v125 = &v129;
    v25 = &v132;
    goto LABEL_31;
  }
  if ( a3 )
  {
    v61.lpVtbl = a3->lpVtbl;
    LODWORD(v147) = 0;
    v62 = ((__int64 (__fastcall *)(struct IUnknown *, const char *, _QWORD, __int64 *))v61.lpVtbl[1].QueryInterface)(
            a3,
            "Microsoft::Windows::RDS::Graphics",
            0,
            &v139);
    v11 = v62;
    if ( v62 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_InitInstanceCreateChannelFail",
        (char *)0x3D3,
        v62,
        v123);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v130) = 980;
        v128 = "CreateChannel(RDPGFX_CHANNEL_NAME) failed!";
        LODWORD(v132) = v11;
        v131 = "InitializeInstance";
        v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v133 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v63,
          (unsigned int)byte_18027B9BB,
          v64,
          v65,
          (__int64)&v133,
          (__int64)&v132,
          (__int64)&v129,
          (__int64)&v130,
          (__int64)&v131,
          (__int64)&v128);
      }
      goto LABEL_164;
    }
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, const char **))(**((_QWORD **)this + 1623) + 32LL))(
           *((_QWORD *)this + 1623),
           L"GfxPipelineTst::DisableMouseCursorDVC",
           &v147) >= 0 )
    {
      if ( !(_DWORD)v147 )
        goto LABEL_102;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v133 = "Test Config - MouseCursor DVC disabled by test config";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v66,
          (unsigned int)byte_18027B999,
          v67,
          v68,
          (__int64)&v133);
      }
    }
    if ( (_DWORD)v147 )
    {
LABEL_105:
      if ( ((int (__fastcall *)(struct IUnknown *, const char *, _QWORD, __int64 *))a3->lpVtbl[1].QueryInterface)(
             a3,
             "ECHO",
             0,
             &v138) < 0
        && (unsigned int)CallbackContext > 3 )
      {
        v133 = "CreateChannel(ECHO) failed.  Non-Fatal.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v72,
          (unsigned int)byte_18027B955,
          v73,
          v74,
          (__int64)&v133);
      }
      goto LABEL_108;
    }
LABEL_102:
    if ( ((int (__fastcall *)(struct IUnknown *, const char *, _QWORD, int *))a3->lpVtbl[1].QueryInterface)(
           a3,
           "Microsoft::Windows::RDS::MouseCursor",
           0,
           v137) < 0
      && (unsigned int)CallbackContext > 3 )
    {
      v133 = "CreateChannel(Microsoft::Windows::RDS::MouseCursor) failed.  Non-Fatal.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v69,
        (unsigned int)&byte_18027B977,
        v70,
        v71,
        (__int64)&v133);
    }
    goto LABEL_105;
  }
LABEL_108:
  CPipeManager::GetCacheMan((CPipeManager *)((char *)this - 24), &v136);
  if ( v136 )
  {
    (*(void (__fastcall **)(struct IRdpCacheMan *, _QWORD))(*(_QWORD *)v136 + 72LL))(v136, *((_QWORD *)this + 6614));
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v147 = "Capability: Cache: Cache manager is disabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      0,
      (unsigned int)byte_18027B933,
      v75,
      v76,
      (__int64)&v147);
  }
  v124 = v137[0];
  v77 = (*(__int64 (__fastcall **)(_QWORD, struct IRDPCoreVirtualChannel *, __int64, __int64))(**((_QWORD **)this + 1620)
                                                                                             + 24LL))(
          *((_QWORD *)this + 1620),
          a2,
          v139,
          v138);
  v11 = v77;
  if ( v77 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceInitProtocolFail",
      (char *)0x402,
      v77,
      v124);
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v147) = 1027;
      v133 = "IRdpPipeprotocol::InitializeInstance failed";
      LODWORD(v132) = v11;
      v128 = "InitializeInstance";
      v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v129 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v78,
        (unsigned int)byte_18027B8E5,
        v79,
        v80,
        (__int64)&v129,
        (__int64)&v132,
        (__int64)&v131,
        (__int64)&v147,
        (__int64)&v128,
        (__int64)&v133);
    }
    goto LABEL_164;
  }
  v81 = CPipeManager::CreateAndBindVideoChannel(
          (CPipeManager *)((char *)this - 32),
          (struct IRDPCoreChannelManager *)a3);
  v11 = v81;
  if ( v81 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_InitInstanceCreateBindVCFail",
      (char *)0x409,
      v81,
      v124);
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v147) = 1034;
      v133 = "CreateAndBindVideoChannel failed";
      LODWORD(v132) = v11;
      v128 = "InitializeInstance";
      v131 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v129 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v82,
        (unsigned int)&byte_18027B897,
        v83,
        v84,
        (__int64)&v129,
        (__int64)&v132,
        (__int64)&v131,
        (__int64)&v147,
        (__int64)&v128,
        (__int64)&v133);
    }
    goto LABEL_164;
  }
  if ( v20 )
  {
    v85 = *(_QWORD *)v20;
    LODWORD(v147) = 0;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, const char **))(v85 + 40))(
           v20,
           L"GfxPipeline::DisplayRefreshRate",
           &v147) >= 0
      && (_DWORD)v147 )
    {
      v86 = (int *)((char *)this + 52984);
      *((_DWORD *)this + 13246) = 0x3E8 / (unsigned int)v147;
    }
    else
    {
      v86 = (int *)((char *)this + 52984);
      if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v20 + 40LL))(
             v20,
             L"GfxPipelineTst::TargetFrameInterval",
             (char *)this + 52984) >= 0
        && !*v86 )
      {
        *v86 = 31;
      }
    }
    if ( (unsigned int)*v86 < 8 )
    {
      v87 = 8;
    }
    else
    {
      v87 = 200;
      if ( (unsigned int)*v86 <= 0xC8 )
        v87 = *v86;
    }
    *v86 = v87;
    v88 = (_DWORD *)((char *)this + 53076);
    (*(void (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v20 + 40LL))(
      v20,
      L"GfxPipelineTst::MaxFramesInFlight",
      (char *)this + 53076);
    v89 = (unsigned int *)((char *)this + 52988);
    (*(void (__fastcall **)(struct IRDPCollection *, const unsigned __int16 *, char *))(*(_QWORD *)v20 + 40LL))(
      v20,
      L"ThrottlingDisabled",
      (char *)this + 52988);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v92 = *v86;
      LODWORD(v132) = *v89;
      LODWORD(v130) = *v88;
      LODWORD(v131) = v92;
      LODWORD(v129) = 2 * v92;
      v133 = "Gfx Pipeline Capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v92,
        (unsigned int)&unk_18027B818,
        v90,
        v91,
        (__int64)&v133,
        (__int64)&v131,
        (__int64)&v129,
        (__int64)&v130,
        (__int64)&v132);
    }
  }
  else
  {
    v89 = (unsigned int *)((char *)this + 52988);
    v88 = (_DWORD *)((char *)this + 53076);
  }
  GetGfxPipeSettingUINT(L"ThrottlingDisabled", *v89, (unsigned int *)this + 13247);
  *((_DWORD *)this + 13273) = *((_DWORD *)this + 13246);
  GetGfxPipeSettingBOOL(L"ProgressiveRefinementEnabled", 0, (int *)this + 13277);
  if ( !*v88 )
    *v89 |= 2u;
  if ( (int)CPipeManager::InitializePerfMonSession((CPipeManager *)((char *)this - 32)) < 0
    && (unsigned int)CallbackContext > 3 )
  {
    v147 = "Failed to initialize perfmon session. Not critical";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v93,
      (unsigned int)&word_18027B7F6,
      v94,
      v95,
      (__int64)&v147);
  }
  v96 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 1623) + 32LL))(
          *((_QWORD *)this + 1623),
          L"ReplaceCustomRdpScheduler",
          &v135);
  v97 = v96;
  if ( v96 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v98 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v98,
      (__int64)"Failed to get property whether to replace custom RDP scheduler from platform context",
      v97);
  }
  if ( v135 )
  {
    v99 = *((_QWORD *)this + 1623);
    v129 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v99 + 184LL))(v99, 0, &v129);
    if ( v11 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_147;
      v103 = "Failed to get thread pool handle.";
      LODWORD(v147) = 1109;
      v104 = qword_18027B7A8;
      goto LABEL_146;
    }
    v11 = RdpTaskTrigger_CreateInstance(v129, (char *)this + 80, (char *)this + 12920);
    if ( v11 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
      {
LABEL_147:
        v105 = v129;
        if ( v129 )
        {
          v129 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v105 + 16LL))(v105);
        }
        goto LABEL_164;
      }
      v103 = "Failed to create task trigger instance";
      LODWORD(v147) = 1112;
      v104 = (__int64 *)&byte_18027B757;
LABEL_146:
      v133 = v103;
      v128 = "InitializeInstance";
      v132 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v130 = "Error HResult failed";
      LODWORD(v131) = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v100,
        (_DWORD)v104,
        v101,
        v102,
        (__int64)&v130,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v147,
        (__int64)&v128,
        (__int64)&v133);
      goto LABEL_147;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v147 = "Task trigger instance is initialized.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v100,
        (unsigned int)byte_18027B735,
        v101,
        v102,
        (__int64)&v147);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1615) + 24LL))(*((_QWORD *)this + 1615), 0);
    v106 = v129;
    if ( v129 )
    {
      v129 = 0;
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v106 + 16LL))(v106);
    }
    goto LABEL_156;
  }
  v116 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 1618) + 40LL))(
           *((_QWORD *)this + 1618),
           (char *)this - 32,
           (char *)this + 12976);
  v11 = v116;
  if ( v116 >= 0 )
  {
LABEL_156:
    v107 = CPipeManager::LogGraphicsSettings((CPipeManager *)((char *)this - 32));
    v110 = v107;
    if ( v107 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v111 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
        v111,
        (__int64)"LogGraphicsSettings failed. Not critical",
        v110);
    }
    *((_DWORD *)this + 13) |= 2u;
    v11 = 0;
    *((_DWORD *)this + 13237) = 1;
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v108, v109) )
    {
      v131 = (const char *)0x1000000;
      v147 = (char *)this + 13520;
      v133 = "PipeMgr";
      v128 = "Stack";
      v129 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v112,
        (unsigned int)&byte_18027B67F,
        v113,
        v114,
        (__int64)&v129,
        (__int64)&v131,
        (__int64)&v128,
        (__int64)&v133,
        (__int64)&v147);
    }
    goto LABEL_164;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
    "PipeManagerError_InitInstanceSchedRegisterWorkerFail",
    (char *)0x461,
    v116,
    v124);
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v147) = 1122;
    v133 = "Gfx Pluging failed to Register Worker with Scheduler";
    LODWORD(v131) = v11;
    v128 = "InitializeInstance";
    v129 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v132 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v117,
      (unsigned int)&byte_18027B6E7,
      v118,
      v119,
      (__int64)&v132,
      (__int64)&v131,
      (__int64)&v129,
      (__int64)&v147,
      (__int64)&v128,
      (__int64)&v133);
  }
LABEL_164:
  VariantClear(&pvarg);
  VariantClear(&v142);
  VariantClear(&v143);
  VariantClear(&v144);
  if ( v11 < 0 )
    CPipeManager::TerminateInstance(this);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v136);
  TCntPtr<IRdpVCMgr>::SafeRelease(v137);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v138);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v139);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180094a60  mov     rax, rsp
0x180094a63  mov     [rax+8], rbx
0x180094a67  mov     [rax+20h], r9
0x180094a6b  mov     [rax+18h], r8
0x180094a6f  mov     [rax+10h], rdx
0x180094a73  push    rbp
0x180094a74  push    rsi
0x180094a75  push    rdi
0x180094a76  push    r12
0x180094a78  push    r13
0x180094a7a  push    r14
0x180094a7c  push    r15
0x180094a7e  lea     rbp, [rax-58h]
0x180094a82  sub     rsp, 120h
0x180094a89  xor     eax, eax
0x180094a8b  mov     [rbp+50h+var_B0], 0
0x180094a93  xorps   xmm0, xmm0
0x180094a96  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x180094a9a  xorps   xmm1, xmm1
0x180094a9d  mov     qword ptr [rbp+50h+var_90+10h], rax
0x180094aa1  mov     rdi, rcx
0x180094aa4  mov     qword ptr [rbp+50h+var_78+10h], rax
0x180094aa8  lea     rcx, [rbp+50h+pvarg]; pvarg
0x180094aac  mov     qword ptr [rbp+50h+var_60+10h], rax
0x180094ab0  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x180094ab4  mov     qword ptr [rbp+50h+var_48+10h], rax
0x180094ab8  mov     rbx, r9
0x180094abb  movups  xmmword ptr [rbp+50h+var_90], xmm1
0x180094abf  mov     [rbp+50h+var_B8], 0
0x180094ac7  movups  xmmword ptr [rbp+50h+var_78], xmm0
0x180094acb  mov     qword ptr [rbp+50h+var_C0], 0
0x180094ad3  movups  xmmword ptr [rbp+50h+var_60], xmm1
0x180094ad7  mov     [rbp+50h+var_C8], 0
0x180094adf  movups  xmmword ptr [rbp+50h+var_48], xmm0
0x180094ae3  mov     [rbp+50h+var_CC], 0
0x180094aea  mov     [rbp+50h+var_D0], 0
0x180094af1  call    cs:__imp_VariantInit
0x180094af7  lea     rcx, [rbp+50h+var_90]; pvarg
0x180094afb  call    cs:__imp_VariantInit
0x180094b01  lea     rcx, [rbp+50h+var_78]; pvarg
0x180094b05  call    cs:__imp_VariantInit
0x180094b0b  lea     rcx, [rbp+50h+var_60]; pvarg
0x180094b0f  call    cs:__imp_VariantInit
0x180094b15  lea     rcx, [rbp+50h+var_48]; pvarg
0x180094b19  call    cs:__imp_VariantInit
0x180094b1f  test    rbx, rbx
0x180094b22  jnz     loc_180094BAF
0x180094b28  mov     ebx, 80004003h
0x180094b2d  lea     rdx, aPipemanagererr_51; "PipeManagerError_InitInstanceNullGfxSou"...
0x180094b34  mov     r9d, ebx; unsigned int
0x180094b37  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x180094b3e  mov     r8d, 301h; char *
0x180094b44  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180094b49  mov     rax, cs:WPP_GLOBAL_Control
0x180094b50  lea     rsi, WPP_GLOBAL_Control
0x180094b57  cmp     rax, rsi
0x180094b5a  jz      loc_180095FFA
0x180094b60  mov     r12d, 8
0x180094b66  test    [rax+1Ch], r12b
0x180094b6a  jz      loc_180095FFA
0x180094b70  cmp     byte ptr [rax+19h], 2
0x180094b74  jb      loc_180095FFA
0x180094b7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180094b7f  lea     rcx, aPgfxsource; "pGfxSource"
0x180094b86  mov     r9d, eax
0x180094b89  mov     qword ptr [rsp+150h+var_130], rcx
0x180094b8e  lea     edx, [r12+12h]
0x180094b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180094b9a  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180094ba1  mov     rcx, [rcx+10h]
0x180094ba5  call    WPP_SF_Ds
0x180094baa  jmp     loc_180095FFA
0x180094baf  mov     r13, [rbp+50h+arg_40]
0x180094bb6  test    r13, r13
0x180094bb9  jnz     short loc_180094C17
0x180094bbb  mov     rax, cs:WPP_GLOBAL_Control
0x180094bc2  lea     rsi, WPP_GLOBAL_Control
0x180094bc9  cmp     rax, rsi
0x180094bcc  jz      short loc_180094C0D
0x180094bce  lea     r12d, [r13+8]
0x180094bd2  test    [rax+1Ch], r12b
0x180094bd6  jz      short loc_180094C0D
0x180094bd8  cmp     byte ptr [rax+19h], 2
0x180094bdc  jb      short loc_180094C0D
0x180094bde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180094be3  lea     rcx, aPextensionfact; "pExtensionFactory"
0x180094bea  mov     r9d, eax
0x180094bed  mov     qword ptr [rsp+150h+var_130], rcx
0x180094bf2  lea     edx, [r13+1Bh]
0x180094bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180094bfd  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180094c04  mov     rcx, [rcx+10h]
0x180094c08  call    WPP_SF_Ds
0x180094c0d  mov     ebx, 80004003h
0x180094c12  jmp     loc_180095FFA
0x180094c17  mov     rsi, [rbp+50h+arg_30]
0x180094c1e  lea     rbx, [rdi+32C0h]
0x180094c25  or      eax, 0FFFFFFFFh
0x180094c28  mov     r14d, eax
0x180094c2b  mov     r12d, eax
0x180094c2e  cmp     rsi, [rbx]
0x180094c31  jz      short loc_180094C46
0x180094c33  mov     rcx, rbx
0x180094c36  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180094c3b  mov     rcx, rbx
0x180094c3e  mov     [rbx], rsi
0x180094c41  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180094c46  mov     rdx, [rbp+50h+arg_38]
0x180094c4d  lea     rcx, [rdi+32D0h]
0x180094c54  call    ??4?$TCntPtr@VIRdpPipeEvents@@@@QEAAPEAVIRdpPipeEvents@@PEAV1@@Z; TCntPtr<IRdpPipeEvents>::operator=(IRdpPipeEvents *)
0x180094c59  mov     rbx, [rbp+50h+arg_20]
0x180094c60  lea     rsi, [rdi+32A0h]
0x180094c67  cmp     rbx, [rsi]
0x180094c6a  jz      short loc_180094C7F
0x180094c6c  mov     rcx, rsi
0x180094c6f  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180094c74  mov     rcx, rsi
0x180094c77  mov     [rsi], rbx
0x180094c7a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180094c7f  mov     r15, [rbp+50h+arg_28]
0x180094c86  lea     rbx, [rdi+0BEF0h]
0x180094c8d  cmp     r15, [rbx]
0x180094c90  jz      short loc_180094CA5
0x180094c92  mov     rcx, rbx
0x180094c95  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180094c9a  mov     rcx, rbx
0x180094c9d  mov     [rbx], r15
0x180094ca0  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180094ca5  lea     rbx, [rdi+3328h]
0x180094cac  cmp     r13, [rbx]
0x180094caf  jz      short loc_180094CCC
0x180094cb1  mov     rcx, rbx
0x180094cb4  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180094cb9  mov     [rbx], r13
0x180094cbc  mov     rcx, r13
0x180094cbf  mov     rax, [r13+0]
0x180094cc3  mov     rax, [rax+8]
0x180094cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094ccc  mov     ebx, 17h
0x180094cd1  mov     word ptr [rbp+50h+pvarg], bx
0x180094cd5  mov     word ptr [rbp+50h+var_90], bx
0x180094cd9  test    r15, r15
0x180094cdc  jz      loc_180094E02
0x180094ce2  mov     rax, [r15]
0x180094ce5  lea     r8, [rbp+50h+var_90]
0x180094ce9  lea     rdx, aSessionid; "SessionID"
0x180094cf0  mov     rcx, r15
0x180094cf3  mov     rax, [rax+18h]
0x180094cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094cfc  test    eax, eax
0x180094cfe  js      short loc_180094D09
0x180094d00  cmp     word ptr [rbp+50h+var_90], bx
0x180094d04  cmovz   r12d, dword ptr [rbp+50h+var_90+8]
0x180094d09  mov     rax, [r15]
0x180094d0c  lea     r8, [rbp+50h+pvarg]
0x180094d10  lea     rdx, aConnectionid; "ConnectionID"
0x180094d17  mov     rcx, r15
0x180094d1a  mov     rax, [rax+18h]
0x180094d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d23  test    eax, eax
0x180094d25  js      short loc_180094D30
0x180094d27  cmp     word ptr [rbp+50h+pvarg], bx
0x180094d2b  cmovz   r14d, dword ptr [rbp+50h+pvarg+8]
0x180094d30  cmp     dword ptr [rdi+0D1E0h], 0
0x180094d37  jz      loc_180094E02
0x180094d3d  mov     rax, [rdi+0D1F0h]
0x180094d44  lea     r8, [rbp+50h+var_48]
0x180094d48  mov     qword ptr [rbp+50h+var_48+8], rax
0x180094d4c  lea     rdx, aRdpqrcodehelpe; "RdpQrCodeHelperDllHandle"
0x180094d53  mov     rax, [r15]
0x180094d56  mov     rcx, r15
0x180094d59  mov     rax, [rax+38h]
0x180094d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d62  mov     ebx, eax
0x180094d64  test    eax, eax
0x180094d66  jns     loc_180094E02
0x180094d6c  mov     ecx, cs:CallbackContext
0x180094d72  cmp     ecx, 2
0x180094d75  jbe     loc_180095FFA
0x180094d7b  lea     rax, aFailedToSetRdp_0; "Failed to set RDPAPI_PROP_QRCODEHELPER_"...
0x180094d82  mov     dword ptr [rbp+50h+arg_18], 328h
0x180094d89  mov     [rsp+150h+var_E8], rax
0x180094d8e  lea     rdx, byte_18027BE35
0x180094d95  lea     rax, aInitializeinst_0; "InitializeInstance"
0x180094d9c  mov     [rsp+150h+var_F8], rax
0x180094da1  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180094da8  mov     [rsp+150h+var_E0], rax
0x180094dad  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094db4  mov     [rsp+150h+var_100], rax
0x180094db9  lea     rax, [rsp+150h+var_E8]
0x180094dbe  mov     [rsp+150h+var_108], rax
0x180094dc3  lea     rax, [rsp+150h+var_F8]
0x180094dc8  mov     [rsp+150h+var_110], rax
0x180094dcd  lea     rax, [rbp+50h+arg_18]
0x180094dd1  mov     [rsp+150h+var_118], rax
0x180094dd6  lea     rax, [rsp+150h+var_E0]
0x180094ddb  mov     [rsp+150h+var_120], rax
0x180094de0  lea     rax, [rsp+150h+var_F0]
0x180094de5  mov     [rsp+150h+var_128], rax
0x180094dea  lea     rax, [rsp+150h+var_100]
0x180094def  mov     dword ptr [rsp+150h+var_F0], ebx
0x180094df3  mov     qword ptr [rsp+150h+var_130], rax
0x180094df8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180094dfd  jmp     loc_180095FFA
0x180094e02  mov     rcx, [rdi+32B8h]
0x180094e09  lea     r8, [rbp+50h+var_78]
0x180094e0d  lea     rdx, aReverseconnect_0; "ReverseConnectGatewayUri"
0x180094e14  mov     rax, [rcx]
0x180094e17  mov     rax, [rax+18h]
0x180094e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e20  mov     ebx, 8
0x180094e25  test    eax, eax
0x180094e27  jns     short loc_180094E44
0x180094e29  mov     eax, cs:CallbackContext
0x180094e2f  cmp     eax, 3
0x180094e32  jbe     short loc_180094E90
0x180094e34  lea     rax, aFailedToGetCon_0; "Failed to get CONN_PROPERTY_WVD_GATEWAY"...
0x180094e3b  lea     rdx, byte_18027BE13
0x180094e42  jmp     short loc_180094E7C
0x180094e44  cmp     word ptr [rbp+50h+var_78], bx
0x180094e48  jnz     short loc_180094E90
0x180094e4a  mov     rcx, [rdi+0CD60h]; this
0x180094e51  test    rcx, rcx
0x180094e54  jz      short loc_180094E90
0x180094e56  mov     rdx, qword ptr [rbp+50h+var_78+8]; unsigned __int16 *
0x180094e5a  call    ?SetReverseConnGatewayUri@QOEAccumulator@@QEAAJPEAG@Z; QOEAccumulator::SetReverseConnGatewayUri(ushort *)
0x180094e5f  test    eax, eax
0x180094e61  jns     short loc_180094E90
0x180094e63  mov     eax, cs:CallbackContext
0x180094e69  cmp     eax, 3
0x180094e6c  jbe     short loc_180094E90
0x180094e6e  lea     rax, aFailedToSetRev; "Failed to set reverse connect gateway U"...
0x180094e75  lea     rdx, byte_18027BDF1
0x180094e7c  mov     [rsp+150h+var_100], rax
0x180094e81  lea     rax, [rsp+150h+var_100]
0x180094e86  mov     qword ptr [rsp+150h+var_130], rax
0x180094e8b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180094e90  mov     rcx, [rdi+32B8h]
0x180094e97  lea     r8, [rbp+50h+var_60]
0x180094e9b  lea     rdx, aReverseconnect; "ReverseConnectHostPoolArmPath"
0x180094ea2  mov     rax, [rcx]
0x180094ea5  mov     rax, [rax+18h]
0x180094ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094eae  test    eax, eax
0x180094eb0  jns     short loc_180094ED1
0x180094eb2  mov     eax, cs:CallbackContext
0x180094eb8  cmp     eax, 3
0x180094ebb  jbe     loc_180094FC8
0x180094ec1  lea     rax, aFailedToGetCon_4; "Failed to get CONN_PROPERTY_WVD_HOSTPOO"...
0x180094ec8  lea     rdx, unk_18027BDC8
0x180094ecf  jmp     short loc_180094F15
0x180094ed1  cmp     word ptr [rbp+50h+var_60], bx
0x180094ed5  jnz     loc_180094FC8
0x180094edb  mov     rcx, [rdi+0CD60h]; this
0x180094ee2  test    rcx, rcx
0x180094ee5  jz      loc_180094FC8
0x180094eeb  mov     rdx, qword ptr [rbp+50h+var_60+8]; unsigned __int16 *
0x180094eef  call    ?SetReverseConnectHostPoolArmPath@QOEAccumulator@@QEAAJPEAG@Z; QOEAccumulator::SetReverseConnectHostPoolArmPath(ushort *)
0x180094ef4  test    eax, eax
0x180094ef6  mov     eax, cs:CallbackContext
0x180094efc  jns     short loc_180094F2E
0x180094efe  cmp     eax, 3
0x180094f01  jbe     loc_180094FC8
0x180094f07  lea     rax, aFailedToSetRev_0; "Failed to set reverse connect hostpool "...
0x180094f0e  lea     rdx, byte_18027BD9F
0x180094f15  mov     [rsp+150h+var_100], rax
0x180094f1a  lea     rax, [rsp+150h+var_100]
0x180094f1f  mov     qword ptr [rsp+150h+var_130], rax
0x180094f24  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180094f29  jmp     loc_180094FC8
0x180094f2e  cmp     eax, 4
0x180094f31  jbe     loc_180094FC8
0x180094f37  mov     rdx, 470000000000h
0x180094f41  lea     rcx, CallbackContext
0x180094f48  call    _tlgKeywordOn
0x180094f4d  test    al, al
0x180094f4f  jz      short loc_180094FC8
0x180094f51  lea     rax, [rdi+34D0h]
0x180094f58  mov     [rsp+150h+var_E0], 1000000h
0x180094f61  mov     [rsp+150h+var_100], rax
0x180094f66  lea     rdx, unk_18027BD38
0x180094f6d  lea     rax, aPipemgr; "PipeMgr"
0x180094f74  mov     [rsp+150h+var_E8], rax
0x180094f79  lea     rax, aStack; "Stack"
0x180094f80  mov     [rsp+150h+var_F8], rax
0x180094f85  lea     rax, aCheckpoint; "Checkpoint"
0x180094f8c  mov     [rsp+150h+var_F0], rax
0x180094f91  lea     rax, [rsp+150h+var_100]
0x180094f96  mov     [rsp+150h+var_110], rax
0x180094f9b  lea     rax, [rsp+150h+var_E8]
0x180094fa0  mov     [rsp+150h+var_118], rax
0x180094fa5  lea     rax, [rsp+150h+var_F8]
0x180094faa  mov     [rsp+150h+var_120], rax
0x180094faf  lea     rax, [rsp+150h+var_E0]
0x180094fb4  mov     [rsp+150h+var_128], rax
0x180094fb9  lea     rax, [rsp+150h+var_F0]
0x180094fbe  mov     qword ptr [rsp+150h+var_130], rax
0x180094fc3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180094fc8  mov     rcx, [rdi+32B8h]
0x180094fcf  lea     rbx, [rdi+0D1E4h]
  ... truncated ...
```
