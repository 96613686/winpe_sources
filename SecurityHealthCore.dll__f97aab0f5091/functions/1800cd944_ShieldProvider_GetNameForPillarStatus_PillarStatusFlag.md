# ShieldProvider::GetNameForPillarStatus(PillarStatusFlag)

- ea: `0x1800cd944`
- end: `0x1800ce34f`
- name: `?GetNameForPillarStatus@ShieldProvider@@YAPEBGW4PillarStatusFlag@@@Z`
- size: `2571`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013630`
- `0x180036960`
- `0x180070740`
- `0x1800772f0`
- `0x180078328`
- `0x1800b1558`
- `0x1800baa20`
- `0x1800bf804`

## callees

- `0x1800cd944`

## string_xrefs

- `0x1800cd9f7`: `Common_Healthy`
- `0x1800cd9ff`: `Common_Unknown`
- `0x1800cd9df`: `Defender_ServiceStopped`
- `0x1800cdaf6`: `Network_ThirdPartyInstalled`
- `0x1800cdabe`: `Network_ServiceStopped`
- `0x1800cdbcc`: `HealthAdvisor_DriverStatusNeedsUpdate`
- `0x1800cdbb4`: `HealthAdvisor_TimeServiceStatusDisabled`
- `0x1800ce197`: `Hardware_SecureBoot_STATUS_FULLY_UPDATED`
- `0x1800cdcbb`: `Threat_3rdP_ScanRecommended`
- `0x1800cdce3`: `Threat_3rdP_UpdatesRecommended`
- `0x1800cdcab`: `Threat_3rdP_SettingsRecommended`
- `0x1800cdd37`: `Threat_3rdP_SettingsUpdatesRecommended`
- `0x1800cdd3f`: `Threat_3rdP_ScanSettingsRecommended`
- `0x1800cdd47`: `Threat_3rdP_ScanUpdatesRecommended`
- `0x1800cdd4f`: `Threat_3rdP_UpdatesNeeded`
- `0x1800cdd17`: `Threat_3rdP_SettingsUpdatesNeeded`
- `0x1800cdd27`: `Threat_3rdP_ScanUpdatesNeeded`
- `0x1800cdd2f`: `Threat_3rdP_ScanSettingsUpdatesRecommended`
- `0x1800cddd8`: `Threat_3rdP_SettingsUpdatesNeeded_ScanRecommended`
- `0x1800cdde0`: `Threat_3rdP_ScanSettingsNeeded_UpdatesRecommended`
- `0x1800cdde8`: `Threat_3rdP_ScanUpdatesNeeded_SettingsRecommended`
- `0x1800cdd57`: `Threat_3rdP_ScanSettingsUpdatesNeeded`
- `0x1800cddb8`: `Threat_3rdP_SettingsNeeded_ScanRecommended`
- `0x1800cddc0`: `Threat_3rdP_ScanNeeded_SettingsUpdatesRecommended`
- `0x1800cddc8`: `Threat_3rdP_ScanNeeded_UpdatesRecommended`
- `0x1800cddd0`: `Threat_3rdP_ScanNeeded_SettingsRecommended`
- `0x1800cde54`: `Threat_3rdP_UpdatesNeeded_SettingsRecommended`
- `0x1800cde5c`: `Threat_3rdP_UpdatesNeeded_ScanRecommended`
- `0x1800cddf0`: `Threat_3rdP_SettingsNeeded_ScanUpdatesRecommended`
- `0x1800cddb0`: `Threat_3rdP_SettingsNeeded_UpdatesRecommended`
- `0x1800cde3c`: `Threat_3rdP_L1_SingleActionRecommended`
- `0x1800cde4c`: `Threat_3rdP_UpdatesNeeded_ScanSettingsRecommended`
- `0x1800cde2c`: `Threat_3rdP_L1_MultipleActionRecommended`
- `0x1800cdebf`: `Network_3rdP_ActionRecommended`
- `0x1800cdedf`: `Network_3rdP_L2L1_MultipleActionRecommended`
- `0x1800cdea7`: `Network_3rdP_L2L1_ActionRecommended`
- `0x1800cdfbd`: `AccountProtection_WindowsHello_Configured`
- `0x1800ce031`: `AccountProtection_DynamicLock_NotConfigured`
- `0x1800ce107`: `Common_ThirdParty_UnknownStatus`

## pseudocode

```c
const wchar_t *__fastcall ShieldProvider::GetNameForPillarStatus(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  const wchar_t *result; // rax
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

  if ( a1 <= 2000 )
  {
    if ( a1 == 2000 )
      return L"Hardware_SecureBootOff_SCPC";
    if ( a1 > 72 )
    {
      if ( a1 > 108 )
      {
        if ( a1 > 126 )
        {
          if ( a1 > 135 )
          {
            v107 = a1 - 136;
            if ( !v107 )
              return L"OSProtection_ResetRequired";
            v108 = v107 - 1;
            if ( !v108 )
              return L"OSProtection_RebootRequired";
            v109 = v108 - 1;
            if ( !v109 )
              return L"ForceField_Unknown";
            v110 = v109 - 1;
            if ( !v110 )
              return L"ForceField_Healthy";
            v111 = v110 - 1;
            if ( !v111 )
              return L"ForceField_Warning";
            v112 = v111 - 1;
            if ( !v112 )
              return L"ForceField_Error";
            v113 = v112 - 1;
            if ( !v113 )
              return L"Threat_EnterpriseG";
            if ( v113 == 1 )
              return L"Common_ThirdParty_UnknownStatus";
          }
          else
          {
            if ( a1 == 135 )
              return L"OSProtection_Healthy";
            v100 = a1 - 127;
            if ( !v100 )
              return L"AccountProtection_DynamicLock_Remote";
            v101 = v100 - 1;
            if ( !v101 )
              return L"DataProtection_Unknown";
            v102 = v101 - 1;
            if ( !v102 )
              return L"DataProtection_Healthy";
            v103 = v102 - 1;
            if ( !v103 )
              return L"DataProtection_UnsupportedOSSku";
            v104 = v103 - 1;
            if ( !v104 )
              return L"DataProtection_UnsupportedODVersion";
            v105 = v104 - 1;
            if ( !v105 )
              return L"DataProtection_CloudBackupProviderSetupRequired";
            v106 = v105 - 1;
            if ( !v106 )
              return L"DataProtection_DataRestoreRequired";
            if ( v106 == 1 )
              return L"OSProtection_Unknown";
          }
        }
        else
        {
          if ( a1 == 126 )
            return L"AccountProtection_DynamicLock_NotMonitoring";
          if ( a1 > 117 )
          {
            v93 = a1 - 118;
            if ( !v93 )
              return L"AccountProtection_WindowsHello_StoppedWorking_Pwdless";
            v94 = v93 - 1;
            if ( !v94 )
              return L"AccountProtection_WindowsHello_StoppedWorking_PwdAcct";
            v95 = v94 - 1;
            if ( !v95 )
              return L"AccountProtection_WindowsHello_StoppedWorking_PwdAcct_Dismissed";
            v96 = v95 - 1;
            if ( !v96 )
              return L"AccountProtection_DynamicLock_NotConfigured";
            v97 = v96 - 1;
            if ( !v97 )
              return L"AccountProtection_DynamicLock_BluetoothOff";
            v98 = v97 - 1;
            if ( !v98 )
              return L"AccountProtection_DynamicLock_NoPairedDevices";
            v99 = v98 - 1;
            if ( !v99 )
              return L"AccountProtection_DynamicLock_Scanning";
            if ( v99 == 1 )
              return L"AccountProtection_DynamicLock_Monitoring";
          }
          else
          {
            if ( a1 == 117 )
              return L"AccountProtection_WindowsHello_NotSetUpCritical";
            v86 = a1 - 109;
            if ( !v86 )
              return (const wchar_t *)&stru_180100C10;
            v87 = v86 - 1;
            if ( !v87 )
              return L"AccountProtection_MicrosoftAccount_Unverified";
            v88 = v87 - 1;
            if ( !v88 )
              return L"AccountProtection_MicrosoftAccount_Unverified_Dismissed";
            v89 = v88 - 1;
            if ( !v89 )
              return L"AccountProtection_WindowsHello_Configured";
            v90 = v89 - 1;
            if ( !v90 )
              return L"AccountProtection_WindowsHello_Available";
            v91 = v90 - 1;
            if ( !v91 )
              return L"AccountProtection_WindowsHello_Available_Dismissed1";
            v92 = v91 - 1;
            if ( !v92 )
              return L"AccountProtection_WindowsHello_Available_Dismissed2";
            if ( v92 == 1 )
              return L"AccountProtection_WindowsHello_NotAvailable";
          }
        }
      }
      else
      {
        if ( a1 == 108 )
          return L"AccountProtection_MicrosoftAccount_NotAvailable";
        if ( a1 > 90 )
        {
          if ( a1 > 99 )
          {
            v79 = a1 - 100;
            if ( !v79 )
              return L"Network_3rdP_L2L1_MultipleActionNeeded";
            v80 = v79 - 1;
            if ( !v80 )
              return L"AccountProtection_Unknown";
            v81 = v80 - 1;
            if ( !v81 )
              return L"AccountProtection_Healthy";
            v82 = v81 - 1;
            if ( !v82 )
              return L"AccountProtection_MicrosoftAccount_Connected";
            v83 = v82 - 1;
            if ( !v83 )
              return L"AccountProtection_MicrosoftAccount_Disconnected";
            v84 = v83 - 1;
            if ( !v84 )
              return L"AccountProtection_MicrosoftAccount_Disconnected_Dismissed1";
            v85 = v84 - 1;
            if ( !v85 )
              return L"AccountProtection_MicrosoftAccount_Disconnected_Dismissed2";
            if ( v85 == 1 )
              return L"AccountProtection_MicrosoftAccount_Associated";
          }
          else
          {
            if ( a1 == 99 )
              return L"Network_3rdP_L2L1_MultipleActionRecommended";
            v72 = a1 - 91;
            if ( !v72 )
              return L"Network_3rdP_Off";
            v73 = v72 - 1;
            if ( !v73 )
              return L"Network_3rdP_Expired";
            v74 = v73 - 1;
            if ( !v74 )
              return L"Network_3rdP_Snoozed";
            v75 = v74 - 1;
            if ( !v75 )
              return L"Network_3rdP_ActionRecommended";
            v76 = v75 - 1;
            if ( !v76 )
              return L"Network_3rdP_ActionNeeded";
            v77 = v76 - 1;
            if ( !v77 )
              return L"Network_3rdP_L2L1_NoAction";
            v78 = v77 - 1;
            if ( !v78 )
              return L"Network_3rdP_L2L1_ActionRecommended";
            if ( v78 == 1 )
              return L"Network_3rdP_L2L1_ActionNeeded";
          }
        }
        else
        {
          if ( a1 == 90 )
            return L"Network_3rdP_NoAction";
          if ( a1 > 81 )
          {
            v65 = a1 - 82;
            if ( !v65 )
              return L"Threat_3rdP_UpdatesNeeded_ScanRecommended";
            v66 = v65 - 1;
            if ( !v66 )
              return L"Threat_3rdP_UpdatesNeeded_SettingsRecommended";
            v67 = v66 - 1;
            if ( !v67 )
              return L"Threat_3rdP_UpdatesNeeded_ScanSettingsRecommended";
            v68 = v67 - 1;
            if ( !v68 )
              return L"Threat_3rdP_L1_NoAction";
            v69 = v68 - 1;
            if ( !v69 )
              return L"Threat_3rdP_L1_SingleActionRecommended";
            v70 = v69 - 1;
            if ( !v70 )
              return L"Threat_3rdP_L1_SingleActionNeeded";
            v71 = v70 - 1;
            if ( !v71 )
              return L"Threat_3rdP_L1_MultipleActionRecommended";
            if ( v71 == 1 )
              return L"Threat_3rdP_L1_MultipleActionNeeded";
          }
          else
          {
            if ( a1 == 81 )
              return L"Threat_3rdP_SettingsNeeded_ScanUpdatesRecommended";
            v58 = a1 - 73;
            if ( !v58 )
              return L"Threat_3rdP_ScanUpdatesNeeded_SettingsRecommended";
            v59 = v58 - 1;
            if ( !v59 )
              return L"Threat_3rdP_ScanSettingsNeeded_UpdatesRecommended";
            v60 = v59 - 1;
            if ( !v60 )
              return L"Threat_3rdP_SettingsUpdatesNeeded_ScanRecommended";
            v61 = v60 - 1;
            if ( !v61 )
              return L"Threat_3rdP_ScanNeeded_SettingsRecommended";
            v62 = v61 - 1;
            if ( !v62 )
              return L"Threat_3rdP_ScanNeeded_UpdatesRecommended";
            v63 = v62 - 1;
            if ( !v63 )
              return L"Threat_3rdP_ScanNeeded_SettingsUpdatesRecommended";
            v64 = v63 - 1;
            if ( !v64 )
              return L"Threat_3rdP_SettingsNeeded_ScanRecommended";
            if ( v64 == 1 )
              return L"Threat_3rdP_SettingsNeeded_UpdatesRecommended";
          }
        }
      }
    }
    else
    {
      if ( a1 == 72 )
        return L"Threat_3rdP_ScanSettingsUpdatesNeeded";
      if ( a1 > 36 )
      {
        if ( a1 > 54 )
        {
          if ( a1 > 63 )
          {
            v51 = a1 - 64;
            if ( !v51 )
              return L"Threat_3rdP_UpdatesNeeded";
            v52 = v51 - 1;
            if ( !v52 )
              return L"Threat_3rdP_ScanUpdatesRecommended";
            v53 = v52 - 1;
            if ( !v53 )
              return L"Threat_3rdP_ScanSettingsRecommended";
            v54 = v53 - 1;
            if ( !v54 )
              return L"Threat_3rdP_SettingsUpdatesRecommended";
            v55 = v54 - 1;
            if ( !v55 )
              return L"Threat_3rdP_ScanSettingsUpdatesRecommended";
            v56 = v55 - 1;
            if ( !v56 )
              return L"Threat_3rdP_ScanUpdatesNeeded";
            v57 = v56 - 1;
            if ( !v57 )
              return L"Threat_3rdP_ScanSettingsNeeded";
            if ( v57 == 1 )
              return L"Threat_3rdP_SettingsUpdatesNeeded";
          }
          else
          {
            if ( a1 == 63 )
              return L"Threat_3rdP_UpdatesRecommended";
            v44 = a1 - 55;
            if ( !v44 )
              return L"Threat_3rdP_Expired";
            v45 = v44 - 1;
            if ( !v45 )
              return L"Threat_3rdP_SignaturesOutOfDate";
            v46 = v45 - 1;
            if ( !v46 )
              return L"Threat_3rdP_Snoozed";
            v47 = v46 - 1;
            if ( !v47 )
              return L"Threat_3rdP_NearExpiry";
            v48 = v47 - 1;
            if ( !v48 )
              return L"Threat_3rdP_ScanRecommended";
            v49 = v48 - 1;
            if ( !v49 )
              return L"Threat_3rdP_ScanNeeded";
            v50 = v49 - 1;
            if ( !v50 )
              return L"Threat_3rdP_SettingsRecommended";
            if ( v50 == 1 )
              return L"Threat_3rdP_SettingsNeeded";
          }
        }
        else
        {
          if ( a1 == 54 )
            return L"Threat_3rdP_Off";
          if ( a1 > 45 )
          {
            v37 = a1 - 46;
            if ( !v37 )
              return L"AppAndBrowser_Healthy";
            v38 = v37 - 1;
            if ( !v38 )
              return L"AppAndBrowser_PuaSmartScreenOff";
            v39 = v38 - 1;
            if ( !v39 )
              return L"AppAndBrowser_EdgeSmartScreenOff";
            v40 = v39 - 1;
            if ( !v40 )
              return L"AppAndBrowser_AppRepSmartScreenOff";
            v41 = v40 - 1;
            if ( !v41 )
              return L"AppAndBrowser_StoreAppsSmartScreenOff";
            v42 = v41 - 1;
            if ( !v42 )
              return L"Hardware_Unknown";
            v43 = v42 - 1;
            if ( !v43 )
              return L"Hardware_Healthy";
            if ( v43 == 1 )
              return L"Threat_3rdP_NoAction";
          }
          else
          {
            if ( a1 == 45 )
              return L"AppAndBrowser_Unknown";
            v30 = a1 - 37;
            if ( !v30 )
              return L"HealthAdvisor_StorageHealthOkWithIssues";
            v31 = v30 - 1;
            if ( !v31 )
              return L"HealthAdvisor_PristineShellContentPresent";
            v32 = v31 - 1;
            if ( !v32 )
              return L"HealthAdvisor_BatteryBrightnessAlert";
            v33 = v32 - 1;
            if ( !v33 )
              return L"HealthAdvisor_BatterySleepSettingsAlert";
            v34 = v33 - 1;
            if ( !v34 )
              return L"HealthAdvisor_DriverStatusNeedsUpdate";
            v35 = v34 - 1;
            if ( !v35 )
              return L"HealthAdvisor_DriverStatusNonOperationalOther";
            v36 = v35 - 1;
            if ( !v36 )
              return L"HealthAdvisor_ReliabilityStatusAppError";
            if ( v36 == 1 )
              return L"HealthAdvisor_TimeServiceStatusDisabled";
          }
        }
      }
      else
      {
        if ( a1 == 36 )
          return L"HealthAdvisor_StorageDiskspaceLow";
        if ( a1 > 18 )
        {
          if ( a1 > 27 )
          {
            v23 = a1 - 28;
            if ( !v23 )
              return L"Network_DomainFwOff";
            v24 = v23 - 1;
            if ( !v24 )
              return L"Network_PrivateFwOff";
            v25 = v24 - 1;
            if ( !v25 )
              return L"Network_PublicFwOff";
            v26 = v25 - 1;
            if ( !v26 )
              return L"Network_MultipleFwOff";
            v27 = v26 - 1;
            if ( !v27 )
              return L"HealthAdvisor_Unknown";
            v28 = v27 - 1;
            if ( !v28 )
              return L"HealthAdvisor_Healthy";
            v29 = v28 - 1;
            if ( !v29 )
              return L"HealthAdvisor_Warning";
            if ( v29 == 1 )
              return L"HealthAdvisor_Critical";
          }
          else
          {
            if ( a1 == 27 )
              return L"Network_ThirdPartyInstalled";
            v16 = a1 - 19;
            if ( !v16 )
              return L"DefenderPua_Unknown";
            v17 = v16 - 1;
            if ( !v17 )
              return L"DefenderPua_Healthy";
            v18 = v17 - 1;
            if ( !v18 )
              return L"DefenderPua_PuaDisabled";
            v19 = v18 - 1;
            if ( !v19 )
              return L"DefenderPua_ActivePuaDetections";
            v20 = v19 - 1;
            if ( !v20 )
              return L"Network_Unknown";
            v21 = v20 - 1;
            if ( !v21 )
              return L"Network_Healthy";
            v22 = v21 - 1;
            if ( !v22 )
              return L"Network_ServiceStopped";
            if ( v22 == 1 )
              return L"Network_NonSecureState";
          }
        }
        else
        {
          if ( a1 == 18 )
            return L"Defender_SModeSigsDue";
          if ( a1 > 9 )
          {
            v9 = a1 - 10;
            if ( !v9 )
              return L"Defender_WdoRequired";
            v10 = v9 - 1;
            if ( !v10 )
              return L"Defender_AvSigsDue";
            v11 = v10 - 1;
            if ( !v11 )
              return L"Defender_AsSigsDue";
            v12 = v11 - 1;
            if ( !v12 )
              return L"Defender_QuickScanDue";
            v13 = v12 - 1;
            if ( !v13 )
              return L"Defender_FullScanDue";
            v14 = v13 - 1;
            if ( !v14 )
              return L"Defender_CloudProtectionDisabled";
            v15 = v14 - 1;
            if ( !v15 )
              return L"Defender_AutoSampleSubmissionDisabled";
            if ( v15 == 1 )
              return L"Defender_TamperProtectionDisabled";
          }
          else
          {
            if ( a1 == 9 )
              return L"Defender_RebootRequired";
            if ( !a1 )
              return L"Common_Unknown";
            v1 = a1 - 1;
            if ( !v1 )
              return L"Common_Healthy";
            v2 = v1 - 1;
            if ( !v2 )
              return L"Defender_Unknown";
            v3 = v2 - 1;
            if ( !v3 )
              return L"Defender_Healthy";
            v4 = v3 - 1;
            if ( !v4 )
              return L"Defender_ServiceStopped";
            v5 = v4 - 1;
            if ( !v5 )
              return L"Defender_EngineUnavailable";
            v6 = v5 - 1;
            if ( !v6 )
              return L"Defender_ActiveThreats";
            v7 = v6 - 1;
            if ( !v7 )
              return L"Defender_RtpDisabled";
            if ( v7 == 1 )
              return L"Defender_FullScanRequired";
          }
        }
      }
    }
    return (const wchar_t *)L"Unknown";
  }
  if ( a1 > 3001 )
    return (const wchar_t *)L"Unknown";
  if ( a1 == 3001 )
    return L"AppAndBrowser_PhishingSensorsOff";
  switch ( a1 )
  {
    case 2001:
    case 2003:
      result = L"Hardware_SecureBoot_Off_Dismissed";
      break;
    case 2002:
      result = L"Hardware_SecureBoot_NotAvailable";
      break;
    case 2004:
      result = L"Hardware_HVCI_Off";
      break;
    case 2005:
      result = L"Hardware_CoreIsolation_HVCI_On_Healthy";
      break;
    case 2006:
      result = L"Hardware_CoreIsolation_HVCI_Dismissed";
      break;
    case 2007:
      result = L"Hardware_CoreIsolation_HVCI_NotAvailable";
      break;
    case 2008:
      result = L"Hardware_DataEncryption_On_Healthy";
      break;
    case 2009:
      result = L"Hardware_DataEncryption_BackupRequired";
      break;
    case 2010:
      result = L"Hardware_DataEncryption_Dismissed";
      break;
    case 2011:
      result = L"Hardware_DataEncryption_NotAvailable";
      break;
    case 2012:
      result = L"Hardware_PlatformResiliency_NotAvailable";
      break;
    case 2013:
      result = L"Hardware_PlatformResiliency_Healthy";
      break;
    case 2014:
      result = L"Hardware_PlatformResiliency_Errors";
      break;
    case 2016:
      result = L"Hardware_PlatformResiliency_BootHealth_Error";
      break;
    case 2017:
      result = L"Hardware_PlatformResiliency_BootHealth_Error_Dismissed";
      break;
    case 2018:
      result = L"Hardware_PlatformResiliency_CaseTamper_Error";
      break;
    case 2019:
      result = L"Hardware_PlatformResiliency_CaseTamper_Error_Dismissed";
      break;
    case 2020:
      result = L"Hardware_PlatformResiliency_HspApi_Error";
      break;
    case 2021:
      result = L"Hardware_PlatformResiliency_HspApi_Error_Dismissed";
      break;
    case 2022:
      result = L"Hardware_SecProc_Healthy";
      break;
    case 2023:
      result = L"Hardware_SecProc_NotAvailable";
      break;
    case 2024:
      result = (const wchar_t *)L"Hardware_SecProc_NotAvailable_SCPC";
      break;
    case 2025:
      result = L"Hardware_SecProc_NotAvailable_SCPC_Dismissed";
      break;
    case 2026:
      result = L"PillarStatusFlag_Hardware_SystemGuard_Off";
      break;
    case 2027:
      result = L"Hardware_SystemGuard_Off_Managed";
      break;
    case 2028:
      result = L"Hardware_SystemGuard_On_Healthy";
      break;
    case 2029:
      result = L"Hardware_SystemGuard_Dismissed";
      break;
    case 2030:
      result = L"Hardware_CoreIsolation_Multiple_Off";
      break;
    case 2031:
      result = L"Hardware_SystemGuard_NotAvailable";
      break;
    case 2032:
      result = L"Hardware_LsaPpl_Off";
      break;
    case 2033:
      result = L"Hardware_LsaPpl_Off_Managed";
      break;
    case 2034:
      result = L"Hardware_LsaPpl_On_Healthy";
      break;
    case 2035:
      result = L"Hardware_LsaPpl_Dismissed";
      break;
    case 2036:
      result = L"Hardware_LsaPpl_NotAvailable";
      break;
    case 2037:
      result = L"Hardware_DataEncryption_AddMsa";
      break;
    case 2038:
      result = L"Hardware_CoreIsolation_KCET_Off";
      break;
    case 2039:
      result = L"Hardware_CoreIsolation_KCET_On_Healthy";
      break;
    case 2040:
      result = L"Hardware_CoreIsolation_KCET_Dismissed";
      break;
    case 2041:
      result = L"Hardware_CoreIsolation_KCET_NotAvailable";
      break;
    case 2042:
      result = L"PillarStatusFlag_Hardware_SecProc_TPMTroublshooterError";
      break;
    case 2043:
      result = L"PillarStatusFlag_Hardware_SecProc_TPMTroublshooterError_Dismissed";
      break;
    case 2044:
      result = L"Hardware_SecureBoot_STATUS_FULLY_UPDATED";
      break;
    case 2045:
      result = L"Hardware_SecureBoot_STATUS_BEFORE_EXPIRED";
      break;
    case 2046:
      result = L"Hardware_SecureBoot_STATUS_EXPIRED";
      break;
    case 2047:
      result = (const wchar_t *)L"Hardware_SecureBoot_STATUS_EXPIRED_VULNERABLE";
      break;
    case 2048:
      result = L"Hardware_SecureBoot_STATUS_PAUSED";
      break;
    case 2049:
      result = L"Hardware_SecureBoot_STATUS_PAUSED_IN_RED";
      break;
    case 2050:
      result = L"Hardware_SecureBoot_STATUS_NEEDS_DATA";
      break;
    case 2051:
      result = L"Hardware_SecureBoot_STATUS_NEEDS_DATA_IN_RED";
      break;
    case 2052:
      result = L"Hardware_SecureBoot_STATUS_FW_ERROR";
      break;
    case 2053:
      result = L"Hardware_SecureBoot_STATUS_FW_ERROR_Dismissed";
      break;
    case 2054:
      result = L"Hardware_SecureBoot_STATUS_FW_ERROR_IN_RED";
      break;
    case 2055:
      result = L"Hardware_SecureBoot_STATUS_EXPIRED_Dismissed";
      break;
    case 2056:
      result = L"Hardware_SecureBoot_STATUS_PAUSED_Dismissed";
      break;
    case 2057:
      result = L"Hardware_SecureBoot_STATUS_NEEDS_DATA_Dismissed";
      break;
    default:
      return (const wchar_t *)L"Unknown";
  }
  return result;
}

```

## disassembly

```asm
0x1800cd944  mov     eax, 7D0h
0x1800cd949  cmp     ecx, eax
0x1800cd94b  jg      loc_1800CE14F
0x1800cd951  jz      loc_1800CE147
0x1800cd957  cmp     ecx, 48h ; 'H'
0x1800cd95a  jg      loc_1800CDD5F
0x1800cd960  jz      loc_1800CDD57
0x1800cd966  cmp     ecx, 24h ; '$'
0x1800cd969  jg      loc_1800CDB72
0x1800cd96f  jz      loc_1800CDB6A
0x1800cd975  cmp     ecx, 12h
0x1800cd978  jg      loc_1800CDA83
0x1800cd97e  jz      loc_1800CDA7B
0x1800cd984  cmp     ecx, 9
0x1800cd987  jg      loc_1800CDA0F
0x1800cd98d  jz      short loc_1800CDA07
0x1800cd98f  test    ecx, ecx
0x1800cd991  jz      short loc_1800CD9FF
0x1800cd993  sub     ecx, 1
0x1800cd996  jz      short loc_1800CD9F7
0x1800cd998  sub     ecx, 1
0x1800cd99b  jz      short loc_1800CD9EF
0x1800cd99d  sub     ecx, 1
0x1800cd9a0  jz      short loc_1800CD9E7
0x1800cd9a2  sub     ecx, 1
0x1800cd9a5  jz      short loc_1800CD9DF
0x1800cd9a7  sub     ecx, 1
0x1800cd9aa  jz      short loc_1800CD9D7
0x1800cd9ac  sub     ecx, 1
0x1800cd9af  jz      short loc_1800CD9CF
0x1800cd9b1  sub     ecx, 1
0x1800cd9b4  jz      short loc_1800CD9C7
0x1800cd9b6  cmp     ecx, 1
0x1800cd9b9  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cd9bf  lea     rax, aDefenderFullsc; "Defender_FullScanRequired"
0x1800cd9c6  retn
0x1800cd9c7  lea     rax, aDefenderRtpdis; "Defender_RtpDisabled"
0x1800cd9ce  retn
0x1800cd9cf  lea     rax, aDefenderActive; "Defender_ActiveThreats"
0x1800cd9d6  retn
0x1800cd9d7  lea     rax, aDefenderEngine; "Defender_EngineUnavailable"
0x1800cd9de  retn
0x1800cd9df  lea     rax, aDefenderServic; "Defender_ServiceStopped"
0x1800cd9e6  retn
0x1800cd9e7  lea     rax, aDefenderHealth; "Defender_Healthy"
0x1800cd9ee  retn
0x1800cd9ef  lea     rax, aDefenderUnknow; "Defender_Unknown"
0x1800cd9f6  retn
0x1800cd9f7  lea     rax, aCommonHealthy; "Common_Healthy"
0x1800cd9fe  retn
0x1800cd9ff  lea     rax, aCommonUnknown; "Common_Unknown"
0x1800cda06  retn
0x1800cda07  lea     rax, aDefenderReboot; "Defender_RebootRequired"
0x1800cda0e  retn
0x1800cda0f  sub     ecx, 0Ah
0x1800cda12  jz      short loc_1800CDA73
0x1800cda14  sub     ecx, 1
0x1800cda17  jz      short loc_1800CDA6B
0x1800cda19  sub     ecx, 1
0x1800cda1c  jz      short loc_1800CDA63
0x1800cda1e  sub     ecx, 1
0x1800cda21  jz      short loc_1800CDA5B
0x1800cda23  sub     ecx, 1
0x1800cda26  jz      short loc_1800CDA53
0x1800cda28  sub     ecx, 1
0x1800cda2b  jz      short loc_1800CDA4B
0x1800cda2d  sub     ecx, 1
0x1800cda30  jz      short loc_1800CDA43
0x1800cda32  cmp     ecx, 1
0x1800cda35  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cda3b  lea     rax, aDefenderTamper; "Defender_TamperProtectionDisabled"
0x1800cda42  retn
0x1800cda43  lea     rax, aDefenderAutosa; "Defender_AutoSampleSubmissionDisabled"
0x1800cda4a  retn
0x1800cda4b  lea     rax, aDefenderCloudp; "Defender_CloudProtectionDisabled"
0x1800cda52  retn
0x1800cda53  lea     rax, aDefenderFullsc_0; "Defender_FullScanDue"
0x1800cda5a  retn
0x1800cda5b  lea     rax, aDefenderQuicks; "Defender_QuickScanDue"
0x1800cda62  retn
0x1800cda63  lea     rax, aDefenderAssigs; "Defender_AsSigsDue"
0x1800cda6a  retn
0x1800cda6b  lea     rax, aDefenderAvsigs; "Defender_AvSigsDue"
0x1800cda72  retn
0x1800cda73  lea     rax, aDefenderWdoreq; "Defender_WdoRequired"
0x1800cda7a  retn
0x1800cda7b  lea     rax, aDefenderSmodes; "Defender_SModeSigsDue"
0x1800cda82  retn
0x1800cda83  cmp     ecx, 1Bh
0x1800cda86  jg      short loc_1800CDAFE
0x1800cda88  jz      short loc_1800CDAF6
0x1800cda8a  sub     ecx, 13h
0x1800cda8d  jz      short loc_1800CDAEE
0x1800cda8f  sub     ecx, 1
0x1800cda92  jz      short loc_1800CDAE6
0x1800cda94  sub     ecx, 1
0x1800cda97  jz      short loc_1800CDADE
0x1800cda99  sub     ecx, 1
0x1800cda9c  jz      short loc_1800CDAD6
0x1800cda9e  sub     ecx, 1
0x1800cdaa1  jz      short loc_1800CDACE
0x1800cdaa3  sub     ecx, 1
0x1800cdaa6  jz      short loc_1800CDAC6
0x1800cdaa8  sub     ecx, 1
0x1800cdaab  jz      short loc_1800CDABE
0x1800cdaad  cmp     ecx, 1
0x1800cdab0  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdab6  lea     rax, aNetworkNonsecu; "Network_NonSecureState"
0x1800cdabd  retn
0x1800cdabe  lea     rax, aNetworkService; "Network_ServiceStopped"
0x1800cdac5  retn
0x1800cdac6  lea     rax, aNetworkHealthy; "Network_Healthy"
0x1800cdacd  retn
0x1800cdace  lea     rax, aNetworkUnknown; "Network_Unknown"
0x1800cdad5  retn
0x1800cdad6  lea     rax, aDefenderpuaAct; "DefenderPua_ActivePuaDetections"
0x1800cdadd  retn
0x1800cdade  lea     rax, aDefenderpuaPua; "DefenderPua_PuaDisabled"
0x1800cdae5  retn
0x1800cdae6  lea     rax, aDefenderpuaHea; "DefenderPua_Healthy"
0x1800cdaed  retn
0x1800cdaee  lea     rax, aDefenderpuaUnk; "DefenderPua_Unknown"
0x1800cdaf5  retn
0x1800cdaf6  lea     rax, aNetworkThirdpa; "Network_ThirdPartyInstalled"
0x1800cdafd  retn
0x1800cdafe  sub     ecx, 1Ch
0x1800cdb01  jz      short loc_1800CDB62
0x1800cdb03  sub     ecx, 1
0x1800cdb06  jz      short loc_1800CDB5A
0x1800cdb08  sub     ecx, 1
0x1800cdb0b  jz      short loc_1800CDB52
0x1800cdb0d  sub     ecx, 1
0x1800cdb10  jz      short loc_1800CDB4A
0x1800cdb12  sub     ecx, 1
0x1800cdb15  jz      short loc_1800CDB42
0x1800cdb17  sub     ecx, 1
0x1800cdb1a  jz      short loc_1800CDB3A
0x1800cdb1c  sub     ecx, 1
0x1800cdb1f  jz      short loc_1800CDB32
0x1800cdb21  cmp     ecx, 1
0x1800cdb24  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdb2a  lea     rax, aHealthadvisorC; "HealthAdvisor_Critical"
0x1800cdb31  retn
0x1800cdb32  lea     rax, aHealthadvisorW; "HealthAdvisor_Warning"
0x1800cdb39  retn
0x1800cdb3a  lea     rax, aHealthadvisorH; "HealthAdvisor_Healthy"
0x1800cdb41  retn
0x1800cdb42  lea     rax, aHealthadvisorU; "HealthAdvisor_Unknown"
0x1800cdb49  retn
0x1800cdb4a  lea     rax, aNetworkMultipl; "Network_MultipleFwOff"
0x1800cdb51  retn
0x1800cdb52  lea     rax, aNetworkPublicf; "Network_PublicFwOff"
0x1800cdb59  retn
0x1800cdb5a  lea     rax, aNetworkPrivate; "Network_PrivateFwOff"
0x1800cdb61  retn
0x1800cdb62  lea     rax, aNetworkDomainf; "Network_DomainFwOff"
0x1800cdb69  retn
0x1800cdb6a  lea     rax, aHealthadvisorS; "HealthAdvisor_StorageDiskspaceLow"
0x1800cdb71  retn
0x1800cdb72  cmp     ecx, 36h ; '6'
0x1800cdb75  jg      loc_1800CDC70
0x1800cdb7b  jz      loc_1800CDC68
0x1800cdb81  cmp     ecx, 2Dh ; '-'
0x1800cdb84  jg      short loc_1800CDBFC
0x1800cdb86  jz      short loc_1800CDBF4
0x1800cdb88  sub     ecx, 25h ; '%'
0x1800cdb8b  jz      short loc_1800CDBEC
0x1800cdb8d  sub     ecx, 1
0x1800cdb90  jz      short loc_1800CDBE4
0x1800cdb92  sub     ecx, 1
0x1800cdb95  jz      short loc_1800CDBDC
0x1800cdb97  sub     ecx, 1
0x1800cdb9a  jz      short loc_1800CDBD4
0x1800cdb9c  sub     ecx, 1
0x1800cdb9f  jz      short loc_1800CDBCC
0x1800cdba1  sub     ecx, 1
0x1800cdba4  jz      short loc_1800CDBC4
0x1800cdba6  sub     ecx, 1
0x1800cdba9  jz      short loc_1800CDBBC
0x1800cdbab  cmp     ecx, 1
0x1800cdbae  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdbb4  lea     rax, aHealthadvisorT; "HealthAdvisor_TimeServiceStatusDisabled"
0x1800cdbbb  retn
0x1800cdbbc  lea     rax, aHealthadvisorR; "HealthAdvisor_ReliabilityStatusAppError"
0x1800cdbc3  retn
0x1800cdbc4  lea     rax, aHealthadvisorD_0; "HealthAdvisor_DriverStatusNonOperationa"...
0x1800cdbcb  retn
0x1800cdbcc  lea     rax, aHealthadvisorD; "HealthAdvisor_DriverStatusNeedsUpdate"
0x1800cdbd3  retn
0x1800cdbd4  lea     rax, aHealthadvisorB; "HealthAdvisor_BatterySleepSettingsAlert"
0x1800cdbdb  retn
0x1800cdbdc  lea     rax, aHealthadvisorB_0; "HealthAdvisor_BatteryBrightnessAlert"
0x1800cdbe3  retn
0x1800cdbe4  lea     rax, aHealthadvisorP; "HealthAdvisor_PristineShellContentPrese"...
0x1800cdbeb  retn
0x1800cdbec  lea     rax, aHealthadvisorS_0; "HealthAdvisor_StorageHealthOkWithIssues"
0x1800cdbf3  retn
0x1800cdbf4  lea     rax, aAppandbrowserU; "AppAndBrowser_Unknown"
0x1800cdbfb  retn
0x1800cdbfc  sub     ecx, 2Eh ; '.'
0x1800cdbff  jz      short loc_1800CDC60
0x1800cdc01  sub     ecx, 1
0x1800cdc04  jz      short loc_1800CDC58
0x1800cdc06  sub     ecx, 1
0x1800cdc09  jz      short loc_1800CDC50
0x1800cdc0b  sub     ecx, 1
0x1800cdc0e  jz      short loc_1800CDC48
0x1800cdc10  sub     ecx, 1
0x1800cdc13  jz      short loc_1800CDC40
0x1800cdc15  sub     ecx, 1
0x1800cdc18  jz      short loc_1800CDC38
0x1800cdc1a  sub     ecx, 1
0x1800cdc1d  jz      short loc_1800CDC30
0x1800cdc1f  cmp     ecx, 1
0x1800cdc22  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdc28  lea     rax, aThreat3rdpNoac; "Threat_3rdP_NoAction"
0x1800cdc2f  retn
0x1800cdc30  lea     rax, aHardwareHealth; "Hardware_Healthy"
0x1800cdc37  retn
0x1800cdc38  lea     rax, aHardwareUnknow; "Hardware_Unknown"
0x1800cdc3f  retn
0x1800cdc40  lea     rax, aAppandbrowserS; "AppAndBrowser_StoreAppsSmartScreenOff"
0x1800cdc47  retn
0x1800cdc48  lea     rax, aAppandbrowserA; "AppAndBrowser_AppRepSmartScreenOff"
0x1800cdc4f  retn
0x1800cdc50  lea     rax, aAppandbrowserE; "AppAndBrowser_EdgeSmartScreenOff"
0x1800cdc57  retn
0x1800cdc58  lea     rax, aAppandbrowserP; "AppAndBrowser_PuaSmartScreenOff"
0x1800cdc5f  retn
0x1800cdc60  lea     rax, aAppandbrowserH; "AppAndBrowser_Healthy"
0x1800cdc67  retn
0x1800cdc68  lea     rax, aThreat3rdpOff; "Threat_3rdP_Off"
0x1800cdc6f  retn
0x1800cdc70  cmp     ecx, 3Fh ; '?'
0x1800cdc73  jg      short loc_1800CDCEB
0x1800cdc75  jz      short loc_1800CDCE3
0x1800cdc77  sub     ecx, 37h ; '7'
0x1800cdc7a  jz      short loc_1800CDCDB
0x1800cdc7c  sub     ecx, 1
0x1800cdc7f  jz      short loc_1800CDCD3
0x1800cdc81  sub     ecx, 1
0x1800cdc84  jz      short loc_1800CDCCB
0x1800cdc86  sub     ecx, 1
0x1800cdc89  jz      short loc_1800CDCC3
0x1800cdc8b  sub     ecx, 1
0x1800cdc8e  jz      short loc_1800CDCBB
0x1800cdc90  sub     ecx, 1
0x1800cdc93  jz      short loc_1800CDCB3
0x1800cdc95  sub     ecx, 1
0x1800cdc98  jz      short loc_1800CDCAB
0x1800cdc9a  cmp     ecx, 1
0x1800cdc9d  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdca3  lea     rax, aThreat3rdpSett_1; "Threat_3rdP_SettingsNeeded"
0x1800cdcaa  retn
0x1800cdcab  lea     rax, aThreat3rdpSett_4; "Threat_3rdP_SettingsRecommended"
0x1800cdcb2  retn
0x1800cdcb3  lea     rax, aThreat3rdpScan_11; "Threat_3rdP_ScanNeeded"
0x1800cdcba  retn
0x1800cdcbb  lea     rax, aThreat3rdpScan_6; "Threat_3rdP_ScanRecommended"
0x1800cdcc2  retn
0x1800cdcc3  lea     rax, aThreat3rdpNear; "Threat_3rdP_NearExpiry"
0x1800cdcca  retn
0x1800cdccb  lea     rax, aThreat3rdpSnoo; "Threat_3rdP_Snoozed"
0x1800cdcd2  retn
0x1800cdcd3  lea     rax, aThreat3rdpSign; "Threat_3rdP_SignaturesOutOfDate"
0x1800cdcda  retn
0x1800cdcdb  lea     rax, aThreat3rdpExpi; "Threat_3rdP_Expired"
0x1800cdce2  retn
0x1800cdce3  lea     rax, aThreat3rdpUpda_0; "Threat_3rdP_UpdatesRecommended"
0x1800cdcea  retn
0x1800cdceb  sub     ecx, 40h ; '@'
0x1800cdcee  jz      short loc_1800CDD4F
0x1800cdcf0  sub     ecx, 1
0x1800cdcf3  jz      short loc_1800CDD47
0x1800cdcf5  sub     ecx, 1
0x1800cdcf8  jz      short loc_1800CDD3F
0x1800cdcfa  sub     ecx, 1
0x1800cdcfd  jz      short loc_1800CDD37
0x1800cdcff  sub     ecx, 1
0x1800cdd02  jz      short loc_1800CDD2F
0x1800cdd04  sub     ecx, 1
0x1800cdd07  jz      short loc_1800CDD27
0x1800cdd09  sub     ecx, 1
0x1800cdd0c  jz      short loc_1800CDD1F
0x1800cdd0e  cmp     ecx, 1
0x1800cdd11  jnz     def_1800CE185; jumptable 00000001800CE185 default case, case 2015
0x1800cdd17  lea     rax, aThreat3rdpSett_2; "Threat_3rdP_SettingsUpdatesNeeded"
0x1800cdd1e  retn
0x1800cdd1f  lea     rax, aThreat3rdpScan; "Threat_3rdP_ScanSettingsNeeded"
0x1800cdd26  retn
0x1800cdd27  lea     rax, aThreat3rdpScan_7; "Threat_3rdP_ScanUpdatesNeeded"
0x1800cdd2e  retn
0x1800cdd2f  lea     rax, aThreat3rdpScan_0; "Threat_3rdP_ScanSettingsUpdatesRecommen"...
0x1800cdd36  retn
0x1800cdd37  lea     rax, aThreat3rdpSett_3; "Threat_3rdP_SettingsUpdatesRecommended"
0x1800cdd3e  retn
0x1800cdd3f  lea     rax, aThreat3rdpScan_8; "Threat_3rdP_ScanSettingsRecommended"
0x1800cdd46  retn
0x1800cdd47  lea     rax, aThreat3rdpScan_5; "Threat_3rdP_ScanUpdatesRecommended"
0x1800cdd4e  retn
  ... truncated ...
```
