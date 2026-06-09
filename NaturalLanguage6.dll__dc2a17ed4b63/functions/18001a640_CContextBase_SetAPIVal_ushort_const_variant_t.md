# CContextBase::SetAPIVal(ushort const *,_variant_t &)

- ea: `0x18001a640`
- end: `0x180021bb6`
- name: `?SetAPIVal@CContextBase@@QEAA_NPEBGAEAV_variant_t@@@Z`
- size: `30070`
- prototype: `bool __fastcall(CContextBase *__hidden this, const unsigned __int16 *, struct _variant_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001a260`

## callees

- `0x18000a550`
- `0x18000a740`
- `0x18001a640`
- `0x180030ca8`
- `0x180035640`
- `0x180037018`
- `0x18003ed6c`
- `0x18005f31c`
- `0x18005f388`
- `0x1800b0010`

## string_xrefs

- `0x18001baad`: `ComputingCompounds`
- `0x18001b9be`: `IsComputingCompounds`
- `0x18001bc4e`: `IsComputingInflections`
- `0x18001bd3d`: `ComputingInflections`
- `0x18001bb7e`: `Compounds`
- `0x18001c086`: `IsComputingLemmas`
- `0x18001c16d`: `ComputingLemmas`
- `0x18001c3e6`: `IsComputingExpansions`
- `0x18001c4c5`: `ComputingExpansions`
- `0x18001c676`: `IsComputingBases`
- `0x18001c751`: `ComputingBases`
- `0x18001c9ef`: `ComputingPartOfSpeechTags`
- `0x18001c906`: `IsComputingPartOfSpeechTags`
- `0x18001dc51`: `IsComputingHyphenation`
- `0x18001dd45`: `ComputingHyphenation`
- `0x18001e8e1`: `ForcingCompoundSuggestions`
- `0x18001e711`: `IsSpellForcingCompoundSuggestions`
- `0x18001e805`: `SpellForcingCompoundSuggestions`
- `0x18001f0f1`: `VerifyAutoReplace`
- `0x18001f015`: `SpellVerifyAutoReplace`
- `0x18001ef21`: `IsSpellVerifyAutoReplace`
- `0x180020d05`: `KoreanAuxCombine`
- `0x1800210a5`: `KoreanCompoundNounProc`
- `0x180020c11`: `IsKoreanAuxCombine`
- `0x180020fb1`: `IsKoreanCompoundNounProc`
- `0x180021aa6`: `ReturnAutoReplace`
- `0x1800219b7`: `IsReturnAutoReplace`

## pseudocode

```c
bool __fastcall CContextBase::SetAPIVal(CContextBase *this, const unsigned __int16 *a2, struct _variant_t *a3)
{
  const wchar_t *v4; // r14
  const unsigned __int16 *v5; // rbp
  const unsigned __int16 *v7; // rsi
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // di
  wchar_t v10; // bx
  wchar_t v11; // cx
  int v12; // eax
  const wchar_t *v13; // r14
  const unsigned __int16 *v14; // rsi
  unsigned __int16 v15; // bx
  unsigned __int16 v16; // di
  wchar_t v17; // bx
  wchar_t v18; // cx
  const wchar_t *v19; // r14
  const unsigned __int16 *v20; // rsi
  unsigned __int16 v21; // bx
  unsigned __int16 v22; // di
  wchar_t v23; // bx
  wchar_t v24; // cx
  const wchar_t *v25; // r14
  const unsigned __int16 *v26; // rsi
  unsigned __int16 v27; // bx
  unsigned __int16 v28; // di
  wchar_t v29; // bx
  wchar_t v30; // cx
  bool result; // al
  const wchar_t *v32; // r14
  const unsigned __int16 *v33; // rsi
  unsigned __int16 v34; // di
  unsigned __int16 v35; // bx
  wchar_t v36; // di
  wchar_t v37; // cx
  void (__fastcall *v38)(CContextBase *, _QWORD); // rbx
  unsigned __int8 v39; // al
  const wchar_t *v40; // r14
  const unsigned __int16 *v41; // rsi
  unsigned __int16 v42; // bx
  unsigned __int16 v43; // di
  wchar_t v44; // bx
  wchar_t v45; // cx
  const OLECHAR *v46; // r14
  const unsigned __int16 *v47; // rsi
  unsigned __int16 v48; // bx
  unsigned __int16 v49; // di
  OLECHAR v50; // bx
  OLECHAR v51; // cx
  const wchar_t *v52; // r14
  const unsigned __int16 *v53; // rsi
  unsigned __int16 v54; // bx
  unsigned __int16 v55; // di
  wchar_t v56; // bx
  wchar_t v57; // cx
  const wchar_t *v58; // r15
  const unsigned __int16 *v59; // rsi
  const wchar_t *v60; // r14
  unsigned __int16 v61; // bx
  unsigned __int16 v62; // di
  wchar_t v63; // bx
  wchar_t v64; // cx
  const unsigned __int16 *v65; // rsi
  unsigned __int16 v66; // bx
  unsigned __int16 v67; // di
  wchar_t v68; // bx
  wchar_t v69; // cx
  const OLECHAR *v70; // r15
  const unsigned __int16 *v71; // rsi
  const OLECHAR *v72; // r14
  unsigned __int16 v73; // bx
  unsigned __int16 v74; // di
  OLECHAR v75; // bx
  OLECHAR v76; // cx
  const unsigned __int16 *v77; // rsi
  unsigned __int16 v78; // di
  unsigned __int16 v79; // bx
  OLECHAR v80; // di
  OLECHAR v81; // cx
  const wchar_t *v82; // r14
  const unsigned __int16 *v83; // rsi
  unsigned __int16 v84; // di
  unsigned __int16 v85; // bx
  wchar_t v86; // di
  wchar_t v87; // cx
  const OLECHAR *v88; // r14
  const unsigned __int16 *v89; // rsi
  unsigned __int16 v90; // di
  unsigned __int16 v91; // bx
  OLECHAR v92; // di
  OLECHAR v93; // cx
  const wchar_t *v94; // r14
  const unsigned __int16 *v95; // rsi
  unsigned __int16 v96; // bx
  unsigned __int16 v97; // di
  wchar_t v98; // bx
  wchar_t v99; // cx
  const wchar_t *v100; // r14
  const unsigned __int16 *v101; // rsi
  unsigned __int16 v102; // bx
  unsigned __int16 v103; // di
  wchar_t v104; // bx
  wchar_t v105; // cx
  const OLECHAR *v106; // r14
  const unsigned __int16 *v107; // rsi
  unsigned __int16 v108; // bx
  unsigned __int16 v109; // di
  OLECHAR v110; // bx
  OLECHAR v111; // cx
  const wchar_t *v112; // r14
  const unsigned __int16 *v113; // rsi
  unsigned __int16 v114; // bx
  unsigned __int16 v115; // di
  wchar_t v116; // bx
  wchar_t v117; // cx
  const wchar_t *v118; // r14
  const unsigned __int16 *v119; // rsi
  unsigned __int16 v120; // bx
  unsigned __int16 v121; // di
  wchar_t v122; // bx
  wchar_t v123; // cx
  const OLECHAR *v124; // r14
  const unsigned __int16 *v125; // rsi
  unsigned __int16 v126; // bx
  unsigned __int16 v127; // di
  OLECHAR v128; // bx
  OLECHAR v129; // cx
  const wchar_t *v130; // r14
  const unsigned __int16 *v131; // rsi
  unsigned __int16 v132; // bx
  unsigned __int16 v133; // di
  wchar_t v134; // bx
  wchar_t v135; // cx
  const wchar_t *v136; // r14
  const unsigned __int16 *v137; // rsi
  unsigned __int16 v138; // bx
  unsigned __int16 v139; // di
  wchar_t v140; // bx
  wchar_t v141; // cx
  const wchar_t *v142; // r14
  const unsigned __int16 *v143; // rsi
  unsigned __int16 v144; // bx
  unsigned __int16 v145; // di
  wchar_t v146; // bx
  wchar_t v147; // cx
  const wchar_t *v148; // r14
  const unsigned __int16 *v149; // rsi
  unsigned __int16 v150; // bx
  unsigned __int16 v151; // di
  wchar_t v152; // bx
  wchar_t v153; // cx
  const wchar_t *v154; // r14
  const unsigned __int16 *v155; // rsi
  unsigned __int16 v156; // bx
  unsigned __int16 v157; // di
  wchar_t v158; // bx
  wchar_t v159; // cx
  const wchar_t *v160; // r14
  const unsigned __int16 *v161; // rsi
  unsigned __int16 v162; // bx
  unsigned __int16 v163; // di
  wchar_t v164; // bx
  wchar_t v165; // cx
  const wchar_t *v166; // r14
  const unsigned __int16 *v167; // rsi
  unsigned __int16 v168; // bx
  unsigned __int16 v169; // di
  wchar_t v170; // bx
  wchar_t v171; // cx
  const wchar_t *v172; // r14
  const unsigned __int16 *v173; // rsi
  unsigned __int16 v174; // bx
  unsigned __int16 v175; // di
  wchar_t v176; // bx
  wchar_t v177; // cx
  const wchar_t *v178; // r14
  const unsigned __int16 *v179; // rsi
  unsigned __int16 v180; // bx
  unsigned __int16 v181; // di
  wchar_t v182; // bx
  wchar_t v183; // cx
  const wchar_t *v184; // r14
  const unsigned __int16 *v185; // rsi
  unsigned __int16 v186; // bx
  unsigned __int16 v187; // di
  wchar_t v188; // bx
  wchar_t v189; // cx
  const wchar_t *v190; // r14
  const unsigned __int16 *v191; // rsi
  unsigned __int16 v192; // bx
  unsigned __int16 v193; // di
  wchar_t v194; // bx
  wchar_t v195; // cx
  const wchar_t *v196; // r14
  const unsigned __int16 *v197; // rsi
  unsigned __int16 v198; // bx
  unsigned __int16 v199; // di
  wchar_t v200; // bx
  wchar_t v201; // cx
  const wchar_t *v202; // r14
  const unsigned __int16 *v203; // rsi
  unsigned __int16 v204; // bx
  unsigned __int16 v205; // di
  wchar_t v206; // bx
  wchar_t v207; // cx
  const wchar_t *v208; // r14
  const unsigned __int16 *v209; // rsi
  unsigned __int16 v210; // bx
  unsigned __int16 v211; // di
  wchar_t v212; // bx
  wchar_t v213; // cx
  const OLECHAR *v214; // r14
  const unsigned __int16 *v215; // rsi
  unsigned __int16 v216; // bx
  unsigned __int16 v217; // di
  OLECHAR v218; // bx
  OLECHAR v219; // cx
  const wchar_t *v220; // r14
  const unsigned __int16 *v221; // rsi
  unsigned __int16 v222; // bx
  unsigned __int16 v223; // di
  wchar_t v224; // bx
  wchar_t v225; // cx
  const wchar_t *v226; // r14
  const unsigned __int16 *v227; // rsi
  unsigned __int16 v228; // bx
  unsigned __int16 v229; // di
  wchar_t v230; // bx
  wchar_t v231; // cx
  const OLECHAR *v232; // r14
  const unsigned __int16 *v233; // rsi
  unsigned __int16 v234; // bx
  unsigned __int16 v235; // di
  OLECHAR v236; // bx
  OLECHAR v237; // cx
  const wchar_t *v238; // r14
  const unsigned __int16 *v239; // rsi
  unsigned __int16 v240; // bx
  unsigned __int16 v241; // di
  wchar_t v242; // bx
  wchar_t v243; // cx
  const wchar_t *v244; // r14
  const unsigned __int16 *v245; // rsi
  unsigned __int16 v246; // bx
  unsigned __int16 v247; // di
  wchar_t v248; // bx
  wchar_t v249; // cx
  const wchar_t *v250; // r14
  const unsigned __int16 *v251; // rsi
  unsigned __int16 v252; // bx
  unsigned __int16 v253; // di
  wchar_t v254; // bx
  wchar_t v255; // cx
  const wchar_t *v256; // r14
  const unsigned __int16 *v257; // rsi
  unsigned __int16 v258; // bx
  unsigned __int16 v259; // di
  wchar_t v260; // bx
  wchar_t v261; // cx
  const wchar_t *v262; // r14
  const unsigned __int16 *v263; // rsi
  unsigned __int16 v264; // bx
  unsigned __int16 v265; // di
  wchar_t v266; // bx
  wchar_t v267; // cx
  const wchar_t *v268; // r14
  const unsigned __int16 *v269; // rsi
  unsigned __int16 v270; // bx
  unsigned __int16 v271; // di
  wchar_t v272; // bx
  wchar_t v273; // cx
  const OLECHAR *v274; // r14
  const unsigned __int16 *v275; // rsi
  unsigned __int16 v276; // bx
  unsigned __int16 v277; // di
  OLECHAR v278; // bx
  OLECHAR v279; // cx
  const wchar_t *v280; // r14
  const unsigned __int16 *v281; // rsi
  unsigned __int16 v282; // bx
  unsigned __int16 v283; // di
  wchar_t v284; // bx
  wchar_t v285; // cx
  const wchar_t *v286; // r14
  const unsigned __int16 *v287; // rsi
  unsigned __int16 v288; // bx
  unsigned __int16 v289; // di
  wchar_t v290; // bx
  wchar_t v291; // cx
  const OLECHAR *v292; // r14
  const unsigned __int16 *v293; // rsi
  unsigned __int16 v294; // bx
  unsigned __int16 v295; // di
  OLECHAR v296; // bx
  OLECHAR v297; // cx
  const wchar_t *v298; // r14
  const unsigned __int16 *v299; // rsi
  unsigned __int16 v300; // bx
  unsigned __int16 v301; // di
  wchar_t v302; // bx
  wchar_t v303; // cx
  const wchar_t *v304; // r14
  const unsigned __int16 *v305; // rsi
  unsigned __int16 v306; // bx
  unsigned __int16 v307; // di
  wchar_t v308; // bx
  wchar_t v309; // cx
  const OLECHAR *v310; // r14
  const unsigned __int16 *v311; // rsi
  unsigned __int16 v312; // bx
  unsigned __int16 v313; // di
  OLECHAR v314; // bx
  OLECHAR v315; // cx
  const wchar_t *v316; // r14
  const unsigned __int16 *v317; // rsi
  unsigned __int16 v318; // bx
  unsigned __int16 v319; // di
  wchar_t v320; // bx
  wchar_t v321; // cx
  const wchar_t *v322; // r14
  const unsigned __int16 *v323; // rsi
  unsigned __int16 v324; // bx
  unsigned __int16 v325; // di
  wchar_t v326; // bx
  wchar_t v327; // cx
  const OLECHAR *v328; // r14
  const unsigned __int16 *v329; // rsi
  unsigned __int16 v330; // bx
  unsigned __int16 v331; // di
  OLECHAR v332; // bx
  OLECHAR v333; // cx
  const wchar_t *v334; // r14
  const unsigned __int16 *v335; // rsi
  unsigned __int16 v336; // bx
  unsigned __int16 v337; // di
  wchar_t v338; // bx
  wchar_t v339; // cx
  const wchar_t *v340; // r14
  const unsigned __int16 *v341; // rsi
  unsigned __int16 v342; // bx
  unsigned __int16 v343; // di
  wchar_t v344; // bx
  wchar_t v345; // cx
  const OLECHAR *v346; // r14
  const unsigned __int16 *v347; // rsi
  unsigned __int16 v348; // bx
  unsigned __int16 v349; // di
  OLECHAR v350; // bx
  OLECHAR v351; // cx
  const wchar_t *v352; // r14
  const unsigned __int16 *v353; // rsi
  unsigned __int16 v354; // bx
  unsigned __int16 v355; // di
  wchar_t v356; // bx
  wchar_t v357; // cx
  const wchar_t *v358; // r14
  const unsigned __int16 *v359; // rsi
  unsigned __int16 v360; // bx
  unsigned __int16 v361; // di
  wchar_t v362; // bx
  wchar_t v363; // cx
  const OLECHAR *v364; // r14
  const unsigned __int16 *v365; // rsi
  unsigned __int16 v366; // bx
  unsigned __int16 v367; // di
  OLECHAR v368; // bx
  OLECHAR v369; // cx
  const wchar_t *v370; // r14
  const unsigned __int16 *v371; // rsi
  unsigned __int16 v372; // bx
  unsigned __int16 v373; // di
  wchar_t v374; // bx
  wchar_t v375; // cx
  const wchar_t *v376; // r14
  const unsigned __int16 *v377; // rsi
  unsigned __int16 v378; // bx
  unsigned __int16 v379; // di
  wchar_t v380; // bx
  wchar_t v381; // cx
  const wchar_t *v382; // r14
  const unsigned __int16 *v383; // rsi
  unsigned __int16 v384; // bx
  unsigned __int16 v385; // di
  wchar_t v386; // bx
  wchar_t v387; // cx
  const wchar_t *v388; // r14
  const unsigned __int16 *v389; // rsi
  unsigned __int16 v390; // bx
  unsigned __int16 v391; // di
  wchar_t v392; // bx
  wchar_t v393; // cx
  const wchar_t *v394; // r14
  const unsigned __int16 *v395; // rsi
  unsigned __int16 v396; // bx
  unsigned __int16 v397; // di
  wchar_t v398; // bx
  wchar_t v399; // cx
  const OLECHAR *v400; // r14
  const unsigned __int16 *v401; // rsi
  unsigned __int16 v402; // bx
  unsigned __int16 v403; // di
  OLECHAR v404; // bx
  OLECHAR v405; // cx
  const wchar_t *v406; // r14
  const unsigned __int16 *v407; // rsi
  unsigned __int16 v408; // bx
  unsigned __int16 v409; // di
  wchar_t v410; // bx
  wchar_t v411; // cx
  const wchar_t *v412; // r14
  const unsigned __int16 *v413; // rsi
  unsigned __int16 v414; // bx
  unsigned __int16 v415; // di
  wchar_t v416; // bx
  wchar_t v417; // cx
  const wchar_t *v418; // r14
  const unsigned __int16 *v419; // rsi
  unsigned __int16 v420; // bx
  unsigned __int16 v421; // di
  wchar_t v422; // bx
  wchar_t v423; // cx
  const wchar_t *v424; // r14
  const unsigned __int16 *v425; // rsi
  unsigned __int16 v426; // bx
  unsigned __int16 v427; // di
  wchar_t v428; // bx
  wchar_t v429; // cx
  const wchar_t *v430; // r14
  const unsigned __int16 *v431; // rsi
  unsigned __int16 v432; // bx
  unsigned __int16 v433; // di
  wchar_t v434; // bx
  wchar_t v435; // cx
  const OLECHAR *v436; // r14
  const unsigned __int16 *v437; // rsi
  unsigned __int16 v438; // bx
  unsigned __int16 v439; // di
  OLECHAR v440; // bx
  OLECHAR v441; // cx
  const wchar_t *v442; // r14
  const unsigned __int16 *v443; // rsi
  unsigned __int16 v444; // bx
  unsigned __int16 v445; // di
  wchar_t v446; // bx
  wchar_t v447; // cx
  const wchar_t *v448; // r14
  const unsigned __int16 *v449; // rsi
  unsigned __int16 v450; // bx
  unsigned __int16 v451; // di
  wchar_t v452; // bx
  wchar_t v453; // cx
  const wchar_t *v454; // r14
  const unsigned __int16 *v455; // rsi
  unsigned __int16 v456; // bx
  unsigned __int16 v457; // di
  wchar_t v458; // bx
  wchar_t v459; // cx
  const wchar_t *v460; // r14
  const unsigned __int16 *v461; // rsi
  unsigned __int16 v462; // bx
  unsigned __int16 v463; // di
  wchar_t v464; // bx
  wchar_t v465; // cx
  const wchar_t *v466; // r14
  const unsigned __int16 *v467; // rsi
  unsigned __int16 v468; // bx
  unsigned __int16 v469; // di
  wchar_t v470; // bx
  wchar_t v471; // cx
  const OLECHAR *v472; // r14
  const unsigned __int16 *v473; // rsi
  unsigned __int16 v474; // bx
  unsigned __int16 v475; // di
  OLECHAR v476; // bx
  OLECHAR v477; // cx
  const wchar_t *v478; // r14
  const unsigned __int16 *v479; // rsi
  unsigned __int16 v480; // bx
  unsigned __int16 v481; // di
  wchar_t v482; // bx
  wchar_t v483; // cx
  const wchar_t *v484; // r14
  const unsigned __int16 *v485; // rsi
  unsigned __int16 v486; // bx
  unsigned __int16 v487; // di
  wchar_t v488; // bx
  wchar_t v489; // cx
  const wchar_t *v490; // r14
  const unsigned __int16 *v491; // rsi
  unsigned __int16 v492; // bx
  unsigned __int16 v493; // di
  wchar_t v494; // bx
  wchar_t v495; // cx
  const wchar_t *v496; // r14
  const unsigned __int16 *v497; // rsi
  unsigned __int16 v498; // bx
  unsigned __int16 v499; // di
  wchar_t v500; // bx
  wchar_t v501; // cx
  const wchar_t *v502; // r14
  const unsigned __int16 *v503; // rsi
  unsigned __int16 v504; // bx
  unsigned __int16 v505; // di
  wchar_t v506; // bx
  wchar_t v507; // cx
  const wchar_t *v508; // r14
  const unsigned __int16 *v509; // rsi
  unsigned __int16 v510; // bx
  unsigned __int16 v511; // di
  wchar_t v512; // bx
  wchar_t v513; // cx
  const wchar_t *v514; // r14
  const unsigned __int16 *v515; // rsi
  unsigned __int16 v516; // bx
  unsigned __int16 v517; // di
  wchar_t v518; // bx
  wchar_t v519; // cx
  const wchar_t *v520; // r14
  const unsigned __int16 *v521; // rsi
  unsigned __int16 v522; // bx
  unsigned __int16 v523; // di
  wchar_t v524; // bx
  wchar_t v525; // cx
  const wchar_t *v526; // r14
  const unsigned __int16 *v527; // rsi
  unsigned __int16 v528; // bx
  unsigned __int16 v529; // di
  wchar_t v530; // bx
  wchar_t v531; // cx
  const wchar_t *v532; // r14
  const unsigned __int16 *v533; // rsi
  unsigned __int16 v534; // bx
  unsigned __int16 v535; // di
  wchar_t v536; // bx
  wchar_t v537; // cx
  const wchar_t *v538; // r14
  const unsigned __int16 *v539; // rsi
  unsigned __int16 v540; // bx
  unsigned __int16 v541; // di
  wchar_t v542; // bx
  wchar_t v543; // cx
  const OLECHAR *v544; // r14
  const unsigned __int16 *v545; // rsi
  unsigned __int16 v546; // bx
  unsigned __int16 v547; // di
  OLECHAR v548; // bx
  OLECHAR v549; // cx
  const wchar_t *v550; // r14
  const unsigned __int16 *v551; // rsi
  unsigned __int16 v552; // bx
  unsigned __int16 v553; // di
  wchar_t v554; // bx
  wchar_t v555; // cx
  const wchar_t *v556; // r14
  const unsigned __int16 *v557; // rsi
  unsigned __int16 v558; // bx
  unsigned __int16 v559; // di
  wchar_t v560; // bx
  wchar_t v561; // cx
  const wchar_t *v562; // r14
  const unsigned __int16 *v563; // rsi
  unsigned __int16 v564; // bx
  unsigned __int16 v565; // di
  wchar_t v566; // bx
  wchar_t v567; // cx
  const wchar_t *v568; // r14
  const unsigned __int16 *v569; // rsi
  unsigned __int16 v570; // bx
  unsigned __int16 v571; // di
  wchar_t v572; // bx
  wchar_t v573; // cx
  const wchar_t *v574; // r14
  const unsigned __int16 *v575; // rsi
  unsigned __int16 v576; // bx
  unsigned __int16 v577; // di
  wchar_t v578; // bx
  wchar_t v579; // cx
  const wchar_t *v580; // r14
  const unsigned __int16 *v581; // rsi
  unsigned __int16 v582; // bx
  unsigned __int16 v583; // di
  wchar_t v584; // bx
  wchar_t v585; // cx
  const OLECHAR *v586; // r14
  const unsigned __int16 *v587; // rsi
  unsigned __int16 v588; // bx
  unsigned __int16 v589; // di
  OLECHAR v590; // bx
  OLECHAR v591; // cx
  const wchar_t *v592; // r14
  const unsigned __int16 *v593; // rsi
  unsigned __int16 v594; // bx
  unsigned __int16 v595; // di
  wchar_t v596; // bx
  wchar_t v597; // cx
  const OLECHAR *v598; // r14
  const unsigned __int16 *v599; // rsi
  unsigned __int16 v600; // bx
  unsigned __int16 v601; // di
  OLECHAR v602; // bx
  OLECHAR v603; // cx
  const wchar_t *v604; // r14
  const unsigned __int16 *v605; // rsi
  unsigned __int16 v606; // bx
  unsigned __int16 v607; // di
  wchar_t v608; // bx
  wchar_t v609; // cx
  const wchar_t *v610; // r14
  const unsigned __int16 *v611; // rsi
  unsigned __int16 v612; // bx
  unsigned __int16 v613; // di
  wchar_t v614; // bx
  wchar_t v615; // cx
  const wchar_t *v616; // r14
  const unsigned __int16 *v617; // rsi
  unsigned __int16 v618; // bx
  unsigned __int16 v619; // di
  wchar_t v620; // bx
  wchar_t v621; // cx
  const wchar_t *v622; // r14
  const unsigned __int16 *v623; // rsi
  unsigned __int16 v624; // bx
  unsigned __int16 v625; // di
  wchar_t v626; // bx
  wchar_t v627; // cx
  const wchar_t *v628; // r14
  const unsigned __int16 *v629; // rsi
  unsigned __int16 v630; // bx
  unsigned __int16 v631; // di
  wchar_t v632; // bx
  wchar_t v633; // cx
  const OLECHAR *v634; // r14
  const unsigned __int16 *v635; // rsi
  unsigned __int16 v636; // bx
  unsigned __int16 v637; // di
  OLECHAR v638; // bx
  OLECHAR v639; // cx
  const wchar_t *v640; // r14
  const unsigned __int16 *v641; // rsi
  unsigned __int16 v642; // bx
  unsigned __int16 v643; // di
  wchar_t v644; // bx
  wchar_t v645; // cx
  const wchar_t *v646; // r14
  const unsigned __int16 *v647; // rsi
  unsigned __int16 v648; // bx
  unsigned __int16 v649; // di
  wchar_t v650; // bx
  wchar_t v651; // cx
  const wchar_t *v652; // r14
  const unsigned __int16 *v653; // rsi
  unsigned __int16 v654; // bx
  unsigned __int16 v655; // di
  wchar_t v656; // bx
  wchar_t v657; // cx
  const wchar_t *v658; // r14
  const unsigned __int16 *v659; // rsi
  unsigned __int16 v660; // bx
  unsigned __int16 v661; // di
  wchar_t v662; // bx
  wchar_t v663; // cx
  const wchar_t *v664; // r14
  const unsigned __int16 *v665; // rsi
  unsigned __int16 v666; // bx
  unsigned __int16 v667; // di
  wchar_t v668; // bx
  wchar_t v669; // cx
  const wchar_t *v670; // r14
  const unsigned __int16 *v671; // rsi
  unsigned __int16 v672; // bx
  unsigned __int16 v673; // di
  wchar_t v674; // bx
  wchar_t v675; // cx
  const wchar_t *v676; // r14
  const unsigned __int16 *v677; // rsi
  unsigned __int16 v678; // bx
  unsigned __int16 v679; // di
  wchar_t v680; // bx
  wchar_t v681; // cx
  const wchar_t *v682; // r14
  const unsigned __int16 *i; // rsi
  unsigned __int16 v684; // bx
  unsigned __int16 v685; // di
  wchar_t v686; // bx
  wchar_t v687; // cx
  int v688; // eax
  const wchar_t *v689; // r14
  const unsigned __int16 *v690; // rsi
  unsigned __int16 v691; // bx
  unsigned __int16 v692; // di
  wchar_t v693; // bx
  wchar_t v694; // cx
  const wchar_t *v695; // r14
  const unsigned __int16 *v696; // rsi
  unsigned __int16 v697; // bx
  unsigned __int16 v698; // di
  wchar_t v699; // bx
  wchar_t v700; // cx
  const wchar_t *v701; // r14
  const unsigned __int16 *v702; // rsi
  unsigned __int16 v703; // bx
  unsigned __int16 v704; // di
  wchar_t v705; // bx
  wchar_t v706; // cx
  const wchar_t *v707; // r14
  const unsigned __int16 *v708; // rsi
  unsigned __int16 v709; // bx
  unsigned __int16 v710; // di
  wchar_t v711; // bx
  wchar_t v712; // cx
  const wchar_t *v713; // r14
  const unsigned __int16 *v714; // rsi
  unsigned __int16 v715; // bx
  unsigned __int16 v716; // di
  wchar_t v717; // bx
  wchar_t v718; // cx
  const wchar_t *v719; // r14
  const unsigned __int16 *v720; // rsi
  unsigned __int16 v721; // bx
  unsigned __int16 v722; // di
  wchar_t v723; // bx
  wchar_t v724; // cx
  const wchar_t *v725; // r14
  const unsigned __int16 *v726; // rsi
  unsigned __int16 v727; // bx
  unsigned __int16 v728; // di
  wchar_t v729; // bx
  wchar_t v730; // cx
  const wchar_t *v731; // r14
  const unsigned __int16 *v732; // rsi
  unsigned __int16 v733; // bx
  unsigned __int16 v734; // di
  wchar_t v735; // bx
  wchar_t v736; // cx
  const wchar_t *v737; // r14
  const unsigned __int16 *v738; // rsi
  unsigned __int16 v739; // bx
  unsigned __int16 v740; // di
  wchar_t v741; // bx
  wchar_t v742; // cx
  const wchar_t *v743; // r14
  const unsigned __int16 *v744; // rsi
  unsigned __int16 v745; // bx
  unsigned __int16 v746; // di
  wchar_t v747; // bx
  wchar_t v748; // cx
  const wchar_t *v749; // r14
  const unsigned __int16 *v750; // rsi
  unsigned __int16 v751; // bx
  unsigned __int16 v752; // di
  wchar_t v753; // bx
  wchar_t v754; // cx
  const wchar_t *v755; // r14
  const unsigned __int16 *v756; // rsi
  unsigned __int16 v757; // bx
  unsigned __int16 v758; // di
  wchar_t v759; // bx
  wchar_t v760; // cx
  const wchar_t *v761; // r14
  const unsigned __int16 *v762; // rsi
  unsigned __int16 v763; // bx
  unsigned __int16 v764; // di
  wchar_t v765; // bx
  wchar_t v766; // cx
  const wchar_t *v767; // r14
  const unsigned __int16 *v768; // rsi
  unsigned __int16 v769; // bx
  unsigned __int16 v770; // di
  wchar_t v771; // bx
  wchar_t v772; // cx
  const wchar_t *v773; // r14
  const unsigned __int16 *v774; // rsi
  unsigned __int16 v775; // bx
  unsigned __int16 v776; // di
  wchar_t v777; // bx
  wchar_t v778; // cx
  const wchar_t *v779; // r14
  const unsigned __int16 *v780; // rsi
  unsigned __int16 v781; // bx
  unsigned __int16 v782; // di
  wchar_t v783; // bx
  wchar_t v784; // cx
  const wchar_t *v785; // r14
  const unsigned __int16 *j; // rsi
  unsigned __int16 v787; // bx
  unsigned __int16 v788; // di
  wchar_t v789; // bx
  wchar_t v790; // cx
  int v791; // eax
  const wchar_t *v792; // r14
  const unsigned __int16 *v793; // rsi
  unsigned __int16 v794; // bx
  unsigned __int16 v795; // di
  wchar_t v796; // bx
  wchar_t v797; // cx
  const wchar_t *v798; // rsi
  unsigned __int16 v799; // bx
  unsigned __int16 v800; // di
  wchar_t v801; // bx
  wchar_t v802; // cx
  _BYTE pExceptionObject[136]; // [rsp+20h] [rbp-88h] BYREF
  const void *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = L"MaxSentences";
  v5 = a2;
  v7 = a2;
  while ( 1 )
  {
    v8 = *v7;
    if ( (*v7 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v8) & 0x100000) == 0 )
        goto LABEL_4;
      v9 = ConvertCaseHighUnicode(v8, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v8) & 1) == 0
           || (v9 = v8 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v8 + 32)) & 2) == 0) )
    {
LABEL_4:
      v9 = v8;
    }
    v10 = *v4;
    if ( (*v4 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v10) & 0x100000) == 0 )
        goto LABEL_7;
      v11 = ConvertCaseHighUnicode(v10, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v10) & 1) == 0
           || (v11 = v10 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v10 + 32)) & 2) == 0) )
    {
LABEL_7:
      v11 = v10;
    }
    if ( v9 != v11 )
      break;
    ++v7;
    ++v4;
    if ( !v9 )
    {
LABEL_10:
      v12 = _variant_t::operator long(a3);
      if ( v12 < 1 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 3241213957LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      *((_DWORD *)this + 3) = v12;
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v13 = L"NLDP_SENTENCE_COUNT";
  v14 = v5;
  while ( 1 )
  {
    v15 = *v14;
    if ( (*v14 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v15) & 0x100000) == 0 )
        goto LABEL_23;
      v16 = ConvertCaseHighUnicode(v15, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v15) & 1) == 0
           || (v16 = v15 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v15 + 32)) & 2) == 0) )
    {
LABEL_23:
      v16 = v15;
    }
    v17 = *v13;
    if ( (*v13 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v17) & 0x100000) == 0 )
        goto LABEL_26;
      v18 = ConvertCaseHighUnicode(v17, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v17) & 1) == 0
           || (v18 = v17 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v17 + 32)) & 2) == 0) )
    {
LABEL_26:
      v18 = v17;
    }
    if ( v16 != v18 )
      break;
    ++v14;
    ++v13;
    if ( !v16 )
      goto LABEL_10;
  }
  v19 = L"NSents";
  v20 = v5;
  while ( 1 )
  {
    v21 = *v20;
    if ( (*v20 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v21) & 0x100000) == 0 )
        goto LABEL_41;
      v22 = ConvertCaseHighUnicode(v21, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v21) & 1) == 0
           || (v22 = v21 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v21 + 32)) & 2) == 0) )
    {
LABEL_41:
      v22 = v21;
    }
    v23 = *v19;
    if ( (*v19 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v23) & 0x100000) == 0 )
        goto LABEL_44;
      v24 = ConvertCaseHighUnicode(v23, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v23) & 1) == 0
           || (v24 = v23 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v23 + 32)) & 2) == 0) )
    {
LABEL_44:
      v24 = v23;
    }
    if ( v22 != v24 )
      break;
    ++v20;
    ++v19;
    if ( !v22 )
      goto LABEL_10;
  }
  v25 = L"IsSingleLanguage";
  v26 = v5;
  while ( 1 )
  {
    v27 = *v26;
    if ( (*v26 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v27) & 0x100000) == 0 )
        goto LABEL_59;
      v28 = ConvertCaseHighUnicode(v27, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v27) & 1) == 0
           || (v28 = v27 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v27 + 32)) & 2) == 0) )
    {
LABEL_59:
      v28 = v27;
    }
    v29 = *v25;
    if ( (*v25 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v29) & 0x100000) == 0 )
        goto LABEL_62;
      v30 = ConvertCaseHighUnicode(v29, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v29) & 1) == 0
           || (v30 = v29 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v29 + 32)) & 2) == 0) )
    {
LABEL_62:
      v30 = v29;
    }
    if ( v28 != v30 )
      break;
    ++v26;
    ++v25;
    if ( !v28 )
    {
LABEL_65:
      *((_BYTE *)this + 16) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v40 = L"SingleLanguage";
  v41 = v5;
  while ( 1 )
  {
    v42 = *v41;
    if ( (*v41 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v42) & 0x100000) == 0 )
        goto LABEL_97;
      v43 = ConvertCaseHighUnicode(v42, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v42) & 1) == 0
           || (v43 = v42 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v42 + 32)) & 2) == 0) )
    {
LABEL_97:
      v43 = v42;
    }
    v44 = *v40;
    if ( (*v40 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v44) & 0x100000) == 0 )
        goto LABEL_100;
      v45 = ConvertCaseHighUnicode(v44, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v44) & 1) == 0
           || (v45 = v44 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v44 + 32)) & 2) == 0) )
    {
LABEL_100:
      v45 = v44;
    }
    if ( v43 != v45 )
      break;
    ++v41;
    ++v40;
    if ( !v43 )
      goto LABEL_65;
  }
  v46 = L"IsSimpleWordBreaking";
  v47 = v5;
  while ( 1 )
  {
    v48 = *v47;
    if ( (*v47 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v48) & 0x100000) == 0 )
        goto LABEL_115;
      v49 = ConvertCaseHighUnicode(v48, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v48) & 1) == 0
           || (v49 = v48 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v48 + 32)) & 2) == 0) )
    {
LABEL_115:
      v49 = v48;
    }
    v50 = *v46;
    if ( (*v46 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v50) & 0x100000) == 0 )
        goto LABEL_118;
      v51 = ConvertCaseHighUnicode(v50, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v50) & 1) == 0
           || (v51 = v50 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v50 + 32)) & 2) == 0) )
    {
LABEL_118:
      v51 = v50;
    }
    if ( v49 != v51 )
      break;
    ++v47;
    ++v46;
    if ( !v49 )
    {
LABEL_121:
      *((_BYTE *)this + 17) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v52 = L"SimpleWordBreaking";
  v53 = v5;
  while ( 1 )
  {
    v54 = *v53;
    if ( (*v53 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v54) & 0x100000) == 0 )
        goto LABEL_133;
      v55 = ConvertCaseHighUnicode(v54, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v54) & 1) == 0
           || (v55 = v54 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v54 + 32)) & 2) == 0) )
    {
LABEL_133:
      v55 = v54;
    }
    v56 = *v52;
    if ( (*v52 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v56) & 0x100000) == 0 )
        goto LABEL_136;
      v57 = ConvertCaseHighUnicode(v56, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v56) & 1) == 0
           || (v57 = v56 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v56 + 32)) & 2) == 0) )
    {
LABEL_136:
      v57 = v56;
    }
    if ( v55 != v57 )
      break;
    ++v53;
    ++v52;
    if ( !v55 )
      goto LABEL_121;
  }
  v58 = L"UseRelativeTimes";
  v59 = v5;
  v60 = L"UseRelativeTimes";
  while ( 1 )
  {
    v61 = *v59;
    if ( (*v59 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v61) & 0x100000) == 0 )
        goto LABEL_151;
      v62 = ConvertCaseHighUnicode(v61, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v61) & 1) == 0
           || (v62 = v61 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v61 + 32)) & 2) == 0) )
    {
LABEL_151:
      v62 = v61;
    }
    v63 = *v60;
    if ( (*v60 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v63) & 0x100000) == 0 )
        goto LABEL_154;
      v64 = ConvertCaseHighUnicode(v63, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v63) & 1) == 0
           || (v64 = v63 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v63 + 32)) & 2) == 0) )
    {
LABEL_154:
      v64 = v63;
    }
    if ( v62 != v64 )
      break;
    ++v59;
    ++v60;
    if ( !v62 )
    {
LABEL_157:
      *((_BYTE *)this + 18) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v65 = v5;
  while ( 1 )
  {
    v66 = *v65;
    if ( (*v65 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v66) & 0x100000) == 0 )
        goto LABEL_169;
      v67 = ConvertCaseHighUnicode(v66, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v66) & 1) == 0
           || (v67 = v66 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v66 + 32)) & 2) == 0) )
    {
LABEL_169:
      v67 = v66;
    }
    v68 = *v58;
    if ( (*v58 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v68) & 0x100000) == 0 )
        goto LABEL_172;
      v69 = ConvertCaseHighUnicode(v68, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v68) & 1) == 0
           || (v69 = v68 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v68 + 32)) & 2) == 0) )
    {
LABEL_172:
      v69 = v68;
    }
    if ( v67 != v69 )
      break;
    ++v65;
    ++v58;
    if ( !v67 )
      goto LABEL_157;
  }
  v70 = L"IgnorePunctuation";
  v71 = v5;
  v72 = L"IgnorePunctuation";
  while ( 1 )
  {
    v73 = *v71;
    if ( (*v71 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v73) & 0x100000) == 0 )
        goto LABEL_187;
      v74 = ConvertCaseHighUnicode(v73, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v73) & 1) == 0
           || (v74 = v73 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v73 + 32)) & 2) == 0) )
    {
LABEL_187:
      v74 = v73;
    }
    v75 = *v72;
    if ( (*v72 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v75) & 0x100000) == 0 )
        goto LABEL_190;
      v76 = ConvertCaseHighUnicode(v75, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v75) & 1) == 0
           || (v76 = v75 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v75 + 32)) & 2) == 0) )
    {
LABEL_190:
      v76 = v75;
    }
    if ( v74 != v76 )
      break;
    ++v71;
    ++v72;
    if ( !v74 )
    {
LABEL_193:
      *((_BYTE *)this + 19) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v77 = v5;
  while ( 1 )
  {
    v78 = *v77;
    if ( (*v77 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v78) & 0x100000) == 0 )
        goto LABEL_205;
      v79 = ConvertCaseHighUnicode(v78, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v78) & 1) == 0
           || (v79 = v78 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v78 + 32)) & 2) == 0) )
    {
LABEL_205:
      v79 = v78;
    }
    v80 = *v70;
    if ( (*v70 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v80) & 0x100000) == 0 )
        goto LABEL_208;
      v81 = ConvertCaseHighUnicode(v80, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v80) & 1) == 0
           || (v81 = v80 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v80 + 32)) & 2) == 0) )
    {
LABEL_208:
      v81 = v80;
    }
    if ( v79 != v81 )
      break;
    ++v77;
    ++v70;
    if ( !v79 )
      goto LABEL_193;
  }
  v32 = L"IsCaching";
  v33 = v5;
  while ( 1 )
  {
    v34 = *v33;
    if ( (*v33 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v34) & 0x100000) == 0 )
        goto LABEL_77;
      v35 = ConvertCaseHighUnicode(v34, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v34) & 1) == 0
           || (v35 = v34 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v34 + 32)) & 2) == 0) )
    {
LABEL_77:
      v35 = v34;
    }
    v36 = *v32;
    if ( (*v32 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v36) & 0x100000) == 0 )
        goto LABEL_80;
      v37 = ConvertCaseHighUnicode(v36, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v36) & 1) == 0
           || (v37 = v36 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v36 + 32)) & 2) == 0) )
    {
LABEL_80:
      v37 = v36;
    }
    if ( v35 != v37 )
      break;
    ++v33;
    ++v32;
    if ( !v35 )
    {
LABEL_83:
      v38 = *(void (__fastcall **)(CContextBase *, _QWORD))(*(_QWORD *)this + 8LL);
LABEL_84:
      v39 = _variant_t::operator bool(a3);
      v38(this, v39);
      return 1;
    }
  }
  v82 = L"Caching";
  v83 = v5;
  while ( 1 )
  {
    v84 = *v83;
    if ( (*v83 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v84) & 0x100000) == 0 )
        goto LABEL_223;
      v85 = ConvertCaseHighUnicode(v84, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v84) & 1) == 0
           || (v85 = v84 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v84 + 32)) & 2) == 0) )
    {
LABEL_223:
      v85 = v84;
    }
    v86 = *v82;
    if ( (*v82 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v86) & 0x100000) == 0 )
        goto LABEL_226;
      v87 = ConvertCaseHighUnicode(v86, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v86) & 1) == 0
           || (v87 = v86 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v86 + 32)) & 2) == 0) )
    {
LABEL_226:
      v87 = v86;
    }
    if ( v85 != v87 )
      break;
    ++v83;
    ++v82;
    if ( !v85 )
      goto LABEL_83;
  }
  v88 = L"IsShowingGaps";
  v89 = v5;
  while ( 1 )
  {
    v90 = *v89;
    if ( (*v89 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v90) & 0x100000) == 0 )
        goto LABEL_241;
      v91 = ConvertCaseHighUnicode(v90, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v90) & 1) == 0
           || (v91 = v90 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v90 + 32)) & 2) == 0) )
    {
LABEL_241:
      v91 = v90;
    }
    v92 = *v88;
    if ( (*v88 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v92) & 0x100000) == 0 )
        goto LABEL_244;
      v93 = ConvertCaseHighUnicode(v92, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v92) & 1) == 0
           || (v93 = v92 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v92 + 32)) & 2) == 0) )
    {
LABEL_244:
      v93 = v92;
    }
    if ( v91 != v93 )
      break;
    ++v89;
    ++v88;
    if ( !v91 )
    {
LABEL_247:
      *((_BYTE *)this + 21) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v94 = L"ShowingGaps";
  v95 = v5;
  while ( 1 )
  {
    v96 = *v95;
    if ( (*v95 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v96) & 0x100000) == 0 )
        goto LABEL_259;
      v97 = ConvertCaseHighUnicode(v96, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v96) & 1) == 0
           || (v97 = v96 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v96 + 32)) & 2) == 0) )
    {
LABEL_259:
      v97 = v96;
    }
    v98 = *v94;
    if ( (*v94 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v98) & 0x100000) == 0 )
        goto LABEL_262;
      v99 = ConvertCaseHighUnicode(v98, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v98) & 1) == 0
           || (v99 = v98 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v98 + 32)) & 2) == 0) )
    {
LABEL_262:
      v99 = v98;
    }
    if ( v97 != v99 )
      break;
    ++v95;
    ++v94;
    if ( !v97 )
      goto LABEL_247;
  }
  v100 = L"Gaps";
  v101 = v5;
  while ( 1 )
  {
    v102 = *v101;
    if ( (*v101 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v102) & 0x100000) == 0 )
        goto LABEL_277;
      v103 = ConvertCaseHighUnicode(v102, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v102) & 1) == 0
           || (v103 = v102 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v102 + 32)) & 2) == 0) )
    {
LABEL_277:
      v103 = v102;
    }
    v104 = *v100;
    if ( (*v100 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v104) & 0x100000) == 0 )
        goto LABEL_280;
      v105 = ConvertCaseHighUnicode(v104, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v104) & 1) == 0
           || (v105 = v104 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v104 + 32)) & 2) == 0) )
    {
LABEL_280:
      v105 = v104;
    }
    if ( v103 != v105 )
      break;
    ++v101;
    ++v100;
    if ( !v103 )
      goto LABEL_247;
  }
  v106 = L"IsShowingCharacterNormalizations";
  v107 = v5;
  while ( 1 )
  {
    v108 = *v107;
    if ( (*v107 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v108) & 0x100000) == 0 )
        goto LABEL_295;
      v109 = ConvertCaseHighUnicode(v108, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v108) & 1) == 0
           || (v109 = v108 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v108 + 32)) & 2) == 0) )
    {
LABEL_295:
      v109 = v108;
    }
    v110 = *v106;
    if ( (*v106 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v110) & 0x100000) == 0 )
        goto LABEL_298;
      v111 = ConvertCaseHighUnicode(v110, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v110) & 1) == 0
           || (v111 = v110 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v110 + 32)) & 2) == 0) )
    {
LABEL_298:
      v111 = v110;
    }
    if ( v109 != v111 )
      break;
    ++v107;
    ++v106;
    if ( !v109 )
    {
LABEL_301:
      *((_BYTE *)this + 22) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v112 = L"ShowingCharacterNormalizations";
  v113 = v5;
  while ( 1 )
  {
    v114 = *v113;
    if ( (*v113 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v114) & 0x100000) == 0 )
        goto LABEL_313;
      v115 = ConvertCaseHighUnicode(v114, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v114) & 1) == 0
           || (v115 = v114 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v114 + 32)) & 2) == 0) )
    {
LABEL_313:
      v115 = v114;
    }
    v116 = *v112;
    if ( (*v112 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v116) & 0x100000) == 0 )
        goto LABEL_316;
      v117 = ConvertCaseHighUnicode(v116, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v116) & 1) == 0
           || (v117 = v116 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v116 + 32)) & 2) == 0) )
    {
LABEL_316:
      v117 = v116;
    }
    if ( v115 != v117 )
      break;
    ++v113;
    ++v112;
    if ( !v115 )
      goto LABEL_301;
  }
  v118 = L"CharacterNormalizations";
  v119 = v5;
  while ( 1 )
  {
    v120 = *v119;
    if ( (*v119 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v120) & 0x100000) == 0 )
        goto LABEL_331;
      v121 = ConvertCaseHighUnicode(v120, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v120) & 1) == 0
           || (v121 = v120 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v120 + 32)) & 2) == 0) )
    {
LABEL_331:
      v121 = v120;
    }
    v122 = *v118;
    if ( (*v118 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v122) & 0x100000) == 0 )
        goto LABEL_334;
      v123 = ConvertCaseHighUnicode(v122, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v122) & 1) == 0
           || (v123 = v122 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v122 + 32)) & 2) == 0) )
    {
LABEL_334:
      v123 = v122;
    }
    if ( v121 != v123 )
      break;
    ++v119;
    ++v118;
    if ( !v121 )
      goto LABEL_301;
  }
  v124 = L"IsShowingWordNormalizations";
  v125 = v5;
  while ( 1 )
  {
    v126 = *v125;
    if ( (*v125 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v126) & 0x100000) == 0 )
        goto LABEL_349;
      v127 = ConvertCaseHighUnicode(v126, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v126) & 1) == 0
           || (v127 = v126 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v126 + 32)) & 2) == 0) )
    {
LABEL_349:
      v127 = v126;
    }
    v128 = *v124;
    if ( (*v124 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v128) & 0x100000) == 0 )
        goto LABEL_352;
      v129 = ConvertCaseHighUnicode(v128, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v128) & 1) == 0
           || (v129 = v128 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v128 + 32)) & 2) == 0) )
    {
LABEL_352:
      v129 = v128;
    }
    if ( v127 != v129 )
      break;
    ++v125;
    ++v124;
    if ( !v127 )
    {
LABEL_355:
      *((_BYTE *)this + 23) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v130 = L"ShowingWordNormalizations";
  v131 = v5;
  while ( 1 )
  {
    v132 = *v131;
    if ( (*v131 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v132) & 0x100000) == 0 )
        goto LABEL_367;
      v133 = ConvertCaseHighUnicode(v132, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v132) & 1) == 0
           || (v133 = v132 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v132 + 32)) & 2) == 0) )
    {
LABEL_367:
      v133 = v132;
    }
    v134 = *v130;
    if ( (*v130 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v134) & 0x100000) == 0 )
        goto LABEL_370;
      v135 = ConvertCaseHighUnicode(v134, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v134) & 1) == 0
           || (v135 = v134 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v134 + 32)) & 2) == 0) )
    {
LABEL_370:
      v135 = v134;
    }
    if ( v133 != v135 )
      break;
    ++v131;
    ++v130;
    if ( !v133 )
      goto LABEL_355;
  }
  v136 = L"WordNormalizations";
  v137 = v5;
  while ( 1 )
  {
    v138 = *v137;
    if ( (*v137 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v138) & 0x100000) == 0 )
        goto LABEL_385;
      v139 = ConvertCaseHighUnicode(v138, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v138) & 1) == 0
           || (v139 = v138 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v138 + 32)) & 2) == 0) )
    {
LABEL_385:
      v139 = v138;
    }
    v140 = *v136;
    if ( (*v136 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v140) & 0x100000) == 0 )
        goto LABEL_388;
      v141 = ConvertCaseHighUnicode(v140, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v140) & 1) == 0
           || (v141 = v140 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v140 + 32)) & 2) == 0) )
    {
LABEL_388:
      v141 = v140;
    }
    if ( v139 != v141 )
      break;
    ++v137;
    ++v136;
    if ( !v139 )
      goto LABEL_355;
  }
  v142 = L"IsComputingCompounds";
  v143 = v5;
  while ( 1 )
  {
    v144 = *v143;
    if ( (*v143 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v144) & 0x100000) == 0 )
        goto LABEL_403;
      v145 = ConvertCaseHighUnicode(v144, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v144) & 1) == 0
           || (v145 = v144 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v144 + 32)) & 2) == 0) )
    {
LABEL_403:
      v145 = v144;
    }
    v146 = *v142;
    if ( (*v142 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v146) & 0x100000) == 0 )
        goto LABEL_406;
      v147 = ConvertCaseHighUnicode(v146, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v146) & 1) == 0
           || (v147 = v146 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v146 + 32)) & 2) == 0) )
    {
LABEL_406:
      v147 = v146;
    }
    if ( v145 != v147 )
      break;
    ++v143;
    ++v142;
    if ( !v145 )
    {
LABEL_409:
      *((_BYTE *)this + 24) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v148 = L"ComputingCompounds";
  v149 = v5;
  while ( 1 )
  {
    v150 = *v149;
    if ( (*v149 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v150) & 0x100000) == 0 )
        goto LABEL_421;
      v151 = ConvertCaseHighUnicode(v150, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v150) & 1) == 0
           || (v151 = v150 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v150 + 32)) & 2) == 0) )
    {
LABEL_421:
      v151 = v150;
    }
    v152 = *v148;
    if ( (*v148 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v152) & 0x100000) == 0 )
        goto LABEL_424;
      v153 = ConvertCaseHighUnicode(v152, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v152) & 1) == 0
           || (v153 = v152 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v152 + 32)) & 2) == 0) )
    {
LABEL_424:
      v153 = v152;
    }
    if ( v151 != v153 )
      break;
    ++v149;
    ++v148;
    if ( !v151 )
      goto LABEL_409;
  }
  v154 = L"Compounds";
  v155 = v5;
  while ( 1 )
  {
    v156 = *v155;
    if ( (*v155 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v156) & 0x100000) == 0 )
        goto LABEL_439;
      v157 = ConvertCaseHighUnicode(v156, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v156) & 1) == 0
           || (v157 = v156 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v156 + 32)) & 2) == 0) )
    {
LABEL_439:
      v157 = v156;
    }
    v158 = *v154;
    if ( (*v154 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v158) & 0x100000) == 0 )
        goto LABEL_442;
      v159 = ConvertCaseHighUnicode(v158, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v158) & 1) == 0
           || (v159 = v158 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v158 + 32)) & 2) == 0) )
    {
LABEL_442:
      v159 = v158;
    }
    if ( v157 != v159 )
      break;
    ++v155;
    ++v154;
    if ( !v157 )
      goto LABEL_409;
  }
  v160 = L"IsComputingInflections";
  v161 = v5;
  while ( 1 )
  {
    v162 = *v161;
    if ( (*v161 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v162) & 0x100000) == 0 )
        goto LABEL_457;
      v163 = ConvertCaseHighUnicode(v162, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v162) & 1) == 0
           || (v163 = v162 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v162 + 32)) & 2) == 0) )
    {
LABEL_457:
      v163 = v162;
    }
    v164 = *v160;
    if ( (*v160 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v164) & 0x100000) == 0 )
        goto LABEL_460;
      v165 = ConvertCaseHighUnicode(v164, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v164) & 1) == 0
           || (v165 = v164 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v164 + 32)) & 2) == 0) )
    {
LABEL_460:
      v165 = v164;
    }
    if ( v163 != v165 )
      break;
    ++v161;
    ++v160;
    if ( !v163 )
    {
LABEL_463:
      *((_BYTE *)this + 25) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v166 = L"ComputingInflections";
  v167 = v5;
  while ( 1 )
  {
    v168 = *v167;
    if ( (*v167 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v168) & 0x100000) == 0 )
        goto LABEL_475;
      v169 = ConvertCaseHighUnicode(v168, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v168) & 1) == 0
           || (v169 = v168 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v168 + 32)) & 2) == 0) )
    {
LABEL_475:
      v169 = v168;
    }
    v170 = *v166;
    if ( (*v166 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v170) & 0x100000) == 0 )
        goto LABEL_478;
      v171 = ConvertCaseHighUnicode(v170, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v170) & 1) == 0
           || (v171 = v170 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v170 + 32)) & 2) == 0) )
    {
LABEL_478:
      v171 = v170;
    }
    if ( v169 != v171 )
      break;
    ++v167;
    ++v166;
    if ( !v169 )
      goto LABEL_463;
  }
  v172 = L"Inflections";
  v173 = v5;
  while ( 1 )
  {
    v174 = *v173;
    if ( (*v173 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v174) & 0x100000) == 0 )
        goto LABEL_493;
      v175 = ConvertCaseHighUnicode(v174, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v174) & 1) == 0
           || (v175 = v174 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v174 + 32)) & 2) == 0) )
    {
LABEL_493:
      v175 = v174;
    }
    v176 = *v172;
    if ( (*v172 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v176) & 0x100000) == 0 )
        goto LABEL_496;
      v177 = ConvertCaseHighUnicode(v176, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v176) & 1) == 0
           || (v177 = v176 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v176 + 32)) & 2) == 0) )
    {
LABEL_496:
      v177 = v176;
    }
    if ( v175 != v177 )
      break;
    ++v173;
    ++v172;
    if ( !v175 )
      goto LABEL_463;
  }
  v178 = L"NLDP_SECTION_INFL_MORPH";
  v179 = v5;
  while ( 1 )
  {
    v180 = *v179;
    if ( (*v179 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v180) & 0x100000) == 0 )
        goto LABEL_511;
      v181 = ConvertCaseHighUnicode(v180, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v180) & 1) == 0
           || (v181 = v180 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v180 + 32)) & 2) == 0) )
    {
LABEL_511:
      v181 = v180;
    }
    v182 = *v178;
    if ( (*v178 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v182) & 0x100000) == 0 )
        goto LABEL_514;
      v183 = ConvertCaseHighUnicode(v182, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v182) & 1) == 0
           || (v183 = v182 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v182 + 32)) & 2) == 0) )
    {
LABEL_514:
      v183 = v182;
    }
    if ( v181 != v183 )
      break;
    ++v179;
    ++v178;
    if ( !v181 )
      goto LABEL_463;
  }
  v184 = L"InflForms";
  v185 = v5;
  while ( 1 )
  {
    v186 = *v185;
    if ( (*v185 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v186) & 0x100000) == 0 )
        goto LABEL_529;
      v187 = ConvertCaseHighUnicode(v186, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v186) & 1) == 0
           || (v187 = v186 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v186 + 32)) & 2) == 0) )
    {
LABEL_529:
      v187 = v186;
    }
    v188 = *v184;
    if ( (*v184 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v188) & 0x100000) == 0 )
        goto LABEL_532;
      v189 = ConvertCaseHighUnicode(v188, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v188) & 1) == 0
           || (v189 = v188 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v188 + 32)) & 2) == 0) )
    {
LABEL_532:
      v189 = v188;
    }
    if ( v187 != v189 )
      break;
    ++v185;
    ++v184;
    if ( !v187 )
      goto LABEL_463;
  }
  v190 = L"IsComputingLemmas";
  v191 = v5;
  while ( 1 )
  {
    v192 = *v191;
    if ( (*v191 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v192) & 0x100000) == 0 )
        goto LABEL_547;
      v193 = ConvertCaseHighUnicode(v192, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v192) & 1) == 0
           || (v193 = v192 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v192 + 32)) & 2) == 0) )
    {
LABEL_547:
      v193 = v192;
    }
    v194 = *v190;
    if ( (*v190 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v194) & 0x100000) == 0 )
        goto LABEL_550;
      v195 = ConvertCaseHighUnicode(v194, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v194) & 1) == 0
           || (v195 = v194 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v194 + 32)) & 2) == 0) )
    {
LABEL_550:
      v195 = v194;
    }
    if ( v193 != v195 )
      break;
    ++v191;
    ++v190;
    if ( !v193 )
    {
LABEL_553:
      *((_BYTE *)this + 26) = _variant_t::operator bool(a3);
      result = 1;
      ++*((_DWORD *)this + 2);
      return result;
    }
  }
  v196 = L"ComputingLemmas";
  v197 = v5;
  while ( 1 )
  {
    v198 = *v197;
    if ( (*v197 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v198) & 0x100000) == 0 )
        goto LABEL_565;
      v199 = ConvertCaseHighUnicode(v198, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v198) & 1) == 0
           || (v199 = v198 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v198 + 32)) & 2) == 0) )
    {
LABEL_565:
      v199 = v198;
    }
    v200 = *v196;
    if ( (*v196 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v200) & 0x100000) == 0 )
        goto LABEL_568;
      v201 = ConvertCaseHighUnicode(v200, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v200) & 1) == 0
           || (v201 = v200 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v200 + 32)) & 2) == 0) )
    {
LABEL_568:
      v201 = v200;
    }
    if ( v199 != v201 )
      break;
    ++v197;
    ++v196;
    if ( !v199 )
      goto LABEL_553;
  }
  v202 = L"Lemmas";
  v203 = v5;
  while ( 1 )
  {
    v204 = *v203;
    if ( (*v203 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v204) & 0x100000) == 0 )
        goto LABEL_583;
      v205 = ConvertCaseHighUnicode(v204, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v204) & 1) == 0
           || (v205 = v204 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v204 + 32)) & 2) == 0) )
    {
LABEL_583:
      v205 = v204;
    }
    v206 = *v202;
    if ( (*v202 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v206) & 0x100000) == 0 )
        goto LABEL_586;
      v207 = ConvertCaseHighUnicode(v206, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v206) & 1) == 0
           || (v207 = v206 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v206 + 32)) & 2) == 0) )
    {
LABEL_586:
      v207 = v206;
    }
    if ( v205 != v207 )
      break;
    ++v203;
    ++v202;
    if ( !v205 )
      goto LABEL_553;
  }
  v208 = L"SectionLemmas";
  v209 = v5;
  while ( 1 )
  {
    v210 = *v209;
    if ( (*v209 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v210) & 0x100000) == 0 )
        goto LABEL_601;
      v211 = ConvertCaseHighUnicode(v210, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v210) & 1) == 0
           || (v211 = v210 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v210 + 32)) & 2) == 0) )
    {
LABEL_601:
      v211 = v210;
    }
    v212 = *v208;
    if ( (*v208 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v212) & 0x100000) == 0 )
        goto LABEL_604;
      v213 = ConvertCaseHighUnicode(v212, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v212) & 1) == 0
           || (v213 = v212 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v212 + 32)) & 2) == 0) )
    {
LABEL_604:
      v213 = v212;
    }
    if ( v211 != v213 )
      break;
    ++v209;
    ++v208;
    if ( !v211 )
      goto LABEL_553;
  }
  v214 = L"IsComputingExpansions";
  v215 = v5;
  while ( 1 )
  {
    v216 = *v215;
    if ( (*v215 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v216) & 0x100000) == 0 )
        goto LABEL_619;
      v217 = ConvertCaseHighUnicode(v216, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v216) & 1) == 0
           || (v217 = v216 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v216 + 32)) & 2) == 0) )
    {
LABEL_619:
      v217 = v216;
    }
    v218 = *v214;
    if ( (*v214 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v218) & 0x100000) == 0 )
        goto LABEL_622;
      v219 = ConvertCaseHighUnicode(v218, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v218) & 1) == 0
           || (v219 = v218 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v218 + 32)) & 2) == 0) )
    {
LABEL_622:
      v219 = v218;
    }
    if ( v217 != v219 )
      break;
    ++v215;
    ++v214;
    if ( !v217 )
    {
LABEL_625:
      v38 = *(void (__fastcall **)(CContextBase *, _QWORD))(*(_QWORD *)this + 16LL);
      goto LABEL_84;
    }
  }
  v220 = L"ComputingExpansions";
  v221 = v5;
  while ( 1 )
  {
    v222 = *v221;
    if ( (*v221 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v222) & 0x100000) == 0 )
        goto LABEL_637;
      v223 = ConvertCaseHighUnicode(v222, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v222) & 1) == 0
           || (v223 = v222 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v222 + 32)) & 2) == 0) )
    {
LABEL_637:
      v223 = v222;
    }
    v224 = *v220;
    if ( (*v220 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v224) & 0x100000) == 0 )
        goto LABEL_640;
      v225 = ConvertCaseHighUnicode(v224, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v224) & 1) == 0
           || (v225 = v224 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v224 + 32)) & 2) == 0) )
    {
LABEL_640:
      v225 = v224;
    }
    if ( v223 != v225 )
      break;
    ++v221;
    ++v220;
    if ( !v223 )
    {
      v38 = *(void (__fastcall **)(CContextBase *, _QWORD))(*(_QWORD *)this + 16LL);
      goto LABEL_84;
    }
  }
  v226 = L"Expansions";
  v227 = v5;
  while ( 1 )
  {
    v228 = *v227;
    if ( (*v227 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v228) & 0x100000) == 0 )
        goto LABEL_655;
      v229 = ConvertCaseHighUnicode(v228, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v228) & 1) == 0
           || (v229 = v228 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v228 + 32)) & 2) == 0) )
    {
LABEL_655:
      v229 = v228;
    }
    v230 = *v226;
    if ( (*v226 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v230) & 0x100000) == 0 )
        goto LABEL_658;
      v231 = ConvertCaseHighUnicode(v230, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v230) & 1) == 0
           || (v231 = v230 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v230 + 32)) & 2) == 0) )
    {
LABEL_658:
      v231 = v230;
    }
    if ( v229 != v231 )
      break;
    ++v227;
    ++v226;
    if ( !v229 )
      goto LABEL_625;
  }
  v232 = L"IsComputingBases";
  v233 = v5;
  while ( 1 )
  {
    v234 = *v233;
    if ( (*v233 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v234) & 0x100000) == 0 )
        goto LABEL_673;
      v235 = ConvertCaseHighUnicode(v234, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v234) & 1) == 0
           || (v235 = v234 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v234 + 32)) & 2) == 0) )
    {
LABEL_673:
      v235 = v234;
    }
    v236 = *v232;
    if ( (*v232 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v236) & 0x100000) == 0 )
        goto LABEL_676;
      v237 = ConvertCaseHighUnicode(v236, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v236) & 1) == 0
           || (v237 = v236 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v236 + 32)) & 2) == 0) )
    {
LABEL_676:
      v237 = v236;
    }
    if ( v235 != v237 )
      break;
    ++v233;
    ++v232;
    if ( !v235 )
    {
LABEL_679:
      v38 = *(void (__fastcall **)(CContextBase *, _QWORD))(*(_QWORD *)this + 24LL);
      goto LABEL_84;
    }
  }
  v238 = L"ComputingBases";
  v239 = v5;
  while ( 1 )
  {
    v240 = *v239;
    if ( (*v239 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v240) & 0x100000) == 0 )
        goto LABEL_691;
      v241 = ConvertCaseHighUnicode(v240, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v240) & 1) == 0
           || (v241 = v240 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v240 + 32)) & 2) == 0) )
    {
LABEL_691:
      v241 = v240;
    }
    v242 = *v238;
    if ( (*v238 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v242) & 0x100000) == 0 )
        goto LABEL_694;
      v243 = ConvertCaseHighUnicode(v242, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v242) & 1) == 0
           || (v243 = v242 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v242 + 32)) & 2) == 0) )
    {
LABEL_694:
      v243 = v242;
    }
    if ( v241 != v243 )
      break;
    ++v239;
    ++v238;
    if ( !v241 )
    {
      v38 = *(void (__fastcall **)(CContextBase *, _QWORD))(*(_QWORD *)this + 24LL);
      goto LABEL_84;
    }
  }
  v244 = L"Bases";
  v245 = v5;
  while ( 1 )
  {
    v246 = *v245;
    if ( (*v245 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v246) & 0x100000) == 0 )
        goto LABEL_709;
      v247 = ConvertCaseHighUnicode(v246, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v246) & 1) == 0
           || (v247 = v246 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v246 + 32)) & 2) == 0) )
    {
LABEL_709:
      v247 = v246;
    }
    v248 = *v244;
    if ( (*v244 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v248) & 0x100000) == 0 )
        goto LABEL_712;
      v249 = ConvertCaseHighUnicode(v248, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v248) & 1) == 0
           || (v249 = v248 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v248 + 32)) & 2) == 0) )
    {
LABEL_712:
      v249 = v248;
    }
    if ( v247 != v249 )
      break;
    ++v245;
    ++v244;
    if ( !v247 )
      goto LABEL_679;
  }
  v250 = L"IsComputingPartOfSpeechTags";
  v251 = v5;
  while ( 1 )
  {
    v252 = *v251;
    if ( (*v251 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v252) & 0x100000) == 0 )
        goto LABEL_727;
      v253 = ConvertCaseHighUnicode(v252, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v252) & 1) == 0
           || (v253 = v252 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v252 + 32)) & 2) == 0) )
    {
LABEL_727:
      v253 = v252;
    }
    v254 = *v250;
    if ( (*v250 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v254) & 0x100000) == 0 )
        goto LABEL_730;
      v255 = ConvertCaseHighUnicode(v254, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v254) & 1) == 0
           || (v255 = v254 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v254 + 32)) & 2) == 0) )
    {
LABEL_730:
      v255 = v254;
    }
    if ( v253 != v255 )
      break;
    ++v251;
    ++v250;
    if ( !v253 )
    {
LABEL_733:
      *((_BYTE *)this + 29) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v256 = L"ComputingPartOfSpeechTags";
  v257 = v5;
  while ( 1 )
  {
    v258 = *v257;
    if ( (*v257 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v258) & 0x100000) == 0 )
        goto LABEL_745;
      v259 = ConvertCaseHighUnicode(v258, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v258) & 1) == 0
           || (v259 = v258 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v258 + 32)) & 2) == 0) )
    {
LABEL_745:
      v259 = v258;
    }
    v260 = *v256;
    if ( (*v256 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v260) & 0x100000) == 0 )
        goto LABEL_748;
      v261 = ConvertCaseHighUnicode(v260, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v260) & 1) == 0
           || (v261 = v260 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v260 + 32)) & 2) == 0) )
    {
LABEL_748:
      v261 = v260;
    }
    if ( v259 != v261 )
      break;
    ++v257;
    ++v256;
    if ( !v259 )
      goto LABEL_733;
  }
  v262 = L"PartOfSpeechTags";
  v263 = v5;
  while ( 1 )
  {
    v264 = *v263;
    if ( (*v263 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v264) & 0x100000) == 0 )
        goto LABEL_763;
      v265 = ConvertCaseHighUnicode(v264, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v264) & 1) == 0
           || (v265 = v264 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v264 + 32)) & 2) == 0) )
    {
LABEL_763:
      v265 = v264;
    }
    v266 = *v262;
    if ( (*v262 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v266) & 0x100000) == 0 )
        goto LABEL_766;
      v267 = ConvertCaseHighUnicode(v266, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v266) & 1) == 0
           || (v267 = v266 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v266 + 32)) & 2) == 0) )
    {
LABEL_766:
      v267 = v266;
    }
    if ( v265 != v267 )
      break;
    ++v263;
    ++v262;
    if ( !v265 )
      goto LABEL_733;
  }
  v268 = L"PosTags";
  v269 = v5;
  while ( 1 )
  {
    v270 = *v269;
    if ( (*v269 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v270) & 0x100000) == 0 )
        goto LABEL_781;
      v271 = ConvertCaseHighUnicode(v270, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v270) & 1) == 0
           || (v271 = v270 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v270 + 32)) & 2) == 0) )
    {
LABEL_781:
      v271 = v270;
    }
    v272 = *v268;
    if ( (*v268 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v272) & 0x100000) == 0 )
        goto LABEL_784;
      v273 = ConvertCaseHighUnicode(v272, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v272) & 1) == 0
           || (v273 = v272 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v272 + 32)) & 2) == 0) )
    {
LABEL_784:
      v273 = v272;
    }
    if ( v271 != v273 )
      break;
    ++v269;
    ++v268;
    if ( !v271 )
      goto LABEL_733;
  }
  v274 = L"IsFindingDefinitions";
  v275 = v5;
  while ( 1 )
  {
    v276 = *v275;
    if ( (*v275 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v276) & 0x100000) == 0 )
        goto LABEL_799;
      v277 = ConvertCaseHighUnicode(v276, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v276) & 1) == 0
           || (v277 = v276 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v276 + 32)) & 2) == 0) )
    {
LABEL_799:
      v277 = v276;
    }
    v278 = *v274;
    if ( (*v274 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v278) & 0x100000) == 0 )
        goto LABEL_802;
      v279 = ConvertCaseHighUnicode(v278, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v278) & 1) == 0
           || (v279 = v278 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v278 + 32)) & 2) == 0) )
    {
LABEL_802:
      v279 = v278;
    }
    if ( v277 != v279 )
      break;
    ++v275;
    ++v274;
    if ( !v277 )
    {
LABEL_805:
      *((_BYTE *)this + 30) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v280 = L"FindingDefinitions";
  v281 = v5;
  while ( 1 )
  {
    v282 = *v281;
    if ( (*v281 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v282) & 0x100000) == 0 )
        goto LABEL_817;
      v283 = ConvertCaseHighUnicode(v282, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v282) & 1) == 0
           || (v283 = v282 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v282 + 32)) & 2) == 0) )
    {
LABEL_817:
      v283 = v282;
    }
    v284 = *v280;
    if ( (*v280 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v284) & 0x100000) == 0 )
        goto LABEL_820;
      v285 = ConvertCaseHighUnicode(v284, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v284) & 1) == 0
           || (v285 = v284 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v284 + 32)) & 2) == 0) )
    {
LABEL_820:
      v285 = v284;
    }
    if ( v283 != v285 )
      break;
    ++v281;
    ++v280;
    if ( !v283 )
      goto LABEL_805;
  }
  v286 = L"Definitions";
  v287 = v5;
  while ( 1 )
  {
    v288 = *v287;
    if ( (*v287 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v288) & 0x100000) == 0 )
        goto LABEL_835;
      v289 = ConvertCaseHighUnicode(v288, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v288) & 1) == 0
           || (v289 = v288 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v288 + 32)) & 2) == 0) )
    {
LABEL_835:
      v289 = v288;
    }
    v290 = *v286;
    if ( (*v286 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v290) & 0x100000) == 0 )
        goto LABEL_838;
      v291 = ConvertCaseHighUnicode(v290, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v290) & 1) == 0
           || (v291 = v290 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v290 + 32)) & 2) == 0) )
    {
LABEL_838:
      v291 = v290;
    }
    if ( v289 != v291 )
      break;
    ++v287;
    ++v286;
    if ( !v289 )
      goto LABEL_805;
  }
  v292 = L"IsFindingDateTimeMeasures";
  v293 = v5;
  while ( 1 )
  {
    v294 = *v293;
    if ( (*v293 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v294) & 0x100000) == 0 )
        goto LABEL_853;
      v295 = ConvertCaseHighUnicode(v294, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v294) & 1) == 0
           || (v295 = v294 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v294 + 32)) & 2) == 0) )
    {
LABEL_853:
      v295 = v294;
    }
    v296 = *v292;
    if ( (*v292 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v296) & 0x100000) == 0 )
        goto LABEL_856;
      v297 = ConvertCaseHighUnicode(v296, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v296) & 1) == 0
           || (v297 = v296 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v296 + 32)) & 2) == 0) )
    {
LABEL_856:
      v297 = v296;
    }
    if ( v295 != v297 )
      break;
    ++v293;
    ++v292;
    if ( !v295 )
    {
LABEL_859:
      *((_BYTE *)this + 31) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v298 = L"FindingDateTimeMeasures";
  v299 = v5;
  while ( 1 )
  {
    v300 = *v299;
    if ( (*v299 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v300) & 0x100000) == 0 )
        goto LABEL_871;
      v301 = ConvertCaseHighUnicode(v300, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v300) & 1) == 0
           || (v301 = v300 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v300 + 32)) & 2) == 0) )
    {
LABEL_871:
      v301 = v300;
    }
    v302 = *v298;
    if ( (*v298 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v302) & 0x100000) == 0 )
        goto LABEL_874;
      v303 = ConvertCaseHighUnicode(v302, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v302) & 1) == 0
           || (v303 = v302 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v302 + 32)) & 2) == 0) )
    {
LABEL_874:
      v303 = v302;
    }
    if ( v301 != v303 )
      break;
    ++v299;
    ++v298;
    if ( !v301 )
      goto LABEL_859;
  }
  v304 = L"DateTimeMeasures";
  v305 = v5;
  while ( 1 )
  {
    v306 = *v305;
    if ( (*v305 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v306) & 0x100000) == 0 )
        goto LABEL_889;
      v307 = ConvertCaseHighUnicode(v306, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v306) & 1) == 0
           || (v307 = v306 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v306 + 32)) & 2) == 0) )
    {
LABEL_889:
      v307 = v306;
    }
    v308 = *v304;
    if ( (*v304 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v308) & 0x100000) == 0 )
        goto LABEL_892;
      v309 = ConvertCaseHighUnicode(v308, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v308) & 1) == 0
           || (v309 = v308 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v308 + 32)) & 2) == 0) )
    {
LABEL_892:
      v309 = v308;
    }
    if ( v307 != v309 )
      break;
    ++v305;
    ++v304;
    if ( !v307 )
      goto LABEL_859;
  }
  v310 = L"IsFindingPersons";
  v311 = v5;
  while ( 1 )
  {
    v312 = *v311;
    if ( (*v311 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v312) & 0x100000) == 0 )
        goto LABEL_907;
      v313 = ConvertCaseHighUnicode(v312, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v312) & 1) == 0
           || (v313 = v312 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v312 + 32)) & 2) == 0) )
    {
LABEL_907:
      v313 = v312;
    }
    v314 = *v310;
    if ( (*v310 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v314) & 0x100000) == 0 )
        goto LABEL_910;
      v315 = ConvertCaseHighUnicode(v314, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v314) & 1) == 0
           || (v315 = v314 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v314 + 32)) & 2) == 0) )
    {
LABEL_910:
      v315 = v314;
    }
    if ( v313 != v315 )
      break;
    ++v311;
    ++v310;
    if ( !v313 )
    {
LABEL_913:
      *((_BYTE *)this + 32) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v316 = L"FindingPersons";
  v317 = v5;
  while ( 1 )
  {
    v318 = *v317;
    if ( (*v317 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v318) & 0x100000) == 0 )
        goto LABEL_925;
      v319 = ConvertCaseHighUnicode(v318, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v318) & 1) == 0
           || (v319 = v318 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v318 + 32)) & 2) == 0) )
    {
LABEL_925:
      v319 = v318;
    }
    v320 = *v316;
    if ( (*v316 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v320) & 0x100000) == 0 )
        goto LABEL_928;
      v321 = ConvertCaseHighUnicode(v320, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v320) & 1) == 0
           || (v321 = v320 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v320 + 32)) & 2) == 0) )
    {
LABEL_928:
      v321 = v320;
    }
    if ( v319 != v321 )
      break;
    ++v317;
    ++v316;
    if ( !v319 )
      goto LABEL_913;
  }
  v322 = L"Persons";
  v323 = v5;
  while ( 1 )
  {
    v324 = *v323;
    if ( (*v323 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v324) & 0x100000) == 0 )
        goto LABEL_943;
      v325 = ConvertCaseHighUnicode(v324, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v324) & 1) == 0
           || (v325 = v324 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v324 + 32)) & 2) == 0) )
    {
LABEL_943:
      v325 = v324;
    }
    v326 = *v322;
    if ( (*v322 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v326) & 0x100000) == 0 )
        goto LABEL_946;
      v327 = ConvertCaseHighUnicode(v326, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v326) & 1) == 0
           || (v327 = v326 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v326 + 32)) & 2) == 0) )
    {
LABEL_946:
      v327 = v326;
    }
    if ( v325 != v327 )
      break;
    ++v323;
    ++v322;
    if ( !v325 )
      goto LABEL_913;
  }
  v328 = L"IsFindingLocations";
  v329 = v5;
  while ( 1 )
  {
    v330 = *v329;
    if ( (*v329 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v330) & 0x100000) == 0 )
        goto LABEL_961;
      v331 = ConvertCaseHighUnicode(v330, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v330) & 1) == 0
           || (v331 = v330 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v330 + 32)) & 2) == 0) )
    {
LABEL_961:
      v331 = v330;
    }
    v332 = *v328;
    if ( (*v328 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v332) & 0x100000) == 0 )
        goto LABEL_964;
      v333 = ConvertCaseHighUnicode(v332, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v332) & 1) == 0
           || (v333 = v332 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v332 + 32)) & 2) == 0) )
    {
LABEL_964:
      v333 = v332;
    }
    if ( v331 != v333 )
      break;
    ++v329;
    ++v328;
    if ( !v331 )
    {
LABEL_967:
      *((_BYTE *)this + 33) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v334 = L"FindingLocations";
  v335 = v5;
  while ( 1 )
  {
    v336 = *v335;
    if ( (*v335 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v336) & 0x100000) == 0 )
        goto LABEL_979;
      v337 = ConvertCaseHighUnicode(v336, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v336) & 1) == 0
           || (v337 = v336 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v336 + 32)) & 2) == 0) )
    {
LABEL_979:
      v337 = v336;
    }
    v338 = *v334;
    if ( (*v334 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v338) & 0x100000) == 0 )
        goto LABEL_982;
      v339 = ConvertCaseHighUnicode(v338, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v338) & 1) == 0
           || (v339 = v338 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v338 + 32)) & 2) == 0) )
    {
LABEL_982:
      v339 = v338;
    }
    if ( v337 != v339 )
      break;
    ++v335;
    ++v334;
    if ( !v337 )
      goto LABEL_967;
  }
  v340 = L"Locations";
  v341 = v5;
  while ( 1 )
  {
    v342 = *v341;
    if ( (*v341 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v342) & 0x100000) == 0 )
        goto LABEL_997;
      v343 = ConvertCaseHighUnicode(v342, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v342) & 1) == 0
           || (v343 = v342 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v342 + 32)) & 2) == 0) )
    {
LABEL_997:
      v343 = v342;
    }
    v344 = *v340;
    if ( (*v340 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v344) & 0x100000) == 0 )
        goto LABEL_1000;
      v345 = ConvertCaseHighUnicode(v344, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v344) & 1) == 0
           || (v345 = v344 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v344 + 32)) & 2) == 0) )
    {
LABEL_1000:
      v345 = v344;
    }
    if ( v343 != v345 )
      break;
    ++v341;
    ++v340;
    if ( !v343 )
      goto LABEL_967;
  }
  v346 = L"IsFindingOrganizations";
  v347 = v5;
  while ( 1 )
  {
    v348 = *v347;
    if ( (*v347 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v348) & 0x100000) == 0 )
        goto LABEL_1015;
      v349 = ConvertCaseHighUnicode(v348, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v348) & 1) == 0
           || (v349 = v348 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v348 + 32)) & 2) == 0) )
    {
LABEL_1015:
      v349 = v348;
    }
    v350 = *v346;
    if ( (*v346 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v350) & 0x100000) == 0 )
        goto LABEL_1018;
      v351 = ConvertCaseHighUnicode(v350, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v350) & 1) == 0
           || (v351 = v350 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v350 + 32)) & 2) == 0) )
    {
LABEL_1018:
      v351 = v350;
    }
    if ( v349 != v351 )
      break;
    ++v347;
    ++v346;
    if ( !v349 )
    {
LABEL_1021:
      *((_BYTE *)this + 34) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v352 = L"FindingOrganizations";
  v353 = v5;
  while ( 1 )
  {
    v354 = *v353;
    if ( (*v353 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v354) & 0x100000) == 0 )
        goto LABEL_1033;
      v355 = ConvertCaseHighUnicode(v354, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v354) & 1) == 0
           || (v355 = v354 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v354 + 32)) & 2) == 0) )
    {
LABEL_1033:
      v355 = v354;
    }
    v356 = *v352;
    if ( (*v352 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v356) & 0x100000) == 0 )
        goto LABEL_1036;
      v357 = ConvertCaseHighUnicode(v356, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v356) & 1) == 0
           || (v357 = v356 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v356 + 32)) & 2) == 0) )
    {
LABEL_1036:
      v357 = v356;
    }
    if ( v355 != v357 )
      break;
    ++v353;
    ++v352;
    if ( !v355 )
      goto LABEL_1021;
  }
  v358 = L"Organizations";
  v359 = v5;
  while ( 1 )
  {
    v360 = *v359;
    if ( (*v359 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v360) & 0x100000) == 0 )
        goto LABEL_1051;
      v361 = ConvertCaseHighUnicode(v360, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v360) & 1) == 0
           || (v361 = v360 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v360 + 32)) & 2) == 0) )
    {
LABEL_1051:
      v361 = v360;
    }
    v362 = *v358;
    if ( (*v358 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v362) & 0x100000) == 0 )
        goto LABEL_1054;
      v363 = ConvertCaseHighUnicode(v362, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v362) & 1) == 0
           || (v363 = v362 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v362 + 32)) & 2) == 0) )
    {
LABEL_1054:
      v363 = v362;
    }
    if ( v361 != v363 )
      break;
    ++v359;
    ++v358;
    if ( !v361 )
      goto LABEL_1021;
  }
  v364 = L"IsFindingPhrases";
  v365 = v5;
  while ( 1 )
  {
    v366 = *v365;
    if ( (*v365 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v366) & 0x100000) == 0 )
        goto LABEL_1069;
      v367 = ConvertCaseHighUnicode(v366, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v366) & 1) == 0
           || (v367 = v366 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v366 + 32)) & 2) == 0) )
    {
LABEL_1069:
      v367 = v366;
    }
    v368 = *v364;
    if ( (*v364 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v368) & 0x100000) == 0 )
        goto LABEL_1072;
      v369 = ConvertCaseHighUnicode(v368, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v368) & 1) == 0
           || (v369 = v368 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v368 + 32)) & 2) == 0) )
    {
LABEL_1072:
      v369 = v368;
    }
    if ( v367 != v369 )
      break;
    ++v365;
    ++v364;
    if ( !v367 )
    {
LABEL_1075:
      *((_BYTE *)this + 35) = _variant_t::operator bool(a3);
      ++*((_DWORD *)this + 2);
      return 1;
    }
  }
  v370 = L"FindingPhrases";
  v371 = v5;
  while ( 1 )
  {
    v372 = *v371;
    if ( (*v371 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v372) & 0x100000) == 0 )
        goto LABEL_1087;
      v373 = ConvertCaseHighUnicode(v372, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v372) & 1) == 0
           || (v373 = v372 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v372 + 32)) & 2) == 0) )
    {
LABEL_1087:
      v373 = v372;
    }
    v374 = *v370;
    if ( (*v370 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v374) & 0x100000) == 0 )
        goto LABEL_1090;
      v375 = ConvertCaseHighUnicode(v374, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v374) & 1) == 0
           || (v375 = v374 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v374 + 32)) & 2) == 0) )
    {
LABEL_1090:
      v375 = v374;
    }
    if ( v373 != v375 )
      break;
    ++v371;
    ++v370;
    if ( !v373 )
      goto LABEL_1075;
  }
  v376 = L"Phrases";
  v377 = v5;
  while ( 1 )
  {
    v378 = *v377;
    if ( (*v377 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v378) & 0x100000) == 0 )
        goto LABEL_1105;
      v379 = ConvertCaseHighUnicode(v378, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v378) & 1) == 0
           || (v379 = v378 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v378 + 32)) & 2) == 0) )
    {
LABEL_1105:
      v379 = v378;
    }
    v380 = *v376;
    if ( (*v376 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v380) & 0x100000) == 0 )
        goto LABEL_1108;
      v381 = ConvertCaseHighUnicode(v380, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v380) & 1) == 0
           || (v381 = v380 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v380 + 32)) & 2) == 0) )
    {
LABEL_1108:
      v381 = v380;
    }
    if ( v379 != v381 )
      break;
    ++v377;
    ++v376;
    if ( !v379 )
      goto LABEL_1075;
  }
  v382 = L"IsComputingHyphenation";
  v383 = v5;
  while ( 1 )
  {
    v384 = *v383;
    if ( (*v383 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v384) & 0x100000) == 0 )
        goto LABEL_1123;
      v385 = ConvertCaseHighUnicode(v384, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v384) & 1) == 0
           || (v385 = v384 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v384 + 32)) & 2) == 0) )
    {
LABEL_1123:
      v385 = v384;
    }
    v386 = *v382;
    if ( (*v382 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v386) & 0x100000) == 0 )
        goto LABEL_1126;
      v387 = ConvertCaseHighUnicode(v386, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v386) & 1) == 0
           || (v387 = v386 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v386 + 32)) & 2) == 0) )
    {
LABEL_1126:
      v387 = v386;
    }
    if ( v385 != v387 )
      break;
    ++v383;
    ++v382;
    if ( !v385 )
    {
LABEL_1129:
      *((_BYTE *)this + 278) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v388 = L"ComputingHyphenation";
  v389 = v5;
  while ( 1 )
  {
    v390 = *v389;
    if ( (*v389 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v390) & 0x100000) == 0 )
        goto LABEL_1141;
      v391 = ConvertCaseHighUnicode(v390, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v390) & 1) == 0
           || (v391 = v390 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v390 + 32)) & 2) == 0) )
    {
LABEL_1141:
      v391 = v390;
    }
    v392 = *v388;
    if ( (*v388 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v392) & 0x100000) == 0 )
        goto LABEL_1144;
      v393 = ConvertCaseHighUnicode(v392, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v392) & 1) == 0
           || (v393 = v392 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v392 + 32)) & 2) == 0) )
    {
LABEL_1144:
      v393 = v392;
    }
    if ( v391 != v393 )
      break;
    ++v389;
    ++v388;
    if ( !v391 )
      goto LABEL_1129;
  }
  v394 = L"Hyphenation";
  v395 = v5;
  while ( 1 )
  {
    v396 = *v395;
    if ( (*v395 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v396) & 0x100000) == 0 )
        goto LABEL_1159;
      v397 = ConvertCaseHighUnicode(v396, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v396) & 1) == 0
           || (v397 = v396 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v396 + 32)) & 2) == 0) )
    {
LABEL_1159:
      v397 = v396;
    }
    v398 = *v394;
    if ( (*v394 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v398) & 0x100000) == 0 )
        goto LABEL_1162;
      v399 = ConvertCaseHighUnicode(v398, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v398) & 1) == 0
           || (v399 = v398 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v398 + 32)) & 2) == 0) )
    {
LABEL_1162:
      v399 = v398;
    }
    if ( v397 != v399 )
      break;
    ++v395;
    ++v394;
    if ( !v397 )
      goto LABEL_1129;
  }
  v400 = L"IsSpellChecking";
  v401 = v5;
  while ( 1 )
  {
    v402 = *v401;
    if ( (*v401 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v402) & 0x100000) == 0 )
        goto LABEL_1177;
      v403 = ConvertCaseHighUnicode(v402, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v402) & 1) == 0
           || (v403 = v402 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v402 + 32)) & 2) == 0) )
    {
LABEL_1177:
      v403 = v402;
    }
    v404 = *v400;
    if ( (*v400 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v404) & 0x100000) == 0 )
        goto LABEL_1180;
      v405 = ConvertCaseHighUnicode(v404, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v404) & 1) == 0
           || (v405 = v404 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v404 + 32)) & 2) == 0) )
    {
LABEL_1180:
      v405 = v404;
    }
    if ( v403 != v405 )
      break;
    ++v401;
    ++v400;
    if ( !v403 )
    {
LABEL_1183:
      *((_BYTE *)this + 279) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v406 = L"SpellChecking";
  v407 = v5;
  while ( 1 )
  {
    v408 = *v407;
    if ( (*v407 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v408) & 0x100000) == 0 )
        goto LABEL_1195;
      v409 = ConvertCaseHighUnicode(v408, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v408) & 1) == 0
           || (v409 = v408 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v408 + 32)) & 2) == 0) )
    {
LABEL_1195:
      v409 = v408;
    }
    v410 = *v406;
    if ( (*v406 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v410) & 0x100000) == 0 )
        goto LABEL_1198;
      v411 = ConvertCaseHighUnicode(v410, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v410) & 1) == 0
           || (v411 = v410 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v410 + 32)) & 2) == 0) )
    {
LABEL_1198:
      v411 = v410;
    }
    if ( v409 != v411 )
      break;
    ++v407;
    ++v406;
    if ( !v409 )
      goto LABEL_1183;
  }
  v412 = L"Checking";
  v413 = v5;
  while ( 1 )
  {
    v414 = *v413;
    if ( (*v413 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v414) & 0x100000) == 0 )
        goto LABEL_1213;
      v415 = ConvertCaseHighUnicode(v414, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v414) & 1) == 0
           || (v415 = v414 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v414 + 32)) & 2) == 0) )
    {
LABEL_1213:
      v415 = v414;
    }
    v416 = *v412;
    if ( (*v412 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v416) & 0x100000) == 0 )
        goto LABEL_1216;
      v417 = ConvertCaseHighUnicode(v416, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v416) & 1) == 0
           || (v417 = v416 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v416 + 32)) & 2) == 0) )
    {
LABEL_1216:
      v417 = v416;
    }
    if ( v415 != v417 )
      break;
    ++v413;
    ++v412;
    if ( !v415 )
      goto LABEL_1183;
  }
  v418 = L"IsSpellAlwaysSuggesting";
  v419 = v5;
  while ( 1 )
  {
    v420 = *v419;
    if ( (*v419 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v420) & 0x100000) == 0 )
        goto LABEL_1231;
      v421 = ConvertCaseHighUnicode(v420, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v420) & 1) == 0
           || (v421 = v420 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v420 + 32)) & 2) == 0) )
    {
LABEL_1231:
      v421 = v420;
    }
    v422 = *v418;
    if ( (*v418 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v422) & 0x100000) == 0 )
        goto LABEL_1234;
      v423 = ConvertCaseHighUnicode(v422, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v422) & 1) == 0
           || (v423 = v422 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v422 + 32)) & 2) == 0) )
    {
LABEL_1234:
      v423 = v422;
    }
    if ( v421 != v423 )
      break;
    ++v419;
    ++v418;
    if ( !v421 )
    {
LABEL_1237:
      *((_BYTE *)this + 280) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v424 = L"SpellAlwaysSuggesting";
  v425 = v5;
  while ( 1 )
  {
    v426 = *v425;
    if ( (*v425 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v426) & 0x100000) == 0 )
        goto LABEL_1249;
      v427 = ConvertCaseHighUnicode(v426, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v426) & 1) == 0
           || (v427 = v426 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v426 + 32)) & 2) == 0) )
    {
LABEL_1249:
      v427 = v426;
    }
    v428 = *v424;
    if ( (*v424 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v428) & 0x100000) == 0 )
        goto LABEL_1252;
      v429 = ConvertCaseHighUnicode(v428, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v428) & 1) == 0
           || (v429 = v428 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v428 + 32)) & 2) == 0) )
    {
LABEL_1252:
      v429 = v428;
    }
    if ( v427 != v429 )
      break;
    ++v425;
    ++v424;
    if ( !v427 )
      goto LABEL_1237;
  }
  v430 = L"AlwaysSuggesting";
  v431 = v5;
  while ( 1 )
  {
    v432 = *v431;
    if ( (*v431 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v432) & 0x100000) == 0 )
        goto LABEL_1267;
      v433 = ConvertCaseHighUnicode(v432, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v432) & 1) == 0
           || (v433 = v432 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v432 + 32)) & 2) == 0) )
    {
LABEL_1267:
      v433 = v432;
    }
    v434 = *v430;
    if ( (*v430 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v434) & 0x100000) == 0 )
        goto LABEL_1270;
      v435 = ConvertCaseHighUnicode(v434, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v434) & 1) == 0
           || (v435 = v434 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v434 + 32)) & 2) == 0) )
    {
LABEL_1270:
      v435 = v434;
    }
    if ( v433 != v435 )
      break;
    ++v431;
    ++v430;
    if ( !v433 )
      goto LABEL_1237;
  }
  v436 = L"IsSpellSuggestingMWEs";
  v437 = v5;
  while ( 1 )
  {
    v438 = *v437;
    if ( (*v437 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v438) & 0x100000) == 0 )
        goto LABEL_1285;
      v439 = ConvertCaseHighUnicode(v438, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v438) & 1) == 0
           || (v439 = v438 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v438 + 32)) & 2) == 0) )
    {
LABEL_1285:
      v439 = v438;
    }
    v440 = *v436;
    if ( (*v436 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v440) & 0x100000) == 0 )
        goto LABEL_1288;
      v441 = ConvertCaseHighUnicode(v440, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v440) & 1) == 0
           || (v441 = v440 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v440 + 32)) & 2) == 0) )
    {
LABEL_1288:
      v441 = v440;
    }
    if ( v439 != v441 )
      break;
    ++v437;
    ++v436;
    if ( !v439 )
    {
LABEL_1291:
      *((_BYTE *)this + 281) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v442 = L"SpellSuggestingMWEs";
  v443 = v5;
  while ( 1 )
  {
    v444 = *v443;
    if ( (*v443 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v444) & 0x100000) == 0 )
        goto LABEL_1303;
      v445 = ConvertCaseHighUnicode(v444, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v444) & 1) == 0
           || (v445 = v444 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v444 + 32)) & 2) == 0) )
    {
LABEL_1303:
      v445 = v444;
    }
    v446 = *v442;
    if ( (*v442 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v446) & 0x100000) == 0 )
        goto LABEL_1306;
      v447 = ConvertCaseHighUnicode(v446, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v446) & 1) == 0
           || (v447 = v446 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v446 + 32)) & 2) == 0) )
    {
LABEL_1306:
      v447 = v446;
    }
    if ( v445 != v447 )
      break;
    ++v443;
    ++v442;
    if ( !v445 )
      goto LABEL_1291;
  }
  v448 = L"SuggestingMWEs";
  v449 = v5;
  while ( 1 )
  {
    v450 = *v449;
    if ( (*v449 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v450) & 0x100000) == 0 )
        goto LABEL_1321;
      v451 = ConvertCaseHighUnicode(v450, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v450) & 1) == 0
           || (v451 = v450 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v450 + 32)) & 2) == 0) )
    {
LABEL_1321:
      v451 = v450;
    }
    v452 = *v448;
    if ( (*v448 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v452) & 0x100000) == 0 )
        goto LABEL_1324;
      v453 = ConvertCaseHighUnicode(v452, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v452) & 1) == 0
           || (v453 = v452 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v452 + 32)) & 2) == 0) )
    {
LABEL_1324:
      v453 = v452;
    }
    if ( v451 != v453 )
      break;
    ++v449;
    ++v448;
    if ( !v451 )
      goto LABEL_1291;
  }
  v454 = L"IsSpellForcingCompoundSuggestions";
  v455 = v5;
  while ( 1 )
  {
    v456 = *v455;
    if ( (*v455 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v456) & 0x100000) == 0 )
        goto LABEL_1339;
      v457 = ConvertCaseHighUnicode(v456, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v456) & 1) == 0
           || (v457 = v456 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v456 + 32)) & 2) == 0) )
    {
LABEL_1339:
      v457 = v456;
    }
    v458 = *v454;
    if ( (*v454 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v458) & 0x100000) == 0 )
        goto LABEL_1342;
      v459 = ConvertCaseHighUnicode(v458, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v458) & 1) == 0
           || (v459 = v458 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v458 + 32)) & 2) == 0) )
    {
LABEL_1342:
      v459 = v458;
    }
    if ( v457 != v459 )
      break;
    ++v455;
    ++v454;
    if ( !v457 )
    {
LABEL_1345:
      *((_BYTE *)this + 282) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v460 = L"SpellForcingCompoundSuggestions";
  v461 = v5;
  while ( 1 )
  {
    v462 = *v461;
    if ( (*v461 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v462) & 0x100000) == 0 )
        goto LABEL_1357;
      v463 = ConvertCaseHighUnicode(v462, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v462) & 1) == 0
           || (v463 = v462 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v462 + 32)) & 2) == 0) )
    {
LABEL_1357:
      v463 = v462;
    }
    v464 = *v460;
    if ( (*v460 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v464) & 0x100000) == 0 )
        goto LABEL_1360;
      v465 = ConvertCaseHighUnicode(v464, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v464) & 1) == 0
           || (v465 = v464 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v464 + 32)) & 2) == 0) )
    {
LABEL_1360:
      v465 = v464;
    }
    if ( v463 != v465 )
      break;
    ++v461;
    ++v460;
    if ( !v463 )
      goto LABEL_1345;
  }
  v466 = L"ForcingCompoundSuggestions";
  v467 = v5;
  while ( 1 )
  {
    v468 = *v467;
    if ( (*v467 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v468) & 0x100000) == 0 )
        goto LABEL_1375;
      v469 = ConvertCaseHighUnicode(v468, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v468) & 1) == 0
           || (v469 = v468 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v468 + 32)) & 2) == 0) )
    {
LABEL_1375:
      v469 = v468;
    }
    v470 = *v466;
    if ( (*v466 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v470) & 0x100000) == 0 )
        goto LABEL_1378;
      v471 = ConvertCaseHighUnicode(v470, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v470) & 1) == 0
           || (v471 = v470 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v470 + 32)) & 2) == 0) )
    {
LABEL_1378:
      v471 = v470;
    }
    if ( v469 != v471 )
      break;
    ++v467;
    ++v466;
    if ( !v469 )
      goto LABEL_1345;
  }
  v472 = L"IsSpellUsingDialects";
  v473 = v5;
  while ( 1 )
  {
    v474 = *v473;
    if ( (*v473 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v474) & 0x100000) == 0 )
        goto LABEL_1393;
      v475 = ConvertCaseHighUnicode(v474, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v474) & 1) == 0
           || (v475 = v474 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v474 + 32)) & 2) == 0) )
    {
LABEL_1393:
      v475 = v474;
    }
    v476 = *v472;
    if ( (*v472 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v476) & 0x100000) == 0 )
        goto LABEL_1396;
      v477 = ConvertCaseHighUnicode(v476, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v476) & 1) == 0
           || (v477 = v476 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v476 + 32)) & 2) == 0) )
    {
LABEL_1396:
      v477 = v476;
    }
    if ( v475 != v477 )
      break;
    ++v473;
    ++v472;
    if ( !v475 )
    {
LABEL_1399:
      *((_BYTE *)this + 283) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v478 = L"SpellUsingDialects";
  v479 = v5;
  while ( 1 )
  {
    v480 = *v479;
    if ( (*v479 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v480) & 0x100000) == 0 )
        goto LABEL_1411;
      v481 = ConvertCaseHighUnicode(v480, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v480) & 1) == 0
           || (v481 = v480 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v480 + 32)) & 2) == 0) )
    {
LABEL_1411:
      v481 = v480;
    }
    v482 = *v478;
    if ( (*v478 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v482) & 0x100000) == 0 )
        goto LABEL_1414;
      v483 = ConvertCaseHighUnicode(v482, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v482) & 1) == 0
           || (v483 = v482 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v482 + 32)) & 2) == 0) )
    {
LABEL_1414:
      v483 = v482;
    }
    if ( v481 != v483 )
      break;
    ++v479;
    ++v478;
    if ( !v481 )
      goto LABEL_1399;
  }
  v484 = L"UsingDialects";
  v485 = v5;
  while ( 1 )
  {
    v486 = *v485;
    if ( (*v485 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v486) & 0x100000) == 0 )
        goto LABEL_1429;
      v487 = ConvertCaseHighUnicode(v486, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v486) & 1) == 0
           || (v487 = v486 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v486 + 32)) & 2) == 0) )
    {
LABEL_1429:
      v487 = v486;
    }
    v488 = *v484;
    if ( (*v484 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v488) & 0x100000) == 0 )
        goto LABEL_1432;
      v489 = ConvertCaseHighUnicode(v488, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v488) & 1) == 0
           || (v489 = v488 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v488 + 32)) & 2) == 0) )
    {
LABEL_1432:
      v489 = v488;
    }
    if ( v487 != v489 )
      break;
    ++v485;
    ++v484;
    if ( !v487 )
      goto LABEL_1399;
  }
  v490 = L"IsSpellVerifyOnly";
  v491 = v5;
  while ( 1 )
  {
    v492 = *v491;
    if ( (*v491 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v492) & 0x100000) == 0 )
        goto LABEL_1447;
      v493 = ConvertCaseHighUnicode(v492, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v492) & 1) == 0
           || (v493 = v492 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v492 + 32)) & 2) == 0) )
    {
LABEL_1447:
      v493 = v492;
    }
    v494 = *v490;
    if ( (*v490 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v494) & 0x100000) == 0 )
        goto LABEL_1450;
      v495 = ConvertCaseHighUnicode(v494, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v494) & 1) == 0
           || (v495 = v494 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v494 + 32)) & 2) == 0) )
    {
LABEL_1450:
      v495 = v494;
    }
    if ( v493 != v495 )
      break;
    ++v491;
    ++v490;
    if ( !v493 )
    {
LABEL_1453:
      *((_BYTE *)this + 284) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v496 = L"SpellVerifyOnly";
  v497 = v5;
  while ( 1 )
  {
    v498 = *v497;
    if ( (*v497 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v498) & 0x100000) == 0 )
        goto LABEL_1465;
      v499 = ConvertCaseHighUnicode(v498, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v498) & 1) == 0
           || (v499 = v498 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v498 + 32)) & 2) == 0) )
    {
LABEL_1465:
      v499 = v498;
    }
    v500 = *v496;
    if ( (*v496 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v500) & 0x100000) == 0 )
        goto LABEL_1468;
      v501 = ConvertCaseHighUnicode(v500, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v500) & 1) == 0
           || (v501 = v500 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v500 + 32)) & 2) == 0) )
    {
LABEL_1468:
      v501 = v500;
    }
    if ( v499 != v501 )
      break;
    ++v497;
    ++v496;
    if ( !v499 )
      goto LABEL_1453;
  }
  v502 = L"VerifyOnly";
  v503 = v5;
  while ( 1 )
  {
    v504 = *v503;
    if ( (*v503 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v504) & 0x100000) == 0 )
        goto LABEL_1483;
      v505 = ConvertCaseHighUnicode(v504, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v504) & 1) == 0
           || (v505 = v504 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v504 + 32)) & 2) == 0) )
    {
LABEL_1483:
      v505 = v504;
    }
    v506 = *v502;
    if ( (*v502 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v506) & 0x100000) == 0 )
        goto LABEL_1486;
      v507 = ConvertCaseHighUnicode(v506, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v506) & 1) == 0
           || (v507 = v506 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v506 + 32)) & 2) == 0) )
    {
LABEL_1486:
      v507 = v506;
    }
    if ( v505 != v507 )
      break;
    ++v503;
    ++v502;
    if ( !v505 )
      goto LABEL_1453;
  }
  v508 = L"IsSpellVerifyAutoReplace";
  v509 = v5;
  while ( 1 )
  {
    v510 = *v509;
    if ( (*v509 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v510) & 0x100000) == 0 )
        goto LABEL_1501;
      v511 = ConvertCaseHighUnicode(v510, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v510) & 1) == 0
           || (v511 = v510 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v510 + 32)) & 2) == 0) )
    {
LABEL_1501:
      v511 = v510;
    }
    v512 = *v508;
    if ( (*v508 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v512) & 0x100000) == 0 )
        goto LABEL_1504;
      v513 = ConvertCaseHighUnicode(v512, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v512) & 1) == 0
           || (v513 = v512 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v512 + 32)) & 2) == 0) )
    {
LABEL_1504:
      v513 = v512;
    }
    if ( v511 != v513 )
      break;
    ++v509;
    ++v508;
    if ( !v511 )
    {
LABEL_1507:
      *((_BYTE *)this + 285) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v514 = L"SpellVerifyAutoReplace";
  v515 = v5;
  while ( 1 )
  {
    v516 = *v515;
    if ( (*v515 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v516) & 0x100000) == 0 )
        goto LABEL_1519;
      v517 = ConvertCaseHighUnicode(v516, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v516) & 1) == 0
           || (v517 = v516 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v516 + 32)) & 2) == 0) )
    {
LABEL_1519:
      v517 = v516;
    }
    v518 = *v514;
    if ( (*v514 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v518) & 0x100000) == 0 )
        goto LABEL_1522;
      v519 = ConvertCaseHighUnicode(v518, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v518) & 1) == 0
           || (v519 = v518 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v518 + 32)) & 2) == 0) )
    {
LABEL_1522:
      v519 = v518;
    }
    if ( v517 != v519 )
      break;
    ++v515;
    ++v514;
    if ( !v517 )
      goto LABEL_1507;
  }
  v520 = L"VerifyAutoReplace";
  v521 = v5;
  while ( 1 )
  {
    v522 = *v521;
    if ( (*v521 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v522) & 0x100000) == 0 )
        goto LABEL_1537;
      v523 = ConvertCaseHighUnicode(v522, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v522) & 1) == 0
           || (v523 = v522 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v522 + 32)) & 2) == 0) )
    {
LABEL_1537:
      v523 = v522;
    }
    v524 = *v520;
    if ( (*v520 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v524) & 0x100000) == 0 )
        goto LABEL_1540;
      v525 = ConvertCaseHighUnicode(v524, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v524) & 1) == 0
           || (v525 = v524 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v524 + 32)) & 2) == 0) )
    {
LABEL_1540:
      v525 = v524;
    }
    if ( v523 != v525 )
      break;
    ++v521;
    ++v520;
    if ( !v523 )
      goto LABEL_1507;
  }
  v526 = L"IsSpellContinued";
  v527 = v5;
  while ( 1 )
  {
    v528 = *v527;
    if ( (*v527 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v528) & 0x100000) == 0 )
        goto LABEL_1555;
      v529 = ConvertCaseHighUnicode(v528, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v528) & 1) == 0
           || (v529 = v528 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v528 + 32)) & 2) == 0) )
    {
LABEL_1555:
      v529 = v528;
    }
    v530 = *v526;
    if ( (*v526 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v530) & 0x100000) == 0 )
        goto LABEL_1558;
      v531 = ConvertCaseHighUnicode(v530, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v530) & 1) == 0
           || (v531 = v530 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v530 + 32)) & 2) == 0) )
    {
LABEL_1558:
      v531 = v530;
    }
    if ( v529 != v531 )
      break;
    ++v527;
    ++v526;
    if ( !v529 )
    {
LABEL_1561:
      *((_BYTE *)this + 286) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v532 = L"SpellContinued";
  v533 = v5;
  while ( 1 )
  {
    v534 = *v533;
    if ( (*v533 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v534) & 0x100000) == 0 )
        goto LABEL_1573;
      v535 = ConvertCaseHighUnicode(v534, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v534) & 1) == 0
           || (v535 = v534 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v534 + 32)) & 2) == 0) )
    {
LABEL_1573:
      v535 = v534;
    }
    v536 = *v532;
    if ( (*v532 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v536) & 0x100000) == 0 )
        goto LABEL_1576;
      v537 = ConvertCaseHighUnicode(v536, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v536) & 1) == 0
           || (v537 = v536 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v536 + 32)) & 2) == 0) )
    {
LABEL_1576:
      v537 = v536;
    }
    if ( v535 != v537 )
      break;
    ++v533;
    ++v532;
    if ( !v535 )
      goto LABEL_1561;
  }
  v538 = L"Continued";
  v539 = v5;
  while ( 1 )
  {
    v540 = *v539;
    if ( (*v539 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v540) & 0x100000) == 0 )
        goto LABEL_1591;
      v541 = ConvertCaseHighUnicode(v540, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v540) & 1) == 0
           || (v541 = v540 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v540 + 32)) & 2) == 0) )
    {
LABEL_1591:
      v541 = v540;
    }
    v542 = *v538;
    if ( (*v538 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v542) & 0x100000) == 0 )
        goto LABEL_1594;
      v543 = ConvertCaseHighUnicode(v542, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v542) & 1) == 0
           || (v543 = v542 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v542 + 32)) & 2) == 0) )
    {
LABEL_1594:
      v543 = v542;
    }
    if ( v541 != v543 )
      break;
    ++v539;
    ++v538;
    if ( !v541 )
      goto LABEL_1561;
  }
  v544 = L"IsSpellCaseSensitive";
  v545 = v5;
  while ( 1 )
  {
    v546 = *v545;
    if ( (*v545 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v546) & 0x100000) == 0 )
        goto LABEL_1609;
      v547 = ConvertCaseHighUnicode(v546, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v546) & 1) == 0
           || (v547 = v546 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v546 + 32)) & 2) == 0) )
    {
LABEL_1609:
      v547 = v546;
    }
    v548 = *v544;
    if ( (*v544 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v548) & 0x100000) == 0 )
        goto LABEL_1612;
      v549 = ConvertCaseHighUnicode(v548, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v548) & 1) == 0
           || (v549 = v548 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v548 + 32)) & 2) == 0) )
    {
LABEL_1612:
      v549 = v548;
    }
    if ( v547 != v549 )
      break;
    ++v545;
    ++v544;
    if ( !v547 )
    {
LABEL_1615:
      *((_BYTE *)this + 287) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v550 = L"SpellCaseSensitive";
  v551 = v5;
  while ( 1 )
  {
    v552 = *v551;
    if ( (*v551 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v552) & 0x100000) == 0 )
        goto LABEL_1627;
      v553 = ConvertCaseHighUnicode(v552, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v552) & 1) == 0
           || (v553 = v552 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v552 + 32)) & 2) == 0) )
    {
LABEL_1627:
      v553 = v552;
    }
    v554 = *v550;
    if ( (*v550 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v554) & 0x100000) == 0 )
        goto LABEL_1630;
      v555 = ConvertCaseHighUnicode(v554, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v554) & 1) == 0
           || (v555 = v554 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v554 + 32)) & 2) == 0) )
    {
LABEL_1630:
      v555 = v554;
    }
    if ( v553 != v555 )
      break;
    ++v551;
    ++v550;
    if ( !v553 )
      goto LABEL_1615;
  }
  v556 = L"CaseSensitive";
  v557 = v5;
  while ( 1 )
  {
    v558 = *v557;
    if ( (*v557 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v558) & 0x100000) == 0 )
        goto LABEL_1645;
      v559 = ConvertCaseHighUnicode(v558, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v558) & 1) == 0
           || (v559 = v558 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v558 + 32)) & 2) == 0) )
    {
LABEL_1645:
      v559 = v558;
    }
    v560 = *v556;
    if ( (*v556 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v560) & 0x100000) == 0 )
        goto LABEL_1648;
      v561 = ConvertCaseHighUnicode(v560, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v560) & 1) == 0
           || (v561 = v560 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v560 + 32)) & 2) == 0) )
    {
LABEL_1648:
      v561 = v560;
    }
    if ( v559 != v561 )
      break;
    ++v557;
    ++v556;
    if ( !v559 )
      goto LABEL_1615;
  }
  v562 = L"SpellLexDataID";
  v563 = v5;
  while ( 1 )
  {
    v564 = *v563;
    if ( (*v563 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v564) & 0x100000) == 0 )
        goto LABEL_1663;
      v565 = ConvertCaseHighUnicode(v564, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v564) & 1) == 0
           || (v565 = v564 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v564 + 32)) & 2) == 0) )
    {
LABEL_1663:
      v565 = v564;
    }
    v566 = *v562;
    if ( (*v562 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v566) & 0x100000) == 0 )
        goto LABEL_1666;
      v567 = ConvertCaseHighUnicode(v566, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v566) & 1) == 0
           || (v567 = v566 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v566 + 32)) & 2) == 0) )
    {
LABEL_1666:
      v567 = v566;
    }
    if ( v565 != v567 )
      break;
    ++v563;
    ++v562;
    if ( !v565 )
    {
LABEL_1669:
      *((_DWORD *)this + 72) = _variant_t::operator long(a3);
      return 1;
    }
  }
  v568 = L"LexDataID";
  v569 = v5;
  while ( 1 )
  {
    v570 = *v569;
    if ( (*v569 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v570) & 0x100000) == 0 )
        goto LABEL_1681;
      v571 = ConvertCaseHighUnicode(v570, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v570) & 1) == 0
           || (v571 = v570 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v570 + 32)) & 2) == 0) )
    {
LABEL_1681:
      v571 = v570;
    }
    v572 = *v568;
    if ( (*v568 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v572) & 0x100000) == 0 )
        goto LABEL_1684;
      v573 = ConvertCaseHighUnicode(v572, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v572) & 1) == 0
           || (v573 = v572 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v572 + 32)) & 2) == 0) )
    {
LABEL_1684:
      v573 = v572;
    }
    if ( v571 != v573 )
      break;
    ++v569;
    ++v568;
    if ( !v571 )
      goto LABEL_1669;
  }
  v574 = L"IsSuggestFromMainLexOnly";
  v575 = v5;
  while ( 1 )
  {
    v576 = *v575;
    if ( (*v575 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v576) & 0x100000) == 0 )
        goto LABEL_1699;
      v577 = ConvertCaseHighUnicode(v576, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v576) & 1) == 0
           || (v577 = v576 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v576 + 32)) & 2) == 0) )
    {
LABEL_1699:
      v577 = v576;
    }
    v578 = *v574;
    if ( (*v574 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v578) & 0x100000) == 0 )
        goto LABEL_1702;
      v579 = ConvertCaseHighUnicode(v578, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v578) & 1) == 0
           || (v579 = v578 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v578 + 32)) & 2) == 0) )
    {
LABEL_1702:
      v579 = v578;
    }
    if ( v577 != v579 )
      break;
    ++v575;
    ++v574;
    if ( !v577 )
    {
LABEL_1705:
      *((_BYTE *)this + 292) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v580 = L"SuggestFromMainLexOnly";
  v581 = v5;
  while ( 1 )
  {
    v582 = *v581;
    if ( (*v581 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v582) & 0x100000) == 0 )
        goto LABEL_1717;
      v583 = ConvertCaseHighUnicode(v582, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v582) & 1) == 0
           || (v583 = v582 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v582 + 32)) & 2) == 0) )
    {
LABEL_1717:
      v583 = v582;
    }
    v584 = *v580;
    if ( (*v580 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v584) & 0x100000) == 0 )
        goto LABEL_1720;
      v585 = ConvertCaseHighUnicode(v584, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v584) & 1) == 0
           || (v585 = v584 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v584 + 32)) & 2) == 0) )
    {
LABEL_1720:
      v585 = v584;
    }
    if ( v583 != v585 )
      break;
    ++v581;
    ++v580;
    if ( !v583 )
      goto LABEL_1705;
  }
  v586 = L"IsIgnoreAllCaps";
  v587 = v5;
  while ( 1 )
  {
    v588 = *v587;
    if ( (*v587 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v588) & 0x100000) == 0 )
        goto LABEL_1735;
      v589 = ConvertCaseHighUnicode(v588, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v588) & 1) == 0
           || (v589 = v588 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v588 + 32)) & 2) == 0) )
    {
LABEL_1735:
      v589 = v588;
    }
    v590 = *v586;
    if ( (*v586 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v590) & 0x100000) == 0 )
        goto LABEL_1738;
      v591 = ConvertCaseHighUnicode(v590, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v590) & 1) == 0
           || (v591 = v590 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v590 + 32)) & 2) == 0) )
    {
LABEL_1738:
      v591 = v590;
    }
    if ( v589 != v591 )
      break;
    ++v587;
    ++v586;
    if ( !v589 )
    {
LABEL_1741:
      *((_BYTE *)this + 293) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v592 = L"IgnoreAllCaps";
  v593 = v5;
  while ( 1 )
  {
    v594 = *v593;
    if ( (*v593 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v594) & 0x100000) == 0 )
        goto LABEL_1753;
      v595 = ConvertCaseHighUnicode(v594, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v594) & 1) == 0
           || (v595 = v594 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v594 + 32)) & 2) == 0) )
    {
LABEL_1753:
      v595 = v594;
    }
    v596 = *v592;
    if ( (*v592 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v596) & 0x100000) == 0 )
        goto LABEL_1756;
      v597 = ConvertCaseHighUnicode(v596, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v596) & 1) == 0
           || (v597 = v596 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v596 + 32)) & 2) == 0) )
    {
LABEL_1756:
      v597 = v596;
    }
    if ( v595 != v597 )
      break;
    ++v593;
    ++v592;
    if ( !v595 )
      goto LABEL_1741;
  }
  v598 = L"IsIgnoreMixedDigits";
  v599 = v5;
  while ( 1 )
  {
    v600 = *v599;
    if ( (*v599 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v600) & 0x100000) == 0 )
        goto LABEL_1771;
      v601 = ConvertCaseHighUnicode(v600, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v600) & 1) == 0
           || (v601 = v600 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v600 + 32)) & 2) == 0) )
    {
LABEL_1771:
      v601 = v600;
    }
    v602 = *v598;
    if ( (*v598 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v602) & 0x100000) == 0 )
        goto LABEL_1774;
      v603 = ConvertCaseHighUnicode(v602, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v602) & 1) == 0
           || (v603 = v602 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v602 + 32)) & 2) == 0) )
    {
LABEL_1774:
      v603 = v602;
    }
    if ( v601 != v603 )
      break;
    ++v599;
    ++v598;
    if ( !v601 )
    {
LABEL_1777:
      *((_BYTE *)this + 294) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v604 = L"IgnoreMixedDigits";
  v605 = v5;
  while ( 1 )
  {
    v606 = *v605;
    if ( (*v605 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v606) & 0x100000) == 0 )
        goto LABEL_1789;
      v607 = ConvertCaseHighUnicode(v606, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v606) & 1) == 0
           || (v607 = v606 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v606 + 32)) & 2) == 0) )
    {
LABEL_1789:
      v607 = v606;
    }
    v608 = *v604;
    if ( (*v604 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v608) & 0x100000) == 0 )
        goto LABEL_1792;
      v609 = ConvertCaseHighUnicode(v608, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v608) & 1) == 0
           || (v609 = v608 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v608 + 32)) & 2) == 0) )
    {
LABEL_1792:
      v609 = v608;
    }
    if ( v607 != v609 )
      break;
    ++v605;
    ++v604;
    if ( !v607 )
      goto LABEL_1777;
  }
  v610 = L"IsIgnoreRomanNumerals";
  v611 = v5;
  while ( 1 )
  {
    v612 = *v611;
    if ( (*v611 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v612) & 0x100000) == 0 )
        goto LABEL_1807;
      v613 = ConvertCaseHighUnicode(v612, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v612) & 1) == 0
           || (v613 = v612 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v612 + 32)) & 2) == 0) )
    {
LABEL_1807:
      v613 = v612;
    }
    v614 = *v610;
    if ( (*v610 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v614) & 0x100000) == 0 )
        goto LABEL_1810;
      v615 = ConvertCaseHighUnicode(v614, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v614) & 1) == 0
           || (v615 = v614 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v614 + 32)) & 2) == 0) )
    {
LABEL_1810:
      v615 = v614;
    }
    if ( v613 != v615 )
      break;
    ++v611;
    ++v610;
    if ( !v613 )
    {
LABEL_1813:
      *((_BYTE *)this + 295) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v616 = L"IgnoreRomanNumerals";
  v617 = v5;
  while ( 1 )
  {
    v618 = *v617;
    if ( (*v617 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v618) & 0x100000) == 0 )
        goto LABEL_1825;
      v619 = ConvertCaseHighUnicode(v618, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v618) & 1) == 0
           || (v619 = v618 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v618 + 32)) & 2) == 0) )
    {
LABEL_1825:
      v619 = v618;
    }
    v620 = *v616;
    if ( (*v616 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v620) & 0x100000) == 0 )
        goto LABEL_1828;
      v621 = ConvertCaseHighUnicode(v620, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v620) & 1) == 0
           || (v621 = v620 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v620 + 32)) & 2) == 0) )
    {
LABEL_1828:
      v621 = v620;
    }
    if ( v619 != v621 )
      break;
    ++v617;
    ++v616;
    if ( !v619 )
      goto LABEL_1813;
  }
  v622 = L"IsFindRepeatWord";
  v623 = v5;
  while ( 1 )
  {
    v624 = *v623;
    if ( (*v623 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v624) & 0x100000) == 0 )
        goto LABEL_1843;
      v625 = ConvertCaseHighUnicode(v624, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v624) & 1) == 0
           || (v625 = v624 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v624 + 32)) & 2) == 0) )
    {
LABEL_1843:
      v625 = v624;
    }
    v626 = *v622;
    if ( (*v622 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v626) & 0x100000) == 0 )
        goto LABEL_1846;
      v627 = ConvertCaseHighUnicode(v626, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v626) & 1) == 0
           || (v627 = v626 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v626 + 32)) & 2) == 0) )
    {
LABEL_1846:
      v627 = v626;
    }
    if ( v625 != v627 )
      break;
    ++v623;
    ++v622;
    if ( !v625 )
    {
LABEL_1849:
      *((_BYTE *)this + 296) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v628 = L"FindRepeatWord";
  v629 = v5;
  while ( 1 )
  {
    v630 = *v629;
    if ( (*v629 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v630) & 0x100000) == 0 )
        goto LABEL_1861;
      v631 = ConvertCaseHighUnicode(v630, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v630) & 1) == 0
           || (v631 = v630 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v630 + 32)) & 2) == 0) )
    {
LABEL_1861:
      v631 = v630;
    }
    v632 = *v628;
    if ( (*v628 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v632) & 0x100000) == 0 )
        goto LABEL_1864;
      v633 = ConvertCaseHighUnicode(v632, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v632) & 1) == 0
           || (v633 = v632 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v632 + 32)) & 2) == 0) )
    {
LABEL_1864:
      v633 = v632;
    }
    if ( v631 != v633 )
      break;
    ++v629;
    ++v628;
    if ( !v631 )
      goto LABEL_1849;
  }
  v634 = L"IsIgnoreSingleLetter";
  v635 = v5;
  while ( 1 )
  {
    v636 = *v635;
    if ( (*v635 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v636) & 0x100000) == 0 )
        goto LABEL_1879;
      v637 = ConvertCaseHighUnicode(v636, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v636) & 1) == 0
           || (v637 = v636 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v636 + 32)) & 2) == 0) )
    {
LABEL_1879:
      v637 = v636;
    }
    v638 = *v634;
    if ( (*v634 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v638) & 0x100000) == 0 )
        goto LABEL_1882;
      v639 = ConvertCaseHighUnicode(v638, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v638) & 1) == 0
           || (v639 = v638 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v638 + 32)) & 2) == 0) )
    {
LABEL_1882:
      v639 = v638;
    }
    if ( v637 != v639 )
      break;
    ++v635;
    ++v634;
    if ( !v637 )
    {
LABEL_1885:
      *((_BYTE *)this + 297) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v640 = L"IgnoreSingleLetter";
  v641 = v5;
  while ( 1 )
  {
    v642 = *v641;
    if ( (*v641 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v642) & 0x100000) == 0 )
        goto LABEL_1897;
      v643 = ConvertCaseHighUnicode(v642, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v642) & 1) == 0
           || (v643 = v642 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v642 + 32)) & 2) == 0) )
    {
LABEL_1897:
      v643 = v642;
    }
    v644 = *v640;
    if ( (*v640 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v644) & 0x100000) == 0 )
        goto LABEL_1900;
      v645 = ConvertCaseHighUnicode(v644, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v644) & 1) == 0
           || (v645 = v644 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v644 + 32)) & 2) == 0) )
    {
LABEL_1900:
      v645 = v644;
    }
    if ( v643 != v645 )
      break;
    ++v641;
    ++v640;
    if ( !v643 )
      goto LABEL_1885;
  }
  v646 = L"IsContextSpell";
  v647 = v5;
  while ( 1 )
  {
    v648 = *v647;
    if ( (*v647 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v648) & 0x100000) == 0 )
        goto LABEL_1915;
      v649 = ConvertCaseHighUnicode(v648, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v648) & 1) == 0
           || (v649 = v648 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v648 + 32)) & 2) == 0) )
    {
LABEL_1915:
      v649 = v648;
    }
    v650 = *v646;
    if ( (*v646 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v650) & 0x100000) == 0 )
        goto LABEL_1918;
      v651 = ConvertCaseHighUnicode(v650, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v650) & 1) == 0
           || (v651 = v650 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v650 + 32)) & 2) == 0) )
    {
LABEL_1918:
      v651 = v650;
    }
    if ( v649 != v651 )
      break;
    ++v647;
    ++v646;
    if ( !v649 )
    {
LABEL_1921:
      *((_BYTE *)this + 298) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v652 = L"ContextSpell";
  v653 = v5;
  while ( 1 )
  {
    v654 = *v653;
    if ( (*v653 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v654) & 0x100000) == 0 )
        goto LABEL_1933;
      v655 = ConvertCaseHighUnicode(v654, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v654) & 1) == 0
           || (v655 = v654 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v654 + 32)) & 2) == 0) )
    {
LABEL_1933:
      v655 = v654;
    }
    v656 = *v652;
    if ( (*v652 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v656) & 0x100000) == 0 )
        goto LABEL_1936;
      v657 = ConvertCaseHighUnicode(v656, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v656) & 1) == 0
           || (v657 = v656 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v656 + 32)) & 2) == 0) )
    {
LABEL_1936:
      v657 = v656;
    }
    if ( v655 != v657 )
      break;
    ++v653;
    ++v652;
    if ( !v655 )
      goto LABEL_1921;
  }
  v658 = L"IsIgnoreUrls";
  v659 = v5;
  while ( 1 )
  {
    v660 = *v659;
    if ( (*v659 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v660) & 0x100000) == 0 )
        goto LABEL_1951;
      v661 = ConvertCaseHighUnicode(v660, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v660) & 1) == 0
           || (v661 = v660 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v660 + 32)) & 2) == 0) )
    {
LABEL_1951:
      v661 = v660;
    }
    v662 = *v658;
    if ( (*v658 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v662) & 0x100000) == 0 )
        goto LABEL_1954;
      v663 = ConvertCaseHighUnicode(v662, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v662) & 1) == 0
           || (v663 = v662 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v662 + 32)) & 2) == 0) )
    {
LABEL_1954:
      v663 = v662;
    }
    if ( v661 != v663 )
      break;
    ++v659;
    ++v658;
    if ( !v661 )
    {
LABEL_1957:
      *((_BYTE *)this + 299) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v664 = L"IgnoreUrls";
  v665 = v5;
  while ( 1 )
  {
    v666 = *v665;
    if ( (*v665 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v666) & 0x100000) == 0 )
        goto LABEL_1969;
      v667 = ConvertCaseHighUnicode(v666, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v666) & 1) == 0
           || (v667 = v666 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v666 + 32)) & 2) == 0) )
    {
LABEL_1969:
      v667 = v666;
    }
    v668 = *v664;
    if ( (*v664 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v668) & 0x100000) == 0 )
        goto LABEL_1972;
      v669 = ConvertCaseHighUnicode(v668, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v668) & 1) == 0
           || (v669 = v668 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v668 + 32)) & 2) == 0) )
    {
LABEL_1972:
      v669 = v668;
    }
    if ( v667 != v669 )
      break;
    ++v665;
    ++v664;
    if ( !v667 )
      goto LABEL_1957;
  }
  v670 = L"IsFrenchAccentedUppercase";
  v671 = v5;
  while ( 1 )
  {
    v672 = *v671;
    if ( (*v671 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v672) & 0x100000) == 0 )
        goto LABEL_1987;
      v673 = ConvertCaseHighUnicode(v672, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v672) & 1) == 0
           || (v673 = v672 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v672 + 32)) & 2) == 0) )
    {
LABEL_1987:
      v673 = v672;
    }
    v674 = *v670;
    if ( (*v670 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v674) & 0x100000) == 0 )
        goto LABEL_1990;
      v675 = ConvertCaseHighUnicode(v674, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v674) & 1) == 0
           || (v675 = v674 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v674 + 32)) & 2) == 0) )
    {
LABEL_1990:
      v675 = v674;
    }
    if ( v673 != v675 )
      break;
    ++v671;
    ++v670;
    if ( !v673 )
    {
LABEL_1993:
      *((_BYTE *)this + 300) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v676 = L"FrenchAccentedUppercase";
  v677 = v5;
  while ( 1 )
  {
    v678 = *v677;
    if ( (*v677 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v678) & 0x100000) == 0 )
        goto LABEL_2005;
      v679 = ConvertCaseHighUnicode(v678, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v678) & 1) == 0
           || (v679 = v678 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v678 + 32)) & 2) == 0) )
    {
LABEL_2005:
      v679 = v678;
    }
    v680 = *v676;
    if ( (*v676 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v680) & 0x100000) == 0 )
        goto LABEL_2008;
      v681 = ConvertCaseHighUnicode(v680, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v680) & 1) == 0
           || (v681 = v680 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v680 + 32)) & 2) == 0) )
    {
LABEL_2008:
      v681 = v680;
    }
    if ( v679 != v681 )
      break;
    ++v677;
    ++v676;
    if ( !v679 )
      goto LABEL_1993;
  }
  v682 = L"FrenchReform";
  for ( i = v5; ; ++i )
  {
    v684 = *i;
    if ( (*i & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v684) & 0x100000) == 0 )
        goto LABEL_2023;
      v685 = ConvertCaseHighUnicode(v684, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v684) & 1) == 0
           || (v685 = v684 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v684 + 32)) & 2) == 0) )
    {
LABEL_2023:
      v685 = v684;
    }
    v686 = *v682;
    if ( (*v682 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v686) & 0x100000) == 0 )
        goto LABEL_2026;
      v687 = ConvertCaseHighUnicode(v686, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v686) & 1) == 0
           || (v687 = v686 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v686 + 32)) & 2) == 0) )
    {
LABEL_2026:
      v687 = v686;
    }
    if ( v685 != v687 )
      break;
    ++v682;
    if ( !v685 )
    {
      v688 = _variant_t::operator long(a3);
      CContextBase::SetFrenchReform(this, v688);
      return 1;
    }
  }
  v689 = L"IsGermanPrereform";
  v690 = v5;
  while ( 1 )
  {
    v691 = *v690;
    if ( (*v690 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v691) & 0x100000) == 0 )
        goto LABEL_2041;
      v692 = ConvertCaseHighUnicode(v691, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v691) & 1) == 0
           || (v692 = v691 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v691 + 32)) & 2) == 0) )
    {
LABEL_2041:
      v692 = v691;
    }
    v693 = *v689;
    if ( (*v689 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v693) & 0x100000) == 0 )
        goto LABEL_2044;
      v694 = ConvertCaseHighUnicode(v693, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v693) & 1) == 0
           || (v694 = v693 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v693 + 32)) & 2) == 0) )
    {
LABEL_2044:
      v694 = v693;
    }
    if ( v692 != v694 )
      break;
    ++v690;
    ++v689;
    if ( !v692 )
    {
LABEL_2047:
      *((_BYTE *)this + 308) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v695 = L"GermanPrereform";
  v696 = v5;
  while ( 1 )
  {
    v697 = *v696;
    if ( (*v696 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v697) & 0x100000) == 0 )
        goto LABEL_2059;
      v698 = ConvertCaseHighUnicode(v697, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v697) & 1) == 0
           || (v698 = v697 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v697 + 32)) & 2) == 0) )
    {
LABEL_2059:
      v698 = v697;
    }
    v699 = *v695;
    if ( (*v695 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v699) & 0x100000) == 0 )
        goto LABEL_2062;
      v700 = ConvertCaseHighUnicode(v699, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v699) & 1) == 0
           || (v700 = v699 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v699 + 32)) & 2) == 0) )
    {
LABEL_2062:
      v700 = v699;
    }
    if ( v698 != v700 )
      break;
    ++v696;
    ++v695;
    if ( !v698 )
      goto LABEL_2047;
  }
  v701 = L"IsKoreanAuxCombine";
  v702 = v5;
  while ( 1 )
  {
    v703 = *v702;
    if ( (*v702 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v703) & 0x100000) == 0 )
        goto LABEL_2077;
      v704 = ConvertCaseHighUnicode(v703, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v703) & 1) == 0
           || (v704 = v703 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v703 + 32)) & 2) == 0) )
    {
LABEL_2077:
      v704 = v703;
    }
    v705 = *v701;
    if ( (*v701 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v705) & 0x100000) == 0 )
        goto LABEL_2080;
      v706 = ConvertCaseHighUnicode(v705, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v705) & 1) == 0
           || (v706 = v705 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v705 + 32)) & 2) == 0) )
    {
LABEL_2080:
      v706 = v705;
    }
    if ( v704 != v706 )
      break;
    ++v702;
    ++v701;
    if ( !v704 )
    {
LABEL_2083:
      *((_BYTE *)this + 309) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v707 = L"KoreanAuxCombine";
  v708 = v5;
  while ( 1 )
  {
    v709 = *v708;
    if ( (*v708 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v709) & 0x100000) == 0 )
        goto LABEL_2095;
      v710 = ConvertCaseHighUnicode(v709, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v709) & 1) == 0
           || (v710 = v709 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v709 + 32)) & 2) == 0) )
    {
LABEL_2095:
      v710 = v709;
    }
    v711 = *v707;
    if ( (*v707 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v711) & 0x100000) == 0 )
        goto LABEL_2098;
      v712 = ConvertCaseHighUnicode(v711, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v711) & 1) == 0
           || (v712 = v711 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v711 + 32)) & 2) == 0) )
    {
LABEL_2098:
      v712 = v711;
    }
    if ( v710 != v712 )
      break;
    ++v708;
    ++v707;
    if ( !v710 )
      goto LABEL_2083;
  }
  v713 = L"IsKoreanMissSpellDictSearch";
  v714 = v5;
  while ( 1 )
  {
    v715 = *v714;
    if ( (*v714 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v715) & 0x100000) == 0 )
        goto LABEL_2113;
      v716 = ConvertCaseHighUnicode(v715, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v715) & 1) == 0
           || (v716 = v715 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v715 + 32)) & 2) == 0) )
    {
LABEL_2113:
      v716 = v715;
    }
    v717 = *v713;
    if ( (*v713 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v717) & 0x100000) == 0 )
        goto LABEL_2116;
      v718 = ConvertCaseHighUnicode(v717, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v717) & 1) == 0
           || (v718 = v717 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v717 + 32)) & 2) == 0) )
    {
LABEL_2116:
      v718 = v717;
    }
    if ( v716 != v718 )
      break;
    ++v714;
    ++v713;
    if ( !v716 )
    {
LABEL_2119:
      *((_BYTE *)this + 310) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v719 = L"KoreanMissSpellDictSearch";
  v720 = v5;
  while ( 1 )
  {
    v721 = *v720;
    if ( (*v720 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v721) & 0x100000) == 0 )
        goto LABEL_2131;
      v722 = ConvertCaseHighUnicode(v721, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v721) & 1) == 0
           || (v722 = v721 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v721 + 32)) & 2) == 0) )
    {
LABEL_2131:
      v722 = v721;
    }
    v723 = *v719;
    if ( (*v719 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v723) & 0x100000) == 0 )
        goto LABEL_2134;
      v724 = ConvertCaseHighUnicode(v723, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v723) & 1) == 0
           || (v724 = v723 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v723 + 32)) & 2) == 0) )
    {
LABEL_2134:
      v724 = v723;
    }
    if ( v722 != v724 )
      break;
    ++v720;
    ++v719;
    if ( !v722 )
      goto LABEL_2119;
  }
  v725 = L"IsKoreanCompoundNounProc";
  v726 = v5;
  while ( 1 )
  {
    v727 = *v726;
    if ( (*v726 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v727) & 0x100000) == 0 )
        goto LABEL_2149;
      v728 = ConvertCaseHighUnicode(v727, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v727) & 1) == 0
           || (v728 = v727 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v727 + 32)) & 2) == 0) )
    {
LABEL_2149:
      v728 = v727;
    }
    v729 = *v725;
    if ( (*v725 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v729) & 0x100000) == 0 )
        goto LABEL_2152;
      v730 = ConvertCaseHighUnicode(v729, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v729) & 1) == 0
           || (v730 = v729 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v729 + 32)) & 2) == 0) )
    {
LABEL_2152:
      v730 = v729;
    }
    if ( v728 != v730 )
      break;
    ++v726;
    ++v725;
    if ( !v728 )
    {
LABEL_2155:
      *((_BYTE *)this + 311) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v731 = L"KoreanCompoundNounProc";
  v732 = v5;
  while ( 1 )
  {
    v733 = *v732;
    if ( (*v732 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v733) & 0x100000) == 0 )
        goto LABEL_2167;
      v734 = ConvertCaseHighUnicode(v733, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v733) & 1) == 0
           || (v734 = v733 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v733 + 32)) & 2) == 0) )
    {
LABEL_2167:
      v734 = v733;
    }
    v735 = *v731;
    if ( (*v731 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v735) & 0x100000) == 0 )
        goto LABEL_2170;
      v736 = ConvertCaseHighUnicode(v735, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v735) & 1) == 0
           || (v736 = v735 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v735 + 32)) & 2) == 0) )
    {
LABEL_2170:
      v736 = v735;
    }
    if ( v734 != v736 )
      break;
    ++v732;
    ++v731;
    if ( !v734 )
      goto LABEL_2155;
  }
  v737 = L"IsArabicStrictAlefHamza";
  v738 = v5;
  while ( 1 )
  {
    v739 = *v738;
    if ( (*v738 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v739) & 0x100000) == 0 )
        goto LABEL_2185;
      v740 = ConvertCaseHighUnicode(v739, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v739) & 1) == 0
           || (v740 = v739 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v739 + 32)) & 2) == 0) )
    {
LABEL_2185:
      v740 = v739;
    }
    v741 = *v737;
    if ( (*v737 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v741) & 0x100000) == 0 )
        goto LABEL_2188;
      v742 = ConvertCaseHighUnicode(v741, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v741) & 1) == 0
           || (v742 = v741 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v741 + 32)) & 2) == 0) )
    {
LABEL_2188:
      v742 = v741;
    }
    if ( v740 != v742 )
      break;
    ++v738;
    ++v737;
    if ( !v740 )
    {
LABEL_2191:
      *((_BYTE *)this + 312) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v743 = L"ArabicStrictAlefHamza";
  v744 = v5;
  while ( 1 )
  {
    v745 = *v744;
    if ( (*v744 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v745) & 0x100000) == 0 )
        goto LABEL_2203;
      v746 = ConvertCaseHighUnicode(v745, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v745) & 1) == 0
           || (v746 = v745 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v745 + 32)) & 2) == 0) )
    {
LABEL_2203:
      v746 = v745;
    }
    v747 = *v743;
    if ( (*v743 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v747) & 0x100000) == 0 )
        goto LABEL_2206;
      v748 = ConvertCaseHighUnicode(v747, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v747) & 1) == 0
           || (v748 = v747 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v747 + 32)) & 2) == 0) )
    {
LABEL_2206:
      v748 = v747;
    }
    if ( v746 != v748 )
      break;
    ++v744;
    ++v743;
    if ( !v746 )
      goto LABEL_2191;
  }
  v749 = L"IsArabicStrictFinalYaa";
  v750 = v5;
  while ( 1 )
  {
    v751 = *v750;
    if ( (*v750 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v751) & 0x100000) == 0 )
        goto LABEL_2221;
      v752 = ConvertCaseHighUnicode(v751, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v751) & 1) == 0
           || (v752 = v751 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v751 + 32)) & 2) == 0) )
    {
LABEL_2221:
      v752 = v751;
    }
    v753 = *v749;
    if ( (*v749 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v753) & 0x100000) == 0 )
        goto LABEL_2224;
      v754 = ConvertCaseHighUnicode(v753, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v753) & 1) == 0
           || (v754 = v753 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v753 + 32)) & 2) == 0) )
    {
LABEL_2224:
      v754 = v753;
    }
    if ( v752 != v754 )
      break;
    ++v750;
    ++v749;
    if ( !v752 )
    {
LABEL_2227:
      *((_BYTE *)this + 313) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v755 = L"ArabicStrictFinalYaa";
  v756 = v5;
  while ( 1 )
  {
    v757 = *v756;
    if ( (*v756 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v757) & 0x100000) == 0 )
        goto LABEL_2239;
      v758 = ConvertCaseHighUnicode(v757, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v757) & 1) == 0
           || (v758 = v757 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v757 + 32)) & 2) == 0) )
    {
LABEL_2239:
      v758 = v757;
    }
    v759 = *v755;
    if ( (*v755 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v759) & 0x100000) == 0 )
        goto LABEL_2242;
      v760 = ConvertCaseHighUnicode(v759, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v759) & 1) == 0
           || (v760 = v759 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v759 + 32)) & 2) == 0) )
    {
LABEL_2242:
      v760 = v759;
    }
    if ( v758 != v760 )
      break;
    ++v756;
    ++v755;
    if ( !v758 )
      goto LABEL_2227;
  }
  v761 = L"IsHebrewPartialScript";
  v762 = v5;
  while ( 1 )
  {
    v763 = *v762;
    if ( (*v762 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v763) & 0x100000) == 0 )
        goto LABEL_2257;
      v764 = ConvertCaseHighUnicode(v763, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v763) & 1) == 0
           || (v764 = v763 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v763 + 32)) & 2) == 0) )
    {
LABEL_2257:
      v764 = v763;
    }
    v765 = *v761;
    if ( (*v761 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v765) & 0x100000) == 0 )
        goto LABEL_2260;
      v766 = ConvertCaseHighUnicode(v765, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v765) & 1) == 0
           || (v766 = v765 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v765 + 32)) & 2) == 0) )
    {
LABEL_2260:
      v766 = v765;
    }
    if ( v764 != v766 )
      break;
    ++v762;
    ++v761;
    if ( !v764 )
    {
LABEL_2263:
      *((_BYTE *)this + 314) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v767 = L"HebrewPartialScript";
  v768 = v5;
  while ( 1 )
  {
    v769 = *v768;
    if ( (*v768 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v769) & 0x100000) == 0 )
        goto LABEL_2275;
      v770 = ConvertCaseHighUnicode(v769, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v769) & 1) == 0
           || (v770 = v769 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v769 + 32)) & 2) == 0) )
    {
LABEL_2275:
      v770 = v769;
    }
    v771 = *v767;
    if ( (*v767 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v771) & 0x100000) == 0 )
        goto LABEL_2278;
      v772 = ConvertCaseHighUnicode(v771, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v771) & 1) == 0
           || (v772 = v771 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v771 + 32)) & 2) == 0) )
    {
LABEL_2278:
      v772 = v771;
    }
    if ( v770 != v772 )
      break;
    ++v768;
    ++v767;
    if ( !v770 )
      goto LABEL_2263;
  }
  v773 = L"IsHebrewMixedScript";
  v774 = v5;
  while ( 1 )
  {
    v775 = *v774;
    if ( (*v774 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v775) & 0x100000) == 0 )
        goto LABEL_2293;
      v776 = ConvertCaseHighUnicode(v775, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v775) & 1) == 0
           || (v776 = v775 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v775 + 32)) & 2) == 0) )
    {
LABEL_2293:
      v776 = v775;
    }
    v777 = *v773;
    if ( (*v773 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v777) & 0x100000) == 0 )
        goto LABEL_2296;
      v778 = ConvertCaseHighUnicode(v777, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v777) & 1) == 0
           || (v778 = v777 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v777 + 32)) & 2) == 0) )
    {
LABEL_2296:
      v778 = v777;
    }
    if ( v776 != v778 )
      break;
    ++v774;
    ++v773;
    if ( !v776 )
    {
LABEL_2299:
      *((_BYTE *)this + 315) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v779 = L"HebrewMixedScript";
  v780 = v5;
  while ( 1 )
  {
    v781 = *v780;
    if ( (*v780 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v781) & 0x100000) == 0 )
        goto LABEL_2311;
      v782 = ConvertCaseHighUnicode(v781, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v781) & 1) == 0
           || (v782 = v781 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v781 + 32)) & 2) == 0) )
    {
LABEL_2311:
      v782 = v781;
    }
    v783 = *v779;
    if ( (*v779 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v783) & 0x100000) == 0 )
        goto LABEL_2314;
      v784 = ConvertCaseHighUnicode(v783, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v783) & 1) == 0
           || (v784 = v783 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v783 + 32)) & 2) == 0) )
    {
LABEL_2314:
      v784 = v783;
    }
    if ( v782 != v784 )
      break;
    ++v780;
    ++v779;
    if ( !v782 )
      goto LABEL_2299;
  }
  v785 = L"GermanReform";
  for ( j = v5; ; ++j )
  {
    v787 = *j;
    if ( (*j & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v787) & 0x100000) == 0 )
        goto LABEL_2329;
      v788 = ConvertCaseHighUnicode(v787, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v787) & 1) == 0
           || (v788 = v787 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v787 + 32)) & 2) == 0) )
    {
LABEL_2329:
      v788 = v787;
    }
    v789 = *v785;
    if ( (*v785 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v789) & 0x100000) == 0 )
        goto LABEL_2332;
      v790 = ConvertCaseHighUnicode(v789, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v789) & 1) == 0
           || (v790 = v789 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v789 + 32)) & 2) == 0) )
    {
LABEL_2332:
      v790 = v789;
    }
    if ( v788 != v790 )
      break;
    ++v785;
    if ( !v788 )
    {
      v791 = _variant_t::operator long(a3);
      CContextBase::SetGermanReform(this, v791);
      return 1;
    }
  }
  v792 = L"IsReturnAutoReplace";
  v793 = v5;
  while ( 1 )
  {
    v794 = *v793;
    if ( (*v793 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v794) & 0x100000) == 0 )
        goto LABEL_2347;
      v795 = ConvertCaseHighUnicode(v794, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v794) & 1) == 0
           || (v795 = v794 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v794 + 32)) & 2) == 0) )
    {
LABEL_2347:
      v795 = v794;
    }
    v796 = *v792;
    if ( (*v792 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v796) & 0x100000) == 0 )
        goto LABEL_2350;
      v797 = ConvertCaseHighUnicode(v796, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v796) & 1) == 0
           || (v797 = v796 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v796 + 32)) & 2) == 0) )
    {
LABEL_2350:
      v797 = v796;
    }
    if ( v795 != v797 )
      break;
    ++v793;
    ++v792;
    if ( !v795 )
    {
LABEL_2353:
      *((_BYTE *)this + 320) = _variant_t::operator bool(a3);
      return 1;
    }
  }
  v798 = L"ReturnAutoReplace";
  while ( 1 )
  {
    v799 = *v5;
    if ( (*v5 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v799) & 0x100000) == 0 )
        goto LABEL_2365;
      v800 = ConvertCaseHighUnicode(v799, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v799) & 1) == 0
           || (v800 = v799 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v799 + 32)) & 2) == 0) )
    {
LABEL_2365:
      v800 = v799;
    }
    v801 = *v798;
    if ( (*v798 & 0xFF00) != 0 )
    {
      if ( (UlGetTypeFlags(v801) & 0x100000) == 0 )
        goto LABEL_2368;
      v802 = ConvertCaseHighUnicode(v801, 0xFFFFFFFFLL, 0x200000);
    }
    else if ( (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v801) & 1) == 0
           || (v802 = v801 + 32, (*((_BYTE *)k_rgbLexTab1 + (unsigned __int8)(v801 + 32)) & 2) == 0) )
    {
LABEL_2368:
      v802 = v801;
    }
    if ( v800 != v802 )
      return 0;
    ++v5;
    ++v798;
    if ( !v800 )
      goto LABEL_2353;
  }
}

```

## disassembly

```asm
0x18001a640  push    rbx
0x18001a642  push    rbp
0x18001a643  push    rsi
0x18001a644  push    rdi
0x18001a645  push    r12
0x18001a647  push    r13
0x18001a649  push    r14
0x18001a64b  push    r15
0x18001a64d  sub     rsp, 68h
0x18001a651  mov     r13, r8
0x18001a654  lea     r14, aMaxsentences; "MaxSentences"
0x18001a65b  mov     rbp, rdx
0x18001a65e  lea     r15, k_rgbLexTab1
0x18001a665  mov     r12, rcx
0x18001a668  mov     rsi, rdx
0x18001a66b  mov     eax, 0FF00h
0x18001a670  movzx   ebx, word ptr [rsi]
0x18001a673  test    ax, bx
0x18001a676  jnz     loc_18001A702
0x18001a67c  movzx   eax, bl
0x18001a67f  test    byte ptr [rax+r15], 1
0x18001a684  jnz     short loc_18001A6E3
0x18001a686  movzx   edi, bx
0x18001a689  movzx   ebx, word ptr [r14]
0x18001a68d  mov     eax, 0FF00h
0x18001a692  test    ax, bx
0x18001a695  jnz     loc_18001A72F
0x18001a69b  movzx   eax, bl
0x18001a69e  test    byte ptr [rax+r15], 1
0x18001a6a3  jnz     short loc_18001A6F3
0x18001a6a5  movzx   ecx, bx
0x18001a6a8  cmp     di, cx
0x18001a6ab  jnz     loc_18001A75C
0x18001a6b1  add     rsi, 2
0x18001a6b5  add     r14, 2
0x18001a6b9  mov     eax, 0FF00h
0x18001a6be  test    di, di
0x18001a6c1  jnz     short loc_18001A670
0x18001a6c3  mov     rcx, r13; struct _variant_t *
0x18001a6c6  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x18001a6cb  cmp     eax, 1
0x18001a6ce  jl      loc_180021B8D
0x18001a6d4  mov     [r12+0Ch], eax
0x18001a6d9  inc     dword ptr [r12+8]
0x18001a6de  jmp     loc_18001AA77
0x18001a6e3  lea     edi, [rbx+20h]
0x18001a6e6  movzx   eax, dil
0x18001a6ea  test    byte ptr [rax+r15], 2
0x18001a6ef  jnz     short loc_18001A689
0x18001a6f1  jmp     short loc_18001A686
0x18001a6f3  lea     ecx, [rbx+20h]
0x18001a6f6  movzx   eax, cl
0x18001a6f9  test    byte ptr [rax+r15], 2
0x18001a6fe  jnz     short loc_18001A6A8
0x18001a700  jmp     short loc_18001A6A5
0x18001a702  movzx   ecx, bx
0x18001a705  call    _UlGetTypeFlags
0x18001a70a  bt      eax, 14h
0x18001a70e  jnb     loc_18001A686
0x18001a714  mov     edx, 0FFFFFFFFh
0x18001a719  mov     r8d, 200000h
0x18001a71f  movzx   ecx, bx
0x18001a722  call    ConvertCaseHighUnicode
0x18001a727  movzx   edi, ax
0x18001a72a  jmp     loc_18001A689
0x18001a72f  movzx   ecx, bx
0x18001a732  call    _UlGetTypeFlags
0x18001a737  bt      eax, 14h
0x18001a73b  jnb     loc_18001A6A5
0x18001a741  mov     edx, 0FFFFFFFFh
0x18001a746  mov     r8d, 200000h
0x18001a74c  movzx   ecx, bx
0x18001a74f  call    ConvertCaseHighUnicode
0x18001a754  movzx   ecx, ax
0x18001a757  jmp     loc_18001A6A8
0x18001a75c  lea     r14, aNldpSentenceCo; "NLDP_SENTENCE_COUNT"
0x18001a763  mov     rsi, rbp
0x18001a766  nop     word ptr [rax+rax+00000000h]
0x18001a770  movzx   ebx, word ptr [rsi]
0x18001a773  mov     eax, 0FF00h
0x18001a778  test    ax, bx
0x18001a77b  jnz     short loc_18001A7DF
0x18001a77d  movzx   eax, bl
0x18001a780  test    byte ptr [rax+r15], 1
0x18001a785  jnz     short loc_18001A7C0
0x18001a787  movzx   edi, bx
0x18001a78a  movzx   ebx, word ptr [r14]
0x18001a78e  mov     eax, 0FF00h
0x18001a793  test    ax, bx
0x18001a796  jnz     short loc_18001A805
0x18001a798  movzx   eax, bl
0x18001a79b  test    byte ptr [rax+r15], 1
0x18001a7a0  jnz     short loc_18001A7D0
0x18001a7a2  movzx   ecx, bx
0x18001a7a5  cmp     di, cx
0x18001a7a8  jnz     loc_18001A82E
0x18001a7ae  add     rsi, 2
0x18001a7b2  add     r14, 2
0x18001a7b6  test    di, di
0x18001a7b9  jnz     short loc_18001A770
0x18001a7bb  jmp     loc_18001A6C3
0x18001a7c0  lea     edi, [rbx+20h]
0x18001a7c3  movzx   eax, dil
0x18001a7c7  test    byte ptr [rax+r15], 2
0x18001a7cc  jnz     short loc_18001A78A
0x18001a7ce  jmp     short loc_18001A787
0x18001a7d0  lea     ecx, [rbx+20h]
0x18001a7d3  movzx   eax, cl
0x18001a7d6  test    byte ptr [rax+r15], 2
0x18001a7db  jnz     short loc_18001A7A5
0x18001a7dd  jmp     short loc_18001A7A2
0x18001a7df  movzx   ecx, bx
0x18001a7e2  call    _UlGetTypeFlags
0x18001a7e7  bt      eax, 14h
0x18001a7eb  jnb     short loc_18001A787
0x18001a7ed  mov     edx, 0FFFFFFFFh
0x18001a7f2  mov     r8d, 200000h
0x18001a7f8  movzx   ecx, bx
0x18001a7fb  call    ConvertCaseHighUnicode
0x18001a800  movzx   edi, ax
0x18001a803  jmp     short loc_18001A78A
0x18001a805  movzx   ecx, bx
0x18001a808  call    _UlGetTypeFlags
0x18001a80d  bt      eax, 14h
0x18001a811  jnb     short loc_18001A7A2
0x18001a813  mov     edx, 0FFFFFFFFh
0x18001a818  mov     r8d, 200000h
0x18001a81e  movzx   ecx, bx
0x18001a821  call    ConvertCaseHighUnicode
0x18001a826  movzx   ecx, ax
0x18001a829  jmp     loc_18001A7A5
0x18001a82e  lea     r14, aNsents; "NSents"
0x18001a835  mov     rsi, rbp
0x18001a838  nop     dword ptr [rax+rax+00000000h]
0x18001a840  movzx   ebx, word ptr [rsi]
0x18001a843  mov     eax, 0FF00h
0x18001a848  test    ax, bx
0x18001a84b  jnz     short loc_18001A8AF
0x18001a84d  movzx   eax, bl
0x18001a850  test    byte ptr [rax+r15], 1
0x18001a855  jnz     short loc_18001A890
0x18001a857  movzx   edi, bx
0x18001a85a  movzx   ebx, word ptr [r14]
0x18001a85e  mov     eax, 0FF00h
0x18001a863  test    ax, bx
0x18001a866  jnz     short loc_18001A8D5
0x18001a868  movzx   eax, bl
0x18001a86b  test    byte ptr [rax+r15], 1
0x18001a870  jnz     short loc_18001A8A0
0x18001a872  movzx   ecx, bx
0x18001a875  cmp     di, cx
0x18001a878  jnz     loc_18001A8FE
0x18001a87e  add     rsi, 2
0x18001a882  add     r14, 2
0x18001a886  test    di, di
0x18001a889  jnz     short loc_18001A840
0x18001a88b  jmp     loc_18001A6C3
0x18001a890  lea     edi, [rbx+20h]
0x18001a893  movzx   eax, dil
0x18001a897  test    byte ptr [rax+r15], 2
0x18001a89c  jnz     short loc_18001A85A
0x18001a89e  jmp     short loc_18001A857
0x18001a8a0  lea     ecx, [rbx+20h]
0x18001a8a3  movzx   eax, cl
0x18001a8a6  test    byte ptr [rax+r15], 2
0x18001a8ab  jnz     short loc_18001A875
0x18001a8ad  jmp     short loc_18001A872
0x18001a8af  movzx   ecx, bx
0x18001a8b2  call    _UlGetTypeFlags
0x18001a8b7  bt      eax, 14h
0x18001a8bb  jnb     short loc_18001A857
0x18001a8bd  mov     edx, 0FFFFFFFFh
0x18001a8c2  mov     r8d, 200000h
0x18001a8c8  movzx   ecx, bx
0x18001a8cb  call    ConvertCaseHighUnicode
0x18001a8d0  movzx   edi, ax
0x18001a8d3  jmp     short loc_18001A85A
0x18001a8d5  movzx   ecx, bx
0x18001a8d8  call    _UlGetTypeFlags
0x18001a8dd  bt      eax, 14h
0x18001a8e1  jnb     short loc_18001A872
0x18001a8e3  mov     edx, 0FFFFFFFFh
0x18001a8e8  mov     r8d, 200000h
0x18001a8ee  movzx   ecx, bx
0x18001a8f1  call    ConvertCaseHighUnicode
0x18001a8f6  movzx   ecx, ax
0x18001a8f9  jmp     loc_18001A875
0x18001a8fe  lea     r14, aIssinglelangua; "IsSingleLanguage"
0x18001a905  mov     rsi, rbp
0x18001a908  nop     dword ptr [rax+rax+00000000h]
0x18001a910  movzx   ebx, word ptr [rsi]
0x18001a913  mov     eax, 0FF00h
0x18001a918  test    ax, bx
0x18001a91b  jnz     short loc_18001A997
0x18001a91d  movzx   eax, bl
0x18001a920  test    byte ptr [rax+r15], 1
0x18001a925  jnz     short loc_18001A978
0x18001a927  movzx   edi, bx
0x18001a92a  movzx   ebx, word ptr [r14]
0x18001a92e  mov     eax, 0FF00h
0x18001a933  test    ax, bx
0x18001a936  jnz     loc_18001A9C0
0x18001a93c  movzx   eax, bl
0x18001a93f  test    byte ptr [rax+r15], 1
0x18001a944  jnz     short loc_18001A988
0x18001a946  movzx   ecx, bx
0x18001a949  cmp     di, cx
0x18001a94c  jnz     loc_18001AB00
0x18001a952  add     rsi, 2
0x18001a956  add     r14, 2
0x18001a95a  test    di, di
0x18001a95d  jnz     short loc_18001A910
0x18001a95f  mov     rcx, r13; struct _variant_t *
0x18001a962  call    ??B_variant_t@@QEBA_NXZ; _variant_t::operator bool(void)
0x18001a967  mov     [r12+10h], al
0x18001a96c  mov     al, 1
0x18001a96e  inc     dword ptr [r12+8]
0x18001a973  jmp     loc_18001AA79
0x18001a978  lea     edi, [rbx+20h]
0x18001a97b  movzx   eax, dil
0x18001a97f  test    byte ptr [rax+r15], 2
0x18001a984  jnz     short loc_18001A92A
0x18001a986  jmp     short loc_18001A927
0x18001a988  lea     ecx, [rbx+20h]
0x18001a98b  movzx   eax, cl
0x18001a98e  test    byte ptr [rax+r15], 2
0x18001a993  jnz     short loc_18001A949
0x18001a995  jmp     short loc_18001A946
0x18001a997  movzx   ecx, bx
0x18001a99a  call    _UlGetTypeFlags
0x18001a99f  bt      eax, 14h
0x18001a9a3  jnb     short loc_18001A927
0x18001a9a5  mov     edx, 0FFFFFFFFh
0x18001a9aa  mov     r8d, 200000h
0x18001a9b0  movzx   ecx, bx
0x18001a9b3  call    ConvertCaseHighUnicode
0x18001a9b8  movzx   edi, ax
0x18001a9bb  jmp     loc_18001A92A
0x18001a9c0  movzx   ecx, bx
0x18001a9c3  call    _UlGetTypeFlags
0x18001a9c8  bt      eax, 14h
0x18001a9cc  jnb     loc_18001A946
0x18001a9d2  mov     edx, 0FFFFFFFFh
0x18001a9d7  mov     r8d, 200000h
0x18001a9dd  movzx   ecx, bx
0x18001a9e0  call    ConvertCaseHighUnicode
0x18001a9e5  movzx   ecx, ax
0x18001a9e8  jmp     loc_18001A949
0x18001a9ed  lea     r14, aIscaching; "IsCaching"
0x18001a9f4  mov     rsi, rbp
0x18001a9f7  mov     r15d, 0FF00h
0x18001a9fd  nop     dword ptr [rax]
0x18001aa00  movzx   edi, word ptr [rsi]
0x18001aa03  test    r15w, di
0x18001aa07  jnz     loc_18001AAA6
0x18001aa0d  movzx   eax, dil
0x18001aa11  lea     rcx, k_rgbLexTab1
0x18001aa18  test    byte ptr [rax+rcx], 1
0x18001aa1c  jnz     short loc_18001AA8A
0x18001aa1e  movzx   ebx, di
0x18001aa21  movzx   edi, word ptr [r14]
0x18001aa25  test    r15w, di
0x18001aa29  jnz     loc_18001AAD3
0x18001aa2f  movzx   eax, dil
0x18001aa33  lea     rdx, k_rgbLexTab1
0x18001aa3a  test    byte ptr [rax+rdx], 1
0x18001aa3e  jnz     short loc_18001AA98
0x18001aa40  movzx   ecx, di
0x18001aa43  cmp     bx, cx
0x18001aa46  jnz     loc_18001B131
0x18001aa4c  add     rsi, 2
0x18001aa50  add     r14, 2
0x18001aa54  test    bx, bx
0x18001aa57  jnz     short loc_18001AA00
0x18001aa59  mov     rax, [r12]
0x18001aa5d  mov     rbx, [rax+8]
0x18001aa61  mov     rcx, r13; struct _variant_t *
0x18001aa64  call    ??B_variant_t@@QEBA_NXZ; _variant_t::operator bool(void)
0x18001aa69  movzx   edx, al
0x18001aa6c  mov     rcx, r12
0x18001aa6f  mov     rax, rbx
0x18001aa72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa77  mov     al, 1
0x18001aa79  add     rsp, 68h
0x18001aa7d  pop     r15
0x18001aa7f  pop     r14
0x18001aa81  pop     r13
0x18001aa83  pop     r12
0x18001aa85  pop     rdi
0x18001aa86  pop     rsi
0x18001aa87  pop     rbp
0x18001aa88  pop     rbx
0x18001aa89  retn
0x18001aa8a  lea     ebx, [rdi+20h]
0x18001aa8d  movzx   eax, bl
0x18001aa90  test    byte ptr [rax+rcx], 2
0x18001aa94  jnz     short loc_18001AA21
0x18001aa96  jmp     short loc_18001AA1E
0x18001aa98  lea     ecx, [rdi+20h]
0x18001aa9b  movzx   eax, cl
  ... truncated ...
```
