# FactoryCreateJob(ulong,_WFC_JOB_TYPE,CJobBase * *)

- ea: `0x1400072a0`
- end: `0x140009412`
- name: `?FactoryCreateJob@@YAHKW4_WFC_JOB_TYPE@@PEAPEAVCJobBase@@@Z`
- size: `8562`
- prototype: ``
- caller_count: `1`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140005d40`

## callees

- `0x140006fec`
- `0x1400072a0`
- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x140019e70`
- `0x140019fc8`
- `0x140022ab0`
- `0x14002b16c`
- `0x14002bfb0`
- `0x14004c598`
- `0x14004c7d4`
- `0x14005362c`
- `0x1400593d0`
- `0x14005fd78`
- `0x14005fdfc`
- `0x14005fe70`
- `0x14006f44c`
- `0x14006f4c8`
- `0x14006f560`
- `0x14006f65c`
- `0x14006f708`
- `0x14006f770`
- `0x14006f898`
- `0x14006f928`
- `0x14006f9a0`
- `0x14006fa1c`
- `0x14006fab0`
- `0x14006fb14`
- `0x14006fb84`
- `0x14006fc10`
- `0x14006fc5c`
- `0x14006fdd0`
- `0x1400700e0`
- `0x140070234`
- `0x14007692c`
- `0x140076984`
- `0x14007fe98`
- `0x14008f9f0`
- `0x14008fa54`
- `0x14008fb34`
- `0x1400a0c7c`
- `0x1400bb630`
- `0x1400bd46c`
- `0x1400bf364`
- `0x1400dfd40`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400093aa`
- `ntoskrnl!ExAllocatePool2` at `0x1400093aa`

## pseudocode

```c
__int64 __fastcall FactoryCreateJob(unsigned int a1, int a2, CSimpleSetOidJob **a3)
{
  int v3; // edi
  unsigned __int64 v6; // rdx
  int v7; // kr08_4
  CSimpleSetOidJob *v8; // rax
  CSimpleSetOidJob *Pool2; // rbx
  void **v10; // rcx
  CSimpleQueryOidJob *v11; // rax
  CDot11ResetJob *v12; // rax
  CSetWFDStopBackgroundDiscovery *OidJob; // rax
  CSimpleQueryOidJob *v14; // rax
  COidJobBase *v15; // rax
  CSimpleQueryOidJob *v16; // rax
  CSimplePropertyCacheULongSetOidJob *v17; // rax
  CSimplePropertyCacheListQueryOidJob *v18; // rax
  unsigned __int8 v19; // r8
  unsigned __int8 v20; // r9
  CSimplePropertyCacheListSetOidJob *v21; // rax
  unsigned __int8 v22; // r8
  unsigned __int8 v23; // r9
  unsigned int v24; // edx
  CSimplePropertyCacheListQueryOidJob *v25; // rax
  unsigned __int8 v26; // r8
  unsigned __int8 v27; // r9
  CSimplePropertyCacheListQueryOidJob *v28; // rax
  unsigned __int8 v29; // r8
  unsigned __int8 v30; // r9
  CSimpleSetOidJob *v31; // rax
  CDeviceCommandOidJobBase *v32; // rax
  CDeviceCommandOidJobBase *v33; // rax
  COidJobBase *v34; // rax
  CSimpleQueryOidJob *v35; // rax
  CSimpleSetOidJob *v36; // rax
  CSimpleQueryOidJob *v37; // rax
  CScanJob *v38; // rax
  CScanOidJob *v39; // rax
  CSimplePropertyCacheListQueryOidJob *v40; // rax
  unsigned __int8 v41; // r8
  unsigned __int8 v42; // r9
  CSimplePropertyCacheListSetOidJob *v43; // rax
  unsigned __int8 v44; // r8
  unsigned __int8 v45; // r9
  CSimpleQueryOidJob *v46; // rax
  CSimpleSetOidJob *v47; // rax
  CSimpleQueryOidJob *v48; // rax
  __int64 v49; // rcx
  CSimpleSetOidJob *v50; // rax
  CSimpleQueryOidJob *v51; // rax
  __int64 v52; // rcx
  CSimpleSetOidJob *v53; // rax
  CConnectJob *v54; // rax
  CDisconnectJob *v55; // rax
  CSimpleSetOidJob *v56; // rax
  CSimplePropertyCacheListQueryOidJob *v57; // rax
  unsigned __int8 v58; // r8
  unsigned __int8 v59; // r9
  CSimplePropertyCacheListQueryOidJob *v60; // rax
  unsigned __int8 v61; // r8
  unsigned __int8 v62; // r9
  CSimpleSetOidJob *v63; // rax
  CSimpleSetOidJob *v64; // rax
  CFlushBSSListJob *v65; // rax
  CSimpleQueryOidJob *v66; // rax
  CSimpleQueryOidJob *v67; // rax
  CSimpleQueryOidJob *v68; // rax
  CSimpleQueryOidJob *v69; // rax
  CSimpleQueryOidJob *v70; // rax
  __int64 v71; // rcx
  CSimpleSetOidJob *v72; // rax
  CSimpleQueryOidJob *v73; // rax
  CSimplePropertyCacheULongSetOidJob *v74; // rax
  CSimpleQueryOidJob *v75; // rax
  CSimpleQueryOidJob *v76; // rax
  CSimplePropertyCacheULongSetOidJob *v77; // rax
  CSimpleQueryOidJob *v78; // rax
  CSimplePropertyCacheULongSetOidJob *v79; // rax
  CSimpleQueryOidJob *v80; // rax
  CSimplePropertyCacheULongSetOidJob *v81; // rax
  CSimpleQueryOidJob *v82; // rax
  __int64 v83; // rcx
  CSimpleSetOidJob *v84; // rax
  CSimpleQueryOidJob *v85; // rax
  CSimpleSetOidJob *v86; // rax
  CSimpleQueryOidJob *v87; // rax
  CSimplePropertyCacheULongSetOidJob *v88; // rax
  CSimpleQueryOidJob *v89; // rax
  CSimplePropertyCacheULongSetOidJob *v90; // rax
  CSimplePropertyCacheListQueryOidJob *v91; // rax
  unsigned __int8 v92; // r8
  unsigned __int8 v93; // r9
  CSimpleSetOidJob *v94; // rax
  CSimplePropertyCacheListQueryOidJob *v95; // rax
  unsigned __int8 v96; // r8
  unsigned __int8 v97; // r9
  unsigned int v98; // edi
  CSimplePropertyCacheListQueryOidJob *v99; // rax
  unsigned __int8 v100; // r8
  unsigned __int8 v101; // r9
  CSimpleQueryOidJob *v102; // rax
  CSimpleQueryOidJob *v103; // rax
  CSimpleQueryOidJob *v104; // rax
  CSimpleQueryOidJob *v105; // rax
  CSimpleQueryOidJob *v106; // rax
  CSimpleSetDeviceCommandOidJob *v107; // rax
  bool v108; // r8
  CSimpleSetDeviceCommandOidJob *v109; // rax
  bool v110; // r8
  CSimpleQueryOidJob *v111; // rax
  CSimpleSetDeviceCommandOidJob *v112; // rax
  bool v113; // r8
  CSimpleSetDeviceCommandOidJob *v114; // rax
  bool v115; // r8
  CSimplePropertyCacheListQueryOidJob *v116; // rax
  unsigned __int8 v117; // r8
  unsigned __int8 v118; // r9
  CSimpleSetOidJob *v119; // rax
  CSimpleSetOidJob *v120; // rax
  CSimpleQueryOidJob *v121; // rax
  CSetRadioStateJob *v122; // rax
  CSimpleQueryOidJob *v123; // rax
  CSimpleQueryDeviceCommandOidJob *v124; // rax
  COidJobBase *v125; // rax
  COidJobBase *v126; // rax
  CSimpleSetOidJob *v127; // rax
  COidJobBase *v128; // rax
  CSimpleQueryOidJob *v129; // rax
  CSetWFDAdvertisementSettings *v130; // rax
  CSimpleQueryOidJob *v131; // rax
  CSimpleSetOidJob *v132; // rax
  _QWORD *v133; // rcx
  CDeviceCommandOidJobBase *v134; // rax
  CP2PDiscoverJob *v135; // rax
  CSimpleSetOidJob *v136; // rax
  _QWORD *v137; // rcx
  CSimpleSetDeviceCommandOidJob *v138; // rax
  bool v139; // r8
  CSetWFDStartBackgroundDiscovery *v140; // rax
  CSetWFDStopBackgroundDiscovery *v141; // rax
  CP2PSendActionFrameRequestJob *v142; // rax
  CSimpleSetOidJob *v143; // rax
  _QWORD *v144; // rcx
  CDeviceCommandOidJobBase *v145; // rax
  CStartAPJob *v146; // rax
  CSimpleSetOidJob *v147; // rax
  CSendAssociationResponseJob *v148; // rax
  CSimpleSetDeviceCommandOidJob *v149; // rax
  bool v150; // r8
  CSimpleQueryDeviceCommandOidJob *v151; // rax
  CSimpleMethodDeviceCommandOidJob *v152; // rax
  CSimpleSetOidJob *v153; // rax
  CANQPQueryJob *v154; // rax
  CRequestFtmJob *v155; // rax
  CDot11RandomMacForScan *v156; // rax
  CSimpleQueryOidJob *v157; // rax
  CSimpleSetOidJob *v158; // rax
  CSimpleSetDeviceCommandOidJob *v159; // rax
  bool v160; // r8
  CIhvTaskRequestJob *v161; // rax
  CSimpleQueryDeviceCommandOidJob *v162; // rax
  CSimpleMethodDeviceCommandOidJob *v163; // rax
  CSimpleMethodDeviceCommandOidJob *v164; // rax
  CSimpleSetOidJob *v165; // rax
  CSimpleSetOidJob *v166; // rax
  CSimpleSetOidJob *v167; // rax
  COidJobBase *v168; // rax
  CSimpleQueryOidJob *v169; // rax
  CSimpleQueryOidJob *v170; // rax
  COidJobBase *v171; // rax
  CSimpleSetDeviceCommandOidJob *v172; // rax
  bool v173; // r8
  COidJobBase *v174; // rax
  CSimpleSetDeviceCommandOidJob *v175; // rax
  bool v176; // r8
  CSimpleSetOidJob *v177; // rax
  CSimpleQueryOidJob *v178; // rax
  CSimpleQueryOidJob *v179; // rax
  CSimpleSetOidJob *v180; // rax
  wificx::authentication_frame::SetAuthenticationFrameSubscriptionJob *v181; // rax
  wificx::authentication_frame::SendAuthenticationFrameJob *v182; // rax
  wlan::wfd2::SetDeviceCapabilitiesAndIdentityJob *v183; // rax
  CEnumBSSListJob *v184; // rax
  _QWORD *v186; // rcx
  _QWORD *v187; // rax
  __int64 v188; // [rsp+28h] [rbp-A0h]
  unsigned int v189; // [rsp+30h] [rbp-98h]
  unsigned int v190; // [rsp+38h] [rbp-90h]
  unsigned int v191; // [rsp+48h] [rbp-80h]
  unsigned int v192; // [rsp+50h] [rbp-78h]
  unsigned int v193; // [rsp+58h] [rbp-70h]
  __int64 v194; // [rsp+60h] [rbp-68h] BYREF
  __int128 v195; // [rsp+68h] [rbp-60h] BYREF
  __int128 v196; // [rsp+78h] [rbp-50h]
  __int128 v197; // [rsp+88h] [rbp-40h]
  __int64 *v198; // [rsp+98h] [rbp-30h]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h]
  void *v200; // [rsp+E8h] [rbp+20h] BYREF

  v3 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      10,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids);
  }
  if ( v3 == 87 )
  {
    if ( !g_Feature_56544556_MoveToWDFMemory_IsEnabled )
    {
      Pool2 = (CSimpleSetOidJob *)ExAllocatePool2(64, 624, 1198089303);
      goto LABEL_325;
    }
    v195 = 0;
    v198 = 0;
    v196 = 0;
    v197 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x26 )
        LODWORD(v195) = -1;
      else
        LODWORD(v195) = *(_DWORD *)(WdfStructures + 304);
    }
    else
    {
      LODWORD(v195) = 56;
    }
    v198 = off_14010E2B8;
    *((_QWORD *)&v196 + 1) = 0x100000001LL;
    v194 = 0;
    v200 = 0;
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64, __int64, __int64 *, void **))(WdfFunctions_01031 + 1536))(
           WdfDriverGlobals,
           &v195,
           512,
           1198089303,
           640,
           &v194,
           &v200) >= 0 )
    {
      memset(v200, 0, 0x280u);
      v186 = v200;
      *(_QWORD *)v200 = 16;
      v186[1] = v194;
      v187 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                         WdfDriverGlobals,
                         v194,
                         off_14010E2B8);
      v187[1] = retaddr;
      *v187 = 16;
      Pool2 = (CSimpleSetOidJob *)((char *)v200 + 16);
      if ( (char *)v200 + 16 >= v200 )
        goto LABEL_325;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          12,
          (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        11,
        (__int64)WPP_8af6070512533c37ff8d635f078fb2ba_Traceguids);
      Pool2 = 0;
LABEL_325:
      if ( !Pool2 )
        goto LABEL_303;
      COidJobBase::COidJobBase(Pool2, a1);
      *((_QWORD *)Pool2 + 73) = 0;
      *((_DWORD *)Pool2 + 148) = 0;
      *((_QWORD *)Pool2 + 75) = 0;
      *((_QWORD *)Pool2 + 76) = 0;
LABEL_327:
      *((_DWORD *)Pool2 + 154) = 30;
LABEL_328:
      v10 = &CQueryMediaStreamingEnabledOidJob::`vftable'{for `IOperationCompletionCallback'};
LABEL_329:
      *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
      *(_QWORD *)Pool2 = v10;
LABEL_330:
      v98 = 0;
      *a3 = Pool2;
      goto LABEL_306;
    }
    Pool2 = 0;
    goto LABEL_325;
  }
  if ( v3 != 139 )
  {
    v7 = a2;
    v6 = 0x140000000uLL;
    switch ( v3 )
    {
      case 1:
        v8 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v8;
        if ( !v8 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v8, a1);
        v10 = &CDummySetJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 2:
        v11 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v11;
        if ( !v11 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v11, a1);
        v10 = &CDummyQueryReturnTrueJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 16:
        v12 = (CDot11ResetJob *)operator new(0xCC8u);
        if ( !v12 )
          goto LABEL_303;
        OidJob = CDot11ResetJob::CDot11ResetJob(v12, a1);
        goto LABEL_302;
      case 17:
        v14 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v14;
        if ( !v14 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v14, a1);
        v10 = &CQueryOperationModeJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 18:
        v15 = (COidJobBase *)operator new(0x430u);
        Pool2 = v15;
        if ( !v15 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v15, a1);
        *(_QWORD *)Pool2 = &CSetOperationModeJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        Task::Task((CSimpleSetOidJob *)((char *)Pool2 + 584), a1);
        *((_QWORD *)Pool2 + 132) = 0;
        goto LABEL_330;
      case 22:
        v126 = (COidJobBase *)operator new(0x560u);
        Pool2 = v126;
        if ( !v126 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v126, a1);
        *(_QWORD *)Pool2 = &CSetAutoPowerSaveJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        CUpdateConnectionQualityJob::CUpdateConnectionQualityJob((CSimpleSetOidJob *)((char *)Pool2 + 608), a1);
        goto LABEL_330;
      case 23:
        v125 = (COidJobBase *)operator new(0x348u);
        Pool2 = v125;
        if ( !v125 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v125, a1);
        *(_QWORD *)Pool2 = &CGetAutoPowerSaveJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        DeviceCommand::DeviceCommand((CSimpleSetOidJob *)((char *)Pool2 + 576), a1);
        goto LABEL_330;
      case 24:
        v127 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v127;
        if ( !v127 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v127, a1);
        v10 = &CSetPowerMgmtRequestJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 25:
        v129 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v129;
        if ( !v129 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v129, a1);
        v10 = &CGetPowerMgmtRequestJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 26:
        v128 = (COidJobBase *)operator new(0x3A0u);
        Pool2 = v128;
        if ( !v128 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v128, a1);
        *(_QWORD *)Pool2 = &CSetNloJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        DeviceCommand::DeviceCommand((CSimpleSetOidJob *)((char *)Pool2 + 576), a1);
        memset((char *)Pool2 + 792, 0, 0x78u);
        goto LABEL_330;
      case 27:
        v16 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v16;
        if ( !v16 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v16, a1);
        *((_DWORD *)Pool2 + 154) = 27;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 28:
        v17 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        Pool2 = v17;
        if ( !v17 )
          goto LABEL_303;
        CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v17, 0x1Bu, 1u, 2u, a1);
        v10 = &CSetDesirerdBssTypeJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 29:
        v18 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v18 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v18,
                   7u,
                   v19,
                   v20,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   a1);
        goto LABEL_302;
      case 30:
        if ( (unsigned int)Feature_57277348__private_IsEnabledDeviceUsageNoInline() )
        {
          v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
          if ( !v21 )
            goto LABEL_303;
          v193 = a1;
          v192 = 5;
          goto LABEL_27;
        }
        v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
        if ( v21 )
        {
          v193 = a1;
          v192 = 2;
LABEL_27:
          v24 = 7;
          goto LABEL_28;
        }
        break;
      case 31:
        v31 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v31;
        if ( !v31 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v31, a1);
        v10 = &CSetFTParametersJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 32:
        v25 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v25 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v25,
                   8u,
                   v26,
                   v27,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   a1);
        goto LABEL_302;
      case 33:
        v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
        if ( !v21 )
          goto LABEL_303;
        v193 = a1;
        v24 = 8;
        v192 = 256;
        v191 = 0;
        goto LABEL_29;
      case 34:
        v28 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v28 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v28,
                   9u,
                   v29,
                   v30,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   a1);
        goto LABEL_302;
      case 35:
        if ( (unsigned int)Feature_57277348__private_IsEnabledDeviceUsageNoInline() )
        {
          v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
          if ( !v21 )
            goto LABEL_303;
          v193 = a1;
          v192 = 5;
        }
        else
        {
          v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
          if ( !v21 )
            goto LABEL_303;
          v193 = a1;
          v192 = 2;
        }
        v24 = 9;
LABEL_28:
        v191 = 1;
LABEL_29:
        OidJob = CSimplePropertyCacheListSetOidJob::CSimplePropertyCacheListSetOidJob(
                   v21,
                   v24,
                   v22,
                   v23,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   v191,
                   v192,
                   v193);
        goto LABEL_302;
      case 36:
        v35 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v35;
        if ( !v35 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v35, a1);
        v10 = &CQueryPhyIdJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 37:
        v36 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v36;
        if ( !v36 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v36, a1);
        v10 = &CSetPhyIdJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 38:
        v38 = (CScanJob *)operator new(0x7C8u);
        if ( !v38 )
          goto LABEL_303;
        OidJob = CScanJob::CScanJob(v38, a1);
        goto LABEL_302;
      case 39:
        v39 = (CScanOidJob *)operator new(0x370u);
        if ( !v39 )
          goto LABEL_303;
        OidJob = CScanOidJob::CScanOidJob(v39, a1);
        goto LABEL_302;
      case 40:
        goto LABEL_300;
      case 41:
        v40 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v40 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v40,
                   5u,
                   v41,
                   v42,
                   48,
                   v188,
                   v189,
                   v190,
                   0x24u,
                   a1);
        goto LABEL_302;
      case 42:
        v43 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
        if ( !v43 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListSetOidJob::CSimplePropertyCacheListSetOidJob(
                   v43,
                   5u,
                   v44,
                   v45,
                   48,
                   v188,
                   v189,
                   v190,
                   0x24u,
                   1u,
                   1u,
                   a1);
        goto LABEL_302;
      case 43:
        v46 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v46;
        if ( !v46 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v46, a1);
        v10 = &CQueryDesiredHESSIDList::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 44:
        v47 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v47;
        if ( !v47 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v47, a1);
        v10 = &CSetDesiredHESSIDList::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 45:
        v48 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v48;
        if ( !v48 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v48, a1);
        *(_DWORD *)(v49 + 616) = 13;
        goto LABEL_328;
      case 46:
        v50 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v50;
        if ( !v50 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v50, a1);
        *((_DWORD *)Pool2 + 154) = 13;
        v10 = &CSimplePropertyCacheBooleanSetOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 47:
        v51 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v51;
        if ( !v51 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v51, a1);
        *(_DWORD *)(v52 + 616) = 12;
        goto LABEL_328;
      case 48:
        v53 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v53;
        if ( !v53 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v53, a1);
        *((_DWORD *)Pool2 + 154) = 12;
        v10 = &CSimplePropertyCacheBooleanSetOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 49:
      case 116:
        v54 = (CConnectJob *)operator new(0x15C8u);
        if ( !v54 )
          goto LABEL_303;
        OidJob = CConnectJob::CConnectJob(v54, a1);
        goto LABEL_302;
      case 50:
        v37 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v37;
        if ( !v37 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v37, a1);
        v10 = &CQueryOperationalRateSet::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 51:
        v55 = (CDisconnectJob *)operator new(0x460u);
        if ( !v55 )
          goto LABEL_303;
        OidJob = CDisconnectJob::CDisconnectJob(v55, a1);
        goto LABEL_302;
      case 52:
        v107 = (CSimpleSetDeviceCommandOidJob *)operator new(0x458u);
        Pool2 = v107;
        if ( !v107 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v107, a1, v108);
        *(_QWORD *)Pool2 = &CSetPrivacyExemptionListJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 53:
        v109 = (CSimpleSetDeviceCommandOidJob *)operator new(0x458u);
        Pool2 = v109;
        if ( !v109 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v109, a1, v110);
        *(_QWORD *)Pool2 = &CSetDefaultKeyJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 54:
        v112 = (CSimpleSetDeviceCommandOidJob *)operator new(0x458u);
        Pool2 = v112;
        if ( !v112 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v112, a1, v113);
        *(_QWORD *)Pool2 = &CSetDefaultKeyIdJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 55:
        v114 = (CSimpleSetDeviceCommandOidJob *)operator new(0x460u);
        Pool2 = v114;
        if ( !v114 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v114, a1, v115);
        *((_BYTE *)Pool2 + 1112) = 0;
        *(_QWORD *)Pool2 = &CSetKeyMappingKeyJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 56:
        v60 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v60 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v60,
                   0x10u,
                   v61,
                   v62,
                   20,
                   v188,
                   v189,
                   v190,
                   6u,
                   a1);
        goto LABEL_302;
      case 57:
        v63 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v63;
        if ( !v63 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v63, a1);
        v10 = &CSetDesiredBSSIDListJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 59:
        v64 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v64;
        if ( !v64 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v64, a1);
        v10 = &CSetStaAssociationIEsJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 60:
      case 141:
        v65 = (CFlushBSSListJob *)operator new(0x328u);
        if ( !v65 )
          goto LABEL_303;
        OidJob = CFlushBSSListJob::CFlushBSSListJob(v65, a1);
        goto LABEL_302;
      case 61:
        v66 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v66;
        if ( !v66 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v66, a1);
        v10 = &CEnumAssociationInfoJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 65:
        v121 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v121;
        if ( !v121 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v121, a1);
        *((_BYTE *)Pool2 + 616) = 0;
        v10 = &CGetRadioStateJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 66:
        v122 = (CSetRadioStateJob *)operator new(0x1110u);
        if ( !v122 )
          goto LABEL_303;
        OidJob = CSetRadioStateJob::CSetRadioStateJob(v122, a1);
        goto LABEL_302;
      case 67:
        v67 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v67;
        if ( !v67 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v67, a1);
        v10 = &CQueryOperationModeCapabilityJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 68:
        v68 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v68;
        if ( !v68 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v68, a1);
        v10 = &CQueryMacAddressJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 69:
        v69 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v69;
        if ( !v69 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v69, a1);
        v10 = &CQueryHardwareAddressJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 71:
        v70 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v70;
        if ( !v70 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v70, a1);
        *(_DWORD *)(v71 + 616) = 28;
        *(_QWORD *)v71 = &CQueryMediaStreamingEnabledOidJob::`vftable'{for `IOperationCompletionCallback'};
        *(_QWORD *)(v71 + 8) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 72:
        v72 = (CSimpleSetOidJob *)operator new(0x550u);
        Pool2 = v72;
        if ( !v72 )
          goto LABEL_303;
        CConnectionQualityOidJob::CConnectionQualityOidJob(v72, a1, 2, 53, 28);
        *(_QWORD *)Pool2 = &CSetMediaStreamingEnabledOidJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 73:
        v123 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v123;
        if ( !v123 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v123, a1);
        *((_BYTE *)Pool2 + 616) = 1;
        v10 = &CGetRadioStateJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 74:
        v57 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v57 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v57,
                   0x29u,
                   v58,
                   v59,
                   20,
                   v188,
                   v189,
                   v190,
                   6u,
                   a1);
        goto LABEL_302;
      case 75:
        v111 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v111;
        if ( !v111 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v111, a1);
        *((_DWORD *)Pool2 + 154) = 1;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 76:
        v99 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v99 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v99,
                   0x32u,
                   v100,
                   v101,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   a1);
        goto LABEL_302;
      case 77:
        v73 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v73;
        if ( !v73 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v73, a1);
        *((_DWORD *)Pool2 + 154) = 29;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 78:
        v74 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v74 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v74, 0x1Du, 0, 2u, a1);
        goto LABEL_302;
      case 79:
        v95 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v95 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v95,
                   0x31u,
                   v96,
                   v97,
                   16,
                   v188,
                   v189,
                   v190,
                   4u,
                   a1);
        goto LABEL_302;
      case 80:
        v21 = (CSimplePropertyCacheListSetOidJob *)operator new(0x288u);
        if ( !v21 )
          goto LABEL_303;
        v193 = a1;
        v24 = 49;
        v192 = 10;
        goto LABEL_28;
      case 81:
        v91 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v91 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v91,
                   0x2Au,
                   v92,
                   v93,
                   20,
                   v188,
                   v189,
                   v190,
                   6u,
                   a1);
        goto LABEL_302;
      case 82:
        v94 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v94;
        if ( !v94 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v94, a1);
        v10 = &CSetExcludedMacAddressListJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 83:
        v116 = (CSimplePropertyCacheListQueryOidJob *)operator new(0x280u);
        if ( !v116 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(
                   v116,
                   0x2Cu,
                   v117,
                   v118,
                   40,
                   v188,
                   v189,
                   v190,
                   0x1Cu,
                   a1);
        goto LABEL_302;
      case 84:
        v119 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v119;
        if ( !v119 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v119, a1);
        v10 = &CSetPMKIDList::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 85:
        v102 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v102;
        if ( !v102 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v102, a1);
        v10 = &CQuerySupportedMulticastAlgorithmPairJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 86:
        v103 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v103;
        if ( !v103 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v103, a1);
        v10 = &CQuerySupportedUnicastAlgorithmPairJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 88:
        v75 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v75;
        if ( !v75 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v75, a1);
        goto LABEL_327;
      case 92:
        v78 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v78;
        if ( !v78 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v78, a1);
        *((_DWORD *)Pool2 + 154) = 34;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 93:
        v79 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v79 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v79, 0x22u, 0, 0x92Bu, a1);
        goto LABEL_302;
      case 94:
        v80 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v80;
        if ( !v80 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v80, a1);
        *((_DWORD *)Pool2 + 154) = 35;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 95:
        v81 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v81 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v81, 0x23u, 0x100u, 0x92Au, a1);
        goto LABEL_302;
      case 96:
        v106 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v106;
        if ( !v106 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v106, a1);
        v10 = &CQueryCurrentRegDomainJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 97:
      case 99:
        v87 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v87;
        if ( !v87 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v87, a1);
        *((_DWORD *)Pool2 + 154) = 37;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 98:
      case 100:
        v88 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v88 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v88, 0x25u, 0, 0xC8u, a1);
        goto LABEL_302;
      case 101:
        v105 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v105;
        if ( !v105 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v105, a1);
        v10 = &CQueryRegDomainsSupportJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 102:
        v89 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v89;
        if ( !v89 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v89, a1);
        *((_DWORD *)Pool2 + 154) = 36;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 103:
        v90 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v90 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v90, 0x24u, 0, 0xEA60u, a1);
        goto LABEL_302;
      case 104:
      case 105:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v6) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            1,
            11,
            (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids);
        }
        goto LABEL_151;
      case 106:
        v82 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v82;
        if ( !v82 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v82, a1);
        *(_DWORD *)(v83 + 616) = 31;
        goto LABEL_328;
      case 107:
        v84 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v84;
        if ( !v84 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v84, a1);
        *((_DWORD *)Pool2 + 154) = 31;
        v10 = &CSimplePropertyCacheBooleanSetOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 108:
        v104 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v104;
        if ( !v104 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v104, a1);
        v10 = &CQueryExtSTACapabilityJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 109:
        v124 = (CSimpleQueryDeviceCommandOidJob *)operator new(0x330u);
        Pool2 = v124;
        if ( !v124 )
          goto LABEL_303;
        CSimpleQueryDeviceCommandOidJob::CSimpleQueryDeviceCommandOidJob(v124, a1);
        *(_QWORD *)Pool2 = &CQueryStatisticsJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 110:
        v76 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v76;
        if ( !v76 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v76, a1);
        *((_DWORD *)Pool2 + 154) = 25;
        v10 = &CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 111:
        v77 = (CSimplePropertyCacheULongSetOidJob *)operator new(0x278u);
        if ( !v77 )
          goto LABEL_303;
        OidJob = CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(v77, 0x19u, 1u, 0xFFFFu, a1);
        goto LABEL_302;
      case 114:
      case 115:
      case 118:
      case 122:
      case 126:
      case 129:
      case 170:
        v130 = (CSetWFDAdvertisementSettings *)operator new(0x638u);
        if ( !v130 )
          goto LABEL_303;
        OidJob = CSetWFDAdvertisementSettings::CSetWFDAdvertisementSettings(v130, a1);
        goto LABEL_302;
      case 117:
        v132 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v132;
        if ( !v132 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v132, a1);
        v133[77] = 58;
        *v133 = &CSetAPGroupStartParametersJob::`vftable'{for `IOperationCompletionCallback'};
        v133[1] = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 119:
        v134 = (CDeviceCommandOidJobBase *)operator new(0x450u);
        Pool2 = v134;
        if ( !v134 )
          goto LABEL_303;
        CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(v134, a1);
        *(_QWORD *)Pool2 = &CP2PDisconnectJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        *((_QWORD *)Pool2 + 137) = 0;
        goto LABEL_330;
      case 120:
        v135 = (CP2PDiscoverJob *)operator new(0x998u);
        if ( !v135 )
          goto LABEL_303;
        OidJob = CP2PDiscoverJob::CP2PDiscoverJob(v135, a1);
        goto LABEL_302;
      case 121:
        v136 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v136;
        if ( !v136 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v136, a1);
        v137[77] = 63;
        *v137 = &CSetAPGroupStartParametersJob::`vftable'{for `IOperationCompletionCallback'};
        v137[1] = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 123:
      case 124:
        v138 = (CSimpleSetDeviceCommandOidJob *)operator new(0x470u);
        Pool2 = v138;
        if ( !v138 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v138, a1, v139);
        *(_QWORD *)Pool2 = &CSetWFDListenState::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        *(_OWORD *)((char *)Pool2 + 1112) = 0;
        *((_QWORD *)Pool2 + 141) = 0;
        goto LABEL_330;
      case 125:
        v131 = (CSimpleQueryOidJob *)operator new(0x270u);
        Pool2 = v131;
        if ( !v131 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v131, a1);
        v10 = &CGetWFDAdvertisementSettings::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 127:
        v140 = (CSetWFDStartBackgroundDiscovery *)operator new(0x4C8u);
        if ( !v140 )
          goto LABEL_303;
        OidJob = CSetWFDStartBackgroundDiscovery::CSetWFDStartBackgroundDiscovery(v140, a1);
        goto LABEL_302;
      case 128:
        v141 = (CSetWFDStopBackgroundDiscovery *)operator new(0x308u);
        if ( !v141 )
          goto LABEL_303;
        OidJob = CSetWFDStopBackgroundDiscovery::CSetWFDStopBackgroundDiscovery(v141, a1);
        goto LABEL_302;
      case 130:
        v142 = (CP2PSendActionFrameRequestJob *)operator new(0x11D0u);
        if ( !v142 )
          goto LABEL_303;
        OidJob = CP2PSendActionFrameRequestJob::CP2PSendActionFrameRequestJob(v142, a1);
        goto LABEL_302;
      case 131:
        v143 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v143;
        if ( !v143 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v143, a1);
        v144[77] = 65;
        *v144 = &CSetAPGroupStartParametersJob::`vftable'{for `IOperationCompletionCallback'};
        v144[1] = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 132:
        v145 = (CDeviceCommandOidJobBase *)operator new(0x7D8u);
        Pool2 = v145;
        if ( !v145 )
          goto LABEL_303;
        CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(v145, a1);
        *(_QWORD *)Pool2 = &CP2PSendActionFrameResponseJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        _WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME_PARAMETERS::_WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME_PARAMETERS((CSimpleSetOidJob *)((char *)Pool2 + 1096));
        WiFiCxTLVStaging::_WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME_PARAMETERS::_WDI_TASK_P2P_SEND_RESPONSE_ACTION_FRAME_PARAMETERS((CSimpleSetOidJob *)((char *)Pool2 + 1472));
        *((_QWORD *)Pool2 + 247) = 0;
        goto LABEL_330;
      case 133:
        v146 = (CStartAPJob *)operator new(0x500u);
        if ( !v146 )
          goto LABEL_303;
        OidJob = CStartAPJob::CStartAPJob(v146, v6, a1);
        goto LABEL_302;
      case 136:
        v147 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v147;
        if ( !v147 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v147, a1);
        v10 = &CP2PDiscoverCancelJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 137:
        v148 = (CSendAssociationResponseJob *)operator new(0x4D0u);
        if ( !v148 )
          goto LABEL_303;
        OidJob = CSendAssociationResponseJob::CSendAssociationResponseJob(v148, a1);
        goto LABEL_302;
      case 138:
        v149 = (CSimpleSetDeviceCommandOidJob *)operator new(0x460u);
        Pool2 = v149;
        if ( !v149 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v149, a1, v150);
        *(_QWORD *)Pool2 = &CSetWpsEnabledJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        *((_BYTE *)Pool2 + 1112) = 0;
        goto LABEL_330;
      case 140:
        v151 = (CSimpleQueryDeviceCommandOidJob *)operator new(0x428u);
        Pool2 = v151;
        if ( !v151 )
          goto LABEL_303;
        CSimpleQueryDeviceCommandOidJob::CSimpleQueryDeviceCommandOidJob(v151, a1);
        *(_QWORD *)Pool2 = &CGetNextDialogTokenJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 143:
        v86 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v86;
        if ( !v86 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v86, a1);
        *((_DWORD *)Pool2 + 154) = 72;
        v10 = &CSimplePropertyCacheUCharWithHeaderSetOidJob::`vftable'{for `IOperationCompletionCallback'};
        *((_DWORD *)Pool2 + 155) = 393600;
        goto LABEL_329;
      case 144:
        v85 = (CSimpleQueryOidJob *)operator new(0x278u);
        Pool2 = v85;
        if ( !v85 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v85, a1);
        *((_DWORD *)Pool2 + 154) = 72;
        v10 = &CSimplePropertyCacheUCharWithHeaderQueryOidJob::`vftable'{for `IOperationCompletionCallback'};
        *((_DWORD *)Pool2 + 155) = 393600;
        goto LABEL_329;
      case 147:
        v152 = (CSimpleMethodDeviceCommandOidJob *)operator new(0x338u);
        Pool2 = v152;
        if ( !v152 )
          goto LABEL_303;
        CSimpleMethodDeviceCommandOidJob::CSimpleMethodDeviceCommandOidJob(v152, a1);
        *(_QWORD *)Pool2 = &CNicSpecificExtensionJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 149:
        v153 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v153;
        if ( !v153 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v153, a1);
        *((_BYTE *)Pool2 + 42) = 1;
        v10 = &CResetRecoveryJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 151:
        v154 = (CANQPQueryJob *)operator new(0x15B8u);
        if ( !v154 )
          goto LABEL_303;
        OidJob = CANQPQueryJob::CANQPQueryJob(v154, a1);
        goto LABEL_302;
      case 155:
        v156 = (CDot11RandomMacForScan *)operator new(0x12E0u);
        if ( !v156 )
          goto LABEL_303;
        OidJob = CDot11RandomMacForScan::CDot11RandomMacForScan(v156, a1);
        goto LABEL_302;
      case 156:
        v158 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v158;
        if ( !v158 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v158, a1);
        v10 = &CP2PEnableHrdssDevices::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 157:
      case 158:
        v157 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v157;
        if ( !v157 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v157, a1);
        v10 = &CGetAdapterCapabilitiesJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 159:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_151;
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          12,
          (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids);
        v98 = -1073741637;
        goto LABEL_306;
      case 161:
        v161 = (CIhvTaskRequestJob *)operator new(0x420u);
        if ( !v161 )
          goto LABEL_303;
        OidJob = CIhvTaskRequestJob::CIhvTaskRequestJob(v161, a1);
        goto LABEL_302;
      case 162:
        v32 = (CDeviceCommandOidJobBase *)operator new(0x450u);
        Pool2 = v32;
        if ( !v32 )
          goto LABEL_303;
        CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(v32, a1);
        *((_QWORD *)Pool2 + 137) = 0;
        *(_QWORD *)Pool2 = &CSetFTReassociationParametersJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 166:
        v159 = (CSimpleSetDeviceCommandOidJob *)operator new(0x460u);
        Pool2 = v159;
        if ( !v159 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v159, a1, v160);
        *(_QWORD *)Pool2 = &CSetEndDwellOnChannel::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 167:
        v56 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v56;
        if ( !v56 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v56, a1);
        v10 = &CRoamOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 171:
        v162 = (CSimpleQueryDeviceCommandOidJob *)operator new(0x330u);
        Pool2 = v162;
        if ( !v162 )
          goto LABEL_303;
        CSimpleQueryDeviceCommandOidJob::CSimpleQueryDeviceCommandOidJob(v162, a1);
        *(_QWORD *)Pool2 = &CGetSupportedDeviceServicesJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 172:
        v163 = (CSimpleMethodDeviceCommandOidJob *)operator new(0x338u);
        Pool2 = v163;
        if ( !v163 )
          goto LABEL_303;
        CSimpleMethodDeviceCommandOidJob::CSimpleMethodDeviceCommandOidJob(v163, a1);
        *(_QWORD *)Pool2 = &CDeviceServiceCommandJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 173:
        v164 = (CSimpleMethodDeviceCommandOidJob *)operator new(0x338u);
        Pool2 = v164;
        if ( !v164 )
          goto LABEL_303;
        CSimpleMethodDeviceCommandOidJob::CSimpleMethodDeviceCommandOidJob(v164, a1);
        *(_QWORD *)Pool2 = &CGetCipherKey::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 174:
        v165 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v165;
        if ( !v165 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v165, a1);
        v10 = &CSetLimitedDisruptionModeJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 175:
        v166 = (CSimpleSetOidJob *)operator new(0x550u);
        Pool2 = v166;
        if ( !v166 )
          goto LABEL_303;
        CConnectionQualityOidJob::CConnectionQualityOidJob(v166, a1, 3, 141, 133);
        *(_QWORD *)Pool2 = &CSetHighChannelAvailabilityModeJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 176:
        v33 = (CDeviceCommandOidJobBase *)operator new(0x510u);
        Pool2 = v33;
        if ( !v33 )
          goto LABEL_303;
        CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(v33, a1);
        *(_QWORD *)Pool2 = &CSetSAEAuthParamsJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        _WDI_SET_SAE_AUTH_PARAMS_COMMAND::_WDI_SET_SAE_AUTH_PARAMS_COMMAND((CSimpleSetOidJob *)((char *)Pool2 + 1096));
        *((_QWORD *)Pool2 + 161) = 0;
        goto LABEL_330;
      case 177:
        v167 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v167;
        if ( !v167 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v167, a1);
        v10 = &CP2PFlushBssEntryJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 178:
        v155 = (CRequestFtmJob *)operator new(0x820u);
        if ( !v155 )
          goto LABEL_303;
        OidJob = CRequestFtmJob::CRequestFtmJob(v155, a1);
        goto LABEL_302;
      case 182:
        v34 = (COidJobBase *)operator new(0x308u);
        Pool2 = v34;
        if ( !v34 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v34, a1);
        *(_QWORD *)Pool2 = &CSetOWEAuthParamsJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        DeviceCommand::DeviceCommand((CSimpleSetOidJob *)((char *)Pool2 + 576), a1);
        *((_BYTE *)Pool2 + 760) = 0;
        *((_DWORD *)Pool2 + 191) = 0;
        *((_QWORD *)Pool2 + 96) = 0;
        goto LABEL_330;
      case 183:
        v120 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v120;
        if ( !v120 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v120, a1);
        *((_QWORD *)Pool2 + 77) = 0;
        v10 = &CSetNwfPMKIDList::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 184:
        v168 = (COidJobBase *)operator new(0x268u);
        Pool2 = v168;
        if ( !v168 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v168, a1);
        v10 = &CGetBSSInfo::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_266;
      case 185:
        v169 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v169;
        if ( !v169 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v169, a1);
        v10 = &CGetLastScanUpdateTime::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 186:
        v172 = (CSimpleSetDeviceCommandOidJob *)operator new(0x458u);
        Pool2 = v172;
        if ( !v172 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v172, a1, v173);
        *(_QWORD *)Pool2 = &CSetLocationPrivacy::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        goto LABEL_330;
      case 187:
        v170 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v170;
        if ( !v170 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v170, a1);
        *((_BYTE *)Pool2 + 42) = 1;
        v10 = &CQueryWifiCxAdapterInfo::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 190:
        v171 = (COidJobBase *)operator new(0x340u);
        Pool2 = v171;
        if ( !v171 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v171, a1);
        *((_BYTE *)Pool2 + 580) = 0;
        v10 = &CCreateAdapterOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 201:
        v174 = (COidJobBase *)operator new(0x268u);
        Pool2 = v174;
        if ( !v174 )
          goto LABEL_303;
        COidJobBase::COidJobBase(v174, a1);
        v10 = &CGetConnectionInfoJob::`vftable'{for `IOperationCompletionCallback'};
LABEL_266:
        *((_QWORD *)Pool2 + 72) = 0;
        *((_QWORD *)Pool2 + 73) = 0;
        *((_QWORD *)Pool2 + 74) = 0;
        *((_QWORD *)Pool2 + 75) = 0;
        *((_QWORD *)Pool2 + 76) = 0;
        goto LABEL_329;
      case 202:
        v175 = (CSimpleSetDeviceCommandOidJob *)operator new(0x468u);
        Pool2 = v175;
        if ( !v175 )
          goto LABEL_303;
        CSimpleSetDeviceCommandOidJob::CSimpleSetDeviceCommandOidJob(v175, a1, v176);
        *(_QWORD *)Pool2 = &CSetMloKeysJob::`vftable'{for `IOperationCompletionCallback'};
        *((_QWORD *)Pool2 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
        *((_QWORD *)Pool2 + 139) = 0;
        *((_DWORD *)Pool2 + 280) = 0;
        goto LABEL_330;
      case 204:
        v177 = (CSimpleSetOidJob *)operator new(0x268u);
        Pool2 = v177;
        if ( !v177 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v177, a1);
        v10 = &QoS::CSetDSCPToUPMappingAllowedJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 205:
        v178 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v178;
        if ( !v178 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v178, a1);
        v10 = &QoS::CQueryQoSInfo::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 207:
        v179 = (CSimpleQueryOidJob *)operator new(0x268u);
        Pool2 = v179;
        if ( !v179 )
          goto LABEL_303;
        CSimpleQueryOidJob::CSimpleQueryOidJob(v179, a1);
        v10 = &CGetFipsCapabilitiesJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 208:
        v180 = (CSimpleSetOidJob *)operator new(0x270u);
        Pool2 = v180;
        if ( !v180 )
          goto LABEL_303;
        CSimpleSetOidJob::CSimpleSetOidJob(v180, a1);
        *((_DWORD *)Pool2 + 154) = 137;
        v10 = &CSimplePropertyCacheBooleanSetOidJob::`vftable'{for `IOperationCompletionCallback'};
        goto LABEL_329;
      case 210:
        if ( !(unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_290;
        v181 = (wificx::authentication_frame::SetAuthenticationFrameSubscriptionJob *)operator new(0x460u);
        if ( !v181 )
          goto LABEL_303;
        OidJob = (CSetWFDStopBackgroundDiscovery *)wificx::authentication_frame::SetAuthenticationFrameSubscriptionJob::SetAuthenticationFrameSubscriptionJob(
                                                     v181,
                                                     a1);
        goto LABEL_302;
      case 211:
LABEL_290:
        if ( !(unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline() || v3 != 211 )
          goto LABEL_294;
        v182 = (wificx::authentication_frame::SendAuthenticationFrameJob *)operator new(0x430u);
        if ( !v182 )
          goto LABEL_303;
        OidJob = (CSetWFDStopBackgroundDiscovery *)wificx::authentication_frame::SendAuthenticationFrameJob::SendAuthenticationFrameJob(
                                                     v182,
                                                     a1);
        goto LABEL_302;
      case 212:
LABEL_294:
        if ( !(unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline() || v3 != 212 )
          goto LABEL_298;
        v183 = (wlan::wfd2::SetDeviceCapabilitiesAndIdentityJob *)operator new(0x560u);
        if ( !v183 )
          goto LABEL_303;
        OidJob = (CSetWFDStopBackgroundDiscovery *)wlan::wfd2::SetDeviceCapabilitiesAndIdentityJob::SetDeviceCapabilitiesAndIdentityJob(
                                                     v183,
                                                     a1);
        goto LABEL_302;
      default:
        LODWORD(v6) = v7;
LABEL_298:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_151:
          v98 = -1073741637;
        }
        else
        {
          LOBYTE(v6) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v6,
            1,
            13,
            (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
            v3);
          v98 = -1073741637;
        }
        goto LABEL_306;
    }
    goto LABEL_303;
  }
LABEL_300:
  v184 = (CEnumBSSListJob *)operator new(0x580u);
  if ( v184 )
  {
    OidJob = CEnumBSSListJob::CEnumBSSListJob(v184, a1);
LABEL_302:
    Pool2 = OidJob;
    if ( OidJob )
      goto LABEL_330;
  }
LABEL_303:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v188) = v3;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      14,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      v188);
  }
  v98 = -1073741670;
LABEL_306:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v188) = v98;
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      15,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      v188);
  }
  return v98;
}

```

## disassembly

```asm
0x1400072a0  mov     rax, rsp
0x1400072a3  push    rdi
0x1400072a4  push    r12
0x1400072a6  sub     rsp, 0B8h
0x1400072ad  mov     [rax+10h], rbp
0x1400072b1  mov     edi, edx
0x1400072b3  mov     [rax-18h], rsi
0x1400072b7  mov     ebp, ecx
0x1400072b9  mov     [rax-20h], r14
0x1400072bd  mov     rsi, r8
0x1400072c0  mov     [rax-28h], r15
0x1400072c4  lea     r15, WPP_RECORDER_INITIALIZED
0x1400072cb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400072d2  lea     r12, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x1400072d9  jz      short loc_14000730B
0x1400072db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072e2  cmp     byte ptr [rcx+29h], 5
0x1400072e6  jnb     short loc_1400072EF
0x1400072e8  cmp     word ptr [rcx+48h], 0
0x1400072ed  jz      short loc_14000730B
0x1400072ef  mov     rcx, [rcx+40h]
0x1400072f3  mov     r9d, 0Ah
0x1400072f9  mov     r8d, 1
0x1400072ff  mov     qword ptr [rsp+0C8h+var_A8], r12
0x140007304  mov     dl, 5
0x140007306  call    WPP_RECORDER_SF_
0x14000730b  xor     r14d, r14d
0x14000730e  mov     [rsp+0C8h+arg_0], rbx
0x140007316  cmp     edi, 57h ; 'W'
0x140007319  jz      loc_1400091C9
0x14000731f  cmp     edi, 8Bh
0x140007325  jz      loc_1400090FC; jumptable 0000000140007354 case 40
0x14000732b  lea     eax, [rdi-1]; switch 212 cases
0x14000732e  cmp     eax, 0D3h
0x140007333  ja      def_140007354; jumptable 0000000140007354 default case, cases 3-15,19-21,58,62-64,70,87,89-91,112,113,134,135,139,142,145,146,148,150,152-154,160,163-165,168,169,179-181,188,189,191-200,203,206,209
0x140007339  lea     rdx, cs:140000000h
0x140007340  cdqe
0x140007342  movzx   eax, ds:(byte_140103E08 - 140000000h)[rdx+rax]
0x14000734a  mov     ecx, ds:(jpt_140007354 - 140000000h)[rdx+rax*4]
0x140007351  add     rcx, rdx
0x140007354  jmp     rcx; switch jump
0x14000735a  mov     ecx, 268h; jumptable 0000000140007354 case 1
0x14000735f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007364  mov     rbx, rax
0x140007367  test    rax, rax
0x14000736a  jz      loc_140009121
0x140007370  mov     edx, ebp; unsigned int
0x140007372  mov     rcx, rax; this
0x140007375  call    ??0CSimpleSetOidJob@@QEAA@K@Z; CSimpleSetOidJob::CSimpleSetOidJob(ulong)
0x14000737a  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x140007381  lea     rcx, ??_7CDummySetJob@@6BIOperationCompletionCallback@@@; const CDummySetJob::`vftable'{for `IOperationCompletionCallback'}
0x140007388  jmp     loc_140009400
0x14000738d  mov     ecx, 268h; jumptable 0000000140007354 case 2
0x140007392  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007397  mov     rbx, rax
0x14000739a  test    rax, rax
0x14000739d  jz      loc_140009121
0x1400073a3  mov     edx, ebp; unsigned int
0x1400073a5  mov     rcx, rax; this
0x1400073a8  call    ??0CSimpleQueryOidJob@@QEAA@K@Z; CSimpleQueryOidJob::CSimpleQueryOidJob(ulong)
0x1400073ad  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400073b4  lea     rcx, ??_7CDummyQueryReturnTrueJob@@6BIOperationCompletionCallback@@@; const CDummyQueryReturnTrueJob::`vftable'{for `IOperationCompletionCallback'}
0x1400073bb  jmp     loc_140009400
0x1400073c0  mov     ecx, 0CC8h; jumptable 0000000140007354 case 16
0x1400073c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400073ca  test    rax, rax
0x1400073cd  jz      loc_140009121
0x1400073d3  mov     edx, ebp; unsigned int
0x1400073d5  mov     rcx, rax; this
0x1400073d8  call    ??0CDot11ResetJob@@QEAA@K@Z; CDot11ResetJob::CDot11ResetJob(ulong)
0x1400073dd  jmp     loc_140009115
0x1400073e2  mov     ecx, 268h; jumptable 0000000140007354 case 17
0x1400073e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400073ec  mov     rbx, rax
0x1400073ef  test    rax, rax
0x1400073f2  jz      loc_140009121
0x1400073f8  mov     edx, ebp; unsigned int
0x1400073fa  mov     rcx, rax; this
0x1400073fd  call    ??0CSimpleQueryOidJob@@QEAA@K@Z; CSimpleQueryOidJob::CSimpleQueryOidJob(ulong)
0x140007402  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x140007409  lea     rcx, ??_7CQueryOperationModeJob@@6BIOperationCompletionCallback@@@; const CQueryOperationModeJob::`vftable'{for `IOperationCompletionCallback'}
0x140007410  jmp     loc_140009400
0x140007415  mov     ecx, 430h; jumptable 0000000140007354 case 18
0x14000741a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000741f  mov     rbx, rax
0x140007422  test    rax, rax
0x140007425  jz      loc_140009121
0x14000742b  mov     edx, ebp; unsigned int
0x14000742d  mov     rcx, rax; this
0x140007430  call    ??0COidJobBase@@QEAA@K@Z; COidJobBase::COidJobBase(ulong)
0x140007435  lea     rcx, ??_7CSetOperationModeJob@@6BIOperationCompletionCallback@@@; const CSetOperationModeJob::`vftable'{for `IOperationCompletionCallback'}
0x14000743c  mov     edx, ebp; unsigned int
0x14000743e  mov     [rbx], rcx
0x140007441  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x140007448  lea     rcx, [rbx+248h]; this
0x14000744f  mov     [rbx+8], rax
0x140007453  call    ??0Task@@QEAA@K@Z; Task::Task(ulong)
0x140007458  mov     [rbx+420h], r14
0x14000745f  jmp     loc_140009407
0x140007464  mov     ecx, 270h; jumptable 0000000140007354 case 27
0x140007469  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000746e  mov     rbx, rax
0x140007471  test    rax, rax
0x140007474  jz      loc_140009121
0x14000747a  mov     edx, ebp; unsigned int
0x14000747c  mov     rcx, rax; this
0x14000747f  call    ??0CSimpleQueryOidJob@@QEAA@K@Z; CSimpleQueryOidJob::CSimpleQueryOidJob(ulong)
0x140007484  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x14000748b  mov     dword ptr [rbx+268h], 1Bh
0x140007495  lea     rcx, ??_7CSimplePropertyCacheULongQueryOidJob@@6BIOperationCompletionCallback@@@; const CSimplePropertyCacheULongQueryOidJob::`vftable'{for `IOperationCompletionCallback'}
0x14000749c  jmp     loc_140009400
0x1400074a1  mov     ecx, 278h; jumptable 0000000140007354 case 28
0x1400074a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400074ab  mov     rbx, rax
0x1400074ae  test    rax, rax
0x1400074b1  jz      loc_140009121
0x1400074b7  mov     edx, 1Bh; unsigned int
0x1400074bc  mov     [rsp+0C8h+var_A8], ebp; unsigned int
0x1400074c0  mov     r9d, 2; unsigned int
0x1400074c6  mov     r8d, 1; unsigned int
0x1400074cc  mov     rcx, rax; this
0x1400074cf  call    ??0CSimplePropertyCacheULongSetOidJob@@QEAA@KKKK@Z; CSimplePropertyCacheULongSetOidJob::CSimplePropertyCacheULongSetOidJob(ulong,ulong,ulong,ulong)
0x1400074d4  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400074db  lea     rcx, ??_7CSetDesirerdBssTypeJob@@6BIOperationCompletionCallback@@@; const CSetDesirerdBssTypeJob::`vftable'{for `IOperationCompletionCallback'}
0x1400074e2  jmp     loc_140009400
0x1400074e7  mov     ecx, 280h; jumptable 0000000140007354 case 29
0x1400074ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400074f1  test    rax, rax
0x1400074f4  jz      loc_140009121
0x1400074fa  mov     [rsp+0C8h+var_80], ebp; unsigned int
0x1400074fe  mov     edx, 7; unsigned int
0x140007503  mov     [rsp+0C8h+var_88], 4; unsigned int
0x14000750b  mov     rcx, rax; this
0x14000750e  mov     qword ptr [rsp+0C8h+var_A8], 10h; __int16
0x140007517  call    ??0CSimplePropertyCacheListQueryOidJob@@QEAA@KEE_KKKKKK@Z; CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(ulong,uchar,uchar,unsigned __int64,ulong,ulong,ulong,ulong,ulong)
0x14000751c  jmp     loc_140009115
0x140007521  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline; jumptable 0000000140007354 case 30
0x140007526  mov     ecx, 288h; unsigned __int64
0x14000752b  test    eax, eax
0x14000752d  jz      short loc_140007574
0x14000752f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007534  test    rax, rax
0x140007537  jz      loc_140009121
0x14000753d  mov     [rsp+0C8h+var_70], ebp; unsigned int
0x140007541  mov     [rsp+0C8h+var_78], 5; unsigned int
0x140007549  mov     edx, 7; unsigned int
0x14000754e  mov     [rsp+0C8h+var_80], 1; unsigned int
0x140007556  mov     [rsp+0C8h+var_88], 4; unsigned int
0x14000755e  mov     qword ptr [rsp+0C8h+var_A8], 10h; __int16
0x140007567  mov     rcx, rax; this
0x14000756a  call    ??0CSimplePropertyCacheListSetOidJob@@QEAA@KEE_KKKKKKKK@Z; CSimplePropertyCacheListSetOidJob::CSimplePropertyCacheListSetOidJob(ulong,uchar,uchar,unsigned __int64,ulong,ulong,ulong,ulong,ulong,ulong,ulong)
0x14000756f  jmp     loc_140009115
0x140007574  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007579  test    rax, rax
0x14000757c  jz      loc_140009121
0x140007582  mov     [rsp+0C8h+var_70], ebp
0x140007586  mov     [rsp+0C8h+var_78], 2
0x14000758e  jmp     short loc_140007549
0x140007590  mov     ecx, 280h; jumptable 0000000140007354 case 32
0x140007595  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000759a  test    rax, rax
0x14000759d  jz      loc_140009121
0x1400075a3  mov     [rsp+0C8h+var_80], ebp; unsigned int
0x1400075a7  mov     edx, 8; unsigned int
0x1400075ac  mov     [rsp+0C8h+var_88], 4; unsigned int
0x1400075b4  mov     rcx, rax; this
0x1400075b7  mov     qword ptr [rsp+0C8h+var_A8], 10h; __int16
0x1400075c0  call    ??0CSimplePropertyCacheListQueryOidJob@@QEAA@KEE_KKKKKK@Z; CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(ulong,uchar,uchar,unsigned __int64,ulong,ulong,ulong,ulong,ulong)
0x1400075c5  jmp     loc_140009115
0x1400075ca  mov     ecx, 288h; jumptable 0000000140007354 case 33
0x1400075cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400075d4  test    rax, rax
0x1400075d7  jz      loc_140009121
0x1400075dd  mov     [rsp+0C8h+var_70], ebp
0x1400075e1  mov     edx, 8
0x1400075e6  mov     [rsp+0C8h+var_78], 100h
0x1400075ee  mov     [rsp+0C8h+var_80], r14d
0x1400075f3  jmp     loc_140007556
0x1400075f8  mov     ecx, 280h; jumptable 0000000140007354 case 34
0x1400075fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007602  test    rax, rax
0x140007605  jz      loc_140009121
0x14000760b  mov     [rsp+0C8h+var_80], ebp; unsigned int
0x14000760f  mov     edx, 9; unsigned int
0x140007614  mov     [rsp+0C8h+var_88], 4; unsigned int
0x14000761c  mov     rcx, rax; this
0x14000761f  mov     qword ptr [rsp+0C8h+var_A8], 10h; __int16
0x140007628  call    ??0CSimplePropertyCacheListQueryOidJob@@QEAA@KEE_KKKKKK@Z; CSimplePropertyCacheListQueryOidJob::CSimplePropertyCacheListQueryOidJob(ulong,uchar,uchar,unsigned __int64,ulong,ulong,ulong,ulong,ulong)
0x14000762d  jmp     loc_140009115
0x140007632  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline; jumptable 0000000140007354 case 35
0x140007637  mov     ecx, 288h; unsigned __int64
0x14000763c  test    eax, eax
0x14000763e  jz      short loc_140007664
0x140007640  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007645  test    rax, rax
0x140007648  jz      loc_140009121
0x14000764e  mov     [rsp+0C8h+var_70], ebp
0x140007652  mov     [rsp+0C8h+var_78], 5
0x14000765a  mov     edx, 9
0x14000765f  jmp     loc_14000754E
0x140007664  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007669  test    rax, rax
0x14000766c  jz      loc_140009121
0x140007672  mov     [rsp+0C8h+var_70], ebp
0x140007676  mov     [rsp+0C8h+var_78], 2
0x14000767e  jmp     short loc_14000765A
0x140007680  mov     ecx, 268h; jumptable 0000000140007354 case 31
0x140007685  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000768a  mov     rbx, rax
0x14000768d  test    rax, rax
0x140007690  jz      loc_140009121
0x140007696  mov     edx, ebp; unsigned int
0x140007698  mov     rcx, rax; this
0x14000769b  call    ??0CSimpleSetOidJob@@QEAA@K@Z; CSimpleSetOidJob::CSimpleSetOidJob(ulong)
0x1400076a0  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400076a7  lea     rcx, ??_7CSetFTParametersJob@@6BIOperationCompletionCallback@@@; const CSetFTParametersJob::`vftable'{for `IOperationCompletionCallback'}
0x1400076ae  jmp     loc_140009400
0x1400076b3  mov     ecx, 450h; jumptable 0000000140007354 case 162
0x1400076b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400076bd  mov     rbx, rax
0x1400076c0  test    rax, rax
0x1400076c3  jz      loc_140009121
0x1400076c9  mov     edx, ebp; unsigned int
0x1400076cb  mov     rcx, rax; this
0x1400076ce  call    ??0CDeviceCommandOidJobBase@@QEAA@K@Z; CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(ulong)
0x1400076d3  lea     rax, ??_7CSetFTReassociationParametersJob@@6BIOperationCompletionCallback@@@; const CSetFTReassociationParametersJob::`vftable'{for `IOperationCompletionCallback'}
0x1400076da  mov     [rbx+448h], r14
0x1400076e1  mov     [rbx], rax
0x1400076e4  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400076eb  mov     [rbx+8], rax
0x1400076ef  jmp     loc_140009407
0x1400076f4  mov     ecx, 510h; jumptable 0000000140007354 case 176
0x1400076f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400076fe  mov     rbx, rax
0x140007701  test    rax, rax
0x140007704  jz      loc_140009121
0x14000770a  mov     edx, ebp; unsigned int
0x14000770c  mov     rcx, rax; this
0x14000770f  call    ??0CDeviceCommandOidJobBase@@QEAA@K@Z; CDeviceCommandOidJobBase::CDeviceCommandOidJobBase(ulong)
0x140007714  lea     rax, ??_7CSetSAEAuthParamsJob@@6BIOperationCompletionCallback@@@; const CSetSAEAuthParamsJob::`vftable'{for `IOperationCompletionCallback'}
0x14000771b  mov     [rbx], rax
0x14000771e  lea     rcx, [rbx+448h]; this
0x140007725  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x14000772c  mov     [rbx+8], rax
0x140007730  call    ??0_WDI_SET_SAE_AUTH_PARAMS_COMMAND@@QEAA@XZ; _WDI_SET_SAE_AUTH_PARAMS_COMMAND::_WDI_SET_SAE_AUTH_PARAMS_COMMAND(void)
0x140007735  mov     [rbx+508h], r14
0x14000773c  jmp     loc_140009407
0x140007741  mov     ecx, 308h; jumptable 0000000140007354 case 182
0x140007746  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000774b  mov     rbx, rax
0x14000774e  test    rax, rax
0x140007751  jz      loc_140009121
0x140007757  mov     edx, ebp; unsigned int
0x140007759  mov     rcx, rax; this
0x14000775c  call    ??0COidJobBase@@QEAA@K@Z; COidJobBase::COidJobBase(ulong)
0x140007761  lea     rcx, ??_7CSetOWEAuthParamsJob@@6BIOperationCompletionCallback@@@; const CSetOWEAuthParamsJob::`vftable'{for `IOperationCompletionCallback'}
0x140007768  mov     edx, ebp; unsigned int
0x14000776a  mov     [rbx], rcx
0x14000776d  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x140007774  lea     rcx, [rbx+240h]; this
0x14000777b  mov     [rbx+8], rax
0x14000777f  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x140007784  mov     [rbx+2F8h], r14b
0x14000778b  mov     [rbx+2FCh], r14d
0x140007792  mov     [rbx+300h], r14
0x140007799  jmp     loc_140009407
0x14000779e  mov     ecx, 268h; jumptable 0000000140007354 case 36
0x1400077a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400077a8  mov     rbx, rax
0x1400077ab  test    rax, rax
0x1400077ae  jz      loc_140009121
0x1400077b4  mov     edx, ebp; unsigned int
0x1400077b6  mov     rcx, rax; this
0x1400077b9  call    ??0CSimpleQueryOidJob@@QEAA@K@Z; CSimpleQueryOidJob::CSimpleQueryOidJob(ulong)
0x1400077be  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400077c5  lea     rcx, ??_7CQueryPhyIdJob@@6BIOperationCompletionCallback@@@; const CQueryPhyIdJob::`vftable'{for `IOperationCompletionCallback'}
0x1400077cc  jmp     loc_140009400
0x1400077d1  mov     ecx, 268h; jumptable 0000000140007354 case 37
0x1400077d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400077db  mov     rbx, rax
0x1400077de  test    rax, rax
0x1400077e1  jz      loc_140009121
0x1400077e7  mov     edx, ebp; unsigned int
0x1400077e9  mov     rcx, rax; this
0x1400077ec  call    ??0CSimpleSetOidJob@@QEAA@K@Z; CSimpleSetOidJob::CSimpleSetOidJob(ulong)
0x1400077f1  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x1400077f8  lea     rcx, ??_7CSetPhyIdJob@@6BIOperationCompletionCallback@@@; const CSetPhyIdJob::`vftable'{for `IOperationCompletionCallback'}
0x1400077ff  jmp     loc_140009400
0x140007804  mov     ecx, 268h; jumptable 0000000140007354 case 50
0x140007809  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000780e  mov     rbx, rax
0x140007811  test    rax, rax
0x140007814  jz      loc_140009121
0x14000781a  mov     edx, ebp; unsigned int
0x14000781c  mov     rcx, rax; this
0x14000781f  call    ??0CSimpleQueryOidJob@@QEAA@K@Z; CSimpleQueryOidJob::CSimpleQueryOidJob(ulong)
0x140007824  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x14000782b  lea     rcx, ??_7CQueryOperationalRateSet@@6BIOperationCompletionCallback@@@; const CQueryOperationalRateSet::`vftable'{for `IOperationCompletionCallback'}
0x140007832  jmp     loc_140009400
0x140007837  mov     ecx, 7C8h; jumptable 0000000140007354 case 38
  ... truncated ...
```
