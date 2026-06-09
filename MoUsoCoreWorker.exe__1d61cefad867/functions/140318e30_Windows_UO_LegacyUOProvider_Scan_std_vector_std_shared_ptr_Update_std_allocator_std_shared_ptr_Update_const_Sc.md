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
  __int64 v26; // rdx
  void (__fastcall *v27)(_QWORD, __int128 *, __int128 *, WCHAR *, __int64 *); // r11
  _QWORD *v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  void (__fastcall *v33)(__int64, _DWORD *, WCHAR *, __int64 *, __int128 *); // r14
  __int128 *v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rbx
  void (__fastcall *v38)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  unsigned int v39; // eax
  __int128 *v40; // rdx
  _QWORD *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r14
  __int64 (__fastcall *v48)(__int64, __int128 *, __int64); // rbx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rbx
  _OWORD *v53; // rdx
  _QWORD *v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 *v58; // rbx
  __int64 *v59; // rax
  __int64 v60; // rcx
  int v61; // r12d
  __int64 v62; // rdx
  __int64 *v63; // rcx
  __int64 v64; // rbx
  int v65; // r12d
  __int64 v66; // rdx
  __int64 *v67; // rcx
  __int64 v68; // rbx
  _QWORD *v69; // rdx
  __int64 v70; // r8
  __int64 *v71; // rbx
  __int64 *v72; // rax
  __int64 v73; // rcx
  _QWORD *v74; // rax
  char v75; // al
  __int64 *v76; // r14
  int v77; // r12d
  __int64 v78; // rbx
  __int64 *v79; // rax
  __int64 v80; // rdx
  __int64 *v81; // rcx
  __int64 v82; // rax
  __int64 v83; // rdx
  _QWORD *v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 *v87; // rbx
  int v88; // r12d
  __int64 *v89; // rax
  __int64 v90; // rcx
  __int64 v91; // rdx
  _QWORD *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 *v95; // rbx
  int v96; // r12d
  __int64 *v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rdx
  int v100; // r8d
  unsigned int v101; // eax
  int v102; // r12d
  __int64 v103; // rdx
  __int64 *v104; // rcx
  __int64 v105; // rbx
  __int64 v106; // rdx
  int v107; // r8d
  unsigned int v108; // eax
  __int64 v109; // rdx
  __int64 *v110; // rcx
  __int64 v111; // rbx
  __int64 v112; // rdx
  char v113; // bl
  __int64 v114; // rdx
  const char *v115; // r9
  const struct web::json::value *v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rcx
  void (__fastcall *v123)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v124; // rax
  __int64 v125; // rdx
  __int64 v126; // rax
  __int128 *v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // rdx
  __int64 v130; // rdx
  __int64 v131; // rdx
  _QWORD *v132; // rax
  __int64 v133; // rdx
  _QWORD *v134; // rax
  web::json::value *v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  web::json::value *v138; // rax
  __int64 v139; // rax
  __int64 v140; // rax
  __int128 v141; // xmm6
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // r8
  __int64 v145; // r9
  web::json::value *v146; // rax
  char v147; // bl
  _QWORD *v148; // rax
  unsigned int v149; // eax
  _QWORD *v150; // rax
  __int64 v151; // r14
  _QWORD *v152; // rax
  __int64 v153; // rbx
  _QWORD *v154; // rax
  __int64 v155; // rax
  __int64 v156; // rdx
  __int64 v157; // rdx
  __int64 v158; // rdx
  __int64 v159; // rdx
  __int64 v160; // rdx
  __int64 v161; // rdx
  __int64 v162; // rax
  __int64 v163; // rcx
  __int64 v164; // rax
  __int64 v165; // rbx
  void (__fastcall *v166)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  __int128 *v167; // rdx
  _QWORD *v168; // rax
  __int64 v169; // rax
  __int64 v170; // rdx
  __int64 v171; // rax
  __int64 v172; // rcx
  __int64 v173; // rax
  __int64 v174; // rbx
  void (__fastcall *v175)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *); // r14
  __int128 *v176; // rax
  __int128 *v177; // rdx
  _QWORD *v178; // rax
  __int64 v179; // rax
  __int64 v180; // rdx
  __int64 v181; // rax
  __int64 v182; // rcx
  __int64 v183; // rbx
  __int128 *v184; // rdx
  _QWORD *v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rcx
  __int64 v189; // rax
  __int64 v190; // rbx
  void (__fastcall *v191)(__int64, WCHAR *, __int64 *, __int128 *, __int128 *); // r14
  __int64 v192; // rax
  __int128 *v193; // rdx
  _QWORD *v194; // rax
  __int64 v195; // rax
  __int64 v196; // rdx
  __int64 v197; // rdx
  __int64 v198; // rdx
  __int64 v199; // rax
  __int64 v200; // rcx
  __int64 v201; // rax
  __int64 v202; // rcx
  void (__fastcall *v203)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v204; // rax
  __int64 v205; // rdx
  _QWORD *v206; // rcx
  __int64 v207; // rax
  __int64 v208; // rdx
  __int64 v209; // rdx
  __int64 v210; // rax
  __int64 v211; // rcx
  __int64 v212; // rax
  __int64 v213; // rbx
  __int64 (__fastcall *v214)(__int64, WCHAR *, __int64 *, __int128 *); // r14
  __int128 *v215; // r8
  _QWORD *v216; // rax
  __int64 v217; // rdx
  char v218; // al
  char v219; // bl
  __int64 v220; // rax
  __int64 v221; // rcx
  __int64 v222; // rax
  __int64 v223; // rcx
  void (__fastcall *v224)(__int64, __int64 *, __int128 *); // r9
  _QWORD *v225; // rax
  __int64 v226; // rdx
  const char *v227; // r9
  __int64 v228; // rax
  __int64 v229; // rcx
  void (__fastcall *v230)(__int64, __int128 *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v232; // r9
  __int64 v233; // r11
  __int64 v234; // rax
  volatile signed __int32 *v235; // rbx
  volatile signed __int32 *v236; // rbx
  void (__fastcall *v237)(_QWORD, __int128 *, __int128 *, __int128 *); // r11
  __int64 v238; // rax
  __int64 v239; // rdx
  int v240; // r9d
  _QWORD *v241; // rsi
  __int64 v242; // rcx
  _QWORD *v243; // rax
  char v244; // al
  volatile signed __int32 *v245; // rbx
  Windows::UO::LegacyUOUpdate *v246; // r14
  _QWORD *v247; // rax
  __int64 v248; // rcx
  _QWORD *v249; // rax
  __int64 v250; // rdx
  bool v251; // zf
  _QWORD *v252; // rax
  __int64 v253; // rdx
  _QWORD *v254; // rcx
  __int16 *v255; // rax
  const char *v256; // r9
  __int64 v257; // r11
  __int64 v258; // rax
  __int128 *v259; // rax
  __int64 v260; // rdx
  Windows::UO::LegacyUOProvider *v261; // rcx
  char v262; // bl
  __int64 v263; // rax
  __int64 v264; // rcx
  __int64 v265; // rax
  __int64 v266; // rdi
  void (__fastcall *v267)(__int64, __int128 *, __int128 *); // rbx
  __int128 v268; // xmm6
  __int128 *v269; // rax
  __int64 v270; // rdx
  __int64 v271; // rax
  __int64 v272; // rcx
  __int64 v273; // rbx
  __int128 *v274; // rdx
  _QWORD *v275; // rax
  __int64 v276; // rax
  char SystemBoolOrDefault; // bl
  __int64 v278; // rcx
  _QWORD *v279; // rax
  __int64 v280; // r8
  __int64 v281; // r9
  __int64 v282; // rdi
  __int64 *v283; // rax
  __int64 v284; // rdx
  __int64 v285; // rbx
  __int64 i; // rcx
  __int64 v287; // rax
  __int64 v288; // rdx
  __int64 v289; // rcx
  _QWORD *v290; // rax
  __int64 v291; // rdx
  _DWORD *v292; // rbx
  __int64 v293; // rdi
  __int64 v294; // rax
  int v295; // eax
  char v296; // di
  __int64 v297; // rax
  __int64 v298; // rax
  __int64 v299; // rdx
  volatile signed __int32 *v300; // rbx
  __int64 *v301; // rbx
  __int64 v302; // rax
  __int64 v303; // rax
  volatile signed __int32 *v304; // rdi
  __int64 v305; // rdx
  volatile signed __int32 *v306; // rsi
  __int64 *v307; // rax
  __int64 *j; // rax
  char *v309; // rdx
  void *v310; // rcx
  void *v311; // rcx
  __int64 v312; // rdx
  __int64 v313; // rcx
  __int64 v314; // rax
  _DWORD *v315; // rdi
  volatile signed __int32 *v316; // rbx
  __int64 v317; // rcx
  int v319; // [rsp+40h] [rbp-8C8h]
  __int128 v320; // [rsp+50h] [rbp-8B8h] BYREF
  __int64 v321; // [rsp+60h] [rbp-8A8h]
  __int64 v322; // [rsp+68h] [rbp-8A0h]
  __int64 v323[2]; // [rsp+70h] [rbp-898h] BYREF
  __int64 v324; // [rsp+80h] [rbp-888h]
  __int64 v325; // [rsp+88h] [rbp-880h]
  __int128 v326; // [rsp+90h] [rbp-878h] BYREF
  __int64 v327; // [rsp+A0h] [rbp-868h]
  unsigned __int64 v328; // [rsp+A8h] [rbp-860h]
  __int128 v329; // [rsp+B0h] [rbp-858h] BYREF
  int v330; // [rsp+C0h] [rbp-848h]
  Windows::UO::LegacyUOProvider *v331; // [rsp+C8h] [rbp-840h]
  char v332; // [rsp+D0h] [rbp-838h]
  _QWORD *v333; // [rsp+D8h] [rbp-830h]
  __int128 v334; // [rsp+E0h] [rbp-828h] BYREF
  _DWORD v335[8]; // [rsp+F0h] [rbp-818h] BYREF
  char v336; // [rsp+110h] [rbp-7F8h]
  __int128 v337; // [rsp+118h] [rbp-7F0h] BYREF
  __int64 v338; // [rsp+128h] [rbp-7E0h]
  __int64 v339; // [rsp+130h] [rbp-7D8h]
  __int128 v340; // [rsp+140h] [rbp-7C8h] BYREF
  __int64 v341; // [rsp+150h] [rbp-7B8h] BYREF
  __int64 v342; // [rsp+158h] [rbp-7B0h] BYREF
  __int128 v343; // [rsp+160h] [rbp-7A8h] BYREF
  _DWORD *v344; // [rsp+170h] [rbp-798h] BYREF
  __int128 v345; // [rsp+180h] [rbp-788h] BYREF
  __int64 v346; // [rsp+190h] [rbp-778h] BYREF
  __int64 v347; // [rsp+198h] [rbp-770h] BYREF
  __int64 v348; // [rsp+1A0h] [rbp-768h] BYREF
  __int64 v349; // [rsp+1A8h] [rbp-760h] BYREF
  _QWORD *v350; // [rsp+1B0h] [rbp-758h]
  LPVOID pv; // [rsp+1B8h] [rbp-750h] BYREF
  _DWORD *v352; // [rsp+1C0h] [rbp-748h]
  __int128 v353; // [rsp+1D0h] [rbp-738h] BYREF
  __int128 v354; // [rsp+1E0h] [rbp-728h] BYREF
  __int128 v355; // [rsp+1F0h] [rbp-718h]
  char v356; // [rsp+200h] [rbp-708h]
  __int128 v357; // [rsp+210h] [rbp-6F8h]
  __int128 v358; // [rsp+220h] [rbp-6E8h]
  __int128 v359; // [rsp+230h] [rbp-6D8h]
  __int128 v360; // [rsp+240h] [rbp-6C8h]
  __int128 v361; // [rsp+250h] [rbp-6B8h]
  __int128 v362; // [rsp+260h] [rbp-6A8h]
  __int128 v363; // [rsp+270h] [rbp-698h]
  __int128 v364; // [rsp+280h] [rbp-688h]
  Windows::UO::LegacyUOProvider *v365; // [rsp+290h] [rbp-678h]
  __int128 v366; // [rsp+2A0h] [rbp-668h]
  __int128 v367; // [rsp+2B0h] [rbp-658h]
  char v368[8]; // [rsp+2C0h] [rbp-648h] BYREF
  volatile signed __int32 *v369; // [rsp+2C8h] [rbp-640h]
  __int128 v370; // [rsp+2D0h] [rbp-638h] BYREF
  _BYTE v371[16]; // [rsp+2E0h] [rbp-628h] BYREF
  __int64 v372; // [rsp+2F0h] [rbp-618h] BYREF
  _BYTE v373[16]; // [rsp+2F8h] [rbp-610h] BYREF
  __int64 v374; // [rsp+308h] [rbp-600h] BYREF
  __int64 v375; // [rsp+310h] [rbp-5F8h] BYREF
  __int64 v376; // [rsp+318h] [rbp-5F0h] BYREF
  __int64 v377; // [rsp+320h] [rbp-5E8h] BYREF
  _BYTE v378[16]; // [rsp+328h] [rbp-5E0h] BYREF
  __int128 v379; // [rsp+338h] [rbp-5D0h]
  __int128 v380; // [rsp+350h] [rbp-5B8h]
  __int128 v381; // [rsp+360h] [rbp-5A8h]
  __int128 v382; // [rsp+370h] [rbp-598h]
  __int128 v383; // [rsp+380h] [rbp-588h]
  __int128 v384; // [rsp+390h] [rbp-578h]
  __int128 v385; // [rsp+3A0h] [rbp-568h]
  __int128 v386; // [rsp+3B0h] [rbp-558h]
  __int128 v387; // [rsp+3C0h] [rbp-548h]
  __int128 v388; // [rsp+3D0h] [rbp-538h]
  __int128 v389; // [rsp+3E0h] [rbp-528h]
  __int128 v390; // [rsp+3F0h] [rbp-518h]
  __int128 v391; // [rsp+400h] [rbp-508h]
  __int128 v392; // [rsp+410h] [rbp-4F8h]
  __int128 v393; // [rsp+420h] [rbp-4E8h]
  __int128 v394; // [rsp+430h] [rbp-4D8h]
  __int128 v395; // [rsp+440h] [rbp-4C8h]
  __int128 v396; // [rsp+450h] [rbp-4B8h]
  __int128 v397; // [rsp+460h] [rbp-4A8h]
  __int128 v398; // [rsp+470h] [rbp-498h]
  __int128 v399; // [rsp+480h] [rbp-488h] BYREF
  __int64 v400; // [rsp+490h] [rbp-478h]
  __int64 v401; // [rsp+498h] [rbp-470h]
  __int128 v402; // [rsp+4A0h] [rbp-468h]
  __int128 v403; // [rsp+4B0h] [rbp-458h]
  _BYTE v404[32]; // [rsp+4C0h] [rbp-448h] BYREF
  _BYTE v405[32]; // [rsp+4E0h] [rbp-428h] BYREF
  __int128 v406; // [rsp+500h] [rbp-408h]
  __int128 v407; // [rsp+510h] [rbp-3F8h]
  _BYTE v408[32]; // [rsp+520h] [rbp-3E8h] BYREF
  _BYTE v409[16]; // [rsp+540h] [rbp-3C8h] BYREF
  _BYTE v410[16]; // [rsp+550h] [rbp-3B8h] BYREF
  _BYTE v411[16]; // [rsp+560h] [rbp-3A8h] BYREF
  _BYTE v412[16]; // [rsp+570h] [rbp-398h] BYREF
  _BYTE v413[16]; // [rsp+580h] [rbp-388h] BYREF
  _BYTE v414[16]; // [rsp+590h] [rbp-378h] BYREF
  _BYTE v415[16]; // [rsp+5A0h] [rbp-368h] BYREF
  _BYTE v416[16]; // [rsp+5B0h] [rbp-358h] BYREF
  _BYTE v417[16]; // [rsp+5C0h] [rbp-348h] BYREF
  _BYTE v418[16]; // [rsp+5D0h] [rbp-338h] BYREF
  _BYTE v419[16]; // [rsp+5E0h] [rbp-328h] BYREF
  _BYTE v420[16]; // [rsp+5F0h] [rbp-318h] BYREF
  char v421[16]; // [rsp+600h] [rbp-308h] BYREF
  _BYTE v422[16]; // [rsp+610h] [rbp-2F8h] BYREF
  char v423[16]; // [rsp+620h] [rbp-2E8h] BYREF
  _BYTE v424[16]; // [rsp+630h] [rbp-2D8h] BYREF
  _BYTE v425[16]; // [rsp+640h] [rbp-2C8h] BYREF
  _BYTE v426[16]; // [rsp+650h] [rbp-2B8h] BYREF
  _BYTE v427[16]; // [rsp+660h] [rbp-2A8h] BYREF
  char v428[16]; // [rsp+670h] [rbp-298h] BYREF
  char v429[16]; // [rsp+680h] [rbp-288h] BYREF
  char v430[16]; // [rsp+690h] [rbp-278h] BYREF
  char v431[16]; // [rsp+6A0h] [rbp-268h] BYREF
  char v432[16]; // [rsp+6B0h] [rbp-258h] BYREF
  char v433[16]; // [rsp+6C0h] [rbp-248h] BYREF
  char v434[16]; // [rsp+6D0h] [rbp-238h] BYREF
  char v435[16]; // [rsp+6E0h] [rbp-228h] BYREF
  char v436[16]; // [rsp+6F0h] [rbp-218h] BYREF
  char v437[16]; // [rsp+700h] [rbp-208h] BYREF
  char v438[16]; // [rsp+710h] [rbp-1F8h] BYREF
  _QWORD Src[2]; // [rsp+720h] [rbp-1E8h] BYREF
  __int64 v440; // [rsp+730h] [rbp-1D8h]
  unsigned __int64 v441; // [rsp+738h] [rbp-1D0h]
  __int128 v442; // [rsp+740h] [rbp-1C8h] BYREF
  WCHAR geoName[8]; // [rsp+750h] [rbp-1B8h] BYREF
  __int64 v444; // [rsp+760h] [rbp-1A8h]
  __int64 v445; // [rsp+768h] [rbp-1A0h]
  __int64 v446; // [rsp+770h] [rbp-198h] BYREF
  void *Block[2]; // [rsp+778h] [rbp-190h] BYREF
  __int128 v448; // [rsp+788h] [rbp-180h] BYREF
  __int64 v449; // [rsp+798h] [rbp-170h]
  Windows::UO::LegacyUOUpdate *v450; // [rsp+7A0h] [rbp-168h] BYREF
  volatile signed __int32 *v451; // [rsp+7A8h] [rbp-160h]
  char v452; // [rsp+7B0h] [rbp-158h]
  __int128 v453; // [rsp+7B8h] [rbp-150h] BYREF
  __int64 v454; // [rsp+7C8h] [rbp-140h] BYREF
  _QWORD v455[2]; // [rsp+7D0h] [rbp-138h] BYREF
  __int64 v456; // [rsp+7E0h] [rbp-128h]
  unsigned __int64 v457; // [rsp+7E8h] [rbp-120h]
  _DWORD v458[8]; // [rsp+7F0h] [rbp-118h] BYREF
  __int64 v459; // [rsp+810h] [rbp-F8h]
  volatile signed __int32 *v460; // [rsp+818h] [rbp-F0h]
  __int128 v461; // [rsp+820h] [rbp-E8h] BYREF
  __int64 v462; // [rsp+830h] [rbp-D8h]
  __int128 v463; // [rsp+838h] [rbp-D0h] BYREF
  __int64 v464; // [rsp+848h] [rbp-C0h]
  unsigned __int64 v465; // [rsp+850h] [rbp-B8h]
  __int128 v466; // [rsp+858h] [rbp-B0h] BYREF
  __int64 v467; // [rsp+868h] [rbp-A0h]
  _BYTE v468[16]; // [rsp+870h] [rbp-98h] BYREF
  __int64 v469; // [rsp+880h] [rbp-88h]
  __int128 v470; // [rsp+890h] [rbp-78h] BYREF
  __int64 v471; // [rsp+8A0h] [rbp-68h]
  _BYTE v472[24]; // [rsp+8A8h] [rbp-60h] BYREF
  char v473; // [rsp+8C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+0h]

  v352 = a2;
  v5 = a1;
  v331 = a1;
  v365 = a1;
  v344 = a2;
  v6 = 0;
  v319 = 0;
  v330 = 0;
  Block[1] = 0;
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(80);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  Block[0] = v7;
  std::lock_guard<std::mutex>::lock_guard<std::mutex>(&v376, (char *)v5 + 128);
  v470 = 0;
  v471 = 0;
  Windows::UO::GetAllowedOobeUpdaters(&v470);
  Windows::UO::GetBlockedOobeUpdaters(v472);
  v453 = 0;
  System = SystemInterface::Providers::GetSystem(v422);
  v9 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 32LL))(v9, &v453);
  std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v422);
  if ( !*(_BYTE *)(a4 + 3)
    || (v10 = SystemInterface::Providers::GetSystem(&v334),
        v6 = 1,
        v319 = 1,
        v11 = *(_QWORD *)v10 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 4LL),
        v12 = 1,
        (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 168LL))(v11)) )
  {
    v12 = 0;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    v319 = v6;
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v334);
  }
  if ( v12 )
  {
    v461 = 0;
    v462 = 0;
    v13 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v453 + 88LL);
    v14 = -1;
    do
      ++v14;
    while ( SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT[v14] );
    v323[0] = (__int64)SystemInterface::Registry::USO_USCHEDULER_OOBE_ROOT;
    v323[1] = v14;
    *(_QWORD *)&v353 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
    v15 = -1;
    do
      ++v15;
    while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v15] );
    *((_QWORD *)&v353 + 1) = v15;
    v334 = *(_OWORD *)v323;
    v345 = v353;
    v13(v453, &v461, &v345, &v334);
    v16 = (_QWORD *)*((_QWORD *)&v461 + 1);
    v350 = (_QWORD *)*((_QWORD *)&v461 + 1);
    v17 = (_QWORD *)v461;
    v18 = v341;
    v19 = v342;
    while ( 1 )
    {
      v333 = v17;
      if ( v17 == v16 )
      {
        try
        {
          v5 = v331;
          Windows::UO::LegacyUOProvider::StageConfigBasedExpeditedUpdaters(v331);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x195,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
            v227);
          v6 = v319;
          v5 = v365;
          v331 = v365;
          v352 = v344;
        }
        v228 = SystemInterface::Providers::GetSystem(v368);
        v229 = *(_QWORD *)v228 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v228 + 8LL) + 4LL);
        v230 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v229 + 24LL))(
                                                                           v229,
                                                                           &v340)
                                                          + 40LL);
        traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                               L"StartOobeAppsScan_OobeAppReady",
                                               &word_14047F996,
                                               0);
        if ( traits_2_unsigned_short == &word_14047F996
          || (v234 = ((char *)traits_2_unsigned_short - (char *)L"StartOobeAppsScan_OobeAppReady") >> 1, v234 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v232);
        }
        *(_QWORD *)&v334 = L"StartOobeAppsScan_OobeAppReady";
        *((_QWORD *)&v334 + 1) = v234;
        v329 = v334;
        v230(v233, &v329);
        v235 = (volatile signed __int32 *)*((_QWORD *)&v340 + 1);
        if ( *((_QWORD *)&v340 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v340 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v235)(v235);
            if ( _InterlockedExchangeAdd(v235 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v235 + 8LL))(v235);
          }
        }
        v236 = v369;
        if ( v369 )
        {
          if ( _InterlockedExchangeAdd(v369 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v236)(v236);
            if ( _InterlockedExchangeAdd(v236 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v236 + 8LL))(v236);
          }
        }
        std::vector<std::filesystem::path>::_Tidy(&v461);
        break;
      }
      *(_QWORD *)&v393 = L"{}\\{}";
      *((_QWORD *)&v393 + 1) = 5;
      *(_OWORD *)v323 = v393;
      std::format<wchar_t const * const &,std::wstring const &>(Src);
      v20 = *(unsigned __int8 (__fastcall **)(_QWORD, WCHAR *, __int64 *))(*(_QWORD *)v453 + 8LL);
      v21 = Src;
      if ( v441 > 7 )
        v21 = (_QWORD *)Src[0];
      *(_QWORD *)&v394 = v21;
      *((_QWORD *)&v394 + 1) = v440;
      *(_QWORD *)&v395 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v22 = -1;
      do
        ++v22;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v22] );
      *((_QWORD *)&v395 + 1) = v22;
      *(_OWORD *)v323 = v394;
      *(_OWORD *)geoName = v395;
      if ( v20(v453, geoName, v323) )
      {
        v23 = Src;
        if ( v441 > 7 )
          v23 = (_QWORD *)Src[0];
        *(_QWORD *)&v396 = v23;
        *((_QWORD *)&v396 + 1) = v440;
        v24 = v17[2];
        v25 = v17;
        if ( v17[3] > 7u )
          v25 = (_QWORD *)*v17;
        *(_QWORD *)&v397 = v25;
        *((_QWORD *)&v397 + 1) = v24;
        *(_OWORD *)v323 = v396;
        *(_OWORD *)geoName = v397;
        if ( !(unsigned __int8)Windows::UO::LegacyUOProvider::ShouldRecoverStoreExpeditedRegistration(
                                 v331,
                                 geoName,
                                 &v453,
                                 v323) )
          goto LABEL_245;
      }
      *(_QWORD *)&v398 = L"{}\\{}";
      *((_QWORD *)&v398 + 1) = 5;
      *(_OWORD *)v323 = v398;
      std::format<wchar_t const * const &,std::wstring const &>(v455);
      v27 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, WCHAR *, __int64 *))(*(_QWORD *)v453 + 104LL);
      v28 = Src;
      if ( v441 > 7 )
        v28 = (_QWORD *)Src[0];
      *(_QWORD *)&v402 = v28;
      *((_QWORD *)&v402 + 1) = v440;
      v29 = -1;
      do
        ++v29;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v29] );
      *(_QWORD *)&v403 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      *((_QWORD *)&v403 + 1) = v29;
      v30 = v455;
      if ( v457 > 7 )
        v30 = (_QWORD *)v455[0];
      *(_QWORD *)&v406 = v30;
      *((_QWORD *)&v406 + 1) = v456;
      *(_QWORD *)&v407 = SystemInterface::Registry::USOROOT_REDIRECTION_ID;
      v31 = -1;
      do
        ++v31;
      while ( SystemInterface::Registry::USOROOT_REDIRECTION_ID[v31] );
      *((_QWORD *)&v407 + 1) = v31;
      *(_OWORD *)v323 = v402;
      *(_OWORD *)geoName = v403;
      v442 = v406;
      v320 = v407;
      v27(v453, &v320, &v442, geoName, v323);
      v32 = v453;
      v33 = *(void (__fastcall **)(__int64, _DWORD *, WCHAR *, __int64 *, __int128 *))(*(_QWORD *)v453 + 56LL);
      v34 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v434, L"updaterPriority");
      v35 = Src;
      if ( v441 > 7 )
        v35 = (_QWORD *)Src[0];
      *(_QWORD *)&v379 = v35;
      *((_QWORD *)&v379 + 1) = v440;
      *(_QWORD *)&v380 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v36 = -1;
      do
        ++v36;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v36] );
      *((_QWORD *)&v380 + 1) = v36;
      v320 = *v34;
      *(_OWORD *)v323 = v379;
      *(_OWORD *)geoName = v380;
      v33(v32, v458, geoName, v323, &v320);
      v37 = v453;
      v38 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(*(_QWORD *)v453 + 64LL);
      if ( !(_BYTE)v460 || (_BYTE)v459 || (v39 = v458[0], v458[0] > 0x64u) )
        v39 = Windows::UO::LegacyUOProvider::sc_defaultUpdaterPriority;
      v335[0] = v39;
      v336 = 0;
      v40 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v435, L"updaterPriority");
      v41 = Src;
      if ( v441 > 7 )
        v41 = (_QWORD *)Src[0];
      *(_QWORD *)&v381 = v41;
      *((_QWORD *)&v381 + 1) = v440;
      *(_QWORD *)&v382 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v42 = -1;
      do
        ++v42;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v42] );
      *((_QWORD *)&v382 + 1) = v42;
      v320 = *v40;
      *(_OWORD *)v323 = v381;
      *(_OWORD *)geoName = v382;
      v38(v37, geoName, v323, &v320, v335);
      if ( v336 != -1 && v336 && v336 != 1 )
        std::wstring::~wstring(v335, v43);
      v44 = SystemInterface::Providers::GetSystem(v418);
      v45 = *(_QWORD *)v44 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v44 + 8LL) + 4LL);
      v46 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v45 + 40LL))(v45, v419);
      v47 = *(_QWORD *)v46;
      v48 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v46 + 64LL);
      v320 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                          v436,
                          L"SupportsThirdPartyExpedite");
      LOBYTE(v49) = 1;
      LOBYTE(v48) = v48(v47, &v320, v49);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v419);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v418);
      if ( (_BYTE)v48 )
      {
        v50 = SystemInterface::Providers::GetSystem(v424);
        v51 = *(_QWORD *)v50 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v50 + 8LL) + 4LL);
        v52 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v51 + 32LL))(v51, v417);
        v399 = 0;
        v400 = 0;
        v401 = 7;
        LOWORD(v399) = 0;
        *(_QWORD *)&v383 = &v399;
        *((_QWORD *)&v383 + 1) = 0;
        v53 = (_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v437, L"expeditedPayload");
        v54 = Src;
        if ( v441 > 7 )
          v54 = (_QWORD *)Src[0];
        *(_QWORD *)&v384 = v54;
        *((_QWORD *)&v384 + 1) = v440;
        *(_QWORD *)&v392 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v55 = -1;
        do
          ++v55;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v55] );
        *((_QWORD *)&v392 + 1) = v55;
        v320 = v383;
        *(_OWORD *)v323 = *v53;
        *(_OWORD *)geoName = v384;
        v442 = v392;
        SystemInterface::Registry::GetSystemValueOrDefault(
          v52,
          (unsigned int)v468,
          (unsigned int)&v442,
          (unsigned int)geoName,
          (__int64)v323,
          (__int64)&v320);
        std::wstring::~wstring(&v399, v56);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v417);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v424);
        if ( v469 )
        {
          *(_QWORD *)&v442 = 0;
          web::json::value::object(&v442);
          v58 = (__int64 *)web::json::value::object(&v375);
          v320 = 0;
          v321 = 0;
          v322 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v320, L"NdupProperties", 14);
          v59 = (__int64 *)web::json::value::operator[](&v442, &v320);
          if ( v59 != v58 )
          {
            v60 = *v59;
            *v59 = *v58;
            *v58 = v60;
          }
          std::wstring::~wstring(&v320, v59);
          if ( v375 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v375 + 192LL))(v375, 1);
          web::json::value::value((web::json::value *)&v346, 30);
          v61 = v6 | 0x4000000;
          v320 = 0;
          v321 = 0;
          v322 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v320, L"updaterMinsToWaitAfterOobeFailure", 33);
          v63 = (__int64 *)web::json::value::operator[](&v442, &v320);
          if ( v63 == &v346 )
          {
            v64 = v346;
          }
          else
          {
            v64 = *v63;
            *v63 = v346;
            v346 = v64;
          }
          std::wstring::~wstring(&v320, v62);
          if ( v64 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 192LL))(v64, 1);
          web::json::value::value((web::json::value *)&v347, 1);
          v65 = v61 | 0x8000000;
          v320 = 0;
          v321 = 0;
          v322 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v320, L"BusinessCritical", 16);
          v67 = (__int64 *)web::json::value::operator[](&v442, &v320);
          if ( v67 == &v347 )
          {
            v68 = v347;
          }
          else
          {
            v68 = *v67;
            *v67 = v347;
            v347 = v68;
          }
          std::wstring::~wstring(&v320, v66);
          if ( v68 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 192LL))(v68, 1);
          v69 = v333;
          if ( v333[3] > 7u )
            v69 = (_QWORD *)*v333;
          v320 = 0;
          v321 = 0;
          v322 = 0;
          v70 = -1;
          do
            ++v70;
          while ( *((_WORD *)v69 + v70) );
          std::wstring::_Construct<1,wchar_t const *>(&v320, v69, v70);
          v71 = (__int64 *)web::json::value::string(&v377, &v320);
          *(_OWORD *)geoName = 0;
          v444 = 0;
          v445 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"id", 2);
          v72 = (__int64 *)web::json::value::operator[](&v442, geoName);
          if ( v72 != v71 )
          {
            v73 = *v72;
            *v72 = *v71;
            *v71 = v73;
          }
          std::wstring::~wstring(geoName, v72);
          if ( v377 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v377 + 192LL))(v377, 1);
          v446 = 0;
          web::json::value::parse(&v446, v468);
          *(_OWORD *)geoName = 0;
          v444 = 0;
          v445 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"AllowedInOobe", 13);
          if ( (*(unsigned __int8 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v446 + 8LL))(v446, geoName) )
          {
            *(_OWORD *)v323 = 0;
            v324 = 0;
            v325 = 0;
            std::wstring::_Construct<1,wchar_t const *>(v323, L"AllowedInOobe", 13);
            v74 = (_QWORD *)web::json::value::at(&v446, v323);
            v75 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v74 + 136LL))(*v74);
            web::json::value::value((web::json::value *)&v341, v75);
            v330 |= 1u;
            v76 = &v341;
            v77 = v65 | 6;
            v18 = v341;
            v78 = v341;
          }
          else
          {
            web::json::value::value((web::json::value *)&v342, 0);
            v330 |= 2u;
            v76 = &v342;
            v77 = v65 | 8;
            v19 = v342;
            v78 = v342;
          }
          v320 = 0;
          v321 = 0;
          v322 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v320, L"allowedPreOobeComplete", 22);
          v79 = (__int64 *)web::json::value::operator[](&v442, &v320);
          v81 = v79;
          if ( v79 != v76 )
          {
            v82 = *v79;
            *v81 = v78;
            *v76 = v82;
            v18 = v341;
            v19 = v342;
          }
          std::wstring::~wstring(&v320, v80);
          if ( (v77 & 8) != 0 )
          {
            v77 &= ~8u;
            if ( v19 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 192LL))(v19, 1);
          }
          if ( (v77 & 4) != 0 )
          {
            v77 &= ~4u;
            if ( v18 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 192LL))(v18, 1);
          }
          if ( (v77 & 2) != 0 )
          {
            v77 &= ~2u;
            std::wstring::~wstring(v323, v83);
          }
          std::wstring::~wstring(geoName, v83);
          v326 = 0;
          v327 = 0;
          v328 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v326, L"PFN", 3);
          if ( (*(unsigned __int8 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v446 + 8LL))(v446, &v326) )
          {
            v337 = 0;
            v338 = 0;
            v339 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v337, L"PFN", 3);
            v84 = (_QWORD *)web::json::value::at(&v446, &v337);
            v85 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v84 + 176LL))(*v84);
            v86 = std::wstring::wstring(v335, v85);
            v87 = (__int64 *)web::json::value::string(&v372, v86);
            v88 = v77 | 0x30;
          }
          else
          {
            v320 = 0;
            v321 = 0;
            v322 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v320, &psz, 0);
            v87 = (__int64 *)web::json::value::string(&v374, &v320);
            v88 = v77 | 0x40;
          }
          *(_OWORD *)geoName = 0;
          v444 = 0;
          v445 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"PFN", 3);
          v89 = (__int64 *)web::json::value::operator[](&v442, geoName);
          if ( v89 != v87 )
          {
            v90 = *v89;
            *v89 = *v87;
            *v87 = v90;
          }
          std::wstring::~wstring(geoName, v89);
          if ( (v88 & 0x40) != 0 )
          {
            v88 &= ~0x40u;
            if ( v374 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v374 + 192LL))(v374, 1);
          }
          if ( (v88 & 0x20) != 0 )
          {
            v88 &= ~0x20u;
            if ( v372 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v372 + 192LL))(v372, 1);
          }
          if ( (v88 & 0x10) != 0 )
          {
            v88 &= ~0x10u;
            std::wstring::~wstring(&v337, v91);
          }
          std::wstring::~wstring(&v326, v91);
          *(_OWORD *)geoName = 0;
          v444 = 0;
          v445 = 0;
          std::wstring::_Construct<1,wchar_t const *>(geoName, L"Endpoint", 8);
          if ( (*(unsigned __int8 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)v446 + 8LL))(v446, geoName) )
          {
            v320 = 0;
            v321 = 0;
            v322 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v320, L"Endpoint", 8);
            v92 = (_QWORD *)web::json::value::at(&v446, &v320);
            v93 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v92 + 176LL))(*v92);
            v94 = std::wstring::wstring(v335, v93);
            v95 = (__int64 *)web::json::value::string(&v353, v94);
            v96 = v88 | 0x180;
          }
          else
          {
            v326 = 0;
            v327 = 0;
            v328 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v326, &psz, 0);
            v95 = (__int64 *)web::json::value::string(&v343, &v326);
            v96 = v88 | 0x200;
          }
          v337 = 0;
          v338 = 0;
          v339 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v337, L"Endpoint", 8);
          v97 = (__int64 *)web::json::value::operator[](&v442, &v337);
          if ( v97 != v95 )
          {
            v98 = *v97;
            *v97 = *v95;
            *v95 = v98;
          }
          std::wstring::~wstring(&v337, v97);
          if ( (v96 & 0x200) != 0 )
          {
            v96 &= ~0x200u;
            if ( (_QWORD)v343 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v343 + 192LL))(v343, 1);
          }
          if ( (v96 & 0x100) != 0 )
          {
            v96 &= ~0x100u;
            if ( (_QWORD)v353 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v353 + 192LL))(v353, 1);
          }
          if ( (v96 & 0x80u) != 0 )
          {
            v96 &= ~0x80u;
            std::wstring::~wstring(&v320, v99);
          }
          std::wstring::~wstring(geoName, v99);
          *(_QWORD *)geoName = &v446;
          v337 = 0;
          v338 = 0;
          v339 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v337, L"MaxRetryCount", 13);
          v101 = Windows::UO::LegacyUOProvider::Scan_::_19_::_lambda_1_::operator()(
                   (unsigned int)geoName,
                   (unsigned int)&v337,
                   v100,
                   5,
                   1);
          web::json::value::value((web::json::value *)&v348, v101);
          v102 = v96 | 0x10000000;
          v326 = 0;
          v327 = 0;
          v328 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v326, L"allowedFailureCount", 19);
          v104 = (__int64 *)web::json::value::operator[](&v442, &v326);
          if ( v104 == &v348 )
          {
            v105 = v348;
          }
          else
          {
            v105 = *v104;
            *v104 = v348;
            v348 = v105;
          }
          std::wstring::~wstring(&v326, v103);
          if ( v105 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v105 + 192LL))(v105, 1);
          std::wstring::~wstring(&v337, v106);
          v337 = 0;
          v338 = 0;
          v339 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v337, L"TimeoutDurationInMinutes", 24);
          v108 = Windows::UO::LegacyUOProvider::Scan_::_19_::_lambda_1_::operator()(
                   (unsigned int)geoName,
                   (unsigned int)&v337,
                   v107,
                   30,
                   15);
          web::json::value::value((web::json::value *)&v349, v108);
          v6 = v102 | 0x20000000;
          v319 = v6;
          v326 = 0;
          v327 = 0;
          v328 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v326, L"updaterOOBETimeoutInMinutes", 27);
          v110 = (__int64 *)web::json::value::operator[](&v442, &v326);
          if ( v110 == &v349 )
          {
            v111 = v349;
          }
          else
          {
            v111 = *v110;
            *v110 = v349;
            v349 = v111;
          }
          std::wstring::~wstring(&v326, v109);
          if ( v111 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v111 + 192LL))(v111, 1);
          std::wstring::~wstring(&v337, v112);
          v326 = 0;
          v327 = 0;
          v328 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v326, L"ExcludedRegions", 15);
          v113 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v446 + 8LL))(v446, &v326);
          std::wstring::~wstring(&v326, v114);
          if ( v113 )
          {
            *(_QWORD *)geoName = 0;
            if ( !GetUserDefaultGeoName(geoName, 4) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x133,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\LegacyUOProvider.cpp",
                v115);
            v454 = 0;
            v326 = 0;
            v327 = 0;
            v328 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v326, L"ExcludedRegions", 15);
            v116 = (const struct web::json::value *)web::json::value::at(&v446, &v326);
            web::json::value::value((web::json::value *)&v454, v116);
            std::wstring::~wstring(&v326, v117);
            v118 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v454 + 152LL))(v454);
            if ( (unsigned __int8)std::ranges::_Any_of_fn::operator()_web::json::array_const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_23_::_lambda_2___(
                                    v118,
                                    geoName) )
            {
              v119 = SystemInterface::Providers::GetSystem(v426);
              v120 = *(_QWORD *)v119 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v119 + 8LL) + 4LL);
              v121 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v120 + 32LL))(v120, v425);
              v122 = *(_QWORD *)v121;
              v123 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v121 + 72LL);
              v124 = Src;
              if ( v441 > 7 )
                v124 = (_QWORD *)Src[0];
              *(_QWORD *)&v385 = v124;
              *((_QWORD *)&v385 + 1) = v440;
              *(_QWORD *)&v386 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
              v125 = -1;
              do
                ++v125;
              while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v125] );
              *((_QWORD *)&v386 + 1) = v125;
              v320 = v385;
              *(_OWORD *)v323 = v386;
              v123(v122, v323, &v320);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v425);
              std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v426);
              v323[0] = (__int64)geoName;
              wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v438, v323);
              v17 = v333;
              v126 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v333);
              *(_QWORD *)&v387 = v126;
              v128 = -1;
              do
                ++v128;
              while ( *(_WORD *)(v126 + 2 * v128) );
              *((_QWORD *)&v387 + 1) = v128;
              v320 = *v127;
              *(_OWORD *)v323 = v387;
              Windows::UO::LogLegacyOobeUpdateIgnoredExcludedRegion(v323, &v320);
              std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v454);
              if ( v446 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v446 + 192LL))(v446, 1);
              std::unique_ptr<web::json::details::_Object>::~unique_ptr<web::json::details::_Object>(&v442);
              std::wstring::~wstring(v468, v129);
              if ( (_BYTE)v460 && (char)v459 != -1 && (_BYTE)v459 && (char)v459 != 1 )
                goto LABEL_139;
              goto LABEL_140;
            }
            if ( v454 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v454 + 192LL))(v454, 1);
          }
          v463 = 0;
          v464 = 0;
          v465 = 7;
          LOWORD(v463) = 0;
          v326 = 0;
          v327 = 0;
          v328 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v326, L"id", 2);
          v6 |= 0x400u;
          v319 = v6;
          v132 = (_QWORD *)web::json::value::operator[](&v442, &v326);
          if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v132 + 88LL))(*v132) != 2 )
            goto LABEL_151;
          std::wstring::wstring(v335, L"id");
          v6 |= 0x800u;
          v319 = v6;
          v134 = (_QWORD *)web::json::value::operator[](&v442, v335);
          if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v134 + 176LL))(*v134) + 16) )
            goto LABEL_151;
          std::wstring::wstring(&v354, L"PFN");
          v6 |= 0x1000u;
          v319 = v6;
          v135 = (web::json::value *)web::json::value::operator[](&v442, &v354);
          if ( !web::json::value::is_string(v135) )
            goto LABEL_151;
          std::wstring::wstring(v405, L"PFN");
          v6 |= 0x2000u;
          v319 = v6;
          v136 = web::json::value::operator[](&v442, v405);
          v137 = web::json::value::as_string(v136);
          if ( (unsigned __int8)std::wstring::empty(v137) )
            goto LABEL_151;
          std::wstring::wstring(v404, L"Endpoint");
          v6 |= 0x4000u;
          v319 = v6;
          v138 = (web::json::value *)web::json::value::operator[](&v442, v404);
          if ( !web::json::value::is_string(v138) )
            goto LABEL_151;
          std::wstring::wstring(v408, L"Endpoint");
          v6 |= 0x8000u;
          v319 = v6;
          v139 = web::json::value::operator[](&v442, v408);
          v140 = web::json::value::as_string(v139);
          if ( (unsigned __int8)std::wstring::empty(v140) )
            goto LABEL_151;
          v141 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v428, L"https");
          std::wstring::wstring(geoName, L"Endpoint");
          v6 |= 0x10000u;
          v319 = v6;
          v142 = web::json::value::operator[](&v442, geoName);
          v143 = web::json::value::as_string(v142);
          v320 = v141;
          *(_OWORD *)v323 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                                         v429,
                                         v143,
                                         v144,
                                         v145);
          if ( !(unsigned __int8)Strings::istarts_with(v323, &v320)
            || (std::wstring::wstring(&v337, L"updaterOOBETimeoutInMinutes"),
                v6 |= 0x20000u,
                v319 = v6,
                v146 = (web::json::value *)web::json::value::operator[](&v442, &v337),
                v147 = 1,
                !web::json::value::is_integer(v146)) )
          {
LABEL_151:
            v147 = 0;
          }
          if ( (v6 & 0x20000) != 0 )
          {
            v6 &= ~0x20000u;
            v319 = v6;
            std::wstring::~wstring(&v337, v133);
          }
          if ( (v6 & 0x10000) != 0 )
          {
            v6 &= ~0x10000u;
            v319 = v6;
            std::wstring::~wstring(geoName, v133);
          }
          if ( (v6 & 0x8000) != 0 )
          {
            v6 &= ~0x8000u;
            v319 = v6;
            std::wstring::~wstring(v408, v133);
          }
          if ( (v6 & 0x4000) != 0 )
          {
            v6 &= ~0x4000u;
            v319 = v6;
            std::wstring::~wstring(v404, v133);
          }
          if ( (v6 & 0x2000) != 0 )
          {
            v6 &= ~0x2000u;
            v319 = v6;
            std::wstring::~wstring(v405, v133);
          }
          if ( (v6 & 0x1000) != 0 )
          {
            v6 &= ~0x1000u;
            v319 = v6;
            std::wstring::~wstring(&v354, v133);
          }
          if ( (v6 & 0x800) != 0 )
          {
            v6 &= ~0x800u;
            v319 = v6;
            std::wstring::~wstring(v335, v133);
          }
          if ( (v6 & 0x400) != 0 )
          {
            v6 &= ~0x400u;
            v319 = v6;
            std::wstring::~wstring(&v326, v133);
          }
          if ( !v147 )
          {
            v199 = SystemInterface::Providers::GetSystem(v373);
            v200 = *(_QWORD *)v199 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v199 + 8LL) + 4LL);
            v201 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v200 + 32LL))(v200, v416);
            v202 = *(_QWORD *)v201;
            v203 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v201 + 72LL);
            v204 = Src;
            if ( v441 > 7 )
              v204 = (_QWORD *)Src[0];
            *(_QWORD *)&v361 = v204;
            *((_QWORD *)&v361 + 1) = v440;
            *(_QWORD *)&v362 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
            v205 = -1;
            do
              ++v205;
            while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v205] );
            *((_QWORD *)&v362 + 1) = v205;
            v320 = v361;
            *(_OWORD *)v323 = v362;
            v203(v202, v323, &v320);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v416);
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v373);
            v17 = v333;
            v206 = v333;
            if ( v333[3] > 7u )
              v206 = (_QWORD *)*v333;
            *(_QWORD *)&v364 = v206;
            v207 = -1;
            do
              ++v207;
            while ( *((_WORD *)v206 + v207) );
            *((_QWORD *)&v364 + 1) = v207;
            v320 = v364;
            Windows::UO::LogLegacyOobeUpdateInvalidExpeditedPayload(&v320);
            std::wstring::~wstring(&v463, v208);
            if ( v446 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v446 + 192LL))(v446, 1);
            if ( (_QWORD)v442 )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v442 + 192LL))(v442, 1);
            std::wstring::~wstring(v468, v209);
            if ( (_BYTE)v460 && (char)v459 != -1 && (_BYTE)v459 && (char)v459 != 1 )
LABEL_139:
              std::wstring::~wstring(v458, v130);
LABEL_140:
            std::wstring::~wstring(v455, v130);
            std::wstring::~wstring(Src, v131);
            v16 = v350;
            goto LABEL_246;
          }
          std::wstring::wstring(v404, L"updaterOOBETimeoutInMinutes");
          v148 = (_QWORD *)web::json::value::operator[](&v442, v404);
          v149 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v148 + 128LL))(*v148);
          v323[0] = std::to_wstring(&v326, v149);
          std::wstring::wstring(v405, L"Endpoint");
          v150 = (_QWORD *)web::json::value::operator[](&v442, v405);
          v151 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v150 + 176LL))(*v150);
          std::wstring::wstring(&v354, L"PFN");
          v152 = (_QWORD *)web::json::value::operator[](&v442, &v354);
          v153 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v152 + 176LL))(*v152);
          std::wstring::wstring(v335, L"id");
          v154 = (_QWORD *)web::json::value::operator[](&v442, v335);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v154 + 176LL))(*v154);
          *(_QWORD *)&v388 = L"{} {} {} {} {}";
          *((_QWORD *)&v388 + 1) = 14;
          v320 = v388;
          v155 = std::format<wchar_t const (&)[29],std::wstring const &,std::wstring const &,std::wstring const &,std::wstring>(
                   v408,
                   v153,
                   v151,
                   v323[0]);
          std::wstring::operator=(&v463, v155);
          std::wstring::~wstring(v408, v156);
          std::wstring::~wstring(v335, v157);
          std::wstring::~wstring(&v354, v158);
          std::wstring::~wstring(v405, v159);
          std::wstring::~wstring(&v326, v160);
          std::wstring::~wstring(v404, v161);
          pv = 0;
          wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%windir%\\system32\\usoclient.exe");
          v162 = SystemInterface::Providers::GetSystem(v409);
          v163 = *(_QWORD *)v162 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v162 + 8LL) + 4LL);
          v164 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v163 + 32LL))(v163, v427);
          v165 = *(_QWORD *)v164;
          v166 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(**(_QWORD **)v164 + 64LL);
          v323[0] = (__int64)pv;
          std::variant<unsigned int,unsigned __int64,std::wstring>::variant<unsigned int,unsigned __int64,std::wstring>(
            v335,
            v323);
          v167 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v430, L"cmdLine");
          v168 = Src;
          if ( v441 > 7 )
            v168 = (_QWORD *)Src[0];
          *(_QWORD *)&v389 = v168;
          *((_QWORD *)&v389 + 1) = v440;
          *(_QWORD *)&v390 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v169 = -1;
          do
            ++v169;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v169] );
          *((_QWORD *)&v390 + 1) = v169;
          v320 = *v167;
          *(_OWORD *)v323 = v389;
          *(_OWORD *)geoName = v390;
          v166(v165, geoName, v323, &v320, v335);
          if ( v336 != -1 && v336 && v336 != 1 )
            std::wstring::~wstring(v335, v170);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v427);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v409);
          v171 = SystemInterface::Providers::GetSystem(v411);
          v172 = *(_QWORD *)v171 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v171 + 8LL) + 4LL);
          v173 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v172 + 32LL))(v172, v410);
          v174 = *(_QWORD *)v173;
          v175 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, _DWORD *))(**(_QWORD **)v173 + 64LL);
          v176 = &v463;
          if ( v465 > 7 )
            v176 = (__int128 *)v463;
          v323[0] = (__int64)v176;
          std::variant<unsigned int,unsigned __int64,std::wstring>::variant<unsigned int,unsigned __int64,std::wstring>(
            v335,
            v323);
          v177 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v431, L"startArg");
          v178 = Src;
          if ( v441 > 7 )
            v178 = (_QWORD *)Src[0];
          *(_QWORD *)&v391 = v178;
          *((_QWORD *)&v391 + 1) = v440;
          *(_QWORD *)&v357 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v179 = -1;
          do
            ++v179;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v179] );
          *((_QWORD *)&v357 + 1) = v179;
          v320 = *v177;
          *(_OWORD *)v323 = v391;
          *(_OWORD *)geoName = v357;
          v175(v174, geoName, v323, &v320, v335);
          if ( v336 != -1 && v336 && v336 != 1 )
            std::wstring::~wstring(v335, v180);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v410);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v411);
          v181 = SystemInterface::Providers::GetSystem(v413);
          v182 = *(_QWORD *)v181 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v181 + 8LL) + 4LL);
          v183 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v182 + 32LL))(v182, v412);
          v184 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v432, L"oemExpeditedUpdate");
          v185 = Src;
          if ( v441 > 7 )
            v185 = (_QWORD *)Src[0];
          *(_QWORD *)&v358 = v185;
          *((_QWORD *)&v358 + 1) = v440;
          *(_QWORD *)&v359 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v186 = -1;
          do
            ++v186;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v186] );
          *((_QWORD *)&v359 + 1) = v186;
          v320 = *v184;
          *(_OWORD *)v323 = v358;
          *(_OWORD *)geoName = v359;
          SystemInterface::Registry::SetSystemBool(
            v183,
            (unsigned int)geoName,
            (unsigned int)v323,
            (unsigned int)&v320,
            1);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v412);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v413);
          v187 = SystemInterface::Providers::GetSystem(v415);
          v188 = *(_QWORD *)v187 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v187 + 8LL) + 4LL);
          v189 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v188 + 32LL))(v188, v414);
          v190 = *(_QWORD *)v189;
          v191 = *(void (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *, __int128 *))(**(_QWORD **)v189 + 64LL);
          v192 = web::json::value::serialize(&v442, v335);
          v354 = 0;
          v355 = 0u;
          v354 = *(_OWORD *)v192;
          v355 = *(_OWORD *)(v192 + 16);
          *(_QWORD *)(v192 + 16) = 0;
          *(_QWORD *)(v192 + 24) = 7;
          *(_WORD *)v192 = 0;
          v356 = 2;
          v193 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                               v433,
                               L"updaterClientMetadata");
          v194 = Src;
          if ( v441 > 7 )
            v194 = (_QWORD *)Src[0];
          *(_QWORD *)&v360 = v194;
          *((_QWORD *)&v360 + 1) = v440;
          *(_QWORD *)&v363 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v195 = -1;
          do
            ++v195;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v195] );
          *((_QWORD *)&v363 + 1) = v195;
          v320 = *v193;
          *(_OWORD *)v323 = v360;
          *(_OWORD *)geoName = v363;
          v191(v190, geoName, v323, &v320, &v354);
          if ( v356 != -1 && v356 && v356 != 1 )
            std::wstring::~wstring(&v354, v196);
          std::wstring::~wstring(v335, v196);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v414);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v415);
          if ( pv )
            CoTaskMemFree(pv);
          std::wstring::~wstring(&v463, v197);
          if ( v446 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v446 + 192LL))(v446, 1);
          if ( (_QWORD)v442 )
            (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v442 + 192LL))(v442, 1);
        }
        std::wstring::~wstring(v468, v57);
      }
      else
      {
        v210 = SystemInterface::Providers::GetSystem(v368);
        v211 = *(_QWORD *)v210 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v210 + 8LL) + 4LL);
        v212 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v211 + 32LL))(v211, v371);
        v6 |= 0xC0000u;
        v319 = v6;
        v213 = *(_QWORD *)v212;
        v214 = *(__int64 (__fastcall **)(__int64, WCHAR *, __int64 *, __int128 *))(**(_QWORD **)v212 + 32LL);
        v215 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v420, L"expeditedPayload");
        v216 = Src;
        if ( v441 > 7 )
          v216 = (_QWORD *)Src[0];
        *(_QWORD *)&v367 = v216;
        *((_QWORD *)&v367 + 1) = v440;
        *(_QWORD *)&v366 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v217 = -1;
        do
          ++v217;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v217] );
        *((_QWORD *)&v366 + 1) = v217;
        v320 = *v215;
        *(_OWORD *)v323 = v367;
        *(_OWORD *)geoName = v366;
        v218 = v214(v213, geoName, v323, &v320);
        v219 = 1;
        if ( v218 )
          goto LABEL_229;
      }
      v219 = 0;
LABEL_229:
      if ( (v6 & 0x80000) != 0 )
      {
        v6 &= ~0x80000u;
        v319 = v6;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v371);
      }
      if ( (v6 & 0x40000) != 0 )
      {
        v6 &= ~0x40000u;
        v319 = v6;
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v368);
      }
      if ( v219 )
      {
        v220 = SystemInterface::Providers::GetSystem(&v329);
        v221 = *(_QWORD *)v220 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v220 + 8LL) + 4LL);
        v222 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v221 + 32LL))(v221, &v340);
        v223 = *(_QWORD *)v222;
        v224 = *(void (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v222 + 72LL);
        v225 = Src;
        if ( v441 > 7 )
          v225 = (_QWORD *)Src[0];
        *(_QWORD *)&v345 = v225;
        *((_QWORD *)&v345 + 1) = v440;
        *(_QWORD *)&v334 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
        v226 = -1;
        do
          ++v226;
        while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v226] );
        *((_QWORD *)&v334 + 1) = v226;
        v320 = v345;
        *(_OWORD *)v323 = v334;
        v224(v223, v323, &v320);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v340);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v329);
      }
      if ( (_BYTE)v460 && (char)v459 != -1 && (_BYTE)v459 && (char)v459 != 1 )
        std::wstring::~wstring(v458, v198);
      std::wstring::~wstring(v455, v198);
      v17 = v333;
LABEL_245:
      std::wstring::~wstring(Src, v26);
      v16 = v350;
LABEL_246:
      v17 += 4;
    }
  }
  v466 = 0;
  v467 = 0;
  v237 = *(void (__fastcall **)(_QWORD, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v453 + 88LL);
  v238 = -1;
  do
    ++v238;
  while ( SystemInterface::Registry::USO_USCHEDULER_ROOT[v238] );
  *(_QWORD *)&v334 = SystemInterface::Registry::USO_USCHEDULER_ROOT;
  *((_QWORD *)&v334 + 1) = v238;
  *(_QWORD *)&v345 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v239 = -1;
  do
    ++v239;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v239] );
  *((_QWORD *)&v345 + 1) = v239;
  v329 = v334;
  v340 = v345;
  v237(v453, &v466, &v340, &v329);
  *(_QWORD *)&v353 = *((_QWORD *)&v466 + 1);
  v241 = (_QWORD *)v466;
  if ( (_QWORD)v466 != *((_QWORD *)&v466 + 1) )
  {
    while ( 1 )
    {
      v242 = v241[2];
      v243 = v241;
      if ( v241[3] > 7u )
        v243 = (_QWORD *)*v241;
      *(_QWORD *)&v334 = v243;
      *((_QWORD *)&v334 + 1) = v242;
      v329 = v334;
      Windows::UO::LegacyUOUpdate::CreateUpdate(&v450, &v329, *((_QWORD *)v5 + 4));
      v244 = v452;
      if ( v452 )
      {
        v343 = 0;
        v245 = v451;
        if ( v451 )
        {
          _InterlockedIncrement(v451 + 2);
          v245 = v451;
        }
        v246 = v450;
        *(_QWORD *)&v343 = v450;
        *((_QWORD *)&v343 + 1) = v245;
        v247 = (_QWORD *)((char *)v450 + 288);
        v248 = *((_QWORD *)v450 + 38);
        if ( *((_QWORD *)v450 + 39) > 7u )
          v247 = (_QWORD *)*v247;
        *(_QWORD *)&v345 = v247;
        *((_QWORD *)&v345 + 1) = v248;
        v329 = v345;
        if ( *(_BYTE *)(Windows::UO::UpdaterSettings::GetUpdaterSettings(&v329) + 84) )
        {
          v249 = (_QWORD *)(*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, _DWORD *))(*(_QWORD *)v246 + 24LL))(
                             v246,
                             v335);
          if ( v249[3] > 7u )
            v249 = (_QWORD *)*v249;
          v323[0] = (__int64)v249;
          *(_QWORD *)&v366 = L"Legacy UO Updater: {} ignored because it is disabled";
          *((_QWORD *)&v366 + 1) = 52;
          v329 = v366;
          SystemInterface::Log<wchar_t const *>(&v329, v323);
          std::wstring::~wstring(v335, v250);
          if ( v245 )
          {
            if ( _InterlockedExchangeAdd(v245 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v245)(v245);
              if ( _InterlockedExchangeAdd(v245 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v245 + 8LL))(v245);
            }
          }
          v251 = v452 == 0;
          goto LABEL_334;
        }
        if ( *((_BYTE *)v246 + 536) )
        {
          v252 = (_QWORD *)(*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, _DWORD *))(*(_QWORD *)v246 + 24LL))(
                             v246,
                             v335);
          if ( v252[3] > 7u )
            v252 = (_QWORD *)*v252;
          v323[0] = (__int64)v252;
          *(_QWORD *)&v367 = L"Legacy UO Updater: {} ignored because it was completed";
          *((_QWORD *)&v367 + 1) = 54;
          v329 = v367;
          SystemInterface::Log<wchar_t const *>(&v329, v323);
          goto LABEL_282;
        }
        v255 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                            L"IA",
                            word_14047EAEA,
                            0);
        if ( v255 == word_14047EAEA || (v258 = ((__int64)v255 - v257) >> 1, v258 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v256);
        *(_QWORD *)&v364 = v257;
        *((_QWORD *)&v364 + 1) = v258;
        std::wstring::wstring(&v326, (char *)v246 + 288);
        v6 |= 0x1100000u;
        v259 = &v326;
        if ( v328 > 7 )
          v259 = (__int128 *)v326;
        *(_QWORD *)&v362 = v259;
        *((_QWORD *)&v362 + 1) = v327;
        v329 = v364;
        v340 = v362;
        if ( !(unsigned __int8)Strings::iequals(&v340, &v329)
          || (unsigned __int8)UpdateMetadata::IsOobeExpedited(v246)
          || (v262 = 1, !Windows::UO::LegacyUOProvider::IsStoreProviderEnabled(v261)) )
        {
          v262 = 0;
        }
        if ( (v6 & 0x100000) != 0 )
        {
          v6 &= ~0x100000u;
          std::wstring::~wstring(&v326, v260);
        }
        if ( v262 )
        {
          v263 = SystemInterface::Providers::GetSystem(v371);
          v264 = *(_QWORD *)v263 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v263 + 8LL) + 4LL);
          v265 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v264 + 104LL))(v264, v368);
          v266 = *(_QWORD *)v265;
          v267 = *(void (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)v265 + 200LL);
          v268 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                              v420,
                              L"StoreProvider active during scan");
          std::wstring::wstring(&v326, (char *)v246 + 288);
          v6 |= 0x2000000u;
          v269 = &v326;
          if ( v328 > 7 )
            v269 = (__int128 *)v326;
          *(_QWORD *)&v361 = v269;
          *((_QWORD *)&v361 + 1) = v327;
          v329 = v268;
          v340 = v361;
          v267(v266, &v340, &v329);
          std::wstring::~wstring(&v326, v270);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v368);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v371);
          Windows::UO::LegacyUOUpdate::RemoveUpdate(v246);
          goto LABEL_284;
        }
        if ( (unsigned __int8)UpdateMetadata::IsOobeExpedited(v246) )
        {
          *(_QWORD *)&v363 = L"{}\\{}";
          *((_QWORD *)&v363 + 1) = 5;
          v329 = v363;
          std::format<wchar_t const * const &,std::wstring const &>(v455);
          v271 = SystemInterface::Providers::GetSystem(v373);
          v272 = *(_QWORD *)v271 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v271 + 8LL) + 4LL);
          v273 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v272 + 32LL))(v272, v378);
          v274 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v421, L"oemExpeditedUpdate");
          v275 = v455;
          if ( v457 > 7 )
            v275 = (_QWORD *)v455[0];
          *(_QWORD *)&v360 = v275;
          *((_QWORD *)&v360 + 1) = v456;
          *(_QWORD *)&v359 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
          v276 = -1;
          do
            ++v276;
          while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v276] );
          *((_QWORD *)&v359 + 1) = v276;
          v329 = *v274;
          v340 = v360;
          v370 = v359;
          SystemBoolOrDefault = SystemInterface::Registry::GetSystemBoolOrDefault(
                                  v273,
                                  (unsigned int)&v370,
                                  (unsigned int)&v340,
                                  (unsigned int)&v329,
                                  0);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v378);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v373);
          if ( (unsigned __int8)std::ranges::_None_of_fn::operator()_std::vector_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t________const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_56_::_lambda_3___(
                                  &v470,
                                  v241)
            && !SystemBoolOrDefault )
          {
            v278 = v241[2];
            v279 = v241;
            if ( v241[3] > 7u )
              v279 = (_QWORD *)*v241;
            *(_QWORD *)&v358 = v279;
            *((_QWORD *)&v358 + 1) = v278;
            v329 = v358;
            Windows::UO::LogLegacyOobeUpdateIgnoredNotAllowed(&v329);
            goto LABEL_309;
          }
          if ( v473
            && (unsigned __int8)std::ranges::_Any_of_fn::operator()_std::vector_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t________const___std::identity__Windows::UO::LegacyUOProvider::Scan_::_59_::_lambda_4___(
                                  v472,
                                  v241) )
          {
            v329 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v423, v241, v280, v281);
            Windows::UO::LogLegacyOobeUpdateIgnoredBlocked(&v329);
            goto LABEL_309;
          }
          v282 = (int)UpdateMetadata::AllowedFailureCount_0(v246);
          v283 = (__int64 *)UpdateDatabase::ActionRecords(*((_QWORD *)v331 + 4), &v461, v246);
          v284 = v283[1];
          v285 = 0;
          for ( i = *v283; i != v284; i += 112 )
          {
            v287 = v285++;
            if ( *(int *)(i + 108) >= 0 )
              v285 = v287;
          }
          std::vector<SystemInterface::ActionRecord>::~vector<SystemInterface::ActionRecord>(&v461);
          if ( v285 >= v282 )
          {
            v289 = v241[2];
            v290 = v241;
            if ( v241[3] > 7u )
              v290 = (_QWORD *)*v241;
            *(_QWORD *)&v357 = v290;
            *((_QWORD *)&v357 + 1) = v289;
            v329 = v357;
            Windows::UO::LogLegacyUOUpdaterIgnoredOobeExpeditedUpdate(&v329);
            Windows::UO::LegacyUOUpdate::RemoveUpdate(v246);
LABEL_309:
            v254 = v455;
LABEL_283:
            std::wstring::~wstring(v254, v253);
LABEL_284:
            std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v343);
            ActionState::~ActionState((ActionState *)&v450);
            goto LABEL_339;
          }
          std::wstring::~wstring(v455, v288);
          v5 = v331;
        }
        v344 = 0;
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>>,0>>::find(
          (char *)v5 + 40,
          &v344,
          v241);
        v292 = v344;
        if ( v344 == *((_DWORD **)v5 + 5)
          || (v293 = (*(__int64 (__fastcall **)(Windows::UO::LegacyUOUpdate *, __int128 *))(*(_QWORD *)v246 + 24LL))(
                       v246,
                       &v354),
              v294 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)v292 + 8) + 24LL))(
                       *((_QWORD *)v292 + 8),
                       v335),
              v6 |= 0x600000u,
              v295 = std::wstring::compare(v293, v294),
              v296 = 1,
              v295) )
        {
          v296 = 0;
        }
        if ( (v6 & 0x400000) != 0 )
        {
          v6 &= ~0x400000u;
          std::wstring::~wstring(v335, v291);
        }
        if ( (v6 & 0x200000) != 0 )
        {
          v6 &= ~0x200000u;
          std::wstring::~wstring(&v354, v291);
        }
        std::wstring::wstring(v335, (char *)v246 + 288);
        if ( v296 )
        {
          v6 |= 0x40000000u;
          v297 = std::map<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>>::operator[](Block, v335);
          std::shared_ptr<Update>::operator=(v297, v292 + 16);
LABEL_282:
          v254 = v335;
          goto LABEL_283;
        }
        v6 |= 0x80000000;
        v298 = std::map<std::wstring,std::shared_ptr<Windows::UO::LegacyUOUpdate>>::operator[](Block, v335);
        std::shared_ptr<Update>::operator=(v298, &v450);
        std::wstring::~wstring(v335, v299);
        std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v343);
        v244 = v452;
      }
      v251 = v244 == 0;
LABEL_334:
      if ( !v251 )
      {
        v300 = v451;
        if ( v451 )
        {
          if ( _InterlockedExchangeAdd(v451 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v300)(v300);
            if ( _InterlockedExchangeAdd(v300 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v300 + 8LL))(v300);
          }
        }
      }
LABEL_339:
      v241 += 4;
      if ( v241 == (_QWORD *)v353 )
        break;
      v5 = v331;
    }
  }
  v448 = 0;
  v449 = 0;
  v301 = *(__int64 **)Block[0];
  while ( !*((_BYTE *)v301 + 25) )
  {
    std::wstring::wstring(v458, v301 + 4);
    v302 = v301[9];
    if ( v302 )
      _InterlockedIncrement((volatile signed __int32 *)(v302 + 8));
    v303 = v301[8];
    v459 = v303;
    v304 = (volatile signed __int32 *)v301[9];
    v460 = v304;
    if ( v304 )
      _InterlockedIncrement(v304 + 2);
    v323[0] = v303;
    v323[1] = (__int64)v304;
    v305 = *((_QWORD *)&v448 + 1);
    if ( *((_QWORD *)&v448 + 1) == v449 )
    {
      std::vector<std::shared_ptr<Update>>::_Emplace_reallocate<std::shared_ptr<Windows::WU::CurrentVersionUpdate>>(
        &v448,
        *((_QWORD *)&v448 + 1),
        v323);
    }
    else
    {
      **((_QWORD **)&v448 + 1) = v303;
      *(_QWORD *)(v305 + 8) = v304;
      *(_OWORD *)v323 = 0;
      *((_QWORD *)&v448 + 1) += 16LL;
    }
    v306 = (volatile signed __int32 *)v323[1];
    if ( v323[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v323[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v306)(v306);
        if ( _InterlockedExchangeAdd(v306 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v306 + 8LL))(v306);
      }
    }
    if ( v304 )
    {
      if ( _InterlockedExchangeAdd(v304 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v304)(v304);
        if ( _InterlockedExchangeAdd(v304 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v304 + 8LL))(v304);
      }
    }
    std::wstring::~wstring(v458, v305);
    v307 = (__int64 *)v301[2];
    if ( *((_BYTE *)v307 + 25) )
    {
      for ( j = (__int64 *)v301[1]; !*((_BYTE *)j + 25) && v301 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v301 = j;
      v301 = j;
    }
    else
    {
      do
      {
        v301 = v307;
        v307 = (__int64 *)*v307;
      }
      while ( !*((_BYTE *)v307 + 25) );
    }
  }
  LOBYTE(v240) = 0;
  std::ranges::_Sort_fn::_Sort_common_std::shared_ptr_Update____std::ranges::less__Windows::UO::LegacyUOProvider::Scan_::_2_::_lambda_6___(
    v448,
    DWORD2(v448),
    (__int64)(*((_QWORD *)&v448 + 1) - v448) >> 4,
    v240,
    v332);
  v309 = (char *)v331 + 40;
  if ( (void **)((char *)v331 + 40) != Block )
  {
    v310 = *(void **)v309;
    *(void **)v309 = Block[0];
    Block[0] = v310;
    v311 = (void *)*((_QWORD *)v309 + 1);
    *((void **)v309 + 1) = Block[1];
    Block[1] = v311;
  }
  Windows::UO::LogLegacyUOProviderScanResults(&v448);
  LODWORD(v326) = 0;
  v312 = v449;
  v449 = 0;
  v313 = *((_QWORD *)&v448 + 1);
  v314 = v448;
  v448 = 0u;
  v315 = v352;
  *v352 = 0;
  v328 = 0;
  v327 = 0;
  *((_QWORD *)&v326 + 1) = 0;
  *((_QWORD *)v315 + 1) = v314;
  *((_QWORD *)v315 + 2) = v313;
  *((_QWORD *)v315 + 3) = v312;
  *((_BYTE *)v315 + 32) = 1;
  std::vector<std::shared_ptr<Update>>::_Tidy((char *)&v326 + 8);
  std::vector<std::shared_ptr<Update>>::_Tidy(&v448);
  std::vector<std::filesystem::path>::_Tidy(&v466);
  v316 = (volatile signed __int32 *)*((_QWORD *)&v453 + 1);
  if ( *((_QWORD *)&v453 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v453 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v316)(v316);
      if ( _InterlockedExchangeAdd(v316 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v316 + 8LL))(v316);
    }
  }
  if ( v473 )
    std::vector<std::filesystem::path>::_Tidy(v472);
  std::vector<std::filesystem::path>::_Tidy(&v470);
  v317 = v376;
  v251 = (*(_DWORD *)(v376 + 76))-- == 1;
  if ( v251 )
  {
    *(_DWORD *)(v317 + 72) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v317 + 16));
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Windows::UO::LegacyUOUpdate>>,void *>>>(
    Block,
    Block,
    *((_QWORD *)Block[0] + 1));
  operator delete(Block[0]);
  return v315;
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
