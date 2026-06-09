# CWwanDataExecutorState::OnNdisNotification(WWAN_EVENT const *,_GUID const *)

- ea: `0x18003cfd8`
- end: `0x18003f009`
- name: `?OnNdisNotification@CWwanDataExecutorState@@IEAAXPEBUWWAN_EVENT@@PEBU_GUID@@@Z`
- size: `8241`
- prototype: `void __fastcall(CWwanDataExecutorState *__hidden this, const struct WWAN_EVENT *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `75`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002aa58`

## callees

- `0x18000153c`
- `0x180002c18`
- `0x180002f80`
- `0x1800085d0`
- `0x1800094d0`
- `0x1800094dc`
- `0x1800094e8`
- `0x1800094f4`
- `0x18000f0f4`
- `0x18000f138`
- `0x18001150c`
- `0x180011a1c`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x18001375c`
- `0x180014154`
- `0x180014b5c`
- `0x180014c68`
- `0x180014f1c`
- `0x180015d6c`
- `0x180016c50`
- `0x180017640`
- `0x180018abc`
- `0x18001a27c`
- `0x18001e9b4`
- `0x18001e9f0`
- `0x180021a04`
- `0x180033a34`
- `0x180034bbc`
- `0x180034c38`
- `0x180035014`
- `0x180035470`
- `0x180035520`
- `0x1800358e4`
- `0x180035a8c`
- `0x180035b60`
- `0x180036cb4`
- `0x180036dbc`
- `0x180039b98`
- `0x18003a0d0`
- `0x18003a930`
- `0x18003aa14`
- `0x18003b218`
- `0x18003b344`
- `0x18003b55c`
- `0x18003b6e0`
- `0x18003bd88`
- `0x18003bf4c`
- `0x18003cfd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003daa5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003daa5`
- `WwanPrfl!WwanProfileGenerateXml` at `0x18003e97e`
- `WwanPrfl!WwanProfileGenerateXml` at `0x18003e97e`

## string_xrefs

- `0x18003da05`: `Failed (0x%x) to copy providerID from IMSI (%ws)`
- `0x18003d957`: `WwanEventCodeReadyInfo (type %d) ReadyState %d EmergencyMode %d`
- `0x18003db61`: `SupportedDataClassBitMap`
- `0x18003db7f`: `SupportedDataClassBitMap`
- `0x18003e25f`: `copying IMSI (%ws) to mbbReadyInfo`
- `0x18003e2ac`: `copying ICCID (%ws) to mbbReadyInfo`
- `0x18003e2fe`: `queried LTEAttach config already, skip`
- `0x18003e338`: `WwanEventCodeReadyInfo (type %d) size %d is less than expected %d`
- `0x18003d33f`: `WwanEventCodePacketService (type %d) handle 0x%p uStatus 0x%x uNwError 0x%x PSState %d DataClass 0x%x AvailClasses 0x%x FreqRange %d CurrentDataSubClass %d TAC %d Revision %d (ExecID %d)`
- `0x18003d38f`: `PacketService response (detachment reqId %d, reqHandle 0x%p), failure with result Code = 0x%x`
- `0x18003d3c7`: `PacketService response (detachment reqId %d, reqHandle 0x%p), success and PS is %s`
- `0x18003d462`: `PacketService response (attachment reqId %d, reqHandle 0x%p), failure with result Code = 0x%x`
- `0x18003d493`: `PacketService response (attachment reqId %d, reqHandle 0x%p), success and PS is %s`
- `0x18003d4c0`: `PacketService response, unwanted and ignored (DetachReqId %d, DetachReqHandle 0x%p, AttachReqId %d, AttachReqHandle 0x%x)`
- `0x18003d4f7`: `PacketService response/event, detached (been waiting for it so as to issue PS attach request)`
- `0x18003d624`: `WwanEventCodePacketService (type %d) size %d is less than expected %d`
- `0x18003eed0`: `NITZ Info Response(ReqHandle 0x%p) Success; Year %d Month %d Day %d Hour %d Minute %d Second %d TimeZoneOffsetMinutes %d DaylightSavingTimeOffsetMinutes %d DataClasses %d`
- `0x18003e792`: `WwanPmDeleteProfile %ws returned (%u)`
- `0x18003e9e6`: ` Added MBB profile for NW URSP rule (%s) created`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CWwanDataExecutorState::OnNdisNotification(
        CWwanDataExecutorState *this,
        const struct WWAN_EVENT *a2,
        struct _GUID *a3)
{
  __int64 v6; // r8
  int v7; // r15d
  unsigned int *v8; // rdx
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  void *v11; // r13
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  __int64 v22; // rcx
  unsigned int v23; // r12d
  __int64 v24; // rcx
  const char *v25; // rax
  int v26; // r8d
  int v27; // r8d
  int v28; // r8d
  int v29; // r8d
  const char *v30; // r9
  unsigned __int8 v31; // al
  unsigned int v32; // edx
  _QWORD *v33; // r12
  __int64 v34; // rcx
  unsigned int v35; // ecx
  __int64 v36; // rdx
  const wchar_t *v37; // rax
  const struct _GUID *v38; // r8
  struct CWwanManager *v39; // rax
  __int64 v40; // rbx
  struct CWwanManager *v41; // rax
  _QWORD *ExecutorFromInterfaceGuid; // rax
  CWwanFirstTimeModemReadyTelemetryEventContext *v43; // rax
  int v44; // ecx
  unsigned int v45; // r12d
  const struct _GUID *v46; // rdx
  const unsigned __int16 *v47; // r8
  unsigned int v48; // ecx
  __int64 v49; // rdx
  unsigned int v50; // r10d
  unsigned __int16 *v51; // rax
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  const char *v55; // r9
  const char *v56; // rax
  const char *v57; // r9
  int v58; // ecx
  int v59; // eax
  __int64 v60; // r9
  int v61; // ecx
  unsigned int v62; // eax
  const unsigned __int16 *v63; // r11
  StateSeparation *v64; // rbx
  unsigned int DWORD; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  int v69; // r13d
  unsigned int String; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  const unsigned __int16 *v74; // r12
  unsigned int v75; // eax
  _WORD *v76; // rax
  __int16 v77; // dx
  const unsigned __int16 *v78; // r12
  unsigned int v79; // eax
  _WORD *v80; // rax
  __int16 v81; // dx
  const unsigned __int16 *v82; // r12
  unsigned int v83; // eax
  __int64 v84; // r8
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  int v88; // ebx
  signed __int64 v89; // r8
  int v90; // ecx
  __int64 v91; // r8
  int v92; // r9d
  int v93; // ecx
  int v94; // ecx
  int v95; // ecx
  int v96; // ecx
  int v97; // ecx
  int v98; // ecx
  int v99; // ecx
  unsigned int *v100; // r9
  __int64 v101; // rcx
  unsigned __int64 v102; // rbx
  unsigned __int8 *v103; // r13
  unsigned int v104; // esi
  CWwanRoutePolicyManager *Instance; // rax
  unsigned int v106; // eax
  __int64 v107; // rcx
  void *v108; // rax
  unsigned int ProfileListByPurpose; // eax
  unsigned int v110; // esi
  StateSeparation *v111; // r13
  const wchar_t *v112; // rax
  const wchar_t *v113; // r9
  unsigned int v114; // esi
  struct CWwanRoutePolicyManager *v115; // r13
  __int64 v116; // rdx
  unsigned __int16 **i; // r13
  __int64 v118; // rax
  char *v119; // r8
  int v120; // ecx
  int v121; // edx
  StateSeparation *v122; // r8
  unsigned __int16 *v123; // rsi
  const unsigned __int16 *v124; // rax
  _QWORD *v125; // rax
  int v126; // eax
  __int64 v127; // rdx
  int v128; // r12d
  unsigned int v129; // eax
  __int64 v130; // rsi
  unsigned int v131; // r15d
  _DWORD *v132; // rax
  _DWORD *v133; // r14
  _DWORD *v134; // rbx
  char *v135; // rbx
  char *v136; // rbx
  char *v137; // rbx
  const struct _GUID *v138; // rdx
  const unsigned __int16 *v139; // r8
  CWwanModemProfileController *v140; // rcx
  __int64 v141; // r9
  struct _WWAN_NETWORK_BLACKLIST_INFO *v142; // [rsp+20h] [rbp-140h]
  int v143; // [rsp+20h] [rbp-140h]
  struct _WWAN_NETWORK_BLACKLIST_INFO *v144; // [rsp+20h] [rbp-140h]
  struct _WWAN_NETWORK_BLACKLIST_INFO *v145; // [rsp+20h] [rbp-140h]
  struct _WWAN_NETWORK_BLACKLIST_INFO *v146; // [rsp+20h] [rbp-140h]
  __int64 v147; // [rsp+28h] [rbp-138h]
  unsigned int v148[2]; // [rsp+28h] [rbp-138h]
  __int64 v149; // [rsp+28h] [rbp-138h]
  unsigned int v150[2]; // [rsp+28h] [rbp-138h]
  char v151[4]; // [rsp+E0h] [rbp-80h] BYREF
  unsigned int v152; // [rsp+E4h] [rbp-7Ch] BYREF
  unsigned int v153; // [rsp+E8h] [rbp-78h] BYREF
  unsigned int v154; // [rsp+ECh] [rbp-74h] BYREF
  unsigned __int64 IMSISize; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int v156; // [rsp+F8h] [rbp-68h] BYREF
  int v157; // [rsp+FCh] [rbp-64h] BYREF
  int v158; // [rsp+100h] [rbp-60h] BYREF
  int v159; // [rsp+104h] [rbp-5Ch] BYREF
  int v160; // [rsp+108h] [rbp-58h] BYREF
  int v161; // [rsp+10Ch] [rbp-54h] BYREF
  unsigned __int16 **v162; // [rsp+110h] [rbp-50h] BYREF
  unsigned __int64 v163; // [rsp+118h] [rbp-48h] BYREF
  __int64 v164; // [rsp+120h] [rbp-40h] BYREF
  signed __int64 v165; // [rsp+128h] [rbp-38h] BYREF
  const struct _GUID *v166; // [rsp+130h] [rbp-30h] BYREF
  __int64 v167; // [rsp+138h] [rbp-28h] BYREF
  __int64 v168; // [rsp+140h] [rbp-20h] BYREF
  __int64 v169; // [rsp+148h] [rbp-18h] BYREF
  __int64 v170; // [rsp+150h] [rbp-10h] BYREF
  __int64 v171; // [rsp+158h] [rbp-8h] BYREF
  __int64 v172; // [rsp+160h] [rbp+0h] BYREF
  __int64 v173; // [rsp+168h] [rbp+8h] BYREF
  __int64 v174; // [rsp+170h] [rbp+10h] BYREF
  __int64 v175; // [rsp+178h] [rbp+18h] BYREF
  unsigned __int16 **v176; // [rsp+180h] [rbp+20h] BYREF
  __int64 v177; // [rsp+188h] [rbp+28h] BYREF
  _BYTE v178[24]; // [rsp+190h] [rbp+30h] BYREF
  __int64 v179; // [rsp+1A8h] [rbp+48h]
  __int128 v180; // [rsp+1B0h] [rbp+50h] BYREF
  size_t MaxCount; // [rsp+1C0h] [rbp+60h]
  __int64 v182; // [rsp+1C8h] [rbp+68h]
  __int128 v183; // [rsp+1D0h] [rbp+70h] BYREF
  __int64 v184; // [rsp+1E0h] [rbp+80h]
  __int64 v185; // [rsp+1E8h] [rbp+88h]
  char v186[16]; // [rsp+1F0h] [rbp+90h] BYREF
  __int128 v187; // [rsp+200h] [rbp+A0h] BYREF
  __int64 v188; // [rsp+210h] [rbp+B0h]
  __int64 v189; // [rsp+218h] [rbp+B8h]
  __int128 v190; // [rsp+220h] [rbp+C0h] BYREF
  __int64 v191; // [rsp+230h] [rbp+D0h]
  __int64 v192; // [rsp+238h] [rbp+D8h]
  __int128 v193; // [rsp+240h] [rbp+E0h] BYREF
  __int64 v194; // [rsp+250h] [rbp+F0h]
  __int64 v195; // [rsp+258h] [rbp+F8h]
  __int128 v196; // [rsp+260h] [rbp+100h] BYREF
  __int64 v197; // [rsp+270h] [rbp+110h]
  __int64 v198; // [rsp+278h] [rbp+118h]
  StateSeparation *v199; // [rsp+280h] [rbp+120h] BYREF
  unsigned __int16 *v200[3]; // [rsp+288h] [rbp+128h] BYREF
  OLECHAR sz[48]; // [rsp+2A0h] [rbp+140h] BYREF

  v6 = 0;
  v7 = 1;
  if ( *(_DWORD *)a2 == 1 )
  {
    v8 = (unsigned int *)((char *)a2 + 32);
    v9 = *v8;
    v10 = (_QWORD *)((char *)a2 + 24);
    v11 = (void *)*((_QWORD *)a2 + 3);
  }
  else
  {
    v9 = 0;
    v11 = 0;
    v10 = (_QWORD *)((char *)a2 + 24);
    v8 = (unsigned int *)((char *)a2 + 32);
  }
  *(_OWORD *)((char *)this + 14600) = 0;
  *((_QWORD *)this + 1827) = 0;
  *((_DWORD *)this + 3650) = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 == 1 )
  {
    *((_DWORD *)this + 3651) = *((_DWORD *)a2 + 4);
    *((_QWORD *)this + 1826) = *v10;
    *((_DWORD *)this + 3654) = *v8;
  }
  v12 = *((_DWORD *)a2 + 1);
  if ( v12 > 54 )
  {
    v93 = v12 - 55;
    if ( !v93 )
    {
      CWwanModemProfileController::OnLteAttachStatusResponse((CWwanDataExecutorState *)((char *)this + 56), a2);
      return;
    }
    v94 = v93 - 1;
    if ( !v94 )
      goto LABEL_296;
    v95 = v94 - 3;
    if ( !v95 )
    {
      if ( *(_DWORD *)a2 != 1 || *((_DWORD *)a2 + 4) )
        v7 = 0;
      *((_DWORD *)this + 3585) = v7;
      return;
    }
    v96 = v95 - 2;
    if ( !v96 )
    {
      CWwanModemBulkConfigController::OnNdisNotification((CWwanDataExecutorState *)((char *)this + 16376), a2);
      return;
    }
    v97 = v96 - 7;
    if ( !v97 )
    {
      if ( *((_DWORD *)a2 + 22) < 0x24u )
      {
        v147 = 36;
        v139 = L"Invalid response data size detected for NITZ Info (ReqHandle 0x%p); size %d is less than expected %d";
      }
      else
      {
        if ( !v9 && (unsigned int)(*(_DWORD *)a2 - 1) <= 1 )
        {
          WwanLog::Info(
            "CWwanDataExecutorState::OnNdisNotification",
            a3,
            L"NITZ Info Response(ReqHandle 0x%p) Success; Year %d Month %d Day %d Hour %d Minute %d Second %d TimeZoneOffs"
             "etMinutes %d DaylightSavingTimeOffsetMinutes %d DataClasses %d",
            v11,
            *((_DWORD *)a2 + 23),
            *((_DWORD *)a2 + 24),
            *((_DWORD *)a2 + 25),
            *((_DWORD *)a2 + 26),
            *((_DWORD *)a2 + 27),
            *((_DWORD *)a2 + 28),
            *((_DWORD *)a2 + 29),
            *((_DWORD *)a2 + 30),
            *((_DWORD *)a2 + 31));
          CWwanDataExecutorState::OnNitzInfoReceived(this, (const struct WWAN_EVENT *)((char *)a2 + 92));
          return;
        }
        LODWORD(v147) = v9;
        v139 = L"NITZ Info Response(ReqHandle 0x%p) failure; PLSize %d uStatus 0x%x";
      }
      WwanLog::Error("CWwanDataExecutorState::OnNdisNotification", a3, v139, v11, *((_DWORD *)a2 + 22), v147);
      return;
    }
    v98 = v97 - 7;
    if ( !v98 )
    {
      if ( *(_DWORD *)a2 != 1 || *((_DWORD *)a2 + 4) )
      {
        WwanLog::Warning(
          "CWwanDataExecutorState::OnNdisNotification",
          (const struct _GUID *)((char *)this + 12536),
          L"EventCodeRegisterParamsState, unwanted and ignored (event type %d, setQueryType %d)",
          *(unsigned int *)a2,
          *((_DWORD *)a2 + 4));
        return;
      }
      if ( !*((_DWORD *)this + 3661) || *((_QWORD *)this + 1831) != *((_QWORD *)a2 + 3) )
      {
        WwanLog::Info(
          "CWwanDataExecutorState::OnNdisNotification",
          (const struct _GUID *)((char *)this + 12536),
          L"Reg params set response unexpected (pendingReqIdRegParams %d, pendingReqHandleRegParams 0x%p, RspHandle 0x%p). Ignored ");
        return;
      }
      v138 = (const struct _GUID *)((char *)this + 12536);
      if ( v9 )
        WwanLog::Error(
          "CWwanDataExecutorState::OnNdisNotification",
          v138,
          L"Reg params set failed with result 0x%x (pendingReqIdRegParams %d, pendingReqHandleRegParams 0x%p)",
          v9,
          *((_DWORD *)this + 3661),
          *((_QWORD *)this + 1831));
      else
        WwanLog::Info(
          "CWwanDataExecutorState::OnNdisNotification",
          v138,
          L"Reg params set successful (pendingReqIdRegParams %d, pendingReqHandleRegParams 0x%p)");
      *((_DWORD *)this + 3661) = 0;
      *((_QWORD *)this + 1831) = 0;
      v127 = 20;
LABEL_281:
      CWwanDataExecutorState::fsmEventHandler(this, v127);
      return;
    }
    v99 = v98 - 1;
    if ( !v99 )
    {
      if ( !*((_DWORD *)this + 3171) )
      {
        WwanLog::Warning(
          "CWwanDataExecutorState::OnNdisNotification",
          a3,
          L"Receive network params notif from a MBB device incapable of 5G SA Phase 2. Ignored");
        return;
      }
      v128 = 0;
      if ( *(_DWORD *)a2 == 1 )
      {
        wwan::unique_autoref_tx::unique_autoref_tx((wwan::unique_autoref_tx *)v200, *((void **)a2 + 3));
        if ( !v200[0] )
        {
          WwanLog::Error(
            "CWwanDataExecutorState::OnNdisNotification",
            a3,
            L"Unexpected result by referencing WwanTx from WwanEventCodeNetworkParamsState");
          wwan::unique_autoref_tx::~unique_autoref_tx((wwan::unique_autoref_tx *)v200);
          return;
        }
        v128 = *((_DWORD *)v200[0] + 13);
        wwan::unique_autoref_tx::~unique_autoref_tx((wwan::unique_autoref_tx *)v200);
      }
      v129 = CWwanNetworkParams::OnNetworkParamsReceived(
               *((CWwanNetworkParams **)this + 2098),
               *((_DWORD *)a2 + 22),
               (const unsigned __int8 *)a2 + 92);
      if ( v129 )
      {
        WwanLog::Error(
          "CWwanDataExecutorState::OnNdisNotification",
          a3,
          L"Malformed Network Parameters Message Received: Error (0x%x)",
          v129);
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        v130 = *((_QWORD *)this + 2098);
        v131 = 8
             * (((__int64)(*(_QWORD *)(v130 + 64) - *(_QWORD *)(v130 + 56)) >> 3)
              + 2
              * (((__int64)(*(_QWORD *)(v130 + 16) - *(_QWORD *)(v130 + 8)) >> 4)
               + ((__int64)(*(_QWORD *)(v130 + 40) - *(_QWORD *)(v130 + 32)) >> 4)
               + ((__int64)(*(_QWORD *)(v130 + 88) - *(_QWORD *)(v130 + 80)) >> 4)))
             + 104;
        v132 = (_DWORD *)WwanMemAlloc(v131);
        v133 = v132;
        if ( v132 )
        {
          v134 = v132 + 26;
          *v132 = v128;
          v132[2] = 24;
          v132[3] = (__int64)(*(_QWORD *)(v130 + 16) - *(_QWORD *)(v130 + 8)) >> 4;
          memmove_0(v132 + 26, *(const void **)(v130 + 8), *(_QWORD *)(v130 + 16) - *(_QWORD *)(v130 + 8));
          *((_QWORD *)v133 + 2) = 104;
          v135 = (char *)v134 + ((*(_QWORD *)(v130 + 16) - *(_QWORD *)(v130 + 8)) & 0xFFFFFFFFFFFFFFF0uLL);
          v133[8] = 24;
          v133[9] = (__int64)(*(_QWORD *)(v130 + 40) - *(_QWORD *)(v130 + 32)) >> 4;
          memmove_0(v135, *(const void **)(v130 + 32), *(_QWORD *)(v130 + 40) - *(_QWORD *)(v130 + 32));
          *((_QWORD *)v133 + 5) = v135 - (char *)v133;
          v136 = &v135[(*(_QWORD *)(v130 + 40) - *(_QWORD *)(v130 + 32)) & 0xFFFFFFFFFFFFFFF0uLL];
          v133[14] = 24;
          v133[15] = (__int64)(*(_QWORD *)(v130 + 88) - *(_QWORD *)(v130 + 80)) >> 4;
          memmove_0(v136, *(const void **)(v130 + 80), *(_QWORD *)(v130 + 88) - *(_QWORD *)(v130 + 80));
          *((_QWORD *)v133 + 8) = v136 - (char *)v133;
          v137 = &v136[(*(_QWORD *)(v130 + 88) - *(_QWORD *)(v130 + 80)) & 0xFFFFFFFFFFFFFFF0uLL];
          v133[20] = 25;
          v133[21] = (__int64)(*(_QWORD *)(v130 + 64) - *(_QWORD *)(v130 + 56)) >> 3;
          memmove_0(v137, *(const void **)(v130 + 56), *(_QWORD *)(v130 + 64) - *(_QWORD *)(v130 + 56));
          *((_QWORD *)v133 + 11) = v137 - (char *)v133;
          if ( v131 != (_DWORD)v137 + ((*(_DWORD *)(v130 + 64) - *(_DWORD *)(v130 + 56)) & 0xFFFFFFF8) - (_DWORD)v133 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          WwanNhNotificationDispatcherWithHeader(
            2u,
            0x6Fu,
            (const struct _GUID *)((char *)this + 12536),
            0,
            0,
            v131,
            v133);
          WwanMemFree(v133);
        }
      }
      return;
    }
    if ( v99 != 1 )
      return;
    if ( !*((_DWORD *)this + 3171) )
    {
      WwanLog::Warning(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"Receive UE policy notif from a MBB device incapable of 5G SA Phase 2. Ignored");
      return;
    }
    v45 = 24;
    if ( v9 )
    {
      WwanLog::Error(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"UePolicyState type %d Error (0x%x)",
        *(unsigned int *)a2,
        v9);
LABEL_260:
      v127 = v45;
      goto LABEL_281;
    }
    v100 = (unsigned int *)((char *)a2 + 92);
    if ( a2 == (const struct WWAN_EVENT *)-92LL || (v101 = *((unsigned int *)a2 + 22), (unsigned int)v101 < 8) )
    {
      WwanLog::Error(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"Invalid UePolicyState data (%p): total size %d");
      goto LABEL_260;
    }
    if ( *v100 != 8 || (v102 = *((unsigned int *)a2 + 24), v162 = (unsigned __int16 **)v102, v102 > v101 - 8) )
    {
      WwanLog::Error(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"Invalid offset or size in UePolicyState data: offset %d size %d total size %d",
        *v100,
        *((_DWORD *)a2 + 24),
        v101);
      goto LABEL_260;
    }
    v103 = (unsigned __int8 *)a2 + 100;
    if ( *((_QWORD *)this + 2097) && (v104 = *((_DWORD *)this + 4192)) != 0 )
    {
      if ( v104 == (_DWORD)v102 && !memcmp_0(*((const void **)this + 2097), v100 + 2, v104) )
      {
        WwanLog::Info(
          "CWwanDataExecutorState::OnNdisNotification",
          a3,
          L"Identical UE Policies are recieved (len %d). Ignored",
          v104);
        goto LABEL_260;
      }
      WwanLog::Verbose(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"Different UE Policies are recieved (len %d last len %d)",
        (unsigned int)v102,
        v104);
    }
    else
    {
      WwanLog::Verbose(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"first UE Policies are recieved (len %d last len %d last ptr %p)",
        (unsigned int)v102,
        *((_DWORD *)this + 4192),
        *((_QWORD *)this + 2097));
    }
    Instance = CWwanRoutePolicyManager::_GetInstance();
    v106 = CWwanRoutePolicyManager::OnUePoliciesReceived(Instance, (const unsigned __int16 *)this + 6476, v102, v103);
    if ( v106 )
    {
      WwanLog::Error(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"Malformed UE Policies Received: Error (0x%x)",
        v106);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      v107 = *((_QWORD *)this + 2097);
      if ( v107 )
      {
        WwanMemFree(v107);
        *((_QWORD *)this + 2097) = 0;
        *((_DWORD *)this + 4192) = 0;
      }
      if ( (_DWORD)v102 )
      {
        v108 = (void *)WwanMemAlloc(v102);
        *((_QWORD *)this + 2097) = v108;
        if ( v108 )
        {
          memcpy_0(v108, v103, v102);
          *((_DWORD *)this + 4192) = v102;
        }
      }
      v199 = 0;
      ProfileListByPurpose = WwanPmGetProfileListByPurpose((wchar_t *)this + 6476, 0, &v199);
      if ( ProfileListByPurpose )
      {
        WwanLog::Error(
          "CWwanDataExecutorState::OnNdisNotification",
          a3,
          L"failed to WwanPmGetProfileList(%u)",
          ProfileListByPurpose);
      }
      else
      {
        std::wstring::wstring(&v180, L"!!##URSPOTAProfile##");
        std::wstring::append(&v180, (char *)this + 12952);
        std::wstring::append(&v180, L"##");
        v110 = 0;
        v111 = v199;
        if ( *(_DWORD *)v199 )
        {
          do
          {
            v199 = (StateSeparation *)((char *)v111 + 516 * v110 + 4);
            v112 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v180);
            if ( !wcsncmp_0(v113, v112, (unsigned int)MaxCount) )
            {
              LODWORD(v144) = WwanPmDeleteProfile((char *)this + 12952, v199);
              WwanLog::Info(
                "CWwanDataExecutorState::OnNdisNotification",
                a3,
                L"WwanPmDeleteProfile %ws returned (%u)",
                v199,
                v144);
            }
            ++v110;
          }
          while ( v110 < *(_DWORD *)v111 );
          LODWORD(v102) = (_DWORD)v162;
        }
        std::wstring::_Tidy_deallocate(&v180);
      }
      v114 = 0;
      v152 = 0;
      v115 = CWwanRoutePolicyManager::_GetInstance();
      memset(v178, 0, sizeof(v178));
      v116 = (*((_QWORD *)v115 + 4) - *((_QWORD *)v115 + 3)) / 48LL;
      if ( v116 )
      {
        std::vector<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>>::_Buy_nonzero(v178, v116);
        v199 = (StateSeparation *)v178;
        *(_QWORD *)&v178[8] = std::_Uninitialized_copy<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>> *,std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>> *,std::allocator<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>>>(
                                *((_QWORD *)v115 + 3),
                                *((_QWORD *)v115 + 4),
                                *(_QWORD *)v178,
                                v178);
        v199 = 0;
        std::_Tidy_guard<std::vector<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>>>::~_Tidy_guard<std::vector<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>>>(&v199);
      }
      v162 = *(unsigned __int16 ***)&v178[8];
      for ( i = *(unsigned __int16 ***)v178; i != v162; i += 6 )
      {
        std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>(
          &v183,
          i);
        std::wstring::wstring(&v180, L"!!##URSPOTAProfile##");
        std::wstring::append(&v180, (char *)this + 12952);
        std::wstring::append(&v180, L"##");
        v118 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v183);
        v119 = (char *)this - v118 + 12952;
        do
        {
          v120 = *(unsigned __int16 *)&v119[v118];
          v121 = *(unsigned __int16 *)v118 - v120;
          if ( v121 )
            break;
          v118 += 2;
        }
        while ( v120 );
        if ( !v121 )
        {
          std::shared_ptr<ProfileHandler>::shared_ptr<ProfileHandler>(v200, v186, 0);
          LODWORD(IMSISize) = (_DWORD)v122;
          v199 = v122;
          v123 = v200[0];
          *((_DWORD *)v200[0] + 769) = 5;
          *((_DWORD *)v123 + 1157) = 3;
          StringCchPrintfW((unsigned __int16 *)&v199, 4u, L"%03d", v152);
          std::wstring::append(&v180, &v199);
          v124 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v180);
          StringCchCopyW(v123, 0x100u, v124);
          StringCchCopyW(v123 + 1556, 0x15u, (const unsigned __int16 *)this + 6476);
          v125 = v123 + 3160;
          if ( !*((_QWORD *)v123 + 790) )
          {
            WwanProfileGenerateXml(v123, 0, v123 + 3160, 0);
            v125 = v123 + 3160;
          }
          v126 = WwanPmSetProfile(
                   (int)v123 + 3112,
                   0,
                   *v125,
                   1,
                   0,
                   0,
                   0,
                   0,
                   0,
                   (enum WWAN_PROFILE_INVALID_REASON *)&IMSISize);
          if ( v126 )
          {
            LODWORD(v145) = v126;
            WwanLog::Error(
              "CWwanDataExecutorState::OnNdisNotification",
              a3,
              L"failed to WwanPmSetProfile for NW URSP rule (%s) 0x%x",
              v123,
              v145);
          }
          else
          {
            WwanLog::Info(
              "CWwanDataExecutorState::OnNdisNotification",
              a3,
              L" Added MBB profile for NW URSP rule (%s) created",
              v123);
          }
          WwanNhNotificationDispatcherWithHeader(2u, 0x71u, (const struct _GUID *)((char *)this + 12536), 0, 0, 0, 0);
          v114 = v152 + 1;
          v152 = v114;
          if ( v114 > 0x3E7 )
          {
            WwanLog::Error(
              "CWwanDataExecutorState::OnNdisNotification",
              a3,
              L"too many rules, only the first 1000 rules are processed");
            if ( v200[1] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v200[1]);
            std::wstring::_Tidy_deallocate(&v180);
            std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(&v183);
            break;
          }
          if ( v200[1] )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v200[1]);
        }
        std::wstring::_Tidy_deallocate(&v180);
        std::pair<std::wstring,std::shared_ptr<ProfileHolder>>::~pair<std::wstring,std::shared_ptr<ProfileHolder>>(&v183);
      }
      WwanNhNotificationDispatcherWithHeader(2u, 0x75u, (const struct _GUID *)((char *)this + 12536), 0, 0, 0, 0);
      LODWORD(v146) = v114;
      WwanLog::Info(
        "CWwanDataExecutorState::OnNdisNotification",
        a3,
        L"UE Policies (len %d) received with %d URSP rules",
        (unsigned int)v102,
        v146);
      std::vector<std::pair<std::wstring,std::shared_ptr<CWwanProfileWrapper>>>::_Tidy(v178);
    }
    goto LABEL_260;
  }
  if ( v12 == 54 )
  {
    CWwanModemProfileController::OnLteAttachConfigResponse((CWwanDataExecutorState *)((char *)this + 56), a2);
    return;
  }
  if ( !v12 )
  {
    if ( *((_DWORD *)a2 + 22) >= 0x160u )
    {
      StringCchCopyW((unsigned __int16 *)this + 6304, 0x12u, (const unsigned __int16 *)a2 + 100);
      return;
    }
    v149 = 352;
    v143 = *((_DWORD *)a2 + 22);
    v47 = L"WwanEventCodeDeviceCaps (type %d) size %d is less than                                    expected %d";
    v46 = 0;
    goto LABEL_87;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( !v14 )
    {
      v60 = *(unsigned int *)a2;
      if ( *((_DWORD *)a2 + 22) < 0x64u )
      {
        WwanLog::Error(
          "CWwanDataExecutorState::OnNdisNotification",
          0,
          L"WwanEventCodeReadyInfo (type %d) size %d is less than expected %d",
          v60,
          *((_DWORD *)a2 + 22),
          104);
        return;
      }
      WwanLog::Info(
        "CWwanDataExecutorState::OnNdisNotification",
        0,
        L"WwanEventCodeReadyInfo (type %d) ReadyState %d EmergencyMode %d",
        v60,
        *((_DWORD *)a2 + 23),
        *((_DWORD *)a2 + 24));
      if ( a3 )
      {
        if ( CServiceHandler::s_lLoggingRegistered >= 0 )
        {
          v61 = *((_DWORD *)a2 + 23);
          if ( v61 != *((_DWORD *)this + 3560)
            || *((_DWORD *)a2 + 24) != *((_DWORD *)this + 3561)
            || *((_DWORD *)this + 3585) )
          {
            v158 = *((_DWORD *)this + 3181);
            IMSISize = 0;
            v163 = 0;
            v200[0] = 0;
            LODWORD(v200[1]) = 0;
            WORD2(v200[1]) = 0;
            if ( *((_DWORD *)this + 3656) || v61 != 1 )
            {
              CWwanDataExecutorState::GetProviderIdFromIMSI(this, (unsigned __int16 (*)[7])v200);
              IMSISize = CWwanDataExecutorState::GetIMSISize(this);
            }
            else
            {
              v62 = StringCchCopyW((unsigned __int16 *)v200, 7u, (const unsigned __int16 *)a2 + 50);
              if ( (int)(v62 + 0x80000000) < 0 || v62 == -2147024774 )
              {
                StringCchLengthW(v63, 0x10u, &v163);
                IMSISize = v163;
              }
              else
              {
                WwanLog::Error(
                  "CWwanDataExecutorState::OnNdisNotification",
                  0,
                  L"Failed (0x%x) to copy providerID from IMSI (%ws)",
                  v62,
                  v63);
                LOWORD(v200[0]) = 0;
              }
            }
            v165 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
            v157 = 37;
            std::make_unique<StateSeparation,enum _REG_ROOT_PATH,0>(&v199, &v157);
            memset_0(sz, 0, 0x5Eu);
            StringFromGUID2(a3, sz, 47);
            v154 = 0;
            v153 = 0;
            v156 = 0;
            v152 = 0;
            v64 = v199;
            DWORD = StateSeparation::GetDWORD(v199, sz, L"DSDxType", &v154);
            if ( DWORD )
            {
              v150[0] = DWORD;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s DWORD property [%s] with error (%u)",
                sz,
                L"DSDxType",
                *(_QWORD *)v150);
              v154 = 0;
            }
            v66 = StateSeparation::GetDWORD(v64, sz, L"ActiveSIMSlotForDSSA", &v153);
            if ( v66 )
            {
              v150[0] = v66;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s DWORD property [%s] with error (%u)",
                sz,
                L"ActiveSIMSlotForDSSA",
                *(_QWORD *)v150);
              v153 = 0;
            }
            v67 = StateSeparation::GetDWORD(v64, sz, L"SupportedDataClassBitMap", &v156);
            if ( v67 )
            {
              v150[0] = v67;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s DWORD property [%s] with error (%u)",
                sz,
                L"SupportedDataClassBitMap",
                *(_QWORD *)v150);
              v156 = 0;
            }
            v68 = StateSeparation::GetDWORD(v64, sz, L"ModemOptionalCapabilityBitMap", &v152);
            if ( v68 )
            {
              v150[0] = v68;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s DWORD property [%s] with error (%u)",
                sz,
                L"ModemOptionalCapabilityBitMap",
                *(_QWORD *)v150);
              v152 = 0;
            }
            if ( v154 != 2 || (v69 = 1, v153 != 1) )
              v69 = 0;
            v180 = 0;
            MaxCount = 0;
            v182 = 7;
            LOWORD(v180) = 0;
            v183 = 0;
            v184 = 0;
            v185 = 7;
            LOWORD(v183) = 0;
            v196 = 0;
            v197 = 0;
            v198 = 7;
            LOWORD(v196) = 0;
            v193 = 0;
            v194 = 0;
            v195 = 7;
            LOWORD(v193) = 0;
            v190 = 0;
            v191 = 0;
            v192 = 7;
            LOWORD(v190) = 0;
            v187 = 0;
            v188 = 0;
            v189 = 7;
            LOWORD(v187) = 0;
            memset(v178, 0, sizeof(v178));
            v179 = 7;
            *(_WORD *)v178 = 0;
            String = StateSeparation::GetString(v64, sz, L"HWID", &v180);
            if ( String )
            {
              v150[0] = String;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                L"HWID",
                *(_QWORD *)v150);
              MaxCount = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v180) = 0;
            }
            v71 = StateSeparation::GetString(v64, sz, L"DriverName", &v183);
            if ( v71 )
            {
              v150[0] = v71;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                L"DriverName",
                *(_QWORD *)v150);
              v184 = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v183) = 0;
            }
            v72 = StateSeparation::GetString(v64, sz, L"Manufacturer", &v196);
            if ( v72 )
            {
              v150[0] = v72;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                L"Manufacturer",
                *(_QWORD *)v150);
              v197 = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v196) = 0;
            }
            v73 = StateSeparation::GetString(v64, sz, L"FirmwareVersion", &v193);
            if ( v73 )
            {
              v150[0] = v73;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                L"FirmwareVersion",
                *(_QWORD *)v150);
              v194 = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v193) = 0;
            }
            v74 = L"MCC1";
            if ( !v69 )
              v74 = L"MCC0";
            v75 = StateSeparation::GetString(v64, sz, v74, &v190);
            if ( v75 )
            {
              v150[0] = v75;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                v74,
                *(_QWORD *)v150);
              v191 = 0;
              v76 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v190);
              *v76 = v77;
            }
            v78 = L"MNC1";
            if ( !v69 )
              v78 = L"MNC0";
            v79 = StateSeparation::GetString(v64, sz, v78, &v187);
            if ( v79 )
            {
              v150[0] = v79;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                v78,
                *(_QWORD *)v150);
              v188 = 0;
              v80 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v187);
              *v80 = v81;
            }
            v82 = L"MobileOperatorInUse1";
            if ( !v69 )
              v82 = L"MobileOperatorInUse0";
            v83 = StateSeparation::GetString(v64, sz, v82, v178);
            if ( v83 )
            {
              v150[0] = v83;
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                0,
                L": Failed to get interface %s string property [%s] with error (%u)",
                sz,
                v82,
                *(_QWORD *)v150);
              *(_QWORD *)&v178[16] = 0;
              *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v178) = 0;
            }
            if ( (unsigned int)dword_180151040 > 5
              && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x800000000000LL, v84) )
            {
              v157 = IMSISize;
              v159 = *((_DWORD *)a2 + 47);
              v151[0] = *((_BYTE *)a2 + 174);
              v160 = *((_DWORD *)a2 + 24);
              v176 = v200;
              v161 = *((_DWORD *)a2 + 23);
              LODWORD(v163) = *((_DWORD *)a2 + 6);
              LODWORD(IMSISize) = *((_DWORD *)this + 3143);
              v177 = 16779264;
              v167 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v187);
              v168 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v190);
              v169 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v178);
              v170 = v156;
              v171 = v152;
              v172 = v153;
              v173 = v154;
              v174 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v193);
              v175 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v196);
              v164 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v183);
              v166 = (const struct _GUID *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v180);
              v162 = (unsigned __int16 **)a3;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v85,
                (unsigned int)byte_18013EEDD,
                v86,
                v87,
                (__int64)&v165,
                (__int64)&v162,
                (__int64)&v166,
                (__int64)&v164,
                (__int64)&v175,
                (__int64)&v174,
                (__int64)&v173,
                (__int64)&v172,
                (__int64)&v171,
                (__int64)&v170,
                (__int64)&v169,
                (__int64)&v168,
                (__int64)&v167,
                (__int64)&v177,
                (__int64)&IMSISize,
                (__int64)&v158,
                (__int64)&v163,
                (__int64)&v161,
                (__int64)&v176,
                (__int64)&v160,
                (__int64)v151,
                (__int64)&v159,
                (__int64)&v157);
            }
            std::wstring::_Tidy_deallocate(v178);
            std::wstring::_Tidy_deallocate(&v187);
            std::wstring::_Tidy_deallocate(&v190);
            std::wstring::_Tidy_deallocate(&v193);
            std::wstring::_Tidy_deallocate(&v196);
            std::wstring::_Tidy_deallocate(&v183);
            std::wstring::_Tidy_deallocate(&v180);
            std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v199);
          }
        }
      }
      *((_OWORD *)this + 890) = *(_OWORD *)((char *)a2 + 92);
      *((_OWORD *)this + 891) = *(_OWORD *)((char *)a2 + 108);
      *((_OWORD *)this + 892) = *(_OWORD *)((char *)a2 + 124);
      *((_OWORD *)this + 893) = *(_OWORD *)((char *)a2 + 140);
      *((_OWORD *)this + 894) = *(_OWORD *)((char *)a2 + 156);
      *((_OWORD *)this + 895) = *(_OWORD *)((char *)a2 + 172);
      *((_QWORD *)this + 1792) = *((unsigned int *)a2 + 47);
      if ( *((_DWORD *)this + 3560) <= 1u )
      {
        if ( !*((_WORD *)this + 7124) && *((_DWORD *)this + 3259) )
        {
          WwanLog::Info(
            "CWwanDataExecutorState::OnNdisNotification",
            0,
            L"copying IMSI (%ws) to mbbReadyInfo",
            (char *)this + 13040);
          StringCchCopyW((unsigned __int16 *)this + 7124, 0x10u, (const unsigned __int16 *)this + 6520);
        }
        if ( *((_DWORD *)this + 3560) <= 1u && !*((_WORD *)this + 7140) && *((_WORD *)this + 6476) )
        {
          WwanLog::Info(
            "CWwanDataExecutorState::OnNdisNotification",
            0,
            L"copying ICCID (%ws) to mbbReadyInfo",
            (char *)this + 12952);
          StringCchCopyW((unsigned __int16 *)this + 7140, 0x15u, (const unsigned __int16 *)this + 6476);
        }
      }
      if ( (*((_BYTE *)this + 12676) & 1) != 0 )
      {
        if ( *((_DWORD *)this + 3560) == 1 )
        {
          if ( *((_BYTE *)this + 72) )
          {
            WwanLog::Info("CWwanDataExecutorState::OnNdisNotification", 0, L"queried LTEAttach config already, skip");
          }
          else
          {
            CWwanModemProfileController::SendMbbLteAttachConfigQuery((CWwanDataExecutorState *)((char *)this + 56));
            CWwanModemProfileController::SendMbbLteAttachStatusQuery((CWwanDataExecutorState *)((char *)this + 56));
          }
        }
        else
        {
          *((_BYTE *)this + 72) = 0;
          *((_QWORD *)this + 10) = 0;
          *((_QWORD *)this + 11) = 0;
        }
      }
      v45 = 5;
      goto LABEL_260;
    }
    v15 = v14 - 4;
    if ( !v15 )
    {
      if ( *(_DWORD *)a2 == 2 || !*((_DWORD *)a2 + 8) )
        CWwanModemProfileController::OnHomeProvider(
          (CWwanDataExecutorState *)((char *)this + 56),
          (const struct WWAN_EVENT *)((char *)a2 + 92));
      else
        WwanLog::Error("CWwanDataExecutorState::OnNdisNotification", 0, L"Error in home provider received");
      return;
    }
    v16 = v15 - 3;
    if ( !v16 )
    {
      v48 = *((_DWORD *)a2 + 22);
      v49 = v48 - 8;
      if ( v48 <= 8 )
        v49 = 0;
      if ( (unsigned int)v49 < 0xC4 )
      {
        WwanLog::Error(
          "CWwanDataExecutorState::OnNdisNotification",
          0,
          L"WwanEventCodeRegisterState (type %d) size %d is less than the minimun %d (ExecID %d)",
          *(unsigned int *)a2,
          v49,
          196,
          *((_DWORD *)this + 3143));
        return;
      }
      if ( a3 )
      {
        if ( (byte_1801528C4 & 4) != 0 )
          McTemplateU0jq_EventWriteTransfer(196, RegistrationState, a3, *((unsigned int *)a2 + 26));
        v50 = *((_DWORD *)a2 + 26);
        if ( v50 != *((_DWORD *)this + 3587) || *((_DWORD *)a2 + 75) != *((_DWORD *)this + 3636) )
          goto LABEL_100;
        v51 = (unsigned __int16 *)((char *)a2 + 126);
        do
        {
          v49 = *(unsigned __int16 *)((char *)v51
                                    + (CWwanDataExecutorState *)((char *)this + 14370)
                                    - (const struct WWAN_EVENT *)((char *)a2 + 126));
          v52 = *v51 - (_DWORD)v49;
          if ( v52 )
            break;
          ++v51;
        }
        while ( (_DWORD)v49 );
        v6 = 0;
        if ( v52 )
        {
LABEL_100:
          v53 = *((_DWORD *)a2 + 75);
          if ( v53 )
          {
            v54 = v53 - 1;
            if ( v54 )
            {
              if ( v54 == 1 )
                v55 = "CDMA";
              else
                v55 = "UndefinedError";
            }
            else
            {
              v55 = "GSM";
            }
          }
          else
          {
            v55 = "Unknown";
          }
          *(_DWORD *)v178 = 5;
          *(struct _GUID *)&v178[4] = *a3;
          *(_DWORD *)&v178[20] = 243;
          v56 = (const char *)EnumToString(v50, v49, v6, v55);
          NetworkingTriageScenario::GetConnected::CellularRegistrationEvent(
            (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v178,
            (const unsigned __int16 *)a2 + 63,
            v56,
            v57);
        }
      }
      v58 = *((_DWORD *)a2 + 25);
      *((_DWORD *)this + 3556) = *((_DWORD *)a2 + 8);
      *((_DWORD *)this + 3557) = v58;
      *(_OWORD *)((char *)this + 14344) = *(_OWORD *)((char *)a2 + 100);
      *(_OWORD *)((char *)this + 14360) = *(_OWORD *)((char *)a2 + 116);
      *(_OWORD *)((char *)this + 14376) = *(_OWORD *)((char *)a2 + 132);
      *(_OWORD *)((char *)this + 14392) = *(_OWORD *)((char *)a2 + 148);
      *(_OWORD *)((char *)this + 14408) = *(_OWORD *)((char *)a2 + 164);
      *(_OWORD *)((char *)this + 14424) = *(_OWORD *)((char *)a2 + 180);
      *(_OWORD *)((char *)this + 14440) = *(_OWORD *)((char *)a2 + 196);
      *(_OWORD *)((char *)this + 14456) = *(_OWORD *)((char *)a2 + 212);
      *(_OWORD *)((char *)this + 14472) = *(_OWORD *)((char *)a2 + 228);
      *(_OWORD *)((char *)this + 14488) = *(_OWORD *)((char *)a2 + 244);
      *(_OWORD *)((char *)this + 14504) = *(_OWORD *)((char *)a2 + 260);
      *(_OWORD *)((char *)this + 14520) = *(_OWORD *)((char *)a2 + 276);
      *((_DWORD *)this + 3634) = *((_DWORD *)a2 + 73);
      if ( *((_BYTE *)a2 + 93) == 1 || *((_DWORD *)a2 + 22) < 0xCCu )
      {
        *(_QWORD *)((char *)this + 14540) = 0;
        *((_DWORD *)this + 3637) = 0;
      }
      else
      {
        *((_DWORD *)this + 3635) = *((_DWORD *)a2 + 74);
        *((_DWORD *)this + 3636) = *((_DWORD *)a2 + 75);
        if ( *((_BYTE *)a2 + 93) < 4u || *((_DWORD *)a2 + 22) < 0xD0u )
          v59 = 0;
        else
          v59 = *((_DWORD *)a2 + 76);
        *((_DWORD *)this + 3637) = v59;
      }
      WwanLog::Info(
        "CWwanDataExecutorState::OnNdisNotification",
        0,
        L"WwanEventCodeRegisterState (type %d) uStatus 0x%x uNwError 0x%x State %d Mode %d CellClass %d ProviderID [%s] Pr"
         "oviderName [%s] RoamingText [%s] (HdrRev %d dataSize %d) (ExecID %d)",
        *(unsigned int *)a2,
        v9,
        *((_DWORD *)a2 + 25),
        *((_DWORD *)a2 + 26),
        *((_DWORD *)a2 + 27),
        *((_DWORD *)this + 3636),
        (char *)a2 + 112,
        (char *)a2 + 126,
        (char *)a2 + 168,
        *((unsigned __int8 *)a2 + 93),
        *((_DWORD *)a2 + 22),
        *((_DWORD *)this + 3143));
      v45 = 6;
      CWwanDataExecutorState::UpdateiWLANAvailability(this);
      goto LABEL_260;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 3;
      if ( v18 )
      {
        v19 = v18 - 37;
        if ( v19 )
        {
          if ( v19 == 3 )
          {
            if ( *((_DWORD *)a2 + 22) < 0xCu )
            {
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                a3,
                L"Invalid response data size detected for BlacklistedMCCMNC Response(ReqHandle 0x%p)",
                v11);
            }
            else if ( (unsigned int)(*(_DWORD *)a2 - 1) <= 1 )
            {
              LODWORD(v142) = *((_DWORD *)a2 + 22);
              if ( v9 )
                WwanLog::Error(
                  "CWwanDataExecutorState::OnNdisNotification",
                  a3,
                  L"BlacklistedMCCMNC Response(ReqHandle 0x%p) failure; PLSize %d uStatus 0x%x",
                  v11);
              else
                WwanLog::Info(
                  "CWwanDataExecutorState::OnNdisNotification",
                  a3,
                  L"BlacklistedMCCMNC Response(ReqHandle 0x%p) Success; PLSize %d BlacklistState %d",
                  v11);
              CWwanModemProfileController::HandleBlacklistMCCMNCResponse(
                (CWwanDataExecutorState *)((char *)this + 56),
                v11,
                v20,
                v21,
                v142);
            }
          }
        }
        else if ( *(_DWORD *)a2 != 1 || *((_DWORD *)a2 + 4) )
        {
          CWwanDataExecutorState::OnPsMediaPrefUpdate(this, a2);
        }
        else
        {
          CWwanDataExecutorState::OnPsMediaPrefSetResponse(this, a2);
        }
        return;
      }
LABEL_296:
      v140 = (CWwanDataExecutorState *)((char *)this + 56);
      if ( *(_DWORD *)a2 == 2 )
      {
        CWwanModemProfileController::OnProvisionedContextsV1Indication(v140, a2);
      }
      else if ( *((_DWORD *)a2 + 4) )
      {
        v141 = *((_QWORD *)a2 + 3);
        if ( *((_QWORD *)this + 45) == v141 )
        {
          CWwanModemProfileController::OnProvisionedContextsQueryV1Response(v140, a2);
        }
        else if ( *((_QWORD *)this + 1548) == v141 )
        {
          CWwanModemProfileController::OnProvisionedContextsQueryV2Response(v140, a2);
        }
        else
        {
          WwanLog::Error(
            "CWwanModemProfileController::OnProvisionedContextsQueryResponse",
            0,
            L"unexpected query response (0x%p)",
            v141);
        }
      }
      else if ( *((_QWORD *)this + 46) == *((_QWORD *)a2 + 3) )
      {
        CWwanModemProfileController::OnProvisionedContextsSetV1Response(v140, a2);
      }
      else
      {
        CWwanModemProfileController::OnProvisionedContextsSetV2Response(v140, a2);
      }
      return;
    }
    v22 = *((unsigned int *)a2 + 22);
    v23 = v22 - 8;
    if ( (unsigned int)v22 <= 8 )
      v23 = 0;
    if ( v23 >= 0x10 )
    {
      if ( a3 )
      {
        if ( (byte_1801528C4 & 8) != 0 )
          McTemplateU0jq_EventWriteTransfer(v22, PSState, a3, *((unsigned int *)a2 + 26));
        v24 = *((unsigned int *)a2 + 28);
        if ( *((_DWORD *)a2 + 26) != *((_DWORD *)this + 3639) || (_DWORD)v24 != *((_DWORD *)this + 3641) )
        {
          v25 = (const char *)CurrentDataClassToString(v24, *((unsigned int *)this + 3636));
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              v28 = v27 - 1;
              if ( v28 )
              {
                v29 = v28 - 1;
                if ( v29 )
                {
                  if ( v29 == 1 )
                    v30 = "Detached";
                  else
                    v30 = "UndefinedError";
                }
                else
                {
                  v30 = "Detaching";
                }
              }
              else
              {
                v30 = "Attached";
              }
            }
            else
            {
              v30 = "Attaching";
            }
          }
          else
          {
            v30 = "Unknown";
          }
          *(_DWORD *)v178 = 5;
          *(struct _GUID *)&v178[4] = *a3;
          *(_DWORD *)&v178[20] = 243;
          NetworkingTriageScenario::GetConnected::CellularPacketServiceEvent(
            (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)v178,
            v30,
            v25);
        }
        LODWORD(v6) = 0;
      }
      *(_OWORD *)((char *)this + 14552) = *(_OWORD *)((char *)a2 + 100);
      v31 = *((_BYTE *)a2 + 93);
      if ( v31 < 3u )
      {
        if ( v31 < 2u )
          goto LABEL_56;
      }
      else if ( v23 >= 0x20 )
      {
        v32 = *((_DWORD *)a2 + 29);
        *((_DWORD *)this + 3642) = v32;
        LODWORD(v6) = *((_DWORD *)a2 + 30);
        *((_DWORD *)this + 3643) = v6;
        *((_QWORD *)this + 1822) = *(_QWORD *)((char *)a2 + 124);
        if ( v23 >= 0x24 )
          *((_DWORD *)this + 3646) = *((_DWORD *)a2 + 33);
        goto LABEL_58;
      }
      if ( v23 >= 0x14 )
      {
        v32 = *((_DWORD *)a2 + 29);
        *((_QWORD *)this + 1821) = v32;
LABEL_57:
        *((_QWORD *)this + 1822) = 0;
LABEL_58:
        v33 = (_QWORD *)((char *)a2 + 24);
        WwanLog::Info(
          "CWwanDataExecutorState::OnNdisNotification",
          (const struct _GUID *)((char *)this + 12536),
          L"WwanEventCodePacketService (type %d) handle 0x%p uStatus 0x%x uNwError 0x%x PSState %d DataClass 0x%x AvailCla"
           "sses 0x%x FreqRange %d CurrentDataSubClass %d TAC %d Revision %d (ExecID %d)",
          *(unsigned int *)a2,
          *((_QWORD *)a2 + 3),
          v9,
          *((_DWORD *)a2 + 25),
          *((_DWORD *)a2 + 26),
          *((_DWORD *)a2 + 28),
          *((_DWORD *)a2 + 27),
          v32,
          v6,
          *((_DWORD *)this + 3645),
          *((unsigned __int8 *)a2 + 93),
          *((_DWORD *)this + 3143));
        if ( *(_DWORD *)a2 == 1 )
        {
          if ( *((_DWORD *)this + 3668) && *((_QWORD *)this + 1835) == *v33 )
          {
            if ( v9 )
              WwanLog::Error(
                "CWwanDataExecutorState::OnNdisNotification",
                (const struct _GUID *)((char *)this + 12536),
                L"PacketService response (detachment reqId %d, reqHandle 0x%p), failure with result Code = 0x%x");
            else
              WwanLog::Info(
                "CWwanDataExecutorState::OnNdisNotification",
                (const struct _GUID *)((char *)this + 12536),
                L"PacketService response (detachment reqId %d, reqHandle 0x%p), success and PS is %s");
            *((_QWORD *)this + 1835) = 0;
            *((_DWORD *)this + 3668) = 0;
            if ( *((_DWORD *)a2 + 26) == 4 )
            {
              CWwanDataExecutorState::StopWwanTimer(v34, (char *)this + 16920, 1);
              *((_DWORD *)this + 3672) = 0;
              CWwanDataExecutorState::SendMbbPsAttachDetachReq(
                this,
                1,
                (unsigned int *)this + 3664,
                (void **)this + 1833);
            }
            else
            {
              *((_DWORD *)this + 3672) = 1;
            }
          }
          else
          {
            v35 = *((_DWORD *)this + 3664);
            if ( v35 && (v36 = *((_QWORD *)this + 1833), v36 == *v33) )
            {
              if ( v9 )
              {
                v148[0] = v9;
                WwanLog::Error(
                  "CWwanDataExecutorState::OnNdisNotification",
                  (const struct _GUID *)((char *)this + 12536),
                  L"PacketService response (attachment reqId %d, reqHandle 0x%p), failure with result Code = 0x%x",
                  v35,
                  v36,
                  *(_QWORD *)v148);
              }
              else
              {
                v37 = L"attached";
                if ( *((_DWORD *)a2 + 26) != 2 )
                  v37 = L"not yet attached";
                WwanLog::Info(
                  "CWwanDataExecutorState::OnNdisNotification",
                  (const struct _GUID *)((char *)this + 12536),
                  L"PacketService response (attachment reqId %d, reqHandle 0x%p), success and PS is %s",
                  v35,
                  v36,
                  v37);
              }
            }
            else
            {
              WwanLog::Info(
                "CWwanDataExecutorState::OnNdisNotification",
                (const struct _GUID *)((char *)this + 12536),
                L"PacketService response, unwanted and ignored (DetachReqId %d, DetachReqHandle 0x%p, AttachReqId %d, Atta"
                 "chReqHandle 0x%x)");
            }
          }
        }
        if ( *((_DWORD *)this + 3672) && *((_DWORD *)a2 + 26) == 4 )
        {
          CWwanDataExecutorState::StopWwanTimer(v34, (char *)this + 16920, 1);
          WwanLog::Info(
            "CWwanDataExecutorState::OnNdisNotification",
            (const struct _GUID *)((char *)this + 12536),
            L"PacketService response/event, detached (been waiting for it so as to issue PS attach request)");
          *((_DWORD *)this + 3672) = 0;
          CWwanDataExecutorState::SendMbbPsAttachDetachReq(this, 1, (unsigned int *)this + 3664, (void **)this + 1833);
        }
        v38 = (const struct _GUID *)((char *)this + 12536);
        if ( *((_DWORD *)a2 + 26) == 2 )
        {
          WwanNhNotificationDispatcherWithHeader(2u, 8u, v38, 0, 0, 4u, (char *)a2 + 112);
          v39 = CWwanManager::GetInstance();
          v40 = *(_QWORD *)CWwanManager::GetExecutorFromInterfaceGuid(v39, v200, (char *)this + 12536);
          if ( v200[1] )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v200[1]);
          if ( v40 )
          {
            v41 = CWwanManager::GetInstance();
            ExecutorFromInterfaceGuid = (_QWORD *)CWwanManager::GetExecutorFromInterfaceGuid(
                                                    v41,
                                                    v200,
                                                    (char *)this + 12536);
            v43 = (CWwanFirstTimeModemReadyTelemetryEventContext *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ExecutorFromInterfaceGuid + 608LL))(*ExecutorFromInterfaceGuid);
            CWwanFirstTimeModemReadyTelemetryEventContext::Emit(v43, 1);
            if ( v200[1] )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v200[1]);
          }
        }
        else
        {
          WwanNhNotificationDispatcherWithHeader(2u, 9u, v38, 0, 0, 0x24u, (char *)this + 14552);
        }
        v44 = *((_DWORD *)a2 + 25);
        *((_DWORD *)this + 3558) = *((_DWORD *)a2 + 8);
        *((_DWORD *)this + 3559) = v44;
        v45 = 7;
        goto LABEL_260;
      }
LABEL_56:
      *((_QWORD *)this + 1821) = 0;
      v32 = 0;
      goto LABEL_57;
    }
    v46 = (const struct _GUID *)((char *)this + 12536);
    v149 = 44;
    v143 = *((_DWORD *)a2 + 22);
    v47 = L"WwanEventCodePacketService (type %d) size %d is less than expected %d";
LABEL_87:
    WwanLog::Error("CWwanDataExecutorState::OnNdisNotification", v46, v47, *(unsigned int *)a2, v143, v149);
    return;
  }
  if ( *((_DWORD *)a2 + 22) >= 0x10u )
  {
    if ( a3
      && CServiceHandler::s_lLoggingRegistered >= 0
      && (*((_DWORD *)a2 + 25) != *((_DWORD *)this + 3647) || *((_DWORD *)a2 + 26) != *((_DWORD *)this + 3648)) )
    {
      v88 = *((_DWORD *)this + 3181);
      v200[0] = 0;
      LODWORD(v200[1]) = 0;
      WORD2(v200[1]) = 0;
      CWwanDataExecutorState::GetProviderIdFromIMSI(this, (unsigned __int16 (*)[7])v200);
      v89 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL, v89) )
        {
          LODWORD(IMSISize) = *((_DWORD *)a2 + 26);
          LODWORD(v163) = *((_DWORD *)a2 + 25);
          v161 = *((_DWORD *)a2 + 24);
          v160 = *((_DWORD *)a2 + 6);
          v162 = v200;
          v159 = v88;
          v166 = a3;
          v164 = v91;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v90,
            (unsigned int)qword_18013EAF0,
            v91,
            v92,
            (__int64)&v164,
            (__int64)&v166,
            (__int64)&v159,
            (__int64)&v162,
            (__int64)&v160,
            (__int64)&v161,
            (__int64)&v163,
            (__int64)&IMSISize);
        }
      }
    }
    *(_QWORD *)((char *)this + 14588) = *(_QWORD *)((char *)a2 + 100);
  }
}

```

## disassembly

```asm
0x18003cfd8  mov     [rsp-8+arg_18], rbx
0x18003cfdd  push    rbp
0x18003cfde  push    rsi
0x18003cfdf  push    rdi
0x18003cfe0  push    r12
0x18003cfe2  push    r13
0x18003cfe4  push    r14
0x18003cfe6  push    r15
0x18003cfe8  lea     rbp, [rsp-1B0h]
0x18003cff0  sub     rsp, 310h
0x18003cff7  mov     rax, cs:__security_cookie
0x18003cffe  xor     rax, rsp
0x18003d001  mov     [rbp+1E0h+var_40], rax
0x18003d008  mov     r14, r8
0x18003d00b  mov     rsi, rdx
0x18003d00e  mov     rdi, rcx
0x18003d011  xor     r8d, r8d
0x18003d014  lea     r15d, [r8+1]
0x18003d018  cmp     [rdx], r15d
0x18003d01b  jnz     short loc_18003D02C
0x18003d01d  add     rdx, 20h ; ' '
0x18003d021  mov     ebx, [rdx]
0x18003d023  lea     rcx, [rsi+18h]
0x18003d027  mov     r13, [rcx]
0x18003d02a  jmp     short loc_18003D03A
0x18003d02c  mov     ebx, r8d
0x18003d02f  mov     r13, r8
0x18003d032  lea     rcx, [rdx+18h]
0x18003d036  add     rdx, 20h ; ' '
0x18003d03a  xorps   xmm0, xmm0
0x18003d03d  xor     eax, eax
0x18003d03f  movups  xmmword ptr [rdi+3908h], xmm0
0x18003d046  mov     [rdi+3918h], rax
0x18003d04d  mov     eax, [rsi]
0x18003d04f  mov     [rdi+3908h], eax
0x18003d055  cmp     [rsi], r15d
0x18003d058  jnz     short loc_18003D075
0x18003d05a  mov     eax, [rsi+10h]
0x18003d05d  mov     [rdi+390Ch], eax
0x18003d063  mov     rax, [rcx]
0x18003d066  mov     [rdi+3910h], rax
0x18003d06d  mov     eax, [rdx]
0x18003d06f  mov     [rdi+3918h], eax
0x18003d075  mov     ecx, [rsi+4]
0x18003d078  cmp     ecx, 36h ; '6'
0x18003d07b  jg      loc_18003E4C8
0x18003d081  jz      loc_18003E4B7
0x18003d087  test    ecx, ecx
0x18003d089  jz      loc_18003E477
0x18003d08f  sub     ecx, r15d
0x18003d092  jz      loc_18003E344
0x18003d098  sub     ecx, r15d
0x18003d09b  jz      loc_18003D931
0x18003d0a1  sub     ecx, 4
0x18003d0a4  jz      loc_18003D8FA
0x18003d0aa  sub     ecx, 3
0x18003d0ad  jz      loc_18003D63F
0x18003d0b3  sub     ecx, r15d
0x18003d0b6  jz      loc_18003D18C
0x18003d0bc  sub     ecx, 3
0x18003d0bf  jz      loc_18003EF5D
0x18003d0c5  sub     ecx, 25h ; '%'
0x18003d0c8  jz      loc_18003D161
0x18003d0ce  cmp     ecx, 3
0x18003d0d1  jnz     loc_18003EFDF
0x18003d0d7  mov     ecx, [rsi+58h]
0x18003d0da  cmp     ecx, 0Ch
0x18003d0dd  jb      short loc_18003D143
0x18003d0df  mov     eax, [rsi]
0x18003d0e1  sub     eax, r15d
0x18003d0e4  cmp     eax, r15d
0x18003d0e7  ja      loc_18003EFDF
0x18003d0ed  mov     r9, r13
0x18003d0f0  mov     rdx, r14; struct _GUID *
0x18003d0f3  test    ebx, ebx
0x18003d0f5  jnz     short loc_18003D117
0x18003d0f7  mov     eax, [rsi+5Ch]
0x18003d0fa  mov     [rsp+340h+var_318], eax
0x18003d0fe  mov     dword ptr [rsp+340h+var_320], ecx
0x18003d102  lea     r8, aBlacklistedmcc; "BlacklistedMCCMNC Response(ReqHandle 0x"...
0x18003d109  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d110  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003d115  jmp     short loc_18003D132
0x18003d117  mov     [rsp+340h+var_318], ebx
0x18003d11b  mov     dword ptr [rsp+340h+var_320], ecx; struct _WWAN_NETWORK_BLACKLIST_INFO *
0x18003d11f  lea     r8, aBlacklistedmcc_1; "BlacklistedMCCMNC Response(ReqHandle 0x"...
0x18003d126  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d12d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003d132  lea     rcx, [rdi+38h]; this
0x18003d136  mov     rdx, r13; void *
0x18003d139  call    ?HandleBlacklistMCCMNCResponse@CWwanModemProfileController@@IEAAXQEAXKKPEBU_WWAN_NETWORK_BLACKLIST_INFO@@@Z; CWwanModemProfileController::HandleBlacklistMCCMNCResponse(void * const,ulong,ulong,_WWAN_NETWORK_BLACKLIST_INFO const *)
0x18003d13e  jmp     loc_18003EFDF
0x18003d143  mov     r9, r13
0x18003d146  lea     r8, aInvalidRespons_0; "Invalid response data size detected for"...
0x18003d14d  mov     rdx, r14; struct _GUID *
0x18003d150  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d157  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003d15c  jmp     loc_18003EFDF
0x18003d161  cmp     [rsi], r15d
0x18003d164  jnz     short loc_18003D17C
0x18003d166  cmp     [rsi+10h], r8d
0x18003d16a  jnz     short loc_18003D17C
0x18003d16c  mov     rdx, rsi; struct WWAN_EVENT *
0x18003d16f  mov     rcx, rdi; this
0x18003d172  call    ?OnPsMediaPrefSetResponse@CWwanDataExecutorState@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanDataExecutorState::OnPsMediaPrefSetResponse(WWAN_EVENT const *)
0x18003d177  jmp     loc_18003EFDF
0x18003d17c  mov     rdx, rsi; struct WWAN_EVENT *
0x18003d17f  mov     rcx, rdi; this
0x18003d182  call    ?OnPsMediaPrefUpdate@CWwanDataExecutorState@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanDataExecutorState::OnPsMediaPrefUpdate(WWAN_EVENT const *)
0x18003d187  jmp     loc_18003EFDF
0x18003d18c  mov     ecx, [rsi+58h]
0x18003d18f  lea     r12d, [rcx-8]
0x18003d193  cmp     ecx, 8
0x18003d196  cmovbe  r12d, r8d
0x18003d19a  cmp     r12d, 10h
0x18003d19e  jb      loc_18003D610
0x18003d1a4  test    r14, r14
0x18003d1a7  jz      loc_18003D262
0x18003d1ad  test    cs:byte_1801528C4, 8
0x18003d1b4  jz      short loc_18003D1C9
0x18003d1b6  mov     r9d, [rsi+68h]
0x18003d1ba  mov     r8, r14
0x18003d1bd  lea     rdx, PSState
0x18003d1c4  call    McTemplateU0jq_EventWriteTransfer
0x18003d1c9  mov     r8d, [rsi+68h]
0x18003d1cd  mov     ecx, [rsi+70h]
0x18003d1d0  cmp     r8d, [rdi+38DCh]
0x18003d1d7  jnz     short loc_18003D1E1
0x18003d1d9  cmp     ecx, [rdi+38E4h]
0x18003d1df  jz      short loc_18003D25F
0x18003d1e1  mov     edx, [rdi+38D0h]
0x18003d1e7  call    ?CurrentDataClassToString@@YAPEBDKW4_WWAN_CELLULAR_CLASS@@@Z; CurrentDataClassToString(ulong,_WWAN_CELLULAR_CLASS)
0x18003d1ec  test    r8d, r8d
0x18003d1ef  jz      short loc_18003D232
0x18003d1f1  sub     r8d, r15d
0x18003d1f4  jz      short loc_18003D229
0x18003d1f6  sub     r8d, r15d
0x18003d1f9  jz      short loc_18003D220
0x18003d1fb  sub     r8d, r15d
0x18003d1fe  jz      short loc_18003D217
0x18003d200  cmp     r8d, r15d
0x18003d203  jz      short loc_18003D20E
0x18003d205  lea     r9, aUndefinederror; "UndefinedError"
0x18003d20c  jmp     short loc_18003D239
0x18003d20e  lea     r9, aDetached; "Detached"
0x18003d215  jmp     short loc_18003D239
0x18003d217  lea     r9, aDetaching; "Detaching"
0x18003d21e  jmp     short loc_18003D239
0x18003d220  lea     r9, aAttached_0; "Attached"
0x18003d227  jmp     short loc_18003D239
0x18003d229  lea     r9, aAttaching; "Attaching"
0x18003d230  jmp     short loc_18003D239
0x18003d232  lea     r9, aUnknown; "Unknown"
0x18003d239  mov     dword ptr [rbp+1E0h+var_1B0], 5
0x18003d240  movups  xmm0, xmmword ptr [r14]
0x18003d244  movdqu  [rbp+1E0h+var_1B0+4], xmm0
0x18003d249  mov     [rbp+1E0h+var_19C], 0F3h
0x18003d250  mov     r8, rax; char *
0x18003d253  mov     rdx, r9; char *
0x18003d256  lea     rcx, [rbp+1E0h+var_1B0]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18003d25a  call    ?CellularPacketServiceEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBD1@Z; NetworkingTriageScenario::GetConnected::CellularPacketServiceEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,char const *,char const *)
0x18003d25f  xor     r8d, r8d
0x18003d262  lea     r13, [rdi+38D8h]
0x18003d269  movups  xmm0, xmmword ptr [rsi+64h]
0x18003d26d  movdqu  xmmword ptr [r13+0], xmm0
0x18003d273  mov     al, [rsi+5Dh]
0x18003d276  cmp     al, 3
0x18003d278  jb      short loc_18003D2B3
0x18003d27a  cmp     r12d, 20h ; ' '
0x18003d27e  jb      short loc_18003D2B7
0x18003d280  mov     edx, [rsi+74h]
0x18003d283  mov     [rdi+38E8h], edx
0x18003d289  mov     r8d, [rsi+78h]
0x18003d28d  mov     [rdi+38ECh], r8d
0x18003d294  mov     rax, [rsi+7Ch]
0x18003d298  mov     [rdi+38F0h], rax
0x18003d29f  cmp     r12d, 24h ; '$'
0x18003d2a3  jb      short loc_18003D2E3
0x18003d2a5  mov     eax, [rsi+84h]
0x18003d2ab  mov     [rdi+38F8h], eax
0x18003d2b1  jmp     short loc_18003D2E3
0x18003d2b3  cmp     al, 2
0x18003d2b5  jb      short loc_18003D2CF
0x18003d2b7  cmp     r12d, 14h
0x18003d2bb  jb      short loc_18003D2CF
0x18003d2bd  mov     edx, [rsi+74h]
0x18003d2c0  mov     [rdi+38E8h], edx
0x18003d2c6  mov     [rdi+38ECh], r8d
0x18003d2cd  jmp     short loc_18003D2DC
0x18003d2cf  mov     qword ptr [rdi+38E8h], 0
0x18003d2da  xor     edx, edx
0x18003d2dc  mov     [rdi+38F0h], r8
0x18003d2e3  lea     r14, [rdi+30F8h]
0x18003d2ea  movzx   ecx, byte ptr [rsi+5Dh]
0x18003d2ee  mov     eax, [rdi+311Ch]
0x18003d2f4  mov     dword ptr [rsp+340h+var_2D0], eax
0x18003d2f8  mov     dword ptr [rsp+340h+var_2D8], ecx
0x18003d2fc  mov     eax, [rdi+38F4h]
0x18003d302  mov     dword ptr [rsp+340h+var_2E0], eax
0x18003d306  mov     dword ptr [rsp+340h+var_2E8], r8d
0x18003d30b  mov     dword ptr [rsp+340h+var_2F0], edx
0x18003d30f  mov     eax, [rsi+6Ch]
0x18003d312  mov     dword ptr [rsp+340h+var_2F8], eax
0x18003d316  mov     eax, [rsi+70h]
0x18003d319  mov     dword ptr [rsp+340h+var_300], eax
0x18003d31d  mov     eax, [rsi+68h]
0x18003d320  mov     dword ptr [rsp+340h+var_308], eax
0x18003d324  mov     eax, [rsi+64h]
0x18003d327  mov     dword ptr [rsp+340h+var_310], eax
0x18003d32b  mov     [rsp+340h+var_318], ebx
0x18003d32f  lea     r12, [rsi+18h]
0x18003d333  mov     rax, [r12]
0x18003d337  mov     [rsp+340h+var_320], rax
0x18003d33c  mov     r9d, [rsi]
0x18003d33f  lea     r8, aWwaneventcodep_0; "WwanEventCodePacketService (type %d) ha"...
0x18003d346  mov     rdx, r14; struct _GUID *
0x18003d349  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d350  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003d355  cmp     [rsi], r15d
0x18003d358  jnz     loc_18003D4D6
0x18003d35e  mov     r9d, [rdi+3950h]
0x18003d365  test    r9d, r9d
0x18003d368  jz      loc_18003D431
0x18003d36e  mov     rcx, [rdi+3958h]
0x18003d375  cmp     rcx, [r12]
0x18003d379  jnz     loc_18003D431
0x18003d37f  xor     r12d, r12d
0x18003d382  test    ebx, ebx
0x18003d384  jz      short loc_18003D3A7
0x18003d386  mov     [rsp+340h+var_318], ebx
0x18003d38a  mov     [rsp+340h+var_320], rcx
0x18003d38f  lea     r8, aPacketserviceR_2; "PacketService response (detachment reqI"...
0x18003d396  mov     rdx, r14; struct _GUID *
0x18003d399  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d3a0  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003d3a5  jmp     short loc_18003D3DD
0x18003d3a7  lea     rdx, aNotYetDetached; "not yet detached"
0x18003d3ae  lea     rax, aDetached_0; "detached"
0x18003d3b5  cmp     dword ptr [rsi+68h], 4
0x18003d3b9  cmovnz  rax, rdx
0x18003d3bd  mov     qword ptr [rsp+340h+var_318], rax
0x18003d3c2  mov     [rsp+340h+var_320], rcx
0x18003d3c7  lea     r8, aPacketserviceR_1; "PacketService response (detachment reqI"...
0x18003d3ce  mov     rdx, r14; struct _GUID *
0x18003d3d1  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d3d8  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003d3dd  mov     [rdi+3958h], r12
0x18003d3e4  mov     [rdi+3950h], r12d
0x18003d3eb  cmp     dword ptr [rsi+68h], 4
0x18003d3ef  jnz     short loc_18003D425
0x18003d3f1  lea     rdx, [rdi+4218h]
0x18003d3f8  mov     r8d, r15d
0x18003d3fb  call    ?StopWwanTimer@CWwanDataExecutorState@@AEAAKPEAU_WwanTimerSpecific@@W4WwanDataExecutorStateTimerId@1@@Z; CWwanDataExecutorState::StopWwanTimer(_WwanTimerSpecific *,CWwanDataExecutorState::WwanDataExecutorStateTimerId)
0x18003d400  mov     [rdi+3960h], r12d
0x18003d407  lea     r9, [rdi+3948h]; void **
0x18003d40e  lea     r8, [rdi+3940h]; unsigned int *
0x18003d415  mov     edx, r15d; int
0x18003d418  mov     rcx, rdi; this
0x18003d41b  call    ?SendMbbPsAttachDetachReq@CWwanDataExecutorState@@AEAAXHPEAKPEAPEAX@Z; CWwanDataExecutorState::SendMbbPsAttachDetachReq(int,ulong *,void * *)
0x18003d420  jmp     loc_18003D4D9
0x18003d425  mov     [rdi+3960h], r15d
0x18003d42c  jmp     loc_18003D4D9
0x18003d431  mov     ecx, [rdi+3940h]
0x18003d437  test    ecx, ecx
0x18003d439  jz      short loc_18003D4A4
0x18003d43b  mov     rdx, [rdi+3948h]
0x18003d442  cmp     rdx, [r12]
0x18003d446  jnz     short loc_18003D4A4
0x18003d448  xor     r12d, r12d
0x18003d44b  mov     r9d, ecx
0x18003d44e  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d455  test    ebx, ebx
0x18003d457  jz      short loc_18003D473
0x18003d459  mov     [rsp+340h+var_318], ebx
0x18003d45d  mov     [rsp+340h+var_320], rdx
0x18003d462  lea     r8, aPacketserviceR; "PacketService response (attachment reqI"...
0x18003d469  mov     rdx, r14; struct _GUID *
0x18003d46c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003d471  jmp     short loc_18003D4D9
0x18003d473  lea     r8, aNotYetAttached; "not yet attached"
0x18003d47a  lea     rax, aAttached; "attached"
0x18003d481  cmp     dword ptr [rsi+68h], 2
0x18003d485  cmovnz  rax, r8
0x18003d489  mov     qword ptr [rsp+340h+var_318], rax
0x18003d48e  mov     [rsp+340h+var_320], rdx
0x18003d493  lea     r8, aPacketserviceR_3; "PacketService response (attachment reqI"...
0x18003d49a  mov     rdx, r14; struct _GUID *
0x18003d49d  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003d4a2  jmp     short loc_18003D4D9
0x18003d4a4  mov     rax, [rdi+3948h]
0x18003d4ab  mov     [rsp+340h+var_310], rax
0x18003d4b0  mov     [rsp+340h+var_318], ecx
0x18003d4b4  mov     rax, [rdi+3958h]
0x18003d4bb  mov     [rsp+340h+var_320], rax
0x18003d4c0  lea     r8, aPacketserviceR_0; "PacketService response, unwanted and ig"...
0x18003d4c7  mov     rdx, r14; struct _GUID *
0x18003d4ca  lea     rcx, aCwwandataexecu_103; "CWwanDataExecutorState::OnNdisNotificat"...
0x18003d4d1  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003d4d6  xor     r12d, r12d
0x18003d4d9  cmp     [rdi+3960h], r12d
  ... truncated ...
```
