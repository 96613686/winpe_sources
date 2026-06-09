# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__

- ea: `0x180007340`
- end: `0x18000a85f`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__`
- size: `13599`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006800`
- `0x180006cf0`
- `0x180007270`
- `0x18000a8e0`
- `0x18001b0e4`
- `0x18002c640`
- `0x18002c664`
- `0x18002cac0`
- `0x180079400`

## string_xrefs

- `0x18000859f`: `MaintenanceTaskComplete`
- `0x180007806`: `EkCertRescheduleTaskFailureStep`
- `0x18000738c`: `ActiveDirectoryBackupSrkPub`
- `0x180009b37`: `TaskReadyForAttestation`
- `0x1800080f1`: `FasrCustomBootPathReasons`
- `0x180009bbe`: `TaskReadyForStorage`
- `0x180007717`: `EkCertPath`
- `0x18000a060`: `WindowsAikCheckCreateResult`
- `0x180009919`: `TaskFirmwareVersion`
- `0x180009a29`: `TaskManufacturerId`
- `0x18000798c`: `EkCertsInstalledFromNV`
- `0x180008067`: `FasrCustomBootPath`
- `0x180008a5b`: `IntermediateCertsInstalledFromNV`
- `0x180007a0f`: `EkCreatePersistResult`
- `0x1800099a0`: `TaskInformationFlags`
- `0x180009ee3`: `WBCLPath`
- `0x180009ab0`: `TaskOsBuildNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=278
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__()
{
  __int64 v0; // rcx
  __int64 v2[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v3; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v4; // [rsp+40h] [rbp-C0h]
  __int64 v5; // [rsp+48h] [rbp-B8h]
  __int128 v6; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v7; // [rsp+60h] [rbp-A0h]
  __int64 v8; // [rsp+68h] [rbp-98h]
  __int128 v9; // [rsp+70h] [rbp-90h] BYREF
  __int64 v10; // [rsp+80h] [rbp-80h]
  __int64 v11; // [rsp+88h] [rbp-78h]
  __int128 v12; // [rsp+90h] [rbp-70h] BYREF
  __int64 v13; // [rsp+A0h] [rbp-60h]
  __int64 v14; // [rsp+A8h] [rbp-58h]
  __int128 v15; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v16; // [rsp+C0h] [rbp-40h]
  __int64 v17; // [rsp+C8h] [rbp-38h]
  __int128 v18; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-20h]
  __int64 v20; // [rsp+E8h] [rbp-18h]
  __int128 v21; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int128 v24; // [rsp+110h] [rbp+10h] BYREF
  __int64 v25; // [rsp+120h] [rbp+20h]
  __int64 v26; // [rsp+128h] [rbp+28h]
  __int128 v27; // [rsp+130h] [rbp+30h] BYREF
  __int64 v28; // [rsp+140h] [rbp+40h]
  __int64 v29; // [rsp+148h] [rbp+48h]
  __int128 v30; // [rsp+150h] [rbp+50h] BYREF
  __int64 v31; // [rsp+160h] [rbp+60h]
  __int64 v32; // [rsp+168h] [rbp+68h]
  __int128 v33; // [rsp+170h] [rbp+70h] BYREF
  __int64 v34; // [rsp+180h] [rbp+80h]
  __int64 v35; // [rsp+188h] [rbp+88h]
  __int128 v36; // [rsp+190h] [rbp+90h] BYREF
  __int64 v37; // [rsp+1A0h] [rbp+A0h]
  __int64 v38; // [rsp+1A8h] [rbp+A8h]
  __int128 v39; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v40; // [rsp+1C0h] [rbp+C0h]
  __int64 v41; // [rsp+1C8h] [rbp+C8h]
  __int128 v42; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v43; // [rsp+1E0h] [rbp+E0h]
  __int64 v44; // [rsp+1E8h] [rbp+E8h]
  __int128 v45; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v46; // [rsp+200h] [rbp+100h]
  __int64 v47; // [rsp+208h] [rbp+108h]
  __int128 v48; // [rsp+210h] [rbp+110h] BYREF
  __int64 v49; // [rsp+220h] [rbp+120h]
  __int64 v50; // [rsp+228h] [rbp+128h]
  __int128 v51; // [rsp+230h] [rbp+130h] BYREF
  __int64 v52; // [rsp+240h] [rbp+140h]
  __int64 v53; // [rsp+248h] [rbp+148h]
  __int128 v54; // [rsp+250h] [rbp+150h] BYREF
  __int64 v55; // [rsp+260h] [rbp+160h]
  __int64 v56; // [rsp+268h] [rbp+168h]
  __int128 v57; // [rsp+270h] [rbp+170h] BYREF
  __int64 v58; // [rsp+280h] [rbp+180h]
  __int64 v59; // [rsp+288h] [rbp+188h]
  __int128 v60; // [rsp+290h] [rbp+190h] BYREF
  __int64 v61; // [rsp+2A0h] [rbp+1A0h]
  __int64 v62; // [rsp+2A8h] [rbp+1A8h]
  __int128 v63; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v64; // [rsp+2C0h] [rbp+1C0h]
  __int64 v65; // [rsp+2C8h] [rbp+1C8h]
  __int128 v66; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v67; // [rsp+2E0h] [rbp+1E0h]
  __int64 v68; // [rsp+2E8h] [rbp+1E8h]
  __int128 v69; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v70; // [rsp+300h] [rbp+200h]
  __int64 v71; // [rsp+308h] [rbp+208h]
  __int128 v72; // [rsp+310h] [rbp+210h] BYREF
  __int64 v73; // [rsp+320h] [rbp+220h]
  __int64 v74; // [rsp+328h] [rbp+228h]
  __int128 v75; // [rsp+330h] [rbp+230h] BYREF
  __int64 v76; // [rsp+340h] [rbp+240h]
  __int64 v77; // [rsp+348h] [rbp+248h]
  __int128 v78; // [rsp+350h] [rbp+250h] BYREF
  __int64 v79; // [rsp+360h] [rbp+260h]
  __int64 v80; // [rsp+368h] [rbp+268h]
  __int128 v81; // [rsp+370h] [rbp+270h] BYREF
  __int64 v82; // [rsp+380h] [rbp+280h]
  __int64 v83; // [rsp+388h] [rbp+288h]
  __int128 v84; // [rsp+390h] [rbp+290h] BYREF
  __int64 v85; // [rsp+3A0h] [rbp+2A0h]
  __int64 v86; // [rsp+3A8h] [rbp+2A8h]
  __int128 v87; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v88; // [rsp+3C0h] [rbp+2C0h]
  __int64 v89; // [rsp+3C8h] [rbp+2C8h]
  __int128 v90; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v91; // [rsp+3E0h] [rbp+2E0h]
  __int64 v92; // [rsp+3E8h] [rbp+2E8h]
  __int128 v93; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v94; // [rsp+400h] [rbp+300h]
  __int64 v95; // [rsp+408h] [rbp+308h]
  __int128 v96; // [rsp+410h] [rbp+310h] BYREF
  __int64 v97; // [rsp+420h] [rbp+320h]
  __int64 v98; // [rsp+428h] [rbp+328h]
  __int128 v99; // [rsp+430h] [rbp+330h] BYREF
  __int64 v100; // [rsp+440h] [rbp+340h]
  __int64 v101; // [rsp+448h] [rbp+348h]
  __int128 v102; // [rsp+450h] [rbp+350h] BYREF
  __int64 v103; // [rsp+460h] [rbp+360h]
  __int64 v104; // [rsp+468h] [rbp+368h]
  __int128 v105; // [rsp+470h] [rbp+370h] BYREF
  __int64 v106; // [rsp+480h] [rbp+380h]
  __int64 v107; // [rsp+488h] [rbp+388h]
  __int128 v108; // [rsp+490h] [rbp+390h] BYREF
  __int64 v109; // [rsp+4A0h] [rbp+3A0h]
  __int64 v110; // [rsp+4A8h] [rbp+3A8h]
  __int128 v111; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v112; // [rsp+4C0h] [rbp+3C0h]
  __int64 v113; // [rsp+4C8h] [rbp+3C8h]
  __int128 v114; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v115; // [rsp+4E0h] [rbp+3E0h]
  __int64 v116; // [rsp+4E8h] [rbp+3E8h]
  __int128 v117; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v118; // [rsp+500h] [rbp+400h]
  __int64 v119; // [rsp+508h] [rbp+408h]
  __int128 v120; // [rsp+510h] [rbp+410h] BYREF
  __int64 v121; // [rsp+520h] [rbp+420h]
  __int64 v122; // [rsp+528h] [rbp+428h]
  __int128 v123; // [rsp+530h] [rbp+430h] BYREF
  __int64 v124; // [rsp+540h] [rbp+440h]
  __int64 v125; // [rsp+548h] [rbp+448h]
  __int128 v126; // [rsp+550h] [rbp+450h] BYREF
  __int64 v127; // [rsp+560h] [rbp+460h]
  __int64 v128; // [rsp+568h] [rbp+468h]
  __int128 v129; // [rsp+570h] [rbp+470h] BYREF
  __int64 v130; // [rsp+580h] [rbp+480h]
  __int64 v131; // [rsp+588h] [rbp+488h]
  __int128 v132; // [rsp+590h] [rbp+490h] BYREF
  __int64 v133; // [rsp+5A0h] [rbp+4A0h]
  __int64 v134; // [rsp+5A8h] [rbp+4A8h]
  __int128 v135; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v136; // [rsp+5C0h] [rbp+4C0h]
  __int64 v137; // [rsp+5C8h] [rbp+4C8h]
  __int128 v138; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v139; // [rsp+5E0h] [rbp+4E0h]
  __int64 v140; // [rsp+5E8h] [rbp+4E8h]
  __int128 v141; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v142; // [rsp+600h] [rbp+500h]
  __int64 v143; // [rsp+608h] [rbp+508h]
  __int128 v144; // [rsp+610h] [rbp+510h] BYREF
  __int64 v145; // [rsp+620h] [rbp+520h]
  __int64 v146; // [rsp+628h] [rbp+528h]
  __int128 v147; // [rsp+630h] [rbp+530h] BYREF
  __int64 v148; // [rsp+640h] [rbp+540h]
  __int64 v149; // [rsp+648h] [rbp+548h]
  __int128 v150; // [rsp+650h] [rbp+550h] BYREF
  __int64 v151; // [rsp+660h] [rbp+560h]
  __int64 v152; // [rsp+668h] [rbp+568h]
  __int128 v153; // [rsp+670h] [rbp+570h] BYREF
  __int64 v154; // [rsp+680h] [rbp+580h]
  __int64 v155; // [rsp+688h] [rbp+588h]
  __int128 v156; // [rsp+690h] [rbp+590h] BYREF
  __int64 v157; // [rsp+6A0h] [rbp+5A0h]
  __int64 v158; // [rsp+6A8h] [rbp+5A8h]
  __int128 v159; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v160; // [rsp+6C0h] [rbp+5C0h]
  __int64 v161; // [rsp+6C8h] [rbp+5C8h]
  __int128 v162; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v163; // [rsp+6E0h] [rbp+5E0h]
  __int64 v164; // [rsp+6E8h] [rbp+5E8h]
  __int128 v165; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v166; // [rsp+700h] [rbp+600h]
  __int64 v167; // [rsp+708h] [rbp+608h]
  __int128 v168; // [rsp+710h] [rbp+610h] BYREF
  __int64 v169; // [rsp+720h] [rbp+620h]
  __int64 v170; // [rsp+728h] [rbp+628h]
  __int128 v171; // [rsp+730h] [rbp+630h] BYREF
  __int64 v172; // [rsp+740h] [rbp+640h]
  __int64 v173; // [rsp+748h] [rbp+648h]
  __int128 v174; // [rsp+750h] [rbp+650h] BYREF
  __int64 v175; // [rsp+760h] [rbp+660h]
  __int64 v176; // [rsp+768h] [rbp+668h]
  __int128 v177; // [rsp+770h] [rbp+670h] BYREF
  __int64 v178; // [rsp+780h] [rbp+680h]
  __int64 v179; // [rsp+788h] [rbp+688h]
  __int128 v180; // [rsp+790h] [rbp+690h] BYREF
  __int64 v181; // [rsp+7A0h] [rbp+6A0h]
  __int64 v182; // [rsp+7A8h] [rbp+6A8h]
  __int128 v183; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int64 v184; // [rsp+7C0h] [rbp+6C0h]
  __int64 v185; // [rsp+7C8h] [rbp+6C8h]
  __int128 v186; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v187; // [rsp+7E0h] [rbp+6E0h]
  __int64 v188; // [rsp+7E8h] [rbp+6E8h]
  __int128 v189; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v190; // [rsp+800h] [rbp+700h]
  __int64 v191; // [rsp+808h] [rbp+708h]
  __int128 v192; // [rsp+810h] [rbp+710h] BYREF
  __int64 v193; // [rsp+820h] [rbp+720h]
  __int64 v194; // [rsp+828h] [rbp+728h]
  __int128 v195; // [rsp+830h] [rbp+730h] BYREF
  __int64 v196; // [rsp+840h] [rbp+740h]
  __int64 v197; // [rsp+848h] [rbp+748h]
  __int128 v198; // [rsp+850h] [rbp+750h] BYREF
  __int64 v199; // [rsp+860h] [rbp+760h]
  __int64 v200; // [rsp+868h] [rbp+768h]
  __int128 v201; // [rsp+870h] [rbp+770h] BYREF
  __int64 v202; // [rsp+880h] [rbp+780h]
  __int64 v203; // [rsp+888h] [rbp+788h]
  __int128 v204; // [rsp+890h] [rbp+790h] BYREF
  __int64 v205; // [rsp+8A0h] [rbp+7A0h]
  __int64 v206; // [rsp+8A8h] [rbp+7A8h]
  __int128 v207; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v208; // [rsp+8C0h] [rbp+7C0h]
  __int64 v209; // [rsp+8C8h] [rbp+7C8h]
  __int128 v210; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v211; // [rsp+8E0h] [rbp+7E0h]
  __int64 v212; // [rsp+8E8h] [rbp+7E8h]
  __int128 v213; // [rsp+8F0h] [rbp+7F0h] BYREF
  __int64 v214; // [rsp+900h] [rbp+800h]
  __int64 v215; // [rsp+908h] [rbp+808h]
  __int128 v216; // [rsp+910h] [rbp+810h] BYREF
  __int64 v217; // [rsp+920h] [rbp+820h]
  __int64 v218; // [rsp+928h] [rbp+828h]
  __int128 v219; // [rsp+930h] [rbp+830h] BYREF
  __int64 v220; // [rsp+940h] [rbp+840h]
  __int64 v221; // [rsp+948h] [rbp+848h]
  __int128 v222; // [rsp+950h] [rbp+850h] BYREF
  __int64 v223; // [rsp+960h] [rbp+860h]
  __int64 v224; // [rsp+968h] [rbp+868h]
  __int128 v225; // [rsp+970h] [rbp+870h] BYREF
  __int64 v226; // [rsp+980h] [rbp+880h]
  __int64 v227; // [rsp+988h] [rbp+888h]
  __int128 v228; // [rsp+990h] [rbp+890h] BYREF
  __int64 v229; // [rsp+9A0h] [rbp+8A0h]
  __int64 v230; // [rsp+9A8h] [rbp+8A8h]
  __int128 v231; // [rsp+9B0h] [rbp+8B0h] BYREF
  __int64 v232; // [rsp+9C0h] [rbp+8C0h]
  __int64 v233; // [rsp+9C8h] [rbp+8C8h]
  __int128 v234; // [rsp+9D0h] [rbp+8D0h] BYREF
  __int64 v235; // [rsp+9E0h] [rbp+8E0h]
  __int64 v236; // [rsp+9E8h] [rbp+8E8h]
  __int128 v237; // [rsp+9F0h] [rbp+8F0h] BYREF
  __int64 v238; // [rsp+A00h] [rbp+900h]
  __int64 v239; // [rsp+A08h] [rbp+908h]
  __int128 v240; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v241; // [rsp+A20h] [rbp+920h]
  __int64 v242; // [rsp+A28h] [rbp+928h]
  __int128 v243; // [rsp+A30h] [rbp+930h] BYREF
  __int64 v244; // [rsp+A40h] [rbp+940h]
  __int64 v245; // [rsp+A48h] [rbp+948h]
  __int128 v246; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v247; // [rsp+A60h] [rbp+960h]
  __int64 v248; // [rsp+A68h] [rbp+968h]
  __int128 v249; // [rsp+A70h] [rbp+970h] BYREF
  __int64 v250; // [rsp+A80h] [rbp+980h]
  __int64 v251; // [rsp+A88h] [rbp+988h]
  __int128 v252; // [rsp+A90h] [rbp+990h] BYREF
  __int64 v253; // [rsp+AA0h] [rbp+9A0h]
  __int64 v254; // [rsp+AA8h] [rbp+9A8h]
  __int128 v255; // [rsp+AB0h] [rbp+9B0h] BYREF
  __int64 v256; // [rsp+AC0h] [rbp+9C0h]
  __int64 v257; // [rsp+AC8h] [rbp+9C8h]
  __int128 v258; // [rsp+AD0h] [rbp+9D0h] BYREF
  __int64 v259; // [rsp+AE0h] [rbp+9E0h]
  __int64 v260; // [rsp+AE8h] [rbp+9E8h]
  __int128 v261; // [rsp+AF0h] [rbp+9F0h] BYREF
  __int64 v262; // [rsp+B00h] [rbp+A00h]
  __int64 v263; // [rsp+B08h] [rbp+A08h]
  __int128 v264; // [rsp+B10h] [rbp+A10h] BYREF
  __int64 v265; // [rsp+B20h] [rbp+A20h]
  __int64 v266; // [rsp+B28h] [rbp+A28h]
  __int128 v267; // [rsp+B30h] [rbp+A30h] BYREF
  __int64 v268; // [rsp+B40h] [rbp+A40h]
  __int64 v269; // [rsp+B48h] [rbp+A48h]
  __int128 v270; // [rsp+B50h] [rbp+A50h] BYREF
  __int64 v271; // [rsp+B60h] [rbp+A60h]
  __int64 v272; // [rsp+B68h] [rbp+A68h]
  __int128 v273; // [rsp+B70h] [rbp+A70h] BYREF
  __int64 v274; // [rsp+B80h] [rbp+A80h]
  __int64 v275; // [rsp+B88h] [rbp+A88h]
  __int128 v276; // [rsp+B90h] [rbp+A90h] BYREF
  __int64 v277; // [rsp+BA0h] [rbp+AA0h]
  __int64 v278; // [rsp+BA8h] [rbp+AA8h]
  __int128 v279; // [rsp+BB0h] [rbp+AB0h] BYREF
  __int64 v280; // [rsp+BC0h] [rbp+AC0h]
  __int64 v281; // [rsp+BC8h] [rbp+AC8h]
  int v282; // [rsp+BD0h] [rbp+AD0h] BYREF
  _BYTE v283[32]; // [rsp+BD8h] [rbp+AD8h] BYREF
  int v284; // [rsp+BF8h] [rbp+AF8h]
  int v285; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v286[32]; // [rsp+C08h] [rbp+B08h] BYREF
  int v287; // [rsp+C28h] [rbp+B28h]
  int v288; // [rsp+C30h] [rbp+B30h] BYREF
  _BYTE v289[32]; // [rsp+C38h] [rbp+B38h] BYREF
  int v290; // [rsp+C58h] [rbp+B58h]
  int v291; // [rsp+C60h] [rbp+B60h] BYREF
  _BYTE v292[32]; // [rsp+C68h] [rbp+B68h] BYREF
  int v293; // [rsp+C88h] [rbp+B88h]
  int v294; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v295[32]; // [rsp+C98h] [rbp+B98h] BYREF
  int v296; // [rsp+CB8h] [rbp+BB8h]
  int v297; // [rsp+CC0h] [rbp+BC0h] BYREF
  _BYTE v298[32]; // [rsp+CC8h] [rbp+BC8h] BYREF
  int v299; // [rsp+CE8h] [rbp+BE8h]
  int v300; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v301[32]; // [rsp+CF8h] [rbp+BF8h] BYREF
  int v302; // [rsp+D18h] [rbp+C18h]
  int v303; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v304[32]; // [rsp+D28h] [rbp+C28h] BYREF
  int v305; // [rsp+D48h] [rbp+C48h]
  int v306; // [rsp+D50h] [rbp+C50h] BYREF
  _BYTE v307[32]; // [rsp+D58h] [rbp+C58h] BYREF
  int v308; // [rsp+D78h] [rbp+C78h]
  int v309; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v310[32]; // [rsp+D88h] [rbp+C88h] BYREF
  int v311; // [rsp+DA8h] [rbp+CA8h]
  int v312; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v313[32]; // [rsp+DB8h] [rbp+CB8h] BYREF
  int v314; // [rsp+DD8h] [rbp+CD8h]
  int v315; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v316[32]; // [rsp+DE8h] [rbp+CE8h] BYREF
  int v317; // [rsp+E08h] [rbp+D08h]
  int v318; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE v319[32]; // [rsp+E18h] [rbp+D18h] BYREF
  int v320; // [rsp+E38h] [rbp+D38h]
  int v321; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v322[32]; // [rsp+E48h] [rbp+D48h] BYREF
  int v323; // [rsp+E68h] [rbp+D68h]
  int v324; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v325[32]; // [rsp+E78h] [rbp+D78h] BYREF
  int v326; // [rsp+E98h] [rbp+D98h]
  int v327; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v328[32]; // [rsp+EA8h] [rbp+DA8h] BYREF
  int v329; // [rsp+EC8h] [rbp+DC8h]
  int v330; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v331[32]; // [rsp+ED8h] [rbp+DD8h] BYREF
  int v332; // [rsp+EF8h] [rbp+DF8h]
  int v333; // [rsp+F00h] [rbp+E00h] BYREF
  _BYTE v334[32]; // [rsp+F08h] [rbp+E08h] BYREF
  int v335; // [rsp+F28h] [rbp+E28h]
  int v336; // [rsp+F30h] [rbp+E30h] BYREF
  _BYTE v337[32]; // [rsp+F38h] [rbp+E38h] BYREF
  int v338; // [rsp+F58h] [rbp+E58h]
  int v339; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v340[32]; // [rsp+F68h] [rbp+E68h] BYREF
  int v341; // [rsp+F88h] [rbp+E88h]
  int v342; // [rsp+F90h] [rbp+E90h] BYREF
  _BYTE v343[32]; // [rsp+F98h] [rbp+E98h] BYREF
  int v344; // [rsp+FB8h] [rbp+EB8h]
  int v345; // [rsp+FC0h] [rbp+EC0h] BYREF
  _BYTE v346[32]; // [rsp+FC8h] [rbp+EC8h] BYREF
  int v347; // [rsp+FE8h] [rbp+EE8h]
  int v348; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v349[32]; // [rsp+FF8h] [rbp+EF8h] BYREF
  int v350; // [rsp+1018h] [rbp+F18h]
  int v351; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v352[32]; // [rsp+1028h] [rbp+F28h] BYREF
  int v353; // [rsp+1048h] [rbp+F48h]
  int v354; // [rsp+1050h] [rbp+F50h] BYREF
  _BYTE v355[32]; // [rsp+1058h] [rbp+F58h] BYREF
  int v356; // [rsp+1078h] [rbp+F78h]
  int v357; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v358[32]; // [rsp+1088h] [rbp+F88h] BYREF
  int v359; // [rsp+10A8h] [rbp+FA8h]
  int v360; // [rsp+10B0h] [rbp+FB0h] BYREF
  _BYTE v361[32]; // [rsp+10B8h] [rbp+FB8h] BYREF
  int v362; // [rsp+10D8h] [rbp+FD8h]
  int v363; // [rsp+10E0h] [rbp+FE0h] BYREF
  _BYTE v364[32]; // [rsp+10E8h] [rbp+FE8h] BYREF
  int v365; // [rsp+1108h] [rbp+1008h]
  int v366; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v367[32]; // [rsp+1118h] [rbp+1018h] BYREF
  int v368; // [rsp+1138h] [rbp+1038h]
  int v369; // [rsp+1140h] [rbp+1040h] BYREF
  _BYTE v370[32]; // [rsp+1148h] [rbp+1048h] BYREF
  int v371; // [rsp+1168h] [rbp+1068h]
  int v372; // [rsp+1170h] [rbp+1070h] BYREF
  _BYTE v373[32]; // [rsp+1178h] [rbp+1078h] BYREF
  int v374; // [rsp+1198h] [rbp+1098h]
  int v375; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v376[32]; // [rsp+11A8h] [rbp+10A8h] BYREF
  int v377; // [rsp+11C8h] [rbp+10C8h]
  int v378; // [rsp+11D0h] [rbp+10D0h] BYREF
  _BYTE v379[32]; // [rsp+11D8h] [rbp+10D8h] BYREF
  int v380; // [rsp+11F8h] [rbp+10F8h]
  int v381; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v382[32]; // [rsp+1208h] [rbp+1108h] BYREF
  int v383; // [rsp+1228h] [rbp+1128h]
  int v384; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v385[32]; // [rsp+1238h] [rbp+1138h] BYREF
  int v386; // [rsp+1258h] [rbp+1158h]
  int v387; // [rsp+1260h] [rbp+1160h] BYREF
  _BYTE v388[32]; // [rsp+1268h] [rbp+1168h] BYREF
  int v389; // [rsp+1288h] [rbp+1188h]
  int v390; // [rsp+1290h] [rbp+1190h] BYREF
  _BYTE v391[32]; // [rsp+1298h] [rbp+1198h] BYREF
  int v392; // [rsp+12B8h] [rbp+11B8h]
  int v393; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v394[32]; // [rsp+12C8h] [rbp+11C8h] BYREF
  int v395; // [rsp+12E8h] [rbp+11E8h]
  int v396; // [rsp+12F0h] [rbp+11F0h] BYREF
  _BYTE v397[32]; // [rsp+12F8h] [rbp+11F8h] BYREF
  int v398; // [rsp+1318h] [rbp+1218h]
  int v399; // [rsp+1320h] [rbp+1220h] BYREF
  _BYTE v400[32]; // [rsp+1328h] [rbp+1228h] BYREF
  int v401; // [rsp+1348h] [rbp+1248h]
  int v402; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v403[32]; // [rsp+1358h] [rbp+1258h] BYREF
  int v404; // [rsp+1378h] [rbp+1278h]
  int v405; // [rsp+1380h] [rbp+1280h] BYREF
  _BYTE v406[32]; // [rsp+1388h] [rbp+1288h] BYREF
  int v407; // [rsp+13A8h] [rbp+12A8h]
  int v408; // [rsp+13B0h] [rbp+12B0h] BYREF
  _BYTE v409[32]; // [rsp+13B8h] [rbp+12B8h] BYREF
  int v410; // [rsp+13D8h] [rbp+12D8h]
  int v411; // [rsp+13E0h] [rbp+12E0h] BYREF
  _BYTE v412[32]; // [rsp+13E8h] [rbp+12E8h] BYREF
  int v413; // [rsp+1408h] [rbp+1308h]
  int v414; // [rsp+1410h] [rbp+1310h] BYREF
  _BYTE v415[32]; // [rsp+1418h] [rbp+1318h] BYREF
  int v416; // [rsp+1438h] [rbp+1338h]
  int v417; // [rsp+1440h] [rbp+1340h] BYREF
  _BYTE v418[32]; // [rsp+1448h] [rbp+1348h] BYREF
  int v419; // [rsp+1468h] [rbp+1368h]
  int v420; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v421[32]; // [rsp+1478h] [rbp+1378h] BYREF
  int v422; // [rsp+1498h] [rbp+1398h]
  int v423; // [rsp+14A0h] [rbp+13A0h] BYREF
  _BYTE v424[32]; // [rsp+14A8h] [rbp+13A8h] BYREF
  int v425; // [rsp+14C8h] [rbp+13C8h]
  int v426; // [rsp+14D0h] [rbp+13D0h] BYREF
  _BYTE v427[32]; // [rsp+14D8h] [rbp+13D8h] BYREF
  int v428; // [rsp+14F8h] [rbp+13F8h]
  int v429; // [rsp+1500h] [rbp+1400h] BYREF
  _BYTE v430[32]; // [rsp+1508h] [rbp+1408h] BYREF
  int v431; // [rsp+1528h] [rbp+1428h]
  int v432; // [rsp+1530h] [rbp+1430h] BYREF
  _BYTE v433[32]; // [rsp+1538h] [rbp+1438h] BYREF
  int v434; // [rsp+1558h] [rbp+1458h]
  int v435; // [rsp+1560h] [rbp+1460h] BYREF
  _BYTE v436[32]; // [rsp+1568h] [rbp+1468h] BYREF
  int v437; // [rsp+1588h] [rbp+1488h]
  int v438; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v439[32]; // [rsp+1598h] [rbp+1498h] BYREF
  int v440; // [rsp+15B8h] [rbp+14B8h]
  int v441; // [rsp+15C0h] [rbp+14C0h] BYREF
  _BYTE v442[32]; // [rsp+15C8h] [rbp+14C8h] BYREF
  int v443; // [rsp+15E8h] [rbp+14E8h]
  int v444; // [rsp+15F0h] [rbp+14F0h] BYREF
  _BYTE v445[32]; // [rsp+15F8h] [rbp+14F8h] BYREF
  int v446; // [rsp+1618h] [rbp+1518h]
  int v447; // [rsp+1620h] [rbp+1520h] BYREF
  _BYTE v448[32]; // [rsp+1628h] [rbp+1528h] BYREF
  int v449; // [rsp+1648h] [rbp+1548h]
  int v450; // [rsp+1650h] [rbp+1550h] BYREF
  _BYTE v451[32]; // [rsp+1658h] [rbp+1558h] BYREF
  int v452; // [rsp+1678h] [rbp+1578h]
  int v453; // [rsp+1680h] [rbp+1580h] BYREF
  _BYTE v454[32]; // [rsp+1688h] [rbp+1588h] BYREF
  int v455; // [rsp+16A8h] [rbp+15A8h]
  int v456; // [rsp+16B0h] [rbp+15B0h] BYREF
  _BYTE v457[32]; // [rsp+16B8h] [rbp+15B8h] BYREF
  int v458; // [rsp+16D8h] [rbp+15D8h]
  int v459; // [rsp+16E0h] [rbp+15E0h] BYREF
  _BYTE v460[32]; // [rsp+16E8h] [rbp+15E8h] BYREF
  int v461; // [rsp+1708h] [rbp+1608h]
  int v462; // [rsp+1710h] [rbp+1610h] BYREF
  _BYTE v463[32]; // [rsp+1718h] [rbp+1618h] BYREF
  int v464; // [rsp+1738h] [rbp+1638h]
  int v465; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v466[32]; // [rsp+1748h] [rbp+1648h] BYREF
  int v467; // [rsp+1768h] [rbp+1668h]
  int v468; // [rsp+1770h] [rbp+1670h] BYREF
  _BYTE v469[32]; // [rsp+1778h] [rbp+1678h] BYREF
  int v470; // [rsp+1798h] [rbp+1698h]
  int v471; // [rsp+17A0h] [rbp+16A0h] BYREF
  _BYTE v472[32]; // [rsp+17A8h] [rbp+16A8h] BYREF
  int v473; // [rsp+17C8h] [rbp+16C8h]
  int v474; // [rsp+17D0h] [rbp+16D0h] BYREF
  _BYTE v475[32]; // [rsp+17D8h] [rbp+16D8h] BYREF
  int v476; // [rsp+17F8h] [rbp+16F8h]
  int v477; // [rsp+1800h] [rbp+1700h] BYREF
  _BYTE v478[32]; // [rsp+1808h] [rbp+1708h] BYREF
  int v479; // [rsp+1828h] [rbp+1728h]
  int v480; // [rsp+1830h] [rbp+1730h] BYREF
  _BYTE v481[32]; // [rsp+1838h] [rbp+1738h] BYREF
  int v482; // [rsp+1858h] [rbp+1758h]
  int v483; // [rsp+1860h] [rbp+1760h] BYREF
  _BYTE v484[32]; // [rsp+1868h] [rbp+1768h] BYREF
  int v485; // [rsp+1888h] [rbp+1788h]
  int v486; // [rsp+1890h] [rbp+1790h] BYREF
  _BYTE v487[32]; // [rsp+1898h] [rbp+1798h] BYREF
  int v488; // [rsp+18B8h] [rbp+17B8h]
  int v489; // [rsp+18C0h] [rbp+17C0h] BYREF
  _BYTE v490[32]; // [rsp+18C8h] [rbp+17C8h] BYREF
  int v491; // [rsp+18E8h] [rbp+17E8h]
  int v492; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v493[32]; // [rsp+18F8h] [rbp+17F8h] BYREF
  int v494; // [rsp+1918h] [rbp+1818h]
  int v495; // [rsp+1920h] [rbp+1820h] BYREF
  _BYTE v496[32]; // [rsp+1928h] [rbp+1828h] BYREF
  int v497; // [rsp+1948h] [rbp+1848h]
  int v498; // [rsp+1950h] [rbp+1850h] BYREF
  _BYTE v499[32]; // [rsp+1958h] [rbp+1858h] BYREF
  int v500; // [rsp+1978h] [rbp+1878h]
  int v501; // [rsp+1980h] [rbp+1880h] BYREF
  _BYTE v502[32]; // [rsp+1988h] [rbp+1888h] BYREF
  int v503; // [rsp+19A8h] [rbp+18A8h]
  int v504; // [rsp+19B0h] [rbp+18B0h] BYREF
  _BYTE v505[32]; // [rsp+19B8h] [rbp+18B8h] BYREF
  int v506; // [rsp+19D8h] [rbp+18D8h]
  int v507; // [rsp+19E0h] [rbp+18E0h] BYREF
  _BYTE v508[32]; // [rsp+19E8h] [rbp+18E8h] BYREF
  int v509; // [rsp+1A08h] [rbp+1908h]
  int v510; // [rsp+1A10h] [rbp+1910h] BYREF
  _BYTE v511[32]; // [rsp+1A18h] [rbp+1918h] BYREF
  int v512; // [rsp+1A38h] [rbp+1938h]
  int v513; // [rsp+1A40h] [rbp+1940h] BYREF
  _BYTE v514[32]; // [rsp+1A48h] [rbp+1948h] BYREF
  int v515; // [rsp+1A68h] [rbp+1968h]
  int v516; // [rsp+1A70h] [rbp+1970h] BYREF
  _BYTE v517[32]; // [rsp+1A78h] [rbp+1978h] BYREF
  int v518; // [rsp+1A98h] [rbp+1998h]
  int v519; // [rsp+1AA0h] [rbp+19A0h] BYREF
  _BYTE v520[32]; // [rsp+1AA8h] [rbp+19A8h] BYREF
  int v521; // [rsp+1AC8h] [rbp+19C8h]
  int v522; // [rsp+1AD0h] [rbp+19D0h] BYREF
  _BYTE v523[32]; // [rsp+1AD8h] [rbp+19D8h] BYREF
  int v524; // [rsp+1AF8h] [rbp+19F8h]
  int v525; // [rsp+1B00h] [rbp+1A00h] BYREF
  _BYTE v526[32]; // [rsp+1B08h] [rbp+1A08h] BYREF
  int v527; // [rsp+1B28h] [rbp+1A28h]
  int v528; // [rsp+1B30h] [rbp+1A30h] BYREF
  _BYTE v529[32]; // [rsp+1B38h] [rbp+1A38h] BYREF
  int v530; // [rsp+1B58h] [rbp+1A58h]
  int v531; // [rsp+1B60h] [rbp+1A60h] BYREF
  _BYTE v532[32]; // [rsp+1B68h] [rbp+1A68h] BYREF
  int v533; // [rsp+1B88h] [rbp+1A88h]
  int v534; // [rsp+1B90h] [rbp+1A90h] BYREF
  _BYTE v535[32]; // [rsp+1B98h] [rbp+1A98h] BYREF
  int v536; // [rsp+1BB8h] [rbp+1AB8h]
  int v537; // [rsp+1BC0h] [rbp+1AC0h] BYREF
  _BYTE v538[32]; // [rsp+1BC8h] [rbp+1AC8h] BYREF
  int v539; // [rsp+1BE8h] [rbp+1AE8h]
  int v540; // [rsp+1BF0h] [rbp+1AF0h] BYREF
  _BYTE v541[32]; // [rsp+1BF8h] [rbp+1AF8h] BYREF
  int v542; // [rsp+1C18h] [rbp+1B18h]
  int v543; // [rsp+1C20h] [rbp+1B20h] BYREF
  _BYTE v544[32]; // [rsp+1C28h] [rbp+1B28h] BYREF
  int v545; // [rsp+1C48h] [rbp+1B48h]
  int v546; // [rsp+1C50h] [rbp+1B50h] BYREF
  _BYTE v547[32]; // [rsp+1C58h] [rbp+1B58h] BYREF
  int v548; // [rsp+1C78h] [rbp+1B78h]
  int v549; // [rsp+1C80h] [rbp+1B80h] BYREF
  _BYTE v550[32]; // [rsp+1C88h] [rbp+1B88h] BYREF
  int v551; // [rsp+1CA8h] [rbp+1BA8h]
  int v552; // [rsp+1CB0h] [rbp+1BB0h] BYREF
  _BYTE v553[32]; // [rsp+1CB8h] [rbp+1BB8h] BYREF
  int v554; // [rsp+1CD8h] [rbp+1BD8h]
  int v555; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  _BYTE v556[32]; // [rsp+1CE8h] [rbp+1BE8h] BYREF
  int v557; // [rsp+1D08h] [rbp+1C08h]
  int v558; // [rsp+1D10h] [rbp+1C10h] BYREF
  _BYTE v559[32]; // [rsp+1D18h] [rbp+1C18h] BYREF
  int v560; // [rsp+1D38h] [rbp+1C38h]
  _DWORD v561[4]; // [rsp+1D40h] [rbp+1C40h] BYREF
  _BYTE v562[32]; // [rsp+1D50h] [rbp+1C50h] BYREF
  int v563; // [rsp+1D70h] [rbp+1C70h]
  int v564; // [rsp+1D78h] [rbp+1C78h]
  int v565; // [rsp+1D80h] [rbp+1C80h]
  _BYTE v566[32]; // [rsp+1D88h] [rbp+1C88h] BYREF
  int v567; // [rsp+1DA8h] [rbp+1CA8h]
  int v568; // [rsp+1DB0h] [rbp+1CB0h]
  int v569; // [rsp+1DB8h] [rbp+1CB8h]
  _BYTE v570[32]; // [rsp+1DC0h] [rbp+1CC0h] BYREF
  int v571; // [rsp+1DE0h] [rbp+1CE0h]
  int v572; // [rsp+1DE8h] [rbp+1CE8h]
  int v573; // [rsp+1DF0h] [rbp+1CF0h]
  _BYTE v574[32]; // [rsp+1DF8h] [rbp+1CF8h] BYREF
  int v575; // [rsp+1E18h] [rbp+1D18h]
  int v576; // [rsp+1E20h] [rbp+1D20h]
  int v577; // [rsp+1E28h] [rbp+1D28h]
  _BYTE v578[32]; // [rsp+1E30h] [rbp+1D30h] BYREF
  int v579; // [rsp+1E50h] [rbp+1D50h]
  int v580; // [rsp+1E58h] [rbp+1D58h]
  int v581; // [rsp+1E60h] [rbp+1D60h]
  _BYTE v582[32]; // [rsp+1E68h] [rbp+1D68h] BYREF
  int v583; // [rsp+1E88h] [rbp+1D88h]
  int v584; // [rsp+1E90h] [rbp+1D90h]
  int v585; // [rsp+1E98h] [rbp+1D98h]
  _BYTE v586[32]; // [rsp+1EA0h] [rbp+1DA0h] BYREF
  int v587; // [rsp+1EC0h] [rbp+1DC0h]
  int v588; // [rsp+1EC8h] [rbp+1DC8h]
  int v589; // [rsp+1ED0h] [rbp+1DD0h]
  _BYTE v590[32]; // [rsp+1ED8h] [rbp+1DD8h] BYREF
  int v591; // [rsp+1EF8h] [rbp+1DF8h]
  int v592; // [rsp+1F00h] [rbp+1E00h]
  int v593; // [rsp+1F08h] [rbp+1E08h]
  _BYTE v594[32]; // [rsp+1F10h] [rbp+1E10h] BYREF
  int v595; // [rsp+1F30h] [rbp+1E30h]
  int v596; // [rsp+1F38h] [rbp+1E38h]
  int v597; // [rsp+1F40h] [rbp+1E40h]
  _BYTE v598[32]; // [rsp+1F48h] [rbp+1E48h] BYREF
  int v599; // [rsp+1F68h] [rbp+1E68h]
  int v600; // [rsp+1F70h] [rbp+1E70h]
  int v601; // [rsp+1F78h] [rbp+1E78h]
  _BYTE v602[32]; // [rsp+1F80h] [rbp+1E80h] BYREF
  int v603; // [rsp+1FA0h] [rbp+1EA0h]
  int v604; // [rsp+1FA8h] [rbp+1EA8h]
  int v605; // [rsp+1FB0h] [rbp+1EB0h]
  _BYTE v606[32]; // [rsp+1FB8h] [rbp+1EB8h] BYREF
  int v607; // [rsp+1FD8h] [rbp+1ED8h]
  int v608; // [rsp+1FE0h] [rbp+1EE0h]
  int v609; // [rsp+1FE8h] [rbp+1EE8h]
  _BYTE v610[32]; // [rsp+1FF0h] [rbp+1EF0h] BYREF
  int v611; // [rsp+2010h] [rbp+1F10h]
  int v612; // [rsp+2018h] [rbp+1F18h]
  int v613; // [rsp+2020h] [rbp+1F20h]
  _BYTE v614[32]; // [rsp+2028h] [rbp+1F28h] BYREF
  int v615; // [rsp+2048h] [rbp+1F48h]
  int v616; // [rsp+2050h] [rbp+1F50h]
  int v617; // [rsp+2058h] [rbp+1F58h]
  _BYTE v618[32]; // [rsp+2060h] [rbp+1F60h] BYREF
  int v619; // [rsp+2080h] [rbp+1F80h]
  int v620; // [rsp+2088h] [rbp+1F88h]
  int v621; // [rsp+2090h] [rbp+1F90h]
  _BYTE v622[32]; // [rsp+2098h] [rbp+1F98h] BYREF
  int v623; // [rsp+20B8h] [rbp+1FB8h]
  int v624; // [rsp+20C0h] [rbp+1FC0h]
  int v625; // [rsp+20C8h] [rbp+1FC8h]
  _BYTE v626[32]; // [rsp+20D0h] [rbp+1FD0h] BYREF
  int v627; // [rsp+20F0h] [rbp+1FF0h]
  int v628; // [rsp+20F8h] [rbp+1FF8h]
  int v629; // [rsp+2100h] [rbp+2000h]
  _BYTE v630[32]; // [rsp+2108h] [rbp+2008h] BYREF
  int v631; // [rsp+2128h] [rbp+2028h]
  int v632; // [rsp+2130h] [rbp+2030h]
  int v633; // [rsp+2138h] [rbp+2038h]
  _BYTE v634[32]; // [rsp+2140h] [rbp+2040h] BYREF
  int v635; // [rsp+2160h] [rbp+2060h]
  int v636; // [rsp+2168h] [rbp+2068h]
  int v637; // [rsp+2170h] [rbp+2070h]
  _BYTE v638[32]; // [rsp+2178h] [rbp+2078h] BYREF
  int v639; // [rsp+2198h] [rbp+2098h]
  int v640; // [rsp+21A0h] [rbp+20A0h]
  int v641; // [rsp+21A8h] [rbp+20A8h]
  _BYTE v642[32]; // [rsp+21B0h] [rbp+20B0h] BYREF
  int v643; // [rsp+21D0h] [rbp+20D0h]
  int v644; // [rsp+21D8h] [rbp+20D8h]
  int v645; // [rsp+21E0h] [rbp+20E0h]
  _BYTE v646[32]; // [rsp+21E8h] [rbp+20E8h] BYREF
  int v647; // [rsp+2208h] [rbp+2108h]
  int v648; // [rsp+2210h] [rbp+2110h]
  int v649; // [rsp+2218h] [rbp+2118h]
  _BYTE v650[32]; // [rsp+2220h] [rbp+2120h] BYREF
  int v651; // [rsp+2240h] [rbp+2140h]
  int v652; // [rsp+2248h] [rbp+2148h]
  int v653; // [rsp+2250h] [rbp+2150h]
  _BYTE v654[32]; // [rsp+2258h] [rbp+2158h] BYREF
  int v655; // [rsp+2278h] [rbp+2178h]
  int v656; // [rsp+2280h] [rbp+2180h]
  int v657; // [rsp+2288h] [rbp+2188h]
  _BYTE v658[32]; // [rsp+2290h] [rbp+2190h] BYREF
  int v659; // [rsp+22B0h] [rbp+21B0h]
  int v660; // [rsp+22B8h] [rbp+21B8h]
  int v661; // [rsp+22C0h] [rbp+21C0h]
  _BYTE v662[32]; // [rsp+22C8h] [rbp+21C8h] BYREF
  int v663; // [rsp+22E8h] [rbp+21E8h]
  int v664; // [rsp+22F0h] [rbp+21F0h]
  int v665; // [rsp+22F8h] [rbp+21F8h]
  _BYTE v666[32]; // [rsp+2300h] [rbp+2200h] BYREF
  int v667; // [rsp+2320h] [rbp+2220h]
  int v668; // [rsp+2328h] [rbp+2228h]
  int v669; // [rsp+2330h] [rbp+2230h]
  _BYTE v670[32]; // [rsp+2338h] [rbp+2238h] BYREF
  int v671; // [rsp+2358h] [rbp+2258h]
  int v672; // [rsp+2360h] [rbp+2260h]
  int v673; // [rsp+2368h] [rbp+2268h]
  _BYTE v674[32]; // [rsp+2370h] [rbp+2270h] BYREF
  int v675; // [rsp+2390h] [rbp+2290h]
  int v676; // [rsp+2398h] [rbp+2298h]
  int v677; // [rsp+23A0h] [rbp+22A0h]
  _BYTE v678[32]; // [rsp+23A8h] [rbp+22A8h] BYREF
  int v679; // [rsp+23C8h] [rbp+22C8h]
  int v680; // [rsp+23D0h] [rbp+22D0h]
  int v681; // [rsp+23D8h] [rbp+22D8h]
  _BYTE v682[32]; // [rsp+23E0h] [rbp+22E0h] BYREF
  int v683; // [rsp+2400h] [rbp+2300h]
  int v684; // [rsp+2408h] [rbp+2308h]
  int v685; // [rsp+2410h] [rbp+2310h]
  _BYTE v686[32]; // [rsp+2418h] [rbp+2318h] BYREF
  int v687; // [rsp+2438h] [rbp+2338h]
  int v688; // [rsp+2440h] [rbp+2340h]
  int v689; // [rsp+2448h] [rbp+2348h]
  _BYTE v690[32]; // [rsp+2450h] [rbp+2350h] BYREF
  int v691; // [rsp+2470h] [rbp+2370h]
  int v692; // [rsp+2478h] [rbp+2378h]
  int v693; // [rsp+2480h] [rbp+2380h]
  _BYTE v694[32]; // [rsp+2488h] [rbp+2388h] BYREF
  int v695; // [rsp+24A8h] [rbp+23A8h]
  int v696; // [rsp+24B0h] [rbp+23B0h]
  int v697; // [rsp+24B8h] [rbp+23B8h]
  _BYTE v698[32]; // [rsp+24C0h] [rbp+23C0h] BYREF
  int v699; // [rsp+24E0h] [rbp+23E0h]
  int v700; // [rsp+24E8h] [rbp+23E8h]
  int v701; // [rsp+24F0h] [rbp+23F0h]
  _BYTE v702[32]; // [rsp+24F8h] [rbp+23F8h] BYREF
  int v703; // [rsp+2518h] [rbp+2418h]
  int v704; // [rsp+2520h] [rbp+2420h]
  int v705; // [rsp+2528h] [rbp+2428h]
  _BYTE v706[32]; // [rsp+2530h] [rbp+2430h] BYREF
  int v707; // [rsp+2550h] [rbp+2450h]
  int v708; // [rsp+2558h] [rbp+2458h]
  int v709; // [rsp+2560h] [rbp+2460h]
  _BYTE v710[32]; // [rsp+2568h] [rbp+2468h] BYREF
  int v711; // [rsp+2588h] [rbp+2488h]
  int v712; // [rsp+2590h] [rbp+2490h]
  int v713; // [rsp+2598h] [rbp+2498h]
  _BYTE v714[32]; // [rsp+25A0h] [rbp+24A0h] BYREF
  int v715; // [rsp+25C0h] [rbp+24C0h]
  int v716; // [rsp+25C8h] [rbp+24C8h]
  int v717; // [rsp+25D0h] [rbp+24D0h]
  _BYTE v718[32]; // [rsp+25D8h] [rbp+24D8h] BYREF
  int v719; // [rsp+25F8h] [rbp+24F8h]
  int v720; // [rsp+2600h] [rbp+2500h]
  int v721; // [rsp+2608h] [rbp+2508h]
  _BYTE v722[32]; // [rsp+2610h] [rbp+2510h] BYREF
  int v723; // [rsp+2630h] [rbp+2530h]
  int v724; // [rsp+2638h] [rbp+2538h]
  int v725; // [rsp+2640h] [rbp+2540h]
  _BYTE v726[32]; // [rsp+2648h] [rbp+2548h] BYREF
  int v727; // [rsp+2668h] [rbp+2568h]
  int v728; // [rsp+2670h] [rbp+2570h]
  int v729; // [rsp+2678h] [rbp+2578h]
  _BYTE v730[32]; // [rsp+2680h] [rbp+2580h] BYREF
  int v731; // [rsp+26A0h] [rbp+25A0h]
  int v732; // [rsp+26A8h] [rbp+25A8h]
  int v733; // [rsp+26B0h] [rbp+25B0h]
  _BYTE v734[32]; // [rsp+26B8h] [rbp+25B8h] BYREF
  int v735; // [rsp+26D8h] [rbp+25D8h]
  int v736; // [rsp+26E0h] [rbp+25E0h]
  int v737; // [rsp+26E8h] [rbp+25E8h]
  _BYTE v738[32]; // [rsp+26F0h] [rbp+25F0h] BYREF
  int v739; // [rsp+2710h] [rbp+2610h]
  int v740; // [rsp+2718h] [rbp+2618h]
  int v741; // [rsp+2720h] [rbp+2620h]
  _BYTE v742[32]; // [rsp+2728h] [rbp+2628h] BYREF
  int v743; // [rsp+2748h] [rbp+2648h]
  int v744; // [rsp+2750h] [rbp+2650h]
  int v745; // [rsp+2758h] [rbp+2658h]
  _BYTE v746[32]; // [rsp+2760h] [rbp+2660h] BYREF
  int v747; // [rsp+2780h] [rbp+2680h]
  int v748; // [rsp+2788h] [rbp+2688h]
  int v749; // [rsp+2790h] [rbp+2690h]
  _BYTE v750[32]; // [rsp+2798h] [rbp+2698h] BYREF
  int v751; // [rsp+27B8h] [rbp+26B8h]
  int v752; // [rsp+27C0h] [rbp+26C0h]
  int v753; // [rsp+27C8h] [rbp+26C8h]
  _BYTE v754[32]; // [rsp+27D0h] [rbp+26D0h] BYREF
  int v755; // [rsp+27F0h] [rbp+26F0h]
  int v756; // [rsp+27F8h] [rbp+26F8h]
  int v757; // [rsp+2800h] [rbp+2700h]
  _BYTE v758[32]; // [rsp+2808h] [rbp+2708h] BYREF
  int v759; // [rsp+2828h] [rbp+2728h]
  int v760; // [rsp+2830h] [rbp+2730h]
  int v761; // [rsp+2838h] [rbp+2738h]
  _BYTE v762[32]; // [rsp+2840h] [rbp+2740h] BYREF
  int v763; // [rsp+2860h] [rbp+2760h]
  int v764; // [rsp+2868h] [rbp+2768h]
  int v765; // [rsp+2870h] [rbp+2770h]
  _BYTE v766[32]; // [rsp+2878h] [rbp+2778h] BYREF
  int v767; // [rsp+2898h] [rbp+2798h]
  int v768; // [rsp+28A0h] [rbp+27A0h]
  int v769; // [rsp+28A8h] [rbp+27A8h]
  _BYTE v770[32]; // [rsp+28B0h] [rbp+27B0h] BYREF
  int v771; // [rsp+28D0h] [rbp+27D0h]
  int v772; // [rsp+28D8h] [rbp+27D8h]
  int v773; // [rsp+28E0h] [rbp+27E0h]
  _BYTE v774[32]; // [rsp+28E8h] [rbp+27E8h] BYREF
  int v775; // [rsp+2908h] [rbp+2808h]
  int v776; // [rsp+2910h] [rbp+2810h]
  int v777; // [rsp+2918h] [rbp+2818h]
  _BYTE v778[32]; // [rsp+2920h] [rbp+2820h] BYREF
  int v779; // [rsp+2940h] [rbp+2840h]
  int v780; // [rsp+2948h] [rbp+2848h]
  int v781; // [rsp+2950h] [rbp+2850h]
  _BYTE v782[32]; // [rsp+2958h] [rbp+2858h] BYREF
  int v783; // [rsp+2978h] [rbp+2878h]
  int v784; // [rsp+2980h] [rbp+2880h]
  int v785; // [rsp+2988h] [rbp+2888h]
  _BYTE v786[32]; // [rsp+2990h] [rbp+2890h] BYREF
  int v787; // [rsp+29B0h] [rbp+28B0h]
  int v788; // [rsp+29B8h] [rbp+28B8h]
  int v789; // [rsp+29C0h] [rbp+28C0h]
  _BYTE v790[32]; // [rsp+29C8h] [rbp+28C8h] BYREF
  int v791; // [rsp+29E8h] [rbp+28E8h]
  int v792; // [rsp+29F0h] [rbp+28F0h]
  int v793; // [rsp+29F8h] [rbp+28F8h]
  _BYTE v794[32]; // [rsp+2A00h] [rbp+2900h] BYREF
  int v795; // [rsp+2A20h] [rbp+2920h]
  int v796; // [rsp+2A28h] [rbp+2928h]
  int v797; // [rsp+2A30h] [rbp+2930h]
  _BYTE v798[32]; // [rsp+2A38h] [rbp+2938h] BYREF
  int v799; // [rsp+2A58h] [rbp+2958h]
  int v800; // [rsp+2A60h] [rbp+2960h]
  int v801; // [rsp+2A68h] [rbp+2968h]
  _BYTE v802[32]; // [rsp+2A70h] [rbp+2970h] BYREF
  int v803; // [rsp+2A90h] [rbp+2990h]
  int v804; // [rsp+2A98h] [rbp+2998h]
  int v805; // [rsp+2AA0h] [rbp+29A0h]
  _BYTE v806[32]; // [rsp+2AA8h] [rbp+29A8h] BYREF
  int v807; // [rsp+2AC8h] [rbp+29C8h]
  int v808; // [rsp+2AD0h] [rbp+29D0h]
  int v809; // [rsp+2AD8h] [rbp+29D8h]
  _BYTE v810[32]; // [rsp+2AE0h] [rbp+29E0h] BYREF
  int v811; // [rsp+2B00h] [rbp+2A00h]
  int v812; // [rsp+2B08h] [rbp+2A08h]
  int v813; // [rsp+2B10h] [rbp+2A10h]
  _BYTE v814[32]; // [rsp+2B18h] [rbp+2A18h] BYREF
  int v815; // [rsp+2B38h] [rbp+2A38h]
  int v816; // [rsp+2B40h] [rbp+2A40h]
  int v817; // [rsp+2B48h] [rbp+2A48h]
  _BYTE v818[32]; // [rsp+2B50h] [rbp+2A50h] BYREF
  int v819; // [rsp+2B70h] [rbp+2A70h]
  int v820; // [rsp+2B78h] [rbp+2A78h]
  int v821; // [rsp+2B80h] [rbp+2A80h]
  _BYTE v822[32]; // [rsp+2B88h] [rbp+2A88h] BYREF
  int v823; // [rsp+2BA8h] [rbp+2AA8h]
  int v824; // [rsp+2BB0h] [rbp+2AB0h]
  int v825; // [rsp+2BB8h] [rbp+2AB8h]
  _BYTE v826[32]; // [rsp+2BC0h] [rbp+2AC0h] BYREF
  int v827; // [rsp+2BE0h] [rbp+2AE0h]
  int v828; // [rsp+2BE8h] [rbp+2AE8h]
  int v829; // [rsp+2BF0h] [rbp+2AF0h]
  _BYTE v830[32]; // [rsp+2BF8h] [rbp+2AF8h] BYREF
  int v831; // [rsp+2C18h] [rbp+2B18h]
  int v832; // [rsp+2C20h] [rbp+2B20h]
  int v833; // [rsp+2C28h] [rbp+2B28h]
  _BYTE v834[32]; // [rsp+2C30h] [rbp+2B30h] BYREF
  int v835; // [rsp+2C50h] [rbp+2B50h]
  int v836; // [rsp+2C58h] [rbp+2B58h]
  int v837; // [rsp+2C60h] [rbp+2B60h]
  _BYTE v838[32]; // [rsp+2C68h] [rbp+2B68h] BYREF
  int v839; // [rsp+2C88h] [rbp+2B88h]
  int v840; // [rsp+2C90h] [rbp+2B90h]
  int v841; // [rsp+2C98h] [rbp+2B98h]
  _BYTE v842[32]; // [rsp+2CA0h] [rbp+2BA0h] BYREF
  int v843; // [rsp+2CC0h] [rbp+2BC0h]
  int v844; // [rsp+2CC8h] [rbp+2BC8h]
  int v845; // [rsp+2CD0h] [rbp+2BD0h]
  _BYTE v846[32]; // [rsp+2CD8h] [rbp+2BD8h] BYREF
  int v847; // [rsp+2CF8h] [rbp+2BF8h]
  int v848; // [rsp+2D00h] [rbp+2C00h]
  int v849; // [rsp+2D08h] [rbp+2C08h]
  _BYTE v850[32]; // [rsp+2D10h] [rbp+2C10h] BYREF
  int v851; // [rsp+2D30h] [rbp+2C30h]
  int v852; // [rsp+2D38h] [rbp+2C38h]
  int v853; // [rsp+2D40h] [rbp+2C40h]
  _BYTE v854[32]; // [rsp+2D48h] [rbp+2C48h] BYREF
  int v855; // [rsp+2D68h] [rbp+2C68h]
  int v856; // [rsp+2D70h] [rbp+2C70h]
  int v857; // [rsp+2D78h] [rbp+2C78h]
  _BYTE v858[32]; // [rsp+2D80h] [rbp+2C80h] BYREF
  int v859; // [rsp+2DA0h] [rbp+2CA0h]
  int v860; // [rsp+2DA8h] [rbp+2CA8h]
  int v861; // [rsp+2DB0h] [rbp+2CB0h]
  _BYTE v862[32]; // [rsp+2DB8h] [rbp+2CB8h] BYREF
  int v863; // [rsp+2DD8h] [rbp+2CD8h]
  int v864; // [rsp+2DE0h] [rbp+2CE0h]
  int v865; // [rsp+2DE8h] [rbp+2CE8h]
  _BYTE v866[32]; // [rsp+2DF0h] [rbp+2CF0h] BYREF
  int v867; // [rsp+2E10h] [rbp+2D10h]
  int v868; // [rsp+2E18h] [rbp+2D18h]
  int v869; // [rsp+2E20h] [rbp+2D20h]
  _BYTE v870[32]; // [rsp+2E28h] [rbp+2D28h] BYREF
  int v871; // [rsp+2E48h] [rbp+2D48h]
  int v872; // [rsp+2E50h] [rbp+2D50h]
  int v873; // [rsp+2E58h] [rbp+2D58h]
  _BYTE v874[32]; // [rsp+2E60h] [rbp+2D60h] BYREF
  int v875; // [rsp+2E80h] [rbp+2D80h]
  int v876; // [rsp+2E88h] [rbp+2D88h]
  int v877; // [rsp+2E90h] [rbp+2D90h]
  _BYTE v878[32]; // [rsp+2E98h] [rbp+2D98h] BYREF
  int v879; // [rsp+2EB8h] [rbp+2DB8h]
  int v880; // [rsp+2EC0h] [rbp+2DC0h]
  int v881; // [rsp+2EC8h] [rbp+2DC8h]
  _BYTE v882[32]; // [rsp+2ED0h] [rbp+2DD0h] BYREF
  int v883; // [rsp+2EF0h] [rbp+2DF0h]
  int v884; // [rsp+2EF8h] [rbp+2DF8h]
  int v885; // [rsp+2F00h] [rbp+2E00h]
  _BYTE v886[32]; // [rsp+2F08h] [rbp+2E08h] BYREF
  int v887; // [rsp+2F28h] [rbp+2E28h]
  int v888; // [rsp+2F30h] [rbp+2E30h]
  int v889; // [rsp+2F38h] [rbp+2E38h]
  _BYTE v890[32]; // [rsp+2F40h] [rbp+2E40h] BYREF
  int v891; // [rsp+2F60h] [rbp+2E60h]
  int v892; // [rsp+2F68h] [rbp+2E68h]
  int v893; // [rsp+2F70h] [rbp+2E70h]
  _BYTE v894[32]; // [rsp+2F78h] [rbp+2E78h] BYREF
  int v895; // [rsp+2F98h] [rbp+2E98h]
  int v896; // [rsp+2FA0h] [rbp+2EA0h]
  int v897; // [rsp+2FA8h] [rbp+2EA8h]
  _BYTE v898[32]; // [rsp+2FB0h] [rbp+2EB0h] BYREF
  int v899; // [rsp+2FD0h] [rbp+2ED0h]
  int v900; // [rsp+2FD8h] [rbp+2ED8h]
  int v901; // [rsp+2FE0h] [rbp+2EE0h]
  _BYTE v902[32]; // [rsp+2FE8h] [rbp+2EE8h] BYREF
  int v903; // [rsp+3008h] [rbp+2F08h]
  int v904; // [rsp+3010h] [rbp+2F10h]
  int v905; // [rsp+3018h] [rbp+2F18h]
  _BYTE v906[32]; // [rsp+3020h] [rbp+2F20h] BYREF
  int v907; // [rsp+3040h] [rbp+2F40h]
  int v908; // [rsp+3048h] [rbp+2F48h]
  int v909; // [rsp+3050h] [rbp+2F50h]
  _BYTE v910[32]; // [rsp+3058h] [rbp+2F58h] BYREF
  int v911; // [rsp+3078h] [rbp+2F78h]
  int v912; // [rsp+3080h] [rbp+2F80h]
  int v913; // [rsp+3088h] [rbp+2F88h]
  _BYTE v914[32]; // [rsp+3090h] [rbp+2F90h] BYREF
  int v915; // [rsp+30B0h] [rbp+2FB0h]
  int v916; // [rsp+30B8h] [rbp+2FB8h]
  int v917; // [rsp+30C0h] [rbp+2FC0h]
  _BYTE v918[32]; // [rsp+30C8h] [rbp+2FC8h] BYREF
  int v919; // [rsp+30E8h] [rbp+2FE8h]
  int v920; // [rsp+30F0h] [rbp+2FF0h]
  int v921; // [rsp+30F8h] [rbp+2FF8h]
  _BYTE v922[32]; // [rsp+3100h] [rbp+3000h] BYREF
  int v923; // [rsp+3120h] [rbp+3020h]
  int v924; // [rsp+3128h] [rbp+3028h]
  int v925; // [rsp+3130h] [rbp+3030h]
  _BYTE v926[32]; // [rsp+3138h] [rbp+3038h] BYREF
  int v927; // [rsp+3158h] [rbp+3058h]
  int v928; // [rsp+3160h] [rbp+3060h]
  int v929; // [rsp+3168h] [rbp+3068h]
  _BYTE v930[32]; // [rsp+3170h] [rbp+3070h] BYREF
  int v931; // [rsp+3190h] [rbp+3090h]
  char v932; // [rsp+3198h] [rbp+3098h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v3, L"ActiveDirectoryBackupSrkPub", 27);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v558, 5, &v3, 3);
  v561[0] = 0;
  v561[2] = v558;
  std::wstring::wstring(v562, v559);
  v563 = v560;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v6, L"AIKCertAcquiredExpired", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v555, 4, &v6, 4);
  v564 = 1;
  v565 = v555;
  std::wstring::wstring(v566, v556);
  v567 = v557;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v9, L"AIKEnrollmentErrorCode", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v552, 4, &v9, 4);
  v568 = 2;
  v569 = v552;
  std::wstring::wstring(v570, v553);
  v571 = v554;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12, L"ClearReason", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v549, 3, &v12, 1);
  v572 = 3;
  v573 = v549;
  std::wstring::wstring(v574, v550);
  v575 = v551;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v15, L"EkCertCorrelationId", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v546, 9, &v15, 1);
  v576 = 12;
  v577 = v546;
  std::wstring::wstring(v578, v547);
  v579 = v548;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"EkCertNvFailureStep", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v543, 9, &v18, 4);
  v580 = 13;
  v581 = v543;
  std::wstring::wstring(v582, v544);
  v583 = v545;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v21, L"EkCertFetchSupport", 18);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v540, 9, &v21, 4);
  v584 = 14;
  v585 = v540;
  std::wstring::wstring(v586, v541);
  v587 = v542;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v24, L"EkCertIndex", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v537, 9, &v24, 4);
  v588 = 15;
  v589 = v537;
  std::wstring::wstring(v590, v538);
  v591 = v539;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v27, L"EkCertPath", 10);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v534, 9, &v27, 4);
  v592 = 16;
  v593 = v534;
  std::wstring::wstring(v594, v535);
  v595 = v536;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"EkCertProvisionResult", 21);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v531, 9, &v30, 4);
  v596 = 17;
  v597 = v531;
  std::wstring::wstring(v598, v532);
  v599 = v533;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v33, L"EkCertRescheduleTaskFailureStep", 31);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v528, 9, &v33, 4);
  v600 = 18;
  v601 = v528;
  std::wstring::wstring(v602, v529);
  v603 = v530;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v36, L"EkCertRetrieveCertFailureStep", 29);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v525, 9, &v36, 4);
  v604 = 19;
  v605 = v525;
  std::wstring::wstring(v606, v526);
  v607 = v527;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v39, L"EkCertsCleanedUp", 16);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v522, 9, &v39, 4);
  v608 = 20;
  v609 = v522;
  std::wstring::wstring(v610, v523);
  v611 = v524;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"EkCertsInstalledFromNV", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v519, 9, &v42, 4);
  v612 = 21;
  v613 = v519;
  std::wstring::wstring(v614, v520);
  v615 = v521;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v45, L"EkCreatePersistResult", 21);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v516, 9, &v45, 4);
  v616 = 22;
  v617 = v516;
  std::wstring::wstring(v618, v517);
  v619 = v518;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v48, L"EKCorrelationId", 15);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v513, 6, &v48, 1);
  v620 = 4;
  v621 = v513;
  std::wstring::wstring(v622, v514);
  v623 = v515;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v51, L"EkFirstTimeout", 14);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v510, 6, &v51, 4);
  v624 = 5;
  v625 = v510;
  std::wstring::wstring(v626, v511);
  v627 = v512;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v54, L"EkMaxTries", 10);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v507, 6, &v54, 4);
  v628 = 6;
  v629 = v507;
  std::wstring::wstring(v630, v508);
  v631 = v509;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v57, L"EkNoFetch", 9);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v504, 6, &v57, 4);
  v632 = 7;
  v633 = v504;
  std::wstring::wstring(v634, v505);
  v635 = v506;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v60, L"EKNonce", 7);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v501, 6, &v60, 3);
  v636 = 8;
  v637 = v501;
  std::wstring::wstring(v638, v502);
  v639 = v503;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v63, L"EkPub", 5);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v498, 6, &v63, 3);
  v640 = 9;
  v641 = v498;
  std::wstring::wstring(v642, v499);
  v643 = v500;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v66, L"EkRetryLast", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v495, 6, &v66, 11);
  v644 = 10;
  v645 = v495;
  std::wstring::wstring(v646, v496);
  v647 = v497;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v69, L"EkTries", 7);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v492, 6, &v69, 4);
  v648 = 11;
  v649 = v492;
  std::wstring::wstring(v650, v493);
  v651 = v494;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v72, L"EnableInterruptSupport", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v489, 1, &v72, 4);
  v652 = 23;
  v653 = v489;
  std::wstring::wstring(v654, v490);
  v655 = v491;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v75, L"EndorsementAuth", 15);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v486, 6, &v75, 1);
  v656 = 24;
  v657 = v486;
  std::wstring::wstring(v658, v487);
  v659 = v488;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v78, L"FasrCapable", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v483, 8, &v78, 4);
  v660 = 27;
  v661 = v483;
  std::wstring::wstring(v662, v484);
  v663 = v485;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v81, L"FasrCustomBootPath", 18);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v480, 8, &v81, 4);
  v664 = 28;
  v665 = v480;
  std::wstring::wstring(v666, v481);
  v667 = v482;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v84, L"FasrCustomBootPathReasons", 25);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v477, 8, &v84, 1);
  v668 = 29;
  v669 = v477;
  std::wstring::wstring(v670, v478);
  v671 = v479;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v87, L"FasrFwVersion", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v474, 8, &v87, 1);
  v672 = 30;
  v673 = v474;
  std::wstring::wstring(v674, v475);
  v675 = v476;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v90, L"FasrProdImage", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v471, 8, &v90, 4);
  v676 = 31;
  v677 = v471;
  std::wstring::wstring(v678, v472);
  v679 = v473;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v93, L"TcgSecureBootValue", 18);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v468, 8, &v93, 4);
  v680 = 34;
  v681 = v468;
  std::wstring::wstring(v682, v469);
  v683 = v470;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v96, L"TcgHvciStatus", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v465, 8, &v96, 11);
  v684 = 33;
  v685 = v465;
  std::wstring::wstring(v686, v466);
  v687 = v467;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v99, L"TcgSmmIsolationLevel", 20);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v462, 8, &v99, 4);
  v688 = 35;
  v689 = v462;
  std::wstring::wstring(v690, v463);
  v691 = v464;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v102, L"TcgDrtmEnabled", 14);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v459, 8, &v102, 4);
  v692 = 32;
  v693 = v459;
  std::wstring::wstring(v694, v460);
  v695 = v461;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v105, L"EkCertificatePresent", 20);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v456, 8, &v105, 4);
  v696 = 25;
  v697 = v456;
  std::wstring::wstring(v698, v457);
  v699 = v458;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v108, L"EccEkCertificatePresent", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v453, 8, &v108, 4);
  v700 = 26;
  v701 = v453;
  std::wstring::wstring(v702, v454);
  v703 = v455;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v111, L"MaintenanceTaskComplete", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v450, 8, &v111, 4);
  v704 = 36;
  v705 = v450;
  std::wstring::wstring(v706, v451);
  v707 = v452;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v114, L"OwnerAuthEndorsementPresent", 27);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v447, 8, &v114, 4);
  v708 = 37;
  v709 = v447;
  std::wstring::wstring(v710, v448);
  v711 = v449;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v117, L"PCR7BindingState", 16);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v444, 8, &v117, 4);
  v712 = 38;
  v713 = v444;
  std::wstring::wstring(v714, v445);
  v715 = v446;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v120, L"TpmProvisionFailedSteps", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v441, 8, &v120, 4);
  v716 = 39;
  v717 = v441;
  std::wstring::wstring(v718, v442);
  v719 = v443;
  v123 = 0;
  v124 = 0;
  v125 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v123, L"TpmProvisionHresult", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v438, 8, &v123, 4);
  v720 = 40;
  v721 = v438;
  std::wstring::wstring(v722, v439);
  v723 = v440;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v126, L"HASEndpoint", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v435, 7, &v126, 1);
  v724 = 41;
  v725 = v435;
  std::wstring::wstring(v726, v436);
  v727 = v437;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v129, L"EnrollmentID", 12);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v432, 7, &v129, 1);
  v728 = 42;
  v729 = v432;
  std::wstring::wstring(v730, v433);
  v731 = v434;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, L"SignedHealthCert", 16);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v429, 7, &v132, 3);
  v732 = 43;
  v733 = v429;
  std::wstring::wstring(v734, v430);
  v735 = v431;
  v135 = 0;
  v136 = 0;
  v137 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v135, L"Status", 6);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v426, 7, &v135, 4);
  v736 = 44;
  v737 = v426;
  std::wstring::wstring(v738, v427);
  v739 = v428;
  v138 = 0;
  v139 = 0;
  v140 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v138, L"IntermediateCertsInstalledFromNV", 32);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v423, 9, &v138, 4);
  v740 = 45;
  v741 = v423;
  std::wstring::wstring(v742, v424);
  v743 = v425;
  v141 = 0;
  v142 = 0;
  v143 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v141, L"IsActiveZeroExhaust", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v420, 4, &v141, 4);
  v744 = 46;
  v745 = v420;
  std::wstring::wstring(v746, v421);
  v747 = v422;
  v144 = 0;
  v145 = 0;
  v146 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v144, L"LastAuthLevel", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v417, 5, &v144, 4);
  v748 = 47;
  v749 = v417;
  std::wstring::wstring(v750, v418);
  v751 = v419;
  v147 = 0;
  v148 = 0;
  v149 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v147, L"LastEccEKCertStoreCount", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v414, 3, &v147, 4);
  v752 = 48;
  v753 = v414;
  std::wstring::wstring(v754, v415);
  v755 = v416;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v150, L"LastEkPub", 9);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v411, 3, &v150, 3);
  v756 = 49;
  v757 = v411;
  std::wstring::wstring(v758, v412);
  v759 = v413;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v153, L"LastPPIRequest", 14);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v408, 4, &v153, 4);
  v760 = 50;
  v761 = v408;
  std::wstring::wstring(v762, v409);
  v763 = v410;
  v156 = 0;
  v157 = 0;
  v158 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v156, L"LastPPIResponseHandled", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v405, 5, &v156, 4);
  v764 = 51;
  v765 = v405;
  std::wstring::wstring(v766, v406);
  v767 = v407;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v159, L"LastRsaEKCertStoreCount", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v402, 3, &v159, 4);
  v768 = 52;
  v769 = v402;
  std::wstring::wstring(v770, v403);
  v771 = v404;
  v162 = 0;
  v163 = 0;
  v164 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v162, L"LastRsaEkCertThumbprint", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v399, 3, &v162, 1);
  v772 = 53;
  v773 = v399;
  std::wstring::wstring(v774, v400);
  v775 = v401;
  v165 = 0;
  v166 = 0;
  v167 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v165, L"LastTPMProvisionedBootId", 24);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v396, 3, &v165, 4);
  v776 = 54;
  v777 = v396;
  std::wstring::wstring(v778, v397);
  v779 = v398;
  v168 = 0;
  v169 = 0;
  v170 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v168, L"LastTPMProvisionedTime", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v393, 3, &v168, 11);
  v780 = 55;
  v781 = v393;
  std::wstring::wstring(v782, v394);
  v783 = v395;
  v171 = 0;
  v172 = 0;
  v173 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v171, L"LockoutHash", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v390, 5, &v171, 1);
  v784 = 56;
  v785 = v390;
  std::wstring::wstring(v786, v391);
  v787 = v392;
  v174 = 0;
  v175 = 0;
  v176 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v174, L"NoAutoProvision", 15);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v387, 4, &v174, 4);
  v788 = 57;
  v789 = v387;
  std::wstring::wstring(v790, v388);
  v791 = v389;
  v177 = 0;
  v178 = 0;
  v179 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v177, L"NoOOBECheck", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v384, 4, &v177, 4);
  v792 = 58;
  v793 = v384;
  std::wstring::wstring(v794, v385);
  v795 = v386;
  v180 = 0;
  v181 = 0;
  v182 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v180, L"NoResourceVirtualizationOnNextReboot", 36);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v381, 5, &v180, 4);
  v796 = 59;
  v797 = v381;
  std::wstring::wstring(v798, v382);
  v799 = v383;
  v183 = 0;
  v184 = 0;
  v185 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v183, L"UseNullDerivedOwnerAuth", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v378, 4, &v183, 4);
  v800 = 60;
  v801 = v378;
  std::wstring::wstring(v802, v379);
  v803 = v380;
  v186 = 0;
  v187 = 0;
  v188 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v186, L"UseNullDerivedOwnerAuth", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v375, 0, &v186, 4);
  v804 = 61;
  v805 = v375;
  std::wstring::wstring(v806, v376);
  v807 = v377;
  v189 = 0;
  v190 = 0;
  v191 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v189, L"OsBootCount", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v372, 1, &v189, 4);
  v808 = 62;
  v809 = v372;
  std::wstring::wstring(v810, v373);
  v811 = v374;
  v192 = 0;
  v193 = 0;
  v194 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v192, L"OsResumeCount", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v369, 15, &v192, 4);
  v812 = 63;
  v813 = v369;
  std::wstring::wstring(v814, v370);
  v815 = v371;
  v195 = 0;
  v196 = 0;
  v197 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v195, L"OSManagedAuthLevel", 18);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v366, 0, &v195, 4);
  v816 = 64;
  v817 = v366;
  std::wstring::wstring(v818, v367);
  v819 = v368;
  v198 = 0;
  v199 = 0;
  v200 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v198, L"OverrideEkCertIndex", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v363, 6, &v198, 4);
  v820 = 65;
  v821 = v363;
  std::wstring::wstring(v822, v364);
  v823 = v365;
  v201 = 0;
  v202 = 0;
  v203 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v201, L"OwnerAuthFull", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v360, 5, &v201, 1);
  v824 = 66;
  v825 = v360;
  std::wstring::wstring(v826, v361);
  v827 = v362;
  v204 = 0;
  v205 = 0;
  v206 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v204, L"OwnerAuthNew", 12);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v357, 5, &v204, 1);
  v828 = 67;
  v829 = v357;
  std::wstring::wstring(v830, v358);
  v831 = v359;
  v207 = 0;
  v208 = 0;
  v209 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v207, L"OwnerAuthStatus", 15);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v354, 5, &v207, 4);
  v832 = 68;
  v833 = v354;
  std::wstring::wstring(v834, v355);
  v835 = v356;
  v210 = 0;
  v211 = 0;
  v212 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v210, L"PlatformLogRetention", 20);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v351, 1, &v210, 4);
  v836 = 69;
  v837 = v351;
  std::wstring::wstring(v838, v352);
  v839 = v353;
  v213 = 0;
  v214 = 0;
  v215 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v213, L"PreAttHCFileError", 17);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v348, 8, &v213, 4);
  v840 = 70;
  v841 = v348;
  std::wstring::wstring(v842, v349);
  v843 = v350;
  v216 = 0;
  v217 = 0;
  v218 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v216, L"RsaPssSaltLengthType", 20);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v345, 4, &v216, 4);
  v844 = 77;
  v845 = v345;
  std::wstring::wstring(v846, v346);
  v847 = v347;
  v219 = 0;
  v220 = 0;
  v221 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v219, L"SRKPub", 6);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v342, 5, &v219, 3);
  v848 = 78;
  v849 = v342;
  std::wstring::wstring(v850, v343);
  v851 = v344;
  v222 = 0;
  v223 = 0;
  v224 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v222, L"TaskFirmwareVersion", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v339, 4, &v222, 1);
  v852 = 71;
  v853 = v339;
  std::wstring::wstring(v854, v340);
  v855 = v341;
  v225 = 0;
  v226 = 0;
  v227 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v225, L"TaskInformationFlags", 20);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v336, 4, &v225, 4);
  v856 = 72;
  v857 = v336;
  std::wstring::wstring(v858, v337);
  v859 = v338;
  v228 = 0;
  v229 = 0;
  v230 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v228, L"TaskManufacturerId", 18);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v333, 4, &v228, 4);
  v860 = 73;
  v861 = v333;
  std::wstring::wstring(v862, v334);
  v863 = v335;
  v231 = 0;
  v232 = 0;
  v233 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v231, L"TaskOsBuildNumber", 17);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v330, 4, &v231, 1);
  v864 = 74;
  v865 = v330;
  std::wstring::wstring(v866, v331);
  v867 = v332;
  v234 = 0;
  v235 = 0;
  v236 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v234, L"TaskReadyForAttestation", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v327, 4, &v234, 4);
  v868 = 75;
  v869 = v327;
  std::wstring::wstring(v870, v328);
  v871 = v329;
  v237 = 0;
  v238 = 0;
  v239 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v237, L"TaskReadyForStorage", 19);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v324, 4, &v237, 4);
  v872 = 76;
  v873 = v324;
  std::wstring::wstring(v874, v325);
  v875 = v326;
  v240 = 0;
  v241 = 0;
  v242 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v240, L"StorageOwnerAuth", 16);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v321, 5, &v240, 1);
  v876 = 79;
  v877 = v321;
  std::wstring::wstring(v878, v322);
  v879 = v323;
  v243 = 0;
  v244 = 0;
  v245 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v243, L"TotalTPMProvisioningCount", 25);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v318, 3, &v243, 4);
  v880 = 80;
  v881 = v318;
  std::wstring::wstring(v882, v319);
  v883 = v320;
  v246 = 0;
  v247 = 0;
  v248 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v246, L"TpmBackedDeviceID", 17);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v315, 4, &v246, 4);
  v884 = 81;
  v885 = v315;
  std::wstring::wstring(v886, v316);
  v887 = v317;
  v249 = 0;
  v250 = 0;
  v251 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v249, L"TPMCleared", 10);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v312, 5, &v249, 4);
  v888 = 82;
  v889 = v312;
  std::wstring::wstring(v890, v313);
  v891 = v314;
  v252 = 0;
  v253 = 0;
  v254 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v252, L"UseLegacyDictionaryAttackParameters", 35);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v309, 0, &v252, 4);
  v892 = 83;
  v893 = v309;
  std::wstring::wstring(v894, v310);
  v895 = v311;
  v255 = 0;
  v256 = 0;
  v257 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v255, L"WBCLPath", 8);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v306, 1, &v255, 1);
  v896 = 84;
  v897 = v306;
  std::wstring::wstring(v898, v307);
  v899 = v308;
  v258 = 0;
  v259 = 0;
  v260 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v258, L"Windows AIK", 11);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v303, 2, &v258, 3);
  v900 = 85;
  v901 = v303;
  std::wstring::wstring(v902, v304);
  v903 = v305;
  v261 = 0;
  v262 = 0;
  v263 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v261, L"WindowsAIKBinding", 17);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v300, 4, &v261, 3);
  v904 = 86;
  v905 = v300;
  std::wstring::wstring(v906, v301);
  v907 = v302;
  v264 = 0;
  v265 = 0;
  v266 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v264, L"WindowsAikCheckCreateResult", 27);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v297, 9, &v264, 4);
  v908 = 87;
  v909 = v297;
  std::wstring::wstring(v910, v298);
  v911 = v299;
  v267 = 0;
  v268 = 0;
  v269 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v267, L"WindowsAikCorrelationId", 23);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v294, 9, &v267, 1);
  v912 = 88;
  v913 = v294;
  std::wstring::wstring(v914, v295);
  v915 = v296;
  v270 = 0;
  v271 = 0;
  v272 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v270, L"WindowsAikEnrollReason", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v291, 9, &v270, 4);
  v916 = 89;
  v917 = v291;
  std::wstring::wstring(v918, v292);
  v919 = v293;
  v273 = 0;
  v274 = 0;
  v275 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v273, L"WindowsAikEnrollResult", 22);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v288, 9, &v273, 4);
  v920 = 90;
  v921 = v288;
  std::wstring::wstring(v922, v289);
  v923 = v290;
  v276 = 0;
  v277 = 0;
  v278 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v276, L"WindowsAIKHash", 14);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v285, 4, &v276, 3);
  v924 = 91;
  v925 = v285;
  std::wstring::wstring(v926, v286);
  v927 = v287;
  v279 = 0;
  v280 = 0;
  v281 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v279, L"WindowsAIKPub", 13);
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(&v282, 4, &v279, 3);
  v928 = 92;
  v929 = v282;
  std::wstring::wstring(v930, v283);
  v931 = v284;
  v2[0] = (__int64)v561;
  v2[1] = (__int64)&v932;
  std::map<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry>::map<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry>(
    v0,
    v2);
  `eh vector destructor iterator'(v561, 0x38u, 0x5Du, std::_Ref_count_obj2<std::wstring>::_Destroy);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v283);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v286);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v289);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v292);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v295);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v298);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v301);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v304);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v307);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v310);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v313);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v316);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v319);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v322);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v325);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v328);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v331);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v334);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v337);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v340);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v343);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v346);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v349);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v352);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v355);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v358);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v361);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v364);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v367);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v370);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v373);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v376);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v379);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v382);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v385);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v388);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v391);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v394);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v397);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v400);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v403);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v406);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v409);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v412);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v415);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v418);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v421);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v424);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v427);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v430);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v433);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v436);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v439);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v442);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v445);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v448);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v451);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v454);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v457);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v460);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v463);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v466);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v469);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v472);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v475);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v478);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v481);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v484);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v487);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v490);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v493);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v496);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v499);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v502);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v505);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v508);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v511);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v514);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v517);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v520);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v523);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v526);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v529);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v532);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v535);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v538);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v541);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v544);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v547);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v550);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v553);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v556);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v559);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegValueTable__);
}

```

## disassembly

```asm
0x180007340  push    rbp
0x180007342  push    rbx
0x180007343  push    rsi
0x180007344  push    rdi
0x180007345  push    r12
0x180007347  push    r13
0x180007349  push    r14
0x18000734b  push    r15
0x18000734d  lea     rbp, [rsp-30B8h]
0x180007355  mov     eax, 31B8h
0x18000735a  call    _alloca_probe
0x18000735f  sub     rsp, rax
0x180007362  mov     rax, cs:__security_cookie
0x180007369  xor     rax, rsp
0x18000736c  mov     [rbp+30F0h+var_50], rax
0x180007373  xorps   xmm0, xmm0
0x180007376  movups  [rsp+31F0h+var_31C0], xmm0
0x18000737b  xor     r15d, r15d
0x18000737e  mov     [rsp+31F0h+var_31B0], r15
0x180007383  mov     [rsp+31F0h+var_31A8], r15
0x180007388  lea     r8d, [r15+1Bh]
0x18000738c  lea     rdx, aActivedirector; "ActiveDirectoryBackupSrkPub"
0x180007393  lea     rcx, [rsp+31F0h+var_31C0]
0x180007398  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000739d  lea     r14d, [r15+3]
0x1800073a1  mov     r9d, r14d
0x1800073a4  lea     r8, [rsp+31F0h+var_31C0]
0x1800073a9  lea     edx, [r15+5]
0x1800073ad  lea     rcx, [rbp+30F0h+var_14E0]
0x1800073b4  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x1800073b9  nop
0x1800073ba  mov     [rbp+30F0h+var_14B0], r15d
0x1800073c1  mov     eax, [rbp+30F0h+var_14E0]
0x1800073c7  mov     [rbp+30F0h+var_14A8], eax
0x1800073cd  lea     rdx, [rbp+30F0h+var_14D8]
0x1800073d4  lea     rcx, [rbp+30F0h+var_14A0]
0x1800073db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800073e0  mov     eax, [rbp+30F0h+var_14B8]
0x1800073e6  mov     [rbp+30F0h+var_1480], eax
0x1800073ec  xorps   xmm0, xmm0
0x1800073ef  movups  [rsp+31F0h+var_31A0], xmm0
0x1800073f4  mov     [rsp+31F0h+var_3190], r15
0x1800073f9  mov     [rsp+31F0h+var_3188], r15
0x1800073fe  lea     ebx, [r15+16h]
0x180007402  mov     r8d, ebx
0x180007405  lea     rdx, aAikcertacquire; "AIKCertAcquiredExpired"
0x18000740c  lea     rcx, [rsp+31F0h+var_31A0]
0x180007411  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007416  lea     esi, [rbx-12h]
0x180007419  mov     r9d, esi
0x18000741c  lea     r8, [rsp+31F0h+var_31A0]
0x180007421  mov     edx, esi
0x180007423  lea     rcx, [rbp+30F0h+var_1510]
0x18000742a  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000742f  nop
0x180007430  lea     edi, [rbx-15h]
0x180007433  mov     [rbp+30F0h+var_1478], edi
0x180007439  mov     eax, [rbp+30F0h+var_1510]
0x18000743f  mov     [rbp+30F0h+var_1470], eax
0x180007445  lea     rdx, [rbp+30F0h+var_1508]
0x18000744c  lea     rcx, [rbp+30F0h+var_1468]
0x180007453  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007458  mov     eax, [rbp+30F0h+var_14E8]
0x18000745e  mov     [rbp+30F0h+var_1448], eax
0x180007464  xorps   xmm0, xmm0
0x180007467  movups  [rsp+31F0h+var_3180], xmm0
0x18000746c  mov     [rbp+30F0h+var_3170], r15
0x180007470  mov     [rbp+30F0h+var_3168], r15
0x180007474  mov     r8d, ebx
0x180007477  lea     rdx, aAikenrollmente; "AIKEnrollmentErrorCode"
0x18000747e  lea     rcx, [rsp+31F0h+var_3180]
0x180007483  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007488  mov     r9d, esi
0x18000748b  lea     r8, [rsp+31F0h+var_3180]
0x180007490  mov     edx, esi
0x180007492  lea     rcx, [rbp+30F0h+var_1540]
0x180007499  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000749e  nop
0x18000749f  mov     [rbp+30F0h+var_1440], 2
0x1800074a9  mov     eax, [rbp+30F0h+var_1540]
0x1800074af  mov     [rbp+30F0h+var_1438], eax
0x1800074b5  lea     rdx, [rbp+30F0h+var_1538]
0x1800074bc  lea     rcx, [rbp+30F0h+var_1430]
0x1800074c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800074c8  mov     eax, [rbp+30F0h+var_1518]
0x1800074ce  mov     [rbp+30F0h+var_1410], eax
0x1800074d4  xorps   xmm0, xmm0
0x1800074d7  movups  [rbp+30F0h+var_3160], xmm0
0x1800074db  mov     [rbp+30F0h+var_3150], r15
0x1800074df  mov     [rbp+30F0h+var_3148], r15
0x1800074e3  lea     ebx, [rsi+7]
0x1800074e6  mov     r8d, ebx
0x1800074e9  lea     rdx, aClearreason; "ClearReason"
0x1800074f0  lea     rcx, [rbp+30F0h+var_3160]
0x1800074f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800074f9  mov     r9d, edi
0x1800074fc  lea     r8, [rbp+30F0h+var_3160]
0x180007500  mov     edx, r14d
0x180007503  lea     rcx, [rbp+30F0h+var_1570]
0x18000750a  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000750f  nop
0x180007510  mov     [rbp+30F0h+var_1408], r14d
0x180007517  mov     eax, [rbp+30F0h+var_1570]
0x18000751d  mov     [rbp+30F0h+var_1400], eax
0x180007523  lea     rdx, [rbp+30F0h+var_1568]
0x18000752a  lea     rcx, [rbp+30F0h+var_13F8]
0x180007531  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007536  mov     eax, [rbp+30F0h+var_1548]
0x18000753c  mov     [rbp+30F0h+var_13D8], eax
0x180007542  xorps   xmm0, xmm0
0x180007545  movups  [rbp+30F0h+var_3140], xmm0
0x180007549  mov     [rbp+30F0h+var_3130], r15
0x18000754d  mov     [rbp+30F0h+var_3128], r15
0x180007551  lea     r13d, [r15+13h]
0x180007555  mov     r8d, r13d
0x180007558  lea     rdx, aEkcertcorrelat; "EkCertCorrelationId"
0x18000755f  lea     rcx, [rbp+30F0h+var_3140]
0x180007563  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007568  mov     r9d, edi
0x18000756b  lea     r8, [rbp+30F0h+var_3140]
0x18000756f  lea     edi, [rsi+5]
0x180007572  mov     edx, edi
0x180007574  lea     rcx, [rbp+30F0h+var_15A0]
0x18000757b  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x180007580  nop
0x180007581  mov     [rbp+30F0h+var_13D0], 0Ch
0x18000758b  mov     eax, [rbp+30F0h+var_15A0]
0x180007591  mov     [rbp+30F0h+var_13C8], eax
0x180007597  lea     rdx, [rbp+30F0h+var_1598]
0x18000759e  lea     rcx, [rbp+30F0h+var_13C0]
0x1800075a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800075aa  mov     eax, [rbp+30F0h+var_1578]
0x1800075b0  mov     [rbp+30F0h+var_13A0], eax
0x1800075b6  xorps   xmm0, xmm0
0x1800075b9  movups  [rbp+30F0h+var_3120], xmm0
0x1800075bd  mov     [rbp+30F0h+var_3110], r15
0x1800075c1  mov     [rbp+30F0h+var_3108], r15
0x1800075c5  mov     r8d, r13d
0x1800075c8  lea     rdx, aEkcertnvfailur; "EkCertNvFailureStep"
0x1800075cf  lea     rcx, [rbp+30F0h+var_3120]
0x1800075d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800075d8  mov     r9d, esi
0x1800075db  lea     r8, [rbp+30F0h+var_3120]
0x1800075df  mov     edx, edi
0x1800075e1  lea     rcx, [rbp+30F0h+var_15D0]
0x1800075e8  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x1800075ed  nop
0x1800075ee  mov     [rbp+30F0h+var_1398], 0Dh
0x1800075f8  mov     eax, [rbp+30F0h+var_15D0]
0x1800075fe  mov     [rbp+30F0h+var_1390], eax
0x180007604  lea     rdx, [rbp+30F0h+var_15C8]
0x18000760b  lea     rcx, [rbp+30F0h+var_1388]
0x180007612  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007617  mov     eax, [rbp+30F0h+var_15A8]
0x18000761d  mov     [rbp+30F0h+var_1368], eax
0x180007623  xorps   xmm0, xmm0
0x180007626  movups  [rbp+30F0h+var_3100], xmm0
0x18000762a  mov     [rbp+30F0h+var_30F0], r15
0x18000762e  mov     [rbp+30F0h+var_30E8], r15
0x180007632  lea     r12d, [r15+12h]
0x180007636  mov     r8d, r12d
0x180007639  lea     rdx, aEkcertfetchsup; "EkCertFetchSupport"
0x180007640  lea     rcx, [rbp+30F0h+var_3100]
0x180007644  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007649  mov     r9d, esi
0x18000764c  lea     r8, [rbp+30F0h+var_3100]
0x180007650  mov     edx, edi
0x180007652  lea     rcx, [rbp+30F0h+var_1600]
0x180007659  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000765e  nop
0x18000765f  mov     [rbp+30F0h+var_1360], 0Eh
0x180007669  mov     eax, [rbp+30F0h+var_1600]
0x18000766f  mov     [rbp+30F0h+var_1358], eax
0x180007675  lea     rdx, [rbp+30F0h+var_15F8]
0x18000767c  lea     rcx, [rbp+30F0h+var_1350]
0x180007683  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007688  mov     eax, [rbp+30F0h+var_15D8]
0x18000768e  mov     [rbp+30F0h+var_1330], eax
0x180007694  xorps   xmm0, xmm0
0x180007697  movups  [rbp+30F0h+var_30E0], xmm0
0x18000769b  mov     [rbp+30F0h+var_30D0], r15
0x18000769f  mov     [rbp+30F0h+var_30C8], r15
0x1800076a3  mov     r8d, ebx
0x1800076a6  lea     rdx, aEkcertindex; "EkCertIndex"
0x1800076ad  lea     rcx, [rbp+30F0h+var_30E0]
0x1800076b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800076b6  mov     r9d, esi
0x1800076b9  lea     r8, [rbp+30F0h+var_30E0]
0x1800076bd  mov     edx, edi
0x1800076bf  lea     rcx, [rbp+30F0h+var_1630]
0x1800076c6  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x1800076cb  nop
0x1800076cc  lea     r15d, [r14+0Ch]
0x1800076d0  mov     [rbp+30F0h+var_1328], r15d
0x1800076d7  mov     eax, [rbp+30F0h+var_1630]
0x1800076dd  mov     [rbp+30F0h+var_1320], eax
0x1800076e3  lea     rdx, [rbp+30F0h+var_1628]
0x1800076ea  lea     rcx, [rbp+30F0h+var_1318]
0x1800076f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800076f6  mov     eax, [rbp+30F0h+var_1608]
0x1800076fc  mov     [rbp+30F0h+var_12F8], eax
0x180007702  xorps   xmm0, xmm0
0x180007705  movups  [rbp+30F0h+var_30C0], xmm0
0x180007709  xor     ebx, ebx
0x18000770b  mov     [rbp+30F0h+var_30B0], rbx
0x18000770f  mov     [rbp+30F0h+var_30A8], rbx
0x180007713  lea     r8d, [r14+7]
0x180007717  lea     rdx, aEkcertpath; "EkCertPath"
0x18000771e  lea     rcx, [rbp+30F0h+var_30C0]
0x180007722  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007727  mov     r9d, esi
0x18000772a  lea     r8, [rbp+30F0h+var_30C0]
0x18000772e  mov     edx, edi
0x180007730  lea     rcx, [rbp+30F0h+var_1660]
0x180007737  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000773c  nop
0x18000773d  lea     r14d, [rsi+0Ch]
0x180007741  mov     [rbp+30F0h+var_12F0], r14d
0x180007748  mov     eax, [rbp+30F0h+var_1660]
0x18000774e  mov     [rbp+30F0h+var_12E8], eax
0x180007754  lea     rdx, [rbp+30F0h+var_1658]
0x18000775b  lea     rcx, [rbp+30F0h+var_12E0]
0x180007762  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007767  mov     eax, [rbp+30F0h+var_1638]
0x18000776d  mov     [rbp+30F0h+var_12C0], eax
0x180007773  xorps   xmm0, xmm0
0x180007776  movups  [rbp+30F0h+var_30A0], xmm0
0x18000777a  mov     [rbp+30F0h+var_3090], rbx
0x18000777e  mov     [rbp+30F0h+var_3088], rbx
0x180007782  lea     ebx, [rsi+11h]
0x180007785  mov     r8d, ebx
0x180007788  lea     rdx, aEkcertprovisio; "EkCertProvisionResult"
0x18000778f  lea     rcx, [rbp+30F0h+var_30A0]
0x180007793  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007798  mov     r9d, esi
0x18000779b  lea     r8, [rbp+30F0h+var_30A0]
0x18000779f  mov     edx, edi
0x1800077a1  lea     rcx, [rbp+30F0h+var_1690]
0x1800077a8  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x1800077ad  nop
0x1800077ae  mov     [rbp+30F0h+var_12B8], 11h
0x1800077b8  mov     eax, [rbp+30F0h+var_1690]
0x1800077be  mov     [rbp+30F0h+var_12B0], eax
0x1800077c4  lea     rdx, [rbp+30F0h+var_1688]
0x1800077cb  lea     rcx, [rbp+30F0h+var_12A8]
0x1800077d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800077d7  mov     eax, [rbp+30F0h+var_1668]
0x1800077dd  mov     [rbp+30F0h+var_1288], eax
0x1800077e3  xorps   xmm0, xmm0
0x1800077e6  movups  [rbp+30F0h+var_3080], xmm0
0x1800077ea  mov     [rbp+30F0h+var_3070], 0
0x1800077f5  mov     [rbp+30F0h+var_3068], 0
0x180007800  lea     esi, [rdi+16h]
0x180007803  mov     r8d, esi
0x180007806  lea     rdx, aEkcertreschedu; "EkCertRescheduleTaskFailureStep"
0x18000780d  lea     rcx, [rbp+30F0h+var_3080]
0x180007811  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007816  lea     r9d, [r13-0Fh]
0x18000781a  lea     r8, [rbp+30F0h+var_3080]
0x18000781e  mov     edx, edi
0x180007820  lea     rcx, [rbp+30F0h+var_16C0]
0x180007827  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000782c  nop
0x18000782d  mov     [rbp+30F0h+var_1280], r12d
0x180007834  mov     eax, [rbp+30F0h+var_16C0]
0x18000783a  mov     [rbp+30F0h+var_1278], eax
0x180007840  lea     rdx, [rbp+30F0h+var_16B8]
0x180007847  lea     rcx, [rbp+30F0h+var_1270]
0x18000784e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180007853  mov     eax, [rbp+30F0h+var_1698]
0x180007859  mov     [rbp+30F0h+var_1250], eax
0x18000785f  xorps   xmm0, xmm0
0x180007862  movups  [rbp+30F0h+var_3060], xmm0
0x180007869  mov     [rbp+30F0h+var_3050], 0
0x180007874  mov     [rbp+30F0h+var_3048], 0
0x18000787f  lea     edi, [rbx+8]
0x180007882  mov     r8d, edi
0x180007885  lea     rdx, aEkcertretrieve; "EkCertRetrieveCertFailureStep"
0x18000788c  lea     rcx, [rbp+30F0h+var_3060]
0x180007893  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007898  lea     r9d, [r13-0Fh]
0x18000789c  lea     r8, [rbp+30F0h+var_3060]
0x1800078a3  lea     edx, [rbx-0Ch]
0x1800078a6  lea     rcx, [rbp+30F0h+var_16F0]
0x1800078ad  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x1800078b2  nop
0x1800078b3  mov     [rbp+30F0h+var_1248], r13d
0x1800078ba  mov     eax, [rbp+30F0h+var_16F0]
0x1800078c0  mov     [rbp+30F0h+var_1240], eax
0x1800078c6  lea     rdx, [rbp+30F0h+var_16E8]
0x1800078cd  lea     rcx, [rbp+30F0h+var_1238]
0x1800078d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800078d9  mov     eax, [rbp+30F0h+var_16C8]
0x1800078df  mov     [rbp+30F0h+var_1218], eax
0x1800078e5  xorps   xmm0, xmm0
0x1800078e8  movups  [rbp+30F0h+var_3040], xmm0
0x1800078ef  xor     r13d, r13d
0x1800078f2  mov     [rbp+30F0h+var_3030], r13
0x1800078f9  mov     [rbp+30F0h+var_3028], r13
0x180007900  mov     r8d, r14d
  ... truncated ...
```
