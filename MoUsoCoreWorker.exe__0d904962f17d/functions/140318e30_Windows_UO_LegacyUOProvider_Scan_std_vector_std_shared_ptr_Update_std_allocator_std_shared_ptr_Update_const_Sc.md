# Windows::UO::LegacyUOProvider::Scan(std::vector<std::shared_ptr<Update>,std::allocator<std::shared_ptr<Update>>> const &,ScanParameters const &)

- ea: `0x140318e30`
- end: `0x14031c657`
- name: `?Scan@LegacyUOProvider@UO@Windows@@UEAA?AV?$optional@U?$pair@JV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@std@@@std@@@std@@AEBV?$vector@V?$shared_ptr@VUpdate@@@std@@V?$allocator@V?$shared_ptr@VUpdate@@@std@@@2@@5@AEBUScanParameters@@@Z`
- size: `14375`
- prototype: ``
- caller_count: `0`
- callee_count: `87`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140021110`
- `0x140021164`
- `0x140024de0`
- `0x1400289d4`
- `0x14002aaec`
- `0x14002ab0c`
- `0x14002b690`
- `0x14003c578`
- `0x140040184`
- `0x140040874`
- `0x140043284`
- `0x140043504`
- `0x1400447ac`
- `0x140045170`
- `0x14004519c`
- `0x1400453f4`
- `0x140045404`
- `0x14004573c`
- `0x140045790`
- `0x140045884`
- `0x1400459cc`
- `0x140045a8c`
- `0x140045b0c`
- `0x140045d90`
- `0x14004616c`
- `0x1400462a8`
- `0x140049bc8`
- `0x140049be0`
- `0x14004afa0`
- `0x140057a20`
- `0x140073568`
- `0x140077008`
- `0x1400772c4`
- `0x140077354`
- `0x1400773b4`
- `0x140079c7c`
- `0x14007be38`
- `0x1400a38a4`
- `0x1400a3b18`
- `0x1400a4bf8`
- `0x1400a5558`
- `0x1400a56f0`
- `0x1400a6160`
- `0x1400a7724`
- `0x1400a778c`
- `0x1400aa704`
- `0x1400aaabc`
- `0x1400affb8`
- `0x1400c8614`
- `0x1400d19d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14031b1de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14031b1de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14031c5a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14031c5a2`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x14031a3ce`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x14031a3ce`

## string_xrefs

- `0x14031c62b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14031c645`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140319bed`: `allowedPreOobeComplete`
- `0x140319896`: `updaterMinsToWaitAfterOobeFailure`
- `0x1403193b6`: `updaterPriority`
- `0x1403194ba`: `updaterPriority`
- `0x14031a2be`: `updaterOOBETimeoutInMinutes`
- `0x14031a923`: `updaterOOBETimeoutInMinutes`
- `0x14031aa67`: `updaterOOBETimeoutInMinutes`
- `0x14031b0be`: `updaterClientMetadata`
- `0x14031bab8`: `Legacy UO Updater: {} ignored because it is disabled`
- `0x14031bb83`: `Legacy UO Updater: {} ignored because it was completed`
- `0x14031c611`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\LegacyUOProvider.cpp`
- `0x14031bd41`: `StoreProvider active during scan`
- `0x14031ac2a`: `%windir%\system32\usoclient.exe`
- `0x14031af4f`: `oemExpeditedUpdate`
- `0x14031bea3`: `oemExpeditedUpdate`
- `0x14031b7e1`: `StartOobeAppsScan_OobeAppReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=107 #try_helpers=1
_DWORD *__fastcall Windows::UO::LegacyUOProvider::Scan(
        Windows::UO::LegacyUOProvider *a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4)
{
  Windows::UO::LegacyUOProvider *v5; // rdi
  int v6; // r12d
  _QWORD *v7; // rax
  __int64 System; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  char v12; // bl
  void (__fastcall *v13)(_QWORD, __int128 *, __int128 *, __int128 *); // r11
  __int64 v14; // rax
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  _QWORD *v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rsi
  unsigned __int8 (__fastcall *v20)(_QWORD, WCHAR *, __int64 *); // r9
  _QWORD *v21; // rax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rax
  void (__fastcall *v26)(_QWORD, __int128 *, __int128 *, WCHAR *, __int64 *); // r11
  _QWORD *v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  void (__fastcall *v32)(__int64, _DWORD *, WCHAR *, __int64 *, __int128 *); // r14
  __int128 *v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rbx
  void (__fastcall *v37)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  unsigned int v38; // eax
  __int128 *v39; // rdx
  _QWORD *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r14
  __int64 (__fastcall *v46)(__int64, __int128 *, __int64); // rbx
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rbx
  _OWORD *v51; // rdx
  _QWORD *v52; // rax
  __int64 v53; // rax
  __int64 *v54; // rbx
  __int64 *v55; // rax
  __int64 v56; // rcx
  int v57; // r12d
  __int64 *v58; // rcx
  __int64 v59; // rbx
  int v60; // r12d
  __int64 *v61; // rcx
  __int64 v62; // rbx
  _QWORD *v63; // rdx
  __int64 v64; // r8
  __int64 *v65; // rbx
  __int64 *v66; // rax
  __int64 v67; // rcx
  _QWORD *v68; // rax
  char v69; // al
  __int64 *v70; // r14
  int v71; // r12d
  __int64 v72; // rbx
  __int64 *v73; // rax
  __int64 *v74; // rcx
  __int64 v75; // rax
  _QWORD *v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 *v79; // rbx
  int v80; // r12d
  __int64 *v81; // rax
  __int64 v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 *v86; // rbx
  int v87; // r12d
  __int64 *v88; // rax
  __int64 v89; // rcx
  int v90; // r8d
  unsigned int v91; // eax
  int v92; // r12d
  __int64 *v93; // rcx
  __int64 v94; // rbx
  int v95; // r8d
  unsigned int v96; // eax
  __int64 *v97; // rcx
  __int64 v98; // rbx
  char v99; // bl
  const char *v100; // r9
  const struct web::json::value *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // rcx
  void (__fastcall *v107)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v108; // rax
  __int64 v109; // rdx
  __int64 v110; // rax
  __int128 *v111; // rdx
  __int64 v112; // rcx
  _QWORD *v113; // rax
  _QWORD *v114; // rax
  web::json::value *v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  web::json::value *v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int128 v121; // xmm6
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // r8
  __int64 v125; // r9
  web::json::value *v126; // rax
  char v127; // bl
  _QWORD *v128; // rax
  unsigned int v129; // eax
  _QWORD *v130; // rax
  __int64 v131; // r14
  _QWORD *v132; // rax
  __int64 v133; // rbx
  _QWORD *v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rcx
  __int64 v138; // rax
  __int64 v139; // rbx
  void (__fastcall *v140)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  __int128 *v141; // rdx
  _QWORD *v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rcx
  __int64 v146; // rax
  __int64 v147; // rbx
  void (__fastcall *v148)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  __int128 *v149; // rax
  __int128 *v150; // rdx
  _QWORD *v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rcx
  __int64 v155; // rbx
  __int128 *v156; // rdx
  _QWORD *v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rcx
  __int64 v161; // rax
  __int64 v162; // rbx
  void (__fastcall *v163)(__int64, WCHAR *, __int64 *, __int128 *, __int128 *); // r14
  __int64 v164; // rax
  __int128 *v165; // rdx
  _QWORD *v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rcx
  __int64 v170; // rax
  __int64 v171; // rcx
  void (__fastcall *v172)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v173; // rax
  __int64 v174; // rdx
  _QWORD *v175; // rcx
  __int64 v176; // rax
  __int64 v177; // rax
  __int64 v178; // rcx
  __int64 v179; // rax
  __int64 v180; // rbx
  __int64 (__fastcall *v181)(__int64, WCHAR *, __int64 *, __int128 *); // r14
  __int128 *v182; // r8
  _QWORD *v183; // rax
  __int64 v184; // rdx
  char v185; // al
  char v186; // bl
  __int64 v187; // rax
  __int64 v188; // rcx
  __int64 v189; // rax
  __int64 v190; // rcx
  void (__fastcall *v191)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v192; // rax
  __int64 v193; // rdx
  const char *v194; // r9
  __int64 v195; // rax
  __int64 v196; // rcx
  void (__fastcall *v197)(__int64, __int128 *); // rbx
  _BYTE *traits_2_unsigned_short; // rax
  const char *v199; // r9
  __int64 v200; // r11
  __int64 v201; // rax
  volatile signed __int32 *v202; // rbx
  volatile signed __int32 *v203; // rbx
  void (__fastcall *v204)(_QWORD, __int128 *, __int128 *, __int128 *); // r11
  __int64 v205; // rax
  __int64 v206; // rdx
  int v207; // r9d
  _QWORD *v208; // rsi
  __int64 v209; // rcx
  _QWORD *v210; // rax
  char v211; // al
  volatile signed __int32 *v212; // rbx
  Windows::UO::LegacyUOUpdate *v213; // r14
  _QWORD *v214; // rax
  __int64 v215; // rcx
  _QWORD *v216; // rax
  bool v217; // zf
  _QWORD *v218; // rax
  _QWORD *v219; // rcx
  void *v220; // rax
  const char *v221; // r9
  __int64 v222; // r11
  __int64 v223; // rax
  __int128 *v224; // rax
  Windows::UO::LegacyUOProvider *v225; // rcx
  char v226; // bl
  __int64 v227; // rax
  __int64 v228; // rcx
  __int64 v229; // rax
  __int64 v230; // rdi
  void (__fastcall *v231)(__int64, __int128 *, __int128 *); // rbx
  __int128 v232; // xmm6
  __int128 *v233; // rax
  __int64 v234; // rax
  __int64 v235; // rcx
  __int64 v236; // rbx
  __int128 *v237; // rdx
  _QWORD *v238; // rax
  __int64 v239; // rax
  char SystemBoolOrDefault; // bl
  __int64 v241; // rcx
  _QWORD *v242; // rax
  __int64 v243; // r8
  __int64 v244; // r9
  __int64 v245; // rdi
  __int64 *v246; // rax
  __int64 v247; // rdx
  __int64 v248; // rbx
  __int64 i; // rcx
  __int64 v250; // rax
  __int64 v251; // rcx
  _QWORD *v252; // rax
  _DWORD *v253; // rbx
  __int64 v254; // rdi
  __int64 v255; // rax
  int v256; // eax
  char v257; // di
  __int64 v258; // rax
  __int64 v259; // rax
  volatile signed __int32 *v260; // rbx
  __int64 *v261; // rbx
  __int64 v262; // rax
  __int64 v263; // rax
  volatile signed __int32 *v264; // rdi
  __int64 v265; // rdx
  volatile signed __int32 *v266; // rsi
  __int64 *v267; // rax
  __int64 *j; // rax
  char *v269; // rdx
  void *v270; // rcx
  void *v271; // rcx
  __int64 v272; // rdx
  __int64 v273; // rcx
  __int64 v274; // rax
  _DWORD *v275; // rdi
  volatile signed __int32 *v276; // rbx
  __int64 v277; // rcx
  int v279; // [rsp+40h] [rbp-8C8h]
  __int128 v280; // [rsp+50h] [rbp-8B8h] BYREF
  __int64 v281; // [rsp+60h] [rbp-8A8h]
  __int64 v282; // [rsp+68h] [rbp-8A0h]
  __int64 v283[2]; // [rsp+70h] [rbp-898h] BYREF
  __int64 v284; // [rsp+80h] [rbp-888h]
  __int64 v285; // [rsp+88h] [rbp-880h]
  __int128 v286; // [rsp+90h] [rbp-878h] BYREF
  __int64 v287; // [rsp+A0h] [rbp-868h]
  unsigned __int64 v288; // [rsp+A8h] [rbp-860h]
  __int128 v289; // [rsp+B0h] [rbp-858h] BYREF
  int v290; // [rsp+C0h] [rbp-848h]
  Windows::UO::LegacyUOProvider *v291; // [rsp+C8h] [rbp-840h]
  char v292; // [rsp+D0h] [rbp-838h]
  _QWORD *v293; // [rsp+D8h] [rbp-830h]
  __int128 v294; // [rsp+E0h] [rbp-828h] BYREF
  _DWORD v295[8]; // [rsp+F0h] [rbp-818h] BYREF
  char v296; // [rsp+110h] [rbp-7F8h]
  __int128 v297; // [rsp+118h] [rbp-7F0h] BYREF
  __int64 v298; // [rsp+128h] [rbp-7E0h]
  __int64 v299; // [rsp+130h] [rbp-7D8h]
  __int128 v300; // [rsp+140h] [rbp-7C8h] BYREF
  __int64 v301; // [rsp+150h] [rbp-7B8h] BYREF
  __int64 v302; // [rsp+158h] [rbp-7B0h] BYREF
  __int128 v303; // [rsp+160h] [rbp-7A8h] BYREF
  _DWORD *v304; // [rsp+170h] [rbp-798h] BYREF
  __int128 v305; // [rsp+180h] [rbp-788h] BYREF
  __int64 v306; // [rsp+190h] [rbp-778h] BYREF
  __int64 v307; // [rsp+198h] [rbp-770h] BYREF
  __int64 v308; // [rsp+1A0h] [rbp-768h] BYREF
  __int64 v309; // [rsp+1A8h] [rbp-760h] BYREF
  _QWORD *v310; // [rsp+1B0h] [rbp-758h]
  LPVOID pv; // [rsp+1B8h] [rbp-750h] BYREF
  _DWORD *v312; // [rsp+1C0h] [rbp-748h]
  __int128 v313; // [rsp+1D0h] [rbp-738h] BYREF
  __int128 v314; // [rsp+1E0h] [rbp-728h] BYREF
  __int128 v315; // [rsp+1F0h] [rbp-718h]
  char v316; // [rsp+200h] [rbp-708h]
  __int128 v317; // [rsp+210h] [rbp-6F8h]
  __int128 v318; // [rsp+220h] [rbp-6E8h]
  __int128 v319; // [rsp+230h] [rbp-6D8h]
  __int128 v320; // [rsp+240h] [rbp-6C8h]
  __int128 v321; // [rsp+250h] [rbp-6B8h]
  __int128 v322; // [rsp+260h] [rbp-6A8h]
  __int128 v323; // [rsp+270h] [rbp-698h]
  __int128 v324; // [rsp+280h] [rbp-688h]
  Windows::UO::LegacyUOProvider *v325; // [rsp+290h] [rbp-678h]
  __int128 v326; // [rsp+2A0h] [rbp-668h]
  __int128 v327; // [rsp+2B0h] [rbp-658h]
  char v328[8]; // [rsp+2C0h] [rbp-648h] BYREF
  volatile signed __int32 *v329; // [rsp+2C8h] [rbp-640h]
  __int128 v330; // [rsp+2D0h] [rbp-638h] BYREF
  _BYTE v331[16]; // [rsp+2E0h] [rbp-628h] BYREF
  __int64 v332; // [rsp+2F0h] [rbp-618h] BYREF
  _BYTE v333[16]; // [rsp+2F8h] [rbp-610h] BYREF
  __int64 v334; // [rsp+308h] [rbp-600h] BYREF
  __int64 v335; // [rsp+310h] [rbp-5F8h] BYREF
  __int64 v336; // [rsp+318h] [rbp-5F0h] BYREF
  __int64 v337; // [rsp+320h] [rbp-5E8h] BYREF
  _BYTE v338[16]; // [rsp+328h] [rbp-5E0h] BYREF
  __int128 v339; // [rsp+338h] [rbp-5D0h]
  __int128 v340; // [rsp+350h] [rbp-5B8h]
  __int128 v341; // [rsp+360h] [rbp-5A8h]
  __int128 v342; // [rsp+370h] [rbp-598h]
  __int128 v343; // [rsp+380h] [rbp-588h]
  __int128 v344; // [rsp+390h] [rbp-578h]
  __int128 v345; // [rsp+3A0h] [rbp-568h]
  __int128 v346; // [rsp+3B0h] [rbp-558h]
  __int128 v347; // [rsp+3C0h] [rbp-548h]
  __int128 v348; // [rsp+3D0h] [rbp-538h]
  __int128 v349; // [rsp+3E0h] [rbp-528h]
  __int128 v350; // [rsp+3F0h] [rbp-518h]
  __int128 v351; // [rsp+400h] [rbp-508h]
  __int128 v352; // [rsp+410h] [rbp-4F8h]
  __int128 v353; // [rsp+420h] [rbp-4E8h]
  __int128 v354; // [rsp+430h] [rbp-4D8h]
  __int128 v355; // [rsp+440h] [rbp-4C8h]
  __int128 v356; // [rsp+450h] [rbp-4B8h]
  __int128 v357; // [rsp+460h] [rbp-4A8h]
  __int128 v358; // [rsp+470h] [rbp-498h]
  __int128 v359; // [rsp+480h] [rbp-488h] BYREF
  __int64 v360; // [rsp+490h] [rbp-478h]
  __int64 v361; // [rsp+498h] [rbp-470h]
  __int128 v362; // [rsp+4A0h] [rbp-468h]
  __int128 v363; // [rsp+4B0h] [rbp-458h]
  _BYTE v364[32]; // [rsp+4C0h] [rbp-448h] BYREF
  _BYTE v365[32]; // [rsp+4E0h] [rbp-428h] BYREF
  __int128 v366; // [rsp+500h] [rbp-408h]
  __int128 v367; // [rsp+510h] [rbp-3F8h]
  _BYTE v368[32]; // [rsp+520h] [rbp-3E8h] BYREF
  _BYTE v369[16]; // [rsp+540h] [rbp-3C8h] BYREF
  _BYTE v370[16]; // [rsp+550h] [rbp-3B8h] BYREF
  _BYTE v371[16]; // [rsp+560h] [rbp-3A8h] BYREF
  _BYTE v372[16]; // [rsp+570h] [rbp-398h] BYREF
  _BYTE v373[16]; // [rsp+580h] [rbp-388h] BYREF
  _BYTE v374[16]; // [rsp+590h] [rbp-378h] BYREF
  _BYTE v375[16]; // [rsp+5A0h] [rbp-368h] BYREF
  _BYTE v376[16]; // [rsp+5B0h] [rbp-358h] BYREF
  _BYTE v377[16]; // [rsp+5C0h] [rbp-348h] BYREF
  _BYTE v378[16]; // [rsp+5D0h] [rbp-338h] BYREF
  _BYTE v379[16]; // [rsp+5E0h] [rbp-328h] BYREF
  _BYTE v380[16]; // [rsp+5F0h] [rbp-318h] BYREF
  char v381[16]; // [rsp+600h] [rbp-308h] BYREF
  _BYTE v382[16]; // [rsp+610h] [rbp-2F8h] BYREF
  char v383[16]; // [rsp+620h] [rbp-2E8h] BYREF
  _BYTE v384[16]; // [rsp+630h] [rbp-2D8h] BYREF
  _BYTE v385[16]; // [rsp+640h] [rbp-2C8h] BYREF
  _BYTE v386[16]; // [rsp+650h] [rbp-2B8h] BYREF
  _BYTE v387[16]; // [rsp+660h] [rbp-2A8h] BYREF
  char v388[16]; // [rsp+670h] [rbp-298h] BYREF
  char v389[16]; // [rsp+680h] [rbp-288h] BYREF
  char v390[16]; // [rsp+690h] [rbp-278h] BYREF
  char v391[16]; // [rsp+6A0h] [rbp-268h] BYREF
  char v392[16]; // [rsp+6B0h] [rbp-258h] BYREF
  char v393[16]; // [rsp+6C0h] [rbp-248h] BYREF
  char v394[16]; // [rsp+6D0h] [rbp-238h] BYREF
  char v395[16]; // [rsp+6E0h] [rbp-228h] BYREF
  char v396[16]; // [rsp+6F0h] [rbp-218h] BYREF
  char v397[16]; // [rsp+700h] [rbp-208h] BYREF
  char v398[16]; // [rsp+710h] [rbp-1F8h] BYREF
  _QWORD Src[2]; // [rsp+720h] [rbp-1E8h] BYREF
  __int64 v400; // [rsp+730h] [rbp-1D8h]
  unsigned __int64 v401; // [rsp+738h] [rbp-1D0h]
  __int128 v402; // [rsp+740h] [rbp-1C8h] BYREF
  WCHAR geoName[8]; // [rsp+750h] [rbp-1B8h] BYREF
  __int64 v404; // [rsp+760h] [rbp-1A8h]
  __int64 v405; // [rsp+768h] [rbp-1A0h]
  __int64 v406; // [rsp+770h] [rbp-198h] BYREF
  void *Block[2]; // [rsp+778h] [rbp-190h] BYREF
  __int128 v408; // [rsp+788h] [rbp-180h] BYREF
  __int64 v409; // [rsp+798h] [rbp-170h]
  Windows::UO::LegacyUOUpdate *v410; // [rsp+7A0h] [rbp-168h] BYREF
  volatile signed __int32 *v411; // [rsp+7A8h] [rbp-160h]
  char v412; // [rsp+7B0h] [rbp-158h]
  __int128 v413; // [rsp+7B8h] [rbp-150h] BYREF
  __int64 v414; // [rsp+7C8h] [rbp-140h] BYREF
  _QWORD v415[2]; // [rsp+7D0h] [rbp-138h] BYREF
  __int64 v416; // [rsp+7E0h] [rbp-128h]
  unsigned __int64 v417; // [rsp+7E8h] [rbp-120h]
  _DWORD v418[8]; // [rsp+7F0h] [rbp-118h] BYREF
  __int64 v419; // [rsp+810h] [rbp-F8h]
  volatile signed __int32 *v420; // [rsp+818h] [rbp-F0h]
  __int128 v421; // [rsp+820h] [rbp-E8h] BYREF
  __int64 v422; // [rsp+830h] [rbp-D8h]
  __int128 v423; // [rsp+838h] [rbp-D0h] BYREF
  __int64 v424; // [rsp+848h] [rbp-C0h]
  unsigned __int64 v425; // [rsp+850h] [rbp-B8h]
  __int128 v426; // [rsp+858h] [rbp-B0h] BYREF
  __int64 v427; // [rsp+868h] [rbp-A0h]
  _BYTE v428[16]; // [rsp+870h] [rbp-98h] BYREF
  __int64 v429; // [rsp+880h] [rbp-88h]
  __int128 v430; // [rsp+890h] [rbp-78h] BYREF
  __int64 v431; // [rsp+8A0h] [rbp-68h]
  _BYTE v432[24]; // [rsp+8A8h] [rbp-60h] BYREF
  char v433; // [rsp+8C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+0h]

  v312 = a2;
  v5 = a1;
  v291 = a1;
  v325 = a1;
  v304 = a2;
  v6 = 0;
  v279 = 0;
  v290 = 0;
  Block[1] = 0;
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(80);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  Block[0] = v7;
  std::lock_guard<std::mutex>::lock_guard<std::mutex>(&v336, (char *)v5 + 128);
  v430 = 0;
  v431 = 0;
  Windows::UO::GetAllowedOobeUpdaters(&v430);
  Windows::UO::GetBlockedOobeUpdaters(v432);
  v413 = 0;
  System = SystemInterface::Providers::GetSystem(v382);
  v9 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 32LL))(v9, &v413);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v382);
  if ( !*(_BYTE *)(a4 + 3)
    || (v10 = SystemInterface::Providers::GetSystem(&v294),
        v6 = 1,
        v279 = 1,
        v11 = *(_QWORD *)v10 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 4LL),
        v12 = 1,
        (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 168LL))(v11)) )
  {
    v12 = 0;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    v279 = v6;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v294);
  }
  if ( v12 )
  {
    v421 = 0;
    v422 = 0;
    v13 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v413 + 88LL);
    v14 = -1;
    do
      ++v14;
    while ( SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT[v14] );
    v283[0] = (__int64)SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT;
    v283[1] = v14;
    *(_QWORD *)&v313 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
    v15 = -1;
    do
      ++v15;
    while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v15] );
    *((_QWORD *)&v313 + 1) = v15;
    v294 = *(_OWORD *)v283;
    v305 = v313;
    v13(v413, &v421, &v305, &v294);
    v16 = (_QWORD *)*((_QWORD *)&v421 + 1);
    v310 = (_QWORD *)*((_QWORD *)&v421 + 1);
    v17 = (_QWORD *)v421;
    v18 = v301;
    v19 = v302;
    while ( 1 )
    {
      v293 = v17;
      if ( v17 == v16 )
      {
        try
        {
          v5 = v291;
          Windows::UO::LegacyUOProvider::StageConfigBasedExpeditedUpdaters(v291);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x195,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
            v194);
          v6 = v279;
          v5 = v325;
          v291 = v325;
          v312 = v304;
        }
        v195 = SystemInterface::Providers::GetSystem(v328);
        v196 = *(_QWORD *)v195 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v195 + 8LL) + 4LL);
        v197 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v196 + 24LL))(
                                                                           v196,
                                                                           &v300)
                                                          + 40LL);
        traits_2_unsigned_short = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                             L"StartOobeAppsScan_OobeAppReady",
                                             &unk_14047F996,
                                             0);
        if ( traits_2_unsigned_short == (_BYTE *)&unk_14047F996
          || (v201 = (traits_2_unsigned_short - (_BYTE *)L"StartOobeAppsScan_OobeAppReady") >> 1, v201 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v199);
        }
        *(_QWORD *)&v294 = L"StartOobeAppsScan_OobeAppReady";
        *((_QWORD *)&v294 + 1) = v201;
        v289 = v294;
        v197(v200, &v289);
        v202 = (volatile signed __int32 *)*((_QWORD *)&v300 + 1);
        if ( *((_QWORD *)&v300 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v300 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v202)(v202);
            if ( _InterlockedExchangeAdd(v202 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v202 + 8LL))(v202);
          }
        }
        v203 = v329;
        if ( v329 )
        {
          if ( _InterlockedExchangeAdd(v329 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v203)(v203);
            if ( _InterlockedExchangeAdd(v203 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v203 + 8LL))(v203);
          }
        }
        std::vector<std::filesystem::path>::_Tidy(&v421);
        break;
      }
      *(_QWORD *)&v353 = L"{}\\{}";
      *((_QWORD *)&v353 + 1) = 5;
      *(_OWORD *)v283 = v353;
      std::format<wchar_t const * const &,std::wstring const &>(Src);
      v20 = *(unsigned __int8 (__fastcall **)(_QWORD, WCHAR *, __int64 *))(*(_QWORD *)v413 + 8LL);
      v21 = Src;
      if ( v401 > 7 )
        v21 = (_QWORD *)Src[0];
      *(_QWORD *)&v354 = v21;
      *((_QWORD *)&v354 + 1) = v400;
      *(_QWORD *)&v355 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v22 = -1;
      do
        ++v22;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v22] );
      *((_QWORD *)&v355 + 1) = v22;
      *(_OWORD *)v283 = v354;
      *(_OWORD *)geoName = v355;
      if ( v20(v413, geoName, v283) )
      {
        v23 = Src;
        if ( v401 > 7 )
          v23 = (_QWORD *)Src[0];
        *(_QWORD *)&v356 = v23;
        *((_QWORD *)&v356 + 1) = v400;
        v24 = v17[2];
        v25 = v17;
        if ( v17[3] > 7u )
          v25 = (_QWORD *)*v17;
        *(_QWORD *)&v357 = v25;
        *((_QWORD *)&v357 + 1) = v24;
        *(_OWORD *)v283 = v356;
        *(_OWORD *)geoName = v357;
        if ( !(unsigned __int8)Windows::UO::LegacyUOProvider::ShouldRecoverStoreExpeditedRegistration(
                                 v291,
                                 geoName,
                                 &v413,
                                 v283) )
          goto LABEL_245;
      }
      *(_QWORD *)&v358 = L"{}\\{}";
      *((_QWORD *)&v358 + 1) = 5;
      *(_OWORD *)v283 = v358;
      std::format<wchar_t const * const &,std::wstring const &>(v415);
      v26 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, WCHAR *, __int64 *))(*(_QWORD *)v413 + 104LL);
      v27 = Src;
      if ( v401 > 7 )
        v27 = (_QWORD *)Src[0];
      *(_QWORD *)&v362 = v27;
      *((_QWORD *)&v362 + 1) = v400;
      v28 = -1;
      do
        ++v28;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v28] );
      *(_QWORD *)&v363 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      *((_QWORD *)&v363 + 1) = v28;
      v29 = v415;
      if ( v417 > 7 )
        v29 = (_QWORD *)v415[0];
      *(_QWORD *)&v366 = v29;
      *((_QWORD *)&v366 + 1) = v416;
      *(_QWORD *)&v367 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
      v30 = -1;
      do
        ++v30;
      while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v30] );
      *((_QWORD *)&v367 + 1) = v30;
      *(_OWORD *)v283 = v362;
      *(_OWORD *)geoName = v363;
      v402 = v366;
      v280 = v367;
      v26(v413, &v280, &v402, geoName, v283);
      v31 = v413;
      v32 = *(void (__fastcall **)(__int64, _DWORD *, WCHAR *, __int64 *, __int128 *))(*(_QWORD *)v413 + 56LL);
      v33 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v394, L"updaterPriority");
      v34 = Src;
      if ( v401 > 7 )
        v34 = (_QWORD *)Src[0];
      *(_QWORD *)&v339 = v34;
      *((_QWORD *)&v339 + 1) = v400;
      *(_QWORD *)&v340 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v35 = -1;
      do
        ++v35;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v35] );
      *((_QWORD *)&v340 + 1) = v35;
      v280 = *v33;
      *(_OWORD *)v283 = v339;
      *(_OWORD *)geoName = v340;
      v32(v31, v418, geoName, v283, &v280);
      v36 = v413;
      v37 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(*(_QWORD *)v413 + 64LL);
      if ( !(_BYTE)v420 || (_BYTE)v419 || (v38 = v418[0], v418[0] > 0x64u) )
        v38 = Windows::UO::LegacyUOProvider::sc_defaultUpdaterPriority;
      v295[0] = v38;
      v296 = 0;
      v39 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v395, L"updaterPriority");
      v40 = Src;
      if ( v401 > 7 )
        v40 = (_QWORD *)Src[0];
      *(_QWORD *)&v341 = v40;
      *((_QWORD *)&v341 + 1) = v400;
      *(_QWORD *)&v342 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v41 = -1;
      do
        ++v41;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v41] );
      *((_QWORD *)&v342 + 1) = v41;
      v280 = *v39;
      *(_OWORD *)v283 = v341;
      *(_OWORD *)geoName = v342;
      v37(v36, geoName, v283, &v280, v295);
      if ( v296 != -1 && v296 && v296 != 1 )
        std::wstring::~wstring(v295);
      v42 = SystemInterface::Providers::GetSystem(v378);
      v43 = *(_QWORD *)v42 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v42 + 8LL) + 4LL);
      v44 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v43 + 40LL))(v43, v379);
      v45 = *(_QWORD *)v44;
      v46 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v44 + 64LL);
      v280 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                          v396,
                          L"SupportsThirdPartyExpedite");
      LOBYTE(v47) = 1;
      LOBYTE(v46) = v46(v45, &v280, v47);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v379);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v378);
      if ( (_BYTE)v46 )
      {
        v48 = SystemInterface::Providers::GetSystem(v384);
        v49 = *(_QWORD *)v48 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v48 + 8LL) + 4LL);
        v50 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v377);
        v359 = 0;
        v360 = 0;
        v361 = 7;
        LOWORD(v359) = 0;
        *(_QWORD *)&v343 = &v359;
        *((_QWORD *)&v343 + 1) = 0;
        v51 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v397, L"expeditedPayload");
        v52 = Src;
        if ( v401 > 7 )
          v52 = (_QWORD *)Src[0];
        *(_QWORD *)&v344 = v52;
        *((_QWORD *)&v344 + 1) = v400;
        *(_QWORD *)&v352 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v53 = -1;
        do
          ++v53;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v53] );
        *((_QWORD *)&v352 + 1) = v53;
        v280 = v343;
        *(_OWORD *)v283 = *v51;
        *(_OWORD *)geoName = v344;
        v402 = v352;
        SystemInterface::Registry::GetSystemValueOrDefault(
          v50,
          (unsigned int)v428,
          (unsigned int)&v402,
          (unsigned int)geoName,
          (__int64)v283,
          (__int64)&v280);
        std::wstring::~wstring(&v359);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v377);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v384);
        if ( v429 )
        {
          *(_QWORD *)&v402 = 0;
          web::json::value::object(&v402);
          v54 = (__int64 *)web::json::value::object(&v335);
          v280 = 0;
          v281 = 0;
          v282 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v280, L"NdupProperties");
          v55 = (__int64 *)web::json::value::operator[](&v402, &v280);
          if ( v55 != v54 )
          {
            v56 = *v55;
            *v55 = *v54;
            *v54 = v56;
          }
          std::wstring::~wstring(&v280);
          if ( v335 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v335 + 192LL))(v335, 1);
          web::json::value::value((web::json::value *)&v306, 30);
          v57 = v6 | 0x4000000;
          v280 = 0;
          v281 = 0;
          v282 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v280, L"updaterMinsToWaitAfterOobeFailure");
          v58 = (__int64 *)web::json::value::operator[](&v402, &v280);
          if ( v58 == &v306 )
          {
            v59 = v306;
          }
          else
          {
            v59 = *v58;
            *v58 = v306;
            v306 = v59;
          }
          std::wstring::~wstring(&v280);
          if ( v59 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v59 + 192LL))(v59, 1);
          web::json::value::value((web::json::value *)&v307, 1);
          v60 = v57 | 0x8000000;
          v280 = 0;
          v281 = 0;
          v282 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v280, L"BusinessCritical");
          v61 = (__int64 *)web::json::value::operator[](&v402, &v280);
          if ( v61 == &v307 )
          {
            v62 = v307;
          }
          else
          {
            v62 = *v61;
            *v61 = v307;
            v307 = v62;
          }
          std::wstring::~wstring(&v280);
          if ( v62 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 192LL))(v62, 1);
          v63 = v293;
          if ( v293[3] > 7u )
            v63 = (_QWORD *)*v293;
          v280 = 0;
          v281 = 0;
          v282 = 0;
          v64 = -1;
          do
            ++v64;
          while ( *((_WORD *)v63 + v64) );
          std::wstring::_Construct<1,wchar_t const *>(&v280, v63);
          v65 = (__int64 *)web::json::value::string(&v337, &v280);
          *(_OWORD *)geoName = 0;
          v404 = 0;
          v405 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"id");
          v66 = (__int64 *)web::json::value::operator[](&v402, geoName);
          if ( v66 != v65 )
          {
            v67 = *v66;
            *v66 = *v65;
            *v65 = v67;
          }
          std::wstring::~wstring(geoName);
          if ( v337 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v337 + 192LL))(v337, 1);
          v406 = 0;
          web::json::value::parse(&v406, v428);
          *(_OWORD *)geoName = 0;
          v404 = 0;
          v405 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"AllowedInOobe");
          if ( (*(unsigned __int8 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v406 + 8LL))(v406, geoName) )
          {
            *(_OWORD *)v283 = 0;
            v284 = 0;
            v285 = 0;
            std::wstring::_Construct<1,wchar_t const *>(v283, L"AllowedInOobe");
            v68 = (_QWORD *)web::json::value::at(&v406, v283);
            v69 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v68 + 136LL))(*v68);
            web::json::value::value((web::json::value *)&v301, v69);
            v290 |= 1u;
            v70 = &v301;
            v71 = v60 | 6;
            v18 = v301;
            v72 = v301;
          }
          else
          {
            web::json::value::value((web::json::value *)&v302, 0);
            v290 |= 2u;
            v70 = &v302;
            v71 = v60 | 8;
            v19 = v302;
            v72 = v302;
          }
          v280 = 0;
          v281 = 0;
          v282 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v280, L"allowedPreOobeComplete");
          v73 = (__int64 *)web::json::value::operator[](&v402, &v280);
          v74 = v73;
          if ( v73 != v70 )
          {
            v75 = *v73;
            *v74 = v72;
            *v70 = v75;
            v18 = v301;
            v19 = v302;
          }
          std::wstring::~wstring(&v280);
          if ( (v71 & 8) != 0 )
          {
            v71 &= ~8u;
            if ( v19 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 192LL))(v19, 1);
          }
          if ( (v71 & 4) != 0 )
          {
            v71 &= ~4u;
            if ( v18 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 192LL))(v18, 1);
          }
          if ( (v71 & 2) != 0 )
          {
            v71 &= ~2u;
            std::wstring::~wstring(v283);
          }
          std::wstring::~wstring(geoName);
          v286 = 0;
          v287 = 0;
          v288 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v286, L"PFN");
          if ( (*(unsigned __int8 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v406 + 8LL))(v406, &v286) )
          {
            v297 = 0;
            v298 = 0;
            v299 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v297, L"PFN");
            v76 = (_QWORD *)web::json::value::at(&v406, &v297);
            v77 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v76 + 176LL))(*v76);
            v78 = std::wstring::wstring(v295, v77);
            v79 = (__int64 *)web::json::value::string(&v332, v78);
            v80 = v71 | 0x30;
          }
          else
          {
            v280 = 0;
            v281 = 0;
            v282 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v280, &psz);
            v79 = (__int64 *)web::json::value::string(&v334, &v280);
            v80 = v71 | 0x40;
          }
          *(_OWORD *)geoName = 0;
          v404 = 0;
          v405 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"PFN");
          v81 = (__int64 *)web::json::value::operator[](&v402, geoName);
          if ( v81 != v79 )
          {
            v82 = *v81;
            *v81 = *v79;
            *v79 = v82;
          }
          std::wstring::~wstring(geoName);
          if ( (v80 & 0x40) != 0 )
          {
            v80 &= ~0x40u;
            if ( v334 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v334 + 192LL))(v334, 1);
          }
          if ( (v80 & 0x20) != 0 )
          {
            v80 &= ~0x20u;
            if ( v332 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v332 + 192LL))(v332, 1);
          }
          if ( (v80 & 0x10) != 0 )
          {
            v80 &= ~0x10u;
            std::wstring::~wstring(&v297);
          }
          std::wstring::~wstring(&v286);
          *(_OWORD *)geoName = 0;
          v404 = 0;
          v405 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"Endpoint");
          if ( (*(unsigned __int8 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v406 + 8LL))(v406, geoName) )
          {
            v280 = 0;
            v281 = 0;
            v282 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v280, L"Endpoint");
            v83 = (_QWORD *)web::json::value::at(&v406, &v280);
            v84 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v83 + 176LL))(*v83);
            v85 = std::wstring::wstring(v295, v84);
            v86 = (__int64 *)web::json::value::string(&v313, v85);
            v87 = v80 | 0x180;
          }
          else
          {
            v286 = 0;
            v287 = 0;
            v288 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v286, &psz);
            v86 = (__int64 *)web::json::value::string(&v303, &v286);
            v87 = v80 | 0x200;
          }
          v297 = 0;
          v298 = 0;
          v299 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v297, L"Endpoint");
          v88 = (__int64 *)web::json::value::operator[](&v402, &v297);
          if ( v88 != v86 )
          {
            v89 = *v88;
            *v88 = *v86;
            *v86 = v89;
          }
          std::wstring::~wstring(&v297);
          if ( (v87 & 0x200) != 0 )
          {
            v87 &= ~0x200u;
            if ( (_QWORD)v303 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v303 + 192LL))(v303, 1);
          }
          if ( (v87 & 0x100) != 0 )
          {
            v87 &= ~0x100u;
            if ( (_QWORD)v313 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v313 + 192LL))(v313, 1);
          }
          if ( (v87 & 0x80u) != 0 )
          {
            v87 &= ~0x80u;
            std::wstring::~wstring(&v280);
          }
          std::wstring::~wstring(geoName);
          *(_QWORD *)geoName = &v406;
          v297 = 0;
          v298 = 0;
          v299 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v297, L"MaxRetryCount");
          v91 = Windows::UO::LegacyUOProvider::Scan_::_19_::_lambda_1_::operator()(
                  (unsigned int)geoName,
                  (unsigned int)&v297,
                  v90,
                  5,
                  1);
          web::json::value::value((web::json::value *)&v308, v91);
          v92 = v87 | 0x10000000;
          v286 = 0;
          v287 = 0;
          v288 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v286, L"allowedFailureCount");
          v93 = (__int64 *)web::json::value::operator[](&v402, &v286);
          if ( v93 == &v308 )
          {
            v94 = v308;
          }
          else
          {
            v94 = *v93;
            *v93 = v308;
            v308 = v94;
          }
          std::wstring::~wstring(&v286);
          if ( v94 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 192LL))(v94, 1);
          std::wstring::~wstring(&v297);
          v297 = 0;
          v298 = 0;
          v299 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v297, L"TimeoutDurationInMinutes");
          v96 = Windows::UO::LegacyUOProvider::Scan_::_19_::_lambda_1_::operator()(
                  (unsigned int)geoName,
                  (unsigned int)&v297,
                  v95,
                  30,
                  15);
          web::json::value::value((web::json::value *)&v309, v96);
          v6 = v92 | 0x20000000;
          v279 = v6;
          v286 = 0;
          v287 = 0;
          v288 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v286, L"updaterOOBETimeoutInMinutes");
          v97 = (__int64 *)web::json::value::operator[](&v402, &v286);
          if ( v97 == &v309 )
          {
            v98 = v309;
          }
          else
          {
            v98 = *v97;
            *v97 = v309;
            v309 = v98;
          }
          std::wstring::~wstring(&v286);
          if ( v98 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v98 + 192LL))(v98, 1);
          std::wstring::~wstring(&v297);
          v286 = 0;
          v287 = 0;
          v288 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v286, L"ExcludedRegions");
          v99 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v406 + 8LL))(v406, &v286);
          std::wstring::~wstring(&v286);
          if ( v99 )
          {
            *(_QWORD *)geoName = 0;
            if ( !GetUserDefaultGeoName(geoName, 4) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x133,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
                v100);
            v414 = 0;
            v286 = 0;
            v287 = 0;
            v288 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v286, L"ExcludedRegions");
            v101 = (const struct web::json::value *)web::json::value::at(&v406, &v286);
            web::json::value::value((web::json::value *)&v414, v101);
            std::wstring::~wstring(&v286);
            v102 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v414 + 152LL))(v414);
            if ( (unsigned __int8)std::ranges::_Any_of_fn::operator()_web::json::array_const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_23_::_lambda_2___(
                                    v102,
                                    geoName) )
            {
              v103 = SystemInterface::Providers::GetSystem(v386);
              v104 = *(_QWORD *)v103 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v103 + 8LL) + 4LL);
              v105 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v104 + 32LL))(v104, v385);
              v106 = *(_QWORD *)v105;
              v107 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v105 + 72LL);
              v108 = Src;
              if ( v401 > 7 )
                v108 = (_QWORD *)Src[0];
              *(_QWORD *)&v345 = v108;
              *((_QWORD *)&v345 + 1) = v400;
              *(_QWORD *)&v346 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v109 = -1;
              do
                ++v109;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v109] );
              *((_QWORD *)&v346 + 1) = v109;
              v280 = v345;
              *(_OWORD *)v283 = v346;
              v107(v106, v283, &v280);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v385);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v386);
              v283[0] = (__int64)geoName;
              wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v398, v283);
              v17 = v293;
              v110 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v293);
              *(_QWORD *)&v347 = v110;
              v112 = -1;
              do
                ++v112;
              while ( *(_WORD *)(v110 + 2 * v112) );
              *((_QWORD *)&v347 + 1) = v112;
              v280 = *v111;
              *(_OWORD *)v283 = v347;
              Windows::UO::LogLegacyOobeUpdateIgnoredExcludedRegion(v283, &v280);
              std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v414);
              if ( v406 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v406 + 192LL))(v406, 1);
              std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v402);
              std::wstring::~wstring(v428);
              if ( (_BYTE)v420 && (char)v419 != -1 && (_BYTE)v419 && (char)v419 != 1 )
                goto LABEL_139;
              goto LABEL_140;
            }
            if ( v414 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v414 + 192LL))(v414, 1);
          }
          v423 = 0;
          v424 = 0;
          v425 = 7;
          LOWORD(v423) = 0;
          v286 = 0;
          v287 = 0;
          v288 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v286, L"id");
          v6 |= 0x400u;
          v279 = v6;
          v113 = (_QWORD *)web::json::value::operator[](&v402, &v286);
          if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v113 + 88LL))(*v113) != 2 )
            goto LABEL_151;
          std::wstring::wstring(v295, L"id");
          v6 |= 0x800u;
          v279 = v6;
          v114 = (_QWORD *)web::json::value::operator[](&v402, v295);
          if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v114 + 176LL))(*v114) + 16) )
            goto LABEL_151;
          std::wstring::wstring(&v314, L"PFN");
          v6 |= 0x1000u;
          v279 = v6;
          v115 = (web::json::value *)web::json::value::operator[](&v402, &v314);
          if ( !web::json::value::is_string(v115) )
            goto LABEL_151;
          std::wstring::wstring(v365, L"PFN");
          v6 |= 0x2000u;
          v279 = v6;
          v116 = web::json::value::operator[](&v402, v365);
          v117 = web::json::value::as_string(v116);
          if ( (unsigned __int8)std::wstring::empty(v117) )
            goto LABEL_151;
          std::wstring::wstring(v364, L"Endpoint");
          v6 |= 0x4000u;
          v279 = v6;
          v118 = (web::json::value *)web::json::value::operator[](&v402, v364);
          if ( !web::json::value::is_string(v118) )
            goto LABEL_151;
          std::wstring::wstring(v368, L"Endpoint");
          v6 |= 0x8000u;
          v279 = v6;
          v119 = web::json::value::operator[](&v402, v368);
          v120 = web::json::value::as_string(v119);
          if ( (unsigned __int8)std::wstring::empty(v120) )
            goto LABEL_151;
          v121 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v388, L"https");
          std::wstring::wstring(geoName, L"Endpoint");
          v6 |= 0x10000u;
          v279 = v6;
          v122 = web::json::value::operator[](&v402, geoName);
          v123 = web::json::value::as_string(v122);
          v280 = v121;
          *(_OWORD *)v283 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                         v389,
                                         v123,
                                         v124,
                                         v125);
          if ( !(unsigned __int8)Strings::istarts_with(v283, &v280)
            || (std::wstring::wstring(&v297, L"updaterOOBETimeoutInMinutes"),
                v6 |= 0x20000u,
                v279 = v6,
                v126 = (web::json::value *)web::json::value::operator[](&v402, &v297),
                v127 = 1,
                !web::json::value::is_integer(v126)) )
          {
LABEL_151:
            v127 = 0;
          }
          if ( (v6 & 0x20000) != 0 )
          {
            v6 &= ~0x20000u;
            v279 = v6;
            std::wstring::~wstring(&v297);
          }
          if ( (v6 & 0x10000) != 0 )
          {
            v6 &= ~0x10000u;
            v279 = v6;
            std::wstring::~wstring(geoName);
          }
          if ( (v6 & 0x8000) != 0 )
          {
            v6 &= ~0x8000u;
            v279 = v6;
            std::wstring::~wstring(v368);
          }
          if ( (v6 & 0x4000) != 0 )
          {
            v6 &= ~0x4000u;
            v279 = v6;
            std::wstring::~wstring(v364);
          }
          if ( (v6 & 0x2000) != 0 )
          {
            v6 &= ~0x2000u;
            v279 = v6;
            std::wstring::~wstring(v365);
          }
          if ( (v6 & 0x1000) != 0 )
          {
            v6 &= ~0x1000u;
            v279 = v6;
            std::wstring::~wstring(&v314);
          }
          if ( (v6 & 0x800) != 0 )
          {
            v6 &= ~0x800u;
            v279 = v6;
            std::wstring::~wstring(v295);
          }
          if ( (v6 & 0x400) != 0 )
          {
            v6 &= ~0x400u;
            v279 = v6;
            std::wstring::~wstring(&v286);
          }
          if ( !v127 )
          {
            v168 = SystemInterface::Providers::GetSystem(v333);
            v169 = *(_QWORD *)v168 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v168 + 8LL) + 4LL);
            v170 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v169 + 32LL))(v169, v376);
            v171 = *(_QWORD *)v170;
            v172 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v170 + 72LL);
            v173 = Src;
            if ( v401 > 7 )
              v173 = (_QWORD *)Src[0];
            *(_QWORD *)&v321 = v173;
            *((_QWORD *)&v321 + 1) = v400;
            *(_QWORD *)&v322 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v174 = -1;
            do
              ++v174;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v174] );
            *((_QWORD *)&v322 + 1) = v174;
            v280 = v321;
            *(_OWORD *)v283 = v322;
            v172(v171, v283, &v280);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v376);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v333);
            v17 = v293;
            v175 = v293;
            if ( v293[3] > 7u )
              v175 = (_QWORD *)*v293;
            *(_QWORD *)&v324 = v175;
            v176 = -1;
            do
              ++v176;
            while ( *((_WORD *)v175 + v176) );
            *((_QWORD *)&v324 + 1) = v176;
            v280 = v324;
            Windows::UO::LogLegacyOobeUpdateInvalidExpeditedPayload(&v280);
            std::wstring::~wstring(&v423);
            if ( v406 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v406 + 192LL))(v406, 1);
            if ( (_QWORD)v402 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v402 + 192LL))(v402, 1);
            std::wstring::~wstring(v428);
            if ( (_BYTE)v420 && (char)v419 != -1 && (_BYTE)v419 && (char)v419 != 1 )
LABEL_139:
              std::wstring::~wstring(v418);
LABEL_140:
            std::wstring::~wstring(v415);
            std::wstring::~wstring(Src);
            v16 = v310;
            goto LABEL_246;
          }
          std::wstring::wstring(v364, L"updaterOOBETimeoutInMinutes");
          v128 = (_QWORD *)web::json::value::operator[](&v402, v364);
          v129 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v128 + 128LL))(*v128);
          v283[0] = std::to_wstring(&v286, v129);
          std::wstring::wstring(v365, L"Endpoint");
          v130 = (_QWORD *)web::json::value::operator[](&v402, v365);
          v131 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v130 + 176LL))(*v130);
          std::wstring::wstring(&v314, L"PFN");
          v132 = (_QWORD *)web::json::value::operator[](&v402, &v314);
          v133 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v132 + 176LL))(*v132);
          std::wstring::wstring(v295, L"id");
          v134 = (_QWORD *)web::json::value::operator[](&v402, v295);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v134 + 176LL))(*v134);
          *(_QWORD *)&v348 = L"{} {} {} {} {}";
          *((_QWORD *)&v348 + 1) = 14;
          v280 = v348;
          v135 = std::format<wchar_t const (&)[29],std::wstring const &,std::wstring const &,std::wstring const &,std::wstring>(
                   v368,
                   v133,
                   v131,
                   v283[0]);
          std::wstring::operator=(&v423, v135);
          std::wstring::~wstring(v368);
          std::wstring::~wstring(v295);
          std::wstring::~wstring(&v314);
          std::wstring::~wstring(v365);
          std::wstring::~wstring(&v286);
          std::wstring::~wstring(v364);
          pv = 0;
          wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%windir%\\system32\\usoclient.exe");
          v136 = SystemInterface::Providers::GetSystem(v369);
          v137 = *(_QWORD *)v136 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v136 + 8LL) + 4LL);
          v138 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v137 + 32LL))(v137, v387);
          v139 = *(_QWORD *)v138;
          v140 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(**(_QWORD **)v138 + 64LL);
          v283[0] = (__int64)pv;
          std::variant<unsigned int,unsigned __int64,std::wstring>::variant<unsigned int,unsigned __int64,std::wstring>(
            v295,
            v283);
          v141 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v390, L"cmdLine");
          v142 = Src;
          if ( v401 > 7 )
            v142 = (_QWORD *)Src[0];
          *(_QWORD *)&v349 = v142;
          *((_QWORD *)&v349 + 1) = v400;
          *(_QWORD *)&v350 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v143 = -1;
          do
            ++v143;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v143] );
          *((_QWORD *)&v350 + 1) = v143;
          v280 = *v141;
          *(_OWORD *)v283 = v349;
          *(_OWORD *)geoName = v350;
          v140(v139, geoName, v283, &v280, v295);
          if ( v296 != -1 && v296 && v296 != 1 )
            std::wstring::~wstring(v295);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v387);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v369);
          v144 = SystemInterface::Providers::GetSystem(v371);
          v145 = *(_QWORD *)v144 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v144 + 8LL) + 4LL);
          v146 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v145 + 32LL))(v145, v370);
          v147 = *(_QWORD *)v146;
          v148 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(**(_QWORD **)v146 + 64LL);
          v149 = &v423;
          if ( v425 > 7 )
            v149 = (__int128 *)v423;
          v283[0] = (__int64)v149;
          std::variant<unsigned int,unsigned __int64,std::wstring>::variant<unsigned int,unsigned __int64,std::wstring>(
            v295,
            v283);
          v150 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v391, L"startArg");
          v151 = Src;
          if ( v401 > 7 )
            v151 = (_QWORD *)Src[0];
          *(_QWORD *)&v351 = v151;
          *((_QWORD *)&v351 + 1) = v400;
          *(_QWORD *)&v317 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v152 = -1;
          do
            ++v152;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v152] );
          *((_QWORD *)&v317 + 1) = v152;
          v280 = *v150;
          *(_OWORD *)v283 = v351;
          *(_OWORD *)geoName = v317;
          v148(v147, geoName, v283, &v280, v295);
          if ( v296 != -1 && v296 && v296 != 1 )
            std::wstring::~wstring(v295);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v370);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v371);
          v153 = SystemInterface::Providers::GetSystem(v373);
          v154 = *(_QWORD *)v153 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v153 + 8LL) + 4LL);
          v155 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v154 + 32LL))(v154, v372);
          v156 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v392, L"oemExpeditedUpdate");
          v157 = Src;
          if ( v401 > 7 )
            v157 = (_QWORD *)Src[0];
          *(_QWORD *)&v318 = v157;
          *((_QWORD *)&v318 + 1) = v400;
          *(_QWORD *)&v319 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v158 = -1;
          do
            ++v158;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v158] );
          *((_QWORD *)&v319 + 1) = v158;
          v280 = *v156;
          *(_OWORD *)v283 = v318;
          *(_OWORD *)geoName = v319;
          SystemInterface::Registry::SetSystemBool(
            v155,
            (unsigned int)geoName,
            (unsigned int)v283,
            (unsigned int)&v280,
            1);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v372);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v373);
          v159 = SystemInterface::Providers::GetSystem(v375);
          v160 = *(_QWORD *)v159 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v159 + 8LL) + 4LL);
          v161 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v160 + 32LL))(v160, v374);
          v162 = *(_QWORD *)v161;
          v163 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, __int128 *))(**(_QWORD **)v161 + 64LL);
          v164 = web::json::value::serialize(&v402, v295);
          v314 = 0;
          v315 = 0u;
          v314 = *(_OWORD *)v164;
          v315 = *(_OWORD *)(v164 + 16);
          *(_QWORD *)(v164 + 16) = 0;
          *(_QWORD *)(v164 + 24) = 7;
          *(_WORD *)v164 = 0;
          v316 = 2;
          v165 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               v393,
                               L"updaterClientMetadata");
          v166 = Src;
          if ( v401 > 7 )
            v166 = (_QWORD *)Src[0];
          *(_QWORD *)&v320 = v166;
          *((_QWORD *)&v320 + 1) = v400;
          *(_QWORD *)&v323 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v167 = -1;
          do
            ++v167;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v167] );
          *((_QWORD *)&v323 + 1) = v167;
          v280 = *v165;
          *(_OWORD *)v283 = v320;
          *(_OWORD *)geoName = v323;
          v163(v162, geoName, v283, &v280, &v314);
          if ( v316 != -1 && v316 && v316 != 1 )
            std::wstring::~wstring(&v314);
          std::wstring::~wstring(v295);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v374);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v375);
          if ( pv )
            CoTaskMemFree(pv);
          std::wstring::~wstring(&v423);
          if ( v406 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v406 + 192LL))(v406, 1);
          if ( (_QWORD)v402 )
            (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v402 + 192LL))(v402, 1);
        }
        std::wstring::~wstring(v428);
      }
      else
      {
        v177 = SystemInterface::Providers::GetSystem(v328);
        v178 = *(_QWORD *)v177 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v177 + 8LL) + 4LL);
        v179 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v178 + 32LL))(v178, v331);
        v6 |= 0xC0000u;
        v279 = v6;
        v180 = *(_QWORD *)v179;
        v181 = *(__int64 (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *))(**(_QWORD **)v179 + 32LL);
        v182 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v380, L"expeditedPayload");
        v183 = Src;
        if ( v401 > 7 )
          v183 = (_QWORD *)Src[0];
        *(_QWORD *)&v327 = v183;
        *((_QWORD *)&v327 + 1) = v400;
        *(_QWORD *)&v326 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v184 = -1;
        do
          ++v184;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v184] );
        *((_QWORD *)&v326 + 1) = v184;
        v280 = *v182;
        *(_OWORD *)v283 = v327;
        *(_OWORD *)geoName = v326;
        v185 = v181(v180, geoName, v283, &v280);
        v186 = 1;
        if ( v185 )
          goto LABEL_229;
      }
      v186 = 0;
LABEL_229:
      if ( (v6 & 0x80000) != 0 )
      {
        v6 &= ~0x80000u;
        v279 = v6;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v331);
      }
      if ( (v6 & 0x40000) != 0 )
      {
        v6 &= ~0x40000u;
        v279 = v6;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v328);
      }
      if ( v186 )
      {
        v187 = SystemInterface::Providers::GetSystem(&v289);
        v188 = *(_QWORD *)v187 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v187 + 8LL) + 4LL);
        v189 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v188 + 32LL))(v188, &v300);
        v190 = *(_QWORD *)v189;
        v191 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v189 + 72LL);
        v192 = Src;
        if ( v401 > 7 )
          v192 = (_QWORD *)Src[0];
        *(_QWORD *)&v305 = v192;
        *((_QWORD *)&v305 + 1) = v400;
        *(_QWORD *)&v294 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v193 = -1;
        do
          ++v193;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v193] );
        *((_QWORD *)&v294 + 1) = v193;
        v280 = v305;
        *(_OWORD *)v283 = v294;
        v191(v190, v283, &v280);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v300);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v289);
      }
      if ( (_BYTE)v420 && (char)v419 != -1 && (_BYTE)v419 && (char)v419 != 1 )
        std::wstring::~wstring(v418);
      std::wstring::~wstring(v415);
      v17 = v293;
LABEL_245:
      std::wstring::~wstring(Src);
      v16 = v310;
LABEL_246:
      v17 += 4;
    }
  }
  v426 = 0;
  v427 = 0;
  v204 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v413 + 88LL);
  v205 = -1;
  do
    ++v205;
  while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v205] );
  *(_QWORD *)&v294 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
  *((_QWORD *)&v294 + 1) = v205;
  *(_QWORD *)&v305 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v206 = -1;
  do
    ++v206;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v206] );
  *((_QWORD *)&v305 + 1) = v206;
  v289 = v294;
  v300 = v305;
  v204(v413, &v426, &v300, &v289);
  *(_QWORD *)&v313 = *((_QWORD *)&v426 + 1);
  v208 = (_QWORD *)v426;
  if ( (_QWORD)v426 != *((_QWORD *)&v426 + 1) )
  {
    while ( 1 )
    {
      v209 = v208[2];
      v210 = v208;
      if ( v208[3] > 7u )
        v210 = (_QWORD *)*v208;
      *(_QWORD *)&v294 = v210;
      *((_QWORD *)&v294 + 1) = v209;
      v289 = v294;
      Windows::UO::LegacyUOUpdate::CreateUpdate(&v410, &v289, *((_QWORD *)v5 + 4));
      v211 = v412;
      if ( v412 )
      {
        v303 = 0;
        v212 = v411;
        if ( v411 )
        {
          _InterlockedIncrement(v411 + 2);
          v212 = v411;
        }
        v213 = v410;
        *(_QWORD *)&v303 = v410;
        *((_QWORD *)&v303 + 1) = v212;
        v214 = (_QWORD *)((char *)v410 + 288);
        v215 = *((_QWORD *)v410 + 38);
        if ( *((_QWORD *)v410 + 39) > 7u )
          v214 = (_QWORD *)*v214;
        *(_QWORD *)&v305 = v214;
        *((_QWORD *)&v305 + 1) = v215;
        v289 = v305;
        if ( *(_BYTE *)(Windows::UO::UpdaterSettings::GetUpdaterSettings(&v289) + 84) )
        {
          v216 = (_QWORD *)(*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, _DWORD *))(*(_QWORD *)v213 + 24LL))(
                             v213,
                             v295);
          if ( v216[3] > 7u )
            v216 = (_QWORD *)*v216;
          v283[0] = (__int64)v216;
          *(_QWORD *)&v326 = L"Legacy UO Updater: {} ignored because it is disabled";
          *((_QWORD *)&v326 + 1) = 52;
          v289 = v326;
          SystemInterface::Log<wchar_t const *>(&v289, v283);
          std::wstring::~wstring(v295);
          if ( v212 )
          {
            if ( _InterlockedExchangeAdd(v212 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v212)(v212);
              if ( _InterlockedExchangeAdd(v212 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v212 + 8LL))(v212);
            }
          }
          v217 = v412 == 0;
          goto LABEL_334;
        }
        if ( *((_BYTE *)v213 + 536) )
        {
          v218 = (_QWORD *)(*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, _DWORD *))(*(_QWORD *)v213 + 24LL))(
                             v213,
                             v295);
          if ( v218[3] > 7u )
            v218 = (_QWORD *)*v218;
          v283[0] = (__int64)v218;
          *(_QWORD *)&v327 = L"Legacy UO Updater: {} ignored because it was completed";
          *((_QWORD *)&v327 + 1) = 54;
          v289 = v327;
          SystemInterface::Log<wchar_t const *>(&v289, v283);
          goto LABEL_282;
        }
        v220 = (void *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"IA",
                         &unk_14047EAEA,
                         0);
        if ( v220 == &unk_14047EAEA || (v223 = ((__int64)v220 - v222) >> 1, v223 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v221);
        *(_QWORD *)&v324 = v222;
        *((_QWORD *)&v324 + 1) = v223;
        std::wstring::wstring(&v286, (char *)v213 + 288);
        v6 |= 0x1100000u;
        v224 = &v286;
        if ( v288 > 7 )
          v224 = (__int128 *)v286;
        *(_QWORD *)&v322 = v224;
        *((_QWORD *)&v322 + 1) = v287;
        v289 = v324;
        v300 = v322;
        if ( !(unsigned __int8)Strings::iequals(&v300, &v289)
          || (unsigned __int8)UpdateMetadata::IsOobeExpedited(v213)
          || (v226 = 1, !Windows::UO::LegacyUOProvider::IsStoreProviderEnabled(v225)) )
        {
          v226 = 0;
        }
        if ( (v6 & 0x100000) != 0 )
        {
          v6 &= ~0x100000u;
          std::wstring::~wstring(&v286);
        }
        if ( v226 )
        {
          v227 = SystemInterface::Providers::GetSystem(v331);
          v228 = *(_QWORD *)v227 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v227 + 8LL) + 4LL);
          v229 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v228 + 104LL))(v228, v328);
          v230 = *(_QWORD *)v229;
          v231 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v229 + 200LL);
          v232 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                              v380,
                              L"StoreProvider active during scan");
          std::wstring::wstring(&v286, (char *)v213 + 288);
          v6 |= 0x2000000u;
          v233 = &v286;
          if ( v288 > 7 )
            v233 = (__int128 *)v286;
          *(_QWORD *)&v321 = v233;
          *((_QWORD *)&v321 + 1) = v287;
          v289 = v232;
          v300 = v321;
          v231(v230, &v300, &v289);
          std::wstring::~wstring(&v286);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v328);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v331);
          Windows::UO::LegacyUOUpdate::RemoveUpdate(v213);
          goto LABEL_284;
        }
        if ( (unsigned __int8)UpdateMetadata::IsOobeExpedited(v213) )
        {
          *(_QWORD *)&v323 = L"{}\\{}";
          *((_QWORD *)&v323 + 1) = 5;
          v289 = v323;
          std::format<wchar_t const * const &,std::wstring const &>(v415);
          v234 = SystemInterface::Providers::GetSystem(v333);
          v235 = *(_QWORD *)v234 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v234 + 8LL) + 4LL);
          v236 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v235 + 32LL))(v235, v338);
          v237 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v381, L"oemExpeditedUpdate");
          v238 = v415;
          if ( v417 > 7 )
            v238 = (_QWORD *)v415[0];
          *(_QWORD *)&v320 = v238;
          *((_QWORD *)&v320 + 1) = v416;
          *(_QWORD *)&v319 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v239 = -1;
          do
            ++v239;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v239] );
          *((_QWORD *)&v319 + 1) = v239;
          v289 = *v237;
          v300 = v320;
          v330 = v319;
          SystemBoolOrDefault = SystemInterface::Registry::GetSystemBoolOrDefault(
                                  v236,
                                  (unsigned int)&v330,
                                  (unsigned int)&v300,
                                  (unsigned int)&v289,
                                  0);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v338);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v333);
          if ( (unsigned __int8)std::ranges::_None_of_fn::operator()_std::vector_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t________const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_56_::_lambda_3___(
                                  &v430,
                                  v208)
            && !SystemBoolOrDefault )
          {
            v241 = v208[2];
            v242 = v208;
            if ( v208[3] > 7u )
              v242 = (_QWORD *)*v208;
            *(_QWORD *)&v318 = v242;
            *((_QWORD *)&v318 + 1) = v241;
            v289 = v318;
            Windows::UO::LogLegacyOobeUpdateIgnoredNotAllowed(&v289);
            goto LABEL_309;
          }
          if ( v433
            && (unsigned __int8)std::ranges::_Any_of_fn::operator()_std::vector_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t________const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_59_::_lambda_4___(
                                  v432,
                                  v208) )
          {
            v289 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v383, v208, v243, v244);
            Windows::UO::LogLegacyOobeUpdateIgnoredBlocked(&v289);
            goto LABEL_309;
          }
          v245 = (int)UpdateMetadata::AllowedFailureCount_0(v213);
          v246 = (__int64 *)UpdateDatabase::ActionRecords(*((_QWORD *)v291 + 4), &v421, v213);
          v247 = v246[1];
          v248 = 0;
          for ( i = *v246; i != v247; i += 112 )
          {
            v250 = v248++;
            if ( *(int *)(i + 108) >= 0 )
              v248 = v250;
          }
          std::vector<SystemInterface::ActionRecord>::~vector<SystemInterface::ActionRecord>(&v421);
          if ( v248 >= v245 )
          {
            v251 = v208[2];
            v252 = v208;
            if ( v208[3] > 7u )
              v252 = (_QWORD *)*v208;
            *(_QWORD *)&v317 = v252;
            *((_QWORD *)&v317 + 1) = v251;
            v289 = v317;
            Windows::UO::LogLegacyUOUpdaterIgnoredOobeExpeditedUpdate(&v289);
            Windows::UO::LegacyUOUpdate::RemoveUpdate(v213);
LABEL_309:
            v219 = v415;
LABEL_283:
            std::wstring::~wstring(v219);
LABEL_284:
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v303);
            ActionState::~ActionState((ActionState *)&v410);
            goto LABEL_339;
          }
          std::wstring::~wstring(v415);
          v5 = v291;
        }
        v304 = 0;
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>>,0>>::find(
          (char *)v5 + 40,
          &v304,
          v208);
        v253 = v304;
        if ( v304 == *((_DWORD **)v5 + 5)
          || (v254 = (*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, __int128 *))(*(_QWORD *)v213 + 24LL))(
                       v213,
                       &v314),
              v255 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v253 + 8) + 24LL))(
                       *((_QWORD *)v253 + 8),
                       v295),
              v6 |= 0x600000u,
              v256 = std::wstring::compare(v254, v255),
              v257 = 1,
              v256) )
        {
          v257 = 0;
        }
        if ( (v6 & 0x400000) != 0 )
        {
          v6 &= ~0x400000u;
          std::wstring::~wstring(v295);
        }
        if ( (v6 & 0x200000) != 0 )
        {
          v6 &= ~0x200000u;
          std::wstring::~wstring(&v314);
        }
        std::wstring::wstring(v295, (char *)v213 + 288);
        if ( v257 )
        {
          v6 |= 0x40000000u;
          v258 = std::map<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>>::operator[](Block, v295);
          std::shared_ptr<Update>::operator=(v258, v253 + 16);
LABEL_282:
          v219 = v295;
          goto LABEL_283;
        }
        v6 |= 0x80000000;
        v259 = std::map<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>>::operator[](Block, v295);
        std::shared_ptr<Update>::operator=(v259, &v410);
        std::wstring::~wstring(v295);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v303);
        v211 = v412;
      }
      v217 = v211 == 0;
LABEL_334:
      if ( !v217 )
      {
        v260 = v411;
        if ( v411 )
        {
          if ( _InterlockedExchangeAdd(v411 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v260)(v260);
            if ( _InterlockedExchangeAdd(v260 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v260 + 8LL))(v260);
          }
        }
      }
LABEL_339:
      v208 += 4;
      if ( v208 == (_QWORD *)v313 )
        break;
      v5 = v291;
    }
  }
  v408 = 0;
  v409 = 0;
  v261 = *(__int64 **)Block[0];
  while ( !*((_BYTE *)v261 + 25) )
  {
    std::wstring::wstring(v418, v261 + 4);
    v262 = v261[9];
    if ( v262 )
      _InterlockedIncrement((volatile signed __int32 *)(v262 + 8));
    v263 = v261[8];
    v419 = v263;
    v264 = (volatile signed __int32 *)v261[9];
    v420 = v264;
    if ( v264 )
      _InterlockedIncrement(v264 + 2);
    v283[0] = v263;
    v283[1] = (__int64)v264;
    v265 = *((_QWORD *)&v408 + 1);
    if ( *((_QWORD *)&v408 + 1) == v409 )
    {
      std::vector<std::shared_ptr<Update>>::_Emplace_reallocate<std::shared_ptr<Windows::WU::CurrentVersionUpdate>>(
        &v408,
        *((_QWORD *)&v408 + 1),
        v283);
    }
    else
    {
      **((_QWORD **)&v408 + 1) = v263;
      *(_QWORD *)(v265 + 8) = v264;
      *(_OWORD *)v283 = 0;
      *((_QWORD *)&v408 + 1) += 16LL;
    }
    v266 = (volatile signed __int32 *)v283[1];
    if ( v283[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v283[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v266)(v266);
        if ( _InterlockedExchangeAdd(v266 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v266 + 8LL))(v266);
      }
    }
    if ( v264 )
    {
      if ( _InterlockedExchangeAdd(v264 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v264)(v264);
        if ( _InterlockedExchangeAdd(v264 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v264 + 8LL))(v264);
      }
    }
    std::wstring::~wstring(v418);
    v267 = (__int64 *)v261[2];
    if ( *((_BYTE *)v267 + 25) )
    {
      for ( j = (__int64 *)v261[1]; !*((_BYTE *)j + 25) && v261 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v261 = j;
      v261 = j;
    }
    else
    {
      do
      {
        v261 = v267;
        v267 = (__int64 *)*v267;
      }
      while ( !*((_BYTE *)v267 + 25) );
    }
  }
  LOBYTE(v207) = 0;
  std::ranges::_Sort_fn::_Sort_common_std::shared_ptr_Update____std::ranges::less__Windows::UO::LegacyUOProvider::Scan_::_2_::_lambda_6___(
    v408,
    DWORD2(v408),
    (__int64)(*((_QWORD *)&v408 + 1) - v408) >> 4,
    v207,
    v292);
  v269 = (char *)v291 + 40;
  if ( (void **)((char *)v291 + 40) != Block )
  {
    v270 = *(void **)v269;
    *(void **)v269 = Block[0];
    Block[0] = v270;
    v271 = (void *)*((_QWORD *)v269 + 1);
    *((void **)v269 + 1) = Block[1];
    Block[1] = v271;
  }
  Windows::UO::LogLegacyUOProviderScanResults(&v408);
  LODWORD(v286) = 0;
  v272 = v409;
  v409 = 0;
  v273 = *((_QWORD *)&v408 + 1);
  v274 = v408;
  v408 = 0u;
  v275 = v312;
  *v312 = 0;
  v288 = 0;
  v287 = 0;
  *((_QWORD *)&v286 + 1) = 0;
  *((_QWORD *)v275 + 1) = v274;
  *((_QWORD *)v275 + 2) = v273;
  *((_QWORD *)v275 + 3) = v272;
  *((_BYTE *)v275 + 32) = 1;
  std::vector<std::shared_ptr<Update>>::_Tidy((char *)&v286 + 8);
  std::vector<std::shared_ptr<Update>>::_Tidy(&v408);
  std::vector<std::filesystem::path>::_Tidy(&v426);
  v276 = (volatile signed __int32 *)*((_QWORD *)&v413 + 1);
  if ( *((_QWORD *)&v413 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v413 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v276)(v276);
      if ( _InterlockedExchangeAdd(v276 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v276 + 8LL))(v276);
    }
  }
  if ( v433 )
    std::vector<std::filesystem::path>::_Tidy(v432);
  std::vector<std::filesystem::path>::_Tidy(&v430);
  v277 = v336;
  v217 = (*(_DWORD *)(v336 + 76))-- == 1;
  if ( v217 )
  {
    *(_DWORD *)(v277 + 72) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v277 + 16));
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>,void *>>>(
    Block,
    Block,
    *((_QWORD *)Block[0] + 1));
  operator delete(Block[0]);
  return v275;
}

```

## disassembly

```asm
0x140318e30  mov     r11, rsp
0x140318e33  mov     [r11+18h], rbx
0x140318e37  mov     [r11+20h], rsi
0x140318e3b  push    rdi
0x140318e3c  push    r12
0x140318e3e  push    r13
0x140318e40  push    r14
0x140318e42  push    r15
0x140318e44  sub     rsp, 8E0h
0x140318e4b  movaps  xmmword ptr [r11-38h], xmm6
0x140318e50  mov     rax, cs:__security_cookie
0x140318e57  xor     rax, rsp
0x140318e5a  mov     [rsp+908h+var_40], rax
0x140318e62  mov     rbx, r9
0x140318e65  mov     [rsp+908h+var_748], rdx
0x140318e6d  mov     rdi, rcx
0x140318e70  mov     [rsp+908h+var_840], rcx
0x140318e78  mov     [rsp+908h+var_678], rcx
0x140318e80  mov     [rsp+908h+var_798], rdx
0x140318e88  xor     r15d, r15d
0x140318e8b  mov     r12d, r15d
0x140318e8e  mov     [rsp+908h+var_8C8], r15d
0x140318e93  mov     [rsp+908h+var_848], r15d
0x140318e9b  xorps   xmm0, xmm0
0x140318e9e  movups  xmmword ptr [rsp+908h+Block], xmm0
0x140318ea6  mov     [r11-190h], r15
0x140318ead  mov     [r11-188h], r15
0x140318eb4  lea     ecx, [r15+50h]
0x140318eb8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140318ebd  mov     [rax], rax
0x140318ec0  mov     [rax+8], rax
0x140318ec4  mov     [rax+10h], rax
0x140318ec8  mov     word ptr [rax+18h], 101h
0x140318ece  mov     [rsp+908h+Block], rax
0x140318ed6  lea     rdx, [rdi+80h]
0x140318edd  lea     rcx, [rsp+908h+var_5F0]
0x140318ee5  call    ??0?$lock_guard@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::lock_guard<std::mutex>::lock_guard<std::mutex>(std::mutex &)
0x140318eea  nop
0x140318eeb  xorps   xmm0, xmm0
0x140318eee  xor     eax, eax
0x140318ef0  movups  [rsp+908h+var_78], xmm0
0x140318ef8  mov     [rsp+908h+var_68], rax
0x140318f00  lea     rcx, [rsp+908h+var_78]
0x140318f08  call    ?GetAllowedOobeUpdaters@UO@Windows@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; Windows::UO::GetAllowedOobeUpdaters(void)
0x140318f0d  nop
0x140318f0e  lea     rcx, [rsp+908h+var_60]
0x140318f16  call    ?GetBlockedOobeUpdaters@UO@Windows@@YA?AV?$optional@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@XZ; Windows::UO::GetBlockedOobeUpdaters(void)
0x140318f1b  nop
0x140318f1c  xorps   xmm0, xmm0
0x140318f1f  movups  [rsp+908h+var_150], xmm0
0x140318f27  lea     rcx, [rsp+908h+var_2F8]
0x140318f2f  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140318f34  nop
0x140318f35  mov     rdx, [rax]
0x140318f38  mov     rax, [rdx+8]
0x140318f3c  movsxd  rcx, dword ptr [rax+4]
0x140318f40  add     rdx, 8
0x140318f44  add     rcx, rdx
0x140318f47  mov     rax, [rcx]
0x140318f4a  lea     rdx, [rsp+908h+var_150]
0x140318f52  mov     rax, [rax+20h]
0x140318f56  call    _guard_dispatch_icall
0x140318f5b  nop
0x140318f5c  lea     rcx, [rsp+908h+var_2F8]; void *
0x140318f64  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140318f69  cmp     [rbx+3], r15b
0x140318f6d  jz      short loc_140318FAE
0x140318f6f  lea     rcx, [rsp+908h+var_828]
0x140318f77  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140318f7c  nop
0x140318f7d  lea     r12d, [r15+1]
0x140318f81  mov     [rsp+908h+var_8C8], r12d
0x140318f86  mov     rdx, [rax]
0x140318f89  mov     rax, [rdx+8]
0x140318f8d  movsxd  rcx, dword ptr [rax+4]
0x140318f91  add     rdx, 8
0x140318f95  add     rcx, rdx
0x140318f98  mov     rax, [rcx]
0x140318f9b  mov     rax, [rax+0A8h]
0x140318fa2  call    _guard_dispatch_icall
0x140318fa7  test    al, al
0x140318fa9  mov     bl, r12b
0x140318fac  jz      short loc_140318FB1
0x140318fae  mov     bl, r15b
0x140318fb1  test    r12b, 1
0x140318fb5  jz      short loc_140318FCD
0x140318fb7  and     r12d, 0FFFFFFFEh
0x140318fbb  mov     [rsp+908h+var_8C8], r12d
0x140318fc0  lea     rcx, [rsp+908h+var_828]; void *
0x140318fc8  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140318fcd  test    bl, bl
0x140318fcf  jz      loc_14031B8D6
0x140318fd5  xorps   xmm0, xmm0
0x140318fd8  xor     eax, eax
0x140318fda  movups  [rsp+908h+var_E8], xmm0
0x140318fe2  mov     [rsp+908h+var_D8], rax
0x140318fea  mov     r10, qword ptr [rsp+908h+var_150]
0x140318ff2  mov     rax, [r10]
0x140318ff5  mov     r11, [rax+58h]
0x140318ff9  mov     rcx, cs:?USO_USCHEDULER_OOBE_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT
0x140319000  or      r13, 0FFFFFFFFFFFFFFFFh
0x140319004  mov     rax, r13
0x140319007  inc     rax
0x14031900a  cmp     [rcx+rax*2], r15w
0x14031900f  jnz     short loc_140319007
0x140319011  mov     [rsp+908h+var_898], rcx
0x140319016  mov     [rsp+908h+var_898+8], rax
0x14031901b  mov     rax, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x140319022  mov     qword ptr [rsp+908h+var_738], rax
0x14031902a  mov     rdx, r13
0x14031902d  inc     rdx
0x140319030  cmp     [rax+rdx*2], r15w
0x140319035  jnz     short loc_14031902D
0x140319037  mov     qword ptr [rsp+908h+var_738+8], rdx
0x14031903f  movups  xmm0, xmmword ptr [rsp+908h+var_898]
0x140319044  movdqu  [rsp+908h+var_828], xmm0
0x14031904d  movaps  xmm1, [rsp+908h+var_738]
0x140319055  movdqa  [rsp+908h+var_788], xmm1
0x14031905e  lea     r9, [rsp+908h+var_828]
0x140319066  lea     r8, [rsp+908h+var_788]
0x14031906e  lea     rdx, [rsp+908h+var_E8]
0x140319076  mov     rcx, r10
0x140319079  mov     rax, r11
0x14031907c  call    _guard_dispatch_icall
0x140319081  nop
0x140319082  mov     rbx, qword ptr [rsp+908h+var_E8]
0x14031908a  mov     rcx, qword ptr [rsp+908h+var_E8+8]
0x140319092  mov     [rsp+908h+var_758], rcx
0x14031909a  lea     r8, asc_14047F3C0; "{}\\{}"
0x1403190a1  mov     rdi, [rsp+908h+var_7B8]
0x1403190a9  mov     rsi, [rsp+908h+var_7B0]
0x1403190b1  mov     [rsp+908h+var_830], rbx
0x1403190b9  cmp     rbx, rcx
0x1403190bc  jz      loc_14031B756
0x1403190c2  mov     qword ptr [rsp+908h+var_4E8], r8
0x1403190ca  mov     qword ptr [rsp+908h+var_4E8+8], 5
0x1403190d6  movaps  xmm0, [rsp+908h+var_4E8]
0x1403190de  movdqa  xmmword ptr [rsp+908h+var_898], xmm0
0x1403190e4  mov     r9, rbx
0x1403190e7  lea     r8, ?USO_USCHEDULER_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_ROOT
0x1403190ee  lea     rdx, [rsp+908h+var_898]
0x1403190f3  lea     rcx, [rsp+908h+Src]; Src
0x1403190fb  call    ??$format@AEBQEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEBQEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEBQEB_WAEBV10@@Z; std::format<wchar_t const * const &,std::wstring const &>(std::basic_format_string<wchar_t,wchar_t const * const &,std::wstring const &>,wchar_t const * const &,std::wstring const &)
0x140319100  nop
0x140319101  mov     rcx, qword ptr [rsp+908h+var_150]
0x140319109  mov     rax, [rcx]
0x14031910c  mov     r9, [rax+8]
0x140319110  lea     rax, [rsp+908h+Src]
0x140319118  cmp     [rsp+908h+var_1D0], 7
0x140319121  cmova   rax, [rsp+908h+Src]
0x14031912a  mov     qword ptr [rsp+908h+var_4D8], rax
0x140319132  mov     rax, [rsp+908h+var_1D8]
0x14031913a  mov     qword ptr [rsp+908h+var_4D8+8], rax
0x140319142  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x140319149  mov     qword ptr [rsp+908h+var_4C8], rax
0x140319151  mov     rdx, r13
0x140319154  inc     rdx
0x140319157  cmp     [rax+rdx*2], r15w
0x14031915c  jnz     short loc_140319154
0x14031915e  mov     qword ptr [rsp+908h+var_4C8+8], rdx
0x140319166  movups  xmm0, [rsp+908h+var_4D8]
0x14031916e  movdqu  xmmword ptr [rsp+908h+var_898], xmm0
0x140319174  movaps  xmm1, [rsp+908h+var_4C8]
0x14031917c  movdqa  xmmword ptr [rsp+908h+geoName], xmm1
0x140319185  lea     r8, [rsp+908h+var_898]
0x14031918a  lea     rdx, [rsp+908h+geoName]
0x140319192  mov     rax, r9
0x140319195  call    _guard_dispatch_icall
0x14031919a  test    al, al
0x14031919c  jz      loc_14031923E
0x1403191a2  lea     rax, [rsp+908h+Src]
0x1403191aa  cmp     [rsp+908h+var_1D0], 7
0x1403191b3  cmova   rax, [rsp+908h+Src]
0x1403191bc  mov     qword ptr [rsp+908h+var_4B8], rax
0x1403191c4  mov     rax, [rsp+908h+var_1D8]
0x1403191cc  mov     qword ptr [rsp+908h+var_4B8+8], rax
0x1403191d4  mov     rcx, [rbx+10h]
0x1403191d8  mov     rax, rbx
0x1403191db  cmp     qword ptr [rbx+18h], 7
0x1403191e0  jbe     short loc_1403191E5
0x1403191e2  mov     rax, [rbx]
0x1403191e5  mov     qword ptr [rsp+908h+var_4A8], rax
0x1403191ed  mov     qword ptr [rsp+908h+var_4A8+8], rcx
0x1403191f5  movups  xmm0, [rsp+908h+var_4B8]
0x1403191fd  movdqu  xmmword ptr [rsp+908h+var_898], xmm0
0x140319203  movaps  xmm1, [rsp+908h+var_4A8]
0x14031920b  movdqa  xmmword ptr [rsp+908h+geoName], xmm1
0x140319214  lea     r9, [rsp+908h+var_898]
0x140319219  lea     r8, [rsp+908h+var_150]
0x140319221  lea     rdx, [rsp+908h+geoName]
0x140319229  mov     rcx, [rsp+908h+var_840]
0x140319231  call    ?ShouldRecoverStoreExpeditedRegistration@LegacyUOProvider@UO@Windows@@AEAA_NV?$basic_zstring_view@_W@wil@@AEAV?$shared_ptr@VRegistry@SystemInterface@@@std@@0@Z; Windows::UO::LegacyUOProvider::ShouldRecoverStoreExpeditedRegistration(wil::basic_zstring_view<wchar_t>,std::shared_ptr<SystemInterface::Registry> &,wil::basic_zstring_view<wchar_t>)
0x140319236  test    al, al
0x140319238  jz      loc_14031B731
0x14031923e  lea     rax, asc_14047F3C0; "{}\\{}"
0x140319245  mov     qword ptr [rsp+908h+var_498], rax
0x14031924d  mov     qword ptr [rsp+908h+var_498+8], 5
0x140319259  movaps  xmm0, [rsp+908h+var_498]
0x140319261  movdqa  xmmword ptr [rsp+908h+var_898], xmm0
0x140319267  mov     r9, rbx
0x14031926a  lea     r8, ?USO_USCHEDULER_OOBE_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT
0x140319271  lea     rdx, [rsp+908h+var_898]
0x140319276  lea     rcx, [rsp+908h+var_138]; Src
0x14031927e  call    ??$format@AEBQEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEBQEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEBQEB_WAEBV10@@Z; std::format<wchar_t const * const &,std::wstring const &>(std::basic_format_string<wchar_t,wchar_t const * const &,std::wstring const &>,wchar_t const * const &,std::wstring const &)
0x140319283  nop
0x140319284  mov     r10, qword ptr [rsp+908h+var_150]
0x14031928c  mov     rax, [r10]
0x14031928f  mov     r11, [rax+68h]
0x140319293  lea     rax, [rsp+908h+Src]
0x14031929b  cmp     [rsp+908h+var_1D0], 7
0x1403192a4  cmova   rax, [rsp+908h+Src]
0x1403192ad  mov     qword ptr [rsp+908h+var_468], rax
0x1403192b5  mov     rax, [rsp+908h+var_1D8]
0x1403192bd  mov     qword ptr [rsp+908h+var_468+8], rax
0x1403192c5  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x1403192cc  mov     rax, r13
0x1403192cf  inc     rax
0x1403192d2  cmp     [rcx+rax*2], r15w
0x1403192d7  jnz     short loc_1403192CF
0x1403192d9  mov     qword ptr [rsp+908h+var_458], rcx
0x1403192e1  mov     qword ptr [rsp+908h+var_458+8], rax
0x1403192e9  lea     rax, [rsp+908h+var_138]
0x1403192f1  cmp     [rsp+908h+var_120], 7
0x1403192fa  cmova   rax, [rsp+908h+var_138]
0x140319303  mov     qword ptr [rsp+908h+var_408], rax
0x14031930b  mov     rax, [rsp+908h+var_128]
0x140319313  mov     qword ptr [rsp+908h+var_408+8], rax
0x14031931b  mov     rcx, cs:?USOROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOROOT_REDIRECTION_ID
0x140319322  mov     qword ptr [rsp+908h+var_3F8], rcx
0x14031932a  mov     rax, r13
0x14031932d  inc     rax
0x140319330  cmp     [rcx+rax*2], r15w
0x140319335  jnz     short loc_14031932D
0x140319337  mov     qword ptr [rsp+908h+var_3F8+8], rax
0x14031933f  movups  xmm0, [rsp+908h+var_468]
0x140319347  movdqu  xmmword ptr [rsp+908h+var_898], xmm0
0x14031934d  movups  xmm1, [rsp+908h+var_458]
0x140319355  movdqu  xmmword ptr [rsp+908h+geoName], xmm1
0x14031935e  movups  xmm0, [rsp+908h+var_408]
0x140319366  movdqu  [rsp+908h+var_1C8], xmm0
0x14031936f  movaps  xmm1, [rsp+908h+var_3F8]
0x140319377  movdqa  [rsp+908h+var_8B8], xmm1
0x14031937d  lea     rax, [rsp+908h+var_898]
0x140319382  mov     [rsp+908h+var_8E8], rax
0x140319387  lea     r9, [rsp+908h+geoName]
0x14031938f  lea     r8, [rsp+908h+var_1C8]
0x140319397  lea     rdx, [rsp+908h+var_8B8]
0x14031939c  mov     rcx, r10
0x14031939f  mov     rax, r11
0x1403193a2  call    _guard_dispatch_icall
0x1403193a7  mov     rbx, qword ptr [rsp+908h+var_150]
0x1403193af  mov     rax, [rbx]
0x1403193b2  mov     r14, [rax+38h]
0x1403193b6  lea     rdx, aUpdaterpriorit; "updaterPriority"
0x1403193bd  lea     rcx, [rsp+908h+var_238]
0x1403193c5  call    ??$?0$0BA@@?$basic_zstring_view@_W@wil@@QEAA@AEAY0BA@$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[16])
0x1403193ca  mov     rdx, rax
0x1403193cd  lea     rax, [rsp+908h+Src]
0x1403193d5  cmp     [rsp+908h+var_1D0], 7
0x1403193de  cmova   rax, [rsp+908h+Src]
0x1403193e7  mov     qword ptr [rsp+908h+var_5D0], rax
0x1403193ef  mov     rax, [rsp+908h+var_1D8]
0x1403193f7  mov     qword ptr [rsp+908h+var_5D0+8], rax
0x1403193ff  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x140319406  mov     qword ptr [rsp+908h+var_5B8], rcx
0x14031940e  mov     rax, r13
0x140319411  inc     rax
0x140319414  cmp     [rcx+rax*2], r15w
0x140319419  jnz     short loc_140319411
0x14031941b  mov     qword ptr [rsp+908h+var_5B8+8], rax
0x140319423  movups  xmm0, xmmword ptr [rdx]
0x140319426  movdqu  [rsp+908h+var_8B8], xmm0
0x14031942c  movups  xmm1, [rsp+908h+var_5D0]
0x140319434  movdqu  xmmword ptr [rsp+908h+var_898], xmm1
0x14031943a  movaps  xmm0, [rsp+908h+var_5B8]
0x140319442  movdqa  xmmword ptr [rsp+908h+geoName], xmm0
0x14031944b  lea     rax, [rsp+908h+var_8B8]
0x140319450  mov     [rsp+908h+var_8E8], rax
0x140319455  lea     r9, [rsp+908h+var_898]
0x14031945a  lea     r8, [rsp+908h+geoName]
0x140319462  lea     rdx, [rsp+908h+var_118]
0x14031946a  mov     rcx, rbx
0x14031946d  mov     rax, r14
0x140319470  call    _guard_dispatch_icall
0x140319475  nop
0x140319476  mov     rbx, qword ptr [rsp+908h+var_150]
0x14031947e  mov     rax, [rbx]
0x140319481  mov     r14, [rax+40h]
0x140319485  cmp     byte ptr [rsp+908h+var_F0], r15b
0x14031948d  jz      short loc_1403194A5
0x14031948f  cmp     byte ptr [rsp+908h+var_F8], r15b
0x140319497  jnz     short loc_1403194A5
0x140319499  mov     eax, [rsp+908h+var_118]
0x1403194a0  cmp     eax, 64h ; 'd'
0x1403194a3  jbe     short loc_1403194AB
0x1403194a5  mov     eax, cs:?sc_defaultUpdaterPriority@LegacyUOProvider@UO@Windows@@0IB; uint const Windows::UO::LegacyUOProvider::sc_defaultUpdaterPriority
0x1403194ab  mov     [rsp+908h+var_818], eax
0x1403194b2  mov     [rsp+908h+var_7F8], r15b
0x1403194ba  lea     rdx, aUpdaterpriorit; "updaterPriority"
0x1403194c1  lea     rcx, [rsp+908h+var_228]
  ... truncated ...
```
