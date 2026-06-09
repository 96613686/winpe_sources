# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x180004ab0`
- end: `0x18000619b`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `5867`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004ab0`
- `0x180006800`
- `0x180006ec4`
- `0x180006fe0`
- `0x18000a8e0`
- `0x180025e14`
- `0x18002c640`
- `0x18002c664`
- `0x18002cac0`
- `0x18005fbb4`
- `0x180079400`

## string_xrefs

- `0x180004c81`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180005404`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x18000566e`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x1800058d1`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180004ee8`: `System\CurrentControlSet\Services\TPM`
- `0x180005169`: `System\CurrentControlSet\Services\TPM`
- `0x18000553d`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x18000563f`: `TaskStates`
- `0x180005d94`: `System\CurrentControlSet\Control\IntegrityServices`
- `0x180004db1`: `System\CurrentControlSet\Services`
- `0x180005a05`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x1800057a0`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__()
{
  __int64 v0; // rbx
  __int64 v1; // r8
  __int64 v2; // r8
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 *v8; // rbx
  int v10; // [rsp+60h] [rbp-A0h] BYREF
  int v11; // [rsp+64h] [rbp-9Ch] BYREF
  int v12; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+6Ch] [rbp-94h] BYREF
  int v14; // [rsp+70h] [rbp-90h] BYREF
  int v15; // [rsp+74h] [rbp-8Ch] BYREF
  int v16; // [rsp+78h] [rbp-88h] BYREF
  int v17; // [rsp+7Ch] [rbp-84h] BYREF
  int v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+84h] [rbp-7Ch] BYREF
  int v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+8Ch] [rbp-74h] BYREF
  int v22; // [rsp+90h] [rbp-70h] BYREF
  int v23; // [rsp+94h] [rbp-6Ch] BYREF
  int v24; // [rsp+98h] [rbp-68h] BYREF
  int v25; // [rsp+9Ch] [rbp-64h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-50h]
  __int64 v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  __int128 v32; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-10h]
  __int64 v34; // [rsp+F8h] [rbp-8h]
  __int128 v35; // [rsp+100h] [rbp+0h] BYREF
  __int64 v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  __int128 v38; // [rsp+120h] [rbp+20h] BYREF
  __int64 v39; // [rsp+130h] [rbp+30h]
  __int64 v40; // [rsp+138h] [rbp+38h]
  __int128 v41; // [rsp+140h] [rbp+40h] BYREF
  __int64 v42; // [rsp+150h] [rbp+50h]
  __int64 v43; // [rsp+158h] [rbp+58h]
  __int128 v44; // [rsp+160h] [rbp+60h] BYREF
  __int64 v45; // [rsp+170h] [rbp+70h]
  __int64 v46; // [rsp+178h] [rbp+78h]
  __int128 v47; // [rsp+180h] [rbp+80h] BYREF
  __int64 v48; // [rsp+190h] [rbp+90h]
  __int64 v49; // [rsp+198h] [rbp+98h]
  __int128 v50; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v51; // [rsp+1B0h] [rbp+B0h]
  __int64 v52; // [rsp+1B8h] [rbp+B8h]
  __int128 v53; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v54; // [rsp+1D0h] [rbp+D0h]
  __int64 v55; // [rsp+1D8h] [rbp+D8h]
  __int128 v56; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v57; // [rsp+1F0h] [rbp+F0h]
  __int64 v58; // [rsp+1F8h] [rbp+F8h]
  __int128 v59; // [rsp+200h] [rbp+100h] BYREF
  __int64 v60; // [rsp+210h] [rbp+110h]
  __int64 v61; // [rsp+218h] [rbp+118h]
  __int128 v62; // [rsp+220h] [rbp+120h] BYREF
  __int64 v63; // [rsp+230h] [rbp+130h]
  __int64 v64; // [rsp+238h] [rbp+138h]
  __int128 v65; // [rsp+240h] [rbp+140h] BYREF
  __int64 v66; // [rsp+250h] [rbp+150h]
  __int64 v67; // [rsp+258h] [rbp+158h]
  __int128 v68; // [rsp+260h] [rbp+160h] BYREF
  __int64 v69; // [rsp+270h] [rbp+170h]
  __int64 v70; // [rsp+278h] [rbp+178h]
  __int128 v71; // [rsp+280h] [rbp+180h] BYREF
  __int64 v72; // [rsp+290h] [rbp+190h]
  __int64 v73; // [rsp+298h] [rbp+198h]
  __int128 v74; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v75; // [rsp+2B0h] [rbp+1B0h]
  __int64 v76; // [rsp+2B8h] [rbp+1B8h]
  __int128 v77; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v78; // [rsp+2D0h] [rbp+1D0h]
  __int64 v79; // [rsp+2D8h] [rbp+1D8h]
  __int128 v80; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v81; // [rsp+2F0h] [rbp+1F0h]
  __int64 v82; // [rsp+2F8h] [rbp+1F8h]
  __int128 v83; // [rsp+300h] [rbp+200h] BYREF
  __int64 v84; // [rsp+310h] [rbp+210h]
  __int64 v85; // [rsp+318h] [rbp+218h]
  __int128 v86; // [rsp+320h] [rbp+220h] BYREF
  __int64 v87; // [rsp+330h] [rbp+230h]
  __int64 v88; // [rsp+338h] [rbp+238h]
  __int128 v89; // [rsp+340h] [rbp+240h] BYREF
  __int64 v90; // [rsp+350h] [rbp+250h]
  __int64 v91; // [rsp+358h] [rbp+258h]
  __int128 v92; // [rsp+360h] [rbp+260h] BYREF
  __int64 v93; // [rsp+370h] [rbp+270h]
  __int64 v94; // [rsp+378h] [rbp+278h]
  __int128 v95; // [rsp+380h] [rbp+280h] BYREF
  __int64 v96; // [rsp+390h] [rbp+290h]
  __int64 v97; // [rsp+398h] [rbp+298h]
  __int128 v98; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v99; // [rsp+3B0h] [rbp+2B0h]
  __int64 v100; // [rsp+3B8h] [rbp+2B8h]
  __int128 v101; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v102; // [rsp+3D0h] [rbp+2D0h]
  __int64 v103; // [rsp+3D8h] [rbp+2D8h]
  __int128 v104; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int64 v105; // [rsp+3F0h] [rbp+2F0h]
  __int64 v106; // [rsp+3F8h] [rbp+2F8h]
  __int128 v107; // [rsp+400h] [rbp+300h] BYREF
  __int64 v108; // [rsp+410h] [rbp+310h]
  __int64 v109; // [rsp+418h] [rbp+318h]
  __int128 v110; // [rsp+420h] [rbp+320h] BYREF
  __int64 v111; // [rsp+430h] [rbp+330h]
  __int64 v112; // [rsp+438h] [rbp+338h]
  __int128 v113; // [rsp+440h] [rbp+340h] BYREF
  __int64 v114; // [rsp+450h] [rbp+350h]
  __int64 v115; // [rsp+458h] [rbp+358h]
  __int128 v116; // [rsp+460h] [rbp+360h] BYREF
  __int64 v117; // [rsp+470h] [rbp+370h]
  __int64 v118; // [rsp+478h] [rbp+378h]
  __int128 v119; // [rsp+480h] [rbp+380h] BYREF
  __int64 v120; // [rsp+490h] [rbp+390h]
  __int64 v121; // [rsp+498h] [rbp+398h]
  __int128 v122; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v123; // [rsp+4B0h] [rbp+3B0h]
  __int64 v124; // [rsp+4B8h] [rbp+3B8h]
  __int128 v125; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v126; // [rsp+4D0h] [rbp+3D0h]
  __int64 v127; // [rsp+4D8h] [rbp+3D8h]
  __int128 v128; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v129; // [rsp+4F0h] [rbp+3F0h]
  __int64 v130; // [rsp+4F8h] [rbp+3F8h]
  __int128 v131; // [rsp+500h] [rbp+400h] BYREF
  __int64 v132; // [rsp+510h] [rbp+410h]
  __int64 v133; // [rsp+518h] [rbp+418h]
  __int128 v134; // [rsp+520h] [rbp+420h] BYREF
  __int64 v135; // [rsp+530h] [rbp+430h]
  __int64 v136; // [rsp+538h] [rbp+438h]
  __int128 v137; // [rsp+540h] [rbp+440h] BYREF
  __int64 v138; // [rsp+550h] [rbp+450h]
  __int64 v139; // [rsp+558h] [rbp+458h]
  __int128 v140; // [rsp+560h] [rbp+460h] BYREF
  __int64 v141; // [rsp+570h] [rbp+470h]
  __int64 v142; // [rsp+578h] [rbp+478h]
  __int128 v143; // [rsp+580h] [rbp+480h] BYREF
  __int64 v144; // [rsp+590h] [rbp+490h]
  __int64 v145; // [rsp+598h] [rbp+498h]
  __int128 v146; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v147; // [rsp+5B0h] [rbp+4B0h]
  __int64 v148; // [rsp+5B8h] [rbp+4B8h]
  __int128 v149; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int64 v150; // [rsp+5D0h] [rbp+4D0h]
  __int64 v151; // [rsp+5D8h] [rbp+4D8h]
  __int128 v152; // [rsp+5E0h] [rbp+4E0h] BYREF
  __int64 v153; // [rsp+5F0h] [rbp+4F0h]
  __int64 v154; // [rsp+5F8h] [rbp+4F8h]
  __int128 v155; // [rsp+600h] [rbp+500h] BYREF
  __int64 v156; // [rsp+610h] [rbp+510h]
  __int64 v157; // [rsp+618h] [rbp+518h]
  __int128 v158; // [rsp+620h] [rbp+520h] BYREF
  __int64 v159; // [rsp+630h] [rbp+530h]
  __int64 v160; // [rsp+638h] [rbp+538h]
  __int128 v161; // [rsp+640h] [rbp+540h] BYREF
  __int64 v162; // [rsp+650h] [rbp+550h]
  __int64 v163; // [rsp+658h] [rbp+558h]
  __int128 v164; // [rsp+660h] [rbp+560h] BYREF
  __int64 v165; // [rsp+670h] [rbp+570h]
  __int64 v166; // [rsp+678h] [rbp+578h]
  __int128 v167; // [rsp+680h] [rbp+580h] BYREF
  __int64 v168; // [rsp+690h] [rbp+590h]
  __int64 v169; // [rsp+698h] [rbp+598h]
  __int128 v170; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int64 v171; // [rsp+6B0h] [rbp+5B0h]
  __int64 v172; // [rsp+6B8h] [rbp+5B8h]
  __int128 v173; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int64 v174; // [rsp+6D0h] [rbp+5D0h]
  __int64 v175; // [rsp+6D8h] [rbp+5D8h]
  __int128 v176; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int64 v177; // [rsp+6F0h] [rbp+5F0h]
  __int64 v178; // [rsp+6F8h] [rbp+5F8h]
  __int128 v179; // [rsp+700h] [rbp+600h] BYREF
  __int64 v180; // [rsp+710h] [rbp+610h]
  __int64 v181; // [rsp+718h] [rbp+618h]
  __int128 v182; // [rsp+720h] [rbp+620h] BYREF
  __int64 v183; // [rsp+730h] [rbp+630h]
  __int64 v184; // [rsp+738h] [rbp+638h]
  __int128 v185; // [rsp+740h] [rbp+640h] BYREF
  __int64 v186; // [rsp+750h] [rbp+650h]
  __int64 v187; // [rsp+758h] [rbp+658h]
  __int128 v188; // [rsp+760h] [rbp+660h] BYREF
  __int64 v189; // [rsp+770h] [rbp+670h]
  __int64 v190; // [rsp+778h] [rbp+678h]
  __int128 v191; // [rsp+780h] [rbp+680h] BYREF
  __int64 v192; // [rsp+790h] [rbp+690h]
  __int64 v193; // [rsp+798h] [rbp+698h]
  __int128 v194; // [rsp+7A0h] [rbp+6A0h] BYREF
  __int64 v195; // [rsp+7B0h] [rbp+6B0h]
  __int64 v196; // [rsp+7B8h] [rbp+6B8h]
  __int128 v197; // [rsp+7C0h] [rbp+6C0h] BYREF
  __int64 v198; // [rsp+7D0h] [rbp+6D0h]
  __int64 v199; // [rsp+7D8h] [rbp+6D8h]
  __int128 v200; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int64 v201; // [rsp+7F0h] [rbp+6F0h]
  __int64 v202; // [rsp+7F8h] [rbp+6F8h]
  __int128 v203; // [rsp+800h] [rbp+700h] BYREF
  __int64 v204; // [rsp+810h] [rbp+710h]
  __int64 v205; // [rsp+818h] [rbp+718h]
  __int128 v206; // [rsp+820h] [rbp+720h] BYREF
  __int64 v207; // [rsp+830h] [rbp+730h]
  __int64 v208; // [rsp+838h] [rbp+738h]
  __int128 v209; // [rsp+840h] [rbp+740h] BYREF
  __int64 v210; // [rsp+850h] [rbp+750h]
  __int64 v211; // [rsp+858h] [rbp+758h]
  __int128 v212; // [rsp+860h] [rbp+760h] BYREF
  __int64 v213; // [rsp+870h] [rbp+770h]
  __int64 v214; // [rsp+878h] [rbp+778h]
  __int128 v215; // [rsp+880h] [rbp+780h] BYREF
  __int64 v216; // [rsp+890h] [rbp+790h]
  __int64 v217; // [rsp+898h] [rbp+798h]
  __int64 v218[4]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v219[32]; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v220[40]; // [rsp+8E0h] [rbp+7E0h] BYREF
  _BYTE v221[40]; // [rsp+908h] [rbp+808h] BYREF
  __int64 v222[4]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v223[32]; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v224[40]; // [rsp+970h] [rbp+870h] BYREF
  _BYTE v225[40]; // [rsp+998h] [rbp+898h] BYREF
  __int64 v226[4]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v227[32]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v228[40]; // [rsp+A00h] [rbp+900h] BYREF
  _BYTE v229[40]; // [rsp+A28h] [rbp+928h] BYREF
  __int64 v230[4]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v231[32]; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v232[40]; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v233[40]; // [rsp+AB8h] [rbp+9B8h] BYREF
  __int64 v234[4]; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v235[32]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v236[40]; // [rsp+B20h] [rbp+A20h] BYREF
  _BYTE v237[40]; // [rsp+B48h] [rbp+A48h] BYREF
  __int64 v238[4]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v239[32]; // [rsp+B90h] [rbp+A90h] BYREF
  _BYTE v240[40]; // [rsp+BB0h] [rbp+AB0h] BYREF
  _BYTE v241[40]; // [rsp+BD8h] [rbp+AD8h] BYREF
  __int64 v242[4]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v243[32]; // [rsp+C20h] [rbp+B20h] BYREF
  _BYTE v244[40]; // [rsp+C40h] [rbp+B40h] BYREF
  _BYTE v245[40]; // [rsp+C68h] [rbp+B68h] BYREF
  __int64 v246[4]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v247[32]; // [rsp+CB0h] [rbp+BB0h] BYREF
  _BYTE v248[40]; // [rsp+CD0h] [rbp+BD0h] BYREF
  _BYTE v249[40]; // [rsp+CF8h] [rbp+BF8h] BYREF
  __int64 v250[4]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v251[32]; // [rsp+D40h] [rbp+C40h] BYREF
  _BYTE v252[40]; // [rsp+D60h] [rbp+C60h] BYREF
  _BYTE v253[40]; // [rsp+D88h] [rbp+C88h] BYREF
  __int64 v254[4]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v255[32]; // [rsp+DD0h] [rbp+CD0h] BYREF
  _BYTE v256[40]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _BYTE v257[40]; // [rsp+E18h] [rbp+D18h] BYREF
  __int64 v258[4]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v259[32]; // [rsp+E60h] [rbp+D60h] BYREF
  _BYTE v260[40]; // [rsp+E80h] [rbp+D80h] BYREF
  _BYTE v261[40]; // [rsp+EA8h] [rbp+DA8h] BYREF
  __int64 v262[4]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v263[32]; // [rsp+EF0h] [rbp+DF0h] BYREF
  _BYTE v264[40]; // [rsp+F10h] [rbp+E10h] BYREF
  _BYTE v265[40]; // [rsp+F38h] [rbp+E38h] BYREF
  __int64 v266[4]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v267[32]; // [rsp+F80h] [rbp+E80h] BYREF
  _BYTE v268[40]; // [rsp+FA0h] [rbp+EA0h] BYREF
  _BYTE v269[40]; // [rsp+FC8h] [rbp+EC8h] BYREF
  __int64 v270[4]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v271[32]; // [rsp+1010h] [rbp+F10h] BYREF
  _BYTE v272[40]; // [rsp+1030h] [rbp+F30h] BYREF
  _BYTE v273[40]; // [rsp+1058h] [rbp+F58h] BYREF
  __int64 v274[4]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v275[32]; // [rsp+10A0h] [rbp+FA0h] BYREF
  _BYTE v276[40]; // [rsp+10C0h] [rbp+FC0h] BYREF
  _BYTE v277[40]; // [rsp+10E8h] [rbp+FE8h] BYREF
  __int64 v278[4]; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v279[32]; // [rsp+1130h] [rbp+1030h] BYREF
  _BYTE v280[40]; // [rsp+1150h] [rbp+1050h] BYREF
  _BYTE v281[40]; // [rsp+1178h] [rbp+1078h] BYREF
  _BYTE v282[144]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v283[144]; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v284[144]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v285[144]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v286[144]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _BYTE v287[144]; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v288[144]; // [rsp+1500h] [rbp+1400h] BYREF
  _BYTE v289[144]; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v290[144]; // [rsp+1620h] [rbp+1520h] BYREF
  _BYTE v291[144]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _BYTE v292[144]; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v293[144]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _BYTE v294[144]; // [rsp+1860h] [rbp+1760h] BYREF
  _BYTE v295[144]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v296[144]; // [rsp+1980h] [rbp+1880h] BYREF
  _BYTE v297[144]; // [rsp+1A10h] [rbp+1910h] BYREF
  __int64 v298; // [rsp+1AA0h] [rbp+19A0h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v26, &word_18008FA7C, 0);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v29, L"TpmRegDriverGroupPolicyData", 27);
  v32 = 0;
  v33 = 0;
  v34 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v32, L"TPM", 3);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v35, L"Software\\Policies\\Microsoft", 27);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v278,
    (void **)&v35,
    (void **)&v32,
    (void **)&v29,
    0,
    131103,
    &v26);
  v10 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v282,
    &v10,
    v278);
  v38 = 0;
  v39 = 0;
  v40 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v38, &word_18008FA7C, 0);
  v41 = 0;
  v42 = 0;
  v43 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v41, &word_18008FA7C, 0);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v44, L"PcrInfo", 7);
  v47 = 0;
  v48 = 0;
  v49 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v47, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v274,
    (void **)&v47,
    (void **)&v44,
    (void **)&v41,
    0,
    131103,
    &v38);
  v11 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v283,
    &v11,
    v274);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v50, &word_18008FA7C, 0);
  v53 = 0;
  v54 = 0;
  v55 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v53, L"TpmRegDriverTpm", 15);
  v56 = 0;
  v57 = 0;
  v58 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v56, L"TPM", 3);
  v59 = 0;
  v60 = 0;
  v61 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v59, L"System\\CurrentControlSet\\Services", 33);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v270,
    (void **)&v59,
    (void **)&v56,
    (void **)&v53,
    0,
    131103,
    &v50);
  v12 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v284,
    &v12,
    v270);
  v62 = 0;
  v63 = 0;
  v64 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v62, &word_18008FA7C, 0);
  v65 = 0;
  v66 = 0;
  v67 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v65, L"TpmRegPlatformQuoteKeysKey", 26);
  v68 = 0;
  v69 = 0;
  v70 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v68, L"PlatformQuoteKeys", 17);
  v71 = 0;
  v72 = 0;
  v73 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v71, L"System\\CurrentControlSet\\Services\\TPM", 37);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v266,
    (void **)&v71,
    (void **)&v68,
    (void **)&v65,
    0,
    131103,
    &v62);
  v13 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v285,
    &v13,
    v266);
  v74 = 0;
  v75 = 0;
  v76 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v74, &word_18008FA7C, 0);
  v77 = 0;
  v78 = 0;
  v79 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v77, L"TpmRegProvisioningKey", 21);
  v80 = 0;
  v81 = 0;
  v82 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v80, L"ProvisionInfo", 13);
  v83 = 0;
  v84 = 0;
  v85 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v83, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v262,
    (void **)&v83,
    (void **)&v80,
    (void **)&v77,
    0,
    131103,
    &v74);
  v14 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v286,
    &v14,
    v262);
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( aOSydAiarAKrAuA[v1] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v86,
    L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA"
     ";;;NS)(A;CIIO;GA;;;NS)",
    v1);
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v2 = -1;
  do
    ++v2;
  while ( aTpmregdriverpe[v2] );
  std::wstring::_Construct<1,unsigned short const *>(&v89, L"TpmRegDriverPersistedData", v2);
  v92 = 0;
  v93 = 0;
  v94 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v92, L"WMI", 3);
  v95 = 0;
  v96 = 0;
  v97 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v95, L"System\\CurrentControlSet\\Services\\TPM", 37);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v258,
    (void **)&v95,
    (void **)&v92,
    (void **)&v89,
    0,
    131103,
    &v86);
  v15 = 4;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v287,
    &v15,
    v258);
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v3 = -1;
  do
    ++v3;
  while ( aOSydPaiAKaBaAC[v3] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v98,
    L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)",
    v3);
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v4 = -1;
  do
    ++v4;
  while ( aTpmregdriverpe_0[v4] );
  std::wstring::_Construct<1,unsigned short const *>(&v101, L"TpmRegDriverPersistedDataAdmin", v4);
  v104 = 0;
  v105 = 0;
  v106 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v104, L"Admin", 5);
  v107 = 0;
  v108 = 0;
  v109 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v107, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v254,
    (void **)&v107,
    (void **)&v104,
    (void **)&v101,
    0,
    131103,
    &v98);
  v16 = 5;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v288,
    &v16,
    v254);
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v5 = -1;
  do
    ++v5;
  while ( aOSydPaiAKaBaAC_0[v5] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v110,
    L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;"
     ";;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-4)(A;;KR;;;S-1-5-11)(A;CIIO;GR;;;S-1-5-11)",
    v5);
  v113 = 0;
  v114 = 0;
  v115 = 0;
  do
    ++v0;
  while ( aTpmregdriverpe_1[v0] );
  std::wstring::_Construct<1,unsigned short const *>(&v113, L"TpmRegDriverPersistedDataEndorsement", v0);
  v116 = 0;
  v117 = 0;
  v118 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v116, L"Endorsement", 11);
  v119 = 0;
  v120 = 0;
  v121 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v119, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v250,
    (void **)&v119,
    (void **)&v116,
    (void **)&v113,
    0,
    131103,
    &v110);
  v17 = 6;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v289,
    &v17,
    v250);
  v122 = 0;
  v123 = 0;
  v124 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v122, &word_18008FA7C, 0);
  v125 = 0;
  v126 = 0;
  v127 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v125, L"TPMCoreProvisioningHealthCertStore", 34);
  v128 = 0;
  v129 = 0;
  v130 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v128, L"Store", 5);
  v131 = 0;
  v132 = 0;
  v133 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v131,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert",
    52);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v246,
    (void **)&v131,
    (void **)&v128,
    (void **)&v125,
    0,
    131103,
    &v122);
  v18 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v290,
    &v18,
    v246);
  v134 = 0;
  v135 = 0;
  v136 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v134, &word_18008FA7C, 0);
  v137 = 0;
  v138 = 0;
  v139 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v137, &word_18008FA7C, 0);
  v140 = 0;
  v141 = 0;
  v142 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v140, L"TaskStates", 10);
  v143 = 0;
  v144 = 0;
  v145 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v143, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v242,
    (void **)&v143,
    (void **)&v140,
    (void **)&v137,
    1,
    131103,
    &v134);
  v19 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v291,
    &v19,
    v242);
  v146 = 0;
  v147 = 0;
  v148 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v146, &word_18008FA7C, 0);
  v149 = 0;
  v150 = 0;
  v151 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v149, &word_18008FA7C, 0);
  v152 = 0;
  v153 = 0;
  v154 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v152, L"AttestationInfo", 15);
  v155 = 0;
  v156 = 0;
  v157 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v155,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates",
    52);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v238,
    (void **)&v155,
    (void **)&v152,
    (void **)&v149,
    1,
    131103,
    &v146);
  v20 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v292,
    &v20,
    v238);
  v158 = 0;
  v159 = 0;
  v160 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v158, &word_18008FA7C, 0);
  v161 = 0;
  v162 = 0;
  v163 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v161, &word_18008FA7C, 0);
  v164 = 0;
  v165 = 0;
  v166 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v164, L"Volatile-AIKCertEnroll-EXCLUSIVE", 32);
  v167 = 0;
  v168 = 0;
  v169 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v167, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v234,
    (void **)&v167,
    (void **)&v164,
    (void **)&v161,
    1,
    131103,
    &v158);
  v21 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v293,
    &v21,
    v234);
  v170 = 0;
  v171 = 0;
  v172 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v170, &word_18008FA7C, 0);
  v173 = 0;
  v174 = 0;
  v175 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v173, L"TPMCoreProvisioningEKCertificates", 33);
  v176 = 0;
  v177 = 0;
  v178 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v176, L"EkCertStore", 11);
  v179 = 0;
  v180 = 0;
  v181 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v179,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v230,
    (void **)&v179,
    (void **)&v176,
    (void **)&v173,
    0,
    983103,
    &v170);
  v22 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v294,
    &v22,
    v230);
  v182 = 0;
  v183 = 0;
  v184 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v182, &word_18008FA7C, 0);
  v185 = 0;
  v186 = 0;
  v187 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v185, L"TPMCoreProvisioningEKCertificates", 33);
  v188 = 0;
  v189 = 0;
  v190 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v188, L"EkCertStoreECC", 14);
  v191 = 0;
  v192 = 0;
  v193 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v191,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v226,
    (void **)&v191,
    (void **)&v188,
    (void **)&v185,
    0,
    983103,
    &v182);
  v23 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v295,
    &v23,
    v226);
  v194 = 0;
  v195 = 0;
  v196 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v194, &word_18008FA7C, 0);
  v197 = 0;
  v198 = 0;
  v199 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v197, L"TPMCoreProvisioningIntermediateCACerts", 38);
  v200 = 0;
  v201 = 0;
  v202 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v200, L"IntermediateCACertStore", 23);
  v203 = 0;
  v204 = 0;
  v205 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v203,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v222,
    (void **)&v203,
    (void **)&v200,
    (void **)&v197,
    0,
    983103,
    &v194);
  v24 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v296,
    &v24,
    v222);
  v206 = 0;
  v207 = 0;
  v208 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v206, &word_18008FA7C, 0);
  v209 = 0;
  v210 = 0;
  v211 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v209, &word_18008FA7C, 0);
  v212 = 0;
  v213 = 0;
  v214 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v212, &word_18008FA7C, 0);
  v215 = 0;
  v216 = 0;
  v217 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v215,
    L"System\\CurrentControlSet\\Control\\IntegrityServices",
    50);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (char *)v218,
    (void **)&v215,
    (void **)&v212,
    (void **)&v209,
    0,
    131097,
    &v206);
  v25 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    (__int64)v297,
    &v25,
    v218);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Alloc_sentinel_and_proxy();
  v7 = HWSecurityRegistryManager::m_RegKeyTable;
  v8 = (__int64 *)v282;
  do
  {
    std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
      v6,
      v7,
      v8);
    v8 += 18;
  }
  while ( v8 != &v298 );
  `eh vector destructor iterator'(
    v282,
    0x90u,
    0x10u,
    std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v221);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v220);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v219);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v218);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v225);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v224);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v223);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v222);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v229);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v228);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v227);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v226);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v233);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v232);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v231);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v230);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v237);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v236);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v235);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v234);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v241);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v240);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v239);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v238);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v245);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v244);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v243);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v242);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v249);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v248);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v247);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v246);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v253);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v252);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v251);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v250);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v257);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v256);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v255);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v254);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v261);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v260);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v259);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v258);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v265);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v264);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v263);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v262);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v269);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v268);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v267);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v266);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v273);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v272);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v271);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v270);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v277);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v276);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v275);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v274);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v281);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v280);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v279);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v278);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegKeyTable__);
}

```

## disassembly

```asm
0x180004ab0  push    rbp
0x180004ab2  push    rbx
0x180004ab3  push    rsi
0x180004ab4  push    rdi
0x180004ab5  push    r12
0x180004ab7  push    r13
0x180004ab9  push    r14
0x180004abb  push    r15
0x180004abd  lea     rbp, [rsp-19B8h]
0x180004ac5  mov     eax, 1AB8h
0x180004aca  call    _alloca_probe
0x180004acf  sub     rsp, rax
0x180004ad2  mov     rax, cs:__security_cookie
0x180004ad9  xor     rax, rsp
0x180004adc  mov     [rbp+19F0h+var_50], rax
0x180004ae3  lea     rax, [rbp+19F0h+var_1A50]
0x180004ae7  mov     [rsp+1AF0h+var_1AB0], rax
0x180004aec  xorps   xmm0, xmm0
0x180004aef  movups  [rbp+19F0h+var_1A50], xmm0
0x180004af3  xor     r15d, r15d
0x180004af6  mov     [rbp+19F0h+var_1A40], r15
0x180004afa  mov     [rbp+19F0h+var_1A38], r15
0x180004afe  xor     r8d, r8d
0x180004b01  lea     r12, word_18008FA7C
0x180004b08  mov     rdx, r12
0x180004b0b  lea     rcx, [rbp+19F0h+var_1A50]
0x180004b0f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004b14  nop
0x180004b15  lea     rax, [rbp+19F0h+var_1A30]
0x180004b19  mov     [rsp+1AF0h+var_1AA8], rax
0x180004b1e  xorps   xmm0, xmm0
0x180004b21  movups  [rbp+19F0h+var_1A30], xmm0
0x180004b25  mov     [rbp+19F0h+var_1A20], r15
0x180004b29  mov     [rbp+19F0h+var_1A18], r15
0x180004b2d  lea     ebx, [r15+1Bh]
0x180004b31  mov     r8d, ebx
0x180004b34  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180004b3b  lea     rcx, [rbp+19F0h+var_1A30]
0x180004b3f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004b44  nop
0x180004b45  lea     rax, [rbp+19F0h+var_1A10]
0x180004b49  mov     [rsp+1AF0h+var_1AA0], rax
0x180004b4e  xorps   xmm0, xmm0
0x180004b51  movups  [rbp+19F0h+var_1A10], xmm0
0x180004b55  mov     [rbp+19F0h+var_1A00], r15
0x180004b59  mov     [rbp+19F0h+var_19F8], r15
0x180004b5d  lea     edi, [rbx-18h]
0x180004b60  mov     r8d, edi
0x180004b63  lea     rdx, aTpm; "TPM"
0x180004b6a  lea     rcx, [rbp+19F0h+var_1A10]
0x180004b6e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004b73  nop
0x180004b74  xorps   xmm0, xmm0
0x180004b77  movups  [rbp+19F0h+var_19F0], xmm0
0x180004b7b  mov     [rbp+19F0h+var_19E0], r15
0x180004b7f  mov     [rbp+19F0h+var_19D8], r15
0x180004b83  mov     r8d, ebx
0x180004b86  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft"
0x180004b8d  lea     rcx, [rbp+19F0h+var_19F0]
0x180004b91  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004b96  nop
0x180004b97  lea     rax, [rbp+19F0h+var_1A50]
0x180004b9b  mov     [rsp+1AF0h+var_1AC0], rax
0x180004ba0  mov     esi, 2001Fh
0x180004ba5  mov     [rsp+1AF0h+var_1AC8], esi
0x180004ba9  mov     [rsp+1AF0h+var_1AD0], r15d
0x180004bae  lea     r9, [rbp+19F0h+var_1A30]
0x180004bb2  lea     r8, [rbp+19F0h+var_1A10]
0x180004bb6  lea     rdx, [rbp+19F0h+var_19F0]
0x180004bba  lea     rcx, [rbp+19F0h+var_9E0]
0x180004bc1  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004bc6  nop
0x180004bc7  mov     [rsp+1AF0h+var_1A90], r15d
0x180004bcc  lea     r8, [rbp+19F0h+var_9E0]
0x180004bd3  lea     rdx, [rsp+1AF0h+var_1A90]
0x180004bd8  lea     rcx, [rbp+19F0h+var_950]
0x180004bdf  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004be4  nop
0x180004be5  lea     rax, [rbp+19F0h+var_19D0]
0x180004be9  mov     [rsp+1AF0h+var_1A98], rax
0x180004bee  xorps   xmm0, xmm0
0x180004bf1  movups  [rbp+19F0h+var_19D0], xmm0
0x180004bf5  mov     [rbp+19F0h+var_19C0], r15
0x180004bf9  mov     [rbp+19F0h+var_19B8], r15
0x180004bfd  xor     r8d, r8d
0x180004c00  mov     rdx, r12
0x180004c03  lea     rcx, [rbp+19F0h+var_19D0]
0x180004c07  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004c0c  nop
0x180004c0d  lea     rax, [rbp+19F0h+var_19B0]
0x180004c11  mov     [rsp+1AF0h+var_1AA0], rax
0x180004c16  xorps   xmm0, xmm0
0x180004c19  movups  [rbp+19F0h+var_19B0], xmm0
0x180004c1d  mov     [rbp+19F0h+var_19A0], r15
0x180004c21  mov     [rbp+19F0h+var_1998], r15
0x180004c25  xor     r8d, r8d
0x180004c28  mov     rdx, r12
0x180004c2b  lea     rcx, [rbp+19F0h+var_19B0]
0x180004c2f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004c34  nop
0x180004c35  lea     rax, [rbp+19F0h+var_1990]
0x180004c39  mov     [rsp+1AF0h+var_1AA8], rax
0x180004c3e  xorps   xmm0, xmm0
0x180004c41  movups  [rbp+19F0h+var_1990], xmm0
0x180004c45  mov     [rbp+19F0h+var_1980], r15
0x180004c49  mov     [rbp+19F0h+var_1978], r15
0x180004c4d  lea     r8d, [r15+7]
0x180004c51  lea     rdx, aPcrinfo_0; "PcrInfo"
0x180004c58  lea     rcx, [rbp+19F0h+var_1990]
0x180004c5c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004c61  nop
0x180004c62  xorps   xmm0, xmm0
0x180004c65  movups  [rbp+19F0h+var_1970], xmm0
0x180004c6c  mov     [rbp+19F0h+var_1960], r15
0x180004c73  mov     [rbp+19F0h+var_1958], r15
0x180004c7a  lea     r13d, [r15+29h]
0x180004c7e  mov     r8d, r13d
0x180004c81  lea     r14, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\TP"...
0x180004c88  mov     rdx, r14
0x180004c8b  lea     rcx, [rbp+19F0h+var_1970]
0x180004c92  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004c97  nop
0x180004c98  lea     rax, [rbp+19F0h+var_19D0]
0x180004c9c  mov     [rsp+1AF0h+var_1AC0], rax
0x180004ca1  mov     [rsp+1AF0h+var_1AC8], esi
0x180004ca5  mov     [rsp+1AF0h+var_1AD0], r15d
0x180004caa  lea     r9, [rbp+19F0h+var_19B0]
0x180004cae  lea     r8, [rbp+19F0h+var_1990]
0x180004cb2  lea     rdx, [rbp+19F0h+var_1970]
0x180004cb9  lea     rcx, [rbp+19F0h+var_A70]
0x180004cc0  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004cc5  nop
0x180004cc6  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180004cce  lea     r8, [rbp+19F0h+var_A70]
0x180004cd5  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180004cda  lea     rcx, [rbp+19F0h+var_8C0]
0x180004ce1  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004ce6  nop
0x180004ce7  lea     rax, [rbp+19F0h+var_1950]
0x180004cee  mov     [rsp+1AF0h+var_1A98], rax
0x180004cf3  xorps   xmm0, xmm0
0x180004cf6  movups  [rbp+19F0h+var_1950], xmm0
0x180004cfd  mov     [rbp+19F0h+var_1940], r15
0x180004d04  mov     [rbp+19F0h+var_1938], r15
0x180004d0b  xor     r8d, r8d
0x180004d0e  mov     rdx, r12
0x180004d11  lea     rcx, [rbp+19F0h+var_1950]
0x180004d18  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004d1d  nop
0x180004d1e  lea     rax, [rbp+19F0h+var_1930]
0x180004d25  mov     [rsp+1AF0h+var_1AA0], rax
0x180004d2a  xorps   xmm0, xmm0
0x180004d2d  movups  [rbp+19F0h+var_1930], xmm0
0x180004d34  mov     [rbp+19F0h+var_1920], r15
0x180004d3b  mov     [rbp+19F0h+var_1918], r15
0x180004d42  lea     r8d, [r15+0Fh]
0x180004d46  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x180004d4d  lea     rcx, [rbp+19F0h+var_1930]
0x180004d54  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004d59  nop
0x180004d5a  lea     rax, [rbp+19F0h+var_1910]
0x180004d61  mov     [rsp+1AF0h+var_1AA8], rax
0x180004d66  xorps   xmm0, xmm0
0x180004d69  movups  [rbp+19F0h+var_1910], xmm0
0x180004d70  mov     [rbp+19F0h+var_1900], r15
0x180004d77  mov     [rbp+19F0h+var_18F8], r15
0x180004d7e  mov     r8d, edi
0x180004d81  lea     rdx, aTpm; "TPM"
0x180004d88  lea     rcx, [rbp+19F0h+var_1910]
0x180004d8f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004d94  nop
0x180004d95  xorps   xmm0, xmm0
0x180004d98  movups  [rbp+19F0h+var_18F0], xmm0
0x180004d9f  mov     [rbp+19F0h+var_18E0], r15
0x180004da6  mov     [rbp+19F0h+var_18D8], r15
0x180004dad  lea     r8d, [r15+21h]
0x180004db1  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services"
0x180004db8  lea     rcx, [rbp+19F0h+var_18F0]
0x180004dbf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004dc4  nop
0x180004dc5  lea     rax, [rbp+19F0h+var_1950]
0x180004dcc  mov     [rsp+1AF0h+var_1AC0], rax
0x180004dd1  mov     [rsp+1AF0h+var_1AC8], esi
0x180004dd5  mov     [rsp+1AF0h+var_1AD0], r15d
0x180004dda  lea     r9, [rbp+19F0h+var_1930]
0x180004de1  lea     r8, [rbp+19F0h+var_1910]
0x180004de8  lea     rdx, [rbp+19F0h+var_18F0]
0x180004def  lea     rcx, [rbp+19F0h+var_B00]
0x180004df6  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004dfb  nop
0x180004dfc  mov     [rsp+1AF0h+var_1A88], 1
0x180004e04  lea     r8, [rbp+19F0h+var_B00]
0x180004e0b  lea     rdx, [rsp+1AF0h+var_1A88]
0x180004e10  lea     rcx, [rbp+19F0h+var_830]
0x180004e17  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004e1c  nop
0x180004e1d  lea     rax, [rbp+19F0h+var_18D0]
0x180004e24  mov     [rsp+1AF0h+var_1A98], rax
0x180004e29  xorps   xmm0, xmm0
0x180004e2c  movups  [rbp+19F0h+var_18D0], xmm0
0x180004e33  mov     [rbp+19F0h+var_18C0], r15
0x180004e3a  mov     [rbp+19F0h+var_18B8], r15
0x180004e41  xor     r8d, r8d
0x180004e44  mov     rdx, r12
0x180004e47  lea     rcx, [rbp+19F0h+var_18D0]
0x180004e4e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004e53  nop
0x180004e54  lea     rax, [rbp+19F0h+var_18B0]
0x180004e5b  mov     [rsp+1AF0h+var_1AA0], rax
0x180004e60  xorps   xmm0, xmm0
0x180004e63  movups  [rbp+19F0h+var_18B0], xmm0
0x180004e6a  mov     [rbp+19F0h+var_18A0], r15
0x180004e71  mov     [rbp+19F0h+var_1898], r15
0x180004e78  lea     r8d, [r15+1Ah]
0x180004e7c  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180004e83  lea     rcx, [rbp+19F0h+var_18B0]
0x180004e8a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004e8f  nop
0x180004e90  lea     rax, [rbp+19F0h+var_1890]
0x180004e97  mov     [rsp+1AF0h+var_1AA8], rax
0x180004e9c  xorps   xmm0, xmm0
0x180004e9f  movups  [rbp+19F0h+var_1890], xmm0
0x180004ea6  mov     [rbp+19F0h+var_1880], r15
0x180004ead  mov     [rbp+19F0h+var_1878], r15
0x180004eb4  lea     r8d, [r15+11h]
0x180004eb8  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180004ebf  lea     rcx, [rbp+19F0h+var_1890]
0x180004ec6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004ecb  nop
0x180004ecc  xorps   xmm0, xmm0
0x180004ecf  movups  [rbp+19F0h+var_1870], xmm0
0x180004ed6  mov     [rbp+19F0h+var_1860], r15
0x180004edd  mov     [rbp+19F0h+var_1858], r15
0x180004ee4  lea     r8d, [r15+25h]
0x180004ee8  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\TP"...
0x180004eef  lea     rcx, [rbp+19F0h+var_1870]
0x180004ef6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004efb  nop
0x180004efc  lea     rax, [rbp+19F0h+var_18D0]
0x180004f03  mov     [rsp+1AF0h+var_1AC0], rax
0x180004f08  mov     [rsp+1AF0h+var_1AC8], esi
0x180004f0c  mov     [rsp+1AF0h+var_1AD0], r15d
0x180004f11  lea     r9, [rbp+19F0h+var_18B0]
0x180004f18  lea     r8, [rbp+19F0h+var_1890]
0x180004f1f  lea     rdx, [rbp+19F0h+var_1870]
0x180004f26  lea     rcx, [rbp+19F0h+var_B90]
0x180004f2d  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180004f32  nop
0x180004f33  mov     [rsp+1AF0h+var_1A84], 2
0x180004f3b  lea     r8, [rbp+19F0h+var_B90]
0x180004f42  lea     rdx, [rsp+1AF0h+var_1A84]
0x180004f47  lea     rcx, [rbp+19F0h+var_7A0]
0x180004f4e  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180004f53  nop
0x180004f54  lea     rax, [rbp+19F0h+var_1850]
0x180004f5b  mov     [rsp+1AF0h+var_1A98], rax
0x180004f60  xorps   xmm0, xmm0
0x180004f63  movups  [rbp+19F0h+var_1850], xmm0
0x180004f6a  mov     [rbp+19F0h+var_1840], r15
0x180004f71  mov     [rbp+19F0h+var_1838], r15
0x180004f78  xor     r8d, r8d
0x180004f7b  mov     rdx, r12
0x180004f7e  lea     rcx, [rbp+19F0h+var_1850]
0x180004f85  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004f8a  nop
0x180004f8b  lea     rax, [rbp+19F0h+var_1830]
0x180004f92  mov     [rsp+1AF0h+var_1AA0], rax
0x180004f97  xorps   xmm0, xmm0
0x180004f9a  movups  [rbp+19F0h+var_1830], xmm0
0x180004fa1  mov     [rbp+19F0h+var_1820], r15
0x180004fa8  mov     [rbp+19F0h+var_1818], r15
0x180004faf  lea     r8d, [r15+15h]
0x180004fb3  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180004fba  lea     rcx, [rbp+19F0h+var_1830]
0x180004fc1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180004fc6  nop
0x180004fc7  lea     rax, [rbp+19F0h+var_1810]
0x180004fce  mov     [rsp+1AF0h+var_1AA8], rax
0x180004fd3  xorps   xmm0, xmm0
0x180004fd6  movups  [rbp+19F0h+var_1810], xmm0
0x180004fdd  mov     [rbp+19F0h+var_1800], r15
0x180004fe4  mov     [rbp+19F0h+var_17F8], r15
0x180004feb  lea     r8d, [r15+0Dh]
0x180004fef  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180004ff6  lea     rcx, [rbp+19F0h+var_1810]
0x180004ffd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180005002  nop
0x180005003  xorps   xmm0, xmm0
0x180005006  movups  [rbp+19F0h+var_17F0], xmm0
0x18000500d  mov     [rbp+19F0h+var_17E0], r15
0x180005014  mov     [rbp+19F0h+var_17D8], r15
0x18000501b  mov     r8d, r13d
0x18000501e  mov     rdx, r14
0x180005021  lea     rcx, [rbp+19F0h+var_17F0]
0x180005028  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000502d  nop
0x18000502e  lea     rax, [rbp+19F0h+var_1850]
0x180005035  mov     [rsp+1AF0h+var_1AC0], rax
0x18000503a  mov     [rsp+1AF0h+var_1AC8], esi
0x18000503e  mov     [rsp+1AF0h+var_1AD0], r15d
  ... truncated ...
```
