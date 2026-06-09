# CtapCborDecodeRpcRequest

- ea: `0x180010d90`
- end: `0x18001592a`
- name: `CtapCborDecodeRpcRequest`
- size: `19354`
- prototype: ``
- caller_count: `9`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010b20`
- `0x180015a40`
- `0x180028a70`
- `0x180069350`
- `0x180073a90`
- `0x180073e80`
- `0x180074000`
- `0x1800d8d68`
- `0x1800d9008`

## callees

- `0x180010d90`
- `0x180017a00`
- `0x180046494`
- `0x180046768`
- `0x1800467a4`
- `0x1800467e0`
- `0x180046820`
- `0x18004685c`
- `0x18004cd7c`
- `0x18005378c`
- `0x180056530`
- `0x180056580`
- `0x180056780`
- `0x1800567c0`
- `0x1800567e0`
- `0x180056a00`
- `0x18006b260`
- `0x1800c8098`
- `0x1800cbb00`
- `0x1800cc264`
- `0x1800cc2a0`
- `0x1800cd86c`
- `0x1800ce3a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800121b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800157c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800121b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800157c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012311`

## string_xrefs

- `0x180014813`: `clientDataJSON`
- `0x180013c13`: `pluginAuthenticatorState`
- `0x180011121`: `command`
- `0x180012d2a`: `linkedData`
- `0x1800131e0`: `pluginAuthenticatorName`
- `0x180013811`: `pluginNewClsId`
- `0x1800137ad`: `pluginClsId`
- `0x1800138d9`: `pluginDarkLogo`
- `0x180013875`: `pluginLightLogo`
- `0x180013a1a`: `pluginIdKey`
- `0x180013b8b`: `pluginAutofillScenarioSupported`
- `0x1800141eb`: `pluginUvOpRes`
- `0x180014595`: `pluginNonce`
- `0x180015146`: `pluginUvBufferToSign`
- `0x18001505b`: `pluginUvKeyName`
- `0x180015918`: `onecore\internal\sdk\inc\wil\opensource\wil\safecast.h`

## pseudocode

```c
__int64 __fastcall CtapCborDecodeRpcRequest(unsigned int a1, __int64 a2, SIZE_T *a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v5; // rbx
  SIZE_T *v6; // r14
  void *v7; // rsi
  SIZE_T v8; // rdi
  char IsEnabled; // al
  int v10; // ecx
  unsigned int v11; // r9d
  int v12; // eax
  unsigned __int64 v13; // r13
  char *v14; // r14
  unsigned __int64 v15; // r12
  SIZE_T v16; // r15
  unsigned int v17; // eax
  int v18; // edx
  SIZE_T v19; // rdi
  int value; // ecx
  __int64 v21; // rdx
  unsigned __int64 v22; // rbx
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // rdx
  unsigned __int64 v26; // rbx
  int v27; // ecx
  int v28; // ecx
  __int64 v29; // rdx
  unsigned __int64 v30; // rbx
  int v31; // ecx
  int v32; // ecx
  int v33; // eax
  unsigned __int64 v34; // rax
  char *v35; // rsi
  unsigned __int64 v36; // rcx
  unsigned int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  unsigned __int64 v50; // r13
  int v51; // eax
  SIZE_T v52; // r13
  unsigned __int64 v53; // rsi
  int v54; // eax
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rcx
  unsigned int v57; // eax
  int v58; // eax
  unsigned __int64 v59; // rax
  char *v60; // rbx
  unsigned __int64 v61; // rcx
  unsigned int v62; // eax
  int v63; // eax
  unsigned __int64 v64; // rax
  char *v65; // rbx
  unsigned __int64 v66; // rcx
  unsigned int v67; // eax
  int v68; // eax
  unsigned __int64 v69; // rax
  char *v70; // rbx
  unsigned __int64 v71; // rcx
  unsigned int v72; // eax
  int v73; // eax
  unsigned __int64 v74; // rax
  char *v75; // rbx
  unsigned __int64 v76; // rcx
  unsigned int v77; // eax
  int v78; // eax
  unsigned __int64 v79; // rax
  char *v80; // rbx
  unsigned __int64 v81; // rcx
  unsigned int v82; // eax
  __int64 v83; // rdx
  unsigned int v84; // edi
  unsigned __int64 v85; // rax
  HLOCAL v86; // rbx
  size_t v87; // r8
  char *v88; // r14
  unsigned __int64 v89; // rcx
  unsigned int v90; // eax
  unsigned int v91; // eax
  int v92; // eax
  int v93; // eax
  __int64 v94; // rax
  int v95; // eax
  __int64 v96; // rax
  int v97; // eax
  int v98; // eax
  int v99; // eax
  __int64 v100; // rax
  int v101; // eax
  __int64 v102; // rax
  int v103; // eax
  __int64 v104; // rax
  int v105; // eax
  int v106; // eax
  __int64 v107; // rax
  unsigned int v108; // edx
  int v109; // eax
  int v110; // eax
  unsigned __int64 v111; // rax
  SIZE_T v112; // rbx
  unsigned __int64 v113; // rcx
  unsigned int v114; // eax
  int v115; // eax
  SIZE_T v116; // r12
  SIZE_T v117; // rsi
  int v118; // ebx
  SIZE_T v119; // r14
  int v120; // edi
  int v121; // eax
  __int64 v122; // rax
  int v123; // eax
  __int64 v124; // rax
  int v125; // eax
  unsigned __int64 v126; // rax
  unsigned __int64 v127; // rcx
  unsigned int v128; // eax
  int v129; // eax
  unsigned __int64 v130; // rax
  unsigned __int64 v131; // rcx
  unsigned int v132; // eax
  int v133; // eax
  int v134; // eax
  int v135; // eax
  unsigned __int64 v136; // rax
  SIZE_T v137; // rbx
  unsigned __int64 v138; // rcx
  unsigned int v139; // eax
  unsigned int v140; // ebx
  int v141; // eax
  unsigned __int64 v142; // rax
  SIZE_T v143; // rdi
  unsigned __int64 v144; // rcx
  int v145; // eax
  int v146; // eax
  int v147; // eax
  int v148; // eax
  int v149; // eax
  __int64 v150; // rax
  int v151; // eax
  __int64 v152; // rax
  int v153; // eax
  __int64 v154; // rax
  int v155; // eax
  __int64 v156; // rax
  int v157; // eax
  __int64 v158; // rax
  int v159; // eax
  __int64 v160; // rax
  int v161; // eax
  __int64 v162; // rax
  int v163; // eax
  __int64 v164; // rax
  int v165; // eax
  __int64 v166; // rax
  int v167; // eax
  int v168; // eax
  int v169; // eax
  __int64 v170; // rax
  int v171; // eax
  __int64 v172; // rax
  int v173; // eax
  int v174; // esi
  int v175; // r14d
  int v176; // r15d
  int v177; // r12d
  SIZE_T v178; // rdi
  int v179; // ebx
  int v180; // eax
  __int64 v181; // rax
  char v182; // al
  unsigned int v183; // ecx
  int v184; // eax
  int v185; // ecx
  unsigned __int64 v186; // rbx
  int v187; // eax
  unsigned __int64 v188; // rax
  SIZE_T v189; // rbx
  unsigned __int64 v190; // rcx
  unsigned int v191; // eax
  int v192; // eax
  int v193; // eax
  unsigned __int64 v194; // rax
  SIZE_T v195; // rbx
  unsigned __int64 v196; // rcx
  unsigned int v197; // eax
  int v198; // eax
  unsigned __int64 v199; // rax
  SIZE_T v200; // rbx
  unsigned __int64 v201; // rcx
  unsigned int v202; // eax
  __int64 v203; // rax
  int v204; // eax
  int v205; // ecx
  unsigned __int64 v206; // rbx
  int v207; // eax
  unsigned __int64 v208; // rax
  SIZE_T v209; // rbx
  unsigned __int64 v210; // rcx
  unsigned int v211; // eax
  int v212; // eax
  unsigned __int64 v213; // rax
  SIZE_T v214; // rbx
  unsigned __int64 v215; // rcx
  unsigned int v216; // eax
  int v217; // eax
  unsigned __int64 v218; // rax
  SIZE_T v219; // rbx
  unsigned __int64 v220; // rcx
  unsigned int v221; // eax
  int v222; // eax
  unsigned __int64 v223; // rax
  SIZE_T v224; // rbx
  unsigned __int64 v225; // rcx
  unsigned int v226; // eax
  unsigned __int64 v227; // rax
  int v228; // eax
  int v229; // eax
  int v230; // eax
  unsigned __int64 v231; // rax
  unsigned __int64 v232; // rcx
  unsigned int v233; // eax
  int v234; // eax
  int v235; // eax
  __int64 v236; // rax
  int v237; // eax
  __int64 v238; // rax
  int v239; // eax
  int v240; // eax
  unsigned __int64 v241; // rax
  SIZE_T v242; // rdx
  unsigned __int64 v243; // rcx
  unsigned int v244; // eax
  int v245; // eax
  unsigned __int64 v246; // rax
  SIZE_T v247; // rdx
  unsigned __int64 v248; // rcx
  unsigned int v249; // eax
  int v250; // eax
  unsigned __int64 v251; // rax
  SIZE_T v252; // rdx
  unsigned __int64 v253; // rcx
  unsigned int v254; // eax
  int v255; // eax
  __int64 v256; // rax
  char v257; // al
  int v258; // eax
  int v259; // eax
  int v260; // eax
  __int64 v261; // rax
  int v262; // eax
  int v263; // eax
  unsigned __int64 v264; // rax
  unsigned __int64 v265; // rcx
  int v266; // eax
  unsigned int v267; // eax
  SIZE_T v268; // rcx
  bool v269; // zf
  int v270; // eax
  SIZE_T v271; // rax
  SIZE_T v272; // rcx
  BOOL v273; // eax
  char v274; // al
  SIZE_T v275; // rcx
  __int64 v276; // rax
  SIZE_T v277; // rax
  SIZE_T v278; // rax
  char *v279; // rax
  __int64 result; // rax
  int v281; // [rsp+28h] [rbp-E0h]
  unsigned int v282; // [rsp+38h] [rbp-D0h]
  int v283[4]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v284; // [rsp+50h] [rbp-B8h]
  _QWORD v285[7]; // [rsp+58h] [rbp-B0h] BYREF
  int cbMultiByte[4]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v287; // [rsp+A0h] [rbp-68h]
  SIZE_T uBytes; // [rsp+A8h] [rbp-60h]
  bool v289; // [rsp+B0h] [rbp-58h]
  bool v290; // [rsp+B1h] [rbp-57h]
  bool v291; // [rsp+B2h] [rbp-56h]
  bool v292; // [rsp+B3h] [rbp-55h]
  bool v293; // [rsp+B4h] [rbp-54h]
  bool v294; // [rsp+B5h] [rbp-53h]
  SIZE_T v295; // [rsp+B8h] [rbp-50h]
  SIZE_T v296; // [rsp+C0h] [rbp-48h]
  int v297; // [rsp+C8h] [rbp-40h]
  int v298; // [rsp+CCh] [rbp-3Ch]
  int v299; // [rsp+D0h] [rbp-38h]
  char *v300; // [rsp+D8h] [rbp-30h]
  int v301; // [rsp+E0h] [rbp-28h]
  int v302; // [rsp+E4h] [rbp-24h]
  char *v303; // [rsp+E8h] [rbp-20h]
  __int128 v304; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v305; // [rsp+100h] [rbp-8h]
  char *v306; // [rsp+108h] [rbp+0h]
  unsigned __int64 v307; // [rsp+110h] [rbp+8h]
  char *v308; // [rsp+118h] [rbp+10h]
  char *v309; // [rsp+120h] [rbp+18h]
  char *v310; // [rsp+128h] [rbp+20h]
  SIZE_T v311; // [rsp+130h] [rbp+28h]
  SIZE_T v312; // [rsp+138h] [rbp+30h]
  SIZE_T v313; // [rsp+140h] [rbp+38h]
  SIZE_T v314; // [rsp+148h] [rbp+40h]
  SIZE_T v315; // [rsp+150h] [rbp+48h]
  SIZE_T v316; // [rsp+158h] [rbp+50h]
  SIZE_T v317; // [rsp+160h] [rbp+58h]
  _OWORD *v318; // [rsp+168h] [rbp+60h]
  SIZE_T v319; // [rsp+170h] [rbp+68h]
  SIZE_T v320; // [rsp+178h] [rbp+70h]
  SIZE_T v321; // [rsp+180h] [rbp+78h]
  SIZE_T v322; // [rsp+188h] [rbp+80h]
  char *v323; // [rsp+190h] [rbp+88h]
  SIZE_T v324; // [rsp+198h] [rbp+90h]
  char *v325; // [rsp+1A0h] [rbp+98h]
  unsigned __int64 v326; // [rsp+1A8h] [rbp+A0h]
  unsigned __int64 v327; // [rsp+1B0h] [rbp+A8h]
  unsigned __int64 v328; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v329; // [rsp+1C0h] [rbp+B8h]
  unsigned __int64 v330; // [rsp+1C8h] [rbp+C0h]
  char *v331; // [rsp+1D0h] [rbp+C8h]
  unsigned __int64 v332; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 v333; // [rsp+1E0h] [rbp+D8h]
  unsigned __int64 v334; // [rsp+1E8h] [rbp+E0h]
  unsigned __int64 v335; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v336; // [rsp+1F8h] [rbp+F0h]
  unsigned __int64 v337; // [rsp+200h] [rbp+F8h]
  unsigned __int64 v338; // [rsp+208h] [rbp+100h]
  unsigned __int64 v339; // [rsp+210h] [rbp+108h]
  unsigned __int64 v340; // [rsp+218h] [rbp+110h]
  unsigned __int64 v341; // [rsp+220h] [rbp+118h]
  unsigned int v342; // [rsp+228h] [rbp+120h] BYREF
  int v343; // [rsp+22Ch] [rbp+124h]
  unsigned int v344; // [rsp+230h] [rbp+128h]
  unsigned __int64 v345; // [rsp+238h] [rbp+130h]
  unsigned __int64 v346; // [rsp+240h] [rbp+138h] BYREF
  unsigned __int64 v347; // [rsp+248h] [rbp+140h] BYREF
  __int64 v348; // [rsp+250h] [rbp+148h]
  unsigned __int64 v349; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int64 v350; // [rsp+260h] [rbp+158h] BYREF
  unsigned __int64 v351; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 v352; // [rsp+270h] [rbp+168h] BYREF
  unsigned __int64 v353; // [rsp+278h] [rbp+170h] BYREF
  unsigned __int64 v354; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 v355; // [rsp+288h] [rbp+180h] BYREF
  unsigned __int64 v356; // [rsp+290h] [rbp+188h] BYREF
  unsigned __int64 v357; // [rsp+298h] [rbp+190h] BYREF
  unsigned __int64 v358; // [rsp+2A0h] [rbp+198h] BYREF
  unsigned __int64 v359; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned __int64 v360; // [rsp+2B0h] [rbp+1A8h] BYREF
  unsigned __int64 v361; // [rsp+2B8h] [rbp+1B0h] BYREF
  unsigned __int64 v362; // [rsp+2C0h] [rbp+1B8h] BYREF
  unsigned __int64 v363; // [rsp+2C8h] [rbp+1C0h] BYREF
  unsigned __int64 v364; // [rsp+2D0h] [rbp+1C8h] BYREF
  unsigned __int64 v365; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int64 v366; // [rsp+2E0h] [rbp+1D8h] BYREF
  unsigned __int64 v367; // [rsp+2E8h] [rbp+1E0h] BYREF
  char *v368; // [rsp+2F0h] [rbp+1E8h]
  unsigned __int64 v369; // [rsp+2F8h] [rbp+1F0h]
  SIZE_T v370; // [rsp+300h] [rbp+1F8h]
  unsigned __int64 v371; // [rsp+308h] [rbp+200h] BYREF
  unsigned __int64 v372; // [rsp+310h] [rbp+208h] BYREF
  unsigned __int64 v373; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int64 v374; // [rsp+320h] [rbp+218h] BYREF
  int v375[2]; // [rsp+328h] [rbp+220h] BYREF
  int v376[2]; // [rsp+330h] [rbp+228h] BYREF
  __int64 v377; // [rsp+338h] [rbp+230h]
  int v378[2]; // [rsp+340h] [rbp+238h] BYREF
  int v379[2]; // [rsp+348h] [rbp+240h] BYREF
  int v380[2]; // [rsp+350h] [rbp+248h] BYREF
  __int64 v381; // [rsp+358h] [rbp+250h]
  int v382[2]; // [rsp+360h] [rbp+258h] BYREF
  int v383[2]; // [rsp+368h] [rbp+260h] BYREF
  int v384[2]; // [rsp+370h] [rbp+268h] BYREF
  __int64 v385; // [rsp+378h] [rbp+270h]
  int v386[2]; // [rsp+380h] [rbp+278h] BYREF
  int v387[2]; // [rsp+388h] [rbp+280h] BYREF
  __int64 i; // [rsp+390h] [rbp+288h]
  _OWORD v389[2]; // [rsp+398h] [rbp+290h] BYREF
  __int64 v390; // [rsp+3B8h] [rbp+2B0h]
  wil::details::in1diag3 *retaddr; // [rsp+410h] [rbp+308h]
  bool v396; // [rsp+440h] [rbp+338h]

  v5 = a1;
  v300 = 0;
  v6 = a3;
  v7 = 0;
  v8 = 0;
  memset(v285, 0, sizeof(v285));
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::GetImpl'::`2'::impl);
  v10 = a2;
  if ( IsEnabled )
  {
    if ( !a2 || (unsigned int)(v5 - 1) > 0xFFFFF )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
      {
        if ( (_DWORD)v5 )
        {
          if ( (unsigned int)v5 > 0x100000 )
            FidoTraceProvider::Log<2>("RPC request of size %ld too large", v5);
        }
        else
        {
          FidoTraceProvider::Log<2>("Decoding empty RPC Request failed");
        }
      }
      v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v282 = v11;
      if ( !v11 )
      {
        v11 = 3;
        LODWORD(v285[5]) = 7334;
        v282 = 3;
      }
      goto LABEL_1285;
    }
  }
  else if ( !a2 || (unsigned int)(v5 - 1) > 0xFFFF )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl) )
    {
      if ( (_DWORD)v5 )
      {
        if ( (unsigned int)v5 > 0x10000 )
          FidoTraceProvider::Log<2>("RPC request of size %ld too large", v5);
      }
      else
      {
        FidoTraceProvider::Log<2>("Decoding empty RPC Request failed");
      }
    }
    v11 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v282 = v11;
    if ( !v11 )
    {
      v11 = 3;
      LODWORD(v285[5]) = 7353;
      v282 = 3;
    }
    goto LABEL_1285;
  }
  v295 = 0;
  v12 = v5;
  v343 = 0;
  for ( i = v5; ; v12 = i )
  {
    v13 = 0;
    v14 = v300;
    v15 = 0;
    v297 = 0;
    v298 = 0;
    v287 = 0;
    v299 = 0;
    v303 = 0;
    v307 = 0;
    v325 = 0;
    v345 = 0;
    v16 = 0;
    v306 = 0;
    v326 = 0;
    v368 = 0;
    v308 = 0;
    v327 = 0;
    v309 = 0;
    v328 = 0;
    v310 = 0;
    v329 = 0;
    v323 = 0;
    v330 = 0;
    v331 = 0;
    v369 = 0;
    v377 = 0;
    v312 = 0;
    v332 = 0;
    v396 = 0;
    v370 = 0;
    v385 = 0;
    v289 = 0;
    v290 = 0;
    v313 = 0;
    v333 = 0;
    *(_QWORD *)v386 = 0;
    v314 = 0;
    v334 = 0;
    *(_QWORD *)v387 = 0;
    *(_QWORD *)v375 = 0;
    *(_QWORD *)v376 = 0;
    *(_QWORD *)v384 = 0;
    *(_QWORD *)v378 = 0;
    v301 = 0;
    v315 = 0;
    v335 = 0;
    v291 = 0;
    v316 = 0;
    v336 = 0;
    v317 = 0;
    v337 = 0;
    v348 = 0;
    v319 = 0;
    v339 = 0;
    v302 = 0;
    v318 = 0;
    v338 = 0;
    *(_QWORD *)v379 = 0;
    *(_QWORD *)v380 = 0;
    v340 = 0;
    v320 = 0;
    v341 = 0;
    v321 = 0;
    v381 = 0;
    v344 = 0;
    *(_QWORD *)v383 = 0;
    *(_QWORD *)v382 = 0;
    uBytes = 0;
    memset(&v285[3], 0, 32);
    v285[0] = v300;
    *(_OWORD *)&v285[1] = v8;
    v389[0] = 0;
    *(_OWORD *)cbMultiByte = 0;
    v17 = cbor_parser_init(v10, v12, 0, (unsigned int)v389, (__int64)cbMultiByte);
    v282 = v17;
    v18 = v17;
    v296 = 0;
    if ( v17 )
    {
      LODWORD(v285[3]) = v17;
      LODWORD(v285[5]) = 7449;
      v285[6] = 0;
      goto LABEL_22;
    }
    if ( !v14 )
      goto LABEL_21;
    v19 = v295;
    if ( v295 >= 0x238 )
    {
      v296 = (SIZE_T)v14;
LABEL_21:
      v18 = v285[3];
      v16 = 568;
      uBytes = 568;
      v285[2] = 568;
      v282 = v285[3];
LABEL_22:
      v19 = v295;
      goto LABEL_23;
    }
    v18 = _mm_cvtsi128_si32((__m128i)0LL);
    v282 = v18;
    if ( !v18 )
    {
      v18 = 0x80000000;
      LODWORD(v285[5]) = 7453;
      v282 = 0x80000000;
      LODWORD(v285[3]) = 0x80000000;
      v285[6] = 0;
    }
LABEL_23:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_43;
    if ( BYTE6(v287) != 0xA0 )
    {
      value = 260;
LABEL_29:
      v18 = value;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      v282 = value;
      LODWORD(v285[3]) = value;
      LODWORD(v285[5]) = 7456;
      v285[6] = 0;
      goto LABEL_43;
    }
    value = cbor_value_map_find_value(cbMultiByte, "command", v283);
    if ( value )
      goto LABEL_29;
    if ( BYTE6(v284) == 0xFF )
    {
      value = 259;
      goto LABEL_29;
    }
    v297 = -1;
    if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
    {
      v23 = 260;
LABEL_40:
      v18 = v23;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v23;
      LODWORD(v285[3]) = v23;
      LODWORD(v285[5]) = 7458;
      v285[6] = 0;
      goto LABEL_41;
    }
    if ( (v284 & 0x100000000000000LL) != 0 )
      v22 = cbor_value_decode_int64_internal(v283, v21);
    else
      v22 = WORD2(v284);
    v23 = cbor_value_advance_fixed(v283);
    if ( v23 )
      goto LABEL_40;
    v18 = v282;
    if ( v22 <= 0xFFFFFFFF )
    {
      v297 = v22;
      goto LABEL_43;
    }
    v23 = 1024;
LABEL_41:
    if ( !v18 )
    {
      v18 = v23;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v23;
      LODWORD(v285[3]) = v23;
      LODWORD(v285[5]) = 7458;
      v285[6] = 0;
    }
LABEL_43:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_63;
    if ( BYTE6(v287) != 0xA0 )
    {
      v24 = 260;
LABEL_49:
      v18 = v24;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      v282 = v24;
      LODWORD(v285[3]) = v24;
      LODWORD(v285[5]) = 7461;
      v285[6] = 0;
      goto LABEL_63;
    }
    v24 = cbor_value_map_find_value(cbMultiByte, "flags", v283);
    if ( v24 )
      goto LABEL_49;
    if ( BYTE6(v284) == 0xFF )
    {
      v24 = 259;
      goto LABEL_49;
    }
    v298 = -1;
    if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
    {
      v27 = 260;
LABEL_60:
      v18 = v27;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v27;
      LODWORD(v285[3]) = v27;
      LODWORD(v285[5]) = 7463;
      v285[6] = 0;
      goto LABEL_61;
    }
    if ( (v284 & 0x100000000000000LL) != 0 )
      v26 = cbor_value_decode_int64_internal(v283, v25);
    else
      v26 = WORD2(v284);
    v27 = cbor_value_advance_fixed(v283);
    if ( v27 )
      goto LABEL_60;
    v18 = v282;
    if ( v26 <= 0xFFFFFFFF )
    {
      v298 = v26;
      goto LABEL_63;
    }
    v27 = 1024;
LABEL_61:
    if ( !v18 )
    {
      v18 = v27;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v27;
      LODWORD(v285[3]) = v27;
      LODWORD(v285[5]) = 7463;
      v285[6] = 0;
    }
LABEL_63:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_83;
    if ( BYTE6(v287) != 0xA0 )
    {
      v28 = 260;
LABEL_69:
      v18 = v28;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      v282 = v28;
      LODWORD(v285[3]) = v28;
      LODWORD(v285[5]) = 7466;
      v285[6] = 0;
      goto LABEL_83;
    }
    v28 = cbor_value_map_find_value(cbMultiByte, "timeout", v283);
    if ( v28 )
      goto LABEL_69;
    if ( BYTE6(v284) == 0xFF )
    {
      v28 = 259;
      goto LABEL_69;
    }
    v299 = -1;
    if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
    {
      v31 = 260;
LABEL_80:
      v18 = v31;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v31;
      LODWORD(v285[3]) = v31;
      LODWORD(v285[5]) = 7468;
      v285[6] = 0;
      goto LABEL_81;
    }
    if ( (v284 & 0x100000000000000LL) != 0 )
      v30 = cbor_value_decode_int64_internal(v283, v29);
    else
      v30 = WORD2(v284);
    v31 = cbor_value_advance_fixed(v283);
    if ( v31 )
      goto LABEL_80;
    v18 = v282;
    if ( v30 <= 0xFFFFFFFF )
    {
      v299 = v30;
      goto LABEL_83;
    }
    v31 = 1024;
LABEL_81:
    if ( !v18 )
    {
      v18 = v31;
      v285[4] = *(_QWORD *)&v283[2];
      v282 = v31;
      LODWORD(v285[3]) = v31;
      LODWORD(v285[5]) = 7468;
      v285[6] = 0;
    }
LABEL_83:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_109;
    if ( BYTE6(v287) != 0xA0 )
    {
      v32 = 260;
LABEL_86:
      v18 = v32;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      v282 = v32;
      LODWORD(v285[3]) = v32;
      LODWORD(v285[5]) = 7471;
      v285[6] = 0;
      goto LABEL_109;
    }
    v32 = cbor_value_map_find_value(cbMultiByte, "transactionId", v283);
    if ( v32 )
      goto LABEL_86;
    if ( BYTE6(v284) == 0xFF )
    {
      v32 = 259;
      goto LABEL_86;
    }
    v18 = v282;
    v346 = 0;
    v307 = 0;
    v303 = 0;
    if ( BYTE6(v284) != 64 )
    {
      v33 = 260;
      goto LABEL_108;
    }
    if ( (v284 & 0x400000000000000LL) != 0 )
    {
      v33 = 2;
      v303 = 0;
      v307 = 0;
LABEL_107:
      if ( v18 )
        goto LABEL_109;
LABEL_108:
      v18 = v33;
      v282 = v33;
      LODWORD(v285[3]) = v33;
      v285[4] = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7473;
      v285[6] = 0;
      goto LABEL_109;
    }
    v34 = (v284 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v283, v282) : WORD2(v284);
    v346 = v34;
    v35 = 0;
    v303 = 0;
    if ( v34 > 0x40000 )
    {
      v37 = 1024;
    }
    else
    {
      v36 = (v34 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v14 )
        goto LABEL_101;
      if ( v16 + v36 <= v19 )
      {
        v35 = &v14[v16];
        v303 = &v14[v16];
LABEL_101:
        v16 += v36;
        uBytes = v16;
        v285[2] = v16;
        goto LABEL_104;
      }
      v37 = 0x80000000;
    }
    v282 = v37;
    LODWORD(v285[3]) = v37;
    v285[4] = *(_QWORD *)&v283[2];
    LODWORD(v285[5]) = 7473;
    v285[6] = 0;
LABEL_104:
    v33 = cbor_value_copy_string(v283, v35, &v346, v283);
    v18 = v282;
    v307 = v346;
    if ( v33 )
      goto LABEL_107;
LABEL_109:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_114;
    if ( BYTE6(v287) != 0xA0 )
    {
      v38 = 260;
LABEL_112:
      v18 = v38;
      v282 = v38;
      LODWORD(v285[3]) = v38;
      v39 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7476;
LABEL_113:
      v285[6] = 0;
      v285[4] = v39;
      goto LABEL_114;
    }
    v38 = cbor_value_map_find_value(cbMultiByte, "ticket", v283);
    if ( v38 )
      goto LABEL_112;
    if ( BYTE6(v284) == 0xFF )
      v38 = 259;
    v18 = v282;
    if ( !v38 )
    {
      v345 = 0;
      v53 = 0;
      v374 = 0;
      if ( v282 )
      {
        v54 = 260;
        v345 = 0;
        goto LABEL_175;
      }
      if ( BYTE6(v284) != 64 )
      {
        v54 = 260;
        v325 = 0;
        v345 = 0;
        goto LABEL_177;
      }
      if ( (v284 & 0x400000000000000LL) == 0 )
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v55 = cbor_value_decode_int64_internal(v283, v282);
        else
          v55 = WORD2(v284);
        v374 = v55;
        v325 = 0;
        if ( v55 > 0x40000 || v16 > 0x40000 )
        {
          v57 = 1024;
LABEL_171:
          v282 = v57;
          LODWORD(v285[3]) = v57;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7478;
          v285[6] = 0;
        }
        else
        {
          v56 = (v55 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v16 + v56 > v19 )
            {
              v57 = 0x80000000;
              goto LABEL_171;
            }
            v13 = (unsigned __int64)&v14[v16];
            v325 = &v14[v16];
          }
          v16 += v56;
          uBytes = v16;
          v285[2] = v16;
        }
        v54 = cbor_value_copy_string(v283, v13, &v374, v283);
        v53 = v374;
        v18 = v282;
        v345 = v374;
        if ( v54 )
        {
          v13 = 0;
          goto LABEL_176;
        }
        goto LABEL_178;
      }
      v54 = 2;
LABEL_175:
      v325 = 0;
LABEL_176:
      if ( v18 )
      {
LABEL_178:
        v39 = *(_QWORD *)&v283[2];
        v13 = 0;
      }
      else
      {
LABEL_177:
        v18 = v54;
        v282 = v54;
        LODWORD(v285[3]) = v54;
        v39 = *(_QWORD *)&v283[2];
        v285[4] = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7478;
        v285[6] = 0;
      }
      if ( !v53 && !v18 )
      {
        v18 = 769;
        LODWORD(v285[5]) = 7481;
        v282 = 769;
        LODWORD(v285[3]) = 769;
        goto LABEL_113;
      }
    }
LABEL_114:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_118;
    if ( BYTE6(v287) != 0xA0 )
    {
      v40 = 260;
LABEL_117:
      v18 = v40;
      v282 = v40;
      LODWORD(v285[3]) = v40;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7485;
      v285[6] = 0;
      goto LABEL_118;
    }
    v40 = cbor_value_map_find_value(cbMultiByte, "request", v283);
    if ( v40 )
      goto LABEL_117;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v40 = 259;
    if ( !v40 )
    {
      v326 = 0;
      v15 = 0;
      v372 = 0;
      if ( v282 )
      {
        v58 = 260;
        v326 = 0;
        goto LABEL_206;
      }
      if ( BYTE6(v284) != 64 )
      {
        v58 = 260;
        v306 = 0;
        v326 = 0;
LABEL_208:
        v18 = v58;
        v282 = v58;
        LODWORD(v285[3]) = v58;
        v285[4] = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7487;
        v285[6] = 0;
        goto LABEL_118;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v58 = 2;
LABEL_206:
        v306 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v59 = cbor_value_decode_int64_internal(v283, v282);
        else
          v59 = WORD2(v284);
        v372 = v59;
        v60 = 0;
        v306 = 0;
        if ( v59 > 0x40000 || v16 > 0x40000 )
        {
          v62 = 1024;
LABEL_202:
          v282 = v62;
          LODWORD(v285[3]) = v62;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7487;
          v285[6] = 0;
        }
        else
        {
          v61 = (v59 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v61 + v16 > v19 )
            {
              v62 = 0x80000000;
              goto LABEL_202;
            }
            v60 = &v14[v16];
            v306 = &v14[v16];
          }
          v16 += v61;
          uBytes = v16;
          v285[2] = v16;
        }
        v58 = cbor_value_copy_string(v283, v60, &v372, v283);
        v15 = v372;
        v18 = v282;
        v326 = v372;
        if ( !v58 )
          goto LABEL_118;
      }
      if ( v18 )
        goto LABEL_118;
      goto LABEL_208;
    }
LABEL_118:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_123;
    if ( BYTE6(v287) != 0xA0 )
    {
      v41 = 260;
LABEL_121:
      v18 = v41;
      v282 = v41;
      LODWORD(v285[3]) = v41;
      v42 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7490;
      goto LABEL_122;
    }
    v41 = cbor_value_map_find_value(cbMultiByte, "pin", v283);
    if ( v41 )
      goto LABEL_121;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v41 = 259;
    if ( !v41 )
    {
      v327 = 0;
      v373 = 0;
      if ( v282 )
      {
        v63 = 260;
        v327 = 0;
        goto LABEL_233;
      }
      if ( BYTE6(v284) != 64 )
      {
        v63 = 260;
        v308 = 0;
        v327 = 0;
LABEL_235:
        v18 = v63;
        v282 = v63;
        LODWORD(v285[3]) = v63;
        v42 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7492;
LABEL_122:
        v285[6] = 0;
        v285[4] = v42;
        goto LABEL_123;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v63 = 2;
LABEL_233:
        v308 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v64 = cbor_value_decode_int64_internal(v283, v282);
        else
          v64 = WORD2(v284);
        v373 = v64;
        v65 = 0;
        v308 = 0;
        if ( v64 > 0x40000 || v16 > 0x40000 )
        {
          v67 = 1024;
LABEL_229:
          v282 = v67;
          LODWORD(v285[3]) = v67;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7492;
          v285[6] = 0;
        }
        else
        {
          v66 = (v64 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v66 + v16 > v19 )
            {
              v67 = 0x80000000;
              goto LABEL_229;
            }
            v65 = &v14[v16];
            v308 = &v14[v16];
          }
          v16 += v66;
          uBytes = v16;
          v285[2] = v16;
        }
        v63 = cbor_value_copy_string(v283, v65, &v373, v283);
        v18 = v282;
        v327 = v373;
        if ( !v63 )
          goto LABEL_123;
      }
      if ( !v18 )
        goto LABEL_235;
    }
LABEL_123:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_128;
    if ( BYTE6(v287) != 0xA0 )
    {
      v43 = 260;
LABEL_126:
      v18 = v43;
      v282 = v43;
      LODWORD(v285[3]) = v43;
      v44 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7495;
      goto LABEL_127;
    }
    v43 = cbor_value_map_find_value(cbMultiByte, "newPin", v283);
    if ( v43 )
      goto LABEL_126;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v43 = 259;
    if ( !v43 )
    {
      v328 = 0;
      v349 = 0;
      if ( v282 )
      {
        v68 = 260;
        v328 = 0;
        goto LABEL_260;
      }
      if ( BYTE6(v284) != 64 )
      {
        v68 = 260;
        v309 = 0;
        v328 = 0;
LABEL_262:
        v18 = v68;
        v282 = v68;
        LODWORD(v285[3]) = v68;
        v44 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7497;
LABEL_127:
        v285[6] = 0;
        v285[4] = v44;
        goto LABEL_128;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v68 = 2;
LABEL_260:
        v309 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v69 = cbor_value_decode_int64_internal(v283, v282);
        else
          v69 = WORD2(v284);
        v349 = v69;
        v70 = 0;
        v309 = 0;
        if ( v69 > 0x40000 || v16 > 0x40000 )
        {
          v72 = 1024;
LABEL_256:
          v282 = v72;
          LODWORD(v285[3]) = v72;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7497;
          v285[6] = 0;
        }
        else
        {
          v71 = (v69 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v71 + v16 > v19 )
            {
              v72 = 0x80000000;
              goto LABEL_256;
            }
            v70 = &v14[v16];
            v309 = &v14[v16];
          }
          v16 += v71;
          uBytes = v16;
          v285[2] = v16;
        }
        v68 = cbor_value_copy_string(v283, v70, &v349, v283);
        v18 = v282;
        v328 = v349;
        if ( !v68 )
          goto LABEL_128;
      }
      if ( !v18 )
        goto LABEL_262;
    }
LABEL_128:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_133;
    if ( BYTE6(v287) != 0xA0 )
    {
      v45 = 260;
LABEL_131:
      v18 = v45;
      v282 = v45;
      LODWORD(v285[3]) = v45;
      v46 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7500;
      goto LABEL_132;
    }
    v45 = cbor_value_map_find_value(cbMultiByte, "hmacSalt", v283);
    if ( v45 )
      goto LABEL_131;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v45 = 259;
    if ( !v45 )
    {
      v329 = 0;
      v350 = 0;
      if ( v282 )
      {
        v73 = 260;
        v329 = 0;
        goto LABEL_287;
      }
      if ( BYTE6(v284) != 64 )
      {
        v73 = 260;
        v310 = 0;
        v329 = 0;
LABEL_289:
        v18 = v73;
        v282 = v73;
        LODWORD(v285[3]) = v73;
        v46 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7502;
LABEL_132:
        v285[6] = 0;
        v285[4] = v46;
        goto LABEL_133;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v73 = 2;
LABEL_287:
        v310 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v74 = cbor_value_decode_int64_internal(v283, v282);
        else
          v74 = WORD2(v284);
        v350 = v74;
        v75 = 0;
        v310 = 0;
        if ( v74 > 0x40000 || v16 > 0x40000 )
        {
          v77 = 1024;
LABEL_283:
          v282 = v77;
          LODWORD(v285[3]) = v77;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7502;
          v285[6] = 0;
        }
        else
        {
          v76 = (v74 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v76 + v16 > v19 )
            {
              v77 = 0x80000000;
              goto LABEL_283;
            }
            v75 = &v14[v16];
            v310 = &v14[v16];
          }
          v16 += v76;
          uBytes = v16;
          v285[2] = v16;
        }
        v73 = cbor_value_copy_string(v283, v75, &v350, v283);
        v18 = v282;
        v329 = v350;
        if ( !v73 )
          goto LABEL_133;
      }
      if ( !v18 )
        goto LABEL_289;
    }
LABEL_133:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_138;
    if ( BYTE6(v287) != 0xA0 )
    {
      v47 = 260;
LABEL_136:
      v18 = v47;
      v282 = v47;
      LODWORD(v285[3]) = v47;
      v48 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7505;
      goto LABEL_137;
    }
    v47 = cbor_value_map_find_value(cbMultiByte, "userIdPrefix", v283);
    if ( v47 )
      goto LABEL_136;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v47 = 259;
    if ( !v47 )
    {
      v330 = 0;
      v351 = 0;
      if ( v282 )
      {
        v78 = 260;
        v330 = 0;
        goto LABEL_314;
      }
      if ( BYTE6(v284) != 64 )
      {
        v78 = 260;
        v323 = 0;
        v330 = 0;
LABEL_316:
        v18 = v78;
        v282 = v78;
        LODWORD(v285[3]) = v78;
        v48 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7507;
LABEL_137:
        v285[6] = 0;
        v285[4] = v48;
        goto LABEL_138;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v78 = 2;
LABEL_314:
        v323 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v79 = cbor_value_decode_int64_internal(v283, v282);
        else
          v79 = WORD2(v284);
        v351 = v79;
        v80 = 0;
        v323 = 0;
        if ( v79 > 0x40000 || v16 > 0x40000 )
        {
          v82 = 1024;
LABEL_310:
          v282 = v82;
          LODWORD(v285[3]) = v82;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7507;
          v285[6] = 0;
        }
        else
        {
          v81 = (v79 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v14 )
          {
            if ( v81 + v16 > v19 )
            {
              v82 = 0x80000000;
              goto LABEL_310;
            }
            v80 = &v14[v16];
            v323 = &v14[v16];
          }
          v16 += v81;
          uBytes = v16;
          v285[2] = v16;
        }
        v78 = cbor_value_copy_string(v283, v80, &v351, v283);
        v18 = v282;
        v330 = v351;
        if ( !v78 )
          goto LABEL_138;
      }
      if ( !v18 )
        goto LABEL_316;
    }
LABEL_138:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_142;
    if ( BYTE6(v287) != 0xA0 )
    {
      v49 = 260;
LABEL_141:
      v18 = v49;
      v282 = v49;
      LODWORD(v285[3]) = v49;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7510;
      v285[6] = 0;
LABEL_142:
      v50 = v295;
      goto LABEL_143;
    }
    v49 = cbor_value_map_find_value(cbMultiByte, "u2fAppId", v283);
    if ( v49 )
      goto LABEL_141;
    if ( BYTE6(v284) == 0xFF )
      v49 = 259;
    if ( v49 )
    {
      v18 = v282;
      v50 = v295;
      goto LABEL_143;
    }
    v347 = 0;
    if ( v282 )
    {
      v84 = 260;
    }
    else if ( BYTE6(v284) == 96 )
    {
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v84 = 2;
      }
      else
      {
        v85 = (v284 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v283, v83) : WORD2(v284);
        v347 = v85;
        if ( v85 <= 0x40000 )
        {
          v86 = LocalAlloc(0x40u, (unsigned int)(v85 + 1));
          if ( v86 )
          {
            v390 = 0;
            v389[1] = 0;
            v84 = cbor_value_copy_string(v283, v86, &v347, v283);
            if ( !v84 )
            {
              v13 = v347;
              goto LABEL_338;
            }
            LocalFree(v86);
          }
          else
          {
            v84 = 0x80000000;
          }
        }
        else
        {
          v84 = 1024;
        }
      }
    }
    else
    {
      v84 = 260;
    }
    v86 = 0;
    v347 = 0;
LABEL_338:
    v369 = v13;
    v331 = 0;
    if ( v84 )
    {
      v50 = v295;
      if ( !v282 )
      {
        LODWORD(v285[5]) = 7512;
        v282 = v84;
        LODWORD(v285[3]) = v84;
        v285[4] = *(_QWORD *)&v283[2];
        v285[6] = 0;
      }
      goto LABEL_355;
    }
    v87 = v13 + 1;
    v88 = 0;
    if ( v282 )
    {
      v50 = v295;
      goto LABEL_352;
    }
    if ( v87 > 0x40000 || v16 > 0x40000 )
    {
      v50 = v295;
      v90 = 1024;
    }
    else
    {
      v50 = v295;
      v89 = (v87 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v300 )
        goto LABEL_348;
      if ( v89 + v16 <= v295 )
      {
        v88 = &v300[v16];
        v331 = &v300[v16];
LABEL_348:
        v16 += v89;
        uBytes = v16;
        v285[2] = v16;
LABEL_352:
        if ( v88 )
          memcpy_0(v88, v86, v87);
        goto LABEL_354;
      }
      v90 = 0x80000000;
    }
    v282 = v90;
    LODWORD(v285[3]) = v90;
    v285[4] = *(_QWORD *)&v283[2];
    LODWORD(v285[5]) = 7512;
    v285[6] = 0;
    v331 = 0;
LABEL_354:
    v14 = v300;
LABEL_355:
    if ( v86 )
      LocalFree(v86);
    v18 = v282;
    if ( v84 && !v282 )
    {
      v18 = v84;
      v282 = v84;
      LODWORD(v285[3]) = v84;
      v285[4] = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7512;
      v285[6] = 0;
    }
LABEL_143:
    if ( (v297 & 0xFFFFFFFB) == 0 && !v15 && !v18 )
    {
      v18 = 769;
      v282 = 769;
      LODWORD(v285[3]) = 769;
      v285[4] = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7517;
      v285[6] = 0;
    }
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_375;
    if ( BYTE6(v287) != 0xA0 )
    {
      v51 = 260;
LABEL_150:
      v18 = v51;
      v282 = v51;
      LODWORD(v285[3]) = v51;
      v52 = 0;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7521;
      v285[6] = 0;
      goto LABEL_376;
    }
    v51 = cbor_value_map_find_value(cbMultiByte, "deviceInfoList", v283);
    if ( v51 )
      goto LABEL_150;
    if ( BYTE6(v284) == 0xFF )
      v51 = 259;
    if ( v51 )
    {
      v18 = v282;
      goto LABEL_375;
    }
    v368 = 0;
    if ( !v282 )
    {
      if ( v16 > 0x40000 )
      {
        v91 = 1024;
        goto LABEL_373;
      }
      if ( v14 )
      {
        if ( v16 + 16 > v50 )
        {
          v91 = 0x80000000;
LABEL_373:
          LODWORD(v285[3]) = v91;
          LODWORD(v285[5]) = 7525;
          v285[6] = 0;
          goto LABEL_374;
        }
        v368 = &v14[v16];
      }
      v285[2] = v16 + 16;
    }
LABEL_374:
    my_cbor_decode_device_info_list((int)v285);
    v16 = v285[2];
    v18 = v285[3];
    v282 = v285[3];
    uBytes = v285[2];
LABEL_375:
    v52 = 0;
LABEL_376:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_380;
    if ( BYTE6(v287) != 0xA0 )
    {
      v92 = 260;
LABEL_379:
      v18 = v92;
      v282 = v92;
      LODWORD(v285[3]) = v92;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7530;
      v285[6] = 0;
      goto LABEL_380;
    }
    v92 = cbor_value_map_find_value(cbMultiByte, "webAuthNPara", v283);
    if ( v92 )
      goto LABEL_379;
    if ( BYTE6(v284) == 0xFF )
      v92 = 259;
    if ( v92 )
    {
      v18 = v282;
    }
    else
    {
      my_cbor_decode_web_authn_para((int)v285);
      v16 = v285[2];
      v18 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_380:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_385;
    if ( BYTE6(v287) != 0xA0 )
    {
      v93 = 260;
LABEL_383:
      v18 = v93;
      v282 = v93;
      LODWORD(v285[3]) = v93;
      v94 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7535;
      goto LABEL_384;
    }
    v93 = cbor_value_map_find_value(cbMultiByte, "hmacSecretSaltValues", v283);
    if ( v93 )
      goto LABEL_383;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v93 = 259;
    if ( !v93 )
    {
      v332 = 0;
      v352 = 0;
      if ( v282 )
      {
        v110 = 260;
        v332 = 0;
        goto LABEL_458;
      }
      if ( BYTE6(v284) != 64 )
      {
        v110 = 260;
        v312 = 0;
        v332 = 0;
LABEL_460:
        v18 = v110;
        v282 = v110;
        LODWORD(v285[3]) = v110;
        v94 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7537;
LABEL_384:
        v285[6] = 0;
        v285[4] = v94;
        goto LABEL_385;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v110 = 2;
LABEL_458:
        v312 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v111 = cbor_value_decode_int64_internal(v283, v282);
        else
          v111 = WORD2(v284);
        v352 = v111;
        v112 = 0;
        v312 = 0;
        if ( v111 > 0x40000 || v16 > 0x40000 )
        {
          v114 = 1024;
LABEL_454:
          v282 = v114;
          LODWORD(v285[3]) = v114;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7537;
          v285[6] = 0;
        }
        else
        {
          v113 = (v111 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v113 + v16 > v285[1] )
            {
              v114 = 0x80000000;
              goto LABEL_454;
            }
            v112 = v16 + v285[0];
            v312 = v16 + v285[0];
          }
          v16 += v113;
          uBytes = v16;
          v285[2] = v16;
        }
        v110 = cbor_value_copy_string(v283, v112, &v352, v283);
        v18 = v282;
        v332 = v352;
        if ( !v110 )
          goto LABEL_385;
      }
      if ( !v18 )
        goto LABEL_460;
    }
LABEL_385:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_390;
    if ( BYTE6(v287) != 0xA0 )
    {
      v95 = 260;
LABEL_388:
      v18 = v95;
      v282 = v95;
      LODWORD(v285[3]) = v95;
      v96 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7540;
      goto LABEL_389;
    }
    v95 = cbor_value_map_find_value(cbMultiByte, "browserInPrivateMode", v283);
    if ( v95 )
      goto LABEL_388;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v95 = 259;
    if ( !v95 )
    {
      v396 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v284) != 0xF5 )
        {
          v115 = 260;
LABEL_469:
          v18 = v115;
          v282 = v115;
          LODWORD(v285[3]) = v115;
          v96 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7542;
LABEL_389:
          v285[6] = 0;
          v285[4] = v96;
          goto LABEL_390;
        }
        v396 = WORD2(v284) != 0;
        v115 = cbor_value_advance_fixed(v283);
        if ( v115 )
          goto LABEL_469;
        v18 = v282;
      }
    }
LABEL_390:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_394;
    if ( BYTE6(v287) != 0xA0 )
    {
      v97 = 260;
LABEL_393:
      v18 = v97;
      v282 = v97;
      LODWORD(v285[3]) = v97;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7545;
      v285[6] = 0;
      goto LABEL_394;
    }
    v97 = cbor_value_map_find_value(cbMultiByte, "hybridQrCodeState", v283);
    if ( v97 )
      goto LABEL_393;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v97 = 259;
    if ( !v97 )
    {
      v370 = 0;
      v116 = 0;
      if ( !v282 )
      {
        if ( v16 > 0x40000 )
        {
          v18 = 1024;
LABEL_483:
          v282 = v18;
          LODWORD(v285[3]) = v18;
          LODWORD(v285[5]) = 7258;
          v285[6] = 0;
        }
        else
        {
          if ( v285[0] )
          {
            if ( v16 + 32 > v285[1] )
            {
              v18 = 0x80000000;
              goto LABEL_483;
            }
            v116 = v16 + v285[0];
            v370 = v16 + v285[0];
          }
          v16 += 32LL;
          uBytes = v16;
          v285[2] = v16;
        }
      }
      v305 = 0;
      v117 = 0;
      v118 = 0;
      v119 = 0;
      v120 = 0;
      v304 = 0;
      if ( !v18 )
      {
        if ( BYTE6(v284) != 0xA0 )
        {
          v121 = 260;
          goto LABEL_487;
        }
        v121 = cbor_value_map_find_value(v283, "privateKey", &v304);
        if ( v121 )
        {
LABEL_487:
          v18 = v121;
          v282 = v121;
          LODWORD(v285[3]) = v121;
          v122 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7267;
          goto LABEL_488;
        }
        if ( BYTE6(v305) == 0xFF )
          v121 = 259;
        v18 = v282;
        if ( !v121 )
        {
          v353 = 0;
          if ( v282 )
          {
            v125 = 260;
            goto LABEL_520;
          }
          if ( BYTE6(v305) != 64 )
          {
            v125 = 260;
            goto LABEL_521;
          }
          if ( (v305 & 0x400000000000000LL) != 0 )
          {
            v125 = 2;
            goto LABEL_520;
          }
          v126 = (v305 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(&v304, v282) : WORD2(v305);
          v353 = v126;
          if ( v126 > 0x40000 || v16 > 0x40000 )
          {
            v128 = 1024;
LABEL_516:
            v282 = v128;
            LODWORD(v285[3]) = v128;
            v285[4] = *((_QWORD *)&v304 + 1);
            LODWORD(v285[5]) = 7269;
            v285[6] = 0;
          }
          else
          {
            v127 = (v126 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            if ( v285[0] )
            {
              if ( v127 + v16 > v285[1] )
              {
                v128 = 0x80000000;
                goto LABEL_516;
              }
              v117 = v16 + v285[0];
            }
            v16 += v127;
            uBytes = v16;
            v285[2] = v16;
          }
          v125 = cbor_value_copy_string(&v304, v117, &v353, &v304);
          v118 = v353;
          v18 = v282;
          if ( v125 )
          {
LABEL_520:
            if ( !v18 )
            {
LABEL_521:
              v18 = v125;
              v282 = v125;
              LODWORD(v285[3]) = v125;
              v122 = *((_QWORD *)&v304 + 1);
              LODWORD(v285[5]) = 7269;
LABEL_488:
              v285[6] = 0;
              v285[4] = v122;
            }
          }
        }
      }
      v305 = 0;
      v304 = 0;
      if ( !v18 )
      {
        if ( BYTE6(v284) != 0xA0 )
        {
          v123 = 260;
          goto LABEL_492;
        }
        v123 = cbor_value_map_find_value(v283, "symetricSecret", &v304);
        if ( v123 )
        {
LABEL_492:
          v18 = v123;
          v282 = v123;
          LODWORD(v285[3]) = v123;
          v124 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7273;
          goto LABEL_493;
        }
        if ( BYTE6(v305) == 0xFF )
          v123 = 259;
        v18 = v282;
        if ( !v123 )
        {
          v354 = 0;
          if ( v282 )
          {
            v129 = 260;
            goto LABEL_546;
          }
          if ( BYTE6(v305) != 64 )
          {
            v129 = 260;
            goto LABEL_547;
          }
          if ( (v305 & 0x400000000000000LL) != 0 )
          {
            v129 = 2;
            goto LABEL_546;
          }
          v130 = (v305 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(&v304, v282) : WORD2(v305);
          v354 = v130;
          if ( v130 > 0x40000 || v16 > 0x40000 )
          {
            v132 = 1024;
LABEL_542:
            v282 = v132;
            LODWORD(v285[3]) = v132;
            v285[4] = *((_QWORD *)&v304 + 1);
            LODWORD(v285[5]) = 7275;
            v285[6] = 0;
          }
          else
          {
            v131 = (v130 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            if ( v285[0] )
            {
              if ( v131 + v16 > v285[1] )
              {
                v132 = 0x80000000;
                goto LABEL_542;
              }
              v119 = v16 + v285[0];
            }
            v16 += v131;
            uBytes = v16;
            v285[2] = v16;
          }
          v129 = cbor_value_copy_string(&v304, v119, &v354, &v304);
          v120 = v354;
          v18 = v282;
          if ( v129 )
          {
LABEL_546:
            if ( !v18 )
            {
LABEL_547:
              v18 = v129;
              v282 = v129;
              LODWORD(v285[3]) = v129;
              v124 = *((_QWORD *)&v304 + 1);
              LODWORD(v285[5]) = 7275;
LABEL_493:
              v285[6] = 0;
              v285[4] = v124;
            }
          }
        }
      }
      if ( v116 )
      {
        *(_QWORD *)(v116 + 8) = v117;
        *(_DWORD *)v116 = v118;
        *(_QWORD *)(v116 + 24) = v119;
        *(_DWORD *)(v116 + 16) = v120;
      }
    }
LABEL_394:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_398;
    if ( BYTE6(v287) != 0xA0 )
    {
      v98 = 260;
LABEL_397:
      v18 = v98;
      v282 = v98;
      LODWORD(v285[3]) = v98;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7550;
      v285[6] = 0;
      goto LABEL_398;
    }
    v98 = cbor_value_map_find_value(cbMultiByte, "linkedData", v283);
    if ( v98 )
      goto LABEL_397;
    if ( BYTE6(v284) == 0xFF )
      v98 = 259;
    if ( v98 )
    {
      v18 = v282;
    }
    else
    {
      my_cbor_decode_hybrid_storage_linked_data((int)v285);
      v16 = v285[2];
      v18 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_398:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_403;
    if ( BYTE6(v287) != 0xA0 )
    {
      v99 = 260;
LABEL_401:
      v18 = v99;
      v282 = v99;
      LODWORD(v285[3]) = v99;
      v100 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7555;
      goto LABEL_402;
    }
    v99 = cbor_value_map_find_value(cbMultiByte, "autoFill", v283);
    if ( v99 )
      goto LABEL_401;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v99 = 259;
    if ( !v99 )
    {
      v289 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v284) != 0xF5 )
        {
          v133 = 260;
LABEL_562:
          v18 = v133;
          v282 = v133;
          LODWORD(v285[3]) = v133;
          v100 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7557;
LABEL_402:
          v285[6] = 0;
          v285[4] = v100;
          goto LABEL_403;
        }
        v289 = WORD2(v284) != 0;
        v133 = cbor_value_advance_fixed(v283);
        if ( v133 )
          goto LABEL_562;
        v18 = v282;
      }
    }
LABEL_403:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_408;
    if ( BYTE6(v287) != 0xA0 )
    {
      v101 = 260;
LABEL_406:
      v18 = v101;
      v282 = v101;
      LODWORD(v285[3]) = v101;
      v102 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7560;
      goto LABEL_407;
    }
    v101 = cbor_value_map_find_value(cbMultiByte, "filterHybridTransport", v283);
    if ( v101 )
      goto LABEL_406;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v101 = 259;
    if ( !v101 )
    {
      v290 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v284) != 0xF5 )
        {
          v134 = 260;
LABEL_572:
          v18 = v134;
          v282 = v134;
          LODWORD(v285[3]) = v134;
          v102 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7562;
LABEL_407:
          v285[6] = 0;
          v285[4] = v102;
          goto LABEL_408;
        }
        v290 = WORD2(v284) != 0;
        v134 = cbor_value_advance_fixed(v283);
        if ( v134 )
          goto LABEL_572;
        v18 = v282;
      }
    }
LABEL_408:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_413;
    if ( BYTE6(v287) != 0xA0 )
    {
      v103 = 260;
LABEL_411:
      v18 = v103;
      v282 = v103;
      LODWORD(v285[3]) = v103;
      v104 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7565;
      goto LABEL_412;
    }
    v103 = cbor_value_map_find_value(cbMultiByte, "json", v283);
    if ( v103 )
      goto LABEL_411;
    v18 = v282;
    if ( BYTE6(v284) == 0xFF )
      v103 = 259;
    if ( !v103 )
    {
      v333 = 0;
      v355 = 0;
      if ( v282 )
      {
        v135 = 260;
        v333 = 0;
        goto LABEL_598;
      }
      if ( BYTE6(v284) != 64 )
      {
        v135 = 260;
        v313 = 0;
        v333 = 0;
LABEL_600:
        v18 = v135;
        v282 = v135;
        LODWORD(v285[3]) = v135;
        v104 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7567;
LABEL_412:
        v285[6] = 0;
        v285[4] = v104;
        goto LABEL_413;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v135 = 2;
LABEL_598:
        v313 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v136 = cbor_value_decode_int64_internal(v283, v282);
        else
          v136 = WORD2(v284);
        v355 = v136;
        v137 = 0;
        v313 = 0;
        if ( v136 > 0x40000 || v16 > 0x40000 )
        {
          v139 = 1024;
LABEL_594:
          v282 = v139;
          LODWORD(v285[3]) = v139;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7567;
          v285[6] = 0;
        }
        else
        {
          v138 = (v136 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v138 + v16 > v285[1] )
            {
              v139 = 0x80000000;
              goto LABEL_594;
            }
            v137 = v16 + v285[0];
            v313 = v16 + v285[0];
          }
          v16 += v138;
          uBytes = v16;
          v285[2] = v16;
        }
        v135 = cbor_value_copy_string(v283, v137, &v355, v283);
        v18 = v282;
        v333 = v355;
        if ( !v135 )
          goto LABEL_413;
      }
      if ( !v18 )
        goto LABEL_600;
    }
LABEL_413:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_417;
    if ( BYTE6(v287) != 0xA0 )
    {
      v105 = 260;
LABEL_416:
      v18 = v105;
      v282 = v105;
      LODWORD(v285[3]) = v105;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7570;
      v285[6] = 0;
      goto LABEL_417;
    }
    v105 = cbor_value_map_find_value(cbMultiByte, "rpId", v283);
    if ( v105 )
      goto LABEL_416;
    if ( BYTE6(v284) == 0xFF )
      v105 = 259;
    if ( v105 )
    {
      v18 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v386, 7572, v281);
      v16 = v285[2];
      v18 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_417:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v18 )
      goto LABEL_422;
    if ( BYTE6(v287) != 0xA0 )
    {
      v106 = 260;
LABEL_420:
      v282 = v106;
      LODWORD(v285[3]) = v106;
      v107 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7575;
      goto LABEL_421;
    }
    v106 = cbor_value_map_find_value(cbMultiByte, "credentialDetails", v283);
    if ( v106 )
      goto LABEL_420;
    if ( BYTE6(v284) == 0xFF )
      v106 = 259;
    if ( !v106 )
    {
      v140 = v282;
      v334 = 0;
      v356 = 0;
      if ( v282 )
      {
        v141 = 260;
        v334 = 0;
        goto LABEL_631;
      }
      if ( BYTE6(v284) != 64 )
      {
        v141 = 260;
        v314 = 0;
        v334 = 0;
LABEL_633:
        v282 = v141;
        LODWORD(v285[3]) = v141;
        v107 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7577;
LABEL_421:
        v285[6] = 0;
        v285[4] = v107;
        goto LABEL_422;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v141 = 2;
LABEL_631:
        v314 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v142 = cbor_value_decode_int64_internal(v283, 0);
        else
          v142 = WORD2(v284);
        v356 = v142;
        v143 = 0;
        v314 = 0;
        if ( v142 > 0x40000 || v16 > 0x40000 )
        {
          v140 = 1024;
LABEL_627:
          v285[4] = *(_QWORD *)&v283[2];
          v282 = v140;
          LODWORD(v285[3]) = v140;
          LODWORD(v285[5]) = 7577;
          v285[6] = 0;
        }
        else
        {
          v144 = (v142 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v144 + v16 > v285[1] )
            {
              v140 = 0x80000000;
              goto LABEL_627;
            }
            v143 = v16 + v285[0];
            v314 = v16 + v285[0];
          }
          v16 += v144;
          uBytes = v16;
          v285[2] = v16;
        }
        v141 = cbor_value_copy_string(v283, v143, &v356, v283);
        v334 = v356;
        if ( !v141 )
          goto LABEL_422;
      }
      if ( !v140 )
        goto LABEL_633;
    }
LABEL_422:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
      goto LABEL_723;
    v108 = v282;
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( !v282 )
    {
      if ( BYTE6(v287) != 0xA0 )
      {
        v109 = 260;
LABEL_426:
        v108 = v109;
        v282 = v109;
        LODWORD(v285[3]) = v109;
        v285[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v285[5]) = 7582;
        v285[6] = 0;
        goto LABEL_640;
      }
      v109 = cbor_value_map_find_value(cbMultiByte, "pluginAuthenticatorName", v283);
      if ( v109 )
        goto LABEL_426;
      if ( BYTE6(v284) == 0xFF )
        v109 = 259;
      if ( v109 )
      {
        v108 = 0;
      }
      else
      {
        my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v387, 7584, v281);
        v16 = v285[2];
        v108 = v285[3];
        v282 = v285[3];
        uBytes = v285[2];
      }
    }
LABEL_640:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_644;
    if ( BYTE6(v287) != 0xA0 )
    {
      v145 = 260;
LABEL_643:
      v108 = v145;
      v282 = v145;
      LODWORD(v285[3]) = v145;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7587;
      v285[6] = 0;
      goto LABEL_644;
    }
    v145 = cbor_value_map_find_value(cbMultiByte, "pluginClsId", v283);
    if ( v145 )
      goto LABEL_643;
    if ( BYTE6(v284) == 0xFF )
      v145 = 259;
    if ( v145 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v375, 7589, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_644:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_648;
    if ( BYTE6(v287) != 0xA0 )
    {
      v146 = 260;
LABEL_647:
      v108 = v146;
      v282 = v146;
      LODWORD(v285[3]) = v146;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7592;
      v285[6] = 0;
      goto LABEL_648;
    }
    v146 = cbor_value_map_find_value(cbMultiByte, "pluginNewClsId", v283);
    if ( v146 )
      goto LABEL_647;
    if ( BYTE6(v284) == 0xFF )
      v146 = 259;
    if ( v146 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v376, 7594, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_648:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_652;
    if ( BYTE6(v287) != 0xA0 )
    {
      v147 = 260;
LABEL_651:
      v108 = v147;
      v282 = v147;
      LODWORD(v285[3]) = v147;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7597;
      v285[6] = 0;
      goto LABEL_652;
    }
    v147 = cbor_value_map_find_value(cbMultiByte, "pluginLightLogo", v283);
    if ( v147 )
      goto LABEL_651;
    if ( BYTE6(v284) == 0xFF )
      v147 = 259;
    if ( v147 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v384, 7599, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_652:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_656;
    if ( BYTE6(v287) != 0xA0 )
    {
      v148 = 260;
LABEL_655:
      v108 = v148;
      v282 = v148;
      LODWORD(v285[3]) = v148;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7602;
      v285[6] = 0;
      goto LABEL_656;
    }
    v148 = cbor_value_map_find_value(cbMultiByte, "pluginDarkLogo", v283);
    if ( v148 )
      goto LABEL_655;
    if ( BYTE6(v284) == 0xFF )
      v148 = 259;
    if ( v148 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v378, 7604, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_656:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_661;
    if ( BYTE6(v287) != 0xA0 )
    {
      v149 = 260;
LABEL_659:
      v108 = v149;
      v282 = v149;
      LODWORD(v285[3]) = v149;
      v150 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7607;
LABEL_660:
      v285[6] = 0;
      v285[4] = v150;
      goto LABEL_661;
    }
    v149 = cbor_value_map_find_value(cbMultiByte, "authenticatorInfoLogoRequestType", v283);
    if ( v149 )
      goto LABEL_659;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v149 = 259;
    if ( !v149 )
    {
      v301 = -1;
      if ( v282 )
      {
        v185 = 260;
      }
      else
      {
        if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
        {
          v185 = 260;
        }
        else
        {
          if ( (v284 & 0x100000000000000LL) != 0 )
            v186 = cbor_value_decode_int64_internal(v283, v282);
          else
            v186 = WORD2(v284);
          v185 = cbor_value_advance_fixed(v283);
          if ( !v185 )
          {
            v108 = v282;
            if ( v186 <= 0xFFFFFFFF )
            {
              v301 = v186;
              goto LABEL_661;
            }
            v185 = 1024;
            goto LABEL_775;
          }
        }
        v108 = v185;
        v285[4] = *(_QWORD *)&v283[2];
        v282 = v185;
        LODWORD(v285[3]) = v185;
        LODWORD(v285[5]) = 7609;
        v285[6] = 0;
      }
LABEL_775:
      if ( !v108 )
      {
        v150 = *(_QWORD *)&v283[2];
        v108 = v185;
        v282 = v185;
        LODWORD(v285[3]) = v185;
        LODWORD(v285[5]) = 7609;
        goto LABEL_660;
      }
    }
LABEL_661:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_666;
    if ( BYTE6(v287) != 0xA0 )
    {
      v151 = 260;
LABEL_664:
      v108 = v151;
      v282 = v151;
      LODWORD(v285[3]) = v151;
      v152 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7612;
      goto LABEL_665;
    }
    v151 = cbor_value_map_find_value(cbMultiByte, "pluginIdKey", v283);
    if ( v151 )
      goto LABEL_664;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v151 = 259;
    if ( !v151 )
    {
      v335 = 0;
      v357 = 0;
      if ( v282 )
      {
        v187 = 260;
        v335 = 0;
        goto LABEL_801;
      }
      if ( BYTE6(v284) != 64 )
      {
        v187 = 260;
        v315 = 0;
        v335 = 0;
LABEL_803:
        v108 = v187;
        v282 = v187;
        LODWORD(v285[3]) = v187;
        v152 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7614;
LABEL_665:
        v285[6] = 0;
        v285[4] = v152;
        goto LABEL_666;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v187 = 2;
LABEL_801:
        v315 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v188 = cbor_value_decode_int64_internal(v283, v282);
        else
          v188 = WORD2(v284);
        v357 = v188;
        v189 = 0;
        v315 = 0;
        if ( v188 > 0x40000 || v16 > 0x40000 )
        {
          v191 = 1024;
LABEL_797:
          v282 = v191;
          LODWORD(v285[3]) = v191;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7614;
          v285[6] = 0;
        }
        else
        {
          v190 = (v188 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v190 + v16 > v285[1] )
            {
              v191 = 0x80000000;
              goto LABEL_797;
            }
            v189 = v16 + v285[0];
            v315 = v16 + v285[0];
          }
          v16 += v190;
          uBytes = v16;
          v285[2] = v16;
        }
        v187 = cbor_value_copy_string(v283, v189, &v357, v283);
        v108 = v282;
        v335 = v357;
        if ( !v187 )
          goto LABEL_666;
      }
      if ( !v108 )
        goto LABEL_803;
    }
LABEL_666:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_671;
    if ( BYTE6(v287) != 0xA0 )
    {
      v153 = 260;
LABEL_669:
      v108 = v153;
      v282 = v153;
      LODWORD(v285[3]) = v153;
      v154 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7617;
      goto LABEL_670;
    }
    v153 = cbor_value_map_find_value(cbMultiByte, "pluginAutofillScenarioSupported", v283);
    if ( v153 )
      goto LABEL_669;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v153 = 259;
    if ( !v153 )
    {
      v291 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v284) != 0xF5 )
        {
          v192 = 260;
LABEL_812:
          v108 = v192;
          v282 = v192;
          LODWORD(v285[3]) = v192;
          v154 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7619;
LABEL_670:
          v285[6] = 0;
          v285[4] = v154;
          goto LABEL_671;
        }
        v291 = WORD2(v284) != 0;
        v192 = cbor_value_advance_fixed(v283);
        if ( v192 )
          goto LABEL_812;
        v108 = v282;
      }
    }
LABEL_671:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_676;
    if ( BYTE6(v287) != 0xA0 )
    {
      v155 = 260;
LABEL_674:
      v108 = v155;
      v282 = v155;
      LODWORD(v285[3]) = v155;
      v156 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7622;
      goto LABEL_675;
    }
    v155 = cbor_value_map_find_value(cbMultiByte, "pluginAuthenticatorState", v283);
    if ( v155 )
      goto LABEL_674;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v155 = 259;
    if ( !v155 )
    {
      v336 = 0;
      v358 = 0;
      if ( v282 )
      {
        v193 = 260;
        v336 = 0;
        goto LABEL_838;
      }
      if ( BYTE6(v284) != 64 )
      {
        v193 = 260;
        v316 = 0;
        v336 = 0;
LABEL_840:
        v108 = v193;
        v282 = v193;
        LODWORD(v285[3]) = v193;
        v156 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7624;
LABEL_675:
        v285[6] = 0;
        v285[4] = v156;
        goto LABEL_676;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v193 = 2;
LABEL_838:
        v316 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v194 = cbor_value_decode_int64_internal(v283, v282);
        else
          v194 = WORD2(v284);
        v358 = v194;
        v195 = 0;
        v316 = 0;
        if ( v194 > 0x40000 || v16 > 0x40000 )
        {
          v197 = 1024;
LABEL_834:
          v282 = v197;
          LODWORD(v285[3]) = v197;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7624;
          v285[6] = 0;
        }
        else
        {
          v196 = (v194 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v196 + v16 > v285[1] )
            {
              v197 = 0x80000000;
              goto LABEL_834;
            }
            v195 = v16 + v285[0];
            v316 = v16 + v285[0];
          }
          v16 += v196;
          uBytes = v16;
          v285[2] = v16;
        }
        v193 = cbor_value_copy_string(v283, v195, &v358, v283);
        v108 = v282;
        v336 = v358;
        if ( !v193 )
          goto LABEL_676;
      }
      if ( !v108 )
        goto LABEL_840;
    }
LABEL_676:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_681;
    if ( BYTE6(v287) != 0xA0 )
    {
      v157 = 260;
LABEL_679:
      v108 = v157;
      v282 = v157;
      LODWORD(v285[3]) = v157;
      v158 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7627;
      goto LABEL_680;
    }
    v157 = cbor_value_map_find_value(cbMultiByte, "operationSignature", v283);
    if ( v157 )
      goto LABEL_679;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v157 = 259;
    if ( !v157 )
    {
      v337 = 0;
      v359 = 0;
      if ( v282 )
      {
        v198 = 260;
        v337 = 0;
        goto LABEL_865;
      }
      if ( BYTE6(v284) != 64 )
      {
        v198 = 260;
        v317 = 0;
        v337 = 0;
LABEL_867:
        v108 = v198;
        v282 = v198;
        LODWORD(v285[3]) = v198;
        v158 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7629;
LABEL_680:
        v285[6] = 0;
        v285[4] = v158;
        goto LABEL_681;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v198 = 2;
LABEL_865:
        v317 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v199 = cbor_value_decode_int64_internal(v283, v282);
        else
          v199 = WORD2(v284);
        v359 = v199;
        v200 = 0;
        v317 = 0;
        if ( v199 > 0x40000 || v16 > 0x40000 )
        {
          v202 = 1024;
LABEL_861:
          v282 = v202;
          LODWORD(v285[3]) = v202;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7629;
          v285[6] = 0;
        }
        else
        {
          v201 = (v199 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v201 + v16 > v285[1] )
            {
              v202 = 0x80000000;
              goto LABEL_861;
            }
            v200 = v16 + v285[0];
            v317 = v16 + v285[0];
          }
          v16 += v201;
          uBytes = v16;
          v285[2] = v16;
        }
        v198 = cbor_value_copy_string(v283, v200, &v359, v283);
        v108 = v282;
        v337 = v359;
        if ( !v198 )
          goto LABEL_681;
      }
      if ( !v108 )
        goto LABEL_867;
    }
LABEL_681:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_686;
    if ( BYTE6(v287) != 0xA0 )
    {
      v159 = 260;
LABEL_684:
      v108 = v159;
      v282 = v159;
      LODWORD(v285[3]) = v159;
      v160 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7632;
      goto LABEL_685;
    }
    v159 = cbor_value_map_find_value(cbMultiByte, "hwnd", v283);
    if ( v159 )
      goto LABEL_684;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v159 = 259;
    if ( !v159 )
    {
      v348 = -1;
      if ( !v282 )
      {
        if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
        {
          v204 = 260;
LABEL_881:
          v108 = v204;
          v282 = v204;
          LODWORD(v285[3]) = v204;
          v160 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7634;
LABEL_685:
          v285[6] = 0;
          v285[4] = v160;
          goto LABEL_686;
        }
        if ( (v284 & 0x100000000000000LL) != 0 )
          v203 = cbor_value_decode_int64_internal(v283, v282);
        else
          v203 = WORD2(v284);
        v348 = v203;
        v204 = cbor_value_advance_fixed(v283);
        if ( v204 )
          goto LABEL_881;
        v108 = v282;
      }
    }
LABEL_686:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_691;
    if ( BYTE6(v287) != 0xA0 )
    {
      v161 = 260;
LABEL_689:
      v108 = v161;
      v282 = v161;
      LODWORD(v285[3]) = v161;
      v162 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7637;
LABEL_690:
      v285[6] = 0;
      v285[4] = v162;
      goto LABEL_691;
    }
    v161 = cbor_value_map_find_value(cbMultiByte, "uvOperationType", v283);
    if ( v161 )
      goto LABEL_689;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v161 = 259;
    if ( !v161 )
    {
      v302 = -1;
      if ( v282 )
      {
        v205 = 260;
      }
      else
      {
        if ( BYTE6(v284) || (v284 & 0x200000000000000LL) != 0 )
        {
          v205 = 260;
        }
        else
        {
          if ( (v284 & 0x100000000000000LL) != 0 )
            v206 = cbor_value_decode_int64_internal(v283, v282);
          else
            v206 = WORD2(v284);
          v205 = cbor_value_advance_fixed(v283);
          if ( !v205 )
          {
            v108 = v282;
            if ( v206 <= 0xFFFFFFFF )
            {
              v302 = v206;
              goto LABEL_691;
            }
            v205 = 1024;
            goto LABEL_899;
          }
        }
        v108 = v205;
        v285[4] = *(_QWORD *)&v283[2];
        v282 = v205;
        LODWORD(v285[3]) = v205;
        LODWORD(v285[5]) = 7639;
        v285[6] = 0;
      }
LABEL_899:
      if ( !v108 )
      {
        v162 = *(_QWORD *)&v283[2];
        v108 = v205;
        v282 = v205;
        LODWORD(v285[3]) = v205;
        LODWORD(v285[5]) = 7639;
        goto LABEL_690;
      }
    }
LABEL_691:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_696;
    if ( BYTE6(v287) != 0xA0 )
    {
      v163 = 260;
LABEL_694:
      v108 = v163;
      v282 = v163;
      LODWORD(v285[3]) = v163;
      v164 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7642;
      goto LABEL_695;
    }
    v163 = cbor_value_map_find_value(cbMultiByte, "uvTransactionId", v283);
    if ( v163 )
      goto LABEL_694;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v163 = 259;
    if ( !v163 )
    {
      v338 = 0;
      v360 = 0;
      if ( v282 )
      {
        v207 = 260;
        v338 = 0;
        goto LABEL_925;
      }
      if ( BYTE6(v284) != 64 )
      {
        v207 = 260;
        v318 = 0;
        v338 = 0;
LABEL_927:
        v108 = v207;
        v282 = v207;
        LODWORD(v285[3]) = v207;
        v164 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7644;
LABEL_695:
        v285[6] = 0;
        v285[4] = v164;
        goto LABEL_696;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v207 = 2;
LABEL_925:
        v318 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v208 = cbor_value_decode_int64_internal(v283, v282);
        else
          v208 = WORD2(v284);
        v360 = v208;
        v209 = 0;
        v318 = 0;
        if ( v208 > 0x40000 || v16 > 0x40000 )
        {
          v211 = 1024;
LABEL_921:
          v282 = v211;
          LODWORD(v285[3]) = v211;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7644;
          v285[6] = 0;
        }
        else
        {
          v210 = (v208 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v210 + v16 > v285[1] )
            {
              v211 = 0x80000000;
              goto LABEL_921;
            }
            v209 = v16 + v285[0];
            v318 = (_OWORD *)(v16 + v285[0]);
          }
          v16 += v210;
          uBytes = v16;
          v285[2] = v16;
        }
        v207 = cbor_value_copy_string(v283, v209, &v360, v283);
        v108 = v282;
        v338 = v360;
        if ( !v207 )
          goto LABEL_696;
      }
      if ( !v108 )
        goto LABEL_927;
    }
LABEL_696:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_701;
    if ( BYTE6(v287) != 0xA0 )
    {
      v165 = 260;
LABEL_699:
      v108 = v165;
      v282 = v165;
      LODWORD(v285[3]) = v165;
      v166 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7647;
      goto LABEL_700;
    }
    v165 = cbor_value_map_find_value(cbMultiByte, "pluginUvOpRes", v283);
    if ( v165 )
      goto LABEL_699;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v165 = 259;
    if ( !v165 )
    {
      v339 = 0;
      v361 = 0;
      if ( v282 )
      {
        v212 = 260;
        v339 = 0;
        goto LABEL_952;
      }
      if ( BYTE6(v284) != 64 )
      {
        v212 = 260;
        v319 = 0;
        v339 = 0;
LABEL_954:
        v108 = v212;
        v282 = v212;
        LODWORD(v285[3]) = v212;
        v166 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7649;
LABEL_700:
        v285[6] = 0;
        v285[4] = v166;
        goto LABEL_701;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v212 = 2;
LABEL_952:
        v319 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v213 = cbor_value_decode_int64_internal(v283, v282);
        else
          v213 = WORD2(v284);
        v361 = v213;
        v214 = 0;
        v319 = 0;
        if ( v213 > 0x40000 || v16 > 0x40000 )
        {
          v216 = 1024;
LABEL_948:
          v282 = v216;
          LODWORD(v285[3]) = v216;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7649;
          v285[6] = 0;
        }
        else
        {
          v215 = (v213 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v215 + v16 > v285[1] )
            {
              v216 = 0x80000000;
              goto LABEL_948;
            }
            v214 = v16 + v285[0];
            v319 = v16 + v285[0];
          }
          v16 += v215;
          uBytes = v16;
          v285[2] = v16;
        }
        v212 = cbor_value_copy_string(v283, v214, &v361, v283);
        v108 = v282;
        v339 = v361;
        if ( !v212 )
          goto LABEL_701;
      }
      if ( !v108 )
        goto LABEL_954;
    }
LABEL_701:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_705;
    if ( BYTE6(v287) != 0xA0 )
    {
      v167 = 260;
LABEL_704:
      v108 = v167;
      v282 = v167;
      LODWORD(v285[3]) = v167;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7652;
      v285[6] = 0;
      goto LABEL_705;
    }
    v167 = cbor_value_map_find_value(cbMultiByte, "uvUsername", v283);
    if ( v167 )
      goto LABEL_704;
    if ( BYTE6(v284) == 0xFF )
      v167 = 259;
    if ( v167 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v379, 7654, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_705:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_709;
    if ( BYTE6(v287) != 0xA0 )
    {
      v168 = 260;
LABEL_708:
      v108 = v168;
      v282 = v168;
      LODWORD(v285[3]) = v168;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7657;
      v285[6] = 0;
      goto LABEL_709;
    }
    v168 = cbor_value_map_find_value(cbMultiByte, "uvContext", v283);
    if ( v168 )
      goto LABEL_708;
    if ( BYTE6(v284) == 0xFF )
      v168 = 259;
    if ( v168 )
    {
      v108 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v380, 7659, v281);
      v16 = v285[2];
      v108 = v285[3];
      v282 = v285[3];
      uBytes = v285[2];
    }
LABEL_709:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_714;
    if ( BYTE6(v287) != 0xA0 )
    {
      v169 = 260;
LABEL_712:
      v108 = v169;
      v282 = v169;
      LODWORD(v285[3]) = v169;
      v170 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7662;
      goto LABEL_713;
    }
    v169 = cbor_value_map_find_value(cbMultiByte, "authenticatorInfo", v283);
    if ( v169 )
      goto LABEL_712;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v169 = 259;
    if ( !v169 )
    {
      v340 = 0;
      v362 = 0;
      if ( v282 )
      {
        v217 = 260;
        v340 = 0;
        goto LABEL_991;
      }
      if ( BYTE6(v284) != 64 )
      {
        v217 = 260;
        v320 = 0;
        v340 = 0;
LABEL_993:
        v108 = v217;
        v282 = v217;
        LODWORD(v285[3]) = v217;
        v170 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7664;
LABEL_713:
        v285[6] = 0;
        v285[4] = v170;
        goto LABEL_714;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v217 = 2;
LABEL_991:
        v320 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v218 = cbor_value_decode_int64_internal(v283, v282);
        else
          v218 = WORD2(v284);
        v362 = v218;
        v219 = 0;
        v320 = 0;
        if ( v218 > 0x40000 || v16 > 0x40000 )
        {
          v221 = 1024;
LABEL_987:
          v282 = v221;
          LODWORD(v285[3]) = v221;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7664;
          v285[6] = 0;
        }
        else
        {
          v220 = (v218 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v220 + v16 > v285[1] )
            {
              v221 = 0x80000000;
              goto LABEL_987;
            }
            v219 = v16 + v285[0];
            v320 = v16 + v285[0];
          }
          v16 += v220;
          uBytes = v16;
          v285[2] = v16;
        }
        v217 = cbor_value_copy_string(v283, v219, &v362, v283);
        v108 = v282;
        v340 = v362;
        if ( !v217 )
          goto LABEL_714;
      }
      if ( !v108 )
        goto LABEL_993;
    }
LABEL_714:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v108 )
      goto LABEL_719;
    if ( BYTE6(v287) != 0xA0 )
    {
      v171 = 260;
LABEL_717:
      v108 = v171;
      v282 = v171;
      LODWORD(v285[3]) = v171;
      v172 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7667;
      goto LABEL_718;
    }
    v171 = cbor_value_map_find_value(cbMultiByte, "pluginNonce", v283);
    if ( v171 )
      goto LABEL_717;
    v108 = v282;
    if ( BYTE6(v284) == 0xFF )
      v171 = 259;
    if ( !v171 )
    {
      v341 = 0;
      v363 = 0;
      if ( v282 )
      {
        v222 = 260;
        v341 = 0;
        goto LABEL_1018;
      }
      if ( BYTE6(v284) != 64 )
      {
        v222 = 260;
        v321 = 0;
        v341 = 0;
LABEL_1020:
        v108 = v222;
        v282 = v222;
        LODWORD(v285[3]) = v222;
        v172 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7669;
LABEL_718:
        v285[6] = 0;
        v285[4] = v172;
        goto LABEL_719;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v222 = 2;
LABEL_1018:
        v321 = 0;
      }
      else
      {
        if ( (v284 & 0x100000000000000LL) != 0 )
          v223 = cbor_value_decode_int64_internal(v283, v282);
        else
          v223 = WORD2(v284);
        v363 = v223;
        v224 = 0;
        v321 = 0;
        if ( v223 > 0x40000 || v16 > 0x40000 )
        {
          v226 = 1024;
LABEL_1014:
          v282 = v226;
          LODWORD(v285[3]) = v226;
          v285[4] = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7669;
          v285[6] = 0;
        }
        else
        {
          v225 = (v223 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v285[0] )
          {
            if ( v225 + v16 > v285[1] )
            {
              v226 = 0x80000000;
              goto LABEL_1014;
            }
            v224 = v16 + v285[0];
            v321 = v16 + v285[0];
          }
          uBytes = v225 + v16;
          v285[2] = v225 + v16;
        }
        v222 = cbor_value_copy_string(v283, v224, &v363, v283);
        v108 = v282;
        v341 = v363;
        if ( !v222 )
          goto LABEL_719;
      }
      if ( !v108 )
        goto LABEL_1020;
    }
LABEL_719:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( !v108 )
    {
      if ( BYTE6(v287) != 0xA0 )
      {
        v173 = 260;
LABEL_722:
        v282 = v173;
        LODWORD(v285[3]) = v173;
        v285[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v285[5]) = 7672;
        v285[6] = 0;
        goto LABEL_723;
      }
      v173 = cbor_value_map_find_value(cbMultiByte, "supportedRpIds", v283);
      if ( v173 )
        goto LABEL_722;
      if ( BYTE6(v284) == 0xFF )
        v173 = 259;
      if ( !v173 )
      {
        v227 = my_cbor_decode_array_of_unicode_stringz((int)v285);
        v342 = 0;
        v228 = ULongLongToULong(v227, &v342);
        if ( v228 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x132,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\safecast.h",
            (const char *)(unsigned int)v228,
            v281);
        v344 = v342;
        v282 = v285[3];
        uBytes = v285[2];
      }
    }
LABEL_723:
    v293 = 0;
    v324 = 0;
    v174 = 0;
    v322 = 0;
    v175 = 0;
    v311 = 0;
    v176 = 0;
    v292 = 0;
    v177 = 0;
    v294 = 0;
    v178 = 0;
    v179 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)v283 = 0;
      v284 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v287) != 0xA0 )
        {
          v180 = 260;
LABEL_727:
          v282 = v180;
          LODWORD(v285[3]) = v180;
          v181 = *(_QWORD *)&cbMultiByte[2];
          LODWORD(v285[5]) = 7681;
          goto LABEL_728;
        }
        v180 = cbor_value_map_find_value(cbMultiByte, "thirdPartyPayment", v283);
        if ( v180 )
          goto LABEL_727;
        if ( BYTE6(v284) == 0xFF )
          v180 = 259;
        if ( !v180 )
        {
          v293 = 0;
          if ( BYTE6(v284) != 0xF5 )
          {
            v229 = 260;
LABEL_1034:
            v282 = v229;
            LODWORD(v285[3]) = v229;
            v181 = *(_QWORD *)&v283[2];
            LODWORD(v285[5]) = 7683;
LABEL_728:
            v285[6] = 0;
            v285[4] = v181;
            goto LABEL_729;
          }
          v293 = WORD2(v284) != 0;
          v229 = cbor_value_advance_fixed(v283);
          if ( v229 )
            goto LABEL_1034;
        }
      }
    }
LABEL_729:
    v182 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::GetImpl'::`2'::impl);
    v183 = v282;
    if ( !v182 )
      goto LABEL_1167;
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( !v282 )
    {
      if ( BYTE6(v287) != 0xA0 )
      {
        v184 = 260;
LABEL_733:
        v183 = v184;
        v282 = v184;
        LODWORD(v285[3]) = v184;
        v285[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v285[5]) = 7697;
        v285[6] = 0;
        goto LABEL_1056;
      }
      v184 = cbor_value_map_find_value(cbMultiByte, "clientDataJSON", v283);
      if ( v184 )
        goto LABEL_733;
      if ( BYTE6(v284) == 0xFF )
        v184 = 259;
      if ( v184 )
      {
LABEL_1055:
        v183 = v282;
        goto LABEL_1056;
      }
      v364 = 0;
      if ( BYTE6(v284) != 64 )
      {
        v230 = 260;
        v52 = 0;
LABEL_1076:
        v183 = v230;
        v282 = v230;
        LODWORD(v285[3]) = v230;
        v285[4] = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7699;
        v285[6] = 0;
        goto LABEL_1056;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v230 = 2;
        v52 = 0;
        goto LABEL_1075;
      }
      if ( (v284 & 0x100000000000000LL) != 0 )
        v231 = cbor_value_decode_int64_internal(v283, 259);
      else
        v231 = WORD2(v284);
      v52 = 0;
      v364 = v231;
      if ( v231 <= 0x40000 && uBytes <= 0x40000 )
      {
        v232 = (v231 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( v285[0] )
        {
          if ( v232 + uBytes > v285[1] )
          {
            v233 = 0x80000000;
LABEL_1053:
            v282 = v233;
            LODWORD(v285[3]) = v233;
            v285[4] = *(_QWORD *)&v283[2];
            LODWORD(v285[5]) = 7699;
            v285[6] = 0;
LABEL_1054:
            v230 = cbor_value_copy_string(v283, v52, &v364, v283);
            v174 = v364;
            if ( !v230 )
              goto LABEL_1055;
LABEL_1075:
            v183 = v282;
            if ( v282 )
              goto LABEL_1056;
            goto LABEL_1076;
          }
          v52 = uBytes + v285[0];
        }
        uBytes += v232;
        v285[2] = uBytes;
        goto LABEL_1054;
      }
      v233 = 1024;
      goto LABEL_1053;
    }
LABEL_1056:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v183 )
      goto LABEL_1060;
    if ( BYTE6(v287) != 0xA0 )
    {
      v234 = 260;
LABEL_1059:
      v183 = v234;
      v282 = v234;
      LODWORD(v285[3]) = v234;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7702;
      v285[6] = 0;
      goto LABEL_1060;
    }
    v234 = cbor_value_map_find_value(cbMultiByte, "remoteWebOrigin", v283);
    if ( v234 )
      goto LABEL_1059;
    if ( BYTE6(v284) == 0xFF )
      v234 = 259;
    if ( v234 )
    {
      v183 = v282;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v383, 7704, v281);
      v183 = v285[3];
      uBytes = v285[2];
      v282 = v285[3];
    }
LABEL_1060:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v183 )
      goto LABEL_1065;
    if ( BYTE6(v287) != 0xA0 )
    {
      v235 = 260;
LABEL_1063:
      v183 = v235;
      v282 = v235;
      LODWORD(v285[3]) = v235;
      v236 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7707;
      v285[6] = 0;
      goto LABEL_1064;
    }
    v235 = cbor_value_map_find_value(cbMultiByte, "publicKeyCredentialCreationOptions", v283);
    if ( v235 )
      goto LABEL_1063;
    if ( BYTE6(v284) == 0xFF )
      v235 = 259;
    if ( v235 )
    {
LABEL_1110:
      v183 = v282;
      goto LABEL_1065;
    }
    v371 = 0;
    if ( v282 )
    {
      v240 = 260;
LABEL_1107:
      v324 = 0;
      goto LABEL_1108;
    }
    if ( BYTE6(v284) != 64 )
    {
      v240 = 260;
      v324 = 0;
LABEL_1109:
      v183 = v240;
      v282 = v240;
      LODWORD(v285[3]) = v240;
      v236 = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7709;
      v285[6] = 0;
LABEL_1064:
      v285[4] = v236;
      goto LABEL_1065;
    }
    if ( (v284 & 0x400000000000000LL) != 0 )
    {
      v240 = 2;
      goto LABEL_1107;
    }
    v241 = (v284 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v283, 259) : WORD2(v284);
    v371 = v241;
    v242 = 0;
    v324 = 0;
    if ( v241 > 0x40000 || uBytes > 0x40000 )
    {
      v244 = 1024;
    }
    else
    {
      v243 = (v241 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v285[0] )
        goto LABEL_1101;
      if ( v243 + uBytes <= v285[1] )
      {
        v242 = uBytes + v285[0];
        v324 = uBytes + v285[0];
LABEL_1101:
        uBytes += v243;
        v285[2] = uBytes;
        goto LABEL_1104;
      }
      v244 = 0x80000000;
    }
    v282 = v244;
    LODWORD(v285[3]) = v244;
    v285[4] = *(_QWORD *)&v283[2];
    LODWORD(v285[5]) = 7709;
    v285[6] = 0;
LABEL_1104:
    v240 = cbor_value_copy_string(v283, v242, &v371, v283);
    v175 = v371;
    if ( !v240 )
      goto LABEL_1110;
LABEL_1108:
    v183 = v282;
    if ( !v282 )
      goto LABEL_1109;
LABEL_1065:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v183 )
      goto LABEL_1070;
    if ( BYTE6(v287) != 0xA0 )
    {
      v237 = 260;
LABEL_1068:
      v183 = v237;
      v282 = v237;
      LODWORD(v285[3]) = v237;
      v238 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7712;
      v285[6] = 0;
      goto LABEL_1069;
    }
    v237 = cbor_value_map_find_value(cbMultiByte, "publicKeyCredentialRequestOptions", v283);
    if ( v237 )
      goto LABEL_1068;
    if ( BYTE6(v284) == 0xFF )
      v237 = 259;
    if ( v237 )
    {
LABEL_1138:
      v183 = v282;
      goto LABEL_1070;
    }
    v365 = 0;
    if ( v282 )
    {
      v245 = 260;
LABEL_1135:
      v322 = 0;
      goto LABEL_1136;
    }
    if ( BYTE6(v284) != 64 )
    {
      v245 = 260;
      v322 = 0;
LABEL_1137:
      v183 = v245;
      v282 = v245;
      LODWORD(v285[3]) = v245;
      v238 = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7714;
      v285[6] = 0;
LABEL_1069:
      v285[4] = v238;
      goto LABEL_1070;
    }
    if ( (v284 & 0x400000000000000LL) != 0 )
    {
      v245 = 2;
      goto LABEL_1135;
    }
    v246 = (v284 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v283, 259) : WORD2(v284);
    v365 = v246;
    v247 = 0;
    v322 = 0;
    if ( v246 > 0x40000 || uBytes > 0x40000 )
    {
      v249 = 1024;
    }
    else
    {
      v248 = (v246 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v285[0] )
        goto LABEL_1129;
      if ( uBytes + v248 <= v285[1] )
      {
        v247 = uBytes + v285[0];
        v322 = uBytes + v285[0];
LABEL_1129:
        uBytes += v248;
        v285[2] = uBytes;
        goto LABEL_1132;
      }
      v249 = 0x80000000;
    }
    v282 = v249;
    LODWORD(v285[3]) = v249;
    v285[4] = *(_QWORD *)&v283[2];
    LODWORD(v285[5]) = 7714;
    v285[6] = 0;
LABEL_1132:
    v245 = cbor_value_copy_string(v283, v247, &v365, v283);
    v176 = v365;
    if ( !v245 )
      goto LABEL_1138;
LABEL_1136:
    v183 = v282;
    if ( !v282 )
      goto LABEL_1137;
LABEL_1070:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v183 )
      goto LABEL_1167;
    if ( BYTE6(v287) != 0xA0 )
    {
      v239 = 260;
LABEL_1073:
      v183 = v239;
      v282 = v239;
      LODWORD(v285[3]) = v239;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7717;
      v285[6] = 0;
      goto LABEL_1167;
    }
    v239 = cbor_value_map_find_value(cbMultiByte, "authenticatorId", v283);
    if ( v239 )
      goto LABEL_1073;
    if ( BYTE6(v284) == 0xFF )
      v239 = 259;
    if ( v239 )
      goto LABEL_1166;
    v366 = 0;
    if ( v282 )
    {
      v250 = 260;
      goto LABEL_1163;
    }
    if ( BYTE6(v284) != 64 )
    {
      v250 = 260;
      v311 = 0;
      goto LABEL_1165;
    }
    if ( (v284 & 0x400000000000000LL) != 0 )
    {
      v250 = 2;
LABEL_1163:
      v311 = 0;
LABEL_1164:
      v183 = v282;
      if ( v282 )
        goto LABEL_1167;
LABEL_1165:
      v183 = v250;
      v282 = v250;
      LODWORD(v285[3]) = v250;
      v285[4] = *(_QWORD *)&v283[2];
      LODWORD(v285[5]) = 7719;
      v285[6] = 0;
      goto LABEL_1167;
    }
    v251 = (v284 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v283, 259) : WORD2(v284);
    v366 = v251;
    v252 = 0;
    v311 = 0;
    if ( v251 > 0x40000 || uBytes > 0x40000 )
    {
      v254 = 1024;
    }
    else
    {
      v253 = (v251 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v285[0] )
        goto LABEL_1157;
      if ( uBytes + v253 <= v285[1] )
      {
        v252 = uBytes + v285[0];
        v311 = uBytes + v285[0];
LABEL_1157:
        uBytes += v253;
        v285[2] = uBytes;
        goto LABEL_1160;
      }
      v254 = 0x80000000;
    }
    v282 = v254;
    LODWORD(v285[3]) = v254;
    v285[4] = *(_QWORD *)&v283[2];
    LODWORD(v285[5]) = 7719;
    v285[6] = 0;
LABEL_1160:
    v250 = cbor_value_copy_string(v283, v252, &v366, v283);
    v177 = v366;
    if ( v250 )
      goto LABEL_1164;
LABEL_1166:
    v183 = v282;
LABEL_1167:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v183 )
      goto LABEL_1172;
    if ( BYTE6(v287) != 0xA0 )
    {
      v255 = 260;
LABEL_1170:
      v282 = v255;
      LODWORD(v285[3]) = v255;
      v256 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7723;
      goto LABEL_1171;
    }
    v255 = cbor_value_map_find_value(cbMultiByte, "remoteWebAuthn", v283);
    if ( v255 )
      goto LABEL_1170;
    if ( BYTE6(v284) == 0xFF )
      v255 = 259;
    if ( !v255 )
    {
      v294 = 0;
      if ( !v282 )
      {
        if ( BYTE6(v284) != 0xF5 )
        {
          v259 = 260;
LABEL_1185:
          v282 = v259;
          LODWORD(v285[3]) = v259;
          v256 = *(_QWORD *)&v283[2];
          LODWORD(v285[5]) = 7725;
LABEL_1171:
          v285[6] = 0;
          v285[4] = v256;
          goto LABEL_1172;
        }
        v294 = WORD2(v284) != 0;
        v259 = cbor_value_advance_fixed(v283);
        if ( v259 )
          goto LABEL_1185;
      }
    }
LABEL_1172:
    v257 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
    v11 = v282;
    if ( !v257 )
      goto LABEL_1237;
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( !v282 )
    {
      if ( BYTE6(v287) != 0xA0 )
      {
        v258 = 260;
LABEL_1176:
        v11 = v258;
        v282 = v258;
        v285[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v285[5]) = 7730;
        v285[6] = 0;
        goto LABEL_1192;
      }
      v258 = cbor_value_map_find_value(cbMultiByte, "pluginUvKeyName", v283);
      if ( v258 )
        goto LABEL_1176;
      if ( BYTE6(v284) == 0xFF )
        v258 = 259;
      if ( v258 )
      {
        v11 = v282;
      }
      else
      {
        my_cbor_value_decoder_copy_unicode_stringz((int)v285, (int)v283, (int)v382, 7732, v281);
        v11 = v285[3];
        uBytes = v285[2];
        v282 = v285[3];
      }
    }
LABEL_1192:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v11 )
      goto LABEL_1197;
    if ( BYTE6(v287) != 0xA0 )
    {
      v260 = 260;
LABEL_1195:
      v11 = v260;
      v282 = v260;
      v261 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7735;
      v285[6] = 0;
      goto LABEL_1196;
    }
    v260 = cbor_value_map_find_value(cbMultiByte, "pluginUvBufferToSign", v283);
    if ( v260 )
      goto LABEL_1195;
    v11 = v282;
    if ( BYTE6(v284) == 0xFF )
      v260 = 259;
    if ( !v260 )
    {
      v367 = 0;
      if ( v282 )
      {
        v263 = 260;
        goto LABEL_1225;
      }
      if ( BYTE6(v284) != 64 )
      {
        v263 = 260;
LABEL_1226:
        v11 = v263;
        v282 = v263;
        v261 = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7737;
        v285[6] = 0;
LABEL_1196:
        v285[4] = v261;
        goto LABEL_1197;
      }
      if ( (v284 & 0x400000000000000LL) != 0 )
      {
        v263 = 2;
LABEL_1225:
        if ( !v11 )
          goto LABEL_1226;
        goto LABEL_1197;
      }
      if ( (v284 & 0x100000000000000LL) != 0 )
        v264 = cbor_value_decode_int64_internal(v283, 259);
      else
        v264 = WORD2(v284);
      v367 = v264;
      if ( v264 > 0x40000 || uBytes > 0x40000 )
      {
        v282 = 1024;
LABEL_1221:
        v285[4] = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7737;
        v285[6] = 0;
      }
      else
      {
        v265 = (v264 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( v285[0] )
        {
          if ( uBytes + v265 > v285[1] )
          {
            v282 = 0x80000000;
            goto LABEL_1221;
          }
          v178 = uBytes + v285[0];
        }
        uBytes += v265;
      }
      v263 = cbor_value_copy_string(v283, v178, &v367, v283);
      v179 = v367;
      v11 = v282;
      if ( !v263 )
        goto LABEL_1197;
      goto LABEL_1225;
    }
LABEL_1197:
    v284 = 0;
    *(_OWORD *)v283 = 0;
    if ( v11 )
      goto LABEL_1241;
    if ( BYTE6(v287) != 0xA0 )
    {
      v262 = 260;
LABEL_1200:
      v11 = v262;
      v282 = v262;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7740;
      v285[6] = 0;
      goto LABEL_1237;
    }
    v262 = cbor_value_map_find_value(cbMultiByte, "excludeThirdPartyCredentials", v283);
    if ( v262 )
      goto LABEL_1200;
    v11 = v282;
    if ( BYTE6(v284) == 0xFF )
      v262 = 259;
    if ( !v262 )
    {
      v292 = 0;
      if ( v282 )
        goto LABEL_1241;
      if ( BYTE6(v284) != 0xF5 )
      {
        v266 = 260;
LABEL_1235:
        v11 = v266;
        v282 = v266;
        v285[4] = *(_QWORD *)&v283[2];
        LODWORD(v285[5]) = 7742;
        v285[6] = 0;
        goto LABEL_1237;
      }
      v292 = WORD2(v284) != 0;
      v266 = cbor_value_advance_fixed(v283);
      if ( v266 )
        goto LABEL_1235;
      v11 = v282;
    }
LABEL_1237:
    if ( v11 )
      goto LABEL_1241;
    v267 = cbor_value_advance(cbMultiByte);
    if ( !v267 )
    {
      v11 = v282;
LABEL_1241:
      v267 = v11;
      goto LABEL_1242;
    }
    v11 = v267;
    v285[4] = *(_QWORD *)&cbMultiByte[2];
    v282 = v267;
    LODWORD(v285[5]) = 7746;
    v285[6] = 0;
LABEL_1242:
    if ( (_DWORD)v287 && !v267 )
    {
      v11 = 1024;
      v282 = 1024;
      v285[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v285[5]) = 7750;
      v285[6] = 0;
    }
    v268 = v296;
    if ( v296 )
    {
      v269 = v307 == 16;
      v270 = v297;
      *(_DWORD *)v296 = 1;
      *(_DWORD *)(v268 + 4) = v270;
      *(_DWORD *)(v268 + 8) = v298;
      *(_DWORD *)(v268 + 12) = v299;
      *(_DWORD *)(v268 + 32) = v345;
      *(_QWORD *)(v268 + 40) = v325;
      *(_DWORD *)(v268 + 136) = v326;
      *(_QWORD *)(v268 + 144) = v306;
      *(_QWORD *)(v268 + 128) = v368;
      if ( v269 )
      {
        *(_OWORD *)(v268 + 16) = *(_OWORD *)v303;
      }
      else if ( !v11 )
      {
        v282 = 1;
        LODWORD(v285[5]) = 7767;
        v285[6] = 0;
      }
      *(_DWORD *)(v268 + 48) = v327;
      *(_QWORD *)(v268 + 56) = v308;
      *(_DWORD *)(v268 + 64) = v328;
      *(_QWORD *)(v268 + 72) = v309;
      *(_DWORD *)(v268 + 80) = v329;
      *(_QWORD *)(v268 + 88) = v310;
      *(_DWORD *)(v268 + 96) = v330;
      *(_QWORD *)(v268 + 104) = v323;
      *(_DWORD *)(v268 + 112) = v369;
      *(_QWORD *)(v268 + 120) = v331;
      *(_QWORD *)(v268 + 152) = v377;
      *(_DWORD *)(v268 + 160) = v332;
      *(_QWORD *)(v268 + 168) = v312;
      if ( v396 )
        *(_DWORD *)(v268 + 176) = 1;
      v269 = !v289;
      *(_QWORD *)(v268 + 184) = v370;
      *(_QWORD *)(v268 + 192) = v385;
      if ( !v269 )
        *(_DWORD *)(v268 + 200) = 1;
      if ( v290 )
        *(_DWORD *)(v268 + 204) = 1;
      *(_DWORD *)(v268 + 208) = v333;
      *(_QWORD *)(v268 + 216) = v313;
      *(_QWORD *)(v268 + 224) = *(_QWORD *)v386;
      *(_DWORD *)(v268 + 232) = v334;
      *(_QWORD *)(v268 + 240) = v314;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl) )
      {
        v269 = !v291;
        v271 = v296;
        *(_QWORD *)(v296 + 248) = *(_QWORD *)v387;
        *(_QWORD *)(v271 + 256) = *(_QWORD *)v375;
        *(_QWORD *)(v271 + 264) = *(_QWORD *)v376;
        *(_QWORD *)(v271 + 280) = *(_QWORD *)v384;
        *(_QWORD *)(v271 + 288) = *(_QWORD *)v378;
        *(_DWORD *)(v271 + 296) = v301;
        *(_DWORD *)(v271 + 300) = v335;
        *(_QWORD *)(v271 + 304) = v315;
        if ( !v269 )
          *(_DWORD *)(v271 + 312) = 1;
        *(_DWORD *)(v271 + 316) = v336;
        *(_QWORD *)(v271 + 320) = v316;
        *(_DWORD *)(v271 + 328) = v337;
        *(_QWORD *)(v271 + 336) = v317;
        *(_QWORD *)(v271 + 344) = v348;
        *(_DWORD *)(v271 + 352) = v302;
        if ( v338 )
        {
          if ( v338 == 16 )
          {
            *(_OWORD *)(v271 + 356) = *v318;
          }
          else if ( !v282 )
          {
            v282 = 1;
            LODWORD(v285[5]) = 7834;
            v285[6] = 0;
          }
        }
        *(_DWORD *)(v271 + 392) = v339;
        *(_QWORD *)(v271 + 400) = v319;
        *(_QWORD *)(v271 + 376) = *(_QWORD *)v379;
        *(_QWORD *)(v271 + 384) = *(_QWORD *)v380;
        *(_DWORD *)(v271 + 408) = v340;
        *(_QWORD *)(v271 + 416) = v320;
        *(_DWORD *)(v271 + 424) = v341;
        *(_QWORD *)(v271 + 432) = v321;
        *(_DWORD *)(v271 + 444) = v344;
        *(_QWORD *)(v271 + 448) = v381;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v272 = v296;
          *(_QWORD *)(v296 + 536) = *(_QWORD *)v382;
          v273 = v292;
          *(_DWORD *)(v272 + 544) = v179;
          *(_QWORD *)(v272 + 552) = v178;
          *(_DWORD *)(v272 + 560) = v273;
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
        && v293 )
      {
        *(_DWORD *)(v296 + 440) = 1;
      }
      v274 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::GetImpl'::`2'::impl);
      v275 = v296;
      if ( v274 )
      {
        v276 = *(_QWORD *)v383;
        *(_QWORD *)(v296 + 472) = v52;
        *(_DWORD *)(v275 + 464) = v174;
        *(_QWORD *)(v275 + 512) = v276;
        *(_QWORD *)(v275 + 488) = v324;
        v277 = v322;
        *(_DWORD *)(v275 + 480) = v175;
        *(_QWORD *)(v275 + 504) = v277;
        v278 = v311;
        *(_DWORD *)(v275 + 496) = v176;
        *(_QWORD *)(v275 + 528) = v278;
        *(_DWORD *)(v275 + 520) = v177;
      }
      v11 = v282;
      if ( v294 )
        *(_DWORD *)(v275 + 460) = 1;
    }
    v7 = v300;
    if ( v11 )
      goto LABEL_1284;
    if ( v300 )
      break;
    v8 = uBytes;
    v295 = uBytes;
    if ( !uBytes )
      goto LABEL_1292;
    v279 = (char *)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v279 )
    {
      v11 = 0x80000000;
      goto LABEL_1283;
    }
    v11 = v282;
    v7 = v279;
    v300 = v279;
LABEL_1280:
    if ( ++v343 > 1 )
      goto LABEL_1284;
    v10 = a2;
  }
  if ( uBytes == v285[1] )
  {
    v8 = v295;
    goto LABEL_1280;
  }
LABEL_1292:
  v11 = 1;
LABEL_1283:
  v282 = v11;
  LODWORD(v285[5]) = 7896;
LABEL_1284:
  v8 = v296;
  v6 = a3;
LABEL_1285:
  if ( a4 )
    *a4 = v285[4];
  if ( a5 )
    *a5 = v285[5];
  if ( v11 )
  {
    FidoSecureZeroFree(v7);
    v11 = v282;
    v8 = 0;
  }
  result = v11;
  *v6 = v8;
  return result;
}

```

## disassembly

```asm
0x180010d90  mov     rax, rsp
0x180010d93  mov     [rax+8], rbx
0x180010d97  mov     [rax+20h], r9
0x180010d9b  mov     [rax+18h], r8
0x180010d9f  mov     [rax+10h], rdx
0x180010da3  push    rbp
0x180010da4  push    rsi
0x180010da5  push    rdi
0x180010da6  push    r12
0x180010da8  push    r13
0x180010daa  push    r14
0x180010dac  push    r15
0x180010dae  lea     rbp, [rax-308h]
0x180010db5  sub     rsp, 3D0h
0x180010dbc  xor     r15d, r15d
0x180010dbf  movaps  xmmword ptr [rax-48h], xmm6
0x180010dc3  xorps   xmm6, xmm6
0x180010dc6  mov     ebx, ecx
0x180010dc8  xor     eax, eax
0x180010dca  mov     [rbp+300h+var_330], r15
0x180010dce  mov     [rbp+300h+var_380], rax
0x180010dd2  mov     r14, r8
0x180010dd5  mov     esi, r15d
0x180010dd8  mov     edi, r15d
0x180010ddb  movups  xmmword ptr [rsp+400h+var_3B8+8], xmm6
0x180010de0  movups  [rsp+400h+var_3A8+8], xmm6
0x180010de5  movups  [rsp+400h+var_398+8], xmm6
0x180010dea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::GetImpl(void)'::`2'::impl
0x180010df1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::__private_IsEnabled(void)
0x180010df6  mov     rcx, [rbp+300h+arg_8]
0x180010dfd  test    al, al
0x180010dff  jz      short loc_180010E7D
0x180010e01  test    rcx, rcx
0x180010e04  jz      short loc_180010E14
0x180010e06  lea     eax, [rbx-1]
0x180010e09  cmp     eax, 0FFFFFh
0x180010e0e  jbe     loc_180010E94
0x180010e14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x180010e1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x180010e20  test    al, al
0x180010e22  jz      short loc_180010E4D
0x180010e24  cmp     ebx, 1
0x180010e27  jnb     short loc_180010E37
0x180010e29  lea     rcx, aDecodingEmptyR; "Decoding empty RPC Request failed"
0x180010e30  call    ??$Log@$01@FidoTraceProvider@@SAXPEBDZZ; FidoTraceProvider::Log<2>(char const *,...)
0x180010e35  jmp     short loc_180010E4D
0x180010e37  cmp     ebx, 100000h
0x180010e3d  jbe     short loc_180010E4D
0x180010e3f  mov     edx, ebx
0x180010e41  lea     rcx, aRpcRequestOfSi; "RPC request of size %ld too large"
0x180010e48  call    ??$Log@$01@FidoTraceProvider@@SAXPEBDZZ; FidoTraceProvider::Log<2>(char const *,...)
0x180010e4d  psrldq  xmm6, 8
0x180010e52  movd    r9d, xmm6
0x180010e57  mov     [rsp+400h+var_3D0], r9d
0x180010e5c  test    r9d, r9d
0x180010e5f  jnz     loc_18001583C
0x180010e65  mov     r9d, 3
0x180010e6b  mov     dword ptr [rsp+78h], 1CA6h
0x180010e73  mov     [rsp+400h+var_3D0], r9d
0x180010e78  jmp     loc_18001583C
0x180010e7d  test    rcx, rcx
0x180010e80  jz      loc_1800158AC
0x180010e86  lea     eax, [rbx-1]
0x180010e89  cmp     eax, 0FFFFh
0x180010e8e  ja      loc_1800158AC
0x180010e94  mov     [rbp+300h+var_350], r15
0x180010e98  mov     rax, rbx
0x180010e9b  mov     [rbp+300h+var_1DC], r15d
0x180010ea2  mov     [rbp+300h+var_78], rbx
0x180010ea9  xor     r13d, r13d
0x180010eac  mov     r14, [rbp+300h+var_330]
0x180010eb0  mov     r12d, r13d
0x180010eb3  mov     [rbp+300h+var_340], r15d
0x180010eb7  xor     edx, edx
0x180010eb9  mov     [rbp+300h+var_33C], r15d
0x180010ebd  xorps   xmm0, xmm0
0x180010ec0  mov     [rbp+300h+var_368], rdx
0x180010ec4  xorps   xmm1, xmm1
0x180010ec7  mov     [rbp+300h+var_338], r15d
0x180010ecb  mov     [rbp+300h+var_320], r15
0x180010ecf  lea     rdx, [rbp+300h+cbMultiByte]
0x180010ed3  mov     [rbp+300h+var_2F8], r15
0x180010ed7  mov     ebx, 0FFFFFFFFh
0x180010edc  mov     [rbp+300h+var_268], r15
0x180010ee3  mov     esi, 103h
0x180010ee8  mov     [rbp+300h+var_1D0], r13
0x180010eef  mov     r15d, r13d
0x180010ef2  mov     [rbp+300h+var_300], r13
0x180010ef6  mov     [rbp+300h+var_260], r13
0x180010efd  mov     [rbp+300h+var_118], r13
0x180010f04  mov     [rbp+300h+var_2F0], r13
0x180010f08  mov     [rbp+300h+var_258], r13
0x180010f0f  mov     [rbp+300h+var_2E8], r13
0x180010f13  mov     [rbp+300h+var_250], r13
0x180010f1a  mov     [rbp+300h+var_2E0], r13
0x180010f1e  mov     [rbp+300h+var_248], r13
0x180010f25  mov     [rbp+300h+var_278], r13
0x180010f2c  mov     [rbp+300h+var_240], r13
0x180010f33  mov     [rbp+300h+var_238], r13
0x180010f3a  mov     [rbp+300h+var_110], r13
0x180010f41  mov     [rbp+300h+var_D0], r13
0x180010f48  mov     [rbp+300h+var_2D0], r13
0x180010f4c  mov     [rbp+300h+var_230], r13
0x180010f53  mov     [rbp+300h+arg_28], r12b
0x180010f5a  mov     [rbp+300h+var_108], r13
0x180010f61  mov     [rbp+300h+var_90], r13
0x180010f68  mov     [rbp+300h+var_358], r12b
0x180010f6c  mov     [rbp+300h+var_357], r12b
0x180010f70  mov     [rbp+300h+var_2C8], r13
0x180010f74  mov     [rbp+300h+var_228], r13
0x180010f7b  mov     qword ptr [rbp+300h+var_88], r13
0x180010f82  mov     [rbp+300h+var_2C0], r13
0x180010f86  mov     [rbp+300h+var_220], r13
0x180010f8d  mov     qword ptr [rbp+300h+var_80], r13
0x180010f94  mov     qword ptr [rbp+300h+var_E0], r13
0x180010f9b  mov     qword ptr [rbp+300h+var_D8], r13
0x180010fa2  mov     qword ptr [rbp+300h+var_98], r13
0x180010fa9  mov     qword ptr [rbp+300h+var_C8], r13
0x180010fb0  mov     [rbp+300h+var_328], r13d
0x180010fb4  mov     [rbp+300h+var_2B8], r13
0x180010fb8  mov     [rbp+300h+var_218], r13
0x180010fbf  mov     [rbp+300h+var_356], r12b
0x180010fc3  mov     [rbp+300h+var_2B0], r13
0x180010fc7  mov     [rbp+300h+var_210], r13
0x180010fce  mov     [rbp+300h+var_2A8], r13
0x180010fd2  mov     [rbp+300h+var_208], r13
0x180010fd9  mov     [rbp+300h+var_1B8], r13
0x180010fe0  mov     [rbp+300h+var_298], r13
0x180010fe4  mov     [rbp+300h+var_1F8], r13
0x180010feb  mov     [rbp+300h+var_324], r13d
0x180010fef  mov     [rbp+300h+var_2A0], r13
0x180010ff3  mov     [rbp+300h+var_200], r13
0x180010ffa  mov     qword ptr [rbp+300h+var_C0], r13
0x180011001  mov     qword ptr [rbp+300h+var_B8], r13
0x180011008  mov     [rbp+300h+var_1F0], r13
0x18001100f  mov     [rbp+300h+var_290], r13
0x180011013  mov     [rbp+300h+var_1E8], r13
0x18001101a  mov     [rbp+300h+var_288], r13
0x18001101e  mov     [rbp+300h+var_B0], r13
0x180011025  mov     [rbp+300h+var_1D8], r13d
0x18001102c  mov     qword ptr [rbp+300h+var_A0], r13
0x180011033  mov     qword ptr [rbp+300h+var_A8], r13
0x18001103a  mov     [rbp+300h+uBytes], r13
0x18001103e  mov     qword ptr [rsp+400h+var_3A8+8], r13
0x180011043  movdqu  [rsp+400h+var_398], xmm6
0x180011049  mov     qword ptr [rsp+400h+var_3B8+8], r14
0x18001104e  movdqu  xmmword ptr [rsp+78h], xmm0
0x180011054  mov     qword ptr [rsp+400h+var_3A8], rdi
0x180011059  movups  [rbp+300h+var_70], xmm0
0x180011060  movups  xmmword ptr [rbp+300h+cbMultiByte], xmm1
0x180011064  mov     [rsp+20h], rdx; int
0x180011069  lea     r9, [rbp+300h+var_70]
0x180011070  mov     rdx, rax
0x180011073  xor     r8d, r8d
0x180011076  call    cbor_parser_init
0x18001107b  mov     [rsp+400h+var_3D0], eax
0x18001107f  mov     edx, eax
0x180011081  mov     [rbp+300h+var_348], r13
0x180011085  test    eax, eax
0x180011087  jz      short loc_18001109B
0x180011089  mov     dword ptr [rsp+400h+var_398], eax
0x18001108d  mov     dword ptr [rsp+78h], 1D19h
0x180011095  mov     [rbp+300h+var_380], r13
0x180011099  jmp     short loc_1800110F4
0x18001109b  test    r14, r14
0x18001109e  jz      short loc_1800110DC
0x1800110a0  mov     rdi, [rbp+300h+var_350]
0x1800110a4  cmp     rdi, 238h
0x1800110ab  jnb     short loc_1800110D4
0x1800110ad  movd    edx, xmm6
0x1800110b1  mov     [rsp+400h+var_3D0], edx
0x1800110b5  test    edx, edx
0x1800110b7  jnz     short loc_1800110F8
0x1800110b9  mov     edx, 80000000h
0x1800110be  mov     dword ptr [rsp+78h], 1D1Dh
0x1800110c6  mov     [rsp+400h+var_3D0], edx
0x1800110ca  mov     dword ptr [rsp+400h+var_398], edx
0x1800110ce  mov     [rbp+300h+var_380], r13
0x1800110d2  jmp     short loc_1800110F8
0x1800110d4  lea     rdi, [r14+r13]
0x1800110d8  mov     [rbp+300h+var_348], rdi
0x1800110dc  mov     edx, dword ptr [rsp+400h+var_398]
0x1800110e0  add     r15, 238h
0x1800110e7  mov     [rbp+300h+uBytes], r15
0x1800110eb  mov     qword ptr [rsp+400h+var_3A8+8], r15
0x1800110f0  mov     [rsp+400h+var_3D0], edx
0x1800110f4  mov     rdi, [rbp+300h+var_350]
0x1800110f8  xor     eax, eax
0x1800110fa  xorps   xmm0, xmm0
0x1800110fd  mov     qword ptr [rsp+400h+var_3B8], rax
0x180011102  movups  xmmword ptr [rsp+400h+var_3D0+8], xmm0
0x180011107  test    edx, edx
0x180011109  jnz     loc_18001120D
0x18001110f  cmp     byte ptr [rbp+300h+var_368+6], 0A0h
0x180011113  jz      short loc_18001111C
0x180011115  mov     ecx, 104h
0x18001111a  jmp     short loc_180011140
0x18001111c  lea     r8, [rsp+400h+var_3D0+8]
0x180011121  lea     rdx, aCommand_0; "command"
0x180011128  lea     rcx, [rbp+300h+cbMultiByte]
0x18001112c  call    cbor_value_map_find_value
0x180011131  mov     ecx, eax
0x180011133  test    eax, eax
0x180011135  jnz     short loc_180011140
0x180011137  cmp     byte ptr [rsp+400h+var_3B8+6], 0FFh
0x18001113c  jnz     short loc_180011167
0x18001113e  mov     ecx, esi
0x180011140  mov     rax, qword ptr [rbp+300h+cbMultiByte+8]
0x180011144  mov     edx, ecx
0x180011146  mov     qword ptr [rsp+400h+var_398+8], rax
0x18001114b  mov     [rsp+400h+var_3D0], ecx
0x18001114f  mov     dword ptr [rsp+400h+var_398], ecx
0x180011153  mov     dword ptr [rsp+78h], 1D20h
0x18001115b  mov     [rbp+300h+var_380], r13
0x18001115f  test    ecx, ecx
0x180011161  jnz     loc_18001120D
0x180011167  mov     [rbp+300h+var_340], ebx
0x18001116a  cmp     byte ptr [rsp+400h+var_3B8+6], r12b
0x18001116f  jnz     short loc_1800111BF
0x180011171  movzx   eax, byte ptr [rsp+400h+var_3B8+7]
0x180011176  test    al, 2
0x180011178  jnz     short loc_1800111BF
0x18001117a  test    al, 1
0x18001117c  jz      short loc_18001118D
0x18001117e  lea     rcx, [rsp+400h+var_3D0+8]
0x180011183  call    _cbor_value_decode_int64_internal
0x180011188  mov     rbx, rax
0x18001118b  jmp     short loc_180011192
0x18001118d  movzx   ebx, word ptr [rsp+400h+var_3B8+4]
0x180011192  lea     rcx, [rsp+400h+var_3D0+8]
0x180011197  call    cbor_value_advance_fixed
0x18001119c  mov     ecx, eax
0x18001119e  test    eax, eax
0x1800111a0  jnz     short loc_1800111C4
0x1800111a2  mov     edx, [rsp+400h+var_3D0]
0x1800111a6  mov     eax, 0FFFFFFFFh
0x1800111ab  cmp     rbx, rax
0x1800111ae  jbe     short loc_1800111B7
0x1800111b0  mov     ecx, 400h
0x1800111b5  jmp     short loc_1800111E4
0x1800111b7  mov     [rbp+300h+var_340], ebx
0x1800111ba  mov     rbx, rax
0x1800111bd  jmp     short loc_18001120D
0x1800111bf  mov     ecx, 104h
0x1800111c4  mov     rax, [rsp+400h+var_3C0]
0x1800111c9  mov     edx, ecx
0x1800111cb  mov     qword ptr [rsp+400h+var_398+8], rax
0x1800111d0  mov     [rsp+400h+var_3D0], ecx
0x1800111d4  mov     dword ptr [rsp+400h+var_398], ecx
0x1800111d8  mov     dword ptr [rsp+78h], 1D22h
0x1800111e0  mov     [rbp+300h+var_380], r13
0x1800111e4  mov     ebx, 0FFFFFFFFh
0x1800111e9  test    edx, edx
0x1800111eb  jnz     short loc_18001120D
0x1800111ed  mov     rax, [rsp+400h+var_3C0]
0x1800111f2  mov     edx, ecx
0x1800111f4  mov     qword ptr [rsp+400h+var_398+8], rax
0x1800111f9  mov     [rsp+400h+var_3D0], ecx
0x1800111fd  mov     dword ptr [rsp+400h+var_398], ecx
0x180011201  mov     dword ptr [rsp+78h], 1D22h
0x180011209  mov     [rbp+300h+var_380], r13
0x18001120d  xor     eax, eax
0x18001120f  xorps   xmm0, xmm0
0x180011212  mov     qword ptr [rsp+400h+var_3B8], rax
0x180011217  movups  xmmword ptr [rsp+400h+var_3D0+8], xmm0
0x18001121c  test    edx, edx
0x18001121e  jnz     loc_18001131A
0x180011224  cmp     byte ptr [rbp+300h+var_368+6], 0A0h
0x180011228  jz      short loc_180011231
0x18001122a  mov     ecx, 104h
0x18001122f  jmp     short loc_180011255
0x180011231  lea     r8, [rsp+400h+var_3D0+8]
0x180011236  lea     rdx, aFlags; "flags"
0x18001123d  lea     rcx, [rbp+300h+cbMultiByte]
0x180011241  call    cbor_value_map_find_value
0x180011246  mov     ecx, eax
0x180011248  test    eax, eax
0x18001124a  jnz     short loc_180011255
0x18001124c  cmp     byte ptr [rsp+400h+var_3B8+6], 0FFh
0x180011251  jnz     short loc_18001127C
0x180011253  mov     ecx, esi
0x180011255  mov     rax, qword ptr [rbp+300h+cbMultiByte+8]
0x180011259  mov     edx, ecx
0x18001125b  mov     qword ptr [rsp+400h+var_398+8], rax
0x180011260  mov     [rsp+400h+var_3D0], ecx
0x180011264  mov     dword ptr [rsp+400h+var_398], ecx
0x180011268  mov     dword ptr [rsp+78h], 1D25h
0x180011270  mov     [rbp+300h+var_380], r13
0x180011274  test    ecx, ecx
0x180011276  jnz     loc_18001131A
0x18001127c  mov     [rbp+300h+var_33C], ebx
0x18001127f  cmp     byte ptr [rsp+400h+var_3B8+6], r12b
0x180011284  jnz     short loc_1800112D1
0x180011286  movzx   eax, byte ptr [rsp+400h+var_3B8+7]
0x18001128b  test    al, 2
0x18001128d  jnz     short loc_1800112D1
0x18001128f  test    al, 1
0x180011291  jz      short loc_1800112A2
0x180011293  lea     rcx, [rsp+400h+var_3D0+8]
0x180011298  call    _cbor_value_decode_int64_internal
  ... truncated ...
```
