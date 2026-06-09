# CServiceModule::_ProcessScmEvent(CServiceModule::ScmEvent *)

- ea: `0x18000fa00`
- end: `0x1800108e0`
- name: `?_ProcessScmEvent@CServiceModule@@AEAAJPEAUScmEvent@1@@Z`
- size: `3808`
- prototype: `__int64 __fastcall(struct _GUID *this, struct CServiceModule::ScmEvent *, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f5d0`

## callees

- `0x180001008`
- `0x180001b18`
- `0x18000ea80`
- `0x18000fa00`
- `0x180010fc0`
- `0x1800110e0`
- `0x180011ae0`
- `0x180012060`
- `0x180012c70`
- `0x1800137e0`
- `0x180013b64`
- `0x180015660`
- `0x18001a174`
- `0x18001bbe0`
- `0x180023bd0`
- `0x180023e6c`
- `0x180023f54`
- `0x180024260`
- `0x180026fa8`
- `0x180028578`
- `0x180028a24`
- `0x180028a60`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b630`
- `0x180031010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001066e`
- `ntdll!EtwEventWriteTransfer` at `0x1800107b7`
- `ntdll!EtwEventWriteTransfer` at `0x18001066e`
- `ntdll!EtwEventWriteTransfer` at `0x1800107b7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001042a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001042a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800104a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800104a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010476`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010476`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800103ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800103ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103bd`

## string_xrefs

- `0x18000fa48`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000fad9`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000fbc0`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000fce6`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000fe16`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000ff59`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18000ffa0`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x180010018`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x1800100a2`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x1800101ce`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x180010256`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x1800102e6`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x1800106d0`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x1800107d4`: `PENSERVICE_CServiceModule::_ProcessScmEvent`
- `0x18001081f`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

## pseudocode

```c
__int64 __fastcall CServiceModule::_ProcessScmEvent(
        struct _GUID *this,
        struct CServiceModule::ScmEvent *a2,
        __int64 a3,
        __int64 a4)
{
  struct _GUID *v6; // r10
  int v7; // esi
  __int64 v8; // rdi
  unsigned int v9; // ebx
  unsigned __int64 v10; // r8
  unsigned int v11; // esi
  int v12; // edi
  int v13; // r15d
  CServiceModule *v14; // rcx
  int v15; // ebx
  const struct _GUID *v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // r9d
  int v19; // edx
  int v20; // edx
  int Data1_low; // edi
  int v22; // ebx
  CServiceModule *v23; // rcx
  int v24; // edx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // ebx
  int v30; // edx
  struct _GUID *v31; // r8
  unsigned int v32; // r9d
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // edx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned __int64 v39; // r8
  __int64 v40; // rcx
  char *v41; // rax
  unsigned __int8 *v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r8
  const char *v46; // r9
  unsigned int v47; // eax
  unsigned int v48; // esi
  __int64 v49; // rdx
  unsigned int v50; // edx
  unsigned int v51; // esi
  CPenProcess *v52; // rcx
  const struct _GUID *v53; // rcx
  unsigned __int64 v54; // r8
  unsigned __int64 v55; // r8
  char Data1; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v58[7]; // [rsp+41h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v60; // [rsp+50h] [rbp-49h] BYREF
  IID rclsid; // [rsp+58h] [rbp-41h] BYREF
  __int16 *v62; // [rsp+70h] [rbp-29h] BYREF
  int v63; // [rsp+78h] [rbp-21h]
  int v64; // [rsp+7Ch] [rbp-1Dh]
  int *v65; // [rsp+80h] [rbp-19h]
  int v66; // [rsp+88h] [rbp-11h]
  int v67; // [rsp+8Ch] [rbp-Dh]
  LPVOID *p_ppv; // [rsp+90h] [rbp-9h]
  __int64 v69; // [rsp+98h] [rbp-1h]
  unsigned int *v70; // [rsp+A0h] [rbp+7h]
  __int64 v71; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      64,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::_ProcessScmEvent");
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *((_DWORD *)a2 + 4);
  v8 = *((int *)a2 + 5);
  v9 = *((_DWORD *)a2 + 6);
  switch ( v7 )
  {
    case 11:
      v10 = *(_QWORD *)v6[3].Data4;
      if ( v10 )
      {
        PrivateTraceEvent(this, 0x613u, v10, 1u);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&v6[1].Data1,
          65,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_ProcessScmEvent");
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                              (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                              (__int64)a2,
                              v10,
                              a4) )
      {
        v11 = 0;
        if ( LOBYTE(this[4].Data1) || (v12 = 0, BYTE1(this[4].Data1)) )
          v12 = 10;
        v13 = *(_DWORD *)&this[4].Data4[4];
        CServiceModule::UpdateHardwarePresenceStatus((CServiceModule *)this);
        if ( LOBYTE(this[4].Data1) || (v15 = 0, BYTE1(this[4].Data1)) )
          v15 = 1;
        CServiceModule::_SetServiceTypeAutoStart(v14);
        v19 = 100;
        if ( v13 == *(_DWORD *)&this[4].Data4[4] )
          v19 = 0;
        v20 = v15 + v12 + v19;
      }
      else
      {
        Data1_low = LOBYTE(this[4].Data1);
        v22 = *(_DWORD *)&this[4].Data4[4];
        CServiceModule::UpdateHardwarePresenceStatus((CServiceModule *)this);
        CServiceModule::_SetServiceTypeAutoStart(v23);
        v16 = (const struct _GUID *)(unsigned int)(5 * Data1_low);
        v11 = 0;
        v24 = 100;
        if ( v22 == *(_DWORD *)&this[4].Data4[4] )
          v24 = 0;
        v20 = LOBYTE(this[4].Data1) + v24 + 10 * Data1_low;
      }
      v25 = (unsigned int)(v20 - 1);
      if ( !(_DWORD)v25 )
        goto LABEL_56;
      v26 = (unsigned int)(v25 - 9);
      if ( !(_DWORD)v26 )
        goto LABEL_41;
      v25 = (unsigned int)(v26 - 91);
      if ( !(_DWORD)v25 )
      {
LABEL_56:
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            66,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::_ProcessScmEvent");
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                                (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                                v25,
                                v17,
                                v18) )
        {
          if ( (unsigned int)dword_1800411A8 > 5
            && (qword_1800411B8 & 0x4000000) != 0
            && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
          {
            v58[0] = BYTE1(this[4].Data1);
            Data1 = this[4].Data1;
            ppv = "Tablet hardware enabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
              qword_1800411C0,
              (int)&dword_180039994,
              v37,
              v38,
              (const unsigned __int16 **)&ppv,
              (__int64)&Data1,
              (__int64)v58);
          }
        }
        else if ( (unsigned int)dword_1800411A8 > 5
               && (qword_1800411B8 & 0x4000000) != 0
               && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          ppv = "Tablet hardware enabled";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            qword_1800411C0,
            (unsigned __int8 *)word_18003A822,
            v37,
            v38,
            (const unsigned __int16 **)&ppv);
        }
        v29 = CServiceModule::_EnableDisablePenProcessTypes(this, 1);
        CServiceModule::StartEnabledPenProcesses(this);
LABEL_69:
        v36 = v29;
        goto LABEL_70;
      }
      v26 = (unsigned int)(v25 - 9);
      if ( (_DWORD)v26 )
      {
        if ( (_DWORD)v26 != 1 )
          goto LABEL_71;
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            68,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::_ProcessScmEvent");
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                                (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                                v26,
                                v17,
                                v18) )
        {
          if ( (unsigned int)dword_1800411A8 > 5
            && (qword_1800411B8 & 0x4000000) != 0
            && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
          {
            Data1 = BYTE1(this[4].Data1);
            v58[0] = this[4].Data1;
            ppv = "Tablet hardware changed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
              qword_1800411C0,
              (int)&dword_18003A73C,
              v27,
              v28,
              (const unsigned __int16 **)&ppv,
              (__int64)v58,
              (__int64)&Data1);
          }
        }
        else if ( (unsigned int)dword_1800411A8 > 5
               && (qword_1800411B8 & 0x4000000) != 0
               && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          ppv = "Tablet hardware changed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            qword_1800411C0,
            (unsigned __int8 *)word_1800398F2,
            v27,
            v28,
            (const unsigned __int16 **)&ppv);
        }
        v29 = CServiceModule::_EnableDisablePenProcessTypes(this, 1);
        CServiceModule::StartEnabledPenProcesses(this);
        CServiceModule::ShutdownDisabledPenProcesses((CServiceModule *)this, v30);
        goto LABEL_69;
      }
LABEL_41:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          67,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_ProcessScmEvent");
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                              (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                              v26,
                              v17,
                              v18) )
      {
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v58[0] = BYTE1(this[4].Data1);
          Data1 = this[4].Data1;
          ppv = "Tablet hardware disabled";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
            qword_1800411C0,
            (int)byte_180039DBB,
            v33,
            v34,
            (const unsigned __int16 **)&ppv,
            (__int64)&Data1,
            (__int64)v58);
        }
      }
      else if ( (unsigned int)dword_1800411A8 > 5
             && (qword_1800411B8 & 0x4000000) != 0
             && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        ppv = "Tablet hardware disabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          qword_1800411C0,
          (unsigned __int8 *)&dword_18003A98C,
          v33,
          v34,
          (const unsigned __int16 **)&ppv);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetImpl'::`2'::impl) )
        v11 = CServiceModule::_EnableDisablePenProcessTypes(this, 1);
      CServiceModule::ShutdownDisabledPenProcesses((CServiceModule *)this, v35);
      v36 = v11;
LABEL_70:
      CServiceModule::_CheckLicense((CServiceModule *)this, v36, v31, v32);
LABEL_71:
      v6 = WPP_GLOBAL_Control;
      v39 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
      if ( v39 )
      {
        PrivateTraceEvent(v16, 0x613u, v39, 2u);
        goto LABEL_177;
      }
LABEL_178:
      if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&v6[1].Data1,
          77,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_ProcessScmEvent");
      return 0;
    case 13:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl'::`2'::impl) )
      {
        v6 = WPP_GLOBAL_Control;
        goto LABEL_170;
      }
      v54 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
      if ( v54 )
        PrivateTraceEvent(v53, 0x61Cu, v54, 1u);
      if ( (unsigned int)dword_1800411A8 > 5 )
      {
        v53 = (const struct _GUID *)qword_1800411C0;
        if ( (qword_1800411B8 & 0x4000000) != 0 && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v60 = v8;
          v70 = &v60;
          v71 = 4;
          p_ppv = (LPVOID *)"Power event.";
          *(_DWORD *)&rclsid.Data2 = 5;
          v62 = (__int16 *)off_1800411B0;
          v69 = 13;
          rclsid.Data1 = 184549376;
          *(_QWORD *)rclsid.Data4 = 0x4000000;
          v63 = *(unsigned __int16 *)off_1800411B0;
          v65 = (int *)&unk_180039FD0;
          v64 = 2;
          v66 = 71;
          v67 = 1;
          LODWORD(ppv) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800411C8, &rclsid, 0, 0, 4, &v62);
        }
      }
      if ( (_DWORD)v8 == 18 )
      {
        v53 = *(const struct _GUID **)this[39].Data4;
        if ( v53 )
          (*(void (__fastcall **)(const struct _GUID *, __int64))(*(_QWORD *)&v53->Data1 + 64LL))(v53, 18);
      }
      v6 = WPP_GLOBAL_Control;
      v55 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
      if ( v55 )
      {
        PrivateTraceEvent(v53, 0x61Cu, v55, 2u);
        goto LABEL_177;
      }
      goto LABEL_178;
    case 14:
      if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
      {
        WPP_SF_s(
          *(_QWORD *)&v6[1].Data1,
          69,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_ProcessScmEvent");
        v6 = WPP_GLOBAL_Control;
      }
      switch ( (int)v8 )
      {
        case 1:
          if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
            WPP_SF_sd(
              *(_QWORD *)&v6[1].Data1,
              70,
              (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
              (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
              v9);
          if ( (unsigned int)dword_1800411A8 <= 5 )
            goto LABEL_122;
          v40 = qword_1800411C0;
          if ( (qword_1800411B8 & 0x4000000) == 0 || (qword_1800411C0 & 0x4000000) != qword_1800411C0 )
            goto LABEL_122;
          v41 = "Session connect.";
          v42 = (unsigned __int8 *)&unk_18003A018;
          goto LABEL_121;
        case 2:
          if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
            WPP_SF_sd(
              *(_QWORD *)&v6[1].Data1,
              71,
              (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
              (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
              v9);
          if ( (unsigned int)dword_1800411A8 > 5
            && (qword_1800411B8 & 0x4000000) != 0
            && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
          {
            ppv = "Session disconnect.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              qword_1800411C0,
              (unsigned __int8 *)byte_180039945,
              a3,
              a4,
              (const unsigned __int16 **)&ppv);
          }
          goto LABEL_177;
        case 3:
          if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
            WPP_SF_sd(
              *(_QWORD *)&v6[1].Data1,
              74,
              (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
              (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
              v9);
          if ( (unsigned int)dword_1800411A8 <= 5 )
            goto LABEL_122;
          v40 = qword_1800411C0;
          if ( (qword_1800411B8 & 0x4000000) == 0 || (qword_1800411C0 & 0x4000000) != qword_1800411C0 )
            goto LABEL_122;
          v41 = "Session remote connect.";
          v42 = (unsigned __int8 *)&unk_180039D68;
LABEL_121:
          ppv = v41;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v40,
            v42,
            a3,
            a4,
            (const unsigned __int16 **)&ppv);
LABEL_122:
          CServiceModule::OnConsoleConnect(this, v9);
          goto LABEL_177;
        case 4:
          if ( v6 == (struct _GUID *)&WPP_GLOBAL_Control )
            return 0;
          if ( (v6[1].Data4[4] & 0x10) == 0 )
            goto LABEL_178;
          WPP_SF_sd(
            *(_QWORD *)&v6[1].Data1,
            75,
            (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
            v9);
          break;
        case 5:
          if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
            WPP_SF_sd(
              *(_QWORD *)&v6[1].Data1,
              72,
              (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
              (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
              v9);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                                  (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                                  (__int64)a2,
                                  a3,
                                  a4) )
          {
            if ( (unsigned int)dword_1800411A8 > 5
              && (qword_1800411B8 & 0x4000000) != 0
              && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
            {
              v58[0] = BYTE1(this[4].Data1);
              Data1 = this[4].Data1;
              ppv = "Session logon.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
                qword_1800411C0,
                (int)byte_180039373,
                v43,
                v44,
                (const unsigned __int16 **)&ppv,
                (__int64)&Data1,
                (__int64)v58);
            }
          }
          else if ( (unsigned int)dword_1800411A8 > 5
                 && (qword_1800411B8 & 0x4000000) != 0
                 && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
          {
            ppv = "Session logon.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              qword_1800411C0,
              (unsigned __int8 *)word_180039BBA,
              v43,
              v44,
              (const unsigned __int16 **)&ppv);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
            CServiceModule::OnSessionLogon(this, v9);
          else
            CServiceModule::OnSessionLogon(this, v9, 1);
          goto LABEL_177;
        case 6:
          if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 0x10) != 0 )
            WPP_SF_sd(
              *(_QWORD *)&v6[1].Data1,
              73,
              (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
              (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent",
              v9);
          if ( (unsigned int)dword_1800411A8 > 5
            && (qword_1800411B8 & 0x4000000) != 0
            && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
          {
            ppv = "Session logoff.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              qword_1800411C0,
              (unsigned __int8 *)byte_18003A367,
              a3,
              a4,
              (const unsigned __int16 **)&ppv);
          }
          CServiceModule::OnSessionLogoff((CServiceModule *)this, v9);
          goto LABEL_177;
        default:
          goto LABEL_178;
      }
      goto LABEL_177;
    case 128:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x683,
          (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
          v46);
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        ppv = "Delay start user Tabtip";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          qword_1800411C0,
          (unsigned __int8 *)byte_1800391D5,
          v45,
          (__int64)v46,
          (const unsigned __int16 **)&ppv);
      }
      CServiceModule::OnSessionLogon(this, v9, 0);
      v47 = *(_DWORD *)&this[34].Data4[4];
      if ( !v47 )
        goto LABEL_177;
      v48 = 0;
      v49 = *(_QWORD *)&this[34].Data1;
      while ( *(_QWORD *)(v49 + 16LL * v48) != *((_QWORD *)a2 + 4) )
      {
        if ( ++v48 >= v47 )
          goto LABEL_177;
      }
      UnregisterWait(*(HANDLE *)(v49 + 16LL * v48 + 8));
      CloseHandle(*(HANDLE *)(*(_QWORD *)&this[34].Data1 + 16LL * v48));
      CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::Remove(&this[24], v48);
      goto LABEL_177;
    case 129:
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        ppv = "Delay start input personalization";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          qword_1800411C0,
          (unsigned __int8 *)&dword_180039C04,
          a3,
          a4,
          (const unsigned __int16 **)&ppv);
      }
      if ( CoInitializeEx(0, 2u) >= 0 )
      {
        rclsid.Data1 = -214362662;
        ppv = 0;
        *(_DWORD *)&rclsid.Data2 = 1104934548;
        *(_DWORD *)rclsid.Data4 = -1381990744;
        *(_DWORD *)&rclsid.Data4[4] = -1023349182;
        if ( CoCreateInstance(&rclsid, 0, 1u, &GUID_839d7762_5121_4009_9234_4f0d19394f04, &ppv) >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0, 0);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          ppv = 0;
        }
        CoUninitialize();
      }
      goto LABEL_177;
    case 130:
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        ppv = "Ensure running event.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          qword_1800411C0,
          (unsigned __int8 *)byte_180039B69,
          a3,
          a4,
          (const unsigned __int16 **)&ppv);
      }
      v50 = *(_DWORD *)&this[23].Data4[4];
      if ( !v50 )
        goto LABEL_177;
      v51 = 0;
      while ( 1 )
      {
        v52 = *(CPenProcess **)(*(_QWORD *)&this[23].Data1 + 8LL * v51);
        if ( v52 )
        {
          if ( *((_DWORD *)v52 + 8) == v9 && *(_QWORD *)v52 == *((_QWORD *)&this[35].Data1 + v8) )
            break;
        }
        if ( ++v51 >= v50 )
          goto LABEL_177;
      }
      CPenProcess::EnsureRunning(v52, 0, 0, 1);
LABEL_177:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_178;
    default:
LABEL_170:
      if ( v6 != (struct _GUID *)&WPP_GLOBAL_Control && (v6[1].Data4[4] & 4) != 0 )
        WPP_SF_sll(*(_QWORD *)&v6[1].Data1, 76, a3, (unsigned int)"PENSERVICE_CServiceModule::_ProcessScmEvent", v7, v8);
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        LODWORD(ppv) = v7;
        p_ppv = &ppv;
        *(_DWORD *)&rclsid.Data2 = 5;
        v62 = (__int16 *)off_1800411B0;
        v69 = 4;
        rclsid.Data1 = 184549376;
        *(_QWORD *)rclsid.Data4 = 0x4000000;
        v63 = *(unsigned __int16 *)off_1800411B0;
        v65 = &dword_1800393FC;
        v64 = 2;
        v66 = 66;
        v67 = 1;
        v60 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_1800411C8, &rclsid, 0, 0, 3, &v62);
      }
      goto LABEL_177;
  }
}

```

## disassembly

```asm
0x18000fa00  push    rbp
0x18000fa02  push    rsi
0x18000fa03  push    rdi
0x18000fa04  push    r12
0x18000fa06  push    r14
0x18000fa08  push    r15
0x18000fa0a  lea     rbp, [rsp-2Fh]
0x18000fa0f  sub     rsp, 0C8h
0x18000fa16  mov     rax, cs:__security_cookie
0x18000fa1d  xor     rax, rsp
0x18000fa20  mov     [rbp+57h+var_40], rax
0x18000fa24  mov     r15, rdx
0x18000fa27  mov     r14, rcx
0x18000fa2a  mov     r10, cs:WPP_GLOBAL_Control
0x18000fa31  lea     r12, WPP_GLOBAL_Control
0x18000fa38  cmp     r10, r12
0x18000fa3b  jz      short loc_18000FA67
0x18000fa3d  test    byte ptr [r10+1Ch], 10h
0x18000fa42  jz      short loc_18000FA67
0x18000fa44  mov     rcx, [r10+10h]
0x18000fa48  lea     r9, aPenserviceCser_18; "PENSERVICE_CServiceModule::_ProcessScmE"...
0x18000fa4f  mov     edx, 40h ; '@'
0x18000fa54  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000fa5b  call    WPP_SF_s
0x18000fa60  mov     r10, cs:WPP_GLOBAL_Control
0x18000fa67  mov     esi, [r15+10h]
0x18000fa6b  movsxd  rdi, dword ptr [r15+14h]
0x18000fa6f  mov     [rsp+0F0h+arg_10], rbx
0x18000fa77  mov     [rsp+0F0h+var_30], r13
0x18000fa7f  lea     eax, [rsi-0Bh]; switch 120 cases
0x18000fa82  cmp     eax, 77h
0x18000fa85  ja      def_18000FAAA; jumptable 000000018000FAAA default case, cases 12,15-127
0x18000fa8b  mov     ebx, [r15+18h]
0x18000fa8f  lea     r13, __ImageBase
0x18000fa96  movzx   eax, ds:(byte_180010850 - 180000000h)[rax+r13]
0x18000fa9f  mov     ecx, ds:(jpt_18000FAAA - 180000000h)[r13+rax*4]
0x18000faa7  add     rcx, r13; struct _GUID *
0x18000faaa  jmp     rcx; switch jump
0x18000faac  mov     r8, [r10+38h]; jumptable 000000018000FAAA case 11
0x18000fab0  test    r8, r8
0x18000fab3  jz      short loc_18000FAC9
0x18000fab5  mov     r9b, 1; unsigned __int8
0x18000fab8  mov     edx, 613h; unsigned int
0x18000fabd  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000fac2  mov     r10, cs:WPP_GLOBAL_Control
0x18000fac9  cmp     r10, r12
0x18000facc  jz      short loc_18000FAF1
0x18000face  test    byte ptr [r10+1Ch], 10h
0x18000fad3  jz      short loc_18000FAF1
0x18000fad5  mov     rcx, [r10+10h]
0x18000fad9  lea     r9, aPenserviceCser_18; "PENSERVICE_CServiceModule::_ProcessScmE"...
0x18000fae0  mov     edx, 41h ; 'A'
0x18000fae5  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000faec  call    WPP_SF_s
0x18000faf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000faf8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000fafd  test    al, al
0x18000faff  jz      short loc_18000FB4C
0x18000fb01  xor     esi, esi
0x18000fb03  cmp     [r14+40h], sil
0x18000fb07  jnz     short loc_18000FB11
0x18000fb09  mov     edi, esi
0x18000fb0b  cmp     [r14+41h], sil
0x18000fb0f  jz      short loc_18000FB16
0x18000fb11  mov     edi, 0Ah
0x18000fb16  mov     r15d, [r14+4Ch]
0x18000fb1a  mov     rcx, r14; this
0x18000fb1d  call    ?UpdateHardwarePresenceStatus@CServiceModule@@QEAAXXZ; CServiceModule::UpdateHardwarePresenceStatus(void)
0x18000fb22  cmp     [r14+40h], sil
0x18000fb26  jnz     short loc_18000FB30
0x18000fb28  mov     ebx, esi
0x18000fb2a  cmp     [r14+41h], sil
0x18000fb2e  jz      short loc_18000FB35
0x18000fb30  mov     ebx, 1
0x18000fb35  call    ?_SetServiceTypeAutoStart@CServiceModule@@AEAAHXZ; CServiceModule::_SetServiceTypeAutoStart(void)
0x18000fb3a  cmp     r15d, [r14+4Ch]
0x18000fb3e  mov     edx, 64h ; 'd'
0x18000fb43  cmovz   edx, esi
0x18000fb46  add     edx, edi
0x18000fb48  add     edx, ebx
0x18000fb4a  jmp     short loc_18000FB7D
0x18000fb4c  movzx   edi, byte ptr [r14+40h]
0x18000fb51  mov     rcx, r14; this
0x18000fb54  mov     ebx, [r14+4Ch]
0x18000fb58  call    ?UpdateHardwarePresenceStatus@CServiceModule@@QEAAXXZ; CServiceModule::UpdateHardwarePresenceStatus(void)
0x18000fb5d  call    ?_SetServiceTypeAutoStart@CServiceModule@@AEAAHXZ; CServiceModule::_SetServiceTypeAutoStart(void)
0x18000fb62  movzx   eax, byte ptr [r14+40h]
0x18000fb67  lea     ecx, [rdi+rdi*4]
0x18000fb6a  xor     esi, esi
0x18000fb6c  mov     edx, 64h ; 'd'
0x18000fb71  cmp     ebx, [r14+4Ch]
0x18000fb75  cmovz   edx, esi
0x18000fb78  lea     edx, [rdx+rcx*2]
0x18000fb7b  add     edx, eax
0x18000fb7d  sub     edx, 1
0x18000fb80  jz      loc_18000FE00
0x18000fb86  sub     edx, 9
0x18000fb89  jz      loc_18000FCD0
0x18000fb8f  sub     edx, 5Bh ; '['
0x18000fb92  jz      loc_18000FE00
0x18000fb98  sub     edx, 9
0x18000fb9b  jz      loc_18000FCD0
0x18000fba1  cmp     edx, 1
0x18000fba4  jnz     loc_18000FF23
0x18000fbaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb1  cmp     rcx, r12
0x18000fbb4  jz      short loc_18000FBD8
0x18000fbb6  test    byte ptr [rcx+1Ch], 10h
0x18000fbba  jz      short loc_18000FBD8
0x18000fbbc  mov     rcx, [rcx+10h]
0x18000fbc0  lea     r9, aPenserviceCser_18; "PENSERVICE_CServiceModule::_ProcessScmE"...
0x18000fbc7  mov     edx, 44h ; 'D'
0x18000fbcc  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000fbd3  call    WPP_SF_s
0x18000fbd8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000fbdf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000fbe4  test    al, al
0x18000fbe6  mov     eax, cs:dword_1800411A8
0x18000fbec  jz      short loc_18000FC65
0x18000fbee  cmp     eax, 5
0x18000fbf1  jbe     loc_18000FCAC
0x18000fbf7  mov     rcx, cs:qword_1800411C0
0x18000fbfe  mov     rax, cs:qword_1800411B8
0x18000fc05  bt      rax, 1Ah
0x18000fc0a  jnb     loc_18000FCAC
0x18000fc10  mov     rax, rcx
0x18000fc13  and     eax, 4000000h
0x18000fc18  cmp     rax, rcx
0x18000fc1b  jnz     loc_18000FCAC
0x18000fc21  movzx   eax, byte ptr [r14+41h]
0x18000fc26  lea     rdx, dword_18003A73C
0x18000fc2d  mov     [rbp+57h+var_B0], al
0x18000fc30  movzx   eax, byte ptr [r14+40h]
0x18000fc35  mov     [rbp+57h+var_AF], al
0x18000fc38  lea     rax, aTabletHardware_0; "Tablet hardware changed"
0x18000fc3f  mov     [rbp+57h+var_A8], rax
0x18000fc43  lea     rax, [rbp+57h+var_B0]
0x18000fc47  mov     [rsp+0F0h+var_C0], rax
0x18000fc4c  lea     rax, [rbp+57h+var_AF]
0x18000fc50  mov     [rsp+0F0h+var_C8], rax
0x18000fc55  lea     rax, [rbp+57h+var_A8]
0x18000fc59  mov     [rsp+0F0h+ppv], rax
0x18000fc5e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18000fc63  jmp     short loc_18000FCAC
0x18000fc65  cmp     eax, 5
0x18000fc68  jbe     short loc_18000FCAC
0x18000fc6a  mov     rcx, cs:qword_1800411C0
0x18000fc71  mov     rax, cs:qword_1800411B8
0x18000fc78  bt      rax, 1Ah
0x18000fc7d  jnb     short loc_18000FCAC
0x18000fc7f  mov     rax, rcx
0x18000fc82  and     eax, 4000000h
0x18000fc87  cmp     rax, rcx
0x18000fc8a  jnz     short loc_18000FCAC
0x18000fc8c  lea     rax, aTabletHardware_0; "Tablet hardware changed"
0x18000fc93  mov     [rbp+57h+var_A8], rax
0x18000fc97  lea     rdx, word_1800398F2
0x18000fc9e  lea     rax, [rbp+57h+var_A8]
0x18000fca2  mov     [rsp+0F0h+ppv], rax
0x18000fca7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000fcac  mov     edx, 1; int
0x18000fcb1  mov     rcx, r14; this
0x18000fcb4  call    ?_EnableDisablePenProcessTypes@CServiceModule@@AEAAHH@Z; CServiceModule::_EnableDisablePenProcessTypes(int)
0x18000fcb9  mov     rcx, r14; Context
0x18000fcbc  mov     ebx, eax
0x18000fcbe  call    ?StartEnabledPenProcesses@CServiceModule@@QEAAXXZ; CServiceModule::StartEnabledPenProcesses(void)
0x18000fcc3  mov     rcx, r14; this
0x18000fcc6  call    ?ShutdownDisabledPenProcesses@CServiceModule@@QEAAXH@Z; CServiceModule::ShutdownDisabledPenProcesses(int)
0x18000fccb  jmp     loc_18000FF19
0x18000fcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcd7  cmp     rcx, r12
0x18000fcda  jz      short loc_18000FCFE
0x18000fcdc  test    byte ptr [rcx+1Ch], 10h
0x18000fce0  jz      short loc_18000FCFE
0x18000fce2  mov     rcx, [rcx+10h]
0x18000fce6  lea     r9, aPenserviceCser_18; "PENSERVICE_CServiceModule::_ProcessScmE"...
0x18000fced  mov     edx, 43h ; 'C'
0x18000fcf2  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000fcf9  call    WPP_SF_s
0x18000fcfe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000fd05  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000fd0a  test    al, al
0x18000fd0c  mov     eax, cs:dword_1800411A8
0x18000fd12  jz      short loc_18000FD8B
0x18000fd14  cmp     eax, 5
0x18000fd17  jbe     loc_18000FDD2
0x18000fd1d  mov     rcx, cs:qword_1800411C0
0x18000fd24  mov     rax, cs:qword_1800411B8
0x18000fd2b  bt      rax, 1Ah
0x18000fd30  jnb     loc_18000FDD2
0x18000fd36  mov     rax, rcx
0x18000fd39  and     eax, 4000000h
0x18000fd3e  cmp     rax, rcx
0x18000fd41  jnz     loc_18000FDD2
0x18000fd47  movzx   eax, byte ptr [r14+41h]
0x18000fd4c  lea     rdx, byte_180039DBB
0x18000fd53  mov     [rbp+57h+var_AF], al
0x18000fd56  movzx   eax, byte ptr [r14+40h]
0x18000fd5b  mov     [rbp+57h+var_B0], al
0x18000fd5e  lea     rax, aTabletHardware; "Tablet hardware disabled"
0x18000fd65  mov     [rbp+57h+var_A8], rax
0x18000fd69  lea     rax, [rbp+57h+var_AF]
0x18000fd6d  mov     [rsp+0F0h+var_C0], rax
0x18000fd72  lea     rax, [rbp+57h+var_B0]
0x18000fd76  mov     [rsp+0F0h+var_C8], rax
0x18000fd7b  lea     rax, [rbp+57h+var_A8]
0x18000fd7f  mov     [rsp+0F0h+ppv], rax
0x18000fd84  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18000fd89  jmp     short loc_18000FDD2
0x18000fd8b  cmp     eax, 5
0x18000fd8e  jbe     short loc_18000FDD2
0x18000fd90  mov     rcx, cs:qword_1800411C0
0x18000fd97  mov     rax, cs:qword_1800411B8
0x18000fd9e  bt      rax, 1Ah
0x18000fda3  jnb     short loc_18000FDD2
0x18000fda5  mov     rax, rcx
0x18000fda8  and     eax, 4000000h
0x18000fdad  cmp     rax, rcx
0x18000fdb0  jnz     short loc_18000FDD2
0x18000fdb2  lea     rax, aTabletHardware; "Tablet hardware disabled"
0x18000fdb9  mov     [rbp+57h+var_A8], rax
0x18000fdbd  lea     rdx, dword_18003A98C
0x18000fdc4  lea     rax, [rbp+57h+var_A8]
0x18000fdc8  mov     [rsp+0F0h+ppv], rax
0x18000fdcd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000fdd2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach> `wil::Feature<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetImpl(void)'::`2'::impl
0x18000fdd9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::__private_IsEnabled(void)
0x18000fdde  test    al, al
0x18000fde0  jnz     short loc_18000FDF1
0x18000fde2  mov     edx, 1; int
0x18000fde7  mov     rcx, r14; this
0x18000fdea  call    ?_EnableDisablePenProcessTypes@CServiceModule@@AEAAHH@Z; CServiceModule::_EnableDisablePenProcessTypes(int)
0x18000fdef  mov     esi, eax
0x18000fdf1  mov     rcx, r14; this
0x18000fdf4  call    ?ShutdownDisabledPenProcesses@CServiceModule@@QEAAXH@Z; CServiceModule::ShutdownDisabledPenProcesses(int)
0x18000fdf9  mov     edx, esi
0x18000fdfb  jmp     loc_18000FF1B
0x18000fe00  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe07  cmp     rcx, r12
0x18000fe0a  jz      short loc_18000FE2E
0x18000fe0c  test    byte ptr [rcx+1Ch], 10h
0x18000fe10  jz      short loc_18000FE2E
0x18000fe12  mov     rcx, [rcx+10h]
0x18000fe16  lea     r9, aPenserviceCser_18; "PENSERVICE_CServiceModule::_ProcessScmE"...
0x18000fe1d  mov     edx, 42h ; 'B'
0x18000fe22  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000fe29  call    WPP_SF_s
0x18000fe2e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000fe35  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000fe3a  test    al, al
0x18000fe3c  mov     eax, cs:dword_1800411A8
0x18000fe42  jz      short loc_18000FEBB
0x18000fe44  cmp     eax, 5
0x18000fe47  jbe     loc_18000FF02
0x18000fe4d  mov     rcx, cs:qword_1800411C0
0x18000fe54  mov     rax, cs:qword_1800411B8
0x18000fe5b  bt      rax, 1Ah
0x18000fe60  jnb     loc_18000FF02
0x18000fe66  mov     rax, rcx
0x18000fe69  and     eax, 4000000h
0x18000fe6e  cmp     rax, rcx
0x18000fe71  jnz     loc_18000FF02
0x18000fe77  movzx   eax, byte ptr [r14+41h]
0x18000fe7c  lea     rdx, dword_180039994
0x18000fe83  mov     [rbp+57h+var_AF], al
0x18000fe86  movzx   eax, byte ptr [r14+40h]
0x18000fe8b  mov     [rbp+57h+var_B0], al
0x18000fe8e  lea     rax, aTabletHardware_1; "Tablet hardware enabled"
0x18000fe95  mov     [rbp+57h+var_A8], rax
0x18000fe99  lea     rax, [rbp+57h+var_AF]
0x18000fe9d  mov     [rsp+0F0h+var_C0], rax
0x18000fea2  lea     rax, [rbp+57h+var_B0]
0x18000fea6  mov     [rsp+0F0h+var_C8], rax
0x18000feab  lea     rax, [rbp+57h+var_A8]
0x18000feaf  mov     [rsp+0F0h+ppv], rax
0x18000feb4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18000feb9  jmp     short loc_18000FF02
0x18000febb  cmp     eax, 5
0x18000febe  jbe     short loc_18000FF02
0x18000fec0  mov     rcx, cs:qword_1800411C0
0x18000fec7  mov     rax, cs:qword_1800411B8
0x18000fece  bt      rax, 1Ah
0x18000fed3  jnb     short loc_18000FF02
0x18000fed5  mov     rax, rcx
0x18000fed8  and     eax, 4000000h
0x18000fedd  cmp     rax, rcx
0x18000fee0  jnz     short loc_18000FF02
0x18000fee2  lea     rax, aTabletHardware_1; "Tablet hardware enabled"
0x18000fee9  mov     [rbp+57h+var_A8], rax
0x18000feed  lea     rdx, word_18003A822
0x18000fef4  lea     rax, [rbp+57h+var_A8]
0x18000fef8  mov     [rsp+0F0h+ppv], rax
0x18000fefd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000ff02  mov     edx, 1; int
0x18000ff07  mov     rcx, r14; this
0x18000ff0a  call    ?_EnableDisablePenProcessTypes@CServiceModule@@AEAAHH@Z; CServiceModule::_EnableDisablePenProcessTypes(int)
0x18000ff0f  mov     rcx, r14; Context
0x18000ff12  mov     ebx, eax
0x18000ff14  call    ?StartEnabledPenProcesses@CServiceModule@@QEAAXXZ; CServiceModule::StartEnabledPenProcesses(void)
0x18000ff19  mov     edx, ebx; int
  ... truncated ...
```
