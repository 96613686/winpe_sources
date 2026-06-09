# TlmLogApiReliability

- ea: `0x180011e18`
- end: `0x180017722`
- name: `TlmLogApiReliability`
- size: `22794`
- prototype: ``
- caller_count: `27`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180002630`
- `0x180002d20`
- `0x1800031d0`
- `0x180003be0`
- `0x180004720`
- `0x180004ac0`
- `0x180005710`
- `0x180005f20`
- `0x180006060`
- `0x1800073b0`
- `0x1800079c0`
- `0x180007cf0`
- `0x18000d560`
- `0x18000d7b0`
- `0x18000daa0`
- `0x18000dc80`
- `0x18000dd60`
- `0x18000deb0`
- `0x18000e020`
- `0x18000e150`
- `0x18000e2c0`
- `0x18000e460`
- `0x18000e610`
- `0x18000eb80`
- `0x18000f520`
- `0x18000f610`
- `0x180018404`

## callees

- `0x180001008`
- `0x180001044`
- `0x180001070`
- `0x180001110`
- `0x180001a80`
- `0x1800022ee`
- `0x180004420`
- `0x180004a68`
- `0x18000f6fc`
- `0x18000f7c4`
- `0x180011e18`
- `0x180018b98`
- `0x180018e24`
- `0x180018f48`
- `0x180018f70`
- `0x180019384`
- `0x18001a54c`
- `0x18001a640`
- `0x18001b864`
- `0x18001bdf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012a6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d94`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180011ec9`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180011ec9`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001206d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001206d`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180012ac4`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180012ac4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012aa2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012aa2`

## pseudocode

```c
__int64 __fastcall TlmLogApiReliability(
        unsigned __int16 a1,
        unsigned __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        const WCHAR *a5,
        __int64 a6,
        int *a7,
        int a8)
{
  const WCHAR *v9; // r12
  __int64 v10; // r13
  __int64 v11; // rsi
  __int64 result; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  void *v20; // r15
  int SyncRootInfoByHandle; // eax
  char IsInitialized; // al
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 *v25; // r8
  unsigned __int64 v26; // r14
  signed int v27; // eax
  int v28; // r9d
  char *v29; // rdx
  char *v30; // rax
  int v31; // edx
  __int64 v32; // rax
  int v33; // edx
  __int64 v34; // rax
  DWORD CurrentProcessId; // eax
  __int64 v36; // r8
  DWORD v37; // r14d
  HANDLE v38; // rax
  int v39; // edx
  __int64 v40; // rax
  DWORD LastError; // eax
  char *v42; // rax
  __int16 *v43; // rdx
  int v44; // edx
  __int64 v45; // rax
  char *v46; // rax
  __int16 *v47; // rdx
  int v48; // edx
  __int64 v49; // rax
  DWORD v50; // eax
  int v51; // edx
  __int64 v52; // rax
  int v53; // edx
  __int64 v54; // rax
  int v55; // edx
  __int64 v56; // rax
  int v57; // edx
  __int64 v58; // rax
  int v59; // edx
  __int64 v60; // rax
  int v61; // edx
  __int64 v62; // rax
  int v63; // edx
  __int64 v64; // rax
  int v65; // edx
  __int64 v66; // rax
  int v67; // edx
  __int64 v68; // rax
  int v69; // edx
  __int64 v70; // rax
  int v71; // edx
  __int64 v72; // rax
  int v73; // edx
  __int64 v74; // rax
  int v75; // edx
  __int64 v76; // rax
  int v77; // r8d
  __int64 v78; // rax
  int v79; // edx
  __int64 v80; // rax
  int v81; // edx
  __int64 v82; // rax
  int v83; // edx
  __int64 v84; // rax
  int v85; // edx
  __int64 v86; // rax
  int v87; // edx
  __int64 v88; // rax
  int v89; // edx
  __int64 v90; // rax
  int v91; // edx
  __int64 v92; // rax
  int v93; // edx
  __int64 v94; // rax
  int v95; // edx
  __int64 v96; // rax
  int v97; // edx
  __int64 v98; // rax
  int v99; // edx
  __int64 v100; // rax
  int v101; // edx
  __int64 v102; // rax
  int v103; // edx
  __int64 v104; // rax
  int v105; // edx
  __int64 v106; // rax
  int v107; // edx
  __int64 v108; // rax
  int v109; // edx
  __int64 v110; // rax
  int v111; // edx
  __int64 v112; // rax
  int v113; // edx
  __int64 v114; // rax
  int v115; // edx
  int v116; // edx
  int v117; // edx
  int v118; // edx
  int v119; // edx
  int v120; // edx
  int v121; // edx
  int v122; // edx
  int v123; // edx
  int v124; // edx
  int v125; // edx
  int v126; // edx
  __int64 v127; // rax
  int v128; // edx
  __int64 v129; // rax
  int v130; // edx
  __int64 v131; // rax
  int v132; // edx
  int v133; // edx
  _QWORD *v134; // rax
  __int64 v135; // rcx
  __int64 v136; // rcx
  __int64 v137; // rcx
  int v138; // edx
  int v139; // edx
  int v140; // edx
  int v141; // edx
  int v142; // edx
  int v143; // edx
  char v144; // [rsp+40h] [rbp-C0h]
  char v145; // [rsp+41h] [rbp-BFh] BYREF
  char v146; // [rsp+42h] [rbp-BEh] BYREF
  char v147; // [rsp+43h] [rbp-BDh] BYREF
  char v148; // [rsp+44h] [rbp-BCh] BYREF
  char v149; // [rsp+45h] [rbp-BBh] BYREF
  char v150; // [rsp+46h] [rbp-BAh] BYREF
  char v151; // [rsp+47h] [rbp-B9h] BYREF
  char v152; // [rsp+48h] [rbp-B8h] BYREF
  char v153; // [rsp+49h] [rbp-B7h] BYREF
  char v154; // [rsp+4Ah] [rbp-B6h] BYREF
  char v155; // [rsp+4Bh] [rbp-B5h] BYREF
  char v156; // [rsp+4Ch] [rbp-B4h] BYREF
  char v157; // [rsp+4Dh] [rbp-B3h] BYREF
  char v158; // [rsp+4Eh] [rbp-B2h] BYREF
  char v159; // [rsp+4Fh] [rbp-B1h] BYREF
  char v160; // [rsp+50h] [rbp-B0h] BYREF
  char v161; // [rsp+51h] [rbp-AFh] BYREF
  char v162; // [rsp+52h] [rbp-AEh] BYREF
  char v163; // [rsp+53h] [rbp-ADh] BYREF
  char v164; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v165; // [rsp+58h] [rbp-A8h]
  unsigned int v166; // [rsp+5Ch] [rbp-A4h]
  int v167; // [rsp+60h] [rbp-A0h]
  __int64 v168; // [rsp+68h] [rbp-98h]
  unsigned __int64 UnbiasedTime; // [rsp+70h] [rbp-90h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp-88h] BYREF
  int v171; // [rsp+80h] [rbp-80h] BYREF
  int v172; // [rsp+84h] [rbp-7Ch] BYREF
  int v173; // [rsp+88h] [rbp-78h] BYREF
  int v174; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD v175; // [rsp+90h] [rbp-70h] BYREF
  DWORD v176; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v177; // [rsp+98h] [rbp-68h] BYREF
  int v178; // [rsp+9Ch] [rbp-64h] BYREF
  int v179; // [rsp+A0h] [rbp-60h] BYREF
  int v180; // [rsp+A4h] [rbp-5Ch] BYREF
  int v181; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v182; // [rsp+ACh] [rbp-54h] BYREF
  int v183; // [rsp+B0h] [rbp-50h] BYREF
  int v184; // [rsp+B4h] [rbp-4Ch] BYREF
  int v185; // [rsp+B8h] [rbp-48h] BYREF
  int v186; // [rsp+BCh] [rbp-44h] BYREF
  DWORD v187; // [rsp+C0h] [rbp-40h] BYREF
  int v188; // [rsp+C4h] [rbp-3Ch] BYREF
  int v189; // [rsp+C8h] [rbp-38h] BYREF
  int v190; // [rsp+CCh] [rbp-34h] BYREF
  int v191; // [rsp+D0h] [rbp-30h] BYREF
  DWORD v192; // [rsp+D4h] [rbp-2Ch] BYREF
  int v193; // [rsp+D8h] [rbp-28h] BYREF
  int v194; // [rsp+DCh] [rbp-24h] BYREF
  int v195; // [rsp+E0h] [rbp-20h] BYREF
  int v196; // [rsp+E4h] [rbp-1Ch] BYREF
  int v197; // [rsp+E8h] [rbp-18h] BYREF
  DWORD v198; // [rsp+ECh] [rbp-14h] BYREF
  int v199; // [rsp+F0h] [rbp-10h] BYREF
  DWORD v200; // [rsp+F4h] [rbp-Ch] BYREF
  int v201; // [rsp+F8h] [rbp-8h] BYREF
  int v202; // [rsp+FCh] [rbp-4h] BYREF
  int v203; // [rsp+100h] [rbp+0h] BYREF
  int v204; // [rsp+104h] [rbp+4h] BYREF
  DWORD v205; // [rsp+108h] [rbp+8h] BYREF
  int v206; // [rsp+10Ch] [rbp+Ch] BYREF
  int v207; // [rsp+110h] [rbp+10h] BYREF
  DWORD v208; // [rsp+114h] [rbp+14h] BYREF
  int v209; // [rsp+118h] [rbp+18h] BYREF
  int v210; // [rsp+11Ch] [rbp+1Ch] BYREF
  int v211; // [rsp+120h] [rbp+20h] BYREF
  int v212; // [rsp+124h] [rbp+24h] BYREF
  DWORD v213; // [rsp+128h] [rbp+28h] BYREF
  DWORD v214; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v215; // [rsp+130h] [rbp+30h] BYREF
  DWORD v216; // [rsp+134h] [rbp+34h] BYREF
  int v217; // [rsp+138h] [rbp+38h] BYREF
  int v218; // [rsp+13Ch] [rbp+3Ch] BYREF
  DWORD v219; // [rsp+140h] [rbp+40h] BYREF
  int v220; // [rsp+144h] [rbp+44h] BYREF
  int v221; // [rsp+148h] [rbp+48h] BYREF
  int v222; // [rsp+14Ch] [rbp+4Ch] BYREF
  DWORD v223; // [rsp+150h] [rbp+50h] BYREF
  int v224; // [rsp+154h] [rbp+54h] BYREF
  int v225; // [rsp+158h] [rbp+58h] BYREF
  int v226; // [rsp+15Ch] [rbp+5Ch] BYREF
  int v227; // [rsp+160h] [rbp+60h] BYREF
  int v228; // [rsp+164h] [rbp+64h] BYREF
  DWORD v229; // [rsp+168h] [rbp+68h] BYREF
  int v230; // [rsp+16Ch] [rbp+6Ch] BYREF
  int v231; // [rsp+170h] [rbp+70h] BYREF
  int v232; // [rsp+174h] [rbp+74h] BYREF
  int v233; // [rsp+178h] [rbp+78h] BYREF
  DWORD v234; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v235; // [rsp+180h] [rbp+80h] BYREF
  int v236; // [rsp+184h] [rbp+84h] BYREF
  int v237; // [rsp+188h] [rbp+88h] BYREF
  DWORD v238; // [rsp+18Ch] [rbp+8Ch] BYREF
  int v239; // [rsp+190h] [rbp+90h] BYREF
  int v240; // [rsp+194h] [rbp+94h] BYREF
  int v241; // [rsp+198h] [rbp+98h] BYREF
  DWORD v242; // [rsp+19Ch] [rbp+9Ch] BYREF
  int v243; // [rsp+1A0h] [rbp+A0h] BYREF
  DWORD v244; // [rsp+1A4h] [rbp+A4h] BYREF
  DWORD v245; // [rsp+1A8h] [rbp+A8h] BYREF
  DWORD v246; // [rsp+1ACh] [rbp+ACh] BYREF
  DWORD v247; // [rsp+1B0h] [rbp+B0h] BYREF
  DWORD v248; // [rsp+1B4h] [rbp+B4h] BYREF
  int v249; // [rsp+1B8h] [rbp+B8h] BYREF
  int v250; // [rsp+1BCh] [rbp+BCh] BYREF
  DWORD v251; // [rsp+1C0h] [rbp+C0h] BYREF
  int v252; // [rsp+1C4h] [rbp+C4h] BYREF
  int v253; // [rsp+1C8h] [rbp+C8h] BYREF
  DWORD v254; // [rsp+1CCh] [rbp+CCh] BYREF
  int v255; // [rsp+1D0h] [rbp+D0h] BYREF
  int v256; // [rsp+1D4h] [rbp+D4h] BYREF
  DWORD v257; // [rsp+1D8h] [rbp+D8h] BYREF
  int v258; // [rsp+1DCh] [rbp+DCh] BYREF
  DWORD v259; // [rsp+1E0h] [rbp+E0h] BYREF
  int v260; // [rsp+1E4h] [rbp+E4h] BYREF
  DWORD v261; // [rsp+1E8h] [rbp+E8h] BYREF
  int v262; // [rsp+1ECh] [rbp+ECh] BYREF
  int v263; // [rsp+1F0h] [rbp+F0h] BYREF
  int v264; // [rsp+1F4h] [rbp+F4h] BYREF
  DWORD v265; // [rsp+1F8h] [rbp+F8h] BYREF
  int v266; // [rsp+1FCh] [rbp+FCh] BYREF
  int v267; // [rsp+200h] [rbp+100h] BYREF
  int v268; // [rsp+204h] [rbp+104h] BYREF
  DWORD v269; // [rsp+208h] [rbp+108h] BYREF
  int v270; // [rsp+20Ch] [rbp+10Ch] BYREF
  int v271; // [rsp+210h] [rbp+110h] BYREF
  int v272; // [rsp+214h] [rbp+114h] BYREF
  int v273; // [rsp+218h] [rbp+118h] BYREF
  int v274; // [rsp+21Ch] [rbp+11Ch] BYREF
  DWORD v275; // [rsp+220h] [rbp+120h] BYREF
  int v276; // [rsp+224h] [rbp+124h] BYREF
  int v277; // [rsp+228h] [rbp+128h] BYREF
  int v278; // [rsp+22Ch] [rbp+12Ch] BYREF
  int v279; // [rsp+230h] [rbp+130h] BYREF
  int v280; // [rsp+234h] [rbp+134h] BYREF
  int v281; // [rsp+238h] [rbp+138h] BYREF
  DWORD v282; // [rsp+23Ch] [rbp+13Ch] BYREF
  int v283; // [rsp+240h] [rbp+140h] BYREF
  int v284; // [rsp+244h] [rbp+144h] BYREF
  DWORD v285; // [rsp+248h] [rbp+148h] BYREF
  int v286; // [rsp+24Ch] [rbp+14Ch] BYREF
  DWORD v287; // [rsp+250h] [rbp+150h] BYREF
  int v288; // [rsp+254h] [rbp+154h] BYREF
  DWORD v289; // [rsp+258h] [rbp+158h] BYREF
  int v290; // [rsp+25Ch] [rbp+15Ch] BYREF
  DWORD v291; // [rsp+260h] [rbp+160h] BYREF
  int v292; // [rsp+264h] [rbp+164h] BYREF
  DWORD v293; // [rsp+268h] [rbp+168h] BYREF
  int v294; // [rsp+26Ch] [rbp+16Ch] BYREF
  DWORD v295; // [rsp+270h] [rbp+170h] BYREF
  int v296; // [rsp+274h] [rbp+174h] BYREF
  DWORD v297; // [rsp+278h] [rbp+178h] BYREF
  DWORD v298; // [rsp+27Ch] [rbp+17Ch] BYREF
  int v299; // [rsp+280h] [rbp+180h] BYREF
  DWORD v300; // [rsp+284h] [rbp+184h] BYREF
  DWORD v301; // [rsp+288h] [rbp+188h] BYREF
  int v302; // [rsp+28Ch] [rbp+18Ch] BYREF
  DWORD v303; // [rsp+290h] [rbp+190h] BYREF
  int v304; // [rsp+294h] [rbp+194h] BYREF
  int v305; // [rsp+298h] [rbp+198h] BYREF
  int v306; // [rsp+29Ch] [rbp+19Ch] BYREF
  int v307; // [rsp+2A0h] [rbp+1A0h] BYREF
  DWORD v308; // [rsp+2A4h] [rbp+1A4h] BYREF
  int v309; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v310; // [rsp+2ACh] [rbp+1ACh] BYREF
  int v311; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v312; // [rsp+2B4h] [rbp+1B4h] BYREF
  DWORD v313; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v314; // [rsp+2BCh] [rbp+1BCh] BYREF
  DWORD v315; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v316; // [rsp+2C4h] [rbp+1C4h] BYREF
  DWORD v317; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v318; // [rsp+2CCh] [rbp+1CCh] BYREF
  DWORD v319; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v320; // [rsp+2D4h] [rbp+1D4h] BYREF
  int v321; // [rsp+2D8h] [rbp+1D8h] BYREF
  int v322; // [rsp+2DCh] [rbp+1DCh] BYREF
  int v323; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int64 v324; // [rsp+2E8h] [rbp+1E8h]
  __int64 v325; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v326; // [rsp+2F8h] [rbp+1F8h] BYREF
  unsigned __int64 v327; // [rsp+300h] [rbp+200h] BYREF
  union _LARGE_INTEGER v328; // [rsp+308h] [rbp+208h] BYREF
  __int64 v329; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int64 v330; // [rsp+318h] [rbp+218h] BYREF
  __int64 v331; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int64 v332; // [rsp+328h] [rbp+228h] BYREF
  __int64 v333; // [rsp+330h] [rbp+230h] BYREF
  __int64 v334; // [rsp+338h] [rbp+238h] BYREF
  __int64 v335; // [rsp+340h] [rbp+240h] BYREF
  __int64 v336; // [rsp+348h] [rbp+248h] BYREF
  __int64 v337; // [rsp+350h] [rbp+250h] BYREF
  __int64 v338; // [rsp+358h] [rbp+258h] BYREF
  __int64 v339; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int64 v340; // [rsp+368h] [rbp+268h] BYREF
  union _LARGE_INTEGER v341; // [rsp+370h] [rbp+270h] BYREF
  __int64 v342; // [rsp+378h] [rbp+278h] BYREF
  unsigned __int64 v343; // [rsp+380h] [rbp+280h] BYREF
  __int64 v344; // [rsp+388h] [rbp+288h] BYREF
  unsigned __int64 v345; // [rsp+390h] [rbp+290h] BYREF
  __int64 v346; // [rsp+398h] [rbp+298h] BYREF
  __int64 v347; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v348; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int64 v349; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v350; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int64 v351; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v352; // [rsp+3C8h] [rbp+2C8h] BYREF
  unsigned __int64 v353; // [rsp+3D0h] [rbp+2D0h] BYREF
  union _LARGE_INTEGER v354; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v355; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int64 v356; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v357; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v358; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v359; // [rsp+400h] [rbp+300h] BYREF
  __int64 v360; // [rsp+408h] [rbp+308h] BYREF
  __int64 v361; // [rsp+410h] [rbp+310h] BYREF
  __int64 v362; // [rsp+418h] [rbp+318h] BYREF
  __int64 v363; // [rsp+420h] [rbp+320h] BYREF
  __int64 v364; // [rsp+428h] [rbp+328h] BYREF
  __int64 v365; // [rsp+430h] [rbp+330h] BYREF
  __int64 v366; // [rsp+438h] [rbp+338h] BYREF
  __int64 v367; // [rsp+440h] [rbp+340h] BYREF
  __int64 v368; // [rsp+448h] [rbp+348h] BYREF
  __int64 v369; // [rsp+450h] [rbp+350h] BYREF
  __int64 v370; // [rsp+458h] [rbp+358h] BYREF
  __int64 v371; // [rsp+460h] [rbp+360h] BYREF
  __int64 v372; // [rsp+468h] [rbp+368h] BYREF
  __int64 v373; // [rsp+470h] [rbp+370h] BYREF
  __int64 v374; // [rsp+478h] [rbp+378h] BYREF
  __int64 v375; // [rsp+480h] [rbp+380h] BYREF
  __int64 v376; // [rsp+488h] [rbp+388h] BYREF
  __int64 v377; // [rsp+490h] [rbp+390h] BYREF
  __int64 v378; // [rsp+498h] [rbp+398h] BYREF
  __int64 v379; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v380; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int64 v381; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v382; // [rsp+4B8h] [rbp+3B8h] BYREF
  __int64 v383; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v384; // [rsp+4C8h] [rbp+3C8h] BYREF
  __int64 v385; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v386; // [rsp+4D8h] [rbp+3D8h] BYREF
  __int64 v387; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v388; // [rsp+4E8h] [rbp+3E8h] BYREF
  __int64 v389; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v390; // [rsp+4F8h] [rbp+3F8h] BYREF
  __int64 v391; // [rsp+500h] [rbp+400h] BYREF
  __int64 v392; // [rsp+508h] [rbp+408h] BYREF
  __int64 v393; // [rsp+510h] [rbp+410h] BYREF
  __int64 v394; // [rsp+518h] [rbp+418h] BYREF
  __int64 v395; // [rsp+520h] [rbp+420h] BYREF
  __int64 v396; // [rsp+528h] [rbp+428h] BYREF
  __int64 v397; // [rsp+530h] [rbp+430h] BYREF
  __int64 v398; // [rsp+538h] [rbp+438h] BYREF
  __int64 v399; // [rsp+540h] [rbp+440h] BYREF
  __int64 v400; // [rsp+548h] [rbp+448h] BYREF
  __int64 v401; // [rsp+550h] [rbp+450h] BYREF
  __int64 v402; // [rsp+558h] [rbp+458h] BYREF
  __int64 v403; // [rsp+560h] [rbp+460h] BYREF
  __int64 v404; // [rsp+568h] [rbp+468h] BYREF
  __int64 v405; // [rsp+570h] [rbp+470h] BYREF
  __int64 v406; // [rsp+578h] [rbp+478h] BYREF
  __int64 v407; // [rsp+580h] [rbp+480h] BYREF
  __int64 v408; // [rsp+588h] [rbp+488h] BYREF
  __int64 v409; // [rsp+590h] [rbp+490h] BYREF
  __int64 v410; // [rsp+598h] [rbp+498h] BYREF
  __int64 v411; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v412; // [rsp+5A8h] [rbp+4A8h] BYREF
  __int64 v413; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v414; // [rsp+5B8h] [rbp+4B8h] BYREF
  __int64 v415; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int64 v416; // [rsp+5C8h] [rbp+4C8h] BYREF
  __int64 v417; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v418; // [rsp+5D8h] [rbp+4D8h] BYREF
  __int64 v419; // [rsp+5E0h] [rbp+4E0h] BYREF
  _QWORD *v420; // [rsp+5E8h] [rbp+4E8h] BYREF
  __int64 v421; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v422; // [rsp+5F8h] [rbp+4F8h] BYREF
  __int64 v423; // [rsp+600h] [rbp+500h] BYREF
  __int64 v424; // [rsp+608h] [rbp+508h] BYREF
  __int64 v425; // [rsp+610h] [rbp+510h] BYREF
  __int64 v426; // [rsp+618h] [rbp+518h] BYREF
  __int64 v427; // [rsp+620h] [rbp+520h] BYREF
  __int64 v428; // [rsp+628h] [rbp+528h] BYREF
  __int64 v429; // [rsp+630h] [rbp+530h] BYREF
  __int64 v430; // [rsp+638h] [rbp+538h] BYREF
  __int64 v431; // [rsp+640h] [rbp+540h] BYREF
  __int64 v432; // [rsp+648h] [rbp+548h] BYREF
  __int64 v433; // [rsp+650h] [rbp+550h] BYREF
  __int64 v434; // [rsp+658h] [rbp+558h] BYREF
  __int64 v435; // [rsp+660h] [rbp+560h] BYREF
  __int64 v436; // [rsp+668h] [rbp+568h] BYREF
  __int64 v437; // [rsp+670h] [rbp+570h] BYREF
  __int64 v438; // [rsp+678h] [rbp+578h] BYREF
  __int64 v439; // [rsp+680h] [rbp+580h] BYREF
  __int64 v440; // [rsp+688h] [rbp+588h] BYREF
  __int64 v441; // [rsp+690h] [rbp+590h] BYREF
  __int64 v442; // [rsp+698h] [rbp+598h] BYREF
  __int64 v443; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int64 v444; // [rsp+6A8h] [rbp+5A8h] BYREF
  __int64 v445; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v446; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v447; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int64 v448; // [rsp+6C8h] [rbp+5C8h] BYREF
  __int64 v449; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v450; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v451; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int64 v452; // [rsp+6E8h] [rbp+5E8h] BYREF
  __int64 v453; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v454; // [rsp+6F8h] [rbp+5F8h] BYREF
  __int64 v455; // [rsp+700h] [rbp+600h] BYREF
  __int64 v456; // [rsp+708h] [rbp+608h] BYREF
  __int64 v457; // [rsp+710h] [rbp+610h] BYREF
  __int64 v458; // [rsp+718h] [rbp+618h] BYREF
  __int64 v459; // [rsp+720h] [rbp+620h] BYREF
  __int64 v460; // [rsp+728h] [rbp+628h] BYREF
  __int64 v461; // [rsp+730h] [rbp+630h] BYREF
  __int64 v462; // [rsp+738h] [rbp+638h] BYREF
  __int64 v463; // [rsp+740h] [rbp+640h] BYREF
  __int64 v464; // [rsp+748h] [rbp+648h] BYREF
  __int64 v465; // [rsp+750h] [rbp+650h] BYREF
  __int64 v466; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v467[4]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v468[512]; // [rsp+764h] [rbp+664h] BYREF
  _BYTE v469[524]; // [rsp+964h] [rbp+864h] BYREF
  char v470; // [rsp+B70h] [rbp+A70h] BYREF
  __int64 *v471; // [rsp+B90h] [rbp+A90h]
  __int64 v472; // [rsp+B98h] [rbp+A98h]
  __int64 *v473; // [rsp+BA0h] [rbp+AA0h]
  __int64 v474; // [rsp+BA8h] [rbp+AA8h]
  unsigned __int64 *v475; // [rsp+BB0h] [rbp+AB0h]
  __int64 v476; // [rsp+BB8h] [rbp+AB8h]
  union _LARGE_INTEGER *v477; // [rsp+BC0h] [rbp+AC0h]
  __int64 v478; // [rsp+BC8h] [rbp+AC8h]
  __int64 *v479; // [rsp+BD0h] [rbp+AD0h]
  __int64 v480; // [rsp+BD8h] [rbp+AD8h]
  unsigned __int64 *v481; // [rsp+BE0h] [rbp+AE0h]
  __int64 v482; // [rsp+BE8h] [rbp+AE8h]
  __int64 *v483; // [rsp+BF0h] [rbp+AF0h]
  __int64 v484; // [rsp+BF8h] [rbp+AF8h]
  unsigned __int64 *v485; // [rsp+C00h] [rbp+B00h]
  __int64 v486; // [rsp+C08h] [rbp+B08h]
  _DWORD *v487; // [rsp+C10h] [rbp+B10h]
  __int64 v488; // [rsp+C18h] [rbp+B18h]
  __int64 v489; // [rsp+C20h] [rbp+B20h]
  _DWORD v490[2]; // [rsp+C28h] [rbp+B28h] BYREF
  char v491[16]; // [rsp+C30h] [rbp+B30h] BYREF
  char v492[16]; // [rsp+C40h] [rbp+B40h] BYREF
  __int64 *v493; // [rsp+C50h] [rbp+B50h]
  __int64 v494; // [rsp+C58h] [rbp+B58h]
  int *v495; // [rsp+C60h] [rbp+B60h]
  __int64 v496; // [rsp+C68h] [rbp+B68h]
  char *v497; // [rsp+C70h] [rbp+B70h]
  __int64 v498; // [rsp+C78h] [rbp+B78h]
  int *v499; // [rsp+C80h] [rbp+B80h]
  __int64 v500; // [rsp+C88h] [rbp+B88h]
  __int64 *v501; // [rsp+C90h] [rbp+B90h]
  __int64 v502; // [rsp+C98h] [rbp+B98h]
  __int64 *v503; // [rsp+CA0h] [rbp+BA0h]
  __int64 v504; // [rsp+CA8h] [rbp+BA8h]
  __int64 *v505; // [rsp+CB0h] [rbp+BB0h]
  __int64 v506; // [rsp+CB8h] [rbp+BB8h]
  int *v507; // [rsp+CC0h] [rbp+BC0h]
  __int64 v508; // [rsp+CC8h] [rbp+BC8h]
  __int64 *v509; // [rsp+CD0h] [rbp+BD0h]
  __int64 v510; // [rsp+CD8h] [rbp+BD8h]
  char v511; // [rsp+CE0h] [rbp+BE0h] BYREF
  __int64 *v512; // [rsp+D00h] [rbp+C00h]
  __int64 v513; // [rsp+D08h] [rbp+C08h]
  __int64 *v514; // [rsp+D10h] [rbp+C10h]
  __int64 v515; // [rsp+D18h] [rbp+C18h]
  unsigned __int64 *v516; // [rsp+D20h] [rbp+C20h]
  __int64 v517; // [rsp+D28h] [rbp+C28h]
  union _LARGE_INTEGER *v518; // [rsp+D30h] [rbp+C30h]
  __int64 v519; // [rsp+D38h] [rbp+C38h]
  __int64 *v520; // [rsp+D40h] [rbp+C40h]
  __int64 v521; // [rsp+D48h] [rbp+C48h]
  unsigned __int64 *v522; // [rsp+D50h] [rbp+C50h]
  __int64 v523; // [rsp+D58h] [rbp+C58h]
  __int64 *v524; // [rsp+D60h] [rbp+C60h]
  __int64 v525; // [rsp+D68h] [rbp+C68h]
  unsigned __int64 *v526; // [rsp+D70h] [rbp+C70h]
  __int64 v527; // [rsp+D78h] [rbp+C78h]
  _DWORD *v528; // [rsp+D80h] [rbp+C80h]
  __int64 v529; // [rsp+D88h] [rbp+C88h]
  wchar_t *v530; // [rsp+D90h] [rbp+C90h]
  _DWORD v531[2]; // [rsp+D98h] [rbp+C98h] BYREF
  char v532[16]; // [rsp+DA0h] [rbp+CA0h] BYREF
  char v533[16]; // [rsp+DB0h] [rbp+CB0h] BYREF
  __int64 *v534; // [rsp+DC0h] [rbp+CC0h]
  __int64 v535; // [rsp+DC8h] [rbp+CC8h]
  char *v536; // [rsp+DD0h] [rbp+CD0h]
  __int64 v537; // [rsp+DD8h] [rbp+CD8h]
  int *v538; // [rsp+DE0h] [rbp+CE0h]
  __int64 v539; // [rsp+DE8h] [rbp+CE8h]
  __int64 *v540; // [rsp+DF0h] [rbp+CF0h]
  __int64 v541; // [rsp+DF8h] [rbp+CF8h]
  __int64 *v542; // [rsp+E00h] [rbp+D00h]
  __int64 v543; // [rsp+E08h] [rbp+D08h]
  __int64 *v544; // [rsp+E10h] [rbp+D10h]
  __int64 v545; // [rsp+E18h] [rbp+D18h]
  int *v546; // [rsp+E20h] [rbp+D20h]
  __int64 v547; // [rsp+E28h] [rbp+D28h]
  __int64 *v548; // [rsp+E30h] [rbp+D30h]
  __int64 v549; // [rsp+E38h] [rbp+D38h]
  char v550[32]; // [rsp+E40h] [rbp+D40h] BYREF
  __int64 *v551; // [rsp+E60h] [rbp+D60h]
  __int64 v552; // [rsp+E68h] [rbp+D68h]
  __int64 *v553; // [rsp+E70h] [rbp+D70h]
  __int64 v554; // [rsp+E78h] [rbp+D78h]
  unsigned __int64 *v555; // [rsp+E80h] [rbp+D80h]
  __int64 v556; // [rsp+E88h] [rbp+D88h]
  union _LARGE_INTEGER *v557; // [rsp+E90h] [rbp+D90h]
  __int64 v558; // [rsp+E98h] [rbp+D98h]
  __int64 *v559; // [rsp+EA0h] [rbp+DA0h]
  __int64 v560; // [rsp+EA8h] [rbp+DA8h]
  unsigned __int64 *v561; // [rsp+EB0h] [rbp+DB0h]
  __int64 v562; // [rsp+EB8h] [rbp+DB8h]
  _DWORD *v563; // [rsp+EC0h] [rbp+DC0h]
  __int64 v564; // [rsp+EC8h] [rbp+DC8h]
  __int64 v565; // [rsp+ED0h] [rbp+DD0h]
  _DWORD v566[2]; // [rsp+ED8h] [rbp+DD8h] BYREF
  char v567[16]; // [rsp+EE0h] [rbp+DE0h] BYREF
  char v568[16]; // [rsp+EF0h] [rbp+DF0h] BYREF
  __int64 *v569; // [rsp+F00h] [rbp+E00h]
  __int64 v570; // [rsp+F08h] [rbp+E08h]
  char *v571; // [rsp+F10h] [rbp+E10h]
  __int64 v572; // [rsp+F18h] [rbp+E18h]
  int *v573; // [rsp+F20h] [rbp+E20h]
  __int64 v574; // [rsp+F28h] [rbp+E28h]
  __int64 *v575; // [rsp+F30h] [rbp+E30h]
  __int64 v576; // [rsp+F38h] [rbp+E38h]
  __int64 *v577; // [rsp+F40h] [rbp+E40h]
  __int64 v578; // [rsp+F48h] [rbp+E48h]
  __int64 *v579; // [rsp+F50h] [rbp+E50h]
  __int64 v580; // [rsp+F58h] [rbp+E58h]
  int *v581; // [rsp+F60h] [rbp+E60h]
  __int64 v582; // [rsp+F68h] [rbp+E68h]
  __int64 *v583; // [rsp+F70h] [rbp+E70h]
  __int64 v584; // [rsp+F78h] [rbp+E78h]
  char v585[32]; // [rsp+F80h] [rbp+E80h] BYREF
  _DWORD *v586; // [rsp+FA0h] [rbp+EA0h]
  __int64 v587; // [rsp+FA8h] [rbp+EA8h]
  __int64 v588; // [rsp+FB0h] [rbp+EB0h]
  _DWORD v589[2]; // [rsp+FB8h] [rbp+EB8h] BYREF
  __int64 *v590; // [rsp+FC0h] [rbp+EC0h]
  __int64 v591; // [rsp+FC8h] [rbp+EC8h]
  __int64 *v592; // [rsp+FD0h] [rbp+ED0h]
  __int64 v593; // [rsp+FD8h] [rbp+ED8h]
  __int64 *v594; // [rsp+FE0h] [rbp+EE0h]
  __int64 v595; // [rsp+FE8h] [rbp+EE8h]
  __int64 *v596; // [rsp+FF0h] [rbp+EF0h]
  __int64 v597; // [rsp+FF8h] [rbp+EF8h]
  __int64 *v598; // [rsp+1000h] [rbp+F00h]
  __int64 v599; // [rsp+1008h] [rbp+F08h]
  char v600[32]; // [rsp+1010h] [rbp+F10h] BYREF
  _DWORD *v601; // [rsp+1030h] [rbp+F30h]
  __int64 v602; // [rsp+1038h] [rbp+F38h]
  __int64 v603; // [rsp+1040h] [rbp+F40h]
  _DWORD v604[2]; // [rsp+1048h] [rbp+F48h] BYREF
  int *v605; // [rsp+1050h] [rbp+F50h]
  __int64 v606; // [rsp+1058h] [rbp+F58h]
  int *v607; // [rsp+1060h] [rbp+F60h]
  __int64 v608; // [rsp+1068h] [rbp+F68h]
  __int64 *v609; // [rsp+1070h] [rbp+F70h]
  __int64 v610; // [rsp+1078h] [rbp+F78h]
  __int64 *v611; // [rsp+1080h] [rbp+F80h]
  __int64 v612; // [rsp+1088h] [rbp+F88h]
  char v613[32]; // [rsp+1090h] [rbp+F90h] BYREF
  __int64 *v614; // [rsp+10B0h] [rbp+FB0h]
  __int64 v615; // [rsp+10B8h] [rbp+FB8h]
  __int64 *v616; // [rsp+10C0h] [rbp+FC0h]
  __int64 v617; // [rsp+10C8h] [rbp+FC8h]
  __int64 *v618; // [rsp+10D0h] [rbp+FD0h]
  __int64 v619; // [rsp+10D8h] [rbp+FD8h]
  __int64 *v620; // [rsp+10E0h] [rbp+FE0h]
  __int64 v621; // [rsp+10E8h] [rbp+FE8h]
  int *v622; // [rsp+10F0h] [rbp+FF0h]
  __int64 v623; // [rsp+10F8h] [rbp+FF8h]
  __int64 *v624; // [rsp+1100h] [rbp+1000h]
  __int64 v625; // [rsp+1108h] [rbp+1008h]
  __int64 *v626; // [rsp+1110h] [rbp+1010h]
  __int64 v627; // [rsp+1118h] [rbp+1018h]
  char v628[32]; // [rsp+1120h] [rbp+1020h] BYREF
  __int64 *v629; // [rsp+1140h] [rbp+1040h]
  __int64 v630; // [rsp+1148h] [rbp+1048h]
  __int64 *v631; // [rsp+1150h] [rbp+1050h]
  __int64 v632; // [rsp+1158h] [rbp+1058h]
  __int64 *v633; // [rsp+1160h] [rbp+1060h]
  __int64 v634; // [rsp+1168h] [rbp+1068h]
  __int64 *v635; // [rsp+1170h] [rbp+1070h]
  __int64 v636; // [rsp+1178h] [rbp+1078h]
  int *v637; // [rsp+1180h] [rbp+1080h]
  __int64 v638; // [rsp+1188h] [rbp+1088h]
  __int64 *v639; // [rsp+1190h] [rbp+1090h]
  __int64 v640; // [rsp+1198h] [rbp+1098h]
  __int64 *v641; // [rsp+11A0h] [rbp+10A0h]
  __int64 v642; // [rsp+11A8h] [rbp+10A8h]
  char v643; // [rsp+11B0h] [rbp+10B0h] BYREF
  _DWORD *v644; // [rsp+11D0h] [rbp+10D0h]
  __int64 v645; // [rsp+11D8h] [rbp+10D8h]
  __int64 v646; // [rsp+11E0h] [rbp+10E0h]
  _DWORD v647[2]; // [rsp+11E8h] [rbp+10E8h] BYREF
  int *v648; // [rsp+11F0h] [rbp+10F0h]
  __int64 v649; // [rsp+11F8h] [rbp+10F8h]
  int *v650; // [rsp+1200h] [rbp+1100h]
  __int64 v651; // [rsp+1208h] [rbp+1108h]
  __int64 *v652; // [rsp+1210h] [rbp+1110h]
  __int64 v653; // [rsp+1218h] [rbp+1118h]
  char *v654; // [rsp+1220h] [rbp+1120h]
  __int64 v655; // [rsp+1228h] [rbp+1128h]
  int *v656; // [rsp+1230h] [rbp+1130h]
  __int64 v657; // [rsp+1238h] [rbp+1138h]
  DWORD *v658; // [rsp+1240h] [rbp+1140h]
  __int64 v659; // [rsp+1248h] [rbp+1148h]
  char v660[16]; // [rsp+1250h] [rbp+1150h] BYREF
  int *v661; // [rsp+1260h] [rbp+1160h]
  __int64 v662; // [rsp+1268h] [rbp+1168h]
  char v663[16]; // [rsp+1270h] [rbp+1170h] BYREF
  char v664; // [rsp+1280h] [rbp+1180h] BYREF
  _DWORD *v665; // [rsp+12A0h] [rbp+11A0h]
  __int64 v666; // [rsp+12A8h] [rbp+11A8h]
  __int64 v667; // [rsp+12B0h] [rbp+11B0h]
  _DWORD v668[2]; // [rsp+12B8h] [rbp+11B8h] BYREF
  int *v669; // [rsp+12C0h] [rbp+11C0h]
  __int64 v670; // [rsp+12C8h] [rbp+11C8h]
  int *v671; // [rsp+12D0h] [rbp+11D0h]
  __int64 v672; // [rsp+12D8h] [rbp+11D8h]
  __int64 *v673; // [rsp+12E0h] [rbp+11E0h]
  __int64 v674; // [rsp+12E8h] [rbp+11E8h]
  char *v675; // [rsp+12F0h] [rbp+11F0h]
  __int64 v676; // [rsp+12F8h] [rbp+11F8h]
  int *v677; // [rsp+1300h] [rbp+1200h]
  __int64 v678; // [rsp+1308h] [rbp+1208h]
  DWORD *v679; // [rsp+1310h] [rbp+1210h]
  __int64 v680; // [rsp+1318h] [rbp+1218h]
  char v681[16]; // [rsp+1320h] [rbp+1220h] BYREF
  int *v682; // [rsp+1330h] [rbp+1230h]
  __int64 v683; // [rsp+1338h] [rbp+1238h]
  char v684[16]; // [rsp+1340h] [rbp+1240h] BYREF
  char v685; // [rsp+1350h] [rbp+1250h] BYREF
  _DWORD *v686; // [rsp+1370h] [rbp+1270h]
  __int64 v687; // [rsp+1378h] [rbp+1278h]
  __int64 v688; // [rsp+1380h] [rbp+1280h]
  _DWORD v689[2]; // [rsp+1388h] [rbp+1288h] BYREF
  DWORD *v690; // [rsp+1390h] [rbp+1290h]
  __int64 v691; // [rsp+1398h] [rbp+1298h]
  char v692[16]; // [rsp+13A0h] [rbp+12A0h] BYREF
  __int64 *v693; // [rsp+13B0h] [rbp+12B0h]
  __int64 v694; // [rsp+13B8h] [rbp+12B8h]
  __int64 *v695; // [rsp+13C0h] [rbp+12C0h]
  __int64 v696; // [rsp+13C8h] [rbp+12C8h]
  __int64 *v697; // [rsp+13D0h] [rbp+12D0h]
  __int64 v698; // [rsp+13D8h] [rbp+12D8h]
  __int64 *v699; // [rsp+13E0h] [rbp+12E0h]
  __int64 v700; // [rsp+13E8h] [rbp+12E8h]
  __int64 *v701; // [rsp+13F0h] [rbp+12F0h]
  __int64 v702; // [rsp+13F8h] [rbp+12F8h]
  int *v703; // [rsp+1400h] [rbp+1300h]
  __int64 v704; // [rsp+1408h] [rbp+1308h]
  char v705[16]; // [rsp+1410h] [rbp+1310h] BYREF
  char v706[32]; // [rsp+1420h] [rbp+1320h] BYREF
  _DWORD *v707; // [rsp+1440h] [rbp+1340h]
  __int64 v708; // [rsp+1448h] [rbp+1348h]
  __int64 v709; // [rsp+1450h] [rbp+1350h]
  _DWORD v710[2]; // [rsp+1458h] [rbp+1358h] BYREF
  DWORD *v711; // [rsp+1460h] [rbp+1360h]
  __int64 v712; // [rsp+1468h] [rbp+1368h]
  char v713[16]; // [rsp+1470h] [rbp+1370h] BYREF
  __int64 *v714; // [rsp+1480h] [rbp+1380h]
  __int64 v715; // [rsp+1488h] [rbp+1388h]
  __int64 *v716; // [rsp+1490h] [rbp+1390h]
  __int64 v717; // [rsp+1498h] [rbp+1398h]
  __int64 *v718; // [rsp+14A0h] [rbp+13A0h]
  __int64 v719; // [rsp+14A8h] [rbp+13A8h]
  __int64 *v720; // [rsp+14B0h] [rbp+13B0h]
  __int64 v721; // [rsp+14B8h] [rbp+13B8h]
  int *v722; // [rsp+14C0h] [rbp+13C0h]
  __int64 v723; // [rsp+14C8h] [rbp+13C8h]
  char v724[16]; // [rsp+14D0h] [rbp+13D0h] BYREF
  char v725[32]; // [rsp+14E0h] [rbp+13E0h] BYREF
  _DWORD *v726; // [rsp+1500h] [rbp+1400h]
  __int64 v727; // [rsp+1508h] [rbp+1408h]
  __int64 v728; // [rsp+1510h] [rbp+1410h]
  _DWORD v729[2]; // [rsp+1518h] [rbp+1418h] BYREF
  DWORD *v730; // [rsp+1520h] [rbp+1420h]
  __int64 v731; // [rsp+1528h] [rbp+1428h]
  char v732[16]; // [rsp+1530h] [rbp+1430h] BYREF
  int *v733; // [rsp+1540h] [rbp+1440h]
  __int64 v734; // [rsp+1548h] [rbp+1448h]
  int *v735; // [rsp+1550h] [rbp+1450h]
  __int64 v736; // [rsp+1558h] [rbp+1458h]
  __int64 *v737; // [rsp+1560h] [rbp+1460h]
  __int64 v738; // [rsp+1568h] [rbp+1468h]
  __int64 *v739; // [rsp+1570h] [rbp+1470h]
  __int64 v740; // [rsp+1578h] [rbp+1478h]
  int *v741; // [rsp+1580h] [rbp+1480h]
  __int64 v742; // [rsp+1588h] [rbp+1488h]
  char v743[16]; // [rsp+1590h] [rbp+1490h] BYREF
  char v744[32]; // [rsp+15A0h] [rbp+14A0h] BYREF
  _DWORD *v745; // [rsp+15C0h] [rbp+14C0h]
  __int64 v746; // [rsp+15C8h] [rbp+14C8h]
  __int64 v747; // [rsp+15D0h] [rbp+14D0h]
  _DWORD v748[2]; // [rsp+15D8h] [rbp+14D8h] BYREF
  char v749[16]; // [rsp+15E0h] [rbp+14E0h] BYREF
  char v750[16]; // [rsp+15F0h] [rbp+14F0h] BYREF
  int *v751; // [rsp+1600h] [rbp+1500h]
  __int64 v752; // [rsp+1608h] [rbp+1508h]
  char *v753; // [rsp+1610h] [rbp+1510h]
  __int64 v754; // [rsp+1618h] [rbp+1518h]
  char *v755; // [rsp+1620h] [rbp+1520h]
  __int64 v756; // [rsp+1628h] [rbp+1528h]
  char *v757; // [rsp+1630h] [rbp+1530h]
  __int64 v758; // [rsp+1638h] [rbp+1538h]
  __int64 *v759; // [rsp+1640h] [rbp+1540h]
  __int64 v760; // [rsp+1648h] [rbp+1548h]
  char v761[32]; // [rsp+1650h] [rbp+1550h] BYREF
  _DWORD *v762; // [rsp+1670h] [rbp+1570h]
  __int64 v763; // [rsp+1678h] [rbp+1578h]
  __int64 v764; // [rsp+1680h] [rbp+1580h]
  _DWORD v765[2]; // [rsp+1688h] [rbp+1588h] BYREF
  char v766[16]; // [rsp+1690h] [rbp+1590h] BYREF
  char v767[16]; // [rsp+16A0h] [rbp+15A0h] BYREF
  DWORD *v768; // [rsp+16B0h] [rbp+15B0h]
  __int64 v769; // [rsp+16B8h] [rbp+15B8h]
  char v770[16]; // [rsp+16C0h] [rbp+15C0h] BYREF
  int *v771; // [rsp+16D0h] [rbp+15D0h]
  __int64 v772; // [rsp+16D8h] [rbp+15D8h]
  char *v773; // [rsp+16E0h] [rbp+15E0h]
  __int64 v774; // [rsp+16E8h] [rbp+15E8h]
  char *v775; // [rsp+16F0h] [rbp+15F0h]
  __int64 v776; // [rsp+16F8h] [rbp+15F8h]
  char *v777; // [rsp+1700h] [rbp+1600h]
  __int64 v778; // [rsp+1708h] [rbp+1608h]
  __int64 *v779; // [rsp+1710h] [rbp+1610h]
  __int64 v780; // [rsp+1718h] [rbp+1618h]
  int *v781; // [rsp+1720h] [rbp+1620h]
  __int64 v782; // [rsp+1728h] [rbp+1628h]
  char v783[16]; // [rsp+1730h] [rbp+1630h] BYREF
  char v784[32]; // [rsp+1740h] [rbp+1640h] BYREF
  _DWORD *v785; // [rsp+1760h] [rbp+1660h]
  __int64 v786; // [rsp+1768h] [rbp+1668h]
  __int64 v787; // [rsp+1770h] [rbp+1670h]
  _DWORD v788[2]; // [rsp+1778h] [rbp+1678h] BYREF
  char v789[16]; // [rsp+1780h] [rbp+1680h] BYREF
  char v790[16]; // [rsp+1790h] [rbp+1690h] BYREF
  DWORD *v791; // [rsp+17A0h] [rbp+16A0h]
  __int64 v792; // [rsp+17A8h] [rbp+16A8h]
  char v793[16]; // [rsp+17B0h] [rbp+16B0h] BYREF
  int *v794; // [rsp+17C0h] [rbp+16C0h]
  __int64 v795; // [rsp+17C8h] [rbp+16C8h]
  char *v796; // [rsp+17D0h] [rbp+16D0h]
  __int64 v797; // [rsp+17D8h] [rbp+16D8h]
  char *v798; // [rsp+17E0h] [rbp+16E0h]
  __int64 v799; // [rsp+17E8h] [rbp+16E8h]
  char *v800; // [rsp+17F0h] [rbp+16F0h]
  __int64 v801; // [rsp+17F8h] [rbp+16F8h]
  __int64 *v802; // [rsp+1800h] [rbp+1700h]
  __int64 v803; // [rsp+1808h] [rbp+1708h]
  int *v804; // [rsp+1810h] [rbp+1710h]
  __int64 v805; // [rsp+1818h] [rbp+1718h]
  char v806[16]; // [rsp+1820h] [rbp+1720h] BYREF
  char v807[32]; // [rsp+1830h] [rbp+1730h] BYREF
  _DWORD *v808; // [rsp+1850h] [rbp+1750h]
  __int64 v809; // [rsp+1858h] [rbp+1758h]
  __int64 v810; // [rsp+1860h] [rbp+1760h]
  _DWORD v811[2]; // [rsp+1868h] [rbp+1768h] BYREF
  DWORD *v812; // [rsp+1870h] [rbp+1770h]
  __int64 v813; // [rsp+1878h] [rbp+1778h]
  char v814[16]; // [rsp+1880h] [rbp+1780h] BYREF
  int *v815; // [rsp+1890h] [rbp+1790h]
  __int64 v816; // [rsp+1898h] [rbp+1798h]
  int *v817; // [rsp+18A0h] [rbp+17A0h]
  __int64 v818; // [rsp+18A8h] [rbp+17A8h]
  int *v819; // [rsp+18B0h] [rbp+17B0h]
  __int64 v820; // [rsp+18B8h] [rbp+17B8h]
  char v821[16]; // [rsp+18C0h] [rbp+17C0h] BYREF
  char v822[32]; // [rsp+18D0h] [rbp+17D0h] BYREF
  _DWORD *v823; // [rsp+18F0h] [rbp+17F0h]
  __int64 v824; // [rsp+18F8h] [rbp+17F8h]
  __int64 v825; // [rsp+1900h] [rbp+1800h]
  _DWORD v826[2]; // [rsp+1908h] [rbp+1808h] BYREF
  char v827[16]; // [rsp+1910h] [rbp+1810h] BYREF
  char v828[16]; // [rsp+1920h] [rbp+1820h] BYREF
  __int64 *v829; // [rsp+1930h] [rbp+1830h]
  __int64 v830; // [rsp+1938h] [rbp+1838h]
  __int64 *v831; // [rsp+1940h] [rbp+1840h]
  __int64 v832; // [rsp+1948h] [rbp+1848h]
  int *v833; // [rsp+1950h] [rbp+1850h]
  __int64 v834; // [rsp+1958h] [rbp+1858h]
  int *v835; // [rsp+1960h] [rbp+1860h]
  __int64 v836; // [rsp+1968h] [rbp+1868h]
  char v837[32]; // [rsp+1970h] [rbp+1870h] BYREF
  _DWORD *v838; // [rsp+1990h] [rbp+1890h]
  __int64 v839; // [rsp+1998h] [rbp+1898h]
  __int64 v840; // [rsp+19A0h] [rbp+18A0h]
  _DWORD v841[2]; // [rsp+19A8h] [rbp+18A8h] BYREF
  char v842[16]; // [rsp+19B0h] [rbp+18B0h] BYREF
  char v843[16]; // [rsp+19C0h] [rbp+18C0h] BYREF
  __int64 *v844; // [rsp+19D0h] [rbp+18D0h]
  __int64 v845; // [rsp+19D8h] [rbp+18D8h]
  __int64 *v846; // [rsp+19E0h] [rbp+18E0h]
  __int64 v847; // [rsp+19E8h] [rbp+18E8h]
  int *v848; // [rsp+19F0h] [rbp+18F0h]
  __int64 v849; // [rsp+19F8h] [rbp+18F8h]
  int *v850; // [rsp+1A00h] [rbp+1900h]
  __int64 v851; // [rsp+1A08h] [rbp+1908h]
  char v852[32]; // [rsp+1A10h] [rbp+1910h] BYREF
  _DWORD *v853; // [rsp+1A30h] [rbp+1930h]
  __int64 v854; // [rsp+1A38h] [rbp+1938h]
  __int64 v855; // [rsp+1A40h] [rbp+1940h]
  _DWORD v856[2]; // [rsp+1A48h] [rbp+1948h] BYREF
  char v857[16]; // [rsp+1A50h] [rbp+1950h] BYREF
  char v858[16]; // [rsp+1A60h] [rbp+1960h] BYREF
  __int64 *v859; // [rsp+1A70h] [rbp+1970h]
  __int64 v860; // [rsp+1A78h] [rbp+1978h]
  __int64 *v861; // [rsp+1A80h] [rbp+1980h]
  __int64 v862; // [rsp+1A88h] [rbp+1988h]
  int *v863; // [rsp+1A90h] [rbp+1990h]
  __int64 v864; // [rsp+1A98h] [rbp+1998h]
  int *v865; // [rsp+1AA0h] [rbp+19A0h]
  __int64 v866; // [rsp+1AA8h] [rbp+19A8h]
  char v867[32]; // [rsp+1AB0h] [rbp+19B0h] BYREF
  _DWORD *v868; // [rsp+1AD0h] [rbp+19D0h]
  __int64 v869; // [rsp+1AD8h] [rbp+19D8h]
  __int64 v870; // [rsp+1AE0h] [rbp+19E0h]
  _DWORD v871[2]; // [rsp+1AE8h] [rbp+19E8h] BYREF
  char v872[16]; // [rsp+1AF0h] [rbp+19F0h] BYREF
  char v873[16]; // [rsp+1B00h] [rbp+1A00h] BYREF
  __int64 *v874; // [rsp+1B10h] [rbp+1A10h]
  __int64 v875; // [rsp+1B18h] [rbp+1A18h]
  __int64 *v876; // [rsp+1B20h] [rbp+1A20h]
  __int64 v877; // [rsp+1B28h] [rbp+1A28h]
  int *v878; // [rsp+1B30h] [rbp+1A30h]
  __int64 v879; // [rsp+1B38h] [rbp+1A38h]
  int *v880; // [rsp+1B40h] [rbp+1A40h]
  __int64 v881; // [rsp+1B48h] [rbp+1A48h]
  char v882[32]; // [rsp+1B50h] [rbp+1A50h] BYREF
  _DWORD *v883; // [rsp+1B70h] [rbp+1A70h]
  __int64 v884; // [rsp+1B78h] [rbp+1A78h]
  __int64 v885; // [rsp+1B80h] [rbp+1A80h]
  _DWORD v886[2]; // [rsp+1B88h] [rbp+1A88h] BYREF
  char v887[16]; // [rsp+1B90h] [rbp+1A90h] BYREF
  char v888[16]; // [rsp+1BA0h] [rbp+1AA0h] BYREF
  __int64 *v889; // [rsp+1BB0h] [rbp+1AB0h]
  __int64 v890; // [rsp+1BB8h] [rbp+1AB8h]
  __int64 *v891; // [rsp+1BC0h] [rbp+1AC0h]
  __int64 v892; // [rsp+1BC8h] [rbp+1AC8h]
  int *v893; // [rsp+1BD0h] [rbp+1AD0h]
  __int64 v894; // [rsp+1BD8h] [rbp+1AD8h]
  int *v895; // [rsp+1BE0h] [rbp+1AE0h]
  __int64 v896; // [rsp+1BE8h] [rbp+1AE8h]
  char v897[32]; // [rsp+1BF0h] [rbp+1AF0h] BYREF
  _DWORD *v898; // [rsp+1C10h] [rbp+1B10h]
  __int64 v899; // [rsp+1C18h] [rbp+1B18h]
  __int64 v900; // [rsp+1C20h] [rbp+1B20h]
  _DWORD v901[2]; // [rsp+1C28h] [rbp+1B28h] BYREF
  char v902[16]; // [rsp+1C30h] [rbp+1B30h] BYREF
  char v903[16]; // [rsp+1C40h] [rbp+1B40h] BYREF
  __int64 *v904; // [rsp+1C50h] [rbp+1B50h]
  __int64 v905; // [rsp+1C58h] [rbp+1B58h]
  int *v906; // [rsp+1C60h] [rbp+1B60h]
  __int64 v907; // [rsp+1C68h] [rbp+1B68h]
  int *v908; // [rsp+1C70h] [rbp+1B70h]
  __int64 v909; // [rsp+1C78h] [rbp+1B78h]
  char *v910; // [rsp+1C80h] [rbp+1B80h]
  __int64 v911; // [rsp+1C88h] [rbp+1B88h]
  char v912[32]; // [rsp+1C90h] [rbp+1B90h] BYREF
  _DWORD *v913; // [rsp+1CB0h] [rbp+1BB0h]
  __int64 v914; // [rsp+1CB8h] [rbp+1BB8h]
  __int64 v915; // [rsp+1CC0h] [rbp+1BC0h]
  _DWORD v916[2]; // [rsp+1CC8h] [rbp+1BC8h] BYREF
  DWORD *v917; // [rsp+1CD0h] [rbp+1BD0h]
  __int64 v918; // [rsp+1CD8h] [rbp+1BD8h]
  char v919[16]; // [rsp+1CE0h] [rbp+1BE0h] BYREF
  int *v920; // [rsp+1CF0h] [rbp+1BF0h]
  __int64 v921; // [rsp+1CF8h] [rbp+1BF8h]
  int *v922; // [rsp+1D00h] [rbp+1C00h]
  __int64 v923; // [rsp+1D08h] [rbp+1C08h]
  int *v924; // [rsp+1D10h] [rbp+1C10h]
  __int64 v925; // [rsp+1D18h] [rbp+1C18h]
  char v926[16]; // [rsp+1D20h] [rbp+1C20h] BYREF
  char v927[32]; // [rsp+1D30h] [rbp+1C30h] BYREF
  _DWORD *v928; // [rsp+1D50h] [rbp+1C50h]
  __int64 v929; // [rsp+1D58h] [rbp+1C58h]
  __int64 v930; // [rsp+1D60h] [rbp+1C60h]
  _DWORD v931[2]; // [rsp+1D68h] [rbp+1C68h] BYREF
  DWORD *v932; // [rsp+1D70h] [rbp+1C70h]
  __int64 v933; // [rsp+1D78h] [rbp+1C78h]
  char v934[16]; // [rsp+1D80h] [rbp+1C80h] BYREF
  int *v935; // [rsp+1D90h] [rbp+1C90h]
  __int64 v936; // [rsp+1D98h] [rbp+1C98h]
  int *v937; // [rsp+1DA0h] [rbp+1CA0h]
  __int64 v938; // [rsp+1DA8h] [rbp+1CA8h]
  int *v939; // [rsp+1DB0h] [rbp+1CB0h]
  __int64 v940; // [rsp+1DB8h] [rbp+1CB8h]
  char v941[16]; // [rsp+1DC0h] [rbp+1CC0h] BYREF
  char v942[32]; // [rsp+1DD0h] [rbp+1CD0h] BYREF
  _DWORD *v943; // [rsp+1DF0h] [rbp+1CF0h]
  __int64 v944; // [rsp+1DF8h] [rbp+1CF8h]
  __int64 v945; // [rsp+1E00h] [rbp+1D00h]
  _DWORD v946[2]; // [rsp+1E08h] [rbp+1D08h] BYREF
  DWORD *v947; // [rsp+1E10h] [rbp+1D10h]
  __int64 v948; // [rsp+1E18h] [rbp+1D18h]
  char v949[16]; // [rsp+1E20h] [rbp+1D20h] BYREF
  __int64 *v950; // [rsp+1E30h] [rbp+1D30h]
  __int64 v951; // [rsp+1E38h] [rbp+1D38h]
  __int64 *v952; // [rsp+1E40h] [rbp+1D40h]
  __int64 v953; // [rsp+1E48h] [rbp+1D48h]
  int *v954; // [rsp+1E50h] [rbp+1D50h]
  __int64 v955; // [rsp+1E58h] [rbp+1D58h]
  char v956[16]; // [rsp+1E60h] [rbp+1D60h] BYREF
  char v957[32]; // [rsp+1E70h] [rbp+1D70h] BYREF
  _DWORD *v958; // [rsp+1E90h] [rbp+1D90h]
  __int64 v959; // [rsp+1E98h] [rbp+1D98h]
  __int64 v960; // [rsp+1EA0h] [rbp+1DA0h]
  _DWORD v961[2]; // [rsp+1EA8h] [rbp+1DA8h] BYREF
  DWORD *v962; // [rsp+1EB0h] [rbp+1DB0h]
  __int64 v963; // [rsp+1EB8h] [rbp+1DB8h]
  char v964[16]; // [rsp+1EC0h] [rbp+1DC0h] BYREF
  __int64 *v965; // [rsp+1ED0h] [rbp+1DD0h]
  __int64 v966; // [rsp+1ED8h] [rbp+1DD8h]
  __int64 *v967; // [rsp+1EE0h] [rbp+1DE0h]
  __int64 v968; // [rsp+1EE8h] [rbp+1DE8h]
  int *v969; // [rsp+1EF0h] [rbp+1DF0h]
  __int64 v970; // [rsp+1EF8h] [rbp+1DF8h]
  char v971[16]; // [rsp+1F00h] [rbp+1E00h] BYREF
  char v972[32]; // [rsp+1F10h] [rbp+1E10h] BYREF
  __int64 *v973; // [rsp+1F30h] [rbp+1E30h]
  __int64 v974; // [rsp+1F38h] [rbp+1E38h]
  __int64 *v975; // [rsp+1F40h] [rbp+1E40h]
  __int64 v976; // [rsp+1F48h] [rbp+1E48h]
  __int64 *v977; // [rsp+1F50h] [rbp+1E50h]
  __int64 v978; // [rsp+1F58h] [rbp+1E58h]
  __int64 *v979; // [rsp+1F60h] [rbp+1E60h]
  __int64 v980; // [rsp+1F68h] [rbp+1E68h]
  char v981[32]; // [rsp+1F70h] [rbp+1E70h] BYREF
  _DWORD *v982; // [rsp+1F90h] [rbp+1E90h]
  __int64 v983; // [rsp+1F98h] [rbp+1E98h]
  __int64 v984; // [rsp+1FA0h] [rbp+1EA0h]
  _DWORD v985[2]; // [rsp+1FA8h] [rbp+1EA8h] BYREF
  char v986[16]; // [rsp+1FB0h] [rbp+1EB0h] BYREF
  char v987[16]; // [rsp+1FC0h] [rbp+1EC0h] BYREF
  DWORD *v988; // [rsp+1FD0h] [rbp+1ED0h]
  __int64 v989; // [rsp+1FD8h] [rbp+1ED8h]
  char v990[16]; // [rsp+1FE0h] [rbp+1EE0h] BYREF
  __int64 *v991; // [rsp+1FF0h] [rbp+1EF0h]
  __int64 v992; // [rsp+1FF8h] [rbp+1EF8h]
  __int64 *v993; // [rsp+2000h] [rbp+1F00h]
  __int64 v994; // [rsp+2008h] [rbp+1F08h]
  int *v995; // [rsp+2010h] [rbp+1F10h]
  __int64 v996; // [rsp+2018h] [rbp+1F18h]
  int *v997; // [rsp+2020h] [rbp+1F20h]
  __int64 v998; // [rsp+2028h] [rbp+1F28h]
  char v999[32]; // [rsp+2030h] [rbp+1F30h] BYREF
  _DWORD *v1000; // [rsp+2050h] [rbp+1F50h]
  __int64 v1001; // [rsp+2058h] [rbp+1F58h]
  __int64 v1002; // [rsp+2060h] [rbp+1F60h]
  _DWORD v1003[2]; // [rsp+2068h] [rbp+1F68h] BYREF
  char v1004[16]; // [rsp+2070h] [rbp+1F70h] BYREF
  __int64 *v1005; // [rsp+2080h] [rbp+1F80h]
  __int64 v1006; // [rsp+2088h] [rbp+1F88h]
  char v1007[16]; // [rsp+2090h] [rbp+1F90h] BYREF
  char v1008[16]; // [rsp+20A0h] [rbp+1FA0h] BYREF
  __int64 *v1009; // [rsp+20B0h] [rbp+1FB0h]
  __int64 v1010; // [rsp+20B8h] [rbp+1FB8h]
  __int64 *v1011; // [rsp+20C0h] [rbp+1FC0h]
  __int64 v1012; // [rsp+20C8h] [rbp+1FC8h]
  __int64 *v1013; // [rsp+20D0h] [rbp+1FD0h]
  __int64 v1014; // [rsp+20D8h] [rbp+1FD8h]
  __int64 *v1015; // [rsp+20E0h] [rbp+1FE0h]
  __int64 v1016; // [rsp+20E8h] [rbp+1FE8h]
  DWORD *v1017; // [rsp+20F0h] [rbp+1FF0h]
  __int64 v1018; // [rsp+20F8h] [rbp+1FF8h]
  char v1019[16]; // [rsp+2100h] [rbp+2000h] BYREF
  char v1020[32]; // [rsp+2110h] [rbp+2010h] BYREF
  _DWORD *v1021; // [rsp+2130h] [rbp+2030h]
  __int64 v1022; // [rsp+2138h] [rbp+2038h]
  __int64 v1023; // [rsp+2140h] [rbp+2040h]
  _DWORD v1024[2]; // [rsp+2148h] [rbp+2048h] BYREF
  DWORD *v1025; // [rsp+2150h] [rbp+2050h]
  __int64 v1026; // [rsp+2158h] [rbp+2058h]
  char v1027[16]; // [rsp+2160h] [rbp+2060h] BYREF
  int *v1028; // [rsp+2170h] [rbp+2070h]
  __int64 v1029; // [rsp+2178h] [rbp+2078h]
  int *v1030; // [rsp+2180h] [rbp+2080h]
  __int64 v1031; // [rsp+2188h] [rbp+2088h]
  char v1032[16]; // [rsp+2190h] [rbp+2090h] BYREF
  char v1033[32]; // [rsp+21A0h] [rbp+20A0h] BYREF
  _DWORD *v1034; // [rsp+21C0h] [rbp+20C0h]
  __int64 v1035; // [rsp+21C8h] [rbp+20C8h]
  __int64 v1036; // [rsp+21D0h] [rbp+20D0h]
  _DWORD v1037[2]; // [rsp+21D8h] [rbp+20D8h] BYREF
  DWORD *v1038; // [rsp+21E0h] [rbp+20E0h]
  __int64 v1039; // [rsp+21E8h] [rbp+20E8h]
  char v1040[16]; // [rsp+21F0h] [rbp+20F0h] BYREF
  int *v1041; // [rsp+2200h] [rbp+2100h]
  __int64 v1042; // [rsp+2208h] [rbp+2108h]
  int *v1043; // [rsp+2210h] [rbp+2110h]
  __int64 v1044; // [rsp+2218h] [rbp+2118h]
  char v1045[16]; // [rsp+2220h] [rbp+2120h] BYREF
  char v1046[32]; // [rsp+2230h] [rbp+2130h] BYREF
  _DWORD *v1047; // [rsp+2250h] [rbp+2150h]
  __int64 v1048; // [rsp+2258h] [rbp+2158h]
  __int64 v1049; // [rsp+2260h] [rbp+2160h]
  _DWORD v1050[2]; // [rsp+2268h] [rbp+2168h] BYREF
  char v1051[16]; // [rsp+2270h] [rbp+2170h] BYREF
  char v1052[16]; // [rsp+2280h] [rbp+2180h] BYREF
  __int64 *v1053; // [rsp+2290h] [rbp+2190h]
  __int64 v1054; // [rsp+2298h] [rbp+2198h]
  int *v1055; // [rsp+22A0h] [rbp+21A0h]
  __int64 v1056; // [rsp+22A8h] [rbp+21A8h]
  int *v1057; // [rsp+22B0h] [rbp+21B0h]
  __int64 v1058; // [rsp+22B8h] [rbp+21B8h]
  char v1059; // [rsp+22C0h] [rbp+21C0h] BYREF
  _DWORD *v1060; // [rsp+22E0h] [rbp+21E0h]
  __int64 v1061; // [rsp+22E8h] [rbp+21E8h]
  __int64 v1062; // [rsp+22F0h] [rbp+21F0h]
  _DWORD v1063[2]; // [rsp+22F8h] [rbp+21F8h] BYREF
  char v1064[16]; // [rsp+2300h] [rbp+2200h] BYREF
  char v1065[16]; // [rsp+2310h] [rbp+2210h] BYREF
  DWORD *v1066; // [rsp+2320h] [rbp+2220h]
  __int64 v1067; // [rsp+2328h] [rbp+2228h]
  char v1068[16]; // [rsp+2330h] [rbp+2230h] BYREF
  __int64 *v1069; // [rsp+2340h] [rbp+2240h]
  __int64 v1070; // [rsp+2348h] [rbp+2248h]
  __int64 *v1071; // [rsp+2350h] [rbp+2250h]
  __int64 v1072; // [rsp+2358h] [rbp+2258h]
  int *v1073; // [rsp+2360h] [rbp+2260h]
  __int64 v1074; // [rsp+2368h] [rbp+2268h]
  int *v1075; // [rsp+2370h] [rbp+2270h]
  __int64 v1076; // [rsp+2378h] [rbp+2278h]
  char v1077[16]; // [rsp+2380h] [rbp+2280h] BYREF
  char v1078; // [rsp+2390h] [rbp+2290h] BYREF
  _DWORD *v1079; // [rsp+23B0h] [rbp+22B0h]
  __int64 v1080; // [rsp+23B8h] [rbp+22B8h]
  __int64 v1081; // [rsp+23C0h] [rbp+22C0h]
  _DWORD v1082[2]; // [rsp+23C8h] [rbp+22C8h] BYREF
  char v1083[16]; // [rsp+23D0h] [rbp+22D0h] BYREF
  char v1084[16]; // [rsp+23E0h] [rbp+22E0h] BYREF
  DWORD *v1085; // [rsp+23F0h] [rbp+22F0h]
  __int64 v1086; // [rsp+23F8h] [rbp+22F8h]
  char v1087[16]; // [rsp+2400h] [rbp+2300h] BYREF
  __int64 *v1088; // [rsp+2410h] [rbp+2310h]
  __int64 v1089; // [rsp+2418h] [rbp+2318h]
  __int64 *v1090; // [rsp+2420h] [rbp+2320h]
  __int64 v1091; // [rsp+2428h] [rbp+2328h]
  int *v1092; // [rsp+2430h] [rbp+2330h]
  __int64 v1093; // [rsp+2438h] [rbp+2338h]
  int *v1094; // [rsp+2440h] [rbp+2340h]
  __int64 v1095; // [rsp+2448h] [rbp+2348h]
  char v1096[16]; // [rsp+2450h] [rbp+2350h] BYREF
  char v1097; // [rsp+2460h] [rbp+2360h] BYREF
  _DWORD *v1098; // [rsp+2480h] [rbp+2380h]
  __int64 v1099; // [rsp+2488h] [rbp+2388h]
  __int64 v1100; // [rsp+2490h] [rbp+2390h]
  _DWORD v1101[2]; // [rsp+2498h] [rbp+2398h] BYREF
  char v1102[16]; // [rsp+24A0h] [rbp+23A0h] BYREF
  char v1103[16]; // [rsp+24B0h] [rbp+23B0h] BYREF
  DWORD *v1104; // [rsp+24C0h] [rbp+23C0h]
  __int64 v1105; // [rsp+24C8h] [rbp+23C8h]
  char v1106[16]; // [rsp+24D0h] [rbp+23D0h] BYREF
  __int64 *v1107; // [rsp+24E0h] [rbp+23E0h]
  __int64 v1108; // [rsp+24E8h] [rbp+23E8h]
  __int64 *v1109; // [rsp+24F0h] [rbp+23F0h]
  __int64 v1110; // [rsp+24F8h] [rbp+23F8h]
  __int64 *v1111; // [rsp+2500h] [rbp+2400h]
  __int64 v1112; // [rsp+2508h] [rbp+2408h]
  int *v1113; // [rsp+2510h] [rbp+2410h]
  __int64 v1114; // [rsp+2518h] [rbp+2418h]
  char v1115[16]; // [rsp+2520h] [rbp+2420h] BYREF
  char v1116; // [rsp+2530h] [rbp+2430h] BYREF
  _DWORD *v1117; // [rsp+2550h] [rbp+2450h]
  __int64 v1118; // [rsp+2558h] [rbp+2458h]
  __int64 v1119; // [rsp+2560h] [rbp+2460h]
  _DWORD v1120[2]; // [rsp+2568h] [rbp+2468h] BYREF
  char v1121[16]; // [rsp+2570h] [rbp+2470h] BYREF
  char v1122[16]; // [rsp+2580h] [rbp+2480h] BYREF
  DWORD *v1123; // [rsp+2590h] [rbp+2490h]
  __int64 v1124; // [rsp+2598h] [rbp+2498h]
  char v1125[16]; // [rsp+25A0h] [rbp+24A0h] BYREF
  __int64 *v1126; // [rsp+25B0h] [rbp+24B0h]
  __int64 v1127; // [rsp+25B8h] [rbp+24B8h]
  __int64 *v1128; // [rsp+25C0h] [rbp+24C0h]
  __int64 v1129; // [rsp+25C8h] [rbp+24C8h]
  int *v1130; // [rsp+25D0h] [rbp+24D0h]
  __int64 v1131; // [rsp+25D8h] [rbp+24D8h]
  int *v1132; // [rsp+25E0h] [rbp+24E0h]
  __int64 v1133; // [rsp+25E8h] [rbp+24E8h]
  char v1134[16]; // [rsp+25F0h] [rbp+24F0h] BYREF
  char v1135; // [rsp+2600h] [rbp+2500h] BYREF
  _DWORD *v1136; // [rsp+2620h] [rbp+2520h]
  __int64 v1137; // [rsp+2628h] [rbp+2528h]
  __int64 v1138; // [rsp+2630h] [rbp+2530h]
  _DWORD v1139[2]; // [rsp+2638h] [rbp+2538h] BYREF
  char v1140[16]; // [rsp+2640h] [rbp+2540h] BYREF
  char v1141[16]; // [rsp+2650h] [rbp+2550h] BYREF
  DWORD *v1142; // [rsp+2660h] [rbp+2560h]
  __int64 v1143; // [rsp+2668h] [rbp+2568h]
  char v1144[16]; // [rsp+2670h] [rbp+2570h] BYREF
  __int64 *v1145; // [rsp+2680h] [rbp+2580h]
  __int64 v1146; // [rsp+2688h] [rbp+2588h]
  __int64 *v1147; // [rsp+2690h] [rbp+2590h]
  __int64 v1148; // [rsp+2698h] [rbp+2598h]
  int *v1149; // [rsp+26A0h] [rbp+25A0h]
  __int64 v1150; // [rsp+26A8h] [rbp+25A8h]
  int *v1151; // [rsp+26B0h] [rbp+25B0h]
  __int64 v1152; // [rsp+26B8h] [rbp+25B8h]
  char v1153[16]; // [rsp+26C0h] [rbp+25C0h] BYREF
  char v1154; // [rsp+26D0h] [rbp+25D0h] BYREF
  _DWORD *v1155; // [rsp+26F0h] [rbp+25F0h]
  __int64 v1156; // [rsp+26F8h] [rbp+25F8h]
  __int64 v1157; // [rsp+2700h] [rbp+2600h]
  _DWORD v1158[2]; // [rsp+2708h] [rbp+2608h] BYREF
  char v1159[16]; // [rsp+2710h] [rbp+2610h] BYREF
  char v1160[16]; // [rsp+2720h] [rbp+2620h] BYREF
  DWORD *v1161; // [rsp+2730h] [rbp+2630h]
  __int64 v1162; // [rsp+2738h] [rbp+2638h]
  char v1163[16]; // [rsp+2740h] [rbp+2640h] BYREF
  __int64 *v1164; // [rsp+2750h] [rbp+2650h]
  __int64 v1165; // [rsp+2758h] [rbp+2658h]
  __int64 *v1166; // [rsp+2760h] [rbp+2660h]
  __int64 v1167; // [rsp+2768h] [rbp+2668h]
  int *v1168; // [rsp+2770h] [rbp+2670h]
  __int64 v1169; // [rsp+2778h] [rbp+2678h]
  int *v1170; // [rsp+2780h] [rbp+2680h]
  __int64 v1171; // [rsp+2788h] [rbp+2688h]
  char v1172[16]; // [rsp+2790h] [rbp+2690h] BYREF
  char v1173; // [rsp+27A0h] [rbp+26A0h] BYREF
  _DWORD *v1174; // [rsp+27C0h] [rbp+26C0h]
  __int64 v1175; // [rsp+27C8h] [rbp+26C8h]
  __int64 v1176; // [rsp+27D0h] [rbp+26D0h]
  _DWORD v1177[2]; // [rsp+27D8h] [rbp+26D8h] BYREF
  char v1178[16]; // [rsp+27E0h] [rbp+26E0h] BYREF
  char v1179[16]; // [rsp+27F0h] [rbp+26F0h] BYREF
  DWORD *v1180; // [rsp+2800h] [rbp+2700h]
  __int64 v1181; // [rsp+2808h] [rbp+2708h]
  char v1182[16]; // [rsp+2810h] [rbp+2710h] BYREF
  __int64 *v1183; // [rsp+2820h] [rbp+2720h]
  __int64 v1184; // [rsp+2828h] [rbp+2728h]
  int *v1185; // [rsp+2830h] [rbp+2730h]
  __int64 v1186; // [rsp+2838h] [rbp+2738h]
  int *v1187; // [rsp+2840h] [rbp+2740h]
  __int64 v1188; // [rsp+2848h] [rbp+2748h]
  int *v1189; // [rsp+2850h] [rbp+2750h]
  __int64 v1190; // [rsp+2858h] [rbp+2758h]
  char v1191[16]; // [rsp+2860h] [rbp+2760h] BYREF
  char v1192; // [rsp+2870h] [rbp+2770h] BYREF
  _DWORD *v1193; // [rsp+2890h] [rbp+2790h]
  __int64 v1194; // [rsp+2898h] [rbp+2798h]
  __int64 v1195; // [rsp+28A0h] [rbp+27A0h]
  _DWORD v1196[2]; // [rsp+28A8h] [rbp+27A8h] BYREF
  DWORD *v1197; // [rsp+28B0h] [rbp+27B0h]
  __int64 v1198; // [rsp+28B8h] [rbp+27B8h]
  char v1199[16]; // [rsp+28C0h] [rbp+27C0h] BYREF
  char v1200; // [rsp+28D0h] [rbp+27D0h] BYREF
  _DWORD *v1201; // [rsp+28F0h] [rbp+27F0h]
  __int64 v1202; // [rsp+28F8h] [rbp+27F8h]
  __int64 v1203; // [rsp+2900h] [rbp+2800h]
  _DWORD v1204[2]; // [rsp+2908h] [rbp+2808h] BYREF
  DWORD *v1205; // [rsp+2910h] [rbp+2810h]
  __int64 v1206; // [rsp+2918h] [rbp+2818h]
  char v1207[16]; // [rsp+2920h] [rbp+2820h] BYREF
  char v1208[32]; // [rsp+2930h] [rbp+2830h] BYREF
  _DWORD *v1209; // [rsp+2950h] [rbp+2850h]
  __int64 v1210; // [rsp+2958h] [rbp+2858h]
  __int64 v1211; // [rsp+2960h] [rbp+2860h]
  _DWORD v1212[2]; // [rsp+2968h] [rbp+2868h] BYREF
  char v1213[16]; // [rsp+2970h] [rbp+2870h] BYREF
  char v1214[16]; // [rsp+2980h] [rbp+2880h] BYREF
  DWORD *v1215; // [rsp+2990h] [rbp+2890h]
  __int64 v1216; // [rsp+2998h] [rbp+2898h]
  char v1217[16]; // [rsp+29A0h] [rbp+28A0h] BYREF
  int *v1218; // [rsp+29B0h] [rbp+28B0h]
  __int64 v1219; // [rsp+29B8h] [rbp+28B8h]
  int *v1220; // [rsp+29C0h] [rbp+28C0h]
  __int64 v1221; // [rsp+29C8h] [rbp+28C8h]
  int *v1222; // [rsp+29D0h] [rbp+28D0h]
  __int64 v1223; // [rsp+29D8h] [rbp+28D8h]
  char v1224[16]; // [rsp+29E0h] [rbp+28E0h] BYREF
  char v1225[32]; // [rsp+29F0h] [rbp+28F0h] BYREF
  _DWORD *v1226; // [rsp+2A10h] [rbp+2910h]
  __int64 v1227; // [rsp+2A18h] [rbp+2918h]
  __int64 v1228; // [rsp+2A20h] [rbp+2920h]
  _DWORD v1229[2]; // [rsp+2A28h] [rbp+2928h] BYREF
  char v1230[16]; // [rsp+2A30h] [rbp+2930h] BYREF
  char v1231[16]; // [rsp+2A40h] [rbp+2940h] BYREF
  DWORD *v1232; // [rsp+2A50h] [rbp+2950h]
  __int64 v1233; // [rsp+2A58h] [rbp+2958h]
  char v1234[16]; // [rsp+2A60h] [rbp+2960h] BYREF
  int *v1235; // [rsp+2A70h] [rbp+2970h]
  __int64 v1236; // [rsp+2A78h] [rbp+2978h]
  int *v1237; // [rsp+2A80h] [rbp+2980h]
  __int64 v1238; // [rsp+2A88h] [rbp+2988h]
  int *v1239; // [rsp+2A90h] [rbp+2990h]
  __int64 v1240; // [rsp+2A98h] [rbp+2998h]
  char v1241[16]; // [rsp+2AA0h] [rbp+29A0h] BYREF
  char v1242[32]; // [rsp+2AB0h] [rbp+29B0h] BYREF
  _DWORD *v1243; // [rsp+2AD0h] [rbp+29D0h]
  __int64 v1244; // [rsp+2AD8h] [rbp+29D8h]
  __int64 v1245; // [rsp+2AE0h] [rbp+29E0h]
  _DWORD v1246[2]; // [rsp+2AE8h] [rbp+29E8h] BYREF
  char v1247[16]; // [rsp+2AF0h] [rbp+29F0h] BYREF
  char v1248[16]; // [rsp+2B00h] [rbp+2A00h] BYREF
  __int64 *v1249; // [rsp+2B10h] [rbp+2A10h]
  __int64 v1250; // [rsp+2B18h] [rbp+2A18h]
  __int64 *v1251; // [rsp+2B20h] [rbp+2A20h]
  __int64 v1252; // [rsp+2B28h] [rbp+2A28h]
  int *v1253; // [rsp+2B30h] [rbp+2A30h]
  __int64 v1254; // [rsp+2B38h] [rbp+2A38h]
  DWORD *v1255; // [rsp+2B40h] [rbp+2A40h]
  __int64 v1256; // [rsp+2B48h] [rbp+2A48h]
  char v1257[16]; // [rsp+2B50h] [rbp+2A50h] BYREF
  char v1258[16]; // [rsp+2B60h] [rbp+2A60h] BYREF
  char v1259[32]; // [rsp+2B70h] [rbp+2A70h] BYREF
  _DWORD *v1260; // [rsp+2B90h] [rbp+2A90h]
  __int64 v1261; // [rsp+2B98h] [rbp+2A98h]
  __int64 v1262; // [rsp+2BA0h] [rbp+2AA0h]
  _DWORD v1263[2]; // [rsp+2BA8h] [rbp+2AA8h] BYREF
  char v1264[16]; // [rsp+2BB0h] [rbp+2AB0h] BYREF
  char v1265[16]; // [rsp+2BC0h] [rbp+2AC0h] BYREF
  DWORD *v1266; // [rsp+2BD0h] [rbp+2AD0h]
  __int64 v1267; // [rsp+2BD8h] [rbp+2AD8h]
  char v1268[16]; // [rsp+2BE0h] [rbp+2AE0h] BYREF
  int *v1269; // [rsp+2BF0h] [rbp+2AF0h]
  __int64 v1270; // [rsp+2BF8h] [rbp+2AF8h]
  int *v1271; // [rsp+2C00h] [rbp+2B00h]
  __int64 v1272; // [rsp+2C08h] [rbp+2B08h]
  char v1273[32]; // [rsp+2C10h] [rbp+2B10h] BYREF
  _DWORD *v1274; // [rsp+2C30h] [rbp+2B30h]
  __int64 v1275; // [rsp+2C38h] [rbp+2B38h]
  __int64 v1276; // [rsp+2C40h] [rbp+2B40h]
  _DWORD v1277[2]; // [rsp+2C48h] [rbp+2B48h] BYREF
  char v1278[16]; // [rsp+2C50h] [rbp+2B50h] BYREF
  char v1279[16]; // [rsp+2C60h] [rbp+2B60h] BYREF
  __int64 *v1280; // [rsp+2C70h] [rbp+2B70h]
  __int64 v1281; // [rsp+2C78h] [rbp+2B78h]
  __int64 *v1282; // [rsp+2C80h] [rbp+2B80h]
  __int64 v1283; // [rsp+2C88h] [rbp+2B88h]
  DWORD *v1284; // [rsp+2C90h] [rbp+2B90h]
  __int64 v1285; // [rsp+2C98h] [rbp+2B98h]
  char v1286[16]; // [rsp+2CA0h] [rbp+2BA0h] BYREF
  char v1287[32]; // [rsp+2CB0h] [rbp+2BB0h] BYREF
  _DWORD *v1288; // [rsp+2CD0h] [rbp+2BD0h]
  __int64 v1289; // [rsp+2CD8h] [rbp+2BD8h]
  __int64 v1290; // [rsp+2CE0h] [rbp+2BE0h]
  _DWORD v1291[2]; // [rsp+2CE8h] [rbp+2BE8h] BYREF
  DWORD *v1292; // [rsp+2CF0h] [rbp+2BF0h]
  __int64 v1293; // [rsp+2CF8h] [rbp+2BF8h]
  char v1294[16]; // [rsp+2D00h] [rbp+2C00h] BYREF
  int *v1295; // [rsp+2D10h] [rbp+2C10h]
  __int64 v1296; // [rsp+2D18h] [rbp+2C18h]
  char v1297[16]; // [rsp+2D20h] [rbp+2C20h] BYREF
  char v1298[32]; // [rsp+2D30h] [rbp+2C30h] BYREF
  _DWORD *v1299; // [rsp+2D50h] [rbp+2C50h]
  __int64 v1300; // [rsp+2D58h] [rbp+2C58h]
  __int64 v1301; // [rsp+2D60h] [rbp+2C60h]
  _DWORD v1302[2]; // [rsp+2D68h] [rbp+2C68h] BYREF
  DWORD *v1303; // [rsp+2D70h] [rbp+2C70h]
  __int64 v1304; // [rsp+2D78h] [rbp+2C78h]
  char v1305[16]; // [rsp+2D80h] [rbp+2C80h] BYREF
  int *v1306; // [rsp+2D90h] [rbp+2C90h]
  __int64 v1307; // [rsp+2D98h] [rbp+2C98h]
  char v1308[16]; // [rsp+2DA0h] [rbp+2CA0h] BYREF
  char v1309[32]; // [rsp+2DB0h] [rbp+2CB0h] BYREF
  _DWORD *v1310; // [rsp+2DD0h] [rbp+2CD0h]
  __int64 v1311; // [rsp+2DD8h] [rbp+2CD8h]
  __int64 v1312; // [rsp+2DE0h] [rbp+2CE0h]
  _DWORD v1313[2]; // [rsp+2DE8h] [rbp+2CE8h] BYREF
  DWORD *v1314; // [rsp+2DF0h] [rbp+2CF0h]
  __int64 v1315; // [rsp+2DF8h] [rbp+2CF8h]
  char v1316[16]; // [rsp+2E00h] [rbp+2D00h] BYREF
  int *v1317; // [rsp+2E10h] [rbp+2D10h]
  __int64 v1318; // [rsp+2E18h] [rbp+2D18h]
  char v1319[16]; // [rsp+2E20h] [rbp+2D20h] BYREF
  char v1320[32]; // [rsp+2E30h] [rbp+2D30h] BYREF
  _DWORD *v1321; // [rsp+2E50h] [rbp+2D50h]
  __int64 v1322; // [rsp+2E58h] [rbp+2D58h]
  __int64 v1323; // [rsp+2E60h] [rbp+2D60h]
  _DWORD v1324[2]; // [rsp+2E68h] [rbp+2D68h] BYREF
  char v1325[16]; // [rsp+2E70h] [rbp+2D70h] BYREF
  char v1326[16]; // [rsp+2E80h] [rbp+2D80h] BYREF
  __int64 *v1327; // [rsp+2E90h] [rbp+2D90h]
  __int64 v1328; // [rsp+2E98h] [rbp+2D98h]
  int *v1329; // [rsp+2EA0h] [rbp+2DA0h]
  __int64 v1330; // [rsp+2EA8h] [rbp+2DA8h]
  char v1331; // [rsp+2EB0h] [rbp+2DB0h] BYREF
  _DWORD *v1332; // [rsp+2ED0h] [rbp+2DD0h]
  __int64 v1333; // [rsp+2ED8h] [rbp+2DD8h]
  __int64 v1334; // [rsp+2EE0h] [rbp+2DE0h]
  _DWORD v1335[2]; // [rsp+2EE8h] [rbp+2DE8h] BYREF
  char v1336[16]; // [rsp+2EF0h] [rbp+2DF0h] BYREF
  char v1337[16]; // [rsp+2F00h] [rbp+2E00h] BYREF
  char v1338[16]; // [rsp+2F10h] [rbp+2E10h] BYREF
  DWORD *v1339; // [rsp+2F20h] [rbp+2E20h]
  __int64 v1340; // [rsp+2F28h] [rbp+2E28h]
  char v1341[16]; // [rsp+2F30h] [rbp+2E30h] BYREF
  __int64 *v1342; // [rsp+2F40h] [rbp+2E40h]
  __int64 v1343; // [rsp+2F48h] [rbp+2E48h]
  char *v1344; // [rsp+2F50h] [rbp+2E50h]
  __int64 v1345; // [rsp+2F58h] [rbp+2E58h]
  int *v1346; // [rsp+2F60h] [rbp+2E60h]
  __int64 v1347; // [rsp+2F68h] [rbp+2E68h]
  char v1348[16]; // [rsp+2F70h] [rbp+2E70h] BYREF
  char v1349; // [rsp+2F80h] [rbp+2E80h] BYREF
  _DWORD *v1350; // [rsp+2FA0h] [rbp+2EA0h]
  __int64 v1351; // [rsp+2FA8h] [rbp+2EA8h]
  __int64 v1352; // [rsp+2FB0h] [rbp+2EB0h]
  _DWORD v1353[2]; // [rsp+2FB8h] [rbp+2EB8h] BYREF
  char v1354[16]; // [rsp+2FC0h] [rbp+2EC0h] BYREF
  char v1355[16]; // [rsp+2FD0h] [rbp+2ED0h] BYREF
  DWORD *v1356; // [rsp+2FE0h] [rbp+2EE0h]
  __int64 v1357; // [rsp+2FE8h] [rbp+2EE8h]
  char v1358[16]; // [rsp+2FF0h] [rbp+2EF0h] BYREF
  int *v1359; // [rsp+3000h] [rbp+2F00h]
  __int64 v1360; // [rsp+3008h] [rbp+2F08h]
  int *v1361; // [rsp+3010h] [rbp+2F10h]
  __int64 v1362; // [rsp+3018h] [rbp+2F18h]
  char v1363[16]; // [rsp+3020h] [rbp+2F20h] BYREF
  int *v1364; // [rsp+3030h] [rbp+2F30h]
  __int64 v1365; // [rsp+3038h] [rbp+2F38h]
  char v1366[16]; // [rsp+3040h] [rbp+2F40h] BYREF
  char v1367[32]; // [rsp+3050h] [rbp+2F50h] BYREF
  _DWORD *v1368; // [rsp+3070h] [rbp+2F70h]
  __int64 v1369; // [rsp+3078h] [rbp+2F78h]
  __int64 v1370; // [rsp+3080h] [rbp+2F80h]
  _DWORD v1371[2]; // [rsp+3088h] [rbp+2F88h] BYREF
  char v1372[16]; // [rsp+3090h] [rbp+2F90h] BYREF
  char v1373[16]; // [rsp+30A0h] [rbp+2FA0h] BYREF
  char v1374[16]; // [rsp+30B0h] [rbp+2FB0h] BYREF
  DWORD *v1375; // [rsp+30C0h] [rbp+2FC0h]
  __int64 v1376; // [rsp+30C8h] [rbp+2FC8h]
  char v1377[16]; // [rsp+30D0h] [rbp+2FD0h] BYREF
  __int64 *v1378; // [rsp+30E0h] [rbp+2FE0h]
  __int64 v1379; // [rsp+30E8h] [rbp+2FE8h]
  char *v1380; // [rsp+30F0h] [rbp+2FF0h]
  __int64 v1381; // [rsp+30F8h] [rbp+2FF8h]
  char v1382[32]; // [rsp+3100h] [rbp+3000h] BYREF
  _DWORD *v1383; // [rsp+3120h] [rbp+3020h]
  __int64 v1384; // [rsp+3128h] [rbp+3028h]
  __int64 v1385; // [rsp+3130h] [rbp+3030h]
  _DWORD v1386[2]; // [rsp+3138h] [rbp+3038h] BYREF
  char v1387[16]; // [rsp+3140h] [rbp+3040h] BYREF
  char v1388[16]; // [rsp+3150h] [rbp+3050h] BYREF
  DWORD *v1389; // [rsp+3160h] [rbp+3060h]
  __int64 v1390; // [rsp+3168h] [rbp+3068h]
  char v1391[16]; // [rsp+3170h] [rbp+3070h] BYREF
  __int64 *v1392; // [rsp+3180h] [rbp+3080h]
  __int64 v1393; // [rsp+3188h] [rbp+3088h]
  int *v1394; // [rsp+3190h] [rbp+3090h]
  __int64 v1395; // [rsp+3198h] [rbp+3098h]
  char v1396[16]; // [rsp+31A0h] [rbp+30A0h] BYREF
  char v1397[32]; // [rsp+31B0h] [rbp+30B0h] BYREF
  _DWORD *v1398; // [rsp+31D0h] [rbp+30D0h]
  __int64 v1399; // [rsp+31D8h] [rbp+30D8h]
  __int64 v1400; // [rsp+31E0h] [rbp+30E0h]
  _DWORD v1401[2]; // [rsp+31E8h] [rbp+30E8h] BYREF
  DWORD *v1402; // [rsp+31F0h] [rbp+30F0h]
  __int64 v1403; // [rsp+31F8h] [rbp+30F8h]
  char v1404[16]; // [rsp+3200h] [rbp+3100h] BYREF
  char v1405[16]; // [rsp+3210h] [rbp+3110h] BYREF
  int *v1406; // [rsp+3220h] [rbp+3120h]
  __int64 v1407; // [rsp+3228h] [rbp+3128h]
  char v1408[16]; // [rsp+3230h] [rbp+3130h] BYREF
  char v1409[32]; // [rsp+3240h] [rbp+3140h] BYREF
  _DWORD *v1410; // [rsp+3260h] [rbp+3160h]
  __int64 v1411; // [rsp+3268h] [rbp+3168h]
  __int64 v1412; // [rsp+3270h] [rbp+3170h]
  _DWORD v1413[2]; // [rsp+3278h] [rbp+3178h] BYREF
  DWORD *v1414; // [rsp+3280h] [rbp+3180h]
  __int64 v1415; // [rsp+3288h] [rbp+3188h]
  char v1416[16]; // [rsp+3290h] [rbp+3190h] BYREF
  char v1417[16]; // [rsp+32A0h] [rbp+31A0h] BYREF
  int *v1418; // [rsp+32B0h] [rbp+31B0h]
  __int64 v1419; // [rsp+32B8h] [rbp+31B8h]
  char v1420[16]; // [rsp+32C0h] [rbp+31C0h] BYREF
  char v1421[32]; // [rsp+32D0h] [rbp+31D0h] BYREF
  _DWORD *v1422; // [rsp+32F0h] [rbp+31F0h]
  __int64 v1423; // [rsp+32F8h] [rbp+31F8h]
  __int64 v1424; // [rsp+3300h] [rbp+3200h]
  _DWORD v1425[2]; // [rsp+3308h] [rbp+3208h] BYREF
  char v1426[16]; // [rsp+3310h] [rbp+3210h] BYREF
  char v1427[16]; // [rsp+3320h] [rbp+3220h] BYREF
  int *v1428; // [rsp+3330h] [rbp+3230h]
  __int64 v1429; // [rsp+3338h] [rbp+3238h]
  int *v1430; // [rsp+3340h] [rbp+3240h]
  __int64 v1431; // [rsp+3348h] [rbp+3248h]
  char v1432[16]; // [rsp+3350h] [rbp+3250h] BYREF
  char v1433[32]; // [rsp+3360h] [rbp+3260h] BYREF
  _DWORD *v1434; // [rsp+3380h] [rbp+3280h]
  __int64 v1435; // [rsp+3388h] [rbp+3288h]
  __int64 v1436; // [rsp+3390h] [rbp+3290h]
  _DWORD v1437[2]; // [rsp+3398h] [rbp+3298h] BYREF
  char v1438[16]; // [rsp+33A0h] [rbp+32A0h] BYREF
  __int64 *v1439; // [rsp+33B0h] [rbp+32B0h]
  __int64 v1440; // [rsp+33B8h] [rbp+32B8h]
  char v1441[16]; // [rsp+33C0h] [rbp+32C0h] BYREF
  char v1442[16]; // [rsp+33D0h] [rbp+32D0h] BYREF
  __int64 *v1443; // [rsp+33E0h] [rbp+32E0h]
  __int64 v1444; // [rsp+33E8h] [rbp+32E8h]
  __int64 *v1445; // [rsp+33F0h] [rbp+32F0h]
  __int64 v1446; // [rsp+33F8h] [rbp+32F8h]
  char v1447[16]; // [rsp+3400h] [rbp+3300h] BYREF
  char v1448[16]; // [rsp+3410h] [rbp+3310h] BYREF
  DWORD *v1449; // [rsp+3420h] [rbp+3320h]
  __int64 v1450; // [rsp+3428h] [rbp+3328h]
  char v1451[16]; // [rsp+3430h] [rbp+3330h] BYREF
  char v1452[32]; // [rsp+3440h] [rbp+3340h] BYREF
  char v1453[32]; // [rsp+3460h] [rbp+3360h] BYREF
  DWORD *v1454; // [rsp+3480h] [rbp+3380h]
  __int64 v1455; // [rsp+3488h] [rbp+3388h]
  char v1456[16]; // [rsp+3490h] [rbp+3390h] BYREF
  __int64 *v1457; // [rsp+34A0h] [rbp+33A0h]
  __int64 v1458; // [rsp+34A8h] [rbp+33A8h]
  char v1459[16]; // [rsp+34B0h] [rbp+33B0h] BYREF
  int *v1460; // [rsp+34C0h] [rbp+33C0h]
  __int64 v1461; // [rsp+34C8h] [rbp+33C8h]
  char v1462[16]; // [rsp+34D0h] [rbp+33D0h] BYREF
  __int64 *v1463; // [rsp+34E0h] [rbp+33E0h]
  __int64 v1464; // [rsp+34E8h] [rbp+33E8h]
  __int64 *v1465; // [rsp+34F0h] [rbp+33F0h]
  __int64 v1466; // [rsp+34F8h] [rbp+33F8h]
  __int64 *v1467; // [rsp+3500h] [rbp+3400h]
  __int64 v1468; // [rsp+3508h] [rbp+3408h]
  __int64 *v1469; // [rsp+3510h] [rbp+3410h]
  __int64 v1470; // [rsp+3518h] [rbp+3418h]
  char v1471[32]; // [rsp+3520h] [rbp+3420h] BYREF
  char v1472[32]; // [rsp+3540h] [rbp+3440h] BYREF
  __int64 *v1473; // [rsp+3560h] [rbp+3460h]
  __int64 v1474; // [rsp+3568h] [rbp+3468h]
  DWORD *v1475; // [rsp+3570h] [rbp+3470h]
  __int64 v1476; // [rsp+3578h] [rbp+3478h]
  char v1477[16]; // [rsp+3580h] [rbp+3480h] BYREF
  char v1478[16]; // [rsp+3590h] [rbp+3490h] BYREF
  __int64 *v1479; // [rsp+35A0h] [rbp+34A0h]
  __int64 v1480; // [rsp+35A8h] [rbp+34A8h]
  _QWORD *v1481; // [rsp+35B0h] [rbp+34B0h]
  __int64 v1482; // [rsp+35B8h] [rbp+34B8h]
  __int64 *v1483; // [rsp+35C0h] [rbp+34C0h]
  __int64 v1484; // [rsp+35C8h] [rbp+34C8h]
  __int64 *v1485; // [rsp+35D0h] [rbp+34D0h]
  __int64 v1486; // [rsp+35D8h] [rbp+34D8h]
  char v1487[32]; // [rsp+35E0h] [rbp+34E0h] BYREF
  char v1488[32]; // [rsp+3600h] [rbp+3500h] BYREF
  __int64 *v1489; // [rsp+3620h] [rbp+3520h]
  __int64 v1490; // [rsp+3628h] [rbp+3528h]
  DWORD *v1491; // [rsp+3630h] [rbp+3530h]
  __int64 v1492; // [rsp+3638h] [rbp+3538h]
  char v1493[16]; // [rsp+3640h] [rbp+3540h] BYREF
  char v1494[16]; // [rsp+3650h] [rbp+3550h] BYREF
  __int64 *v1495; // [rsp+3660h] [rbp+3560h]
  __int64 v1496; // [rsp+3668h] [rbp+3568h]
  __int64 *v1497; // [rsp+3670h] [rbp+3570h]
  __int64 v1498; // [rsp+3678h] [rbp+3578h]
  __int64 *v1499; // [rsp+3680h] [rbp+3580h]
  __int64 v1500; // [rsp+3688h] [rbp+3588h]
  __int64 *v1501; // [rsp+3690h] [rbp+3590h]
  __int64 v1502; // [rsp+3698h] [rbp+3598h]
  char v1503[32]; // [rsp+36A0h] [rbp+35A0h] BYREF
  _DWORD *v1504; // [rsp+36C0h] [rbp+35C0h]
  __int64 v1505; // [rsp+36C8h] [rbp+35C8h]
  __int64 v1506; // [rsp+36D0h] [rbp+35D0h]
  _DWORD v1507[2]; // [rsp+36D8h] [rbp+35D8h] BYREF
  char v1508[16]; // [rsp+36E0h] [rbp+35E0h] BYREF
  char v1509[16]; // [rsp+36F0h] [rbp+35F0h] BYREF
  DWORD *v1510; // [rsp+3700h] [rbp+3600h]
  __int64 v1511; // [rsp+3708h] [rbp+3608h]
  char v1512[16]; // [rsp+3710h] [rbp+3610h] BYREF
  int *v1513; // [rsp+3720h] [rbp+3620h]
  __int64 v1514; // [rsp+3728h] [rbp+3628h]
  char v1515[16]; // [rsp+3730h] [rbp+3630h] BYREF
  char v1516[32]; // [rsp+3740h] [rbp+3640h] BYREF
  _DWORD *v1517; // [rsp+3760h] [rbp+3660h]
  __int64 v1518; // [rsp+3768h] [rbp+3668h]
  __int64 v1519; // [rsp+3770h] [rbp+3670h]
  _DWORD v1520[2]; // [rsp+3778h] [rbp+3678h] BYREF
  char v1521[16]; // [rsp+3780h] [rbp+3680h] BYREF
  char v1522[16]; // [rsp+3790h] [rbp+3690h] BYREF
  DWORD *v1523; // [rsp+37A0h] [rbp+36A0h]
  __int64 v1524; // [rsp+37A8h] [rbp+36A8h]
  char v1525[16]; // [rsp+37B0h] [rbp+36B0h] BYREF
  int *v1526; // [rsp+37C0h] [rbp+36C0h]
  __int64 v1527; // [rsp+37C8h] [rbp+36C8h]
  char v1528[16]; // [rsp+37D0h] [rbp+36D0h] BYREF
  char v1529[32]; // [rsp+37E0h] [rbp+36E0h] BYREF
  _DWORD *v1530; // [rsp+3800h] [rbp+3700h]
  __int64 v1531; // [rsp+3808h] [rbp+3708h]
  __int64 v1532; // [rsp+3810h] [rbp+3710h]
  _DWORD v1533[2]; // [rsp+3818h] [rbp+3718h] BYREF
  char v1534[16]; // [rsp+3820h] [rbp+3720h] BYREF
  char v1535[16]; // [rsp+3830h] [rbp+3730h] BYREF
  char v1536[16]; // [rsp+3840h] [rbp+3740h] BYREF
  DWORD *v1537; // [rsp+3850h] [rbp+3750h]
  __int64 v1538; // [rsp+3858h] [rbp+3758h]
  char v1539[16]; // [rsp+3860h] [rbp+3760h] BYREF
  int *v1540; // [rsp+3870h] [rbp+3770h]
  __int64 v1541; // [rsp+3878h] [rbp+3778h]
  char v1542[16]; // [rsp+3880h] [rbp+3780h] BYREF
  char v1543[32]; // [rsp+3890h] [rbp+3790h] BYREF
  char v1544[32]; // [rsp+38B0h] [rbp+37B0h] BYREF
  char v1545[16]; // [rsp+38D0h] [rbp+37D0h] BYREF
  char v1546[16]; // [rsp+38E0h] [rbp+37E0h] BYREF
  DWORD *v1547; // [rsp+38F0h] [rbp+37F0h]
  __int64 v1548; // [rsp+38F8h] [rbp+37F8h]
  char v1549[16]; // [rsp+3900h] [rbp+3800h] BYREF
  __int64 *v1550; // [rsp+3910h] [rbp+3810h]
  __int64 v1551; // [rsp+3918h] [rbp+3818h]
  int *v1552; // [rsp+3920h] [rbp+3820h]
  __int64 v1553; // [rsp+3928h] [rbp+3828h]
  int *v1554; // [rsp+3930h] [rbp+3830h]
  __int64 v1555; // [rsp+3938h] [rbp+3838h]
  char *v1556; // [rsp+3940h] [rbp+3840h]
  __int64 v1557; // [rsp+3948h] [rbp+3848h]
  int *v1558; // [rsp+3950h] [rbp+3850h]
  __int64 v1559; // [rsp+3958h] [rbp+3858h]
  char v1560[16]; // [rsp+3960h] [rbp+3860h] BYREF
  char v1561[32]; // [rsp+3970h] [rbp+3870h] BYREF
  _DWORD *v1562; // [rsp+3990h] [rbp+3890h]
  __int64 v1563; // [rsp+3998h] [rbp+3898h]
  __int64 v1564; // [rsp+39A0h] [rbp+38A0h]
  _DWORD v1565[2]; // [rsp+39A8h] [rbp+38A8h] BYREF
  char v1566[16]; // [rsp+39B0h] [rbp+38B0h] BYREF
  char v1567[16]; // [rsp+39C0h] [rbp+38C0h] BYREF
  char v1568[16]; // [rsp+39D0h] [rbp+38D0h] BYREF
  DWORD *v1569; // [rsp+39E0h] [rbp+38E0h]
  __int64 v1570; // [rsp+39E8h] [rbp+38E8h]
  char v1571[16]; // [rsp+39F0h] [rbp+38F0h] BYREF
  char v1572[32]; // [rsp+3A00h] [rbp+3900h] BYREF
  _DWORD *v1573; // [rsp+3A20h] [rbp+3920h]
  __int64 v1574; // [rsp+3A28h] [rbp+3928h]
  __int64 v1575; // [rsp+3A30h] [rbp+3930h]
  _DWORD v1576[2]; // [rsp+3A38h] [rbp+3938h] BYREF
  char v1577[16]; // [rsp+3A40h] [rbp+3940h] BYREF
  char v1578[16]; // [rsp+3A50h] [rbp+3950h] BYREF
  char v1579; // [rsp+3A60h] [rbp+3960h] BYREF
  char v1580[32]; // [rsp+3A80h] [rbp+3980h] BYREF
  char v1581[16]; // [rsp+3AA0h] [rbp+39A0h] BYREF
  char v1582[16]; // [rsp+3AB0h] [rbp+39B0h] BYREF
  DWORD *v1583; // [rsp+3AC0h] [rbp+39C0h]
  __int64 v1584; // [rsp+3AC8h] [rbp+39C8h]
  char v1585[16]; // [rsp+3AD0h] [rbp+39D0h] BYREF
  char v1586[16]; // [rsp+3AE0h] [rbp+39E0h] BYREF
  char *v1587; // [rsp+3AF0h] [rbp+39F0h]
  __int64 v1588; // [rsp+3AF8h] [rbp+39F8h]
  __int64 *v1589; // [rsp+3B00h] [rbp+3A00h]
  __int64 v1590; // [rsp+3B08h] [rbp+3A08h]
  int *v1591; // [rsp+3B10h] [rbp+3A10h]
  __int64 v1592; // [rsp+3B18h] [rbp+3A18h]
  char v1593[16]; // [rsp+3B20h] [rbp+3A20h] BYREF
  char v1594[32]; // [rsp+3B30h] [rbp+3A30h] BYREF
  char v1595[32]; // [rsp+3B50h] [rbp+3A50h] BYREF
  char v1596[16]; // [rsp+3B70h] [rbp+3A70h] BYREF
  char v1597[16]; // [rsp+3B80h] [rbp+3A80h] BYREF
  char v1598[16]; // [rsp+3B90h] [rbp+3A90h] BYREF
  char *v1599; // [rsp+3BA0h] [rbp+3AA0h]
  __int64 v1600; // [rsp+3BA8h] [rbp+3AA8h]
  __int64 *v1601; // [rsp+3BB0h] [rbp+3AB0h]
  __int64 v1602; // [rsp+3BB8h] [rbp+3AB8h]
  WCHAR ImageFileName[512]; // [rsp+3BC0h] [rbp+3AC0h] BYREF

  v9 = a5;
  v10 = 0;
  v168 = a3;
  v11 = a1;
  UnbiasedTime = 0;
  FileSize.QuadPart = 0;
  result = (__int64)memset_0(v467, 0, 0x404u);
  if ( !byte_180028930 && !byte_180028B80 )
    return result;
  result = (__int64)NtCurrentPeb();
  if ( *(_BYTE *)(*(_QWORD *)(result + 24) + 72LL) )
    return result;
  v165 = 0;
  v166 = 0;
  v167 = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v324 = UnbiasedTime - a6;
  LOBYTE(v14) = (_WORD)v11 == 15;
  TlmiUpdateFirstRunExpStatus(UnbiasedTime, v14, a7, (unsigned int)a8);
  v15 = 8;
  v16 = 65533;
  v17 = 9;
  v18 = 13;
  if ( (_WORD)v11 == 11 )
  {
    TlmiInitializeRunawayHydrationDetection();
    TlmiInitializeHydrationPerformanceTracking();
LABEL_22:
    v10 = a7[6];
    goto LABEL_29;
  }
  if ( (_WORD)v11 == 9 )
    goto LABEL_13;
  v17 = 15;
  if ( (_WORD)v11 == 15 )
  {
    v10 = (unsigned int)a7[8];
    v165 = a7[4];
    goto LABEL_29;
  }
  v17 = 17;
  if ( (_WORD)v11 == 17 || (_DWORD)v11 == 16 || (v17 = 20, (_WORD)v11 == 20) || (_WORD)v11 == 22 )
  {
LABEL_13:
    v10 = a7[4];
    goto LABEL_29;
  }
  if ( (_DWORD)v11 == 21 )
  {
    TlmiLogHydrationAborted(a7, 20, 13, 65533);
    v10 = a7[5];
  }
  else
  {
    if ( (_DWORD)v11 != 28 )
    {
      if ( (v11 & 0xFFFD) != 0 )
      {
        switch ( (_WORD)v11 )
        {
          case 4:
            v10 = a7[4];
            v165 = a7[6];
            v19 = a7[5];
            break;
          case 0xE:
            goto LABEL_22;
          case 0xD:
            v10 = a7[7];
            goto LABEL_29;
          default:
            if ( (unsigned __int16)v11 >= 8u )
              goto LABEL_29;
            v10 = *((_QWORD *)a7 + 2);
            v166 = *a7;
            FileSize = *(union _LARGE_INTEGER *)(a7 + 6);
            v19 = a7[8];
            break;
        }
      }
      else
      {
        v10 = *((_QWORD *)a7 + 2);
        v19 = a7[6];
      }
      v167 = v19;
      goto LABEL_29;
    }
    v165 = a7[4];
  }
LABEL_29:
  if ( !a4 || !a5 )
  {
    if ( a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL || a8 == -2147024890 || !byte_180028930 )
    {
      if ( v168 )
      {
        a4 = (const WCHAR *)v468;
        v9 = (const WCHAR *)v469;
        if ( (int)CfpGetSyncRootInfoByPath(v168, 2, (unsigned int)v467, 1028, 0) < 0 )
        {
          a4 = 0;
          v9 = 0;
        }
      }
      else
      {
        a4 = &SourceString;
        FileSize.QuadPart = 0;
        v9 = &SourceString;
      }
    }
    else
    {
      if ( (unsigned __int8)CfReferenceProtectedHandle(a2, v17, v18, v16) )
      {
        if ( (a2 & 1) != 0 )
          v20 = *(void **)(a2 & 0xFFFFFFFFFFFFFFFEuLL);
        else
          v20 = (void *)a2;
        v144 = 1;
      }
      else
      {
        v144 = 0;
        v20 = (void *)a2;
      }
      GetFileSizeEx(v20, &FileSize);
      SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(v20, 0);
      v17 = 0;
      v9 = (const WCHAR *)v469;
      a4 = (const WCHAR *)v468;
      if ( SyncRootInfoByHandle < 0 )
      {
        v9 = 0;
        a4 = 0;
      }
      if ( v144 )
        CfpReleaseProtectedHandle(a2);
    }
  }
  IsInitialized = TlmiIsInitialized(v15, v17, v18, v16);
  v25 = qword_1800283B0;
  if ( IsInitialized )
  {
    v23 = (v324 * (unsigned __int128)0x346DC5D63886594BuLL) >> 64;
    v26 = v324 / 0x2710;
    if ( (v11 & 0xFFFD) == 0 )
    {
      v27 = a7[6];
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      TlmiLogHydrationPerformance(
        0,
        (_DWORD)a4,
        (_DWORD)v9,
        *((_QWORD *)a7 + 5),
        *((_QWORD *)a7 + 4),
        UnbiasedTime,
        v27,
        v166);
      v25 = qword_1800283B0;
    }
    if ( (_DWORD)v11 == 24 )
    {
      if ( (unsigned int)dword_1800281A0 > 5 )
      {
        v24 = qword_1800281B8;
        v23 = 0x200000000000LL;
        if ( (qword_1800281B0 & 0x200000000000LL) != 0 && (qword_1800281B8 & 0x200000000000LL) == qword_1800281B8 )
        {
          v327 = v26;
          v512 = &v325;
          v326 = v165;
          v514 = &v326;
          v516 = &v327;
          v328 = FileSize;
          v518 = &v328;
          v520 = &v329;
          v330 = UnbiasedTime;
          v332 = UnbiasedTime;
          v522 = &v330;
          v526 = &v332;
          v524 = &v331;
          v530 = off_180028600;
          v329 = a6;
          v331 = a6;
          v528 = v531;
          v531[0] = (unsigned __int16)word_1800285F8;
          v325 = 1;
          v513 = 8;
          v515 = 8;
          v517 = 8;
          v519 = 8;
          v521 = 8;
          v523 = 8;
          v525 = 8;
          v527 = 8;
          v529 = 2;
          v531[1] = 0;
          tlgCreate1Sz_wchar_t(v532, a4);
          tlgCreate1Sz_wchar_t(v533, v9);
          v333 = v10;
          v534 = &v333;
          v145 = byte_180028968;
          v536 = &v145;
          v538 = &v279;
          v334 = v166;
          v540 = &v334;
          v335 = (unsigned int)dword_180028B78;
          v542 = &v335;
          v336 = qword_180028B70;
          v544 = &v336;
          v321 = dword_180028B7C;
          v535 = 8;
          v537 = 1;
          v279 = a8;
          v539 = 4;
          v541 = 8;
          v543 = 8;
          v545 = 8;
          v547 = 4;
          v546 = &v321;
          v28 = 22;
          v337 = 0x1000000;
          v548 = &v337;
          v29 = &byte_180024017;
          v30 = &v511;
          v549 = 8;
LABEL_59:
          tlgWriteAgg((unsigned int)&dword_1800281A0, (_DWORD)v29, 0, v28, (__int64)v30);
        }
      }
    }
    else if ( (unsigned __int16)(v11 - 11) <= 1u )
    {
      if ( (unsigned int)dword_1800281A0 > 5 )
      {
        v23 = qword_1800281B8;
        v24 = 0x400000000000LL;
        if ( (qword_1800281B0 & 0x400000000000LL) != 0 && (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
        {
          v353 = v26;
          v351 = 1;
          v551 = &v351;
          v352 = v165;
          v553 = &v352;
          v555 = &v353;
          v354 = FileSize;
          v557 = &v354;
          v355 = a6;
          v559 = &v355;
          v356 = UnbiasedTime;
          v561 = &v356;
          v552 = 8;
          v554 = 8;
          v556 = 8;
          v558 = 8;
          v560 = 8;
          v562 = 8;
          v33 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v34 = qword_1800283B0[3 * v11 + 2];
          v563 = v566;
          v566[0] = v33;
          v564 = 2;
          v565 = v34;
          v566[1] = 0;
          tlgCreate1Sz_wchar_t(v567, a4);
          tlgCreate1Sz_wchar_t(v568, v9);
          v357 = v10;
          v569 = &v357;
          v147 = byte_180028968;
          v571 = &v147;
          v573 = &v173;
          v358 = v166;
          v575 = &v358;
          v359 = (unsigned int)dword_180028B78;
          v577 = &v359;
          v360 = qword_180028B70;
          v579 = &v360;
          v174 = dword_180028B7C;
          v581 = &v174;
          v583 = &v361;
          v570 = 8;
          v572 = 1;
          v173 = a8;
          v574 = 4;
          v576 = 8;
          v578 = 8;
          v580 = 8;
          v582 = 4;
          v361 = 0x1000000;
          v584 = 8;
          tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023E8B, 0, 0, 20, v550);
        }
      }
    }
    else if ( (unsigned int)dword_1800281A0 > 5 )
    {
      v23 = qword_1800281B8;
      v24 = 0x400000000000LL;
      if ( (qword_1800281B0 & 0x400000000000LL) != 0 && (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
      {
        v342 = a6;
        v471 = &v338;
        v339 = v165;
        v473 = &v339;
        v475 = &v340;
        v341 = FileSize;
        v344 = a6;
        v477 = &v341;
        v483 = &v344;
        v479 = &v342;
        v343 = UnbiasedTime;
        v345 = UnbiasedTime;
        v340 = v26;
        v481 = &v343;
        v485 = &v345;
        v338 = 1;
        v472 = 8;
        v474 = 8;
        v476 = 8;
        v478 = 8;
        v480 = 8;
        v482 = 8;
        v484 = 8;
        v486 = 8;
        v31 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v32 = qword_1800283B0[3 * v11 + 2];
        v487 = v490;
        v490[0] = v31;
        v488 = 2;
        v489 = v32;
        v490[1] = 0;
        tlgCreate1Sz_wchar_t(v491, a4);
        tlgCreate1Sz_wchar_t(v492, v9);
        v346 = v10;
        v493 = &v346;
        v322 = v167;
        v495 = &v322;
        v146 = byte_180028968;
        v497 = &v146;
        v499 = &v171;
        v347 = v166;
        v501 = &v347;
        v348 = (unsigned int)dword_180028B78;
        v503 = &v348;
        v494 = 8;
        v496 = 4;
        v498 = 1;
        v171 = a8;
        v500 = 4;
        v502 = 8;
        v504 = 8;
        v349 = qword_180028B70;
        v28 = 23;
        v506 = 8;
        v505 = &v349;
        v29 = byte_180022963;
        v172 = dword_180028B7C;
        v507 = &v172;
        v509 = &v350;
        v30 = &v470;
        v508 = 4;
        v350 = 0x1000000;
        v510 = 8;
        goto LABEL_59;
      }
    }
  }
  result = TracingInitialized(v24, v23, v25);
  if ( !(_BYTE)result || !a7 )
    return result;
  memset_0(ImageFileName, 0, sizeof(ImageFileName));
  CurrentProcessId = GetCurrentProcessId();
  v36 = 9;
  v37 = CurrentProcessId;
  if ( (unsigned __int16)(v11 - 9) <= 3u || a8 < 0 || v167 < 0 )
  {
    v38 = OpenProcess(0x410u, 0, CurrentProcessId);
    if ( v38 )
    {
      if ( K32GetProcessImageFileNameW(v38, ImageFileName, 0x200u) || (unsigned int)dword_1800281A0 <= 2 )
        goto LABEL_79;
      v39 = LOWORD(qword_1800283B0[3 * v11 + 1]);
      v40 = qword_1800283B0[3 * v11 + 2];
      v1193 = v1196;
      v1194 = 2;
      v1195 = v40;
      v1196[0] = v39;
      v1196[1] = 0;
      LastError = GetLastError();
      v1198 = 4;
      v175 = LastError;
      v1197 = &v175;
      tlgCreate1Sz_wchar_t(v1199, L"Failed retrieving processName");
      v42 = &v1192;
      v43 = (__int16 *)byte_180024543;
    }
    else
    {
      if ( (unsigned int)dword_1800281A0 <= 2 )
        goto LABEL_79;
      v48 = LOWORD(qword_1800283B0[3 * v11 + 1]);
      v49 = qword_1800283B0[3 * v11 + 2];
      v1201 = v1204;
      v1202 = 2;
      v1203 = v49;
      v1204[0] = v48;
      v1204[1] = 0;
      v50 = GetLastError();
      v1206 = 4;
      v176 = v50;
      v1205 = &v176;
      tlgCreate1Sz_wchar_t(v1207, L"Failed retrieving processhandle");
      v42 = &v1200;
      v43 = word_180022DD2;
    }
    tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v43, 0, 0, 6, v42);
LABEL_79:
    v36 = 9;
  }
  result = 17;
  if ( (unsigned int)v11 > 0x11 )
  {
    if ( (unsigned int)v11 <= 0x19 )
    {
      switch ( (_DWORD)v11 )
      {
        case 0x19:
          if ( a8 == -2147024662 || a8 == -2147024506 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 4 )
            {
              v133 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1301 = qword_1800283B0[3 * v11 + 2];
              v1299 = v1302;
              v1302[0] = v133;
              v1303 = &v295;
              v1300 = 2;
              v1302[1] = 0;
              v295 = v37;
              v1304 = 4;
              tlgCreate1Sz_wchar_t(v1305, ImageFileName);
              v296 = a8;
              v1306 = &v296;
              v1307 = 4;
              tlgCreate1Sz_wchar_t(v1308, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_180022234, 0, 0, 8, v1298);
            }
          }
          else if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v132 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1312 = qword_1800283B0[3 * v11 + 2];
              v1310 = v1313;
              v1313[0] = v132;
              v1314 = &v293;
              v1311 = 2;
              v1313[1] = 0;
              v293 = v37;
              v1315 = 4;
              tlgCreate1Sz_wchar_t(v1316, ImageFileName);
              v294 = a8;
              v1317 = &v294;
              v1318 = 4;
              tlgCreate1Sz_wchar_t(v1319, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_18002357D, 0, 0, 8, v1309);
            }
          }
          break;
        case 0x12:
          result = (unsigned int)dword_1800281A0;
          if ( a8 < 0 )
          {
            if ( a8 == -2147023899 )
            {
              if ( (unsigned int)dword_1800281A0 > 5 )
              {
                v128 = LOWORD(qword_1800283B0[3 * v11 + 1]);
                v129 = qword_1800283B0[3 * v11 + 2];
                v1517 = v1520;
                v1520[0] = v128;
                v1518 = 2;
                v1519 = v129;
                v1520[1] = 0;
                tlgCreate1Sz_wchar_t(v1521, a4);
                tlgCreate1Sz_wchar_t(v1522, v9);
                v289 = v37;
                v1523 = &v289;
                v1524 = 4;
                tlgCreate1Sz_wchar_t(v1525, ImageFileName);
                v290 = -2147023899;
                v1526 = &v290;
                v1527 = 4;
                tlgCreate1Sz_wchar_t(v1528, *((_QWORD *)a7 + 1));
                return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023033, 0, 0, 10, v1516);
              }
            }
            else if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v130 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v131 = qword_1800283B0[3 * v11 + 2];
              v1504 = v1507;
              v1507[0] = v130;
              v1505 = 2;
              v1506 = v131;
              v1507[1] = 0;
              tlgCreate1Sz_wchar_t(v1508, a4);
              tlgCreate1Sz_wchar_t(v1509, v9);
              v291 = v37;
              v1510 = &v291;
              v1511 = 4;
              tlgCreate1Sz_wchar_t(v1512, ImageFileName);
              v292 = a8;
              v1513 = &v292;
              v1514 = 4;
              tlgCreate1Sz_wchar_t(v1515, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, word_180023F9A, 0, 0, 10, v1503);
            }
          }
          else if ( (unsigned int)dword_1800281A0 > 5 )
          {
            v126 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v127 = qword_1800283B0[3 * v11 + 2];
            v1573 = v1576;
            v1576[0] = v126;
            v1574 = 2;
            v1575 = v127;
            v1576[1] = 0;
            tlgCreate1Sz_wchar_t(v1577, a4);
            tlgCreate1Sz_wchar_t(v1578, v9);
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_180023774, 0, 0, 6, v1572);
          }
          break;
        case 0x13:
          if ( a8 == -2147023899 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              v124 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v945 = qword_1800283B0[3 * v11 + 2];
              v943 = v946;
              v946[0] = v124;
              v947 = &v285;
              v944 = 2;
              v946[1] = 0;
              v285 = v37;
              v948 = 4;
              tlgCreate1Sz_wchar_t(v949, ImageFileName);
              v414 = *((_QWORD *)a7 + 2);
              v950 = &v414;
              v951 = 8;
              v415 = *((_QWORD *)a7 + 3);
              v952 = &v415;
              v954 = &v286;
              v953 = 8;
              v286 = -2147023899;
              v955 = 4;
              tlgCreate1Sz_wchar_t(v956, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &byte_1800228E7, 0, 0, 10, v942);
            }
          }
          else if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v125 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v960 = qword_1800283B0[3 * v11 + 2];
              v958 = v961;
              v961[0] = v125;
              v962 = &v287;
              v959 = 2;
              v961[1] = 0;
              v287 = v37;
              v963 = 4;
              tlgCreate1Sz_wchar_t(v964, ImageFileName);
              v416 = *((_QWORD *)a7 + 2);
              v965 = &v416;
              v966 = 8;
              v417 = *((_QWORD *)a7 + 3);
              v967 = &v417;
              v969 = &v288;
              v968 = 8;
              v288 = a8;
              v970 = 4;
              tlgCreate1Sz_wchar_t(v971, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_18002398B, 0, 0, 10, v957);
            }
          }
          break;
        case 0x14:
          if ( a8 == -2147023899 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              v122 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1036 = qword_1800283B0[3 * v11 + 2];
              v1034 = v1037;
              v1037[0] = v122;
              v1038 = &v301;
              v1035 = 2;
              v1037[1] = 0;
              v301 = v37;
              v1039 = 4;
              tlgCreate1Sz_wchar_t(v1040, ImageFileName);
              v280 = a7[4];
              v1041 = &v280;
              v1043 = &v281;
              v1042 = 4;
              v281 = -2147023899;
              v1044 = 4;
              tlgCreate1Sz_wchar_t(v1045, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &unk_180024430, 0, 0, 9, v1033);
            }
          }
          else if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v123 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1023 = qword_1800283B0[3 * v11 + 2];
              v1021 = v1024;
              v1024[0] = v123;
              v1025 = &v282;
              v1022 = 2;
              v1024[1] = 0;
              v282 = v37;
              v1026 = 4;
              tlgCreate1Sz_wchar_t(v1027, ImageFileName);
              v283 = a7[4];
              v1028 = &v283;
              v1030 = &v284;
              v1029 = 4;
              v284 = a8;
              v1031 = 4;
              tlgCreate1Sz_wchar_t(v1032, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180022F45, 0, 0, 9, v1020);
            }
          }
          break;
        case 0x15:
          result = (unsigned int)dword_1800281A0;
          if ( a8 < 0 )
          {
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v121 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v728 = qword_1800283B0[3 * v11 + 2];
              v726 = v729;
              v729[0] = v121;
              v730 = &v275;
              v727 = 2;
              v729[1] = 0;
              v275 = v37;
              v731 = 4;
              tlgCreate1Sz_wchar_t(v732, ImageFileName);
              v276 = a7[4];
              v733 = &v276;
              v734 = 4;
              v277 = a7[5];
              v735 = &v277;
              v736 = 4;
              v412 = *((_QWORD *)a7 + 3);
              v737 = &v412;
              v738 = 8;
              v413 = *((_QWORD *)a7 + 4);
              v739 = &v413;
              v741 = &v278;
              v740 = 8;
              v278 = a8;
              v742 = 4;
              tlgCreate1Sz_wchar_t(v743, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &byte_180024307, 0, 0, 12, v725);
            }
          }
          else if ( (unsigned int)dword_1800281A0 > 4 )
          {
            v120 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v603 = qword_1800283B0[3 * v11 + 2];
            v601 = v604;
            v604[0] = v120;
            v602 = 2;
            v604[1] = 0;
            v273 = a7[4];
            v605 = &v273;
            v606 = 4;
            v274 = a7[5];
            v607 = &v274;
            v608 = 4;
            v410 = *((_QWORD *)a7 + 3);
            v609 = &v410;
            v610 = 8;
            v411 = *((_QWORD *)a7 + 4);
            v611 = &v411;
            v612 = 8;
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &word_180022D66, 0, 0, 8, v600);
          }
          break;
        case 0x16:
          if ( a8 == -2147023899 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              v118 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v810 = qword_1800283B0[3 * v11 + 2];
              v808 = v811;
              v811[0] = v118;
              v812 = &v265;
              v809 = 2;
              v811[1] = 0;
              v265 = v37;
              v813 = 4;
              tlgCreate1Sz_wchar_t(v814, ImageFileName);
              v266 = a7[4];
              v815 = &v266;
              v816 = 4;
              v267 = a7[5];
              v817 = &v267;
              v819 = &v268;
              v818 = 4;
              v268 = -2147023899;
              v820 = 4;
              tlgCreate1Sz_wchar_t(v821, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023703, 0, 0, 10, v807);
            }
          }
          else if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v119 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v930 = qword_1800283B0[3 * v11 + 2];
              v928 = v931;
              v931[0] = v119;
              v932 = &v269;
              v929 = 2;
              v931[1] = 0;
              v269 = v37;
              v933 = 4;
              tlgCreate1Sz_wchar_t(v934, ImageFileName);
              v270 = a7[4];
              v935 = &v270;
              v936 = 4;
              v271 = a7[5];
              v937 = &v271;
              v939 = &v272;
              v938 = 4;
              v272 = a8;
              v940 = 4;
              tlgCreate1Sz_wchar_t(v941, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023D63, 0, 0, 10, v927);
            }
          }
          break;
        case 0x17:
          if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v117 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v915 = qword_1800283B0[3 * v11 + 2];
              v913 = v916;
              v916[0] = v117;
              v917 = &v261;
              v914 = 2;
              v916[1] = 0;
              v261 = v37;
              v918 = 4;
              tlgCreate1Sz_wchar_t(v919, ImageFileName);
              v262 = a7[4];
              v920 = &v262;
              v921 = 4;
              v263 = *((unsigned __int8 *)a7 + 20);
              v922 = &v263;
              v924 = &v264;
              v923 = 4;
              v264 = a8;
              v925 = 4;
              tlgCreate1Sz_wchar_t(v926, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800230B3, 0, 0, 10, v912);
            }
          }
          break;
        default:
          if ( a8 == -2147024662 || a8 == -2147024506 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 4 )
            {
              v116 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1400 = qword_1800283B0[3 * v11 + 2];
              v1398 = v1401;
              v1401[0] = v116;
              v1402 = &v259;
              v1399 = 2;
              v1401[1] = 0;
              v259 = v37;
              v1403 = 4;
              tlgCreate1Sz_wchar_t(v1404, ImageFileName);
              tlgCreate1Sz_wchar_t(v1405, v168);
              v260 = a8;
              v1406 = &v260;
              v1407 = 4;
              tlgCreate1Sz_wchar_t(v1408, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_18002420D, 0, 0, 9, v1397);
            }
          }
          else if ( a8 < 0 )
          {
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 2 )
            {
              v115 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v1412 = qword_1800283B0[3 * v11 + 2];
              v1410 = v1413;
              v1413[0] = v115;
              v1414 = &v257;
              v1411 = 2;
              v1413[1] = 0;
              v257 = v37;
              v1415 = 4;
              tlgCreate1Sz_wchar_t(v1416, ImageFileName);
              tlgCreate1Sz_wchar_t(v1417, v168);
              v258 = a8;
              v1418 = &v258;
              v1419 = 4;
              tlgCreate1Sz_wchar_t(v1420, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800235E3, 0, 0, 9, v1409);
            }
          }
          break;
      }
      return result;
    }
    switch ( (_DWORD)v11 )
    {
      case 0x1D:
        result = (unsigned int)dword_1800281A0;
        if ( a8 >= 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 4 )
          {
            result = tlgKeywordOn(&dword_1800281A0, 0, 9);
            if ( (_BYTE)result )
            {
              tlgCreate2Binary(v1595, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
              tlgCreate1Sz_wchar_t(v1596, a4);
              tlgCreate1Sz_wchar_t(v1597, v9);
              tlgCreate1Sz_wchar_t(v1598, *((_QWORD *)a7 + 2));
              v163 = *((_BYTE *)a7 + 32);
              v1599 = &v163;
              v1600 = 1;
              v465 = *((_QWORD *)a7 + 3);
              v1601 = &v465;
              v1602 = 8;
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_180023A04, 0, 0, 9, v1594);
            }
          }
          return result;
        }
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        result = tlgKeywordOn(&dword_1800281A0, 0, 9);
        if ( !(_BYTE)result )
          return result;
        tlgCreate2Binary(v1580, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
        tlgCreate1Sz_wchar_t(v1581, a4);
        tlgCreate1Sz_wchar_t(v1582, v9);
        v319 = v37;
        v1583 = &v319;
        v1584 = 4;
        tlgCreate1Sz_wchar_t(v1585, ImageFileName);
        tlgCreate1Sz_wchar_t(v1586, *((_QWORD *)a7 + 2));
        v164 = *((_BYTE *)a7 + 32);
        v1587 = &v164;
        v1588 = 1;
        v466 = *((_QWORD *)a7 + 3);
        v1589 = &v466;
        v1591 = &v320;
        v1590 = 8;
        v320 = a8;
        v1592 = 4;
        tlgCreate1Sz_wchar_t(v1593, *((_QWORD *)a7 + 1));
        v46 = &v1579;
        v47 = (__int16 *)byte_180022483;
        break;
      case 0x1E:
        if ( a8 < 0 )
        {
          result = (unsigned int)dword_1800281A0;
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v143 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v1290 = qword_1800283B0[3 * v11 + 2];
            v1288 = v1291;
            v1291[0] = v143;
            v1292 = &v317;
            v1289 = 2;
            v1291[1] = 0;
            v317 = v37;
            v1293 = 4;
            tlgCreate1Sz_wchar_t(v1294, ImageFileName);
            v318 = a8;
            v1295 = &v318;
            v1296 = 4;
            tlgCreate1Sz_wchar_t(v1297, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180022531, 0, 0, 8, v1287);
          }
        }
        return result;
      case 0x1F:
        if ( a8 < 0 )
        {
          result = (unsigned int)dword_1800281A0;
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v142 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v709 = qword_1800283B0[3 * v11 + 2];
            v707 = v710;
            v710[0] = v142;
            v711 = &v315;
            v708 = 2;
            v710[1] = 0;
            v315 = v37;
            v712 = 4;
            tlgCreate1Sz_wchar_t(v713, ImageFileName);
            v461 = *((_QWORD *)a7 + 2);
            v714 = &v461;
            v715 = 8;
            v462 = *((_QWORD *)a7 + 3);
            v716 = &v462;
            v717 = 8;
            v463 = *((_QWORD *)a7 + 4);
            v718 = &v463;
            v719 = 8;
            v464 = a7[10];
            v720 = &v464;
            v722 = &v316;
            v721 = 8;
            v316 = a8;
            v723 = 4;
            tlgCreate1Sz_wchar_t(v724, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_18002323C, 0, 0, 12, v706);
          }
        }
        return result;
      case 0x20:
        if ( a8 == -2147024774 )
        {
          result = (unsigned int)dword_1800281A0;
          if ( (unsigned int)dword_1800281A0 <= 5 )
            return result;
          v140 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v646 = qword_1800283B0[3 * v11 + 2];
          v644 = v647;
          v647[0] = v140;
          v645 = 2;
          v647[1] = 0;
          v305 = a7[5];
          v648 = &v305;
          v649 = 4;
          v306 = a7[6];
          v650 = &v306;
          v651 = 4;
          v459 = *((_QWORD *)a7 + 4);
          v652 = &v459;
          v653 = 8;
          v161 = *((_BYTE *)a7 + 40);
          v654 = &v161;
          v655 = 1;
          v307 = a7[4];
          v656 = &v307;
          v658 = &v308;
          v657 = 4;
          v308 = v37;
          v659 = 4;
          tlgCreate1Sz_wchar_t(v660, ImageFileName);
          v309 = -2147024774;
          v661 = &v309;
          v662 = 4;
          tlgCreate1Sz_wchar_t(v663, *((_QWORD *)a7 + 1));
          v46 = &v643;
          v47 = (__int16 *)&unk_180022628;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
        }
        if ( a8 >= 0 )
          return result;
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v141 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v667 = qword_1800283B0[3 * v11 + 2];
        v665 = v668;
        v668[0] = v141;
        v666 = 2;
        v668[1] = 0;
        v310 = a7[5];
        v669 = &v310;
        v670 = 4;
        v311 = a7[6];
        v671 = &v311;
        v672 = 4;
        v460 = *((_QWORD *)a7 + 4);
        v673 = &v460;
        v674 = 8;
        v162 = *((_BYTE *)a7 + 40);
        v675 = &v162;
        v676 = 1;
        v312 = a7[4];
        v677 = &v312;
        v679 = &v313;
        v678 = 4;
        v313 = v37;
        v680 = 4;
        tlgCreate1Sz_wchar_t(v681, ImageFileName);
        v314 = a8;
        v682 = &v314;
        v683 = 4;
        tlgCreate1Sz_wchar_t(v684, *((_QWORD *)a7 + 1));
        v46 = &v664;
        v47 = &word_180024646;
        break;
      default:
        switch ( (_DWORD)v11 )
        {
          case '!':
            result = (unsigned int)dword_1800281A0;
            if ( a8 < 0 )
            {
              if ( (unsigned int)dword_1800281A0 <= 2 )
                return result;
              v139 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v688 = qword_1800283B0[3 * v11 + 2];
              v686 = v689;
              v689[0] = v139;
              v690 = &v303;
              v687 = 2;
              v689[1] = 0;
              v303 = v37;
              v691 = 4;
              tlgCreate1Sz_wchar_t(v692, ImageFileName);
              v454 = *((_QWORD *)a7 + 2);
              v693 = &v454;
              v694 = 8;
              v455 = *((_QWORD *)a7 + 3);
              v695 = &v455;
              v696 = 8;
              v456 = *((_QWORD *)a7 + 4);
              v697 = &v456;
              v698 = 8;
              v457 = *((_QWORD *)a7 + 5);
              v699 = &v457;
              v700 = 8;
              v458 = *((_QWORD *)a7 + 6);
              v701 = &v458;
              v703 = &v304;
              v702 = 8;
              v304 = a8;
              v704 = 4;
              tlgCreate1Sz_wchar_t(v705, *((_QWORD *)a7 + 1));
              v46 = &v685;
              v47 = (__int16 *)&unk_1800237C8;
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
            }
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              v138 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v588 = qword_1800283B0[3 * v11 + 2];
              v589[0] = v138;
              v586 = v589;
              v587 = 2;
              v589[1] = 0;
              v449 = *((_QWORD *)a7 + 2);
              v590 = &v449;
              v591 = 8;
              v450 = *((_QWORD *)a7 + 3);
              v592 = &v450;
              v593 = 8;
              v451 = *((_QWORD *)a7 + 4);
              v594 = &v451;
              v595 = 8;
              v452 = *((_QWORD *)a7 + 5);
              v596 = &v452;
              v597 = 8;
              v453 = *((_QWORD *)a7 + 6);
              v598 = &v453;
              v599 = 8;
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &word_1800231A6, 0, 0, 9, v585);
            }
            break;
          case '"':
            if ( a8 < 0 )
            {
              if ( (unsigned int)dword_1800281A0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800281A0, 0, 9) )
              {
                tlgCreate2Binary(v1453, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
                v300 = v37;
                v1454 = &v300;
                v1455 = 4;
                tlgCreate1Sz_wchar_t(v1456, ImageFileName);
                v438 = a6;
                v1457 = &v438;
                v1458 = 8;
                tlgCreate1Sz_wchar_t(v1459, *((_QWORD *)a7 + 1));
                v323 = a8;
                v1460 = &v323;
                v1461 = 4;
                tlgCreate1Sz_wchar_t(v1462, *((_QWORD *)a7 + 2));
                v439 = (unsigned int)a7[6];
                v1464 = 8;
                v1463 = &v439;
                v440 = (unsigned int)a7[7];
                v1465 = &v440;
                v1466 = 8;
                v441 = (unsigned int)a7[8];
                v1467 = &v441;
                v1468 = 8;
                v442 = (unsigned int)a7[9];
                v1469 = &v442;
                v1470 = 8;
                tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_18002233D, 0, 0, 14, v1452);
              }
              result = (unsigned int)dword_1800281A0;
              if ( (unsigned int)dword_1800281A0 > 5 )
              {
                result = tlgKeywordOn(&dword_1800281A0, 0, v36);
                if ( (_BYTE)result )
                {
                  v443 = *((_QWORD *)a7 + 10);
                  v629 = &v443;
                  v630 = 8;
                  v137 = *((_QWORD *)a7 + 5);
                  v631 = &v444;
                  v444 = v137;
                  v632 = 8;
                  v445 = *((_QWORD *)a7 + 6);
                  v633 = &v445;
                  v634 = 8;
                  v446 = *((_QWORD *)a7 + 9);
                  v635 = &v446;
                  v636 = 8;
                  v302 = a7[16];
                  v637 = &v302;
                  v638 = 4;
                  v447 = *((_QWORD *)a7 + 7);
                  v639 = &v447;
                  v641 = &v448;
                  v640 = 8;
                  v448 = v137;
                  v642 = 8;
                  return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800246EB, 0, 0, 9, v628);
                }
              }
            }
            else
            {
              if ( (unsigned int)dword_1800281A0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800281A0, 0, 9) )
              {
                tlgCreate2Binary(v1488, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
                v427 = a6;
                v1490 = 8;
                v1489 = &v427;
                v1491 = &v298;
                v298 = v37;
                v1492 = 4;
                tlgCreate1Sz_wchar_t(v1493, ImageFileName);
                tlgCreate1Sz_wchar_t(v1494, *((_QWORD *)a7 + 2));
                v428 = (unsigned int)a7[6];
                v1496 = 8;
                v1495 = &v428;
                v429 = (unsigned int)a7[7];
                v1497 = &v429;
                v1498 = 8;
                v430 = (unsigned int)a7[8];
                v1499 = &v430;
                v1500 = 8;
                v431 = (unsigned int)a7[9];
                v1501 = &v431;
                v1502 = 8;
                tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800218F5, 0, 0, 12, v1487);
              }
              result = (unsigned int)dword_1800281A0;
              if ( (unsigned int)dword_1800281A0 > 5 )
              {
                result = tlgKeywordOn(&dword_1800281A0, 0, v36);
                if ( (_BYTE)result )
                {
                  v432 = *((_QWORD *)a7 + 10);
                  v614 = &v432;
                  v615 = 8;
                  v136 = *((_QWORD *)a7 + 5);
                  v616 = &v433;
                  v433 = v136;
                  v617 = 8;
                  v434 = *((_QWORD *)a7 + 6);
                  v618 = &v434;
                  v619 = 8;
                  v435 = *((_QWORD *)a7 + 9);
                  v620 = &v435;
                  v621 = 8;
                  v299 = a7[16];
                  v622 = &v299;
                  v623 = 4;
                  v436 = *((_QWORD *)a7 + 7);
                  v624 = &v436;
                  v626 = &v437;
                  v625 = 8;
                  v437 = v136;
                  v627 = 8;
                  return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800247BB, 0, 0, 9, v613);
                }
              }
            }
            break;
          case '#':
            result = (unsigned int)dword_1800281A0;
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              result = tlgKeywordOn(&dword_1800281A0, 0, 9);
              if ( (_BYTE)result )
              {
                tlgCreate2Binary(v1472, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
                v418 = a6;
                v1474 = 8;
                v1473 = &v418;
                v1475 = &v297;
                v297 = v37;
                v1476 = 4;
                tlgCreate1Sz_wchar_t(v1477, ImageFileName);
                tlgCreate1Sz_wchar_t(v1478, *((_QWORD *)a7 + 2));
                v419 = *((_QWORD *)a7 + 9);
                v1479 = &v419;
                v1480 = 8;
                v134 = (_QWORD *)*((_QWORD *)a7 + 4);
                v420 = v134;
                v1481 = &v420;
                v1482 = 8;
                if ( v134 )
                  v135 = *v134;
                else
                  v135 = 0;
                v421 = v135;
                v1483 = &v421;
                v1484 = 8;
                v422 = *((_QWORD *)a7 + 3);
                v1486 = 8;
                v1485 = &v422;
                result = tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, word_180023C8A, 0, 0, 12, v1471);
              }
            }
            if ( *((_QWORD *)a7 + 5) )
            {
              result = (unsigned int)dword_1800281A0;
              if ( (unsigned int)dword_1800281A0 > 5 )
              {
                result = tlgKeywordOn(&dword_1800281A0, 0, v36);
                if ( (_BYTE)result )
                {
                  v423 = *((_QWORD *)a7 + 5);
                  v973 = &v423;
                  v974 = 8;
                  v424 = *((_QWORD *)a7 + 8);
                  v975 = &v424;
                  v976 = 8;
                  v425 = a7[14];
                  v977 = &v425;
                  v978 = 8;
                  v426 = *((_QWORD *)a7 + 6);
                  v979 = &v426;
                  v980 = 8;
                  return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800227C9, 0, 0, 6, v972);
                }
              }
            }
            break;
        }
        return result;
    }
    return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
  }
  if ( (_DWORD)v11 == 17 )
  {
    result = (unsigned int)dword_1800281A0;
    if ( a8 < 0 )
    {
      if ( a8 == -2147023899 )
      {
        if ( (unsigned int)dword_1800281A0 > 5 )
        {
          v111 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v112 = qword_1800283B0[3 * v11 + 2];
          v762 = v765;
          v765[0] = v111;
          v763 = 2;
          v764 = v112;
          v765[1] = 0;
          tlgCreate1Sz_wchar_t(v766, a4);
          tlgCreate1Sz_wchar_t(v767, v9);
          v251 = v37;
          v768 = &v251;
          v769 = 4;
          tlgCreate1Sz_wchar_t(v770, ImageFileName);
          v252 = a7[4];
          v771 = &v252;
          v772 = 4;
          v155 = *((_BYTE *)a7 + 22);
          v773 = &v155;
          v774 = 1;
          v156 = *((_BYTE *)a7 + 21);
          v775 = &v156;
          v776 = 1;
          v157 = *((_BYTE *)a7 + 20);
          v777 = &v157;
          v778 = 1;
          v408 = *((_QWORD *)a7 + 3);
          v779 = &v408;
          v781 = &v253;
          v780 = 8;
          v253 = -2147023899;
          v782 = 4;
          tlgCreate1Sz_wchar_t(v783, *((_QWORD *)a7 + 1));
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180022ADB, 0, 0, 15, v761);
        }
      }
      else if ( (unsigned int)dword_1800281A0 > 2 )
      {
        v113 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v114 = qword_1800283B0[3 * v11 + 2];
        v785 = v788;
        v788[0] = v113;
        v786 = 2;
        v787 = v114;
        v788[1] = 0;
        tlgCreate1Sz_wchar_t(v789, a4);
        tlgCreate1Sz_wchar_t(v790, v9);
        v254 = v37;
        v791 = &v254;
        v792 = 4;
        tlgCreate1Sz_wchar_t(v793, ImageFileName);
        v255 = a7[4];
        v794 = &v255;
        v795 = 4;
        v158 = *((_BYTE *)a7 + 22);
        v796 = &v158;
        v797 = 1;
        v159 = *((_BYTE *)a7 + 21);
        v798 = &v159;
        v799 = 1;
        v160 = *((_BYTE *)a7 + 20);
        v800 = &v160;
        v801 = 1;
        v409 = *((_QWORD *)a7 + 3);
        v802 = &v409;
        v804 = &v256;
        v803 = 8;
        v256 = a8;
        v805 = 4;
        tlgCreate1Sz_wchar_t(v806, *((_QWORD *)a7 + 1));
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &word_180022C46, 0, 0, 15, v784);
      }
    }
    else if ( (unsigned int)dword_1800281A0 > 5 )
    {
      v109 = LOWORD(qword_1800283B0[3 * v11 + 1]);
      v110 = qword_1800283B0[3 * v11 + 2];
      v745 = v748;
      v748[0] = v109;
      v746 = 2;
      v747 = v110;
      v748[1] = 0;
      tlgCreate1Sz_wchar_t(v749, a4);
      tlgCreate1Sz_wchar_t(v750, v9);
      v250 = a7[4];
      v751 = &v250;
      v752 = 4;
      v152 = *((_BYTE *)a7 + 22);
      v753 = &v152;
      v754 = 1;
      v153 = *((_BYTE *)a7 + 21);
      v755 = &v153;
      v756 = 1;
      v154 = *((_BYTE *)a7 + 20);
      v757 = &v154;
      v758 = 1;
      v407 = *((_QWORD *)a7 + 3);
      v759 = &v407;
      v760 = 8;
      return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800226D9, 0, 0, 11, v744);
    }
    return result;
  }
  if ( (unsigned int)v11 > 9 )
  {
    switch ( (_DWORD)v11 )
    {
      case 0xA:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v107 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v108 = qword_1800283B0[3 * v11 + 2];
            v1530 = v1533;
            v1533[0] = v107;
            v1531 = 2;
            v1532 = v108;
            v1533[1] = 0;
            tlgCreate1Sz_wchar_t(v1534, v168);
            tlgCreate1Sz_wchar_t(v1535, a4);
            tlgCreate1Sz_wchar_t(v1536, v9);
            v248 = v37;
            v1537 = &v248;
            v1538 = 4;
            tlgCreate1Sz_wchar_t(v1539, ImageFileName);
            v249 = a8;
            v1540 = &v249;
            v1541 = 4;
            tlgCreate1Sz_wchar_t(v1542, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180021B35, 0, 0, 11, v1529);
          }
        }
        else if ( dword_1800281A0 )
        {
          v105 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v106 = qword_1800283B0[3 * v11 + 2];
          v1562 = v1565;
          v1565[0] = v105;
          v1563 = 2;
          v1564 = v106;
          v1565[1] = 0;
          tlgCreate1Sz_wchar_t(v1566, v168);
          tlgCreate1Sz_wchar_t(v1567, a4);
          tlgCreate1Sz_wchar_t(v1568, v9);
          v247 = v37;
          v1569 = &v247;
          v1570 = 4;
          tlgCreate1Sz_wchar_t(v1571, ImageFileName);
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &word_18002488E, 0, 0, 9, v1561);
        }
        break;
      case 0xB:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v103 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v104 = qword_1800283B0[3 * v11 + 2];
            v1434 = v1437;
            v1437[0] = v103;
            v1435 = 2;
            v1436 = v104;
            v1437[1] = 0;
            tlgCreate1Sz_wchar_t(v1438, v168);
            v404 = v10;
            v1439 = &v404;
            v1440 = 8;
            tlgCreate1Sz_wchar_t(v1441, a4);
            tlgCreate1Sz_wchar_t(v1442, v9);
            v405 = (unsigned int)a7[10];
            v1444 = 8;
            v1443 = &v405;
            v406 = a7[6];
            v1445 = &v406;
            v1446 = 8;
            tlgCreate1Sz_wchar_t(v1447, a4);
            tlgCreate1Sz_wchar_t(v1448, v9);
            v246 = v37;
            v1449 = &v246;
            v1450 = 4;
            tlgCreate1Sz_wchar_t(v1451, ImageFileName);
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &unk_1800249B8, 0, 0, 14, v1433);
          }
        }
        else if ( dword_1800281A0 )
        {
          v101 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v102 = qword_1800283B0[3 * v11 + 2];
          v1000 = v1003;
          v1003[0] = v101;
          v1001 = 2;
          v1002 = v102;
          v1003[1] = 0;
          tlgCreate1Sz_wchar_t(v1004, v168);
          v399 = v10;
          v1005 = &v399;
          v1006 = 8;
          tlgCreate1Sz_wchar_t(v1007, a4);
          tlgCreate1Sz_wchar_t(v1008, v9);
          v400 = (unsigned int)a7[10];
          v1010 = 8;
          v1009 = &v400;
          v401 = a7[6];
          v1011 = &v401;
          v1012 = 8;
          v402 = *((_QWORD *)a7 + 4);
          v1013 = &v402;
          v1014 = 8;
          v403 = *((_QWORD *)a7 + 2);
          v1015 = &v403;
          v1017 = &v245;
          v1016 = 8;
          v245 = v37;
          v1018 = 4;
          tlgCreate1Sz_wchar_t(v1019, ImageFileName);
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023DD1, 0, 0, 14, v999);
        }
        break;
      case 0xC:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v99 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v100 = qword_1800283B0[3 * v11 + 2];
            v1243 = v1246;
            v1246[0] = v99;
            v1244 = 2;
            v1245 = v100;
            v1246[1] = 0;
            tlgCreate1Sz_wchar_t(v1247, a4);
            tlgCreate1Sz_wchar_t(v1248, v9);
            v397 = *((_QWORD *)a7 + 3);
            v1250 = 8;
            v1249 = &v397;
            v398 = *((_QWORD *)a7 + 2);
            v1251 = &v398;
            v1253 = &v243;
            v1255 = &v244;
            v1252 = 8;
            v243 = a8;
            v1254 = 4;
            v244 = v37;
            v1256 = 4;
            tlgCreate1Sz_wchar_t(v1257, ImageFileName);
            tlgCreate1Sz_wchar_t(v1258, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &unk_1800245A8, 0, 0, 12, v1242);
          }
        }
        else if ( dword_1800281A0 )
        {
          v97 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v98 = qword_1800283B0[3 * v11 + 2];
          v1274 = v1277;
          v1277[0] = v97;
          v1275 = 2;
          v1276 = v98;
          v1277[1] = 0;
          tlgCreate1Sz_wchar_t(v1278, a4);
          tlgCreate1Sz_wchar_t(v1279, v9);
          v395 = *((_QWORD *)a7 + 3);
          v1281 = 8;
          v1280 = &v395;
          v396 = *((_QWORD *)a7 + 2);
          v1282 = &v396;
          v1284 = &v242;
          v1283 = 8;
          v242 = v37;
          v1285 = 4;
          tlgCreate1Sz_wchar_t(v1286, ImageFileName);
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180024BA3, 0, 0, 10, v1273);
        }
        break;
      case 0xD:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            result = tlgKeywordOn(&dword_1800281A0, 0, 9);
            if ( (_BYTE)result )
            {
              tlgCreate2Binary(v1544, qword_1800283B0[3 * v11 + 2], LOWORD(qword_1800283B0[3 * v11 + 1]));
              tlgCreate1Sz_wchar_t(v1545, a4);
              tlgCreate1Sz_wchar_t(v1546, v9);
              v238 = v37;
              v1547 = &v238;
              v1548 = 4;
              tlgCreate1Sz_wchar_t(v1549, ImageFileName);
              v394 = *((_QWORD *)a7 + 2);
              v1550 = &v394;
              v1551 = 8;
              v239 = a7[6];
              v1552 = &v239;
              v1553 = 4;
              v240 = a7[7];
              v1554 = &v240;
              v1555 = 4;
              v151 = *((_BYTE *)a7 + 32);
              v1556 = &v151;
              v1558 = &v241;
              v1557 = 1;
              v241 = a8;
              v1559 = 4;
              tlgCreate1Sz_wchar_t(v1560, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_180021CCC, 0, 0, 14, v1543);
            }
          }
        }
        else if ( (unsigned int)dword_1800281A0 > 4 )
        {
          v95 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v96 = qword_1800283B0[3 * v11 + 2];
          v898 = v901;
          v901[0] = v95;
          v899 = 2;
          v900 = v96;
          v901[1] = 0;
          tlgCreate1Sz_wchar_t(v902, a4);
          tlgCreate1Sz_wchar_t(v903, v9);
          v393 = *((_QWORD *)a7 + 2);
          v904 = &v393;
          v905 = 8;
          v236 = a7[6];
          v906 = &v236;
          v907 = 4;
          v237 = a7[7];
          v908 = &v237;
          v909 = 4;
          v150 = *((_BYTE *)a7 + 32);
          v910 = &v150;
          v911 = 1;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &byte_1800223E7, 0, 0, 10, v897);
        }
        break;
      case 0xE:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v93 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v94 = qword_1800283B0[3 * v11 + 2];
            v1383 = v1386;
            v1386[0] = v93;
            v1384 = 2;
            v1385 = v94;
            v1386[1] = 0;
            tlgCreate1Sz_wchar_t(v1387, a4);
            tlgCreate1Sz_wchar_t(v1388, v9);
            v234 = v37;
            v1389 = &v234;
            v1390 = 4;
            tlgCreate1Sz_wchar_t(v1391, ImageFileName);
            v392 = *((_QWORD *)a7 + 2);
            v1392 = &v392;
            v1394 = &v235;
            v1393 = 8;
            v235 = a8;
            v1395 = 4;
            tlgCreate1Sz_wchar_t(v1396, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &unk_180023BF8, 0, 0, 11, v1382);
          }
        }
        else if ( (unsigned int)dword_1800281A0 > 4 )
        {
          v91 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v92 = qword_1800283B0[3 * v11 + 2];
          v1321 = v1324;
          v1324[0] = v91;
          v1322 = 2;
          v1323 = v92;
          v1324[1] = 0;
          tlgCreate1Sz_wchar_t(v1325, a4);
          tlgCreate1Sz_wchar_t(v1326, v9);
          v391 = *((_QWORD *)a7 + 2);
          v1327 = &v391;
          v1328 = 8;
          v233 = a7[6];
          v1329 = &v233;
          v1330 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180022FBB, 0, 0, 8, v1320);
        }
        break;
      case 0xF:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( (unsigned int)dword_1800281A0 <= 2 )
            return result;
          v89 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v90 = qword_1800283B0[3 * v11 + 2];
          v1350 = v1353;
          v1353[0] = v89;
          v1351 = 2;
          v1352 = v90;
          v1353[1] = 0;
          tlgCreate1Sz_wchar_t(v1354, a4);
          tlgCreate1Sz_wchar_t(v1355, v9);
          v229 = v37;
          v1356 = &v229;
          v1357 = 4;
          tlgCreate1Sz_wchar_t(v1358, ImageFileName);
          v230 = a7[8];
          v1359 = &v230;
          v1360 = 4;
          v231 = a7[4];
          v1361 = &v231;
          v1362 = 4;
          tlgCreate1Sz_wchar_t(v1363, *((_QWORD *)a7 + 3));
          v232 = a8;
          v1364 = &v232;
          v1365 = 4;
          tlgCreate1Sz_wchar_t(v1366, *((_QWORD *)a7 + 1));
          v46 = &v1349;
          v47 = (__int16 *)byte_180023651;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
        }
        if ( (unsigned int)dword_1800281A0 > 5 )
        {
          v87 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v88 = qword_1800283B0[3 * v11 + 2];
          v1422 = v1425;
          v1425[0] = v87;
          v1423 = 2;
          v1424 = v88;
          v1425[1] = 0;
          tlgCreate1Sz_wchar_t(v1426, a4);
          tlgCreate1Sz_wchar_t(v1427, v9);
          v227 = a7[8];
          v1428 = &v227;
          v1429 = 4;
          v228 = a7[4];
          v1430 = &v228;
          v1431 = 4;
          tlgCreate1Sz_wchar_t(v1432, *((_QWORD *)a7 + 3));
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_180021AAC, 0, 0, 9, v1421);
        }
        break;
      default:
        result = (unsigned int)dword_1800281A0;
        if ( a8 < 0 )
        {
          if ( a8 == -2147023899 )
          {
            if ( (unsigned int)dword_1800281A0 > 5 )
            {
              v83 = LOWORD(qword_1800283B0[3 * v11 + 1]);
              v84 = qword_1800283B0[3 * v11 + 2];
              v1209 = v1212;
              v1212[0] = v83;
              v1210 = 2;
              v1211 = v84;
              v1212[1] = 0;
              tlgCreate1Sz_wchar_t(v1213, a4);
              tlgCreate1Sz_wchar_t(v1214, v9);
              v219 = v37;
              v1215 = &v219;
              v1216 = 4;
              tlgCreate1Sz_wchar_t(v1217, ImageFileName);
              v220 = a7[4];
              v1218 = &v220;
              v1219 = 4;
              v221 = *((unsigned __int8 *)a7 + 20);
              v1220 = &v221;
              v1222 = &v222;
              v1221 = 4;
              v222 = -2147023899;
              v1223 = 4;
              tlgCreate1Sz_wchar_t(v1224, *((_QWORD *)a7 + 1));
              return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800232DB, 0, 0, 12, v1208);
            }
          }
          else if ( (unsigned int)dword_1800281A0 > 2 )
          {
            v85 = LOWORD(qword_1800283B0[3 * v11 + 1]);
            v86 = qword_1800283B0[3 * v11 + 2];
            v1226 = v1229;
            v1229[0] = v85;
            v1227 = 2;
            v1228 = v86;
            v1229[1] = 0;
            tlgCreate1Sz_wchar_t(v1230, a4);
            tlgCreate1Sz_wchar_t(v1231, v9);
            v223 = v37;
            v1232 = &v223;
            v1233 = 4;
            tlgCreate1Sz_wchar_t(v1234, ImageFileName);
            v224 = a7[4];
            v1235 = &v224;
            v1236 = 4;
            v225 = *((unsigned __int8 *)a7 + 20);
            v1237 = &v225;
            v1239 = &v226;
            v1238 = 4;
            v226 = a8;
            v1240 = 4;
            tlgCreate1Sz_wchar_t(v1241, *((_QWORD *)a7 + 1));
            return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &word_180021F5E, 0, 0, 12, v1225);
          }
        }
        else if ( (unsigned int)dword_1800281A0 > 5 )
        {
          v81 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v82 = qword_1800283B0[3 * v11 + 2];
          v1260 = v1263;
          v1263[0] = v81;
          v1261 = 2;
          v1262 = v82;
          v1263[1] = 0;
          tlgCreate1Sz_wchar_t(v1264, a4);
          tlgCreate1Sz_wchar_t(v1265, v9);
          v216 = v37;
          v1266 = &v216;
          v1267 = 4;
          tlgCreate1Sz_wchar_t(v1268, ImageFileName);
          v217 = a7[4];
          v1269 = &v217;
          v1270 = 4;
          v218 = *((unsigned __int8 *)a7 + 20);
          v1271 = &v218;
          v1272 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180021C41, 0, 0, 10, v1259);
        }
        break;
    }
    return result;
  }
  switch ( (_DWORD)v11 )
  {
    case 9:
      result = (unsigned int)dword_1800281A0;
      if ( a8 < 0 )
      {
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v79 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v80 = qword_1800283B0[3 * v11 + 2];
        v1332 = v1335;
        v1335[0] = v79;
        v1333 = 2;
        v1334 = v80;
        v1335[1] = 0;
        tlgCreate1Sz_wchar_t(v1336, v168);
        tlgCreate1Sz_wchar_t(v1337, a4);
        tlgCreate1Sz_wchar_t(v1338, v9);
        v214 = v37;
        v1339 = &v214;
        v1340 = 4;
        tlgCreate1Sz_wchar_t(v1341, ImageFileName);
        v390 = v10;
        v1342 = &v390;
        v1343 = 8;
        v149 = *((_BYTE *)a7 + 20);
        v1344 = &v149;
        v1346 = &v215;
        v1345 = 1;
        v215 = a8;
        v1347 = 4;
        tlgCreate1Sz_wchar_t(v1348, *((_QWORD *)a7 + 1));
        v46 = &v1331;
        v47 = (__int16 *)&unk_180024908;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( dword_1800281A0 )
      {
        v77 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v78 = qword_1800283B0[3 * v11 + 2];
        v1368 = v1371;
        v1369 = 2;
        v1370 = v78;
        v1371[0] = v77;
        v1371[1] = 0;
        tlgCreate1Sz_wchar_t(v1372, v168);
        tlgCreate1Sz_wchar_t(v1373, a4);
        tlgCreate1Sz_wchar_t(v1374, v9);
        v213 = v37;
        v1375 = &v213;
        v1376 = 4;
        tlgCreate1Sz_wchar_t(v1377, ImageFileName);
        v389 = v10;
        v1378 = &v389;
        v1379 = 8;
        v148 = *((_BYTE *)a7 + 20);
        v1380 = &v148;
        v1381 = 1;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &byte_180022197, 0, 0, 11, v1367);
      }
      return result;
    case 0:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v73 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v74 = qword_1800283B0[3 * v11 + 2];
        v1079 = v1082;
        v1082[0] = v73;
        v1080 = 2;
        v1081 = v74;
        v1082[1] = 0;
        tlgCreate1Sz_wchar_t(v1083, a4);
        tlgCreate1Sz_wchar_t(v1084, v9);
        v208 = v37;
        v1085 = &v208;
        v1086 = 4;
        tlgCreate1Sz_wchar_t(v1087, ImageFileName);
        v385 = *((_QWORD *)a7 + 5);
        v1088 = &v385;
        v1089 = 8;
        v386 = *((_QWORD *)a7 + 2);
        v1090 = &v386;
        v1091 = 8;
        v209 = a7[6];
        v1092 = &v209;
        v1094 = &v210;
        v1093 = 4;
        v210 = a8;
        v1095 = 4;
        tlgCreate1Sz_wchar_t(v1096, *((_QWORD *)a7 + 1));
        v46 = &v1078;
        v47 = (__int16 *)&unk_180022BA8;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[6] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 4 )
        {
          v75 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v76 = qword_1800283B0[3 * v11 + 2];
          v883 = v886;
          v886[0] = v75;
          v884 = 2;
          v885 = v76;
          v886[1] = 0;
          tlgCreate1Sz_wchar_t(v887, a4);
          tlgCreate1Sz_wchar_t(v888, v9);
          v387 = *((_QWORD *)a7 + 5);
          v889 = &v387;
          v890 = 8;
          v388 = *((_QWORD *)a7 + 2);
          v891 = &v388;
          v892 = 8;
          v211 = a7[6];
          v893 = &v211;
          v895 = &v212;
          v894 = 4;
          v212 = a8;
          v896 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180024285, 0, 0, 10, v882);
        }
      }
      return result;
    case 1:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 2 )
        {
          v71 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v72 = qword_1800283B0[3 * v11 + 2];
          v982 = v985;
          v985[0] = v71;
          v983 = 2;
          v984 = v72;
          v985[1] = 0;
          tlgCreate1Sz_wchar_t(v986, a4);
          tlgCreate1Sz_wchar_t(v987, v9);
          v205 = v37;
          v988 = &v205;
          v989 = 4;
          tlgCreate1Sz_wchar_t(v990, ImageFileName);
          v383 = *((_QWORD *)a7 + 5);
          v991 = &v383;
          v992 = 8;
          v384 = *((_QWORD *)a7 + 2);
          v993 = &v384;
          v994 = 8;
          v206 = a7[8];
          v995 = &v206;
          v997 = &v207;
          v996 = 4;
          v207 = a8;
          v998 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_18002439C, 0, 0, 12, v981);
        }
      }
      return result;
    case 2:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v67 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v68 = qword_1800283B0[3 * v11 + 2];
        v1060 = v1063;
        v1063[0] = v67;
        v1061 = 2;
        v1062 = v68;
        v1063[1] = 0;
        tlgCreate1Sz_wchar_t(v1064, a4);
        tlgCreate1Sz_wchar_t(v1065, v9);
        v200 = v37;
        v1066 = &v200;
        v1067 = 4;
        tlgCreate1Sz_wchar_t(v1068, ImageFileName);
        v379 = *((_QWORD *)a7 + 5);
        v1069 = &v379;
        v1070 = 8;
        v380 = *((_QWORD *)a7 + 2);
        v1071 = &v380;
        v1072 = 8;
        v201 = a7[6];
        v1073 = &v201;
        v1075 = &v202;
        v1074 = 4;
        v202 = a8;
        v1076 = 4;
        tlgCreate1Sz_wchar_t(v1077, *((_QWORD *)a7 + 1));
        v46 = &v1059;
        v47 = (__int16 *)&dword_180024174;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[6] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 2 )
        {
          v69 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v70 = qword_1800283B0[3 * v11 + 2];
          v868 = v871;
          v871[0] = v69;
          v869 = 2;
          v870 = v70;
          v871[1] = 0;
          tlgCreate1Sz_wchar_t(v872, a4);
          tlgCreate1Sz_wchar_t(v873, v9);
          v381 = *((_QWORD *)a7 + 5);
          v874 = &v381;
          v875 = 8;
          v382 = *((_QWORD *)a7 + 2);
          v876 = &v382;
          v877 = 8;
          v203 = a7[6];
          v878 = &v203;
          v880 = &v204;
          v879 = 4;
          v204 = a8;
          v881 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023129, 0, 0, 10, v867);
        }
      }
      return result;
    case 3:
      if ( a8 >= 0 )
        return result;
      result = (unsigned int)dword_1800281A0;
      if ( (unsigned int)dword_1800281A0 <= 2 )
        return result;
      v65 = LOWORD(qword_1800283B0[3 * v11 + 1]);
      v66 = qword_1800283B0[3 * v11 + 2];
      v1098 = v1101;
      v1101[0] = v65;
      v1099 = 2;
      v1100 = v66;
      v1101[1] = 0;
      tlgCreate1Sz_wchar_t(v1102, a4);
      tlgCreate1Sz_wchar_t(v1103, v9);
      v198 = v37;
      v1104 = &v198;
      v1105 = 4;
      tlgCreate1Sz_wchar_t(v1106, ImageFileName);
      v376 = *((_QWORD *)a7 + 5);
      v1107 = &v376;
      v1108 = 8;
      v377 = *((_QWORD *)a7 + 3);
      v1109 = &v377;
      v1110 = 8;
      v378 = *((_QWORD *)a7 + 2);
      v1111 = &v378;
      v1113 = &v199;
      v1112 = 8;
      v199 = a8;
      v1114 = 4;
      tlgCreate1Sz_wchar_t(v1115, *((_QWORD *)a7 + 1));
      v46 = &v1097;
      v47 = (__int16 *)&dword_1800222A4;
      return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
    case 4:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v61 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v62 = qword_1800283B0[3 * v11 + 2];
        v1174 = v1177;
        v1177[0] = v61;
        v1175 = 2;
        v1176 = v62;
        v1177[1] = 0;
        tlgCreate1Sz_wchar_t(v1178, a4);
        tlgCreate1Sz_wchar_t(v1179, v9);
        v192 = v37;
        v1180 = &v192;
        v1181 = 4;
        tlgCreate1Sz_wchar_t(v1182, ImageFileName);
        v374 = a7[4];
        v1183 = &v374;
        v1184 = 8;
        v193 = a7[5];
        v1185 = &v193;
        v1186 = 4;
        v194 = a7[6];
        v1187 = &v194;
        v1189 = &v195;
        v1188 = 4;
        v195 = a8;
        v1190 = 4;
        tlgCreate1Sz_wchar_t(v1191, *((_QWORD *)a7 + 1));
        v46 = &v1173;
        v47 = (__int16 *)&unk_1800238E0;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[5] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 4 )
        {
          v63 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v64 = qword_1800283B0[3 * v11 + 2];
          v1047 = v1050;
          v1050[0] = v63;
          v1048 = 2;
          v1049 = v64;
          v1050[1] = 0;
          tlgCreate1Sz_wchar_t(v1051, a4);
          tlgCreate1Sz_wchar_t(v1052, v9);
          v375 = a7[4];
          v1053 = &v375;
          v1054 = 8;
          v196 = a7[5];
          v1055 = &v196;
          v1057 = &v197;
          v1056 = 4;
          v197 = a8;
          v1058 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_1800233FB, 0, 0, 9, v1046);
        }
      }
      break;
    case 5:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v57 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v58 = qword_1800283B0[3 * v11 + 2];
        v1155 = v1158;
        v1158[0] = v57;
        v1156 = 2;
        v1157 = v58;
        v1158[1] = 0;
        tlgCreate1Sz_wchar_t(v1159, a4);
        tlgCreate1Sz_wchar_t(v1160, v9);
        v187 = v37;
        v1161 = &v187;
        v1162 = 4;
        tlgCreate1Sz_wchar_t(v1163, ImageFileName);
        v370 = *((_QWORD *)a7 + 5);
        v1164 = &v370;
        v1165 = 8;
        v371 = *((_QWORD *)a7 + 2);
        v1166 = &v371;
        v1167 = 8;
        v188 = a7[8];
        v1168 = &v188;
        v1170 = &v189;
        v1169 = 4;
        v189 = a8;
        v1171 = 4;
        tlgCreate1Sz_wchar_t(v1172, *((_QWORD *)a7 + 1));
        v46 = &v1154;
        v47 = word_18002284A;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[5] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 2 )
        {
          v59 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v60 = qword_1800283B0[3 * v11 + 2];
          v853 = v856;
          v856[0] = v59;
          v854 = 2;
          v855 = v60;
          v856[1] = 0;
          tlgCreate1Sz_wchar_t(v857, a4);
          tlgCreate1Sz_wchar_t(v858, v9);
          v372 = *((_QWORD *)a7 + 5);
          v859 = &v372;
          v860 = 8;
          v373 = *((_QWORD *)a7 + 2);
          v861 = &v373;
          v862 = 8;
          v190 = a7[8];
          v863 = &v190;
          v865 = &v191;
          v864 = 4;
          v191 = a8;
          v866 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180023379, 0, 0, 10, v852);
        }
      }
      break;
    case 6:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v53 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v54 = qword_1800283B0[3 * v11 + 2];
        v1136 = v1139;
        v1139[0] = v53;
        v1137 = 2;
        v1138 = v54;
        v1139[1] = 0;
        tlgCreate1Sz_wchar_t(v1140, a4);
        tlgCreate1Sz_wchar_t(v1141, v9);
        v182 = v37;
        v1142 = &v182;
        v1143 = 4;
        tlgCreate1Sz_wchar_t(v1144, ImageFileName);
        v366 = *((_QWORD *)a7 + 5);
        v1145 = &v366;
        v1146 = 8;
        v367 = *((_QWORD *)a7 + 2);
        v1147 = &v367;
        v1148 = 8;
        v183 = a7[8];
        v1149 = &v183;
        v1151 = &v184;
        v1150 = 4;
        v184 = a8;
        v1152 = 4;
        tlgCreate1Sz_wchar_t(v1153, *((_QWORD *)a7 + 1));
        v46 = &v1135;
        v47 = &word_18002258E;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[5] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 2 )
        {
          v55 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v56 = qword_1800283B0[3 * v11 + 2];
          v823 = v826;
          v826[0] = v55;
          v824 = 2;
          v825 = v56;
          v826[1] = 0;
          tlgCreate1Sz_wchar_t(v827, a4);
          tlgCreate1Sz_wchar_t(v828, v9);
          v368 = *((_QWORD *)a7 + 5);
          v829 = &v368;
          v830 = 8;
          v369 = *((_QWORD *)a7 + 2);
          v831 = &v369;
          v832 = 8;
          v185 = a7[8];
          v833 = &v185;
          v835 = &v186;
          v834 = 4;
          v186 = a8;
          v836 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, word_180021D92, 0, 0, 10, v822);
        }
      }
      break;
    case 7:
      if ( a8 < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 <= 2 )
          return result;
        v44 = LOWORD(qword_1800283B0[3 * v11 + 1]);
        v45 = qword_1800283B0[3 * v11 + 2];
        v1117 = v1120;
        v1120[0] = v44;
        v1118 = 2;
        v1119 = v45;
        v1120[1] = 0;
        tlgCreate1Sz_wchar_t(v1121, a4);
        tlgCreate1Sz_wchar_t(v1122, v9);
        v177 = v37;
        v1123 = &v177;
        v1124 = 4;
        tlgCreate1Sz_wchar_t(v1125, ImageFileName);
        v362 = *((_QWORD *)a7 + 5);
        v1126 = &v362;
        v1127 = 8;
        v363 = *((_QWORD *)a7 + 2);
        v1128 = &v363;
        v1129 = 8;
        v178 = a7[8];
        v1130 = &v178;
        v1132 = &v179;
        v1131 = 4;
        v179 = a8;
        v1133 = 4;
        tlgCreate1Sz_wchar_t(v1134, *((_QWORD *)a7 + 1));
        v46 = &v1116;
        v47 = (__int16 *)byte_1800244A9;
        return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, v47, 0, 0, 13, v46);
      }
      if ( a7[5] < 0 )
      {
        result = (unsigned int)dword_1800281A0;
        if ( (unsigned int)dword_1800281A0 > 2 )
        {
          v51 = LOWORD(qword_1800283B0[3 * v11 + 1]);
          v52 = qword_1800283B0[3 * v11 + 2];
          v838 = v841;
          v841[0] = v51;
          v839 = 2;
          v840 = v52;
          v841[1] = 0;
          tlgCreate1Sz_wchar_t(v842, a4);
          tlgCreate1Sz_wchar_t(v843, v9);
          v364 = *((_QWORD *)a7 + 5);
          v844 = &v364;
          v845 = 8;
          v365 = *((_QWORD *)a7 + 2);
          v846 = &v365;
          v847 = 8;
          v180 = a7[8];
          v848 = &v180;
          v850 = &v181;
          v849 = 4;
          v181 = a8;
          v851 = 4;
          return tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, word_180021BC2, 0, 0, 10, v837);
        }
      }
      break;
    default:
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x180011e18  push    rbp
0x180011e1a  push    rbx
0x180011e1b  push    rsi
0x180011e1c  push    rdi
0x180011e1d  push    r12
0x180011e1f  push    r13
0x180011e21  push    r14
0x180011e23  push    r15
0x180011e25  lea     rbp, [rsp-3ED8h]
0x180011e2d  mov     eax, 3FD8h
0x180011e32  call    _alloca_probe
0x180011e37  sub     rsp, rax
0x180011e3a  mov     rax, cs:__security_cookie
0x180011e41  xor     rax, rsp
0x180011e44  mov     [rbp+3F10h+var_50], rax
0x180011e4b  mov     rbx, [rbp+3F10h+arg_30]
0x180011e52  mov     r14, rdx
0x180011e55  mov     r12, [rbp+3F10h+arg_20]
0x180011e5c  xor     r13d, r13d
0x180011e5f  mov     [rsp+4010h+var_3FA8], r8
0x180011e64  xor     edx, edx; Val
0x180011e66  movzx   esi, cx
0x180011e69  mov     r8d, 404h; Size
0x180011e6f  lea     rcx, [rbp+3F10h+var_38B0]; void *
0x180011e76  mov     [rsp+4010h+UnbiasedTime], r13
0x180011e7b  mov     qword ptr [rsp+4010h+FileSize], r13
0x180011e80  mov     r15, r9
0x180011e83  call    memset_0
0x180011e88  cmp     cs:byte_180028930, r13b
0x180011e8f  jnz     short loc_180011E9E
0x180011e91  cmp     cs:byte_180028B80, r13b
0x180011e98  jz      loc_1800176FF
0x180011e9e  mov     rax, gs:60h
0x180011ea7  mov     rcx, [rax+18h]
0x180011eab  cmp     [rcx+48h], r13b
0x180011eaf  jnz     loc_1800176FF
0x180011eb5  lea     rcx, [rsp+4010h+UnbiasedTime]; UnbiasedTime
0x180011eba  mov     [rsp+4010h+var_3FB8], r13d
0x180011ebf  mov     [rsp+4010h+var_3FB4], r13d
0x180011ec4  mov     [rsp+4010h+var_3FB0], r13d
0x180011ec9  call    cs:__imp_QueryUnbiasedInterruptTime
0x180011ecf  mov     rcx, [rsp+4010h+UnbiasedTime]
0x180011ed4  mov     r8, rbx
0x180011ed7  mov     edi, [rbp+3F10h+arg_38]
0x180011edd  mov     rax, rcx
0x180011ee0  sub     rax, [rbp+3F10h+arg_28]
0x180011ee7  mov     r9d, edi
0x180011eea  mov     [rbp+3F10h+var_3D28], rax
0x180011ef1  mov     eax, 0Fh
0x180011ef6  cmp     si, ax
0x180011ef9  setz    dl
0x180011efc  call    TlmiUpdateFirstRunExpStatus
0x180011f01  mov     ecx, 8
0x180011f06  mov     r9d, 0FFFDh
0x180011f0c  lea     r10d, [rcx+3]
0x180011f10  lea     eax, [rcx-4]
0x180011f13  lea     edx, [rcx+1]
0x180011f16  lea     r8d, [rcx+5]
0x180011f1a  lea     r11d, [rcx+0Eh]
0x180011f1e  cmp     si, r10w
0x180011f22  jnz     short loc_180011F33
0x180011f24  call    TlmiInitializeRunawayHydrationDetection
0x180011f29  call    TlmiInitializeHydrationPerformanceTracking
0x180011f2e  jmp     loc_180011FC0
0x180011f33  cmp     si, dx
0x180011f36  jz      short loc_180011F71
0x180011f38  mov     edx, 0Fh
0x180011f3d  cmp     si, dx
0x180011f40  jnz     short loc_180011F52
0x180011f42  mov     eax, [rbx+10h]
0x180011f45  mov     r13d, [rbx+20h]
0x180011f49  mov     [rsp+4010h+var_3FB8], eax
0x180011f4d  jmp     loc_180011FFA
0x180011f52  mov     edx, 11h
0x180011f57  cmp     si, dx
0x180011f5a  jz      short loc_180011F71
0x180011f5c  cmp     esi, 10h
0x180011f5f  jz      short loc_180011F71
0x180011f61  mov     edx, 14h
0x180011f66  cmp     si, dx
0x180011f69  jz      short loc_180011F71
0x180011f6b  cmp     si, r11w
0x180011f6f  jnz     short loc_180011F7A
0x180011f71  movsxd  r13, dword ptr [rbx+10h]
0x180011f75  jmp     loc_180011FFA
0x180011f7a  cmp     esi, 15h
0x180011f7d  jnz     short loc_180011F8D
0x180011f7f  mov     rcx, rbx
0x180011f82  call    TlmiLogHydrationAborted
0x180011f87  movsxd  r13, dword ptr [rbx+14h]
0x180011f8b  jmp     short loc_180011FFA
0x180011f8d  cmp     esi, 1Ch
0x180011f90  jnz     short loc_180011F9B
0x180011f92  mov     eax, [rbx+10h]
0x180011f95  mov     [rsp+4010h+var_3FB8], eax
0x180011f99  jmp     short loc_180011FFA
0x180011f9b  test    r9w, si
0x180011f9f  jz      short loc_180011FEF
0x180011fa1  cmp     si, ax
0x180011fa4  jnz     short loc_180011FB6
0x180011fa6  mov     eax, [rbx+18h]
0x180011fa9  movsxd  r13, dword ptr [rbx+10h]
0x180011fad  mov     [rsp+4010h+var_3FB8], eax
0x180011fb1  mov     eax, [rbx+14h]
0x180011fb4  jmp     short loc_180011FF6
0x180011fb6  mov     eax, 0Eh
0x180011fbb  cmp     si, ax
0x180011fbe  jnz     short loc_180011FC6
0x180011fc0  movsxd  r13, dword ptr [rbx+18h]
0x180011fc4  jmp     short loc_180011FFA
0x180011fc6  cmp     si, r8w
0x180011fca  jnz     short loc_180011FD2
0x180011fcc  movsxd  r13, dword ptr [rbx+1Ch]
0x180011fd0  jmp     short loc_180011FFA
0x180011fd2  cmp     si, cx
0x180011fd5  jnb     short loc_180011FFA
0x180011fd7  mov     eax, [rbx]
0x180011fd9  mov     r13, [rbx+10h]
0x180011fdd  mov     [rsp+4010h+var_3FB4], eax
0x180011fe1  mov     rax, [rbx+18h]
0x180011fe5  mov     qword ptr [rsp+4010h+FileSize], rax
0x180011fea  mov     eax, [rbx+20h]
0x180011fed  jmp     short loc_180011FF6
0x180011fef  mov     r13, [rbx+10h]
0x180011ff3  mov     eax, [rbx+18h]
0x180011ff6  mov     [rsp+4010h+var_3FB0], eax
0x180011ffa  test    r15, r15
0x180011ffd  jz      short loc_180012008
0x180011fff  test    r12, r12
0x180012002  jnz     loc_180012110
0x180012008  lea     rax, [r14-1]
0x18001200c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012010  ja      loc_1800120BC
0x180012016  cmp     edi, 80070006h
0x18001201c  jz      loc_1800120BC
0x180012022  xor     r12d, r12d
0x180012025  cmp     cs:byte_180028930, r12b
0x18001202c  jz      loc_1800120BC
0x180012032  mov     rcx, r14
0x180012035  call    CfReferenceProtectedHandle
0x18001203a  test    al, al
0x18001203c  jz      short loc_18001205D
0x18001203e  lea     ecx, [r12+1]
0x180012043  test    cl, r14b
0x180012046  jz      short loc_180012054
0x180012048  mov     rax, r14
0x18001204b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001204f  mov     r15, [rax]
0x180012052  jmp     short loc_180012057
0x180012054  mov     r15, r14
0x180012057  mov     [rsp+4010h+var_3FD0], cl
0x18001205b  jmp     short loc_180012065
0x18001205d  mov     [rsp+4010h+var_3FD0], r12b
0x180012062  mov     r15, r14
0x180012065  lea     rdx, [rsp+4010h+FileSize]; lpFileSize
0x18001206a  mov     rcx, r15; hFile
0x18001206d  call    cs:__imp_GetFileSizeEx
0x180012073  mov     r9d, 404h
0x180012079  mov     [rsp+4010h+var_3FF0], r12; __int64
0x18001207e  lea     r8, [rbp+3F10h+var_38B0]
0x180012085  mov     edx, 2
0x18001208a  mov     rcx, r15; hFile
0x18001208d  call    CfpGetSyncRootInfoByHandle
0x180012092  xor     edx, edx
0x180012094  lea     r12, [rbp+3F10h+var_36AC]
0x18001209b  test    eax, eax
0x18001209d  lea     r15, [rbp+3F10h+var_38AC]
0x1800120a4  cmovs   r12, rdx
0x1800120a8  cmovs   r15, rdx
0x1800120ac  cmp     [rsp+4010h+var_3FD0], dl
0x1800120b0  jz      short loc_180012110
0x1800120b2  mov     rcx, r14
0x1800120b5  call    CfpReleaseProtectedHandle
0x1800120ba  jmp     short loc_180012110
0x1800120bc  mov     rax, [rsp+4010h+var_3FA8]
0x1800120c1  xor     r14d, r14d
0x1800120c4  test    rax, rax
0x1800120c7  jz      short loc_180012101
0x1800120c9  mov     r9d, 404h
0x1800120cf  mov     [rsp+4010h+var_3FF0], r14
0x1800120d4  lea     r8, [rbp+3F10h+var_38B0]
0x1800120db  mov     rcx, rax
0x1800120de  lea     edx, [r14+2]
0x1800120e2  call    CfpGetSyncRootInfoByPath
0x1800120e7  test    eax, eax
0x1800120e9  lea     r15, [rbp+3F10h+var_38AC]
0x1800120f0  lea     r12, [rbp+3F10h+var_36AC]
0x1800120f7  cmovs   r15, r14
0x1800120fb  cmovs   r12, r14
0x1800120ff  jmp     short loc_180012110
0x180012101  lea     r15, SourceString
0x180012108  mov     qword ptr [rsp+4010h+FileSize], r14
0x18001210d  mov     r12, r15
0x180012110  call    TlmiIsInitialized
0x180012115  lea     r8, qword_1800283B0
0x18001211c  test    al, al
0x18001211e  jz      loc_180012A40
0x180012124  mov     rax, 346DC5D63886594Bh
0x18001212e  mul     [rbp+3F10h+var_3D28]
0x180012135  mov     eax, 0FFFDh
0x18001213a  mov     r14, rdx
0x18001213d  shr     r14, 0Bh
0x180012141  test    ax, si
0x180012144  jnz     short loc_18001218C
0x180012146  mov     eax, [rbx+18h]
0x180012149  test    eax, eax
0x18001214b  jle     short loc_180012155
0x18001214d  movzx   eax, ax
0x180012150  or      eax, 80070000h
0x180012155  mov     ecx, [rsp+4010h+var_3FB4]
0x180012159  mov     r8, r12
0x18001215c  mov     r9, [rbx+28h]
0x180012160  mov     rdx, r15
0x180012163  mov     [rsp+4010h+var_3FD8], ecx
0x180012167  xor     ecx, ecx
0x180012169  mov     [rsp+4010h+var_3FE0], eax
0x18001216d  mov     rax, [rsp+4010h+UnbiasedTime]
0x180012172  mov     [rsp+4010h+var_3FE8], rax
0x180012177  mov     rax, [rbx+20h]
0x18001217b  mov     [rsp+4010h+var_3FF0], rax
0x180012180  call    TlmiLogHydrationPerformance
0x180012185  lea     r8, qword_1800283B0
0x18001218c  cmp     esi, 18h
0x18001218f  jnz     loc_18001248E
0x180012195  mov     eax, cs:dword_1800281A0
0x18001219b  cmp     eax, 5
0x18001219e  jbe     loc_180012A40
0x1800121a4  mov     rcx, cs:qword_1800281B8
0x1800121ab  mov     rdx, 200000000000h
0x1800121b5  mov     rax, cs:qword_1800281B0
0x1800121bc  test    rdx, rax
0x1800121bf  jz      loc_180012A40
0x1800121c5  mov     rax, rcx
0x1800121c8  and     rax, rdx
0x1800121cb  cmp     rax, rcx
0x1800121ce  jnz     loc_180012A40
0x1800121d4  mov     [rbp+3F10h+var_3D10], r14
0x1800121db  lea     rax, [rbp+3F10h+var_3D20]
0x1800121e2  mov     r14, [rbp+3F10h+arg_28]
0x1800121e9  lea     rcx, [rbp+3F10h+var_3CF8]
0x1800121f0  mov     [rbp+3F10h+var_3310], rax
0x1800121f7  mov     rdx, r15
0x1800121fa  mov     eax, [rsp+4010h+var_3FB8]
0x1800121fe  mov     [rbp+3F10h+var_3D18], rax
0x180012205  lea     rax, [rbp+3F10h+var_3D18]
0x18001220c  mov     [rbp+3F10h+var_3300], rax
0x180012213  lea     rax, [rbp+3F10h+var_3D10]
0x18001221a  mov     [rbp+3F10h+var_32F0], rax
0x180012221  mov     rax, qword ptr [rsp+4010h+FileSize]
0x180012226  mov     [rbp+3F10h+var_3D08], rax
0x18001222d  lea     rax, [rbp+3F10h+var_3D08]
0x180012234  mov     [rbp+3F10h+var_32E0], rax
0x18001223b  lea     rax, [rbp+3F10h+var_3D00]
0x180012242  mov     [rbp+3F10h+var_32D0], rax
0x180012249  mov     rax, [rsp+4010h+UnbiasedTime]
0x18001224e  mov     [rbp+3F10h+var_3CF8], rax
0x180012255  mov     [rbp+3F10h+var_3CE8], rax
0x18001225c  lea     rax, [rbp+3F10h+var_3CE8]
0x180012263  mov     [rbp+3F10h+var_32C0], rcx
0x18001226a  lea     rcx, [rbp+3F10h+var_3CF0]
0x180012271  mov     [rbp+3F10h+var_32A0], rax
0x180012278  mov     rax, cs:off_180028600; "CfGetSyncRootInfoByPath"
0x18001227f  mov     [rbp+3F10h+var_32B0], rcx
0x180012286  lea     rcx, [rbp+3F10h+var_3278]
0x18001228d  mov     [rbp+3F10h+var_3280], rax
0x180012294  movzx   eax, cs:word_1800285F8
0x18001229b  mov     [rbp+3F10h+var_3D00], r14
0x1800122a2  mov     [rbp+3F10h+var_3CF0], r14
0x1800122a9  xor     r14d, r14d
0x1800122ac  mov     [rbp+3F10h+var_3290], rcx
0x1800122b3  lea     rcx, [rbp+3F10h+var_3270]
0x1800122ba  mov     [rbp+3F10h+var_3278], eax
0x1800122c0  mov     [rbp+3F10h+var_3D20], 1
0x1800122cb  mov     [rbp+3F10h+var_3308], 8
0x1800122d6  mov     [rbp+3F10h+var_32F8], 8
0x1800122e1  mov     [rbp+3F10h+var_32E8], 8
0x1800122ec  mov     [rbp+3F10h+var_32D8], 8
0x1800122f7  mov     [rbp+3F10h+var_32C8], 8
0x180012302  mov     [rbp+3F10h+var_32B8], 8
0x18001230d  mov     [rbp+3F10h+var_32A8], 8
0x180012318  mov     [rbp+3F10h+var_3298], 8
0x180012323  mov     [rbp+3F10h+var_3288], 2
0x18001232e  mov     [rbp+3F10h+var_3274], r14d
0x180012335  call    _tlgCreate1Sz_wchar_t
0x18001233a  mov     rdx, r12
0x18001233d  lea     rcx, [rbp+3F10h+var_3260]
0x180012344  call    _tlgCreate1Sz_wchar_t
0x180012349  lea     rax, [rbp+3F10h+var_3CE0]
0x180012350  mov     [rbp+3F10h+var_3CE0], r13
0x180012357  mov     [rbp+3F10h+var_3250], rax
0x18001235e  mov     al, cs:byte_180028968
0x180012364  mov     [rsp+4010h+var_3FCF], al
0x180012368  lea     rax, [rsp+4010h+var_3FCF]
0x18001236d  mov     [rbp+3F10h+var_3240], rax
0x180012374  lea     rax, [rbp+3F10h+var_3DE0]
0x18001237b  mov     [rbp+3F10h+var_3230], rax
0x180012382  mov     eax, [rsp+4010h+var_3FB4]
0x180012386  mov     [rbp+3F10h+var_3CD8], rax
0x18001238d  lea     rax, [rbp+3F10h+var_3CD8]
0x180012394  mov     [rbp+3F10h+var_3220], rax
  ... truncated ...
```
