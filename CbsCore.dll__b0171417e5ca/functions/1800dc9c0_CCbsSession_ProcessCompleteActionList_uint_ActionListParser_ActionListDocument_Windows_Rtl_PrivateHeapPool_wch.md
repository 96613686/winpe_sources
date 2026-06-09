# CCbsSession::ProcessCompleteActionList(uint,ActionListParser::ActionListDocument *,Windows::Rtl::PrivateHeapPool &,wchar_t const *,bool)

- ea: `0x1800dc9c0`
- end: `0x1800e0ef1`
- name: `?ProcessCompleteActionList@CCbsSession@@AEAAJIPEAUActionListDocument@ActionListParser@@AEAVPrivateHeapPool@Rtl@Windows@@PEB_W_N@Z`
- size: `17713`
- prototype: `__int64 __usercall@<rax>(CCbsSession *__hidden this@<rcx>, unsigned int@<edx>, struct ActionListParser::ActionListDocument *@<r8>, struct Windows::Rtl::PrivateHeapPool *@<r9>, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `89`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801cb8a0`

## callees

- `0x18000e780`
- `0x180010b60`
- `0x180010cc0`
- `0x180011a14`
- `0x180012fe4`
- `0x180013018`
- `0x1800130e0`
- `0x180013250`
- `0x1800132a4`
- `0x1800133a4`
- `0x1800138b8`
- `0x180015420`
- `0x1800158d0`
- `0x180018124`
- `0x18001837c`
- `0x1800194bc`
- `0x180019c10`
- `0x180023ca8`
- `0x18002573c`
- `0x1800261e0`
- `0x180028e24`
- `0x18002a2bc`
- `0x18002a448`
- `0x18002f04c`
- `0x1800337fc`
- `0x180042448`
- `0x180043990`
- `0x180043a48`
- `0x180043adc`
- `0x180045c24`
- `0x180048edc`
- `0x18004a6d8`
- `0x18004b1b8`
- `0x180052cb4`
- `0x1800532d4`
- `0x180057c28`
- `0x180059a00`
- `0x18005aa38`
- `0x18005ec58`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a7340`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800be2e0`
- `0x1800c0054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ddeb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800de13b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ddeb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800de13b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800de119`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800de119`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800dded6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800dded6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfcfd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de711`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de72f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de711`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de72f`

## string_xrefs

- `0x1800dfc78`: `Failed to move file from: {} to {}`
- `0x1800dfd30`: `Failed to move file from: {} to {}`
- `0x1800de8bb`: `update.mum`
- `0x1800dcb71`: `Failed to create private session store.`
- `0x1800dd220`: `Failed adding payload path source`
- `0x1800dd2b9`: `Failed adding payload path source`
- `0x1800df451`: `Failed adding payload path source`
- `0x1800dfb21`: `Failed adding payload path source`
- `0x1800e00ec`: `Failed adding payload path source`
- `0x1800e0089`: `Failed to create sandbox.`
- `0x1800df729`: `Failed to setup the environment for cimbased update`
- `0x1800df84b`: `Failed to get staging root directory path for payload cims catalog.`
- `0x1800dffd5`: `Failed to get Staging directory path for unmanifested files.`
- `0x1800df536`: `Failed to clean staging directory {} for unmanifested files.`
- `0x1800dff65`: `Failed to create staging directory {} for unmanifested files.`
- `0x1800df939`: `Failed to get staging root directory path for payload Cims.`
- `0x1800df61d`: `Failed to create staging directory {} for cim payload.`
- `0x1800df8cf`: `Failed to create staging directory {} for cim payload.`
- `0x1800de2c3`: `windows\system32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\microsoft-windows-cimcatalog.cat`
- `0x1800de2e5`: `Extracting completed.`
- `0x1800dcc20`: `ActionList: No feature or package to install or remove in actionList, this is not expected.`
- `0x1800dd1b6`: `Scheduling installation of package: {} after reboot`
- `0x1800dd491`: `Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first`
- `0x1800ddd13`: `UpdateReserveManager available; checking if reserves should be used...`
- `0x1800ddd6b`: `The current quality update is not using the reserves`
- `0x1800dec9e`: `Scheduling installation of packages after reboot`
- `0x1800e055b`: `Failed adding payload path source: {}`
- `0x1800deda9`: `Failed to set payload path for package`
- `0x1800df01e`: `Skipping already installed SSU: {}`
- `0x1800defd0`: `SSU will pend. Setting IncompleteSetOfActions. Package: {}`
- `0x1800de2ff`: `CIM validation completed.`
- `0x1800dfbdc`: `Failed to get the packages directory`
- `0x1800de663`: `%wsupdate.cat`
- `0x1800de68a`: `%wsupdate.mum`
- `0x1800de8f0`: `Ignoring missing files in case of installation after reboot`
- `0x1800e0496`: `Failed to create package: {}`
- `0x1800e01a4`: `ActionList: Universal diff InstallPayload identity : ({}) does not match InstallPackage identity : ({}).`
- `0x1800e082f`: `Failed to process RemoveFeature Action`
- `0x1800e09aa`: `Failed to process InstallFeature Action`
- `0x1800e0a65`: `Failed to create foundation identity`
- `0x1800e0ba8`: `Failed to open foundation package`

## pseudocode

```c
__int64 __fastcall CCbsSession::ProcessCompleteActionList(
        CCbsSession *this,
        __int16 a2,
        struct ActionListParser::ActionListDocument *a3,
        struct Windows::Rtl::PrivateHeapPool *a4,
        wchar_t *a5,
        bool a6)
{
  int ServicingDirectory; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int SessionSandbox; // eax
  unsigned __int64 v13; // r9
  _QWORD *v14; // rax
  int v15; // eax
  int v16; // eax
  struct _LUTF8_STRING *v17; // rcx
  int v18; // eax
  int v19; // eax
  char v20; // bl
  char v21; // r12
  struct _LUTF8_STRING *v22; // rcx
  struct _LUTF8_STRING *v23; // r14
  __int128 *v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned __int64 v32; // r9
  __int64 v33; // rdx
  wchar_t **v34; // rcx
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  int v37; // eax
  int IsSmartPended; // eax
  char v39; // r13
  int v40; // ebx
  __int16 v41; // r12
  struct ActionListParser::InstallPackage *v42; // rcx
  struct ActionListParser::InstallPackage *v43; // r13
  int v44; // r14d
  unsigned int v45; // ebx
  __int64 v46; // r8
  bool IsOSFeatureUpdate; // al
  int v48; // ecx
  bool v49; // zf
  int v50; // eax
  int v51; // eax
  char v52; // al
  __int128 *v53; // r14
  const struct _LUTF8_STRING *v54; // rdx
  const struct _LUTF8_STRING *v55; // rbx
  int v56; // eax
  int v57; // eax
  __int128 *v58; // r14
  int v59; // eax
  const struct _LUTF8_STRING *v60; // rdx
  int v61; // ecx
  int v62; // r14d
  int v63; // eax
  unsigned int ReserveManager; // eax
  __int64 v65; // rbx
  const char *v66; // rdx
  wchar_t **v67; // r12
  int v68; // r13d
  wchar_t **v69; // rax
  const struct _LUTF8_STRING *v70; // r14
  int v71; // eax
  const wchar_t **v72; // r14
  const wchar_t **v73; // r13
  int v74; // eax
  int SingleFile; // eax
  __int64 v76; // rdx
  unsigned __int64 v77; // r9
  int v78; // eax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  int v82; // eax
  int v83; // eax
  int OfflineWindowsDirectory; // eax
  __int64 v85; // rdx
  void *v86; // rbx
  void *v87; // rcx
  int v88; // eax
  int v89; // eax
  char v90; // r12
  wchar_t **v91; // r14
  wchar_t **v92; // r13
  wchar_t **v93; // r14
  wchar_t **v94; // r12
  int v95; // eax
  wchar_t **v96; // r14
  wchar_t **v97; // r12
  __int64 v98; // rdx
  int v99; // eax
  struct CCbsIdentity **v100; // rax
  struct ActionListParser::InstallPackage *v101; // rax
  CCbsPackage *v102; // rcx
  wchar_t **v103; // rcx
  char v104; // bl
  int v105; // eax
  wchar_t **v106; // r14
  wchar_t **v107; // r13
  const wchar_t **v108; // r12
  unsigned int v109; // ebx
  int v110; // eax
  unsigned __int64 v111; // r9
  __int64 v112; // rdx
  struct ActionListParser::InstallPackage *v113; // r14
  unsigned int v114; // r13d
  int v115; // eax
  wchar_t **v116; // r14
  wchar_t **v117; // r12
  int v118; // eax
  bool v119; // cc
  int v120; // eax
  wchar_t **v121; // r14
  wchar_t **v122; // r12
  int v123; // eax
  wchar_t **v124; // r14
  wchar_t **v125; // r12
  __int64 v126; // rax
  char v127; // bl
  wchar_t **v128; // rcx
  __int64 v129; // rdx
  unsigned __int64 v130; // r9
  __int64 v131; // rdx
  __int64 v132; // rdx
  wchar_t **v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // rdx
  unsigned __int64 v136; // r9
  __int64 v137; // rdx
  void *p_lpNewFileName; // rcx
  unsigned __int64 v139; // r9
  signed int LastError; // ebx
  unsigned int v141; // eax
  __int64 v142; // rdx
  unsigned int v143; // eax
  __int64 v144; // rdx
  __int64 v145; // rdx
  unsigned __int64 v146; // r9
  __int64 v147; // rdx
  __int64 v148; // r9
  __int64 v149; // rdx
  __int64 v150; // rdx
  __int64 v151; // rcx
  __int64 v152; // rcx
  struct CCbsIdentity **InitPointer; // rax
  int CbsIdentity; // eax
  __int64 v155; // rdx
  struct ICbsIdentity **v156; // rcx
  int v157; // eax
  struct CCbsPackage **v158; // rax
  int v159; // eax
  int CurrentState; // eax
  int v161; // eax
  struct CCbsIdentity **v162; // rax
  struct CCbsPackage **v163; // rax
  int v164; // eax
  unsigned __int64 v165; // r9
  __int64 v166; // rdx
  int v167; // eax
  int *DirCount; // [rsp+20h] [rbp-E0h]
  int DirCounta; // [rsp+20h] [rbp-E0h]
  char v171; // [rsp+70h] [rbp-90h]
  char v172; // [rsp+71h] [rbp-8Fh]
  char v173; // [rsp+72h] [rbp-8Eh]
  char v174; // [rsp+73h] [rbp-8Dh]
  char v175; // [rsp+74h] [rbp-8Ch]
  int v176; // [rsp+78h] [rbp-88h]
  char v178; // [rsp+80h] [rbp-80h]
  struct ActionListParser::InstallPackage *v180; // [rsp+90h] [rbp-70h]
  int v181; // [rsp+98h] [rbp-68h]
  int v182; // [rsp+9Ch] [rbp-64h]
  int v183; // [rsp+A0h] [rbp-60h]
  int v184; // [rsp+A4h] [rbp-5Ch]
  int v185; // [rsp+A8h] [rbp-58h]
  int v186; // [rsp+ACh] [rbp-54h]
  unsigned int v187; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v188; // [rsp+B4h] [rbp-4Ch] BYREF
  struct ActionListParser::ActionListDocument *v189; // [rsp+B8h] [rbp-48h]
  int v190[4]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v191; // [rsp+D8h] [rbp-28h] BYREF
  int *v192; // [rsp+E0h] [rbp-20h] BYREF
  int *v193; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v194; // [rsp+F0h] [rbp-10h] BYREF
  int *v195; // [rsp+F8h] [rbp-8h] BYREF
  int *v196; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v197; // [rsp+108h] [rbp+8h] BYREF
  int *v198; // [rsp+110h] [rbp+10h] BYREF
  int *v199; // [rsp+118h] [rbp+18h] BYREF
  int *v200; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v201; // [rsp+128h] [rbp+28h] BYREF
  int v202[2]; // [rsp+130h] [rbp+30h] BYREF
  int *v203; // [rsp+138h] [rbp+38h] BYREF
  int *v204; // [rsp+140h] [rbp+40h] BYREF
  int *v205; // [rsp+148h] [rbp+48h] BYREF
  int *v206; // [rsp+150h] [rbp+50h] BYREF
  int *v207; // [rsp+158h] [rbp+58h] BYREF
  int v208[2]; // [rsp+160h] [rbp+60h] BYREF
  int *v209; // [rsp+168h] [rbp+68h] BYREF
  int v210[2]; // [rsp+170h] [rbp+70h] BYREF
  int *v211; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *v212; // [rsp+180h] [rbp+80h] BYREF
  int v213[2]; // [rsp+188h] [rbp+88h] BYREF
  int *v214; // [rsp+190h] [rbp+90h] BYREF
  int *v215; // [rsp+198h] [rbp+98h] BYREF
  int *v216; // [rsp+1A0h] [rbp+A0h] BYREF
  int *v217; // [rsp+1A8h] [rbp+A8h] BYREF
  int *v218; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t *v219; // [rsp+1B8h] [rbp+B8h] BYREF
  int *v220; // [rsp+1C0h] [rbp+C0h] BYREF
  int v221[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  int *v222; // [rsp+1D0h] [rbp+D0h] BYREF
  wchar_t *v223; // [rsp+1D8h] [rbp+D8h] BYREF
  int *v224; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t *v225; // [rsp+1E8h] [rbp+E8h] BYREF
  int *v226; // [rsp+1F0h] [rbp+F0h] BYREF
  int *v227; // [rsp+1F8h] [rbp+F8h] BYREF
  const wchar_t *v228; // [rsp+200h] [rbp+100h] BYREF
  const wchar_t *IdentityFast; // [rsp+208h] [rbp+108h] BYREF
  const wchar_t *v230; // [rsp+210h] [rbp+110h] BYREF
  const wchar_t *v231; // [rsp+218h] [rbp+118h] BYREF
  const wchar_t *v232; // [rsp+220h] [rbp+120h] BYREF
  const wchar_t *v233; // [rsp+228h] [rbp+128h] BYREF
  int *v234; // [rsp+230h] [rbp+130h] BYREF
  int v235[2]; // [rsp+238h] [rbp+138h] BYREF
  int *v236; // [rsp+240h] [rbp+140h] BYREF
  wchar_t *v237; // [rsp+248h] [rbp+148h] BYREF
  __int64 v238; // [rsp+250h] [rbp+150h] BYREF
  wchar_t *v239; // [rsp+258h] [rbp+158h] BYREF
  int *v240; // [rsp+260h] [rbp+160h] BYREF
  int *v241; // [rsp+268h] [rbp+168h] BYREF
  int *v242; // [rsp+270h] [rbp+170h] BYREF
  int *v243; // [rsp+278h] [rbp+178h] BYREF
  int *v244; // [rsp+280h] [rbp+180h] BYREF
  int *v245; // [rsp+288h] [rbp+188h] BYREF
  int v246[2]; // [rsp+290h] [rbp+190h] BYREF
  int *v247; // [rsp+298h] [rbp+198h] BYREF
  int *v248; // [rsp+2A0h] [rbp+1A0h] BYREF
  int *v249; // [rsp+2A8h] [rbp+1A8h] BYREF
  int *v250; // [rsp+2B0h] [rbp+1B0h] BYREF
  int *v251; // [rsp+2B8h] [rbp+1B8h] BYREF
  wchar_t *FastCbsIdentityString; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v253[2]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v254; // [rsp+2D0h] [rbp+1D0h] BYREF
  int *v255; // [rsp+2D8h] [rbp+1D8h] BYREF
  LPCWSTR v256; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int *v257; // [rsp+2E8h] [rbp+1E8h] BYREF
  LPCWSTR v258; // [rsp+2F0h] [rbp+1F0h] BYREF
  LPCWSTR v259; // [rsp+2F8h] [rbp+1F8h] BYREF
  unsigned int v260[2]; // [rsp+300h] [rbp+200h] BYREF
  int *v261; // [rsp+308h] [rbp+208h] BYREF
  wchar_t *v262; // [rsp+310h] [rbp+210h] BYREF
  int *v263; // [rsp+318h] [rbp+218h] BYREF
  int v264[2]; // [rsp+320h] [rbp+220h] BYREF
  int *v265; // [rsp+328h] [rbp+228h] BYREF
  int *v266; // [rsp+330h] [rbp+230h] BYREF
  const wchar_t *v267; // [rsp+338h] [rbp+238h] BYREF
  int *v268; // [rsp+340h] [rbp+240h] BYREF
  int *v269; // [rsp+348h] [rbp+248h] BYREF
  int *v270; // [rsp+350h] [rbp+250h] BYREF
  int *v271; // [rsp+358h] [rbp+258h] BYREF
  const wchar_t *v272; // [rsp+360h] [rbp+260h] BYREF
  int *v273; // [rsp+368h] [rbp+268h] BYREF
  const wchar_t *v274; // [rsp+370h] [rbp+270h] BYREF
  int *v275; // [rsp+378h] [rbp+278h] BYREF
  wchar_t *v276; // [rsp+380h] [rbp+280h] BYREF
  int v277[2]; // [rsp+388h] [rbp+288h] BYREF
  int *v278; // [rsp+390h] [rbp+290h] BYREF
  wchar_t *v279; // [rsp+3C0h] [rbp+2C0h] BYREF
  wchar_t *v280; // [rsp+3C8h] [rbp+2C8h] BYREF
  wchar_t *Str; // [rsp+3D0h] [rbp+2D0h] BYREF
  wchar_t *v282; // [rsp+3D8h] [rbp+2D8h] BYREF
  wchar_t *v283; // [rsp+3E0h] [rbp+2E0h] BYREF
  struct IUpdateReserveManagerCBS *v284; // [rsp+3E8h] [rbp+2E8h] BYREF
  wchar_t *v285; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t *v286; // [rsp+3F8h] [rbp+2F8h] BYREF
  wchar_t *v287; // [rsp+400h] [rbp+300h] BYREF
  wchar_t *v288; // [rsp+408h] [rbp+308h] BYREF
  wchar_t *v289; // [rsp+410h] [rbp+310h] BYREF
  wchar_t *v290; // [rsp+418h] [rbp+318h] BYREF
  wchar_t *v291; // [rsp+420h] [rbp+320h] BYREF
  wchar_t *v292; // [rsp+428h] [rbp+328h] BYREF
  wchar_t *v293; // [rsp+430h] [rbp+330h] BYREF
  wchar_t *v294; // [rsp+438h] [rbp+338h] BYREF
  wchar_t *v295; // [rsp+440h] [rbp+340h] BYREF
  wchar_t *v296; // [rsp+448h] [rbp+348h] BYREF
  __int128 v297; // [rsp+450h] [rbp+350h] BYREF
  __int64 v298; // [rsp+460h] [rbp+360h]
  __int128 v299; // [rsp+468h] [rbp+368h]
  __int64 v300; // [rsp+478h] [rbp+378h]
  __int64 v301; // [rsp+480h] [rbp+380h]
  __int128 v302; // [rsp+488h] [rbp+388h]
  __int64 v303; // [rsp+498h] [rbp+398h]
  __int128 v304; // [rsp+4A0h] [rbp+3A0h]
  __int64 v305; // [rsp+4B0h] [rbp+3B0h]
  __int128 v306; // [rsp+4B8h] [rbp+3B8h]
  __int64 v307; // [rsp+4C8h] [rbp+3C8h]
  __int64 v308; // [rsp+4D0h] [rbp+3D0h]
  __int64 v309; // [rsp+4D8h] [rbp+3D8h]
  __int128 v310; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v311; // [rsp+4F0h] [rbp+3F0h]
  __int128 v312; // [rsp+4F8h] [rbp+3F8h]
  __int64 v313; // [rsp+508h] [rbp+408h]
  __int64 v314; // [rsp+510h] [rbp+410h]
  __int128 v315; // [rsp+518h] [rbp+418h]
  __int64 v316; // [rsp+528h] [rbp+428h]
  __int128 v317; // [rsp+530h] [rbp+430h]
  __int64 v318; // [rsp+540h] [rbp+440h]
  __int128 v319; // [rsp+548h] [rbp+448h]
  __int64 v320; // [rsp+558h] [rbp+458h]
  __int64 v321; // [rsp+560h] [rbp+460h]
  __int64 v322; // [rsp+568h] [rbp+468h]
  __int64 v323; // [rsp+570h] [rbp+470h] BYREF
  __int64 v324; // [rsp+578h] [rbp+478h] BYREF
  __int64 v325; // [rsp+580h] [rbp+480h] BYREF
  wchar_t *v326; // [rsp+588h] [rbp+488h] BYREF
  __int64 v327; // [rsp+590h] [rbp+490h] BYREF
  char v328[8]; // [rsp+598h] [rbp+498h] BYREF
  wchar_t *v329; // [rsp+5A0h] [rbp+4A0h] BYREF
  CCbsPackage *v330; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v331[24]; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v332; // [rsp+5C8h] [rbp+4C8h]
  wchar_t **v333; // [rsp+5D8h] [rbp+4D8h]
  int v334; // [rsp+5F0h] [rbp+4F0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+5F8h] [rbp+4F8h] BYREF
  wchar_t *v336; // [rsp+600h] [rbp+500h] BYREF
  wchar_t *v337; // [rsp+608h] [rbp+508h] BYREF
  struct ICbsIdentity *v338; // [rsp+610h] [rbp+510h] BYREF
  CCbsPackage *v339; // [rsp+618h] [rbp+518h] BYREF
  __int64 v340; // [rsp+620h] [rbp+520h] BYREF
  LPCWSTR v341; // [rsp+628h] [rbp+528h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+630h] [rbp+530h] BYREF
  wchar_t *v343; // [rsp+638h] [rbp+538h] BYREF
  CCbsIdentity *v344; // [rsp+640h] [rbp+540h] BYREF
  wchar_t *v345; // [rsp+648h] [rbp+548h] BYREF
  wchar_t *v346; // [rsp+650h] [rbp+550h] BYREF
  wchar_t *v347; // [rsp+658h] [rbp+558h] BYREF
  wchar_t *v348; // [rsp+660h] [rbp+560h] BYREF
  struct CCbsIdentity *v349; // [rsp+668h] [rbp+568h] BYREF
  wchar_t *v350; // [rsp+670h] [rbp+570h] BYREF
  wchar_t *v351; // [rsp+678h] [rbp+578h] BYREF
  wchar_t *v352; // [rsp+680h] [rbp+580h] BYREF
  __int64 v353; // [rsp+688h] [rbp+588h] BYREF
  unsigned int v354; // [rsp+690h] [rbp+590h] BYREF
  int v355; // [rsp+694h] [rbp+594h] BYREF
  int v356; // [rsp+698h] [rbp+598h] BYREF
  unsigned int v357; // [rsp+69Ch] [rbp+59Ch] BYREF
  unsigned int v358; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned int v359; // [rsp+6A4h] [rbp+5A4h] BYREF
  int v360; // [rsp+6A8h] [rbp+5A8h] BYREF
  int v361; // [rsp+6ACh] [rbp+5ACh] BYREF
  __int128 *v362; // [rsp+6B0h] [rbp+5B0h] BYREF
  struct _LUTF8_STRING *v363; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v364; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int128 *v365; // [rsp+6C8h] [rbp+5C8h] BYREF
  __int128 *v366; // [rsp+6D0h] [rbp+5D0h] BYREF
  struct ActionListParser::InstallPackage *v367; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v368; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int64 v369; // [rsp+6E8h] [rbp+5E8h] BYREF
  __int64 v370; // [rsp+6F0h] [rbp+5F0h] BYREF
  struct _LUTF8_STRING *v371; // [rsp+6F8h] [rbp+5F8h] BYREF
  int v372; // [rsp+700h] [rbp+600h] BYREF
  int v373; // [rsp+704h] [rbp+604h] BYREF
  int v374; // [rsp+708h] [rbp+608h] BYREF
  int v375; // [rsp+70Ch] [rbp+60Ch] BYREF
  int v376; // [rsp+710h] [rbp+610h] BYREF
  int v377; // [rsp+714h] [rbp+614h] BYREF
  int v378; // [rsp+718h] [rbp+618h] BYREF
  int v379; // [rsp+71Ch] [rbp+61Ch] BYREF
  int v380; // [rsp+720h] [rbp+620h] BYREF
  int v381; // [rsp+724h] [rbp+624h] BYREF
  int v382; // [rsp+728h] [rbp+628h] BYREF
  int v383; // [rsp+72Ch] [rbp+62Ch] BYREF
  int v384; // [rsp+730h] [rbp+630h] BYREF
  int v385; // [rsp+734h] [rbp+634h] BYREF
  int v386; // [rsp+738h] [rbp+638h] BYREF
  int v387; // [rsp+73Ch] [rbp+63Ch] BYREF
  int v388; // [rsp+740h] [rbp+640h] BYREF
  int v389; // [rsp+744h] [rbp+644h] BYREF
  int v390; // [rsp+748h] [rbp+648h] BYREF
  int v391; // [rsp+74Ch] [rbp+64Ch] BYREF
  int v392; // [rsp+750h] [rbp+650h] BYREF
  int v393; // [rsp+754h] [rbp+654h] BYREF
  int v394; // [rsp+758h] [rbp+658h] BYREF
  int v395; // [rsp+75Ch] [rbp+65Ch] BYREF
  int v396; // [rsp+760h] [rbp+660h] BYREF
  int v397; // [rsp+764h] [rbp+664h] BYREF
  int v398; // [rsp+768h] [rbp+668h] BYREF
  int v399; // [rsp+76Ch] [rbp+66Ch] BYREF
  int v400; // [rsp+770h] [rbp+670h] BYREF
  int v401; // [rsp+774h] [rbp+674h] BYREF
  int v402; // [rsp+778h] [rbp+678h] BYREF
  int v403; // [rsp+77Ch] [rbp+67Ch] BYREF
  int v404; // [rsp+780h] [rbp+680h] BYREF
  int v405; // [rsp+784h] [rbp+684h] BYREF
  int v406; // [rsp+788h] [rbp+688h] BYREF
  int v407; // [rsp+78Ch] [rbp+68Ch] BYREF
  int v408; // [rsp+790h] [rbp+690h] BYREF
  int v409; // [rsp+794h] [rbp+694h] BYREF
  int v410; // [rsp+798h] [rbp+698h] BYREF
  int v411; // [rsp+79Ch] [rbp+69Ch] BYREF
  int v412; // [rsp+7A0h] [rbp+6A0h] BYREF
  int v413; // [rsp+7A4h] [rbp+6A4h] BYREF
  int v414; // [rsp+7A8h] [rbp+6A8h] BYREF
  int v415; // [rsp+7ACh] [rbp+6ACh] BYREF
  int v416; // [rsp+7B0h] [rbp+6B0h] BYREF
  int v417; // [rsp+7B4h] [rbp+6B4h] BYREF
  int v418; // [rsp+7B8h] [rbp+6B8h] BYREF
  int v419; // [rsp+7BCh] [rbp+6BCh] BYREF
  int v420; // [rsp+7C0h] [rbp+6C0h] BYREF
  int v421; // [rsp+7C4h] [rbp+6C4h] BYREF
  int v422; // [rsp+7C8h] [rbp+6C8h] BYREF
  int v423; // [rsp+7CCh] [rbp+6CCh] BYREF
  int v424; // [rsp+7D0h] [rbp+6D0h] BYREF
  int v425; // [rsp+7D4h] [rbp+6D4h] BYREF
  int v426; // [rsp+7D8h] [rbp+6D8h] BYREF
  int v427; // [rsp+7DCh] [rbp+6DCh] BYREF
  int v428; // [rsp+7E0h] [rbp+6E0h] BYREF
  int v429; // [rsp+7E4h] [rbp+6E4h] BYREF
  int v430; // [rsp+7E8h] [rbp+6E8h] BYREF
  __int128 v431; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int128 v432; // [rsp+800h] [rbp+700h] BYREF
  __int128 v433; // [rsp+810h] [rbp+710h] BYREF
  __int64 v434; // [rsp+820h] [rbp+720h]
  __int64 v435; // [rsp+828h] [rbp+728h] BYREF
  __int64 v436; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v437[24]; // [rsp+840h] [rbp+740h] BYREF
  __int64 v438; // [rsp+858h] [rbp+758h]
  const wchar_t **v439; // [rsp+868h] [rbp+768h]
  __int64 v440; // [rsp+880h] [rbp+780h] BYREF
  __int64 v441; // [rsp+888h] [rbp+788h] BYREF
  __int64 v442; // [rsp+890h] [rbp+790h] BYREF
  __int64 v443; // [rsp+898h] [rbp+798h] BYREF
  __int64 v444; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int64 v445; // [rsp+8A8h] [rbp+7A8h] BYREF
  __int64 v446; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v447; // [rsp+8B8h] [rbp+7B8h] BYREF
  __int64 v448; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v449[2]; // [rsp+8C8h] [rbp+7C8h] BYREF
  int v450; // [rsp+8D0h] [rbp+7D0h]
  __int128 v451; // [rsp+8D8h] [rbp+7D8h]
  __int64 v452; // [rsp+8E8h] [rbp+7E8h]
  wchar_t Ext[256]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B38h] [rbp+A38h]

  v279 = a5;
  v189 = a3;
  v436 = 0;
  v183 = a2 & 0x400;
  v185 = a2 & 0x1000;
  if ( (a2 & 0x400) != 0 )
  {
    if ( (a2 & 0x1000) != 0 )
    {
      ServicingDirectory = -2147024809;
      v386 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid parameter: ServicingProcessorOptions.");
        v248 = &v386;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v248);
      }
      v10 = 892;
      goto LABEL_18;
    }
  }
  else if ( (a2 & 0x1000) != 0 && (a2 & 0x2000) != 0 )
  {
    ServicingDirectory = -2147024809;
    v385 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid parameter: ServicingProcessorOptions.");
      v247 = &v385;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v247);
    }
    v10 = 898;
LABEL_18:
    v13 = (unsigned int)ServicingDirectory;
    goto LABEL_19;
  }
  v11 = *((_DWORD *)a3 + 20);
  *((_DWORD *)this + 553) = v11;
  if ( (*((_BYTE *)a3 + 84) & 1) != 0 || v11 == 17 )
    *((_DWORD *)this + 552) |= 0x80000u;
  SessionSandbox = CCbsSession::CreateSessionSandbox(this, *((void **)this + 141), 0, 0);
  ServicingDirectory = SessionSandbox;
  if ( SessionSandbox < 0 )
  {
    v384 = SessionSandbox;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create private session store.");
      *(_QWORD *)v246 = &v384;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v246);
    }
    v10 = 909;
    goto LABEL_18;
  }
  if ( !*(_QWORD *)(*((_QWORD *)a3 + 19) + 64LL) )
  {
    v14 = (_QWORD *)*((_QWORD *)a3 + 17);
    if ( !v14 || !v14[5] && !v14[1] && !v14[3] )
    {
      ServicingDirectory = -2146498222;
      v383 = -2146498222;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"ActionList: No feature or package to install or remove in ac"
                                                            "tionList, this is not expected.");
        v245 = &v383;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v245);
      }
      v10 = 923;
      goto LABEL_18;
    }
  }
  if ( *((_BYTE *)a3 + 164) )
  {
    v293 = 0;
    v15 = DuplicateParserString(a4, (struct ActionListParser::ActionListDocument *)((char *)a3 + 88), &v293);
    ServicingDirectory = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v10 = 929;
      goto LABEL_19;
    }
    v16 = SczAllocFromSz((char *)this + 2216, v293);
    ServicingDirectory = v16;
    if ( v16 < 0 )
    {
      v13 = (unsigned int)v16;
      v10 = 930;
      goto LABEL_19;
    }
  }
  if ( CCbsSession::IsFODRetryOperation(this) )
  {
    v17 = (struct _LUTF8_STRING *)**((_QWORD **)a3 + 17);
    v440 = 0;
    while ( 1 )
    {
      v371 = v17;
      if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                               &v371,
                               &v440) )
        goto LABEL_41;
      v286 = 0;
      v18 = DuplicateParserString(a4, v371, &v286);
      ServicingDirectory = v18;
      if ( v18 < 0 )
      {
        v13 = (unsigned int)v18;
        v10 = 944;
        goto LABEL_19;
      }
      LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Adding FOD retry: {}", &v286);
      v19 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)this + 1760), v286);
      ServicingDirectory = v19;
      if ( v19 < 0 )
        break;
      v17 = (struct _LUTF8_STRING *)*((_QWORD *)v371 + 9);
    }
    v13 = (unsigned int)v19;
    v10 = 948;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)v13,
      (int)DirCount);
    goto LABEL_698;
  }
LABEL_41:
  v20 = 0;
  v173 = 0;
  v21 = 0;
  v172 = 0;
  v22 = *(struct _LUTF8_STRING **)(*((_QWORD *)a3 + 19) + 56LL);
  v441 = 0;
  while ( 1 )
  {
    v363 = v22;
    if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v363,
                             &v441) )
      break;
    v23 = v363;
    if ( *((_DWORD *)v363 + 34) == 4 )
      v21 = 1;
    LogAdapter::DebuggerLogger::IncludeNewline((LogAdapter::DebuggerLogger *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl) )
    {
      if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v23)
        || v21 && *((_BYTE *)v23 + 307) && *((_DWORD *)v23 + 35) == 6 && *((_DWORD *)v23 + 34) != 4 )
      {
        v301 = 0;
        v298 = 0;
        v300 = 0;
        v297 = 0;
        v303 = 0;
        v299 = 0;
        v305 = 0;
        v302 = 0;
        v307 = 0;
        v304 = 0;
        v308 = 0;
        v306 = 0;
        v309 = 0;
        if ( *((_QWORD *)v23 + 33) )
        {
          v24 = (__int128 *)*((_QWORD *)v23 + 32);
        }
        else
        {
          v24 = &v297;
          BYTE3(v309) = *((_BYTE *)v23 + 305);
          v302 = *(_OWORD *)((char *)v23 + 40);
          v303 = *((_QWORD *)v23 + 7);
          BYTE4(v309) = *((_BYTE *)v23 + 307);
          v304 = *(_OWORD *)((char *)v23 + 88);
          v305 = *((_QWORD *)v23 + 13);
          BYTE5(v309) = *((_BYTE *)v23 + 308);
          v306 = *((_OWORD *)v23 + 7);
          v307 = *((_QWORD *)v23 + 16);
        }
        v442 = 0;
        while ( 1 )
        {
          v362 = v24;
          if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                   &v362,
                                   &v442) )
            goto LABEL_69;
          v288 = 0;
          v25 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)(v362 + 5), &v288);
          ServicingDirectory = v25;
          if ( v25 < 0 )
            break;
          v350 = 0;
          v26 = SczAllocFormatted(&v350, L"%ws%ws", v279, v288);
          ServicingDirectory = v26;
          if ( v26 < 0 )
          {
            v32 = (unsigned int)v26;
            v33 = 1002;
LABEL_92:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)v32,
              (int)DirCount);
            v34 = &v350;
            goto LABEL_93;
          }
          if ( (unsigned __int8)DoesDirectoryExist(v350, 0) )
          {
            LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "Adding sandbox metadata source: {}{}", &v279, &v288);
            ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v350, 0);
            if ( ServicingDirectory < 0 )
            {
              v382 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
                v244 = &v382;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v244);
              }
              v32 = (unsigned int)ServicingDirectory;
              v33 = 1017;
              goto LABEL_92;
            }
          }
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v350);
          v24 = (__int128 *)*((_QWORD *)v362 + 16);
        }
        v13 = (unsigned int)v25;
        v10 = 999;
        goto LABEL_19;
      }
    }
    else if ( v21 && *((_BYTE *)v23 + 307) && *((_DWORD *)v23 + 35) == 6 )
    {
      v287 = 0;
      v27 = DuplicateParserString(a4, (struct _LUTF8_STRING *)((char *)v23 + 88), &v287);
      ServicingDirectory = v27;
      if ( v27 < 0 )
      {
        v13 = (unsigned int)v27;
        v10 = 1031;
        goto LABEL_19;
      }
      v351 = 0;
      v28 = SczAllocFormatted(&v351, L"%ws%ws", v279, v287);
      ServicingDirectory = v28;
      if ( v28 < 0 )
      {
        v35 = (unsigned int)v28;
        v36 = 1034;
LABEL_99:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v35,
          (int)DirCount);
        v34 = &v351;
        goto LABEL_93;
      }
      if ( (unsigned __int8)DoesDirectoryExist(v351, 0) )
      {
        LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "Adding sandbox metadata source: {}{}", &v279, &v287);
        ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v351, 0);
        if ( ServicingDirectory < 0 )
        {
          v381 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
            v243 = &v381;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v243);
          }
          v35 = (unsigned int)ServicingDirectory;
          v36 = 1049;
          goto LABEL_99;
        }
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v351);
LABEL_69:
      v20 = v172;
    }
    v29 = *((_DWORD *)v23 + 34);
    if ( !v29 || v29 == 5 )
    {
      if ( (unsigned int)CCbsSession::IsOffline(this) || *((_DWORD *)v23 + 57) != 1 || a6 )
      {
        if ( *((_DWORD *)v23 + 35) != 2 && *((_DWORD *)v23 + 35) != 3 && *((_DWORD *)v23 + 35) != 4 )
        {
          if ( *((_DWORD *)v23 + 35) == 5 || *((_DWORD *)v23 + 35) == 6 )
            goto LABEL_85;
          if ( *((_DWORD *)v23 + 35) != 9 )
          {
            if ( *((_DWORD *)v23 + 35) != 13 )
              goto LABEL_87;
LABEL_85:
            v173 = 1;
            goto LABEL_87;
          }
        }
        v20 = 1;
        v172 = 1;
      }
      else
      {
        v292 = 0;
        v30 = DuplicateParserString(a4, v23, &v292);
        ServicingDirectory = v30;
        if ( v30 < 0 )
        {
          v13 = (unsigned int)v30;
          v10 = 1065;
          goto LABEL_19;
        }
        *((_BYTE *)this + 2273) = 1;
        v31 = SczAllocFromSz((char *)this + 2280, v279);
        ServicingDirectory = v31;
        if ( v31 < 0 )
        {
          v13 = (unsigned int)v31;
          v10 = 1068;
          goto LABEL_19;
        }
        LogAdapter::TraceAtLevel<wchar_t *>(1, "Scheduling installation of package: {} after reboot", &v292);
        v20 = v172;
      }
    }
LABEL_87:
    v22 = (struct _LUTF8_STRING *)*((_QWORD *)v363 + 37);
  }
  if ( v173 )
  {
    if ( v20 )
    {
      LogAdapter::TraceAtLevel<>(1, "Delaying parallel hydration use until the LCU is processed.");
      v37 = CCbsSession::SetReservicingSandboxPath(this, v279);
      ServicingDirectory = v37;
      if ( v37 < 0 )
      {
        v380 = v37;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
          v242 = &v380;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v242);
        }
        v10 = 1100;
        goto LABEL_18;
      }
    }
  }
  v361 = 0;
  IsSmartPended = CCbsSession::LCUInstallIsSmartPended(this, &v361);
  ServicingDirectory = IsSmartPended;
  if ( IsSmartPended < 0 )
  {
    v379 = IsSmartPended;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting LCU smart pended state");
      v241 = &v379;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v241);
    }
    v10 = 1119;
    goto LABEL_18;
  }
  if ( v361 && v172 )
  {
    ServicingDirectory = -2146498554;
    v412 = -2146498554;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Attempted to install a FOD or LP with a postponed LCU install "
                                                          "pending, a reboot must be performed first");
      v240 = &v412;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v240);
    }
    v10 = 1125;
    goto LABEL_18;
  }
  v171 = 0;
  v178 = 0;
  v39 = 0;
  v40 = 0;
LABEL_119:
  v181 = v40;
  if ( v40 > 5 )
    goto LABEL_432;
  v41 = a2;
  if ( v40 > 0 && (a2 & 0x4000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "Stopping after pass 0 because CbsServicingProcessorOptionSSUOnly is set");
    goto LABEL_432;
  }
  v42 = *(struct ActionListParser::InstallPackage **)(*((_QWORD *)v189 + 19) + 56LL);
  v446 = 0;
  while ( 1 )
  {
    v367 = v42;
    if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v367,
                             &v446) )
    {
      if ( v39 )
        goto LABEL_432;
      v40 = v181 + 1;
      v171 = 0;
      goto LABEL_119;
    }
    v43 = v367;
    v280 = 0;
    v285 = 0;
    v283 = 0;
    v324 = 0;
    v323 = 0;
    v44 = *((_DWORD *)v367 + 36);
    v45 = *((_DWORD *)v367 + 66);
    v176 = v44;
    v180 = v367;
    CCbsArray<MultiplePayloadsforPackage>::CCbsArray<MultiplePayloadsforPackage>(v331, 1);
    v186 = v41 & 0x1400;
    if ( !*((_BYTE *)v43 + 312)
      || (v328[0] = 0,
          (int)Windows::StringUtil::Rtl::AreStringsEqualByOrdinalCaseInvariant<_LUTF8_STRING,_LUTF8_STRING>(
                 (char *)v43 + 152,
                 ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GB__0GJ__0GO__0EP__0FD__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
                 v328) < 0)
      || v328[0] )
    {
      LOBYTE(v46) = CCbsSession::IsOSFeatureUpdate(this);
      if ( (unsigned __int8)IsActionListPackageSupportedByCBS(
                              *((unsigned int *)v43 + 35),
                              *((unsigned int *)v43 + 34),
                              v46) )
        break;
    }
LABEL_138:
    v39 = v171;
LABEL_139:
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v331);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v323);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v324);
    v41 = a2;
    v42 = (struct ActionListParser::InstallPackage *)*((_QWORD *)v367 + 37);
  }
  if ( v181 )
  {
    if ( v181 == 1 )
    {
      v49 = *((_DWORD *)v43 + 34) == 4;
LABEL_137:
      if ( !v49 )
        goto LABEL_138;
      goto LABEL_153;
    }
    if ( v181 >= 2 )
    {
      if ( *((_DWORD *)v43 + 34) == 4 )
        goto LABEL_138;
      if ( v181 == 2 )
      {
        v50 = *((_DWORD *)v43 + 35);
        if ( v50 != 4 )
        {
          v49 = v50 == 9;
          goto LABEL_137;
        }
LABEL_153:
        v52 = v178;
        if ( *((_DWORD *)v43 + 35) == 6 )
          v52 = 1;
        v178 = v52;
LABEL_156:
        v176 = v44;
        goto LABEL_157;
      }
    }
    if ( v181 == 3 )
    {
      if ( (unsigned int)(*((_DWORD *)v43 + 35) - 2) <= 1 )
        goto LABEL_153;
    }
    else
    {
      if ( v181 == 4 )
      {
        v51 = *((_DWORD *)v43 + 35);
        if ( v51 != 6 )
        {
          v49 = v51 == 13;
          goto LABEL_137;
        }
        goto LABEL_153;
      }
      if ( v181 != 5 || *((_DWORD *)v43 + 35) == 5 )
        goto LABEL_153;
    }
    goto LABEL_138;
  }
  if ( *((_DWORD *)v43 + 34) == 4 )
    goto LABEL_138;
  IsOSFeatureUpdate = CCbsSession::IsOSFeatureUpdate(this);
  v48 = *((_DWORD *)v43 + 35);
  if ( !IsOSFeatureUpdate )
  {
    if ( v48 != 7 )
      goto LABEL_138;
    goto LABEL_156;
  }
  if ( v48 != 11 )
    goto LABEL_138;
LABEL_157:
  if ( v45 )
    v176 = *(_DWORD *)(*((_QWORD *)v43 + 32) + 48LL);
  v321 = 0;
  v311 = 0;
  v313 = 0;
  v310 = 0;
  v314 = 0;
  v312 = 0;
  v316 = 0;
  v315 = 0;
  v318 = 0;
  v317 = 0;
  v320 = 0;
  v319 = 0;
  v322 = 0;
  v175 = 0;
  if ( *((_QWORD *)v43 + 33) )
  {
    v53 = (__int128 *)*((_QWORD *)v43 + 32);
    if ( *((_DWORD *)v43 + 35) == 6 && v45 > 1 )
    {
      if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v43) )
      {
        v364 = *((_QWORD *)v43 + 32);
        v448 = 0;
        while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                   &v364,
                                   &v448) )
        {
          if ( *(_QWORD *)(v364 + 128) )
          {
            v55 = (const struct _LUTF8_STRING *)(v364 + 104);
            if ( !Windows::StringUtil::IsEmpty((Windows::StringUtil *)(v364 + 104), v54) )
            {
              v56 = DuplicateParserString(a4, v55, &v283);
              ServicingDirectory = v56;
              if ( v56 < 0 )
              {
                v112 = 1290;
                goto LABEL_445;
              }
              v352 = 0;
              v57 = SczAllocCombinePath2Sz(&v352, v279, v283);
              ServicingDirectory = v57;
              if ( v57 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x511,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)(unsigned int)v57,
                  (int)DirCount);
                v128 = &v352;
                goto LABEL_443;
              }
              v239 = v352;
              LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Using TurboContainer: {}", &v239);
              CCbsSession::InitializeMetadataContainer(this, v352);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v352);
            }
          }
          v364 = *(_QWORD *)(v364 + 128);
        }
      }
      v175 = 1;
      v365 = v53;
      v435 = 0;
      while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                 &v365,
                                 &v435) )
      {
        v53 = v365;
        v365 = (__int128 *)*((_QWORD *)v365 + 16);
      }
      if ( !v172 )
        *((_BYTE *)this + 2254) = 1;
    }
  }
  else
  {
    v53 = &v310;
    BYTE3(v322) = *((_BYTE *)v43 + 305);
    v315 = *(_OWORD *)((char *)v43 + 40);
    v316 = *((_QWORD *)v43 + 7);
    BYTE4(v322) = *((_BYTE *)v43 + 307);
    v317 = *(_OWORD *)((char *)v43 + 88);
    v318 = *((_QWORD *)v43 + 13);
    BYTE5(v322) = *((_BYTE *)v43 + 308);
    v319 = *((_OWORD *)v43 + 7);
    v320 = *((_QWORD *)v43 + 16);
  }
  v366 = v53;
  v444 = 0;
  while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v366,
                             &v444) )
  {
    v58 = v366;
    v434 = 0;
    v431 = 0;
    v432 = 0;
    v433 = 0;
    if ( !CCbsSession::IsOSFeatureUpdate(this)
      && v176 == 2
      && *((_BYTE *)v58 + 140)
      && (*((_DWORD *)v43 + 35) == 6 || *((_DWORD *)v43 + 34) != 4) )
    {
      v59 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)(v58 + 5), &v280);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1375;
        goto LABEL_454;
      }
      v59 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v43 + 40), &v285);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1380;
        goto LABEL_454;
      }
      v59 = SczAllocFromSz(&v431, v280);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1382;
        goto LABEL_454;
      }
      v59 = SczAllocFromSz((char *)&v431 + 8, v285);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1384;
        goto LABEL_454;
      }
      if ( !Windows::StringUtil::IsEmpty((Windows::StringUtil *)((char *)v58 + 104), v60) )
      {
        v59 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)((char *)v58 + 104), &v283);
        ServicingDirectory = v59;
        if ( v59 < 0 )
        {
          v129 = 1392;
          goto LABEL_454;
        }
        v59 = SczAllocCombinePath2Sz((char *)&v433 + 8, v279, v283);
        ServicingDirectory = v59;
        if ( v59 < 0 )
        {
          v129 = 1398;
LABEL_454:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v129,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v59,
            (int)DirCount);
          MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v431);
          goto LABEL_447;
        }
        v238 = *((_QWORD *)&v433 + 1);
        LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Using TurboContainer: {}", &v238);
      }
    }
    else
    {
      v59 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v43 + 40), &v280);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1407;
        goto LABEL_454;
      }
      v59 = SczAllocFromSz(&v431, v280);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1409;
        goto LABEL_454;
      }
      v59 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v43 + 40), &v285);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1411;
        goto LABEL_454;
      }
      v59 = SczAllocFromSz((char *)&v431 + 8, v285);
      ServicingDirectory = v59;
      if ( v59 < 0 )
      {
        v129 = 1413;
        goto LABEL_454;
      }
    }
    v59 = SczAllocFormatted(&v432, L"%ws%ws", v279, (_QWORD)v431);
    ServicingDirectory = v59;
    if ( v59 < 0 )
    {
      v129 = 1421;
      goto LABEL_454;
    }
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::SwapOntoBack(v331, &v431);
    MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v431);
    v366 = (__int128 *)*((_QWORD *)v366 + 16);
  }
  v61 = *((_DWORD *)v43 + 34);
  v62 = v176;
  v63 = 64;
  if ( ((v61 - 2) & 0xFFFFFFFD) != 0 )
    v63 = v186 != 0 ? 64 : 112;
  v184 = v63;
  if ( *((_DWORD *)v43 + 35) == 6 && v176 == 2 && v61 != 4 && *((_BYTE *)v43 + 307) )
  {
    v56 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v43 + 88), &v280);
    ServicingDirectory = v56;
    if ( v56 < 0 )
    {
      v112 = 1436;
      goto LABEL_445;
    }
    v56 = SczAllocFormatted((char *)this + 2344, L"%ws%ws", v279, v280);
    ServicingDirectory = v56;
    if ( v56 < 0 )
    {
      v112 = 1440;
      goto LABEL_445;
    }
  }
  if ( (unsigned int)(*((_DWORD *)v43 + 35) - 6) <= 1 )
  {
    v284 = 0;
    ReserveManager = CCbsSession::GetReserveManager(this, &v284);
    if ( ReserveManager != -2146498192 )
      LogAdapter::TraceAtLevelIfFailed<long,>(1, ReserveManager, "Unable to get reserve manager.");
    if ( v284 )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(struct IUpdateReserveManagerCBS *))(*(_QWORD *)v284 + 160LL))(v284) )
      {
        LogAdapter::TraceAtLevel<>(1, "UpdateReserveManager available; checking if reserves should be used...");
        v360 = 0;
        v65 = (*(unsigned int (__fastcall **)(struct IUpdateReserveManagerCBS *, wchar_t *, int *))(*(_QWORD *)v284
                                                                                                  + 104LL))(
                v284,
                v279,
                &v360);
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v65, "Unable to get the scenario of the sandbox");
        if ( (int)v65 >= 0 )
        {
          if ( v360 != 4 )
          {
            v66 = "The current quality update is not using the reserves";
            goto LABEL_216;
          }
          ServicingDirectory = (*(__int64 (__fastcall **)(struct IUpdateReserveManagerCBS *, __int64, __int64, _QWORD))(*(_QWORD *)v284 + 88LL))(
                                 v284,
                                 1,
                                 4,
                                 *((_QWORD *)this + 138));
          if ( ServicingDirectory == -2146498188 )
          {
            v66 = "Unable to set the sandbox in hard reserve as it is not empty.";
LABEL_216:
            LogAdapter::TraceAtLevel<>(1, v66);
          }
          else
          {
            if ( ServicingDirectory < 0 )
            {
              v378 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to mark the sandbox in hard reserve.");
                v227 = &v378;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v227);
              }
              v111 = (unsigned int)ServicingDirectory;
              v112 = 1511;
LABEL_446:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v112,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v111,
                (int)DirCount);
              goto LABEL_447;
            }
            *((_DWORD *)this + 552) |= 0x4000u;
          }
        }
      }
    }
  }
  v67 = v333;
  v68 = 1;
  v69 = &v333[7 * v332];
  v182 = 1;
  *(_QWORD *)v190 = v69;
  v174 = 0;
  while ( v67 != v69 )
  {
    if ( (v62 & 0xFFFFFFFB) == 0 )
    {
      ServicingDirectory = CCbsSession::CreateSessionSandbox(this, *((void **)this + 141), *v67, v67 + 4);
      if ( ServicingDirectory < 0 )
      {
        v418 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create sandbox.");
          v265 = &v418;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v265);
        }
        v111 = (unsigned int)ServicingDirectory;
        v112 = 1551;
        goto LABEL_446;
      }
      v70 = v180;
      v68 = 0;
      v182 = 0;
      if ( *((_DWORD *)v180 + 35) == 11 )
      {
        v325 = 0;
        v291 = 0;
        Str = 0;
        v71 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v180 + 176), &v291);
        ServicingDirectory = v71;
        if ( v71 < 0 )
        {
          v131 = 1573;
          goto LABEL_578;
        }
        v71 = DuplicateParserString(a4, v180, &Str);
        ServicingDirectory = v71;
        if ( v71 < 0 )
        {
          v131 = 1575;
          goto LABEL_578;
        }
        v71 = SczAllocFormatted(&v325, L"%ws.esd", v291);
        ServicingDirectory = v71;
        if ( v71 < 0 )
        {
          v131 = 1577;
LABEL_578:
          v130 = (unsigned int)v71;
LABEL_579:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v131,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)v130,
            (int)DirCount);
          goto LABEL_580;
        }
        if ( !(unsigned int)_o__wcsicmp(v325, *v67) || wcsstr(Str, L"_layercake_overlay") )
        {
          v326 = 0;
          ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging", &v326);
          if ( ServicingDirectory < 0 )
          {
            v419 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get Staging directory path for unmanifested files.");
              *(_QWORD *)v264 = &v419;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v264);
            }
            v132 = 1585;
            goto LABEL_572;
          }
          if ( (unsigned __int8)DoesDirectoryExist(v326, 0) )
          {
            ServicingDirectory = RecursiveRemoveDirectory(1, v326);
            if ( ServicingDirectory < 0 )
            {
              v375 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v223 = v326;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to clean staging directory {} for unmanifested files.",
                  (__int64)&v223);
                v222 = &v375;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v222);
              }
              v132 = 1591;
LABEL_572:
              v146 = (unsigned int)ServicingDirectory;
              goto LABEL_573;
            }
          }
          ServicingDirectory = RecursivelyCreateDirectory(v326, 0);
          if ( ServicingDirectory < 0 )
          {
            v420 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              v262 = v326;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to create staging directory {} for unmanifested files.",
                (__int64)&v262);
              v263 = &v420;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v263);
            }
            v132 = 1596;
            goto LABEL_572;
          }
          if ( a2 < 0 )
          {
            LogAdapter::TraceAtLevel<>(1, "Extracting Payload CIMs from ESD.");
            CCbsStringArray::CCbsStringArray((CCbsStringArray *)v437);
            ServicingDirectory = CbsEsdEnumerateFiles(
                                   3u,
                                   v67[2],
                                   3u,
                                   L"windows\\winsxs\\cims\\",
                                   v326,
                                   L"payload*",
                                   (struct CCbsStringArray *)v437);
            if ( ServicingDirectory >= 0 )
            {
              v329 = 0;
              ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging\\Cims", &v329);
              if ( ServicingDirectory < 0 )
              {
                v429 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get staging root directory path for payload Cims.");
                  *(_QWORD *)v210 = &v429;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v210);
                }
                v135 = 1618;
              }
              else
              {
                ServicingDirectory = RecursivelyCreateDirectory(v329, 0);
                if ( ServicingDirectory >= 0 )
                {
                  v72 = v439;
                  v73 = &v439[v438];
                  while ( v72 != v73 )
                  {
                    v336 = 0;
                    v74 = SczAllocCombinePath2Sz(&v336, L"windows\\winsxs\\cims\\", *v72);
                    ServicingDirectory = v74;
                    if ( v74 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x65F,
                        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                        (const char *)(unsigned int)v74,
                        (int)DirCount);
                      goto LABEL_483;
                    }
                    v337 = 0;
                    memset_0(Ext, 0, sizeof(Ext));
                    if ( _wsplitpath_s(*v72, 0, 0, 0, 0, 0, 0, Ext, 0x100u) || (unsigned int)_o__wcsicmp(Ext, L".cim") )
                    {
                      v78 = SczAllocCombinePath2Sz(&v337, v329, *v72);
                      ServicingDirectory = v78;
                      if ( v78 < 0 )
                      {
                        v77 = (unsigned int)v78;
                        v76 = 1655;
                        goto LABEL_253;
                      }
                      ServicingDirectory = RecursivelyCreateDirectory(v337, 0);
                      if ( ServicingDirectory < 0 )
                      {
                        v372 = ServicingDirectory;
                        if ( LogAdapter::g_Logger )
                        {
                          v219 = v337;
                          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (__int64)"Failed to create staging directory {} for cim payload.",
                            (__int64)&v219);
                          v218 = &v372;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (__int64)LogAdapter::g_Logger,
                            1,
                            3,
                            (__int64)": {}",
                            (__int64)&v218);
                        }
                        v76 = 1659;
LABEL_252:
                        v77 = (unsigned int)ServicingDirectory;
LABEL_253:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v76,
                          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                          (const char *)v77,
                          (int)DirCount);
                        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v337);
LABEL_483:
                        v133 = &v336;
                        goto LABEL_484;
                      }
                      v79 = SczEnsureBackslashTerminated(&v336);
                      ServicingDirectory = v79;
                      if ( v79 < 0 )
                      {
                        v77 = (unsigned int)v79;
                        v76 = 1661;
                        goto LABEL_253;
                      }
                      ServicingDirectory = CbsEsdExtractDirectory(v67[2], 3u, v337, v336, 1);
                      if ( ServicingDirectory < 0 )
                      {
                        v373 = ServicingDirectory;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract cim payload from ESD.");
                          v220 = &v373;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (__int64)LogAdapter::g_Logger,
                            1,
                            3,
                            (__int64)": {}",
                            (__int64)&v220);
                        }
                        v76 = 1669;
                        goto LABEL_252;
                      }
                    }
                    else
                    {
                      SingleFile = CbsEsdExtractSingleFile(v67[2], 3u, v329, v336, 1);
                      ServicingDirectory = SingleFile;
                      if ( SingleFile < 0 )
                      {
                        v374 = SingleFile;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract cim payload file from ESD");
                          *(_QWORD *)v221 = &v374;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (__int64)LogAdapter::g_Logger,
                            1,
                            3,
                            (__int64)": {}",
                            (__int64)v221);
                        }
                        v76 = 1647;
                        goto LABEL_252;
                      }
                    }
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v337);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v336);
                    ++v72;
                  }
                  v346 = 0;
                  ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging\\", &v346);
                  if ( ServicingDirectory < 0 )
                  {
                    v394 = ServicingDirectory;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        (__int64)LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get staging root directory path for "
                                                                          "payload cims catalog.");
                      *(_QWORD *)v213 = &v394;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (__int64)LogAdapter::g_Logger,
                        1,
                        3,
                        (__int64)": {}",
                        (__int64)v213);
                    }
                    v134 = 1678;
                  }
                  else
                  {
                    ServicingDirectory = CbsEsdExtractSingleFile(
                                           v67[2],
                                           3u,
                                           v346,
                                           L"windows\\system32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\microsoft"
                                            "-windows-cimcatalog.cat",
                                           1);
                    if ( ServicingDirectory < 0 )
                    {
                      v399 = ServicingDirectory;
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(
                          (__int64)LogAdapter::g_Logger,
                          0,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract cat file from ESD");
                        v214 = &v399;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (__int64)LogAdapter::g_Logger,
                          1,
                          3,
                          (__int64)": {}",
                          (__int64)&v214);
                      }
                      v134 = 1686;
                    }
                    else
                    {
                      LogAdapter::TraceAtLevel<>(1, "Extracting completed.");
                      ValidateCimPayloadFiles(v329);
                      LogAdapter::TraceAtLevel<>(1, "CIM validation completed.");
                      if ( Windows::AutoNewPtr<CimSetup>::Allocate<>((char *)this + 2456) )
                      {
                        ServicingDirectory = CimSetup::Initialize(*((CimSetup **)this + 307), v329, 0);
                        if ( ServicingDirectory < 0 )
                        {
                          v405 = ServicingDirectory;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(
                              (__int64)LogAdapter::g_Logger,
                              0,
                              3,
                              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to setup the environment for cimbased update");
                            v216 = &v405;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              (__int64)LogAdapter::g_Logger,
                              1,
                              3,
                              (__int64)": {}",
                              (__int64)&v216);
                          }
                          v134 = 1700;
                        }
                        else
                        {
                          ServicingDirectory = CCbsSession::SetEnhancedOptions(this, 0x80000u);
                          if ( ServicingDirectory >= 0 )
                          {
                            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v346);
                            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v329);
                            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v437);
                            v70 = v180;
                            goto LABEL_265;
                          }
                          v406 = ServicingDirectory;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(
                              (__int64)LogAdapter::g_Logger,
                              0,
                              3,
                              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set the enhanced option on the session.");
                            v217 = &v406;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              (__int64)LogAdapter::g_Logger,
                              1,
                              3,
                              (__int64)": {}",
                              (__int64)&v217);
                          }
                          v134 = 1704;
                        }
                      }
                      else
                      {
                        ServicingDirectory = -2147024882;
                        v404 = -2147024882;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate CimSetup helper.");
                          v215 = &v404;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (__int64)LogAdapter::g_Logger,
                            1,
                            3,
                            (__int64)": {}",
                            (__int64)&v215);
                        }
                        v134 = 1696;
                      }
                    }
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v134,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)ServicingDirectory,
                    (int)DirCount);
                  v133 = &v346;
LABEL_484:
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v133);
LABEL_508:
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v329);
LABEL_512:
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v437);
                  goto LABEL_574;
                }
                v430 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  v212 = v329;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (__int64)"Failed to create staging directory {} for cim payload.",
                    (__int64)&v212);
                  v211 = &v430;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v211);
                }
                v135 = 1622;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v135,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)ServicingDirectory,
                (int)DirCount);
              goto LABEL_508;
            }
            v428 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enumerate cim payload directories ESD.");
              *(_QWORD *)v208 = &v428;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v208);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x64D,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)ServicingDirectory,
              (int)DirCount);
            goto LABEL_512;
          }
LABEL_265:
          Str = 0;
          v80 = DuplicateParserString(a4, v70, &Str);
          ServicingDirectory = v80;
          if ( v80 < 0 )
          {
            v146 = (unsigned int)v80;
            v132 = 1708;
LABEL_573:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v132,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)v146,
              (int)DirCount);
            goto LABEL_574;
          }
          v294 = 0;
          v295 = 0;
          v290 = 0;
          v296 = 0;
          v289 = 0;
          ServicingDirectory = ShredStringIdIntoAttributes(
                                 Str,
                                 0x7Eu,
                                 (const wchar_t **)&v294,
                                 (const wchar_t **)&v295,
                                 (const wchar_t **)&v290,
                                 (const wchar_t **)&v296,
                                 (const wchar_t **)&v289);
          if ( ServicingDirectory < 0 )
          {
            v421 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (__int64)"Failed to shred string ID: {}",
                (__int64)&Str);
              v261 = &v421;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v261);
            }
            v132 = 1724;
            goto LABEL_572;
          }
          v327 = 0;
          LODWORD(DirCount) = (_DWORD)v289;
          v81 = SczAllocFormatted(&v327, L"%ws~31bf3856ad364e35~%ws~~%ws", *((_QWORD *)this + 280), v290);
          ServicingDirectory = v81;
          if ( v81 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6C5,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)v81,
              (int)DirCount);
LABEL_561:
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v327);
LABEL_574:
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v326);
LABEL_580:
            v128 = (wchar_t **)&v325;
            goto LABEL_443;
          }
          if ( !(unsigned __int8)CCbsSession::IsSessionEnhancedOptionSet(this, 0x80000) )
          {
            v348 = 0;
            v347 = 0;
            v82 = SczAllocFormatted(&v348, L"windows\\servicing\\packages\\%ws.mum", v327);
            ServicingDirectory = v82;
            if ( v82 < 0 )
            {
              v137 = 1745;
              goto LABEL_521;
            }
            v82 = SczAllocFormatted(&v347, L"windows\\servicing\\packages\\%ws.cat", v327);
            ServicingDirectory = v82;
            if ( v82 < 0 )
            {
              v137 = 1751;
LABEL_521:
              v136 = (unsigned int)v82;
LABEL_522:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v137,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v136,
                (int)DirCount);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v347);
              p_lpNewFileName = &v348;
              goto LABEL_523;
            }
            ServicingDirectory = CbsEsdExtractSingleFile(v67[2], 3u, v67[4], v347, 1);
            if ( ServicingDirectory < 0 )
            {
              v426 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract cat file from ESD");
                v206 = &v426;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v206);
              }
              v136 = (unsigned int)ServicingDirectory;
              v137 = 1769;
              goto LABEL_522;
            }
            ServicingDirectory = CbsEsdExtractSingleFile(v67[2], 3u, v67[4], v348, 1);
            if ( ServicingDirectory < 0 )
            {
              v427 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to extract mum file from ESD");
                v207 = &v427;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v207);
              }
              v136 = (unsigned int)ServicingDirectory;
              v137 = 1777;
              goto LABEL_522;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v347);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v348);
          }
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v67 + 2);
          if ( (unsigned __int8)CCbsSession::IsSessionEnhancedOptionSet(this, 0x80000) )
          {
            v343 = 0;
            v345 = 0;
            ServicingDirectory = CCbsSession::GetPackageStoreDirectory(this, &v345);
            if ( ServicingDirectory < 0 )
            {
              v422 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get the packages directory");
                *(_QWORD *)v202 = &v422;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v202);
              }
              v85 = 1793;
LABEL_534:
              v139 = (unsigned int)ServicingDirectory;
LABEL_535:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v85,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v139,
                (int)DirCount);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v345);
              p_lpNewFileName = &v343;
              goto LABEL_523;
            }
            v83 = SczAllocFormatted(v67 + 2, L"%ws%ws.mum", v345, v327);
            ServicingDirectory = v83;
            if ( v83 < 0 )
            {
              v139 = (unsigned int)v83;
              v85 = 1800;
              goto LABEL_535;
            }
            if ( (unsigned int)CCbsSession::IsOffline(this) )
            {
              OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(this, &v343);
              ServicingDirectory = OfflineWindowsDirectory;
              if ( OfflineWindowsDirectory < 0 )
              {
                v425 = OfflineWindowsDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get offline Windir.");
                  v205 = &v425;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v205);
                }
                v85 = 1806;
                goto LABEL_534;
              }
            }
            else
            {
              ServicingDirectory = PathGetWindowsDirectory(&v343, 0);
              if ( ServicingDirectory < 0 )
              {
                v423 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get online Windir.");
                  v203 = &v423;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v203);
                }
                v85 = 1812;
                goto LABEL_534;
              }
            }
            ServicingDirectory = CCbsSession::AddSource(this, 1, 0, v343, 0);
            if ( ServicingDirectory < 0 )
            {
              v424 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
                v204 = &v424;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v204);
              }
              v85 = 1817;
              goto LABEL_534;
            }
            v86 = &v343;
            v87 = &v345;
          }
          else
          {
            lpNewFileName = 0;
            v88 = SczAllocFormatted(&lpNewFileName, L"%wsupdate.cat", v67[4]);
            ServicingDirectory = v88;
            if ( v88 < 0 )
            {
              v145 = 1824;
              goto LABEL_558;
            }
            v88 = SczAllocFormatted(v67 + 2, L"%wsupdate.mum", v67[4]);
            ServicingDirectory = v88;
            if ( v88 < 0 )
            {
              v145 = 1830;
LABEL_558:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v145,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)v88,
                (int)DirCount);
              goto LABEL_559;
            }
            v341 = 0;
            lpExistingFileName = 0;
            v89 = SczAllocFormatted(&v341, L"%ws%ws.mum", v67[4], v327);
            ServicingDirectory = v89;
            if ( v89 < 0 )
            {
              v144 = 1840;
              goto LABEL_554;
            }
            v89 = SczAllocFormatted(&lpExistingFileName, L"%ws%ws.cat", v67[4], v327);
            ServicingDirectory = v89;
            if ( v89 < 0 )
            {
              v144 = 1847;
LABEL_554:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v144,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)v89,
                (int)DirCount);
              goto LABEL_555;
            }
            if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                v258 = lpNewFileName;
                v259 = lpExistingFileName;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move file from: {} to {}",
                  (__int64)&v259,
                  (__int64)&v258);
                if ( LastError > 0 )
                  v143 = (unsigned __int16)LastError | 0x80070000;
                else
                  v143 = LastError;
                v188 = v143;
                *(_QWORD *)v260 = &v188;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {0}",
                  (__int64)v260);
              }
              if ( !LastError )
                goto LABEL_551;
              v142 = 1853;
LABEL_550:
              ServicingDirectory = wil::details::in1diag3::Return_Win32(
                                     retaddr,
                                     (void *)v142,
                                     (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                                     (const char *)(unsigned int)LastError,
                                     (unsigned int)DirCount);
LABEL_555:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v341);
LABEL_559:
              p_lpNewFileName = &lpNewFileName;
LABEL_523:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(p_lpNewFileName);
              goto LABEL_561;
            }
            if ( !MoveFileW(v341, v67[2]) )
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                v201 = v67[2];
                v256 = v341;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to move file from: {} to {}",
                  (__int64)&v256,
                  (__int64)&v201);
                if ( LastError > 0 )
                  v141 = (unsigned __int16)LastError | 0x80070000;
                else
                  v141 = LastError;
                v187 = v141;
                v257 = &v187;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {0}",
                  (__int64)&v257);
              }
              if ( LastError )
              {
                v142 = 1859;
                goto LABEL_550;
              }
LABEL_551:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v341);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v327);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v326);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v325);
              CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v331);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v323);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v324);
              ServicingDirectory = 0;
              goto LABEL_698;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            v87 = &v341;
            v86 = &lpNewFileName;
          }
          v68 = 4;
          v182 = 4;
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v87);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v86);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v327);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v326);
        }
        else if ( *((_DWORD *)v180 + 34) == 3 )
        {
          if ( a2 < 0 )
          {
            v237 = v67[2];
            LogAdapter::TraceAtLevel<wchar_t *>(1, "Skipping expansion of the package {}", &v237);
          }
          else
          {
            ServicingDirectory = DpxExtractAllFilesFromCabinet(v67[2], v67[4]);
            if ( ServicingDirectory < 0 )
            {
              v376 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v225 = v67[2];
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed to extract all files from the container {}",
                  (__int64)&v225);
                v224 = &v376;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v224);
              }
              v130 = (unsigned int)ServicingDirectory;
              v131 = 1875;
              goto LABEL_579;
            }
            ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v67[4], 0);
            if ( ServicingDirectory < 0 )
            {
              v377 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
                v226 = &v377;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v226);
              }
              v130 = (unsigned int)ServicingDirectory;
              v131 = 1886;
              goto LABEL_579;
            }
          }
          v174 = 1;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v325);
      }
      v69 = *(wchar_t ***)v190;
      v62 = v176;
    }
    v67 += 7;
  }
  if ( *((_DWORD *)v180 + 34) == 3 )
  {
    v90 = 0;
    if ( v174 )
      goto LABEL_138;
    v91 = v333;
    v92 = &v333[7 * v332];
    while ( v91 != v92 )
    {
      if ( (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(v91 + 1) )
      {
        v56 = SczAllocFormatted(v91 + 3, L"%ws%ws", v279, v91[1]);
        ServicingDirectory = v56;
        if ( v56 < 0 )
        {
          v112 = 1919;
          goto LABEL_445;
        }
        ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v91[3], 0);
        if ( ServicingDirectory < 0 )
        {
          v417 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
            v266 = &v417;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v266);
          }
          v111 = (unsigned int)ServicingDirectory;
          v112 = 1923;
          goto LABEL_446;
        }
        v90 = 1;
      }
      v91 += 7;
    }
    if ( v90 )
      goto LABEL_138;
    v68 = v182;
  }
  if ( a6 && v68 == 1 )
  {
    v93 = v333;
    v94 = &v333[7 * v332];
    v340 = 0;
    while ( v93 != v94 )
    {
      v95 = SczAllocFromSz(&v340, v93[2]);
      ServicingDirectory = v95;
      if ( v95 < 0 )
      {
        v147 = 1943;
LABEL_591:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v147,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)(unsigned int)v95,
          (int)DirCount);
        v128 = (wchar_t **)&v340;
LABEL_443:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v128);
        goto LABEL_447;
      }
      v95 = SczEnsureBackslashTerminated(&v340);
      ServicingDirectory = v95;
      if ( v95 < 0 )
      {
        v147 = 1945;
        goto LABEL_591;
      }
      v95 = SczAllocConcatSz(&v340, L"update.mum");
      ServicingDirectory = v95;
      if ( v95 < 0 )
      {
        v147 = 1947;
        goto LABEL_591;
      }
      if ( !(unsigned int)DoesFileExist(v340, 0) )
      {
        LogAdapter::TraceAtLevel<>(1, "Ignoring missing files in case of installation after reboot");
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v340);
        goto LABEL_138;
      }
      v93 += 7;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v340);
  }
  v96 = v333;
  v97 = &v333[7 * v332];
  while ( 1 )
  {
    if ( v96 == v97 )
    {
      v103 = v333;
      v104 = 0;
      while ( v103 != &v333[7 * v332] )
      {
        if ( *((_BYTE *)v103[6] + 1057) )
        {
          v104 = 1;
          break;
        }
        v103 += 7;
      }
      if ( !(unsigned int)CCbsSession::IsOffline(this) && v104 && !a6 )
      {
        *(_QWORD *)v449 = 0;
        v451 = 0;
        v450 = 0;
        v452 = 0;
        if ( v178 )
          goto LABEL_349;
        if ( (int)CCbsSession::GetStoreObject(this, 0, 14, 0, v449) >= 0
          || (int)CCbsSession::GetStoreObject(this, 0, 15, 0, v449) >= 0 )
        {
          v178 = 1;
LABEL_349:
          *((_BYTE *)this + 2273) = 1;
          v105 = SczAllocFromSz((char *)this + 2280, v279);
          ServicingDirectory = v105;
          if ( v105 >= 0 )
          {
            LogAdapter::TraceAtLevel<>(1, "Scheduling installation of packages after reboot");
            CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v449);
            goto LABEL_138;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v105,
            (int)DirCount);
          CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v449);
          goto LABEL_447;
        }
        CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v449);
      }
      v106 = v333;
      v107 = &v333[7 * v332];
      while ( v106 != v107 )
      {
        if ( (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(v106 + 1) )
        {
          v108 = (const wchar_t **)(v106 + 3);
          v56 = SczAllocFormatted(v106 + 3, L"%ws%ws", v279, v106[1]);
          ServicingDirectory = v56;
          if ( v56 < 0 )
          {
            v112 = 2169;
            goto LABEL_445;
          }
          v109 = 2 * (a2 & 1);
          if ( (unsigned __int8)DoesDirectoryExist(*v108, 0) )
          {
            ServicingDirectory = CCbsSession::AddSource(this, 1, v109, *v108, 0);
            if ( ServicingDirectory < 0 )
            {
              v407 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v191 = *v108;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed adding payload path source: {}",
                  (__int64)&v191);
                v192 = &v407;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v192);
              }
              v111 = (unsigned int)ServicingDirectory;
              v112 = 2177;
              goto LABEL_446;
            }
            v110 = CCbsPackage::SetPayloadPath((CCbsPackage *)v106[6], *v108);
            ServicingDirectory = v110;
            if ( v110 < 0 )
            {
              v408 = v110;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set payload path for package");
                v278 = &v408;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v278);
              }
              v111 = (unsigned int)ServicingDirectory;
              v112 = 2184;
              goto LABEL_446;
            }
          }
          else if ( *((_BYTE *)this + 2254) && v176 == 4 && (unsigned __int8)DoesDirectoryExist(v106[4], 0) )
          {
            ServicingDirectory = CCbsSession::AddSource(this, 1, v109, v106[4], 0);
            if ( ServicingDirectory < 0 )
            {
              v402 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v194 = v106[4];
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"Failed adding CBS sandbox as source for GDR package: {}",
                  (__int64)&v194);
                v209 = &v402;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v209);
              }
              v111 = (unsigned int)ServicingDirectory;
              v112 = 2196;
              goto LABEL_446;
            }
            ServicingDirectory = CCbsPackage::SetPayloadPath((CCbsPackage *)v106[6], v106[4]);
            if ( ServicingDirectory < 0 )
            {
              v403 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding CBS sandbox as source for GDR package");
                v193 = &v403;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v193);
              }
              v111 = (unsigned int)ServicingDirectory;
              v112 = 2203;
              goto LABEL_446;
            }
          }
        }
        v106 += 7;
      }
      v113 = v180;
      v114 = 16 * (a2 & 1) + 1;
      v115 = *((_DWORD *)v180 + 34);
      if ( (v115 == 4 || v183) && (v114 |= 0x200u, v115 == 4) )
      {
        v114 |= 0x80000u;
      }
      else if ( v115 == 5 )
      {
        v114 |= 0x100u;
      }
      if ( *((_DWORD *)v180 + 35) == 7 )
      {
        v116 = v333;
        v117 = &v333[7 * v332];
        while ( 1 )
        {
          if ( v116 == v117 )
          {
            v113 = v180;
            break;
          }
          v334 = 4096;
          v356 = 4096;
          ServicingDirectory = CCbsPackage::GetCurrentStateConsideringSmartPending(
                                 (CCbsPackage *)v116[6],
                                 this,
                                 (enum CbsState *)&v334);
          if ( ServicingDirectory < 0 )
          {
            v400 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting current state");
              v196 = &v400;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v196);
            }
            v111 = (unsigned int)ServicingDirectory;
            v112 = 2251;
            goto LABEL_446;
          }
          ServicingDirectory = CCbsPackage::GetApplicableState((CCbsPackage *)v116[6], this, 0, (enum CbsState *)&v356);
          if ( ServicingDirectory < 0 )
          {
            v401 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get applicable state");
              v195 = &v401;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v195);
            }
            v111 = (unsigned int)ServicingDirectory;
            v112 = 2255;
            goto LABEL_446;
          }
          v118 = v334;
          v119 = v334 < 96;
          if ( v334 == 96 )
          {
            if ( !v172 && !v173 )
            {
LABEL_400:
              IdentityFast = CCbsPackage::GetIdentityFast((CCbsPackage *)v116[6]);
              LogAdapter::TraceAtLevel<wchar_t const *>(1, "Skipping already installed SSU: {}", &IdentityFast);
              goto LABEL_138;
            }
            if ( !(unsigned int)CCbsSession::IsOffline(this) )
            {
              v231 = CCbsPackage::GetIdentityFast((CCbsPackage *)v116[6]);
              LogAdapter::TraceAtLevel<wchar_t const *>(1, "SSU is pending, need to skip other actions: {}", &v231);
              *((_DWORD *)this + 552) |= 0x40000u;
LABEL_398:
              v171 = 1;
              goto LABEL_399;
            }
            v118 = v334;
            v119 = v334 < 96;
          }
          if ( !v119 && v118 != 4096 )
            goto LABEL_400;
          if ( v118 != v356 )
          {
            if ( !v186 && (v172 || v173) )
            {
              if ( !(unsigned int)CCbsSession::IsOffline(this) && (unsigned int)PackageStoreIsPendingRequired(0, 0, 0) )
              {
                v230 = CCbsPackage::GetIdentityFast((CCbsPackage *)v116[6]);
                LogAdapter::TraceAtLevel<wchar_t const *>(
                  1,
                  "SSU will pend. Setting IncompleteSetOfActions. Package: {}",
                  &v230);
                *((_DWORD *)this + 552) |= 0x40000u;
              }
              v118 = v334;
            }
            if ( v184 != 64 || v118 != 64 )
              goto LABEL_398;
          }
LABEL_399:
          v116 += 7;
        }
      }
      if ( v176 == 2 && *((_BYTE *)v113 + 307) && *((_DWORD *)v113 + 34) != 4 )
      {
        v56 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v113 + 88), &v280);
        ServicingDirectory = v56;
        if ( v56 < 0 )
        {
          v112 = 2323;
LABEL_445:
          v111 = (unsigned int)v56;
          goto LABEL_446;
        }
      }
      else
      {
        v56 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v113 + 40), &v280);
        ServicingDirectory = v56;
        if ( v56 < 0 )
        {
          v112 = 2332;
          goto LABEL_445;
        }
      }
      LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "ActionList: Adding package: {}{}", &v279, &v280);
      if ( v172 && v173 && (v181 == 1 || (unsigned int)(v181 - 4) <= 1) )
      {
        v120 = *((_DWORD *)v113 + 34);
        if ( (v120 & 0xFFFFFFFA) == 0 && v120 != 1 )
        {
          v121 = v333;
          v122 = &v333[7 * v332];
          while ( 1 )
          {
            if ( v121 == v122 )
              goto LABEL_430;
            v228 = CCbsPackage::GetIdentityFast((CCbsPackage *)v121[6]);
            LogAdapter::TraceAtLevel<wchar_t const *>(1, "ActionList: Add package: {} for reservicing", &v228);
            v123 = *((_DWORD *)v180 + 34);
            if ( v123 == 4 )
            {
              *(wchar_t *)((char *)v121[6] + 1061) = 257;
            }
            else if ( v123 == 5 )
            {
              *((_BYTE *)v121[6] + 1062) = 1;
            }
            if ( *((_DWORD *)v180 + 35) == 6 && *((_QWORD *)v180 + 33) > 1u )
              *((_BYTE *)this + 2255) = 1;
            ServicingDirectory = CCbsSession::AddLCUOrGDRToInstall(this, (struct CCbsPackage *)v121[6]);
            if ( ServicingDirectory < 0 )
              break;
            v121 += 7;
          }
          v398 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
            v255 = &v398;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v255);
          }
          v111 = (unsigned int)ServicingDirectory;
          v112 = 2384;
          goto LABEL_446;
        }
      }
      if ( !v185 )
      {
        v124 = v333;
        v125 = &v333[7 * v332];
        while ( 1 )
        {
          if ( v124 == v125 )
            goto LABEL_430;
          ServicingDirectory = CCbsPackage::InitiateChanges(
                                 (__int64)v124[6],
                                 (__int64)this,
                                 *((void **)this + 141),
                                 v114,
                                 v184,
                                 1u,
                                 0,
                                 0);
          if ( ServicingDirectory < 0 )
            break;
          v124 += 7;
        }
        v397 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v197 = v124[2];
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed Initiating changes for package: {}",
            (__int64)&v197);
          v198 = &v397;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v198);
        }
        v111 = (unsigned int)ServicingDirectory;
        v112 = 2401;
        goto LABEL_446;
      }
LABEL_430:
      v39 = v171;
      if ( v171 )
      {
        CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v331);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v323);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v324);
LABEL_432:
        if ( !v185 && (a2 & 0x4000) == 0 )
        {
          v126 = *((_QWORD *)v189 + 17);
          if ( v126 )
          {
            v127 = 0;
            v368 = *(_QWORD *)(v126 + 16);
            v445 = 0;
            while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                       &v368,
                                       &v445) )
            {
              ServicingDirectory = CCbsSession::AddFeatureToModify(this, v368, 0);
              if ( ServicingDirectory < 0 )
              {
                v396 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process RemoveFeature Action");
                  v199 = &v396;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v199);
                }
                v10 = 2445;
                goto LABEL_18;
              }
              v127 = 1;
              v368 = *(_QWORD *)(v368 + 72);
            }
            if ( !v183 )
            {
              v151 = *(_QWORD *)(*((_QWORD *)v189 + 17) + 32LL);
              v447 = 0;
              while ( 1 )
              {
                v369 = v151;
                if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                         &v369,
                                         &v447) )
                  break;
                ServicingDirectory = CCbsSession::AddFeatureToModify(this, v369, 64);
                if ( ServicingDirectory < 0 )
                {
                  v395 = ServicingDirectory;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process DisableFeature Action");
                    v200 = &v395;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v200);
                  }
                  v10 = 2456;
                  goto LABEL_18;
                }
                v127 = 1;
                v151 = *(_QWORD *)(v369 + 72);
              }
              v152 = **((_QWORD **)v189 + 17);
              v443 = 0;
              while ( 1 )
              {
                v370 = v152;
                if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                         &v370,
                                         &v443) )
                  break;
                ServicingDirectory = CCbsSession::AddFeatureToModify(this, v370, 112);
                if ( ServicingDirectory < 0 )
                {
                  v393 = ServicingDirectory;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process InstallFeature Action");
                    v234 = &v393;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)&v234);
                  }
                  v10 = 2464;
                  goto LABEL_18;
                }
                v127 = 1;
                v152 = *(_QWORD *)(v370 + 72);
              }
            }
            if ( !(unsigned int)CCbsSession::InspectSessionTask(this) && *((_QWORD *)v189 + 17) && v127 )
            {
              v338 = 0;
              v339 = 0;
              v355 = 4096;
              InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v338);
              CbsIdentity = CreateCbsIdentity(InitPointer);
              ServicingDirectory = CbsIdentity;
              if ( CbsIdentity < 0 )
              {
                v392 = CbsIdentity;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create foundation identity");
                  *(_QWORD *)v235 = &v392;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v235);
                }
                v155 = 2476;
LABEL_666:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v155,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)(unsigned int)ServicingDirectory,
                  (int)DirCount);
                Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v339);
                v156 = &v338;
                goto LABEL_667;
              }
              v157 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, const wchar_t *))(*(_QWORD *)v338 + 56LL))(
                       v338,
                       L"@Foundation");
              ServicingDirectory = v157;
              if ( v157 < 0 )
              {
                v391 = v157;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load foundation identity");
                  v236 = &v391;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v236);
                }
                v155 = 2480;
                goto LABEL_666;
              }
              v158 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v339);
              v159 = CCbsSession::OpenPackage(this, *((void **)this + 141), 0, v338, 0, v158);
              ServicingDirectory = v159;
              if ( v159 < 0 )
              {
                v390 = v159;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open foundation package");
                  v249 = &v390;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v249);
                }
                v155 = 2488;
                goto LABEL_666;
              }
              CurrentState = CCbsPackage::GetCurrentState(v339, this, (enum CbsState *)&v355);
              ServicingDirectory = CurrentState;
              if ( CurrentState < 0 )
              {
                v389 = CurrentState;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get current state of foundation package");
                  v250 = &v389;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v250);
                }
                v155 = 2492;
                goto LABEL_666;
              }
              v161 = CCbsPackage::InitiateChanges(
                       (__int64)v339,
                       (__int64)this,
                       *((void **)this + 141),
                       1u,
                       v355,
                       0,
                       0,
                       0);
              ServicingDirectory = v161;
              if ( v161 < 0 )
              {
                v388 = v161;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initiate changes for foundation package");
                  v251 = &v388;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)&v251);
                }
                v155 = 2502;
                goto LABEL_666;
              }
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v339);
              Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v338);
            }
          }
          if ( CCbsSession::IsOSFeatureUpdate(this) )
          {
            v349 = 0;
            v162 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v349);
            if ( CCbsSession::IsAnLCUInstalled(this, v162)
              && (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(&v349) )
            {
              v353 = 0;
              v163 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v353);
              v164 = CCbsSession::ResolvePackage(this, 0, *((void **)this + 141), 0, v349, 1, v163, 0);
              ServicingDirectory = v164;
              if ( v164 < 0 )
              {
                v387 = v164;
                if ( LogAdapter::g_Logger )
                {
                  FastCbsIdentityString = GetFastCbsIdentityString(v349);
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (__int64)"Failed to resolve the LCU package: {}",
                    (__int64)&FastCbsIdentityString);
                  *(_QWORD *)v253 = &v387;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v253);
                }
                v165 = (unsigned int)ServicingDirectory;
                v166 = 2521;
LABEL_692:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v166,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)v165,
                  DirCounta);
                Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v353);
                v156 = &v349;
LABEL_667:
                Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(v156);
                goto LABEL_698;
              }
              v254 = v353;
              v167 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, &v254);
              ServicingDirectory = v167;
              if ( v167 < 0 )
              {
                v165 = (unsigned int)v167;
                v166 = 2523;
                goto LABEL_692;
              }
              *((_DWORD *)this + 173) |= 0x40000000u;
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v353);
            }
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v349);
          }
        }
        ServicingDirectory = 0;
        goto LABEL_698;
      }
      goto LABEL_139;
    }
    v330 = 0;
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v330);
    v98 = *((_QWORD *)this + 141);
    DirCount = v190;
    *(GUID *)v190 = GUID_NULL;
    ServicingDirectory = CCbsSession::CreateWindowsUpdatePackage(this, v98, 0, 0);
    if ( ServicingDirectory < 0 )
    {
      v409 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        v276 = v96[2];
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to create package: {}",
          (__int64)&v276);
        *(_QWORD *)v277 = &v409;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v277);
      }
      v150 = 1982;
      goto LABEL_615;
    }
    if ( v175 )
      break;
LABEL_329:
    LogAdapter::DebuggerLogger::IncludeNewline((LogAdapter::DebuggerLogger *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl);
    v49 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl) == 0;
    v101 = v180;
    if ( !v49 && *((_DWORD *)v180 + 34) == 4 && *((_DWORD *)v180 + 35) == 6 && *((_DWORD *)v180 + 66) > 1u )
    {
      v233 = CCbsPackage::GetIdentityFast(v330);
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "ActionList: Setting the partial baseline package flag for package: ({})",
        &v233);
      *(_WORD *)((char *)v330 + 1061) = 257;
      ServicingDirectory = CCbsPackage::SetParentRevisionApplicability(v330, 1);
      if ( ServicingDirectory < 0 )
      {
        v411 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v272 = CCbsPackage::GetIdentityFast(v330);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"ActionList: Failed set parent revision applicability for package: ({})",
            (__int64)&v272);
          v273 = &v411;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v273);
        }
        v150 = 2070;
        goto LABEL_615;
      }
      v101 = v180;
    }
    if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v101) )
    {
      v232 = CCbsPackage::GetIdentityFast(v330);
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "ActionList: Skipping parent revision level applicability for package: ({}) in WinPE",
        &v232);
      ServicingDirectory = CCbsPackage::SetParentRevisionApplicability(v330, 1);
      if ( ServicingDirectory < 0 )
      {
        v410 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v274 = CCbsPackage::GetIdentityFast(v330);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"ActionList: Failed to set parent revision applicability for package in WinPE: ({})",
            (__int64)&v274);
          v275 = &v410;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v275);
        }
        v150 = 2085;
LABEL_615:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v150,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)(unsigned int)ServicingDirectory,
          (int)DirCount);
        goto LABEL_616;
      }
    }
    v102 = (CCbsPackage *)v96[6];
    v96[6] = (wchar_t *)v330;
    v330 = v102;
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v330);
    v96 += 7;
  }
  v282 = 0;
  v344 = 0;
  v99 = DuplicateParserString(a4, v180, &v282);
  ServicingDirectory = v99;
  if ( v99 < 0 )
  {
    v148 = (unsigned int)v99;
    v149 = 2030;
    goto LABEL_605;
  }
  v100 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v344);
  ServicingDirectory = GetCbsIdentityFromKeyForm(v282, v100);
  if ( ServicingDirectory >= 0 )
  {
    v358 = 0;
    v354 = 0;
    ServicingDirectory = CCbsIdentity::GetVersion(v344, &v358, &v354);
    if ( ServicingDirectory < 0 )
    {
      v414 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to get version from keyform: '{}'",
          (__int64)&v282);
        v270 = &v414;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v270);
      }
      v148 = (unsigned int)ServicingDirectory;
      v149 = 2040;
      goto LABEL_605;
    }
    v359 = 0;
    v357 = 0;
    ServicingDirectory = CCbsIdentity::GetVersion(*((CCbsIdentity **)v330 + 14), &v359, &v357);
    if ( ServicingDirectory < 0 )
    {
      v415 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get version from package");
        v269 = &v415;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v269);
      }
      v148 = (unsigned int)ServicingDirectory;
      v149 = 2046;
      goto LABEL_605;
    }
    if ( v358 != v359 || v354 != v357 )
    {
      ServicingDirectory = -2146498221;
      v416 = -2146498221;
      if ( LogAdapter::g_Logger )
      {
        v267 = CCbsPackage::GetIdentityFast(v330);
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"ActionList: Universal diff InstallPayload identity : ({}) does not match InstallPackage identity : ({}).",
          (__int64)&v267,
          (__int64)&v282);
        v268 = &v416;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v268);
      }
      v148 = 2148469075LL;
      v149 = 2054;
      goto LABEL_605;
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v344);
    goto LABEL_329;
  }
  v413 = ServicingDirectory;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (__int64)"Failed to get identity from keyform: '{}'",
      (__int64)&v282);
    v271 = &v413;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v271);
  }
  v148 = (unsigned int)ServicingDirectory;
  v149 = 2034;
LABEL_605:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v149,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
    (const char *)v148,
    (int)DirCount);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v344);
LABEL_616:
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v330);
LABEL_447:
  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v331);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v323);
  v34 = (wchar_t **)&v324;
LABEL_93:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v34);
LABEL_698:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v436);
  return (unsigned int)ServicingDirectory;
}

```

## disassembly

```asm
0x1800dc9c0  mov     [rsp-8+arg_8], rbx
0x1800dc9c5  push    rbp
0x1800dc9c6  push    rsi
0x1800dc9c7  push    rdi
0x1800dc9c8  push    r12
0x1800dc9ca  push    r13
0x1800dc9cc  push    r14
0x1800dc9ce  push    r15
0x1800dc9d0  lea     rbp, [rsp-0A00h]
0x1800dc9d8  sub     rsp, 0B00h
0x1800dc9df  mov     rax, cs:__security_cookie
0x1800dc9e6  xor     rax, rsp
0x1800dc9e9  mov     [rbp+0A30h+var_40], rax
0x1800dc9f0  mov     rax, [rbp+0A30h+arg_20]
0x1800dc9f7  mov     r15, rcx
0x1800dc9fa  mov     [rbp+0A30h+var_770], rax
0x1800dca01  xor     edi, edi
0x1800dca03  mov     eax, edx
0x1800dca05  mov     [rbp+0A30h+var_AA8], r9
0x1800dca09  and     eax, 1000h
0x1800dca0e  mov     [rbp+0A30h+var_A78], r8
0x1800dca12  mov     ecx, edx
0x1800dca14  mov     [rsp+0B30h+var_AB4], edx
0x1800dca18  and     ecx, 400h
0x1800dca1e  mov     [rbp+0A30h+var_300], rdi
0x1800dca25  mov     [rbp+0A30h+var_A90], ecx
0x1800dca28  mov     r13, r9
0x1800dca2b  mov     [rbp+0A30h+var_A88], eax
0x1800dca2e  mov     r14, r8
0x1800dca31  test    ecx, ecx
0x1800dca33  jz      short loc_1800DCAA7
0x1800dca35  test    eax, eax
0x1800dca37  jz      loc_1800DCB1B
0x1800dca3d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dca44  mov     ebx, 80070057h
0x1800dca49  mov     [rbp+0A30h+var_3F8], ebx
0x1800dca4f  test    rcx, rcx
0x1800dca52  jz      short loc_1800DCA9D
0x1800dca54  mov     edi, 3
0x1800dca59  lea     r9, aInvalidParamet_20; "Invalid parameter: ServicingProcessorOp"...
0x1800dca60  mov     r8d, edi
0x1800dca63  xor     edx, edx
0x1800dca65  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dca6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dca71  lea     rax, [rbp+0A30h+var_3F8]
0x1800dca78  mov     [rbp+0A30h+var_890], rax
0x1800dca7f  lea     r9, asc_1802EE7AC; ": {}"
0x1800dca86  lea     rax, [rbp+0A30h+var_890]
0x1800dca8d  mov     r8d, edi
0x1800dca90  lea     edx, [rdi-2]
0x1800dca93  mov     [rsp+0B30h+DirCount], rax
0x1800dca98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dca9d  mov     edx, 37Ch
0x1800dcaa2  jmp     loc_1800DCBBA
0x1800dcaa7  test    eax, eax
0x1800dcaa9  jz      short loc_1800DCB1B
0x1800dcaab  bt      edx, 0Dh
0x1800dcaaf  jnb     short loc_1800DCB1B
0x1800dcab1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcab8  mov     ebx, 80070057h
0x1800dcabd  mov     [rbp+0A30h+var_3FC], ebx
0x1800dcac3  test    rcx, rcx
0x1800dcac6  jz      short loc_1800DCB11
0x1800dcac8  mov     edi, 3
0x1800dcacd  lea     r9, aInvalidParamet_20; "Invalid parameter: ServicingProcessorOp"...
0x1800dcad4  mov     r8d, edi
0x1800dcad7  xor     edx, edx
0x1800dcad9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcade  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcae5  lea     rax, [rbp+0A30h+var_3FC]
0x1800dcaec  mov     [rbp+0A30h+var_898], rax
0x1800dcaf3  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcafa  lea     rax, [rbp+0A30h+var_898]
0x1800dcb01  mov     r8d, edi
0x1800dcb04  lea     edx, [rdi-2]
0x1800dcb07  mov     [rsp+0B30h+DirCount], rax
0x1800dcb0c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcb11  mov     edx, 382h
0x1800dcb16  jmp     loc_1800DCBBA
0x1800dcb1b  mov     eax, [r8+50h]
0x1800dcb1f  mov     esi, 1
0x1800dcb24  mov     [r15+8A4h], eax
0x1800dcb2b  test    [r8+54h], sil
0x1800dcb2f  jnz     short loc_1800DCB36
0x1800dcb31  cmp     eax, 11h
0x1800dcb34  jnz     short loc_1800DCB3F
0x1800dcb36  bts     dword ptr [r15+8A0h], 13h
0x1800dcb3f  mov     rdx, [r15+468h]; void *
0x1800dcb46  xor     r9d, r9d; wchar_t **
0x1800dcb49  xor     r8d, r8d; wchar_t *
0x1800dcb4c  mov     rcx, r15; this
0x1800dcb4f  call    ?CreateSessionSandbox@CCbsSession@@QEAAJPEAXPEB_WPEAPEA_W@Z; CCbsSession::CreateSessionSandbox(void *,wchar_t const *,wchar_t * *)
0x1800dcb54  mov     ebx, eax
0x1800dcb56  test    eax, eax
0x1800dcb58  jns     short loc_1800DCBD5
0x1800dcb5a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcb61  mov     [rbp+0A30h+var_400], eax
0x1800dcb67  test    rcx, rcx
0x1800dcb6a  jz      short loc_1800DCBB5
0x1800dcb6c  mov     edi, 3
0x1800dcb71  lea     r9, aFailedToCreate_14; "Failed to create private session store."
0x1800dcb78  mov     r8d, edi
0x1800dcb7b  xor     edx, edx
0x1800dcb7d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcb82  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcb89  lea     rax, [rbp+0A30h+var_400]
0x1800dcb90  mov     qword ptr [rbp+0A30h+var_8A0], rax
0x1800dcb97  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcb9e  lea     rax, [rbp+0A30h+var_8A0]
0x1800dcba5  mov     r8d, edi
0x1800dcba8  mov     dl, sil
0x1800dcbab  mov     [rsp+0B30h+DirCount], rax; int
0x1800dcbb0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcbb5  mov     edx, 38Dh; void *
0x1800dcbba  mov     r9d, ebx; char *
0x1800dcbbd  mov     rcx, [rbp+0A38h]; this
0x1800dcbc4  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800dcbcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcbd0  jmp     loc_1800E0EB8
0x1800dcbd5  mov     rax, [r14+98h]
0x1800dcbdc  cmp     [rax+40h], rdi
0x1800dcbe0  jnz     loc_1800DCC6E
0x1800dcbe6  mov     rax, [r14+88h]
0x1800dcbed  test    rax, rax
0x1800dcbf0  jz      short loc_1800DCC04
0x1800dcbf2  cmp     [rax+28h], rdi
0x1800dcbf6  jnz     short loc_1800DCC6E
0x1800dcbf8  cmp     [rax+8], rdi
0x1800dcbfc  jnz     short loc_1800DCC6E
0x1800dcbfe  cmp     [rax+18h], rdi
0x1800dcc02  jnz     short loc_1800DCC6E
0x1800dcc04  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcc0b  mov     ebx, 800F0952h
0x1800dcc10  mov     [rbp+0A30h+var_404], ebx
0x1800dcc16  test    rcx, rcx
0x1800dcc19  jz      short loc_1800DCC64
0x1800dcc1b  mov     edi, 3
0x1800dcc20  lea     r9, aActionlistNoFe; "ActionList: No feature or package to in"...
0x1800dcc27  mov     r8d, edi
0x1800dcc2a  xor     edx, edx
0x1800dcc2c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcc31  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcc38  lea     rax, [rbp+0A30h+var_404]
0x1800dcc3f  mov     [rbp+0A30h+var_8A8], rax
0x1800dcc46  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcc4d  lea     rax, [rbp+0A30h+var_8A8]
0x1800dcc54  mov     r8d, edi
0x1800dcc57  mov     dl, sil
0x1800dcc5a  mov     [rsp+0B30h+DirCount], rax
0x1800dcc5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcc64  mov     edx, 39Bh
0x1800dcc69  jmp     loc_1800DCBBA
0x1800dcc6e  cmp     [r14+0A4h], dil
0x1800dcc75  jz      short loc_1800DCCCA
0x1800dcc77  lea     rdx, [r14+58h]; struct _LUTF8_STRING *
0x1800dcc7b  mov     [rbp+0A30h+var_700], rdi
0x1800dcc82  lea     r8, [rbp+0A30h+var_700]; wchar_t **
0x1800dcc89  mov     rcx, r13; struct Windows::Rtl::IPoolAllocator *
0x1800dcc8c  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800dcc91  mov     ebx, eax
0x1800dcc93  test    eax, eax
0x1800dcc95  jns     short loc_1800DCCA4
0x1800dcc97  mov     r9d, eax
0x1800dcc9a  mov     edx, 3A1h
0x1800dcc9f  jmp     loc_1800DCBBD
0x1800dcca4  mov     rdx, [rbp+0A30h+var_700]
0x1800dccab  lea     rcx, [r15+8A8h]
0x1800dccb2  call    SczAllocFromSz
0x1800dccb7  mov     ebx, eax
0x1800dccb9  test    eax, eax
0x1800dccbb  jns     short loc_1800DCCCA
0x1800dccbd  mov     r9d, eax
0x1800dccc0  mov     edx, 3A2h
0x1800dccc5  jmp     loc_1800DCBBD
0x1800dccca  mov     rcx, r15; this
0x1800dcccd  call    ?IsFODRetryOperation@CCbsSession@@QEBA_NXZ; CCbsSession::IsFODRetryOperation(void)
0x1800dccd2  test    al, al
0x1800dccd4  jz      loc_1800DCD81
0x1800dccda  mov     rax, [r14+88h]
0x1800dcce1  mov     rcx, [rax]
0x1800dcce4  mov     [rbp+0A30h+var_2B0], rdi
0x1800dcceb  mov     [rbp+0A30h+var_438], rcx
0x1800dccf2  lea     rdx, [rbp+0A30h+var_2B0]
0x1800dccf9  lea     rcx, [rbp+0A30h+var_438]
0x1800dcd00  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcd05  test    al, al
0x1800dcd07  jz      short loc_1800DCD81
0x1800dcd09  mov     rdx, [rbp+0A30h+var_438]; struct _LUTF8_STRING *
0x1800dcd10  lea     r8, [rbp+0A30h+var_738]; wchar_t **
0x1800dcd17  mov     rcx, r13; struct Windows::Rtl::IPoolAllocator *
0x1800dcd1a  mov     [rbp+0A30h+var_738], rdi
0x1800dcd21  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800dcd26  mov     ebx, eax
0x1800dcd28  test    eax, eax
0x1800dcd2a  js      short loc_1800DCD74
0x1800dcd2c  lea     r8, [rbp+0A30h+var_738]
0x1800dcd33  mov     ecx, esi
0x1800dcd35  lea     rdx, aActionlistAddi_0; "ActionList: Adding FOD retry: {}"
0x1800dcd3c  call    ??$TraceAtLevel@PEA_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEA_W@Z; LogAdapter::TraceAtLevel<wchar_t *>(LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x1800dcd41  mov     rdx, [rbp+0A30h+var_738]; wchar_t *
0x1800dcd48  lea     rcx, [r15+6E0h]; this
0x1800dcd4f  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x1800dcd54  mov     ebx, eax
0x1800dcd56  test    eax, eax
0x1800dcd58  js      short loc_1800DCD67
0x1800dcd5a  mov     rax, [rbp+0A30h+var_438]
0x1800dcd61  mov     rcx, [rax+48h]
0x1800dcd65  jmp     short loc_1800DCCEB
0x1800dcd67  mov     r9d, eax
0x1800dcd6a  mov     edx, 3B4h
0x1800dcd6f  jmp     loc_1800DCBBD
0x1800dcd74  mov     r9d, eax
0x1800dcd77  mov     edx, 3B0h
0x1800dcd7c  jmp     loc_1800DCBBD
0x1800dcd81  mov     rax, [r14+98h]
0x1800dcd88  mov     bl, dil
0x1800dcd8b  mov     [rsp+0B30h+var_ABE], dil
0x1800dcd90  mov     r12b, dil
0x1800dcd93  mov     [rsp+0B30h+var_ABF], bl
0x1800dcd97  mov     rcx, [rax+38h]
0x1800dcd9b  mov     [rbp+0A30h+var_2A8], rdi
0x1800dcda2  mov     edi, 3
0x1800dcda7  mov     [rbp+0A30h+var_478], rcx
0x1800dcdae  lea     rdx, [rbp+0A30h+var_2A8]
0x1800dcdb5  lea     rcx, [rbp+0A30h+var_478]
0x1800dcdbc  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcdc1  test    al, al
0x1800dcdc3  jz      loc_1800DD355
0x1800dcdc9  mov     r14, [rbp+0A30h+var_478]
0x1800dcdd0  movzx   r12d, r12b
0x1800dcdd4  cmp     dword ptr [r14+88h], 4
0x1800dcddc  cmovz   r12d, esi
0x1800dcde0  mov     dl, dil
0x1800dcde3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@3@XZ@4V453@A; this
0x1800dcdea  call    ?IncludeNewline@DebuggerLogger@LogAdapter@@UEBA_NXZ; LogAdapter::DebuggerLogger::IncludeNewline(void)
0x1800dcdef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl(void)'::`2'::impl
0x1800dcdf6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(void)
0x1800dcdfb  xor     edx, edx
0x1800dcdfd  test    al, al
0x1800dcdff  jz      loc_1800DD048
0x1800dce05  mov     rdx, r14; struct ActionListParser::InstallPackage *
0x1800dce08  mov     rcx, r15; this
0x1800dce0b  call    ?IsWinPEServicingWithMultiPayloadRebaseLCU@CCbsSession@@QEAA_NPEAUInstallPackage@ActionListParser@@@Z; CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(ActionListParser::InstallPackage *)
0x1800dce10  xor     edx, edx
0x1800dce12  test    al, al
0x1800dce14  jnz     short loc_1800DCE48
0x1800dce16  test    r12b, r12b
0x1800dce19  jz      loc_1800DD133
0x1800dce1f  cmp     [r14+133h], dl
0x1800dce26  jz      loc_1800DD133
0x1800dce2c  cmp     dword ptr [r14+8Ch], 6
0x1800dce34  jnz     loc_1800DD133
0x1800dce3a  cmp     dword ptr [r14+88h], 4
0x1800dce42  jz      loc_1800DD133
0x1800dce48  xor     eax, eax
0x1800dce4a  mov     [rbp+0A30h+var_6B0], rdx
0x1800dce51  xorps   xmm0, xmm0
0x1800dce54  mov     [rbp+0A30h+var_6D0], rax
0x1800dce5b  xorps   xmm1, xmm1
0x1800dce5e  mov     [rbp+0A30h+var_6B8], rax
0x1800dce65  movups  [rbp+0A30h+var_6E0], xmm0
0x1800dce6c  mov     [rbp+0A30h+var_698], rax
0x1800dce73  movups  [rbp+0A30h+var_6C8], xmm1
0x1800dce7a  mov     [rbp+0A30h+var_680], rax
0x1800dce81  movups  [rbp+0A30h+var_6A8], xmm0
0x1800dce88  mov     [rbp+0A30h+var_668], rax
0x1800dce8f  movups  [rbp+0A30h+var_690], xmm1
0x1800dce96  mov     [rbp+0A30h+var_660], rdx
0x1800dce9d  movups  [rbp+0A30h+var_678], xmm0
0x1800dcea4  mov     [rbp+0A30h+var_658], rdx
0x1800dceab  cmp     [r14+108h], rdx
0x1800dceb2  jnz     loc_1800DCF39
0x1800dceb8  mov     al, [r14+131h]
0x1800dcebf  lea     rcx, [rbp+0A30h+var_6E0]
0x1800dcec6  mov     byte ptr [rbp+0A30h+var_658+3], al
0x1800dcecc  movups  xmm0, xmmword ptr [r14+28h]
0x1800dced1  movups  [rbp+0A30h+var_6A8], xmm0
0x1800dced8  movsd   xmm1, qword ptr [r14+38h]
0x1800dcede  movsd   [rbp+0A30h+var_698], xmm1
0x1800dcee6  mov     al, [r14+133h]
0x1800dceed  mov     byte ptr [rbp+0A30h+var_658+4], al
0x1800dcef3  movups  xmm0, xmmword ptr [r14+58h]
0x1800dcef8  movaps  [rbp+0A30h+var_690], xmm0
0x1800dceff  movsd   xmm1, qword ptr [r14+68h]
0x1800dcf05  movsd   [rbp+0A30h+var_680], xmm1
0x1800dcf0d  mov     al, [r14+134h]
0x1800dcf14  mov     byte ptr [rbp+0A30h+var_658+5], al
0x1800dcf1a  movups  xmm0, xmmword ptr [r14+70h]
0x1800dcf1f  movups  [rbp+0A30h+var_678], xmm0
0x1800dcf26  movsd   xmm1, qword ptr [r14+80h]
0x1800dcf2f  movsd   [rbp+0A30h+var_668], xmm1
0x1800dcf37  jmp     short loc_1800DCF40
0x1800dcf39  mov     rcx, [r14+100h]
0x1800dcf40  mov     [rbp+0A30h+var_2A0], rdx
0x1800dcf47  mov     [rbp+0A30h+var_480], rcx
0x1800dcf4e  lea     rdx, [rbp+0A30h+var_2A0]
0x1800dcf55  lea     rcx, [rbp+0A30h+var_480]
0x1800dcf5c  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcf61  xor     edx, edx
0x1800dcf63  test    al, al
  ... truncated ...
```
