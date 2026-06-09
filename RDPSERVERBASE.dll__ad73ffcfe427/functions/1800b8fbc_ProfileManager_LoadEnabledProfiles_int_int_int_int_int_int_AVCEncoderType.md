# ProfileManager::LoadEnabledProfiles(int,int,int,int,int,int,AVCEncoderType)

- ea: `0x1800b8fbc`
- end: `0x1800bf5a9`
- name: `?LoadEnabledProfiles@ProfileManager@@AEAAJHHHHHHW4AVCEncoderType@@@Z`
- size: `26093`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `38`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b6a34`
- `0x1800c1310`

## callees

- `0x18000116c`
- `0x180001284`
- `0x1800012bc`
- `0x1800012cc`
- `0x1800012dc`
- `0x180001308`
- `0x180001764`
- `0x180003818`
- `0x180003f88`
- `0x180004214`
- `0x18001dcf4`
- `0x18001f838`
- `0x180028a30`
- `0x180050194`
- `0x1800515fc`
- `0x180076090`
- `0x180076f0c`
- `0x180079770`
- `0x180079dac`
- `0x18007a6f0`
- `0x18007e9e0`
- `0x180089e40`
- `0x1800b61bc`
- `0x1800b6710`
- `0x1800b6998`
- `0x1800b75b0`
- `0x1800b77a0`
- `0x1800b7b80`
- `0x1800b8730`
- `0x1800b8fbc`
- `0x1800bf5b0`
- `0x1800bf7a8`
- `0x1800bf904`
- `0x1800bfdac`
- `0x1800c0460`
- `0x1800c0da4`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x1800b9c84`: `ReadRegistryUINT failed!`
- `0x1800bc0f0`: `ReadRegistryBOOL failed!`
- `0x1800b917c`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800b9530`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800b9754`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800b9b1a`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800ba517`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bae3e`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bb75e`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bc2b0`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bcd5a`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bd50c`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800bdcf8`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800be5f1`: `ProfileManagerError_LoadEnabledProfilesCreateProfileFail`
- `0x1800b91c8`: `CreateProfile failed`
- `0x1800b9274`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800b95f4`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800b9842`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800b9cb5`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800ba6a6`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bafd0`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bb8f6`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bc44c`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bcea7`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bd687`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800bde6e`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800be8e6`: `ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail`
- `0x1800b92c0`: `CRDPKeyCollection::CreateInstance failed`
- `0x1800b9e1b`: `Failed to set IntraFrameCacheKey to false`
- `0x1800ba3ad`: `Failed to set EnableEarlyGfxSourceUpdates to true`
- `0x1800bca35`: `Failed to set CodecProcDisableInternalDelta ( !fDeltaEnabled ) in AVC 444 full screen max compression mode`
- `0x1800be782`: `MixedmodeCacheAllowed`
- `0x1800bee9c`: `SetPropertyBool( IntraFrameCacheKey ) failed`

## pseudocode

```c
__int64 __fastcall ProfileManager::LoadEnabledProfiles(
        ProfileManager *a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8)
{
  int GfxPipeSettingBOOL; // r14d
  __int64 v12; // r9
  int v13; // r10d
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // ecx
  signed int v18; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v20; // edx
  const char *v21; // rcx
  signed int Instance; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  signed int v35; // eax
  __int64 v36; // rbx
  __int64 v37; // rax
  signed int v38; // eax
  signed int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rax
  struct IRDPKeyCollection **v42; // rax
  signed int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  signed int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  signed int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rax
  signed int v52; // eax
  __int64 v53; // rax
  __int64 v54; // rax
  signed int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rax
  signed int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rax
  signed int v61; // eax
  __int64 v62; // rax
  __int64 v63; // rax
  signed int v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  signed int v67; // eax
  __int64 v68; // rax
  __int64 v69; // rax
  signed int v70; // eax
  __int64 v71; // rax
  __int64 v72; // rax
  signed int v73; // eax
  __int64 v74; // rax
  __int64 v75; // rax
  signed int v76; // eax
  __int64 v77; // rax
  __int64 v78; // rax
  signed int v79; // eax
  __int64 v80; // rbx
  __int64 v81; // rax
  signed int v82; // eax
  int v83; // ebx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // r8
  signed int v87; // eax
  signed int v88; // eax
  __int64 v89; // rax
  __int64 v90; // rax
  struct IRDPKeyCollection **v91; // rax
  signed int v92; // eax
  __int64 v93; // rax
  __int64 v94; // rax
  signed int v95; // eax
  __int64 v96; // rax
  __int64 v97; // rax
  signed int v98; // eax
  __int64 v99; // rax
  __int64 v100; // rax
  signed int v101; // eax
  __int64 v102; // rax
  __int64 v103; // rax
  signed int v104; // eax
  __int64 v105; // rax
  __int64 v106; // rax
  signed int v107; // eax
  __int64 v108; // rax
  __int64 v109; // rax
  signed int v110; // eax
  __int64 v111; // rax
  __int64 v112; // rax
  signed int v113; // eax
  __int64 v114; // rax
  __int64 v115; // rax
  signed int v116; // eax
  __int64 v117; // rax
  __int64 v118; // rax
  signed int v119; // eax
  __int64 v120; // rax
  __int64 v121; // rax
  signed int v122; // eax
  __int64 v123; // rax
  __int64 v124; // rax
  signed int v125; // eax
  __int64 v126; // rax
  __int64 v127; // rax
  signed int v128; // eax
  __int64 v129; // rbx
  __int64 v130; // rax
  signed int v131; // eax
  signed int v132; // eax
  __int64 v133; // rax
  __int64 v134; // rax
  struct IRDPKeyCollection **v135; // rax
  signed int v136; // eax
  __int64 v137; // rax
  __int64 v138; // rax
  signed int v139; // eax
  __int64 v140; // rax
  __int64 v141; // rax
  signed int v142; // eax
  __int64 v143; // rax
  __int64 v144; // rax
  signed int v145; // eax
  __int64 v146; // rax
  __int64 v147; // rax
  signed int v148; // eax
  __int64 v149; // rax
  __int64 v150; // rax
  signed int v151; // eax
  __int64 v152; // rax
  __int64 v153; // rax
  signed int v154; // eax
  __int64 v155; // rax
  __int64 v156; // rax
  signed int v157; // eax
  __int64 v158; // rax
  __int64 v159; // rax
  signed int v160; // eax
  __int64 v161; // rax
  __int64 v162; // rax
  signed int v163; // eax
  __int64 v164; // rax
  __int64 v165; // rax
  signed int v166; // eax
  __int64 v167; // rax
  __int64 v168; // rax
  signed int v169; // eax
  __int64 v170; // rax
  __int64 v171; // rax
  signed int v172; // eax
  __int64 v173; // rbx
  __int64 v174; // rax
  signed int v175; // eax
  signed int v176; // eax
  int v177; // ebx
  __int64 v178; // rax
  __int64 v179; // rax
  struct IRDPKeyCollection **v180; // rax
  signed int v181; // eax
  __int64 v182; // rax
  __int64 v183; // rax
  signed int v184; // eax
  __int64 v185; // rax
  __int64 v186; // rax
  signed int v187; // eax
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // r8
  __int64 v191; // rax
  signed int v192; // eax
  __int64 v193; // rax
  __int64 v194; // rax
  signed int v195; // eax
  __int64 v196; // rax
  __int64 v197; // rax
  unsigned int v198; // r12d
  signed int v199; // eax
  __int64 v200; // rax
  __int64 v201; // rax
  signed int v202; // eax
  __int64 v203; // rax
  __int64 v204; // rax
  signed int v205; // eax
  __int64 v206; // rax
  __int64 v207; // rax
  signed int v208; // eax
  __int64 v209; // rax
  __int64 v210; // rax
  signed int v211; // eax
  __int64 v212; // rax
  __int64 v213; // rax
  signed int v214; // eax
  __int64 v215; // rax
  __int64 v216; // rax
  signed int v217; // eax
  __int64 v218; // rax
  __int64 v219; // rax
  signed int v220; // eax
  __int64 v221; // rbx
  __int64 v222; // rax
  signed int v223; // eax
  signed int v224; // eax
  __int64 v225; // rax
  __int64 v226; // rax
  signed int v227; // eax
  __int64 v228; // r8
  __int64 v229; // r9
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // r8
  signed int v234; // eax
  signed int v235; // eax
  int v236; // ebx
  __int64 v237; // rax
  __int64 v238; // rax
  struct IRDPKeyCollection **v239; // rax
  signed int v240; // eax
  __int64 v241; // rax
  __int64 v242; // rax
  signed int v243; // eax
  __int64 v244; // rax
  __int64 v245; // rax
  signed int v246; // eax
  __int64 v247; // rax
  __int64 v248; // rax
  __int64 v249; // r8
  __int64 v250; // rax
  signed int v251; // eax
  __int64 v252; // rax
  __int64 v253; // rax
  signed int v254; // eax
  __int64 v255; // rax
  __int64 v256; // rax
  unsigned int v257; // esi
  signed int v258; // eax
  __int64 v259; // rax
  __int64 v260; // rax
  signed int v261; // eax
  __int64 v262; // rax
  __int64 v263; // rax
  signed int v264; // eax
  __int64 v265; // rax
  __int64 v266; // rax
  signed int v267; // eax
  __int64 v268; // rax
  __int64 v269; // rax
  signed int v270; // eax
  __int64 v271; // rax
  __int64 v272; // rax
  signed int v273; // eax
  __int64 v274; // rax
  __int64 v275; // rax
  signed int v276; // eax
  __int64 v277; // rax
  __int64 v278; // rax
  signed int v279; // eax
  __int64 v280; // rbx
  __int64 v281; // rax
  signed int v282; // eax
  signed int v283; // eax
  __int64 v284; // rax
  __int64 v285; // rax
  signed int v286; // eax
  __int64 v287; // r8
  __int64 v288; // r9
  __int64 v289; // rax
  signed int v290; // eax
  __int64 v291; // rax
  __int64 v292; // rax
  struct IRDPKeyCollection **v293; // rax
  signed int v294; // eax
  __int64 v295; // rax
  __int64 v296; // rax
  signed int v297; // eax
  __int64 v298; // rax
  __int64 v299; // rax
  signed int v300; // eax
  __int64 v301; // rax
  __int64 v302; // rax
  signed int v303; // eax
  __int64 v304; // rax
  __int64 v305; // rax
  signed int v306; // eax
  __int64 v307; // rax
  __int64 v308; // rax
  signed int v309; // eax
  __int64 v310; // rax
  __int64 v311; // rax
  signed int v312; // eax
  __int64 v313; // rax
  __int64 v314; // rax
  signed int v315; // eax
  __int64 v316; // rax
  __int64 v317; // rax
  signed int v318; // eax
  __int64 v319; // rax
  __int64 v320; // rax
  signed int v321; // eax
  __int64 v322; // rax
  __int64 v323; // rax
  signed int v324; // eax
  __int64 v325; // rbx
  __int64 v326; // rax
  signed int v327; // eax
  signed int v328; // eax
  int v329; // ebx
  __int64 v330; // rax
  __int64 v331; // rax
  unsigned int v332; // r13d
  bool v333; // zf
  __int64 v334; // rax
  struct IRDPKeyCollection **v335; // rax
  signed int v336; // eax
  __int64 v337; // rax
  __int64 v338; // rax
  signed int v339; // eax
  __int64 v340; // rax
  __int64 v341; // rax
  signed int v342; // eax
  __int64 v343; // rax
  __int64 v344; // rax
  signed int v345; // eax
  __int64 v346; // rax
  __int64 v347; // rax
  signed int v348; // eax
  __int64 v349; // rax
  __int64 v350; // rax
  signed int v351; // eax
  __int64 v352; // rax
  __int64 v353; // rax
  signed int v354; // eax
  __int64 v355; // rax
  __int64 v356; // rax
  signed int v357; // eax
  __int64 v358; // rax
  __int64 v359; // rax
  signed int v360; // eax
  __int64 v361; // rax
  __int64 v362; // rax
  signed int v363; // eax
  __int64 v364; // rax
  __int64 v365; // rax
  signed int v366; // eax
  __int64 v367; // rbx
  __int64 v368; // rax
  signed int v369; // eax
  signed int v370; // eax
  int v371; // ebx
  __int64 v372; // rax
  __int64 v373; // rax
  struct IRDPKeyCollection **v374; // rax
  signed int v375; // eax
  __int64 v376; // rax
  __int64 v377; // rax
  signed int v378; // eax
  __int64 v379; // rax
  __int64 v380; // rax
  signed int v381; // eax
  __int64 v382; // rax
  __int64 v383; // rax
  signed int v384; // eax
  __int64 v385; // rax
  __int64 v386; // rax
  signed int v387; // eax
  __int64 v388; // rax
  __int64 v389; // rax
  signed int v390; // eax
  __int64 v391; // rax
  __int64 v392; // rax
  signed int v393; // eax
  __int64 v394; // rax
  __int64 v395; // rax
  signed int v396; // eax
  __int64 v397; // rax
  __int64 v398; // rax
  signed int v399; // eax
  __int64 v400; // rax
  __int64 v401; // rax
  signed int v402; // eax
  __int64 v403; // rax
  __int64 v404; // rax
  signed int v405; // eax
  __int64 v406; // rax
  __int64 v407; // rax
  signed int v408; // eax
  __int64 v409; // rax
  __int64 v410; // rax
  signed int v411; // eax
  __int64 v412; // rbx
  __int64 v413; // rax
  signed int v414; // eax
  signed int v415; // eax
  __int64 v416; // rax
  int v417; // esi
  BOOL v418; // ebx
  BOOL v419; // ebx
  __int64 v420; // rax
  struct IRDPKeyCollection **v421; // rax
  signed int v422; // eax
  __int64 v423; // rax
  __int64 v424; // rax
  signed int v425; // eax
  __int64 v426; // rax
  __int64 v427; // rax
  signed int v428; // eax
  __int64 v429; // rax
  __int64 v430; // rax
  signed int v431; // eax
  __int64 v432; // rax
  __int64 v433; // rax
  signed int v434; // eax
  __int64 v435; // rax
  __int64 v436; // rax
  signed int v437; // eax
  __int64 v438; // rax
  __int64 v439; // rax
  signed int v440; // eax
  __int64 v441; // rax
  __int64 v442; // rax
  signed int v443; // eax
  __int64 v444; // rax
  __int64 v445; // rax
  signed int v446; // eax
  __int64 v447; // rax
  __int64 v448; // rax
  signed int v449; // eax
  __int64 v450; // rax
  __int64 v451; // rax
  signed int v452; // eax
  __int64 v453; // rax
  __int64 v454; // rax
  signed int v455; // eax
  __int64 v456; // rax
  __int64 v457; // rax
  signed int v458; // eax
  __int64 v459; // rax
  __int64 v460; // rax
  signed int v461; // eax
  __int64 v462; // rax
  __int64 v463; // rax
  signed int v464; // eax
  __int64 v465; // rax
  __int64 v466; // rax
  signed int v467; // eax
  __int64 v468; // rbx
  __int64 v469; // rax
  signed int v470; // eax
  unsigned int v471; // ebx
  void *v472; // rax
  __int64 v473; // r8
  __int64 v474; // r9
  __int64 v475; // rax
  __int64 v476; // rdi
  __int64 v477; // rax
  __int64 v478; // rbx
  __int64 v479; // rax
  __int64 ProfileName; // rax
  __int64 v481; // rbx
  __int64 v482; // rax
  __int64 v483; // rax
  __int64 v484; // rsi
  __int64 v485; // rdi
  __int64 v486; // rax
  __int64 v487; // rbx
  __int64 v488; // rax
  unsigned int v489; // ebx
  struct IRDPPerfCounterGeneric *v490; // rax
  int v492; // [rsp+20h] [rbp-E0h]
  __int64 v493; // [rsp+60h] [rbp-A0h] BYREF
  int v494; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v495; // [rsp+6Ch] [rbp-94h]
  unsigned int v496; // [rsp+70h] [rbp-90h]
  _BYTE v497[8]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v498; // [rsp+80h] [rbp-80h]
  int v499; // [rsp+84h] [rbp-7Ch]
  int v500; // [rsp+88h] [rbp-78h] BYREF
  int v501; // [rsp+8Ch] [rbp-74h] BYREF
  int v502; // [rsp+90h] [rbp-70h] BYREF
  int v503; // [rsp+94h] [rbp-6Ch] BYREF
  int v504; // [rsp+98h] [rbp-68h] BYREF
  int v505; // [rsp+9Ch] [rbp-64h] BYREF
  int v506; // [rsp+A0h] [rbp-60h] BYREF
  int v507; // [rsp+A4h] [rbp-5Ch] BYREF
  int v508; // [rsp+A8h] [rbp-58h] BYREF
  int v509; // [rsp+ACh] [rbp-54h] BYREF
  int v510; // [rsp+B0h] [rbp-50h] BYREF
  int v511; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v512; // [rsp+B8h] [rbp-48h] BYREF
  int v513; // [rsp+BCh] [rbp-44h] BYREF
  int v514; // [rsp+C0h] [rbp-40h] BYREF
  int v515; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v516; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v517[4]; // [rsp+CCh] [rbp-34h] BYREF
  _BYTE v518[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v519[4]; // [rsp+D4h] [rbp-2Ch] BYREF
  int v520; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v521[4]; // [rsp+DCh] [rbp-24h] BYREF
  int v522[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v523; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v524[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v525[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v526[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v527[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v528[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v529[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v530[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v531[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v532[8]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v533[8]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v534[8]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v535[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v536[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v537[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v538; // [rsp+190h] [rbp+90h]
  __int64 v539; // [rsp+198h] [rbp+98h]
  _BYTE v540[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  v493 = 0;
  v499 = 0;
  GfxPipeSettingBOOL = 0;
  v498 = 0;
  v496 = 0;
  v12 = 0;
  v13 = 0;
  if ( *((_DWORD *)a1 + 77) != 1 || (v495 = 0, *((_DWORD *)a1 + 78) != 1) )
    v495 = 1;
  if ( a2 )
  {
    v14 = *((_DWORD *)a1 + 74);
    if ( v14 )
    {
      if ( v14 == 2 || a7 )
        v499 = 3;
    }
  }
  v15 = a6;
  v16 = a5;
  v17 = *((_DWORD *)a1 + 79) - 3;
  if ( v17 )
  {
    if ( v17 == 1 )
    {
      if ( a5 )
      {
        if ( *((_DWORD *)a1 + 75) )
          v12 = 1;
        v498 = v12;
      }
      v13 = v12;
      v496 = v12;
    }
  }
  else if ( a6 )
  {
    if ( *((_DWORD *)a1 + 75) )
      v13 = 1;
    v496 = v13;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v508 = v12;
    v520 = v13;
    v509 = 0;
    v510 = *((_DWORD *)a1 + 79);
    v511 = *((_DWORD *)a1 + 75);
    *(_QWORD *)v522 = "LoadEnabledProfiles - DownSamplingProfileInfo:";
    v516 = a6;
    v512 = a5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&unk_18027ECF0,
      0,
      0,
      (__int64)v522,
      (__int64)&v512,
      (__int64)&v516,
      (__int64)&v511,
      (__int64)&v510,
      (__int64)&v509,
      (__int64)&v508,
      (__int64)&v520);
  }
  CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::RemoveAll((char *)a1 + 96, v16, v15, v12);
  if ( (*((_BYTE *)a1 + 284) & 0x20) != 0 )
  {
    v18 = ProfileManager::CreateProfile(a1, &v493);
    GfxPipeSettingBOOL = v18;
    if ( v18 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
        (char *)0x363,
        v18,
        v492);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 33;
LABEL_28:
        v21 = "CreateProfile failed";
LABEL_29:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          (unsigned int)WPP_8c9510a349ee3b6327c0d183301c85a7_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v21,
          GfxPipeSettingBOOL);
        goto LABEL_928;
      }
      goto LABEL_928;
    }
    *(_DWORD *)(v493 + 16) = 32;
    *(_DWORD *)(v493 + 20) = 1;
    *(_DWORD *)(v493 + 24) = *((_DWORD *)a1 + 59);
    ProfileManager::SetRank(a1, 32, v493);
    *(_DWORD *)(v493 + 32) = 1000;
    *(_DWORD *)(v493 + 36) = 1000;
    *(_DWORD *)(v493 + 44) = 1;
    *(_DWORD *)(v493 + 40) = 2;
    *(_DWORD *)(v493 + 72) = 2;
    Instance = CRDPKeyCollection::CreateInstance((struct IRDPKeyCollection **)(v493 + 80));
    GfxPipeSettingBOOL = Instance;
    if ( Instance < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
        (char *)0x376,
        Instance,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 34;
      goto LABEL_35;
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 72LL))(
            *(_QWORD *)(v493 + 80),
            1,
            5);
    GfxPipeSettingBOOL = v23;
    if ( v23 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x37A,
        v23,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 35;
      goto LABEL_41;
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 72LL))(
            *(_QWORD *)(v493 + 80),
            11,
            2);
    GfxPipeSettingBOOL = v24;
    if ( v24 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x37F,
        v24,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 36;
      goto LABEL_47;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      _tlgCreate1Sz<char>(
        v540,
        "LoadEnabledProfiles: Always set quality to HIGH in RemoteFx Profile (Calista fullscreen).");
      v492 = 3;
      tlgWriteTransfer_EventWriteTransfer(&CallbackContext, &byte_18027ECC7, 0, 0);
    }
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 64LL))(
            *(_QWORD *)(v493 + 80),
            12,
            1);
    GfxPipeSettingBOOL = v25;
    if ( v25 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x385,
        v25,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 37;
      goto LABEL_55;
    }
    v26 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
            (char *)a1 + 96,
            *(unsigned int *)(v493 + 16),
            v493);
    GfxPipeSettingBOOL = v26;
    if ( v26 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesAddFail",
        (char *)0x389,
        v26,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 38;
      goto LABEL_61;
    }
  }
  if ( (*((_BYTE *)a1 + 284) & 0x40) == 0 )
  {
LABEL_83:
    if ( (*((_BYTE *)a1 + 284) & 8) != 0 )
    {
      v31 = ProfileManager::CreateProfile(a1, &v493);
      GfxPipeSettingBOOL = v31;
      if ( v31 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
          (char *)0x3C7,
          v31,
          v492);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 43;
          goto LABEL_28;
        }
        goto LABEL_928;
      }
      *(_DWORD *)(v493 + 16) = 8;
      *(_DWORD *)(v493 + 20) = 1;
      *(_DWORD *)(v493 + 24) = 0;
      ProfileManager::SetRank(a1, 8, v493);
      *(_DWORD *)(v493 + 32) = 1000;
      *(_DWORD *)(v493 + 36) = 700;
      *(_DWORD *)(v493 + 44) = 1;
      *(_DWORD *)(v493 + 48) = 1;
      *(_DWORD *)(v493 + 52) = 1;
      *(_DWORD *)(v493 + 40) = 2;
      *(_DWORD *)(v493 + 60) = 1;
      *(_DWORD *)(v493 + 64) = 2;
      *(_DWORD *)(v493 + 72) = 2;
      v32 = CRDPKeyCollection::CreateInstance((struct IRDPKeyCollection **)(v493 + 80));
      GfxPipeSettingBOOL = v32;
      if ( v32 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
          (char *)0x3DD,
          v32,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 44;
        goto LABEL_35;
      }
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 72LL))(
              *(_QWORD *)(v493 + 80),
              1,
              6);
      GfxPipeSettingBOOL = v33;
      if ( v33 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x3E2,
          v33,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 45;
        goto LABEL_41;
      }
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 72LL))(
              *(_QWORD *)(v493 + 80),
              11,
              1);
      GfxPipeSettingBOOL = v34;
      if ( v34 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x3E7,
          v34,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 46;
        goto LABEL_47;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v513 = 1;
        v538 = &v513;
        v539 = 4;
        _tlgCreate1Sz<char>(v537, "LoadEnabledProfiles: Lossless profile. Set");
        v492 = 4;
        tlgWriteTransfer_EventWriteTransfer(&CallbackContext, byte_18027EC8D, 0, 0);
      }
      v35 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v493 + 80) + 64LL))(*(_QWORD *)(v493 + 80), 20);
      GfxPipeSettingBOOL = v35;
      if ( v35 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x3EE,
          v35,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 47;
        goto LABEL_111;
      }
      v36 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v37 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v38 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
              (char *)a1 + 96,
              *(unsigned int *)(v37 + 16),
              v36);
      GfxPipeSettingBOOL = v38;
      if ( v38 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesAddFail",
          (char *)0x3F2,
          v38,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 48;
        goto LABEL_61;
      }
    }
    if ( (*((_DWORD *)a1 + 71) & 0x400) != 0 )
    {
      v39 = ProfileManager::CreateProfile(a1, &v493);
      GfxPipeSettingBOOL = v39;
      if ( v39 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
          (char *)0x3FC,
          v39,
          v492);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 49;
          goto LABEL_28;
        }
        goto LABEL_928;
      }
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 1024;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = 0;
      v40 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      ProfileManager::SetRank(a1, 1024, v40);
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 1000;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 700;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 0;
      v500 = 1;
      GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"DeltaReducerEnabled", 1, &v500);
      if ( GfxPipeSettingBOOL < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 50;
        goto LABEL_128;
      }
      v41 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v42 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v41 + 80));
      v43 = CRDPKeyCollection::CreateInstance(v42);
      GfxPipeSettingBOOL = v43;
      if ( v43 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
          (char *)0x419,
          v43,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 51;
        goto LABEL_35;
      }
      v44 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v45 = TCntPtr<IRDPKeyCollection>::operator->(v44 + 80);
      v46 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v45 + 64LL))(v45, 4, 1);
      GfxPipeSettingBOOL = v46;
      if ( v46 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x41E,
          v46,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 52;
        goto LABEL_139;
      }
      v47 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v48 = TCntPtr<IRDPKeyCollection>::operator->(v47 + 80);
      v49 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 64LL))(v48, 13);
      GfxPipeSettingBOOL = v49;
      if ( v49 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x424,
          v49,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 53;
        goto LABEL_145;
      }
      v50 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v51 = TCntPtr<IRDPKeyCollection>::operator->(v50 + 80);
      v52 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v51 + 72LL))(v51, 1, 7);
      GfxPipeSettingBOOL = v52;
      if ( v52 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x428,
          v52,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 54;
        goto LABEL_41;
      }
      v53 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v54 = TCntPtr<IRDPKeyCollection>::operator->(v53 + 80);
      v55 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v54 + 72LL))(
              v54,
              11,
              *((unsigned int *)a1 + 79));
      GfxPipeSettingBOOL = v55;
      if ( v55 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x42C,
          v55,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 55;
        goto LABEL_47;
      }
      v56 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v57 = TCntPtr<IRDPKeyCollection>::operator->(v56 + 80);
      v58 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v57 + 64LL))(v57, 21);
      GfxPipeSettingBOOL = v58;
      if ( v58 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x430,
          v58,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 56;
        goto LABEL_55;
      }
      v59 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v60 = TCntPtr<IRDPKeyCollection>::operator->(v59 + 80);
      v61 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v60 + 64LL))(v60, 12, 1);
      GfxPipeSettingBOOL = v61;
      if ( v61 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x434,
          v61,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 57;
        goto LABEL_55;
      }
      v62 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v63 = TCntPtr<IRDPKeyCollection>::operator->(v62 + 80);
      v64 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 64LL))(v63, 14);
      GfxPipeSettingBOOL = v64;
      if ( v64 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x43A,
          v64,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 58;
        goto LABEL_171;
      }
      v65 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v66 = TCntPtr<IRDPKeyCollection>::operator->(v65 + 80);
      v67 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v66 + 72LL))(v66, 16, 16);
      GfxPipeSettingBOOL = v67;
      if ( v67 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x43E,
          v67,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 59;
        goto LABEL_177;
      }
      v68 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v69 = TCntPtr<IRDPKeyCollection>::operator->(v68 + 80);
      v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 64LL))(v69, 15);
      GfxPipeSettingBOOL = v70;
      if ( v70 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x442,
          v70,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 60;
        goto LABEL_183;
      }
      v71 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v72 = TCntPtr<IRDPKeyCollection>::operator->(v71 + 80);
      v73 = (*(__int64 (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v72 + 64LL))(v72, 19, v500 == 0);
      GfxPipeSettingBOOL = v73;
      if ( v73 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x446,
          v73,
          v492);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 61;
          v21 = "Failed to set CodecProcDisableInternalDelta ( !fDeltaEnabled ) in AVC 420 full screen mode";
          goto LABEL_29;
        }
        goto LABEL_928;
      }
      v74 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v75 = TCntPtr<IRDPKeyCollection>::operator->(v74 + 80);
      v76 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v75 + 64LL))(v75, 20, v495);
      GfxPipeSettingBOOL = v76;
      if ( v76 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x44C,
          v76,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 62;
        goto LABEL_194;
      }
      v77 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v78 = TCntPtr<IRDPKeyCollection>::operator->(v77 + 80);
      v79 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v78 + 64LL))(v78, 17, 1);
      GfxPipeSettingBOOL = v79;
      if ( v79 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x451,
          v79,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 63;
        goto LABEL_200;
      }
      v80 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v81 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v82 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
              (char *)a1 + 96,
              *(unsigned int *)(v81 + 16),
              v80);
      v83 = 0;
      GfxPipeSettingBOOL = v82;
      if ( v82 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesAddFail",
          (char *)0x455,
          v82,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 64;
        goto LABEL_61;
      }
      v84 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v85 = TCntPtr<IRDPKeyCollection>::operator->(v84 + 80);
      if ( !*((_DWORD *)a1 + 77) || (v86 = 1, !*((_DWORD *)a1 + 78)) )
        v86 = 0;
      v87 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v85 + 64LL))(v85, 24, v86);
      GfxPipeSettingBOOL = v87;
      if ( v87 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x45A,
          v87,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 65;
        goto LABEL_214;
      }
    }
    else
    {
      v83 = 0;
    }
    if ( a3 && (*((_DWORD *)a1 + 71) & 0x8000) != 0 )
    {
      v88 = ProfileManager::CreateProfile(a1, &v493);
      GfxPipeSettingBOOL = v88;
      if ( v88 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
          (char *)0x464,
          v88,
          v492);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 66;
          goto LABEL_28;
        }
        goto LABEL_928;
      }
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 0x8000;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = 0;
      v89 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      ProfileManager::SetRank(a1, 0x8000, v89);
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 3000;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 2700;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 0;
      v501 = 1;
      GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"DeltaReducerEnabled", 1, &v501);
      if ( GfxPipeSettingBOOL < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 67;
        goto LABEL_128;
      }
      v90 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v91 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v90 + 80));
      v92 = CRDPKeyCollection::CreateInstance(v91);
      GfxPipeSettingBOOL = v92;
      if ( v92 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
          (char *)0x485,
          v92,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 68;
        goto LABEL_35;
      }
      v93 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v94 = TCntPtr<IRDPKeyCollection>::operator->(v93 + 80);
      v95 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v94 + 64LL))(v94, 4, 1);
      GfxPipeSettingBOOL = v95;
      if ( v95 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x489,
          v95,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 69;
        goto LABEL_139;
      }
      v96 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v97 = TCntPtr<IRDPKeyCollection>::operator->(v96 + 80);
      v98 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v97 + 64LL))(v97, 13);
      GfxPipeSettingBOOL = v98;
      if ( v98 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x48D,
          v98,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 70;
        goto LABEL_145;
      }
      v99 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v100 = TCntPtr<IRDPKeyCollection>::operator->(v99 + 80);
      v101 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v100 + 72LL))(v100, 1, 10);
      GfxPipeSettingBOOL = v101;
      if ( v101 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x491,
          v101,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 71;
        goto LABEL_41;
      }
      v102 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v103 = TCntPtr<IRDPKeyCollection>::operator->(v102 + 80);
      v104 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 72LL))(
               v103,
               11,
               *((unsigned int *)a1 + 79));
      GfxPipeSettingBOOL = v104;
      if ( v104 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x495,
          v104,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 72;
        goto LABEL_47;
      }
      v105 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v106 = TCntPtr<IRDPKeyCollection>::operator->(v105 + 80);
      v107 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v106 + 64LL))(v106, 21);
      GfxPipeSettingBOOL = v107;
      if ( v107 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x499,
          v107,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 73;
        goto LABEL_55;
      }
      v108 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v109 = TCntPtr<IRDPKeyCollection>::operator->(v108 + 80);
      v110 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v109 + 64LL))(v109, 12, 1);
      GfxPipeSettingBOOL = v110;
      if ( v110 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x49D,
          v110,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 74;
        goto LABEL_55;
      }
      v111 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v112 = TCntPtr<IRDPKeyCollection>::operator->(v111 + 80);
      v113 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v112 + 64LL))(v112, 14);
      GfxPipeSettingBOOL = v113;
      if ( v113 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4A3,
          v113,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 75;
        goto LABEL_171;
      }
      v114 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v115 = TCntPtr<IRDPKeyCollection>::operator->(v114 + 80);
      v116 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v115 + 72LL))(v115, 16, 16);
      GfxPipeSettingBOOL = v116;
      if ( v116 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4A7,
          v116,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 76;
        goto LABEL_177;
      }
      v117 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v118 = TCntPtr<IRDPKeyCollection>::operator->(v117 + 80);
      v119 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v118 + 64LL))(v118, 15);
      GfxPipeSettingBOOL = v119;
      if ( v119 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4AB,
          v119,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 77;
        goto LABEL_183;
      }
      v120 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v121 = TCntPtr<IRDPKeyCollection>::operator->(v120 + 80);
      v122 = (*(__int64 (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v121 + 64LL))(v121, 19, v501 == 0);
      GfxPipeSettingBOOL = v122;
      if ( v122 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4B0,
          v122,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 78;
        goto LABEL_283;
      }
      v123 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v124 = TCntPtr<IRDPKeyCollection>::operator->(v123 + 80);
      v125 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v124 + 64LL))(v124, 20);
      GfxPipeSettingBOOL = v125;
      if ( v125 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4B5,
          v125,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 79;
        goto LABEL_111;
      }
      v126 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v127 = TCntPtr<IRDPKeyCollection>::operator->(v126 + 80);
      v128 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v127 + 64LL))(v127, 23);
      GfxPipeSettingBOOL = v128;
      if ( v128 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4BA,
          v128,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 80;
        goto LABEL_294;
      }
      v129 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v130 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v131 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
               (char *)a1 + 96,
               *(unsigned int *)(v130 + 16),
               v129);
      v83 = 0;
      GfxPipeSettingBOOL = v131;
      if ( v131 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesAddFail",
          (char *)0x4BE,
          v131,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 81;
        goto LABEL_61;
      }
    }
    if ( a4 && (*((_DWORD *)a1 + 71) & 0x20000) != 0 )
    {
      v132 = ProfileManager::CreateProfile(a1, &v493);
      GfxPipeSettingBOOL = v132;
      if ( v132 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
          (char *)0x4C8,
          v132,
          v492);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 82;
          goto LABEL_28;
        }
        goto LABEL_928;
      }
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 0x20000;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = 0;
      v133 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      ProfileManager::SetRank(a1, 0x20000, v133);
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 3000;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 2700;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 0;
      *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 0;
      v502 = 1;
      GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"DeltaReducerEnabled", 1, &v502);
      if ( GfxPipeSettingBOOL < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 83;
        goto LABEL_128;
      }
      v134 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v135 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v134 + 80));
      v136 = CRDPKeyCollection::CreateInstance(v135);
      GfxPipeSettingBOOL = v136;
      if ( v136 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
          (char *)0x4E9,
          v136,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 84;
        goto LABEL_35;
      }
      v137 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v138 = TCntPtr<IRDPKeyCollection>::operator->(v137 + 80);
      v139 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v138 + 64LL))(v138, 4, 1);
      GfxPipeSettingBOOL = v139;
      if ( v139 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4ED,
          v139,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 85;
        goto LABEL_139;
      }
      v140 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v141 = TCntPtr<IRDPKeyCollection>::operator->(v140 + 80);
      v142 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v141 + 64LL))(v141, 13);
      GfxPipeSettingBOOL = v142;
      if ( v142 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4F1,
          v142,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 86;
        goto LABEL_145;
      }
      v143 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v144 = TCntPtr<IRDPKeyCollection>::operator->(v143 + 80);
      v145 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v144 + 72LL))(v144, 1, 10);
      GfxPipeSettingBOOL = v145;
      if ( v145 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4F5,
          v145,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 87;
        goto LABEL_41;
      }
      v146 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v147 = TCntPtr<IRDPKeyCollection>::operator->(v146 + 80);
      v148 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v147 + 72LL))(
               v147,
               11,
               *((unsigned int *)a1 + 79));
      GfxPipeSettingBOOL = v148;
      if ( v148 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4F9,
          v148,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 88;
        goto LABEL_47;
      }
      v149 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v150 = TCntPtr<IRDPKeyCollection>::operator->(v149 + 80);
      v151 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v150 + 64LL))(v150, 21);
      GfxPipeSettingBOOL = v151;
      if ( v151 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x4FD,
          v151,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 89;
        goto LABEL_55;
      }
      v152 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v153 = TCntPtr<IRDPKeyCollection>::operator->(v152 + 80);
      v154 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v153 + 64LL))(v153, 12, 1);
      GfxPipeSettingBOOL = v154;
      if ( v154 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x501,
          v154,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 90;
        goto LABEL_55;
      }
      v155 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v156 = TCntPtr<IRDPKeyCollection>::operator->(v155 + 80);
      v157 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v156 + 64LL))(v156, 14);
      GfxPipeSettingBOOL = v157;
      if ( v157 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x507,
          v157,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 91;
        goto LABEL_171;
      }
      v158 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v159 = TCntPtr<IRDPKeyCollection>::operator->(v158 + 80);
      v160 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v159 + 72LL))(v159, 16, 16);
      GfxPipeSettingBOOL = v160;
      if ( v160 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x50B,
          v160,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 92;
        goto LABEL_177;
      }
      v161 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v162 = TCntPtr<IRDPKeyCollection>::operator->(v161 + 80);
      v163 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v162 + 64LL))(v162, 15);
      GfxPipeSettingBOOL = v163;
      if ( v163 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x50F,
          v163,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 93;
        goto LABEL_183;
      }
      v164 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v165 = TCntPtr<IRDPKeyCollection>::operator->(v164 + 80);
      v166 = (*(__int64 (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v165 + 64LL))(v165, 19, v502 == 0);
      GfxPipeSettingBOOL = v166;
      if ( v166 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x514,
          v166,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 94;
LABEL_283:
        v21 = "Failed to set CodecProcDisableInternalDelta ( !fDeltaEnabled ) in HEVC full screen mode";
        goto LABEL_29;
      }
      v167 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v168 = TCntPtr<IRDPKeyCollection>::operator->(v167 + 80);
      v169 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v168 + 64LL))(v168, 20);
      GfxPipeSettingBOOL = v169;
      if ( v169 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x519,
          v169,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 95;
        goto LABEL_111;
      }
      v170 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v171 = TCntPtr<IRDPKeyCollection>::operator->(v170 + 80);
      v172 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v171 + 64LL))(
               v171,
               23,
               *((unsigned int *)a1 + 70));
      GfxPipeSettingBOOL = v172;
      if ( v172 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
          (char *)0x51E,
          v172,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 96;
LABEL_294:
        v21 = "Failed to set HEVC444EnabledKey";
        goto LABEL_29;
      }
      v173 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v174 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v175 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
               (char *)a1 + 96,
               *(unsigned int *)(v174 + 16),
               v173);
      v83 = 0;
      GfxPipeSettingBOOL = v175;
      if ( v175 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_LoadEnabledProfilesAddFail",
          (char *)0x522,
          v175,
          v492);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_928;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 97;
        goto LABEL_61;
      }
    }
    if ( (*((_DWORD *)a1 + 71) & 0x800) == 0 )
    {
      v198 = v498;
      goto LABEL_492;
    }
    v176 = ProfileManager::CreateProfile(a1, &v493);
    GfxPipeSettingBOOL = v176;
    if ( v176 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
        (char *)0x52C,
        v176,
        v492);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 98;
        goto LABEL_28;
      }
      goto LABEL_928;
    }
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 2048;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
    v177 = *((_DWORD *)a1 + 72);
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = v177;
    v178 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
    ProfileManager::SetRank(a1, 2048, v178);
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 3000;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 2700;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 0;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 0;
    *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 0;
    v503 = 1;
    GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"DeltaReducerEnabled", 1, &v503);
    if ( GfxPipeSettingBOOL < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 99;
      goto LABEL_128;
    }
    v179 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
    v180 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v179 + 80));
    v181 = CRDPKeyCollection::CreateInstance(v180);
    GfxPipeSettingBOOL = v181;
    if ( v181 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
        (char *)0x549,
        v181,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 100;
      goto LABEL_35;
    }
    v182 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
    v183 = TCntPtr<IRDPKeyCollection>::operator->(v182 + 80);
    v184 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v183 + 64LL))(v183, 4, 1);
    GfxPipeSettingBOOL = v184;
    if ( v184 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x54E,
        v184,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 101;
      goto LABEL_139;
    }
    v185 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
    v186 = TCntPtr<IRDPKeyCollection>::operator->(v185 + 80);
    v187 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v186 + 64LL))(v186, 13);
    GfxPipeSettingBOOL = v187;
    if ( v187 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x554,
        v187,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 102;
      goto LABEL_145;
    }
    if ( a8 == 1 )
    {
      v188 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v189 = TCntPtr<IRDPKeyCollection>::operator->(v188 + 80);
      v190 = 8;
    }
    else
    {
      if ( a8 != 2 )
      {
LABEL_417:
        v193 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v194 = TCntPtr<IRDPKeyCollection>::operator->(v193 + 80);
        v195 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v194 + 72LL))(
                 v194,
                 11,
                 *((unsigned int *)a1 + 79));
        GfxPipeSettingBOOL = v195;
        if ( v195 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x568,
            v195,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 105;
          goto LABEL_47;
        }
        v196 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v197 = TCntPtr<IRDPKeyCollection>::operator->(v196 + 80);
        v198 = v498;
        v199 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v197 + 64LL))(v197, 21, v498);
        GfxPipeSettingBOOL = v199;
        if ( v199 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x56C,
            v199,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 106;
          goto LABEL_55;
        }
        v200 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v201 = TCntPtr<IRDPKeyCollection>::operator->(v200 + 80);
        v202 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v201 + 64LL))(v201, 12, 1);
        GfxPipeSettingBOOL = v202;
        if ( v202 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x570,
            v202,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 107;
          goto LABEL_55;
        }
        v203 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v204 = TCntPtr<IRDPKeyCollection>::operator->(v203 + 80);
        v205 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v204 + 64LL))(v204, 14);
        GfxPipeSettingBOOL = v205;
        if ( v205 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x576,
            v205,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 108;
          goto LABEL_171;
        }
        v206 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v207 = TCntPtr<IRDPKeyCollection>::operator->(v206 + 80);
        v208 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v207 + 72LL))(v207, 16, 16);
        GfxPipeSettingBOOL = v208;
        if ( v208 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x57A,
            v208,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 109;
          goto LABEL_177;
        }
        v209 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v210 = TCntPtr<IRDPKeyCollection>::operator->(v209 + 80);
        v211 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v210 + 64LL))(v210, 15);
        GfxPipeSettingBOOL = v211;
        if ( v211 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x57E,
            v211,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 110;
          goto LABEL_183;
        }
        v212 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v213 = TCntPtr<IRDPKeyCollection>::operator->(v212 + 80);
        v214 = (*(__int64 (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v213 + 64LL))(v213, 19, v503 == 0);
        GfxPipeSettingBOOL = v214;
        if ( v214 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x583,
            v214,
            v492);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 111;
            v21 = "Failed to set CodecProcDisableInternalDelta ( !fDeltaEnabled ) in AVC 444 full screen mode";
            goto LABEL_29;
          }
          goto LABEL_928;
        }
        v215 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v216 = TCntPtr<IRDPKeyCollection>::operator->(v215 + 80);
        v217 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v216 + 64LL))(v216, 17, 1);
        GfxPipeSettingBOOL = v217;
        if ( v217 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x588,
            v217,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 112;
          goto LABEL_200;
        }
        v218 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v219 = TCntPtr<IRDPKeyCollection>::operator->(v218 + 80);
        v220 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v219 + 64LL))(v219, 20, v495);
        GfxPipeSettingBOOL = v220;
        if ( v220 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x58E,
            v220,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 113;
          goto LABEL_194;
        }
        v221 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v222 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v223 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                 (char *)a1 + 96,
                 *(unsigned int *)(v222 + 16),
                 v221);
        v83 = 0;
        GfxPipeSettingBOOL = v223;
        if ( v223 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesAddFail",
            (char *)0x592,
            v223,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 114;
          goto LABEL_61;
        }
        v504 = 0;
        v224 = GetGfxPipeSettingBOOL(L"AvcCabacEnabled", 0, &v504);
        GfxPipeSettingBOOL = v224;
        if ( v224 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_InitializeGetGfxPipeSettingFail",
            (char *)0x59C,
            v224,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 115;
          goto LABEL_472;
        }
        if ( v504 )
        {
          v225 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
          v226 = TCntPtr<IRDPKeyCollection>::operator->(v225 + 80);
          v227 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v226 + 64LL))(v226, 18, 1);
          GfxPipeSettingBOOL = v227;
          if ( v227 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
              "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
              (char *)0x5A4,
              v227,
              v492);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_928;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 116;
            goto LABEL_479;
          }
          if ( (unsigned int)CallbackContext > 5 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0, v228, v229) )
          {
            v230 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                     v526,
                     "LoadEnabledProfiles: AVC CABAC is enabled");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (unsigned int)&dword_18027EC64,
              0,
              0,
              v230);
          }
        }
        v231 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v232 = TCntPtr<IRDPKeyCollection>::operator->(v231 + 80);
        if ( !*((_DWORD *)a1 + 77) || (v233 = 1, !*((_DWORD *)a1 + 78)) )
          v233 = 0;
        v234 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v232 + 64LL))(v232, 24, v233);
        GfxPipeSettingBOOL = v234;
        if ( v234 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x5AC,
            v234,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 117;
LABEL_214:
          v21 = "Failed to set ScrollingDetectionEnabledKey";
          goto LABEL_29;
        }
LABEL_492:
        if ( (*((_DWORD *)a1 + 71) & 0x200) == 0 )
        {
          v257 = v496;
          goto LABEL_592;
        }
        v235 = ProfileManager::CreateProfile(a1, &v493);
        GfxPipeSettingBOOL = v235;
        if ( v235 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
            (char *)0x5B6,
            v235,
            v492);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 118;
            goto LABEL_28;
          }
          goto LABEL_928;
        }
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 512;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
        v236 = *((_DWORD *)a1 + 72);
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = v236;
        v237 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        ProfileManager::SetRank(a1, 512, v237);
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 2600;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 3500;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 0;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 0;
        *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 0;
        v505 = 1;
        GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"DeltaReducerEnabled", 1, &v505);
        if ( GfxPipeSettingBOOL < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 119;
          goto LABEL_128;
        }
        v238 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v239 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v238 + 80));
        v240 = CRDPKeyCollection::CreateInstance(v239);
        GfxPipeSettingBOOL = v240;
        if ( v240 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
            (char *)0x5D3,
            v240,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 120;
          goto LABEL_35;
        }
        v241 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v242 = TCntPtr<IRDPKeyCollection>::operator->(v241 + 80);
        v243 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v242 + 64LL))(v242, 4, 1);
        GfxPipeSettingBOOL = v243;
        if ( v243 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x5D8,
            v243,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 121;
LABEL_139:
          v21 = "Failed to set SpoilPrimitivesKey to true";
          goto LABEL_29;
        }
        v244 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
        v245 = TCntPtr<IRDPKeyCollection>::operator->(v244 + 80);
        v246 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v245 + 64LL))(v245, 13);
        GfxPipeSettingBOOL = v246;
        if ( v246 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x5DE,
            v246,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 122;
          goto LABEL_145;
        }
        if ( a8 == 1 )
        {
          v247 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
          v248 = TCntPtr<IRDPKeyCollection>::operator->(v247 + 80);
          v249 = 8;
        }
        else
        {
          if ( a8 != 2 )
          {
LABEL_527:
            v252 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v253 = TCntPtr<IRDPKeyCollection>::operator->(v252 + 80);
            v254 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v253 + 72LL))(
                     v253,
                     11,
                     *((unsigned int *)a1 + 79));
            GfxPipeSettingBOOL = v254;
            if ( v254 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x5F2,
                v254,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 125;
              goto LABEL_47;
            }
            v255 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v256 = TCntPtr<IRDPKeyCollection>::operator->(v255 + 80);
            v257 = v496;
            v258 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v256 + 64LL))(v256, 21, v496);
            GfxPipeSettingBOOL = v258;
            if ( v258 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x5F6,
                v258,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 126;
              goto LABEL_55;
            }
            v259 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v260 = TCntPtr<IRDPKeyCollection>::operator->(v259 + 80);
            v261 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v260 + 64LL))(v260, 12, 1);
            GfxPipeSettingBOOL = v261;
            if ( v261 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x5FA,
                v261,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 127;
              goto LABEL_55;
            }
            v262 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v263 = TCntPtr<IRDPKeyCollection>::operator->(v262 + 80);
            v264 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v263 + 64LL))(v263, 14);
            GfxPipeSettingBOOL = v264;
            if ( v264 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x600,
                v264,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 128;
              goto LABEL_171;
            }
            v265 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v266 = TCntPtr<IRDPKeyCollection>::operator->(v265 + 80);
            v267 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v266 + 72LL))(v266, 16, 16);
            GfxPipeSettingBOOL = v267;
            if ( v267 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x604,
                v267,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 129;
              goto LABEL_177;
            }
            v268 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v269 = TCntPtr<IRDPKeyCollection>::operator->(v268 + 80);
            v270 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v269 + 64LL))(v269, 15);
            GfxPipeSettingBOOL = v270;
            if ( v270 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x608,
                v270,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 130;
              goto LABEL_183;
            }
            v271 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v272 = TCntPtr<IRDPKeyCollection>::operator->(v271 + 80);
            v273 = (*(__int64 (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)v272 + 64LL))(v272, 19, v505 == 0);
            GfxPipeSettingBOOL = v273;
            if ( v273 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x60D,
                v273,
                v492);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 131;
                v21 = "Failed to set CodecProcDisableInternalDelta ( !fDeltaEnabled ) in AVC 444 full screen max compression mode";
                goto LABEL_29;
              }
              goto LABEL_928;
            }
            v274 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v275 = TCntPtr<IRDPKeyCollection>::operator->(v274 + 80);
            v276 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v275 + 64LL))(v275, 17, 1);
            GfxPipeSettingBOOL = v276;
            if ( v276 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x612,
                v276,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 132;
LABEL_200:
              v21 = "Failed to set EnableEarlyGfxSourceUpdates to true";
              goto LABEL_29;
            }
            v277 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v278 = TCntPtr<IRDPKeyCollection>::operator->(v277 + 80);
            v279 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v278 + 64LL))(v278, 20, v495);
            GfxPipeSettingBOOL = v279;
            if ( v279 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                (char *)0x618,
                v279,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 133;
LABEL_194:
              v21 = "Failed to set MotionProcEnableExternalMotion";
              goto LABEL_29;
            }
            v280 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v281 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
            v282 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                     (char *)a1 + 96,
                     *(unsigned int *)(v281 + 16),
                     v280);
            v83 = 0;
            GfxPipeSettingBOOL = v282;
            if ( v282 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_LoadEnabledProfilesAddFail",
                (char *)0x61C,
                v282,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 134;
              goto LABEL_61;
            }
            v506 = 0;
            v283 = GetGfxPipeSettingBOOL(L"AvcCabacEnabled", 0, &v506);
            GfxPipeSettingBOOL = v283;
            if ( v283 < 0 )
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                "ProfileManagerError_InitializeGetGfxPipeSettingFail",
                (char *)0x626,
                v283,
                v492);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_928;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 135;
LABEL_472:
              v21 = "ReadRegistryBOOL failed!";
              goto LABEL_29;
            }
            if ( v506 )
            {
              v284 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v285 = TCntPtr<IRDPKeyCollection>::operator->(v284 + 80);
              v286 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v285 + 64LL))(v285, 18, 1);
              GfxPipeSettingBOOL = v286;
              if ( v286 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x62E,
                  v286,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 136;
LABEL_479:
                v21 = "Failed to set CabacEntropyCodingKey to TRUE";
                goto LABEL_29;
              }
              if ( (unsigned int)CallbackContext > 5 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0, v287, v288) )
              {
                v289 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                         v527,
                         "LoadEnabledProfiles: AVC CABAC is enabled");
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&CallbackContext,
                  (unsigned int)byte_18027EC3B,
                  0,
                  0,
                  v289);
              }
            }
LABEL_592:
            if ( (*((_DWORD *)a1 + 71) & 0x1000) != 0 )
            {
              v290 = ProfileManager::CreateProfile(a1, &v493);
              GfxPipeSettingBOOL = v290;
              if ( v290 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
                  (char *)0x63B,
                  v290,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 137;
                  goto LABEL_28;
                }
                goto LABEL_928;
              }
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 4096;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = 0;
              v291 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              ProfileManager::SetRank(a1, 4096, v291);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 3000;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 2700;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 64) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 1;
              v292 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v293 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v292 + 80));
              v294 = CRDPKeyCollection::CreateInstance(v293);
              GfxPipeSettingBOOL = v294;
              if ( v294 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
                  (char *)0x651,
                  v294,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 138;
                goto LABEL_35;
              }
              v295 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v296 = TCntPtr<IRDPKeyCollection>::operator->(v295 + 80);
              v297 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v296 + 64LL))(v296, 13);
              GfxPipeSettingBOOL = v297;
              if ( v297 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x656,
                  v297,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 139;
LABEL_145:
                v21 = "Failed to set IntraFrameCacheKey to false";
                goto LABEL_29;
              }
              v298 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v299 = TCntPtr<IRDPKeyCollection>::operator->(v298 + 80);
              v300 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v299 + 64LL))(v299, 14);
              GfxPipeSettingBOOL = v300;
              if ( v300 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x65C,
                  v300,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 140;
                goto LABEL_171;
              }
              v301 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v302 = TCntPtr<IRDPKeyCollection>::operator->(v301 + 80);
              v303 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v302 + 72LL))(v302, 16, 16);
              GfxPipeSettingBOOL = v303;
              if ( v303 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x660,
                  v303,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 141;
                goto LABEL_177;
              }
              v304 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v305 = TCntPtr<IRDPKeyCollection>::operator->(v304 + 80);
              v306 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v305 + 64LL))(v305, 15, 1);
              GfxPipeSettingBOOL = v306;
              if ( v306 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x664,
                  v306,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 142;
LABEL_183:
                v21 = "Failed to set DeltaReduceSADToleranceKey to false";
                goto LABEL_29;
              }
              v307 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v308 = TCntPtr<IRDPKeyCollection>::operator->(v307 + 80);
              v309 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v308 + 72LL))(v308, 1, 8);
              GfxPipeSettingBOOL = v309;
              if ( v309 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x668,
                  v309,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 143;
                goto LABEL_41;
              }
              v310 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v311 = TCntPtr<IRDPKeyCollection>::operator->(v310 + 80);
              v312 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v311 + 72LL))(
                       v311,
                       11,
                       *((unsigned int *)a1 + 79));
              GfxPipeSettingBOOL = v312;
              if ( v312 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x66C,
                  v312,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 144;
                goto LABEL_47;
              }
              v313 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v314 = TCntPtr<IRDPKeyCollection>::operator->(v313 + 80);
              v315 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v314 + 64LL))(v314, 21, v198);
              GfxPipeSettingBOOL = v315;
              if ( v315 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x670,
                  v315,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 145;
                goto LABEL_55;
              }
              v316 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v317 = TCntPtr<IRDPKeyCollection>::operator->(v316 + 80);
              v318 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v317 + 72LL))(v317, 0, 0);
              GfxPipeSettingBOOL = v318;
              if ( v318 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x674,
                  v318,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 146;
                goto LABEL_41;
              }
              v319 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v320 = TCntPtr<IRDPKeyCollection>::operator->(v319 + 80);
              v321 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v320 + 64LL))(v320, 19);
              GfxPipeSettingBOOL = v321;
              if ( v321 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x678,
                  v321,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 147;
                  v21 = "Failed to set CodecProcDisableInternalDelta to false";
                  goto LABEL_29;
                }
                goto LABEL_928;
              }
              v322 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v323 = TCntPtr<IRDPKeyCollection>::operator->(v322 + 80);
              v324 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v323 + 64LL))(v323, 20);
              GfxPipeSettingBOOL = v324;
              if ( v324 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x67D,
                  v324,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 148;
                goto LABEL_111;
              }
              v325 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v326 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v327 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                       (char *)a1 + 96,
                       *(unsigned int *)(v326 + 16),
                       v325);
              v83 = 0;
              GfxPipeSettingBOOL = v327;
              if ( v327 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesAddFail",
                  (char *)0x681,
                  v327,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 149;
                goto LABEL_61;
              }
            }
            if ( (*((_BYTE *)a1 + 284) & 2) != 0 )
            {
              v328 = ProfileManager::CreateProfile(a1, &v493);
              GfxPipeSettingBOOL = v328;
              if ( v328 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
                  (char *)0x68B,
                  v328,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 150;
                  goto LABEL_28;
                }
                goto LABEL_928;
              }
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
              v329 = *((_DWORD *)a1 + 72);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = v329;
              v330 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              ProfileManager::SetRank(a1, 2, v330);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 600;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 1500;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
              v331 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v332 = v499;
              v333 = v499 == 3;
              *(_DWORD *)(v331 + 40) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 56) = !v333;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 64) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 68) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
              v334 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v335 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v334 + 80));
              v336 = CRDPKeyCollection::CreateInstance(v335);
              GfxPipeSettingBOOL = v336;
              if ( v336 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
                  (char *)0x6A3,
                  v336,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 151;
                goto LABEL_35;
              }
              v337 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v338 = TCntPtr<IRDPKeyCollection>::operator->(v337 + 80);
              v339 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v338 + 72LL))(v338, 0, 1);
              GfxPipeSettingBOOL = v339;
              if ( v339 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6A7,
                  v339,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 152;
                goto LABEL_41;
              }
              v340 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v341 = TCntPtr<IRDPKeyCollection>::operator->(v340 + 80);
              v342 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v341 + 72LL))(v341, 1, 1);
              GfxPipeSettingBOOL = v342;
              if ( v342 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6AB,
                  v342,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 153;
                goto LABEL_41;
              }
              v343 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v344 = TCntPtr<IRDPKeyCollection>::operator->(v343 + 80);
              v345 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v344 + 72LL))(v344, 2, 4);
              GfxPipeSettingBOOL = v345;
              if ( v345 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6AF,
                  v345,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 154;
                goto LABEL_41;
              }
              v346 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v347 = TCntPtr<IRDPKeyCollection>::operator->(v346 + 80);
              v348 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v347 + 72LL))(v347, 3, 5);
              GfxPipeSettingBOOL = v348;
              if ( v348 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6B3,
                  v348,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 155;
                goto LABEL_41;
              }
              v349 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v350 = TCntPtr<IRDPKeyCollection>::operator->(v349 + 80);
              v351 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v350 + 72LL))(v350, 6, 50);
              GfxPipeSettingBOOL = v351;
              if ( v351 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6B7,
                  v351,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 156;
                goto LABEL_41;
              }
              v352 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v353 = TCntPtr<IRDPKeyCollection>::operator->(v352 + 80);
              v354 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v353 + 72LL))(v353, 7, 25);
              GfxPipeSettingBOOL = v354;
              if ( v354 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6BB,
                  v354,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 157;
                goto LABEL_41;
              }
              v355 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v356 = TCntPtr<IRDPKeyCollection>::operator->(v355 + 80);
              v357 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v356 + 72LL))(v356, 5, v332);
              GfxPipeSettingBOOL = v357;
              if ( v357 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6BF,
                  v357,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 158;
                goto LABEL_704;
              }
              v358 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v359 = TCntPtr<IRDPKeyCollection>::operator->(v358 + 80);
              v360 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v359 + 72LL))(
                       v359,
                       11,
                       *((unsigned int *)a1 + 79));
              GfxPipeSettingBOOL = v360;
              if ( v360 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6C3,
                  v360,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 159;
                goto LABEL_47;
              }
              v361 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v362 = TCntPtr<IRDPKeyCollection>::operator->(v361 + 80);
              v363 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v362 + 64LL))(v362, 21, v198);
              GfxPipeSettingBOOL = v363;
              if ( v363 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6C7,
                  v363,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 160;
                goto LABEL_55;
              }
              v364 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v365 = TCntPtr<IRDPKeyCollection>::operator->(v364 + 80);
              v366 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v365 + 64LL))(v365, 20);
              GfxPipeSettingBOOL = v366;
              if ( v366 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6CC,
                  v366,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 161;
                goto LABEL_111;
              }
              v367 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v368 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v369 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                       (char *)a1 + 96,
                       *(unsigned int *)(v368 + 16),
                       v367);
              v83 = 0;
              GfxPipeSettingBOOL = v369;
              if ( v369 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesAddFail",
                  (char *)0x6D0,
                  v369,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 162;
                goto LABEL_61;
              }
            }
            else
            {
              v332 = v499;
            }
            if ( (*((_BYTE *)a1 + 284) & 4) != 0 )
            {
              v370 = ProfileManager::CreateProfile(a1, &v493);
              GfxPipeSettingBOOL = v370;
              if ( v370 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
                  (char *)0x6DA,
                  v370,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 163;
                  goto LABEL_28;
                }
                goto LABEL_928;
              }
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 4;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
              v371 = *((_DWORD *)a1 + 72);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = v371;
              v372 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              ProfileManager::SetRank(a1, 4, v372);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 400;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 2000;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 56) = v332 != 3;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 64) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 68) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
              v373 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v374 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v373 + 80));
              v375 = CRDPKeyCollection::CreateInstance(v374);
              GfxPipeSettingBOOL = v375;
              if ( v375 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
                  (char *)0x6F2,
                  v375,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 164;
                goto LABEL_35;
              }
              v376 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v377 = TCntPtr<IRDPKeyCollection>::operator->(v376 + 80);
              v378 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v377 + 72LL))(v377, 0, 2);
              GfxPipeSettingBOOL = v378;
              if ( v378 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6F6,
                  v378,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 165;
                goto LABEL_41;
              }
              v379 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v380 = TCntPtr<IRDPKeyCollection>::operator->(v379 + 80);
              v381 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v380 + 72LL))(v380, 1, 1);
              GfxPipeSettingBOOL = v381;
              if ( v381 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6FA,
                  v381,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 166;
                goto LABEL_41;
              }
              v382 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v383 = TCntPtr<IRDPKeyCollection>::operator->(v382 + 80);
              v384 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v383 + 72LL))(v383, 2, 4);
              GfxPipeSettingBOOL = v384;
              if ( v384 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x6FE,
                  v384,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 167;
                goto LABEL_41;
              }
              v385 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v386 = TCntPtr<IRDPKeyCollection>::operator->(v385 + 80);
              v387 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v386 + 72LL))(v386, 3, 5);
              GfxPipeSettingBOOL = v387;
              if ( v387 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x702,
                  v387,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 168;
                goto LABEL_41;
              }
              v388 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v389 = TCntPtr<IRDPKeyCollection>::operator->(v388 + 80);
              v390 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v389 + 72LL))(v389, 6, 25);
              GfxPipeSettingBOOL = v390;
              if ( v390 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x706,
                  v390,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 169;
                goto LABEL_41;
              }
              v391 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v392 = TCntPtr<IRDPKeyCollection>::operator->(v391 + 80);
              v393 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v392 + 72LL))(v392, 7, 25);
              GfxPipeSettingBOOL = v393;
              if ( v393 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x70A,
                  v393,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 170;
                goto LABEL_41;
              }
              v394 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v395 = TCntPtr<IRDPKeyCollection>::operator->(v394 + 80);
              v396 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v395 + 72LL))(v395, 5, v332);
              GfxPipeSettingBOOL = v396;
              if ( v396 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x70E,
                  v396,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 171;
                goto LABEL_704;
              }
              v397 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v398 = TCntPtr<IRDPKeyCollection>::operator->(v397 + 80);
              v399 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v398 + 72LL))(
                       v398,
                       11,
                       *((unsigned int *)a1 + 79));
              GfxPipeSettingBOOL = v399;
              if ( v399 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x712,
                  v399,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 172;
                goto LABEL_47;
              }
              v400 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v401 = TCntPtr<IRDPKeyCollection>::operator->(v400 + 80);
              v402 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v401 + 64LL))(v401, 21, v257);
              GfxPipeSettingBOOL = v402;
              if ( v402 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x716,
                  v402,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 173;
                goto LABEL_55;
              }
              v403 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v404 = TCntPtr<IRDPKeyCollection>::operator->(v403 + 80);
              v405 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v404 + 64LL))(v404, 10, 1);
              GfxPipeSettingBOOL = v405;
              if ( v405 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x71A,
                  v405,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 174;
                goto LABEL_55;
              }
              v406 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v407 = TCntPtr<IRDPKeyCollection>::operator->(v406 + 80);
              v408 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v407 + 64LL))(v407, 9, 1);
              GfxPipeSettingBOOL = v408;
              if ( v408 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x71E,
                  v408,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 175;
                goto LABEL_55;
              }
              v409 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v410 = TCntPtr<IRDPKeyCollection>::operator->(v409 + 80);
              v411 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v410 + 64LL))(v410, 20);
              GfxPipeSettingBOOL = v411;
              if ( v411 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x723,
                  v411,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 176;
                goto LABEL_111;
              }
              v412 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v413 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v414 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                       (char *)a1 + 96,
                       *(unsigned int *)(v413 + 16),
                       v412);
              v83 = 0;
              GfxPipeSettingBOOL = v414;
              if ( v414 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesAddFail",
                  (char *)0x727,
                  v414,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 177;
                goto LABEL_61;
              }
            }
            if ( (*((_DWORD *)a1 + 71) & 0x2000) != 0 )
            {
              v415 = ProfileManager::CreateProfile(a1, &v493);
              GfxPipeSettingBOOL = v415;
              if ( v415 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
                  (char *)0x730,
                  v415,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 178;
                  goto LABEL_28;
                }
                goto LABEL_928;
              }
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 16) = 0x2000;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 20) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 24) = 0;
              v416 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              ProfileManager::SetRank(a1, 0x2000, v416);
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 32) = 600;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 36) = 1500;
              v507 = 0;
              GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"MixedmodeUseAvc444", 0, &v507);
              if ( GfxPipeSettingBOOL < 0 )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 179;
                goto LABEL_128;
              }
              v494 = 0;
              v417 = v507 != 0 ? 2 : 0;
              GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"MixedmodeMotionDetectionAllowed", 1, &v494);
              if ( GfxPipeSettingBOOL < 0 )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 180;
                goto LABEL_128;
              }
              LOBYTE(v83) = v494 != 0;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 60) = v83;
              GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"MixedmodeCacheAllowed", 1, &v494);
              if ( GfxPipeSettingBOOL < 0 )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 181;
                goto LABEL_128;
              }
              v418 = v494 != 0;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 64) = v418;
              GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"MixedmodeVideoDetectorAllowed", 1, &v494);
              if ( GfxPipeSettingBOOL < 0 )
              {
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 182;
LABEL_128:
                v21 = "ReadRegistryUINT failed!";
                goto LABEL_29;
              }
              v419 = v494 != 0;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 52) = v419;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 44) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 40) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 56) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 48) = 1;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 68) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 72) = 2;
              *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(&v493) + 56) = 0;
              v420 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v421 = (struct IRDPKeyCollection **)KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>((void *)(v420 + 80));
              v422 = CRDPKeyCollection::CreateInstance(v421);
              GfxPipeSettingBOOL = v422;
              if ( v422 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
                  (char *)0x76F,
                  v422,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 183;
LABEL_35:
                v21 = "CRDPKeyCollection::CreateInstance failed";
                goto LABEL_29;
              }
              v423 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v424 = TCntPtr<IRDPKeyCollection>::operator->(v423 + 80);
              v425 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v424 + 72LL))(v424, 0, 1);
              GfxPipeSettingBOOL = v425;
              if ( v425 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x773,
                  v425,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 184;
                goto LABEL_41;
              }
              v426 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v427 = TCntPtr<IRDPKeyCollection>::operator->(v426 + 80);
              v428 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v427 + 72LL))(v427, 1, 1);
              GfxPipeSettingBOOL = v428;
              if ( v428 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x777,
                  v428,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 185;
                goto LABEL_41;
              }
              v429 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v430 = TCntPtr<IRDPKeyCollection>::operator->(v429 + 80);
              v431 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v430 + 72LL))(v430, 2, 4);
              GfxPipeSettingBOOL = v431;
              if ( v431 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x77B,
                  v431,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 186;
                goto LABEL_41;
              }
              v432 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v433 = TCntPtr<IRDPKeyCollection>::operator->(v432 + 80);
              v434 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v433 + 72LL))(
                       v433,
                       3,
                       (unsigned int)(v417 + 7));
              GfxPipeSettingBOOL = v434;
              if ( v434 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x77F,
                  v434,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 187;
                goto LABEL_41;
              }
              v435 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v436 = TCntPtr<IRDPKeyCollection>::operator->(v435 + 80);
              v437 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v436 + 72LL))(v436, 6, 50);
              GfxPipeSettingBOOL = v437;
              if ( v437 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x783,
                  v437,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 188;
                goto LABEL_41;
              }
              v438 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v439 = TCntPtr<IRDPKeyCollection>::operator->(v438 + 80);
              v440 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v439 + 72LL))(v439, 7, 25);
              GfxPipeSettingBOOL = v440;
              if ( v440 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x787,
                  v440,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 189;
LABEL_41:
                v21 = "SetPropertyUnsignedLong failed";
                goto LABEL_29;
              }
              v441 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v442 = TCntPtr<IRDPKeyCollection>::operator->(v441 + 80);
              v443 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v442 + 72LL))(v442, 5);
              GfxPipeSettingBOOL = v443;
              if ( v443 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x78B,
                  v443,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 190;
LABEL_704:
                v21 = "SetPropertyUnsignedLong( VOBRCodec ) failed";
                goto LABEL_29;
              }
              v444 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v445 = TCntPtr<IRDPKeyCollection>::operator->(v444 + 80);
              v446 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v445 + 72LL))(
                       v445,
                       11,
                       *((unsigned int *)a1 + 79));
              GfxPipeSettingBOOL = v446;
              if ( v446 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x78F,
                  v446,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 191;
LABEL_47:
                v21 = "SetPropertyUnsignedLong( ImageQualityKey ) failed";
                goto LABEL_29;
              }
              v447 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v448 = TCntPtr<IRDPKeyCollection>::operator->(v447 + 80);
              v449 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v448 + 64LL))(v448, 21, v198);
              GfxPipeSettingBOOL = v449;
              if ( v449 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x793,
                  v449,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 192;
LABEL_55:
                v21 = "SetPropertyBool failed";
                goto LABEL_29;
              }
              v450 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v451 = TCntPtr<IRDPKeyCollection>::operator->(v450 + 80);
              v452 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v451 + 64LL))(v451, 13);
              GfxPipeSettingBOOL = v452;
              if ( v452 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x798,
                  v452,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 193;
                  v21 = "SetPropertyBool( IntraFrameCacheKey ) failed";
                  goto LABEL_29;
                }
                goto LABEL_928;
              }
              v453 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v454 = TCntPtr<IRDPKeyCollection>::operator->(v453 + 80);
              v455 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v454 + 64LL))(v454, 14);
              GfxPipeSettingBOOL = v455;
              if ( v455 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x79E,
                  v455,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 194;
LABEL_171:
                v21 = "Failed to set DeltaReduceExactBoundariesKey to false";
                goto LABEL_29;
              }
              v456 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v457 = TCntPtr<IRDPKeyCollection>::operator->(v456 + 80);
              v458 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v457 + 72LL))(v457, 16, 16);
              GfxPipeSettingBOOL = v458;
              if ( v458 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x7A2,
                  v458,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 195;
LABEL_177:
                v21 = "Failed to set DeltaReduceTileSizeKey to false";
                goto LABEL_29;
              }
              v459 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v460 = TCntPtr<IRDPKeyCollection>::operator->(v459 + 80);
              v461 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v460 + 64LL))(v460, 19, 1);
              GfxPipeSettingBOOL = v461;
              if ( v461 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x7A7,
                  v461,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 196;
                  v21 = "Failed to set CodecProcDisableInternalDelta to TRUE for Mixedmode AVC";
                  goto LABEL_29;
                }
                goto LABEL_928;
              }
              v462 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v463 = TCntPtr<IRDPKeyCollection>::operator->(v462 + 80);
              v464 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v463 + 64LL))(v463, 20);
              GfxPipeSettingBOOL = v464;
              if ( v464 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x7AC,
                  v464,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 197;
LABEL_111:
                v21 = "Failed to set MotionProcEnableExternalMotion to false";
                goto LABEL_29;
              }
              v465 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v466 = TCntPtr<IRDPKeyCollection>::operator->(v465 + 80);
              v467 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v466 + 64LL))(v466, 22, 1);
              GfxPipeSettingBOOL = v467;
              if ( v467 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
                  (char *)0x7B1,
                  v467,
                  v492);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v20 = 198;
                  v21 = "Failed to set MotionProcAlignTargetToMacroBlock to true";
                  goto LABEL_29;
                }
                goto LABEL_928;
              }
              v468 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v469 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
              v470 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
                       (char *)a1 + 96,
                       *(unsigned int *)(v469 + 16),
                       v468);
              GfxPipeSettingBOOL = v470;
              if ( v470 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_LoadEnabledProfilesAddFail",
                  (char *)0x7B5,
                  v470,
                  v492);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_928;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v20 = 199;
LABEL_61:
                v21 = "Add failed";
                goto LABEL_29;
              }
            }
            if ( (*((_BYTE *)a1 + 284) & 1) != 0 )
              ProfileManager::LoadTestProfile(a1);
            if ( (*((_BYTE *)a1 + 284) & 0x10) != 0 )
              ProfileManager::LoadLegacyProfile(a1);
            if ( (*((_DWORD *)a1 + 71) & 0x4000) != 0 )
              ProfileManager::LoadFbrProfile(a1);
            if ( (*((_DWORD *)a1 + 71) & 0x10000) != 0 )
              ProfileManager::LoadDisplayProtectionProfile(a1);
            ProfileManager::LoadThinClientProfiles(a1, *((_DWORD *)a1 + 71));
            v471 = -1;
            CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::StartEnum((char *)a1 + 96);
            TCntPtr<ProfileManager::Profile>::TCntPtr<ProfileManager::Profile>(v497);
            while ( 1 )
            {
              v472 = KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>::KeyComPtrNode<enum PipelineProcessor,IRdpProcessor>(v497);
              if ( !(unsigned int)CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::GetNext(
                                    (char *)a1 + 96,
                                    v472) )
                break;
              if ( *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(v497) + 20)
                && *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(v497) + 28) < v471 )
              {
                *((_DWORD *)a1 + 32) = *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(v497) + 16);
                v471 = *(_DWORD *)(TCntPtr<IRDPKeyCollection>::operator->(v497) + 28);
              }
              TCntPtr<MotionDetectionContext>::operator=(v497, 0);
            }
            TCntPtr<CRdpGridIterator>::~TCntPtr<CRdpGridIterator>(v497);
            *((_DWORD *)a1 + 33) = *((_DWORD *)a1 + 32);
            *((_DWORD *)a1 + 73) = *((_DWORD *)a1 + 72);
            goto LABEL_928;
          }
          v250 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
          v248 = TCntPtr<IRDPKeyCollection>::operator->(v250 + 80);
          v249 = 9;
        }
        v251 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v248 + 72LL))(v248, 1, v249);
        GfxPipeSettingBOOL = v251;
        if ( v251 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
            (char *)0x5EE,
            v251,
            v492);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_928;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 124;
          goto LABEL_41;
        }
        goto LABEL_527;
      }
      v191 = TCntPtr<IRDPKeyCollection>::operator->(&v493);
      v189 = TCntPtr<IRDPKeyCollection>::operator->(v191 + 80);
      v190 = 9;
    }
    v192 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v189 + 72LL))(v189, 1, v190);
    GfxPipeSettingBOOL = v192;
    if ( v192 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x564,
        v192,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 104;
      goto LABEL_41;
    }
    goto LABEL_417;
  }
  v27 = ProfileManager::CreateProfile(a1, &v493);
  GfxPipeSettingBOOL = v27;
  if ( v27 >= 0 )
  {
    *(_DWORD *)(v493 + 16) = 64;
    *(_DWORD *)(v493 + 20) = 1;
    *(_DWORD *)(v493 + 24) = 0;
    ProfileManager::SetRank(a1, 64, v493);
    *(_DWORD *)(v493 + 32) = 1000;
    *(_DWORD *)(v493 + 36) = 1000;
    *(_DWORD *)(v493 + 64) = 1;
    *(_DWORD *)(v493 + 72) = 2;
    v28 = CRDPKeyCollection::CreateInstance((struct IRDPKeyCollection **)(v493 + 80));
    GfxPipeSettingBOOL = v28;
    if ( v28 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesCRDPKeyCollectionCreateInstanceFail",
        (char *)0x3B5,
        v28,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 40;
      goto LABEL_35;
    }
    v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v493 + 80) + 72LL))(
            *(_QWORD *)(v493 + 80),
            1,
            2);
    GfxPipeSettingBOOL = v29;
    if ( v29 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesSetPropertyFail",
        (char *)0x3B9,
        v29,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 41;
      goto LABEL_41;
    }
    v30 = CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::Add(
            (char *)a1 + 96,
            *(unsigned int *)(v493 + 16),
            v493);
    GfxPipeSettingBOOL = v30;
    if ( v30 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
        "ProfileManagerError_LoadEnabledProfilesAddFail",
        (char *)0x3BD,
        v30,
        v492);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_928;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 42;
      goto LABEL_61;
    }
    goto LABEL_83;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
    "ProfileManagerError_LoadEnabledProfilesCreateProfileFail",
    (char *)0x394,
    v27,
    v492);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 39;
    goto LABEL_28;
  }
LABEL_928:
  CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::GetSize((char *)a1 + 96);
  if ( (unsigned int)CTSSimpleKeyComPtrArray<enum ProfileId,ProfileManager::Profile>::GetSize((char *)a1 + 96) )
  {
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0, v473, v474) )
    {
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v518, (char *)a1 + 288);
      ProfileName = GetProfileName(*((unsigned int *)a1 + 32));
      v481 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v531, ProfileName);
      v482 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v532, "LoadEnabledProfiles - Starting with");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&dword_18027EBA4,
        0,
        0,
        v482,
        v481,
        (__int64)v518);
    }
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v473, v474) )
    {
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v519, (char *)a1 + 288);
      v483 = GetProfileName(*((unsigned int *)a1 + 32));
      v484 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v533, v483);
      _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v524, (char *)a1 + 328);
      v485 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v534, "ProfileMgr");
      v486 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v535, "Stack");
      v523 = 0x1000000;
      v487 = v486;
      _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(v525, &v523);
      v488 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v536, "Checkpoint");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&unk_18027EB20,
        0,
        0,
        v488,
        (__int64)v525,
        v487,
        v485,
        (__int64)v524,
        v484,
        (__int64)v519);
    }
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0, v473, v474) )
    {
      v475 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v528, "LoadEnabledProfiles");
      v514 = 2038;
      v476 = v475;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v521, &v514);
      v477 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
               v529,
               "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\profilemanager.cpp");
      v515 = GfxPipeSettingBOOL;
      v478 = v477;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v517, &v515);
      v479 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
               v530,
               "Capability: Critical error: no profiles are enabled");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&word_18027EBEE,
        0,
        0,
        v479,
        (__int64)v517,
        v478,
        (__int64)v521,
        v476);
    }
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
      "ProfileManagerError_LoadEnabledProfilesNoProfilesFail",
      (char *)0x7F7,
      *((_DWORD *)a1 + 71),
      v492);
  }
  v489 = *((_DWORD *)a1 + 32);
  v490 = (struct IRDPPerfCounterGeneric *)TCntPtr<IRDPKeyCollection>::operator->((char *)a1 + 352);
  PerfCounterSetRdpIntervalMarker(v490, 0, v489);
  TCntPtr<CRdpGridIterator>::~TCntPtr<CRdpGridIterator>(&v493);
  return (unsigned int)GfxPipeSettingBOOL;
}

```

## disassembly

```asm
0x1800b8fbc  push    rbp
0x1800b8fbe  push    rbx
0x1800b8fbf  push    rsi
0x1800b8fc0  push    rdi
0x1800b8fc1  push    r12
0x1800b8fc3  push    r13
0x1800b8fc5  push    r14
0x1800b8fc7  push    r15
0x1800b8fc9  lea     rbp, [rsp-0E8h]
0x1800b8fd1  sub     rsp, 1E8h
0x1800b8fd8  mov     rax, cs:__security_cookie
0x1800b8fdf  xor     rax, rsp
0x1800b8fe2  mov     [rbp+120h+var_50], rax
0x1800b8fe9  xor     r11d, r11d
0x1800b8fec  mov     r12d, r9d
0x1800b8fef  mov     [rsp+220h+var_1C0], r11
0x1800b8ff4  mov     esi, r8d
0x1800b8ff7  mov     r15, rcx
0x1800b8ffa  mov     [rbp+120h+var_19C], r11d
0x1800b8ffe  mov     r14d, r11d
0x1800b9001  mov     [rbp+120h+var_1A0], r11d
0x1800b9005  lea     edi, [r11+1]
0x1800b9009  mov     [rsp+220h+var_1B0], r11d
0x1800b900e  mov     r9d, r11d
0x1800b9011  mov     r10d, r11d
0x1800b9014  cmp     [rcx+134h], edi
0x1800b901a  jnz     short loc_1800B9029
0x1800b901c  mov     [rsp+220h+var_1B4], r11d
0x1800b9021  cmp     [rcx+138h], edi
0x1800b9027  jz      short loc_1800B902D
0x1800b9029  mov     [rsp+220h+var_1B4], edi
0x1800b902d  mov     ebx, 2
0x1800b9032  test    edx, edx
0x1800b9034  jz      short loc_1800B9054
0x1800b9036  mov     eax, [rcx+128h]
0x1800b903c  test    eax, eax
0x1800b903e  jz      short loc_1800B9054
0x1800b9040  cmp     eax, ebx
0x1800b9042  jz      short loc_1800B904D
0x1800b9044  cmp     [rbp+120h+arg_30], r11d
0x1800b904b  jz      short loc_1800B9054
0x1800b904d  mov     [rbp+120h+var_19C], 3
0x1800b9054  mov     ecx, [rcx+13Ch]
0x1800b905a  mov     r8d, [rbp+120h+arg_28]
0x1800b9061  mov     edx, [rbp+120h+arg_20]
0x1800b9067  sub     ecx, 3
0x1800b906a  jz      short loc_1800B908D
0x1800b906c  cmp     ecx, edi
0x1800b906e  jnz     short loc_1800B90A2
0x1800b9070  test    edx, edx
0x1800b9072  jz      short loc_1800B9083
0x1800b9074  cmp     [r15+12Ch], r11d
0x1800b907b  cmovnz  r9d, edi
0x1800b907f  mov     [rbp+120h+var_1A0], r9d
0x1800b9083  mov     r10d, r9d
0x1800b9086  mov     [rsp+220h+var_1B0], r9d
0x1800b908b  jmp     short loc_1800B90A2
0x1800b908d  test    r8d, r8d
0x1800b9090  jz      short loc_1800B90A2
0x1800b9092  cmp     [r15+12Ch], r11d
0x1800b9099  cmovnz  r10d, edi
0x1800b909d  mov     [rsp+220h+var_1B0], r10d
0x1800b90a2  mov     eax, cs:CallbackContext
0x1800b90a8  cmp     eax, 4
0x1800b90ab  jbe     loc_1800B9144
0x1800b90b1  mov     [rbp+120h+var_178], r9d
0x1800b90b5  lea     rcx, CallbackContext
0x1800b90bc  mov     [rbp+120h+var_148], r10d
0x1800b90c0  xor     r9d, r9d
0x1800b90c3  mov     [rbp+120h+var_174], r11d
0x1800b90c7  mov     eax, [r15+13Ch]
0x1800b90ce  mov     [rbp+120h+var_170], eax
0x1800b90d1  mov     eax, [r15+12Ch]
0x1800b90d8  mov     [rbp+120h+var_16C], eax
0x1800b90db  lea     rax, aLoadenabledpro_2; "LoadEnabledProfiles - DownSamplingProfi"...
0x1800b90e2  mov     qword ptr [rbp+120h+var_140], rax
0x1800b90e6  lea     rax, [rbp+120h+var_148]
0x1800b90ea  mov     [rsp+220h+var_1C8], rax
0x1800b90ef  lea     rax, [rbp+120h+var_178]
0x1800b90f3  mov     [rsp+220h+var_1D0], rax
0x1800b90f8  lea     rax, [rbp+120h+var_174]
0x1800b90fc  mov     [rsp+220h+var_1D8], rax
0x1800b9101  lea     rax, [rbp+120h+var_170]
0x1800b9105  mov     [rsp+220h+var_1E0], rax
0x1800b910a  lea     rax, [rbp+120h+var_16C]
0x1800b910e  mov     [rsp+220h+var_1E8], rax
0x1800b9113  lea     rax, [rbp+120h+var_158]
0x1800b9117  mov     [rsp+220h+var_1F0], rax
0x1800b911c  lea     rax, [rbp+120h+var_168]
0x1800b9120  mov     [rsp+220h+var_1F8], rax
0x1800b9125  lea     rax, [rbp+120h+var_140]
0x1800b9129  mov     [rbp+120h+var_158], r8d
0x1800b912d  xor     r8d, r8d
0x1800b9130  mov     [rbp+120h+var_168], edx
0x1800b9133  lea     rdx, unk_18027ECF0
0x1800b913a  mov     qword ptr [rsp+220h+var_200], rax; int
0x1800b913f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b9144  lea     r13, [r15+60h]
0x1800b9148  mov     rcx, r13
0x1800b914b  call    ?RemoveAll@?$CTSSimpleKeyComPtrArray@W4ProfileId@@UProfile@ProfileManager@@@@QEAAXXZ; CTSSimpleKeyComPtrArray<ProfileId,ProfileManager::Profile>::RemoveAll(void)
0x1800b9150  test    byte ptr [r15+11Ch], 20h
0x1800b9158  lea     rdi, aIidIrdpprofile; "IID_IRdpProfileManager"
0x1800b915f  jz      loc_1800B950B
0x1800b9165  lea     rdx, [rsp+220h+var_1C0]
0x1800b916a  mov     rcx, r15
0x1800b916d  call    ?CreateProfile@ProfileManager@@AEAAJAEAV?$TCntPtr@UProfile@ProfileManager@@@@@Z; ProfileManager::CreateProfile(TCntPtr<ProfileManager::Profile> &)
0x1800b9172  mov     r14d, eax
0x1800b9175  test    eax, eax
0x1800b9177  jns     short loc_1800B91F8
0x1800b9179  mov     r9d, eax; unsigned int
0x1800b917c  lea     rdx, aProfilemanager_9; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b9183  mov     r8d, 363h; char *
0x1800b9189  mov     rcx, rdi; this
0x1800b918c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b9191  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9198  lea     rax, WPP_GLOBAL_Control
0x1800b919f  cmp     rcx, rax
0x1800b91a2  jz      loc_1800BF2E7
0x1800b91a8  mov     edi, 8
0x1800b91ad  test    [rcx+1Ch], dil
0x1800b91b1  jz      loc_1800BF2E7
0x1800b91b7  cmp     [rcx+19h], bl
0x1800b91ba  jb      loc_1800BF2E7
0x1800b91c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b91c5  lea     edx, [rdi+19h]
0x1800b91c8  lea     rcx, aCreateprofileF; "CreateProfile failed"
0x1800b91cf  mov     dword ptr [rsp+220h+var_1F8], r14d
0x1800b91d4  lea     r8, WPP_8c9510a349ee3b6327c0d183301c85a7_Traceguids
0x1800b91db  mov     qword ptr [rsp+220h+var_200], rcx
0x1800b91e0  mov     r9d, eax
0x1800b91e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b91ea  mov     rcx, [rcx+10h]
0x1800b91ee  call    WPP_SF_DsD
0x1800b91f3  jmp     loc_1800BF2E7
0x1800b91f8  mov     rax, [rsp+220h+var_1C0]
0x1800b91fd  mov     edx, 20h ; ' '
0x1800b9202  mov     [rax+10h], edx
0x1800b9205  lea     r14d, [rdx-1Fh]
0x1800b9209  mov     rax, [rsp+220h+var_1C0]
0x1800b920e  mov     [rax+14h], r14d
0x1800b9212  mov     ecx, [r15+0ECh]
0x1800b9219  mov     rax, [rsp+220h+var_1C0]
0x1800b921e  mov     [rax+18h], ecx
0x1800b9221  mov     rcx, r15
0x1800b9224  mov     r8, [rsp+220h+var_1C0]
0x1800b9229  call    ?SetRank@ProfileManager@@AEAAXW4ProfileId@@PEAUProfile@1@@Z; ProfileManager::SetRank(ProfileId,ProfileManager::Profile *)
0x1800b922e  mov     rax, [rsp+220h+var_1C0]
0x1800b9233  mov     ecx, 3E8h
0x1800b9238  mov     [rax+20h], ecx
0x1800b923b  mov     rax, [rsp+220h+var_1C0]
0x1800b9240  mov     [rax+24h], ecx
0x1800b9243  mov     rax, [rsp+220h+var_1C0]
0x1800b9248  mov     [rax+2Ch], r14d
0x1800b924c  mov     rax, [rsp+220h+var_1C0]
0x1800b9251  mov     [rax+28h], ebx
0x1800b9254  mov     rax, [rsp+220h+var_1C0]
0x1800b9259  mov     [rax+48h], ebx
0x1800b925c  mov     rcx, [rsp+220h+var_1C0]
0x1800b9261  add     rcx, 50h ; 'P'; struct IRDPKeyCollection **
0x1800b9265  call    ?CreateInstance@CRDPKeyCollection@@SAJPEAPEAUIRDPKeyCollection@@@Z; CRDPKeyCollection::CreateInstance(IRDPKeyCollection * *)
0x1800b926a  mov     r14d, eax
0x1800b926d  test    eax, eax
0x1800b926f  jns     short loc_1800B92CC
0x1800b9271  mov     r9d, eax; unsigned int
0x1800b9274  lea     rdx, aProfilemanager_0; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b927b  mov     r8d, 376h; char *
0x1800b9281  mov     rcx, rdi; this
0x1800b9284  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b9289  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9290  lea     rax, WPP_GLOBAL_Control
0x1800b9297  cmp     rcx, rax
0x1800b929a  jz      loc_1800BF2E7
0x1800b92a0  mov     edi, 8
0x1800b92a5  test    [rcx+1Ch], dil
0x1800b92a9  jz      loc_1800BF2E7
0x1800b92af  cmp     [rcx+19h], bl
0x1800b92b2  jb      loc_1800BF2E7
0x1800b92b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b92bd  lea     edx, [rdi+1Ah]
0x1800b92c0  lea     rcx, aCrdpkeycollect_0; "CRDPKeyCollection::CreateInstance faile"...
0x1800b92c7  jmp     loc_1800B91CF
0x1800b92cc  mov     rax, [rsp+220h+var_1C0]
0x1800b92d1  mov     edx, 1
0x1800b92d6  mov     rcx, [rax+50h]
0x1800b92da  lea     r8d, [rdx+4]
0x1800b92de  mov     rax, [rcx]
0x1800b92e1  mov     rax, [rax+48h]
0x1800b92e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b92ea  mov     r14d, eax
0x1800b92ed  test    eax, eax
0x1800b92ef  jns     short loc_1800B934C
0x1800b92f1  mov     r9d, eax; unsigned int
0x1800b92f4  lea     rdx, aProfilemanager_4; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b92fb  mov     r8d, 37Ah; char *
0x1800b9301  mov     rcx, rdi; this
0x1800b9304  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b9309  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9310  lea     rax, WPP_GLOBAL_Control
0x1800b9317  cmp     rcx, rax
0x1800b931a  jz      loc_1800BF2E7
0x1800b9320  mov     edi, 8
0x1800b9325  test    [rcx+1Ch], dil
0x1800b9329  jz      loc_1800BF2E7
0x1800b932f  cmp     [rcx+19h], bl
0x1800b9332  jb      loc_1800BF2E7
0x1800b9338  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b933d  lea     edx, [rdi+1Bh]
0x1800b9340  lea     rcx, aSetpropertyuns_1; "SetPropertyUnsignedLong failed"
0x1800b9347  jmp     loc_1800B91CF
0x1800b934c  mov     rax, [rsp+220h+var_1C0]
0x1800b9351  mov     r8d, ebx
0x1800b9354  mov     edx, 0Bh
0x1800b9359  mov     rcx, [rax+50h]
0x1800b935d  mov     rax, [rcx]
0x1800b9360  mov     rax, [rax+48h]
0x1800b9364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9369  mov     r14d, eax
0x1800b936c  test    eax, eax
0x1800b936e  jns     short loc_1800B93CB
0x1800b9370  mov     r9d, eax; unsigned int
0x1800b9373  lea     rdx, aProfilemanager_4; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b937a  mov     r8d, 37Fh; char *
0x1800b9380  mov     rcx, rdi; this
0x1800b9383  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b9388  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b938f  lea     rax, WPP_GLOBAL_Control
0x1800b9396  cmp     rcx, rax
0x1800b9399  jz      loc_1800BF2E7
0x1800b939f  mov     edi, 8
0x1800b93a4  test    [rcx+1Ch], dil
0x1800b93a8  jz      loc_1800BF2E7
0x1800b93ae  cmp     [rcx+19h], bl
0x1800b93b1  jb      loc_1800BF2E7
0x1800b93b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b93bc  lea     edx, [rdi+1Ch]
0x1800b93bf  lea     rcx, aSetpropertyuns; "SetPropertyUnsignedLong( ImageQualityKe"...
0x1800b93c6  jmp     loc_1800B91CF
0x1800b93cb  mov     eax, cs:CallbackContext
0x1800b93d1  cmp     eax, 4
0x1800b93d4  jbe     short loc_1800B9416
0x1800b93d6  lea     rdx, aLoadenabledpro_0; "LoadEnabledProfiles: Always set quality"...
0x1800b93dd  lea     rcx, [rbp+120h+var_60]
0x1800b93e4  call    ??$_tlgCreate1Sz@D@@YAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBD@Z; _tlgCreate1Sz<char>(_EVENT_DATA_DESCRIPTOR *,char const *)
0x1800b93e9  lea     rax, [rbp+120h+var_80]
0x1800b93f0  xor     r9d, r9d
0x1800b93f3  mov     [rsp+220h+var_1F8], rax
0x1800b93f8  lea     rdx, byte_18027ECC7
0x1800b93ff  xor     r8d, r8d
0x1800b9402  mov     [rsp+220h+var_200], 3; int
0x1800b940a  lea     rcx, CallbackContext
0x1800b9411  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b9416  mov     rax, [rsp+220h+var_1C0]
0x1800b941b  mov     edx, 0Ch
0x1800b9420  mov     rcx, [rax+50h]
0x1800b9424  lea     r8d, [rdx-0Bh]
0x1800b9428  mov     rax, [rcx]
0x1800b942b  mov     rax, [rax+40h]
0x1800b942f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9434  mov     r14d, eax
0x1800b9437  test    eax, eax
0x1800b9439  jns     short loc_1800B9496
0x1800b943b  mov     r9d, eax; unsigned int
0x1800b943e  lea     rdx, aProfilemanager_4; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b9445  mov     r8d, 385h; char *
0x1800b944b  mov     rcx, rdi; this
0x1800b944e  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b9453  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b945a  lea     rax, WPP_GLOBAL_Control
0x1800b9461  cmp     rcx, rax
0x1800b9464  jz      loc_1800BF2E7
0x1800b946a  mov     edi, 8
0x1800b946f  test    [rcx+1Ch], dil
0x1800b9473  jz      loc_1800BF2E7
0x1800b9479  cmp     [rcx+19h], bl
0x1800b947c  jb      loc_1800BF2E7
0x1800b9482  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b9487  lea     edx, [rdi+1Dh]
0x1800b948a  lea     rcx, aSetpropertyboo_1; "SetPropertyBool failed"
0x1800b9491  jmp     loc_1800B91CF
0x1800b9496  mov     rdx, [rsp+220h+var_1C0]
0x1800b949b  mov     rcx, r13
0x1800b949e  mov     r8, rdx
0x1800b94a1  mov     edx, [rdx+10h]
0x1800b94a4  call    ?Add@?$CTSSimpleKeyComPtrArray@W4ProfileId@@UProfile@ProfileManager@@@@QEAAJW4ProfileId@@PEAUProfile@ProfileManager@@@Z; CTSSimpleKeyComPtrArray<ProfileId,ProfileManager::Profile>::Add(ProfileId,ProfileManager::Profile *)
0x1800b94a9  mov     r14d, eax
0x1800b94ac  test    eax, eax
0x1800b94ae  jns     short loc_1800B950B
0x1800b94b0  mov     r9d, eax; unsigned int
0x1800b94b3  lea     rdx, aProfilemanager_6; "ProfileManagerError_LoadEnabledProfiles"...
0x1800b94ba  mov     r8d, 389h; char *
0x1800b94c0  mov     rcx, rdi; this
0x1800b94c3  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b94c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b94cf  lea     rax, WPP_GLOBAL_Control
0x1800b94d6  cmp     rcx, rax
0x1800b94d9  jz      loc_1800BF2E7
0x1800b94df  mov     edi, 8
0x1800b94e4  test    [rcx+1Ch], dil
0x1800b94e8  jz      loc_1800BF2E7
0x1800b94ee  cmp     [rcx+19h], bl
  ... truncated ...
```
