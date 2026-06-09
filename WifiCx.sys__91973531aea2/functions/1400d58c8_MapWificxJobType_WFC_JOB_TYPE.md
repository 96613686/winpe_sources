# MapWificxJobType(_WFC_JOB_TYPE)

- ea: `0x1400d58c8`
- end: `0x1400d65fa`
- name: `?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z`
- size: `3378`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400d76a0`
- `0x1400d7b40`
- `0x1400d7e58`

## callees

- `0x1400d58c8`

## string_xrefs

- `0x1400d59b1`: `WiFiJobCreatePort`
- `0x1400d59a8`: `WiFiJobDeletePort`
- `0x1400d5bb5`: `WiFiJobQueryDesiredSSIDList`
- `0x1400d5bac`: `WiFiJobSetDesiredSSIDList`
- `0x1400d5ba3`: `WiFiJobQueryDesiredHESSIDList`
- `0x1400d5b9a`: `WiFiJobSetDesiredHESSIDList`
- `0x1400d5c7c`: `WiFiJobQueryDesiredBSSIDList`
- `0x1400d5c73`: `WiFiJobSetDesiredBSSIDList`
- `0x1400d5cdd`: `WiFiJobCreateMac`
- `0x1400d5cd4`: `WiFiJobDeleteMac`
- `0x1400d5d4e`: `WiFiJobQueryHardwareAddress`
- `0x1400d5d98`: `WiFiJobQueryAutoConfigEnabled`
- `0x1400d5d8f`: `WiFiJobSetAutoConfigEnabled`
- `0x1400d6176`: `WiFiJobP2PGetDialogToken`
- `0x1400d61da`: `WiFiJobNicSpecificExtension`
- `0x1400d6240`: `WiFiJobUpdateBSSList`
- `0x1400d621c`: `WiFiJobQueryTcpOffloadVirtualPortConfig`
- `0x1400d6249`: `WiFiJobUpdateConnectionQuality`
- `0x1400d632b`: `WiFiJobIhvTaskRequest`
- `0x1400d6374`: `WiFiJobGetSupportedDeviceServices`
- `0x1400d636b`: `WiFiJobDeviceServiceCommand`
- `0x1400d6439`: `WiFiJobGetLastScanUpdateTime`
- `0x1400d64c4`: `WiFiJobCreateAdapter`
- `0x1400d64a9`: `WiFiJobDevicePrepareForSystemPowerTargetToSxState`
- `0x1400d6523`: `WiFiJobNetAdapterAddProtocolOffload`
- `0x1400d651a`: `WiFiJobNetAdapterRemoveProtocolOffload`
- `0x1400d6508`: `WiFiJobNetAdapterUpdateProtocolOffloadEnabledFields`
- `0x1400d6535`: `WiFiJobDevicePreDisarmHandleProtocolOffloads`
- `0x1400d6573`: `WiFiJobGetDataPathWakeReason`
- `0x1400d65ce`: `WiFiJobRemoveStalePowerOffloadsJob`

## pseudocode

```c
const wchar_t *__fastcall MapWificxJobType(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  int v58; // ecx
  int v59; // ecx
  int v60; // ecx
  int v61; // ecx
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  int v66; // ecx
  int v67; // ecx
  int v68; // ecx
  int v69; // ecx
  int v70; // ecx
  int v71; // ecx
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  int v76; // ecx
  int v77; // ecx
  int v78; // ecx
  int v79; // ecx
  int v80; // ecx
  int v81; // ecx
  int v82; // ecx
  int v83; // ecx
  int v84; // ecx
  int v85; // ecx
  int v86; // ecx
  int v87; // ecx
  int v88; // ecx
  int v89; // ecx
  int v90; // ecx
  int v91; // ecx
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  int v95; // ecx
  int v96; // ecx
  int v97; // ecx
  int v98; // ecx
  int v99; // ecx
  int v100; // ecx
  int v101; // ecx
  int v102; // ecx
  int v103; // ecx
  int v104; // ecx
  int v105; // ecx
  int v106; // ecx
  int v107; // ecx
  int v108; // ecx
  int v109; // ecx
  int v110; // ecx
  int v111; // ecx
  int v112; // ecx
  int v113; // ecx
  int v114; // ecx
  int v115; // ecx
  int v116; // ecx
  int v117; // ecx
  int v118; // ecx
  int v119; // ecx
  int v120; // ecx
  int v121; // ecx
  int v122; // ecx
  int v123; // ecx
  int v124; // ecx
  int v125; // ecx
  int v126; // ecx
  int v127; // ecx
  int v128; // ecx
  int v129; // ecx
  int v130; // ecx
  int v131; // ecx
  int v132; // ecx
  int v133; // ecx
  int v134; // ecx
  int v135; // ecx
  int v136; // ecx
  int v137; // ecx
  int v138; // ecx
  int v139; // ecx
  int v140; // ecx
  int v141; // ecx
  int v142; // ecx
  int v143; // ecx
  int v144; // ecx
  int v145; // ecx
  int v146; // ecx
  int v147; // ecx
  int v148; // ecx
  int v149; // ecx
  int v150; // ecx

  if ( a1 <= 106 )
  {
    if ( a1 == 106 )
      return L"WiFiJobQuerySafeModeEnabled";
    if ( a1 > 53 )
    {
      if ( a1 > 80 )
      {
        if ( a1 > 93 )
        {
          if ( a1 > 100 )
          {
            v72 = a1 - 101;
            if ( !v72 )
              return L"WiFiJobQueryRegDomainsSupportValue";
            v73 = v72 - 1;
            if ( !v73 )
              return L"WiFiJobQueryUnreachableDetectionThreshold";
            v74 = v73 - 1;
            if ( !v74 )
              return L"WiFiJobSetUnreachableDetectionThreshold";
            v75 = v74 - 1;
            if ( !v75 )
              return L"WiFiJobQueryIBSSParams";
            if ( v75 == 1 )
              return L"WiFiJobSetIBSSParams";
          }
          else
          {
            if ( a1 == 100 )
              return L"WiFiJobSetCurrentFrequency";
            v67 = a1 - 94;
            if ( !v67 )
              return L"WiFiJobQueryFragmentationThreshold";
            v68 = v67 - 1;
            if ( !v68 )
              return L"WiFiJobSetFragmentationThreshold";
            v69 = v68 - 1;
            if ( !v69 )
              return L"WiFiJobQueryCurrentRegDomain";
            v70 = v69 - 1;
            if ( !v70 )
              return L"WiFiJobQueryCurrentChannel";
            v71 = v70 - 1;
            if ( !v71 )
              return L"WiFiJobSetCurrentChannel";
            if ( v71 == 1 )
              return L"WiFiJobQueryCurrentFrequency";
          }
        }
        else
        {
          if ( a1 == 93 )
            return L"WiFiJobSetRTSThreshold";
          if ( a1 > 87 )
          {
            v63 = a1 - 88;
            if ( !v63 )
              return L"WiFiJobSetUnicastUseGroupEnable";
            v64 = v63 - 1;
            if ( !v64 )
              return L"WiFiJobQueryVendorDescription";
            v65 = v64 - 1;
            if ( !v65 )
              return L"WiFiJobQueryVendorDriverVersion";
            v66 = v65 - 1;
            if ( !v66 )
              return L"WiFiJobQueryVendorID";
            if ( v66 == 1 )
              return L"WiFiJobQueryRTSThreshold";
          }
          else
          {
            if ( a1 == 87 )
              return L"WiFiJobQueryUnicastUseGroupEnabled";
            v58 = a1 - 81;
            if ( !v58 )
              return L"WiFiJobQueryExcludedMacAddressList";
            v59 = v58 - 1;
            if ( !v59 )
              return L"WiFiJobSetExcludedMacAddressList";
            v60 = v59 - 1;
            if ( !v60 )
              return L"WiFiJobQueryPMKIDList";
            v61 = v60 - 1;
            if ( !v61 )
              return L"WiFiJobSetPMKIDList";
            v62 = v61 - 1;
            if ( !v62 )
              return L"WiFiJobQuerySupportedMulticastAlgorithmPair";
            if ( v62 == 1 )
              return L"WiFiJobQuerySupportedUnicastAlgorithmPair";
          }
        }
      }
      else
      {
        if ( a1 == 80 )
          return L"WiFiJobSetDesiredPhyList";
        if ( a1 > 67 )
        {
          if ( a1 > 74 )
          {
            v54 = a1 - 75;
            if ( !v54 )
              return L"WiFiJobQueryDefaultKeyId";
            v55 = v54 - 1;
            if ( !v55 )
              return L"WiFiJobQueryActivePhyList";
            v56 = v55 - 1;
            if ( !v56 )
              return L"WiFiJobQueryAutoConfigEnabled";
            v57 = v56 - 1;
            if ( !v57 )
              return L"WiFiJobSetAutoConfigEnabled";
            if ( v57 == 1 )
              return L"WiFiJobQueryDesiredPhyList";
          }
          else
          {
            if ( a1 == 74 )
              return L"WiFiJobQueryPrivacyExemptionList";
            v49 = a1 - 68;
            if ( !v49 )
              return L"WiFiJobQueryMacAddress";
            v50 = v49 - 1;
            if ( !v50 )
              return L"WiFiJobQueryHardwareAddress";
            v51 = v50 - 1;
            if ( !v51 )
              return L"WiFiJobSetOperationalRateSet";
            v52 = v51 - 1;
            if ( !v52 )
              return L"WiFiJobQueryMediaStreamingEnabled";
            v53 = v52 - 1;
            if ( !v53 )
              return L"WiFiJobSetMediaStreamingEnabled";
            if ( v53 == 1 )
              return L"WiFiJobQueryHardwarePhyState";
          }
        }
        else
        {
          if ( a1 == 67 )
            return L"WiFiJobQueryOperationModeCapability";
          if ( a1 > 60 )
          {
            v44 = a1 - 61;
            if ( !v44 )
              return L"WiFiJobEnumAssociationInfo";
            v45 = v44 - 1;
            if ( !v45 )
              return L"WiFiJobRoam";
            v46 = v45 - 1;
            if ( !v46 )
              return L"WiFiJobCreateMac";
            v47 = v46 - 1;
            if ( !v47 )
              return L"WiFiJobDeleteMac";
            v48 = v47 - 1;
            if ( !v48 )
              return L"WiFiJobQueryNicPowerState";
            if ( v48 == 1 )
              return L"WiFiJobSetNicPowerState";
          }
          else
          {
            if ( a1 == 60 )
              return L"WiFiJobFlushBssList";
            v39 = a1 - 54;
            if ( !v39 )
              return L"WiFiJobSetDefaultKeyId";
            v40 = v39 - 1;
            if ( !v40 )
              return L"WiFiJobSetKeyMappingKey";
            v41 = v40 - 1;
            if ( !v41 )
              return L"WiFiJobQueryDesiredBSSIDList";
            v42 = v41 - 1;
            if ( !v42 )
              return L"WiFiJobSetDesiredBSSIDList";
            v43 = v42 - 1;
            if ( !v43 )
              return L"WiFiJobQueryStaAssociationIEs";
            if ( v43 == 1 )
              return L"WiFiJobSetStaAssociationIEs";
          }
        }
      }
    }
    else
    {
      if ( a1 == 53 )
        return L"WiFiJobSetDefaultKey";
      if ( a1 > 26 )
      {
        if ( a1 > 40 )
        {
          if ( a1 > 47 )
          {
            v35 = a1 - 48;
            if ( !v35 )
              return L"WiFiJobSetExcludeUnencrypted";
            v36 = v35 - 1;
            if ( !v36 )
              return L"WiFiJobConnectRequest";
            v37 = v36 - 1;
            if ( !v37 )
              return L"WiFiJobQueryOperationalRateSet";
            v38 = v37 - 1;
            if ( !v38 )
              return L"WiFiJobDisconnectRequest";
            if ( v38 == 1 )
              return L"WiFiJobSetPrivacyExemptionList";
          }
          else
          {
            if ( a1 == 47 )
              return L"WiFiJobQueryExcludeUnencrypted";
            v30 = a1 - 41;
            if ( !v30 )
              return L"WiFiJobQueryDesiredSSIDList";
            v31 = v30 - 1;
            if ( !v31 )
              return L"WiFiJobSetDesiredSSIDList";
            v32 = v31 - 1;
            if ( !v32 )
              return L"WiFiJobQueryDesiredHESSIDList";
            v33 = v32 - 1;
            if ( !v33 )
              return L"WiFiJobSetDesiredHESSIDList";
            v34 = v33 - 1;
            if ( !v34 )
              return L"WiFiJobQueryHiddenNetworkEnabled";
            if ( v34 == 1 )
              return L"WiFiJobSetHiddenNetworkEnabled";
          }
        }
        else
        {
          if ( a1 == 40 )
            return L"WiFiJobEnumBSSList";
          if ( a1 > 33 )
          {
            v25 = a1 - 34;
            if ( !v25 )
              return L"WiFiJobQueryEnabledUnicastCipherAlgo";
            v26 = v25 - 1;
            if ( !v26 )
              return L"WiFiJobSetEnabledUnicastCipherAlgo";
            v27 = v26 - 1;
            if ( !v27 )
              return L"WiFiJobQueryPhyId";
            v28 = v27 - 1;
            if ( !v28 )
              return L"WiFiJobSetPhyId";
            v29 = v28 - 1;
            if ( !v29 )
              return L"WiFiJobScan";
            if ( v29 == 1 )
              return L"WiFiJobScanOidRequest";
          }
          else
          {
            if ( a1 == 33 )
              return L"WiFiJobSetEnabledMulticastCipherAlgo";
            v20 = a1 - 27;
            if ( !v20 )
              return L"WiFiJobQueryDesiredBssType";
            v21 = v20 - 1;
            if ( !v21 )
              return L"WiFiJobSetDesiredBssType";
            v22 = v21 - 1;
            if ( !v22 )
              return L"WiFiJobQueryEnabledAuthAlgo";
            v23 = v22 - 1;
            if ( !v23 )
              return L"WiFiJobSetEnabledAuthAlgo";
            v24 = v23 - 1;
            if ( !v24 )
              return L"WiFiJobSetFTParameters";
            if ( v24 == 1 )
              return L"WiFiJobQueryEnabledMulticastCipherAlgo";
          }
        }
      }
      else
      {
        if ( a1 == 26 )
          return L"WiFiJobSetNlo";
        if ( a1 > 13 )
        {
          if ( a1 > 20 )
          {
            v16 = a1 - 21;
            if ( !v16 )
              return L"WiFiJobQueryPower";
            v17 = v16 - 1;
            if ( !v17 )
              return L"WiFiJobSetAutoPowerSave";
            v18 = v17 - 1;
            if ( !v18 )
              return L"WiFiJobGetAutoPowerSave";
            v19 = v18 - 1;
            if ( !v19 )
              return L"WiFiJobSetPowerMgmtRequest";
            if ( v19 == 1 )
              return L"WiFiJobGetPowerMgmtRequest";
          }
          else
          {
            if ( a1 == 20 )
              return L"WiFiJobSetPower";
            v11 = a1 - 14;
            if ( !v11 )
              return L"WiFiJobQueryDot11MulticastList";
            v12 = v11 - 1;
            if ( !v12 )
              return L"WiFiJobSetDot11MulticastList";
            v13 = v12 - 1;
            if ( !v13 )
              return L"WiFiJobDot11ResetPort";
            v14 = v13 - 1;
            if ( !v14 )
              return L"WiFiJobQueryOperationMode";
            v15 = v14 - 1;
            if ( !v15 )
              return L"WiFiJobSetOperationMode";
            if ( v15 == 1 )
              return L"WiFiJobTypeConnect";
          }
        }
        else
        {
          if ( a1 == 13 )
            return L"WiFiJobSet8023MulticastList";
          if ( a1 > 6 )
          {
            v6 = a1 - 7;
            if ( !v6 )
              return L"WiFiJobMiniportSurpriseRemoval";
            v7 = v6 - 1;
            if ( !v7 )
              return L"WiFiJobCreatePort";
            v8 = v7 - 1;
            if ( !v8 )
              return L"WiFiJobDeletePort";
            v9 = v8 - 1;
            if ( !v9 )
              return L"WiFiJobQuerySupportedGuids";
            v10 = v9 - 1;
            if ( !v10 )
              return L"WiFiJobSetPacketFilter";
            if ( v10 == 1 )
              return L"WiFiJobQuery8023MulticastList";
          }
          else
          {
            if ( a1 == 6 )
              return L"WiFiJobMiniportRestart";
            if ( !a1 )
              return L"WiFiJobTypeInvalid";
            v1 = a1 - 1;
            if ( !v1 )
              return L"WiFiJobOIDSetNotYetImplemented";
            v2 = v1 - 1;
            if ( !v2 )
              return L"WiFiJobOIDQueryNotYetImplemented";
            v3 = v2 - 1;
            if ( !v3 )
              return L"WiFiJobMiniportInitialize";
            v4 = v3 - 1;
            if ( !v4 )
              return L"WiFiJobMiniportHalt";
            if ( v4 == 1 )
              return L"WiFiJobMiniportPause";
          }
        }
      }
    }
    return L"WifiCxJobTypeUnknown";
  }
  if ( a1 <= 160 )
  {
    if ( a1 == 160 )
      return L"WiFiJobUnrecognizedOidHandler";
    if ( a1 > 133 )
    {
      if ( a1 > 147 )
      {
        if ( a1 > 154 )
        {
          v110 = a1 - 155;
          if ( !v110 )
            return L"WiFiJobRandomMacForScan";
          v111 = v110 - 1;
          if ( !v111 )
            return L"WiFiJobP2PEnableHrdssDevices";
          v112 = v111 - 1;
          if ( !v112 )
            return L"WiFiJobGetAdapterEnhancedCapabilities";
          v113 = v112 - 1;
          if ( !v113 )
            return L"WiFiJobGetAdapterBandCapabilities";
          if ( v113 == 1 )
            return L"WiFiJobGeneralStatistics";
        }
        else
        {
          if ( a1 == 154 )
            return L"WiFiJobUpdateConnectionQuality";
          v105 = a1 - 148;
          if ( !v105 )
            return L"WiFiJobUpdateBSSList";
          v106 = v105 - 1;
          if ( !v106 )
            return L"WiFiJobResetRecovery";
          v107 = v106 - 1;
          if ( !v107 )
            return L"WiFiJobSendActionFrameRequest";
          v108 = v107 - 1;
          if ( !v108 )
            return L"WiFiJobANQPQuery";
          v109 = v108 - 1;
          if ( !v109 )
            return L"WiFiJobQueryTcpOffloadVirtualPortConfig";
          if ( v109 == 1 )
            return L"WiFiJobAssociationParametersRequestResponder";
        }
      }
      else
      {
        if ( a1 == 147 )
          return L"WiFiJobNicSpecificExtension";
        if ( a1 > 140 )
        {
          v100 = a1 - 141;
          if ( !v100 )
            return L"WiFiJobP2PFlushDeviceList";
          v101 = v100 - 1;
          if ( !v101 )
            return L"WiFiJobGetPeerInfo";
          v102 = v101 - 1;
          if ( !v102 )
            return L"WiFiJobSetQoSParams";
          v103 = v102 - 1;
          if ( !v103 )
            return L"WiFiJobGetQoSParams";
          v104 = v103 - 1;
          if ( !v104 )
            return L"WiFiJobResumeFirmware";
          if ( v104 == 1 )
            return L"WiFiJobResumeP2pPort";
        }
        else
        {
          if ( a1 == 140 )
            return L"WiFiJobP2PGetDialogToken";
          v95 = a1 - 134;
          if ( !v95 )
            return L"WiFiJobStartLegacyAp";
          v96 = v95 - 1;
          if ( !v96 )
            return L"WiFiJobStopAp";
          v97 = v96 - 1;
          if ( !v97 )
            return L"WiFiJobP2PCancelDiscover";
          v98 = v97 - 1;
          if ( !v98 )
            return L"WiFiJobSendAssociationResponse";
          v99 = v98 - 1;
          if ( !v99 )
            return L"WiFiJobSetWpsEnabled";
          if ( v99 == 1 )
            return L"WiFiJobP2PEnumDeviceList";
        }
      }
    }
    else
    {
      if ( a1 == 133 )
        return L"WiFiJobStartP2PAp";
      if ( a1 > 120 )
      {
        if ( a1 > 127 )
        {
          v91 = a1 - 128;
          if ( !v91 )
            return L"WiFiJobP2PStopBackgroundDiscovery";
          v92 = v91 - 1;
          if ( !v92 )
            return L"WiFiJobP2PSetSecondaryDeviceTypeList";
          v93 = v92 - 1;
          if ( !v93 )
            return L"WiFiJobP2PSendActionFrameRequest";
          v94 = v93 - 1;
          if ( !v94 )
            return L"WiFiJobP2PSetGroupStartParameters";
          if ( v94 == 1 )
            return L"WiFiJobP2PSendActionFrameResponse";
        }
        else
        {
          if ( a1 == 127 )
            return L"WiFiJobP2PStartBackgroundDiscovery";
          v86 = a1 - 121;
          if ( !v86 )
            return L"WiFiJobP2PSetGroupJoinParameters";
          v87 = v86 - 1;
          if ( !v87 )
            return L"WiFiJobP2PSetGroupOwnerCapability";
          v88 = v87 - 1;
          if ( !v88 )
            return L"WiFiJobP2PSetListenState";
          v89 = v88 - 1;
          if ( !v89 )
            return L"WiFiJobP2PSetListenStatePassiveAvailability";
          v90 = v89 - 1;
          if ( !v90 )
            return L"WiFiJobP2PGetAdvertisementList";
          if ( v90 == 1 )
            return L"WiFiJobP2PSetAdvertisementList";
        }
      }
      else
      {
        if ( a1 == 120 )
          return L"WiFiJobP2PDiscover";
        if ( a1 > 113 )
        {
          v81 = a1 - 114;
          if ( !v81 )
            return L"WiFiJobP2PSetDeviceCapability";
          v82 = v81 - 1;
          if ( !v82 )
            return L"WiFiJobP2PSetAdditionalIE";
          v83 = v82 - 1;
          if ( !v83 )
            return L"WiFiJobP2PConnectRequest";
          v84 = v83 - 1;
          if ( !v84 )
            return L"WiFiJobP2PSetDesiredGroupID";
          v85 = v84 - 1;
          if ( !v85 )
            return L"WiFiJobP2PSetDeviceInfo";
          if ( v85 == 1 )
            return L"WiFiJobP2PDisconnectPeerRequest";
        }
        else
        {
          if ( a1 == 113 )
            return L"WiFiJobGetRadioState";
          v76 = a1 - 107;
          if ( !v76 )
            return L"WiFiJobSetSafeModeEnabled";
          v77 = v76 - 1;
          if ( !v77 )
            return L"WiFiJobQueryExtSTACapability";
          v78 = v77 - 1;
          if ( !v78 )
            return L"WiFiJobQueryStatistics";
          v79 = v78 - 1;
          if ( !v79 )
            return L"WiFiJobOIDQueryBeaconPeriod";
          v80 = v79 - 1;
          if ( !v80 )
            return L"WiFiJobOIDSetBeaconPeriod";
          if ( v80 == 1 )
            return L"WiFiJobSetRadioState";
        }
      }
    }
    return L"WifiCxJobTypeUnknown";
  }
  if ( a1 <= 187 )
  {
    if ( a1 == 187 )
      return L"WiFiJobQueryWifiCxAdapterInfo";
    if ( a1 > 174 )
    {
      if ( a1 > 181 )
      {
        v129 = a1 - 182;
        if ( !v129 )
          return L"WiFiJobSetOWEAuthParams";
        v130 = v129 - 1;
        if ( !v130 )
          return L"WiFiJobSetNwfPMKIDList";
        v131 = v130 - 1;
        if ( !v131 )
          return L"WiFiJobGetBSSInfo";
        v132 = v131 - 1;
        if ( !v132 )
          return L"WiFiJobGetLastScanUpdateTime";
        if ( v132 == 1 )
          return L"WiFiJobSetLocationPrivacy";
      }
      else
      {
        if ( a1 == 181 )
          return L"WiFiJobInitializeFtmTargets";
        v124 = a1 - 175;
        if ( !v124 )
          return L"WiFiJobSetHighChannelAvailabilityModeEnabled";
        v125 = v124 - 1;
        if ( !v125 )
          return L"WiFiJobSetSAEAuthParams";
        v126 = v125 - 1;
        if ( !v126 )
          return L"WiFiJobP2PFlushBSSEntry";
        v127 = v126 - 1;
        if ( !v127 )
          return L"WiFiJobRequestFtm";
        v128 = v127 - 1;
        if ( !v128 )
          return L"WiFiJobRequestFtmChild";
        if ( v128 == 1 )
          return L"WiFiJobProcessRadioMeasurementRequest";
      }
    }
    else
    {
      if ( a1 == 174 )
        return L"WiFiJobSetLimitedDisruptionModeEnabled";
      if ( a1 > 167 )
      {
        v119 = a1 - 168;
        if ( !v119 )
          return L"WiFiJobLowPowerNotify";
        v120 = v119 - 1;
        if ( !v120 )
          return L"WiFiJobSetNapsDelay";
        v121 = v120 - 1;
        if ( !v121 )
          return L"WiFiJobP2PSetCurrentASP2SessionID";
        v122 = v121 - 1;
        if ( !v122 )
          return L"WiFiJobGetSupportedDeviceServices";
        v123 = v122 - 1;
        if ( !v123 )
          return L"WiFiJobDeviceServiceCommand";
        if ( v123 == 1 )
          return L"WiFiJobGetCipherKey";
      }
      else
      {
        if ( a1 == 167 )
          return L"WiFiJobRoamRequest";
        v114 = a1 - 161;
        if ( !v114 )
          return L"WiFiJobIhvTaskRequest";
        v115 = v114 - 1;
        if ( !v115 )
          return L"WiFiJobSetFTReassociationParameters";
        v116 = v115 - 1;
        if ( !v116 )
          return L"WiFiJobSetNeighborReportEntries";
        v117 = v116 - 1;
        if ( !v117 )
          return L"WiFiJobQueryXmitOk";
        v118 = v117 - 1;
        if ( !v118 )
          return L"WiFiJobQueryRcvOk";
        if ( v118 == 1 )
          return L"WiFiJobSetEndDwellOnChannel";
      }
    }
    return L"WifiCxJobTypeUnknown";
  }
  if ( a1 <= 200 )
  {
    if ( a1 == 200 )
      return L"WiFiJobDevicePreDisarmHandleProtocolOffloads";
    if ( a1 > 194 )
    {
      v138 = a1 - 195;
      if ( !v138 )
        return L"WiFiJobDevicePowerManangedQueueForcedRequestStop";
      v139 = v138 - 1;
      if ( !v139 )
        return L"WiFiJobNetAdapterAddProtocolOffload";
      v140 = v139 - 1;
      if ( !v140 )
        return L"WiFiJobNetAdapterRemoveProtocolOffload";
      v141 = v140 - 1;
      if ( !v141 )
        return L"WiFiJobDeviceGetPowerOffloadList";
      if ( v141 == 1 )
        return L"WiFiJobNetAdapterUpdateProtocolOffloadEnabledFields";
    }
    else
    {
      if ( a1 == 194 )
        return L"WiFiJobDevicePortsStatusMonitor";
      v133 = a1 - 188;
      if ( !v133 )
        return L"WiFiJobDeviceInitialize";
      v134 = v133 - 1;
      if ( !v134 )
        return L"WiFiJobDeviceDeInitialize";
      v135 = v134 - 1;
      if ( !v135 )
        return L"WiFiJobCreateAdapter";
      v136 = v135 - 1;
      if ( !v136 )
        return L"WiFiJobDeInitInterface";
      v137 = v136 - 1;
      if ( !v137 )
        return L"WiFiJobNetAdapterStopPreparation";
      if ( v137 == 1 )
        return L"WiFiJobDevicePrepareForSystemPowerTargetToSxState";
    }
    return L"WifiCxJobTypeUnknown";
  }
  if ( a1 <= 208 )
  {
    if ( a1 == 208 )
      return L"WiFiJobSetHardwareFipsMode";
    v142 = a1 - 201;
    if ( !v142 )
      return L"WiFiJobQueryConnectionInfo";
    v143 = v142 - 1;
    if ( !v143 )
      return L"WiFiJobSetMloKeys";
    v144 = v143 - 2;
    if ( !v144 )
      return L"WiFiJobSetDSCPToUPMappingAllowed";
    v145 = v144 - 1;
    if ( !v145 )
      return L"WifiJobQueryQoSInfo";
    v146 = v145 - 1;
    if ( !v146 )
      return L"WiFiJobGetDataPathWakeReason";
    if ( v146 == 1 )
      return L"WiFiJobGetFipsCapabilities";
    return L"WifiCxJobTypeUnknown";
  }
  v147 = a1 - 209;
  if ( !v147 )
    return L"WiFiJobQoSWFATest5_4_1Job";
  v148 = v147 - 1;
  if ( !v148 )
    return L"WiFiJobSetAuthenticationFrameSubscription";
  v149 = v148 - 1;
  if ( !v149 )
    return L"WiFiJobSendAuthenticationFrame";
  v150 = v149 - 1;
  if ( !v150 )
    return L"WiFiJobWFD2SetDeviceCapabilitiesAndIdentity";
  if ( v150 != 1 )
    return L"WifiCxJobTypeUnknown";
  return L"WiFiJobRemoveStalePowerOffloadsJob";
}

```

## disassembly

```asm
0x1400d58c8  cmp     ecx, 6Ah ; 'j'
0x1400d58cb  jg      loc_1400D5F41
0x1400d58d1  jz      loc_1400D5F38
0x1400d58d7  cmp     ecx, 35h ; '5'
0x1400d58da  jg      loc_1400D5C1A
0x1400d58e0  jz      loc_1400D5C11
0x1400d58e6  cmp     ecx, 1Ah
0x1400d58e9  jg      loc_1400D5A87
0x1400d58ef  jz      loc_1400D5A7E
0x1400d58f5  cmp     ecx, 0Dh
0x1400d58f8  jg      loc_1400D59CC
0x1400d58fe  jz      loc_1400D59C3
0x1400d5904  cmp     ecx, 6
0x1400d5907  jg      short loc_1400D596B
0x1400d5909  jz      short loc_1400D5962
0x1400d590b  test    ecx, ecx
0x1400d590d  jz      short loc_1400D5959
0x1400d590f  sub     ecx, 1
0x1400d5912  jz      short loc_1400D5950
0x1400d5914  sub     ecx, 1
0x1400d5917  jz      short loc_1400D5947
0x1400d5919  sub     ecx, 1
0x1400d591c  jz      short loc_1400D593E
0x1400d591e  sub     ecx, 1
0x1400d5921  jz      short loc_1400D5935
0x1400d5923  cmp     ecx, 1
0x1400d5926  jnz     loc_1400D65C5
0x1400d592c  lea     rax, aWifijobminipor_1; "WiFiJobMiniportPause"
0x1400d5933  retn
0x1400d5935  lea     rax, aWifijobminipor_3; "WiFiJobMiniportHalt"
0x1400d593c  retn
0x1400d593e  lea     rax, aWifijobminipor_2; "WiFiJobMiniportInitialize"
0x1400d5945  retn
0x1400d5947  lea     rax, aWifijoboidquer_0; "WiFiJobOIDQueryNotYetImplemented"
0x1400d594e  retn
0x1400d5950  lea     rax, aWifijoboidsetn; "WiFiJobOIDSetNotYetImplemented"
0x1400d5957  retn
0x1400d5959  lea     rax, aWifijobtypeinv; "WiFiJobTypeInvalid"
0x1400d5960  retn
0x1400d5962  lea     rax, aWifijobminipor_0; "WiFiJobMiniportRestart"
0x1400d5969  retn
0x1400d596b  sub     ecx, 7
0x1400d596e  jz      short loc_1400D59BA
0x1400d5970  sub     ecx, 1
0x1400d5973  jz      short loc_1400D59B1
0x1400d5975  sub     ecx, 1
0x1400d5978  jz      short loc_1400D59A8
0x1400d597a  sub     ecx, 1
0x1400d597d  jz      short loc_1400D599F
0x1400d597f  sub     ecx, 1
0x1400d5982  jz      short loc_1400D5996
0x1400d5984  cmp     ecx, 1
0x1400d5987  jnz     loc_1400D65C5
0x1400d598d  lea     rax, aWifijobquery80; "WiFiJobQuery8023MulticastList"
0x1400d5994  retn
0x1400d5996  lea     rax, aWifijobsetpack; "WiFiJobSetPacketFilter"
0x1400d599d  retn
0x1400d599f  lea     rax, aWifijobquerysu_0; "WiFiJobQuerySupportedGuids"
0x1400d59a6  retn
0x1400d59a8  lea     rax, aWifijobdeletep; "WiFiJobDeletePort"
0x1400d59af  retn
0x1400d59b1  lea     rax, aWifijobcreatep; "WiFiJobCreatePort"
0x1400d59b8  retn
0x1400d59ba  lea     rax, aWifijobminipor; "WiFiJobMiniportSurpriseRemoval"
0x1400d59c1  retn
0x1400d59c3  lea     rax, aWifijobset8023; "WiFiJobSet8023MulticastList"
0x1400d59ca  retn
0x1400d59cc  cmp     ecx, 14h
0x1400d59cf  jg      short loc_1400D5A34
0x1400d59d1  jz      short loc_1400D5A2B
0x1400d59d3  sub     ecx, 0Eh
0x1400d59d6  jz      short loc_1400D5A22
0x1400d59d8  sub     ecx, 1
0x1400d59db  jz      short loc_1400D5A19
0x1400d59dd  sub     ecx, 1
0x1400d59e0  jz      short loc_1400D5A10
0x1400d59e2  sub     ecx, 1
0x1400d59e5  jz      short loc_1400D5A07
0x1400d59e7  sub     ecx, 1
0x1400d59ea  jz      short loc_1400D59FE
0x1400d59ec  cmp     ecx, 1
0x1400d59ef  jnz     loc_1400D65C5
0x1400d59f5  lea     rax, aWifijobtypecon; "WiFiJobTypeConnect"
0x1400d59fc  retn
0x1400d59fe  lea     rax, aWifijobsetoper_0; "WiFiJobSetOperationMode"
0x1400d5a05  retn
0x1400d5a07  lea     rax, aWifijobqueryop; "WiFiJobQueryOperationMode"
0x1400d5a0e  retn
0x1400d5a10  lea     rax, aWifijobdot11re; "WiFiJobDot11ResetPort"
0x1400d5a17  retn
0x1400d5a19  lea     rax, aWifijobsetdot1; "WiFiJobSetDot11MulticastList"
0x1400d5a20  retn
0x1400d5a22  lea     rax, aWifijobquerydo; "WiFiJobQueryDot11MulticastList"
0x1400d5a29  retn
0x1400d5a2b  lea     rax, aWifijobsetpowe; "WiFiJobSetPower"
0x1400d5a32  retn
0x1400d5a34  sub     ecx, 15h
0x1400d5a37  jz      short loc_1400D5A75
0x1400d5a39  sub     ecx, 1
0x1400d5a3c  jz      short loc_1400D5A6C
0x1400d5a3e  sub     ecx, 1
0x1400d5a41  jz      short loc_1400D5A63
0x1400d5a43  sub     ecx, 1
0x1400d5a46  jz      short loc_1400D5A5A
0x1400d5a48  cmp     ecx, 1
0x1400d5a4b  jnz     loc_1400D65C5
0x1400d5a51  lea     rax, aWifijobgetpowe; "WiFiJobGetPowerMgmtRequest"
0x1400d5a58  retn
0x1400d5a5a  lea     rax, aWifijobsetpowe_0; "WiFiJobSetPowerMgmtRequest"
0x1400d5a61  retn
0x1400d5a63  lea     rax, aWifijobgetauto; "WiFiJobGetAutoPowerSave"
0x1400d5a6a  retn
0x1400d5a6c  lea     rax, aWifijobsetauto; "WiFiJobSetAutoPowerSave"
0x1400d5a73  retn
0x1400d5a75  lea     rax, aWifijobquerypo; "WiFiJobQueryPower"
0x1400d5a7c  retn
0x1400d5a7e  lea     rax, aWifijobsetnlo; "WiFiJobSetNlo"
0x1400d5a85  retn
0x1400d5a87  cmp     ecx, 28h ; '('
0x1400d5a8a  jg      loc_1400D5B5F
0x1400d5a90  jz      loc_1400D5B56
0x1400d5a96  cmp     ecx, 21h ; '!'
0x1400d5a99  jg      short loc_1400D5AFE
0x1400d5a9b  jz      short loc_1400D5AF5
0x1400d5a9d  sub     ecx, 1Bh
0x1400d5aa0  jz      short loc_1400D5AEC
0x1400d5aa2  sub     ecx, 1
0x1400d5aa5  jz      short loc_1400D5AE3
0x1400d5aa7  sub     ecx, 1
0x1400d5aaa  jz      short loc_1400D5ADA
0x1400d5aac  sub     ecx, 1
0x1400d5aaf  jz      short loc_1400D5AD1
0x1400d5ab1  sub     ecx, 1
0x1400d5ab4  jz      short loc_1400D5AC8
0x1400d5ab6  cmp     ecx, 1
0x1400d5ab9  jnz     loc_1400D65C5
0x1400d5abf  lea     rax, aWifijobqueryen_1; "WiFiJobQueryEnabledMulticastCipherAlgo"
0x1400d5ac6  retn
0x1400d5ac8  lea     rax, aWifijobsetftpa; "WiFiJobSetFTParameters"
0x1400d5acf  retn
0x1400d5ad1  lea     rax, aWifijobsetenab_0; "WiFiJobSetEnabledAuthAlgo"
0x1400d5ad8  retn
0x1400d5ada  lea     rax, aWifijobqueryen; "WiFiJobQueryEnabledAuthAlgo"
0x1400d5ae1  retn
0x1400d5ae3  lea     rax, aWifijobsetdesi; "WiFiJobSetDesiredBssType"
0x1400d5aea  retn
0x1400d5aec  lea     rax, aWifijobqueryde_1; "WiFiJobQueryDesiredBssType"
0x1400d5af3  retn
0x1400d5af5  lea     rax, aWifijobsetenab; "WiFiJobSetEnabledMulticastCipherAlgo"
0x1400d5afc  retn
0x1400d5afe  sub     ecx, 22h ; '"'
0x1400d5b01  jz      short loc_1400D5B4D
0x1400d5b03  sub     ecx, 1
0x1400d5b06  jz      short loc_1400D5B44
0x1400d5b08  sub     ecx, 1
0x1400d5b0b  jz      short loc_1400D5B3B
0x1400d5b0d  sub     ecx, 1
0x1400d5b10  jz      short loc_1400D5B32
0x1400d5b12  sub     ecx, 1
0x1400d5b15  jz      short loc_1400D5B29
0x1400d5b17  cmp     ecx, 1
0x1400d5b1a  jnz     loc_1400D65C5
0x1400d5b20  lea     rax, aWifijobscanoid; "WiFiJobScanOidRequest"
0x1400d5b27  retn
0x1400d5b29  lea     rax, aWifijobscan; "WiFiJobScan"
0x1400d5b30  retn
0x1400d5b32  lea     rax, aWifijobsetphyi; "WiFiJobSetPhyId"
0x1400d5b39  retn
0x1400d5b3b  lea     rax, aWifijobqueryph; "WiFiJobQueryPhyId"
0x1400d5b42  retn
0x1400d5b44  lea     rax, aWifijobsetenab_1; "WiFiJobSetEnabledUnicastCipherAlgo"
0x1400d5b4b  retn
0x1400d5b4d  lea     rax, aWifijobqueryen_0; "WiFiJobQueryEnabledUnicastCipherAlgo"
0x1400d5b54  retn
0x1400d5b56  lea     rax, aWifijobenumbss; "WiFiJobEnumBSSList"
0x1400d5b5d  retn
0x1400d5b5f  cmp     ecx, 2Fh ; '/'
0x1400d5b62  jg      short loc_1400D5BC7
0x1400d5b64  jz      short loc_1400D5BBE
0x1400d5b66  sub     ecx, 29h ; ')'
0x1400d5b69  jz      short loc_1400D5BB5
0x1400d5b6b  sub     ecx, 1
0x1400d5b6e  jz      short loc_1400D5BAC
0x1400d5b70  sub     ecx, 1
0x1400d5b73  jz      short loc_1400D5BA3
0x1400d5b75  sub     ecx, 1
0x1400d5b78  jz      short loc_1400D5B9A
0x1400d5b7a  sub     ecx, 1
0x1400d5b7d  jz      short loc_1400D5B91
0x1400d5b7f  cmp     ecx, 1
0x1400d5b82  jnz     loc_1400D65C5
0x1400d5b88  lea     rax, aWifijobsethidd; "WiFiJobSetHiddenNetworkEnabled"
0x1400d5b8f  retn
0x1400d5b91  lea     rax, aWifijobqueryhi; "WiFiJobQueryHiddenNetworkEnabled"
0x1400d5b98  retn
0x1400d5b9a  lea     rax, aWifijobsetdesi_1; "WiFiJobSetDesiredHESSIDList"
0x1400d5ba1  retn
0x1400d5ba3  lea     rax, aWifijobqueryde_4; "WiFiJobQueryDesiredHESSIDList"
0x1400d5baa  retn
0x1400d5bac  lea     rax, aWifijobsetdesi_3; "WiFiJobSetDesiredSSIDList"
0x1400d5bb3  retn
0x1400d5bb5  lea     rax, aWifijobqueryde_2; "WiFiJobQueryDesiredSSIDList"
0x1400d5bbc  retn
0x1400d5bbe  lea     rax, aWifijobqueryex_1; "WiFiJobQueryExcludeUnencrypted"
0x1400d5bc5  retn
0x1400d5bc7  sub     ecx, 30h ; '0'
0x1400d5bca  jz      short loc_1400D5C08
0x1400d5bcc  sub     ecx, 1
0x1400d5bcf  jz      short loc_1400D5BFF
0x1400d5bd1  sub     ecx, 1
0x1400d5bd4  jz      short loc_1400D5BF6
0x1400d5bd6  sub     ecx, 1
0x1400d5bd9  jz      short loc_1400D5BED
0x1400d5bdb  cmp     ecx, 1
0x1400d5bde  jnz     loc_1400D65C5
0x1400d5be4  lea     rax, aWifijobsetpriv; "WiFiJobSetPrivacyExemptionList"
0x1400d5beb  retn
0x1400d5bed  lea     rax, aWifijobdisconn; "WiFiJobDisconnectRequest"
0x1400d5bf4  retn
0x1400d5bf6  lea     rax, aWifijobqueryop_0; "WiFiJobQueryOperationalRateSet"
0x1400d5bfd  retn
0x1400d5bff  lea     rax, aWifijobconnect; "WiFiJobConnectRequest"
0x1400d5c06  retn
0x1400d5c08  lea     rax, aWifijobsetexcl; "WiFiJobSetExcludeUnencrypted"
0x1400d5c0f  retn
0x1400d5c11  lea     rax, aWifijobsetdefa_0; "WiFiJobSetDefaultKey"
0x1400d5c18  retn
0x1400d5c1a  cmp     ecx, 50h ; 'P'
0x1400d5c1d  jg      loc_1400D5DBC
0x1400d5c23  jz      loc_1400D5DB3
0x1400d5c29  cmp     ecx, 43h ; 'C'
0x1400d5c2c  jg      loc_1400D5D01
0x1400d5c32  jz      loc_1400D5CF8
0x1400d5c38  cmp     ecx, 3Ch ; '<'
0x1400d5c3b  jg      short loc_1400D5CA0
0x1400d5c3d  jz      short loc_1400D5C97
0x1400d5c3f  sub     ecx, 36h ; '6'
0x1400d5c42  jz      short loc_1400D5C8E
0x1400d5c44  sub     ecx, 1
0x1400d5c47  jz      short loc_1400D5C85
0x1400d5c49  sub     ecx, 1
0x1400d5c4c  jz      short loc_1400D5C7C
0x1400d5c4e  sub     ecx, 1
0x1400d5c51  jz      short loc_1400D5C73
0x1400d5c53  sub     ecx, 1
0x1400d5c56  jz      short loc_1400D5C6A
0x1400d5c58  cmp     ecx, 1
0x1400d5c5b  jnz     loc_1400D65C5
0x1400d5c61  lea     rax, aWifijobsetstaa; "WiFiJobSetStaAssociationIEs"
0x1400d5c68  retn
0x1400d5c6a  lea     rax, aWifijobqueryst_0; "WiFiJobQueryStaAssociationIEs"
0x1400d5c71  retn
0x1400d5c73  lea     rax, aWifijobsetdesi_2; "WiFiJobSetDesiredBSSIDList"
0x1400d5c7a  retn
0x1400d5c7c  lea     rax, aWifijobqueryde_3; "WiFiJobQueryDesiredBSSIDList"
0x1400d5c83  retn
0x1400d5c85  lea     rax, aWifijobsetkeym; "WiFiJobSetKeyMappingKey"
0x1400d5c8c  retn
0x1400d5c8e  lea     rax, aWifijobsetdefa; "WiFiJobSetDefaultKeyId"
0x1400d5c95  retn
0x1400d5c97  lea     rax, aWifijobflushbs; "WiFiJobFlushBssList"
0x1400d5c9e  retn
0x1400d5ca0  sub     ecx, 3Dh ; '='
0x1400d5ca3  jz      short loc_1400D5CEF
0x1400d5ca5  sub     ecx, 1
0x1400d5ca8  jz      short loc_1400D5CE6
0x1400d5caa  sub     ecx, 1
0x1400d5cad  jz      short loc_1400D5CDD
0x1400d5caf  sub     ecx, 1
0x1400d5cb2  jz      short loc_1400D5CD4
0x1400d5cb4  sub     ecx, 1
0x1400d5cb7  jz      short loc_1400D5CCB
0x1400d5cb9  cmp     ecx, 1
0x1400d5cbc  jnz     loc_1400D65C5
0x1400d5cc2  lea     rax, aWifijobsetnicp; "WiFiJobSetNicPowerState"
0x1400d5cc9  retn
0x1400d5ccb  lea     rax, aWifijobqueryni; "WiFiJobQueryNicPowerState"
0x1400d5cd2  retn
0x1400d5cd4  lea     rax, aWifijobdeletem; "WiFiJobDeleteMac"
0x1400d5cdb  retn
0x1400d5cdd  lea     rax, aWifijobcreatem; "WiFiJobCreateMac"
0x1400d5ce4  retn
0x1400d5ce6  lea     rax, aWifijobroam; "WiFiJobRoam"
0x1400d5ced  retn
0x1400d5cef  lea     rax, aWifijobenumass; "WiFiJobEnumAssociationInfo"
0x1400d5cf6  retn
0x1400d5cf8  lea     rax, aWifijobqueryop_1; "WiFiJobQueryOperationModeCapability"
0x1400d5cff  retn
0x1400d5d01  cmp     ecx, 4Ah ; 'J'
0x1400d5d04  jg      short loc_1400D5D69
0x1400d5d06  jz      short loc_1400D5D60
0x1400d5d08  sub     ecx, 44h ; 'D'
0x1400d5d0b  jz      short loc_1400D5D57
0x1400d5d0d  sub     ecx, 1
0x1400d5d10  jz      short loc_1400D5D4E
0x1400d5d12  sub     ecx, 1
0x1400d5d15  jz      short loc_1400D5D45
0x1400d5d17  sub     ecx, 1
0x1400d5d1a  jz      short loc_1400D5D3C
0x1400d5d1c  sub     ecx, 1
  ... truncated ...
```
