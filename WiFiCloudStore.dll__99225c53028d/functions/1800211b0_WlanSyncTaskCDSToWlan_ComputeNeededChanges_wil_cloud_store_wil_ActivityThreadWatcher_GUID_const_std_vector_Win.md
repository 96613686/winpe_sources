# WlanSyncTaskCDSToWlan::ComputeNeededChanges(wil::cloud_store &,wil::ActivityThreadWatcher &,_GUID const &,std::vector<Windows::Internal::WiFiCloudStore::ProfileGeneration,std::allocator<Windows::Internal::WiFiCloudStore::ProfileGeneration>> const &,bool)

- ea: `0x1800211b0`
- end: `0x1800231c1`
- name: `?ComputeNeededChanges@WlanSyncTaskCDSToWlan@@QEAA?AV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEAVcloud_store@wil@@AEAVActivityThreadWatcher@5@AEBU_GUID@@AEBV?$vector@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@V?$allocator@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@@3@_N@Z`
- size: `8209`
- prototype: `_QWORD *__fastcall(WlanSyncTaskCDSToWlan *, _QWORD *, __int64, wil::ActivityThreadWatcher *, struct _GUID *, unsigned int **, bool)`
- caller_count: `1`
- callee_count: `90`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012594`

## callees

- `0x180001200`
- `0x1800056c8`
- `0x180005700`
- `0x180005880`
- `0x180005b70`
- `0x180005e00`
- `0x18000766c`
- `0x1800077bc`
- `0x1800079f0`
- `0x180007ee4`
- `0x180007f90`
- `0x180008c50`
- `0x18000a2c8`
- `0x18000a710`
- `0x18000a944`
- `0x18000aebc`
- `0x180010c8c`
- `0x1800119bc`
- `0x180013a94`
- `0x180015fa8`
- `0x1800174c0`
- `0x18001788c`
- `0x180017de4`
- `0x1800183c0`
- `0x180018730`
- `0x180018780`
- `0x180018900`
- `0x180019598`
- `0x180019764`
- `0x18001a5bc`
- `0x18001aa58`
- `0x18001aaf0`
- `0x18001b634`
- `0x18001b838`
- `0x18001bbe8`
- `0x18001c63c`
- `0x18001ca70`
- `0x18001ce94`
- `0x18001d86c`
- `0x18001df70`
- `0x18001e290`
- `0x18001e5b0`
- `0x18001efb8`
- `0x18001f008`
- `0x18001f298`
- `0x18001fa7c`
- `0x1800202bc`
- `0x1800209e0`
- `0x180020a40`
- `0x180020acc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180021f62`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180021f62`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800225e3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800225e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180021f96`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180022f2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180021f96`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180022f2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022091`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002302e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022091`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002302e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180022047`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180022fdd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180022047`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180022fdd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180022062`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180022ff8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180022062`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180022ff8`
- `wlanapi!WlanFreeMemory` at `0x1800212b5`
- `wlanapi!WlanFreeMemory` at `0x1800212c4`
- `wlanapi!WlanFreeMemory` at `0x1800213c8`
- `wlanapi!WlanFreeMemory` at `0x18002175b`
- `wlanapi!WlanFreeMemory` at `0x1800212b5`
- `wlanapi!WlanFreeMemory` at `0x1800212c4`
- `wlanapi!WlanFreeMemory` at `0x1800213c8`
- `wlanapi!WlanFreeMemory` at `0x18002175b`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x18002139b`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x18002139b`
- `wlanapi!WlanWcmGetProfileList` at `0x180021264`
- `wlanapi!WlanWcmGetProfileList` at `0x180021264`
- `dusmapi!DusmQueryUserCost` at `0x1800229a2`
- `dusmapi!DusmQueryUserCost` at `0x1800229a2`

## string_xrefs

- `0x1800228d6`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180022b18`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180022ee9`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x18002312f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180023144`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180023176`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x18002318b`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WlanSyncTaskCDSToWlan::ComputeNeededChanges(
        WlanSyncTaskCDSToWlan *a1,
        _QWORD *a2,
        __int64 a3,
        wil::ActivityThreadWatcher *a4,
        struct _GUID *a5,
        unsigned int **a6,
        bool a7)
{
  wil::ActivityThreadWatcher *v7; // rdi
  __int64 v8; // r12
  struct _GUID *v10; // r14
  struct wil::details_abi::ThreadLocalData *v11; // r15
  unsigned int v12; // esi
  unsigned int ProfileList; // eax
  unsigned int *v14; // rdi
  unsigned int i; // ebx
  void *v16; // rcx
  unsigned int v17; // r13d
  unsigned int *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r12
  int v21; // r9d
  unsigned int ProfileMetadataWithProfileGuid; // eax
  void *v23; // rcx
  int v24; // r14d
  _OWORD *v25; // rdi
  signed __int64 v26; // rax
  signed __int64 v27; // rsi
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rbx
  size_t v31; // rcx
  unsigned __int64 v32; // r13
  void *v33; // rax
  unsigned __int64 v34; // rsi
  int v35; // edx
  __int64 v36; // rsi
  _QWORD *v37; // r14
  struct wil::details_abi::ThreadLocalData *v38; // rcx
  _QWORD *v39; // rbx
  unsigned __int64 v40; // rdx
  char *v41; // rax
  unsigned __int64 v42; // rdx
  char *v43; // rcx
  unsigned __int64 v44; // rdx
  PVOID v45; // rcx
  void *v46; // rsi
  signed __int64 v47; // rax
  signed __int64 v48; // r14
  unsigned __int64 v49; // r15
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rdi
  size_t v53; // rax
  size_t v54; // rcx
  struct wil::details_abi::ThreadLocalData *v55; // rbx
  void *v56; // rax
  unsigned __int64 v57; // r14
  int v58; // edx
  __int64 v59; // r14
  void *v60; // rdx
  _QWORD *v61; // r8
  void *v62; // rcx
  unsigned int *v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rax
  int v66; // esi
  wil::details_abi *v67; // rcx
  bool v68; // dl
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  struct wil::details::IFunctorHost *v70; // r8
  __int64 v71; // rcx
  __int64 v72; // rbx
  wil::ActivityThreadWatcher *v73; // r15
  wil::ActivityThreadWatcher *v74; // r14
  unsigned __int64 v75; // rdi
  unsigned __int64 v76; // rax
  _QWORD *v77; // r10
  void *v78; // rax
  __int64 v79; // r8
  _QWORD *k; // rdx
  bool v81; // al
  int v82; // r13d
  __int64 v83; // rsi
  __int64 v84; // rcx
  __int64 v85; // rdx
  unsigned __int64 v86; // rcx
  unsigned __int64 v87; // r8
  __int64 v88; // r12
  unsigned __int64 v89; // rdi
  __int64 v90; // r15
  size_t v91; // rcx
  struct wil::details_abi::ThreadLocalData *v92; // rbx
  void *v93; // rax
  char *v94; // rdx
  char *v95; // r15
  __int64 v96; // rdx
  _QWORD *v97; // r8
  __int64 v98; // rcx
  signed __int64 v99; // rsi
  __int64 v100; // rdi
  ULONGLONG *v101; // rbx
  _DWORD *v102; // rcx
  unsigned __int64 FutureIgnoreDateAsStdTime; // r12
  _QWORD *v104; // rax
  char *v105; // rbx
  char *v106; // r13
  const char *v107; // rdx
  __int64 v108; // rdi
  unsigned __int64 v109; // rcx
  unsigned __int64 v110; // r8
  _QWORD *v111; // rax
  _QWORD *v112; // r14
  unsigned __int64 v113; // rsi
  _OWORD *v114; // r12
  __int64 v115; // rcx
  unsigned __int64 v116; // rax
  void *v117; // rax
  __int64 v118; // rdx
  unsigned __int64 v119; // rcx
  float v120; // xmm0_4
  unsigned __int64 v121; // rsi
  float v122; // xmm2_4
  float v123; // xmm0_4
  unsigned __int64 v124; // rcx
  unsigned __int64 v125; // rax
  unsigned __int64 v126; // rcx
  _QWORD *v127; // rcx
  _QWORD *v128; // r8
  __int64 v129; // rax
  __int64 v130; // rdi
  _QWORD *v131; // rdx
  __int64 v132; // rdi
  struct _GUID *v133; // r13
  unsigned __int64 v134; // r13
  void *v135; // r12
  void *v136; // r15
  _BYTE *v137; // rsi
  const struct _TOKEN_USER *v138; // rax
  char DoesSidAllowUpdateWithProfileGuid; // al
  const struct _TOKEN_USER *CurrentUserToken; // rax
  char v141; // al
  _QWORD *v142; // rcx
  _QWORD *v143; // r12
  char v144; // r15
  const unsigned __int16 *v145; // rsi
  __int64 v146; // rax
  __int64 v147; // rax
  bool v148; // r14
  WINBOOL v149; // eax
  const char *v150; // rax
  const unsigned __int16 *v151; // rax
  int v152; // eax
  unsigned int v153; // eax
  __int64 v154; // rsi
  char *v155; // rcx
  _QWORD *v156; // rcx
  int v157; // eax
  int v158; // r14d
  const unsigned __int16 *v159; // rsi
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rsi
  __int64 v163; // r15
  const struct _TOKEN_USER *v164; // rax
  bool v165; // al
  bool v166; // r12
  __int64 v167; // r15
  __int64 v168; // r15
  ULONGLONG *v169; // rsi
  int v170; // r8d
  int v171; // r9d
  unsigned int v173; // eax
  unsigned int v174; // [rsp+20h] [rbp-E0h]
  _BYTE v175[4]; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL fPending; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v177; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID Context; // [rsp+60h] [rbp-A0h] BYREF
  int v179; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v180[2]; // [rsp+70h] [rbp-90h] BYREF
  char v181[8]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 j; // [rsp+80h] [rbp-80h] BYREF
  void *v183[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v184; // [rsp+98h] [rbp-68h]
  wil::ActivityThreadWatcher *v185; // [rsp+A0h] [rbp-60h] BYREF
  PVOID pMemory; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID *v187; // [rsp+B0h] [rbp-50h]
  int v188; // [rsp+B8h] [rbp-48h]
  __int128 v189; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v190; // [rsp+D0h] [rbp-30h]
  _QWORD *v191; // [rsp+D8h] [rbp-28h]
  __int128 v192; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v193; // [rsp+F0h] [rbp-10h]
  unsigned int *v194; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v195; // [rsp+100h] [rbp+0h]
  WlanSyncTaskCDSToWlan *v196; // [rsp+108h] [rbp+8h]
  __int64 v197; // [rsp+110h] [rbp+10h] BYREF
  __int64 v198; // [rsp+118h] [rbp+18h] BYREF
  void *v199; // [rsp+120h] [rbp+20h]
  char v200; // [rsp+130h] [rbp+30h]
  __int128 v201; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v202[2]; // [rsp+150h] [rbp+50h] BYREF
  int v203; // [rsp+160h] [rbp+60h]
  int v204; // [rsp+164h] [rbp+64h]
  LPVOID *p_Context; // [rsp+168h] [rbp+68h]
  _BYTE v206[24]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD *v207; // [rsp+188h] [rbp+88h]
  void **v208; // [rsp+190h] [rbp+90h] BYREF
  struct wil::details_abi::ThreadLocalData *v209; // [rsp+198h] [rbp+98h]
  unsigned __int64 v210; // [rsp+1A0h] [rbp+A0h]
  GUID *v211; // [rsp+1A8h] [rbp+A8h]
  __int64 v212; // [rsp+1B0h] [rbp+B0h]
  GUID ProviderId; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v214[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 *v215; // [rsp+1D8h] [rbp+D8h]
  unsigned __int64 v216; // [rsp+1E0h] [rbp+E0h]
  GUID v217; // [rsp+1E8h] [rbp+E8h] BYREF
  const char *v218; // [rsp+1F8h] [rbp+F8h]
  __int16 v219; // [rsp+200h] [rbp+100h]
  _BYTE v220[32]; // [rsp+210h] [rbp+110h] BYREF
  void *v221; // [rsp+230h] [rbp+130h]
  void *v222; // [rsp+238h] [rbp+138h]
  __int64 v223; // [rsp+240h] [rbp+140h]
  char v224; // [rsp+248h] [rbp+148h]
  _BYTE v225[32]; // [rsp+260h] [rbp+160h] BYREF
  struct _GUID v226; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v227[256]; // [rsp+290h] [rbp+190h] BYREF
  float v228; // [rsp+490h] [rbp+390h] BYREF
  _QWORD *v229; // [rsp+498h] [rbp+398h] BYREF
  __int64 v230; // [rsp+4A0h] [rbp+3A0h]
  __int64 v231; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int128 v232; // [rsp+4B0h] [rbp+3B0h]
  __int64 v233; // [rsp+4C0h] [rbp+3C0h]
  __int64 v234; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v7 = a4;
  v185 = a4;
  v8 = a3;
  v195 = a3;
  v191 = a2;
  v196 = a1;
  v207 = a2;
  v10 = a5;
  v187 = a5;
  v11 = 0;
  Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(v206, a5);
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v12 = 1;
  v179 = 1;
  v188 = 1;
  *(_OWORD *)v183 = 0;
  v184 = 0;
  v194 = 0;
  *(_QWORD *)&v192 = &v194;
  *((_QWORD *)&v192 + 1) = 0;
  LOBYTE(v193) = 1;
  ProfileList = WlanWcmGetProfileList(a5, 0, (struct WCM_WLAN_PROFILE_INFO_LIST **)&v192 + 1);
  if ( ProfileList )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      (const char *)ProfileList,
      v174);
  if ( (_BYTE)v193 )
  {
    v14 = *(unsigned int **)v192;
    *(_QWORD *)v192 = *((_QWORD *)&v192 + 1);
    if ( v14 )
    {
      for ( i = 0; i < *v14; ++i )
      {
        v16 = *(void **)&v14[154 * i + 154];
        if ( v16 )
          WlanFreeMemory(v16);
      }
      WlanFreeMemory(v14);
    }
    v7 = v185;
  }
  v17 = 0;
  fPending = 0;
  v18 = v194;
  if ( *v194 )
  {
    while ( 1 )
    {
      v19 = 154LL * v17;
      Context = &v18[v19 + 6];
      v20 = (__int64)&v18[v19 + 2];
      if ( v18[v19 + 150] == 9 )
        v21 = 1;
      else
        v21 = v18[v19 + 150] == 10 ? 2 : 0;
      LODWORD(j) = v21;
      wil::ActivityThreadWatcher::SetMessage(v7, "Profile name: %ws, Generation: %d");
      if ( WlanSyncTaskCommon::IsProfileEligibleForCDSSync(v10, (const struct WCM_WLAN_PROFILE_INFO *)&v194[v19 + 2]) )
        break;
      v175[0] = 0;
      v46 = v183[1];
      if ( v183[1] == v184 )
      {
        v47 = ((char *)v183[1] - (char *)v183[0]) >> 6;
        if ( v47 == 0x3FFFFFFFFFFFFFFLL )
          ((void (__noreturn *)(void))std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Xlength)();
        v48 = (char *)v183[1] - (char *)v183[0];
        v49 = v47 + 1;
        v50 = (v184 - (char *)v183[0]) >> 6;
        v51 = v50 >> 1;
        if ( v50 > 0x3FFFFFFFFFFFFFFLL - (v50 >> 1) )
        {
          v52 = 0x3FFFFFFFFFFFFFFLL;
          v53 = -25;
          goto LABEL_75;
        }
        v52 = v47 + 1;
        if ( v51 + v50 >= v49 )
          v52 = v51 + v50;
        if ( v52 > 0x3FFFFFFFFFFFFFFLL )
LABEL_300:
          std::_Throw_bad_array_new_length();
        v54 = v52 << 6;
        if ( v52 << 6 )
        {
          if ( v54 < 0x1000 )
          {
            v55 = (struct wil::details_abi::ThreadLocalData *)operator new(v54);
          }
          else
          {
            v53 = v54 + 39;
            if ( v54 + 39 < v54 )
              goto LABEL_300;
LABEL_75:
            v56 = operator new(v53);
            if ( !v56 )
              __fastfail(5u);
            v55 = (struct wil::details_abi::ThreadLocalData *)(((unsigned __int64)v56 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v55 - 1) = v56;
          }
        }
        else
        {
          v55 = 0;
        }
        v57 = v48 & 0xFFFFFFFFFFFFFFC0uLL;
        v58 = v57 + (_DWORD)v55;
        v59 = (__int64)v55 + v57 + 64;
        v208 = v183;
        v209 = v55;
        v210 = v52;
        v211 = (GUID *)v59;
        v212 = v59;
        std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_unsigned_short_const______GUID_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration_const___(
          v54,
          v58,
          (unsigned int)&Context,
          v20,
          (__int64)v175,
          (__int64)&j);
        v60 = v183[1];
        v61 = v55;
        v62 = v183[0];
        if ( v46 != v183[1] )
        {
          std::_Uninitialized_move__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___(
            v183[0],
            v46,
            v55);
          v61 = (_QWORD *)v59;
          v60 = v183[1];
          v62 = v46;
        }
        std::_Uninitialized_move__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___(
          v62,
          v60,
          v61);
        std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::_Change_array(
          v183,
          v55,
          v49,
          v52);
        v11 = 0;
LABEL_81:
        v7 = v185;
        v10 = v187;
        goto LABEL_82;
      }
      std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_unsigned_short_const______GUID_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration_const___(
        (_DWORD)v184,
        v183[1],
        (unsigned int)&Context,
        v20,
        (__int64)v175,
        (__int64)&j);
      v183[1] = (char *)v183[1] + 64;
LABEL_82:
      fPending = ++v17;
      v18 = v194;
      if ( v17 >= *v194 )
      {
        v12 = v179;
        v8 = v195;
        goto LABEL_84;
      }
    }
    pMemory = 0;
    v180[0] = 0;
    *(_QWORD *)&v192 = &pMemory;
    *((_QWORD *)&v192 + 1) = 0;
    LOBYTE(v193) = 1;
    ProfileMetadataWithProfileGuid = WlanGetProfileMetadataWithProfileGuid(v10, v20, 0, L"LastModified");
    if ( ProfileMetadataWithProfileGuid )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
        (const char *)ProfileMetadataWithProfileGuid,
        (unsigned int)v180);
    if ( (_BYTE)v193 )
    {
      v23 = *(void **)v192;
      *(_QWORD *)v192 = *((_QWORD *)&v192 + 1);
      if ( v23 )
        WlanFreeMemory(v23);
    }
    if ( v180[0] != 8 )
    {
      v173 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
        (const char *)v173,
        (int)v180);
    }
    v175[0] = 1;
    v24 = (int)pMemory;
    v25 = v183[1];
    if ( v183[1] != v184 )
    {
      std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_unsigned_short_const______FILETIME____GUID_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration_const___(
        (_DWORD)v184,
        v183[1],
        (unsigned int)&Context,
        (_DWORD)pMemory,
        v20,
        (__int64)v175,
        (__int64)&j);
      v183[1] = (char *)v183[1] + 64;
LABEL_61:
      v45 = pMemory;
      pMemory = 0;
      if ( v45 )
        WlanFreeMemory(v45);
      goto LABEL_81;
    }
    v26 = ((char *)v183[1] - (char *)v183[0]) >> 6;
    if ( v26 == 0x3FFFFFFFFFFFFFFLL )
      std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Xlength(
        v184,
        v183[0]);
    v27 = (char *)v183[1] - (char *)v183[0];
    v177 = v26 + 1;
    v28 = (v184 - (char *)v183[0]) >> 6;
    v29 = v28 >> 1;
    if ( v28 <= 0x3FFFFFFFFFFFFFFLL - (v28 >> 1) )
    {
      v30 = v26 + 1;
      if ( v29 + v28 >= v26 + 1 )
        v30 = v29 + v28;
      if ( v30 > 0x3FFFFFFFFFFFFFFLL )
LABEL_296:
        std::_Throw_bad_array_new_length();
      v32 = v30 << 6;
      if ( !(v30 << 6) )
      {
LABEL_36:
        v34 = v27 & 0xFFFFFFFFFFFFFFC0uLL;
        v35 = v34 + (_DWORD)v11;
        v36 = (__int64)v11 + v34 + 64;
        v208 = v183;
        v209 = v11;
        v210 = v30;
        v211 = (GUID *)v36;
        v212 = v36;
        std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_unsigned_short_const______FILETIME____GUID_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration_const___(
          v28,
          v35,
          (unsigned int)&Context,
          v24,
          v20,
          (__int64)v175,
          (__int64)&j);
        v37 = v183[1];
        v38 = v11;
        v39 = v183[0];
        if ( v25 == v183[1] )
        {
          if ( v183[0] == v183[1] )
          {
LABEL_46:
            if ( v39 )
            {
              if ( v39 != v37 )
              {
                do
                {
                  v40 = v39[3];
                  if ( v40 > 7 )
                  {
                    v41 = (char *)*v39;
                    v42 = 2 * v40 + 2;
                    if ( v42 < 0x1000 )
                    {
                      v43 = (char *)*v39;
                    }
                    else
                    {
                      v43 = (char *)*((_QWORD *)v41 - 1);
                      if ( (unsigned __int64)(v41 - v43 - 8) > 0x1F )
                        goto LABEL_90;
                      v42 += 39LL;
                    }
                    operator delete(v43, v42);
                  }
                  v39[2] = 0;
                  v39[3] = 7;
                  *(_WORD *)v39 = 0;
                  v39 += 8;
                }
                while ( v39 != v37 );
                v39 = v183[0];
              }
              v44 = (v184 - (char *)v39) & 0xFFFFFFFFFFFFFFC0uLL;
              if ( v44 >= 0x1000 )
              {
                if ( (unsigned __int64)v39 - *(v39 - 1) - 8 > 0x1F )
LABEL_90:
                  __fastfail(5u);
                v44 += 39LL;
                v39 = (_QWORD *)*(v39 - 1);
              }
              operator delete(v39, v44);
            }
            v183[0] = v11;
            v183[1] = (char *)v11 + 64 * v177;
            v184 = (char *)v11 + v32;
            v17 = fPending;
            v11 = 0;
            goto LABEL_61;
          }
          do
          {
            *(_OWORD *)v38 = 0;
            *((_QWORD *)v38 + 2) = 0;
            *((_QWORD *)v38 + 3) = 0;
            *(_OWORD *)v38 = *(_OWORD *)v39;
            *((_OWORD *)v38 + 1) = *((_OWORD *)v39 + 1);
            v39[2] = 0;
            v39[3] = 7;
            *(_WORD *)v39 = 0;
            *((_QWORD *)v38 + 4) = v39[4];
            *(_OWORD *)((char *)v38 + 40) = *(_OWORD *)(v39 + 5);
            *((_BYTE *)v38 + 56) = *((_BYTE *)v39 + 56);
            *((_DWORD *)v38 + 15) = *((_DWORD *)v39 + 15);
            v38 = (struct wil::details_abi::ThreadLocalData *)((char *)v38 + 64);
            v39 += 8;
          }
          while ( v39 != v37 );
        }
        else
        {
          if ( v183[0] != v25 )
          {
            do
            {
              *(_OWORD *)v38 = 0;
              *((_QWORD *)v38 + 2) = 0;
              *((_QWORD *)v38 + 3) = 0;
              *(_OWORD *)v38 = *(_OWORD *)v39;
              *((_OWORD *)v38 + 1) = *((_OWORD *)v39 + 1);
              v39[2] = 0;
              v39[3] = 7;
              *(_WORD *)v39 = 0;
              *((_QWORD *)v38 + 4) = v39[4];
              *(_OWORD *)((char *)v38 + 40) = *(_OWORD *)(v39 + 5);
              *((_BYTE *)v38 + 56) = *((_BYTE *)v39 + 56);
              *((_DWORD *)v38 + 15) = *((_DWORD *)v39 + 15);
              v38 = (struct wil::details_abi::ThreadLocalData *)((char *)v38 + 64);
              v39 += 8;
            }
            while ( v39 != (_QWORD *)v25 );
            v37 = v183[1];
            v39 = v183[0];
          }
          if ( v25 == (_OWORD *)v37 )
            goto LABEL_46;
          do
          {
            *(_OWORD *)v36 = 0;
            *(_QWORD *)(v36 + 16) = 0;
            *(_QWORD *)(v36 + 24) = 0;
            *(_OWORD *)v36 = *v25;
            *(_OWORD *)(v36 + 16) = v25[1];
            *((_QWORD *)v25 + 2) = 0;
            *((_QWORD *)v25 + 3) = 7;
            *(_WORD *)v25 = 0;
            *(_QWORD *)(v36 + 32) = *((_QWORD *)v25 + 4);
            *(_OWORD *)(v36 + 40) = *(_OWORD *)((char *)v25 + 40);
            *(_BYTE *)(v36 + 56) = *((_BYTE *)v25 + 56);
            *(_DWORD *)(v36 + 60) = *((_DWORD *)v25 + 15);
            v36 += 64;
            v25 += 4;
          }
          while ( v25 != (_OWORD *)v37 );
        }
        v39 = v183[0];
        v37 = v183[1];
        goto LABEL_46;
      }
      if ( v32 < 0x1000 )
      {
        v11 = (struct wil::details_abi::ThreadLocalData *)operator new(v30 << 6);
        goto LABEL_36;
      }
      v31 = v32 + 39;
      if ( v32 + 39 < v32 )
        goto LABEL_296;
    }
    else
    {
      v30 = 0x3FFFFFFFFFFFFFFLL;
      v31 = -25;
      v32 = -64;
    }
    v33 = operator new(v31);
    if ( !v33 )
      __fastfail(5u);
    v11 = (struct wil::details_abi::ThreadLocalData *)(((unsigned __int64)v33 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)v11 - 1) = v33;
    goto LABEL_36;
  }
LABEL_84:
  wil::details::StoredCallContextInfo::ClearMessage(v7);
  *((_QWORD *)v7 + 2) = 0;
  v189 = 0;
  v190 = 0;
  v63 = *a6;
  *(_QWORD *)v180 = v63;
  for ( j = (unsigned __int64)a6[1]; v63 != (unsigned int *)j; *(_QWORD *)v180 = v63 )
  {
    v64 = *v63;
    fPending = v64;
    _mm_lfence();
    v65 = *(_QWORD *)(qword_180052A58
                    + 16
                    * (qword_180052A70
                     & (0x100000001B3LL
                      * (BYTE3(v64)
                       ^ (0x100000001B3LL
                        * (BYTE2(v64)
                         ^ (0x100000001B3LL
                          * ((0x100000001B3LL * ((unsigned __int8)v64 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v64))))))))
                    + 8);
    if ( v65 == qword_180052A48 )
    {
LABEL_141:
      std::_Xout_of_range("invalid unordered_map<K, T> key");
      __debugbreak();
    }
    while ( (_DWORD)v64 != *(_DWORD *)(v65 + 16) )
    {
      if ( v65 == *(_QWORD *)(qword_180052A58
                            + 16
                            * (qword_180052A70
                             & (0x100000001B3LL
                              * (BYTE3(v64)
                               ^ (0x100000001B3LL
                                * (BYTE2(v64)
                                 ^ (0x100000001B3LL
                                  * ((0x100000001B3LL * ((unsigned __int8)v64 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v64))))))))) )
        goto LABEL_141;
      v65 = *(_QWORD *)(v65 + 8);
    }
    Context = (LPVOID)&dword_180043B4C;
    v177 = *(_QWORD *)(v65 + 24);
    *(_QWORD *)&v217.Data1 = retaddr;
    *(_QWORD *)v217.Data4 = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
    v218 = "LoadCollection";
    v219 = 995;
    v202[0] = v8;
    v202[1] = &v177;
    v203 = 0;
    v204 = 1;
    p_Context = &Context;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl'::`2'::impl,
      2
    * (qword_180052A70
     & (0x100000001B3LL
      * (BYTE3(v64)
       ^ (0x100000001B3LL
        * (BYTE2(v64)
         ^ (0x100000001B3LL * ((0x100000001B3LL * ((unsigned __int8)v64 ^ 0xCBF29CE484222325uLL)) ^ BYTE1(v64)))))))),
      v64,
      0x100000001B3LL);
    v192 = 0;
    v193 = 0;
    v66 = v12 | 0x20;
    v188 = v66;
    v214[0] = &wil::details::functor_wrapper_other<_lambda_7d003934526d0242e45c838f7fda2c5e_ &,std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>>::`vftable';
    v214[1] = v202;
    v215 = &v192;
    v208 = &wil::details::FeatureFunctorHost::`vftable';
    LOBYTE(v67) = 1;
    ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v67, v68);
    v209 = ThreadLocalDataCache;
    v210 = 0;
    if ( ThreadLocalDataCache )
    {
      HIDWORD(v210) = *((_DWORD *)ThreadLocalDataCache + 4);
      LODWORD(v210) = **((_DWORD **)ThreadLocalDataCache + 1);
      *((_DWORD *)v209 + 4) = v210;
    }
    v211 = &v217;
    LODWORD(v212) = 6201249;
    wil::details::RunFunctor((wil::details *)v214, (struct wil::details::IFunctor *)&v208, v70);
    if ( v209 )
      *((_DWORD *)v209 + 4) = HIDWORD(v210);
    v12 = v66 & 0xFFFFFFC1 | 0x1E;
    v179 = v12;
    v188 = v12;
    v71 = v189;
    v72 = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)&v189 + 1) - v189) >> 3);
    v73 = (wil::ActivityThreadWatcher *)*((_QWORD *)&v192 + 1);
    v185 = (wil::ActivityThreadWatcher *)*((_QWORD *)&v192 + 1);
    v74 = (wil::ActivityThreadWatcher *)v192;
    v75 = v72 + ((__int64)(*((_QWORD *)&v192 + 1) - v192) >> 6);
    if ( v75 > 0x6DB6DB6DB6DB6DB7LL * ((v190 - (__int64)v189) >> 3) )
    {
      if ( v75 > 0x492492492492492LL )
        std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Xlength(
          v189,
          0x6DB6DB6DB6DB6DB7LL);
      v76 = 56 * v75;
      if ( 56 * v75 )
      {
        if ( v76 < 0x1000 )
        {
          v77 = operator new(56 * v75);
        }
        else
        {
          if ( v76 + 39 < v76 )
            std::_Throw_bad_array_new_length();
          v78 = operator new(v76 + 39);
          if ( !v78 )
            __fastfail(5u);
          v77 = (_QWORD *)(((unsigned __int64)v78 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v77 - 1) = v78;
        }
        v71 = v189;
      }
      else
      {
        v77 = 0;
      }
      v79 = *((_QWORD *)&v189 + 1);
      for ( k = v77; v71 != v79; v71 += 56 )
      {
        *(_OWORD *)k = 0;
        k[2] = 0;
        k[3] = 0;
        *(_OWORD *)k = *(_OWORD *)v71;
        *((_OWORD *)k + 1) = *(_OWORD *)(v71 + 16);
        *(_QWORD *)(v71 + 16) = 0;
        *(_QWORD *)(v71 + 24) = 7;
        *(_WORD *)v71 = 0;
        k[4] = *(_QWORD *)(v71 + 32);
        k[5] = *(_QWORD *)(v71 + 40);
        *((_BYTE *)k + 48) = *(_BYTE *)(v71 + 48);
        *((_DWORD *)k + 13) = *(_DWORD *)(v71 + 52);
        k += 7;
      }
      std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Change_array(
        &v189,
        v77,
        v72,
        v75);
      v73 = (wil::ActivityThreadWatcher *)*((_QWORD *)&v192 + 1);
      v185 = (wil::ActivityThreadWatcher *)*((_QWORD *)&v192 + 1);
      v74 = (wil::ActivityThreadWatcher *)v192;
    }
    if ( v74 != v73 )
    {
      do
      {
        wil::cloud_store::load<Windows::Data::WiFi::WiFiProfile>(v8, v220, v74, 0);
        Context = v222;
        v81 = v222 && v224;
        v175[0] = v81;
        pMemory = v221;
        v82 = Windows::Internal::WiFiCloudStore::CDSReferenceIdToProfileName(v214, v74);
        v83 = *((_QWORD *)&v189 + 1);
        if ( *((_QWORD *)&v189 + 1) == v190 )
        {
          v85 = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)&v189 + 1) - v189) >> 3);
          if ( v85 == 0x492492492492492LL )
            std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Xlength(
              v190,
              0x492492492492492LL);
          v86 = 0x6DB6DB6DB6DB6DB7LL * ((v190 - (__int64)v189) >> 3);
          v87 = v86 >> 1;
          if ( v86 > 0x492492492492492LL - (v86 >> 1) )
            goto LABEL_304;
          v88 = v85 + 1;
          v89 = v85 + 1;
          if ( v86 + v87 >= v85 + 1 )
            v89 = v86 + v87;
          if ( v89 > 0x492492492492492LL )
LABEL_304:
            std::_Throw_bad_array_new_length();
          v90 = *((_QWORD *)&v189 + 1) - v189;
          v91 = 56 * v89;
          if ( 56 * v89 )
          {
            if ( v91 < 0x1000 )
            {
              v92 = (struct wil::details_abi::ThreadLocalData *)operator new(v91);
            }
            else
            {
              if ( v91 + 39 < v91 )
                goto LABEL_304;
              v93 = operator new(v91 + 39);
              if ( !v93 )
                __fastfail(5u);
              v92 = (struct wil::details_abi::ThreadLocalData *)(((unsigned __int64)v93 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v92 - 1) = v93;
            }
          }
          else
          {
            v92 = 0;
          }
          v94 = (char *)v92 + 56 * (v90 / 56);
          v95 = v94 + 56;
          v208 = (void **)&v189;
          v209 = v92;
          v210 = v89;
          v211 = (GUID *)(v94 + 56);
          v212 = (__int64)(v94 + 56);
          std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____FILETIME_unsigned___int64_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration___(
            v91,
            (_DWORD)v94,
            v82,
            (unsigned int)&pMemory,
            (__int64)&Context,
            (__int64)v175,
            (__int64)&fPending);
          v96 = *((_QWORD *)&v189 + 1);
          v97 = v92;
          v98 = v189;
          if ( v83 != *((_QWORD *)&v189 + 1) )
          {
            std::_Uninitialized_move__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___(
              v189,
              v83,
              v92);
            v97 = v95;
            v96 = *((_QWORD *)&v189 + 1);
            v98 = v83;
          }
          std::_Uninitialized_move__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___(
            v98,
            v96,
            v97);
          std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_Change_array(
            &v189,
            v92,
            v88,
            v89);
          v73 = v185;
          v8 = v195;
        }
        else
        {
          std::_Default_allocator_traits_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::construct__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____FILETIME_unsigned___int64_const___bool_enum_Windows::Internal::WiFiCloudStore::ProfileGeneration___(
            v190,
            DWORD2(v189),
            v82,
            (unsigned int)&pMemory,
            (__int64)&Context,
            (__int64)v175,
            (__int64)&fPending);
          *((_QWORD *)&v189 + 1) += 56LL;
        }
        if ( v216 > 7 )
          std::wstring::_Deallocate_for_capacity(v84, v214[0]);
        v215 = 0;
        v216 = 7;
        LOWORD(v214[0]) = 0;
        if ( v223 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v223 + 16LL))(v223);
        std::wstring::~wstring(v220);
        v74 = (wil::ActivityThreadWatcher *)((char *)v74 + 64);
      }
      while ( v74 != v73 );
      v12 = v179;
    }
    std::vector<Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfile>>::_Tidy(&v192);
    v63 = (unsigned int *)(*(_QWORD *)v180 + 4LL);
  }
  v99 = (char *)v183[1] - (char *)v183[0];
  v100 = *((_QWORD *)&v189 + 1) - v189;
  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_180052768;
    qword_180052770 = 0;
    byte_180052778 = 0;
    dword_18005277C = 0;
    qword_180052768 = (__int64)&WiFiCloudStoreTelemetry::`vftable';
    CallbackContext = &`WiFiCloudStoreTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_95670f246c18451995f5d42fbee9df36_::_lambda_invoker_cdecl_);
    v101 = (ULONGLONG *)CallbackContext;
    qword_180052770 = (__int64)CallbackContext;
    byte_180052778 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v101[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v101, v101 + 4) )
      EventSetInformation(v101[4], 2, v101[1], *(unsigned __int16 *)v101[1]);
    dword_18005277C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180052768 + 8))(&qword_180052768);
    InitOnceComplete(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &qword_180052768);
  }
  v102 = (_DWORD *)*((_QWORD *)Context + 1);
  if ( *v102 > 5u )
  {
    v177 = v99 >> 6;
    Context = (LPVOID)(0x6DB6DB6DB6DB6DB7LL * (v100 >> 3));
    v233 = (__int64)&v177;
    v234 = 8;
    *(_QWORD *)&v232 = &Context;
    *((_QWORD *)&v232 + 1) = 8;
    v174 = 4;
    tlgWriteTransfer_EventWriteTransfer(v102, byte_180047A19, 0, 0);
  }
  std::_Sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___bool____cdecl____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_const____(
    v183[0],
    v183[1],
    ((char *)v183[1] - (char *)v183[0]) >> 6,
    lesser__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_);
  std::_Sort_unchecked__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___bool____cdecl____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const____WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_const____(
    v189,
    *((_QWORD *)&v189 + 1),
    0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)&v189 + 1) - v189) >> 3),
    lesser__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_);
  FutureIgnoreDateAsStdTime = GetFutureIgnoreDateAsStdTime();
  j = FutureIgnoreDateAsStdTime;
  v228 = 0.0;
  v229 = 0;
  v230 = 0;
  v104 = operator new(0x30u);
  *v104 = v104;
  v104[1] = v104;
  v229 = v104;
  v231 = 0;
  v232 = 0;
  v233 = 7;
  v234 = 8;
  v228 = 1.0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v231,
    16,
    v104);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::GetImpl'::`2'::impl) )
  {
    v105 = (char *)v183[0];
    v106 = (char *)v183[1];
    if ( v183[0] != v183[1] )
    {
      while ( 1 )
      {
        if ( v105[56] )
          goto LABEL_194;
        v107 = v105;
        if ( *((_QWORD *)v105 + 3) > 7u )
          v107 = *(const char **)v105;
        v108 = 0xCBF29CE484222325uLL;
        v109 = 0;
        v110 = 2LL * *((_QWORD *)v105 + 2);
        if ( v110 )
        {
          do
            v108 = 0x100000001B3LL * ((unsigned __int8)v107[v109++] ^ (unsigned __int64)v108);
          while ( v109 < v110 );
        }
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
          &v228,
          &v201,
          v105,
          v108);
        if ( *((_QWORD *)&v201 + 1) )
          goto LABEL_194;
        if ( v230 == 0x555555555555555LL )
          std::_Xlength_error("unordered_map/set too long");
        *(_QWORD *)&ProviderId.Data1 = &v229;
        *(_QWORD *)ProviderId.Data4 = 0;
        v111 = operator new(0x30u);
        v112 = v111;
        *(_QWORD *)ProviderId.Data4 = v111;
        *((_OWORD *)v111 + 1) = 0;
        v111[4] = 0;
        v111[5] = 0;
        v113 = *((_QWORD *)v105 + 2);
        if ( *((_QWORD *)v105 + 3) <= 7u )
          v114 = v105;
        else
          v114 = *(_OWORD **)v105;
        v115 = 0x7FFFFFFFFFFFFFFELL;
        if ( v113 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        if ( v113 > 7 )
        {
          v116 = v113 | 7;
          if ( (v113 | 7) <= 0x7FFFFFFFFFFFFFFELL )
          {
            v115 = 10;
            if ( v116 < 0xA )
              v116 = 10;
          }
          else
          {
            v116 = 0x7FFFFFFFFFFFFFFELL;
          }
          Context = (LPVOID)v116;
          v117 = (void *)std::wstring::_Allocate_for_capacity<0>(v115, &Context);
          v112[2] = v117;
          v112[4] = v113;
          v112[5] = Context;
          memcpy_0(v117, v114, 2 * v113 + 2);
        }
        else
        {
          v111[4] = v113;
          v111[5] = 7;
          *((_OWORD *)v111 + 1) = *v114;
        }
        v118 = v230;
        v119 = v230 + 1;
        if ( v230 + 1 < 0 )
          v120 = (float)(int)(v119 & 1 | (v119 >> 1)) + (float)(int)(v119 & 1 | (v119 >> 1));
        else
          v120 = (float)(int)v119;
        v121 = v234;
        if ( v234 < 0 )
          v122 = (float)(v234 & 1 | (unsigned int)((unsigned __int64)v234 >> 1))
               + (float)(v234 & 1 | (unsigned int)((unsigned __int64)v234 >> 1));
        else
          v122 = (float)(int)v234;
        if ( (float)(v120 / v122) > v228 )
        {
          v123 = o_ceilf_0(v120 / v228);
          v124 = 0;
          if ( v123 >= 9.223372e18 )
          {
            v123 = v123 - 9.223372e18;
            if ( v123 < 9.223372e18 )
              v124 = 0x8000000000000000uLL;
          }
          v125 = v124 + (unsigned int)(int)v123;
          v126 = 8;
          if ( v125 > 8 )
            v126 = v125;
          if ( v121 < v126 )
          {
            if ( v121 >= 0x200 || (v121 *= 8LL, v121 < v126) )
              v121 = v126;
          }
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
            &v228,
            v121);
          v201 = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                              &v228,
                              &v217,
                              v112 + 2,
                              v108);
          v118 = v230;
        }
        *(_QWORD *)ProviderId.Data4 = 0;
        v127 = (_QWORD *)v201;
        v128 = *(_QWORD **)(v201 + 8);
        v230 = v118 + 1;
        *v112 = v201;
        v112[1] = v128;
        *v128 = v112;
        v127[1] = v112;
        v129 = v231;
        v130 = 2 * (v233 & v108);
        v131 = *(_QWORD **)(v231 + 8 * v130);
        if ( v131 == v229 )
          break;
        if ( v131 == v127 )
        {
          *(_QWORD *)(v231 + 8 * v130) = v112;
        }
        else if ( *(_QWORD **)(v231 + 8 * v130 + 8) == v128 )
        {
          goto LABEL_193;
        }
LABEL_194:
        v105 += 64;
        if ( v105 == v106 )
        {
          FutureIgnoreDateAsStdTime = j;
          goto LABEL_196;
        }
      }
      *(_QWORD *)(v231 + 8 * v130) = v112;
LABEL_193:
      *(_QWORD *)(v129 + 8 * v130 + 8) = v112;
      goto LABEL_194;
    }
  }
  else
  {
LABEL_196:
    v105 = (char *)v183[0];
  }
  v132 = v189;
LABEL_198:
  v133 = v187;
  while ( v105 != v183[1] || v132 != *((_QWORD *)&v189 + 1) )
  {
    if ( v132 != *((_QWORD *)&v189 + 1)
      && (v105 == v183[1]
       || !(unsigned __int8)std::operator<<unsigned short>(v105, v132)
       && (!(unsigned __int8)std::operator==<unsigned short>(v105, v132)
        || *((_DWORD *)v105 + 15) <= *(_DWORD *)(v132 + 52))) )
    {
      v134 = wil::filetime::to_int64<unsigned __int64,0>(v132 + 32);
      v177 = v134;
      if ( v105 != v183[1]
        && !(unsigned __int8)lesser__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_(
                               v132,
                               v105) )
      {
        v135 = (void *)wil::filetime::to_int64<unsigned __int64,0>(v105 + 32);
        Context = v135;
        v136 = (void *)FileTimeToStdTime((const unsigned __int64 *)&Context);
        pMemory = v136;
        std::wstring::wstring(v225, v105);
        if ( v105[56]
          && ((v137 = (_BYTE *)(v132 + 48), !*(_BYTE *)(v132 + 48))
            ? (CurrentUserToken = WlanSyncTaskCDSToWlan::GetCurrentUserToken(v196),
               DoesSidAllowUpdateWithProfileGuid = WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(
                                                     CurrentUserToken,
                                                     v187,
                                                     (const struct _GUID *)(v105 + 40),
                                                     a7))
            : (v138 = WlanSyncTaskCDSToWlan::GetCurrentUserToken(v196),
               DoesSidAllowUpdateWithProfileGuid = WlanSyncTaskCommon::DoesSidAllowDeletion(
                                                     v138,
                                                     v187,
                                                     (const struct _GUID *)(v105 + 40))),
              DoesSidAllowUpdateWithProfileGuid) )
        {
          v141 = 1;
        }
        else
        {
          v141 = 0;
          v137 = (_BYTE *)(v132 + 48);
        }
        if ( !v105[56] )
        {
          v177 = std::wstring::c_str(v105);
          WiFiCloudStoreTelemetry::ProfileNotEligibleForSync<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
            &v177,
            v105 + 60);
          goto LABEL_259;
        }
        if ( !v141 )
        {
          fPending = 4 - (*(_BYTE *)(v132 + 48) != 0);
          v177 = std::wstring::c_str(v105);
          WiFiCloudStoreTelemetry::SidDoesNotAllowAction<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,enum WiFiSyncAction>(
            &v177,
            v105 + 60,
            &fPending);
          goto LABEL_259;
        }
        v175[0] = 0;
        if ( *(_QWORD *)(v132 + 40) > j )
        {
          v177 = std::wstring::c_str(v132);
          WiFiCloudStoreTelemetry::CloudProfileFromFuture<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,unsigned __int64 const &,unsigned __int64 const &>(
            &v177,
            v132 + 52,
            &pMemory,
            v132 + 40);
          goto LABEL_228;
        }
        v142 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                           &v228,
                           &v201,
                           v132);
        if ( (_QWORD *)*v142 != v229 )
        {
          v177 = std::wstring::c_str(v132);
          WiFiCloudStoreTelemetry::HigherGenerationWillExistLocally<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
            &v177,
            v132 + 52);
          v137 = (_BYTE *)(v132 + 48);
          goto LABEL_228;
        }
        v137 = (_BYTE *)(v132 + 48);
        if ( *(_BYTE *)(v132 + 48) )
        {
          if ( (unsigned __int64)v136 >= *(_QWORD *)(v132 + 40) )
          {
            if ( (unsigned __int64)v136 <= *(_QWORD *)(v132 + 40) )
              goto LABEL_227;
LABEL_238:
            if ( !(unsigned __int8)WlanSyncTaskCDSToWlan::IsKnownErrorCondition(
                                     (unsigned int)v206,
                                     (_DWORD)v105,
                                     (_DWORD)v136,
                                     *(_QWORD *)(v132 + 40),
                                     j,
                                     (__int64)v187,
                                     (__int64)(v105 + 40),
                                     *((_DWORD *)v105 + 15)) )
            {
              v150 = (const char *)std::wstring::c_str(v132);
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x1F3,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)0x8000FFFFLL,
                (int)"Profile name: %ws, Local version: %llu, Cloud version: %llu, Local modified time: %llu, Cloud modified time: %llu",
                v150);
            }
            goto LABEL_228;
          }
          v149 = 3;
LABEL_236:
          fPending = v149;
          *(_QWORD *)v180 = std::wstring::c_str(v105);
          WiFiCloudStoreTelemetry::NecessaryActionIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,enum WiFiSyncAction>(
            (unsigned int)v180,
            (_DWORD)v105 + 60,
            (unsigned int)&pMemory,
            v132 + 40,
            (__int64)&Context,
            (__int64)&v177,
            (__int64)&fPending);
          fPending = 2 - (*v137 != 0);
          v143 = v191;
          std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<std::wstring,_FILETIME &,enum Windows::Internal::WiFiCloudStore::ProfileModificationType,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
            (_DWORD)v191,
            v132,
            v132 + 32,
            (unsigned int)&fPending,
            v132 + 52);
          v144 = *v137 != 0;
        }
        else
        {
          if ( (unsigned __int64)v135 < v134 )
          {
            v149 = 4;
            goto LABEL_236;
          }
          if ( (unsigned __int64)v135 > v134 )
            goto LABEL_238;
LABEL_227:
          v177 = std::wstring::c_str(v105);
          WiFiCloudStoreTelemetry::LocalProfileUpToDate<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,unsigned __int64 const &,unsigned __int64 const &>(
            &v177,
            v105 + 60,
            &pMemory,
            &Context);
LABEL_228:
          v143 = v191;
          v144 = v175[0];
        }
        if ( !*v137 )
        {
          v145 = c_wiFiCloudStoreDataReferenceDefaultCollectionName;
          v146 = Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(&v208, v105);
          v147 = std::wstring::c_str(v146);
          wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(v220, v147, v145);
          std::wstring::~wstring(&v208);
          wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(v195, &v197, v220, 0);
          Context = v199;
          v148 = v200 && v199;
          if ( v200 && !v148 )
          {
            v177 = std::wstring::c_str(v105);
            WiFiCloudStoreTelemetry::CloudCostNotPresent<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
              &v177,
              v105 + 60);
            goto LABEL_257;
          }
          if ( (unsigned __int64)v199 > j )
          {
            v177 = std::wstring::c_str(v132);
            WiFiCloudStoreTelemetry::CloudCostFromFuture<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,unsigned __int64 const &>(
              &v177,
              v132 + 52,
              &Context);
            goto LABEL_257;
          }
          memset_0(&v226, 0, 0x210u);
          v226 = *v187;
          v151 = (const unsigned __int16 *)std::wstring::c_str(v105);
          v152 = StringCchCopyW(v227, 0x100u, v151);
          if ( v152 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x210,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
              (const char *)(unsigned int)v152,
              v174);
          v185 = 0;
          v153 = DusmQueryUserCost(&v226, &v185);
          if ( v153 )
          {
            if ( v153 == 2 )
            {
              v154 = (__int64)(v105 + 60);
              v155 = v105;
              if ( !v148 )
                goto LABEL_254;
              fPending = 0;
              v177 = std::wstring::c_str(v105);
              WiFiCloudStoreTelemetry::LocalCostUpToDate<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,enum _DUSM_CONNECTION_COST>(
                &v177,
                v105 + 60,
                &fPending);
            }
            else
            {
              wil::details::in1diag3::Log_Win32(
                retaddr,
                (void *)0x25B,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)v153,
                v174);
            }
          }
          else
          {
            v154 = (__int64)(v105 + 60);
            v155 = v105;
            if ( v148 )
            {
              fPending = 12;
              v180[0] = 0;
              v179 = 0;
              v177 = std::wstring::c_str(v105);
              WiFiCloudStoreTelemetry::NecessaryActionIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,unsigned __int64 const &,int,unsigned __int64 &,enum WiFiSyncAction>(
                (unsigned int)&v177,
                (_DWORD)v105 + 60,
                (unsigned int)&v179,
                (unsigned int)&Context,
                (__int64)v180,
                (__int64)&v198,
                (__int64)&fPending);
              fPending = 8;
              std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<std::wstring,enum Windows::Internal::WiFiCloudStore::ProfileModificationType,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
                v143,
                v105,
                &fPending,
                v105 + 60);
            }
            else
            {
              if ( (unsigned int)v185 == v197 )
              {
                v177 = std::wstring::c_str(v105);
                WiFiCloudStoreTelemetry::LocalCostUpToDate<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,unsigned long &>(
                  &v177,
                  v105 + 60,
                  &v185);
                goto LABEL_257;
              }
LABEL_254:
              fPending = 10;
              v180[0] = 0;
              v179 = 0;
              v177 = std::wstring::c_str(v155);
              WiFiCloudStoreTelemetry::NecessaryActionIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,unsigned __int64 const &,int,unsigned __int64 &,enum WiFiSyncAction>(
                (unsigned int)&v177,
                v154,
                (unsigned int)&v179,
                (unsigned int)&Context,
                (__int64)v180,
                (__int64)&v198,
                (__int64)&fPending);
              fPending = 4;
              v177 = v198;
              std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<std::wstring,_FILETIME,enum Windows::Internal::WiFiCloudStore::ProfileModificationType,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
                (_DWORD)v143,
                (_DWORD)v105,
                (unsigned int)&v177,
                (unsigned int)&fPending,
                v154);
            }
          }
LABEL_257:
          wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>::~cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>(&v197);
          Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v220);
        }
        if ( !v144 )
LABEL_259:
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
            &v228,
            v202,
            v225);
        v105 += 64;
        v132 += 56;
        std::wstring::~wstring(v225);
        FutureIgnoreDateAsStdTime = j;
        goto LABEL_198;
      }
      if ( *(_BYTE *)(v132 + 48) )
      {
        fPending = 0;
        v180[0] = 0;
        v177 = std::wstring::c_str(v132);
        WiFiCloudStoreTelemetry::LocalProfileUpToDate<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,int>(
          &v177,
          v132 + 52,
          v180,
          &fPending);
        v132 += 56;
      }
      else if ( *(_QWORD *)(v132 + 40) <= FutureIgnoreDateAsStdTime )
      {
        v156 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                           &v228,
                           &ProviderId,
                           v132);
        if ( (_QWORD *)*v156 == v229 )
        {
          fPending = 4;
          v180[0] = 0;
          v179 = 0;
          Context = (LPVOID)std::wstring::c_str(v132);
          WiFiCloudStoreTelemetry::NecessaryActionIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,unsigned __int64 const &,int,unsigned __int64 const &,enum WiFiSyncAction>(
            (unsigned int)&Context,
            v132 + 52,
            (unsigned int)&v179,
            v132 + 40,
            (__int64)v180,
            (__int64)&v177,
            (__int64)&fPending);
          fPending = 2;
          v157 = std::wstring::wstring(&v208, v132);
          v158 = (int)v191;
          std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<std::wstring,_FILETIME &,enum Windows::Internal::WiFiCloudStore::ProfileModificationType,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
            (_DWORD)v191,
            v157,
            v132 + 32,
            (unsigned int)&fPending,
            v132 + 52);
          std::wstring::~wstring(&v208);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
            &v228,
            v214,
            v132);
          v159 = c_wiFiCloudStoreDataReferenceDefaultCollectionName;
          v160 = Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(&v208, v132);
          v161 = std::wstring::c_str(v160);
          wil::make_cloud_store_data_reference<Windows::Data::WiFi::WiFiProfileCost>(v220, v161, v159);
          std::wstring::~wstring(&v208);
          wil::cloud_store::load<Windows::Data::WiFi::WiFiProfileCost>(v195, &v197, v220, 0);
          if ( v200 )
          {
            v177 = std::wstring::c_str(v132);
            WiFiCloudStoreTelemetry::CloudCostNotPresent<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
              &v177,
              v132 + 52);
          }
          else
          {
            fPending = 10;
            v180[0] = 0;
            v177 = (__int64)v199;
            v179 = 0;
            Context = (LPVOID)std::wstring::c_str(v132);
            WiFiCloudStoreTelemetry::NecessaryActionIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,unsigned __int64,int,unsigned __int64 &,enum WiFiSyncAction>(
              (unsigned int)&Context,
              v132 + 52,
              (unsigned int)&v179,
              (unsigned int)&v177,
              (__int64)v180,
              (__int64)&v198,
              (__int64)&fPending);
            fPending = 4;
            v177 = v198;
            std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::emplace_back<std::wstring,_FILETIME,enum Windows::Internal::WiFiCloudStore::ProfileModificationType,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
              v158,
              v132,
              (unsigned int)&v177,
              (unsigned int)&fPending,
              v132 + 52);
          }
          wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>::~cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>(&v197);
          Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(v220);
          v132 += 56;
        }
        else
        {
          v177 = std::wstring::c_str(v132);
          WiFiCloudStoreTelemetry::HigherGenerationWillExistLocally<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &>(
            &v177,
            v132 + 52);
          v132 += 56;
        }
      }
      else
      {
        fPending = 0;
        v177 = std::wstring::c_str(v132);
        WiFiCloudStoreTelemetry::CloudProfileFromFuture<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration &,int,unsigned __int64 const &>(
          &v177,
          v132 + 52,
          &fPending,
          v132 + 40);
        v132 += 56;
      }
      goto LABEL_198;
    }
    v162 = *((unsigned int *)v105 + 9);
    v163 = *((unsigned int *)v105 + 8);
    v164 = WlanSyncTaskCDSToWlan::GetCurrentUserToken(v196);
    v165 = WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(v164, v133, (const struct _GUID *)(v105 + 40), a7);
    v166 = v165;
    if ( v105[56] && v165 )
    {
      v167 = (v162 << 32) + v163;
      FutureIgnoreDateAsStdTime = j;
      if ( !(unsigned __int8)WlanSyncTaskCDSToWlan::IsKnownErrorCondition(
                               (unsigned int)v206,
                               (_DWORD)v105,
                               (v167 - 116444736000000000LL) / 10000000,
                               0,
                               j,
                               (__int64)v133,
                               (__int64)(v105 + 40),
                               *((_DWORD *)v105 + 15)) )
      {
        if ( *((_QWORD *)v105 + 3) <= 7u )
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x134,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Profile name: %ws, Local version: %llu, Local modified time: %llu",
            v105,
            (v167 - 116444736000000000LL) / 10000000,
            v167);
        else
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x134,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Profile name: %ws, Local version: %llu, Local modified time: %llu",
            *(const char **)v105,
            (v167 - 116444736000000000LL) / 10000000,
            v167);
      }
    }
    else
    {
      if ( *((_QWORD *)v105 + 3) <= 7u )
        v168 = (__int64)v105;
      else
        v168 = *(_QWORD *)v105;
      Context = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
        && fPending )
      {
        Context = &qword_180052768;
        qword_180052770 = 0;
        byte_180052778 = 0;
        dword_18005277C = 0;
        qword_180052768 = (__int64)&WiFiCloudStoreTelemetry::`vftable';
        CallbackContext = &`WiFiCloudStoreTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_95670f246c18451995f5d42fbee9df36_::_lambda_invoker_cdecl_);
        v169 = (ULONGLONG *)CallbackContext;
        qword_180052770 = (__int64)CallbackContext;
        byte_180052778 = 1;
        v217 = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
        if ( *((_QWORD *)CallbackContext + 4) )
          __fastfail(5u);
        *((_QWORD *)CallbackContext + 5) = 0;
        v169[6] = 0;
        if ( !EventRegister(&v217, tlgEnableCallback, v169, v169 + 4) )
          EventSetInformation(v169[4], 2, v169[1], *(unsigned __int16 *)v169[1]);
        dword_18005277C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_180052768 + 8))(&qword_180052768);
        InitOnceComplete(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &qword_180052768);
      }
      if ( **((_DWORD **)Context + 1) > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)Context + 1), 0) )
      {
        v175[0] = v166;
        v181[0] = v105[56];
        fPending = *((_DWORD *)v105 + 15);
        v177 = v168;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
          v170,
          (unsigned int)byte_1800479B5,
          v170,
          v171,
          (__int64)&v177,
          (__int64)&fPending,
          (__int64)v181,
          (__int64)v175);
      }
      FutureIgnoreDateAsStdTime = j;
    }
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::insert(
      &v228,
      &v192,
      v105);
    v105 += 64;
  }
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v228);
  std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___::_vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameWithTimestampAndVersion___(&v189);
  std::unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>::~unique_ptr<WCM_WLAN_PROFILE_INFO_LIST,WlanWcmProfileListFreeMemoryHelper>(&v194);
  std::vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___::_vector__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo_std::allocator__WlanSyncTaskCDSToWlan::ComputeNeededChanges_::_2_::ProfileNameFromWlanInfo___(v183);
  std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::~vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>(v206);
  return v191;
}

```

## disassembly

```asm
0x1800211b0  push    rbp
0x1800211b2  push    rbx
0x1800211b3  push    rsi
0x1800211b4  push    rdi
0x1800211b5  push    r12
0x1800211b7  push    r13
0x1800211b9  push    r14
0x1800211bb  push    r15
0x1800211bd  lea     rbp, [rsp-3F8h]
0x1800211c5  sub     rsp, 4F8h
0x1800211cc  movaps  [rsp+530h+var_50], xmm6
0x1800211d4  mov     rax, cs:__security_cookie
0x1800211db  xor     rax, rsp
0x1800211de  mov     [rbp+430h+var_60], rax
0x1800211e5  mov     rdi, r9
0x1800211e8  mov     [rbp+430h+var_490], r9
0x1800211ec  mov     r12, r8
0x1800211ef  mov     [rbp+430h+var_430], r8
0x1800211f3  mov     rbx, rdx
0x1800211f6  mov     [rbp+430h+var_458], rdx
0x1800211fa  mov     [rbp+430h+var_428], rcx
0x1800211fe  mov     [rbp+430h+var_3A8], rdx
0x180021205  mov     r14, [rbp+430h+arg_20]
0x18002120c  mov     [rbp+430h+var_480], r14
0x180021210  xor     r15d, r15d
0x180021213  mov     [rbp+430h+var_478], r15d
0x180021217  mov     rdx, r14
0x18002121a  lea     rcx, [rbp+430h+var_3C0]
0x18002121e  call    ?GetSyncNeededProfilesFromRegistry@WiFiCloudStore@Internal@Windows@@YA?AV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEBU_GUID@@@Z; Windows::Internal::WiFiCloudStore::GetSyncNeededProfilesFromRegistry(_GUID const &)
0x180021223  nop
0x180021224  mov     [rbx], r15
0x180021227  mov     [rbx+8], r15
0x18002122b  mov     [rbx+10h], r15
0x18002122f  mov     esi, 1
0x180021234  mov     [rsp+530h+var_4C8], esi
0x180021238  mov     [rbp+430h+var_478], esi
0x18002123b  xorps   xmm0, xmm0
0x18002123e  movdqu  xmmword ptr [rbp+430h+var_4A8], xmm0
0x180021243  mov     [rbp+430h+var_498], r15
0x180021247  mov     [rbp+430h+var_438], r15
0x18002124b  lea     rax, [rbp+430h+var_438]
0x18002124f  mov     qword ptr [rbp+430h+var_450], rax
0x180021253  mov     qword ptr [rbp+430h+var_450+8], r15
0x180021257  mov     byte ptr [rbp+430h+var_440], sil
0x18002125b  lea     r8, [rbp+430h+var_450+8]
0x18002125f  xor     edx, edx
0x180021261  mov     rcx, r14
0x180021264  call    cs:__imp_?WlanWcmGetProfileList@@YAKPEBU_GUID@@PEAXPEAPEAUWCM_WLAN_PROFILE_INFO_LIST@@@Z; WlanWcmGetProfileList(_GUID const *,void *,WCM_WLAN_PROFILE_INFO_LIST * *)
0x18002126a  mov     rcx, [rbp+438h]; this
0x180021271  test    eax, eax
0x180021273  jnz     loc_180023141
0x180021279  cmp     byte ptr [rbp+430h+var_440], al
0x18002127c  jz      short loc_1800212CE
0x18002127e  mov     rcx, qword ptr [rbp+430h+var_450]
0x180021282  mov     rdi, [rcx]
0x180021285  mov     rax, qword ptr [rbp+430h+var_450+8]
0x180021289  mov     [rcx], rax
0x18002128c  test    rdi, rdi
0x18002128f  jz      short loc_1800212CA
0x180021291  mov     ebx, r15d
0x180021294  cmp     [rdi], r15d
0x180021297  jbe     short loc_1800212C1
0x180021299  nop     dword ptr [rax+00000000h]
0x1800212a0  mov     eax, ebx
0x1800212a2  inc     rax
0x1800212a5  imul    rax, 268h
0x1800212ac  mov     rcx, [rax+rdi]; pMemory
0x1800212b0  test    rcx, rcx
0x1800212b3  jz      short loc_1800212BB
0x1800212b5  call    cs:__imp_WlanFreeMemory
0x1800212bb  inc     ebx
0x1800212bd  cmp     ebx, [rdi]
0x1800212bf  jb      short loc_1800212A0
0x1800212c1  mov     rcx, rdi; pMemory
0x1800212c4  call    cs:__imp_WlanFreeMemory
0x1800212ca  mov     rdi, [rbp+430h+var_490]
0x1800212ce  mov     r13d, r15d
0x1800212d1  mov     [rsp+530h+fPending], r15d
0x1800212d6  mov     rax, [rbp+430h+var_438]
0x1800212da  cmp     [rax], r15d
0x1800212dd  jbe     loc_18002190D
0x1800212e3  nop     dword ptr [rax+00h]
0x1800212e7  nop     word ptr [rax+rax+00000000h]
0x1800212f0  mov     ecx, r13d
0x1800212f3  imul    rbx, rcx, 268h
0x1800212fa  lea     r8, [rax+18h]
0x1800212fe  add     r8, rbx
0x180021301  mov     [rsp+530h+Context], r8
0x180021306  lea     r12, [rax+8]
0x18002130a  add     r12, rbx
0x18002130d  mov     edx, [rbx+rax+258h]
0x180021314  sub     edx, 9
0x180021317  jz      short loc_18002132B
0x180021319  cmp     edx, 1
0x18002131c  jz      short loc_180021323
0x18002131e  mov     r9d, r15d
0x180021321  jmp     short loc_180021331
0x180021323  mov     r9d, 2
0x180021329  jmp     short loc_180021331
0x18002132b  mov     r9d, 1
0x180021331  mov     dword ptr [rbp+430h+var_4B0], r9d
0x180021335  lea     rdx, aProfileNameWsG_0; "Profile name: %ws, Generation: %d"
0x18002133c  mov     rcx, rdi; this
0x18002133f  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180021344  mov     rdx, [rbp+430h+var_438]
0x180021348  add     rdx, 8
0x18002134c  add     rdx, rbx; struct WCM_WLAN_PROFILE_INFO *
0x18002134f  mov     rcx, r14; struct _GUID *
0x180021352  call    ?IsProfileEligibleForCDSSync@WlanSyncTaskCommon@@SA_NAEBU_GUID@@AEBUWCM_WLAN_PROFILE_INFO@@@Z; WlanSyncTaskCommon::IsProfileEligibleForCDSSync(_GUID const &,WCM_WLAN_PROFILE_INFO const &)
0x180021357  test    al, al
0x180021359  jz      loc_180021766
0x18002135f  mov     [rbp+430h+pMemory], r15
0x180021363  mov     [rsp+530h+var_4C0], r15d
0x180021368  lea     rax, [rbp+430h+pMemory]
0x18002136c  mov     qword ptr [rbp+430h+var_450], rax
0x180021370  mov     qword ptr [rbp+430h+var_450+8], r15
0x180021374  mov     byte ptr [rbp+430h+var_440], 1
0x180021378  lea     rax, [rbp+430h+var_450+8]
0x18002137c  mov     [rsp+530h+var_508], rax
0x180021381  lea     rax, [rsp+530h+var_4C0]
0x180021386  mov     qword ptr [rsp+530h+var_510], rax; unsigned int
0x18002138b  lea     r9, aLastmodified; "LastModified"
0x180021392  xor     r8d, r8d
0x180021395  mov     rdx, r12
0x180021398  mov     rcx, r14
0x18002139b  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x1800213a1  mov     rcx, [rbp+438h]; this
0x1800213a8  test    eax, eax
0x1800213aa  jnz     loc_180023188
0x1800213b0  cmp     byte ptr [rbp+430h+var_440], al
0x1800213b3  jz      short loc_1800213CE
0x1800213b5  mov     rdx, qword ptr [rbp+430h+var_450]
0x1800213b9  mov     rcx, [rdx]; pMemory
0x1800213bc  mov     rax, qword ptr [rbp+430h+var_450+8]
0x1800213c0  mov     [rdx], rax
0x1800213c3  test    rcx, rcx
0x1800213c6  jz      short loc_1800213CE
0x1800213c8  call    cs:__imp_WlanFreeMemory
0x1800213ce  cmp     [rsp+530h+var_4C0], 8
0x1800213d3  jnz     loc_180023162
0x1800213d9  mov     [rsp+530h+var_4E0], 1
0x1800213de  mov     r14, [rbp+430h+pMemory]
0x1800213e2  mov     rdi, [rbp+430h+var_4A8+8]
0x1800213e6  mov     rcx, [rbp+430h+var_498]
0x1800213ea  cmp     rdi, rcx
0x1800213ed  jz      short loc_180021421
0x1800213ef  lea     rax, [rbp+430h+var_4B0]
0x1800213f3  mov     [rsp+530h+var_500], rax
0x1800213f8  lea     rax, [rsp+530h+var_4E0]
0x1800213fd  mov     [rsp+530h+var_508], rax
0x180021402  mov     qword ptr [rsp+530h+var_510], r12
0x180021407  mov     r9, r14
0x18002140a  lea     r8, [rsp+530h+Context]
0x18002140f  mov     rdx, rdi
0x180021412  call    std___Default_allocator_traits_std__allocator__WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo_____construct__WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo_unsigned_short_const______FILETIME____GUID_const___bool_enum_Windows__Internal__WiFiCloudStore__ProfileGeneration_const___
0x180021417  add     [rbp+430h+var_4A8+8], 40h ; '@'
0x18002141c  jmp     loc_18002174A
0x180021421  mov     rax, rdi
0x180021424  mov     rdx, [rbp+430h+var_4A8]
0x180021428  sub     rax, rdx
0x18002142b  sar     rax, 6
0x18002142f  mov     r9, 3FFFFFFFFFFFFFFh
0x180021439  cmp     rax, r9
0x18002143c  jz      loc_18002315C
0x180021442  mov     rsi, rdi
0x180021445  sub     rsi, rdx
0x180021448  lea     r8, [rax+1]
0x18002144c  mov     [rsp+530h+var_4D8], r8
0x180021451  sub     rcx, rdx
0x180021454  sar     rcx, 6
0x180021458  mov     rdx, rcx
0x18002145b  shr     rdx, 1
0x18002145e  mov     rax, r9
0x180021461  sub     rax, rdx
0x180021464  cmp     rcx, rax
0x180021467  jbe     short loc_18002147C
0x180021469  mov     rbx, r9
0x18002146c  mov     rcx, 0FFFFFFFFFFFFFFE7h
0x180021473  mov     r13, 0FFFFFFFFFFFFFFC0h
0x18002147a  jmp     short loc_1800214B5
0x18002147c  lea     rax, [rdx+rcx]
0x180021480  mov     rbx, r8
0x180021483  cmp     rax, r8
0x180021486  cmovnb  rbx, rax
0x18002148a  cmp     rbx, r9
0x18002148d  ja      loc_180023156
0x180021493  mov     r13, rbx
0x180021496  shl     r13, 6
0x18002149a  test    r13, r13
0x18002149d  jz      short loc_1800214DC
0x18002149f  cmp     r13, 1000h
0x1800214a6  jb      short loc_1800214D1
0x1800214a8  lea     rcx, [r13+27h]; Size
0x1800214ac  cmp     rcx, r13
0x1800214af  jbe     loc_180023156
0x1800214b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800214ba  test    rax, rax
0x1800214bd  jz      loc_180021A15
0x1800214c3  lea     r15, [rax+27h]
0x1800214c7  and     r15, 0FFFFFFFFFFFFFFE0h
0x1800214cb  mov     [r15-8], rax
0x1800214cf  jmp     short loc_1800214DC
0x1800214d1  mov     rcx, r13; Size
0x1800214d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800214d9  mov     r15, rax
0x1800214dc  and     rsi, 0FFFFFFFFFFFFFFC0h
0x1800214e0  lea     rdx, [rsi+r15]
0x1800214e4  lea     rsi, [rdx+40h]
0x1800214e8  lea     rax, [rbp+430h+var_4A8]
0x1800214ec  mov     [rbp+430h+var_3A0], rax
0x1800214f3  mov     [rbp+430h+var_398], r15
0x1800214fa  mov     [rbp+430h+var_390], rbx
0x180021501  mov     [rbp+430h+var_388], rsi
0x180021508  mov     [rbp+430h+var_380], rsi
0x18002150f  lea     rax, [rbp+430h+var_4B0]
0x180021513  mov     [rsp+530h+var_500], rax
0x180021518  lea     rax, [rsp+530h+var_4E0]
0x18002151d  mov     [rsp+530h+var_508], rax
0x180021522  mov     qword ptr [rsp+530h+var_510], r12
0x180021527  mov     r9, r14
0x18002152a  lea     r8, [rsp+530h+Context]
0x18002152f  call    std___Default_allocator_traits_std__allocator__WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo_____construct__WlanSyncTaskCDSToWlan__ComputeNeededChanges____2___ProfileNameFromWlanInfo_unsigned_short_const______FILETIME____GUID_const___bool_enum_Windows__Internal__WiFiCloudStore__ProfileGeneration_const___
0x180021534  mov     r14, [rbp+430h+var_4A8+8]
0x180021538  mov     rcx, r15
0x18002153b  mov     rbx, [rbp+430h+var_4A8]
0x18002153f  xor     r12d, r12d
0x180021542  cmp     rdi, r14
0x180021545  jnz     short loc_1800215AB
0x180021547  cmp     rbx, r14
0x18002154a  jz      loc_18002167E
0x180021550  xorps   xmm0, xmm0
0x180021553  movups  xmmword ptr [rcx], xmm0
0x180021556  mov     [rcx+10h], r12
0x18002155a  mov     [rcx+18h], r12
0x18002155e  movups  xmm0, xmmword ptr [rbx]
0x180021561  movups  xmmword ptr [rcx], xmm0
0x180021564  movups  xmm1, xmmword ptr [rbx+10h]
0x180021568  movups  xmmword ptr [rcx+10h], xmm1
0x18002156c  mov     [rbx+10h], r12
0x180021570  mov     qword ptr [rbx+18h], 7
0x180021578  mov     [rbx], r12w
0x18002157c  mov     rax, [rbx+20h]
0x180021580  mov     [rcx+20h], rax
0x180021584  movups  xmm0, xmmword ptr [rbx+28h]
0x180021588  movups  xmmword ptr [rcx+28h], xmm0
0x18002158c  movzx   eax, byte ptr [rbx+38h]
0x180021590  mov     [rcx+38h], al
0x180021593  mov     eax, [rbx+3Ch]
0x180021596  mov     [rcx+3Ch], eax
0x180021599  lea     rcx, [rcx+40h]
0x18002159d  add     rbx, 40h ; '@'
0x1800215a1  cmp     rbx, r14
0x1800215a4  jnz     short loc_180021550
0x1800215a6  jmp     loc_180021676
0x1800215ab  cmp     rbx, rdi
0x1800215ae  jz      short loc_18002160E
0x1800215b0  xorps   xmm0, xmm0
0x1800215b3  movups  xmmword ptr [rcx], xmm0
0x1800215b6  mov     [rcx+10h], r12
0x1800215ba  mov     [rcx+18h], r12
0x1800215be  movups  xmm0, xmmword ptr [rbx]
0x1800215c1  movups  xmmword ptr [rcx], xmm0
0x1800215c4  movups  xmm1, xmmword ptr [rbx+10h]
0x1800215c8  movups  xmmword ptr [rcx+10h], xmm1
0x1800215cc  mov     [rbx+10h], r12
0x1800215d0  mov     qword ptr [rbx+18h], 7
0x1800215d8  mov     [rbx], r12w
0x1800215dc  mov     rax, [rbx+20h]
0x1800215e0  mov     [rcx+20h], rax
0x1800215e4  movups  xmm0, xmmword ptr [rbx+28h]
0x1800215e8  movups  xmmword ptr [rcx+28h], xmm0
0x1800215ec  movzx   eax, byte ptr [rbx+38h]
0x1800215f0  mov     [rcx+38h], al
0x1800215f3  mov     eax, [rbx+3Ch]
0x1800215f6  mov     [rcx+3Ch], eax
0x1800215f9  lea     rcx, [rcx+40h]
0x1800215fd  add     rbx, 40h ; '@'
0x180021601  cmp     rbx, rdi
0x180021604  jnz     short loc_1800215B0
0x180021606  mov     r14, [rbp+430h+var_4A8+8]
0x18002160a  mov     rbx, [rbp+430h+var_4A8]
0x18002160e  cmp     rdi, r14
0x180021611  jz      short loc_18002167E
0x180021613  nop     dword ptr [rax+00h]
0x180021617  nop     word ptr [rax+rax+00000000h]
0x180021620  xorps   xmm0, xmm0
0x180021623  movups  xmmword ptr [rsi], xmm0
0x180021626  mov     [rsi+10h], r12
0x18002162a  mov     [rsi+18h], r12
0x18002162e  movups  xmm0, xmmword ptr [rdi]
0x180021631  movups  xmmword ptr [rsi], xmm0
0x180021634  movups  xmm1, xmmword ptr [rdi+10h]
0x180021638  movups  xmmword ptr [rsi+10h], xmm1
0x18002163c  mov     [rdi+10h], r12
0x180021640  mov     qword ptr [rdi+18h], 7
0x180021648  mov     [rdi], r12w
0x18002164c  mov     rax, [rdi+20h]
0x180021650  mov     [rsi+20h], rax
0x180021654  movups  xmm0, xmmword ptr [rdi+28h]
0x180021658  movups  xmmword ptr [rsi+28h], xmm0
  ... truncated ...
```
