# CWwanDataExecutor::OnNdisNotification(WWAN_EVENT const *,_GUID const *)

- ea: `0x18002aa58`
- end: `0x18002c224`
- name: `?OnNdisNotification@CWwanDataExecutor@@QEAAXPEBUWWAN_EVENT@@PEBU_GUID@@@Z`
- size: `6092`
- prototype: `void __fastcall(CWwanDataExecutor *__hidden this, const struct WWAN_EVENT *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061830`

## callees

- `0x18000153c`
- `0x1800018e4`
- `0x180001980`
- `0x180001a20`
- `0x180001c28`
- `0x180001cc0`
- `0x180001d5c`
- `0x180001e0c`
- `0x180001ebc`
- `0x180001f84`
- `0x180002000`
- `0x180002098`
- `0x180002144`
- `0x1800021dc`
- `0x1800022a4`
- `0x180002368`
- `0x18000244c`
- `0x1800085d0`
- `0x1800094d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180014f1c`
- `0x18002a178`
- `0x18002aa58`
- `0x180030bb4`
- `0x180030dd8`
- `0x180033abc`
- `0x180033ce8`
- `0x18003c028`
- `0x18003c0c0`
- `0x18003c130`
- `0x18003c278`
- `0x18003c300`
- `0x18003c494`
- `0x18003c51c`
- `0x18003cfd8`
- `0x1800522dc`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b80a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b991`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b80a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b991`

## string_xrefs

- `0x18002b6db`: `IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d. Size wrong: Expeceted size %d`
- `0x18002b6f2`: `IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d APN [%s] IPv6Enabled %d`
- `0x18002b7a9`: `IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x`
- `0x18002b7c8`: `DMConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d. Size wrong: Expeceted size %d`
- `0x18002b81e`: `DMConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, OEMConnectionId %s, enabled %d, roaming %d, apnString %s, iptype %d `
- `0x18002b952`: `DMConfig DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x`
- `0x18002b971`: `DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d. Size wrong: Expeceted size %d`
- `0x18002b9a5`: `DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, OEMConnectionId %s, enabled %d, roaming %d, apnString %s, iptype %d `
- `0x18002baba`: `DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x`
- `0x18002bc63`: `DMConfigBinary DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, AdditionalInfo 0x%08x`
- `0x18002bcf3`: `DMConfigBinary DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x`

## pseudocode

```c
void __fastcall CWwanDataExecutor::OnNdisNotification(__int64 **this, const struct WWAN_EVENT *a2, struct _GUID *a3)
{
  unsigned int v4; // edx
  const wchar_t *v7; // r8
  unsigned int v8; // r14d
  __int64 v9; // r12
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // r9
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  unsigned int *v21; // rsi
  signed __int64 v22; // r8
  int v23; // ecx
  struct _GUID *v24; // r8
  int v25; // r9d
  const enum WWAN_WINPHONE_DATA_SUSPENSION_STATE *v26; // rdx
  signed __int64 v27; // r8
  int v28; // ecx
  OLECHAR *v29; // r8
  int v30; // r9d
  signed __int64 v31; // r8
  int v32; // ecx
  __int64 v33; // r8
  int v34; // r9d
  signed __int64 v35; // r8
  int v36; // ecx
  struct _GUID *v37; // r8
  int v38; // r9d
  const enum WWAN_WINPHONE_IWLAN_STATE *v39; // rdx
  signed __int64 v40; // r8
  int v41; // ecx
  struct _GUID *v42; // r8
  int v43; // r9d
  const struct WWAN_WINPHONE_MODEMTYPE_CAP *v44; // rdx
  signed __int64 v45; // r8
  int v46; // ecx
  struct _GUID *v47; // r8
  int v48; // r9d
  signed __int64 v49; // r8
  int v50; // ecx
  __int64 v51; // r8
  int v52; // r9d
  unsigned __int16 *v53; // rdx
  unsigned int v54; // r9d
  unsigned int *v55; // rbx
  unsigned int v56; // r15d
  __int64 v57; // r9
  const struct _GUID *v58; // rdx
  signed __int64 v59; // r8
  int v60; // ecx
  OLECHAR *v61; // r8
  int v62; // r9d
  const unsigned __int16 *v63; // r8
  __int64 v64; // rdx
  signed __int64 v65; // r8
  int v66; // ecx
  int v67; // r9d
  signed __int64 v68; // r8
  int v69; // ecx
  struct _GUID *v70; // r8
  int v71; // r9d
  signed __int64 v72; // r8
  int v73; // ecx
  OLECHAR *v74; // r8
  int v75; // r9d
  signed __int64 v76; // r8
  int v77; // ecx
  OLECHAR *v78; // r8
  int v79; // r9d
  signed __int64 v80; // r8
  int v81; // ecx
  struct _GUID *v82; // r8
  int v83; // r9d
  signed __int64 v84; // r8
  int v85; // ecx
  OLECHAR *v86; // r8
  int v87; // r9d
  __int64 v88; // rax
  const unsigned __int16 *v89; // r8
  signed __int64 v90; // r8
  int v91; // ecx
  __int64 v92; // r8
  int v93; // r9d
  __int64 v94; // rdx
  signed __int64 v95; // r8
  int v96; // ecx
  OLECHAR *v97; // r8
  int v98; // r9d
  signed __int64 v99; // r8
  int v100; // ecx
  struct _GUID *v101; // r8
  int v102; // r9d
  signed __int64 v103; // r8
  int v104; // ecx
  __int64 v105; // r8
  int v106; // r9d
  signed __int64 v107; // r8
  int v108; // ecx
  OLECHAR *v109; // r8
  int v110; // r9d
  signed __int64 v111; // r8
  int v112; // ecx
  __int64 v113; // r8
  int v114; // r9d
  signed __int64 v115; // r8
  int v116; // ecx
  OLECHAR *v117; // r8
  int v118; // r9d
  int v119; // edx
  int v120; // r8d
  const wchar_t *v121; // r9
  const wchar_t *v122; // r9
  const void *v123; // rax
  __int64 *v124; // rcx
  __int64 *v125; // rbx
  const void *v126; // rax
  __int64 *v127; // r15
  __int64 *i; // rbx
  const void *v129; // rax
  int v130; // ecx
  int v131; // ecx
  int v132; // ecx
  int v133; // ecx
  int v134; // ecx
  __int64 v135; // [rsp+28h] [rbp-E8h]
  struct _GUID *v136; // [rsp+90h] [rbp-80h] BYREF
  OLECHAR *v137; // [rsp+98h] [rbp-78h] BYREF
  struct _GUID *v138; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v139; // [rsp+A8h] [rbp-68h] BYREF
  OLECHAR *v140; // [rsp+B0h] [rbp-60h] BYREF
  struct _GUID *v141; // [rsp+B8h] [rbp-58h] BYREF
  _QWORD v142[2]; // [rsp+C0h] [rbp-50h] BYREF
  unsigned __int16 v143[102]; // [rsp+D0h] [rbp-40h] BYREF
  int v144; // [rsp+19Ch] [rbp+8Ch]
  OLECHAR sz[40]; // [rsp+1A0h] [rbp+90h] BYREF

  v4 = *(_DWORD *)a2;
  if ( v4 - 1 > 1 )
  {
    v7 = L"invalid event type %d";
LABEL_3:
    WwanLog::Error("CWwanDataExecutor::OnNdisNotification", 0, v7, v4);
    return;
  }
  if ( !a3 )
  {
    WwanLog::Error("CWwanDataExecutor::OnNdisNotification", 0, L"pInterfaceGuid in NULL");
    return;
  }
  if ( v4 == 1 )
  {
    v8 = *((_DWORD *)a2 + 8);
    v9 = *((_QWORD *)a2 + 3);
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  v10 = *((_DWORD *)a2 + 1);
  if ( v10 <= 41 )
  {
    if ( v10 == 41 )
      goto LABEL_209;
    if ( v10 <= 10 )
    {
      if ( v10 == 10 )
        goto LABEL_209;
      if ( !v10 )
        goto LABEL_209;
      v11 = v10 - 1;
      if ( !v11 )
        goto LABEL_209;
      v12 = v11 - 1;
      if ( !v12 )
        goto LABEL_209;
      v13 = v12 - 4;
      if ( !v13 )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState>::GetImpl'::`2'::impl) )
          return;
LABEL_209:
        CWwanDataExecutorState::OnNdisNotification((CWwanDataExecutorState *)this, a2, a3);
        return;
      }
      goto LABEL_204;
    }
    v14 = v10 - 12;
    if ( !v14 )
    {
      if ( *((_DWORD *)a2 + 22) < 0x100u )
      {
        WwanLog::Error(
          "CWwanDataExecutor::OnNdisNotification",
          0,
          L"WwanEventCodeContextState (type %d) size %d is less than expected sizeof(WWAN_CONTEXT_STATE) %d",
          v4,
          *((_DWORD *)a2 + 22),
          256);
        return;
      }
      if ( v8 )
      {
        v122 = L"Set";
        if ( *((_DWORD *)a2 + 4) )
          v122 = L"Query";
        WwanLog::Error(
          "CWwanDataExecutor::OnNdisNotification",
          a3,
          L"NDIS_STATUS_WWAN_CONTEXT_STATE Resp (%s): ReqHandle 0x%p asyncRspResult 0x%x nwStatus %d connID 0x%x ActState "
           "%d IpType %d OldConnId 0x%x (ExecId %d Sz %d)",
          v122,
          *((_QWORD *)a2 + 3),
          v8,
          *((_DWORD *)a2 + 23),
          *((_DWORD *)a2 + 24),
          *((_DWORD *)a2 + 25),
          *((_DWORD *)a2 + 27),
          *((_DWORD *)a2 + 84),
          *((_DWORD *)this + 3143),
          *((_DWORD *)a2 + 22));
      }
      else
      {
        if ( v4 == 1 )
        {
          if ( (*((_BYTE *)a2 + 320) & 1) != 0 )
          {
            v119 = *((unsigned __int16 *)a2 + 162);
            v120 = *((_DWORD *)a2 + 82);
          }
          else
          {
            v119 = 0xFFFF;
            v120 = 0xFFFFFF;
          }
          v121 = L"Set";
          if ( *((_DWORD *)a2 + 4) )
            v121 = L"Query";
          WwanLog::Info(
            "CWwanDataExecutor::OnNdisNotification",
            a3,
            L"NDIS_STATUS_WWAN_CONTEXT_STATE Resp (%s): ReqHandle 0x%p nwStatus %d connID 0x%x ActState %d APN [%s] IpType"
             " %d SST/SD 0x%x/0x%x TPoffset/TPsize %d/%d Media %d (ExecId %d Sz %d)",
            v121,
            *((_QWORD *)a2 + 3),
            *((_DWORD *)a2 + 23),
            *((_DWORD *)a2 + 24),
            *((_DWORD *)a2 + 25),
            (char *)a2 + 116,
            *((_DWORD *)a2 + 27),
            v119,
            v120,
            *((_DWORD *)a2 + 85),
            *((_DWORD *)a2 + 86),
            *((_DWORD *)a2 + 28),
            *((_DWORD *)this + 3143),
            *((_DWORD *)a2 + 22));
        }
        else
        {
          WwanLog::Info(
            "CWwanDataExecutor::OnNdisNotification",
            a3,
            L"NDIS_STATUS_WWAN_CONTEXT_STATE Event: nwStatus %d connID 0x%x ActState %d IpType %d Media %d (ExecId %d Sz %d)",
            *((unsigned int *)a2 + 23),
            *((_DWORD *)a2 + 24),
            *((_DWORD *)a2 + 25),
            *((_DWORD *)a2 + 27),
            *((_DWORD *)a2 + 28),
            *((_DWORD *)this + 3143),
            *((_DWORD *)a2 + 22));
        }
        CWwanDataExecutorState::HandleVoiceCallState(this, *((unsigned int *)a2 + 26));
      }
LABEL_183:
      v123 = (const void *)(*(__int64 (__fastcall **)(__int64 *, __int64, signed __int64))(*this[2146] + 16))(
                             this[2146],
                             v64,
                             v65);
      if ( !memcmp_0(a3, v123, 0x10u) )
      {
        v124 = this[2146];
      }
      else
      {
        v125 = this[2148];
        while ( 1 )
        {
          v125 = (__int64 *)*v125;
          if ( v125 == this[2148] )
            break;
          v126 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v125[6] + 16LL))(v125[6]);
          if ( !memcmp_0(a3, v126, 0x10u) )
          {
            if ( v125 != this[2148] )
            {
              v124 = (__int64 *)v125[6];
              goto LABEL_190;
            }
            break;
          }
        }
        v127 = this[2155];
        for ( i = (__int64 *)*v127; i != v127; i = (__int64 *)*i )
        {
          v129 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i[2] + 16LL))(i[2]);
          if ( !memcmp_0(a3, v129, 0x10u) )
            break;
        }
        if ( i == this[2155] )
        {
          WwanLog::Info(
            "CWwanDataExecutor::OnNdisNotification",
            a3,
            L"Interface is not used for the default context nor any additional context.");
          return;
        }
        v124 = (__int64 *)i[2];
      }
LABEL_190:
      CWwanContextLifeCycle::OnNdisNotification((CWwanContextLifeCycle *)(v124 + 1025), a2);
      return;
    }
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_209;
    v16 = v15 - 16;
    if ( !v16 )
    {
      if ( !(unsigned int)CWwanDataExecutor::shallWeProcessDSNotification(a2) )
        return;
      v54 = *((_DWORD *)a2 + 27);
      v55 = (unsigned int *)((char *)a2 + 116);
      v56 = *((_DWORD *)a2 + 28);
      if ( v54 > 0xCEEF1001 )
      {
        switch ( v54 )
        {
          case 0xCEEF1002:
LABEL_90:
            v57 = v9;
            if ( v8 )
            {
              v63 = L"LTEInfo DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_101;
            }
            if ( *v55 == 1 )
            {
              WwanLog::Info(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"LTEInfoV1 DSResponse(ReqHandle 0x%p) PLSize %d bLTEAttached %d lastAttachAPN [%s] lastAttachIpType %d",
                v9,
                *((_DWORD *)a2 + 28),
                *((_DWORD *)a2 + 30),
                (char *)a2 + 124,
                *((_DWORD *)a2 + 82));
              v68 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
              if ( (unsigned int)dword_180151040 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v68) )
              {
                LODWORD(v138) = *((_DWORD *)a2 + 82);
                LODWORD(v139) = *((_DWORD *)a2 + 30);
                v137 = (OLECHAR *)((char *)a2 + 124);
                v136 = v70;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                  v69,
                  (unsigned int)&dword_18013E94C,
                  (_DWORD)v70,
                  v71,
                  (__int64)&v136,
                  (__int64)&v139,
                  (__int64)&v137,
                  (__int64)&v138);
              }
            }
            else
            {
              WwanLog::Info(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"LTEInfoV2 DSResponse(ReqHandle 0x%p) PLSize %d bLTEAttached %d lastAttachAPN [%s] lastAttachIpType %d Un"
                 "bridgedBearer %d bUnbridgedBearerModemUsage %d ",
                v9,
                *((_DWORD *)a2 + 28),
                *((_DWORD *)a2 + 30),
                (char *)a2 + 124,
                *((_DWORD *)a2 + 82),
                *((_DWORD *)a2 + 83),
                *((_DWORD *)a2 + 84));
              v72 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
              if ( (unsigned int)dword_180151040 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v72) )
              {
                LODWORD(v138) = *((_DWORD *)a2 + 84);
                LODWORD(v139) = *((_DWORD *)a2 + 83);
                LODWORD(v141) = *((_DWORD *)a2 + 82);
                LODWORD(v136) = *((_DWORD *)a2 + 30);
                v137 = (OLECHAR *)((char *)a2 + 124);
                v140 = v74;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v73,
                  (unsigned int)byte_18013E8C9,
                  (_DWORD)v74,
                  v75,
                  (__int64)&v140,
                  (__int64)&v136,
                  (__int64)&v137,
                  (__int64)&v141,
                  (__int64)&v139,
                  (__int64)&v138);
              }
            }
            if ( *((_DWORD *)a2 + 30) )
            {
              memset_0(v143, 0, sizeof(v143));
              v144 = *((_DWORD *)a2 + 82);
              StringCchCopyW(v143, 0x65u, (const unsigned __int16 *)a2 + 62);
              v53 = v143;
              goto LABEL_71;
            }
            return;
          case 0xCEEF1003:
LABEL_85:
            if ( v8 )
            {
              WwanLog::Error(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"ActivOption DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x",
                v9,
                *((_DWORD *)a2 + 28),
                v8);
            }
            else
            {
              WwanLog::Info(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"ActivOption DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d CurOption %d",
                v9,
                *((_DWORD *)a2 + 28),
                *v55,
                *((_DWORD *)a2 + 30));
              v65 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
              if ( (unsigned int)dword_180151040 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v65) )
              {
                LODWORD(v138) = *((_DWORD *)a2 + 30);
                LODWORD(v139) = *v55;
                v137 = (OLECHAR *)v65;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v66,
                  (unsigned int)byte_18013E9A1,
                  v65,
                  v67,
                  (__int64)&v137,
                  (__int64)&v139,
                  (__int64)&v138);
              }
            }
            goto LABEL_183;
          case 0xCEEF1004:
LABEL_102:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"DataDormancyHint DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"DataDormancyHint DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d CurDDHint %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55,
              *((_DWORD *)a2 + 30));
            v76 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v76) )
            {
              LODWORD(v136) = *((_DWORD *)a2 + 30);
              LODWORD(v138) = *v55;
              v140 = (OLECHAR *)a3;
              v137 = v78;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v77,
                (unsigned int)&word_18013E866,
                (_DWORD)v78,
                v79,
                (__int64)&v137,
                (__int64)&v140,
                (__int64)&v138,
                (__int64)&v136);
            }
            CWwanDataExecutorState::HandleDormancyHintRsp(
              (CWwanDataExecutorState *)this,
              (const struct WWAN_EVENT *)((char *)a2 + 116));
            return;
          case 0xCEEF1005:
LABEL_108:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"ModemExecutorNumber DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"ModemExecutorNumber DSResponse(ReqHandle 0x%p) PLSize %d Modem# %d Exe# %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55,
              *((_DWORD *)a2 + 30));
            v80 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v80) )
            {
              v140 = (OLECHAR *)*((unsigned int *)a2 + 30);
              v137 = (OLECHAR *)*v55;
              v136 = v82;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                v81,
                (unsigned int)word_18013E822,
                (_DWORD)v82,
                v83,
                (__int64)&v136,
                (__int64)&v137,
                (__int64)&v140);
            }
            return;
          case 0xCEEF1006:
LABEL_121:
            if ( v8 )
            {
              v57 = v9;
              v63 = L"DMConfig DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_101;
            }
            v88 = 236;
            if ( v56 != 236 )
            {
              v89 = L"DMConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d. Size wrong: Expeceted size %d";
              goto LABEL_124;
            }
            StringFromGUID2((const GUID *const)a2 + 21, sz, 40);
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"DMConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, OEMConnectionId %s, enabled %d, roaming %d, apnS"
               "tring %s, iptype %d ",
              v9,
              236,
              *v55,
              sz,
              *((_DWORD *)a2 + 81),
              *((_DWORD *)a2 + 82),
              (char *)a2 + 120,
              *((_DWORD *)a2 + 83));
            v90 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v90) )
            {
              LODWORD(v136) = *((_DWORD *)a2 + 83);
              LODWORD(v138) = *((_DWORD *)a2 + 82);
              LODWORD(v139) = *((_DWORD *)a2 + 81);
              v137 = sz;
              LODWORD(v141) = *v55;
              v140 = (OLECHAR *)((char *)a2 + 120);
              v142[0] = v92;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v91,
                (unsigned int)qword_18013E770,
                v92,
                v93,
                (__int64)v142,
                (__int64)&v141,
                (__int64)&v137,
                (__int64)&v139,
                (__int64)&v138,
                (__int64)&v140,
                (__int64)&v136);
            }
            v142[0] = 1;
            goto LABEL_129;
          case 0xCEEF1007:
LABEL_113:
            v57 = v9;
            if ( v8 )
            {
              v63 = L"IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_101;
            }
            v58 = a3;
            if ( v56 != 212 )
            {
              v135 = 212;
              v63 = L"IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d. Size wrong: Expeceted size %d";
              goto LABEL_83;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"IPV6eHRPDConfig DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d APN [%s] IPv6Enabled %d",
              v9,
              212,
              *v55,
              (char *)a2 + 120,
              *((_DWORD *)a2 + 81));
            v84 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v84) )
            {
              LODWORD(v136) = *((_DWORD *)a2 + 81);
              LODWORD(v138) = *v55;
              v140 = (OLECHAR *)((char *)a2 + 120);
              v137 = v86;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v85,
                (unsigned int)byte_18013E7D5,
                (_DWORD)v86,
                v87,
                (__int64)&v137,
                (__int64)&v138,
                (__int64)&v140,
                (__int64)&v136);
            }
            CWwanDataExecutorState::HandleIPv6eHRPDControlResponse(
              (CWwanDataExecutorState *)this,
              *((void *const *)a2 + 3),
              (const struct WWAN_EVENT *)((char *)a2 + 116));
            return;
          case 0xCEEF1008:
LABEL_139:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"ModemDualSIMCap DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"ModemDualSIMCap DSResponse(ReqHandle 0x%p) PLSize %d fTypeKnown %d nExecutors %d nActiveExecutors %d nActi"
               "veDataExecutors %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55,
              *((_DWORD *)a2 + 30),
              *((_DWORD *)a2 + 31),
              *((_DWORD *)a2 + 32));
            v99 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v99) )
            {
              v142[0] = *((unsigned int *)a2 + 32);
              v140 = (OLECHAR *)*((unsigned int *)a2 + 31);
              v137 = (OLECHAR *)*((unsigned int *)a2 + 30);
              LODWORD(v136) = *v55;
              v138 = v101;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                v100,
                (unsigned int)&unk_18013E6A0,
                (_DWORD)v101,
                v102,
                (__int64)&v138,
                (__int64)&v136,
                (__int64)&v137,
                (__int64)&v140,
                (__int64)v142);
            }
            v44 = (const struct WWAN_EVENT *)((char *)a2 + 116);
            goto LABEL_63;
          case 0xCEEF1009:
LABEL_145:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"MaxCntxtNumber DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"MaxCntxtNumber DSResponse(ReqHandle 0x%p) PLSize %d MaxCntxtNumber %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55);
            v103 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v103) )
            {
              LODWORD(v136) = *v55;
              v142[0] = v105;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                v104,
                (unsigned int)&byte_18013E667,
                v105,
                v106,
                (__int64)v142,
                (__int64)&v136);
            }
            return;
          case 0xCEEF100A:
LABEL_131:
            if ( !v8 )
            {
              v88 = 1272;
              if ( v56 == 1272 )
              {
                StringFromGUID2((const GUID *const)((char *)a2 + 344), sz, 40);
                WwanLog::Info(
                  "CWwanDataExecutor::OnNdisNotification",
                  a3,
                  L"DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, OEMConnectionId %s, enabled %d, roaming %d"
                   ", apnString %s, iptype %d ",
                  v9,
                  1272,
                  *v55,
                  sz,
                  *((_DWORD *)a2 + 83),
                  *((_DWORD *)a2 + 84),
                  (char *)a2 + 128,
                  *((_DWORD *)a2 + 85));
                v95 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
                if ( (unsigned int)dword_180151040 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v95) )
                {
                  LODWORD(v136) = *((_DWORD *)a2 + 85);
                  LODWORD(v138) = *((_DWORD *)a2 + 84);
                  LODWORD(v139) = *((_DWORD *)a2 + 83);
                  v140 = sz;
                  LODWORD(v141) = *v55;
                  v142[0] = (char *)a2 + 128;
                  v137 = v97;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    v96,
                    (unsigned int)byte_18013E70D,
                    (_DWORD)v97,
                    v98,
                    (__int64)&v137,
                    (__int64)&v141,
                    (__int64)&v140,
                    (__int64)&v139,
                    (__int64)&v138,
                    (__int64)v142,
                    (__int64)&v136);
                }
                v142[0] = 2;
LABEL_129:
                v94 = *((_QWORD *)a2 + 3);
                v142[1] = (char *)a2 + 116;
                CWwanModemProfileController::HandleDmConfigConnResponse(this + 7, v94, v142);
              }
              else
              {
                v89 = L"DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d. Size wrong: Expeceted size %d";
LABEL_124:
                WwanLog::Error("CWwanDataExecutor::OnNdisNotification", a3, v89, v9, *((_DWORD *)a2 + 28), *v55, v88);
              }
              return;
            }
            v57 = v9;
            v63 = L"DMConfigV2 DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
LABEL_101:
            LODWORD(v135) = v8;
            v58 = a3;
            goto LABEL_83;
          case 0xCEEF100B:
LABEL_150:
            if ( v8 )
            {
              WwanLog::Error(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"DMConfigBinary DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x",
                v9,
                *((_DWORD *)a2 + 28),
                v8);
            }
            else
            {
              WwanLog::Info(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"DMConfigBinary DSResponse(ReqHandle 0x%p) PLSize %d Rspcode %d, AdditionalInfo 0x%08x",
                v9,
                *((_DWORD *)a2 + 28),
                *((_DWORD *)a2 + 30),
                *((_DWORD *)a2 + 31));
              v107 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
              if ( (unsigned int)dword_180151040 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v107) )
              {
                v142[0] = *((unsigned int *)a2 + 31);
                LODWORD(v136) = *((_DWORD *)a2 + 30);
                v140 = v109;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                  v108,
                  (unsigned int)byte_18013E623,
                  (_DWORD)v109,
                  v110,
                  (__int64)&v140,
                  (__int64)&v136,
                  (__int64)v142);
              }
            }
            CWwanModemProfileController::HandleDmConfigBinaryResponse(
              (CWwanModemProfileController *)(this + 7),
              *((void *const *)a2 + 3),
              v8,
              v56,
              (const struct WWAN_EVENT *)((char *)a2 + 116));
            return;
          case 0xCEEF100C:
LABEL_156:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"IWlanState DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"IWlanState DSResponse(ReqHandle 0x%p) PLSize %d IWLAN availability state %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55);
            v111 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v111) )
            {
              LODWORD(v136) = *v55;
              v142[0] = v113;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                v112,
                (unsigned int)byte_18013E5F5,
                v113,
                v114,
                (__int64)v142,
                (__int64)&v136);
            }
            v39 = (const struct WWAN_EVENT *)((char *)a2 + 116);
            goto LABEL_58;
          case 0xCEEF100D:
LABEL_162:
            v57 = v9;
            v58 = a3;
            if ( v8 )
            {
              v63 = L"ConnectionMediumState DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
              goto LABEL_82;
            }
            WwanLog::Info(
              "CWwanDataExecutor::OnNdisNotification",
              a3,
              L"ConnectionMediumState DSResponse(ReqHandle 0x%p) PLSize %d ver %d connID 0x%x medium %d",
              v9,
              *((_DWORD *)a2 + 28),
              *v55,
              *((_DWORD *)a2 + 30),
              *((_DWORD *)a2 + 31));
            v115 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v115) )
            {
              LODWORD(v136) = *((_DWORD *)a2 + 31);
              v142[0] = *((unsigned int *)a2 + 30);
              v140 = (OLECHAR *)*v55;
              v137 = v117;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                v116,
                (unsigned int)byte_18013E595,
                (_DWORD)v117,
                v118,
                (__int64)&v137,
                (__int64)&v140,
                (__int64)v142,
                (__int64)&v136);
            }
            break;
          default:
LABEL_167:
            WwanLog::Info("CWwanDataExecutor::OnNdisNotification", a3, L"WP 0x%x DSResponse(ReqHandle 0x%p) PLSize %d");
            return;
        }
        return;
      }
      if ( v54 != -823193599 )
      {
        switch ( v54 )
        {
          case 0xBEEF1001:
            break;
          case 0xBEEF1002:
            goto LABEL_90;
          case 0xBEEF1003:
            goto LABEL_85;
          case 0xBEEF1004:
            goto LABEL_102;
          case 0xBEEF1005:
            goto LABEL_108;
          case 0xBEEF1006:
            goto LABEL_121;
          case 0xBEEF1007:
            goto LABEL_113;
          case 0xBEEF1008:
            goto LABEL_139;
          case 0xBEEF1009:
            goto LABEL_145;
          case 0xBEEF100A:
            goto LABEL_131;
          case 0xBEEF100B:
            goto LABEL_150;
          case 0xBEEF100C:
            goto LABEL_156;
          case 0xBEEF100D:
            goto LABEL_162;
          default:
            goto LABEL_167;
        }
      }
      v57 = v9;
      v58 = a3;
      if ( v8 )
      {
        v63 = L"-->DataSuspension DSResponse(ReqHandle 0x%p) PLSize %d asyncRspResult 0x%x";
LABEL_82:
        LODWORD(v135) = v8;
LABEL_83:
        WwanLog::Error("CWwanDataExecutor::OnNdisNotification", v58, v63, v57, *((_DWORD *)a2 + 28), v135);
        return;
      }
      WwanLog::Info(
        "CWwanDataExecutor::OnNdisNotification",
        a3,
        L"-->DataSuspension DSResponse(ReqHandle 0x%p) PLSize %d State %d",
        v9,
        *((_DWORD *)a2 + 28),
        *v55);
      v59 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v59) )
      {
        LODWORD(v138) = *v55;
        v137 = v61;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v60,
          (unsigned int)qword_18013E9F0,
          (_DWORD)v61,
          v62,
          (__int64)&v137,
          (__int64)&v138);
      }
      v26 = (const struct WWAN_EVENT *)((char *)a2 + 116);
LABEL_41:
      CWwanDataExecutorState::HandleDataSuspension((CWwanDataExecutorState *)this, v26);
      return;
    }
    v17 = v16 - 2;
    if ( v17 )
    {
      if ( v17 == 9 )
      {
        if ( v4 != 2 )
        {
          v7 = L"invalid event type (%d) with WwanEventCodeDevicePowerState";
          goto LABEL_3;
        }
        v18 = *((unsigned int *)a2 + 22);
        if ( (unsigned int)v18 >= 4 )
          CWwanDataExecutor::OnDevicePowerStateChange((CWwanDataExecutor *)this, *((_DWORD *)a2 + 23));
        else
          WwanLog::Error(
            "CWwanDataExecutor::OnNdisNotification",
            0,
            L"invalid data size (%d) with WwanEventCodeDevicePowerState",
            v18);
      }
      return;
    }
    if ( !(unsigned int)CWwanDataExecutor::shallWeProcessDSNotification(a2) )
      return;
    v19 = *((_DWORD *)a2 + 27);
    v20 = *((_DWORD *)a2 + 28);
    v21 = (unsigned int *)((char *)a2 + 116);
    if ( v19 > 0xDEEF1002 )
    {
      if ( v19 == -554758141 )
      {
        WwanLog::Info(
          "CWwanDataExecutor::OnNdisNotification",
          a3,
          L"LTEAttachDefaultBearer DSEvent PLSize %d AttachAPN [%s] IpType %d ",
          v20,
          v21,
          v21[51]);
        v49 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
        if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v49) )
        {
          LODWORD(v138) = v21[51];
          v137 = (OLECHAR *)v21;
          v136 = a3;
          v139 = v51;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v50,
            (unsigned int)&unk_18013E478,
            v51,
            v52,
            (__int64)&v139,
            (__int64)&v136,
            (__int64)&v137,
            (__int64)&v138);
        }
        v53 = (unsigned __int16 *)v21;
LABEL_71:
        CWwanDataExecutorState::HandleLTEAttachBearerInfo(
          (CWwanDataExecutorState *)this,
          (const struct _WWAN_WINPHONE_LTE_ATTACH_BEARER_DATA *)v53);
        return;
      }
      if ( v19 == -554758140 )
      {
        WwanLog::Info(
          "CWwanDataExecutor::OnNdisNotification",
          a3,
          L"LTEDefaultBearerBridging DSEvent PLSize %d bBridging %d APN [%s] IpType %d ",
          v20,
          *v21,
          v21 + 1,
          v21[52]);
        v45 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
        if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v45) )
        {
          LODWORD(v138) = *v21;
          v137 = (OLECHAR *)(v21 + 1);
          v136 = v47;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v46,
            (unsigned int)byte_18013E42B,
            (_DWORD)v47,
            v48,
            (__int64)&v136,
            (__int64)&v138,
            (__int64)&v137);
        }
        return;
      }
      if ( v19 != -554758139 )
      {
        if ( v19 != -554758138 )
        {
          if ( v19 != -554758137 )
            goto LABEL_50;
          goto LABEL_51;
        }
LABEL_54:
        WwanLog::Info(
          "CWwanDataExecutor::OnNdisNotification",
          a3,
          L"IWlanState DSEvent PLSize %d IWLAN availability state %d",
          v20,
          *v21);
        v35 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
        if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v35) )
        {
          LODWORD(v141) = *v21;
          v137 = (OLECHAR *)a3;
          v136 = v37;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v36,
            (unsigned int)word_18013E38A,
            (_DWORD)v37,
            v38,
            (__int64)&v136,
            (__int64)&v137,
            (__int64)&v141);
        }
        v39 = (const enum WWAN_WINPHONE_IWLAN_STATE *)v21;
LABEL_58:
        CWwanDataExecutorState::HandleIWLANState((CWwanDataExecutorState *)this, v39);
        return;
      }
    }
    else
    {
      if ( v19 == -554758142 )
      {
        WwanLog::Info(
          "CWwanDataExecutor::OnNdisNotification",
          a3,
          L"InternalErrorReport DSEvent PLSize %d IntErrGrp %d IntErrCause %d IntErrInfo %d",
          v20,
          *v21,
          v21[1],
          v21[2]);
        v27 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
        if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v27) )
        {
          v136 = (struct _GUID *)v21[2];
          v138 = (struct _GUID *)v21[1];
          v139 = *v21;
          v141 = a3;
          v137 = v29;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v28,
            (unsigned int)byte_18013E4CB,
            (_DWORD)v29,
            v30,
            (__int64)&v137,
            (__int64)&v141,
            (__int64)&v139,
            (__int64)&v138,
            (__int64)&v136);
        }
        return;
      }
      if ( v19 == -1091629055 )
        goto LABEL_37;
      if ( v19 != -1091629048 )
      {
        if ( v19 != -1091629044 )
        {
          if ( v19 != -1091629043 )
          {
            if ( v19 == -554758143 )
            {
LABEL_37:
              WwanLog::Info(
                "CWwanDataExecutor::OnNdisNotification",
                a3,
                L"DataSuspension DSEvent PLSize %d State %d",
                v20,
                *v21);
              v22 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
              if ( (unsigned int)dword_180151040 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v22) )
              {
                LODWORD(v141) = *v21;
                v136 = a3;
                v138 = v24;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                  v23,
                  (unsigned int)word_18013E54A,
                  (_DWORD)v24,
                  v25,
                  (__int64)&v138,
                  (__int64)&v136,
                  (__int64)&v141);
              }
              v26 = (const enum WWAN_WINPHONE_DATA_SUSPENSION_STATE *)v21;
              goto LABEL_41;
            }
LABEL_50:
            WwanLog::Info("CWwanDataExecutor::OnNdisNotification", a3, L"WP 0x%x DSEvent PLSize %d");
            return;
          }
LABEL_51:
          WwanLog::Info(
            "CWwanDataExecutor::OnNdisNotification",
            a3,
            L"ConnectionMediumState DSEvent PLSize %d ver %d connID 0x%x medium %d",
            v20,
            *v21,
            v21[1],
            v21[2]);
          v31 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
          if ( (unsigned int)dword_180151040 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v31) )
          {
            LODWORD(v141) = v21[2];
            v137 = (OLECHAR *)v21[1];
            v136 = (struct _GUID *)*v21;
            v138 = a3;
            v139 = v33;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v32,
              (unsigned int)&unk_18013E318,
              v33,
              v34,
              (__int64)&v139,
              (__int64)&v138,
              (__int64)&v136,
              (__int64)&v137,
              (__int64)&v141);
          }
          return;
        }
        goto LABEL_54;
      }
    }
    WwanLog::Info(
      "CWwanDataExecutor::OnNdisNotification",
      a3,
      L"ModemDualSIMCap DSEvent PLSize %d fTypeKnown %d nExecutors %d nActiveExecutors %d nActiveDataExecutors %d",
      v20,
      *v21,
      v21[1],
      v21[2],
      v21[3]);
    v40 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
    if ( (unsigned int)dword_180151040 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x200000000000LL, v40) )
    {
      LODWORD(v141) = v21[2];
      LODWORD(v139) = v21[1];
      LODWORD(v138) = *v21;
      v137 = (OLECHAR *)a3;
      v136 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v41,
        (unsigned int)&byte_18013E3C7,
        (_DWORD)v42,
        v43,
        (__int64)&v136,
        (__int64)&v137,
        (__int64)&v138,
        (__int64)&v139,
        (__int64)&v141);
    }
    v44 = (const struct WWAN_WINPHONE_MODEMTYPE_CAP *)v21;
LABEL_63:
    CWwanDataExecutorState::HandleModemDualSIMCap((CWwanDataExecutorState *)this, v44);
    return;
  }
  if ( v10 > 61 )
  {
    v133 = v10 - 68;
    if ( !v133 )
      goto LABEL_209;
    v134 = v133 - 7;
    if ( !v134 || (unsigned int)(v134 - 1) <= 1 )
      goto LABEL_209;
    return;
  }
  if ( v10 == 61 )
    goto LABEL_209;
  v130 = v10 - 50;
  if ( !v130 )
    goto LABEL_209;
  v131 = v130 - 4;
  if ( !v131 )
    goto LABEL_209;
  v132 = v131 - 1;
  if ( !v132 )
    goto LABEL_209;
  v13 = v132 - 1;
  if ( !v13 )
    goto LABEL_209;
LABEL_204:
  if ( v13 == 3 )
    goto LABEL_209;
}

```

## disassembly

```asm
0x18002aa58  mov     [rsp-8+arg_18], rbx
0x18002aa5d  push    rbp
0x18002aa5e  push    rsi
0x18002aa5f  push    rdi
0x18002aa60  push    r12
0x18002aa62  push    r13
0x18002aa64  push    r14
0x18002aa66  push    r15
0x18002aa68  lea     rbp, [rsp-0F0h]
0x18002aa70  sub     rsp, 200h
0x18002aa77  mov     rax, cs:__security_cookie
0x18002aa7e  xor     rax, rsp
0x18002aa81  mov     [rbp+120h+var_40], rax
0x18002aa88  mov     rsi, rdx
0x18002aa8b  mov     r15d, 1
0x18002aa91  mov     edx, [rdx]
0x18002aa93  mov     rdi, r8
0x18002aa96  mov     r13, rcx
0x18002aa99  lea     eax, [rdx-1]
0x18002aa9c  cmp     eax, r15d
0x18002aa9f  jbe     short loc_18002AABE
0x18002aaa1  lea     r8, aInvalidEventTy_1; "invalid event type %d"
0x18002aaa8  mov     r9d, edx
0x18002aaab  xor     edx, edx; struct _GUID *
0x18002aaad  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002aab4  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002aab9  jmp     loc_18002C194
0x18002aabe  test    rdi, rdi
0x18002aac1  jnz     short loc_18002AADD
0x18002aac3  lea     r8, aPinterfaceguid_0; "pInterfaceGuid in NULL"
0x18002aaca  xor     edx, edx; struct _GUID *
0x18002aacc  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002aad3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18002aad8  jmp     loc_18002C194
0x18002aadd  cmp     edx, r15d
0x18002aae0  jnz     short loc_18002AAEC
0x18002aae2  mov     r14d, [rsi+20h]
0x18002aae6  mov     r12, [rsi+18h]
0x18002aaea  jmp     short loc_18002AAF2
0x18002aaec  xor     r14d, r14d
0x18002aaef  xor     r12d, r12d
0x18002aaf2  mov     ecx, [rsi+4]
0x18002aaf5  cmp     ecx, 29h ; ')'
0x18002aaf8  jg      loc_18002C150
0x18002aafe  jz      loc_18002C186
0x18002ab04  cmp     ecx, 0Ah
0x18002ab07  jg      short loc_18002AB4B
0x18002ab09  jz      loc_18002C186
0x18002ab0f  test    ecx, ecx
0x18002ab11  jz      loc_18002C186
0x18002ab17  sub     ecx, r15d
0x18002ab1a  jz      loc_18002C186
0x18002ab20  sub     ecx, r15d
0x18002ab23  jz      loc_18002C186
0x18002ab29  sub     ecx, 4
0x18002ab2c  jnz     loc_18002C16B
0x18002ab32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState> `wil::Feature<__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState>::GetImpl(void)'::`2'::impl
0x18002ab39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSvc_Fix_Missing_HomeProvider_in_CWwanDataExecutorState>::__private_IsEnabled(void)
0x18002ab3e  test    al, al
0x18002ab40  jnz     loc_18002C186
0x18002ab46  jmp     loc_18002C194
0x18002ab4b  sub     ecx, 0Ch
0x18002ab4e  jz      loc_18002BEAF
0x18002ab54  sub     ecx, r15d
0x18002ab57  jz      loc_18002C186
0x18002ab5d  sub     ecx, 10h
0x18002ab60  jz      loc_18002B148
0x18002ab66  sub     ecx, 2
0x18002ab69  jz      short loc_18002ABAB
0x18002ab6b  cmp     ecx, 9
0x18002ab6e  jnz     loc_18002C194
0x18002ab74  cmp     edx, 2
0x18002ab77  jz      short loc_18002AB85
0x18002ab79  lea     r8, aInvalidEventTy; "invalid event type (%d) with WwanEventC"...
0x18002ab80  jmp     loc_18002AAA8
0x18002ab85  mov     r9d, [rsi+58h]
0x18002ab89  cmp     r9d, 4
0x18002ab8d  jnb     short loc_18002AB9B
0x18002ab8f  lea     r8, aInvalidDataSiz_2; "invalid data size (%d) with WwanEventCo"...
0x18002ab96  jmp     loc_18002AAAB
0x18002ab9b  mov     edx, [rsi+5Ch]; unsigned int
0x18002ab9e  mov     rcx, r13; this
0x18002aba1  call    ?OnDevicePowerStateChange@CWwanDataExecutor@@AEAAXK@Z; CWwanDataExecutor::OnDevicePowerStateChange(ulong)
0x18002aba6  jmp     loc_18002C194
0x18002abab  mov     rcx, rsi; struct WWAN_EVENT *
0x18002abae  call    ?shallWeProcessDSNotification@CWwanDataExecutor@@KAHPEBUWWAN_EVENT@@@Z; CWwanDataExecutor::shallWeProcessDSNotification(WWAN_EVENT const *)
0x18002abb3  test    eax, eax
0x18002abb5  jz      loc_18002C194
0x18002abbb  mov     r9d, [rsi+6Ch]
0x18002abbf  mov     eax, 0DEEF1002h
0x18002abc4  mov     ecx, [rsi+70h]
0x18002abc7  add     rsi, 74h ; 't'
0x18002abcb  cmp     r9d, eax
0x18002abce  ja      loc_18002AD71
0x18002abd4  jz      loc_18002ACAE
0x18002abda  cmp     r9d, 0BEEF1001h
0x18002abe1  jz      short loc_18002AC17
0x18002abe3  cmp     r9d, 0BEEF1008h
0x18002abea  jz      loc_18002AF26
0x18002abf0  cmp     r9d, 0BEEF100Ch
0x18002abf7  jz      loc_18002AE8F
0x18002abfd  cmp     r9d, 0BEEF100Dh
0x18002ac04  jz      loc_18002ADCD
0x18002ac0a  cmp     r9d, 0DEEF1001h
0x18002ac11  jnz     loc_18002ADAE
0x18002ac17  mov     eax, [rsi]
0x18002ac19  lea     r8, aDatasuspension; "DataSuspension DSEvent PLSize %d State "...
0x18002ac20  mov     r9d, ecx
0x18002ac23  mov     dword ptr [rsp+230h+var_210], eax
0x18002ac27  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002ac2e  mov     rdx, rdi; struct _GUID *
0x18002ac31  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002ac36  mov     r8, r15
0x18002ac39  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002ac42  mov     eax, cs:dword_180151040
0x18002ac48  add     r8, r15
0x18002ac4b  cmp     eax, 5
0x18002ac4e  jbe     short loc_18002AC9E
0x18002ac50  mov     rdx, 200000000000h
0x18002ac5a  lea     rcx, dword_180151040
0x18002ac61  call    _tlgKeywordOn
0x18002ac66  test    al, al
0x18002ac68  jz      short loc_18002AC9E
0x18002ac6a  mov     eax, [rsi]
0x18002ac6c  lea     rdx, word_18013E54A
0x18002ac73  mov     dword ptr [rbp+120h+var_178], eax
0x18002ac76  lea     rax, [rbp+120h+var_178]
0x18002ac7a  mov     [rsp+230h+var_200], rax
0x18002ac7f  lea     rax, [rbp+120h+var_1A0]
0x18002ac83  mov     [rsp+230h+var_208], rax
0x18002ac88  lea     rax, [rbp+120h+var_190]
0x18002ac8c  mov     [rsp+230h+var_210], rax
0x18002ac91  mov     [rbp+120h+var_1A0], rdi
0x18002ac95  mov     [rbp+120h+var_190], r8
0x18002ac99  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002ac9e  mov     rdx, rsi; enum WWAN_WINPHONE_DATA_SUSPENSION_STATE *
0x18002aca1  mov     rcx, r13; this
0x18002aca4  call    ?HandleDataSuspension@CWwanDataExecutorState@@IEAAXPEBW4WWAN_WINPHONE_DATA_SUSPENSION_STATE@@@Z; CWwanDataExecutorState::HandleDataSuspension(WWAN_WINPHONE_DATA_SUSPENSION_STATE const *)
0x18002aca9  jmp     loc_18002C194
0x18002acae  mov     eax, [rsi+8]
0x18002acb1  lea     r8, aInternalerrorr; "InternalErrorReport DSEvent PLSize %d I"...
0x18002acb8  mov     dword ptr [rsp+230h+var_200], eax
0x18002acbc  mov     r9d, ecx
0x18002acbf  mov     eax, [rsi+4]
0x18002acc2  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002acc9  mov     dword ptr [rsp+230h+var_208], eax
0x18002accd  mov     rdx, rdi; struct _GUID *
0x18002acd0  mov     eax, [rsi]
0x18002acd2  mov     dword ptr [rsp+230h+var_210], eax
0x18002acd6  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002acdb  mov     r8, r15
0x18002acde  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002ace7  mov     eax, cs:dword_180151040
0x18002aced  add     r8, r15
0x18002acf0  cmp     eax, 5
0x18002acf3  jbe     loc_18002C194
0x18002acf9  mov     rdx, 200000000000h
0x18002ad03  lea     rcx, dword_180151040
0x18002ad0a  call    _tlgKeywordOn
0x18002ad0f  test    al, al
0x18002ad11  jz      loc_18002C194
0x18002ad17  mov     eax, [rsi+8]
0x18002ad1a  lea     rdx, byte_18013E4CB
0x18002ad21  mov     [rbp+120h+var_1A0], rax
0x18002ad25  mov     eax, [rsi+4]
0x18002ad28  mov     [rbp+120h+var_190], rax
0x18002ad2c  mov     eax, [rsi]
0x18002ad2e  mov     [rbp+120h+var_188], rax
0x18002ad32  lea     rax, [rbp+120h+var_1A0]
0x18002ad36  mov     [rsp+230h+var_1F0], rax
0x18002ad3b  lea     rax, [rbp+120h+var_190]
0x18002ad3f  mov     [rsp+230h+var_1F8], rax
0x18002ad44  lea     rax, [rbp+120h+var_188]
0x18002ad48  mov     [rsp+230h+var_200], rax
0x18002ad4d  lea     rax, [rbp+120h+var_178]
0x18002ad51  mov     [rsp+230h+var_208], rax
0x18002ad56  lea     rax, [rbp+120h+var_198]
0x18002ad5a  mov     [rsp+230h+var_210], rax
0x18002ad5f  mov     [rbp+120h+var_178], rdi
0x18002ad63  mov     [rbp+120h+var_198], r8
0x18002ad67  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002ad6c  jmp     loc_18002C194
0x18002ad71  cmp     r9d, 0DEEF1003h
0x18002ad78  jz      loc_18002B097
0x18002ad7e  cmp     r9d, 0DEEF1004h
0x18002ad85  jz      loc_18002AFF0
0x18002ad8b  cmp     r9d, 0DEEF1005h
0x18002ad92  jz      loc_18002AF26
0x18002ad98  cmp     r9d, 0DEEF1006h
0x18002ad9f  jz      loc_18002AE8F
0x18002ada5  cmp     r9d, 0DEEF1007h
0x18002adac  jz      short loc_18002ADCD
0x18002adae  mov     dword ptr [rsp+230h+var_210], ecx
0x18002adb2  lea     r8, aWp0xXDseventPl; "WP 0x%x DSEvent PLSize %d"
0x18002adb9  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002adc0  mov     rdx, rdi; struct _GUID *
0x18002adc3  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002adc8  jmp     loc_18002C194
0x18002adcd  mov     eax, [rsi+8]
0x18002add0  lea     r8, aConnectionmedi; "ConnectionMediumState DSEvent PLSize %d"...
0x18002add7  mov     dword ptr [rsp+230h+var_200], eax
0x18002addb  mov     r9d, ecx
0x18002adde  mov     eax, [rsi+4]
0x18002ade1  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002ade8  mov     dword ptr [rsp+230h+var_208], eax
0x18002adec  mov     rdx, rdi; struct _GUID *
0x18002adef  mov     eax, [rsi]
0x18002adf1  mov     dword ptr [rsp+230h+var_210], eax
0x18002adf5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002adfa  mov     r8, r15
0x18002adfd  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002ae06  mov     eax, cs:dword_180151040
0x18002ae0c  add     r8, r15
0x18002ae0f  cmp     eax, 5
0x18002ae12  jbe     loc_18002C194
0x18002ae18  mov     rdx, 200000000000h
0x18002ae22  lea     rcx, dword_180151040
0x18002ae29  call    _tlgKeywordOn
0x18002ae2e  test    al, al
0x18002ae30  jz      loc_18002C194
0x18002ae36  mov     eax, [rsi+8]
0x18002ae39  lea     rdx, unk_18013E318
0x18002ae40  mov     dword ptr [rbp+120h+var_178], eax
0x18002ae43  mov     eax, [rsi+4]
0x18002ae46  mov     [rbp+120h+var_198], rax
0x18002ae4a  mov     eax, [rsi]
0x18002ae4c  mov     [rbp+120h+var_1A0], rax
0x18002ae50  lea     rax, [rbp+120h+var_178]
0x18002ae54  mov     [rsp+230h+var_1F0], rax
0x18002ae59  lea     rax, [rbp+120h+var_198]
0x18002ae5d  mov     [rsp+230h+var_1F8], rax
0x18002ae62  lea     rax, [rbp+120h+var_1A0]
0x18002ae66  mov     [rsp+230h+var_200], rax
0x18002ae6b  lea     rax, [rbp+120h+var_190]
0x18002ae6f  mov     [rsp+230h+var_208], rax
0x18002ae74  lea     rax, [rbp+120h+var_188]
0x18002ae78  mov     [rsp+230h+var_210], rax
0x18002ae7d  mov     [rbp+120h+var_190], rdi
0x18002ae81  mov     [rbp+120h+var_188], r8
0x18002ae85  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002ae8a  jmp     loc_18002C194
0x18002ae8f  mov     eax, [rsi]
0x18002ae91  lea     r8, aIwlanstateDsev; "IWlanState DSEvent PLSize %d IWLAN avai"...
0x18002ae98  mov     r9d, ecx
0x18002ae9b  mov     dword ptr [rsp+230h+var_210], eax
0x18002ae9f  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002aea6  mov     rdx, rdi; struct _GUID *
0x18002aea9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002aeae  mov     r8, r15
0x18002aeb1  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002aeba  mov     eax, cs:dword_180151040
0x18002aec0  add     r8, r15
0x18002aec3  cmp     eax, 5
0x18002aec6  jbe     short loc_18002AF16
0x18002aec8  mov     rdx, 200000000000h
0x18002aed2  lea     rcx, dword_180151040
0x18002aed9  call    _tlgKeywordOn
0x18002aede  test    al, al
0x18002aee0  jz      short loc_18002AF16
0x18002aee2  mov     eax, [rsi]
0x18002aee4  lea     rdx, word_18013E38A
0x18002aeeb  mov     dword ptr [rbp+120h+var_178], eax
0x18002aeee  lea     rax, [rbp+120h+var_178]
0x18002aef2  mov     [rsp+230h+var_200], rax
0x18002aef7  lea     rax, [rbp+120h+var_198]
0x18002aefb  mov     [rsp+230h+var_208], rax
0x18002af00  lea     rax, [rbp+120h+var_1A0]
0x18002af04  mov     [rsp+230h+var_210], rax
0x18002af09  mov     [rbp+120h+var_198], rdi
0x18002af0d  mov     [rbp+120h+var_1A0], r8
0x18002af11  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002af16  mov     rdx, rsi; enum WWAN_WINPHONE_IWLAN_STATE *
0x18002af19  mov     rcx, r13; this
0x18002af1c  call    ?HandleIWLANState@CWwanDataExecutorState@@IEAAXPEBW4WWAN_WINPHONE_IWLAN_STATE@@@Z; CWwanDataExecutorState::HandleIWLANState(WWAN_WINPHONE_IWLAN_STATE const *)
0x18002af21  jmp     loc_18002C194
0x18002af26  mov     eax, [rsi+0Ch]
0x18002af29  lea     r8, aModemdualsimca_2; "ModemDualSIMCap DSEvent PLSize %d fType"...
0x18002af30  mov     dword ptr [rsp+230h+var_1F8], eax
0x18002af34  mov     r9d, ecx
0x18002af37  mov     eax, [rsi+8]
0x18002af3a  lea     rcx, aCwwandataexecu_51; "CWwanDataExecutor::OnNdisNotification"
0x18002af41  mov     dword ptr [rsp+230h+var_200], eax
0x18002af45  mov     rdx, rdi; struct _GUID *
0x18002af48  mov     eax, [rsi+4]
0x18002af4b  mov     dword ptr [rsp+230h+var_208], eax
0x18002af4f  mov     eax, [rsi]
0x18002af51  mov     dword ptr [rsp+230h+var_210], eax
0x18002af55  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002af5a  mov     r8, r15
0x18002af5d  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002af66  mov     eax, cs:dword_180151040
0x18002af6c  add     r8, r15
0x18002af6f  cmp     eax, 5
0x18002af72  jbe     short loc_18002AFE0
0x18002af74  mov     rdx, 200000000000h
0x18002af7e  lea     rcx, dword_180151040
0x18002af85  call    _tlgKeywordOn
0x18002af8a  test    al, al
0x18002af8c  jz      short loc_18002AFE0
0x18002af8e  mov     eax, [rsi+8]
  ... truncated ...
```
