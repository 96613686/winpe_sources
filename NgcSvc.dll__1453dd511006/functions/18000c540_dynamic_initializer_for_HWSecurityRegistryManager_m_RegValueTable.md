# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__

- ea: `0x18000c540`
- end: `0x18000e48d`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__`
- size: `8013`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bf18`
- `0x18000e4a0`
- `0x18000e570`
- `0x18000e660`
- `0x18000e960`
- `0x18005cee0`
- `0x18005d290`
- `0x18005d2ec`
- `0x18006060c`
- `0x1800c4090`

## string_xrefs

- `0x18000cf57`: `MaintenanceTaskComplete`
- `0x18000c822`: `EkCertRescheduleTaskFailureStep`
- `0x18000c571`: `ActiveDirectoryBackupSrkPub`
- `0x18000dac6`: `TaskReadyForAttestation`
- `0x18000ccc8`: `FasrCustomBootPathReasons`
- `0x18000db0c`: `TaskReadyForStorage`
- `0x18000c79c`: `EkCertPath`
- `0x18000dd86`: `WindowsAikCheckCreateResult`
- `0x18000d9ae`: `TaskFirmwareVersion`
- `0x18000da3a`: `TaskManufacturerId`
- `0x18000c8f1`: `EkCertsInstalledFromNV`
- `0x18000cc7f`: `FasrCustomBootPath`
- `0x18000d1e4`: `IntermediateCertsInstalledFromNV`
- `0x18000c937`: `EkCreatePersistResult`
- `0x18000d9f4`: `TaskInformationFlags`
- `0x18000dcb3`: `WBCLPath`
- `0x18000da80`: `TaskOsBuildNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=279
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegValueTable__()
{
  char **v0; // rax
  char **v1; // rax
  char **v2; // rax
  char **v3; // rax
  char **v4; // rax
  char **v5; // rax
  char **v6; // rax
  char **v7; // rax
  char **v8; // rax
  char **v9; // rax
  char **v10; // rax
  char **v11; // rax
  char **v12; // rax
  char **v13; // rax
  char **v14; // rax
  char **v15; // rax
  char **v16; // rax
  char **v17; // rax
  char **v18; // rax
  char **v19; // rax
  char **v20; // rax
  char **v21; // rax
  char **v22; // rax
  char **v23; // rax
  char **v24; // rax
  char **v25; // rax
  char **v26; // rax
  char **v27; // rax
  char **v28; // rax
  char **v29; // rax
  char **v30; // rax
  char **v31; // rax
  char **v32; // rax
  char **v33; // rax
  char **v34; // rax
  char **v35; // rax
  char **v36; // rax
  char **v37; // rax
  char **v38; // rax
  char **v39; // rax
  char **v40; // rax
  char **v41; // rax
  char **v42; // rax
  char **v43; // rax
  char **v44; // rax
  char **v45; // rax
  char **v46; // rax
  char **v47; // rax
  char **v48; // rax
  char **v49; // rax
  char **v50; // rax
  char **v51; // rax
  char **v52; // rax
  char **v53; // rax
  char **v54; // rax
  char **v55; // rax
  char **v56; // rax
  char **v57; // rax
  char **v58; // rax
  char **v59; // rax
  char **v60; // rax
  char **v61; // rax
  char **v62; // rax
  char **v63; // rax
  char **v64; // rax
  char **v65; // rax
  char **v66; // rax
  char **v67; // rax
  char **v68; // rax
  char **v69; // rax
  char **v70; // rax
  char **v71; // rax
  char **v72; // rax
  char **v73; // rax
  char **v74; // rax
  char **v75; // rax
  char **v76; // rax
  char **v77; // rax
  char **v78; // rax
  char **v79; // rax
  char **v80; // rax
  char **v81; // rax
  char **v82; // rax
  char **v83; // rax
  char **v84; // rax
  char **v85; // rax
  char **v86; // rax
  char **v87; // rax
  char **v88; // rax
  char **v89; // rax
  char **v90; // rax
  char **v91; // rax
  char **v92; // rax
  _QWORD *v93; // rax
  __int64 v94; // rcx
  _QWORD v96[2]; // [rsp+20h] [rbp-E0h] BYREF
  char *v97; // [rsp+30h] [rbp-D0h] BYREF
  char *v98; // [rsp+50h] [rbp-B0h] BYREF
  char *v99; // [rsp+70h] [rbp-90h] BYREF
  char *v100; // [rsp+90h] [rbp-70h] BYREF
  char *v101; // [rsp+B0h] [rbp-50h] BYREF
  char *v102; // [rsp+D0h] [rbp-30h] BYREF
  char *v103; // [rsp+F0h] [rbp-10h] BYREF
  char *v104; // [rsp+110h] [rbp+10h] BYREF
  char *v105; // [rsp+130h] [rbp+30h] BYREF
  char *v106; // [rsp+150h] [rbp+50h] BYREF
  char *v107; // [rsp+170h] [rbp+70h] BYREF
  char *v108; // [rsp+190h] [rbp+90h] BYREF
  char *v109; // [rsp+1B0h] [rbp+B0h] BYREF
  char *v110; // [rsp+1D0h] [rbp+D0h] BYREF
  char *v111; // [rsp+1F0h] [rbp+F0h] BYREF
  char *v112; // [rsp+210h] [rbp+110h] BYREF
  char *v113; // [rsp+230h] [rbp+130h] BYREF
  char *v114; // [rsp+250h] [rbp+150h] BYREF
  char *v115; // [rsp+270h] [rbp+170h] BYREF
  char *v116; // [rsp+290h] [rbp+190h] BYREF
  char *v117; // [rsp+2B0h] [rbp+1B0h] BYREF
  char *v118; // [rsp+2D0h] [rbp+1D0h] BYREF
  char *v119; // [rsp+2F0h] [rbp+1F0h] BYREF
  char *v120; // [rsp+310h] [rbp+210h] BYREF
  char *v121; // [rsp+330h] [rbp+230h] BYREF
  char *v122; // [rsp+350h] [rbp+250h] BYREF
  char *v123; // [rsp+370h] [rbp+270h] BYREF
  char *v124; // [rsp+390h] [rbp+290h] BYREF
  char *v125; // [rsp+3B0h] [rbp+2B0h] BYREF
  char *v126; // [rsp+3D0h] [rbp+2D0h] BYREF
  char *v127; // [rsp+3F0h] [rbp+2F0h] BYREF
  char *v128; // [rsp+410h] [rbp+310h] BYREF
  char *v129; // [rsp+430h] [rbp+330h] BYREF
  char *v130; // [rsp+450h] [rbp+350h] BYREF
  char *v131; // [rsp+470h] [rbp+370h] BYREF
  char *v132; // [rsp+490h] [rbp+390h] BYREF
  char *v133; // [rsp+4B0h] [rbp+3B0h] BYREF
  char *v134; // [rsp+4D0h] [rbp+3D0h] BYREF
  char *v135; // [rsp+4F0h] [rbp+3F0h] BYREF
  char *v136; // [rsp+510h] [rbp+410h] BYREF
  char *v137; // [rsp+530h] [rbp+430h] BYREF
  char *v138; // [rsp+550h] [rbp+450h] BYREF
  char *v139; // [rsp+570h] [rbp+470h] BYREF
  char *v140; // [rsp+590h] [rbp+490h] BYREF
  char *v141; // [rsp+5B0h] [rbp+4B0h] BYREF
  char *v142; // [rsp+5D0h] [rbp+4D0h] BYREF
  char *v143; // [rsp+5F0h] [rbp+4F0h] BYREF
  char *v144; // [rsp+610h] [rbp+510h] BYREF
  char *v145; // [rsp+630h] [rbp+530h] BYREF
  char *v146; // [rsp+650h] [rbp+550h] BYREF
  char *v147; // [rsp+670h] [rbp+570h] BYREF
  char *v148; // [rsp+690h] [rbp+590h] BYREF
  char *v149; // [rsp+6B0h] [rbp+5B0h] BYREF
  char *v150; // [rsp+6D0h] [rbp+5D0h] BYREF
  char *v151; // [rsp+6F0h] [rbp+5F0h] BYREF
  char *v152; // [rsp+710h] [rbp+610h] BYREF
  char *v153; // [rsp+730h] [rbp+630h] BYREF
  char *v154; // [rsp+750h] [rbp+650h] BYREF
  char *v155; // [rsp+770h] [rbp+670h] BYREF
  char *v156; // [rsp+790h] [rbp+690h] BYREF
  char *v157; // [rsp+7B0h] [rbp+6B0h] BYREF
  char *v158; // [rsp+7D0h] [rbp+6D0h] BYREF
  char *v159; // [rsp+7F0h] [rbp+6F0h] BYREF
  char *v160; // [rsp+810h] [rbp+710h] BYREF
  char *v161; // [rsp+830h] [rbp+730h] BYREF
  char *v162; // [rsp+850h] [rbp+750h] BYREF
  char *v163; // [rsp+870h] [rbp+770h] BYREF
  char *v164; // [rsp+890h] [rbp+790h] BYREF
  char *v165; // [rsp+8B0h] [rbp+7B0h] BYREF
  char *v166; // [rsp+8D0h] [rbp+7D0h] BYREF
  char *v167; // [rsp+8F0h] [rbp+7F0h] BYREF
  char *v168; // [rsp+910h] [rbp+810h] BYREF
  char *v169; // [rsp+930h] [rbp+830h] BYREF
  char *v170; // [rsp+950h] [rbp+850h] BYREF
  char *v171; // [rsp+970h] [rbp+870h] BYREF
  char *v172; // [rsp+990h] [rbp+890h] BYREF
  char *v173; // [rsp+9B0h] [rbp+8B0h] BYREF
  char *v174; // [rsp+9D0h] [rbp+8D0h] BYREF
  char *v175; // [rsp+9F0h] [rbp+8F0h] BYREF
  char *v176; // [rsp+A10h] [rbp+910h] BYREF
  char *v177; // [rsp+A30h] [rbp+930h] BYREF
  char *v178; // [rsp+A50h] [rbp+950h] BYREF
  char *v179; // [rsp+A70h] [rbp+970h] BYREF
  char *v180; // [rsp+A90h] [rbp+990h] BYREF
  char *v181; // [rsp+AB0h] [rbp+9B0h] BYREF
  char *v182; // [rsp+AD0h] [rbp+9D0h] BYREF
  char *v183; // [rsp+AF0h] [rbp+9F0h] BYREF
  char *v184; // [rsp+B10h] [rbp+A10h] BYREF
  char *v185; // [rsp+B30h] [rbp+A30h] BYREF
  char *v186; // [rsp+B50h] [rbp+A50h] BYREF
  char *v187; // [rsp+B70h] [rbp+A70h] BYREF
  char *v188; // [rsp+B90h] [rbp+A90h] BYREF
  char *v189; // [rsp+BB0h] [rbp+AB0h] BYREF
  _BYTE v190[8]; // [rsp+BD0h] [rbp+AD0h] BYREF
  _BYTE v191[40]; // [rsp+BD8h] [rbp+AD8h] BYREF
  _BYTE v192[8]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v193[40]; // [rsp+C08h] [rbp+B08h] BYREF
  _BYTE v194[8]; // [rsp+C30h] [rbp+B30h] BYREF
  _BYTE v195[40]; // [rsp+C38h] [rbp+B38h] BYREF
  _BYTE v196[8]; // [rsp+C60h] [rbp+B60h] BYREF
  _BYTE v197[40]; // [rsp+C68h] [rbp+B68h] BYREF
  _BYTE v198[8]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v199[40]; // [rsp+C98h] [rbp+B98h] BYREF
  _BYTE v200[8]; // [rsp+CC0h] [rbp+BC0h] BYREF
  _BYTE v201[40]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v202[8]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v203[40]; // [rsp+CF8h] [rbp+BF8h] BYREF
  _BYTE v204[8]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v205[40]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v206[8]; // [rsp+D50h] [rbp+C50h] BYREF
  _BYTE v207[40]; // [rsp+D58h] [rbp+C58h] BYREF
  _BYTE v208[8]; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v209[40]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v210[8]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v211[40]; // [rsp+DB8h] [rbp+CB8h] BYREF
  _BYTE v212[8]; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v213[40]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v214[8]; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE v215[40]; // [rsp+E18h] [rbp+D18h] BYREF
  _BYTE v216[8]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v217[40]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v218[8]; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v219[40]; // [rsp+E78h] [rbp+D78h] BYREF
  _BYTE v220[8]; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v221[40]; // [rsp+EA8h] [rbp+DA8h] BYREF
  _BYTE v222[8]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v223[40]; // [rsp+ED8h] [rbp+DD8h] BYREF
  _BYTE v224[8]; // [rsp+F00h] [rbp+E00h] BYREF
  _BYTE v225[40]; // [rsp+F08h] [rbp+E08h] BYREF
  _BYTE v226[8]; // [rsp+F30h] [rbp+E30h] BYREF
  _BYTE v227[40]; // [rsp+F38h] [rbp+E38h] BYREF
  _BYTE v228[8]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v229[40]; // [rsp+F68h] [rbp+E68h] BYREF
  _BYTE v230[8]; // [rsp+F90h] [rbp+E90h] BYREF
  _BYTE v231[40]; // [rsp+F98h] [rbp+E98h] BYREF
  _BYTE v232[8]; // [rsp+FC0h] [rbp+EC0h] BYREF
  _BYTE v233[40]; // [rsp+FC8h] [rbp+EC8h] BYREF
  _BYTE v234[8]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v235[40]; // [rsp+FF8h] [rbp+EF8h] BYREF
  _BYTE v236[8]; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v237[40]; // [rsp+1028h] [rbp+F28h] BYREF
  _BYTE v238[8]; // [rsp+1050h] [rbp+F50h] BYREF
  _BYTE v239[40]; // [rsp+1058h] [rbp+F58h] BYREF
  _BYTE v240[8]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v241[40]; // [rsp+1088h] [rbp+F88h] BYREF
  _BYTE v242[8]; // [rsp+10B0h] [rbp+FB0h] BYREF
  _BYTE v243[40]; // [rsp+10B8h] [rbp+FB8h] BYREF
  _BYTE v244[8]; // [rsp+10E0h] [rbp+FE0h] BYREF
  _BYTE v245[40]; // [rsp+10E8h] [rbp+FE8h] BYREF
  _BYTE v246[8]; // [rsp+1110h] [rbp+1010h] BYREF
  _BYTE v247[40]; // [rsp+1118h] [rbp+1018h] BYREF
  _BYTE v248[8]; // [rsp+1140h] [rbp+1040h] BYREF
  _BYTE v249[40]; // [rsp+1148h] [rbp+1048h] BYREF
  _BYTE v250[8]; // [rsp+1170h] [rbp+1070h] BYREF
  _BYTE v251[40]; // [rsp+1178h] [rbp+1078h] BYREF
  _BYTE v252[8]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _BYTE v253[40]; // [rsp+11A8h] [rbp+10A8h] BYREF
  _BYTE v254[8]; // [rsp+11D0h] [rbp+10D0h] BYREF
  _BYTE v255[40]; // [rsp+11D8h] [rbp+10D8h] BYREF
  _BYTE v256[8]; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v257[40]; // [rsp+1208h] [rbp+1108h] BYREF
  _BYTE v258[8]; // [rsp+1230h] [rbp+1130h] BYREF
  _BYTE v259[40]; // [rsp+1238h] [rbp+1138h] BYREF
  _BYTE v260[8]; // [rsp+1260h] [rbp+1160h] BYREF
  _BYTE v261[40]; // [rsp+1268h] [rbp+1168h] BYREF
  _BYTE v262[8]; // [rsp+1290h] [rbp+1190h] BYREF
  _BYTE v263[40]; // [rsp+1298h] [rbp+1198h] BYREF
  _BYTE v264[8]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _BYTE v265[40]; // [rsp+12C8h] [rbp+11C8h] BYREF
  _BYTE v266[8]; // [rsp+12F0h] [rbp+11F0h] BYREF
  _BYTE v267[40]; // [rsp+12F8h] [rbp+11F8h] BYREF
  _BYTE v268[8]; // [rsp+1320h] [rbp+1220h] BYREF
  _BYTE v269[40]; // [rsp+1328h] [rbp+1228h] BYREF
  _BYTE v270[8]; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v271[40]; // [rsp+1358h] [rbp+1258h] BYREF
  _BYTE v272[8]; // [rsp+1380h] [rbp+1280h] BYREF
  _BYTE v273[40]; // [rsp+1388h] [rbp+1288h] BYREF
  _BYTE v274[8]; // [rsp+13B0h] [rbp+12B0h] BYREF
  _BYTE v275[40]; // [rsp+13B8h] [rbp+12B8h] BYREF
  _BYTE v276[8]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _BYTE v277[40]; // [rsp+13E8h] [rbp+12E8h] BYREF
  _BYTE v278[8]; // [rsp+1410h] [rbp+1310h] BYREF
  _BYTE v279[40]; // [rsp+1418h] [rbp+1318h] BYREF
  _BYTE v280[8]; // [rsp+1440h] [rbp+1340h] BYREF
  _BYTE v281[40]; // [rsp+1448h] [rbp+1348h] BYREF
  _BYTE v282[8]; // [rsp+1470h] [rbp+1370h] BYREF
  _BYTE v283[40]; // [rsp+1478h] [rbp+1378h] BYREF
  _BYTE v284[8]; // [rsp+14A0h] [rbp+13A0h] BYREF
  _BYTE v285[40]; // [rsp+14A8h] [rbp+13A8h] BYREF
  _BYTE v286[8]; // [rsp+14D0h] [rbp+13D0h] BYREF
  _BYTE v287[40]; // [rsp+14D8h] [rbp+13D8h] BYREF
  _BYTE v288[8]; // [rsp+1500h] [rbp+1400h] BYREF
  _BYTE v289[40]; // [rsp+1508h] [rbp+1408h] BYREF
  _BYTE v290[8]; // [rsp+1530h] [rbp+1430h] BYREF
  _BYTE v291[40]; // [rsp+1538h] [rbp+1438h] BYREF
  _BYTE v292[8]; // [rsp+1560h] [rbp+1460h] BYREF
  _BYTE v293[40]; // [rsp+1568h] [rbp+1468h] BYREF
  _BYTE v294[8]; // [rsp+1590h] [rbp+1490h] BYREF
  _BYTE v295[40]; // [rsp+1598h] [rbp+1498h] BYREF
  _BYTE v296[8]; // [rsp+15C0h] [rbp+14C0h] BYREF
  _BYTE v297[40]; // [rsp+15C8h] [rbp+14C8h] BYREF
  _BYTE v298[8]; // [rsp+15F0h] [rbp+14F0h] BYREF
  _BYTE v299[40]; // [rsp+15F8h] [rbp+14F8h] BYREF
  _BYTE v300[8]; // [rsp+1620h] [rbp+1520h] BYREF
  _BYTE v301[40]; // [rsp+1628h] [rbp+1528h] BYREF
  _BYTE v302[8]; // [rsp+1650h] [rbp+1550h] BYREF
  _BYTE v303[40]; // [rsp+1658h] [rbp+1558h] BYREF
  _BYTE v304[8]; // [rsp+1680h] [rbp+1580h] BYREF
  _BYTE v305[40]; // [rsp+1688h] [rbp+1588h] BYREF
  _BYTE v306[8]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _BYTE v307[40]; // [rsp+16B8h] [rbp+15B8h] BYREF
  _BYTE v308[8]; // [rsp+16E0h] [rbp+15E0h] BYREF
  _BYTE v309[40]; // [rsp+16E8h] [rbp+15E8h] BYREF
  _BYTE v310[8]; // [rsp+1710h] [rbp+1610h] BYREF
  _BYTE v311[40]; // [rsp+1718h] [rbp+1618h] BYREF
  _BYTE v312[8]; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v313[40]; // [rsp+1748h] [rbp+1648h] BYREF
  _BYTE v314[8]; // [rsp+1770h] [rbp+1670h] BYREF
  _BYTE v315[40]; // [rsp+1778h] [rbp+1678h] BYREF
  _BYTE v316[8]; // [rsp+17A0h] [rbp+16A0h] BYREF
  _BYTE v317[40]; // [rsp+17A8h] [rbp+16A8h] BYREF
  _BYTE v318[8]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _BYTE v319[40]; // [rsp+17D8h] [rbp+16D8h] BYREF
  _BYTE v320[8]; // [rsp+1800h] [rbp+1700h] BYREF
  _BYTE v321[40]; // [rsp+1808h] [rbp+1708h] BYREF
  _BYTE v322[8]; // [rsp+1830h] [rbp+1730h] BYREF
  _BYTE v323[40]; // [rsp+1838h] [rbp+1738h] BYREF
  _BYTE v324[8]; // [rsp+1860h] [rbp+1760h] BYREF
  _BYTE v325[40]; // [rsp+1868h] [rbp+1768h] BYREF
  _BYTE v326[8]; // [rsp+1890h] [rbp+1790h] BYREF
  _BYTE v327[40]; // [rsp+1898h] [rbp+1798h] BYREF
  _BYTE v328[8]; // [rsp+18C0h] [rbp+17C0h] BYREF
  _BYTE v329[40]; // [rsp+18C8h] [rbp+17C8h] BYREF
  _BYTE v330[8]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _BYTE v331[40]; // [rsp+18F8h] [rbp+17F8h] BYREF
  _BYTE v332[8]; // [rsp+1920h] [rbp+1820h] BYREF
  _BYTE v333[40]; // [rsp+1928h] [rbp+1828h] BYREF
  _BYTE v334[8]; // [rsp+1950h] [rbp+1850h] BYREF
  _BYTE v335[40]; // [rsp+1958h] [rbp+1858h] BYREF
  _BYTE v336[8]; // [rsp+1980h] [rbp+1880h] BYREF
  _BYTE v337[40]; // [rsp+1988h] [rbp+1888h] BYREF
  _BYTE v338[8]; // [rsp+19B0h] [rbp+18B0h] BYREF
  _BYTE v339[40]; // [rsp+19B8h] [rbp+18B8h] BYREF
  _BYTE v340[8]; // [rsp+19E0h] [rbp+18E0h] BYREF
  _BYTE v341[40]; // [rsp+19E8h] [rbp+18E8h] BYREF
  _BYTE v342[8]; // [rsp+1A10h] [rbp+1910h] BYREF
  _BYTE v343[40]; // [rsp+1A18h] [rbp+1918h] BYREF
  _BYTE v344[8]; // [rsp+1A40h] [rbp+1940h] BYREF
  _BYTE v345[40]; // [rsp+1A48h] [rbp+1948h] BYREF
  _BYTE v346[8]; // [rsp+1A70h] [rbp+1970h] BYREF
  _BYTE v347[40]; // [rsp+1A78h] [rbp+1978h] BYREF
  _BYTE v348[8]; // [rsp+1AA0h] [rbp+19A0h] BYREF
  _BYTE v349[40]; // [rsp+1AA8h] [rbp+19A8h] BYREF
  _BYTE v350[8]; // [rsp+1AD0h] [rbp+19D0h] BYREF
  _BYTE v351[40]; // [rsp+1AD8h] [rbp+19D8h] BYREF
  _BYTE v352[8]; // [rsp+1B00h] [rbp+1A00h] BYREF
  _BYTE v353[40]; // [rsp+1B08h] [rbp+1A08h] BYREF
  _BYTE v354[8]; // [rsp+1B30h] [rbp+1A30h] BYREF
  _BYTE v355[40]; // [rsp+1B38h] [rbp+1A38h] BYREF
  _BYTE v356[8]; // [rsp+1B60h] [rbp+1A60h] BYREF
  _BYTE v357[40]; // [rsp+1B68h] [rbp+1A68h] BYREF
  _BYTE v358[8]; // [rsp+1B90h] [rbp+1A90h] BYREF
  _BYTE v359[40]; // [rsp+1B98h] [rbp+1A98h] BYREF
  _BYTE v360[8]; // [rsp+1BC0h] [rbp+1AC0h] BYREF
  _BYTE v361[40]; // [rsp+1BC8h] [rbp+1AC8h] BYREF
  _BYTE v362[8]; // [rsp+1BF0h] [rbp+1AF0h] BYREF
  _BYTE v363[40]; // [rsp+1BF8h] [rbp+1AF8h] BYREF
  _BYTE v364[8]; // [rsp+1C20h] [rbp+1B20h] BYREF
  _BYTE v365[40]; // [rsp+1C28h] [rbp+1B28h] BYREF
  _BYTE v366[8]; // [rsp+1C50h] [rbp+1B50h] BYREF
  _BYTE v367[40]; // [rsp+1C58h] [rbp+1B58h] BYREF
  _BYTE v368[8]; // [rsp+1C80h] [rbp+1B80h] BYREF
  _BYTE v369[40]; // [rsp+1C88h] [rbp+1B88h] BYREF
  _BYTE v370[8]; // [rsp+1CB0h] [rbp+1BB0h] BYREF
  _BYTE v371[40]; // [rsp+1CB8h] [rbp+1BB8h] BYREF
  _BYTE v372[8]; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  _BYTE v373[40]; // [rsp+1CE8h] [rbp+1BE8h] BYREF
  _BYTE v374[8]; // [rsp+1D10h] [rbp+1C10h] BYREF
  _BYTE v375[40]; // [rsp+1D18h] [rbp+1C18h] BYREF
  int v376; // [rsp+1D40h] [rbp+1C40h] BYREF
  _BYTE v377[48]; // [rsp+1D48h] [rbp+1C48h] BYREF
  int v378; // [rsp+1D78h] [rbp+1C78h]
  _BYTE v379[48]; // [rsp+1D80h] [rbp+1C80h] BYREF
  int v380; // [rsp+1DB0h] [rbp+1CB0h]
  _BYTE v381[48]; // [rsp+1DB8h] [rbp+1CB8h] BYREF
  int v382; // [rsp+1DE8h] [rbp+1CE8h]
  _BYTE v383[48]; // [rsp+1DF0h] [rbp+1CF0h] BYREF
  int v384; // [rsp+1E20h] [rbp+1D20h]
  _BYTE v385[48]; // [rsp+1E28h] [rbp+1D28h] BYREF
  int v386; // [rsp+1E58h] [rbp+1D58h]
  _BYTE v387[48]; // [rsp+1E60h] [rbp+1D60h] BYREF
  int v388; // [rsp+1E90h] [rbp+1D90h]
  _BYTE v389[48]; // [rsp+1E98h] [rbp+1D98h] BYREF
  int v390; // [rsp+1EC8h] [rbp+1DC8h]
  _BYTE v391[48]; // [rsp+1ED0h] [rbp+1DD0h] BYREF
  int v392; // [rsp+1F00h] [rbp+1E00h]
  _BYTE v393[48]; // [rsp+1F08h] [rbp+1E08h] BYREF
  int v394; // [rsp+1F38h] [rbp+1E38h]
  _BYTE v395[48]; // [rsp+1F40h] [rbp+1E40h] BYREF
  int v396; // [rsp+1F70h] [rbp+1E70h]
  _BYTE v397[48]; // [rsp+1F78h] [rbp+1E78h] BYREF
  int v398; // [rsp+1FA8h] [rbp+1EA8h]
  _BYTE v399[48]; // [rsp+1FB0h] [rbp+1EB0h] BYREF
  int v400; // [rsp+1FE0h] [rbp+1EE0h]
  _BYTE v401[48]; // [rsp+1FE8h] [rbp+1EE8h] BYREF
  int v402; // [rsp+2018h] [rbp+1F18h]
  _BYTE v403[48]; // [rsp+2020h] [rbp+1F20h] BYREF
  int v404; // [rsp+2050h] [rbp+1F50h]
  _BYTE v405[48]; // [rsp+2058h] [rbp+1F58h] BYREF
  int v406; // [rsp+2088h] [rbp+1F88h]
  _BYTE v407[48]; // [rsp+2090h] [rbp+1F90h] BYREF
  int v408; // [rsp+20C0h] [rbp+1FC0h]
  _BYTE v409[48]; // [rsp+20C8h] [rbp+1FC8h] BYREF
  int v410; // [rsp+20F8h] [rbp+1FF8h]
  _BYTE v411[48]; // [rsp+2100h] [rbp+2000h] BYREF
  int v412; // [rsp+2130h] [rbp+2030h]
  _BYTE v413[48]; // [rsp+2138h] [rbp+2038h] BYREF
  int v414; // [rsp+2168h] [rbp+2068h]
  _BYTE v415[48]; // [rsp+2170h] [rbp+2070h] BYREF
  int v416; // [rsp+21A0h] [rbp+20A0h]
  _BYTE v417[48]; // [rsp+21A8h] [rbp+20A8h] BYREF
  int v418; // [rsp+21D8h] [rbp+20D8h]
  _BYTE v419[48]; // [rsp+21E0h] [rbp+20E0h] BYREF
  int v420; // [rsp+2210h] [rbp+2110h]
  _BYTE v421[48]; // [rsp+2218h] [rbp+2118h] BYREF
  int v422; // [rsp+2248h] [rbp+2148h]
  _BYTE v423[48]; // [rsp+2250h] [rbp+2150h] BYREF
  int v424; // [rsp+2280h] [rbp+2180h]
  _BYTE v425[48]; // [rsp+2288h] [rbp+2188h] BYREF
  int v426; // [rsp+22B8h] [rbp+21B8h]
  _BYTE v427[48]; // [rsp+22C0h] [rbp+21C0h] BYREF
  int v428; // [rsp+22F0h] [rbp+21F0h]
  _BYTE v429[48]; // [rsp+22F8h] [rbp+21F8h] BYREF
  int v430; // [rsp+2328h] [rbp+2228h]
  _BYTE v431[48]; // [rsp+2330h] [rbp+2230h] BYREF
  int v432; // [rsp+2360h] [rbp+2260h]
  _BYTE v433[48]; // [rsp+2368h] [rbp+2268h] BYREF
  int v434; // [rsp+2398h] [rbp+2298h]
  _BYTE v435[48]; // [rsp+23A0h] [rbp+22A0h] BYREF
  int v436; // [rsp+23D0h] [rbp+22D0h]
  _BYTE v437[48]; // [rsp+23D8h] [rbp+22D8h] BYREF
  int v438; // [rsp+2408h] [rbp+2308h]
  _BYTE v439[48]; // [rsp+2410h] [rbp+2310h] BYREF
  int v440; // [rsp+2440h] [rbp+2340h]
  _BYTE v441[48]; // [rsp+2448h] [rbp+2348h] BYREF
  int v442; // [rsp+2478h] [rbp+2378h]
  _BYTE v443[48]; // [rsp+2480h] [rbp+2380h] BYREF
  int v444; // [rsp+24B0h] [rbp+23B0h]
  _BYTE v445[48]; // [rsp+24B8h] [rbp+23B8h] BYREF
  int v446; // [rsp+24E8h] [rbp+23E8h]
  _BYTE v447[48]; // [rsp+24F0h] [rbp+23F0h] BYREF
  int v448; // [rsp+2520h] [rbp+2420h]
  _BYTE v449[48]; // [rsp+2528h] [rbp+2428h] BYREF
  int v450; // [rsp+2558h] [rbp+2458h]
  _BYTE v451[48]; // [rsp+2560h] [rbp+2460h] BYREF
  int v452; // [rsp+2590h] [rbp+2490h]
  _BYTE v453[48]; // [rsp+2598h] [rbp+2498h] BYREF
  int v454; // [rsp+25C8h] [rbp+24C8h]
  _BYTE v455[48]; // [rsp+25D0h] [rbp+24D0h] BYREF
  int v456; // [rsp+2600h] [rbp+2500h]
  _BYTE v457[48]; // [rsp+2608h] [rbp+2508h] BYREF
  int v458; // [rsp+2638h] [rbp+2538h]
  _BYTE v459[48]; // [rsp+2640h] [rbp+2540h] BYREF
  int v460; // [rsp+2670h] [rbp+2570h]
  _BYTE v461[48]; // [rsp+2678h] [rbp+2578h] BYREF
  int v462; // [rsp+26A8h] [rbp+25A8h]
  _BYTE v463[48]; // [rsp+26B0h] [rbp+25B0h] BYREF
  int v464; // [rsp+26E0h] [rbp+25E0h]
  _BYTE v465[48]; // [rsp+26E8h] [rbp+25E8h] BYREF
  int v466; // [rsp+2718h] [rbp+2618h]
  _BYTE v467[48]; // [rsp+2720h] [rbp+2620h] BYREF
  int v468; // [rsp+2750h] [rbp+2650h]
  _BYTE v469[48]; // [rsp+2758h] [rbp+2658h] BYREF
  int v470; // [rsp+2788h] [rbp+2688h]
  _BYTE v471[48]; // [rsp+2790h] [rbp+2690h] BYREF
  int v472; // [rsp+27C0h] [rbp+26C0h]
  _BYTE v473[48]; // [rsp+27C8h] [rbp+26C8h] BYREF
  int v474; // [rsp+27F8h] [rbp+26F8h]
  _BYTE v475[48]; // [rsp+2800h] [rbp+2700h] BYREF
  int v476; // [rsp+2830h] [rbp+2730h]
  _BYTE v477[48]; // [rsp+2838h] [rbp+2738h] BYREF
  int v478; // [rsp+2868h] [rbp+2768h]
  _BYTE v479[48]; // [rsp+2870h] [rbp+2770h] BYREF
  int v480; // [rsp+28A0h] [rbp+27A0h]
  _BYTE v481[48]; // [rsp+28A8h] [rbp+27A8h] BYREF
  int v482; // [rsp+28D8h] [rbp+27D8h]
  _BYTE v483[48]; // [rsp+28E0h] [rbp+27E0h] BYREF
  int v484; // [rsp+2910h] [rbp+2810h]
  _BYTE v485[48]; // [rsp+2918h] [rbp+2818h] BYREF
  int v486; // [rsp+2948h] [rbp+2848h]
  _BYTE v487[48]; // [rsp+2950h] [rbp+2850h] BYREF
  int v488; // [rsp+2980h] [rbp+2880h]
  _BYTE v489[48]; // [rsp+2988h] [rbp+2888h] BYREF
  int v490; // [rsp+29B8h] [rbp+28B8h]
  _BYTE v491[48]; // [rsp+29C0h] [rbp+28C0h] BYREF
  int v492; // [rsp+29F0h] [rbp+28F0h]
  _BYTE v493[48]; // [rsp+29F8h] [rbp+28F8h] BYREF
  int v494; // [rsp+2A28h] [rbp+2928h]
  _BYTE v495[48]; // [rsp+2A30h] [rbp+2930h] BYREF
  int v496; // [rsp+2A60h] [rbp+2960h]
  _BYTE v497[48]; // [rsp+2A68h] [rbp+2968h] BYREF
  int v498; // [rsp+2A98h] [rbp+2998h]
  _BYTE v499[48]; // [rsp+2AA0h] [rbp+29A0h] BYREF
  int v500; // [rsp+2AD0h] [rbp+29D0h]
  _BYTE v501[48]; // [rsp+2AD8h] [rbp+29D8h] BYREF
  int v502; // [rsp+2B08h] [rbp+2A08h]
  _BYTE v503[48]; // [rsp+2B10h] [rbp+2A10h] BYREF
  int v504; // [rsp+2B40h] [rbp+2A40h]
  _BYTE v505[48]; // [rsp+2B48h] [rbp+2A48h] BYREF
  int v506; // [rsp+2B78h] [rbp+2A78h]
  _BYTE v507[48]; // [rsp+2B80h] [rbp+2A80h] BYREF
  int v508; // [rsp+2BB0h] [rbp+2AB0h]
  _BYTE v509[48]; // [rsp+2BB8h] [rbp+2AB8h] BYREF
  int v510; // [rsp+2BE8h] [rbp+2AE8h]
  _BYTE v511[48]; // [rsp+2BF0h] [rbp+2AF0h] BYREF
  int v512; // [rsp+2C20h] [rbp+2B20h]
  _BYTE v513[48]; // [rsp+2C28h] [rbp+2B28h] BYREF
  int v514; // [rsp+2C58h] [rbp+2B58h]
  _BYTE v515[48]; // [rsp+2C60h] [rbp+2B60h] BYREF
  int v516; // [rsp+2C90h] [rbp+2B90h]
  _BYTE v517[48]; // [rsp+2C98h] [rbp+2B98h] BYREF
  int v518; // [rsp+2CC8h] [rbp+2BC8h]
  _BYTE v519[48]; // [rsp+2CD0h] [rbp+2BD0h] BYREF
  int v520; // [rsp+2D00h] [rbp+2C00h]
  _BYTE v521[48]; // [rsp+2D08h] [rbp+2C08h] BYREF
  int v522; // [rsp+2D38h] [rbp+2C38h]
  _BYTE v523[48]; // [rsp+2D40h] [rbp+2C40h] BYREF
  int v524; // [rsp+2D70h] [rbp+2C70h]
  _BYTE v525[48]; // [rsp+2D78h] [rbp+2C78h] BYREF
  int v526; // [rsp+2DA8h] [rbp+2CA8h]
  _BYTE v527[48]; // [rsp+2DB0h] [rbp+2CB0h] BYREF
  int v528; // [rsp+2DE0h] [rbp+2CE0h]
  _BYTE v529[48]; // [rsp+2DE8h] [rbp+2CE8h] BYREF
  int v530; // [rsp+2E18h] [rbp+2D18h]
  _BYTE v531[48]; // [rsp+2E20h] [rbp+2D20h] BYREF
  int v532; // [rsp+2E50h] [rbp+2D50h]
  _BYTE v533[48]; // [rsp+2E58h] [rbp+2D58h] BYREF
  int v534; // [rsp+2E88h] [rbp+2D88h]
  _BYTE v535[48]; // [rsp+2E90h] [rbp+2D90h] BYREF
  int v536; // [rsp+2EC0h] [rbp+2DC0h]
  _BYTE v537[48]; // [rsp+2EC8h] [rbp+2DC8h] BYREF
  int v538; // [rsp+2EF8h] [rbp+2DF8h]
  _BYTE v539[48]; // [rsp+2F00h] [rbp+2E00h] BYREF
  int v540; // [rsp+2F30h] [rbp+2E30h]
  _BYTE v541[48]; // [rsp+2F38h] [rbp+2E38h] BYREF
  int v542; // [rsp+2F68h] [rbp+2E68h]
  _BYTE v543[48]; // [rsp+2F70h] [rbp+2E70h] BYREF
  int v544; // [rsp+2FA0h] [rbp+2EA0h]
  _BYTE v545[48]; // [rsp+2FA8h] [rbp+2EA8h] BYREF
  int v546; // [rsp+2FD8h] [rbp+2ED8h]
  _BYTE v547[48]; // [rsp+2FE0h] [rbp+2EE0h] BYREF
  int v548; // [rsp+3010h] [rbp+2F10h]
  _BYTE v549[48]; // [rsp+3018h] [rbp+2F18h] BYREF
  int v550; // [rsp+3048h] [rbp+2F48h]
  _BYTE v551[48]; // [rsp+3050h] [rbp+2F50h] BYREF
  int v552; // [rsp+3080h] [rbp+2F80h]
  _BYTE v553[48]; // [rsp+3088h] [rbp+2F88h] BYREF
  int v554; // [rsp+30B8h] [rbp+2FB8h]
  _BYTE v555[48]; // [rsp+30C0h] [rbp+2FC0h] BYREF
  int v556; // [rsp+30F0h] [rbp+2FF0h]
  _BYTE v557[48]; // [rsp+30F8h] [rbp+2FF8h] BYREF
  int v558; // [rsp+3128h] [rbp+3028h]
  _BYTE v559[48]; // [rsp+3130h] [rbp+3030h] BYREF
  int v560; // [rsp+3160h] [rbp+3060h]
  _BYTE v561[48]; // [rsp+3168h] [rbp+3068h] BYREF
  char v562; // [rsp+3198h] [rbp+3098h] BYREF

  v0 = std::wstring::wstring(&v97, L"ActiveDirectoryBackupSrkPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v374, 5, v0, 3);
  v376 = 0;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v377,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v374);
  v1 = std::wstring::wstring(&v98, L"AIKCertAcquiredExpired");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v372, 4, v1, 4);
  v378 = 1;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v379,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v372);
  v2 = std::wstring::wstring(&v99, L"AIKEnrollmentErrorCode");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v370, 4, v2, 4);
  v380 = 2;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v381,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v370);
  v3 = std::wstring::wstring(&v100, L"ClearReason");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v368, 3, v3, 1);
  v382 = 3;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v383,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v368);
  v4 = std::wstring::wstring(&v101, L"EkCertCorrelationId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v366, 9, v4, 1);
  v384 = 12;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v385,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v366);
  v5 = std::wstring::wstring(&v102, L"EkCertNvFailureStep");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v364, 9, v5, 4);
  v386 = 13;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v387,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v364);
  v6 = std::wstring::wstring(&v103, L"EkCertFetchSupport");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v362, 9, v6, 4);
  v388 = 14;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v389,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v362);
  v7 = std::wstring::wstring(&v104, L"EkCertIndex");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v360, 9, v7, 4);
  v390 = 15;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v391,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v360);
  v8 = std::wstring::wstring(&v105, L"EkCertPath");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v358, 9, v8, 4);
  v392 = 16;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v393,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v358);
  v9 = std::wstring::wstring(&v106, L"EkCertProvisionResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v356, 9, v9, 4);
  v394 = 17;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v395,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v356);
  v10 = std::wstring::wstring(&v107, L"EkCertRescheduleTaskFailureStep");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v354, 9, v10, 4);
  v396 = 18;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v397,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v354);
  v11 = std::wstring::wstring(&v108, L"EkCertRetrieveCertFailureStep");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v352, 9, v11, 4);
  v398 = 19;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v399,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v352);
  v12 = std::wstring::wstring(&v109, L"EkCertsCleanedUp");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v350, 9, v12, 4);
  v400 = 20;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v401,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v350);
  v13 = std::wstring::wstring(&v110, L"EkCertsInstalledFromNV");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v348, 9, v13, 4);
  v402 = 21;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v403,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v348);
  v14 = std::wstring::wstring(&v111, L"EkCreatePersistResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v346, 9, v14, 4);
  v404 = 22;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v405,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v346);
  v15 = std::wstring::wstring(&v112, L"EKCorrelationId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v344, 6, v15, 1);
  v406 = 4;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v407,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v344);
  v16 = std::wstring::wstring(&v113, L"EkFirstTimeout");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v342, 6, v16, 4);
  v408 = 5;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v409,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v342);
  v17 = std::wstring::wstring(&v114, L"EkMaxTries");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v340, 6, v17, 4);
  v410 = 6;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v411,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v340);
  v18 = std::wstring::wstring(&v115, L"EkNoFetch");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v338, 6, v18, 4);
  v412 = 7;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v413,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v338);
  v19 = std::wstring::wstring(&v116, L"EKNonce");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v336, 6, v19, 3);
  v414 = 8;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v415,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v336);
  v20 = std::wstring::wstring(&v117, L"EkPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v334, 6, v20, 3);
  v416 = 9;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v417,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v334);
  v21 = std::wstring::wstring(&v118, L"EkRetryLast");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v332, 6, v21, 11);
  v418 = 10;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v419,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v332);
  v22 = std::wstring::wstring(&v119, L"EkTries");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v330, 6, v22, 4);
  v420 = 11;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v421,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v330);
  v23 = std::wstring::wstring(&v120, L"EnableInterruptSupport");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v328, 1, v23, 4);
  v422 = 23;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v423,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v328);
  v24 = std::wstring::wstring(&v121, L"EndorsementAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v326, 6, v24, 1);
  v424 = 24;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v425,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v326);
  v25 = std::wstring::wstring(&v122, L"FasrCapable");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v324, 8, v25, 4);
  v426 = 27;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v427,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v324);
  v26 = std::wstring::wstring(&v123, L"FasrCustomBootPath");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v322, 8, v26, 4);
  v428 = 28;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v429,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v322);
  v27 = std::wstring::wstring(&v124, L"FasrCustomBootPathReasons");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v320, 8, v27, 1);
  v430 = 29;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v431,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v320);
  v28 = std::wstring::wstring(&v125, L"FasrFwVersion");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v318, 8, v28, 1);
  v432 = 30;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v433,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v318);
  v29 = std::wstring::wstring(&v126, L"FasrProdImage");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v316, 8, v29, 4);
  v434 = 31;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v435,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v316);
  v30 = std::wstring::wstring(&v127, L"TcgSecureBootValue");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v314, 8, v30, 4);
  v436 = 34;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v437,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v314);
  v31 = std::wstring::wstring(&v128, L"TcgHvciStatus");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v312, 8, v31, 11);
  v438 = 33;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v439,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v312);
  v32 = std::wstring::wstring(&v129, L"TcgSmmIsolationLevel");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v310, 8, v32, 4);
  v440 = 35;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v441,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v310);
  v33 = std::wstring::wstring(&v130, L"TcgDrtmEnabled");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v308, 8, v33, 4);
  v442 = 32;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v443,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v308);
  v34 = std::wstring::wstring(&v131, L"EkCertificatePresent");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v306, 8, v34, 4);
  v444 = 25;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v445,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v306);
  v35 = std::wstring::wstring(&v132, L"EccEkCertificatePresent");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v304, 8, v35, 4);
  v446 = 26;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v447,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v304);
  v36 = std::wstring::wstring(&v133, L"MaintenanceTaskComplete");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v302, 8, v36, 4);
  v448 = 36;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v449,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v302);
  v37 = std::wstring::wstring(&v134, L"OwnerAuthEndorsementPresent");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v300, 8, v37, 4);
  v450 = 37;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v451,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v300);
  v38 = std::wstring::wstring(&v135, L"PCR7BindingState");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v298, 8, v38, 4);
  v452 = 38;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v453,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v298);
  v39 = std::wstring::wstring(&v136, L"TpmProvisionFailedSteps");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v296, 8, v39, 4);
  v454 = 39;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v455,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v296);
  v40 = std::wstring::wstring(&v137, L"TpmProvisionHresult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v294, 8, v40, 4);
  v456 = 40;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v457,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v294);
  v41 = std::wstring::wstring(&v138, L"HASEndpoint");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v292, 7, v41, 1);
  v458 = 41;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v459,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v292);
  v42 = std::wstring::wstring(&v139, L"EnrollmentID");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v290, 7, v42, 1);
  v460 = 42;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v461,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v290);
  v43 = std::wstring::wstring(&v140, L"SignedHealthCert");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v288, 7, v43, 3);
  v462 = 43;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v463,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v288);
  v44 = std::wstring::wstring(&v141, L"Status");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v286, 7, v44, 4);
  v464 = 44;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v465,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v286);
  v45 = std::wstring::wstring(&v142, L"IntermediateCertsInstalledFromNV");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v284, 9, v45, 4);
  v466 = 45;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v467,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v284);
  v46 = std::wstring::wstring(&v143, L"IsActiveZeroExhaust");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v282, 4, v46, 4);
  v468 = 46;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v469,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v282);
  v47 = std::wstring::wstring(&v144, L"LastAuthLevel");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v280, 5, v47, 4);
  v470 = 47;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v471,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v280);
  v48 = std::wstring::wstring(&v145, L"LastEccEKCertStoreCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v278, 3, v48, 4);
  v472 = 48;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v473,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v278);
  v49 = std::wstring::wstring(&v146, L"LastEkPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v276, 3, v49, 3);
  v474 = 49;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v475,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v276);
  v50 = std::wstring::wstring(&v147, L"LastPPIRequest");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v274, 4, v50, 4);
  v476 = 50;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v477,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v274);
  v51 = std::wstring::wstring(&v148, L"LastPPIResponseHandled");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v272, 5, v51, 4);
  v478 = 51;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v479,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v272);
  v52 = std::wstring::wstring(&v149, L"LastRsaEKCertStoreCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v270, 3, v52, 4);
  v480 = 52;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v481,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v270);
  v53 = std::wstring::wstring(&v150, L"LastRsaEkCertThumbprint");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v268, 3, v53, 1);
  v482 = 53;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v483,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v268);
  v54 = std::wstring::wstring(&v151, L"LastTPMProvisionedBootId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v266, 3, v54, 4);
  v484 = 54;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v485,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v266);
  v55 = std::wstring::wstring(&v152, L"LastTPMProvisionedTime");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v264, 3, v55, 11);
  v486 = 55;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v487,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v264);
  v56 = std::wstring::wstring(&v153, L"LockoutHash");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v262, 5, v56, 1);
  v488 = 56;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v489,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v262);
  v57 = std::wstring::wstring(&v154, L"NoAutoProvision");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v260, 4, v57, 4);
  v490 = 57;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v491,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v260);
  v58 = std::wstring::wstring(&v155, L"NoOOBECheck");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v258, 4, v58, 4);
  v492 = 58;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v493,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v258);
  v59 = std::wstring::wstring(&v156, L"NoResourceVirtualizationOnNextReboot");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v256, 5, v59, 4);
  v494 = 59;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v495,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v256);
  v60 = std::wstring::wstring(&v157, L"UseNullDerivedOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v254, 4, v60, 4);
  v496 = 60;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v497,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v254);
  v61 = std::wstring::wstring(&v158, L"UseNullDerivedOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v252, 0, v61, 4);
  v498 = 61;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v499,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v252);
  v62 = std::wstring::wstring(&v159, L"OsBootCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v250, 1, v62, 4);
  v500 = 62;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v501,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v250);
  v63 = std::wstring::wstring(&v160, L"OsResumeCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v248, 15, v63, 4);
  v502 = 63;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v503,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v248);
  v64 = std::wstring::wstring(&v161, L"OSManagedAuthLevel");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v246, 0, v64, 4);
  v504 = 64;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v505,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v246);
  v65 = std::wstring::wstring(&v162, L"OverrideEkCertIndex");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v244, 6, v65, 4);
  v506 = 65;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v507,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v244);
  v66 = std::wstring::wstring(&v163, L"OwnerAuthFull");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v242, 5, v66, 1);
  v508 = 66;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v509,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v242);
  v67 = std::wstring::wstring(&v164, L"OwnerAuthNew");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v240, 5, v67, 1);
  v510 = 67;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v511,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v240);
  v68 = std::wstring::wstring(&v165, L"OwnerAuthStatus");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v238, 5, v68, 4);
  v512 = 68;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v513,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v238);
  v69 = std::wstring::wstring(&v166, L"PlatformLogRetention");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v236, 1, v69, 4);
  v514 = 69;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v515,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v236);
  v70 = std::wstring::wstring(&v167, L"PreAttHCFileError");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v234, 8, v70, 4);
  v516 = 70;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v517,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v234);
  v71 = std::wstring::wstring(&v168, L"RsaPssSaltLengthType");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v232, 4, v71, 4);
  v518 = 77;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v519,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v232);
  v72 = std::wstring::wstring(&v169, L"SRKPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v230, 5, v72, 3);
  v520 = 78;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v521,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v230);
  v73 = std::wstring::wstring(&v170, L"TaskFirmwareVersion");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v228, 4, v73, 1);
  v522 = 71;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v523,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v228);
  v74 = std::wstring::wstring(&v171, L"TaskInformationFlags");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v226, 4, v74, 4);
  v524 = 72;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v525,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v226);
  v75 = std::wstring::wstring(&v172, L"TaskManufacturerId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v224, 4, v75, 4);
  v526 = 73;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v527,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v224);
  v76 = std::wstring::wstring(&v173, L"TaskOsBuildNumber");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v222, 4, v76, 1);
  v528 = 74;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v529,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v222);
  v77 = std::wstring::wstring(&v174, L"TaskReadyForAttestation");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v220, 4, v77, 4);
  v530 = 75;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v531,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v220);
  v78 = std::wstring::wstring(&v175, L"TaskReadyForStorage");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v218, 4, v78, 4);
  v532 = 76;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v533,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v218);
  v79 = std::wstring::wstring(&v176, L"StorageOwnerAuth");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v216, 5, v79, 1);
  v534 = 79;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v535,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v216);
  v80 = std::wstring::wstring(&v177, L"TotalTPMProvisioningCount");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v214, 3, v80, 4);
  v536 = 80;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v537,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v214);
  v81 = std::wstring::wstring(&v178, L"TpmBackedDeviceID");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v212, 4, v81, 4);
  v538 = 81;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v539,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v212);
  v82 = std::wstring::wstring(&v179, L"TPMCleared");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v210, 5, v82, 4);
  v540 = 82;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v541,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v210);
  v83 = std::wstring::wstring(&v180, L"UseLegacyDictionaryAttackParameters");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v208, 0, v83, 4);
  v542 = 83;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v543,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v208);
  v84 = std::wstring::wstring(&v181, L"WBCLPath");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v206, 1, v84, 1);
  v544 = 84;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v545,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v206);
  v85 = std::wstring::wstring(&v182, L"Windows AIK");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v204, 2, v85, 3);
  v546 = 85;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v547,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v204);
  v86 = std::wstring::wstring(&v183, L"WindowsAIKBinding");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v202, 4, v86, 3);
  v548 = 86;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v549,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v202);
  v87 = std::wstring::wstring(&v184, L"WindowsAikCheckCreateResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v200, 9, v87, 4);
  v550 = 87;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v551,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v200);
  v88 = std::wstring::wstring(&v185, L"WindowsAikCorrelationId");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v198, 9, v88, 1);
  v552 = 88;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v553,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v198);
  v89 = std::wstring::wstring(&v186, L"WindowsAikEnrollReason");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v196, 9, v89, 4);
  v554 = 89;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v555,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v196);
  v90 = std::wstring::wstring(&v187, L"WindowsAikEnrollResult");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v194, 9, v90, 4);
  v556 = 90;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v557,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v194);
  v91 = std::wstring::wstring(&v188, L"WindowsAIKHash");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v192, 4, v91, 3);
  v558 = 91;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v559,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v192);
  v92 = std::wstring::wstring(&v189, L"WindowsAIKPub");
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry((__int64)v190, 4, v92, 3);
  v560 = 92;
  HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(
    (HWSecurityRegistryManager::RegistryValueEntry *)v561,
    (const struct HWSecurityRegistryManager::RegistryValueEntry *)v190);
  HWSecurityRegistryManager::m_RegValueTable = 0;
  qword_180123310 = 0;
  v93 = operator new(0x58u);
  *v93 = v93;
  v93[1] = v93;
  v93[2] = v93;
  *((_WORD *)v93 + 12) = 257;
  HWSecurityRegistryManager::m_RegValueTable = (__int64)v93;
  v96[0] = &v376;
  v96[1] = &v562;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::insert(
    v94,
    v96);
  `eh vector destructor iterator'(
    &v376,
    0x38u,
    0x5Du,
    std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>::~pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v191);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v193);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v195);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v197);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v199);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v201);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v203);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v205);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v207);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v209);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v211);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v213);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v215);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v217);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v219);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v221);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v223);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v225);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v227);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v229);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v231);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v233);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v235);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v237);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v239);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v241);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v243);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v245);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v247);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v249);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v251);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v253);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v255);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v257);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v259);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v261);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v263);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v265);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v267);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v269);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v271);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v273);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v275);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v277);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v279);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v281);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v283);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v285);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v287);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v289);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v291);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v293);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v295);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v297);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v299);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v301);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v303);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v305);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v307);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v309);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v311);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v313);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v315);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v317);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v319);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v321);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v323);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v325);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v327);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v329);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v331);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v333);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v335);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v337);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v339);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v341);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v343);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v345);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v347);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v349);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v351);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v353);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v355);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v357);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v359);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v361);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v363);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v365);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v367);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v369);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v371);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v373);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v375);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegValueTable__);
}

```

## disassembly

```asm
0x18000c540  push    rbp
0x18000c542  push    rbx
0x18000c543  push    rsi
0x18000c544  push    rdi
0x18000c545  push    r12
0x18000c547  push    r14
0x18000c549  push    r15
0x18000c54b  lea     rbp, [rsp-30B0h]
0x18000c553  mov     eax, 31B0h
0x18000c558  call    _alloca_probe
0x18000c55d  sub     rsp, rax
0x18000c560  mov     rax, cs:__security_cookie
0x18000c567  xor     rax, rsp
0x18000c56a  mov     [rbp+30E0h+var_40], rax
0x18000c571  lea     rdx, aActivedirector; "ActiveDirectoryBackupSrkPub"
0x18000c578  lea     rcx, [rsp+31E0h+var_31B0]
0x18000c57d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c582  mov     r14d, 3
0x18000c588  mov     r9d, r14d
0x18000c58b  mov     r8, rax
0x18000c58e  lea     r12d, [r14+2]
0x18000c592  mov     edx, r12d
0x18000c595  lea     rcx, [rbp+30E0h+var_14D0]
0x18000c59c  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c5a1  nop
0x18000c5a2  mov     [rbp+30E0h+var_14A0], 0
0x18000c5ac  lea     rdx, [rbp+30E0h+var_14D0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c5b3  lea     rcx, [rbp+30E0h+var_1498]; this
0x18000c5ba  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c5bf  nop
0x18000c5c0  lea     rdx, aAikcertacquire; "AIKCertAcquiredExpired"
0x18000c5c7  lea     rcx, [rsp+31E0h+var_3190]
0x18000c5cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c5d1  lea     ebx, [r14+1]
0x18000c5d5  mov     r9d, ebx
0x18000c5d8  mov     r8, rax
0x18000c5db  mov     edx, ebx
0x18000c5dd  lea     rcx, [rbp+30E0h+var_1500]
0x18000c5e4  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c5e9  nop
0x18000c5ea  lea     esi, [rbx-3]
0x18000c5ed  mov     [rbp+30E0h+var_1468], esi
0x18000c5f3  lea     rdx, [rbp+30E0h+var_1500]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c5fa  lea     rcx, [rbp+30E0h+var_1460]; this
0x18000c601  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c606  nop
0x18000c607  lea     rdx, aAikenrollmente; "AIKEnrollmentErrorCode"
0x18000c60e  lea     rcx, [rsp+31E0h+var_3170]
0x18000c613  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c618  mov     r9d, ebx
0x18000c61b  mov     r8, rax
0x18000c61e  mov     edx, ebx
0x18000c620  lea     rcx, [rbp+30E0h+var_1530]
0x18000c627  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c62c  nop
0x18000c62d  mov     [rbp+30E0h+var_1430], 2
0x18000c637  lea     rdx, [rbp+30E0h+var_1530]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c63e  lea     rcx, [rbp+30E0h+var_1428]; this
0x18000c645  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c64a  nop
0x18000c64b  lea     rdx, aClearreason; "ClearReason"
0x18000c652  lea     rcx, [rbp+30E0h+var_3150]
0x18000c656  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c65b  mov     r9d, esi
0x18000c65e  mov     r8, rax
0x18000c661  mov     edx, r14d
0x18000c664  lea     rcx, [rbp+30E0h+var_1560]
0x18000c66b  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c670  nop
0x18000c671  mov     [rbp+30E0h+var_13F8], r14d
0x18000c678  lea     rdx, [rbp+30E0h+var_1560]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c67f  lea     rcx, [rbp+30E0h+var_13F0]; this
0x18000c686  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c68b  nop
0x18000c68c  lea     rdx, aEkcertcorrelat; "EkCertCorrelationId"
0x18000c693  lea     rcx, [rbp+30E0h+var_3130]
0x18000c697  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c69c  mov     r9d, esi
0x18000c69f  mov     r8, rax
0x18000c6a2  lea     edi, [rbx+5]
0x18000c6a5  mov     edx, edi
0x18000c6a7  lea     rcx, [rbp+30E0h+var_1590]
0x18000c6ae  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c6b3  nop
0x18000c6b4  mov     [rbp+30E0h+var_13C0], 0Ch
0x18000c6be  lea     rdx, [rbp+30E0h+var_1590]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c6c5  lea     rcx, [rbp+30E0h+var_13B8]; this
0x18000c6cc  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c6d1  nop
0x18000c6d2  lea     rdx, aEkcertnvfailur; "EkCertNvFailureStep"
0x18000c6d9  lea     rcx, [rbp+30E0h+var_3110]
0x18000c6dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c6e2  mov     r9d, ebx
0x18000c6e5  mov     r8, rax
0x18000c6e8  mov     edx, edi
0x18000c6ea  lea     rcx, [rbp+30E0h+var_15C0]
0x18000c6f1  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c6f6  nop
0x18000c6f7  mov     [rbp+30E0h+var_1388], 0Dh
0x18000c701  lea     rdx, [rbp+30E0h+var_15C0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c708  lea     rcx, [rbp+30E0h+var_1380]; this
0x18000c70f  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c714  nop
0x18000c715  lea     rdx, aEkcertfetchsup; "EkCertFetchSupport"
0x18000c71c  lea     rcx, [rbp+30E0h+var_30F0]
0x18000c720  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c725  mov     r9d, ebx
0x18000c728  mov     r8, rax
0x18000c72b  mov     edx, edi
0x18000c72d  lea     rcx, [rbp+30E0h+var_15F0]
0x18000c734  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c739  nop
0x18000c73a  mov     [rbp+30E0h+var_1350], 0Eh
0x18000c744  lea     rdx, [rbp+30E0h+var_15F0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c74b  lea     rcx, [rbp+30E0h+var_1348]; this
0x18000c752  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c757  nop
0x18000c758  lea     rdx, aEkcertindex; "EkCertIndex"
0x18000c75f  lea     rcx, [rbp+30E0h+var_30D0]
0x18000c763  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c768  mov     r9d, ebx
0x18000c76b  mov     r8, rax
0x18000c76e  mov     edx, edi
0x18000c770  lea     rcx, [rbp+30E0h+var_1620]
0x18000c777  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c77c  nop
0x18000c77d  lea     r15d, [r14+0Ch]
0x18000c781  mov     [rbp+30E0h+var_1318], r15d
0x18000c788  lea     rdx, [rbp+30E0h+var_1620]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c78f  lea     rcx, [rbp+30E0h+var_1310]; this
0x18000c796  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c79b  nop
0x18000c79c  lea     rdx, aEkcertpath; "EkCertPath"
0x18000c7a3  lea     rcx, [rbp+30E0h+var_30B0]
0x18000c7a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c7ac  mov     r9d, ebx
0x18000c7af  mov     r8, rax
0x18000c7b2  mov     edx, edi
0x18000c7b4  lea     rcx, [rbp+30E0h+var_1650]
0x18000c7bb  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c7c0  nop
0x18000c7c1  mov     [rbp+30E0h+var_12E0], 10h
0x18000c7cb  lea     rdx, [rbp+30E0h+var_1650]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c7d2  lea     rcx, [rbp+30E0h+var_12D8]; this
0x18000c7d9  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c7de  nop
0x18000c7df  lea     rdx, aEkcertprovisio; "EkCertProvisionResult"
0x18000c7e6  lea     rcx, [rbp+30E0h+var_3090]
0x18000c7ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c7ef  mov     r9d, ebx
0x18000c7f2  mov     r8, rax
0x18000c7f5  mov     edx, edi
0x18000c7f7  lea     rcx, [rbp+30E0h+var_1680]
0x18000c7fe  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c803  nop
0x18000c804  mov     [rbp+30E0h+var_12A8], 11h
0x18000c80e  lea     rdx, [rbp+30E0h+var_1680]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c815  lea     rcx, [rbp+30E0h+var_12A0]; this
0x18000c81c  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c821  nop
0x18000c822  lea     rdx, aEkcertreschedu; "EkCertRescheduleTaskFailureStep"
0x18000c829  lea     rcx, [rbp+30E0h+var_3070]
0x18000c82d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c832  mov     r9d, ebx
0x18000c835  mov     r8, rax
0x18000c838  mov     edx, edi
0x18000c83a  lea     rcx, [rbp+30E0h+var_16B0]
0x18000c841  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c846  nop
0x18000c847  mov     [rbp+30E0h+var_1270], 12h
0x18000c851  lea     rdx, [rbp+30E0h+var_16B0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c858  lea     rcx, [rbp+30E0h+var_1268]; this
0x18000c85f  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c864  nop
0x18000c865  lea     rdx, aEkcertretrieve; "EkCertRetrieveCertFailureStep"
0x18000c86c  lea     rcx, [rbp+30E0h+var_3050]
0x18000c873  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c878  mov     r9d, ebx
0x18000c87b  mov     r8, rax
0x18000c87e  mov     edx, edi
0x18000c880  lea     rcx, [rbp+30E0h+var_16E0]
0x18000c887  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c88c  nop
0x18000c88d  mov     [rbp+30E0h+var_1238], 13h
0x18000c897  lea     rdx, [rbp+30E0h+var_16E0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c89e  lea     rcx, [rbp+30E0h+var_1230]; this
0x18000c8a5  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c8aa  nop
0x18000c8ab  lea     rdx, aEkcertscleaned; "EkCertsCleanedUp"
0x18000c8b2  lea     rcx, [rbp+30E0h+var_3030]
0x18000c8b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c8be  mov     r9d, ebx
0x18000c8c1  mov     r8, rax
0x18000c8c4  mov     edx, edi
0x18000c8c6  lea     rcx, [rbp+30E0h+var_1710]
0x18000c8cd  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c8d2  nop
0x18000c8d3  mov     [rbp+30E0h+var_1200], 14h
0x18000c8dd  lea     rdx, [rbp+30E0h+var_1710]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c8e4  lea     rcx, [rbp+30E0h+var_11F8]; this
0x18000c8eb  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c8f0  nop
0x18000c8f1  lea     rdx, aEkcertsinstall; "EkCertsInstalledFromNV"
0x18000c8f8  lea     rcx, [rbp+30E0h+var_3010]
0x18000c8ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c904  mov     r9d, ebx
0x18000c907  mov     r8, rax
0x18000c90a  mov     edx, edi
0x18000c90c  lea     rcx, [rbp+30E0h+var_1740]
0x18000c913  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c918  nop
0x18000c919  mov     [rbp+30E0h+var_11C8], 15h
0x18000c923  lea     rdx, [rbp+30E0h+var_1740]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c92a  lea     rcx, [rbp+30E0h+var_11C0]; this
0x18000c931  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c936  nop
0x18000c937  lea     rdx, aEkcreatepersis; "EkCreatePersistResult"
0x18000c93e  lea     rcx, [rbp+30E0h+var_2FF0]
0x18000c945  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c94a  mov     r9d, ebx
0x18000c94d  mov     r8, rax
0x18000c950  mov     edx, edi
0x18000c952  lea     rcx, [rbp+30E0h+var_1770]
0x18000c959  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c95e  nop
0x18000c95f  mov     [rbp+30E0h+var_1190], 16h
0x18000c969  lea     rdx, [rbp+30E0h+var_1770]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c970  lea     rcx, [rbp+30E0h+var_1188]; this
0x18000c977  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c97c  nop
0x18000c97d  lea     rdx, aEkcorrelationi; "EKCorrelationId"
0x18000c984  lea     rcx, [rbp+30E0h+var_2FD0]
0x18000c98b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c990  mov     r9d, esi
0x18000c993  mov     r8, rax
0x18000c996  lea     esi, [rbx+2]
0x18000c999  mov     edx, esi
0x18000c99b  lea     rcx, [rbp+30E0h+var_17A0]
0x18000c9a2  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c9a7  nop
0x18000c9a8  mov     [rbp+30E0h+var_1158], ebx
0x18000c9ae  lea     rdx, [rbp+30E0h+var_17A0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c9b5  lea     rcx, [rbp+30E0h+var_1150]; this
0x18000c9bc  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000c9c1  nop
0x18000c9c2  lea     rdx, aEkfirsttimeout; "EkFirstTimeout"
0x18000c9c9  lea     rcx, [rbp+30E0h+var_2FB0]
0x18000c9d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c9d5  mov     r9d, ebx
0x18000c9d8  mov     r8, rax
0x18000c9db  mov     edx, esi
0x18000c9dd  lea     rcx, [rbp+30E0h+var_17D0]
0x18000c9e4  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000c9e9  nop
0x18000c9ea  mov     [rbp+30E0h+var_1120], r12d
0x18000c9f1  lea     rdx, [rbp+30E0h+var_17D0]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000c9f8  lea     rcx, [rbp+30E0h+var_1118]; this
0x18000c9ff  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000ca04  nop
0x18000ca05  lea     rdx, aEkmaxtries; "EkMaxTries"
0x18000ca0c  lea     rcx, [rbp+30E0h+var_2F90]
0x18000ca13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ca18  mov     r9d, ebx
0x18000ca1b  mov     r8, rax
0x18000ca1e  mov     edx, esi
0x18000ca20  lea     rcx, [rbp+30E0h+var_1800]
0x18000ca27  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000ca2c  nop
0x18000ca2d  mov     [rbp+30E0h+var_10E8], esi
0x18000ca33  lea     rdx, [rbp+30E0h+var_1800]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000ca3a  lea     rcx, [rbp+30E0h+var_10E0]; this
0x18000ca41  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000ca46  nop
0x18000ca47  lea     rdx, aEknofetch; "EkNoFetch"
0x18000ca4e  lea     rcx, [rbp+30E0h+var_2F70]
0x18000ca55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ca5a  mov     r9d, ebx
0x18000ca5d  mov     r8, rax
0x18000ca60  mov     edx, esi
0x18000ca62  lea     rcx, [rbp+30E0h+var_1830]
0x18000ca69  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000ca6e  nop
0x18000ca6f  lea     ebx, [rdi-2]
0x18000ca72  mov     [rbp+30E0h+var_10B0], ebx
0x18000ca78  lea     rdx, [rbp+30E0h+var_1830]; struct HWSecurityRegistryManager::RegistryValueEntry *
0x18000ca7f  lea     rcx, [rbp+30E0h+var_10A8]; this
0x18000ca86  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegistryValueEntry const &)
0x18000ca8b  nop
0x18000ca8c  lea     rdx, aEknonce; "EKNonce"
0x18000ca93  lea     rcx, [rbp+30E0h+var_2F50]
0x18000ca9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000ca9f  mov     r9d, r14d
0x18000caa2  mov     r8, rax
0x18000caa5  mov     edx, esi
0x18000caa7  lea     rcx, [rbp+30E0h+var_1860]
0x18000caae  call    ??0RegistryValueEntry@HWSecurityRegistryManager@@QEAA@W4RegKeys@1@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; HWSecurityRegistryManager::RegistryValueEntry::RegistryValueEntry(HWSecurityRegistryManager::RegKeys,std::wstring,uint)
0x18000cab3  nop
0x18000cab4  lea     r14d, [r12+3]
0x18000cab9  mov     [rbp+30E0h+var_1078], r14d
0x18000cac0  lea     rdx, [rbp+30E0h+var_1860]; struct HWSecurityRegistryManager::RegistryValueEntry *
  ... truncated ...
```
