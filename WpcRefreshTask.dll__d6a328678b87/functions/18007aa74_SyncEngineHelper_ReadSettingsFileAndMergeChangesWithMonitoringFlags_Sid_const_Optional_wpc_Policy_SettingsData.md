# SyncEngineHelper::ReadSettingsFileAndMergeChangesWithMonitoringFlags(Sid const &,Optional<wpc::Policy::SettingsData> const &,Optional<wpc::Policy::TimeRestrictionsSettings> const &,Optional<wpc::Policy::AppTimeLimitsSettings>,Sync::MonitoringFlags const &)

- ea: `0x18007aa74`
- end: `0x18007bf92`
- name: `?ReadSettingsFileAndMergeChangesWithMonitoringFlags@SyncEngineHelper@@YA?AW4MergeSettingsResult@1@AEBVSid@@AEBV?$Optional@VSettingsData@Policy@wpc@@@@AEBV?$Optional@UTimeRestrictionsSettings@Policy@wpc@@@@V?$Optional@UAppTimeLimitsSettings@Policy@wpc@@@@AEBUMonitoringFlags@Sync@@@Z`
- size: `5406`
- prototype: `__int64 __fastcall(SyncEngineHelper *this, __int64, __int64, __int64, char *)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180071fc8`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000813c`
- `0x18000819c`
- `0x180008cd8`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x180009de0`
- `0x18000e8b0`
- `0x18001cd10`
- `0x18001e250`
- `0x18001fb38`
- `0x180021090`
- `0x180022180`
- `0x180023638`
- `0x180035e0c`
- `0x180040888`
- `0x1800409b4`
- `0x1800623f0`
- `0x180062974`
- `0x1800717b8`
- `0x1800736a0`
- `0x180073b98`
- `0x180073e64`
- `0x180073f70`
- `0x1800745c0`
- `0x180074828`
- `0x180074cd4`
- `0x180077200`
- `0x180077f04`
- `0x1800782b0`
- `0x1800783bc`
- `0x180078710`
- `0x1800787a8`
- `0x18007899c`
- `0x18007aa74`
- `0x18007bf98`
- `0x18007c1d0`
- `0x18007d06c`
- `0x18009ed88`
- `0x18009f3b4`

## string_xrefs

- `0x18007b9ac`: `Updated LastSyncTime for existing user `
- `0x18007b498`: `Settings entry removed for unmanaged user `
- `0x18007b2b2`: `Updated LastSyncTime for user `
- `0x18007bdfb`: `Settings file saved with LastSyncTime update for user `
- `0x18007beb4`: `Settings file updated for user `
- `0x18007bc1a`: `Created new user entry and added TimeRestrictions settings `
- `0x18007be54`: `Settings file NOT updated because there is no change for user `
- `0x18007b057`: `applyMonitoringFlagsFromLocalSettings when user with sid:`
- `0x18007af43`: `applyMonitoringFlagsFromServer when user with sid:`
- `0x18007b74e`: `applyMonitoringFlagsFromLocalSettings for user with sid:`
- `0x18007b63d`: `applyMonitoringFlagsFromServer for user with sid:`
- `0x18007bb0b`: `applyMonitoringFlagsFromServer for user with sid:`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SyncEngineHelper::ReadSettingsFileAndMergeChangesWithMonitoringFlags(
        SyncEngineHelper *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *a5)
{
  _BYTE *v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rdi
  unsigned int v12; // esi
  _BYTE *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const struct Sid *v16; // rdx
  const struct wpc::Policy::SettingsData *v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // r8d
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int128 *v25; // rcx
  __int64 v26; // rax
  __int128 *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 Current; // rax
  char v35; // bl
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  __int128 *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rax
  char v58; // bl
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  __int128 *p_pExceptionObject; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rbx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  _QWORD *v75; // rdi
  __int64 v76; // rdx
  const struct Sid *v77; // rdx
  bool v78; // bl
  _QWORD *v79; // rbx
  __int64 v80; // rax
  __int64 v81; // rbx
  __int64 v82; // rdi
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v86; // [rsp+40h] [rbp-C0h] BYREF
  char v87; // [rsp+48h] [rbp-B8h] BYREF
  char v88; // [rsp+49h] [rbp-B7h] BYREF
  _QWORD v89[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v90[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v91; // [rsp+70h] [rbp-90h] BYREF
  __int64 v92; // [rsp+80h] [rbp-80h]
  _QWORD v93[3]; // [rsp+88h] [rbp-78h] BYREF
  __int128 pExceptionObject; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v95; // [rsp+B0h] [rbp-50h]
  __int64 v96; // [rsp+C8h] [rbp-38h]
  __int128 v97; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v98; // [rsp+E0h] [rbp-20h]
  __int128 Src; // [rsp+100h] [rbp+0h] BYREF
  __int128 v100; // [rsp+110h] [rbp+10h]
  _BYTE v101[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v102[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v103[40]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v104[176]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v105[8]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v106[4]; // [rsp+240h] [rbp+140h] BYREF
  __int128 v107; // [rsp+244h] [rbp+144h] BYREF
  __int128 v108; // [rsp+254h] [rbp+154h]
  __int128 *v109; // [rsp+268h] [rbp+168h]
  int v110; // [rsp+280h] [rbp+180h]
  _BYTE Sid[72]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v112[40]; // [rsp+328h] [rbp+228h] BYREF

  v93[2] = a4;
  v87 = *a5;
  v88 = a5[1];
  Settings::LoadSettings(v89);
  std::wstring::wstring(v102, (char *)this + 72);
  Sid::AbbrevString(this, v101);
  v9 = (_BYTE *)stdext::lookup<std::wstring,std::map<std::wstring,wpc::Policy::SettingsData>>(v89, v102);
  v11 = v9;
  v12 = 1;
  if ( v9 )
  {
    if ( *v9 )
    {
      if ( v9[1] )
      {
        v13 = *(_BYTE **)(a2 + 392);
        if ( v13 )
        {
          if ( !*v13 || !v13[1] )
          {
            Src = 0;
            v100 = 0;
            v86 = 47;
            v14 = std::wstring::_Allocate_for_capacity<0>(v10, &v86);
            *(_QWORD *)&Src = v14;
            *(_QWORD *)&v100 = 42;
            *((_QWORD *)&v100 + 1) = v86;
            *(_OWORD *)v14 = *(_OWORD *)L"Restrictions turned off, alerting parent: ";
            *(_OWORD *)(v14 + 16) = *(_OWORD *)L"ions turned off, alerting parent: ";
            *(_OWORD *)(v14 + 32) = *(_OWORD *)L"ned off, alerting parent: ";
            *(_OWORD *)(v14 + 48) = *(_OWORD *)L" alerting parent: ";
            *(_OWORD *)(v14 + 64) = *(_OWORD *)L"g parent: ";
            *(_DWORD *)(v14 + 80) = *(_DWORD *)L": ";
            *(_WORD *)(v14 + 84) = 0;
            v15 = std::wstring::append(&Src);
            v97 = 0;
            v98 = 0;
            v97 = *(_OWORD *)v15;
            v98 = *(_OWORD *)(v15 + 16);
            *(_QWORD *)(v15 + 16) = 0;
            *(_QWORD *)(v15 + 24) = 7;
            *(_WORD *)v15 = 0;
            LODWORD(v86) = 1;
            wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &v97);
            std::wstring::~wstring(&v97);
            std::wstring::~wstring(&Src);
            SyncEngineHelper::ReportChildSettingsDisabled(this, v16);
          }
        }
      }
    }
  }
  *(_QWORD *)&Src = &v87;
  *((_QWORD *)&Src + 1) = &v88;
  *(_QWORD *)&v100 = v101;
  v93[0] = v102;
  v93[1] = v101;
  v17 = *(const struct wpc::Policy::SettingsData **)(a2 + 392);
  if ( v17 )
  {
    wpc::Policy::SettingsData::SettingsData((wpc::Policy::SettingsData *)v103, v17);
    if ( v103[0] )
    {
      v19 = *(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor;
      if ( (*(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor & 4) == 0 )
      {
        v90[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FamilySafetyRemoteLock>::GetCachedFeatureEnabledState(
                              v18,
                              v90);
        v19 = v90[0];
      }
      LODWORD(v86) = 0;
      WORD2(v86) = 3;
      wil::details::ReportUsageToService(&qword_180109418, 32425780, (v19 >> 10) & 1, (v19 >> 11) & 1);
      v20 = *(_QWORD *)(a3 + 88);
      if ( v20 )
      {
        wpc::Policy::TimeLimitsRule::operator=(v105, v20);
        v110 = *(_DWORD *)(v20 + 72);
        v97 = 0;
        v98 = 0;
        v86 = 55;
        v22 = std::wstring::_Allocate_for_capacity<0>(v21, &v86);
        *(_QWORD *)&v97 = v22;
        *(_QWORD *)&v98 = 53;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v22 = *(_OWORD *)L"TimeRestrictions changes merged to settings for user ";
        *(_OWORD *)(v22 + 16) = *(_OWORD *)L"rictions changes merged to settings for user ";
        *(_OWORD *)(v22 + 32) = *(_OWORD *)L" changes merged to settings for user ";
        *(_OWORD *)(v22 + 48) = *(_OWORD *)L" merged to settings for user ";
        *(_OWORD *)(v22 + 64) = *(_OWORD *)L"to settings for user ";
        *(_OWORD *)(v22 + 80) = *(_OWORD *)L"ngs for user ";
        *(_OWORD *)(v22 + 90) = *(_OWORD *)L"or user ";
        *(_WORD *)(v22 + 106) = 0;
        v23 = std::wstring::append(&v97);
        pExceptionObject = 0;
        v95 = 0;
        pExceptionObject = *(_OWORD *)v23;
        v95 = *(_OWORD *)(v23 + 16);
        *(_QWORD *)(v23 + 16) = 0;
        *(_QWORD *)(v23 + 24) = 7;
        *(_WORD *)v23 = 0;
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
        std::wstring::~wstring(&v97);
        if ( v11 )
        {
          v24 = ReconcileOverrides(&pExceptionObject, this, v11 + 56, v106);
          if ( v109 )
            v109 = 0;
          v25 = *(__int128 **)(v24 + 40);
          if ( v25 )
          {
            v107 = *v25;
            v108 = v25[1];
            v109 = &v107;
            if ( *(_QWORD *)(v24 + 40) )
              *(_QWORD *)(v24 + 40) = 0;
          }
        }
      }
      else if ( v11 )
      {
        wpc::Policy::TimeLimitsRule::operator=(v105, v11 + 54);
        v110 = v11[72];
        v96 = 0;
        v26 = ReconcileOverrides(&v97, this, v11 + 56, &pExceptionObject);
        if ( v109 )
          v109 = 0;
        v27 = *(__int128 **)(v26 + 40);
        if ( v27 )
        {
          v107 = *v27;
          v108 = v27[1];
          v109 = &v107;
          if ( *(_QWORD *)(v26 + 40) )
            *(_QWORD *)(v26 + 40) = 0;
        }
      }
      if ( *(_QWORD *)(a4 + 56) )
      {
        lambda_23d3af2253d0be10932d07aa17f626e7_::operator()(&Src, v103);
        v97 = 0;
        v98 = 0;
        v86 = 55;
        v29 = std::wstring::_Allocate_for_capacity<0>(v28, &v86);
        *(_QWORD *)&v97 = v29;
        *(_QWORD *)&v98 = 50;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v29 = *(_OWORD *)L"applyMonitoringFlagsFromServer when user with sid:";
        *(_OWORD *)(v29 + 16) = *(_OWORD *)L"itoringFlagsFromServer when user with sid:";
        *(_OWORD *)(v29 + 32) = *(_OWORD *)L"lagsFromServer when user with sid:";
        *(_OWORD *)(v29 + 48) = *(_OWORD *)L"Server when user with sid:";
        *(_OWORD *)(v29 + 64) = *(_OWORD *)L"hen user with sid:";
        *(_OWORD *)(v29 + 80) = *(_OWORD *)L" with sid:";
        *(_DWORD *)(v29 + 96) = *(_DWORD *)L"d:";
        *(_WORD *)(v29 + 100) = 0;
      }
      else
      {
        lambda_677938615710015d3b793b663f87da3d_::operator()(v93, v103);
        v97 = 0;
        v98 = 0;
        v86 = 63;
        v33 = std::wstring::_Allocate_for_capacity<0>(v32, &v86);
        *(_QWORD *)&v97 = v33;
        *(_QWORD *)&v98 = 57;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v33 = *(_OWORD *)L"applyMonitoringFlagsFromLocalSettings when user with sid:";
        *(_OWORD *)(v33 + 16) = *(_OWORD *)L"itoringFlagsFromLocalSettings when user with sid:";
        *(_OWORD *)(v33 + 32) = *(_OWORD *)L"lagsFromLocalSettings when user with sid:";
        *(_OWORD *)(v33 + 48) = *(_OWORD *)L"LocalSettings when user with sid:";
        *(_OWORD *)(v33 + 64) = *(_OWORD *)L"tings when user with sid:";
        *(_OWORD *)(v33 + 80) = *(_OWORD *)L"en user with sid:";
        *(_OWORD *)(v33 + 96) = *(_OWORD *)L"with sid:";
        *(_WORD *)(v33 + 112) = aApplymonitorin_5[56];
        *(_WORD *)(v33 + 114) = 0;
      }
      v30 = std::wstring::append(&v97);
      pExceptionObject = 0;
      v95 = 0;
      pExceptionObject = *(_OWORD *)v30;
      v95 = *(_OWORD *)(v30 + 16);
      *(_QWORD *)(v30 + 16) = 0;
      *(_QWORD *)(v30 + 24) = 7;
      *(_WORD *)v30 = 0;
      v31 = std::operator+<unsigned short>(&Src, &pExceptionObject, L" has newSettingsPolicy");
      LODWORD(v86) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v31);
      std::wstring::~wstring(&Src);
      std::wstring::~wstring(&pExceptionObject);
      std::wstring::~wstring(&v97);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58247009>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58247009>::GetImpl'::`2'::impl) )
      {
        Current = DateTime::GetCurrent(v90);
        DateTime::ToDebugString(Current, &pExceptionObject, 0);
        std::wstring::operator=(v104, &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
        if ( !v11 || (v35 = 0, !(unsigned __int8)wpc::Policy::operator==(v103, v11)) )
          v35 = 1;
        v36 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v89, v102);
        wpc::Policy::SettingsData::operator=(v36, v103);
        v97 = 0;
        v98 = 0;
        if ( v35 )
        {
          v12 = 2;
          v86 = 39;
          v38 = std::wstring::_Allocate_for_capacity<0>(v37, &v86);
          *(_QWORD *)&v97 = v38;
          *(_QWORD *)&v98 = 33;
          *((_QWORD *)&v98 + 1) = v86;
          *(_OWORD *)v38 = *(_OWORD *)L"Settings changes merged for user ";
          *(_OWORD *)(v38 + 16) = *(_OWORD *)L" changes merged for user ";
          *(_OWORD *)(v38 + 32) = *(_OWORD *)L" merged for user ";
          *(_OWORD *)(v38 + 48) = *(_OWORD *)L"for user ";
          *(_WORD *)(v38 + 64) = aSettingsChange[32];
          *(_WORD *)(v38 + 66) = 0;
        }
        else
        {
          v86 = 31;
          v40 = std::wstring::_Allocate_for_capacity<0>(v37, &v86);
          *(_QWORD *)&v97 = v40;
          *(_QWORD *)&v98 = 30;
          *((_QWORD *)&v98 + 1) = v86;
          *(_OWORD *)v40 = *(_OWORD *)L"Updated LastSyncTime for user ";
          *(_OWORD *)(v40 + 16) = *(_OWORD *)L"LastSyncTime for user ";
          *(_OWORD *)(v40 + 32) = *(_OWORD *)L"Time for user ";
          *(_OWORD *)(v40 + 44) = *(_OWORD *)L"or user ";
          *(_WORD *)(v40 + 60) = 0;
        }
        v39 = std::wstring::append(&v97);
        pExceptionObject = 0;
        v95 = 0;
        pExceptionObject = *(_OWORD *)v39;
        v95 = *(_OWORD *)(v39 + 16);
        *(_QWORD *)(v39 + 16) = 0;
        *(_QWORD *)(v39 + 24) = 7;
        *(_WORD *)v39 = 0;
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
      }
      else
      {
        if ( v11 && (unsigned __int8)wpc::Policy::operator==(v103, v11) )
          goto LABEL_75;
        v41 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v89, v102);
        wpc::Policy::SettingsData::operator=(v41, v103);
        v12 = 2;
        v97 = 0;
        v98 = 0;
        v86 = 39;
        v43 = std::wstring::_Allocate_for_capacity<0>(v42, &v86);
        *(_QWORD *)&v97 = v43;
        *(_QWORD *)&v98 = 33;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v43 = *(_OWORD *)L"Settings changes merged for user ";
        *(_OWORD *)(v43 + 16) = *(_OWORD *)L" changes merged for user ";
        *(_OWORD *)(v43 + 32) = *(_OWORD *)L" merged for user ";
        *(_OWORD *)(v43 + 48) = *(_OWORD *)L"for user ";
        *(_WORD *)(v43 + 64) = aSettingsChange[32];
        *(_WORD *)(v43 + 66) = 0;
        v44 = std::wstring::append(&v97);
        pExceptionObject = 0;
        v95 = 0;
        pExceptionObject = *(_OWORD *)v44;
        v95 = *(_OWORD *)(v44 + 16);
        *(_QWORD *)(v44 + 16) = 0;
        *(_QWORD *)(v44 + 24) = 7;
        *(_WORD *)v44 = 0;
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
      }
    }
    else
    {
      if ( !v11 )
      {
LABEL_75:
        wpc::Policy::SettingsData::~SettingsData((wpc::Policy::SettingsData *)v103);
        goto LABEL_76;
      }
      std::_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>::erase(
        v89,
        v102);
      v12 = 3;
      v97 = 0;
      v98 = 0;
      v86 = 47;
      v46 = std::wstring::_Allocate_for_capacity<0>(v45, &v86);
      *(_QWORD *)&v97 = v46;
      *(_QWORD *)&v98 = 42;
      *((_QWORD *)&v98 + 1) = v86;
      *(_OWORD *)v46 = *(_OWORD *)L"Settings entry removed for unmanaged user ";
      *(_OWORD *)(v46 + 16) = *(_OWORD *)L" entry removed for unmanaged user ";
      *(_OWORD *)(v46 + 32) = *(_OWORD *)L"emoved for unmanaged user ";
      *(_OWORD *)(v46 + 48) = *(_OWORD *)L"or unmanaged user ";
      *(_OWORD *)(v46 + 64) = *(_OWORD *)L"aged user ";
      *(_DWORD *)(v46 + 80) = *(_DWORD *)L"r ";
      *(_WORD *)(v46 + 84) = 0;
      v47 = std::wstring::append(&v97);
      pExceptionObject = 0;
      v95 = 0;
      pExceptionObject = *(_OWORD *)v47;
      v95 = *(_OWORD *)(v47 + 16);
      *(_QWORD *)(v47 + 16) = 0;
      *(_QWORD *)(v47 + 24) = 7;
      *(_WORD *)v47 = 0;
      LODWORD(v86) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &pExceptionObject);
      std::wstring::~wstring(&pExceptionObject);
    }
    std::wstring::~wstring(&v97);
    goto LABEL_75;
  }
  if ( *(_QWORD *)(a3 + 88) )
  {
    if ( !v11 )
    {
      wpc::Policy::SettingsData::SettingsData((wpc::Policy::SettingsData *)v103);
      v68 = *(_QWORD *)(a3 + 88);
      if ( !v68 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, -2147467261);
        throw (ErrorCodeException *)&pExceptionObject;
      }
      wpc::Policy::TimeLimitsRule::operator=(v105, v68);
      v110 = *(_DWORD *)(v68 + 72);
      if ( *(_QWORD *)(a4 + 56) )
      {
        lambda_23d3af2253d0be10932d07aa17f626e7_::operator()(&Src, v103);
        pExceptionObject = 0;
        v95 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          &pExceptionObject,
          L"applyMonitoringFlagsFromServer for user with sid:",
          49);
        v69 = std::operator+<unsigned short>(&Src, &pExceptionObject, v101);
        v70 = std::operator+<unsigned short>(&v97, v69, L" has newScreenLimitsPolicy but no old settings present");
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v70);
        std::wstring::~wstring(&v97);
        std::wstring::~wstring(&Src);
        std::wstring::~wstring(&pExceptionObject);
      }
      else
      {
        if ( !v105[0] && !v105[1] && (!v109 || *(_BYTE *)v109) )
          LOBYTE(v12) = 0;
        v103[1] = v12;
        v103[4] = v12;
        v103[5] = v12;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58247009>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58247009>::GetImpl'::`2'::impl) )
      {
        v71 = DateTime::GetCurrent(v90);
        DateTime::ToDebugString(v71, &pExceptionObject, 0);
        std::wstring::operator=(v104, &pExceptionObject);
        std::wstring::~wstring(&pExceptionObject);
      }
      v72 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v89, v102);
      wpc::Policy::SettingsData::operator=(v72, v103);
      v12 = 2;
      pExceptionObject = 0;
      v95 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &pExceptionObject,
        L"Created new user entry and added TimeRestrictions settings ",
        59);
      v73 = std::operator+<unsigned short>(&v97, &pExceptionObject, v101);
      LODWORD(v86) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v73);
      std::wstring::~wstring(&v97);
      std::wstring::~wstring(&pExceptionObject);
      goto LABEL_75;
    }
    wpc::Policy::SettingsData::SettingsData(
      (wpc::Policy::SettingsData *)v103,
      (const struct wpc::Policy::SettingsData *)v11);
    v48 = *(_QWORD *)(a3 + 88);
    if ( !v48 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, -2147467261);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    wpc::Policy::TimeLimitsRule::operator=(v105, v48);
    v110 = *(_DWORD *)(v48 + 72);
    v49 = ReconcileOverrides(&pExceptionObject, this, v11 + 56, v106);
    if ( v109 )
      v109 = 0;
    v50 = *(__int128 **)(v49 + 40);
    if ( v50 )
    {
      v107 = *v50;
      v108 = v50[1];
      v109 = &v107;
      if ( *(_QWORD *)(v49 + 40) )
        *(_QWORD *)(v49 + 40) = 0;
    }
    if ( *(_QWORD *)(a4 + 56) )
    {
      lambda_23d3af2253d0be10932d07aa17f626e7_::operator()(&Src, v103);
      v97 = 0;
      v98 = 0;
      v86 = 55;
      v52 = std::wstring::_Allocate_for_capacity<0>(v51, &v86);
      *(_QWORD *)&v97 = v52;
      *(_QWORD *)&v98 = 49;
      *((_QWORD *)&v98 + 1) = v86;
      *(_OWORD *)v52 = *(_OWORD *)L"applyMonitoringFlagsFromServer for user with sid:";
      *(_OWORD *)(v52 + 16) = *(_OWORD *)L"itoringFlagsFromServer for user with sid:";
      *(_OWORD *)(v52 + 32) = *(_OWORD *)L"lagsFromServer for user with sid:";
      *(_OWORD *)(v52 + 48) = *(_OWORD *)L"Server for user with sid:";
      *(_OWORD *)(v52 + 64) = *(_OWORD *)L"or user with sid:";
      *(_OWORD *)(v52 + 80) = *(_OWORD *)L"with sid:";
      *(_WORD *)(v52 + 96) = aApplymonitorin_3[48];
      *(_WORD *)(v52 + 98) = 0;
    }
    else
    {
      lambda_677938615710015d3b793b663f87da3d_::operator()(v93, v103);
      v97 = 0;
      v98 = 0;
      v86 = 63;
      v56 = std::wstring::_Allocate_for_capacity<0>(v55, &v86);
      *(_QWORD *)&v97 = v56;
      *(_QWORD *)&v98 = 56;
      *((_QWORD *)&v98 + 1) = v86;
      *(_OWORD *)v56 = *(_OWORD *)L"applyMonitoringFlagsFromLocalSettings for user with sid:";
      *(_OWORD *)(v56 + 16) = *(_OWORD *)L"itoringFlagsFromLocalSettings for user with sid:";
      *(_OWORD *)(v56 + 32) = *(_OWORD *)L"lagsFromLocalSettings for user with sid:";
      *(_OWORD *)(v56 + 48) = *(_OWORD *)L"LocalSettings for user with sid:";
      *(_OWORD *)(v56 + 64) = *(_OWORD *)L"tings for user with sid:";
      *(_OWORD *)(v56 + 80) = *(_OWORD *)L"r user with sid:";
      *(_OWORD *)(v56 + 96) = *(_OWORD *)L"ith sid:";
      *(_WORD *)(v56 + 112) = 0;
    }
    v53 = std::wstring::append(&v97);
    pExceptionObject = 0;
    v95 = 0;
    pExceptionObject = *(_OWORD *)v53;
    v95 = *(_OWORD *)(v53 + 16);
    *(_QWORD *)(v53 + 16) = 0;
    *(_QWORD *)(v53 + 24) = 7;
    *(_WORD *)v53 = 0;
    v54 = std::operator+<unsigned short>(&Src, &pExceptionObject, L" has newScreenLimitsPolicy");
    LODWORD(v86) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v54);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(&pExceptionObject);
    std::wstring::~wstring(&v97);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58247009>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58247009>::GetImpl'::`2'::impl) )
    {
      v57 = DateTime::GetCurrent(v90);
      DateTime::ToDebugString(v57, &pExceptionObject, 0);
      std::wstring::operator=(v104, &pExceptionObject);
      std::wstring::~wstring(&pExceptionObject);
      v58 = wpc::Policy::operator==(
              (struct wpc::Policy::TimeLimitsRule *)v105,
              (struct wpc::Policy::TimeLimitsRule *)(v11 + 54));
      v59 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v89, v102);
      wpc::Policy::SettingsData::operator=(v59, v103);
      v97 = 0;
      v98 = 0;
      if ( v58 )
      {
        v86 = 39;
        v64 = std::wstring::_Allocate_for_capacity<0>(v60, &v86);
        *(_QWORD *)&v97 = v64;
        *(_QWORD *)&v98 = 39;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v64 = *(_OWORD *)L"Updated LastSyncTime for existing user ";
        *(_OWORD *)(v64 + 16) = *(_OWORD *)L"LastSyncTime for existing user ";
        *(_OWORD *)(v64 + 32) = *(_OWORD *)L"Time for existing user ";
        *(_OWORD *)(v64 + 48) = *(_OWORD *)L" existing user ";
        *(_OWORD *)(v64 + 62) = *(_OWORD *)L"ng user ";
        *(_WORD *)(v64 + 78) = 0;
        v65 = std::operator+<unsigned short>(&pExceptionObject, &v97, v101);
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v65);
      }
      else
      {
        v12 = 2;
        v86 = 55;
        v61 = std::wstring::_Allocate_for_capacity<0>(v60, &v86);
        *(_QWORD *)&v97 = v61;
        *(_QWORD *)&v98 = 50;
        *((_QWORD *)&v98 + 1) = v86;
        *(_OWORD *)v61 = *(_OWORD *)L"TimeRestrictions changes merged for existing user ";
        *(_OWORD *)(v61 + 16) = *(_OWORD *)L"rictions changes merged for existing user ";
        *(_OWORD *)(v61 + 32) = *(_OWORD *)L" changes merged for existing user ";
        *(_OWORD *)(v61 + 48) = *(_OWORD *)L" merged for existing user ";
        *(_OWORD *)(v61 + 64) = *(_OWORD *)L"for existing user ";
        *(_OWORD *)(v61 + 80) = *(_OWORD *)L"ting user ";
        *(_DWORD *)(v61 + 96) = *(_DWORD *)L"r ";
        *(_WORD *)(v61 + 100) = 0;
        v62 = std::wstring::append(&v97);
        pExceptionObject = 0;
        v95 = 0;
        pExceptionObject = *(_OWORD *)v62;
        v95 = *(_OWORD *)(v62 + 16);
        *(_QWORD *)(v62 + 16) = 0;
        *(_QWORD *)(v62 + 24) = 7;
        *(_WORD *)v62 = 0;
        LODWORD(v86) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v86, &pExceptionObject);
      }
      std::wstring::~wstring(&pExceptionObject);
      p_pExceptionObject = &v97;
    }
    else
    {
      if ( (unsigned __int8)wpc::Policy::operator==(
                              (struct wpc::Policy::TimeLimitsRule *)v105,
                              (struct wpc::Policy::TimeLimitsRule *)(v11 + 54)) )
        goto LABEL_75;
      v66 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v89, v102);
      wpc::Policy::SettingsData::operator=(v66, v103);
      v12 = 2;
      pExceptionObject = 0;
      v95 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &pExceptionObject,
        L"TimeRestrictions changes merged for existing user ",
        50);
      v67 = std::operator+<unsigned short>(&v97, &pExceptionObject, v101);
      LODWORD(v86) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v67);
      std::wstring::~wstring(&v97);
      p_pExceptionObject = &pExceptionObject;
    }
    std::wstring::~wstring(p_pExceptionObject);
    goto LABEL_75;
  }
LABEL_76:
  v91 = 0;
  v92 = 0;
  v74 = *(_QWORD *)v89[0];
  v90[0] = *(_QWORD *)v89[0];
  while ( !*(_BYTE *)(v74 + 25) )
  {
    v75 = (_QWORD *)(v74 + 32);
    if ( *(_QWORD *)(v74 + 56) <= 7u )
      v76 = v74 + 32;
    else
      v76 = *v75;
    Sid::FromString(Sid, v76);
    v78 = SyncEngineHelper::AccountExists(Sid, v77);
    std::wstring::~wstring(v112);
    if ( !v78 )
    {
      if ( v75[3] <= 7u )
        v79 = v75;
      else
        v79 = (_QWORD *)*v75;
      pExceptionObject = 0;
      v95 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &pExceptionObject,
        L"Deleting settings entry for nonexistent user  ",
        46);
      v80 = std::operator+<unsigned short>(&v97, &pExceptionObject, v79);
      LODWORD(v86) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v80);
      std::wstring::~wstring(&v97);
      std::wstring::~wstring(&pExceptionObject);
      if ( *((_QWORD *)&v91 + 1) == v92 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v91, *((_QWORD *)&v91 + 1), v75);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v91 + 1), v75);
        *((_QWORD *)&v91 + 1) += 32LL;
      }
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wpc::Policy::SettingsData>>>,std::_Iterator_base0>::operator++(v90);
    v74 = v90[0];
  }
  v82 = *((_QWORD *)&v91 + 1);
  v81 = v91;
  if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>::erase(
        v89,
        v81);
      v81 += 32;
    }
    while ( v81 != v82 );
    v81 = v91;
  }
  if ( v12 == 2 || v12 == 3 || v81 != *((_QWORD *)&v91 + 1) )
  {
    Settings::SaveSettings(v89);
    pExceptionObject = 0;
    v95 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, L"Settings file updated for user ", 31);
    v84 = std::operator+<unsigned short>(&v97, &pExceptionObject, v101);
    LODWORD(v86) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v84);
    std::wstring::~wstring(&v97);
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58247009>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58247009>::GetImpl'::`2'::impl) )
    {
      Settings::SaveSettings(v89);
      pExceptionObject = 0;
      v95 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &pExceptionObject,
        L"Settings file saved with LastSyncTime update for user ",
        54);
    }
    else
    {
      pExceptionObject = 0;
      v95 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &pExceptionObject,
        L"Settings file NOT updated because there is no change for user ",
        62);
    }
    v83 = std::operator+<unsigned short>(&v97, &pExceptionObject, v101);
    LODWORD(v86) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v86, v83);
    std::wstring::~wstring(&v97);
  }
  std::wstring::~wstring(&pExceptionObject);
  std::vector<std::wstring>::_Tidy(&v91);
  std::wstring::~wstring(v101);
  std::wstring::~wstring(v102);
  std::_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>(v89);
  Optional<wpc::Policy::AppTimeLimitsSettings>::~Optional<wpc::Policy::AppTimeLimitsSettings>(a4);
  return v12;
}

```

## disassembly

```asm
0x18007aa74  push    rbp
0x18007aa76  push    rbx
0x18007aa77  push    rsi
0x18007aa78  push    rdi
0x18007aa79  push    r12
0x18007aa7b  push    r13
0x18007aa7d  push    r14
0x18007aa7f  push    r15
0x18007aa81  lea     rbp, [rsp-268h]
0x18007aa89  sub     rsp, 368h
0x18007aa90  mov     rax, cs:__security_cookie
0x18007aa97  xor     rax, rsp
0x18007aa9a  mov     [rbp+2A0h+var_50], rax
0x18007aaa1  mov     r12, r9
0x18007aaa4  mov     rbx, r8
0x18007aaa7  mov     r15, rdx
0x18007aaaa  mov     r14, rcx
0x18007aaad  mov     [rbp+2A0h+var_308], r9
0x18007aab1  xor     r13d, r13d
0x18007aab4  mov     rcx, [rbp+2A0h+arg_20]
0x18007aabb  mov     al, [rcx]
0x18007aabd  mov     [rsp+3A0h+var_358], al
0x18007aac1  mov     al, [rcx+1]
0x18007aac4  mov     [rsp+3A0h+var_357], al
0x18007aac8  lea     rcx, [rsp+3A0h+var_350]
0x18007aacd  call    ?LoadSettings@Settings@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@@std@@@2@@std@@XZ; Settings::LoadSettings(void)
0x18007aad2  nop
0x18007aad3  lea     rdx, [r14+48h]
0x18007aad7  lea     rcx, [rbp+2A0h+var_260]
0x18007aadb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007aae0  nop
0x18007aae1  lea     rdx, [rbp+2A0h+var_280]
0x18007aae5  mov     rcx, r14
0x18007aae8  call    ?AbbrevString@Sid@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sid::AbbrevString(void)
0x18007aaed  nop
0x18007aaee  lea     rdx, [rbp+2A0h+var_260]
0x18007aaf2  lea     rcx, [rsp+3A0h+var_350]
0x18007aaf7  call    ??$lookup@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@@std@@@2@@2@@stdext@@YAPEBVSettingsData@Policy@wpc@@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSettingsData@Policy@wpc@@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; stdext::lookup<std::wstring,std::map<std::wstring,wpc::Policy::SettingsData>>(std::map<std::wstring,wpc::Policy::SettingsData> const &,std::wstring const &)
0x18007aafc  mov     rdi, rax
0x18007aaff  lea     esi, [r13+1]
0x18007ab03  test    rax, rax
0x18007ab06  jz      loc_18007AC25
0x18007ab0c  cmp     [rax], r13b
0x18007ab0f  jz      loc_18007AC25
0x18007ab15  cmp     [rax+1], r13b
0x18007ab19  jz      loc_18007AC25
0x18007ab1f  mov     rax, [r15+188h]
0x18007ab26  test    rax, rax
0x18007ab29  jz      loc_18007AC25
0x18007ab2f  cmp     [rax], r13b
0x18007ab32  jz      short loc_18007AB3E
0x18007ab34  cmp     [rax+1], r13b
0x18007ab38  jnz     loc_18007AC25
0x18007ab3e  xorps   xmm0, xmm0
0x18007ab41  movups  [rbp+2A0h+Src], xmm0
0x18007ab45  xorps   xmm1, xmm1
0x18007ab48  movdqu  [rbp+2A0h+var_290], xmm1
0x18007ab4d  mov     [rsp+3A0h+var_360], 2Fh ; '/'
0x18007ab56  lea     rdx, [rsp+3A0h+var_360]
0x18007ab5b  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18007ab60  mov     rdx, rax
0x18007ab63  mov     qword ptr [rbp+2A0h+Src], rax
0x18007ab67  mov     qword ptr [rbp+2A0h+var_290], 2Ah ; '*'
0x18007ab6f  mov     rcx, [rsp+3A0h+var_360]
0x18007ab74  mov     qword ptr [rbp+2A0h+var_290+8], rcx
0x18007ab78  movaps  xmm0, xmmword ptr cs:aRestrictionsTu; "Restrictions turned off, alerting paren"...
0x18007ab7f  movups  xmmword ptr [rax], xmm0
0x18007ab82  movaps  xmm1, xmmword ptr cs:aRestrictionsTu+10h; "ions turned off, alerting parent: "
0x18007ab89  movups  xmmword ptr [rax+10h], xmm1
0x18007ab8d  movaps  xmm0, xmmword ptr cs:aRestrictionsTu+20h; "ned off, alerting parent: "
0x18007ab94  movups  xmmword ptr [rax+20h], xmm0
0x18007ab98  movaps  xmm1, xmmword ptr cs:aRestrictionsTu+30h; " alerting parent: "
0x18007ab9f  movups  xmmword ptr [rax+30h], xmm1
0x18007aba3  movaps  xmm0, xmmword ptr cs:aRestrictionsTu+40h; "g parent: "
0x18007abaa  movups  xmmword ptr [rax+40h], xmm0
0x18007abae  mov     eax, dword ptr cs:aRestrictionsTu+50h; ": "
0x18007abb4  mov     [rdx+50h], eax
0x18007abb7  mov     [rdx+54h], r13w
0x18007abbc  lea     rdx, [rbp+2A0h+var_280]
0x18007abc0  lea     rcx, [rbp+2A0h+Src]; Src
0x18007abc4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18007abc9  xorps   xmm0, xmm0
0x18007abcc  movups  [rbp+2A0h+var_2D0], xmm0
0x18007abd0  xorps   xmm1, xmm1
0x18007abd3  movdqu  [rbp+2A0h+var_2C0], xmm1
0x18007abd8  movups  xmm0, xmmword ptr [rax]
0x18007abdb  movups  [rbp+2A0h+var_2D0], xmm0
0x18007abdf  movups  xmm1, xmmword ptr [rax+10h]
0x18007abe3  movups  [rbp+2A0h+var_2C0], xmm1
0x18007abe7  mov     [rax+10h], r13
0x18007abeb  mov     qword ptr [rax+18h], 7
0x18007abf3  mov     [rax], r13w
0x18007abf7  mov     dword ptr [rsp+3A0h+var_360], esi
0x18007abfb  lea     rdx, [rbp+2A0h+var_2D0]
0x18007abff  lea     rcx, [rsp+3A0h+var_360]
0x18007ac04  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007ac09  nop
0x18007ac0a  lea     rcx, [rbp+2A0h+var_2D0]
0x18007ac0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ac13  nop
0x18007ac14  lea     rcx, [rbp+2A0h+Src]
0x18007ac18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ac1d  mov     rcx, r14; this
0x18007ac20  call    ?ReportChildSettingsDisabled@SyncEngineHelper@@YAXAEBVSid@@@Z; SyncEngineHelper::ReportChildSettingsDisabled(Sid const &)
0x18007ac25  lea     rax, [rsp+3A0h+var_358]
0x18007ac2a  mov     qword ptr [rbp+2A0h+Src], rax
0x18007ac2e  lea     rax, [rsp+3A0h+var_357]
0x18007ac33  mov     qword ptr [rbp+2A0h+Src+8], rax
0x18007ac37  lea     rax, [rbp+2A0h+var_280]
0x18007ac3b  mov     qword ptr [rbp+2A0h+var_290], rax
0x18007ac3f  lea     rax, [rbp+2A0h+var_260]
0x18007ac43  mov     [rbp+2A0h+var_318], rax
0x18007ac47  lea     rax, [rbp+2A0h+var_280]
0x18007ac4b  mov     [rbp+2A0h+var_310], rax
0x18007ac4f  mov     rdx, [r15+188h]; struct wpc::Policy::SettingsData *
0x18007ac56  mov     r15d, 2
0x18007ac5c  test    rdx, rdx
0x18007ac5f  jz      loc_18007B544
0x18007ac65  lea     rcx, [rbp+2A0h+var_240]; this
0x18007ac69  call    ??0SettingsData@Policy@wpc@@QEAA@AEBV012@@Z; wpc::Policy::SettingsData::SettingsData(wpc::Policy::SettingsData const &)
0x18007ac6e  nop
0x18007ac6f  cmp     [rbp+2A0h+var_240], r13b
0x18007ac73  jz      loc_18007B442
0x18007ac79  mov     rax, cs:Feature_FamilySafetyRemoteLock__descriptor
0x18007ac80  mov     r8d, [rax]
0x18007ac83  test    r8b, 4
0x18007ac87  jnz     short loc_18007AC9E
0x18007ac89  lea     rdx, [rsp+3A0h+var_340]
0x18007ac8e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_FamilySafetyRemoteLock@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FamilySafetyRemoteLock>::GetCachedFeatureEnabledState(void)
0x18007ac93  mov     rcx, [rax]
0x18007ac96  mov     [rsp+3A0h+var_340], rcx
0x18007ac9b  mov     r8d, ecx
0x18007ac9e  mov     dword ptr [rsp+3A0h+var_360], r13d
0x18007aca3  mov     word ptr [rsp+3A0h+var_360+4], 3
0x18007acaa  mov     r9d, r8d
0x18007acad  shr     r9d, 0Bh
0x18007acb1  and     r9d, esi
0x18007acb4  shr     r8d, 0Ah
0x18007acb8  and     r8d, esi
0x18007acbb  mov     [rsp+3A0h+var_370], 3
0x18007acc3  mov     [rsp+3A0h+var_378], esi
0x18007acc7  lea     rax, [rsp+3A0h+var_360]
0x18007accc  mov     [rsp+3A0h+var_380], rax
0x18007acd1  mov     edx, 1EEC734h
0x18007acd6  lea     rcx, qword_180109418
0x18007acdd  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18007ace2  mov     rbx, [rbx+58h]
0x18007ace6  mov     r15d, 37h ; '7'
0x18007acec  test    rbx, rbx
0x18007acef  jz      loc_18007AE6C
0x18007acf5  mov     rdx, rbx
0x18007acf8  lea     rcx, [rbp+2A0h+var_168]
0x18007acff  call    ??4TimeLimitsRule@Policy@wpc@@QEAAAEAU012@AEBU012@@Z; wpc::Policy::TimeLimitsRule::operator=(wpc::Policy::TimeLimitsRule const &)
0x18007ad04  mov     eax, [rbx+48h]
0x18007ad07  mov     [rbp+2A0h+var_120], eax
0x18007ad0d  xorps   xmm0, xmm0
0x18007ad10  movups  [rbp+2A0h+var_2D0], xmm0
0x18007ad14  xorps   xmm1, xmm1
0x18007ad17  movdqu  [rbp+2A0h+var_2C0], xmm1
0x18007ad1c  mov     [rsp+3A0h+var_360], r15
0x18007ad21  lea     rdx, [rsp+3A0h+var_360]
0x18007ad26  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18007ad2b  mov     qword ptr [rbp+2A0h+var_2D0], rax
0x18007ad2f  mov     qword ptr [rbp+2A0h+var_2C0], 35h ; '5'
0x18007ad37  mov     rcx, [rsp+3A0h+var_360]
0x18007ad3c  mov     qword ptr [rbp+2A0h+var_2C0+8], rcx
0x18007ad40  movaps  xmm0, xmmword ptr cs:aTimerestrictio_1; "TimeRestrictions changes merged to sett"...
0x18007ad47  movups  xmmword ptr [rax], xmm0
0x18007ad4a  movaps  xmm1, xmmword ptr cs:aTimerestrictio_1+10h; "rictions changes merged to settings for"...
0x18007ad51  movups  xmmword ptr [rax+10h], xmm1
0x18007ad55  movaps  xmm0, xmmword ptr cs:aTimerestrictio_1+20h; " changes merged to settings for user "
0x18007ad5c  movups  xmmword ptr [rax+20h], xmm0
0x18007ad60  movaps  xmm1, xmmword ptr cs:aTimerestrictio_1+30h; " merged to settings for user "
0x18007ad67  movups  xmmword ptr [rax+30h], xmm1
0x18007ad6b  movaps  xmm0, xmmword ptr cs:aTimerestrictio_1+40h; "to settings for user "
0x18007ad72  movups  xmmword ptr [rax+40h], xmm0
0x18007ad76  movaps  xmm1, xmmword ptr cs:aTimerestrictio_1+50h; "ngs for user "
0x18007ad7d  movups  xmmword ptr [rax+50h], xmm1
0x18007ad81  movups  xmm0, xmmword ptr cs:aTimerestrictio_1+5Ah; "or user "
0x18007ad88  movups  xmmword ptr [rax+5Ah], xmm0
0x18007ad8c  mov     [rax+6Ah], r13w
0x18007ad91  lea     rdx, [rbp+2A0h+var_280]
0x18007ad95  lea     rcx, [rbp+2A0h+var_2D0]; Src
0x18007ad99  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18007ad9e  xorps   xmm0, xmm0
0x18007ada1  movups  [rbp+2A0h+pExceptionObject], xmm0
0x18007ada5  xorps   xmm1, xmm1
0x18007ada8  movdqu  [rbp+2A0h+var_2F0], xmm1
0x18007adad  movups  xmm0, xmmword ptr [rax]
0x18007adb0  movups  [rbp+2A0h+pExceptionObject], xmm0
0x18007adb4  movups  xmm1, xmmword ptr [rax+10h]
0x18007adb8  movups  [rbp+2A0h+var_2F0], xmm1
0x18007adbc  mov     [rax+10h], r13
0x18007adc0  mov     qword ptr [rax+18h], 7
0x18007adc8  mov     [rax], r13w
0x18007adcc  mov     dword ptr [rsp+3A0h+var_360], 2
0x18007add4  lea     rdx, [rbp+2A0h+pExceptionObject]
0x18007add8  lea     rcx, [rsp+3A0h+var_360]
0x18007addd  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007ade2  nop
0x18007ade3  lea     rcx, [rbp+2A0h+pExceptionObject]
0x18007ade7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007adec  nop
0x18007aded  lea     rcx, [rbp+2A0h+var_2D0]
0x18007adf1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007adf6  test    rdi, rdi
0x18007adf9  jz      loc_18007AEF5
0x18007adff  lea     r8, [rdi+0E0h]
0x18007ae06  lea     r9, [rbp+2A0h+var_160]
0x18007ae0d  mov     rdx, r14
0x18007ae10  lea     rcx, [rbp+2A0h+pExceptionObject]
0x18007ae14  call    ?ReconcileOverrides@@YA?AV?$Optional@UExceptionRule@Policy@wpc@@@@AEBVSid@@AEBV1@1@Z; ReconcileOverrides(Sid const &,Optional<wpc::Policy::ExceptionRule> const &,Optional<wpc::Policy::ExceptionRule> const &)
0x18007ae19  cmp     [rbp+2A0h+var_138], r13
0x18007ae20  jz      short loc_18007AE29
0x18007ae22  mov     [rbp+2A0h+var_138], r13
0x18007ae29  mov     rcx, [rax+28h]
0x18007ae2d  test    rcx, rcx
0x18007ae30  jz      loc_18007AEF5
0x18007ae36  movups  xmm0, xmmword ptr [rcx]
0x18007ae39  movups  [rbp+2A0h+var_15C], xmm0
0x18007ae40  movups  xmm1, xmmword ptr [rcx+10h]
0x18007ae44  movups  [rbp+2A0h+var_14C], xmm1
0x18007ae4b  lea     rcx, [rbp+2A0h+var_15C]
0x18007ae52  mov     [rbp+2A0h+var_138], rcx
0x18007ae59  cmp     [rax+28h], r13
0x18007ae5d  jz      loc_18007AEF5
0x18007ae63  mov     [rax+28h], r13
0x18007ae67  jmp     loc_18007AEF5
0x18007ae6c  test    rdi, rdi
0x18007ae6f  jz      loc_18007AEF5
0x18007ae75  lea     rbx, [rdi+0D8h]
0x18007ae7c  mov     rdx, rbx
0x18007ae7f  lea     rcx, [rbp+2A0h+var_168]
0x18007ae86  call    ??4TimeLimitsRule@Policy@wpc@@QEAAAEAU012@AEBU012@@Z; wpc::Policy::TimeLimitsRule::operator=(wpc::Policy::TimeLimitsRule const &)
0x18007ae8b  mov     eax, [rbx+48h]
0x18007ae8e  mov     [rbp+2A0h+var_120], eax
0x18007ae94  mov     [rbp+2A0h+var_2D8], r13
0x18007ae98  lea     r8, [rdi+0E0h]
0x18007ae9f  lea     r9, [rbp+2A0h+pExceptionObject]
0x18007aea3  mov     rdx, r14
0x18007aea6  lea     rcx, [rbp+2A0h+var_2D0]
0x18007aeaa  call    ?ReconcileOverrides@@YA?AV?$Optional@UExceptionRule@Policy@wpc@@@@AEBVSid@@AEBV1@1@Z; ReconcileOverrides(Sid const &,Optional<wpc::Policy::ExceptionRule> const &,Optional<wpc::Policy::ExceptionRule> const &)
0x18007aeaf  cmp     [rbp+2A0h+var_138], r13
0x18007aeb6  jz      short loc_18007AEBF
0x18007aeb8  mov     [rbp+2A0h+var_138], r13
0x18007aebf  mov     rcx, [rax+28h]
0x18007aec3  test    rcx, rcx
0x18007aec6  jz      short loc_18007AEF5
0x18007aec8  movups  xmm0, xmmword ptr [rcx]
0x18007aecb  movups  [rbp+2A0h+var_15C], xmm0
0x18007aed2  movups  xmm1, xmmword ptr [rcx+10h]
0x18007aed6  movups  [rbp+2A0h+var_14C], xmm1
0x18007aedd  lea     rcx, [rbp+2A0h+var_15C]
0x18007aee4  mov     [rbp+2A0h+var_138], rcx
0x18007aeeb  cmp     [rax+28h], r13
0x18007aeef  jz      short loc_18007AEF5
0x18007aef1  mov     [rax+28h], r13
0x18007aef5  lea     rdx, [rbp+2A0h+var_240]
0x18007aef9  cmp     [r12+38h], r13
0x18007aefe  jz      loc_18007B014
0x18007af04  lea     rcx, [rbp+2A0h+Src]
0x18007af08  call    _lambda_23d3af2253d0be10932d07aa17f626e7___operator__
0x18007af0d  xorps   xmm0, xmm0
0x18007af10  movups  [rbp+2A0h+var_2D0], xmm0
0x18007af14  xorps   xmm1, xmm1
0x18007af17  movdqu  [rbp+2A0h+var_2C0], xmm1
0x18007af1c  mov     [rsp+3A0h+var_360], r15
0x18007af21  lea     rdx, [rsp+3A0h+var_360]
0x18007af26  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18007af2b  mov     rdx, rax
0x18007af2e  mov     qword ptr [rbp+2A0h+var_2D0], rax
0x18007af32  mov     qword ptr [rbp+2A0h+var_2C0], 32h ; '2'
0x18007af3a  mov     rcx, [rsp+3A0h+var_360]
0x18007af3f  mov     qword ptr [rbp+2A0h+var_2C0+8], rcx
0x18007af43  movaps  xmm0, xmmword ptr cs:aApplymonitorin_0; "applyMonitoringFlagsFromServer when use"...
0x18007af4a  movups  xmmword ptr [rax], xmm0
0x18007af4d  movaps  xmm1, xmmword ptr cs:aApplymonitorin_0+10h; "itoringFlagsFromServer when user with s"...
0x18007af54  movups  xmmword ptr [rax+10h], xmm1
0x18007af58  movaps  xmm0, xmmword ptr cs:aApplymonitorin_0+20h; "lagsFromServer when user with sid:"
0x18007af5f  movups  xmmword ptr [rax+20h], xmm0
0x18007af63  movaps  xmm1, xmmword ptr cs:aApplymonitorin_0+30h; "Server when user with sid:"
0x18007af6a  movups  xmmword ptr [rax+30h], xmm1
0x18007af6e  movaps  xmm0, xmmword ptr cs:aApplymonitorin_0+40h; "hen user with sid:"
0x18007af75  movups  xmmword ptr [rax+40h], xmm0
0x18007af79  movaps  xmm1, xmmword ptr cs:aApplymonitorin_0+50h; " with sid:"
0x18007af80  movups  xmmword ptr [rax+50h], xmm1
0x18007af84  mov     eax, dword ptr cs:aApplymonitorin_0+60h; "d:"
0x18007af8a  mov     [rdx+60h], eax
0x18007af8d  mov     [rdx+64h], r13w
0x18007af92  lea     rdx, [rbp+2A0h+var_280]
0x18007af96  lea     rcx, [rbp+2A0h+var_2D0]; Src
0x18007af9a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18007af9f  xorps   xmm0, xmm0
0x18007afa2  movups  [rbp+2A0h+pExceptionObject], xmm0
0x18007afa6  xorps   xmm1, xmm1
0x18007afa9  movdqu  [rbp+2A0h+var_2F0], xmm1
0x18007afae  movups  xmm0, xmmword ptr [rax]
0x18007afb1  movups  [rbp+2A0h+pExceptionObject], xmm0
0x18007afb5  movups  xmm1, xmmword ptr [rax+10h]
0x18007afb9  movups  [rbp+2A0h+var_2F0], xmm1
  ... truncated ...
```
