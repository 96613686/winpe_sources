# _dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataListWildcard__

- ea: `0x180004970`
- end: `0x180005dfa`
- name: `_dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataListWildcard__`
- size: `5258`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006640`
- `0x1800069f0`
- `0x1800088ec`
- `0x180014a5c`
- `0x18004a020`
- `0x18008d880`

## string_xrefs

- `0x180004a08`: `%systemroot%\*\cacls.exe`
- `0x180004a30`: `%systemroot%\winsxs\*\cacls.exe`
- `0x180004f6e`: `%systemroot%\*\icacls.exe`
- `0x180004fa5`: `%systemroot%\winsxs\*\icacls.exe`
- `0x18000534c`: `%systemroot%\winsxs\*\msconfig.exe`
- `0x180005a9a`: `%systemroot%\winsxs\*\taskkill.exe`
- `0x180005a63`: `%systemroot%\*\taskkill.exe`
- `0x180005b08`: `%systemroot%\winsxs\*\tasklist.exe`
- `0x180005ad1`: `%systemroot%\*\tasklist.exe`
- `0x180005b76`: `%systemroot%\winsxs\*\taskmgr.exe`
- `0x180005b3f`: `%systemroot%\*\taskmgr.exe`
- `0x180005c52`: `%systemroot%\*\write.exe`
- `0x180005c89`: `%systemroot%\winsxs\*\write.exe`
- `0x180005d2e`: `%systemroot%\*\xcopy.exe`
- `0x180005d65`: `%systemroot%\winsxs\*\xcopy.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=94
int dynamic_initializer_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataListWildcard__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v2[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v3[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v4; // [rsp+70h] [rbp-90h]
  const wchar_t *v5; // [rsp+78h] [rbp-88h]
  const wchar_t *v6; // [rsp+80h] [rbp-80h]
  const wchar_t *v7; // [rsp+88h] [rbp-78h]
  _BYTE v8[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v9; // [rsp+B0h] [rbp-50h]
  const wchar_t *v10; // [rsp+B8h] [rbp-48h]
  const wchar_t *v11; // [rsp+C0h] [rbp-40h]
  const wchar_t *v12; // [rsp+C8h] [rbp-38h]
  _BYTE v13[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v14; // [rsp+F0h] [rbp-10h]
  const wchar_t *v15; // [rsp+F8h] [rbp-8h]
  const wchar_t *v16; // [rsp+100h] [rbp+0h]
  const wchar_t *v17; // [rsp+108h] [rbp+8h]
  _BYTE v18[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v19; // [rsp+130h] [rbp+30h]
  const wchar_t *v20; // [rsp+138h] [rbp+38h]
  const wchar_t *v21; // [rsp+140h] [rbp+40h]
  const wchar_t *v22; // [rsp+148h] [rbp+48h]
  _BYTE v23[32]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v24; // [rsp+170h] [rbp+70h]
  const wchar_t *v25; // [rsp+178h] [rbp+78h]
  const wchar_t *v26; // [rsp+180h] [rbp+80h]
  const wchar_t *v27; // [rsp+188h] [rbp+88h]
  _BYTE v28[32]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v29; // [rsp+1B0h] [rbp+B0h]
  const wchar_t *v30; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v31; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v32; // [rsp+1C8h] [rbp+C8h]
  _BYTE v33[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v34; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v35; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v36; // [rsp+200h] [rbp+100h]
  const wchar_t *v37; // [rsp+208h] [rbp+108h]
  _BYTE v38[32]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v39; // [rsp+230h] [rbp+130h]
  const wchar_t *v40; // [rsp+238h] [rbp+138h]
  const wchar_t *v41; // [rsp+240h] [rbp+140h]
  const wchar_t *v42; // [rsp+248h] [rbp+148h]
  _BYTE v43[32]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v44; // [rsp+270h] [rbp+170h]
  const wchar_t *v45; // [rsp+278h] [rbp+178h]
  const wchar_t *v46; // [rsp+280h] [rbp+180h]
  const wchar_t *v47; // [rsp+288h] [rbp+188h]
  _BYTE v48[32]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v49; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v50; // [rsp+2B8h] [rbp+1B8h]
  const wchar_t *v51; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v52; // [rsp+2C8h] [rbp+1C8h]
  _BYTE v53[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v54; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v55; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v56; // [rsp+300h] [rbp+200h]
  const wchar_t *v57; // [rsp+308h] [rbp+208h]
  _BYTE v58[32]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v59; // [rsp+330h] [rbp+230h]
  const wchar_t *v60; // [rsp+338h] [rbp+238h]
  const wchar_t *v61; // [rsp+340h] [rbp+240h]
  const wchar_t *v62; // [rsp+348h] [rbp+248h]
  _BYTE v63[32]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v64; // [rsp+370h] [rbp+270h]
  const wchar_t *v65; // [rsp+378h] [rbp+278h]
  const wchar_t *v66; // [rsp+380h] [rbp+280h]
  const wchar_t *v67; // [rsp+388h] [rbp+288h]
  _BYTE v68[32]; // [rsp+390h] [rbp+290h] BYREF
  __int64 v69; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v70; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v71; // [rsp+3C0h] [rbp+2C0h]
  const wchar_t *v72; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v73[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v74; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v75; // [rsp+3F8h] [rbp+2F8h]
  const wchar_t *v76; // [rsp+400h] [rbp+300h]
  const wchar_t *v77; // [rsp+408h] [rbp+308h]
  _BYTE v78[32]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v79; // [rsp+430h] [rbp+330h]
  const wchar_t *v80; // [rsp+438h] [rbp+338h]
  const wchar_t *v81; // [rsp+440h] [rbp+340h]
  const wchar_t *v82; // [rsp+448h] [rbp+348h]
  _BYTE v83[32]; // [rsp+450h] [rbp+350h] BYREF
  __int64 v84; // [rsp+470h] [rbp+370h]
  const wchar_t *v85; // [rsp+478h] [rbp+378h]
  const wchar_t *v86; // [rsp+480h] [rbp+380h]
  const wchar_t *v87; // [rsp+488h] [rbp+388h]
  _BYTE v88[32]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v89; // [rsp+4B0h] [rbp+3B0h]
  const wchar_t *v90; // [rsp+4B8h] [rbp+3B8h]
  const wchar_t *v91; // [rsp+4C0h] [rbp+3C0h]
  const wchar_t *v92; // [rsp+4C8h] [rbp+3C8h]
  _BYTE v93[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v94; // [rsp+4F0h] [rbp+3F0h]
  const wchar_t *v95; // [rsp+4F8h] [rbp+3F8h]
  const wchar_t *v96; // [rsp+500h] [rbp+400h]
  const wchar_t *v97; // [rsp+508h] [rbp+408h]
  _BYTE v98[32]; // [rsp+510h] [rbp+410h] BYREF
  __int64 v99; // [rsp+530h] [rbp+430h]
  const wchar_t *v100; // [rsp+538h] [rbp+438h]
  const wchar_t *v101; // [rsp+540h] [rbp+440h]
  const wchar_t *v102; // [rsp+548h] [rbp+448h]
  _BYTE v103[32]; // [rsp+550h] [rbp+450h] BYREF
  __int64 v104; // [rsp+570h] [rbp+470h]
  const wchar_t *v105; // [rsp+578h] [rbp+478h]
  const wchar_t *v106; // [rsp+580h] [rbp+480h]
  const wchar_t *v107; // [rsp+588h] [rbp+488h]
  _BYTE v108[32]; // [rsp+590h] [rbp+490h] BYREF
  __int64 v109; // [rsp+5B0h] [rbp+4B0h]
  const wchar_t *v110; // [rsp+5B8h] [rbp+4B8h]
  const wchar_t *v111; // [rsp+5C0h] [rbp+4C0h]
  const wchar_t *v112; // [rsp+5C8h] [rbp+4C8h]
  _BYTE v113[32]; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v114; // [rsp+5F0h] [rbp+4F0h]
  const wchar_t *v115; // [rsp+5F8h] [rbp+4F8h]
  const wchar_t *v116; // [rsp+600h] [rbp+500h]
  const wchar_t *v117; // [rsp+608h] [rbp+508h]
  _BYTE v118[32]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v119; // [rsp+630h] [rbp+530h]
  const wchar_t *v120; // [rsp+638h] [rbp+538h]
  const wchar_t *v121; // [rsp+640h] [rbp+540h]
  const wchar_t *v122; // [rsp+648h] [rbp+548h]
  _BYTE v123[32]; // [rsp+650h] [rbp+550h] BYREF
  __int64 v124; // [rsp+670h] [rbp+570h]
  const wchar_t *v125; // [rsp+678h] [rbp+578h]
  const wchar_t *v126; // [rsp+680h] [rbp+580h]
  const wchar_t *v127; // [rsp+688h] [rbp+588h]
  _BYTE v128[32]; // [rsp+690h] [rbp+590h] BYREF
  __int64 v129; // [rsp+6B0h] [rbp+5B0h]
  const wchar_t *v130; // [rsp+6B8h] [rbp+5B8h]
  const wchar_t *v131; // [rsp+6C0h] [rbp+5C0h]
  const wchar_t *v132; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v133[32]; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v134; // [rsp+6F0h] [rbp+5F0h]
  const wchar_t *v135; // [rsp+6F8h] [rbp+5F8h]
  const wchar_t *v136; // [rsp+700h] [rbp+600h]
  const wchar_t *v137; // [rsp+708h] [rbp+608h]
  _BYTE v138[32]; // [rsp+710h] [rbp+610h] BYREF
  __int64 v139; // [rsp+730h] [rbp+630h]
  const wchar_t *v140; // [rsp+738h] [rbp+638h]
  const wchar_t *v141; // [rsp+740h] [rbp+640h]
  const wchar_t *v142; // [rsp+748h] [rbp+648h]
  _BYTE v143[32]; // [rsp+750h] [rbp+650h] BYREF
  __int64 v144; // [rsp+770h] [rbp+670h]
  const wchar_t *v145; // [rsp+778h] [rbp+678h]
  const wchar_t *v146; // [rsp+780h] [rbp+680h]
  const wchar_t *v147; // [rsp+788h] [rbp+688h]
  _BYTE v148[32]; // [rsp+790h] [rbp+690h] BYREF
  __int64 v149; // [rsp+7B0h] [rbp+6B0h]
  const wchar_t *v150; // [rsp+7B8h] [rbp+6B8h]
  const wchar_t *v151; // [rsp+7C0h] [rbp+6C0h]
  const wchar_t *v152; // [rsp+7C8h] [rbp+6C8h]
  _BYTE v153[32]; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v154; // [rsp+7F0h] [rbp+6F0h]
  const wchar_t *v155; // [rsp+7F8h] [rbp+6F8h]
  const wchar_t *v156; // [rsp+800h] [rbp+700h]
  const wchar_t *v157; // [rsp+808h] [rbp+708h]
  _BYTE v158[32]; // [rsp+810h] [rbp+710h] BYREF
  __int64 v159; // [rsp+830h] [rbp+730h]
  const wchar_t *v160; // [rsp+838h] [rbp+738h]
  const wchar_t *v161; // [rsp+840h] [rbp+740h]
  const wchar_t *v162; // [rsp+848h] [rbp+748h]
  _BYTE v163[32]; // [rsp+850h] [rbp+750h] BYREF
  __int64 v164; // [rsp+870h] [rbp+770h]
  const wchar_t *v165; // [rsp+878h] [rbp+778h]
  const wchar_t *v166; // [rsp+880h] [rbp+780h]
  const wchar_t *v167; // [rsp+888h] [rbp+788h]
  _BYTE v168[32]; // [rsp+890h] [rbp+790h] BYREF
  __int64 v169; // [rsp+8B0h] [rbp+7B0h]
  const wchar_t *v170; // [rsp+8B8h] [rbp+7B8h]
  const wchar_t *v171; // [rsp+8C0h] [rbp+7C0h]
  const wchar_t *v172; // [rsp+8C8h] [rbp+7C8h]
  _BYTE v173[32]; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v174; // [rsp+8F0h] [rbp+7F0h]
  const wchar_t *v175; // [rsp+8F8h] [rbp+7F8h]
  const wchar_t *v176; // [rsp+900h] [rbp+800h]
  const wchar_t *v177; // [rsp+908h] [rbp+808h]
  _BYTE v178[32]; // [rsp+910h] [rbp+810h] BYREF
  __int64 v179; // [rsp+930h] [rbp+830h]
  const wchar_t *v180; // [rsp+938h] [rbp+838h]
  const wchar_t *v181; // [rsp+940h] [rbp+840h]
  const wchar_t *v182; // [rsp+948h] [rbp+848h]
  _BYTE v183[32]; // [rsp+950h] [rbp+850h] BYREF
  __int64 v184; // [rsp+970h] [rbp+870h]
  const wchar_t *v185; // [rsp+978h] [rbp+878h]
  const wchar_t *v186; // [rsp+980h] [rbp+880h]
  const wchar_t *v187; // [rsp+988h] [rbp+888h]
  _BYTE v188[32]; // [rsp+990h] [rbp+890h] BYREF
  __int64 v189; // [rsp+9B0h] [rbp+8B0h]
  const wchar_t *v190; // [rsp+9B8h] [rbp+8B8h]
  const wchar_t *v191; // [rsp+9C0h] [rbp+8C0h]
  const wchar_t *v192; // [rsp+9C8h] [rbp+8C8h]
  _BYTE v193[32]; // [rsp+9D0h] [rbp+8D0h] BYREF
  __int64 v194; // [rsp+9F0h] [rbp+8F0h]
  const wchar_t *v195; // [rsp+9F8h] [rbp+8F8h]
  const wchar_t *v196; // [rsp+A00h] [rbp+900h]
  const wchar_t *v197; // [rsp+A08h] [rbp+908h]
  _BYTE v198[32]; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v199; // [rsp+A30h] [rbp+930h]
  const wchar_t *v200; // [rsp+A38h] [rbp+938h]
  const wchar_t *v201; // [rsp+A40h] [rbp+940h]
  const wchar_t *v202; // [rsp+A48h] [rbp+948h]
  _BYTE v203[32]; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v204; // [rsp+A70h] [rbp+970h]
  const wchar_t *v205; // [rsp+A78h] [rbp+978h]
  const wchar_t *v206; // [rsp+A80h] [rbp+980h]
  const wchar_t *v207; // [rsp+A88h] [rbp+988h]
  _BYTE v208[32]; // [rsp+A90h] [rbp+990h] BYREF
  __int64 v209; // [rsp+AB0h] [rbp+9B0h]
  const wchar_t *v210; // [rsp+AB8h] [rbp+9B8h]
  const wchar_t *v211; // [rsp+AC0h] [rbp+9C0h]
  const wchar_t *v212; // [rsp+AC8h] [rbp+9C8h]
  _BYTE v213[32]; // [rsp+AD0h] [rbp+9D0h] BYREF
  __int64 v214; // [rsp+AF0h] [rbp+9F0h]
  const wchar_t *v215; // [rsp+AF8h] [rbp+9F8h]
  const wchar_t *v216; // [rsp+B00h] [rbp+A00h]
  const wchar_t *v217; // [rsp+B08h] [rbp+A08h]
  _BYTE v218[32]; // [rsp+B10h] [rbp+A10h] BYREF
  __int64 v219; // [rsp+B30h] [rbp+A30h]
  const wchar_t *v220; // [rsp+B38h] [rbp+A38h]
  const wchar_t *v221; // [rsp+B40h] [rbp+A40h]
  const wchar_t *v222; // [rsp+B48h] [rbp+A48h]
  _BYTE v223[32]; // [rsp+B50h] [rbp+A50h] BYREF
  __int64 v224; // [rsp+B70h] [rbp+A70h]
  const wchar_t *v225; // [rsp+B78h] [rbp+A78h]
  const wchar_t *v226; // [rsp+B80h] [rbp+A80h]
  const wchar_t *v227; // [rsp+B88h] [rbp+A88h]
  _BYTE v228[32]; // [rsp+B90h] [rbp+A90h] BYREF
  __int64 v229; // [rsp+BB0h] [rbp+AB0h]
  const wchar_t *v230; // [rsp+BB8h] [rbp+AB8h]
  const wchar_t *v231; // [rsp+BC0h] [rbp+AC0h]
  const wchar_t *v232; // [rsp+BC8h] [rbp+AC8h]
  _BYTE v233[32]; // [rsp+BD0h] [rbp+AD0h] BYREF
  __int64 v234; // [rsp+BF0h] [rbp+AF0h]
  const wchar_t *v235; // [rsp+BF8h] [rbp+AF8h]
  const wchar_t *v236; // [rsp+C00h] [rbp+B00h]
  const wchar_t *v237; // [rsp+C08h] [rbp+B08h]
  _BYTE v238[32]; // [rsp+C10h] [rbp+B10h] BYREF
  __int64 v239; // [rsp+C30h] [rbp+B30h]
  const wchar_t *v240; // [rsp+C38h] [rbp+B38h]
  const wchar_t *v241; // [rsp+C40h] [rbp+B40h]
  const wchar_t *v242; // [rsp+C48h] [rbp+B48h]
  _BYTE v243[32]; // [rsp+C50h] [rbp+B50h] BYREF
  __int64 v244; // [rsp+C70h] [rbp+B70h]
  const wchar_t *v245; // [rsp+C78h] [rbp+B78h]
  const wchar_t *v246; // [rsp+C80h] [rbp+B80h]
  const wchar_t *v247; // [rsp+C88h] [rbp+B88h]
  _BYTE v248[32]; // [rsp+C90h] [rbp+B90h] BYREF
  __int64 v249; // [rsp+CB0h] [rbp+BB0h]
  const wchar_t *v250; // [rsp+CB8h] [rbp+BB8h]
  const wchar_t *v251; // [rsp+CC0h] [rbp+BC0h]
  const wchar_t *v252; // [rsp+CC8h] [rbp+BC8h]
  _BYTE v253[32]; // [rsp+CD0h] [rbp+BD0h] BYREF
  __int64 v254; // [rsp+CF0h] [rbp+BF0h]
  const wchar_t *v255; // [rsp+CF8h] [rbp+BF8h]
  const wchar_t *v256; // [rsp+D00h] [rbp+C00h]
  const wchar_t *v257; // [rsp+D08h] [rbp+C08h]
  _BYTE v258[32]; // [rsp+D10h] [rbp+C10h] BYREF
  __int64 v259; // [rsp+D30h] [rbp+C30h]
  const wchar_t *v260; // [rsp+D38h] [rbp+C38h]
  const wchar_t *v261; // [rsp+D40h] [rbp+C40h]
  const wchar_t *v262; // [rsp+D48h] [rbp+C48h]
  _BYTE v263[32]; // [rsp+D50h] [rbp+C50h] BYREF
  __int64 v264; // [rsp+D70h] [rbp+C70h]
  const wchar_t *v265; // [rsp+D78h] [rbp+C78h]
  const wchar_t *v266; // [rsp+D80h] [rbp+C80h]
  const wchar_t *v267; // [rsp+D88h] [rbp+C88h]
  _BYTE v268[32]; // [rsp+D90h] [rbp+C90h] BYREF
  __int64 v269; // [rsp+DB0h] [rbp+CB0h]
  const wchar_t *v270; // [rsp+DB8h] [rbp+CB8h]
  const wchar_t *v271; // [rsp+DC0h] [rbp+CC0h]
  const wchar_t *v272; // [rsp+DC8h] [rbp+CC8h]
  _BYTE v273[32]; // [rsp+DD0h] [rbp+CD0h] BYREF
  __int64 v274; // [rsp+DF0h] [rbp+CF0h]
  const wchar_t *v275; // [rsp+DF8h] [rbp+CF8h]
  const wchar_t *v276; // [rsp+E00h] [rbp+D00h]
  const wchar_t *v277; // [rsp+E08h] [rbp+D08h]
  _BYTE v278[32]; // [rsp+E10h] [rbp+D10h] BYREF
  __int64 v279; // [rsp+E30h] [rbp+D30h]
  const wchar_t *v280; // [rsp+E38h] [rbp+D38h]
  const wchar_t *v281; // [rsp+E40h] [rbp+D40h]
  const wchar_t *v282; // [rsp+E48h] [rbp+D48h]
  _BYTE v283[32]; // [rsp+E50h] [rbp+D50h] BYREF
  __int64 v284; // [rsp+E70h] [rbp+D70h]
  const wchar_t *v285; // [rsp+E78h] [rbp+D78h]
  const wchar_t *v286; // [rsp+E80h] [rbp+D80h]
  const wchar_t *v287; // [rsp+E88h] [rbp+D88h]
  _BYTE v288[32]; // [rsp+E90h] [rbp+D90h] BYREF
  __int64 v289; // [rsp+EB0h] [rbp+DB0h]
  const wchar_t *v290; // [rsp+EB8h] [rbp+DB8h]
  const wchar_t *v291; // [rsp+EC0h] [rbp+DC0h]
  const wchar_t *v292; // [rsp+EC8h] [rbp+DC8h]
  _BYTE v293[32]; // [rsp+ED0h] [rbp+DD0h] BYREF
  __int64 v294; // [rsp+EF0h] [rbp+DF0h]
  const wchar_t *v295; // [rsp+EF8h] [rbp+DF8h]
  const wchar_t *v296; // [rsp+F00h] [rbp+E00h]
  const wchar_t *v297; // [rsp+F08h] [rbp+E08h]
  _BYTE v298[32]; // [rsp+F10h] [rbp+E10h] BYREF
  __int64 v299; // [rsp+F30h] [rbp+E30h]
  const wchar_t *v300; // [rsp+F38h] [rbp+E38h]
  const wchar_t *v301; // [rsp+F40h] [rbp+E40h]
  const wchar_t *v302; // [rsp+F48h] [rbp+E48h]
  _BYTE v303[32]; // [rsp+F50h] [rbp+E50h] BYREF
  __int64 v304; // [rsp+F70h] [rbp+E70h]
  const wchar_t *v305; // [rsp+F78h] [rbp+E78h]
  const wchar_t *v306; // [rsp+F80h] [rbp+E80h]
  const wchar_t *v307; // [rsp+F88h] [rbp+E88h]
  _BYTE v308[32]; // [rsp+F90h] [rbp+E90h] BYREF
  __int64 v309; // [rsp+FB0h] [rbp+EB0h]
  const wchar_t *v310; // [rsp+FB8h] [rbp+EB8h]
  const wchar_t *v311; // [rsp+FC0h] [rbp+EC0h]
  const wchar_t *v312; // [rsp+FC8h] [rbp+EC8h]
  _BYTE v313[32]; // [rsp+FD0h] [rbp+ED0h] BYREF
  __int64 v314; // [rsp+FF0h] [rbp+EF0h]
  const wchar_t *v315; // [rsp+FF8h] [rbp+EF8h]
  const wchar_t *v316; // [rsp+1000h] [rbp+F00h]
  const wchar_t *v317; // [rsp+1008h] [rbp+F08h]
  _BYTE v318[32]; // [rsp+1010h] [rbp+F10h] BYREF
  __int64 v319; // [rsp+1030h] [rbp+F30h]
  const wchar_t *v320; // [rsp+1038h] [rbp+F38h]
  const wchar_t *v321; // [rsp+1040h] [rbp+F40h]
  const wchar_t *v322; // [rsp+1048h] [rbp+F48h]
  _BYTE v323[32]; // [rsp+1050h] [rbp+F50h] BYREF
  __int64 v324; // [rsp+1070h] [rbp+F70h]
  const wchar_t *v325; // [rsp+1078h] [rbp+F78h]
  const wchar_t *v326; // [rsp+1080h] [rbp+F80h]
  const wchar_t *v327; // [rsp+1088h] [rbp+F88h]
  _BYTE v328[32]; // [rsp+1090h] [rbp+F90h] BYREF
  __int64 v329; // [rsp+10B0h] [rbp+FB0h]
  const wchar_t *v330; // [rsp+10B8h] [rbp+FB8h]
  const wchar_t *v331; // [rsp+10C0h] [rbp+FC0h]
  const wchar_t *v332; // [rsp+10C8h] [rbp+FC8h]
  _BYTE v333[32]; // [rsp+10D0h] [rbp+FD0h] BYREF
  __int64 v334; // [rsp+10F0h] [rbp+FF0h]
  const wchar_t *v335; // [rsp+10F8h] [rbp+FF8h]
  const wchar_t *v336; // [rsp+1100h] [rbp+1000h]
  const wchar_t *v337; // [rsp+1108h] [rbp+1008h]
  _BYTE v338[32]; // [rsp+1110h] [rbp+1010h] BYREF
  __int64 v339; // [rsp+1130h] [rbp+1030h]
  const wchar_t *v340; // [rsp+1138h] [rbp+1038h]
  const wchar_t *v341; // [rsp+1140h] [rbp+1040h]
  const wchar_t *v342; // [rsp+1148h] [rbp+1048h]
  _BYTE v343[32]; // [rsp+1150h] [rbp+1050h] BYREF
  __int64 v344; // [rsp+1170h] [rbp+1070h]
  const wchar_t *v345; // [rsp+1178h] [rbp+1078h]
  const wchar_t *v346; // [rsp+1180h] [rbp+1080h]
  const wchar_t *v347; // [rsp+1188h] [rbp+1088h]
  _BYTE v348[32]; // [rsp+1190h] [rbp+1090h] BYREF
  __int64 v349; // [rsp+11B0h] [rbp+10B0h]
  const wchar_t *v350; // [rsp+11B8h] [rbp+10B8h]
  const wchar_t *v351; // [rsp+11C0h] [rbp+10C0h]
  const wchar_t *v352; // [rsp+11C8h] [rbp+10C8h]
  _BYTE v353[32]; // [rsp+11D0h] [rbp+10D0h] BYREF
  __int64 v354; // [rsp+11F0h] [rbp+10F0h]
  const wchar_t *v355; // [rsp+11F8h] [rbp+10F8h]
  const wchar_t *v356; // [rsp+1200h] [rbp+1100h]
  const wchar_t *v357; // [rsp+1208h] [rbp+1108h]
  _BYTE v358[32]; // [rsp+1210h] [rbp+1110h] BYREF
  __int64 v359; // [rsp+1230h] [rbp+1130h]
  const wchar_t *v360; // [rsp+1238h] [rbp+1138h]
  const wchar_t *v361; // [rsp+1240h] [rbp+1140h]
  const wchar_t *v362; // [rsp+1248h] [rbp+1148h]
  _BYTE v363[32]; // [rsp+1250h] [rbp+1150h] BYREF
  __int64 v364; // [rsp+1270h] [rbp+1170h]
  const wchar_t *v365; // [rsp+1278h] [rbp+1178h]
  const wchar_t *v366; // [rsp+1280h] [rbp+1180h]
  const wchar_t *v367; // [rsp+1288h] [rbp+1188h]
  _BYTE v368[32]; // [rsp+1290h] [rbp+1190h] BYREF
  __int64 v369; // [rsp+12B0h] [rbp+11B0h]
  const wchar_t *v370; // [rsp+12B8h] [rbp+11B8h]
  const wchar_t *v371; // [rsp+12C0h] [rbp+11C0h]
  const wchar_t *v372; // [rsp+12C8h] [rbp+11C8h]
  _BYTE v373[32]; // [rsp+12D0h] [rbp+11D0h] BYREF
  __int64 v374; // [rsp+12F0h] [rbp+11F0h]
  const wchar_t *v375; // [rsp+12F8h] [rbp+11F8h]
  const wchar_t *v376; // [rsp+1300h] [rbp+1200h]
  const wchar_t *v377; // [rsp+1308h] [rbp+1208h]
  _BYTE v378[32]; // [rsp+1310h] [rbp+1210h] BYREF
  __int64 v379; // [rsp+1330h] [rbp+1230h]
  const wchar_t *v380; // [rsp+1338h] [rbp+1238h]
  const wchar_t *v381; // [rsp+1340h] [rbp+1240h]
  const wchar_t *v382; // [rsp+1348h] [rbp+1248h]
  _BYTE v383[32]; // [rsp+1350h] [rbp+1250h] BYREF
  __int64 v384; // [rsp+1370h] [rbp+1270h]
  const wchar_t *v385; // [rsp+1378h] [rbp+1278h]
  const wchar_t *v386; // [rsp+1380h] [rbp+1280h]
  const wchar_t *v387; // [rsp+1388h] [rbp+1288h]
  _BYTE v388[32]; // [rsp+1390h] [rbp+1290h] BYREF
  __int64 v389; // [rsp+13B0h] [rbp+12B0h]
  const wchar_t *v390; // [rsp+13B8h] [rbp+12B8h]
  const wchar_t *v391; // [rsp+13C0h] [rbp+12C0h]
  const wchar_t *v392; // [rsp+13C8h] [rbp+12C8h]
  _BYTE v393[32]; // [rsp+13D0h] [rbp+12D0h] BYREF
  __int64 v394; // [rsp+13F0h] [rbp+12F0h]
  const wchar_t *v395; // [rsp+13F8h] [rbp+12F8h]
  const wchar_t *v396; // [rsp+1400h] [rbp+1300h]
  const wchar_t *v397; // [rsp+1408h] [rbp+1308h]
  _BYTE v398[32]; // [rsp+1410h] [rbp+1310h] BYREF
  __int64 v399; // [rsp+1430h] [rbp+1330h]
  const wchar_t *v400; // [rsp+1438h] [rbp+1338h]
  const wchar_t *v401; // [rsp+1440h] [rbp+1340h]
  const wchar_t *v402; // [rsp+1448h] [rbp+1348h]
  _BYTE v403[32]; // [rsp+1450h] [rbp+1350h] BYREF
  __int64 v404; // [rsp+1470h] [rbp+1370h]
  const wchar_t *v405; // [rsp+1478h] [rbp+1378h]
  const wchar_t *v406; // [rsp+1480h] [rbp+1380h]
  const wchar_t *v407; // [rsp+1488h] [rbp+1388h]
  _BYTE v408[32]; // [rsp+1490h] [rbp+1390h] BYREF
  __int64 v409; // [rsp+14B0h] [rbp+13B0h]
  const wchar_t *v410; // [rsp+14B8h] [rbp+13B8h]
  const wchar_t *v411; // [rsp+14C0h] [rbp+13C0h]
  const wchar_t *v412; // [rsp+14C8h] [rbp+13C8h]
  _BYTE v413[32]; // [rsp+14D0h] [rbp+13D0h] BYREF
  __int64 v414; // [rsp+14F0h] [rbp+13F0h]
  const wchar_t *v415; // [rsp+14F8h] [rbp+13F8h]
  const wchar_t *v416; // [rsp+1500h] [rbp+1400h]
  const wchar_t *v417; // [rsp+1508h] [rbp+1408h]
  _BYTE v418[32]; // [rsp+1510h] [rbp+1410h] BYREF
  __int64 v419; // [rsp+1530h] [rbp+1430h]
  const wchar_t *v420; // [rsp+1538h] [rbp+1438h]
  const wchar_t *v421; // [rsp+1540h] [rbp+1440h]
  const wchar_t *v422; // [rsp+1548h] [rbp+1448h]
  _BYTE v423[32]; // [rsp+1550h] [rbp+1450h] BYREF
  __int64 v424; // [rsp+1570h] [rbp+1470h]
  const wchar_t *v425; // [rsp+1578h] [rbp+1478h]
  const wchar_t *v426; // [rsp+1580h] [rbp+1480h]
  const wchar_t *v427; // [rsp+1588h] [rbp+1488h]
  _BYTE v428[32]; // [rsp+1590h] [rbp+1490h] BYREF
  __int64 v429; // [rsp+15B0h] [rbp+14B0h]
  const wchar_t *v430; // [rsp+15B8h] [rbp+14B8h]
  const wchar_t *v431; // [rsp+15C0h] [rbp+14C0h]
  const wchar_t *v432; // [rsp+15C8h] [rbp+14C8h]
  _BYTE v433[32]; // [rsp+15D0h] [rbp+14D0h] BYREF
  __int64 v434; // [rsp+15F0h] [rbp+14F0h]
  const wchar_t *v435; // [rsp+15F8h] [rbp+14F8h]
  const wchar_t *v436; // [rsp+1600h] [rbp+1500h]
  const wchar_t *v437; // [rsp+1608h] [rbp+1508h]
  _BYTE v438[32]; // [rsp+1610h] [rbp+1510h] BYREF
  __int64 v439; // [rsp+1630h] [rbp+1530h]
  const wchar_t *v440; // [rsp+1638h] [rbp+1538h]
  const wchar_t *v441; // [rsp+1640h] [rbp+1540h]
  const wchar_t *v442; // [rsp+1648h] [rbp+1548h]
  _BYTE v443[32]; // [rsp+1650h] [rbp+1550h] BYREF
  __int64 v444; // [rsp+1670h] [rbp+1570h]
  const wchar_t *v445; // [rsp+1678h] [rbp+1578h]
  const wchar_t *v446; // [rsp+1680h] [rbp+1580h]
  const wchar_t *v447; // [rsp+1688h] [rbp+1588h]
  _BYTE v448[32]; // [rsp+1690h] [rbp+1590h] BYREF
  __int64 v449; // [rsp+16B0h] [rbp+15B0h]
  const wchar_t *v450; // [rsp+16B8h] [rbp+15B8h]
  const wchar_t *v451; // [rsp+16C0h] [rbp+15C0h]
  const wchar_t *v452; // [rsp+16C8h] [rbp+15C8h]
  _BYTE v453[32]; // [rsp+16D0h] [rbp+15D0h] BYREF
  __int64 v454; // [rsp+16F0h] [rbp+15F0h]
  const wchar_t *v455; // [rsp+16F8h] [rbp+15F8h]
  const wchar_t *v456; // [rsp+1700h] [rbp+1600h]
  const wchar_t *v457; // [rsp+1708h] [rbp+1608h]
  _BYTE v458[32]; // [rsp+1710h] [rbp+1610h] BYREF
  __int64 v459; // [rsp+1730h] [rbp+1630h]
  const wchar_t *v460; // [rsp+1738h] [rbp+1638h]
  const wchar_t *v461; // [rsp+1740h] [rbp+1640h]
  const wchar_t *v462; // [rsp+1748h] [rbp+1648h]
  _BYTE v463[32]; // [rsp+1750h] [rbp+1650h] BYREF
  __int64 v464; // [rsp+1770h] [rbp+1670h]
  const wchar_t *v465; // [rsp+1778h] [rbp+1678h]
  const wchar_t *v466; // [rsp+1780h] [rbp+1680h]
  const wchar_t *v467; // [rsp+1788h] [rbp+1688h]
  _BYTE v468[32]; // [rsp+1790h] [rbp+1690h] BYREF
  __int64 v469; // [rsp+17B0h] [rbp+16B0h] BYREF

  v2[0] = 3;
  v2[1] = L"%systemroot%\\winsxs\\*\\bcdboot.exe";
  v2[2] = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v2[3] = L"*";
  std::wstring::wstring(v3, L"*");
  v4 = 3;
  v5 = L"%systemroot%\\winsxs\\*\\bcdedit.exe";
  v6 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v7 = L"*";
  std::wstring::wstring(v8, L"*");
  v9 = 3;
  v10 = L"%systemroot%\\*\\cacls.exe";
  v11 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v12 = L"*";
  std::wstring::wstring(v13, L"*");
  v14 = 3;
  v15 = L"%systemroot%\\winsxs\\*\\cacls.exe";
  v16 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v17 = L"*";
  std::wstring::wstring(v18, L"*");
  v19 = 3;
  v20 = L"%systemroot%\\*\\calc.exe";
  v21 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v22 = L"*";
  std::wstring::wstring(v23, L"*");
  v24 = 3;
  v25 = L"%systemroot%\\winsxs\\*\\calc.exe";
  v26 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v27 = L"*";
  std::wstring::wstring(v28, L"*");
  v29 = 3;
  v30 = L"%systemroot%\\winsxs\\*\\change.exe";
  v31 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v32 = L"*";
  std::wstring::wstring(v33, L"*");
  v34 = 3;
  v35 = L"%systemroot%\\winsxs\\*\\changepk.exe";
  v36 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v37 = L"*";
  std::wstring::wstring(v38, L"*");
  v39 = 3;
  v40 = L"%systemroot%\\*\\charmap.exe";
  v41 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v42 = L"*";
  std::wstring::wstring(v43, L"*");
  v44 = 3;
  v45 = L"%systemroot%\\winsxs\\*\\charmap.exe";
  v46 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v47 = L"*";
  std::wstring::wstring(v48, L"*");
  v49 = 3;
  v50 = L"%systemroot%\\*\\chkdsk.exe";
  v51 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v52 = L"*";
  std::wstring::wstring(v53, L"*");
  v54 = 3;
  v55 = L"%systemroot%\\winsxs\\*\\chkdsk.exe";
  v56 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v57 = L"*";
  std::wstring::wstring(v58, L"*");
  v59 = 3;
  v60 = L"%systemroot%\\*\\cleanmgr.exe";
  v61 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v62 = L"*";
  std::wstring::wstring(v63, L"*");
  v64 = 3;
  v65 = L"%systemroot%\\winsxs\\*\\cleanmgr.exe";
  v66 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v67 = L"*";
  std::wstring::wstring(v68, L"*");
  v69 = 3;
  v70 = L"%systemroot%\\*\\cmd.exe";
  v71 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v72 = L"*";
  std::wstring::wstring(v73, L"*");
  v74 = 3;
  v75 = L"%systemroot%\\winsxs\\*\\cmd.exe";
  v76 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v77 = L"*";
  std::wstring::wstring(v78, L"*");
  v79 = 3;
  v80 = L"%systemroot%\\*\\cmdkey.exe";
  v81 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v82 = L"*";
  std::wstring::wstring(v83, L"*");
  v84 = 3;
  v85 = L"%systemroot%\\winsxs\\*\\cmdkey.exe";
  v86 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v87 = L"*";
  std::wstring::wstring(v88, L"*");
  v89 = 3;
  v90 = L"%systemroot%\\*\\control.exe";
  v91 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v92 = L"*";
  std::wstring::wstring(v93, L"*");
  v94 = 3;
  v95 = L"%systemroot%\\winsxs\\*\\control.exe";
  v96 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v97 = L"*";
  std::wstring::wstring(v98, L"*");
  v99 = 3;
  v100 = L"%systemroot%\\*\\cscript.exe";
  v101 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v102 = L"*";
  std::wstring::wstring(v103, L"*");
  v104 = 3;
  v105 = L"%systemroot%\\winsxs\\*\\cscript.exe";
  v106 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v107 = L"*";
  std::wstring::wstring(v108, L"*");
  v109 = 3;
  v110 = L"%systemroot%\\*\\dialer.exe";
  v111 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v112 = L"*";
  std::wstring::wstring(v113, L"*");
  v114 = 3;
  v115 = L"%systemroot%\\winsxs\\*\\dialer.exe";
  v116 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v117 = L"*";
  std::wstring::wstring(v118, L"*");
  v119 = 3;
  v120 = L"%systemroot%\\*\\doskey.exe";
  v121 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v122 = L"*";
  std::wstring::wstring(v123, L"*");
  v124 = 3;
  v125 = L"%systemroot%\\winsxs\\*\\doskey.exe";
  v126 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v127 = L"*";
  std::wstring::wstring(v128, L"*");
  v129 = 3;
  v130 = L"%systemroot%\\*\\dfrgui.exe";
  v131 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v132 = L"*";
  std::wstring::wstring(v133, L"*");
  v134 = 3;
  v135 = L"%systemroot%\\winsxs\\*\\dfrgui.exe";
  v136 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v137 = L"*";
  std::wstring::wstring(v138, L"*");
  v139 = 3;
  v140 = L"%systemroot%\\*\\icacls.exe";
  v141 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v142 = L"*";
  std::wstring::wstring(v143, L"*");
  v144 = 3;
  v145 = L"%systemroot%\\winsxs\\*\\icacls.exe";
  v146 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v147 = L"*";
  std::wstring::wstring(v148, L"*");
  v149 = 3;
  v150 = L"%systemroot%\\winsxs\\*\\iexplore.exe";
  v151 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v152 = L"*";
  std::wstring::wstring(v153, L"*");
  v154 = 3;
  v155 = L"%systemroot%\\*\\iscsicpl.exe";
  v156 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v157 = L"*";
  std::wstring::wstring(v158, L"*");
  v159 = 3;
  v160 = L"%systemroot%\\winsxs\\*\\iscsicpl.exe";
  v161 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v162 = L"*";
  std::wstring::wstring(v163, L"*");
  v164 = 3;
  v165 = L"%systemroot%\\*\\fc.exe";
  v166 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v167 = L"*";
  std::wstring::wstring(v168, L"*");
  v169 = 3;
  v170 = L"%systemroot%\\winsxs\\*\\fc.exe";
  v171 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v172 = L"*";
  std::wstring::wstring(v173, L"*");
  v174 = 3;
  v175 = L"%systemroot%\\*\\find.exe";
  v176 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v177 = L"*";
  std::wstring::wstring(v178, L"*");
  v179 = 3;
  v180 = L"%systemroot%\\winsxs\\*\\find.exe";
  v181 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v182 = L"*";
  std::wstring::wstring(v183, L"*");
  v184 = 3;
  v185 = L"%systemroot%\\*\\findstr.exe";
  v186 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v187 = L"*";
  std::wstring::wstring(v188, L"*");
  v189 = 3;
  v190 = L"%systemroot%\\winsxs\\*\\findstr.exe";
  v191 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v192 = L"*";
  std::wstring::wstring(v193, L"*");
  v194 = 3;
  v195 = L"%systemroot%\\winsxs\\*\\helppane.exe";
  v196 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v197 = L"*";
  std::wstring::wstring(v198, L"*");
  v199 = 3;
  v200 = L"%systemroot%\\winsxs\\*\\klist.exe";
  v201 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v202 = L"*";
  std::wstring::wstring(v203, L"*");
  v204 = 3;
  v205 = L"%systemroot%\\winsxs\\*\\logoff.exe";
  v206 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v207 = L"*";
  std::wstring::wstring(v208, L"*");
  v209 = 3;
  v210 = L"%systemroot%\\winsxs\\*\\mdsched.exe";
  v211 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v212 = L"*";
  std::wstring::wstring(v213, L"*");
  v214 = 3;
  v215 = L"%systemroot%\\winsxs\\*\\mip.exe";
  v216 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v217 = L"*";
  std::wstring::wstring(v218, L"*");
  v219 = 3;
  v220 = L"%systemroot%\\*\\mmc.exe";
  v221 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v222 = L"*";
  std::wstring::wstring(v223, L"*");
  v224 = 3;
  v225 = L"%systemroot%\\winsxs\\*\\mmc.exe";
  v226 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v227 = L"*";
  std::wstring::wstring(v228, L"*");
  v229 = 3;
  v230 = L"%systemroot%\\winsxs\\*\\msconfig.exe";
  v231 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v232 = L"*";
  std::wstring::wstring(v233, L"*");
  v234 = 3;
  v235 = L"%systemroot%\\*\\mspaint.exe";
  v236 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v237 = L"*";
  std::wstring::wstring(v238, L"*");
  v239 = 3;
  v240 = L"%systemroot%\\winsxs\\*\\mspaint.exe";
  v241 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v242 = L"*";
  std::wstring::wstring(v243, L"*");
  v244 = 3;
  v245 = L"%systemroot%\\*\\mstsc.exe";
  v246 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v247 = L"*";
  std::wstring::wstring(v248, L"*");
  v249 = 3;
  v250 = L"%systemroot%\\winsxs\\*\\mstsc.exe";
  v251 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v252 = L"*";
  std::wstring::wstring(v253, L"*");
  v254 = 3;
  v255 = L"%systemroot%\\*\\net.exe";
  v256 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v257 = L"*";
  std::wstring::wstring(v258, L"*");
  v259 = 3;
  v260 = L"%systemroot%\\winsxs\\*\\net.exe";
  v261 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v262 = L"*";
  std::wstring::wstring(v263, L"*");
  v264 = 3;
  v265 = L"%systemroot%\\*\\net1.exe";
  v266 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v267 = L"*";
  std::wstring::wstring(v268, L"*");
  v269 = 3;
  v270 = L"%systemroot%\\winsxs\\*\\net1.exe";
  v271 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v272 = L"*";
  std::wstring::wstring(v273, L"*");
  v274 = 3;
  v275 = L"%systemroot%\\*\\notepad.exe";
  v276 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v277 = L"*";
  std::wstring::wstring(v278, L"*");
  v279 = 3;
  v280 = L"%systemroot%\\winsxs\\*\\notepad.exe";
  v281 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v282 = L"*";
  std::wstring::wstring(v283, L"*");
  v284 = 3;
  v285 = L"%systemroot%\\*\\odbcad32.exe";
  v286 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v287 = L"*";
  std::wstring::wstring(v288, L"*");
  v289 = 3;
  v290 = L"%systemroot%\\winsxs\\*\\odbcad32.exe";
  v291 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v292 = L"*";
  std::wstring::wstring(v293, L"*");
  v294 = 3;
  v295 = L"%systemroot%\\*\\windowspowershell\\v1.0\\powershell*.exe";
  v296 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v297 = L"*";
  std::wstring::wstring(v298, L"*");
  v299 = 3;
  v300 = L"%systemroot%\\winsxs\\*\\powershell*.exe";
  v301 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v302 = L"*";
  std::wstring::wstring(v303, L"*");
  v304 = 3;
  v305 = L"%systemroot%\\*\\perfmon.exe";
  v306 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v307 = L"*";
  std::wstring::wstring(v308, L"*");
  v309 = 3;
  v310 = L"%systemroot%\\winsxs\\*\\perfmon.exe";
  v311 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v312 = L"*";
  std::wstring::wstring(v313, L"*");
  v314 = 3;
  v315 = L"%systemroot%\\*\\psr.exe";
  v316 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v317 = L"*";
  std::wstring::wstring(v318, L"*");
  v319 = 3;
  v320 = L"%systemroot%\\winsxs\\*\\psr.exe";
  v321 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v322 = L"*";
  std::wstring::wstring(v323, L"*");
  v324 = 3;
  v325 = L"%systemroot%\\*\\quickassist.exe";
  v326 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v327 = L"*";
  std::wstring::wstring(v328, L"*");
  v329 = 3;
  v330 = L"%systemroot%\\winsxs\\*\\quickassist.exe";
  v331 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v332 = L"*";
  std::wstring::wstring(v333, L"*");
  v334 = 3;
  v335 = L"%systemroot%\\winsxs\\*\\recoverydrive.exe";
  v336 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v337 = L"*";
  std::wstring::wstring(v338, L"*");
  v339 = 3;
  v340 = L"%systemroot%\\winsxs\\*\\recdisc.exe";
  v341 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v342 = L"*";
  std::wstring::wstring(v343, L"*");
  v344 = 3;
  v345 = L"%systemroot%\\*\\reg.exe";
  v346 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v347 = L"*";
  std::wstring::wstring(v348, L"*");
  v349 = 3;
  v350 = L"%systemroot%\\winsxs\\*\\reg.exe";
  v351 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v352 = L"*";
  std::wstring::wstring(v353, L"*");
  v354 = 3;
  v355 = L"%systemroot%\\*\\regedit.exe";
  v356 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v357 = L"*";
  std::wstring::wstring(v358, L"*");
  v359 = 3;
  v360 = L"%systemroot%\\winsxs\\*\\regedit.exe";
  v361 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v362 = L"*";
  std::wstring::wstring(v363, L"*");
  v364 = 3;
  v365 = L"%systemroot%\\winsxs\\*\\sapisvr.exe";
  v366 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v367 = L"*";
  std::wstring::wstring(v368, L"*");
  v369 = 3;
  v370 = L"%systemroot%\\*\\shutdown.exe";
  v371 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v372 = L"*";
  std::wstring::wstring(v373, L"*");
  v374 = 3;
  v375 = L"%systemroot%\\winsxs\\*\\shutdown.exe";
  v376 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v377 = L"*";
  std::wstring::wstring(v378, L"*");
  v379 = 3;
  v380 = L"%systemroot%\\winsxs\\*\\snippingtool.exe";
  v381 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v382 = L"*";
  std::wstring::wstring(v383, L"*");
  v384 = 3;
  v385 = L"%systemroot%\\*\\takeown.exe";
  v386 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v387 = L"*";
  std::wstring::wstring(v388, L"*");
  v389 = 3;
  v390 = L"%systemroot%\\winsxs\\*\\takeown.exe";
  v391 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v392 = L"*";
  std::wstring::wstring(v393, L"*");
  v394 = 3;
  v395 = L"%systemroot%\\*\\taskkill.exe";
  v396 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v397 = L"*";
  std::wstring::wstring(v398, L"*");
  v399 = 3;
  v400 = L"%systemroot%\\winsxs\\*\\taskkill.exe";
  v401 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v402 = L"*";
  std::wstring::wstring(v403, L"*");
  v404 = 3;
  v405 = L"%systemroot%\\*\\tasklist.exe";
  v406 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v407 = L"*";
  std::wstring::wstring(v408, L"*");
  v409 = 3;
  v410 = L"%systemroot%\\winsxs\\*\\tasklist.exe";
  v411 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v412 = L"*";
  std::wstring::wstring(v413, L"*");
  v414 = 3;
  v415 = L"%systemroot%\\*\\taskmgr.exe";
  v416 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v417 = L"*";
  std::wstring::wstring(v418, L"*");
  v419 = 3;
  v420 = L"%systemroot%\\winsxs\\*\\taskmgr.exe";
  v421 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v422 = L"*";
  std::wstring::wstring(v423, L"*");
  v424 = 3;
  v425 = L"%systemroot%\\winsxs\\*\\wfs.exe";
  v426 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v427 = L"*";
  std::wstring::wstring(v428, L"*");
  v429 = 3;
  v430 = L"%systemroot%\\*\\where.exe";
  v431 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v432 = L"*";
  std::wstring::wstring(v433, L"*");
  v434 = 3;
  v435 = L"%systemroot%\\winsxs\\*\\where.exe";
  v436 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v437 = L"*";
  std::wstring::wstring(v438, L"*");
  v439 = 3;
  v440 = L"%systemroot%\\*\\write.exe";
  v441 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v442 = L"*";
  std::wstring::wstring(v443, L"*");
  v444 = 3;
  v445 = L"%systemroot%\\winsxs\\*\\write.exe";
  v446 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v447 = L"*";
  std::wstring::wstring(v448, L"*");
  v449 = 3;
  v450 = L"%systemroot%\\winsxs\\*\\wmplayer.exe";
  v451 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v452 = L"*";
  std::wstring::wstring(v453, L"*");
  v454 = 3;
  v455 = L"%systemroot%\\winsxs\\*\\wordpad.exe";
  v456 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v457 = L"*";
  std::wstring::wstring(v458, L"*");
  v459 = 3;
  v460 = L"%systemroot%\\*\\xcopy.exe";
  v461 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v462 = L"*";
  std::wstring::wstring(v463, L"*");
  v464 = 3;
  v465 = L"%systemroot%\\winsxs\\*\\xcopy.exe";
  v466 = L"O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US";
  v467 = L"*";
  std::wstring::wstring(v468, L"*");
  v1[0] = v2;
  v1[1] = &v469;
  std::vector<Windows::Internal::AssignedAccess::RawAppData>::vector<Windows::Internal::AssignedAccess::RawAppData>(
    &Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataListWildcard,
    v1);
  `eh vector destructor iterator'(
    v2,
    0x40u,
    0x5Eu,
    (void (*)(void *))Windows::Internal::AssignedAccess::RawAppData::~RawAppData);
  return atexit(dynamic_atexit_destructor_for__Windows::Internal::AssignedAccess::DefaultAppDenyListBuilderForDesktop::c_rawAppDataListWildcard__);
}

```

## disassembly

```asm
0x180004970  push    rbp
0x180004972  push    rbx
0x180004973  push    rsi
0x180004974  push    rdi
0x180004975  lea     rbp, [rsp-16C8h]
0x18000497d  mov     eax, 17C8h
0x180004982  call    _alloca_probe
0x180004987  sub     rsp, rax
0x18000498a  mov     rax, cs:__security_cookie
0x180004991  xor     rax, rsp
0x180004994  mov     [rbp+16E0h+var_30], rax
0x18000499b  mov     [rsp+17E0h+var_17B0], 3
0x1800049a4  lea     rax, aSystemrootWins; "%systemroot%\\winsxs\\*\\bcdboot.exe"
0x1800049ab  mov     [rsp+17E0h+var_17A8], rax
0x1800049b0  lea     rbx, aOMicrosoftCorp; "O=MICROSOFT CORPORATION, L=REDMOND, S=W"...
0x1800049b7  mov     [rsp+17E0h+var_17A0], rbx
0x1800049bc  lea     rdi, asc_1800A7204; "*"
0x1800049c3  mov     [rsp+17E0h+var_1798], rdi
0x1800049c8  mov     rdx, rdi
0x1800049cb  lea     rcx, [rsp+17E0h+var_1790]
0x1800049d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800049d5  nop
0x1800049d6  mov     [rsp+17E0h+var_1770], 3
0x1800049df  lea     rax, aSystemrootWins_37; "%systemroot%\\winsxs\\*\\bcdedit.exe"
0x1800049e6  mov     [rsp+17E0h+var_1768], rax
0x1800049eb  mov     [rbp+16E0h+var_1760], rbx
0x1800049ef  mov     [rbp+16E0h+var_1758], rdi
0x1800049f3  mov     rdx, rdi
0x1800049f6  lea     rcx, [rbp+16E0h+var_1750]
0x1800049fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800049ff  nop
0x180004a00  mov     [rbp+16E0h+var_1730], 3
0x180004a08  lea     rax, aSystemrootCacl; "%systemroot%\\*\\cacls.exe"
0x180004a0f  mov     [rbp+16E0h+var_1728], rax
0x180004a13  mov     [rbp+16E0h+var_1720], rbx
0x180004a17  mov     [rbp+16E0h+var_1718], rdi
0x180004a1b  mov     rdx, rdi
0x180004a1e  lea     rcx, [rbp+16E0h+var_1710]
0x180004a22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004a27  nop
0x180004a28  mov     [rbp+16E0h+var_16F0], 3
0x180004a30  lea     rax, aSystemrootWins_38; "%systemroot%\\winsxs\\*\\cacls.exe"
0x180004a37  mov     [rbp+16E0h+var_16E8], rax
0x180004a3b  mov     [rbp+16E0h+var_16E0], rbx
0x180004a3f  mov     [rbp+16E0h+var_16D8], rdi
0x180004a43  mov     rdx, rdi
0x180004a46  lea     rcx, [rbp+16E0h+var_16D0]
0x180004a4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004a4f  nop
0x180004a50  mov     [rbp+16E0h+var_16B0], 3
0x180004a58  lea     rax, aSystemrootCalc; "%systemroot%\\*\\calc.exe"
0x180004a5f  mov     [rbp+16E0h+var_16A8], rax
0x180004a63  mov     [rbp+16E0h+var_16A0], rbx
0x180004a67  mov     [rbp+16E0h+var_1698], rdi
0x180004a6b  mov     rdx, rdi
0x180004a6e  lea     rcx, [rbp+16E0h+var_1690]
0x180004a72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004a77  nop
0x180004a78  mov     [rbp+16E0h+var_1670], 3
0x180004a80  lea     rax, aSystemrootWins_8; "%systemroot%\\winsxs\\*\\calc.exe"
0x180004a87  mov     [rbp+16E0h+var_1668], rax
0x180004a8b  mov     [rbp+16E0h+var_1660], rbx
0x180004a92  mov     [rbp+16E0h+var_1658], rdi
0x180004a99  mov     rdx, rdi
0x180004a9c  lea     rcx, [rbp+16E0h+var_1650]
0x180004aa3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004aa8  nop
0x180004aa9  mov     [rbp+16E0h+var_1630], 3
0x180004ab4  lea     rax, aSystemrootWins_1; "%systemroot%\\winsxs\\*\\change.exe"
0x180004abb  mov     [rbp+16E0h+var_1628], rax
0x180004ac2  mov     [rbp+16E0h+var_1620], rbx
0x180004ac9  mov     [rbp+16E0h+var_1618], rdi
0x180004ad0  mov     rdx, rdi
0x180004ad3  lea     rcx, [rbp+16E0h+var_1610]
0x180004ada  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004adf  nop
0x180004ae0  mov     [rbp+16E0h+var_15F0], 3
0x180004aeb  lea     rax, aSystemrootWins_33; "%systemroot%\\winsxs\\*\\changepk.exe"
0x180004af2  mov     [rbp+16E0h+var_15E8], rax
0x180004af9  mov     [rbp+16E0h+var_15E0], rbx
0x180004b00  mov     [rbp+16E0h+var_15D8], rdi
0x180004b07  mov     rdx, rdi
0x180004b0a  lea     rcx, [rbp+16E0h+var_15D0]
0x180004b11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004b16  nop
0x180004b17  mov     [rbp+16E0h+var_15B0], 3
0x180004b22  lea     rax, aSystemrootChar; "%systemroot%\\*\\charmap.exe"
0x180004b29  mov     [rbp+16E0h+var_15A8], rax
0x180004b30  mov     [rbp+16E0h+var_15A0], rbx
0x180004b37  mov     [rbp+16E0h+var_1598], rdi
0x180004b3e  mov     rdx, rdi
0x180004b41  lea     rcx, [rbp+16E0h+var_1590]
0x180004b48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004b4d  nop
0x180004b4e  mov     [rbp+16E0h+var_1570], 3
0x180004b59  lea     rax, aSystemrootWins_25; "%systemroot%\\winsxs\\*\\charmap.exe"
0x180004b60  mov     [rbp+16E0h+var_1568], rax
0x180004b67  mov     [rbp+16E0h+var_1560], rbx
0x180004b6e  mov     [rbp+16E0h+var_1558], rdi
0x180004b75  mov     rdx, rdi
0x180004b78  lea     rcx, [rbp+16E0h+var_1550]
0x180004b7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004b84  nop
0x180004b85  mov     [rbp+16E0h+var_1530], 3
0x180004b90  lea     rax, aSystemrootChkd; "%systemroot%\\*\\chkdsk.exe"
0x180004b97  mov     [rbp+16E0h+var_1528], rax
0x180004b9e  mov     [rbp+16E0h+var_1520], rbx
0x180004ba5  mov     [rbp+16E0h+var_1518], rdi
0x180004bac  mov     rdx, rdi
0x180004baf  lea     rcx, [rbp+16E0h+var_1510]
0x180004bb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004bbb  nop
0x180004bbc  mov     [rbp+16E0h+var_14F0], 3
0x180004bc7  lea     rax, aSystemrootWins_39; "%systemroot%\\winsxs\\*\\chkdsk.exe"
0x180004bce  mov     [rbp+16E0h+var_14E8], rax
0x180004bd5  mov     [rbp+16E0h+var_14E0], rbx
0x180004bdc  mov     [rbp+16E0h+var_14D8], rdi
0x180004be3  mov     rdx, rdi
0x180004be6  lea     rcx, [rbp+16E0h+var_14D0]
0x180004bed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004bf2  nop
0x180004bf3  mov     [rbp+16E0h+var_14B0], 3
0x180004bfe  lea     rax, aSystemrootClea; "%systemroot%\\*\\cleanmgr.exe"
0x180004c05  mov     [rbp+16E0h+var_14A8], rax
0x180004c0c  mov     [rbp+16E0h+var_14A0], rbx
0x180004c13  mov     [rbp+16E0h+var_1498], rdi
0x180004c1a  mov     rdx, rdi
0x180004c1d  lea     rcx, [rbp+16E0h+var_1490]
0x180004c24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004c29  nop
0x180004c2a  mov     [rbp+16E0h+var_1470], 3
0x180004c35  lea     rax, aSystemrootWins_30; "%systemroot%\\winsxs\\*\\cleanmgr.exe"
0x180004c3c  mov     [rbp+16E0h+var_1468], rax
0x180004c43  mov     [rbp+16E0h+var_1460], rbx
0x180004c4a  mov     [rbp+16E0h+var_1458], rdi
0x180004c51  mov     rdx, rdi
0x180004c54  lea     rcx, [rbp+16E0h+var_1450]
0x180004c5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004c60  nop
0x180004c61  mov     [rbp+16E0h+var_1430], 3
0x180004c6c  lea     rax, aSystemrootCmdE; "%systemroot%\\*\\cmd.exe"
0x180004c73  mov     [rbp+16E0h+var_1428], rax
0x180004c7a  mov     [rbp+16E0h+var_1420], rbx
0x180004c81  mov     [rbp+16E0h+var_1418], rdi
0x180004c88  mov     rdx, rdi
0x180004c8b  lea     rcx, [rbp+16E0h+var_1410]
0x180004c92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004c97  nop
0x180004c98  mov     [rbp+16E0h+var_13F0], 3
0x180004ca3  lea     rax, aSystemrootWins_49; "%systemroot%\\winsxs\\*\\cmd.exe"
0x180004caa  mov     [rbp+16E0h+var_13E8], rax
0x180004cb1  mov     [rbp+16E0h+var_13E0], rbx
0x180004cb8  mov     [rbp+16E0h+var_13D8], rdi
0x180004cbf  mov     rdx, rdi
0x180004cc2  lea     rcx, [rbp+16E0h+var_13D0]
0x180004cc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004cce  nop
0x180004ccf  mov     [rbp+16E0h+var_13B0], 3
0x180004cda  lea     rax, aSystemrootCmdk; "%systemroot%\\*\\cmdkey.exe"
0x180004ce1  mov     [rbp+16E0h+var_13A8], rax
0x180004ce8  mov     [rbp+16E0h+var_13A0], rbx
0x180004cef  mov     [rbp+16E0h+var_1398], rdi
0x180004cf6  mov     rdx, rdi
0x180004cf9  lea     rcx, [rbp+16E0h+var_1390]
0x180004d00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004d05  nop
0x180004d06  mov     [rbp+16E0h+var_1370], 3
0x180004d11  lea     rax, aSystemrootWins_27; "%systemroot%\\winsxs\\*\\cmdkey.exe"
0x180004d18  mov     [rbp+16E0h+var_1368], rax
0x180004d1f  mov     [rbp+16E0h+var_1360], rbx
0x180004d26  mov     [rbp+16E0h+var_1358], rdi
0x180004d2d  mov     rdx, rdi
0x180004d30  lea     rcx, [rbp+16E0h+var_1350]
0x180004d37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004d3c  nop
0x180004d3d  mov     [rbp+16E0h+var_1330], 3
0x180004d48  lea     rax, aSystemrootCont; "%systemroot%\\*\\control.exe"
0x180004d4f  mov     [rbp+16E0h+var_1328], rax
0x180004d56  mov     [rbp+16E0h+var_1320], rbx
0x180004d5d  mov     [rbp+16E0h+var_1318], rdi
0x180004d64  mov     rdx, rdi
0x180004d67  lea     rcx, [rbp+16E0h+var_1310]
0x180004d6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004d73  nop
0x180004d74  mov     [rbp+16E0h+var_12F0], 3
0x180004d7f  lea     rax, aSystemrootWins_45; "%systemroot%\\winsxs\\*\\control.exe"
0x180004d86  mov     [rbp+16E0h+var_12E8], rax
0x180004d8d  mov     [rbp+16E0h+var_12E0], rbx
0x180004d94  mov     [rbp+16E0h+var_12D8], rdi
0x180004d9b  mov     rdx, rdi
0x180004d9e  lea     rcx, [rbp+16E0h+var_12D0]
0x180004da5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004daa  nop
0x180004dab  mov     [rbp+16E0h+var_12B0], 3
0x180004db6  lea     rax, aSystemrootCscr; "%systemroot%\\*\\cscript.exe"
0x180004dbd  mov     [rbp+16E0h+var_12A8], rax
0x180004dc4  mov     [rbp+16E0h+var_12A0], rbx
0x180004dcb  mov     [rbp+16E0h+var_1298], rdi
0x180004dd2  mov     rdx, rdi
0x180004dd5  lea     rcx, [rbp+16E0h+var_1290]
0x180004ddc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004de1  nop
0x180004de2  mov     [rbp+16E0h+var_1270], 3
0x180004ded  lea     rax, aSystemrootWins_19; "%systemroot%\\winsxs\\*\\cscript.exe"
0x180004df4  mov     [rbp+16E0h+var_1268], rax
0x180004dfb  mov     [rbp+16E0h+var_1260], rbx
0x180004e02  mov     [rbp+16E0h+var_1258], rdi
0x180004e09  mov     rdx, rdi
0x180004e0c  lea     rcx, [rbp+16E0h+var_1250]
0x180004e13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004e18  nop
0x180004e19  mov     [rbp+16E0h+var_1230], 3
0x180004e24  lea     rax, aSystemrootDial; "%systemroot%\\*\\dialer.exe"
0x180004e2b  mov     [rbp+16E0h+var_1228], rax
0x180004e32  mov     [rbp+16E0h+var_1220], rbx
0x180004e39  mov     [rbp+16E0h+var_1218], rdi
0x180004e40  mov     rdx, rdi
0x180004e43  lea     rcx, [rbp+16E0h+var_1210]
0x180004e4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004e4f  nop
0x180004e50  mov     [rbp+16E0h+var_11F0], 3
0x180004e5b  lea     rax, aSystemrootWins_2; "%systemroot%\\winsxs\\*\\dialer.exe"
0x180004e62  mov     [rbp+16E0h+var_11E8], rax
0x180004e69  mov     [rbp+16E0h+var_11E0], rbx
0x180004e70  mov     [rbp+16E0h+var_11D8], rdi
0x180004e77  mov     rdx, rdi
0x180004e7a  lea     rcx, [rbp+16E0h+var_11D0]
0x180004e81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004e86  nop
0x180004e87  mov     [rbp+16E0h+var_11B0], 3
0x180004e92  lea     rax, aSystemrootDosk; "%systemroot%\\*\\doskey.exe"
0x180004e99  mov     [rbp+16E0h+var_11A8], rax
0x180004ea0  mov     [rbp+16E0h+var_11A0], rbx
0x180004ea7  mov     [rbp+16E0h+var_1198], rdi
0x180004eae  mov     rdx, rdi
0x180004eb1  lea     rcx, [rbp+16E0h+var_1190]
0x180004eb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004ebd  nop
0x180004ebe  mov     [rbp+16E0h+var_1170], 3
0x180004ec9  lea     rax, aSystemrootWins_32; "%systemroot%\\winsxs\\*\\doskey.exe"
0x180004ed0  mov     [rbp+16E0h+var_1168], rax
0x180004ed7  mov     [rbp+16E0h+var_1160], rbx
0x180004ede  mov     [rbp+16E0h+var_1158], rdi
0x180004ee5  mov     rdx, rdi
0x180004ee8  lea     rcx, [rbp+16E0h+var_1150]
0x180004eef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004ef4  nop
0x180004ef5  mov     [rbp+16E0h+var_1130], 3
0x180004f00  lea     rax, aSystemrootDfrg; "%systemroot%\\*\\dfrgui.exe"
0x180004f07  mov     [rbp+16E0h+var_1128], rax
0x180004f0e  mov     [rbp+16E0h+var_1120], rbx
0x180004f15  mov     [rbp+16E0h+var_1118], rdi
0x180004f1c  mov     rdx, rdi
0x180004f1f  lea     rcx, [rbp+16E0h+var_1110]
0x180004f26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004f2b  nop
0x180004f2c  mov     [rbp+16E0h+var_10F0], 3
0x180004f37  lea     rax, aSystemrootWins_12; "%systemroot%\\winsxs\\*\\dfrgui.exe"
0x180004f3e  mov     [rbp+16E0h+var_10E8], rax
0x180004f45  mov     [rbp+16E0h+var_10E0], rbx
0x180004f4c  mov     [rbp+16E0h+var_10D8], rdi
0x180004f53  mov     rdx, rdi
0x180004f56  lea     rcx, [rbp+16E0h+var_10D0]
0x180004f5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004f62  nop
0x180004f63  mov     [rbp+16E0h+var_10B0], 3
0x180004f6e  lea     rax, aSystemrootIcac; "%systemroot%\\*\\icacls.exe"
0x180004f75  mov     [rbp+16E0h+var_10A8], rax
0x180004f7c  mov     [rbp+16E0h+var_10A0], rbx
0x180004f83  mov     [rbp+16E0h+var_1098], rdi
0x180004f8a  mov     rdx, rdi
0x180004f8d  lea     rcx, [rbp+16E0h+var_1090]
0x180004f94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004f99  nop
0x180004f9a  mov     [rbp+16E0h+var_1070], 3
0x180004fa5  lea     rax, aSystemrootWins_18; "%systemroot%\\winsxs\\*\\icacls.exe"
0x180004fac  mov     [rbp+16E0h+var_1068], rax
0x180004fb3  mov     [rbp+16E0h+var_1060], rbx
0x180004fba  mov     [rbp+16E0h+var_1058], rdi
0x180004fc1  mov     rdx, rdi
0x180004fc4  lea     rcx, [rbp+16E0h+var_1050]
0x180004fcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180004fd0  nop
0x180004fd1  mov     [rbp+16E0h+var_1030], 3
0x180004fdc  lea     rax, aSystemrootWins_53; "%systemroot%\\winsxs\\*\\iexplore.exe"
0x180004fe3  mov     [rbp+16E0h+var_1028], rax
0x180004fea  mov     [rbp+16E0h+var_1020], rbx
0x180004ff1  mov     [rbp+16E0h+var_1018], rdi
0x180004ff8  mov     rdx, rdi
0x180004ffb  lea     rcx, [rbp+16E0h+var_1010]
0x180005002  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180005007  nop
0x180005008  mov     [rbp+16E0h+var_FF0], 3
0x180005013  lea     rax, aSystemrootIscs; "%systemroot%\\*\\iscsicpl.exe"
0x18000501a  mov     [rbp+16E0h+var_FE8], rax
0x180005021  mov     [rbp+16E0h+var_FE0], rbx
0x180005028  mov     [rbp+16E0h+var_FD8], rdi
0x18000502f  mov     rdx, rdi
0x180005032  lea     rcx, [rbp+16E0h+var_FD0]
0x180005039  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
