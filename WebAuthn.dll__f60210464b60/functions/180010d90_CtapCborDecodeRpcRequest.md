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
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ecx
  unsigned int v13; // r9d
  int v14; // eax
  unsigned __int64 v15; // r13
  char *v16; // r14
  unsigned __int64 v17; // r12
  SIZE_T v18; // r15
  unsigned int v19; // eax
  size_t v20; // r8
  __int64 v21; // rdx
  SIZE_T v22; // rdi
  unsigned int value; // ecx
  __int64 v24; // rdx
  unsigned __int64 v25; // rbx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rdx
  unsigned __int64 v29; // rbx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  __int64 v32; // rdx
  unsigned __int64 v33; // rbx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // eax
  unsigned __int64 v37; // rax
  char *v38; // rsi
  unsigned __int64 v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rax
  unsigned int v43; // eax
  unsigned int v44; // eax
  __int64 v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rax
  unsigned int v48; // eax
  __int64 v49; // rax
  unsigned int v50; // eax
  __int64 v51; // rax
  unsigned int v52; // eax
  unsigned __int64 v53; // r13
  unsigned int v54; // eax
  SIZE_T v55; // r13
  unsigned __int64 v56; // rsi
  unsigned int v57; // eax
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // rcx
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned __int64 v62; // rax
  char *v63; // rbx
  unsigned __int64 v64; // rcx
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned __int64 v67; // rax
  char *v68; // rbx
  unsigned __int64 v69; // rcx
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned __int64 v72; // rax
  char *v73; // rbx
  unsigned __int64 v74; // rcx
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned __int64 v77; // rax
  char *v78; // rbx
  unsigned __int64 v79; // rcx
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned __int64 v82; // rax
  char *v83; // rbx
  unsigned __int64 v84; // rcx
  unsigned int v85; // eax
  __int64 v86; // rdx
  unsigned int v87; // edi
  unsigned __int64 v88; // rax
  HLOCAL v89; // rbx
  char *v90; // r14
  unsigned __int64 v91; // rcx
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // eax
  unsigned int v95; // eax
  __int64 v96; // rax
  unsigned int v97; // eax
  __int64 v98; // rax
  unsigned int v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // eax
  __int64 v102; // rax
  unsigned int v103; // eax
  __int64 v104; // rax
  unsigned int v105; // eax
  __int64 v106; // rax
  unsigned int v107; // eax
  int v108; // eax
  __int64 v109; // rax
  unsigned int v110; // edx
  int v111; // eax
  unsigned int v112; // eax
  unsigned __int64 v113; // rax
  SIZE_T v114; // rbx
  unsigned __int64 v115; // rcx
  unsigned int v116; // eax
  unsigned int v117; // eax
  SIZE_T v118; // r12
  SIZE_T v119; // rsi
  int v120; // ebx
  SIZE_T v121; // r14
  int v122; // edi
  unsigned int v123; // eax
  __int64 v124; // rax
  unsigned int v125; // eax
  __int64 v126; // rax
  unsigned int v127; // eax
  unsigned __int64 v128; // rax
  unsigned __int64 v129; // rcx
  unsigned int v130; // eax
  unsigned int v131; // eax
  unsigned __int64 v132; // rax
  unsigned __int64 v133; // rcx
  unsigned int v134; // eax
  unsigned int v135; // eax
  unsigned int v136; // eax
  unsigned int v137; // eax
  unsigned __int64 v138; // rax
  SIZE_T v139; // rbx
  unsigned __int64 v140; // rcx
  unsigned int v141; // eax
  unsigned int v142; // ebx
  int v143; // eax
  unsigned __int64 v144; // rax
  SIZE_T v145; // rdi
  unsigned __int64 v146; // rcx
  int v147; // eax
  int v148; // eax
  int v149; // eax
  int v150; // eax
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
  __int64 v168; // rax
  int v169; // eax
  int v170; // eax
  int v171; // eax
  __int64 v172; // rax
  int v173; // eax
  __int64 v174; // rax
  int v175; // eax
  int v176; // esi
  int v177; // r14d
  int v178; // r15d
  int v179; // r12d
  SIZE_T v180; // rdi
  int v181; // ebx
  int v182; // eax
  __int64 v183; // rax
  char v184; // al
  unsigned int v185; // ecx
  int v186; // eax
  int v187; // ecx
  unsigned __int64 v188; // rbx
  int v189; // eax
  unsigned __int64 v190; // rax
  SIZE_T v191; // rbx
  unsigned __int64 v192; // rcx
  unsigned int v193; // eax
  int v194; // eax
  int v195; // eax
  unsigned __int64 v196; // rax
  SIZE_T v197; // rbx
  unsigned __int64 v198; // rcx
  unsigned int v199; // eax
  int v200; // eax
  unsigned __int64 v201; // rax
  SIZE_T v202; // rbx
  unsigned __int64 v203; // rcx
  unsigned int v204; // eax
  __int64 v205; // rax
  int v206; // eax
  int v207; // ecx
  unsigned __int64 v208; // rbx
  int v209; // eax
  unsigned __int64 v210; // rax
  SIZE_T v211; // rbx
  unsigned __int64 v212; // rcx
  unsigned int v213; // eax
  int v214; // eax
  unsigned __int64 v215; // rax
  SIZE_T v216; // rbx
  unsigned __int64 v217; // rcx
  unsigned int v218; // eax
  int v219; // eax
  unsigned __int64 v220; // rax
  SIZE_T v221; // rbx
  unsigned __int64 v222; // rcx
  unsigned int v223; // eax
  int v224; // eax
  unsigned __int64 v225; // rax
  SIZE_T v226; // rbx
  unsigned __int64 v227; // rcx
  unsigned int v228; // eax
  unsigned __int64 v229; // rax
  int v230; // eax
  int v231; // eax
  int v232; // eax
  unsigned __int64 v233; // rax
  unsigned __int64 v234; // rcx
  unsigned int v235; // eax
  int v236; // eax
  int v237; // eax
  __int64 v238; // rax
  int v239; // eax
  __int64 v240; // rax
  int v241; // eax
  int v242; // eax
  unsigned __int64 v243; // rax
  SIZE_T v244; // rdx
  unsigned __int64 v245; // rcx
  unsigned int v246; // eax
  int v247; // eax
  unsigned __int64 v248; // rax
  SIZE_T v249; // rdx
  unsigned __int64 v250; // rcx
  unsigned int v251; // eax
  int v252; // eax
  unsigned __int64 v253; // rax
  SIZE_T v254; // rdx
  unsigned __int64 v255; // rcx
  unsigned int v256; // eax
  int v257; // eax
  __int64 v258; // rax
  char v259; // al
  __int64 v260; // rdx
  __int64 v261; // r8
  int v262; // eax
  int v263; // eax
  int v264; // eax
  __int64 v265; // rax
  int v266; // eax
  int v267; // eax
  unsigned __int64 v268; // rax
  unsigned __int64 v269; // rcx
  int v270; // eax
  unsigned int v271; // eax
  SIZE_T v272; // rcx
  bool v273; // zf
  int v274; // eax
  SIZE_T v275; // rax
  SIZE_T v276; // rcx
  BOOL v277; // eax
  char v278; // al
  SIZE_T v279; // rcx
  __int64 v280; // rax
  SIZE_T v281; // rax
  SIZE_T v282; // rax
  char *v283; // rax
  __int64 result; // rax
  int v285; // [rsp+28h] [rbp-E0h]
  unsigned int v286; // [rsp+38h] [rbp-D0h]
  int v287[4]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v288; // [rsp+50h] [rbp-B8h]
  _QWORD v289[7]; // [rsp+58h] [rbp-B0h] BYREF
  int cbMultiByte[4]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v291; // [rsp+A0h] [rbp-68h]
  SIZE_T uBytes; // [rsp+A8h] [rbp-60h]
  bool v293; // [rsp+B0h] [rbp-58h]
  bool v294; // [rsp+B1h] [rbp-57h]
  bool v295; // [rsp+B2h] [rbp-56h]
  bool v296; // [rsp+B3h] [rbp-55h]
  bool v297; // [rsp+B4h] [rbp-54h]
  bool v298; // [rsp+B5h] [rbp-53h]
  SIZE_T v299; // [rsp+B8h] [rbp-50h]
  SIZE_T v300; // [rsp+C0h] [rbp-48h]
  int v301; // [rsp+C8h] [rbp-40h]
  int v302; // [rsp+CCh] [rbp-3Ch]
  int v303; // [rsp+D0h] [rbp-38h]
  char *v304; // [rsp+D8h] [rbp-30h]
  int v305; // [rsp+E0h] [rbp-28h]
  int v306; // [rsp+E4h] [rbp-24h]
  char *v307; // [rsp+E8h] [rbp-20h]
  __int128 v308; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v309; // [rsp+100h] [rbp-8h]
  char *v310; // [rsp+108h] [rbp+0h]
  unsigned __int64 v311; // [rsp+110h] [rbp+8h]
  char *v312; // [rsp+118h] [rbp+10h]
  char *v313; // [rsp+120h] [rbp+18h]
  char *v314; // [rsp+128h] [rbp+20h]
  SIZE_T v315; // [rsp+130h] [rbp+28h]
  SIZE_T v316; // [rsp+138h] [rbp+30h]
  SIZE_T v317; // [rsp+140h] [rbp+38h]
  SIZE_T v318; // [rsp+148h] [rbp+40h]
  SIZE_T v319; // [rsp+150h] [rbp+48h]
  SIZE_T v320; // [rsp+158h] [rbp+50h]
  SIZE_T v321; // [rsp+160h] [rbp+58h]
  _OWORD *v322; // [rsp+168h] [rbp+60h]
  SIZE_T v323; // [rsp+170h] [rbp+68h]
  SIZE_T v324; // [rsp+178h] [rbp+70h]
  SIZE_T v325; // [rsp+180h] [rbp+78h]
  SIZE_T v326; // [rsp+188h] [rbp+80h]
  char *v327; // [rsp+190h] [rbp+88h]
  SIZE_T v328; // [rsp+198h] [rbp+90h]
  char *v329; // [rsp+1A0h] [rbp+98h]
  unsigned __int64 v330; // [rsp+1A8h] [rbp+A0h]
  unsigned __int64 v331; // [rsp+1B0h] [rbp+A8h]
  unsigned __int64 v332; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v333; // [rsp+1C0h] [rbp+B8h]
  unsigned __int64 v334; // [rsp+1C8h] [rbp+C0h]
  char *v335; // [rsp+1D0h] [rbp+C8h]
  unsigned __int64 v336; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 v337; // [rsp+1E0h] [rbp+D8h]
  unsigned __int64 v338; // [rsp+1E8h] [rbp+E0h]
  unsigned __int64 v339; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v340; // [rsp+1F8h] [rbp+F0h]
  unsigned __int64 v341; // [rsp+200h] [rbp+F8h]
  unsigned __int64 v342; // [rsp+208h] [rbp+100h]
  unsigned __int64 v343; // [rsp+210h] [rbp+108h]
  unsigned __int64 v344; // [rsp+218h] [rbp+110h]
  unsigned __int64 v345; // [rsp+220h] [rbp+118h]
  unsigned int v346; // [rsp+228h] [rbp+120h] BYREF
  int v347; // [rsp+22Ch] [rbp+124h]
  unsigned int v348; // [rsp+230h] [rbp+128h]
  unsigned __int64 v349; // [rsp+238h] [rbp+130h]
  unsigned __int64 v350; // [rsp+240h] [rbp+138h] BYREF
  unsigned __int64 v351; // [rsp+248h] [rbp+140h] BYREF
  __int64 v352; // [rsp+250h] [rbp+148h]
  unsigned __int64 v353; // [rsp+258h] [rbp+150h] BYREF
  unsigned __int64 v354; // [rsp+260h] [rbp+158h] BYREF
  unsigned __int64 v355; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 v356; // [rsp+270h] [rbp+168h] BYREF
  unsigned __int64 v357; // [rsp+278h] [rbp+170h] BYREF
  unsigned __int64 v358; // [rsp+280h] [rbp+178h] BYREF
  unsigned __int64 v359; // [rsp+288h] [rbp+180h] BYREF
  unsigned __int64 v360; // [rsp+290h] [rbp+188h] BYREF
  unsigned __int64 v361; // [rsp+298h] [rbp+190h] BYREF
  unsigned __int64 v362; // [rsp+2A0h] [rbp+198h] BYREF
  unsigned __int64 v363; // [rsp+2A8h] [rbp+1A0h] BYREF
  unsigned __int64 v364; // [rsp+2B0h] [rbp+1A8h] BYREF
  unsigned __int64 v365; // [rsp+2B8h] [rbp+1B0h] BYREF
  unsigned __int64 v366; // [rsp+2C0h] [rbp+1B8h] BYREF
  unsigned __int64 v367; // [rsp+2C8h] [rbp+1C0h] BYREF
  unsigned __int64 v368; // [rsp+2D0h] [rbp+1C8h] BYREF
  unsigned __int64 v369; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int64 v370; // [rsp+2E0h] [rbp+1D8h] BYREF
  unsigned __int64 v371; // [rsp+2E8h] [rbp+1E0h] BYREF
  char *v372; // [rsp+2F0h] [rbp+1E8h]
  unsigned __int64 v373; // [rsp+2F8h] [rbp+1F0h]
  SIZE_T v374; // [rsp+300h] [rbp+1F8h]
  unsigned __int64 v375; // [rsp+308h] [rbp+200h] BYREF
  unsigned __int64 v376; // [rsp+310h] [rbp+208h] BYREF
  unsigned __int64 v377; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int64 v378; // [rsp+320h] [rbp+218h] BYREF
  int v379[2]; // [rsp+328h] [rbp+220h] BYREF
  int v380[2]; // [rsp+330h] [rbp+228h] BYREF
  __int64 v381; // [rsp+338h] [rbp+230h]
  int v382[2]; // [rsp+340h] [rbp+238h] BYREF
  int v383[2]; // [rsp+348h] [rbp+240h] BYREF
  int v384[2]; // [rsp+350h] [rbp+248h] BYREF
  __int64 v385; // [rsp+358h] [rbp+250h]
  int v386[2]; // [rsp+360h] [rbp+258h] BYREF
  int v387[2]; // [rsp+368h] [rbp+260h] BYREF
  int v388[2]; // [rsp+370h] [rbp+268h] BYREF
  __int64 v389; // [rsp+378h] [rbp+270h]
  int v390[2]; // [rsp+380h] [rbp+278h] BYREF
  int v391[2]; // [rsp+388h] [rbp+280h] BYREF
  __int64 i; // [rsp+390h] [rbp+288h]
  _OWORD v393[2]; // [rsp+398h] [rbp+290h] BYREF
  __int64 v394; // [rsp+3B8h] [rbp+2B0h]
  wil::details::in1diag3 *retaddr; // [rsp+410h] [rbp+308h]
  bool v400; // [rsp+440h] [rbp+338h]

  v5 = a1;
  v304 = 0;
  v6 = a3;
  v7 = 0;
  v8 = 0;
  memset(v289, 0, sizeof(v289));
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNIncreaseRpcBufferSize>::GetImpl'::`2'::impl);
  v12 = a2;
  if ( IsEnabled )
  {
    if ( !a2 || (unsigned int)(v5 - 1) > 0xFFFFF )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                              v10,
                              v11) )
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
      v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v286 = v13;
      if ( !v13 )
      {
        v13 = 3;
        LODWORD(v289[5]) = 7334;
        v286 = 3;
      }
      goto LABEL_1285;
    }
  }
  else if ( !a2 || (unsigned int)(v5 - 1) > 0xFFFF )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            v10,
                            v11) )
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
    v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v286 = v13;
    if ( !v13 )
    {
      v13 = 3;
      LODWORD(v289[5]) = 7353;
      v286 = 3;
    }
    goto LABEL_1285;
  }
  v299 = 0;
  v14 = v5;
  v347 = 0;
  for ( i = v5; ; v14 = i )
  {
    v15 = 0;
    v16 = v304;
    v17 = 0;
    v301 = 0;
    v302 = 0;
    v291 = 0;
    v303 = 0;
    v307 = 0;
    v311 = 0;
    v329 = 0;
    v349 = 0;
    v18 = 0;
    v310 = 0;
    v330 = 0;
    v372 = 0;
    v312 = 0;
    v331 = 0;
    v313 = 0;
    v332 = 0;
    v314 = 0;
    v333 = 0;
    v327 = 0;
    v334 = 0;
    v335 = 0;
    v373 = 0;
    v381 = 0;
    v316 = 0;
    v336 = 0;
    v400 = 0;
    v374 = 0;
    v389 = 0;
    v293 = 0;
    v294 = 0;
    v317 = 0;
    v337 = 0;
    *(_QWORD *)v390 = 0;
    v318 = 0;
    v338 = 0;
    *(_QWORD *)v391 = 0;
    *(_QWORD *)v379 = 0;
    *(_QWORD *)v380 = 0;
    *(_QWORD *)v388 = 0;
    *(_QWORD *)v382 = 0;
    v305 = 0;
    v319 = 0;
    v339 = 0;
    v295 = 0;
    v320 = 0;
    v340 = 0;
    v321 = 0;
    v341 = 0;
    v352 = 0;
    v323 = 0;
    v343 = 0;
    v306 = 0;
    v322 = 0;
    v342 = 0;
    *(_QWORD *)v383 = 0;
    *(_QWORD *)v384 = 0;
    v344 = 0;
    v324 = 0;
    v345 = 0;
    v325 = 0;
    v385 = 0;
    v348 = 0;
    *(_QWORD *)v387 = 0;
    *(_QWORD *)v386 = 0;
    uBytes = 0;
    memset(&v289[3], 0, 32);
    v289[0] = v304;
    *(_OWORD *)&v289[1] = v8;
    v393[0] = 0;
    *(_OWORD *)cbMultiByte = 0;
    v19 = cbor_parser_init(v12, v14, 0, (unsigned int)v393, (__int64)cbMultiByte);
    v286 = v19;
    v21 = v19;
    v300 = 0;
    if ( v19 )
    {
      LODWORD(v289[3]) = v19;
      LODWORD(v289[5]) = 7449;
      v289[6] = 0;
      goto LABEL_22;
    }
    if ( !v16 )
      goto LABEL_21;
    v22 = v299;
    if ( v299 >= 0x238 )
    {
      v300 = (SIZE_T)v16;
LABEL_21:
      v21 = LODWORD(v289[3]);
      v18 = 568;
      uBytes = 568;
      v289[2] = 568;
      v286 = v289[3];
LABEL_22:
      v22 = v299;
      goto LABEL_23;
    }
    v21 = (unsigned int)_mm_cvtsi128_si32((__m128i)0LL);
    v286 = v21;
    if ( !(_DWORD)v21 )
    {
      v21 = 0x80000000LL;
      LODWORD(v289[5]) = 7453;
      v286 = 0x80000000;
      LODWORD(v289[3]) = 0x80000000;
      v289[6] = 0;
    }
LABEL_23:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_43;
    if ( BYTE6(v291) != 0xA0 )
    {
      value = 260;
LABEL_29:
      v21 = value;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      v286 = value;
      LODWORD(v289[3]) = value;
      LODWORD(v289[5]) = 7456;
      v289[6] = 0;
      goto LABEL_43;
    }
    value = cbor_value_map_find_value(cbMultiByte, "command", v287);
    if ( value )
      goto LABEL_29;
    if ( BYTE6(v288) == 0xFF )
    {
      value = 259;
      goto LABEL_29;
    }
    v301 = -1;
    if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
    {
      v26 = 260;
LABEL_40:
      v21 = v26;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v26;
      LODWORD(v289[3]) = v26;
      LODWORD(v289[5]) = 7458;
      v289[6] = 0;
      goto LABEL_41;
    }
    if ( (v288 & 0x100000000000000LL) != 0 )
      v25 = cbor_value_decode_int64_internal(v287, v24);
    else
      v25 = WORD2(v288);
    v26 = cbor_value_advance_fixed(v287);
    if ( v26 )
      goto LABEL_40;
    v21 = v286;
    if ( v25 <= 0xFFFFFFFF )
    {
      v301 = v25;
      goto LABEL_43;
    }
    v26 = 1024;
LABEL_41:
    if ( !(_DWORD)v21 )
    {
      v21 = v26;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v26;
      LODWORD(v289[3]) = v26;
      LODWORD(v289[5]) = 7458;
      v289[6] = 0;
    }
LABEL_43:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_63;
    if ( BYTE6(v291) != 0xA0 )
    {
      v27 = 260;
LABEL_49:
      v21 = v27;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      v286 = v27;
      LODWORD(v289[3]) = v27;
      LODWORD(v289[5]) = 7461;
      v289[6] = 0;
      goto LABEL_63;
    }
    v27 = cbor_value_map_find_value(cbMultiByte, "flags", v287);
    if ( v27 )
      goto LABEL_49;
    if ( BYTE6(v288) == 0xFF )
    {
      v27 = 259;
      goto LABEL_49;
    }
    v302 = -1;
    if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
    {
      v30 = 260;
LABEL_60:
      v21 = v30;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v30;
      LODWORD(v289[3]) = v30;
      LODWORD(v289[5]) = 7463;
      v289[6] = 0;
      goto LABEL_61;
    }
    if ( (v288 & 0x100000000000000LL) != 0 )
      v29 = cbor_value_decode_int64_internal(v287, v28);
    else
      v29 = WORD2(v288);
    v30 = cbor_value_advance_fixed(v287);
    if ( v30 )
      goto LABEL_60;
    v21 = v286;
    if ( v29 <= 0xFFFFFFFF )
    {
      v302 = v29;
      goto LABEL_63;
    }
    v30 = 1024;
LABEL_61:
    if ( !(_DWORD)v21 )
    {
      v21 = v30;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v30;
      LODWORD(v289[3]) = v30;
      LODWORD(v289[5]) = 7463;
      v289[6] = 0;
    }
LABEL_63:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_83;
    if ( BYTE6(v291) != 0xA0 )
    {
      v31 = 260;
LABEL_69:
      v21 = v31;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      v286 = v31;
      LODWORD(v289[3]) = v31;
      LODWORD(v289[5]) = 7466;
      v289[6] = 0;
      goto LABEL_83;
    }
    v31 = cbor_value_map_find_value(cbMultiByte, "timeout", v287);
    if ( v31 )
      goto LABEL_69;
    if ( BYTE6(v288) == 0xFF )
    {
      v31 = 259;
      goto LABEL_69;
    }
    v303 = -1;
    if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
    {
      v34 = 260;
LABEL_80:
      v21 = v34;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v34;
      LODWORD(v289[3]) = v34;
      LODWORD(v289[5]) = 7468;
      v289[6] = 0;
      goto LABEL_81;
    }
    if ( (v288 & 0x100000000000000LL) != 0 )
      v33 = cbor_value_decode_int64_internal(v287, v32);
    else
      v33 = WORD2(v288);
    v34 = cbor_value_advance_fixed(v287);
    if ( v34 )
      goto LABEL_80;
    v21 = v286;
    if ( v33 <= 0xFFFFFFFF )
    {
      v303 = v33;
      goto LABEL_83;
    }
    v34 = 1024;
LABEL_81:
    if ( !(_DWORD)v21 )
    {
      v21 = v34;
      v289[4] = *(_QWORD *)&v287[2];
      v286 = v34;
      LODWORD(v289[3]) = v34;
      LODWORD(v289[5]) = 7468;
      v289[6] = 0;
    }
LABEL_83:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_109;
    if ( BYTE6(v291) != 0xA0 )
    {
      v35 = 260;
LABEL_86:
      v21 = v35;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      v286 = v35;
      LODWORD(v289[3]) = v35;
      LODWORD(v289[5]) = 7471;
      v289[6] = 0;
      goto LABEL_109;
    }
    v35 = cbor_value_map_find_value(cbMultiByte, "transactionId", v287);
    if ( v35 )
      goto LABEL_86;
    if ( BYTE6(v288) == 0xFF )
    {
      v35 = 259;
      goto LABEL_86;
    }
    v21 = v286;
    v350 = 0;
    v311 = 0;
    v307 = 0;
    if ( BYTE6(v288) != 64 )
    {
      v36 = 260;
      goto LABEL_108;
    }
    if ( (v288 & 0x400000000000000LL) != 0 )
    {
      v36 = 2;
      v307 = 0;
      v311 = 0;
LABEL_107:
      if ( (_DWORD)v21 )
        goto LABEL_109;
LABEL_108:
      v21 = v36;
      v286 = v36;
      LODWORD(v289[3]) = v36;
      v289[4] = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7473;
      v289[6] = 0;
      goto LABEL_109;
    }
    v37 = (v288 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v287, v286) : WORD2(v288);
    v350 = v37;
    v38 = 0;
    v307 = 0;
    if ( v37 > 0x40000 )
    {
      v40 = 1024;
    }
    else
    {
      v39 = (v37 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v16 )
        goto LABEL_101;
      if ( v18 + v39 <= v22 )
      {
        v38 = &v16[v18];
        v307 = &v16[v18];
LABEL_101:
        v18 += v39;
        uBytes = v18;
        v289[2] = v18;
        goto LABEL_104;
      }
      v40 = 0x80000000;
    }
    v286 = v40;
    LODWORD(v289[3]) = v40;
    v289[4] = *(_QWORD *)&v287[2];
    LODWORD(v289[5]) = 7473;
    v289[6] = 0;
LABEL_104:
    v36 = cbor_value_copy_string(v287, v38, &v350, v287);
    v21 = v286;
    v311 = v350;
    if ( v36 )
      goto LABEL_107;
LABEL_109:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_114;
    if ( BYTE6(v291) != 0xA0 )
    {
      v41 = 260;
LABEL_112:
      v21 = v41;
      v286 = v41;
      LODWORD(v289[3]) = v41;
      v42 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7476;
LABEL_113:
      v289[6] = 0;
      v289[4] = v42;
      goto LABEL_114;
    }
    v41 = cbor_value_map_find_value(cbMultiByte, "ticket", v287);
    if ( v41 )
      goto LABEL_112;
    if ( BYTE6(v288) == 0xFF )
      v41 = 259;
    v21 = v286;
    if ( !v41 )
    {
      v349 = 0;
      v56 = 0;
      v378 = 0;
      if ( v286 )
      {
        v57 = 260;
        v349 = 0;
        goto LABEL_175;
      }
      if ( BYTE6(v288) != 64 )
      {
        v57 = 260;
        v329 = 0;
        v349 = 0;
        goto LABEL_177;
      }
      if ( (v288 & 0x400000000000000LL) == 0 )
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v58 = cbor_value_decode_int64_internal(v287, v286);
        else
          v58 = WORD2(v288);
        v378 = v58;
        v329 = 0;
        if ( v58 > 0x40000 || v18 > 0x40000 )
        {
          v60 = 1024;
LABEL_171:
          v286 = v60;
          LODWORD(v289[3]) = v60;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7478;
          v289[6] = 0;
        }
        else
        {
          v59 = (v58 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v18 + v59 > v22 )
            {
              v60 = 0x80000000;
              goto LABEL_171;
            }
            v15 = (unsigned __int64)&v16[v18];
            v329 = &v16[v18];
          }
          v18 += v59;
          uBytes = v18;
          v289[2] = v18;
        }
        v57 = cbor_value_copy_string(v287, v15, &v378, v287);
        v56 = v378;
        v21 = v286;
        v349 = v378;
        if ( v57 )
        {
          v15 = 0;
          goto LABEL_176;
        }
        goto LABEL_178;
      }
      v57 = 2;
LABEL_175:
      v329 = 0;
LABEL_176:
      if ( (_DWORD)v21 )
      {
LABEL_178:
        v42 = *(_QWORD *)&v287[2];
        v15 = 0;
      }
      else
      {
LABEL_177:
        v21 = v57;
        v286 = v57;
        LODWORD(v289[3]) = v57;
        v42 = *(_QWORD *)&v287[2];
        v289[4] = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7478;
        v289[6] = 0;
      }
      if ( !v56 && !(_DWORD)v21 )
      {
        v21 = 769;
        LODWORD(v289[5]) = 7481;
        v286 = 769;
        LODWORD(v289[3]) = 769;
        goto LABEL_113;
      }
    }
LABEL_114:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_118;
    if ( BYTE6(v291) != 0xA0 )
    {
      v43 = 260;
LABEL_117:
      v21 = v43;
      v286 = v43;
      LODWORD(v289[3]) = v43;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7485;
      v289[6] = 0;
      goto LABEL_118;
    }
    v43 = cbor_value_map_find_value(cbMultiByte, "request", v287);
    if ( v43 )
      goto LABEL_117;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v43 = 259;
    if ( !v43 )
    {
      v330 = 0;
      v17 = 0;
      v376 = 0;
      if ( v286 )
      {
        v61 = 260;
        v330 = 0;
        goto LABEL_206;
      }
      if ( BYTE6(v288) != 64 )
      {
        v61 = 260;
        v310 = 0;
        v330 = 0;
LABEL_208:
        v21 = v61;
        v286 = v61;
        LODWORD(v289[3]) = v61;
        v289[4] = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7487;
        v289[6] = 0;
        goto LABEL_118;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v61 = 2;
LABEL_206:
        v310 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v62 = cbor_value_decode_int64_internal(v287, v286);
        else
          v62 = WORD2(v288);
        v376 = v62;
        v63 = 0;
        v310 = 0;
        if ( v62 > 0x40000 || v18 > 0x40000 )
        {
          v65 = 1024;
LABEL_202:
          v286 = v65;
          LODWORD(v289[3]) = v65;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7487;
          v289[6] = 0;
        }
        else
        {
          v64 = (v62 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v64 + v18 > v22 )
            {
              v65 = 0x80000000;
              goto LABEL_202;
            }
            v63 = &v16[v18];
            v310 = &v16[v18];
          }
          v18 += v64;
          uBytes = v18;
          v289[2] = v18;
        }
        v61 = cbor_value_copy_string(v287, v63, &v376, v287);
        v17 = v376;
        v21 = v286;
        v330 = v376;
        if ( !v61 )
          goto LABEL_118;
      }
      if ( (_DWORD)v21 )
        goto LABEL_118;
      goto LABEL_208;
    }
LABEL_118:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_123;
    if ( BYTE6(v291) != 0xA0 )
    {
      v44 = 260;
LABEL_121:
      v21 = v44;
      v286 = v44;
      LODWORD(v289[3]) = v44;
      v45 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7490;
      goto LABEL_122;
    }
    v44 = cbor_value_map_find_value(cbMultiByte, "pin", v287);
    if ( v44 )
      goto LABEL_121;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v44 = 259;
    if ( !v44 )
    {
      v331 = 0;
      v377 = 0;
      if ( v286 )
      {
        v66 = 260;
        v331 = 0;
        goto LABEL_233;
      }
      if ( BYTE6(v288) != 64 )
      {
        v66 = 260;
        v312 = 0;
        v331 = 0;
LABEL_235:
        v21 = v66;
        v286 = v66;
        LODWORD(v289[3]) = v66;
        v45 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7492;
LABEL_122:
        v289[6] = 0;
        v289[4] = v45;
        goto LABEL_123;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v66 = 2;
LABEL_233:
        v312 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v67 = cbor_value_decode_int64_internal(v287, v286);
        else
          v67 = WORD2(v288);
        v377 = v67;
        v68 = 0;
        v312 = 0;
        if ( v67 > 0x40000 || v18 > 0x40000 )
        {
          v70 = 1024;
LABEL_229:
          v286 = v70;
          LODWORD(v289[3]) = v70;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7492;
          v289[6] = 0;
        }
        else
        {
          v69 = (v67 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v69 + v18 > v22 )
            {
              v70 = 0x80000000;
              goto LABEL_229;
            }
            v68 = &v16[v18];
            v312 = &v16[v18];
          }
          v18 += v69;
          uBytes = v18;
          v289[2] = v18;
        }
        v66 = cbor_value_copy_string(v287, v68, &v377, v287);
        v21 = v286;
        v331 = v377;
        if ( !v66 )
          goto LABEL_123;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_235;
    }
LABEL_123:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_128;
    if ( BYTE6(v291) != 0xA0 )
    {
      v46 = 260;
LABEL_126:
      v21 = v46;
      v286 = v46;
      LODWORD(v289[3]) = v46;
      v47 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7495;
      goto LABEL_127;
    }
    v46 = cbor_value_map_find_value(cbMultiByte, "newPin", v287);
    if ( v46 )
      goto LABEL_126;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v46 = 259;
    if ( !v46 )
    {
      v332 = 0;
      v353 = 0;
      if ( v286 )
      {
        v71 = 260;
        v332 = 0;
        goto LABEL_260;
      }
      if ( BYTE6(v288) != 64 )
      {
        v71 = 260;
        v313 = 0;
        v332 = 0;
LABEL_262:
        v21 = v71;
        v286 = v71;
        LODWORD(v289[3]) = v71;
        v47 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7497;
LABEL_127:
        v289[6] = 0;
        v289[4] = v47;
        goto LABEL_128;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v71 = 2;
LABEL_260:
        v313 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v72 = cbor_value_decode_int64_internal(v287, v286);
        else
          v72 = WORD2(v288);
        v353 = v72;
        v73 = 0;
        v313 = 0;
        if ( v72 > 0x40000 || v18 > 0x40000 )
        {
          v75 = 1024;
LABEL_256:
          v286 = v75;
          LODWORD(v289[3]) = v75;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7497;
          v289[6] = 0;
        }
        else
        {
          v74 = (v72 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v74 + v18 > v22 )
            {
              v75 = 0x80000000;
              goto LABEL_256;
            }
            v73 = &v16[v18];
            v313 = &v16[v18];
          }
          v18 += v74;
          uBytes = v18;
          v289[2] = v18;
        }
        v71 = cbor_value_copy_string(v287, v73, &v353, v287);
        v21 = v286;
        v332 = v353;
        if ( !v71 )
          goto LABEL_128;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_262;
    }
LABEL_128:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_133;
    if ( BYTE6(v291) != 0xA0 )
    {
      v48 = 260;
LABEL_131:
      v21 = v48;
      v286 = v48;
      LODWORD(v289[3]) = v48;
      v49 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7500;
      goto LABEL_132;
    }
    v48 = cbor_value_map_find_value(cbMultiByte, "hmacSalt", v287);
    if ( v48 )
      goto LABEL_131;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v48 = 259;
    if ( !v48 )
    {
      v333 = 0;
      v354 = 0;
      if ( v286 )
      {
        v76 = 260;
        v333 = 0;
        goto LABEL_287;
      }
      if ( BYTE6(v288) != 64 )
      {
        v76 = 260;
        v314 = 0;
        v333 = 0;
LABEL_289:
        v21 = v76;
        v286 = v76;
        LODWORD(v289[3]) = v76;
        v49 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7502;
LABEL_132:
        v289[6] = 0;
        v289[4] = v49;
        goto LABEL_133;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v76 = 2;
LABEL_287:
        v314 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v77 = cbor_value_decode_int64_internal(v287, v286);
        else
          v77 = WORD2(v288);
        v354 = v77;
        v78 = 0;
        v314 = 0;
        if ( v77 > 0x40000 || v18 > 0x40000 )
        {
          v80 = 1024;
LABEL_283:
          v286 = v80;
          LODWORD(v289[3]) = v80;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7502;
          v289[6] = 0;
        }
        else
        {
          v79 = (v77 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v79 + v18 > v22 )
            {
              v80 = 0x80000000;
              goto LABEL_283;
            }
            v78 = &v16[v18];
            v314 = &v16[v18];
          }
          v18 += v79;
          uBytes = v18;
          v289[2] = v18;
        }
        v76 = cbor_value_copy_string(v287, v78, &v354, v287);
        v21 = v286;
        v333 = v354;
        if ( !v76 )
          goto LABEL_133;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_289;
    }
LABEL_133:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_138;
    if ( BYTE6(v291) != 0xA0 )
    {
      v50 = 260;
LABEL_136:
      v21 = v50;
      v286 = v50;
      LODWORD(v289[3]) = v50;
      v51 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7505;
      goto LABEL_137;
    }
    v50 = cbor_value_map_find_value(cbMultiByte, "userIdPrefix", v287);
    if ( v50 )
      goto LABEL_136;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v50 = 259;
    if ( !v50 )
    {
      v334 = 0;
      v355 = 0;
      if ( v286 )
      {
        v81 = 260;
        v334 = 0;
        goto LABEL_314;
      }
      if ( BYTE6(v288) != 64 )
      {
        v81 = 260;
        v327 = 0;
        v334 = 0;
LABEL_316:
        v21 = v81;
        v286 = v81;
        LODWORD(v289[3]) = v81;
        v51 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7507;
LABEL_137:
        v289[6] = 0;
        v289[4] = v51;
        goto LABEL_138;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v81 = 2;
LABEL_314:
        v327 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v82 = cbor_value_decode_int64_internal(v287, v286);
        else
          v82 = WORD2(v288);
        v355 = v82;
        v83 = 0;
        v327 = 0;
        if ( v82 > 0x40000 || v18 > 0x40000 )
        {
          v85 = 1024;
LABEL_310:
          v286 = v85;
          LODWORD(v289[3]) = v85;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7507;
          v289[6] = 0;
        }
        else
        {
          v84 = (v82 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v16 )
          {
            if ( v84 + v18 > v22 )
            {
              v85 = 0x80000000;
              goto LABEL_310;
            }
            v83 = &v16[v18];
            v327 = &v16[v18];
          }
          v18 += v84;
          uBytes = v18;
          v289[2] = v18;
        }
        v81 = cbor_value_copy_string(v287, v83, &v355, v287);
        v21 = v286;
        v334 = v355;
        if ( !v81 )
          goto LABEL_138;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_316;
    }
LABEL_138:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_142;
    if ( BYTE6(v291) != 0xA0 )
    {
      v52 = 260;
LABEL_141:
      v21 = v52;
      v286 = v52;
      LODWORD(v289[3]) = v52;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7510;
      v289[6] = 0;
LABEL_142:
      v53 = v299;
      goto LABEL_143;
    }
    v52 = cbor_value_map_find_value(cbMultiByte, "u2fAppId", v287);
    if ( v52 )
      goto LABEL_141;
    if ( BYTE6(v288) == 0xFF )
      v52 = 259;
    if ( v52 )
    {
      v21 = v286;
      v53 = v299;
      goto LABEL_143;
    }
    v351 = 0;
    if ( v286 )
    {
      v87 = 260;
    }
    else if ( BYTE6(v288) == 96 )
    {
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v87 = 2;
      }
      else
      {
        v88 = (v288 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v287, v86) : WORD2(v288);
        v351 = v88;
        if ( v88 <= 0x40000 )
        {
          v89 = LocalAlloc(0x40u, (unsigned int)(v88 + 1));
          if ( v89 )
          {
            v394 = 0;
            v393[1] = 0;
            v87 = cbor_value_copy_string(v287, v89, &v351, v287);
            if ( !v87 )
            {
              v15 = v351;
              goto LABEL_338;
            }
            LocalFree(v89);
          }
          else
          {
            v87 = 0x80000000;
          }
        }
        else
        {
          v87 = 1024;
        }
      }
    }
    else
    {
      v87 = 260;
    }
    v89 = 0;
    v351 = 0;
LABEL_338:
    v373 = v15;
    v335 = 0;
    if ( v87 )
    {
      v53 = v299;
      if ( !v286 )
      {
        LODWORD(v289[5]) = 7512;
        v286 = v87;
        LODWORD(v289[3]) = v87;
        v289[4] = *(_QWORD *)&v287[2];
        v289[6] = 0;
      }
      goto LABEL_355;
    }
    v20 = v15 + 1;
    v90 = 0;
    if ( v286 )
    {
      v53 = v299;
      goto LABEL_352;
    }
    if ( v20 > 0x40000 || v18 > 0x40000 )
    {
      v53 = v299;
      v92 = 1024;
    }
    else
    {
      v53 = v299;
      v91 = (v20 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v304 )
        goto LABEL_348;
      if ( v91 + v18 <= v299 )
      {
        v90 = &v304[v18];
        v335 = &v304[v18];
LABEL_348:
        v18 += v91;
        uBytes = v18;
        v289[2] = v18;
LABEL_352:
        if ( v90 )
          memcpy_0(v90, v89, v20);
        goto LABEL_354;
      }
      v92 = 0x80000000;
    }
    v286 = v92;
    LODWORD(v289[3]) = v92;
    v289[4] = *(_QWORD *)&v287[2];
    LODWORD(v289[5]) = 7512;
    v289[6] = 0;
    v335 = 0;
LABEL_354:
    v16 = v304;
LABEL_355:
    if ( v89 )
      LocalFree(v89);
    v21 = v286;
    if ( v87 && !v286 )
    {
      v21 = v87;
      v286 = v87;
      LODWORD(v289[3]) = v87;
      v289[4] = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7512;
      v289[6] = 0;
    }
LABEL_143:
    if ( (v301 & 0xFFFFFFFB) == 0 && !v17 && !(_DWORD)v21 )
    {
      v21 = 769;
      v286 = 769;
      LODWORD(v289[3]) = 769;
      v289[4] = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7517;
      v289[6] = 0;
    }
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_375;
    if ( BYTE6(v291) != 0xA0 )
    {
      v54 = 260;
LABEL_150:
      v21 = v54;
      v286 = v54;
      LODWORD(v289[3]) = v54;
      v55 = 0;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7521;
      v289[6] = 0;
      goto LABEL_376;
    }
    v54 = cbor_value_map_find_value(cbMultiByte, "deviceInfoList", v287);
    if ( v54 )
      goto LABEL_150;
    if ( BYTE6(v288) == 0xFF )
      v54 = 259;
    if ( v54 )
    {
      v21 = v286;
      goto LABEL_375;
    }
    v372 = 0;
    if ( !v286 )
    {
      if ( v18 > 0x40000 )
      {
        v93 = 1024;
        goto LABEL_373;
      }
      if ( v16 )
      {
        if ( v18 + 16 > v53 )
        {
          v93 = 0x80000000;
LABEL_373:
          LODWORD(v289[3]) = v93;
          LODWORD(v289[5]) = 7525;
          v289[6] = 0;
          goto LABEL_374;
        }
        v372 = &v16[v18];
      }
      v289[2] = v18 + 16;
    }
LABEL_374:
    my_cbor_decode_device_info_list((int)v289);
    v18 = v289[2];
    v21 = LODWORD(v289[3]);
    v286 = v289[3];
    uBytes = v289[2];
LABEL_375:
    v55 = 0;
LABEL_376:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_380;
    if ( BYTE6(v291) != 0xA0 )
    {
      v94 = 260;
LABEL_379:
      v21 = v94;
      v286 = v94;
      LODWORD(v289[3]) = v94;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7530;
      v289[6] = 0;
      goto LABEL_380;
    }
    v94 = cbor_value_map_find_value(cbMultiByte, "webAuthNPara", v287);
    if ( v94 )
      goto LABEL_379;
    if ( BYTE6(v288) == 0xFF )
      v94 = 259;
    if ( v94 )
    {
      v21 = v286;
    }
    else
    {
      my_cbor_decode_web_authn_para((int)v289);
      v18 = v289[2];
      v21 = LODWORD(v289[3]);
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_380:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_385;
    if ( BYTE6(v291) != 0xA0 )
    {
      v95 = 260;
LABEL_383:
      v21 = v95;
      v286 = v95;
      LODWORD(v289[3]) = v95;
      v96 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7535;
      goto LABEL_384;
    }
    v95 = cbor_value_map_find_value(cbMultiByte, "hmacSecretSaltValues", v287);
    if ( v95 )
      goto LABEL_383;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v95 = 259;
    if ( !v95 )
    {
      v336 = 0;
      v356 = 0;
      if ( v286 )
      {
        v112 = 260;
        v336 = 0;
        goto LABEL_458;
      }
      if ( BYTE6(v288) != 64 )
      {
        v112 = 260;
        v316 = 0;
        v336 = 0;
LABEL_460:
        v21 = v112;
        v286 = v112;
        LODWORD(v289[3]) = v112;
        v96 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7537;
LABEL_384:
        v289[6] = 0;
        v289[4] = v96;
        goto LABEL_385;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v112 = 2;
LABEL_458:
        v316 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v113 = cbor_value_decode_int64_internal(v287, v286);
        else
          v113 = WORD2(v288);
        v356 = v113;
        v114 = 0;
        v316 = 0;
        if ( v113 > 0x40000 || v18 > 0x40000 )
        {
          v116 = 1024;
LABEL_454:
          v286 = v116;
          LODWORD(v289[3]) = v116;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7537;
          v289[6] = 0;
        }
        else
        {
          v115 = (v113 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v115 + v18 > v289[1] )
            {
              v116 = 0x80000000;
              goto LABEL_454;
            }
            v114 = v18 + v289[0];
            v316 = v18 + v289[0];
          }
          v18 += v115;
          uBytes = v18;
          v289[2] = v18;
        }
        v112 = cbor_value_copy_string(v287, v114, &v356, v287);
        v21 = v286;
        v336 = v356;
        if ( !v112 )
          goto LABEL_385;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_460;
    }
LABEL_385:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_390;
    if ( BYTE6(v291) != 0xA0 )
    {
      v97 = 260;
LABEL_388:
      v21 = v97;
      v286 = v97;
      LODWORD(v289[3]) = v97;
      v98 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7540;
      goto LABEL_389;
    }
    v97 = cbor_value_map_find_value(cbMultiByte, "browserInPrivateMode", v287);
    if ( v97 )
      goto LABEL_388;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v97 = 259;
    if ( !v97 )
    {
      v400 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v288) != 0xF5 )
        {
          v117 = 260;
LABEL_469:
          v21 = v117;
          v286 = v117;
          LODWORD(v289[3]) = v117;
          v98 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7542;
LABEL_389:
          v289[6] = 0;
          v289[4] = v98;
          goto LABEL_390;
        }
        v400 = WORD2(v288) != 0;
        v117 = cbor_value_advance_fixed(v287);
        if ( v117 )
          goto LABEL_469;
        v21 = v286;
      }
    }
LABEL_390:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_394;
    if ( BYTE6(v291) != 0xA0 )
    {
      v99 = 260;
LABEL_393:
      v21 = v99;
      v286 = v99;
      LODWORD(v289[3]) = v99;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7545;
      v289[6] = 0;
      goto LABEL_394;
    }
    v99 = cbor_value_map_find_value(cbMultiByte, "hybridQrCodeState", v287);
    if ( v99 )
      goto LABEL_393;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v99 = 259;
    if ( !v99 )
    {
      v374 = 0;
      v118 = 0;
      if ( !v286 )
      {
        if ( v18 > 0x40000 )
        {
          v21 = 1024;
LABEL_483:
          v286 = v21;
          LODWORD(v289[3]) = v21;
          LODWORD(v289[5]) = 7258;
          v289[6] = 0;
        }
        else
        {
          if ( v289[0] )
          {
            if ( v18 + 32 > v289[1] )
            {
              v21 = 0x80000000LL;
              goto LABEL_483;
            }
            v118 = v18 + v289[0];
            v374 = v18 + v289[0];
          }
          v18 += 32LL;
          uBytes = v18;
          v289[2] = v18;
        }
      }
      v309 = 0;
      v119 = 0;
      v120 = 0;
      v121 = 0;
      v122 = 0;
      v308 = 0;
      if ( !(_DWORD)v21 )
      {
        if ( BYTE6(v288) != 0xA0 )
        {
          v123 = 260;
          goto LABEL_487;
        }
        v123 = cbor_value_map_find_value(v287, "privateKey", &v308);
        if ( v123 )
        {
LABEL_487:
          v21 = v123;
          v286 = v123;
          LODWORD(v289[3]) = v123;
          v124 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7267;
          goto LABEL_488;
        }
        if ( BYTE6(v309) == 0xFF )
          v123 = 259;
        v21 = v286;
        if ( !v123 )
        {
          v357 = 0;
          if ( v286 )
          {
            v127 = 260;
            goto LABEL_520;
          }
          if ( BYTE6(v309) != 64 )
          {
            v127 = 260;
            goto LABEL_521;
          }
          if ( (v309 & 0x400000000000000LL) != 0 )
          {
            v127 = 2;
            goto LABEL_520;
          }
          v128 = (v309 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(&v308, v286) : WORD2(v309);
          v357 = v128;
          if ( v128 > 0x40000 || v18 > 0x40000 )
          {
            v130 = 1024;
LABEL_516:
            v286 = v130;
            LODWORD(v289[3]) = v130;
            v289[4] = *((_QWORD *)&v308 + 1);
            LODWORD(v289[5]) = 7269;
            v289[6] = 0;
          }
          else
          {
            v129 = (v128 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            if ( v289[0] )
            {
              if ( v129 + v18 > v289[1] )
              {
                v130 = 0x80000000;
                goto LABEL_516;
              }
              v119 = v18 + v289[0];
            }
            v18 += v129;
            uBytes = v18;
            v289[2] = v18;
          }
          v127 = cbor_value_copy_string(&v308, v119, &v357, &v308);
          v120 = v357;
          v21 = v286;
          if ( v127 )
          {
LABEL_520:
            if ( !(_DWORD)v21 )
            {
LABEL_521:
              v21 = v127;
              v286 = v127;
              LODWORD(v289[3]) = v127;
              v124 = *((_QWORD *)&v308 + 1);
              LODWORD(v289[5]) = 7269;
LABEL_488:
              v289[6] = 0;
              v289[4] = v124;
            }
          }
        }
      }
      v309 = 0;
      v308 = 0;
      if ( !(_DWORD)v21 )
      {
        if ( BYTE6(v288) != 0xA0 )
        {
          v125 = 260;
          goto LABEL_492;
        }
        v125 = cbor_value_map_find_value(v287, "symetricSecret", &v308);
        if ( v125 )
        {
LABEL_492:
          v21 = v125;
          v286 = v125;
          LODWORD(v289[3]) = v125;
          v126 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7273;
          goto LABEL_493;
        }
        if ( BYTE6(v309) == 0xFF )
          v125 = 259;
        v21 = v286;
        if ( !v125 )
        {
          v358 = 0;
          if ( v286 )
          {
            v131 = 260;
            goto LABEL_546;
          }
          if ( BYTE6(v309) != 64 )
          {
            v131 = 260;
            goto LABEL_547;
          }
          if ( (v309 & 0x400000000000000LL) != 0 )
          {
            v131 = 2;
            goto LABEL_546;
          }
          v132 = (v309 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(&v308, v286) : WORD2(v309);
          v358 = v132;
          if ( v132 > 0x40000 || v18 > 0x40000 )
          {
            v134 = 1024;
LABEL_542:
            v286 = v134;
            LODWORD(v289[3]) = v134;
            v289[4] = *((_QWORD *)&v308 + 1);
            LODWORD(v289[5]) = 7275;
            v289[6] = 0;
          }
          else
          {
            v133 = (v132 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            if ( v289[0] )
            {
              if ( v133 + v18 > v289[1] )
              {
                v134 = 0x80000000;
                goto LABEL_542;
              }
              v121 = v18 + v289[0];
            }
            v18 += v133;
            uBytes = v18;
            v289[2] = v18;
          }
          v131 = cbor_value_copy_string(&v308, v121, &v358, &v308);
          v122 = v358;
          v21 = v286;
          if ( v131 )
          {
LABEL_546:
            if ( !(_DWORD)v21 )
            {
LABEL_547:
              v21 = v131;
              v286 = v131;
              LODWORD(v289[3]) = v131;
              v126 = *((_QWORD *)&v308 + 1);
              LODWORD(v289[5]) = 7275;
LABEL_493:
              v289[6] = 0;
              v289[4] = v126;
            }
          }
        }
      }
      if ( v118 )
      {
        *(_QWORD *)(v118 + 8) = v119;
        *(_DWORD *)v118 = v120;
        *(_QWORD *)(v118 + 24) = v121;
        *(_DWORD *)(v118 + 16) = v122;
      }
    }
LABEL_394:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_398;
    if ( BYTE6(v291) != 0xA0 )
    {
      v100 = 260;
LABEL_397:
      v21 = v100;
      v286 = v100;
      LODWORD(v289[3]) = v100;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7550;
      v289[6] = 0;
      goto LABEL_398;
    }
    v100 = cbor_value_map_find_value(cbMultiByte, "linkedData", v287);
    if ( v100 )
      goto LABEL_397;
    if ( BYTE6(v288) == 0xFF )
      v100 = 259;
    if ( v100 )
    {
      v21 = v286;
    }
    else
    {
      my_cbor_decode_hybrid_storage_linked_data((int)v289);
      v18 = v289[2];
      v21 = LODWORD(v289[3]);
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_398:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_403;
    if ( BYTE6(v291) != 0xA0 )
    {
      v101 = 260;
LABEL_401:
      v21 = v101;
      v286 = v101;
      LODWORD(v289[3]) = v101;
      v102 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7555;
      goto LABEL_402;
    }
    v101 = cbor_value_map_find_value(cbMultiByte, "autoFill", v287);
    if ( v101 )
      goto LABEL_401;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v101 = 259;
    if ( !v101 )
    {
      v293 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v288) != 0xF5 )
        {
          v135 = 260;
LABEL_562:
          v21 = v135;
          v286 = v135;
          LODWORD(v289[3]) = v135;
          v102 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7557;
LABEL_402:
          v289[6] = 0;
          v289[4] = v102;
          goto LABEL_403;
        }
        v293 = WORD2(v288) != 0;
        v135 = cbor_value_advance_fixed(v287);
        if ( v135 )
          goto LABEL_562;
        v21 = v286;
      }
    }
LABEL_403:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_408;
    if ( BYTE6(v291) != 0xA0 )
    {
      v103 = 260;
LABEL_406:
      v21 = v103;
      v286 = v103;
      LODWORD(v289[3]) = v103;
      v104 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7560;
      goto LABEL_407;
    }
    v103 = cbor_value_map_find_value(cbMultiByte, "filterHybridTransport", v287);
    if ( v103 )
      goto LABEL_406;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v103 = 259;
    if ( !v103 )
    {
      v294 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v288) != 0xF5 )
        {
          v136 = 260;
LABEL_572:
          v21 = v136;
          v286 = v136;
          LODWORD(v289[3]) = v136;
          v104 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7562;
LABEL_407:
          v289[6] = 0;
          v289[4] = v104;
          goto LABEL_408;
        }
        v294 = WORD2(v288) != 0;
        v136 = cbor_value_advance_fixed(v287);
        if ( v136 )
          goto LABEL_572;
        v21 = v286;
      }
    }
LABEL_408:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_413;
    if ( BYTE6(v291) != 0xA0 )
    {
      v105 = 260;
LABEL_411:
      v21 = v105;
      v286 = v105;
      LODWORD(v289[3]) = v105;
      v106 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7565;
      goto LABEL_412;
    }
    v105 = cbor_value_map_find_value(cbMultiByte, "json", v287);
    if ( v105 )
      goto LABEL_411;
    v21 = v286;
    if ( BYTE6(v288) == 0xFF )
      v105 = 259;
    if ( !v105 )
    {
      v337 = 0;
      v359 = 0;
      if ( v286 )
      {
        v137 = 260;
        v337 = 0;
        goto LABEL_598;
      }
      if ( BYTE6(v288) != 64 )
      {
        v137 = 260;
        v317 = 0;
        v337 = 0;
LABEL_600:
        v21 = v137;
        v286 = v137;
        LODWORD(v289[3]) = v137;
        v106 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7567;
LABEL_412:
        v289[6] = 0;
        v289[4] = v106;
        goto LABEL_413;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v137 = 2;
LABEL_598:
        v317 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v138 = cbor_value_decode_int64_internal(v287, v286);
        else
          v138 = WORD2(v288);
        v359 = v138;
        v139 = 0;
        v317 = 0;
        if ( v138 > 0x40000 || v18 > 0x40000 )
        {
          v141 = 1024;
LABEL_594:
          v286 = v141;
          LODWORD(v289[3]) = v141;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7567;
          v289[6] = 0;
        }
        else
        {
          v140 = (v138 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v140 + v18 > v289[1] )
            {
              v141 = 0x80000000;
              goto LABEL_594;
            }
            v139 = v18 + v289[0];
            v317 = v18 + v289[0];
          }
          v18 += v140;
          uBytes = v18;
          v289[2] = v18;
        }
        v137 = cbor_value_copy_string(v287, v139, &v359, v287);
        v21 = v286;
        v337 = v359;
        if ( !v137 )
          goto LABEL_413;
      }
      if ( !(_DWORD)v21 )
        goto LABEL_600;
    }
LABEL_413:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_417;
    if ( BYTE6(v291) != 0xA0 )
    {
      v107 = 260;
LABEL_416:
      v21 = v107;
      v286 = v107;
      LODWORD(v289[3]) = v107;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7570;
      v289[6] = 0;
      goto LABEL_417;
    }
    v107 = cbor_value_map_find_value(cbMultiByte, "rpId", v287);
    if ( v107 )
      goto LABEL_416;
    if ( BYTE6(v288) == 0xFF )
      v107 = 259;
    if ( v107 )
    {
      v21 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v390, 7572, v285);
      v18 = v289[2];
      v21 = LODWORD(v289[3]);
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_417:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( (_DWORD)v21 )
      goto LABEL_422;
    if ( BYTE6(v291) != 0xA0 )
    {
      v108 = 260;
LABEL_420:
      v286 = v108;
      LODWORD(v289[3]) = v108;
      v109 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7575;
      goto LABEL_421;
    }
    v108 = cbor_value_map_find_value(cbMultiByte, "credentialDetails", v287);
    if ( v108 )
      goto LABEL_420;
    if ( BYTE6(v288) == 0xFF )
      v108 = 259;
    if ( !v108 )
    {
      v142 = v286;
      v21 = 0;
      v338 = 0;
      v360 = 0;
      if ( v286 )
      {
        v143 = 260;
        v338 = 0;
        goto LABEL_631;
      }
      if ( BYTE6(v288) != 64 )
      {
        v143 = 260;
        v318 = 0;
        v338 = 0;
LABEL_633:
        v286 = v143;
        LODWORD(v289[3]) = v143;
        v109 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7577;
LABEL_421:
        v289[6] = 0;
        v289[4] = v109;
        goto LABEL_422;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v143 = 2;
LABEL_631:
        v318 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v144 = cbor_value_decode_int64_internal(v287, 0);
        else
          v144 = WORD2(v288);
        v360 = v144;
        v145 = 0;
        v318 = 0;
        if ( v144 > 0x40000 || v18 > 0x40000 )
        {
          v142 = 1024;
LABEL_627:
          v289[4] = *(_QWORD *)&v287[2];
          v286 = v142;
          LODWORD(v289[3]) = v142;
          LODWORD(v289[5]) = 7577;
          v289[6] = 0;
        }
        else
        {
          v146 = (v144 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v146 + v18 > v289[1] )
            {
              v142 = 0x80000000;
              goto LABEL_627;
            }
            v145 = v18 + v289[0];
            v318 = v18 + v289[0];
          }
          v18 += v146;
          uBytes = v18;
          v289[2] = v18;
        }
        v143 = cbor_value_copy_string(v287, v145, &v360, v287);
        v338 = v360;
        if ( !v143 )
          goto LABEL_422;
      }
      if ( !v142 )
        goto LABEL_633;
    }
LABEL_422:
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                             `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                             v21,
                             v20) )
      goto LABEL_723;
    v110 = v286;
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( !v286 )
    {
      if ( BYTE6(v291) != 0xA0 )
      {
        v111 = 260;
LABEL_426:
        v110 = v111;
        v286 = v111;
        LODWORD(v289[3]) = v111;
        v289[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v289[5]) = 7582;
        v289[6] = 0;
        goto LABEL_640;
      }
      v111 = cbor_value_map_find_value(cbMultiByte, "pluginAuthenticatorName", v287);
      if ( v111 )
        goto LABEL_426;
      if ( BYTE6(v288) == 0xFF )
        v111 = 259;
      if ( v111 )
      {
        v110 = 0;
      }
      else
      {
        my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v391, 7584, v285);
        v18 = v289[2];
        v110 = v289[3];
        v286 = v289[3];
        uBytes = v289[2];
      }
    }
LABEL_640:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_644;
    if ( BYTE6(v291) != 0xA0 )
    {
      v147 = 260;
LABEL_643:
      v110 = v147;
      v286 = v147;
      LODWORD(v289[3]) = v147;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7587;
      v289[6] = 0;
      goto LABEL_644;
    }
    v147 = cbor_value_map_find_value(cbMultiByte, "pluginClsId", v287);
    if ( v147 )
      goto LABEL_643;
    if ( BYTE6(v288) == 0xFF )
      v147 = 259;
    if ( v147 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v379, 7589, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_644:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_648;
    if ( BYTE6(v291) != 0xA0 )
    {
      v148 = 260;
LABEL_647:
      v110 = v148;
      v286 = v148;
      LODWORD(v289[3]) = v148;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7592;
      v289[6] = 0;
      goto LABEL_648;
    }
    v148 = cbor_value_map_find_value(cbMultiByte, "pluginNewClsId", v287);
    if ( v148 )
      goto LABEL_647;
    if ( BYTE6(v288) == 0xFF )
      v148 = 259;
    if ( v148 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v380, 7594, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_648:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_652;
    if ( BYTE6(v291) != 0xA0 )
    {
      v149 = 260;
LABEL_651:
      v110 = v149;
      v286 = v149;
      LODWORD(v289[3]) = v149;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7597;
      v289[6] = 0;
      goto LABEL_652;
    }
    v149 = cbor_value_map_find_value(cbMultiByte, "pluginLightLogo", v287);
    if ( v149 )
      goto LABEL_651;
    if ( BYTE6(v288) == 0xFF )
      v149 = 259;
    if ( v149 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v388, 7599, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_652:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_656;
    if ( BYTE6(v291) != 0xA0 )
    {
      v150 = 260;
LABEL_655:
      v110 = v150;
      v286 = v150;
      LODWORD(v289[3]) = v150;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7602;
      v289[6] = 0;
      goto LABEL_656;
    }
    v150 = cbor_value_map_find_value(cbMultiByte, "pluginDarkLogo", v287);
    if ( v150 )
      goto LABEL_655;
    if ( BYTE6(v288) == 0xFF )
      v150 = 259;
    if ( v150 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v382, 7604, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_656:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_661;
    if ( BYTE6(v291) != 0xA0 )
    {
      v151 = 260;
LABEL_659:
      v110 = v151;
      v286 = v151;
      LODWORD(v289[3]) = v151;
      v152 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7607;
LABEL_660:
      v289[6] = 0;
      v289[4] = v152;
      goto LABEL_661;
    }
    v151 = cbor_value_map_find_value(cbMultiByte, "authenticatorInfoLogoRequestType", v287);
    if ( v151 )
      goto LABEL_659;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v151 = 259;
    if ( !v151 )
    {
      v305 = -1;
      if ( v286 )
      {
        v187 = 260;
      }
      else
      {
        if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
        {
          v187 = 260;
        }
        else
        {
          if ( (v288 & 0x100000000000000LL) != 0 )
            v188 = cbor_value_decode_int64_internal(v287, v286);
          else
            v188 = WORD2(v288);
          v187 = cbor_value_advance_fixed(v287);
          if ( !v187 )
          {
            v110 = v286;
            if ( v188 <= 0xFFFFFFFF )
            {
              v305 = v188;
              goto LABEL_661;
            }
            v187 = 1024;
            goto LABEL_775;
          }
        }
        v110 = v187;
        v289[4] = *(_QWORD *)&v287[2];
        v286 = v187;
        LODWORD(v289[3]) = v187;
        LODWORD(v289[5]) = 7609;
        v289[6] = 0;
      }
LABEL_775:
      if ( !v110 )
      {
        v152 = *(_QWORD *)&v287[2];
        v110 = v187;
        v286 = v187;
        LODWORD(v289[3]) = v187;
        LODWORD(v289[5]) = 7609;
        goto LABEL_660;
      }
    }
LABEL_661:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_666;
    if ( BYTE6(v291) != 0xA0 )
    {
      v153 = 260;
LABEL_664:
      v110 = v153;
      v286 = v153;
      LODWORD(v289[3]) = v153;
      v154 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7612;
      goto LABEL_665;
    }
    v153 = cbor_value_map_find_value(cbMultiByte, "pluginIdKey", v287);
    if ( v153 )
      goto LABEL_664;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v153 = 259;
    if ( !v153 )
    {
      v339 = 0;
      v361 = 0;
      if ( v286 )
      {
        v189 = 260;
        v339 = 0;
        goto LABEL_801;
      }
      if ( BYTE6(v288) != 64 )
      {
        v189 = 260;
        v319 = 0;
        v339 = 0;
LABEL_803:
        v110 = v189;
        v286 = v189;
        LODWORD(v289[3]) = v189;
        v154 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7614;
LABEL_665:
        v289[6] = 0;
        v289[4] = v154;
        goto LABEL_666;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v189 = 2;
LABEL_801:
        v319 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v190 = cbor_value_decode_int64_internal(v287, v286);
        else
          v190 = WORD2(v288);
        v361 = v190;
        v191 = 0;
        v319 = 0;
        if ( v190 > 0x40000 || v18 > 0x40000 )
        {
          v193 = 1024;
LABEL_797:
          v286 = v193;
          LODWORD(v289[3]) = v193;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7614;
          v289[6] = 0;
        }
        else
        {
          v192 = (v190 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v192 + v18 > v289[1] )
            {
              v193 = 0x80000000;
              goto LABEL_797;
            }
            v191 = v18 + v289[0];
            v319 = v18 + v289[0];
          }
          v18 += v192;
          uBytes = v18;
          v289[2] = v18;
        }
        v189 = cbor_value_copy_string(v287, v191, &v361, v287);
        v110 = v286;
        v339 = v361;
        if ( !v189 )
          goto LABEL_666;
      }
      if ( !v110 )
        goto LABEL_803;
    }
LABEL_666:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_671;
    if ( BYTE6(v291) != 0xA0 )
    {
      v155 = 260;
LABEL_669:
      v110 = v155;
      v286 = v155;
      LODWORD(v289[3]) = v155;
      v156 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7617;
      goto LABEL_670;
    }
    v155 = cbor_value_map_find_value(cbMultiByte, "pluginAutofillScenarioSupported", v287);
    if ( v155 )
      goto LABEL_669;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v155 = 259;
    if ( !v155 )
    {
      v295 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v288) != 0xF5 )
        {
          v194 = 260;
LABEL_812:
          v110 = v194;
          v286 = v194;
          LODWORD(v289[3]) = v194;
          v156 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7619;
LABEL_670:
          v289[6] = 0;
          v289[4] = v156;
          goto LABEL_671;
        }
        v295 = WORD2(v288) != 0;
        v194 = cbor_value_advance_fixed(v287);
        if ( v194 )
          goto LABEL_812;
        v110 = v286;
      }
    }
LABEL_671:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_676;
    if ( BYTE6(v291) != 0xA0 )
    {
      v157 = 260;
LABEL_674:
      v110 = v157;
      v286 = v157;
      LODWORD(v289[3]) = v157;
      v158 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7622;
      goto LABEL_675;
    }
    v157 = cbor_value_map_find_value(cbMultiByte, "pluginAuthenticatorState", v287);
    if ( v157 )
      goto LABEL_674;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v157 = 259;
    if ( !v157 )
    {
      v340 = 0;
      v362 = 0;
      if ( v286 )
      {
        v195 = 260;
        v340 = 0;
        goto LABEL_838;
      }
      if ( BYTE6(v288) != 64 )
      {
        v195 = 260;
        v320 = 0;
        v340 = 0;
LABEL_840:
        v110 = v195;
        v286 = v195;
        LODWORD(v289[3]) = v195;
        v158 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7624;
LABEL_675:
        v289[6] = 0;
        v289[4] = v158;
        goto LABEL_676;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v195 = 2;
LABEL_838:
        v320 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v196 = cbor_value_decode_int64_internal(v287, v286);
        else
          v196 = WORD2(v288);
        v362 = v196;
        v197 = 0;
        v320 = 0;
        if ( v196 > 0x40000 || v18 > 0x40000 )
        {
          v199 = 1024;
LABEL_834:
          v286 = v199;
          LODWORD(v289[3]) = v199;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7624;
          v289[6] = 0;
        }
        else
        {
          v198 = (v196 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v198 + v18 > v289[1] )
            {
              v199 = 0x80000000;
              goto LABEL_834;
            }
            v197 = v18 + v289[0];
            v320 = v18 + v289[0];
          }
          v18 += v198;
          uBytes = v18;
          v289[2] = v18;
        }
        v195 = cbor_value_copy_string(v287, v197, &v362, v287);
        v110 = v286;
        v340 = v362;
        if ( !v195 )
          goto LABEL_676;
      }
      if ( !v110 )
        goto LABEL_840;
    }
LABEL_676:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_681;
    if ( BYTE6(v291) != 0xA0 )
    {
      v159 = 260;
LABEL_679:
      v110 = v159;
      v286 = v159;
      LODWORD(v289[3]) = v159;
      v160 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7627;
      goto LABEL_680;
    }
    v159 = cbor_value_map_find_value(cbMultiByte, "operationSignature", v287);
    if ( v159 )
      goto LABEL_679;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v159 = 259;
    if ( !v159 )
    {
      v341 = 0;
      v363 = 0;
      if ( v286 )
      {
        v200 = 260;
        v341 = 0;
        goto LABEL_865;
      }
      if ( BYTE6(v288) != 64 )
      {
        v200 = 260;
        v321 = 0;
        v341 = 0;
LABEL_867:
        v110 = v200;
        v286 = v200;
        LODWORD(v289[3]) = v200;
        v160 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7629;
LABEL_680:
        v289[6] = 0;
        v289[4] = v160;
        goto LABEL_681;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v200 = 2;
LABEL_865:
        v321 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v201 = cbor_value_decode_int64_internal(v287, v286);
        else
          v201 = WORD2(v288);
        v363 = v201;
        v202 = 0;
        v321 = 0;
        if ( v201 > 0x40000 || v18 > 0x40000 )
        {
          v204 = 1024;
LABEL_861:
          v286 = v204;
          LODWORD(v289[3]) = v204;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7629;
          v289[6] = 0;
        }
        else
        {
          v203 = (v201 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v203 + v18 > v289[1] )
            {
              v204 = 0x80000000;
              goto LABEL_861;
            }
            v202 = v18 + v289[0];
            v321 = v18 + v289[0];
          }
          v18 += v203;
          uBytes = v18;
          v289[2] = v18;
        }
        v200 = cbor_value_copy_string(v287, v202, &v363, v287);
        v110 = v286;
        v341 = v363;
        if ( !v200 )
          goto LABEL_681;
      }
      if ( !v110 )
        goto LABEL_867;
    }
LABEL_681:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_686;
    if ( BYTE6(v291) != 0xA0 )
    {
      v161 = 260;
LABEL_684:
      v110 = v161;
      v286 = v161;
      LODWORD(v289[3]) = v161;
      v162 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7632;
      goto LABEL_685;
    }
    v161 = cbor_value_map_find_value(cbMultiByte, "hwnd", v287);
    if ( v161 )
      goto LABEL_684;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v161 = 259;
    if ( !v161 )
    {
      v352 = -1;
      if ( !v286 )
      {
        if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
        {
          v206 = 260;
LABEL_881:
          v110 = v206;
          v286 = v206;
          LODWORD(v289[3]) = v206;
          v162 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7634;
LABEL_685:
          v289[6] = 0;
          v289[4] = v162;
          goto LABEL_686;
        }
        if ( (v288 & 0x100000000000000LL) != 0 )
          v205 = cbor_value_decode_int64_internal(v287, v286);
        else
          v205 = WORD2(v288);
        v352 = v205;
        v206 = cbor_value_advance_fixed(v287);
        if ( v206 )
          goto LABEL_881;
        v110 = v286;
      }
    }
LABEL_686:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_691;
    if ( BYTE6(v291) != 0xA0 )
    {
      v163 = 260;
LABEL_689:
      v110 = v163;
      v286 = v163;
      LODWORD(v289[3]) = v163;
      v164 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7637;
LABEL_690:
      v289[6] = 0;
      v289[4] = v164;
      goto LABEL_691;
    }
    v163 = cbor_value_map_find_value(cbMultiByte, "uvOperationType", v287);
    if ( v163 )
      goto LABEL_689;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v163 = 259;
    if ( !v163 )
    {
      v306 = -1;
      if ( v286 )
      {
        v207 = 260;
      }
      else
      {
        if ( BYTE6(v288) || (v288 & 0x200000000000000LL) != 0 )
        {
          v207 = 260;
        }
        else
        {
          if ( (v288 & 0x100000000000000LL) != 0 )
            v208 = cbor_value_decode_int64_internal(v287, v286);
          else
            v208 = WORD2(v288);
          v207 = cbor_value_advance_fixed(v287);
          if ( !v207 )
          {
            v110 = v286;
            if ( v208 <= 0xFFFFFFFF )
            {
              v306 = v208;
              goto LABEL_691;
            }
            v207 = 1024;
            goto LABEL_899;
          }
        }
        v110 = v207;
        v289[4] = *(_QWORD *)&v287[2];
        v286 = v207;
        LODWORD(v289[3]) = v207;
        LODWORD(v289[5]) = 7639;
        v289[6] = 0;
      }
LABEL_899:
      if ( !v110 )
      {
        v164 = *(_QWORD *)&v287[2];
        v110 = v207;
        v286 = v207;
        LODWORD(v289[3]) = v207;
        LODWORD(v289[5]) = 7639;
        goto LABEL_690;
      }
    }
LABEL_691:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_696;
    if ( BYTE6(v291) != 0xA0 )
    {
      v165 = 260;
LABEL_694:
      v110 = v165;
      v286 = v165;
      LODWORD(v289[3]) = v165;
      v166 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7642;
      goto LABEL_695;
    }
    v165 = cbor_value_map_find_value(cbMultiByte, "uvTransactionId", v287);
    if ( v165 )
      goto LABEL_694;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v165 = 259;
    if ( !v165 )
    {
      v342 = 0;
      v364 = 0;
      if ( v286 )
      {
        v209 = 260;
        v342 = 0;
        goto LABEL_925;
      }
      if ( BYTE6(v288) != 64 )
      {
        v209 = 260;
        v322 = 0;
        v342 = 0;
LABEL_927:
        v110 = v209;
        v286 = v209;
        LODWORD(v289[3]) = v209;
        v166 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7644;
LABEL_695:
        v289[6] = 0;
        v289[4] = v166;
        goto LABEL_696;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v209 = 2;
LABEL_925:
        v322 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v210 = cbor_value_decode_int64_internal(v287, v286);
        else
          v210 = WORD2(v288);
        v364 = v210;
        v211 = 0;
        v322 = 0;
        if ( v210 > 0x40000 || v18 > 0x40000 )
        {
          v213 = 1024;
LABEL_921:
          v286 = v213;
          LODWORD(v289[3]) = v213;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7644;
          v289[6] = 0;
        }
        else
        {
          v212 = (v210 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v212 + v18 > v289[1] )
            {
              v213 = 0x80000000;
              goto LABEL_921;
            }
            v211 = v18 + v289[0];
            v322 = (_OWORD *)(v18 + v289[0]);
          }
          v18 += v212;
          uBytes = v18;
          v289[2] = v18;
        }
        v209 = cbor_value_copy_string(v287, v211, &v364, v287);
        v110 = v286;
        v342 = v364;
        if ( !v209 )
          goto LABEL_696;
      }
      if ( !v110 )
        goto LABEL_927;
    }
LABEL_696:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_701;
    if ( BYTE6(v291) != 0xA0 )
    {
      v167 = 260;
LABEL_699:
      v110 = v167;
      v286 = v167;
      LODWORD(v289[3]) = v167;
      v168 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7647;
      goto LABEL_700;
    }
    v167 = cbor_value_map_find_value(cbMultiByte, "pluginUvOpRes", v287);
    if ( v167 )
      goto LABEL_699;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v167 = 259;
    if ( !v167 )
    {
      v343 = 0;
      v365 = 0;
      if ( v286 )
      {
        v214 = 260;
        v343 = 0;
        goto LABEL_952;
      }
      if ( BYTE6(v288) != 64 )
      {
        v214 = 260;
        v323 = 0;
        v343 = 0;
LABEL_954:
        v110 = v214;
        v286 = v214;
        LODWORD(v289[3]) = v214;
        v168 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7649;
LABEL_700:
        v289[6] = 0;
        v289[4] = v168;
        goto LABEL_701;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v214 = 2;
LABEL_952:
        v323 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v215 = cbor_value_decode_int64_internal(v287, v286);
        else
          v215 = WORD2(v288);
        v365 = v215;
        v216 = 0;
        v323 = 0;
        if ( v215 > 0x40000 || v18 > 0x40000 )
        {
          v218 = 1024;
LABEL_948:
          v286 = v218;
          LODWORD(v289[3]) = v218;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7649;
          v289[6] = 0;
        }
        else
        {
          v217 = (v215 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v217 + v18 > v289[1] )
            {
              v218 = 0x80000000;
              goto LABEL_948;
            }
            v216 = v18 + v289[0];
            v323 = v18 + v289[0];
          }
          v18 += v217;
          uBytes = v18;
          v289[2] = v18;
        }
        v214 = cbor_value_copy_string(v287, v216, &v365, v287);
        v110 = v286;
        v343 = v365;
        if ( !v214 )
          goto LABEL_701;
      }
      if ( !v110 )
        goto LABEL_954;
    }
LABEL_701:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_705;
    if ( BYTE6(v291) != 0xA0 )
    {
      v169 = 260;
LABEL_704:
      v110 = v169;
      v286 = v169;
      LODWORD(v289[3]) = v169;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7652;
      v289[6] = 0;
      goto LABEL_705;
    }
    v169 = cbor_value_map_find_value(cbMultiByte, "uvUsername", v287);
    if ( v169 )
      goto LABEL_704;
    if ( BYTE6(v288) == 0xFF )
      v169 = 259;
    if ( v169 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v383, 7654, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_705:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_709;
    if ( BYTE6(v291) != 0xA0 )
    {
      v170 = 260;
LABEL_708:
      v110 = v170;
      v286 = v170;
      LODWORD(v289[3]) = v170;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7657;
      v289[6] = 0;
      goto LABEL_709;
    }
    v170 = cbor_value_map_find_value(cbMultiByte, "uvContext", v287);
    if ( v170 )
      goto LABEL_708;
    if ( BYTE6(v288) == 0xFF )
      v170 = 259;
    if ( v170 )
    {
      v110 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v384, 7659, v285);
      v18 = v289[2];
      v110 = v289[3];
      v286 = v289[3];
      uBytes = v289[2];
    }
LABEL_709:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_714;
    if ( BYTE6(v291) != 0xA0 )
    {
      v171 = 260;
LABEL_712:
      v110 = v171;
      v286 = v171;
      LODWORD(v289[3]) = v171;
      v172 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7662;
      goto LABEL_713;
    }
    v171 = cbor_value_map_find_value(cbMultiByte, "authenticatorInfo", v287);
    if ( v171 )
      goto LABEL_712;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v171 = 259;
    if ( !v171 )
    {
      v344 = 0;
      v366 = 0;
      if ( v286 )
      {
        v219 = 260;
        v344 = 0;
        goto LABEL_991;
      }
      if ( BYTE6(v288) != 64 )
      {
        v219 = 260;
        v324 = 0;
        v344 = 0;
LABEL_993:
        v110 = v219;
        v286 = v219;
        LODWORD(v289[3]) = v219;
        v172 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7664;
LABEL_713:
        v289[6] = 0;
        v289[4] = v172;
        goto LABEL_714;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v219 = 2;
LABEL_991:
        v324 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v220 = cbor_value_decode_int64_internal(v287, v286);
        else
          v220 = WORD2(v288);
        v366 = v220;
        v221 = 0;
        v324 = 0;
        if ( v220 > 0x40000 || v18 > 0x40000 )
        {
          v223 = 1024;
LABEL_987:
          v286 = v223;
          LODWORD(v289[3]) = v223;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7664;
          v289[6] = 0;
        }
        else
        {
          v222 = (v220 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v222 + v18 > v289[1] )
            {
              v223 = 0x80000000;
              goto LABEL_987;
            }
            v221 = v18 + v289[0];
            v324 = v18 + v289[0];
          }
          v18 += v222;
          uBytes = v18;
          v289[2] = v18;
        }
        v219 = cbor_value_copy_string(v287, v221, &v366, v287);
        v110 = v286;
        v344 = v366;
        if ( !v219 )
          goto LABEL_714;
      }
      if ( !v110 )
        goto LABEL_993;
    }
LABEL_714:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v110 )
      goto LABEL_719;
    if ( BYTE6(v291) != 0xA0 )
    {
      v173 = 260;
LABEL_717:
      v110 = v173;
      v286 = v173;
      LODWORD(v289[3]) = v173;
      v174 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7667;
      goto LABEL_718;
    }
    v173 = cbor_value_map_find_value(cbMultiByte, "pluginNonce", v287);
    if ( v173 )
      goto LABEL_717;
    v110 = v286;
    if ( BYTE6(v288) == 0xFF )
      v173 = 259;
    if ( !v173 )
    {
      v345 = 0;
      v367 = 0;
      if ( v286 )
      {
        v224 = 260;
        v345 = 0;
        goto LABEL_1018;
      }
      if ( BYTE6(v288) != 64 )
      {
        v224 = 260;
        v325 = 0;
        v345 = 0;
LABEL_1020:
        v110 = v224;
        v286 = v224;
        LODWORD(v289[3]) = v224;
        v174 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7669;
LABEL_718:
        v289[6] = 0;
        v289[4] = v174;
        goto LABEL_719;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v224 = 2;
LABEL_1018:
        v325 = 0;
      }
      else
      {
        if ( (v288 & 0x100000000000000LL) != 0 )
          v225 = cbor_value_decode_int64_internal(v287, v286);
        else
          v225 = WORD2(v288);
        v367 = v225;
        v226 = 0;
        v325 = 0;
        if ( v225 > 0x40000 || v18 > 0x40000 )
        {
          v228 = 1024;
LABEL_1014:
          v286 = v228;
          LODWORD(v289[3]) = v228;
          v289[4] = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7669;
          v289[6] = 0;
        }
        else
        {
          v227 = (v225 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v289[0] )
          {
            if ( v227 + v18 > v289[1] )
            {
              v228 = 0x80000000;
              goto LABEL_1014;
            }
            v226 = v18 + v289[0];
            v325 = v18 + v289[0];
          }
          uBytes = v227 + v18;
          v289[2] = v227 + v18;
        }
        v224 = cbor_value_copy_string(v287, v226, &v367, v287);
        v110 = v286;
        v345 = v367;
        if ( !v224 )
          goto LABEL_719;
      }
      if ( !v110 )
        goto LABEL_1020;
    }
LABEL_719:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( !v110 )
    {
      if ( BYTE6(v291) != 0xA0 )
      {
        v175 = 260;
LABEL_722:
        v286 = v175;
        LODWORD(v289[3]) = v175;
        v289[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v289[5]) = 7672;
        v289[6] = 0;
        goto LABEL_723;
      }
      v175 = cbor_value_map_find_value(cbMultiByte, "supportedRpIds", v287);
      if ( v175 )
        goto LABEL_722;
      if ( BYTE6(v288) == 0xFF )
        v175 = 259;
      if ( !v175 )
      {
        v229 = my_cbor_decode_array_of_unicode_stringz((int)v289);
        v346 = 0;
        v230 = ULongLongToULong(v229, &v346);
        if ( v230 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x132,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\safecast.h",
            (const char *)(unsigned int)v230,
            v285);
        v348 = v346;
        v286 = v289[3];
        uBytes = v289[2];
      }
    }
LABEL_723:
    v297 = 0;
    v328 = 0;
    v176 = 0;
    v326 = 0;
    v177 = 0;
    v315 = 0;
    v178 = 0;
    v296 = 0;
    v179 = 0;
    v298 = 0;
    v180 = 0;
    v181 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
    {
      *(_OWORD *)v287 = 0;
      v288 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v291) != 0xA0 )
        {
          v182 = 260;
LABEL_727:
          v286 = v182;
          LODWORD(v289[3]) = v182;
          v183 = *(_QWORD *)&cbMultiByte[2];
          LODWORD(v289[5]) = 7681;
          goto LABEL_728;
        }
        v182 = cbor_value_map_find_value(cbMultiByte, "thirdPartyPayment", v287);
        if ( v182 )
          goto LABEL_727;
        if ( BYTE6(v288) == 0xFF )
          v182 = 259;
        if ( !v182 )
        {
          v297 = 0;
          if ( BYTE6(v288) != 0xF5 )
          {
            v231 = 260;
LABEL_1034:
            v286 = v231;
            LODWORD(v289[3]) = v231;
            v183 = *(_QWORD *)&v287[2];
            LODWORD(v289[5]) = 7683;
LABEL_728:
            v289[6] = 0;
            v289[4] = v183;
            goto LABEL_729;
          }
          v297 = WORD2(v288) != 0;
          v231 = cbor_value_advance_fixed(v287);
          if ( v231 )
            goto LABEL_1034;
        }
      }
    }
LABEL_729:
    v184 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::GetImpl'::`2'::impl);
    v185 = v286;
    if ( !v184 )
      goto LABEL_1167;
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( !v286 )
    {
      if ( BYTE6(v291) != 0xA0 )
      {
        v186 = 260;
LABEL_733:
        v185 = v186;
        v286 = v186;
        LODWORD(v289[3]) = v186;
        v289[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v289[5]) = 7697;
        v289[6] = 0;
        goto LABEL_1056;
      }
      v186 = cbor_value_map_find_value(cbMultiByte, "clientDataJSON", v287);
      if ( v186 )
        goto LABEL_733;
      if ( BYTE6(v288) == 0xFF )
        v186 = 259;
      if ( v186 )
      {
LABEL_1055:
        v185 = v286;
        goto LABEL_1056;
      }
      v368 = 0;
      if ( BYTE6(v288) != 64 )
      {
        v232 = 260;
        v55 = 0;
LABEL_1076:
        v185 = v232;
        v286 = v232;
        LODWORD(v289[3]) = v232;
        v289[4] = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7699;
        v289[6] = 0;
        goto LABEL_1056;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v232 = 2;
        v55 = 0;
        goto LABEL_1075;
      }
      if ( (v288 & 0x100000000000000LL) != 0 )
        v233 = cbor_value_decode_int64_internal(v287, 259);
      else
        v233 = WORD2(v288);
      v55 = 0;
      v368 = v233;
      if ( v233 <= 0x40000 && uBytes <= 0x40000 )
      {
        v234 = (v233 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( v289[0] )
        {
          if ( v234 + uBytes > v289[1] )
          {
            v235 = 0x80000000;
LABEL_1053:
            v286 = v235;
            LODWORD(v289[3]) = v235;
            v289[4] = *(_QWORD *)&v287[2];
            LODWORD(v289[5]) = 7699;
            v289[6] = 0;
LABEL_1054:
            v232 = cbor_value_copy_string(v287, v55, &v368, v287);
            v176 = v368;
            if ( !v232 )
              goto LABEL_1055;
LABEL_1075:
            v185 = v286;
            if ( v286 )
              goto LABEL_1056;
            goto LABEL_1076;
          }
          v55 = uBytes + v289[0];
        }
        uBytes += v234;
        v289[2] = uBytes;
        goto LABEL_1054;
      }
      v235 = 1024;
      goto LABEL_1053;
    }
LABEL_1056:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v185 )
      goto LABEL_1060;
    if ( BYTE6(v291) != 0xA0 )
    {
      v236 = 260;
LABEL_1059:
      v185 = v236;
      v286 = v236;
      LODWORD(v289[3]) = v236;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7702;
      v289[6] = 0;
      goto LABEL_1060;
    }
    v236 = cbor_value_map_find_value(cbMultiByte, "remoteWebOrigin", v287);
    if ( v236 )
      goto LABEL_1059;
    if ( BYTE6(v288) == 0xFF )
      v236 = 259;
    if ( v236 )
    {
      v185 = v286;
    }
    else
    {
      my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v387, 7704, v285);
      v185 = v289[3];
      uBytes = v289[2];
      v286 = v289[3];
    }
LABEL_1060:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v185 )
      goto LABEL_1065;
    if ( BYTE6(v291) != 0xA0 )
    {
      v237 = 260;
LABEL_1063:
      v185 = v237;
      v286 = v237;
      LODWORD(v289[3]) = v237;
      v238 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7707;
      v289[6] = 0;
      goto LABEL_1064;
    }
    v237 = cbor_value_map_find_value(cbMultiByte, "publicKeyCredentialCreationOptions", v287);
    if ( v237 )
      goto LABEL_1063;
    if ( BYTE6(v288) == 0xFF )
      v237 = 259;
    if ( v237 )
    {
LABEL_1110:
      v185 = v286;
      goto LABEL_1065;
    }
    v375 = 0;
    if ( v286 )
    {
      v242 = 260;
LABEL_1107:
      v328 = 0;
      goto LABEL_1108;
    }
    if ( BYTE6(v288) != 64 )
    {
      v242 = 260;
      v328 = 0;
LABEL_1109:
      v185 = v242;
      v286 = v242;
      LODWORD(v289[3]) = v242;
      v238 = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7709;
      v289[6] = 0;
LABEL_1064:
      v289[4] = v238;
      goto LABEL_1065;
    }
    if ( (v288 & 0x400000000000000LL) != 0 )
    {
      v242 = 2;
      goto LABEL_1107;
    }
    v243 = (v288 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v287, 259) : WORD2(v288);
    v375 = v243;
    v244 = 0;
    v328 = 0;
    if ( v243 > 0x40000 || uBytes > 0x40000 )
    {
      v246 = 1024;
    }
    else
    {
      v245 = (v243 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v289[0] )
        goto LABEL_1101;
      if ( v245 + uBytes <= v289[1] )
      {
        v244 = uBytes + v289[0];
        v328 = uBytes + v289[0];
LABEL_1101:
        uBytes += v245;
        v289[2] = uBytes;
        goto LABEL_1104;
      }
      v246 = 0x80000000;
    }
    v286 = v246;
    LODWORD(v289[3]) = v246;
    v289[4] = *(_QWORD *)&v287[2];
    LODWORD(v289[5]) = 7709;
    v289[6] = 0;
LABEL_1104:
    v242 = cbor_value_copy_string(v287, v244, &v375, v287);
    v177 = v375;
    if ( !v242 )
      goto LABEL_1110;
LABEL_1108:
    v185 = v286;
    if ( !v286 )
      goto LABEL_1109;
LABEL_1065:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v185 )
      goto LABEL_1070;
    if ( BYTE6(v291) != 0xA0 )
    {
      v239 = 260;
LABEL_1068:
      v185 = v239;
      v286 = v239;
      LODWORD(v289[3]) = v239;
      v240 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7712;
      v289[6] = 0;
      goto LABEL_1069;
    }
    v239 = cbor_value_map_find_value(cbMultiByte, "publicKeyCredentialRequestOptions", v287);
    if ( v239 )
      goto LABEL_1068;
    if ( BYTE6(v288) == 0xFF )
      v239 = 259;
    if ( v239 )
    {
LABEL_1138:
      v185 = v286;
      goto LABEL_1070;
    }
    v369 = 0;
    if ( v286 )
    {
      v247 = 260;
LABEL_1135:
      v326 = 0;
      goto LABEL_1136;
    }
    if ( BYTE6(v288) != 64 )
    {
      v247 = 260;
      v326 = 0;
LABEL_1137:
      v185 = v247;
      v286 = v247;
      LODWORD(v289[3]) = v247;
      v240 = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7714;
      v289[6] = 0;
LABEL_1069:
      v289[4] = v240;
      goto LABEL_1070;
    }
    if ( (v288 & 0x400000000000000LL) != 0 )
    {
      v247 = 2;
      goto LABEL_1135;
    }
    v248 = (v288 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v287, 259) : WORD2(v288);
    v369 = v248;
    v249 = 0;
    v326 = 0;
    if ( v248 > 0x40000 || uBytes > 0x40000 )
    {
      v251 = 1024;
    }
    else
    {
      v250 = (v248 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v289[0] )
        goto LABEL_1129;
      if ( uBytes + v250 <= v289[1] )
      {
        v249 = uBytes + v289[0];
        v326 = uBytes + v289[0];
LABEL_1129:
        uBytes += v250;
        v289[2] = uBytes;
        goto LABEL_1132;
      }
      v251 = 0x80000000;
    }
    v286 = v251;
    LODWORD(v289[3]) = v251;
    v289[4] = *(_QWORD *)&v287[2];
    LODWORD(v289[5]) = 7714;
    v289[6] = 0;
LABEL_1132:
    v247 = cbor_value_copy_string(v287, v249, &v369, v287);
    v178 = v369;
    if ( !v247 )
      goto LABEL_1138;
LABEL_1136:
    v185 = v286;
    if ( !v286 )
      goto LABEL_1137;
LABEL_1070:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v185 )
      goto LABEL_1167;
    if ( BYTE6(v291) != 0xA0 )
    {
      v241 = 260;
LABEL_1073:
      v185 = v241;
      v286 = v241;
      LODWORD(v289[3]) = v241;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7717;
      v289[6] = 0;
      goto LABEL_1167;
    }
    v241 = cbor_value_map_find_value(cbMultiByte, "authenticatorId", v287);
    if ( v241 )
      goto LABEL_1073;
    if ( BYTE6(v288) == 0xFF )
      v241 = 259;
    if ( v241 )
      goto LABEL_1166;
    v370 = 0;
    if ( v286 )
    {
      v252 = 260;
      goto LABEL_1163;
    }
    if ( BYTE6(v288) != 64 )
    {
      v252 = 260;
      v315 = 0;
      goto LABEL_1165;
    }
    if ( (v288 & 0x400000000000000LL) != 0 )
    {
      v252 = 2;
LABEL_1163:
      v315 = 0;
LABEL_1164:
      v185 = v286;
      if ( v286 )
        goto LABEL_1167;
LABEL_1165:
      v185 = v252;
      v286 = v252;
      LODWORD(v289[3]) = v252;
      v289[4] = *(_QWORD *)&v287[2];
      LODWORD(v289[5]) = 7719;
      v289[6] = 0;
      goto LABEL_1167;
    }
    v253 = (v288 & 0x100000000000000LL) != 0 ? cbor_value_decode_int64_internal(v287, 259) : WORD2(v288);
    v370 = v253;
    v254 = 0;
    v315 = 0;
    if ( v253 > 0x40000 || uBytes > 0x40000 )
    {
      v256 = 1024;
    }
    else
    {
      v255 = (v253 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( !v289[0] )
        goto LABEL_1157;
      if ( uBytes + v255 <= v289[1] )
      {
        v254 = uBytes + v289[0];
        v315 = uBytes + v289[0];
LABEL_1157:
        uBytes += v255;
        v289[2] = uBytes;
        goto LABEL_1160;
      }
      v256 = 0x80000000;
    }
    v286 = v256;
    LODWORD(v289[3]) = v256;
    v289[4] = *(_QWORD *)&v287[2];
    LODWORD(v289[5]) = 7719;
    v289[6] = 0;
LABEL_1160:
    v252 = cbor_value_copy_string(v287, v254, &v370, v287);
    v179 = v370;
    if ( v252 )
      goto LABEL_1164;
LABEL_1166:
    v185 = v286;
LABEL_1167:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v185 )
      goto LABEL_1172;
    if ( BYTE6(v291) != 0xA0 )
    {
      v257 = 260;
LABEL_1170:
      v286 = v257;
      LODWORD(v289[3]) = v257;
      v258 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7723;
      goto LABEL_1171;
    }
    v257 = cbor_value_map_find_value(cbMultiByte, "remoteWebAuthn", v287);
    if ( v257 )
      goto LABEL_1170;
    if ( BYTE6(v288) == 0xFF )
      v257 = 259;
    if ( !v257 )
    {
      v298 = 0;
      if ( !v286 )
      {
        if ( BYTE6(v288) != 0xF5 )
        {
          v263 = 260;
LABEL_1185:
          v286 = v263;
          LODWORD(v289[3]) = v263;
          v258 = *(_QWORD *)&v287[2];
          LODWORD(v289[5]) = 7725;
LABEL_1171:
          v289[6] = 0;
          v289[4] = v258;
          goto LABEL_1172;
        }
        v298 = WORD2(v288) != 0;
        v263 = cbor_value_advance_fixed(v287);
        if ( v263 )
          goto LABEL_1185;
      }
    }
LABEL_1172:
    v259 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl);
    v13 = v286;
    if ( !v259 )
      goto LABEL_1237;
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( !v286 )
    {
      if ( BYTE6(v291) != 0xA0 )
      {
        v262 = 260;
LABEL_1176:
        v13 = v262;
        v286 = v262;
        v289[4] = *(_QWORD *)&cbMultiByte[2];
        LODWORD(v289[5]) = 7730;
        v289[6] = 0;
        goto LABEL_1192;
      }
      v262 = cbor_value_map_find_value(cbMultiByte, "pluginUvKeyName", v287);
      if ( v262 )
        goto LABEL_1176;
      if ( BYTE6(v288) == 0xFF )
        v262 = 259;
      if ( v262 )
      {
        v13 = v286;
      }
      else
      {
        my_cbor_value_decoder_copy_unicode_stringz((int)v289, (int)v287, (int)v386, 7732, v285);
        v13 = v289[3];
        uBytes = v289[2];
        v286 = v289[3];
      }
    }
LABEL_1192:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v13 )
      goto LABEL_1197;
    if ( BYTE6(v291) != 0xA0 )
    {
      v264 = 260;
LABEL_1195:
      v13 = v264;
      v286 = v264;
      v265 = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7735;
      v289[6] = 0;
      goto LABEL_1196;
    }
    v264 = cbor_value_map_find_value(cbMultiByte, "pluginUvBufferToSign", v287);
    if ( v264 )
      goto LABEL_1195;
    v260 = 259;
    v13 = v286;
    if ( BYTE6(v288) == 0xFF )
      v264 = 259;
    if ( !v264 )
    {
      v371 = 0;
      if ( v286 )
      {
        v267 = 260;
        goto LABEL_1225;
      }
      if ( BYTE6(v288) != 64 )
      {
        v267 = 260;
LABEL_1226:
        v13 = v267;
        v286 = v267;
        v265 = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7737;
        v289[6] = 0;
LABEL_1196:
        v289[4] = v265;
        goto LABEL_1197;
      }
      if ( (v288 & 0x400000000000000LL) != 0 )
      {
        v267 = 2;
LABEL_1225:
        if ( !v13 )
          goto LABEL_1226;
        goto LABEL_1197;
      }
      if ( (v288 & 0x100000000000000LL) != 0 )
        v268 = cbor_value_decode_int64_internal(v287, 259);
      else
        v268 = WORD2(v288);
      v371 = v268;
      if ( v268 > 0x40000 || uBytes > 0x40000 )
      {
        v286 = 1024;
LABEL_1221:
        v289[4] = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7737;
        v289[6] = 0;
      }
      else
      {
        v269 = (v268 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( v289[0] )
        {
          if ( uBytes + v269 > v289[1] )
          {
            v286 = 0x80000000;
            goto LABEL_1221;
          }
          v180 = uBytes + v289[0];
        }
        uBytes += v269;
      }
      v267 = cbor_value_copy_string(v287, v180, &v371, v287);
      v181 = v371;
      v13 = v286;
      if ( !v267 )
        goto LABEL_1197;
      goto LABEL_1225;
    }
LABEL_1197:
    v288 = 0;
    *(_OWORD *)v287 = 0;
    if ( v13 )
      goto LABEL_1241;
    if ( BYTE6(v291) != 0xA0 )
    {
      v266 = 260;
LABEL_1200:
      v13 = v266;
      v286 = v266;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7740;
      v289[6] = 0;
      goto LABEL_1237;
    }
    v266 = cbor_value_map_find_value(cbMultiByte, "excludeThirdPartyCredentials", v287);
    if ( v266 )
      goto LABEL_1200;
    v260 = 259;
    v13 = v286;
    if ( BYTE6(v288) == 0xFF )
      v266 = 259;
    if ( !v266 )
    {
      v296 = 0;
      if ( v286 )
        goto LABEL_1241;
      if ( BYTE6(v288) != 0xF5 )
      {
        v270 = 260;
LABEL_1235:
        v13 = v270;
        v286 = v270;
        v289[4] = *(_QWORD *)&v287[2];
        LODWORD(v289[5]) = 7742;
        v289[6] = 0;
        goto LABEL_1237;
      }
      v296 = WORD2(v288) != 0;
      v270 = cbor_value_advance_fixed(v287);
      if ( v270 )
        goto LABEL_1235;
      v13 = v286;
    }
LABEL_1237:
    if ( v13 )
      goto LABEL_1241;
    v271 = cbor_value_advance(cbMultiByte);
    if ( !v271 )
    {
      v13 = v286;
LABEL_1241:
      v271 = v13;
      goto LABEL_1242;
    }
    v13 = v271;
    v289[4] = *(_QWORD *)&cbMultiByte[2];
    v286 = v271;
    LODWORD(v289[5]) = 7746;
    v289[6] = 0;
LABEL_1242:
    if ( (_DWORD)v291 && !v271 )
    {
      v13 = 1024;
      v286 = 1024;
      v289[4] = *(_QWORD *)&cbMultiByte[2];
      LODWORD(v289[5]) = 7750;
      v289[6] = 0;
    }
    v272 = v300;
    if ( v300 )
    {
      v273 = v311 == 16;
      v274 = v301;
      *(_DWORD *)v300 = 1;
      *(_DWORD *)(v272 + 4) = v274;
      *(_DWORD *)(v272 + 8) = v302;
      *(_DWORD *)(v272 + 12) = v303;
      *(_DWORD *)(v272 + 32) = v349;
      *(_QWORD *)(v272 + 40) = v329;
      *(_DWORD *)(v272 + 136) = v330;
      *(_QWORD *)(v272 + 144) = v310;
      *(_QWORD *)(v272 + 128) = v372;
      if ( v273 )
      {
        *(_OWORD *)(v272 + 16) = *(_OWORD *)v307;
      }
      else if ( !v13 )
      {
        v286 = 1;
        LODWORD(v289[5]) = 7767;
        v289[6] = 0;
      }
      *(_DWORD *)(v272 + 48) = v331;
      *(_QWORD *)(v272 + 56) = v312;
      *(_DWORD *)(v272 + 64) = v332;
      *(_QWORD *)(v272 + 72) = v313;
      *(_DWORD *)(v272 + 80) = v333;
      *(_QWORD *)(v272 + 88) = v314;
      *(_DWORD *)(v272 + 96) = v334;
      *(_QWORD *)(v272 + 104) = v327;
      *(_DWORD *)(v272 + 112) = v373;
      *(_QWORD *)(v272 + 120) = v335;
      *(_QWORD *)(v272 + 152) = v381;
      *(_DWORD *)(v272 + 160) = v336;
      *(_QWORD *)(v272 + 168) = v316;
      if ( v400 )
        *(_DWORD *)(v272 + 176) = 1;
      v273 = !v293;
      *(_QWORD *)(v272 + 184) = v374;
      *(_QWORD *)(v272 + 192) = v389;
      if ( !v273 )
        *(_DWORD *)(v272 + 200) = 1;
      if ( v294 )
        *(_DWORD *)(v272 + 204) = 1;
      *(_DWORD *)(v272 + 208) = v337;
      *(_QWORD *)(v272 + 216) = v317;
      *(_QWORD *)(v272 + 224) = *(_QWORD *)v390;
      *(_DWORD *)(v272 + 232) = v338;
      *(_QWORD *)(v272 + 240) = v318;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl,
                              v260,
                              v261) )
      {
        v273 = !v295;
        v275 = v300;
        *(_QWORD *)(v300 + 248) = *(_QWORD *)v391;
        *(_QWORD *)(v275 + 256) = *(_QWORD *)v379;
        *(_QWORD *)(v275 + 264) = *(_QWORD *)v380;
        *(_QWORD *)(v275 + 280) = *(_QWORD *)v388;
        *(_QWORD *)(v275 + 288) = *(_QWORD *)v382;
        *(_DWORD *)(v275 + 296) = v305;
        *(_DWORD *)(v275 + 300) = v339;
        *(_QWORD *)(v275 + 304) = v319;
        if ( !v273 )
          *(_DWORD *)(v275 + 312) = 1;
        *(_DWORD *)(v275 + 316) = v340;
        *(_QWORD *)(v275 + 320) = v320;
        *(_DWORD *)(v275 + 328) = v341;
        *(_QWORD *)(v275 + 336) = v321;
        *(_QWORD *)(v275 + 344) = v352;
        *(_DWORD *)(v275 + 352) = v306;
        if ( v342 )
        {
          if ( v342 == 16 )
          {
            *(_OWORD *)(v275 + 356) = *v322;
          }
          else if ( !v286 )
          {
            v286 = 1;
            LODWORD(v289[5]) = 7834;
            v289[6] = 0;
          }
        }
        *(_DWORD *)(v275 + 392) = v343;
        *(_QWORD *)(v275 + 400) = v323;
        *(_QWORD *)(v275 + 376) = *(_QWORD *)v383;
        *(_QWORD *)(v275 + 384) = *(_QWORD *)v384;
        *(_DWORD *)(v275 + 408) = v344;
        *(_QWORD *)(v275 + 416) = v324;
        *(_DWORD *)(v275 + 424) = v345;
        *(_QWORD *)(v275 + 432) = v325;
        *(_DWORD *)(v275 + 444) = v348;
        *(_QWORD *)(v275 + 448) = v385;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginAuthenticatorsImprovements>::GetImpl'::`2'::impl) )
        {
          v276 = v300;
          *(_QWORD *)(v300 + 536) = *(_QWORD *)v386;
          v277 = v296;
          *(_DWORD *)(v276 + 544) = v181;
          *(_QWORD *)(v276 + 552) = v180;
          *(_DWORD *)(v276 + 560) = v277;
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl)
        && v297 )
      {
        *(_DWORD *)(v300 + 440) = 1;
      }
      v278 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::GetImpl'::`2'::impl);
      v279 = v300;
      if ( v278 )
      {
        v280 = *(_QWORD *)v387;
        *(_QWORD *)(v300 + 472) = v55;
        *(_DWORD *)(v279 + 464) = v176;
        *(_QWORD *)(v279 + 512) = v280;
        *(_QWORD *)(v279 + 488) = v328;
        v281 = v326;
        *(_DWORD *)(v279 + 480) = v177;
        *(_QWORD *)(v279 + 504) = v281;
        v282 = v315;
        *(_DWORD *)(v279 + 496) = v178;
        *(_QWORD *)(v279 + 528) = v282;
        *(_DWORD *)(v279 + 520) = v179;
      }
      v13 = v286;
      if ( v298 )
        *(_DWORD *)(v279 + 460) = 1;
    }
    v7 = v304;
    if ( v13 )
      goto LABEL_1284;
    if ( v304 )
      break;
    v8 = uBytes;
    v299 = uBytes;
    if ( !uBytes )
      goto LABEL_1292;
    v283 = (char *)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v283 )
    {
      v13 = 0x80000000;
      goto LABEL_1283;
    }
    v13 = v286;
    v7 = v283;
    v304 = v283;
LABEL_1280:
    if ( ++v347 > 1 )
      goto LABEL_1284;
    v12 = a2;
  }
  if ( uBytes == v289[1] )
  {
    v8 = v299;
    goto LABEL_1280;
  }
LABEL_1292:
  v13 = 1;
LABEL_1283:
  v286 = v13;
  LODWORD(v289[5]) = 7896;
LABEL_1284:
  v8 = v300;
  v6 = a3;
LABEL_1285:
  if ( a4 )
    *a4 = v289[4];
  if ( a5 )
    *a5 = v289[5];
  if ( v13 )
  {
    FidoSecureZeroFree(v7);
    v13 = v286;
    v8 = 0;
  }
  result = v13;
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
