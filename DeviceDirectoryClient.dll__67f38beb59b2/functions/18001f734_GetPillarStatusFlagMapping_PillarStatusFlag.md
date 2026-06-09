# GetPillarStatusFlagMapping(PillarStatusFlag)

- ea: `0x18001f734`
- end: `0x18001fc4e`
- name: `?GetPillarStatusFlagMapping@@YAPEBGW4PillarStatusFlag@@@Z`
- size: `1306`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e164`
- `0x18001fd74`

## callees

- `0x18001f734`

## string_xrefs

- `0x18001f7a5`: `PillarStatusFlag_Common_Healthy`
- `0x18001f78d`: `PillarStatusFlag_Defender_ServiceStopped`
- `0x18001f876`: `PillarStatusFlag_Network_ServiceStopped`
- `0x18001f88e`: `PillarStatusFlag_Network_ThirdPartyInstalled`
- `0x18001fa2f`: `PillarStatusFlag_Threat_3rdP_ScanRecommended`
- `0x18001fa1f`: `PillarStatusFlag_Threat_3rdP_SettingsRecommended`
- `0x18001fa0f`: `PillarStatusFlag_Threat_3rdP_UpdatesRecommended`
- `0x18001fa37`: `PillarStatusFlag_Threat_3rdP_UpdatesNeeded`
- `0x18001fa6f`: `PillarStatusFlag_Threat_3rdP_ScanUpdatesRecommended`
- `0x18001fa67`: `PillarStatusFlag_Threat_3rdP_ScanSettingsRecommended`
- `0x18001fa5f`: `PillarStatusFlag_Threat_3rdP_SettingsUpdatesRecommended`
- `0x18001fa57`: `PillarStatusFlag_Threat_3rdP_ScanSettingsUpdatesRecommended`
- `0x18001fa77`: `PillarStatusFlag_Threat_3rdP_ScanUpdatesNeeded`
- `0x18001fabb`: `PillarStatusFlag_Threat_3rdP_SettingsUpdatesNeeded`
- `0x18001fab3`: `PillarStatusFlag_Threat_3rdP_ScanSettingsUpdatesNeeded`
- `0x18001faab`: `PillarStatusFlag_Threat_3rdP_ScanUpdatesNeeded_SettingsRecommended`
- `0x18001faa3`: `PillarStatusFlag_Threat_3rdP_ScanSettingsNeeded_UpdatesRecommended`
- `0x18001facb`: `PillarStatusFlag_Threat_3rdP_SettingsUpdatesNeeded_ScanRecommended`
- `0x18001fb03`: `PillarStatusFlag_Threat_3rdP_ScanNeeded_SettingsRecommended`
- `0x18001fafb`: `PillarStatusFlag_Threat_3rdP_ScanNeeded_UpdatesRecommended`
- `0x18001faf3`: `PillarStatusFlag_Threat_3rdP_ScanNeeded_SettingsUpdatesRecommended`
- `0x18001faeb`: `PillarStatusFlag_Threat_3rdP_SettingsNeeded_ScanRecommended`
- `0x18001fb0b`: `PillarStatusFlag_Threat_3rdP_SettingsNeeded_UpdatesRecommended`
- `0x18001fb79`: `PillarStatusFlag_Threat_3rdP_SettingsNeeded_ScanUpdatesRecommended`
- `0x18001fb71`: `PillarStatusFlag_Threat_3rdP_UpdatesNeeded_ScanRecommended`
- `0x18001fb69`: `PillarStatusFlag_Threat_3rdP_UpdatesNeeded_SettingsRecommended`
- `0x18001fb61`: `PillarStatusFlag_Threat_3rdP_UpdatesNeeded_ScanSettingsRecommended`
- `0x18001fc3e`: `PillarStatusFlag_Common_ThirdParty_UnknownStatus`
- `0x18001fb81`: `PillarStatusFlag_Threat_3rdP_L1_SingleActionRecommended`
- `0x18001fbb1`: `PillarStatusFlag_Threat_3rdP_L1_MultipleActionRecommended`
- `0x18001fc26`: `PillarStatusFlag_Network_3rdP_ActionRecommended`
- `0x18001fc0e`: `PillarStatusFlag_Network_3rdP_L2L1_ActionRecommended`
- `0x18001fbfe`: `PillarStatusFlag_Network_3rdP_L2L1_MultipleActionRecommended`
- `0x18001fc46`: `PillarStatusFlag_Common_Unknown`

## pseudocode

```c
const wchar_t *__fastcall GetPillarStatusFlagMapping(int a1)
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

  if ( a1 > 57 )
  {
    if ( a1 > 80 )
    {
      if ( a1 <= 143 )
      {
        if ( a1 == 143 )
          return L"PillarStatusFlag_Common_ThirdParty_UnknownStatus";
        if ( a1 > 91 )
        {
          v52 = a1 - 92;
          if ( !v52 )
            return L"PillarStatusFlag_Network_3rdP_Expired";
          v53 = v52 - 1;
          if ( !v53 )
            return L"PillarStatusFlag_Network_3rdP_Snoozed";
          v54 = v53 - 1;
          if ( !v54 )
            return L"PillarStatusFlag_Network_3rdP_ActionRecommended";
          v55 = v54 - 1;
          if ( !v55 )
            return L"PillarStatusFlag_Network_3rdP_ActionNeeded";
          v56 = v55 - 1;
          if ( !v56 )
            return L"PillarStatusFlag_Network_3rdP_L2L1_NoAction";
          v57 = v56 - 1;
          if ( !v57 )
            return L"PillarStatusFlag_Network_3rdP_L2L1_ActionRecommended";
          v58 = v57 - 1;
          if ( !v58 )
            return L"PillarStatusFlag_Network_3rdP_L2L1_ActionNeeded";
          v59 = v58 - 1;
          if ( !v59 )
            return L"PillarStatusFlag_Network_3rdP_L2L1_MultipleActionRecommended";
          if ( v59 == 1 )
            return L"PillarStatusFlag_Network_3rdP_L2L1_MultipleActionNeeded";
        }
        else
        {
          if ( a1 == 91 )
            return L"PillarStatusFlag_Network_3rdP_Off";
          if ( a1 > 86 )
          {
            v49 = a1 - 87;
            if ( !v49 )
              return L"PillarStatusFlag_Threat_3rdP_L1_SingleActionNeeded";
            v50 = v49 - 1;
            if ( !v50 )
              return L"PillarStatusFlag_Threat_3rdP_L1_MultipleActionRecommended";
            v51 = v50 - 1;
            if ( !v51 )
              return L"PillarStatusFlag_Threat_3rdP_L1_MultipleActionNeeded";
            if ( v51 == 1 )
              return L"PillarStatusFlag_Network_3rdP_NoAction";
          }
          else
          {
            if ( a1 == 86 )
              return L"PillarStatusFlag_Threat_3rdP_L1_SingleActionRecommended";
            v45 = a1 - 81;
            if ( !v45 )
              return L"PillarStatusFlag_Threat_3rdP_SettingsNeeded_ScanUpdatesRecommended";
            v46 = v45 - 1;
            if ( !v46 )
              return L"PillarStatusFlag_Threat_3rdP_UpdatesNeeded_ScanRecommended";
            v47 = v46 - 1;
            if ( !v47 )
              return L"PillarStatusFlag_Threat_3rdP_UpdatesNeeded_SettingsRecommended";
            v48 = v47 - 1;
            if ( !v48 )
              return L"PillarStatusFlag_Threat_3rdP_UpdatesNeeded_ScanSettingsRecommended";
            if ( v48 == 1 )
              return L"PillarStatusFlag_Threat_3rdP_L1_NoAction";
          }
        }
      }
    }
    else
    {
      if ( a1 == 80 )
        return L"PillarStatusFlag_Threat_3rdP_SettingsNeeded_UpdatesRecommended";
      if ( a1 > 69 )
      {
        if ( a1 > 75 )
        {
          v42 = a1 - 76;
          if ( !v42 )
            return L"PillarStatusFlag_Threat_3rdP_ScanNeeded_SettingsRecommended";
          v43 = v42 - 1;
          if ( !v43 )
            return L"PillarStatusFlag_Threat_3rdP_ScanNeeded_UpdatesRecommended";
          v44 = v43 - 1;
          if ( !v44 )
            return L"PillarStatusFlag_Threat_3rdP_ScanNeeded_SettingsUpdatesRecommended";
          if ( v44 == 1 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsNeeded_ScanRecommended";
        }
        else
        {
          if ( a1 == 75 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsUpdatesNeeded_ScanRecommended";
          v38 = a1 - 70;
          if ( !v38 )
            return L"PillarStatusFlag_Threat_3rdP_ScanSettingsNeeded";
          v39 = v38 - 1;
          if ( !v39 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsUpdatesNeeded";
          v40 = v39 - 1;
          if ( !v40 )
            return L"PillarStatusFlag_Threat_3rdP_ScanSettingsUpdatesNeeded";
          v41 = v40 - 1;
          if ( !v41 )
            return L"PillarStatusFlag_Threat_3rdP_ScanUpdatesNeeded_SettingsRecommended";
          if ( v41 == 1 )
            return L"PillarStatusFlag_Threat_3rdP_ScanSettingsNeeded_UpdatesRecommended";
        }
      }
      else
      {
        if ( a1 == 69 )
          return L"PillarStatusFlag_Threat_3rdP_ScanUpdatesNeeded";
        if ( a1 > 64 )
        {
          v35 = a1 - 65;
          if ( !v35 )
            return L"PillarStatusFlag_Threat_3rdP_ScanUpdatesRecommended";
          v36 = v35 - 1;
          if ( !v36 )
            return L"PillarStatusFlag_Threat_3rdP_ScanSettingsRecommended";
          v37 = v36 - 1;
          if ( !v37 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsUpdatesRecommended";
          if ( v37 == 1 )
            return L"PillarStatusFlag_Threat_3rdP_ScanSettingsUpdatesRecommended";
        }
        else
        {
          if ( a1 == 64 )
            return L"PillarStatusFlag_Threat_3rdP_UpdatesNeeded";
          v31 = a1 - 59;
          if ( !v31 )
            return L"PillarStatusFlag_Threat_3rdP_ScanRecommended";
          v32 = v31 - 1;
          if ( !v32 )
            return L"PillarStatusFlag_Threat_3rdP_ScanNeeded";
          v33 = v32 - 1;
          if ( !v33 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsRecommended";
          v34 = v33 - 1;
          if ( !v34 )
            return L"PillarStatusFlag_Threat_3rdP_SettingsNeeded";
          if ( v34 == 1 )
            return L"PillarStatusFlag_Threat_3rdP_UpdatesRecommended";
        }
      }
    }
  }
  else
  {
    if ( a1 == 57 )
      return L"PillarStatusFlag_Threat_3rdP_Snoozed";
    if ( a1 > 27 )
    {
      if ( a1 > 38 )
      {
        if ( a1 > 49 )
        {
          v28 = a1 - 50;
          if ( !v28 )
            return L"PillarStatusFlag_AppAndBrowser_StoreAppsSmartScreenOff";
          v29 = v28 - 3;
          if ( !v29 )
            return L"PillarStatusFlag_Threat_3rdP_NoAction";
          v30 = v29 - 1;
          if ( !v30 )
            return L"PillarStatusFlag_Threat_3rdP_Off";
          if ( v30 == 1 )
            return L"PillarStatusFlag_Threat_3rdP_Expired";
        }
        else
        {
          if ( a1 == 49 )
            return L"PillarStatusFlag_AppAndBrowser_AppRepSmartScreenOff";
          v24 = a1 - 39;
          if ( !v24 )
            return L"PillarStatusFlag_HealthAdvisor_BatteryBrightnessAlert";
          v25 = v24 - 1;
          if ( !v25 )
            return L"PillarStatusFlag_HealthAdvisor_BatterySleepSettingsAlert";
          v26 = v25 - 5;
          if ( !v26 )
            return L"PillarStatusFlag_AppAndBrowser_Unknown";
          v27 = v26 - 1;
          if ( !v27 )
            return L"PillarStatusFlag_AppAndBrowser_Healthy";
          if ( v27 == 2 )
            return L"PillarStatusFlag_AppAndBrowser_EdgeSmartScreenOff";
        }
      }
      else
      {
        if ( a1 == 38 )
          return L"PillarStatusFlag_HealthAdvisor_PristineShellContentPresent";
        if ( a1 > 33 )
        {
          v21 = a1 - 34;
          if ( !v21 )
            return L"PillarStatusFlag_HealthAdvisor_Warning";
          v22 = v21 - 1;
          if ( !v22 )
            return L"PillarStatusFlag_HealthAdvisor_Critical";
          v23 = v22 - 1;
          if ( !v23 )
            return L"PillarStatusFlag_HealthAdvisor_StorageDiskspaceLow";
          if ( v23 == 1 )
            return L"PillarStatusFlag_HealthAdvisor_StorageHealthOkWithIssues";
        }
        else
        {
          if ( a1 == 33 )
            return L"PillarStatusFlag_HealthAdvisor_Healthy";
          v17 = a1 - 28;
          if ( !v17 )
            return L"PillarStatusFlag_Network_DomainFwOff";
          v18 = v17 - 1;
          if ( !v18 )
            return L"PillarStatusFlag_Network_PrivateFwOff";
          v19 = v18 - 1;
          if ( !v19 )
            return L"PillarStatusFlag_Network_PublicFwOff";
          v20 = v19 - 1;
          if ( !v20 )
            return L"PillarStatusFlag_Network_MultipleFwOff";
          if ( v20 == 1 )
            return L"PillarStatusFlag_HealthAdvisor_Unknown";
        }
      }
    }
    else
    {
      if ( a1 == 27 )
        return L"PillarStatusFlag_Network_ThirdPartyInstalled";
      if ( a1 > 12 )
      {
        if ( a1 > 18 )
        {
          v14 = a1 - 23;
          if ( !v14 )
            return L"PillarStatusFlag_Network_Unknown";
          v15 = v14 - 1;
          if ( !v15 )
            return L"PillarStatusFlag_Network_Healthy";
          v16 = v15 - 1;
          if ( !v16 )
            return L"PillarStatusFlag_Network_ServiceStopped";
          if ( v16 == 1 )
            return L"PillarStatusFlag_Network_NonSecureState";
        }
        else
        {
          if ( a1 == 18 )
            return L"PillarStatusFlag_Defender_SModeSigsDue";
          v10 = a1 - 13;
          if ( !v10 )
            return L"PillarStatusFlag_Defender_QuickScanDue";
          v11 = v10 - 1;
          if ( !v11 )
            return L"PillarStatusFlag_Defender_FullScanDue";
          v12 = v11 - 1;
          if ( !v12 )
            return L"PillarStatusFlag_Defender_CloudProtectionDisabled";
          v13 = v12 - 1;
          if ( !v13 )
            return L"PillarStatusFlag_Defender_AutoSampleSubmissionDisabled";
          if ( v13 == 1 )
            return L"PillarStatusFlag_Defender_TamperProtectionDisabled";
        }
      }
      else
      {
        if ( a1 == 12 )
          return L"PillarStatusFlag_Defender_AsSigsDue";
        if ( a1 > 6 )
        {
          v6 = a1 - 7;
          if ( !v6 )
            return L"PillarStatusFlag_Defender_RtpDisabled";
          v7 = v6 - 1;
          if ( !v7 )
            return L"PillarStatusFlag_Defender_FullScanRequired";
          v8 = v7 - 1;
          if ( !v8 )
            return L"PillarStatusFlag_Defender_RebootRequired";
          v9 = v8 - 1;
          if ( !v9 )
            return L"PillarStatusFlag_Defender_WdoRequired";
          if ( v9 == 1 )
            return L"PillarStatusFlag_Defender_AvSigsDue";
        }
        else
        {
          if ( a1 == 6 )
            return L"PillarStatusFlag_Defender_ActiveThreats";
          v1 = a1 - 1;
          if ( !v1 )
            return L"PillarStatusFlag_Common_Healthy";
          v2 = v1 - 1;
          if ( !v2 )
            return L"PillarStatusFlag_Defender_Unknown";
          v3 = v2 - 1;
          if ( !v3 )
            return L"PillarStatusFlag_Defender_Healthy";
          v4 = v3 - 1;
          if ( !v4 )
            return L"PillarStatusFlag_Defender_ServiceStopped";
          if ( v4 == 1 )
            return L"PillarStatusFlag_Defender_EngineUnavailable";
        }
      }
    }
  }
  return L"PillarStatusFlag_Common_Unknown";
}

```

## disassembly

```asm
0x18001f734  cmp     ecx, 39h ; '9'
0x18001f737  jg      loc_18001F9CD
0x18001f73d  jz      loc_18001F9C5
0x18001f743  cmp     ecx, 1Bh
0x18001f746  jg      loc_18001F896
0x18001f74c  jz      loc_18001F88E
0x18001f752  cmp     ecx, 0Ch
0x18001f755  jg      loc_18001F802
0x18001f75b  jz      loc_18001F7FA
0x18001f761  cmp     ecx, 6
0x18001f764  jg      short loc_18001F7B5
0x18001f766  jz      short loc_18001F7AD
0x18001f768  sub     ecx, 1
0x18001f76b  jz      short loc_18001F7A5
0x18001f76d  sub     ecx, 1
0x18001f770  jz      short loc_18001F79D
0x18001f772  sub     ecx, 1
0x18001f775  jz      short loc_18001F795
0x18001f777  sub     ecx, 1
0x18001f77a  jz      short loc_18001F78D
0x18001f77c  cmp     ecx, 1
0x18001f77f  jnz     loc_18001FC46
0x18001f785  lea     rax, aPillarstatusfl_15; "PillarStatusFlag_Defender_EngineUnavail"...
0x18001f78c  retn
0x18001f78d  lea     rax, aPillarstatusfl_22; "PillarStatusFlag_Defender_ServiceStoppe"...
0x18001f794  retn
0x18001f795  lea     rax, aPillarstatusfl_9; "PillarStatusFlag_Defender_Healthy"
0x18001f79c  retn
0x18001f79d  lea     rax, aPillarstatusfl_27; "PillarStatusFlag_Defender_Unknown"
0x18001f7a4  retn
0x18001f7a5  lea     rax, aPillarstatusfl_39; "PillarStatusFlag_Common_Healthy"
0x18001f7ac  retn
0x18001f7ad  lea     rax, aPillarstatusfl_72; "PillarStatusFlag_Defender_ActiveThreats"
0x18001f7b4  retn
0x18001f7b5  sub     ecx, 7
0x18001f7b8  jz      short loc_18001F7F2
0x18001f7ba  sub     ecx, 1
0x18001f7bd  jz      short loc_18001F7EA
0x18001f7bf  sub     ecx, 1
0x18001f7c2  jz      short loc_18001F7E2
0x18001f7c4  sub     ecx, 1
0x18001f7c7  jz      short loc_18001F7DA
0x18001f7c9  cmp     ecx, 1
0x18001f7cc  jnz     loc_18001FC46
0x18001f7d2  lea     rax, aPillarstatusfl_61; "PillarStatusFlag_Defender_AvSigsDue"
0x18001f7d9  retn
0x18001f7da  lea     rax, aPillarstatusfl_11; "PillarStatusFlag_Defender_WdoRequired"
0x18001f7e1  retn
0x18001f7e2  lea     rax, aPillarstatusfl_81; "PillarStatusFlag_Defender_RebootRequire"...
0x18001f7e9  retn
0x18001f7ea  lea     rax, aPillarstatusfl_18; "PillarStatusFlag_Defender_FullScanRequi"...
0x18001f7f1  retn
0x18001f7f2  lea     rax, aPillarstatusfl_55; "PillarStatusFlag_Defender_RtpDisabled"
0x18001f7f9  retn
0x18001f7fa  lea     rax, aPillarstatusfl_13; "PillarStatusFlag_Defender_AsSigsDue"
0x18001f801  retn
0x18001f802  cmp     ecx, 12h
0x18001f805  jg      short loc_18001F856
0x18001f807  jz      short loc_18001F84E
0x18001f809  sub     ecx, 0Dh
0x18001f80c  jz      short loc_18001F846
0x18001f80e  sub     ecx, 1
0x18001f811  jz      short loc_18001F83E
0x18001f813  sub     ecx, 1
0x18001f816  jz      short loc_18001F836
0x18001f818  sub     ecx, 1
0x18001f81b  jz      short loc_18001F82E
0x18001f81d  cmp     ecx, 1
0x18001f820  jnz     loc_18001FC46
0x18001f826  lea     rax, aPillarstatusfl_60; "PillarStatusFlag_Defender_TamperProtect"...
0x18001f82d  retn
0x18001f82e  lea     rax, aPillarstatusfl_17; "PillarStatusFlag_Defender_AutoSampleSub"...
0x18001f835  retn
0x18001f836  lea     rax, aPillarstatusfl_79; "PillarStatusFlag_Defender_CloudProtecti"...
0x18001f83d  retn
0x18001f83e  lea     rax, aPillarstatusfl_53; "PillarStatusFlag_Defender_FullScanDue"
0x18001f845  retn
0x18001f846  lea     rax, aPillarstatusfl_48; "PillarStatusFlag_Defender_QuickScanDue"
0x18001f84d  retn
0x18001f84e  lea     rax, aPillarstatusfl_38; "PillarStatusFlag_Defender_SModeSigsDue"
0x18001f855  retn
0x18001f856  sub     ecx, 17h
0x18001f859  jz      short loc_18001F886
0x18001f85b  sub     ecx, 1
0x18001f85e  jz      short loc_18001F87E
0x18001f860  sub     ecx, 1
0x18001f863  jz      short loc_18001F876
0x18001f865  cmp     ecx, 1
0x18001f868  jnz     loc_18001FC46
0x18001f86e  lea     rax, aPillarstatusfl_2; "PillarStatusFlag_Network_NonSecureState"
0x18001f875  retn
0x18001f876  lea     rax, aPillarstatusfl_6; "PillarStatusFlag_Network_ServiceStopped"
0x18001f87d  retn
0x18001f87e  lea     rax, aPillarstatusfl_84; "PillarStatusFlag_Network_Healthy"
0x18001f885  retn
0x18001f886  lea     rax, aPillarstatusfl_43; "PillarStatusFlag_Network_Unknown"
0x18001f88d  retn
0x18001f88e  lea     rax, aPillarstatusfl_80; "PillarStatusFlag_Network_ThirdPartyInst"...
0x18001f895  retn
0x18001f896  cmp     ecx, 26h ; '&'
0x18001f899  jg      loc_18001F939
0x18001f89f  jz      loc_18001F931
0x18001f8a5  cmp     ecx, 21h ; '!'
0x18001f8a8  jg      short loc_18001F8F9
0x18001f8aa  jz      short loc_18001F8F1
0x18001f8ac  sub     ecx, 1Ch
0x18001f8af  jz      short loc_18001F8E9
0x18001f8b1  sub     ecx, 1
0x18001f8b4  jz      short loc_18001F8E1
0x18001f8b6  sub     ecx, 1
0x18001f8b9  jz      short loc_18001F8D9
0x18001f8bb  sub     ecx, 1
0x18001f8be  jz      short loc_18001F8D1
0x18001f8c0  cmp     ecx, 1
0x18001f8c3  jnz     loc_18001FC46
0x18001f8c9  lea     rax, aPillarstatusfl_82; "PillarStatusFlag_HealthAdvisor_Unknown"
0x18001f8d0  retn
0x18001f8d1  lea     rax, aPillarstatusfl; "PillarStatusFlag_Network_MultipleFwOff"
0x18001f8d8  retn
0x18001f8d9  lea     rax, aPillarstatusfl_4; "PillarStatusFlag_Network_PublicFwOff"
0x18001f8e0  retn
0x18001f8e1  lea     rax, aPillarstatusfl_67; "PillarStatusFlag_Network_PrivateFwOff"
0x18001f8e8  retn
0x18001f8e9  lea     rax, aPillarstatusfl_49; "PillarStatusFlag_Network_DomainFwOff"
0x18001f8f0  retn
0x18001f8f1  lea     rax, aPillarstatusfl_31; "PillarStatusFlag_HealthAdvisor_Healthy"
0x18001f8f8  retn
0x18001f8f9  sub     ecx, 22h ; '"'
0x18001f8fc  jz      short loc_18001F929
0x18001f8fe  sub     ecx, 1
0x18001f901  jz      short loc_18001F921
0x18001f903  sub     ecx, 1
0x18001f906  jz      short loc_18001F919
0x18001f908  cmp     ecx, 1
0x18001f90b  jnz     loc_18001FC46
0x18001f911  lea     rax, aPillarstatusfl_7; "PillarStatusFlag_HealthAdvisor_StorageH"...
0x18001f918  retn
0x18001f919  lea     rax, aPillarstatusfl_33; "PillarStatusFlag_HealthAdvisor_StorageD"...
0x18001f920  retn
0x18001f921  lea     rax, aPillarstatusfl_71; "PillarStatusFlag_HealthAdvisor_Critical"
0x18001f928  retn
0x18001f929  lea     rax, aPillarstatusfl_46; "PillarStatusFlag_HealthAdvisor_Warning"
0x18001f930  retn
0x18001f931  lea     rax, aPillarstatusfl_83; "PillarStatusFlag_HealthAdvisor_Pristine"...
0x18001f938  retn
0x18001f939  cmp     ecx, 31h ; '1'
0x18001f93c  jg      short loc_18001F98D
0x18001f93e  jz      short loc_18001F985
0x18001f940  sub     ecx, 27h ; '''
0x18001f943  jz      short loc_18001F97D
0x18001f945  sub     ecx, 1
0x18001f948  jz      short loc_18001F975
0x18001f94a  sub     ecx, 5
0x18001f94d  jz      short loc_18001F96D
0x18001f94f  sub     ecx, 1
0x18001f952  jz      short loc_18001F965
0x18001f954  cmp     ecx, 2
0x18001f957  jnz     loc_18001FC46
0x18001f95d  lea     rax, aPillarstatusfl_44; "PillarStatusFlag_AppAndBrowser_EdgeSmar"...
0x18001f964  retn
0x18001f965  lea     rax, aPillarstatusfl_52; "PillarStatusFlag_AppAndBrowser_Healthy"
0x18001f96c  retn
0x18001f96d  lea     rax, aPillarstatusfl_78; "PillarStatusFlag_AppAndBrowser_Unknown"
0x18001f974  retn
0x18001f975  lea     rax, aPillarstatusfl_8; "PillarStatusFlag_HealthAdvisor_BatteryS"...
0x18001f97c  retn
0x18001f97d  lea     rax, aPillarstatusfl_87; "PillarStatusFlag_HealthAdvisor_BatteryB"...
0x18001f984  retn
0x18001f985  lea     rax, aPillarstatusfl_23; "PillarStatusFlag_AppAndBrowser_AppRepSm"...
0x18001f98c  retn
0x18001f98d  sub     ecx, 32h ; '2'
0x18001f990  jz      short loc_18001F9BD
0x18001f992  sub     ecx, 3
0x18001f995  jz      short loc_18001F9B5
0x18001f997  sub     ecx, 1
0x18001f99a  jz      short loc_18001F9AD
0x18001f99c  cmp     ecx, 1
0x18001f99f  jnz     loc_18001FC46
0x18001f9a5  lea     rax, aPillarstatusfl_74; "PillarStatusFlag_Threat_3rdP_Expired"
0x18001f9ac  retn
0x18001f9ad  lea     rax, aPillarstatusfl_58; "PillarStatusFlag_Threat_3rdP_Off"
0x18001f9b4  retn
0x18001f9b5  lea     rax, aPillarstatusfl_20; "PillarStatusFlag_Threat_3rdP_NoAction"
0x18001f9bc  retn
0x18001f9bd  lea     rax, aPillarstatusfl_59; "PillarStatusFlag_AppAndBrowser_StoreApp"...
0x18001f9c4  retn
0x18001f9c5  lea     rax, aPillarstatusfl_69; "PillarStatusFlag_Threat_3rdP_Snoozed"
0x18001f9cc  retn
0x18001f9cd  cmp     ecx, 50h ; 'P'
0x18001f9d0  jg      loc_18001FB13
0x18001f9d6  jz      loc_18001FB0B
0x18001f9dc  cmp     ecx, 45h ; 'E'
0x18001f9df  jg      loc_18001FA7F
0x18001f9e5  jz      loc_18001FA77
0x18001f9eb  cmp     ecx, 40h ; '@'
0x18001f9ee  jg      short loc_18001FA3F
0x18001f9f0  jz      short loc_18001FA37
0x18001f9f2  sub     ecx, 3Bh ; ';'
0x18001f9f5  jz      short loc_18001FA2F
0x18001f9f7  sub     ecx, 1
0x18001f9fa  jz      short loc_18001FA27
0x18001f9fc  sub     ecx, 1
0x18001f9ff  jz      short loc_18001FA1F
0x18001fa01  sub     ecx, 1
0x18001fa04  jz      short loc_18001FA17
0x18001fa06  cmp     ecx, 1
0x18001fa09  jnz     loc_18001FC46
0x18001fa0f  lea     rax, aPillarstatusfl_75; "PillarStatusFlag_Threat_3rdP_UpdatesRec"...
0x18001fa16  retn
0x18001fa17  lea     rax, aPillarstatusfl_16; "PillarStatusFlag_Threat_3rdP_SettingsNe"...
0x18001fa1e  retn
0x18001fa1f  lea     rax, aPillarstatusfl_40; "PillarStatusFlag_Threat_3rdP_SettingsRe"...
0x18001fa26  retn
0x18001fa27  lea     rax, aPillarstatusfl_65; "PillarStatusFlag_Threat_3rdP_ScanNeeded"
0x18001fa2e  retn
0x18001fa2f  lea     rax, aPillarstatusfl_68; "PillarStatusFlag_Threat_3rdP_ScanRecomm"...
0x18001fa36  retn
0x18001fa37  lea     rax, aPillarstatusfl_57; "PillarStatusFlag_Threat_3rdP_UpdatesNee"...
0x18001fa3e  retn
0x18001fa3f  sub     ecx, 41h ; 'A'
0x18001fa42  jz      short loc_18001FA6F
0x18001fa44  sub     ecx, 1
0x18001fa47  jz      short loc_18001FA67
0x18001fa49  sub     ecx, 1
0x18001fa4c  jz      short loc_18001FA5F
0x18001fa4e  cmp     ecx, 1
0x18001fa51  jnz     loc_18001FC46
0x18001fa57  lea     rax, aPillarstatusfl_5; "PillarStatusFlag_Threat_3rdP_ScanSettin"...
0x18001fa5e  retn
0x18001fa5f  lea     rax, aPillarstatusfl_85; "PillarStatusFlag_Threat_3rdP_SettingsUp"...
0x18001fa66  retn
0x18001fa67  lea     rax, aPillarstatusfl_66; "PillarStatusFlag_Threat_3rdP_ScanSettin"...
0x18001fa6e  retn
0x18001fa6f  lea     rax, aPillarstatusfl_3; "PillarStatusFlag_Threat_3rdP_ScanUpdate"...
0x18001fa76  retn
0x18001fa77  lea     rax, aPillarstatusfl_64; "PillarStatusFlag_Threat_3rdP_ScanUpdate"...
0x18001fa7e  retn
0x18001fa7f  cmp     ecx, 4Bh ; 'K'
0x18001fa82  jg      short loc_18001FAD3
0x18001fa84  jz      short loc_18001FACB
0x18001fa86  sub     ecx, 46h ; 'F'
0x18001fa89  jz      short loc_18001FAC3
0x18001fa8b  sub     ecx, 1
0x18001fa8e  jz      short loc_18001FABB
0x18001fa90  sub     ecx, 1
0x18001fa93  jz      short loc_18001FAB3
0x18001fa95  sub     ecx, 1
0x18001fa98  jz      short loc_18001FAAB
0x18001fa9a  cmp     ecx, 1
0x18001fa9d  jnz     loc_18001FC46
0x18001faa3  lea     rax, aPillarstatusfl_37; "PillarStatusFlag_Threat_3rdP_ScanSettin"...
0x18001faaa  retn
0x18001faab  lea     rax, aPillarstatusfl_10; "PillarStatusFlag_Threat_3rdP_ScanUpdate"...
0x18001fab2  retn
0x18001fab3  lea     rax, aPillarstatusfl_42; "PillarStatusFlag_Threat_3rdP_ScanSettin"...
0x18001faba  retn
0x18001fabb  lea     rax, aPillarstatusfl_0; "PillarStatusFlag_Threat_3rdP_SettingsUp"...
0x18001fac2  retn
0x18001fac3  lea     rax, aPillarstatusfl_24; "PillarStatusFlag_Threat_3rdP_ScanSettin"...
0x18001faca  retn
0x18001facb  lea     rax, aPillarstatusfl_30; "PillarStatusFlag_Threat_3rdP_SettingsUp"...
0x18001fad2  retn
0x18001fad3  sub     ecx, 4Ch ; 'L'
0x18001fad6  jz      short loc_18001FB03
0x18001fad8  sub     ecx, 1
0x18001fadb  jz      short loc_18001FAFB
0x18001fadd  sub     ecx, 1
0x18001fae0  jz      short loc_18001FAF3
0x18001fae2  cmp     ecx, 1
0x18001fae5  jnz     loc_18001FC46
0x18001faeb  lea     rax, aPillarstatusfl_41; "PillarStatusFlag_Threat_3rdP_SettingsNe"...
0x18001faf2  retn
0x18001faf3  lea     rax, aPillarstatusfl_54; "PillarStatusFlag_Threat_3rdP_ScanNeeded"...
0x18001fafa  retn
0x18001fafb  lea     rax, aPillarstatusfl_76; "PillarStatusFlag_Threat_3rdP_ScanNeeded"...
0x18001fb02  retn
0x18001fb03  lea     rax, aPillarstatusfl_47; "PillarStatusFlag_Threat_3rdP_ScanNeeded"...
0x18001fb0a  retn
0x18001fb0b  lea     rax, aPillarstatusfl_32; "PillarStatusFlag_Threat_3rdP_SettingsNe"...
0x18001fb12  retn
0x18001fb13  mov     eax, 8Fh
0x18001fb18  cmp     ecx, eax
0x18001fb1a  jg      loc_18001FC46
0x18001fb20  jz      loc_18001FC3E
0x18001fb26  cmp     ecx, 5Bh ; '['
0x18001fb29  jg      loc_18001FBC9
0x18001fb2f  jz      loc_18001FBC1
0x18001fb35  cmp     ecx, 56h ; 'V'
0x18001fb38  jg      short loc_18001FB89
0x18001fb3a  jz      short loc_18001FB81
0x18001fb3c  sub     ecx, 51h ; 'Q'
0x18001fb3f  jz      short loc_18001FB79
0x18001fb41  sub     ecx, 1
0x18001fb44  jz      short loc_18001FB71
0x18001fb46  sub     ecx, 1
0x18001fb49  jz      short loc_18001FB69
0x18001fb4b  sub     ecx, 1
0x18001fb4e  jz      short loc_18001FB61
0x18001fb50  cmp     ecx, 1
0x18001fb53  jnz     loc_18001FC46
  ... truncated ...
```
