# svgpp::policy::xml::GetAttributeDefaultNamespace(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x180009618`
- end: `0x18000b936`
- name: `?GetAttributeDefaultNamespace@xml@policy@svgpp@@YA?AW4namespace_id@detail@3@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `8990`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005ea58`

## callees

- `0x180009538`
- `0x180009618`
- `0x18000b938`
- `0x18000ba4c`
- `0x18000bbbc`
- `0x18000c5b0`
- `0x18013d700`
- `0x18013d78c`
- `0x18013d7f8`
- `0x18013dbe8`
- `0x18013e810`
- `0x18013f740`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1800096b5`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800096b5`
- `KERNEL32!InitOnceComplete` at `0x180009781`
- `KERNEL32!InitOnceComplete` at `0x180009781`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800096bf`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800096bf`

## string_xrefs

- `0x180009a85`: `clip-path`
- `0x180009abd`: `clipPathUnits`
- `0x18000a8fd`: `onmousemove`
- `0x18000ab95`: `pathLength`
- `0x18000adee`: `requiredExtensions`
- `0x18000afbc`: `spreadMethod`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall svgpp::policy::xml::GetAttributeDefaultNamespace(__m128i *a1)
{
  __int64 v2; // r9
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rbx
  __m128i v6; // xmm1
  size_t v7; // rdi
  size_t v8; // r8
  unsigned __int64 v9; // xmm0_8
  BOOL fPending[2]; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h]
  _QWORD v14[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[2]; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+80h] [rbp-80h]
  const wchar_t *v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+98h] [rbp-68h]
  const wchar_t *v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+A8h] [rbp-58h]
  int v23; // [rsp+B0h] [rbp-50h]
  const wchar_t *v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  int v26; // [rsp+C8h] [rbp-38h]
  const wchar_t *v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+E0h] [rbp-20h]
  const wchar_t *v30; // [rsp+E8h] [rbp-18h]
  __int64 v31; // [rsp+F0h] [rbp-10h]
  int v32; // [rsp+F8h] [rbp-8h]
  const wchar_t *v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+110h] [rbp+10h]
  const wchar_t *v36; // [rsp+118h] [rbp+18h]
  __int64 v37; // [rsp+120h] [rbp+20h]
  int v38; // [rsp+128h] [rbp+28h]
  const wchar_t *v39; // [rsp+130h] [rbp+30h]
  __int64 v40; // [rsp+138h] [rbp+38h]
  int v41; // [rsp+140h] [rbp+40h]
  const wchar_t *v42; // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+150h] [rbp+50h]
  int v44; // [rsp+158h] [rbp+58h]
  const wchar_t *v45; // [rsp+160h] [rbp+60h]
  __int64 v46; // [rsp+168h] [rbp+68h]
  int v47; // [rsp+170h] [rbp+70h]
  const wchar_t *v48; // [rsp+178h] [rbp+78h]
  __int64 v49; // [rsp+180h] [rbp+80h]
  int v50; // [rsp+188h] [rbp+88h]
  const wchar_t *v51; // [rsp+190h] [rbp+90h]
  __int64 v52; // [rsp+198h] [rbp+98h]
  int v53; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v54; // [rsp+1A8h] [rbp+A8h]
  __int64 v55; // [rsp+1B0h] [rbp+B0h]
  int v56; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v57; // [rsp+1C0h] [rbp+C0h]
  __int64 v58; // [rsp+1C8h] [rbp+C8h]
  int v59; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v60; // [rsp+1D8h] [rbp+D8h]
  __int64 v61; // [rsp+1E0h] [rbp+E0h]
  int v62; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v63; // [rsp+1F0h] [rbp+F0h]
  __int64 v64; // [rsp+1F8h] [rbp+F8h]
  int v65; // [rsp+200h] [rbp+100h]
  const wchar_t *v66; // [rsp+208h] [rbp+108h]
  __int64 v67; // [rsp+210h] [rbp+110h]
  int v68; // [rsp+218h] [rbp+118h]
  const wchar_t *v69; // [rsp+220h] [rbp+120h]
  __int64 v70; // [rsp+228h] [rbp+128h]
  int v71; // [rsp+230h] [rbp+130h]
  const wchar_t *v72; // [rsp+238h] [rbp+138h]
  __int64 v73; // [rsp+240h] [rbp+140h]
  int v74; // [rsp+248h] [rbp+148h]
  const wchar_t *v75; // [rsp+250h] [rbp+150h]
  __int64 v76; // [rsp+258h] [rbp+158h]
  int v77; // [rsp+260h] [rbp+160h]
  const wchar_t *v78; // [rsp+268h] [rbp+168h]
  __int64 v79; // [rsp+270h] [rbp+170h]
  int v80; // [rsp+278h] [rbp+178h]
  const wchar_t *v81; // [rsp+280h] [rbp+180h]
  __int64 v82; // [rsp+288h] [rbp+188h]
  int v83; // [rsp+290h] [rbp+190h]
  const wchar_t *v84; // [rsp+298h] [rbp+198h]
  __int64 v85; // [rsp+2A0h] [rbp+1A0h]
  int v86; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v87; // [rsp+2B0h] [rbp+1B0h]
  __int64 v88; // [rsp+2B8h] [rbp+1B8h]
  int v89; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v90; // [rsp+2C8h] [rbp+1C8h]
  __int64 v91; // [rsp+2D0h] [rbp+1D0h]
  int v92; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v93; // [rsp+2E0h] [rbp+1E0h]
  __int64 v94; // [rsp+2E8h] [rbp+1E8h]
  int v95; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v96; // [rsp+2F8h] [rbp+1F8h]
  __int64 v97; // [rsp+300h] [rbp+200h]
  int v98; // [rsp+308h] [rbp+208h]
  const wchar_t *v99; // [rsp+310h] [rbp+210h]
  __int64 v100; // [rsp+318h] [rbp+218h]
  int v101; // [rsp+320h] [rbp+220h]
  const wchar_t *v102; // [rsp+328h] [rbp+228h]
  __int64 v103; // [rsp+330h] [rbp+230h]
  int v104; // [rsp+338h] [rbp+238h]
  const wchar_t *v105; // [rsp+340h] [rbp+240h]
  __int64 v106; // [rsp+348h] [rbp+248h]
  int v107; // [rsp+350h] [rbp+250h]
  const wchar_t *v108; // [rsp+358h] [rbp+258h]
  __int64 v109; // [rsp+360h] [rbp+260h]
  int v110; // [rsp+368h] [rbp+268h]
  const wchar_t *v111; // [rsp+370h] [rbp+270h]
  __int64 v112; // [rsp+378h] [rbp+278h]
  int v113; // [rsp+380h] [rbp+280h]
  const wchar_t *v114; // [rsp+388h] [rbp+288h]
  __int64 v115; // [rsp+390h] [rbp+290h]
  int v116; // [rsp+398h] [rbp+298h]
  const wchar_t *v117; // [rsp+3A0h] [rbp+2A0h]
  __int64 v118; // [rsp+3A8h] [rbp+2A8h]
  int v119; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v120; // [rsp+3B8h] [rbp+2B8h]
  __int64 v121; // [rsp+3C0h] [rbp+2C0h]
  int v122; // [rsp+3C8h] [rbp+2C8h]
  const wchar_t *v123; // [rsp+3D0h] [rbp+2D0h]
  __int64 v124; // [rsp+3D8h] [rbp+2D8h]
  int v125; // [rsp+3E0h] [rbp+2E0h]
  const wchar_t *v126; // [rsp+3E8h] [rbp+2E8h]
  __int64 v127; // [rsp+3F0h] [rbp+2F0h]
  int v128; // [rsp+3F8h] [rbp+2F8h]
  const wchar_t *v129; // [rsp+400h] [rbp+300h]
  __int64 v130; // [rsp+408h] [rbp+308h]
  int v131; // [rsp+410h] [rbp+310h]
  const wchar_t *v132; // [rsp+418h] [rbp+318h]
  __int64 v133; // [rsp+420h] [rbp+320h]
  int v134; // [rsp+428h] [rbp+328h]
  const wchar_t *v135; // [rsp+430h] [rbp+330h]
  __int64 v136; // [rsp+438h] [rbp+338h]
  int v137; // [rsp+440h] [rbp+340h]
  const wchar_t *v138; // [rsp+448h] [rbp+348h]
  __int64 v139; // [rsp+450h] [rbp+350h]
  int v140; // [rsp+458h] [rbp+358h]
  const wchar_t *v141; // [rsp+460h] [rbp+360h]
  __int64 v142; // [rsp+468h] [rbp+368h]
  int v143; // [rsp+470h] [rbp+370h]
  const wchar_t *v144; // [rsp+478h] [rbp+378h]
  __int64 v145; // [rsp+480h] [rbp+380h]
  int v146; // [rsp+488h] [rbp+388h]
  const wchar_t *v147; // [rsp+490h] [rbp+390h]
  __int64 v148; // [rsp+498h] [rbp+398h]
  int v149; // [rsp+4A0h] [rbp+3A0h]
  const wchar_t *v150; // [rsp+4A8h] [rbp+3A8h]
  __int64 v151; // [rsp+4B0h] [rbp+3B0h]
  int v152; // [rsp+4B8h] [rbp+3B8h]
  const wchar_t *v153; // [rsp+4C0h] [rbp+3C0h]
  __int64 v154; // [rsp+4C8h] [rbp+3C8h]
  int v155; // [rsp+4D0h] [rbp+3D0h]
  const wchar_t *v156; // [rsp+4D8h] [rbp+3D8h]
  __int64 v157; // [rsp+4E0h] [rbp+3E0h]
  int v158; // [rsp+4E8h] [rbp+3E8h]
  const wchar_t *v159; // [rsp+4F0h] [rbp+3F0h]
  __int64 v160; // [rsp+4F8h] [rbp+3F8h]
  int v161; // [rsp+500h] [rbp+400h]
  const wchar_t *v162; // [rsp+508h] [rbp+408h]
  __int64 v163; // [rsp+510h] [rbp+410h]
  int v164; // [rsp+518h] [rbp+418h]
  const wchar_t *v165; // [rsp+520h] [rbp+420h]
  __int64 v166; // [rsp+528h] [rbp+428h]
  int v167; // [rsp+530h] [rbp+430h]
  const wchar_t *v168; // [rsp+538h] [rbp+438h]
  __int64 v169; // [rsp+540h] [rbp+440h]
  int v170; // [rsp+548h] [rbp+448h]
  const wchar_t *v171; // [rsp+550h] [rbp+450h]
  __int64 v172; // [rsp+558h] [rbp+458h]
  int v173; // [rsp+560h] [rbp+460h]
  const wchar_t *v174; // [rsp+568h] [rbp+468h]
  __int64 v175; // [rsp+570h] [rbp+470h]
  int v176; // [rsp+578h] [rbp+478h]
  const wchar_t *v177; // [rsp+580h] [rbp+480h]
  __int64 v178; // [rsp+588h] [rbp+488h]
  int v179; // [rsp+590h] [rbp+490h]
  const wchar_t *v180; // [rsp+598h] [rbp+498h]
  __int64 v181; // [rsp+5A0h] [rbp+4A0h]
  int v182; // [rsp+5A8h] [rbp+4A8h]
  const wchar_t *v183; // [rsp+5B0h] [rbp+4B0h]
  __int64 v184; // [rsp+5B8h] [rbp+4B8h]
  int v185; // [rsp+5C0h] [rbp+4C0h]
  const wchar_t *v186; // [rsp+5C8h] [rbp+4C8h]
  __int64 v187; // [rsp+5D0h] [rbp+4D0h]
  int v188; // [rsp+5D8h] [rbp+4D8h]
  const wchar_t *v189; // [rsp+5E0h] [rbp+4E0h]
  __int64 v190; // [rsp+5E8h] [rbp+4E8h]
  int v191; // [rsp+5F0h] [rbp+4F0h]
  const wchar_t *v192; // [rsp+5F8h] [rbp+4F8h]
  __int64 v193; // [rsp+600h] [rbp+500h]
  int v194; // [rsp+608h] [rbp+508h]
  const wchar_t *v195; // [rsp+610h] [rbp+510h]
  __int64 v196; // [rsp+618h] [rbp+518h]
  int v197; // [rsp+620h] [rbp+520h]
  const wchar_t *v198; // [rsp+628h] [rbp+528h]
  __int64 v199; // [rsp+630h] [rbp+530h]
  int v200; // [rsp+638h] [rbp+538h]
  const wchar_t *v201; // [rsp+640h] [rbp+540h]
  __int64 v202; // [rsp+648h] [rbp+548h]
  int v203; // [rsp+650h] [rbp+550h]
  const wchar_t *v204; // [rsp+658h] [rbp+558h]
  __int64 v205; // [rsp+660h] [rbp+560h]
  int v206; // [rsp+668h] [rbp+568h]
  const wchar_t *v207; // [rsp+670h] [rbp+570h]
  __int64 v208; // [rsp+678h] [rbp+578h]
  int v209; // [rsp+680h] [rbp+580h]
  const wchar_t *v210; // [rsp+688h] [rbp+588h]
  __int64 v211; // [rsp+690h] [rbp+590h]
  int v212; // [rsp+698h] [rbp+598h]
  const wchar_t *v213; // [rsp+6A0h] [rbp+5A0h]
  __int64 v214; // [rsp+6A8h] [rbp+5A8h]
  int v215; // [rsp+6B0h] [rbp+5B0h]
  const wchar_t *v216; // [rsp+6B8h] [rbp+5B8h]
  __int64 v217; // [rsp+6C0h] [rbp+5C0h]
  int v218; // [rsp+6C8h] [rbp+5C8h]
  const wchar_t *v219; // [rsp+6D0h] [rbp+5D0h]
  __int64 v220; // [rsp+6D8h] [rbp+5D8h]
  int v221; // [rsp+6E0h] [rbp+5E0h]
  const wchar_t *v222; // [rsp+6E8h] [rbp+5E8h]
  __int64 v223; // [rsp+6F0h] [rbp+5F0h]
  int v224; // [rsp+6F8h] [rbp+5F8h]
  const wchar_t *v225; // [rsp+700h] [rbp+600h]
  __int64 v226; // [rsp+708h] [rbp+608h]
  int v227; // [rsp+710h] [rbp+610h]
  const wchar_t *v228; // [rsp+718h] [rbp+618h]
  __int64 v229; // [rsp+720h] [rbp+620h]
  int v230; // [rsp+728h] [rbp+628h]
  const wchar_t *v231; // [rsp+730h] [rbp+630h]
  __int64 v232; // [rsp+738h] [rbp+638h]
  int v233; // [rsp+740h] [rbp+640h]
  const wchar_t *v234; // [rsp+748h] [rbp+648h]
  __int64 v235; // [rsp+750h] [rbp+650h]
  int v236; // [rsp+758h] [rbp+658h]
  const wchar_t *v237; // [rsp+760h] [rbp+660h]
  __int64 v238; // [rsp+768h] [rbp+668h]
  int v239; // [rsp+770h] [rbp+670h]
  const wchar_t *v240; // [rsp+778h] [rbp+678h]
  __int64 v241; // [rsp+780h] [rbp+680h]
  int v242; // [rsp+788h] [rbp+688h]
  const wchar_t *v243; // [rsp+790h] [rbp+690h]
  __int64 v244; // [rsp+798h] [rbp+698h]
  int v245; // [rsp+7A0h] [rbp+6A0h]
  const wchar_t *v246; // [rsp+7A8h] [rbp+6A8h]
  __int64 v247; // [rsp+7B0h] [rbp+6B0h]
  int v248; // [rsp+7B8h] [rbp+6B8h]
  const wchar_t *v249; // [rsp+7C0h] [rbp+6C0h]
  __int64 v250; // [rsp+7C8h] [rbp+6C8h]
  int v251; // [rsp+7D0h] [rbp+6D0h]
  const wchar_t *v252; // [rsp+7D8h] [rbp+6D8h]
  __int64 v253; // [rsp+7E0h] [rbp+6E0h]
  int v254; // [rsp+7E8h] [rbp+6E8h]
  const wchar_t *v255; // [rsp+7F0h] [rbp+6F0h]
  __int64 v256; // [rsp+7F8h] [rbp+6F8h]
  int v257; // [rsp+800h] [rbp+700h]
  const wchar_t *v258; // [rsp+808h] [rbp+708h]
  __int64 v259; // [rsp+810h] [rbp+710h]
  int v260; // [rsp+818h] [rbp+718h]
  const wchar_t *v261; // [rsp+820h] [rbp+720h]
  __int64 v262; // [rsp+828h] [rbp+728h]
  int v263; // [rsp+830h] [rbp+730h]
  const wchar_t *v264; // [rsp+838h] [rbp+738h]
  __int64 v265; // [rsp+840h] [rbp+740h]
  int v266; // [rsp+848h] [rbp+748h]
  const wchar_t *v267; // [rsp+850h] [rbp+750h]
  __int64 v268; // [rsp+858h] [rbp+758h]
  int v269; // [rsp+860h] [rbp+760h]
  const wchar_t *v270; // [rsp+868h] [rbp+768h]
  __int64 v271; // [rsp+870h] [rbp+770h]
  int v272; // [rsp+878h] [rbp+778h]
  const wchar_t *v273; // [rsp+880h] [rbp+780h]
  __int64 v274; // [rsp+888h] [rbp+788h]
  int v275; // [rsp+890h] [rbp+790h]
  const wchar_t *v276; // [rsp+898h] [rbp+798h]
  __int64 v277; // [rsp+8A0h] [rbp+7A0h]
  int v278; // [rsp+8A8h] [rbp+7A8h]
  const wchar_t *v279; // [rsp+8B0h] [rbp+7B0h]
  __int64 v280; // [rsp+8B8h] [rbp+7B8h]
  int v281; // [rsp+8C0h] [rbp+7C0h]
  const wchar_t *v282; // [rsp+8C8h] [rbp+7C8h]
  __int64 v283; // [rsp+8D0h] [rbp+7D0h]
  int v284; // [rsp+8D8h] [rbp+7D8h]
  const wchar_t *v285; // [rsp+8E0h] [rbp+7E0h]
  __int64 v286; // [rsp+8E8h] [rbp+7E8h]
  int v287; // [rsp+8F0h] [rbp+7F0h]
  const wchar_t *v288; // [rsp+8F8h] [rbp+7F8h]
  __int64 v289; // [rsp+900h] [rbp+800h]
  int v290; // [rsp+908h] [rbp+808h]
  const wchar_t *v291; // [rsp+910h] [rbp+810h]
  __int64 v292; // [rsp+918h] [rbp+818h]
  int v293; // [rsp+920h] [rbp+820h]
  const wchar_t *v294; // [rsp+928h] [rbp+828h]
  __int64 v295; // [rsp+930h] [rbp+830h]
  int v296; // [rsp+938h] [rbp+838h]
  const wchar_t *v297; // [rsp+940h] [rbp+840h]
  __int64 v298; // [rsp+948h] [rbp+848h]
  int v299; // [rsp+950h] [rbp+850h]
  const wchar_t *v300; // [rsp+958h] [rbp+858h]
  __int64 v301; // [rsp+960h] [rbp+860h]
  int v302; // [rsp+968h] [rbp+868h]
  const wchar_t *v303; // [rsp+970h] [rbp+870h]
  __int64 v304; // [rsp+978h] [rbp+878h]
  int v305; // [rsp+980h] [rbp+880h]
  const wchar_t *v306; // [rsp+988h] [rbp+888h]
  __int64 v307; // [rsp+990h] [rbp+890h]
  int v308; // [rsp+998h] [rbp+898h]
  const wchar_t *v309; // [rsp+9A0h] [rbp+8A0h]
  __int64 v310; // [rsp+9A8h] [rbp+8A8h]
  int v311; // [rsp+9B0h] [rbp+8B0h]
  const wchar_t *v312; // [rsp+9B8h] [rbp+8B8h]
  __int64 v313; // [rsp+9C0h] [rbp+8C0h]
  int v314; // [rsp+9C8h] [rbp+8C8h]
  const wchar_t *v315; // [rsp+9D0h] [rbp+8D0h]
  __int64 v316; // [rsp+9D8h] [rbp+8D8h]
  int v317; // [rsp+9E0h] [rbp+8E0h]
  const wchar_t *v318; // [rsp+9E8h] [rbp+8E8h]
  __int64 v319; // [rsp+9F0h] [rbp+8F0h]
  int v320; // [rsp+9F8h] [rbp+8F8h]
  const wchar_t *v321; // [rsp+A00h] [rbp+900h]
  __int64 v322; // [rsp+A08h] [rbp+908h]
  int v323; // [rsp+A10h] [rbp+910h]
  const wchar_t *v324; // [rsp+A18h] [rbp+918h]
  __int64 v325; // [rsp+A20h] [rbp+920h]
  int v326; // [rsp+A28h] [rbp+928h]
  const wchar_t *v327; // [rsp+A30h] [rbp+930h]
  __int64 v328; // [rsp+A38h] [rbp+938h]
  int v329; // [rsp+A40h] [rbp+940h]
  const wchar_t *v330; // [rsp+A48h] [rbp+948h]
  __int64 v331; // [rsp+A50h] [rbp+950h]
  int v332; // [rsp+A58h] [rbp+958h]
  const wchar_t *v333; // [rsp+A60h] [rbp+960h]
  __int64 v334; // [rsp+A68h] [rbp+968h]
  int v335; // [rsp+A70h] [rbp+970h]
  const wchar_t *v336; // [rsp+A78h] [rbp+978h]
  __int64 v337; // [rsp+A80h] [rbp+980h]
  int v338; // [rsp+A88h] [rbp+988h]
  const wchar_t *v339; // [rsp+A90h] [rbp+990h]
  __int64 v340; // [rsp+A98h] [rbp+998h]
  int v341; // [rsp+AA0h] [rbp+9A0h]
  const wchar_t *v342; // [rsp+AA8h] [rbp+9A8h]
  __int64 v343; // [rsp+AB0h] [rbp+9B0h]
  int v344; // [rsp+AB8h] [rbp+9B8h]
  const wchar_t *v345; // [rsp+AC0h] [rbp+9C0h]
  __int64 v346; // [rsp+AC8h] [rbp+9C8h]
  int v347; // [rsp+AD0h] [rbp+9D0h]
  const wchar_t *v348; // [rsp+AD8h] [rbp+9D8h]
  __int64 v349; // [rsp+AE0h] [rbp+9E0h]
  int v350; // [rsp+AE8h] [rbp+9E8h]
  const wchar_t *v351; // [rsp+AF0h] [rbp+9F0h]
  __int64 v352; // [rsp+AF8h] [rbp+9F8h]
  int v353; // [rsp+B00h] [rbp+A00h]
  const wchar_t *v354; // [rsp+B08h] [rbp+A08h]
  __int64 v355; // [rsp+B10h] [rbp+A10h]
  int v356; // [rsp+B18h] [rbp+A18h]
  const wchar_t *v357; // [rsp+B20h] [rbp+A20h]
  __int64 v358; // [rsp+B28h] [rbp+A28h]
  int v359; // [rsp+B30h] [rbp+A30h]
  const wchar_t *v360; // [rsp+B38h] [rbp+A38h]
  __int64 v361; // [rsp+B40h] [rbp+A40h]
  int v362; // [rsp+B48h] [rbp+A48h]
  const wchar_t *v363; // [rsp+B50h] [rbp+A50h]
  __int64 v364; // [rsp+B58h] [rbp+A58h]
  int v365; // [rsp+B60h] [rbp+A60h]
  const wchar_t *v366; // [rsp+B68h] [rbp+A68h]
  __int64 v367; // [rsp+B70h] [rbp+A70h]
  int v368; // [rsp+B78h] [rbp+A78h]
  const wchar_t *v369; // [rsp+B80h] [rbp+A80h]
  __int64 v370; // [rsp+B88h] [rbp+A88h]
  int v371; // [rsp+B90h] [rbp+A90h]
  const wchar_t *v372; // [rsp+B98h] [rbp+A98h]
  __int64 v373; // [rsp+BA0h] [rbp+AA0h]
  int v374; // [rsp+BA8h] [rbp+AA8h]
  const wchar_t *v375; // [rsp+BB0h] [rbp+AB0h]
  __int64 v376; // [rsp+BB8h] [rbp+AB8h]
  int v377; // [rsp+BC0h] [rbp+AC0h]
  const wchar_t *v378; // [rsp+BC8h] [rbp+AC8h]
  __int64 v379; // [rsp+BD0h] [rbp+AD0h]
  int v380; // [rsp+BD8h] [rbp+AD8h]
  const wchar_t *v381; // [rsp+BE0h] [rbp+AE0h]
  __int64 v382; // [rsp+BE8h] [rbp+AE8h]
  int v383; // [rsp+BF0h] [rbp+AF0h]
  const wchar_t *v384; // [rsp+BF8h] [rbp+AF8h]
  __int64 v385; // [rsp+C00h] [rbp+B00h]
  int v386; // [rsp+C08h] [rbp+B08h]
  const wchar_t *v387; // [rsp+C10h] [rbp+B10h]
  __int64 v388; // [rsp+C18h] [rbp+B18h]
  int v389; // [rsp+C20h] [rbp+B20h]
  const wchar_t *v390; // [rsp+C28h] [rbp+B28h]
  __int64 v391; // [rsp+C30h] [rbp+B30h]
  int v392; // [rsp+C38h] [rbp+B38h]
  const wchar_t *v393; // [rsp+C40h] [rbp+B40h]
  __int64 v394; // [rsp+C48h] [rbp+B48h]
  int v395; // [rsp+C50h] [rbp+B50h]
  const wchar_t *v396; // [rsp+C58h] [rbp+B58h]
  __int64 v397; // [rsp+C60h] [rbp+B60h]
  int v398; // [rsp+C68h] [rbp+B68h]
  const wchar_t *v399; // [rsp+C70h] [rbp+B70h]
  __int64 v400; // [rsp+C78h] [rbp+B78h]
  int v401; // [rsp+C80h] [rbp+B80h]
  const wchar_t *v402; // [rsp+C88h] [rbp+B88h]
  __int64 v403; // [rsp+C90h] [rbp+B90h]
  int v404; // [rsp+C98h] [rbp+B98h]
  const wchar_t *v405; // [rsp+CA0h] [rbp+BA0h]
  __int64 v406; // [rsp+CA8h] [rbp+BA8h]
  int v407; // [rsp+CB0h] [rbp+BB0h]
  const wchar_t *v408; // [rsp+CB8h] [rbp+BB8h]
  __int64 v409; // [rsp+CC0h] [rbp+BC0h]
  int v410; // [rsp+CC8h] [rbp+BC8h]
  const wchar_t *v411; // [rsp+CD0h] [rbp+BD0h]
  __int64 v412; // [rsp+CD8h] [rbp+BD8h]
  int v413; // [rsp+CE0h] [rbp+BE0h]
  const wchar_t *v414; // [rsp+CE8h] [rbp+BE8h]
  __int64 v415; // [rsp+CF0h] [rbp+BF0h]
  int v416; // [rsp+CF8h] [rbp+BF8h]
  const wchar_t *v417; // [rsp+D00h] [rbp+C00h]
  __int64 v418; // [rsp+D08h] [rbp+C08h]
  int v419; // [rsp+D10h] [rbp+C10h]
  const wchar_t *v420; // [rsp+D18h] [rbp+C18h]
  __int64 v421; // [rsp+D20h] [rbp+C20h]
  int v422; // [rsp+D28h] [rbp+C28h]
  const wchar_t *v423; // [rsp+D30h] [rbp+C30h]
  __int64 v424; // [rsp+D38h] [rbp+C38h]
  int v425; // [rsp+D40h] [rbp+C40h]
  const wchar_t *v426; // [rsp+D48h] [rbp+C48h]
  __int64 v427; // [rsp+D50h] [rbp+C50h]
  int v428; // [rsp+D58h] [rbp+C58h]
  const wchar_t *v429; // [rsp+D60h] [rbp+C60h]
  __int64 v430; // [rsp+D68h] [rbp+C68h]
  int v431; // [rsp+D70h] [rbp+C70h]
  const wchar_t *v432; // [rsp+D78h] [rbp+C78h]
  __int64 v433; // [rsp+D80h] [rbp+C80h]
  int v434; // [rsp+D88h] [rbp+C88h]
  const wchar_t *v435; // [rsp+D90h] [rbp+C90h]
  __int64 v436; // [rsp+D98h] [rbp+C98h]
  int v437; // [rsp+DA0h] [rbp+CA0h]
  const wchar_t *v438; // [rsp+DA8h] [rbp+CA8h]
  __int64 v439; // [rsp+DB0h] [rbp+CB0h]
  int v440; // [rsp+DB8h] [rbp+CB8h]
  const wchar_t *v441; // [rsp+DC0h] [rbp+CC0h]
  __int64 v442; // [rsp+DC8h] [rbp+CC8h]
  int v443; // [rsp+DD0h] [rbp+CD0h]
  const wchar_t *v444; // [rsp+DD8h] [rbp+CD8h]
  __int64 v445; // [rsp+DE0h] [rbp+CE0h]
  int v446; // [rsp+DE8h] [rbp+CE8h]
  const wchar_t *v447; // [rsp+DF0h] [rbp+CF0h]
  __int64 v448; // [rsp+DF8h] [rbp+CF8h]
  int v449; // [rsp+E00h] [rbp+D00h]
  const wchar_t *v450; // [rsp+E08h] [rbp+D08h]
  __int64 v451; // [rsp+E10h] [rbp+D10h]
  int v452; // [rsp+E18h] [rbp+D18h]
  const wchar_t *v453; // [rsp+E20h] [rbp+D20h]
  __int64 v454; // [rsp+E28h] [rbp+D28h]
  int v455; // [rsp+E30h] [rbp+D30h]
  const wchar_t *v456; // [rsp+E38h] [rbp+D38h]
  __int64 v457; // [rsp+E40h] [rbp+D40h]
  int v458; // [rsp+E48h] [rbp+D48h]
  const wchar_t *v459; // [rsp+E50h] [rbp+D50h]
  __int64 v460; // [rsp+E58h] [rbp+D58h]
  int v461; // [rsp+E60h] [rbp+D60h]
  const wchar_t *v462; // [rsp+E68h] [rbp+D68h]
  __int64 v463; // [rsp+E70h] [rbp+D70h]
  int v464; // [rsp+E78h] [rbp+D78h]
  const wchar_t *v465; // [rsp+E80h] [rbp+D80h]
  __int64 v466; // [rsp+E88h] [rbp+D88h]
  int v467; // [rsp+E90h] [rbp+D90h]
  const wchar_t *v468; // [rsp+E98h] [rbp+D98h]
  __int64 v469; // [rsp+EA0h] [rbp+DA0h]
  int v470; // [rsp+EA8h] [rbp+DA8h]
  const wchar_t *v471; // [rsp+EB0h] [rbp+DB0h]
  __int64 v472; // [rsp+EB8h] [rbp+DB8h]
  int v473; // [rsp+EC0h] [rbp+DC0h]
  const wchar_t *v474; // [rsp+EC8h] [rbp+DC8h]
  __int64 v475; // [rsp+ED0h] [rbp+DD0h]
  int v476; // [rsp+ED8h] [rbp+DD8h]
  const wchar_t *v477; // [rsp+EE0h] [rbp+DE0h]
  __int64 v478; // [rsp+EE8h] [rbp+DE8h]
  int v479; // [rsp+EF0h] [rbp+DF0h]
  const wchar_t *v480; // [rsp+EF8h] [rbp+DF8h]
  __int64 v481; // [rsp+F00h] [rbp+E00h]
  int v482; // [rsp+F08h] [rbp+E08h]
  const wchar_t *v483; // [rsp+F10h] [rbp+E10h]
  __int64 v484; // [rsp+F18h] [rbp+E18h]
  int v485; // [rsp+F20h] [rbp+E20h]
  const wchar_t *v486; // [rsp+F28h] [rbp+E28h]
  __int64 v487; // [rsp+F30h] [rbp+E30h]
  int v488; // [rsp+F38h] [rbp+E38h]
  const wchar_t *v489; // [rsp+F40h] [rbp+E40h]
  __int64 v490; // [rsp+F48h] [rbp+E48h]
  int v491; // [rsp+F50h] [rbp+E50h]
  const wchar_t *v492; // [rsp+F58h] [rbp+E58h]
  __int64 v493; // [rsp+F60h] [rbp+E60h]
  int v494; // [rsp+F68h] [rbp+E68h]
  const wchar_t *v495; // [rsp+F70h] [rbp+E70h]
  __int64 v496; // [rsp+F78h] [rbp+E78h]
  int v497; // [rsp+F80h] [rbp+E80h]
  const wchar_t *v498; // [rsp+F88h] [rbp+E88h]
  __int64 v499; // [rsp+F90h] [rbp+E90h]
  int v500; // [rsp+F98h] [rbp+E98h]
  const wchar_t *v501; // [rsp+FA0h] [rbp+EA0h]
  __int64 v502; // [rsp+FA8h] [rbp+EA8h]
  int v503; // [rsp+FB0h] [rbp+EB0h]
  const wchar_t *v504; // [rsp+FB8h] [rbp+EB8h]
  __int64 v505; // [rsp+FC0h] [rbp+EC0h]
  int v506; // [rsp+FC8h] [rbp+EC8h]
  const wchar_t *v507; // [rsp+FD0h] [rbp+ED0h]
  __int64 v508; // [rsp+FD8h] [rbp+ED8h]
  int v509; // [rsp+FE0h] [rbp+EE0h]
  const wchar_t *v510; // [rsp+FE8h] [rbp+EE8h]
  __int64 v511; // [rsp+FF0h] [rbp+EF0h]
  int v512; // [rsp+FF8h] [rbp+EF8h]
  const wchar_t *v513; // [rsp+1000h] [rbp+F00h]
  __int64 v514; // [rsp+1008h] [rbp+F08h]
  int v515; // [rsp+1010h] [rbp+F10h]
  const wchar_t *v516; // [rsp+1018h] [rbp+F18h]
  __int64 v517; // [rsp+1020h] [rbp+F20h]
  int v518; // [rsp+1028h] [rbp+F28h]
  const wchar_t *v519; // [rsp+1030h] [rbp+F30h]
  __int64 v520; // [rsp+1038h] [rbp+F38h]
  int v521; // [rsp+1040h] [rbp+F40h]
  const wchar_t *v522; // [rsp+1048h] [rbp+F48h]
  __int64 v523; // [rsp+1050h] [rbp+F50h]
  int v524; // [rsp+1058h] [rbp+F58h]
  const wchar_t *v525; // [rsp+1060h] [rbp+F60h]
  __int64 v526; // [rsp+1068h] [rbp+F68h]
  int v527; // [rsp+1070h] [rbp+F70h]
  const wchar_t *v528; // [rsp+1078h] [rbp+F78h]
  __int64 v529; // [rsp+1080h] [rbp+F80h]
  int v530; // [rsp+1088h] [rbp+F88h]
  const wchar_t *v531; // [rsp+1090h] [rbp+F90h]
  __int64 v532; // [rsp+1098h] [rbp+F98h]
  int v533; // [rsp+10A0h] [rbp+FA0h]
  const wchar_t *v534; // [rsp+10A8h] [rbp+FA8h]
  __int64 v535; // [rsp+10B0h] [rbp+FB0h]
  int v536; // [rsp+10B8h] [rbp+FB8h]
  const wchar_t *v537; // [rsp+10C0h] [rbp+FC0h]
  __int64 v538; // [rsp+10C8h] [rbp+FC8h]
  int v539; // [rsp+10D0h] [rbp+FD0h]
  const wchar_t *v540; // [rsp+10D8h] [rbp+FD8h]
  __int64 v541; // [rsp+10E0h] [rbp+FE0h]
  int v542; // [rsp+10E8h] [rbp+FE8h]
  const wchar_t *v543; // [rsp+10F0h] [rbp+FF0h]
  __int64 v544; // [rsp+10F8h] [rbp+FF8h]
  int v545; // [rsp+1100h] [rbp+1000h]
  const wchar_t *v546; // [rsp+1108h] [rbp+1008h]
  __int64 v547; // [rsp+1110h] [rbp+1010h]
  int v548; // [rsp+1118h] [rbp+1018h]
  const wchar_t *v549; // [rsp+1120h] [rbp+1020h]
  __int64 v550; // [rsp+1128h] [rbp+1028h]
  int v551; // [rsp+1130h] [rbp+1030h]
  const wchar_t *v552; // [rsp+1138h] [rbp+1038h]
  __int64 v553; // [rsp+1140h] [rbp+1040h]
  int v554; // [rsp+1148h] [rbp+1048h]
  const wchar_t *v555; // [rsp+1150h] [rbp+1050h]
  __int64 v556; // [rsp+1158h] [rbp+1058h]
  int v557; // [rsp+1160h] [rbp+1060h]
  const wchar_t *v558; // [rsp+1168h] [rbp+1068h]
  __int64 v559; // [rsp+1170h] [rbp+1070h]
  int v560; // [rsp+1178h] [rbp+1078h]
  const wchar_t *v561; // [rsp+1180h] [rbp+1080h]
  __int64 v562; // [rsp+1188h] [rbp+1088h]
  int v563; // [rsp+1190h] [rbp+1090h]
  const wchar_t *v564; // [rsp+1198h] [rbp+1098h]
  __int64 v565; // [rsp+11A0h] [rbp+10A0h]
  int v566; // [rsp+11A8h] [rbp+10A8h]
  const wchar_t *v567; // [rsp+11B0h] [rbp+10B0h]
  __int64 v568; // [rsp+11B8h] [rbp+10B8h]
  int v569; // [rsp+11C0h] [rbp+10C0h]
  const wchar_t *v570; // [rsp+11C8h] [rbp+10C8h]
  __int64 v571; // [rsp+11D0h] [rbp+10D0h]
  int v572; // [rsp+11D8h] [rbp+10D8h]
  const wchar_t *v573; // [rsp+11E0h] [rbp+10E0h]
  __int64 v574; // [rsp+11E8h] [rbp+10E8h]
  int v575; // [rsp+11F0h] [rbp+10F0h]
  const wchar_t *v576; // [rsp+11F8h] [rbp+10F8h]
  __int64 v577; // [rsp+1200h] [rbp+1100h]
  int v578; // [rsp+1208h] [rbp+1108h]
  const wchar_t *v579; // [rsp+1210h] [rbp+1110h]
  __int64 v580; // [rsp+1218h] [rbp+1118h]
  int v581; // [rsp+1220h] [rbp+1120h]
  const wchar_t *v582; // [rsp+1228h] [rbp+1128h]
  __int64 v583; // [rsp+1230h] [rbp+1130h]
  int v584; // [rsp+1238h] [rbp+1138h]
  const wchar_t *v585; // [rsp+1240h] [rbp+1140h]
  __int64 v586; // [rsp+1248h] [rbp+1148h]
  int v587; // [rsp+1250h] [rbp+1150h]
  const wchar_t *v588; // [rsp+1258h] [rbp+1158h]
  __int64 v589; // [rsp+1260h] [rbp+1160h]
  int v590; // [rsp+1268h] [rbp+1168h]
  const wchar_t *v591; // [rsp+1270h] [rbp+1170h]
  __int64 v592; // [rsp+1278h] [rbp+1178h]
  int v593; // [rsp+1280h] [rbp+1180h]
  const wchar_t *v594; // [rsp+1288h] [rbp+1188h]
  __int64 v595; // [rsp+1290h] [rbp+1190h]
  int v596; // [rsp+1298h] [rbp+1198h]
  const wchar_t *v597; // [rsp+12A0h] [rbp+11A0h]
  __int64 v598; // [rsp+12A8h] [rbp+11A8h]
  int v599; // [rsp+12B0h] [rbp+11B0h]
  const wchar_t *v600; // [rsp+12B8h] [rbp+11B8h]
  __int64 v601; // [rsp+12C0h] [rbp+11C0h]
  int v602; // [rsp+12C8h] [rbp+11C8h]
  const wchar_t *v603; // [rsp+12D0h] [rbp+11D0h]
  __int64 v604; // [rsp+12D8h] [rbp+11D8h]
  int v605; // [rsp+12E0h] [rbp+11E0h]
  const wchar_t *v606; // [rsp+12E8h] [rbp+11E8h]
  __int64 v607; // [rsp+12F0h] [rbp+11F0h]
  int v608; // [rsp+12F8h] [rbp+11F8h]
  const wchar_t *v609; // [rsp+1300h] [rbp+1200h]
  __int64 v610; // [rsp+1308h] [rbp+1208h]
  int v611; // [rsp+1310h] [rbp+1210h]
  const wchar_t *v612; // [rsp+1318h] [rbp+1218h]
  __int64 v613; // [rsp+1320h] [rbp+1220h]
  int v614; // [rsp+1328h] [rbp+1228h]
  const wchar_t *v615; // [rsp+1330h] [rbp+1230h]
  __int64 v616; // [rsp+1338h] [rbp+1238h]
  int v617; // [rsp+1340h] [rbp+1240h]
  const wchar_t *v618; // [rsp+1348h] [rbp+1248h]
  __int64 v619; // [rsp+1350h] [rbp+1250h]
  int v620; // [rsp+1358h] [rbp+1258h]
  const wchar_t *v621; // [rsp+1360h] [rbp+1260h]
  __int64 v622; // [rsp+1368h] [rbp+1268h]
  int v623; // [rsp+1370h] [rbp+1270h]
  const wchar_t *v624; // [rsp+1378h] [rbp+1278h]
  __int64 v625; // [rsp+1380h] [rbp+1280h]
  int v626; // [rsp+1388h] [rbp+1288h]
  const wchar_t *v627; // [rsp+1390h] [rbp+1290h]
  __int64 v628; // [rsp+1398h] [rbp+1298h]
  int v629; // [rsp+13A0h] [rbp+12A0h]
  const wchar_t *v630; // [rsp+13A8h] [rbp+12A8h]
  __int64 v631; // [rsp+13B0h] [rbp+12B0h]
  int v632; // [rsp+13B8h] [rbp+12B8h]
  const wchar_t *v633; // [rsp+13C0h] [rbp+12C0h]
  __int64 v634; // [rsp+13C8h] [rbp+12C8h]
  int v635; // [rsp+13D0h] [rbp+12D0h]
  const wchar_t *v636; // [rsp+13D8h] [rbp+12D8h]
  __int64 v637; // [rsp+13E0h] [rbp+12E0h]
  int v638; // [rsp+13E8h] [rbp+12E8h]
  const wchar_t *v639; // [rsp+13F0h] [rbp+12F0h]
  __int64 v640; // [rsp+13F8h] [rbp+12F8h]
  int v641; // [rsp+1400h] [rbp+1300h]
  const wchar_t *v642; // [rsp+1408h] [rbp+1308h]
  __int64 v643; // [rsp+1410h] [rbp+1310h]
  int v644; // [rsp+1418h] [rbp+1318h]
  const wchar_t *v645; // [rsp+1420h] [rbp+1320h]
  __int64 v646; // [rsp+1428h] [rbp+1328h]
  int v647; // [rsp+1430h] [rbp+1330h]
  const wchar_t *v648; // [rsp+1438h] [rbp+1338h]
  __int64 v649; // [rsp+1440h] [rbp+1340h]
  int v650; // [rsp+1448h] [rbp+1348h]
  const wchar_t *v651; // [rsp+1450h] [rbp+1350h]
  __int64 v652; // [rsp+1458h] [rbp+1358h]
  int v653; // [rsp+1460h] [rbp+1360h]
  const wchar_t *v654; // [rsp+1468h] [rbp+1368h]
  __int64 v655; // [rsp+1470h] [rbp+1370h]
  int v656; // [rsp+1478h] [rbp+1378h]
  const wchar_t *v657; // [rsp+1480h] [rbp+1380h]
  __int64 v658; // [rsp+1488h] [rbp+1388h]
  int v659; // [rsp+1490h] [rbp+1390h]
  const wchar_t *v660; // [rsp+1498h] [rbp+1398h]
  __int64 v661; // [rsp+14A0h] [rbp+13A0h]
  int v662; // [rsp+14A8h] [rbp+13A8h]
  const wchar_t *v663; // [rsp+14B0h] [rbp+13B0h]
  __int64 v664; // [rsp+14B8h] [rbp+13B8h]
  int v665; // [rsp+14C0h] [rbp+13C0h]
  const wchar_t *v666; // [rsp+14C8h] [rbp+13C8h]
  __int64 v667; // [rsp+14D0h] [rbp+13D0h]
  int v668; // [rsp+14D8h] [rbp+13D8h]
  const wchar_t *v669; // [rsp+14E0h] [rbp+13E0h]
  __int64 v670; // [rsp+14E8h] [rbp+13E8h]
  int v671; // [rsp+14F0h] [rbp+13F0h]
  const wchar_t *v672; // [rsp+14F8h] [rbp+13F8h]
  __int64 v673; // [rsp+1500h] [rbp+1400h]
  int v674; // [rsp+1508h] [rbp+1408h]
  const wchar_t *v675; // [rsp+1510h] [rbp+1410h]
  __int64 v676; // [rsp+1518h] [rbp+1418h]
  int v677; // [rsp+1520h] [rbp+1420h]
  const wchar_t *v678; // [rsp+1528h] [rbp+1428h]
  __int64 v679; // [rsp+1530h] [rbp+1430h]
  int v680; // [rsp+1538h] [rbp+1438h]
  const wchar_t *v681; // [rsp+1540h] [rbp+1440h]
  __int64 v682; // [rsp+1548h] [rbp+1448h]
  int v683; // [rsp+1550h] [rbp+1450h]
  const wchar_t *v684; // [rsp+1558h] [rbp+1458h]
  __int64 v685; // [rsp+1560h] [rbp+1460h]
  int v686; // [rsp+1568h] [rbp+1468h]
  const wchar_t *v687; // [rsp+1570h] [rbp+1470h]
  __int64 v688; // [rsp+1578h] [rbp+1478h]
  int v689; // [rsp+1580h] [rbp+1480h]
  const wchar_t *v690; // [rsp+1588h] [rbp+1488h]
  __int64 v691; // [rsp+1590h] [rbp+1490h]
  int v692; // [rsp+1598h] [rbp+1498h]
  const wchar_t *v693; // [rsp+15A0h] [rbp+14A0h]
  __int64 v694; // [rsp+15A8h] [rbp+14A8h]
  int v695; // [rsp+15B0h] [rbp+14B0h]
  const wchar_t *v696; // [rsp+15B8h] [rbp+14B8h]
  __int64 v697; // [rsp+15C0h] [rbp+14C0h]
  int v698; // [rsp+15C8h] [rbp+14C8h]
  const wchar_t *v699; // [rsp+15D0h] [rbp+14D0h]
  __int64 v700; // [rsp+15D8h] [rbp+14D8h]
  int v701; // [rsp+15E0h] [rbp+14E0h]
  const wchar_t *v702; // [rsp+15E8h] [rbp+14E8h]
  __int64 v703; // [rsp+15F0h] [rbp+14F0h]
  int v704; // [rsp+15F8h] [rbp+14F8h]
  const wchar_t *v705; // [rsp+1600h] [rbp+1500h]
  __int64 v706; // [rsp+1608h] [rbp+1508h]
  int v707; // [rsp+1610h] [rbp+1510h]
  const wchar_t *v708; // [rsp+1618h] [rbp+1518h]
  __int64 v709; // [rsp+1620h] [rbp+1520h]
  int v710; // [rsp+1628h] [rbp+1528h]
  const wchar_t *v711; // [rsp+1630h] [rbp+1530h]
  __int64 v712; // [rsp+1638h] [rbp+1538h]
  int v713; // [rsp+1640h] [rbp+1540h]
  const wchar_t *v714; // [rsp+1648h] [rbp+1548h]
  __int64 v715; // [rsp+1650h] [rbp+1550h]
  int v716; // [rsp+1658h] [rbp+1558h]
  const wchar_t *v717; // [rsp+1660h] [rbp+1560h]
  __int64 v718; // [rsp+1668h] [rbp+1568h]
  int v719; // [rsp+1670h] [rbp+1570h]
  const wchar_t *v720; // [rsp+1678h] [rbp+1578h]
  __int64 v721; // [rsp+1680h] [rbp+1580h]
  int v722; // [rsp+1688h] [rbp+1588h]
  const wchar_t *v723; // [rsp+1690h] [rbp+1590h]
  __int64 v724; // [rsp+1698h] [rbp+1598h]
  int v725; // [rsp+16A0h] [rbp+15A0h]
  const wchar_t *v726; // [rsp+16A8h] [rbp+15A8h]
  __int64 v727; // [rsp+16B0h] [rbp+15B0h]
  int v728; // [rsp+16B8h] [rbp+15B8h]
  const wchar_t *v729; // [rsp+16C0h] [rbp+15C0h]
  __int64 v730; // [rsp+16C8h] [rbp+15C8h]
  int v731; // [rsp+16D0h] [rbp+15D0h]
  const wchar_t *v732; // [rsp+16D8h] [rbp+15D8h]
  __int64 v733; // [rsp+16E0h] [rbp+15E0h]
  int v734; // [rsp+16E8h] [rbp+15E8h]
  const wchar_t *v735; // [rsp+16F0h] [rbp+15F0h]
  __int64 v736; // [rsp+16F8h] [rbp+15F8h]
  int v737; // [rsp+1700h] [rbp+1600h]
  const wchar_t *v738; // [rsp+1708h] [rbp+1608h]
  __int64 v739; // [rsp+1710h] [rbp+1610h]
  int v740; // [rsp+1718h] [rbp+1618h]
  const wchar_t *v741; // [rsp+1720h] [rbp+1620h]
  __int64 v742; // [rsp+1728h] [rbp+1628h]
  int v743; // [rsp+1730h] [rbp+1630h]
  const wchar_t *v744; // [rsp+1738h] [rbp+1638h]
  __int64 v745; // [rsp+1740h] [rbp+1640h]
  int v746; // [rsp+1748h] [rbp+1648h]
  const wchar_t *v747; // [rsp+1750h] [rbp+1650h]
  __int64 v748; // [rsp+1758h] [rbp+1658h]
  int v749; // [rsp+1760h] [rbp+1660h]
  const wchar_t *v750; // [rsp+1768h] [rbp+1668h]
  __int64 v751; // [rsp+1770h] [rbp+1670h]
  int v752; // [rsp+1778h] [rbp+1678h]
  const wchar_t *v753; // [rsp+1780h] [rbp+1680h]
  __int64 v754; // [rsp+1788h] [rbp+1688h]
  int v755; // [rsp+1790h] [rbp+1690h]
  const wchar_t *v756; // [rsp+1798h] [rbp+1698h]
  __int64 v757; // [rsp+17A0h] [rbp+16A0h]
  int v758; // [rsp+17A8h] [rbp+16A8h]
  const wchar_t *v759; // [rsp+17B0h] [rbp+16B0h]
  __int64 v760; // [rsp+17B8h] [rbp+16B8h]
  int v761; // [rsp+17C0h] [rbp+16C0h]
  const wchar_t *v762; // [rsp+17C8h] [rbp+16C8h]
  __int64 v763; // [rsp+17D0h] [rbp+16D0h]
  int v764; // [rsp+17D8h] [rbp+16D8h]
  const wchar_t *v765; // [rsp+17E0h] [rbp+16E0h]
  __int64 v766; // [rsp+17E8h] [rbp+16E8h]
  int v767; // [rsp+17F0h] [rbp+16F0h]
  const wchar_t *v768; // [rsp+17F8h] [rbp+16F8h]
  __int64 v769; // [rsp+1800h] [rbp+1700h]
  int v770; // [rsp+1808h] [rbp+1708h]
  const wchar_t *v771; // [rsp+1810h] [rbp+1710h]
  __int64 v772; // [rsp+1818h] [rbp+1718h]
  int v773; // [rsp+1820h] [rbp+1720h]
  const wchar_t *v774; // [rsp+1828h] [rbp+1728h]
  __int64 v775; // [rsp+1830h] [rbp+1730h]
  int v776; // [rsp+1838h] [rbp+1738h]
  const wchar_t *v777; // [rsp+1840h] [rbp+1740h]
  __int64 v778; // [rsp+1848h] [rbp+1748h]
  int v779; // [rsp+1850h] [rbp+1750h]
  const wchar_t *v780; // [rsp+1858h] [rbp+1758h]
  __int64 v781; // [rsp+1860h] [rbp+1760h]
  int v782; // [rsp+1868h] [rbp+1768h]
  const wchar_t *v783; // [rsp+1870h] [rbp+1770h]
  __int64 v784; // [rsp+1878h] [rbp+1778h]
  int v785; // [rsp+1880h] [rbp+1780h]
  const wchar_t *v786; // [rsp+1888h] [rbp+1788h]
  __int64 v787; // [rsp+1890h] [rbp+1790h]
  int v788; // [rsp+1898h] [rbp+1798h]
  const wchar_t *v789; // [rsp+18A0h] [rbp+17A0h]
  __int64 v790; // [rsp+18A8h] [rbp+17A8h]
  int v791; // [rsp+18B0h] [rbp+17B0h]
  const wchar_t *v792; // [rsp+18B8h] [rbp+17B8h]
  __int64 v793; // [rsp+18C0h] [rbp+17C0h]
  int v794; // [rsp+18C8h] [rbp+17C8h]
  const wchar_t *v795; // [rsp+18D0h] [rbp+17D0h]
  __int64 v796; // [rsp+18D8h] [rbp+17D8h]
  int v797; // [rsp+18E0h] [rbp+17E0h]
  const wchar_t *v798; // [rsp+18E8h] [rbp+17E8h]
  __int64 v799; // [rsp+18F0h] [rbp+17F0h]
  int v800; // [rsp+18F8h] [rbp+17F8h]
  const wchar_t *v801; // [rsp+1900h] [rbp+1800h]
  __int64 v802; // [rsp+1908h] [rbp+1808h]
  int v803; // [rsp+1910h] [rbp+1810h]
  const wchar_t *v804; // [rsp+1918h] [rbp+1818h]
  __int64 v805; // [rsp+1920h] [rbp+1820h]
  int v806; // [rsp+1928h] [rbp+1828h]
  const wchar_t *v807; // [rsp+1930h] [rbp+1830h]
  __int64 v808; // [rsp+1938h] [rbp+1838h]
  int v809; // [rsp+1940h] [rbp+1840h]
  const wchar_t *v810; // [rsp+1948h] [rbp+1848h]
  __int64 v811; // [rsp+1950h] [rbp+1850h]
  int v812; // [rsp+1958h] [rbp+1858h]
  const wchar_t *v813; // [rsp+1960h] [rbp+1860h]
  __int64 v814; // [rsp+1968h] [rbp+1868h]
  int v815; // [rsp+1970h] [rbp+1870h]
  const wchar_t *v816; // [rsp+1978h] [rbp+1878h]
  __int64 v817; // [rsp+1980h] [rbp+1880h]
  int v818; // [rsp+1988h] [rbp+1888h]
  const wchar_t *v819; // [rsp+1990h] [rbp+1890h]
  __int64 v820; // [rsp+1998h] [rbp+1898h]
  int v821; // [rsp+19A0h] [rbp+18A0h]
  char v822; // [rsp+19A8h] [rbp+18A8h] BYREF

  if ( dword_180195118 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180195118);
    if ( dword_180195118 == -1 )
    {
      v16[0] = L"accent-height";
      v16[1] = 13;
      v17 = 0;
      v18 = L"accumulate";
      v19 = 10;
      v20 = 0;
      v21 = L"additive";
      v22 = 8;
      v23 = 0;
      v24 = L"alignment-baseline";
      v25 = 18;
      v26 = 0;
      v27 = L"alphabetic";
      v28 = 10;
      v29 = 0;
      v30 = L"amplitude";
      v31 = 9;
      v32 = 0;
      v33 = L"arabic-form";
      v34 = 11;
      v35 = 0;
      v36 = L"ascent";
      v37 = 6;
      v38 = 0;
      v39 = L"attributeName";
      v40 = 13;
      v41 = 0;
      v42 = L"attributeType";
      v43 = 13;
      v44 = 0;
      v45 = L"azimuth";
      v46 = 7;
      v47 = 0;
      v48 = L"baseFrequency";
      v49 = 13;
      v50 = 0;
      v51 = L"baseProfile";
      v52 = 11;
      v53 = 0;
      v54 = L"baseline-shift";
      v55 = 14;
      v56 = 0;
      v57 = L"bbox";
      v58 = 4;
      v59 = 0;
      v60 = L"begin";
      v61 = 5;
      v62 = 0;
      v63 = L"bias";
      v64 = 4;
      v65 = 0;
      v66 = L"by";
      v67 = 2;
      v68 = 0;
      v69 = L"calcMode";
      v70 = 8;
      v71 = 0;
      v72 = L"cap-height";
      v73 = 10;
      v74 = 0;
      v75 = L"class";
      v76 = 5;
      v77 = 0;
      v78 = L"clip";
      v79 = 4;
      v80 = 0;
      v81 = L"clip-path";
      v82 = 9;
      v83 = 0;
      v84 = L"clip-rule";
      v85 = 9;
      v86 = 0;
      v87 = L"clipPathUnits";
      v88 = 13;
      v89 = 0;
      v90 = L"color";
      v91 = 5;
      v92 = 0;
      v93 = L"color-interpolation";
      v94 = 19;
      v95 = 0;
      v96 = L"color-interpolation-filters";
      v97 = 27;
      v98 = 0;
      v99 = L"color-profile";
      v100 = 13;
      v101 = 0;
      v102 = L"color-rendering";
      v103 = 15;
      v104 = 0;
      v105 = L"contentScriptType";
      v106 = 17;
      v107 = 0;
      v108 = L"contentStyleType";
      v109 = 16;
      v110 = 0;
      v111 = L"cursor";
      v112 = 6;
      v113 = 0;
      v114 = L"cx";
      v115 = 2;
      v116 = 0;
      v117 = L"cy";
      v118 = 2;
      v119 = 0;
      v120 = L"d";
      v121 = 1;
      v122 = 0;
      v123 = L"descent";
      v124 = 7;
      v125 = 0;
      v126 = L"diffuseConstant";
      v127 = 15;
      v128 = 0;
      v129 = L"direction";
      v130 = 9;
      v131 = 0;
      v132 = L"display";
      v133 = 7;
      v134 = 0;
      v135 = L"divisor";
      v136 = 7;
      v137 = 0;
      v138 = L"dominant-baseline";
      v139 = 17;
      v140 = 0;
      v141 = L"dur";
      v142 = 3;
      v143 = 0;
      v144 = L"dx";
      v145 = 2;
      v146 = 0;
      v147 = L"dy";
      v148 = 2;
      v149 = 0;
      v150 = L"edgeMode";
      v151 = 8;
      v152 = 0;
      v153 = L"elevation";
      v154 = 9;
      v155 = 0;
      v156 = L"enable-background";
      v157 = 17;
      v158 = 0;
      v159 = L"end";
      v160 = 3;
      v161 = 0;
      v162 = L"exponent";
      v163 = 8;
      v164 = 0;
      v165 = L"externalResourcesRequired";
      v166 = 25;
      v167 = 0;
      v168 = L"fill";
      v169 = 4;
      v170 = 0;
      v171 = L"fill-opacity";
      v172 = 12;
      v173 = 0;
      v174 = L"fill-rule";
      v175 = 9;
      v176 = 0;
      v177 = L"filter";
      v178 = 6;
      v179 = 0;
      v180 = L"filterRes";
      v181 = 9;
      v182 = 0;
      v183 = L"filterUnits";
      v184 = 11;
      v185 = 0;
      v186 = L"flood-color";
      v187 = 11;
      v188 = 0;
      v189 = L"flood-opacity";
      v190 = 13;
      v191 = 0;
      v192 = L"font";
      v193 = 4;
      v194 = 0;
      v195 = L"font-family";
      v196 = 11;
      v197 = 0;
      v198 = L"font-size";
      v199 = 9;
      v200 = 0;
      v201 = L"font-size-adjust";
      v202 = 16;
      v203 = 0;
      v204 = L"font-stretch";
      v205 = 12;
      v206 = 0;
      v207 = L"font-style";
      v208 = 10;
      v209 = 0;
      v210 = L"font-variant";
      v211 = 12;
      v212 = 0;
      v213 = L"font-weight";
      v214 = 11;
      v215 = 0;
      v216 = L"format";
      v217 = 6;
      v218 = 0;
      v219 = L"from";
      v220 = 4;
      v221 = 0;
      v222 = L"fx";
      v223 = 2;
      v224 = 0;
      v225 = L"fy";
      v226 = 2;
      v227 = 0;
      v228 = L"g1";
      v229 = 2;
      v230 = 0;
      v231 = L"g2";
      v232 = 2;
      v233 = 0;
      v234 = L"glyph-name";
      v235 = 10;
      v236 = 0;
      v237 = L"glyph-orientation-horizontal";
      v238 = 28;
      v239 = 0;
      v240 = L"glyph-orientation-vertical";
      v241 = 26;
      v242 = 0;
      v243 = L"glyphRef";
      v244 = 8;
      v245 = 0;
      v246 = L"gradientTransform";
      v247 = 17;
      v248 = 0;
      v249 = L"gradientUnits";
      v250 = 13;
      v251 = 0;
      v252 = L"hanging";
      v253 = 7;
      v254 = 0;
      v255 = L"height";
      v256 = 6;
      v257 = 0;
      v258 = L"horiz-adv-x";
      v259 = 11;
      v260 = 0;
      v261 = L"horiz-origin-x";
      v262 = 14;
      v263 = 0;
      v264 = L"horiz-origin-y";
      v265 = 14;
      v266 = 0;
      v267 = L"id";
      v268 = 2;
      v269 = 0;
      v270 = L"ideographic";
      v271 = 11;
      v272 = 0;
      v273 = L"image-rendering";
      v274 = 15;
      v275 = 0;
      v276 = L"in";
      v277 = 2;
      v278 = 0;
      v279 = L"in2";
      v280 = 3;
      v281 = 0;
      v282 = L"intercept";
      v283 = 9;
      v284 = 0;
      v285 = L"k";
      v286 = 1;
      v287 = 0;
      v288 = L"k1";
      v289 = 2;
      v290 = 0;
      v291 = L"k2";
      v292 = 2;
      v293 = 0;
      v294 = L"k3";
      v295 = 2;
      v296 = 0;
      v297 = L"k4";
      v298 = 2;
      v299 = 0;
      v300 = L"kernelMatrix";
      v301 = 12;
      v302 = 0;
      v303 = L"kernelUnitLength";
      v304 = 16;
      v305 = 0;
      v306 = L"kerning";
      v307 = 7;
      v308 = 0;
      v309 = L"keyPoints";
      v310 = 9;
      v311 = 0;
      v312 = L"keySplines";
      v313 = 10;
      v314 = 0;
      v315 = L"keyTimes";
      v316 = 8;
      v317 = 0;
      v318 = L"lang";
      v319 = 4;
      v320 = 0;
      v321 = L"lengthAdjust";
      v322 = 12;
      v323 = 0;
      v324 = L"letter-spacing";
      v325 = 14;
      v326 = 0;
      v327 = L"lighting-color";
      v328 = 14;
      v329 = 0;
      v330 = L"limitingConeAngle";
      v331 = 17;
      v332 = 0;
      v333 = L"local";
      v334 = 5;
      v335 = 0;
      v336 = L"marker";
      v337 = 6;
      v338 = 0;
      v339 = L"marker-end";
      v340 = 10;
      v341 = 0;
      v342 = L"marker-mid";
      v343 = 10;
      v344 = 0;
      v345 = L"marker-start";
      v346 = 12;
      v347 = 0;
      v348 = L"markerHeight";
      v349 = 12;
      v350 = 0;
      v351 = L"markerUnits";
      v352 = 11;
      v353 = 0;
      v354 = L"markerWidth";
      v355 = 11;
      v356 = 0;
      v357 = L"mask";
      v358 = 4;
      v359 = 0;
      v360 = L"maskContentUnits";
      v361 = 16;
      v362 = 0;
      v363 = L"maskUnits";
      v364 = 9;
      v365 = 0;
      v366 = L"mathematical";
      v367 = 12;
      v368 = 0;
      v369 = L"max";
      v370 = 3;
      v371 = 0;
      v372 = L"media";
      v373 = 5;
      v374 = 0;
      v375 = L"method";
      v376 = 6;
      v377 = 0;
      v378 = L"min";
      v379 = 3;
      v380 = 0;
      v381 = L"mode";
      v382 = 4;
      v383 = 0;
      v384 = L"name";
      v385 = 4;
      v386 = 0;
      v387 = L"numOctaves";
      v388 = 10;
      v389 = 0;
      v390 = L"offset";
      v391 = 6;
      v392 = 0;
      v393 = L"onabort";
      v394 = 7;
      v395 = 0;
      v396 = L"onactivate";
      v397 = 10;
      v398 = 0;
      v399 = L"onbegin";
      v400 = 7;
      v401 = 0;
      v402 = L"onclick";
      v403 = 7;
      v404 = 0;
      v405 = L"onend";
      v406 = 5;
      v407 = 0;
      v408 = L"onerror";
      v409 = 7;
      v410 = 0;
      v411 = L"onfocusin";
      v412 = 9;
      v413 = 0;
      v414 = L"onfocusout";
      v415 = 10;
      v416 = 0;
      v417 = L"onload";
      v418 = 6;
      v419 = 0;
      v420 = L"onmousedown";
      v421 = 11;
      v422 = 0;
      v423 = L"onmousemove";
      v424 = 11;
      v425 = 0;
      v426 = L"onmouseout";
      v427 = 10;
      v428 = 0;
      v429 = L"onmouseover";
      v430 = 11;
      v431 = 0;
      v432 = L"onmouseup";
      v433 = 9;
      v434 = 0;
      v435 = L"onrepeat";
      v436 = 8;
      v437 = 0;
      v438 = L"onresize";
      v439 = 8;
      v440 = 0;
      v441 = L"onscroll";
      v442 = 8;
      v443 = 0;
      v444 = L"onunload";
      v445 = 8;
      v446 = 0;
      v447 = L"onzoom";
      v448 = 6;
      v449 = 0;
      v450 = L"opacity";
      v451 = 7;
      v452 = 0;
      v453 = L"operator";
      v454 = 8;
      v455 = 0;
      v456 = L"order";
      v457 = 5;
      v458 = 0;
      v459 = L"orient";
      v460 = 6;
      v461 = 0;
      v462 = L"orientation";
      v463 = 11;
      v464 = 0;
      v465 = L"origin";
      v466 = 6;
      v467 = 0;
      v468 = L"overflow";
      v469 = 8;
      v470 = 0;
      v471 = L"overline-position";
      v472 = 17;
      v473 = 0;
      v474 = L"overline-thickness";
      v475 = 18;
      v476 = 0;
      v477 = L"panose-1";
      v478 = 8;
      v479 = 0;
      v480 = L"path";
      v481 = 4;
      v482 = 0;
      v483 = L"pathLength";
      v484 = 10;
      v485 = 0;
      v486 = L"patternContentUnits";
      v487 = 19;
      v488 = 0;
      v489 = L"patternTransform";
      v490 = 16;
      v491 = 0;
      v492 = L"patternUnits";
      v493 = 12;
      v494 = 0;
      v495 = L"pointer-events";
      v496 = 14;
      v497 = 0;
      v498 = L"points";
      v499 = 6;
      v500 = 0;
      v501 = L"pointsAtX";
      v502 = 9;
      v503 = 0;
      v504 = L"pointsAtY";
      v505 = 9;
      v506 = 0;
      v507 = L"pointsAtZ";
      v508 = 9;
      v509 = 0;
      v510 = L"preserveAlpha";
      v511 = 13;
      v512 = 0;
      v513 = L"preserveAspectRatio";
      v514 = 19;
      v515 = 0;
      v516 = L"primitiveUnits";
      v517 = 14;
      v518 = 0;
      v519 = L"r";
      v520 = 1;
      v521 = 0;
      v522 = L"radius";
      v523 = 6;
      v524 = 0;
      v525 = L"refX";
      v526 = 4;
      v527 = 0;
      v528 = L"refY";
      v529 = 4;
      v530 = 0;
      v531 = L"rendering-intent";
      v532 = 16;
      v533 = 0;
      v534 = L"repeatCount";
      v535 = 11;
      v536 = 0;
      v537 = L"repeatDur";
      v538 = 9;
      v539 = 0;
      v540 = L"requiredExtensions";
      v541 = 18;
      v542 = 0;
      v543 = L"requiredFeatures";
      v544 = 16;
      v545 = 0;
      v546 = L"restart";
      v547 = 7;
      v548 = 0;
      v549 = L"result";
      v550 = 6;
      v551 = 0;
      v552 = L"rotate";
      v553 = 6;
      v554 = 0;
      v555 = L"rx";
      v556 = 2;
      v557 = 0;
      v558 = L"ry";
      v559 = 2;
      v560 = 0;
      v561 = L"scale";
      v562 = 5;
      v563 = 0;
      v564 = L"seed";
      v565 = 4;
      v566 = 0;
      v567 = L"shape-rendering";
      v568 = 15;
      v569 = 0;
      v570 = L"slope";
      v571 = 5;
      v572 = 0;
      v573 = L"spacing";
      v574 = 7;
      v575 = 0;
      v576 = L"specularConstant";
      v577 = 16;
      v578 = 0;
      v579 = L"specularExponent";
      v580 = 16;
      v581 = 0;
      v582 = L"spreadMethod";
      v583 = 12;
      v584 = 0;
      v585 = L"startOffset";
      v586 = 11;
      v587 = 0;
      v588 = L"stdDeviation";
      v589 = 12;
      v590 = 0;
      v591 = L"stemh";
      v592 = 5;
      v593 = 0;
      v594 = L"stemv";
      v595 = 5;
      v596 = 0;
      v597 = L"stitchTiles";
      v598 = 11;
      v599 = 0;
      v600 = L"stop-color";
      v601 = 10;
      v602 = 0;
      v603 = L"stop-opacity";
      v604 = 12;
      v605 = 0;
      v606 = L"strikethrough-position";
      v607 = 22;
      v608 = 0;
      v609 = L"strikethrough-thickness";
      v610 = 23;
      v611 = 0;
      v612 = L"string";
      v613 = 6;
      v614 = 0;
      v615 = L"stroke";
      v616 = 6;
      v617 = 0;
      v618 = L"stroke-dasharray";
      v619 = 16;
      v620 = 0;
      v621 = L"stroke-dashoffset";
      v622 = 17;
      v623 = 0;
      v624 = L"stroke-linecap";
      v625 = 14;
      v626 = 0;
      v627 = L"stroke-linejoin";
      v628 = 15;
      v629 = 0;
      v630 = L"stroke-miterlimit";
      v631 = 17;
      v632 = 0;
      v633 = L"stroke-opacity";
      v634 = 14;
      v635 = 0;
      v636 = L"stroke-width";
      v637 = 12;
      v638 = 0;
      v639 = L"style";
      v640 = 5;
      v641 = 0;
      v642 = L"surfaceScale";
      v643 = 12;
      v644 = 0;
      v645 = L"systemLanguage";
      v646 = 14;
      v647 = 0;
      v648 = L"tableValues";
      v649 = 11;
      v650 = 0;
      v651 = L"target";
      v652 = 6;
      v653 = 0;
      v654 = L"targetX";
      v655 = 7;
      v656 = 0;
      v657 = L"targetY";
      v658 = 7;
      v659 = 0;
      v660 = L"text-anchor";
      v661 = 11;
      v662 = 0;
      v663 = L"text-decoration";
      v664 = 15;
      v665 = 0;
      v666 = L"text-rendering";
      v667 = 14;
      v668 = 0;
      v669 = L"textLength";
      v670 = 10;
      v671 = 0;
      v672 = L"title";
      v673 = 5;
      v674 = 0;
      v675 = L"to";
      v676 = 2;
      v677 = 0;
      v678 = L"transform";
      v679 = 9;
      v680 = 0;
      v681 = L"type";
      v682 = 4;
      v683 = 0;
      v684 = L"u1";
      v685 = 2;
      v686 = 0;
      v687 = L"u2";
      v688 = 2;
      v689 = 0;
      v690 = L"underline-position";
      v691 = 18;
      v692 = 0;
      v693 = L"underline-thickness";
      v694 = 19;
      v695 = 0;
      v696 = L"unicode";
      v697 = 7;
      v698 = 0;
      v699 = L"unicode-bidi";
      v700 = 12;
      v701 = 0;
      v702 = L"unicode-range";
      v703 = 13;
      v704 = 0;
      v705 = L"units-per-em";
      v706 = 12;
      v707 = 0;
      v708 = L"v-alphabetic";
      v709 = 12;
      v710 = 0;
      v711 = L"v-hanging";
      v712 = 9;
      v713 = 0;
      v714 = L"v-ideographic";
      v715 = 13;
      v716 = 0;
      v717 = L"v-mathematical";
      v718 = 14;
      v719 = 0;
      v720 = L"values";
      v721 = 6;
      v722 = 0;
      v723 = L"version";
      v724 = 7;
      v725 = 0;
      v726 = L"vert-adv-y";
      v727 = 10;
      v728 = 0;
      v729 = L"vert-origin-x";
      v730 = 13;
      v731 = 0;
      v732 = L"vert-origin-y";
      v733 = 13;
      v734 = 0;
      v735 = L"viewBox";
      v736 = 7;
      v737 = 0;
      v738 = L"viewTarget";
      v739 = 10;
      v740 = 0;
      v741 = L"visibility";
      v742 = 10;
      v743 = 0;
      v744 = L"white-space";
      v745 = 11;
      v746 = 0;
      v747 = L"width";
      v748 = 5;
      v749 = 0;
      v750 = L"widths";
      v751 = 6;
      v752 = 0;
      v753 = L"word-spacing";
      v754 = 12;
      v755 = 0;
      v756 = L"writing-mode";
      v757 = 12;
      v758 = 0;
      v759 = L"x";
      v760 = 1;
      v761 = 0;
      v762 = L"x-height";
      v763 = 8;
      v764 = 0;
      v765 = L"x1";
      v766 = 2;
      v767 = 0;
      v768 = L"x2";
      v769 = 2;
      v770 = 0;
      v771 = L"xChannelSelector";
      v772 = 16;
      v773 = 0;
      v774 = L"actuate";
      v775 = 7;
      v776 = 2;
      v777 = L"arcrole";
      v778 = 7;
      v779 = 2;
      v780 = L"href";
      v781 = 4;
      v782 = 2;
      v783 = L"role";
      v784 = 4;
      v785 = 2;
      v786 = L"show";
      v787 = 4;
      v788 = 2;
      v789 = L"title";
      v790 = 5;
      v791 = 2;
      v792 = L"type";
      v793 = 4;
      v794 = 2;
      v795 = L"base";
      v796 = 4;
      v797 = 1;
      v798 = L"lang";
      v799 = 4;
      v800 = 1;
      v801 = L"space";
      v802 = 5;
      v803 = 1;
      v804 = L"y";
      v805 = 1;
      v806 = 0;
      v807 = L"y1";
      v808 = 2;
      v809 = 0;
      v810 = L"y2";
      v811 = 2;
      v812 = 0;
      v813 = L"yChannelSelector";
      v814 = 16;
      v815 = 0;
      v816 = L"z";
      v817 = 1;
      v818 = 0;
      v819 = L"zoomAndPan";
      v820 = 10;
      v821 = 0;
      v14[0] = v16;
      v14[1] = &v822;
      std::vector<std::pair<std::wstring_view,enum svgpp::detail::namespace_id>>::vector<std::pair<std::wstring_view,enum svgpp::detail::namespace_id>>(
        7,
        v14);
      atexit(sub_1801425F0);
      Init_thread_footer(&dword_180195118);
    }
  }
  fPending[1] = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending[1], 0) )
    abort();
  if ( fPending[1] )
  {
    HIDWORD(v13) = 0;
    LOBYTE(v2) = fPending[0];
    std::_Sort_unchecked<std::pair<std::wstring_view,enum svgpp::detail::namespace_id> *,svgpp::policy::xml::LessThan>(
      xmmword_180195100,
      *((_QWORD *)&xmmword_180195100 + 1),
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&xmmword_180195100 + 1) - xmmword_180195100) >> 3),
      v2);
    v12 = L"lang";
    v13 = 4;
    v14[0] = xmmword_180195100;
    sub_180009538(v15, v3, v14, &v12);
    v12 = L"title";
    v13 = 5;
    v15[0] = *(_QWORD *)sub_180009538(v14, v4, v15, &v12);
    v12 = L"type";
    v13 = 4;
    sub_180009538(v14, v15[0], v15, &v12);
    if ( !InitOnceComplete(&InitOnce, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  std::lower_bound<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<std::wstring_view,enum svgpp::detail::namespace_id>>>>,std::wstring_view,svgpp::policy::xml::LessThan>(
    v14,
    xmmword_180195100,
    *((_QWORD *)&xmmword_180195100 + 1),
    a1);
  v5 = v14[0];
  if ( v14[0] == *((_QWORD *)&xmmword_180195100 + 1) )
    return 3;
  v6 = *a1;
  v7 = *(_QWORD *)(v14[0] + 8LL);
  v8 = v7;
  v9 = _mm_srli_si128(v6, 8).m128i_u64[0];
  if ( v9 < v7 )
    v8 = v9;
  if ( wmemcmp(*(const wchar_t **)v14[0], (const wchar_t *)v6.m128i_i64[0], v8) || v7 < v9 || v7 > v9 )
    return 3;
  else
    return *(unsigned int *)(v5 + 16);
}

```

## disassembly

```asm
0x180009618  mov     rax, rsp
0x18000961b  mov     [rax+10h], rbx
0x18000961f  mov     [rax+18h], rsi
0x180009623  mov     [rax+20h], rdi
0x180009627  push    rbp
0x180009628  push    r12
0x18000962a  push    r13
0x18000962c  push    r14
0x18000962e  push    r15
0x180009630  lea     rbp, [rax-18E8h]
0x180009637  mov     eax, 19C0h
0x18000963c  call    _alloca_probe
0x180009641  sub     rsp, rax
0x180009644  mov     rax, cs:__security_cookie
0x18000964b  xor     rax, rsp
0x18000964e  mov     [rbp+18E0h+var_30], rax
0x180009655  mov     rdi, rcx
0x180009658  mov     edx, cs:_tls_index
0x18000965e  mov     rax, gs:58h
0x180009667  mov     ecx, 4
0x18000966c  mov     rax, [rax+rdx*8]
0x180009670  xor     r14d, r14d
0x180009673  lea     ebx, [r14+4]
0x180009677  lea     r15d, [r14+5]
0x18000967b  lea     rsi, aLang; "lang"
0x180009682  lea     r12, aTitle; "title"
0x180009689  lea     r13, aType; "type"
0x180009690  mov     eax, [rcx+rax]
0x180009693  cmp     cs:dword_180195118, eax
0x180009699  jg      loc_180009836
0x18000969f  mov     [rsp+19E0h+fPending+4], r14d
0x1800096a4  xor     r9d, r9d; lpContext
0x1800096a7  lea     r8, [rsp+19E0h+fPending+4]; fPending
0x1800096ac  xor     edx, edx; dwFlags
0x1800096ae  lea     rcx, InitOnce; lpInitOnce
0x1800096b5  call    cs:__imp___std_init_once_begin_initialize
0x1800096bb  test    eax, eax
0x1800096bd  jnz     short loc_1800096C6
0x1800096bf  call    cs:__imp_abort
0x1800096c6  cmp     [rsp+19E0h+fPending+4], r14d
0x1800096cb  jz      loc_18000978F
0x1800096d1  xor     eax, eax
0x1800096d3  mov     dword ptr [rsp+19E0h+var_19A0+4], eax
0x1800096d7  mov     rdx, qword ptr cs:xmmword_180195100+8
0x1800096de  mov     r8, rdx
0x1800096e1  mov     rcx, qword ptr cs:xmmword_180195100
0x1800096e8  sub     r8, rcx
0x1800096eb  sar     r8, 3
0x1800096ef  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800096f9  imul    r8, rax
0x1800096fd  mov     r9b, byte ptr [rsp+19E0h+fPending]
0x180009702  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4namespace_id@detail@svgpp@@@std@@ULessThan@xml@policy@svgpp@@@std@@YAXPEAU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4namespace_id@detail@svgpp@@@0@0_JULessThan@xml@policy@svgpp@@@Z; std::_Sort_unchecked<std::pair<std::wstring_view,svgpp::detail::namespace_id> *,svgpp::policy::xml::LessThan>(std::pair<std::wstring_view,svgpp::detail::namespace_id> *,std::pair<std::wstring_view,svgpp::detail::namespace_id> *,__int64,svgpp::policy::xml::LessThan)
0x180009707  mov     [rsp+19E0h+var_19A8], rsi
0x18000970c  mov     [rsp+19E0h+var_19A0], rbx
0x180009711  mov     rax, qword ptr cs:xmmword_180195100
0x180009718  mov     [rsp+19E0h+var_1990], rax
0x18000971d  lea     r9, [rsp+19E0h+var_19A8]
0x180009722  lea     r8, [rsp+19E0h+var_1990]
0x180009727  lea     rcx, [rsp+19E0h+var_1980]
0x18000972c  call    sub_180009538
0x180009731  mov     [rsp+19E0h+var_19A8], r12
0x180009736  mov     [rsp+19E0h+var_19A0], r15
0x18000973b  lea     r9, [rsp+19E0h+var_19A8]
0x180009740  lea     r8, [rsp+19E0h+var_1980]
0x180009745  lea     rcx, [rsp+19E0h+var_1990]
0x18000974a  call    sub_180009538
0x18000974f  mov     rdx, [rax]
0x180009752  mov     [rsp+19E0h+var_1980], rdx
0x180009757  mov     [rsp+19E0h+var_19A8], r13
0x18000975c  mov     [rsp+19E0h+var_19A0], rbx
0x180009761  lea     r9, [rsp+19E0h+var_19A8]
0x180009766  lea     r8, [rsp+19E0h+var_1980]
0x18000976b  lea     rcx, [rsp+19E0h+var_1990]
0x180009770  call    sub_180009538
0x180009775  xor     r8d, r8d; lpContext
0x180009778  xor     edx, edx; dwFlags
0x18000977a  lea     rcx, InitOnce; lpInitOnce
0x180009781  call    cs:__imp_InitOnceComplete
0x180009787  test    eax, eax
0x180009789  jz      loc_180009830
0x18000978f  mov     r9, rdi
0x180009792  mov     r8, qword ptr cs:xmmword_180195100+8
0x180009799  mov     rdx, qword ptr cs:xmmword_180195100
0x1800097a0  lea     rcx, [rsp+19E0h+var_1990]
0x1800097a5  call    ??$lower_bound@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4namespace_id@detail@svgpp@@@std@@@std@@@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@ULessThan@xml@policy@svgpp@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4namespace_id@detail@svgpp@@@std@@@std@@@std@@@0@V10@V10@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@0@ULessThan@xml@policy@svgpp@@@Z; std::lower_bound<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<std::wstring_view,svgpp::detail::namespace_id>>>>,std::wstring_view,svgpp::policy::xml::LessThan>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<std::wstring_view,svgpp::detail::namespace_id>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::pair<std::wstring_view,svgpp::detail::namespace_id>>>>,std::wstring_view const &,svgpp::policy::xml::LessThan)
0x1800097aa  mov     rbx, [rsp+19E0h+var_1990]
0x1800097af  cmp     rbx, qword ptr cs:xmmword_180195100+8
0x1800097b6  jz      short loc_1800097FB
0x1800097b8  movups  xmm1, xmmword ptr [rdi]
0x1800097bb  mov     rdi, [rbx+8]
0x1800097bf  mov     r8, rdi
0x1800097c2  movdqa  xmm0, xmm1
0x1800097c6  psrldq  xmm0, 8
0x1800097cb  movq    rsi, xmm0
0x1800097d0  cmp     rsi, rdi
0x1800097d3  cmovb   r8, rsi; N
0x1800097d7  movq    rdx, xmm1; S2
0x1800097dc  mov     rcx, [rbx]; S1
0x1800097df  call    wmemcmp
0x1800097e4  test    eax, eax
0x1800097e6  jnz     short loc_1800097FB
0x1800097e8  cmp     rdi, rsi
0x1800097eb  jb      short loc_1800097FB
0x1800097ed  ja      short loc_1800097FB
0x1800097ef  mov     eax, r14d
0x1800097f2  test    eax, eax
0x1800097f4  jnz     short loc_1800097FB
0x1800097f6  mov     eax, [rbx+10h]
0x1800097f9  jmp     short loc_180009800
0x1800097fb  mov     eax, 3
0x180009800  mov     rcx, [rbp+18E0h+var_30]
0x180009807  xor     rcx, rsp; StackCookie
0x18000980a  call    __security_check_cookie
0x18000980f  lea     r11, [rsp+19E0h+var_20]
0x180009817  mov     rbx, [r11+38h]
0x18000981b  mov     rsi, [r11+40h]
0x18000981f  mov     rdi, [r11+48h]
0x180009823  mov     rsp, r11
0x180009826  pop     r15
0x180009828  pop     r14
0x18000982a  pop     r13
0x18000982c  pop     r12
0x18000982e  pop     rbp
0x18000982f  retn
0x180009830  call    __std_init_once_link_alternate_names_and_abort
0x180009836  lea     rcx, dword_180195118
0x18000983d  call    _Init_thread_header
0x180009842  cmp     cs:dword_180195118, 0FFFFFFFFh
0x180009849  jnz     loc_18000969F
0x18000984f  lea     rax, aAccentHeight; "accent-height"
0x180009856  mov     [rsp+19E0h+var_1970], rax
0x18000985b  mov     r13d, 0Dh
0x180009861  mov     [rsp+19E0h+var_1968], r13
0x180009866  mov     [rbp+18E0h+var_1960], r14d
0x18000986a  lea     rax, aAccumulate; "accumulate"
0x180009871  mov     [rbp+18E0h+var_1958], rax
0x180009875  lea     edx, [r13-3]
0x180009879  mov     [rbp+18E0h+var_1950], rdx
0x18000987d  mov     [rbp+18E0h+var_1948], r14d
0x180009881  lea     rax, aAdditive; "additive"
0x180009888  mov     [rbp+18E0h+var_1940], rax
0x18000988c  lea     ecx, [rdx-2]
0x18000988f  mov     [rbp+18E0h+var_1938], rcx
0x180009893  mov     [rbp+18E0h+var_1930], r14d
0x180009897  lea     rax, aAlignmentBasel; "alignment-baseline"
0x18000989e  mov     [rbp+18E0h+var_1928], rax
0x1800098a2  lea     r11d, [r13+5]
0x1800098a6  mov     [rbp+18E0h+var_1920], r11
0x1800098aa  mov     [rbp+18E0h+var_1918], r14d
0x1800098ae  lea     rax, aAlphabetic; "alphabetic"
0x1800098b5  mov     [rbp+18E0h+var_1910], rax
0x1800098b9  mov     [rbp+18E0h+var_1908], rdx
0x1800098bd  mov     [rbp+18E0h+var_1900], r14d
0x1800098c1  lea     rax, aAmplitude; "amplitude"
0x1800098c8  mov     [rbp+18E0h+var_18F8], rax
0x1800098cc  lea     ebx, [rdx-1]
0x1800098cf  mov     [rbp+18E0h+var_18F0], rbx
0x1800098d3  mov     [rbp+18E0h+var_18E8], r14d
0x1800098d7  lea     rax, aArabicForm; "arabic-form"
0x1800098de  mov     [rbp+18E0h+var_18E0], rax
0x1800098e2  lea     r15d, [r13-2]
0x1800098e6  mov     [rbp+18E0h+var_18D8], r15
0x1800098ea  mov     [rbp+18E0h+var_18D0], r14d
0x1800098ee  lea     rax, aAscent; "ascent"
0x1800098f5  mov     [rbp+18E0h+var_18C8], rax
0x1800098f9  lea     r12d, [r13-7]
0x1800098fd  mov     [rbp+18E0h+var_18C0], r12
0x180009901  mov     [rbp+18E0h+var_18B8], r14d
0x180009905  lea     rax, aAttributename; "attributeName"
0x18000990c  mov     [rbp+18E0h+var_18B0], rax
0x180009910  mov     [rbp+18E0h+var_18A8], r13
0x180009914  mov     [rbp+18E0h+var_18A0], r14d
0x180009918  lea     rax, aAttributetype; "attributeType"
0x18000991f  mov     [rbp+18E0h+var_1898], rax
0x180009923  mov     [rbp+18E0h+var_1890], r13
0x180009927  mov     [rbp+18E0h+var_1888], r14d
0x18000992b  lea     rax, aAzimuth_0; "azimuth"
0x180009932  mov     [rbp+18E0h+var_1880], rax
0x180009936  lea     r8d, [r13-6]
0x18000993a  mov     [rbp+18E0h+var_1878], r8
0x18000993e  mov     [rbp+18E0h+var_1870], r14d
0x180009942  lea     rax, aBasefrequency; "baseFrequency"
0x180009949  mov     [rbp+18E0h+var_1868], rax
0x18000994d  mov     [rbp+18E0h+var_1860], r13
0x180009954  mov     [rbp+18E0h+var_1858], r14d
0x18000995b  lea     rax, aBaseprofile; "baseProfile"
0x180009962  mov     [rbp+18E0h+var_1850], rax
0x180009969  mov     [rbp+18E0h+var_1848], r15
0x180009970  mov     [rbp+18E0h+var_1840], r14d
0x180009977  lea     rax, aBaselineShift; "baseline-shift"
0x18000997e  mov     [rbp+18E0h+var_1838], rax
0x180009985  lea     r10d, [r13+1]
0x180009989  mov     [rbp+18E0h+var_1830], r10
0x180009990  mov     [rbp+18E0h+var_1828], r14d
0x180009997  lea     rax, aBbox; "bbox"
0x18000999e  mov     [rbp+18E0h+var_1820], rax
0x1800099a5  lea     r9d, [r13-9]
0x1800099a9  mov     [rbp+18E0h+var_1818], r9
0x1800099b0  mov     [rbp+18E0h+var_1810], r14d
0x1800099b7  lea     rax, aBegin; "begin"
0x1800099be  mov     [rbp+18E0h+var_1808], rax
0x1800099c5  mov     [rbp+18E0h+var_1800], 5
0x1800099d0  mov     [rbp+18E0h+var_17F8], r14d
0x1800099d7  lea     rax, aBias; "bias"
0x1800099de  mov     [rbp+18E0h+var_17F0], rax
0x1800099e5  mov     [rbp+18E0h+var_17E8], r9
0x1800099ec  mov     [rbp+18E0h+var_17E0], r14d
0x1800099f3  lea     rax, aBy; "by"
0x1800099fa  mov     [rbp+18E0h+var_17D8], rax
0x180009a01  lea     esi, [rdx-8]
0x180009a04  mov     [rbp+18E0h+var_17D0], rsi
0x180009a0b  mov     [rbp+18E0h+var_17C8], r14d
0x180009a12  lea     rax, aCalcmode; "calcMode"
0x180009a19  mov     [rbp+18E0h+var_17C0], rax
0x180009a20  mov     [rbp+18E0h+var_17B8], rcx
0x180009a27  mov     [rbp+18E0h+var_17B0], r14d
0x180009a2e  lea     rax, aCapHeight; "cap-height"
0x180009a35  mov     [rbp+18E0h+var_17A8], rax
0x180009a3c  mov     [rbp+18E0h+var_17A0], rdx
0x180009a43  mov     [rbp+18E0h+var_1798], r14d
0x180009a4a  lea     rax, aClass; "class"
0x180009a51  mov     [rbp+18E0h+var_1790], rax
0x180009a58  lea     ecx, [rdx-5]
0x180009a5b  mov     [rbp+18E0h+var_1788], rcx
0x180009a62  mov     [rbp+18E0h+var_1780], r14d
0x180009a69  lea     rax, aClip; "clip"
0x180009a70  mov     [rbp+18E0h+var_1778], rax
0x180009a77  mov     [rbp+18E0h+var_1770], r9
0x180009a7e  mov     [rbp+18E0h+var_1768], r14d
0x180009a85  lea     rax, aClipPath; "clip-path"
0x180009a8c  mov     [rbp+18E0h+var_1760], rax
0x180009a93  mov     [rbp+18E0h+var_1758], rbx
0x180009a9a  mov     [rbp+18E0h+var_1750], r14d
0x180009aa1  lea     rax, aClipRule; "clip-rule"
0x180009aa8  mov     [rbp+18E0h+var_1748], rax
0x180009aaf  mov     [rbp+18E0h+var_1740], rbx
0x180009ab6  mov     [rbp+18E0h+var_1738], r14d
0x180009abd  lea     rax, aClippathunits; "clipPathUnits"
0x180009ac4  mov     [rbp+18E0h+var_1730], rax
0x180009acb  mov     [rbp+18E0h+var_1728], r13
0x180009ad2  mov     [rbp+18E0h+var_1720], r14d
0x180009ad9  lea     rax, aColor; "color"
0x180009ae0  mov     [rbp+18E0h+var_1718], rax
0x180009ae7  mov     [rbp+18E0h+var_1710], rcx
0x180009aee  mov     [rbp+18E0h+var_1708], r14d
0x180009af5  lea     rax, aColorInterpola_0; "color-interpolation"
0x180009afc  mov     [rbp+18E0h+var_1700], rax
0x180009b03  lea     r9d, [r13+6]
0x180009b07  mov     [rbp+18E0h+var_16F8], r9
0x180009b0e  mov     [rbp+18E0h+var_16F0], r14d
0x180009b15  lea     rax, aColorInterpola; "color-interpolation-filters"
0x180009b1c  mov     [rbp+18E0h+var_16E8], rax
0x180009b23  mov     [rbp+18E0h+var_16E0], 1Bh
0x180009b2e  mov     [rbp+18E0h+var_16D8], r14d
0x180009b35  lea     rax, aColorProfile; "color-profile"
0x180009b3c  mov     [rbp+18E0h+var_16D0], rax
0x180009b43  mov     [rbp+18E0h+var_16C8], r13
0x180009b4a  mov     [rbp+18E0h+var_16C0], r14d
0x180009b51  lea     rax, aColorRendering; "color-rendering"
0x180009b58  mov     [rbp+18E0h+var_16B8], rax
0x180009b5f  lea     edx, [rbx+6]
0x180009b62  mov     [rbp+18E0h+var_16B0], rdx
0x180009b69  mov     [rbp+18E0h+var_16A8], r14d
0x180009b70  lea     rax, aContentscriptt; "contentScriptType"
0x180009b77  mov     [rbp+18E0h+var_16A0], rax
0x180009b7e  lea     ecx, [rbx+8]
0x180009b81  mov     [rbp+18E0h+var_1698], rcx
0x180009b88  mov     [rbp+18E0h+var_1690], r14d
0x180009b8f  lea     rax, aContentstylety; "contentStyleType"
0x180009b96  mov     [rbp+18E0h+var_1688], rax
0x180009b9d  lea     r14d, [r13+3]
0x180009ba1  mov     [rbp+18E0h+var_1680], r14
0x180009ba8  mov     [rbp+18E0h+var_1678], 0
0x180009bb2  lea     rax, aCursor_0; "cursor"
0x180009bb9  mov     [rbp+18E0h+var_1670], rax
0x180009bc0  mov     [rbp+18E0h+var_1668], r12
0x180009bc7  mov     [rbp+18E0h+var_1660], 0
0x180009bd1  lea     rax, aCx_0; "cx"
0x180009bd8  mov     [rbp+18E0h+var_1658], rax
0x180009bdf  mov     [rbp+18E0h+var_1650], rsi
0x180009be6  mov     [rbp+18E0h+var_1648], 0
0x180009bf0  lea     rax, aCy_0; "cy"
0x180009bf7  mov     [rbp+18E0h+var_1640], rax
0x180009bfe  mov     [rbp+18E0h+var_1638], rsi
0x180009c05  mov     [rbp+18E0h+var_1630], 0
0x180009c0f  lea     rax, aD; "d"
0x180009c16  mov     [rbp+18E0h+var_1628], rax
0x180009c1d  lea     esi, [rbx-8]
0x180009c20  mov     [rbp+18E0h+var_1620], rsi
0x180009c27  mov     [rbp+18E0h+var_1618], 0
0x180009c31  lea     rax, aDescent; "descent"
0x180009c38  mov     [rbp+18E0h+var_1610], rax
0x180009c3f  mov     [rbp+18E0h+var_1608], r8
0x180009c46  mov     [rbp+18E0h+var_1600], 0
0x180009c50  lea     rax, aDiffuseconstan_0; "diffuseConstant"
0x180009c57  mov     [rbp+18E0h+var_15F8], rax
0x180009c5e  mov     [rbp+18E0h+var_15F0], rdx
0x180009c65  mov     [rbp+18E0h+var_15E8], 0
0x180009c6f  lea     rax, aDirection; "direction"
0x180009c76  mov     [rbp+18E0h+var_15E0], rax
  ... truncated ...
```
