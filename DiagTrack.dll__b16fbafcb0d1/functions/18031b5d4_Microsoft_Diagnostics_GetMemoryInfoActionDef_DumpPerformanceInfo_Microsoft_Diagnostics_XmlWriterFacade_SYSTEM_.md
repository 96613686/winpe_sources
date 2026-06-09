# Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(Microsoft::Diagnostics::XmlWriterFacade &,_SYSTEM_PERFORMANCE_INFORMATION const &,_PERFORMANCE_INFORMATION const &,_EDP_ENFORCEMENT_LEVEL)

- ea: `0x18031b5d4`
- end: `0x18031cca8`
- name: `?DumpPerformanceInfo@GetMemoryInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@AEBU_SYSTEM_PERFORMANCE_INFORMATION@@AEBU_PERFORMANCE_INFORMATION@@W4_EDP_ENFORCEMENT_LEVEL@@@Z`
- size: `5844`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18031ea00`

## callees

- `0x18001a8f0`
- `0x18001b24c`
- `0x18002b318`
- `0x180312c78`
- `0x18031310c`
- `0x18031321c`

## string_xrefs

- `0x18031b6ff`: `IoReadOperationCount`
- `0x18031b73f`: `IoWriteOperationCount`
- `0x18031b5f4`: `systemperformanceinfo`
- `0x18031b68f`: `IoWriteTransferCount`
- `0x18031b657`: `IoReadTransferCount`
- `0x18031b8ed`: `CopyOnWriteCount`
- `0x18031b967`: `CacheTransitionCount`
- `0x18031b7f6`: `CommittedPages`
- `0x18031b873`: `PeakCommitment`
- `0x18031b833`: `CommitLimit`
- `0x18031bb12`: `DirtyWriteIoCount`
- `0x18031bad5`: `DirtyPagesWriteCount`
- `0x18031bb8c`: `MappedWriteIoCount`
- `0x18031bb4f`: `MappedPagesWriteCount`
- `0x18031ba1e`: `PageReadIoCount`
- `0x18031b9e1`: `PageReadCount`
- `0x18031ba98`: `CacheIoCount`
- `0x18031ba5b`: `CacheReadCount`
- `0x18031bd7d`: `ResidentSystemCodePage`
- `0x18031bd3d`: `FreeSystemPtes`
- `0x18031befd`: `ResidentSystemCachePage`
- `0x18031bf7d`: `ResidentSystemDriverPage`
- `0x18031bf3d`: `ResidentPagedPoolPage`
- `0x18031be7d`: `PagedPoolLookasideHits`
- `0x18031be3d`: `NonPagedPoolLookasideHits`
- `0x18031c0fd`: `CcFastMdlReadWait`
- `0x18031c0bd`: `CcFastMdlReadNoWait`
- `0x18031c17d`: `CcFastMdlReadNotPossible`
- `0x18031c13d`: `CcFastMdlReadResourceMiss`
- `0x18031bffd`: `CcFastReadWait`
- `0x18031bfbd`: `CcFastReadNoWait`
- `0x18031c07d`: `CcFastReadNotPossible`
- `0x18031c03d`: `CcFastReadResourceMiss`
- `0x18031c2fd`: `CcPinReadNoWait`
- `0x18031c37d`: `CcPinReadNoWaitMiss`
- `0x18031c33d`: `CcPinReadWait`
- `0x18031c4fd`: `CcMdlReadNoWait`
- `0x18031c4bd`: `CcCopyReadWaitMiss`
- `0x18031c57d`: `CcMdlReadNoWaitMiss`
- `0x18031c53d`: `CcMdlReadWait`
- `0x18031c3fd`: `CcCopyReadNoWait`
- `0x18031c3bd`: `CcPinReadWaitMiss`
- `0x18031c47d`: `CcCopyReadNoWaitMiss`
- `0x18031c43d`: `CcCopyReadWait`
- `0x18031c5fd`: `CcReadAheadIos`
- `0x18031c5bd`: `CcMdlReadWaitMiss`
- `0x18031c67d`: `CcLazyWritePages`
- `0x18031c63d`: `CcLazyWriteIos`
- `0x18031c938`: `CommitTotal`
- `0x18031c8f8`: `SharedCommittedPages`
- `0x18031c9ae`: `CommitPeak`
- `0x18031c8bd`: `ResidentAvailablePages`
- `0x18031cc10`: `ThreadCount`
- `0x18031ca65`: `SystemCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::GetMemoryInfoActionDef::DumpPerformanceInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // esi
  int v5; // edi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // r9
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // r9
  __int64 v98; // rdx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // rdx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // r9
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // rdx
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 v122; // rdx
  __int64 v123; // r8
  __int64 v124; // r9
  __int64 v125; // rdx
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // rdx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rdx
  __int64 v132; // r8
  __int64 v133; // r9
  __int64 v134; // rdx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rdx
  __int64 v138; // r8
  __int64 v139; // r9
  __int64 v140; // rdx
  __int64 v141; // r8
  __int64 v142; // r9
  __int64 v143; // rdx
  __int64 v144; // r8
  __int64 v145; // r9
  __int64 v146; // rdx
  __int64 v147; // r8
  __int64 v148; // r9
  __int64 v149; // rdx
  __int64 v150; // r8
  __int64 v151; // r9
  __int64 v152; // rdx
  __int64 v153; // r8
  __int64 v154; // r9
  __int64 v155; // rdx
  __int64 v156; // r8
  __int64 v157; // r9
  __int64 v158; // rdx
  __int64 v159; // r8
  __int64 v160; // r9
  __int64 v161; // rdx
  __int64 v162; // r8
  __int64 v163; // r9
  __int64 v164; // rdx
  __int64 v165; // r8
  __int64 v166; // r9
  __int64 v167; // rdx
  __int64 v168; // r8
  __int64 v169; // r9
  __int64 v170; // rdx
  __int64 v171; // r8
  __int64 v172; // r9
  __int64 v173; // rdx
  __int64 v174; // r8
  __int64 v175; // r9
  __int64 v176; // rdx
  __int64 v177; // r8
  __int64 v178; // r9
  __int64 v179; // rdx
  __int64 v180; // r8
  __int64 v181; // r9
  __int64 v182; // rdx
  __int64 v183; // r8
  __int64 v184; // r9
  __int64 v185; // rdx
  __int64 v186; // r8
  __int64 v187; // r9
  __int64 v188; // rdx
  __int64 v189; // r8
  __int64 v190; // r9
  __int64 v191; // rdx
  __int64 v192; // r8
  __int64 v193; // r9
  __int64 v194; // rdx
  __int64 v195; // r8
  __int64 v196; // r9
  __int64 v197; // rdx
  __int64 v198; // r8
  __int64 v199; // r9
  __int64 v200; // rdx
  __int64 v201; // r8
  __int64 v202; // r9
  __int64 v203; // rdx
  __int64 v204; // r8
  __int64 v205; // r9
  __int64 v206; // rdx
  __int64 v207; // r8
  __int64 v208; // r9
  __int64 v209; // rdx
  __int64 v210; // r8
  __int64 v211; // r9
  __int64 v212; // rdx
  __int64 v213; // r8
  __int64 v214; // r9
  __int64 v215; // rdx
  __int64 v216; // r8
  __int64 v217; // r9
  __int64 v218; // rdx
  __int64 v219; // r8
  __int64 v220; // r9
  __int64 v221; // rdx
  __int64 v222; // r8
  __int64 v223; // r9
  __int64 v224; // rdx
  __int64 v225; // r8
  __int64 v226; // r9
  __int64 v227; // rdx
  __int64 v228; // r8
  __int64 v229; // r9
  __int64 v230; // rdx
  __int64 v231; // r8
  __int64 v232; // r9
  __int64 v233; // rdx
  __int64 v234; // r8
  __int64 v235; // r9
  __int64 v236; // rdx
  __int64 v237; // r8
  __int64 v238; // r9
  __int64 v239; // rdx
  __int64 v240; // r8
  __int64 v241; // r9
  __int64 v242; // rdx
  __int64 v243; // r8
  __int64 v244; // r9
  __int64 v245; // rdx
  __int64 v246; // r8
  __int64 v247; // r9
  __int64 v248; // rdx
  __int64 v249; // r8
  __int64 v250; // r9
  __int64 v251; // rdx
  __int64 v252; // r8
  __int64 v253; // r9
  __int64 v254; // rdx
  __int64 v255; // r8
  __int64 v256; // r9
  __int64 v257; // rdx
  __int64 v258; // r8
  __int64 v259; // r9
  __int64 v260; // rdx
  __int64 v261; // r8
  __int64 v262; // r9
  __int64 v263; // rdx
  __int64 v264; // r8
  __int64 v265; // r9
  __int64 v266; // rdx
  __int64 v267; // r8
  __int64 v268; // r9
  __int64 v269; // rdx
  __int64 v270; // r8
  __int64 v271; // r9
  __int64 v272; // rdx
  __int64 v273; // r8
  __int64 v274; // r9
  __int64 v275; // rdx
  __int64 v276; // r8
  __int64 v277; // r9
  __int64 v278; // rdx
  __int64 v279; // r8
  __int64 v280; // r9
  __int64 v281; // rdx
  __int64 v282; // r8
  __int64 v283; // r9
  __int64 v284; // rdx
  __int64 v285; // r8
  __int64 v286; // r9
  __int64 v287; // rdx
  __int64 v288; // r8
  __int64 v289; // r9
  __int64 v290; // rdx
  __int64 v291; // r8
  __int64 v292; // r9
  __int64 v293; // rdx
  __int64 v294; // r8
  __int64 v295; // r9
  __int64 v296; // rdx
  __int64 v297; // r8
  __int64 v298; // r9
  __int64 v299; // rdx
  __int64 v300; // r8
  __int64 v301; // r9
  __int64 v302; // rdx
  __int64 v303; // r8
  __int64 v304; // r9
  __int64 v305; // rdx
  __int64 v306; // r8
  __int64 v307; // r9
  __int64 v308; // rdx
  __int64 v309; // r8
  __int64 v310; // r9
  __int64 v311; // rdx
  __int64 v312; // r8
  __int64 v313; // r9
  __int64 v314; // rdx
  __int64 v315; // r8
  __int64 v316; // r9
  __int64 v317; // rdx
  __int64 v318; // r8
  __int64 v319; // r9
  __int64 v320; // rdx
  __int64 v321; // r8
  __int64 v322; // r9
  __int64 v323; // rdx
  __int64 v324; // r8
  __int64 v325; // r9
  __int64 v326; // rdx
  __int64 v327; // r8
  __int64 v328; // r9
  __int64 v329; // rdx
  __int64 v330; // r8
  __int64 v331; // r9
  __int64 v332; // rdx
  __int64 v333; // r8
  __int64 v334; // r9
  __int64 v335; // rdx
  __int64 v336; // r8
  __int64 v337; // r9
  __int64 v338; // rdx
  __int64 v339; // r8
  __int64 v340; // r9
  __int64 v341; // rdx
  __int64 v342; // r8
  __int64 v343; // r9
  __int64 v344; // rdx
  __int64 v345; // r8
  __int64 v346; // r9
  __int64 v347; // rdx
  __int64 v348; // r8
  __int64 v349; // r9
  __int64 v350; // rdx
  __int64 v351; // r8
  __int64 v352; // r9
  __int64 v353; // rdx
  __int64 v354; // r8
  __int64 v355; // r9
  __int64 v356; // rdx
  __int64 v357; // r8
  __int64 v358; // r9
  __int64 v359; // rdx
  __int64 v360; // r8
  __int64 v361; // r9
  __int64 v362; // rdx
  __int64 v363; // r8
  __int64 v364; // r9
  __int64 v365; // rdx
  __int64 v366; // r8
  __int64 v367; // r9
  __int64 v368; // rdx
  __int64 v369; // r8
  __int64 v370; // r9
  __int64 v371; // rdx
  __int64 v372; // r8
  __int64 v373; // r9
  __int64 v374; // rdx
  __int64 v375; // r8
  __int64 v376; // r9
  __int64 v377; // rdx
  __int64 v378; // r8
  __int64 v379; // r9
  __int64 v380; // rdx
  __int64 v381; // r8
  __int64 v382; // r9
  __int64 v383; // rdx
  __int64 v384; // r8
  __int64 v385; // r9
  __int64 v386; // rdx
  __int64 v387; // r8
  __int64 v388; // r9
  __int64 v389; // rdx
  __int64 v390; // r8
  __int64 v391; // r9
  __int64 v392; // rdx
  __int64 v393; // r8
  __int64 v394; // r9
  __int64 v395; // rdx
  __int64 v396; // r8
  __int64 v397; // r9
  __int64 v398; // rdx
  __int64 v399; // r8
  __int64 v400; // r9
  __int64 v401; // rdx
  __int64 v402; // r8
  __int64 v403; // r9
  __int64 v404; // rdx
  __int64 v405; // r8
  __int64 v406; // r9
  __int64 v407; // rdx
  __int64 v408; // r8
  __int64 v409; // r9
  __int64 v410; // rdx
  __int64 v411; // r8
  __int64 v412; // r9
  __int64 v413; // rdx
  __int64 v414; // r8
  __int64 v415; // r9
  __int64 v416; // rdx
  __int64 v417; // r8
  __int64 v418; // r9
  __int64 v419; // rdx
  __int64 v420; // r8
  __int64 v421; // r9
  __int64 v422; // rdx
  __int64 v423; // r8
  __int64 v424; // r9
  __int64 v425; // rdx
  __int64 v426; // r8
  __int64 v427; // r9
  __int64 v428; // rdx
  __int64 v429; // r8
  __int64 v430; // r9
  __int64 v431; // rdx
  __int64 v432; // r8
  __int64 v433; // r9
  __int64 v434; // rdx
  __int64 v435; // r8
  __int64 v436; // r9
  __int64 v437; // rdx
  __int64 v438; // r8
  __int64 v439; // r9
  __int64 v440; // rdx
  __int64 v441; // r8
  __int64 v442; // r9
  __int64 v443; // rdx
  __int64 v444; // r8
  __int64 v445; // r9
  __int64 v446; // rdx
  __int64 v447; // r8
  __int64 v448; // r9
  __int64 v449; // rdx
  __int64 v450; // r8
  __int64 v451; // r9
  __int64 v452; // rdx
  __int64 v453; // r8
  __int64 v454; // r9
  __int64 v455; // rdx
  __int64 v456; // r8
  __int64 v457; // r9
  __int64 v458; // rdx
  __int64 v459; // r8
  __int64 v460; // r9
  __int64 v461; // rdx
  __int64 v462; // r8
  __int64 v463; // r9
  __int64 v464; // rdx
  __int64 v465; // r8
  __int64 v466; // r9
  __int64 v467; // rdx
  __int64 v468; // r8
  __int64 v469; // r9
  __int64 v470; // rdx
  __int64 v471; // r8
  __int64 v472; // r9
  __int64 v473; // rdx
  __int64 v474; // r8
  __int64 v475; // r9
  __int64 v476; // rdx
  __int64 v477; // r8
  __int64 v478; // r9
  __int64 v479; // rdx
  __int64 v480; // r8
  __int64 v481; // r9
  __int64 v482; // rdx
  __int64 v483; // r8
  __int64 v484; // r9
  __int64 v485; // rdx
  __int64 v486; // r8
  __int64 v487; // r9
  __int64 v488; // rdx
  __int64 v489; // r8
  __int64 v490; // r9
  __int64 v491; // rdx
  __int64 v492; // r8
  __int64 v493; // r9
  __int64 v494; // rdx
  __int64 v495; // r8
  __int64 v496; // r9
  __int64 v497; // rdx
  __int64 v498; // r8
  __int64 v499; // r9
  __int64 v500; // rdx
  __int64 v501; // r8
  __int64 v502; // r9
  __int64 v503; // rdx
  __int64 v504; // r8
  __int64 v505; // r9
  __int64 v506; // rdx
  __int64 v507; // r8
  __int64 v508; // r9
  __int64 v509; // rdx
  __int64 v510; // r8
  __int64 v511; // r9
  __int64 v512; // rdx
  __int64 v513; // r8
  __int64 v514; // r9
  __int64 v515; // rdx
  __int64 v516; // r8
  __int64 v517; // r9
  __int64 v518; // rdx
  __int64 v519; // r8
  __int64 v520; // r9
  __int64 v521; // rdx
  __int64 v522; // r8
  __int64 v523; // r9
  __int64 v524; // rdx
  __int64 v525; // r8
  __int64 v526; // r9
  __int64 v527; // rdx
  __int64 v528; // r8
  __int64 v529; // r9
  __int64 v530; // rdx
  __int64 v531; // r8
  __int64 v532; // r9
  __int64 v533; // rdx
  __int64 v534; // r8
  __int64 v535; // r9
  __int64 v536; // rdx
  __int64 v537; // r8
  __int64 v538; // r9
  __int64 v539; // rdx
  __int64 v540; // r8
  __int64 v541; // r9
  __int64 v542; // rdx
  __int64 v543; // r8
  __int64 v544; // r9
  __int64 v545; // rdx
  __int64 v546; // r8
  __int64 v547; // r9
  __int64 v548; // rdx
  __int64 v549; // r8
  __int64 v550; // r9
  __int64 v551; // rdx
  __int64 v552; // r8
  __int64 v553; // r9
  __int64 v554; // rdx
  __int64 v555; // r8
  __int64 v556; // r9
  __int64 v557; // rdx
  __int64 v558; // r8
  __int64 v559; // r9
  const wchar_t *v560; // [rsp+30h] [rbp-38h] BYREF
  __int64 v561; // [rsp+38h] [rbp-30h]
  const wchar_t *v562; // [rsp+40h] [rbp-28h] BYREF
  __int64 v563; // [rsp+48h] [rbp-20h]
  _BYTE v564[24]; // [rsp+50h] [rbp-18h] BYREF
  int v565; // [rsp+C8h] [rbp+60h] BYREF

  v4 = a4;
  v5 = a3;
  v560 = L"systemperformanceinfo";
  v561 = std::_WChar_traits<wchar_t>::length(L"systemperformanceinfo", a2, a3, a4);
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(a1, v564, &v560);
  v560 = L"IdleProcessTime";
  v561 = std::_WChar_traits<wchar_t>::length(L"IdleProcessTime", v8, v9, v10);
  v562 = L"info";
  v563 = std::_WChar_traits<wchar_t>::length(L"info", v11, v12, v13);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v562, &v560, a2);
  v562 = L"IoReadTransferCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoReadTransferCount", v14, v15, v16);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v17, v18, v19);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v560, &v562, a2 + 8);
  v562 = L"IoWriteTransferCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoWriteTransferCount", v20, v21, v22);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v23, v24, v25);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v560, &v562, a2 + 16);
  v562 = L"IoOtherTransferCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoOtherTransferCount", v26, v27, v28);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v29, v30, v31);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v560, &v562, a2 + 24);
  v562 = L"IoReadOperationCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoReadOperationCount", v32, v33, v34);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v35, v36, v37);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 32,
    0);
  v562 = L"IoWriteOperationCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoWriteOperationCount", v38, v39, v40);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v41, v42, v43);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 36,
    0);
  v562 = L"IoOtherOperationCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"IoOtherOperationCount", v44, v45, v46);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v47, v48, v49);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 40,
    0);
  v562 = L"AvailablePages";
  v563 = std::_WChar_traits<wchar_t>::length(L"AvailablePages", v50, v51, v52);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v53, v54, v55);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 44,
    0);
  v562 = L"CommittedPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"CommittedPages", v56, v57, v58);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v59, v60, v61);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 48,
    0);
  v562 = L"CommitLimit";
  v563 = std::_WChar_traits<wchar_t>::length(L"CommitLimit", v62, v63, v64);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v65, v66, v67);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 52,
    0);
  v562 = L"PeakCommitment";
  v563 = std::_WChar_traits<wchar_t>::length(L"PeakCommitment", v68, v69, v70);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v71, v72, v73);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 56,
    0);
  v562 = L"PageFaultCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"PageFaultCount", v74, v75, v76);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v77, v78, v79);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 60,
    0);
  v562 = L"CopyOnWriteCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"CopyOnWriteCount", v80, v81, v82);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v83, v84, v85);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 64,
    0);
  v562 = L"TransitionCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"TransitionCount", v86, v87, v88);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v89, v90, v91);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 68,
    0);
  v562 = L"CacheTransitionCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"CacheTransitionCount", v92, v93, v94);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v95, v96, v97);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 72,
    0);
  v562 = L"DemandZeroCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"DemandZeroCount", v98, v99, v100);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v101, v102, v103);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 76,
    0);
  v562 = L"PageReadCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"PageReadCount", v104, v105, v106);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v107, v108, v109);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 80,
    0);
  v562 = L"PageReadIoCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"PageReadIoCount", v110, v111, v112);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v113, v114, v115);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 84,
    0);
  v562 = L"CacheReadCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"CacheReadCount", v116, v117, v118);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v119, v120, v121);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 88,
    0);
  v562 = L"CacheIoCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"CacheIoCount", v122, v123, v124);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v125, v126, v127);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 92,
    0);
  v562 = L"DirtyPagesWriteCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"DirtyPagesWriteCount", v128, v129, v130);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v131, v132, v133);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 96,
    0);
  v562 = L"DirtyWriteIoCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"DirtyWriteIoCount", v134, v135, v136);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v137, v138, v139);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 100,
    0);
  v562 = L"MappedPagesWriteCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"MappedPagesWriteCount", v140, v141, v142);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v143, v144, v145);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 104,
    0);
  v562 = L"MappedWriteIoCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"MappedWriteIoCount", v146, v147, v148);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v149, v150, v151);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 108,
    0);
  v562 = L"PagedPoolPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"PagedPoolPages", v152, v153, v154);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v155, v156, v157);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 112,
    0);
  v562 = L"NonPagedPoolPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolPages", v158, v159, v160);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v161, v162, v163);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 116,
    0);
  v562 = L"PagedPoolAllocs";
  v563 = std::_WChar_traits<wchar_t>::length(L"PagedPoolAllocs", v164, v165, v166);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v167, v168, v169);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 120,
    0);
  v562 = L"PagedPoolFrees";
  v563 = std::_WChar_traits<wchar_t>::length(L"PagedPoolFrees", v170, v171, v172);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v173, v174, v175);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 124,
    0);
  v562 = L"NonPagedPoolAllocs";
  v563 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolAllocs", v176, v177, v178);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v179, v180, v181);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 128,
    0);
  v562 = L"NonPagedPoolFrees";
  v563 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolFrees", v182, v183, v184);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v185, v186, v187);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 132,
    0);
  v562 = L"FreeSystemPtes";
  v563 = std::_WChar_traits<wchar_t>::length(L"FreeSystemPtes", v188, v189, v190);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v191, v192, v193);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 136,
    0);
  v562 = L"ResidentSystemCodePage";
  v563 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemCodePage", v194, v195, v196);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v197, v198, v199);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 140,
    0);
  v562 = L"TotalSystemDriverPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"TotalSystemDriverPages", v200, v201, v202);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v203, v204, v205);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 144,
    0);
  v562 = L"TotalSystemCodePages";
  v563 = std::_WChar_traits<wchar_t>::length(L"TotalSystemCodePages", v206, v207, v208);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v209, v210, v211);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 148,
    0);
  v562 = L"NonPagedPoolLookasideHits";
  v563 = std::_WChar_traits<wchar_t>::length(L"NonPagedPoolLookasideHits", v212, v213, v214);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v215, v216, v217);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 152,
    0);
  v562 = L"PagedPoolLookasideHits";
  v563 = std::_WChar_traits<wchar_t>::length(L"PagedPoolLookasideHits", v218, v219, v220);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v221, v222, v223);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 156,
    0);
  v562 = L"AvailablePagedPoolPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"AvailablePagedPoolPages", v224, v225, v226);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v227, v228, v229);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 160,
    0);
  v562 = L"ResidentSystemCachePage";
  v563 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemCachePage", v230, v231, v232);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v233, v234, v235);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 164,
    0);
  v562 = L"ResidentPagedPoolPage";
  v563 = std::_WChar_traits<wchar_t>::length(L"ResidentPagedPoolPage", v236, v237, v238);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v239, v240, v241);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 168,
    0);
  v562 = L"ResidentSystemDriverPage";
  v563 = std::_WChar_traits<wchar_t>::length(L"ResidentSystemDriverPage", v242, v243, v244);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v245, v246, v247);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 172,
    0);
  v562 = L"CcFastReadNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastReadNoWait", v248, v249, v250);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v251, v252, v253);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 176,
    0);
  v562 = L"CcFastReadWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastReadWait", v254, v255, v256);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v257, v258, v259);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 180,
    0);
  v562 = L"CcFastReadResourceMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastReadResourceMiss", v260, v261, v262);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v263, v264, v265);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 184,
    0);
  v562 = L"CcFastReadNotPossible";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastReadNotPossible", v266, v267, v268);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v269, v270, v271);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 188,
    0);
  v562 = L"CcFastMdlReadNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadNoWait", v272, v273, v274);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v275, v276, v277);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 192,
    0);
  v562 = L"CcFastMdlReadWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadWait", v278, v279, v280);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v281, v282, v283);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 196,
    0);
  v562 = L"CcFastMdlReadResourceMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadResourceMiss", v284, v285, v286);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v287, v288, v289);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 200,
    0);
  v562 = L"CcFastMdlReadNotPossible";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcFastMdlReadNotPossible", v290, v291, v292);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v293, v294, v295);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 204,
    0);
  v562 = L"CcMapDataNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMapDataNoWait", v296, v297, v298);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v299, v300, v301);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 208,
    0);
  v562 = L"CcMapDataWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMapDataWait", v302, v303, v304);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v305, v306, v307);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 212,
    0);
  v562 = L"CcMapDataNoWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMapDataNoWaitMiss", v308, v309, v310);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v311, v312, v313);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 216,
    0);
  v562 = L"CcMapDataWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMapDataWaitMiss", v314, v315, v316);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v317, v318, v319);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 220,
    0);
  v562 = L"CcPinMappedDataCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcPinMappedDataCount", v320, v321, v322);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v323, v324, v325);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 224,
    0);
  v562 = L"CcPinReadNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcPinReadNoWait", v326, v327, v328);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v329, v330, v331);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 228,
    0);
  v562 = L"CcPinReadWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcPinReadWait", v332, v333, v334);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v335, v336, v337);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 232,
    0);
  v562 = L"CcPinReadNoWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcPinReadNoWaitMiss", v338, v339, v340);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v341, v342, v343);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 236,
    0);
  v562 = L"CcPinReadWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcPinReadWaitMiss", v344, v345, v346);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v347, v348, v349);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 240,
    0);
  v562 = L"CcCopyReadNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadNoWait", v350, v351, v352);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v353, v354, v355);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 244,
    0);
  v562 = L"CcCopyReadWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadWait", v356, v357, v358);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v359, v360, v361);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 248,
    0);
  v562 = L"CcCopyReadNoWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadNoWaitMiss", v362, v363, v364);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v365, v366, v367);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 252,
    0);
  v562 = L"CcCopyReadWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcCopyReadWaitMiss", v368, v369, v370);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v371, v372, v373);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 256,
    0);
  v562 = L"CcMdlReadNoWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadNoWait", v374, v375, v376);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v377, v378, v379);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 260,
    0);
  v562 = L"CcMdlReadWait";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadWait", v380, v381, v382);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v383, v384, v385);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 264,
    0);
  v562 = L"CcMdlReadNoWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadNoWaitMiss", v386, v387, v388);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v389, v390, v391);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 268,
    0);
  v562 = L"CcMdlReadWaitMiss";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcMdlReadWaitMiss", v392, v393, v394);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v395, v396, v397);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 272,
    0);
  v562 = L"CcReadAheadIos";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcReadAheadIos", v398, v399, v400);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v401, v402, v403);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 276,
    0);
  v562 = L"CcLazyWriteIos";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcLazyWriteIos", v404, v405, v406);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v407, v408, v409);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 280,
    0);
  v562 = L"CcLazyWritePages";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcLazyWritePages", v410, v411, v412);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v413, v414, v415);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 284,
    0);
  v562 = L"CcDataFlushes";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcDataFlushes", v416, v417, v418);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v419, v420, v421);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 288,
    0);
  v562 = L"CcDataPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcDataPages", v422, v423, v424);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v425, v426, v427);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 292,
    0);
  v562 = L"ContextSwitches";
  v563 = std::_WChar_traits<wchar_t>::length(L"ContextSwitches", v428, v429, v430);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v431, v432, v433);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 296,
    0);
  v562 = L"FirstLevelTbFills";
  v563 = std::_WChar_traits<wchar_t>::length(L"FirstLevelTbFills", v434, v435, v436);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v437, v438, v439);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 300,
    0);
  v562 = L"SecondLevelTbFills";
  v563 = std::_WChar_traits<wchar_t>::length(L"SecondLevelTbFills", v440, v441, v442);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v443, v444, v445);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 304,
    0);
  v562 = L"SystemCalls";
  v563 = std::_WChar_traits<wchar_t>::length(L"SystemCalls", v446, v447, v448);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v449, v450, v451);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 308,
    0);
  v562 = L"CcTotalDirtyPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcTotalDirtyPages", v452, v453, v454);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v455, v456, v457);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 312,
    0);
  v562 = L"CcDirtyPageThreshold";
  v563 = std::_WChar_traits<wchar_t>::length(L"CcDirtyPageThreshold", v458, v459, v460);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v461, v462, v463);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 320,
    0);
  v562 = L"ResidentAvailablePages";
  v563 = std::_WChar_traits<wchar_t>::length(L"ResidentAvailablePages", v464, v465, v466);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v467, v468, v469);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(a1, &v560, &v562, a2 + 328);
  v562 = L"SharedCommittedPages";
  v563 = std::_WChar_traits<wchar_t>::length(L"SharedCommittedPages", v470, v471, v472);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v473, v474, v475);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    a2 + 336,
    0);
  v562 = L"CommitTotal";
  v563 = std::_WChar_traits<wchar_t>::length(L"CommitTotal", v476, v477, v478);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v479, v480, v481);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 8,
    0);
  v562 = L"CommitLimit";
  v563 = std::_WChar_traits<wchar_t>::length(L"CommitLimit", v482, v483, v484);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v485, v486, v487);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 16,
    0);
  v562 = L"CommitPeak";
  v563 = std::_WChar_traits<wchar_t>::length(L"CommitPeak", v488, v489, v490);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v491, v492, v493);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 24,
    0);
  v562 = L"PhysicalTotal";
  v563 = std::_WChar_traits<wchar_t>::length(L"PhysicalTotal", v494, v495, v496);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v497, v498, v499);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 32,
    0);
  v562 = L"PhysicalAvailable";
  v563 = std::_WChar_traits<wchar_t>::length(L"PhysicalAvailable", v500, v501, v502);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v503, v504, v505);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 40,
    0);
  v562 = L"SystemCache";
  v563 = std::_WChar_traits<wchar_t>::length(L"SystemCache", v506, v507, v508);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v509, v510, v511);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 48,
    0);
  v562 = L"KernelTotal";
  v563 = std::_WChar_traits<wchar_t>::length(L"KernelTotal", v512, v513, v514);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v515, v516, v517);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 56,
    0);
  v562 = L"KernelPaged";
  v563 = std::_WChar_traits<wchar_t>::length(L"KernelPaged", v518, v519, v520);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v521, v522, v523);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 64,
    0);
  v562 = L"KernelNonpaged";
  v563 = std::_WChar_traits<wchar_t>::length(L"KernelNonpaged", v524, v525, v526);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v527, v528, v529);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 72,
    0);
  v562 = L"PageSize";
  v563 = std::_WChar_traits<wchar_t>::length(L"PageSize", v530, v531, v532);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v533, v534, v535);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 80,
    0);
  v562 = L"HandleCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"HandleCount", v536, v537, v538);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v539, v540, v541);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 88,
    0);
  v562 = L"ProcessCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"ProcessCount", v542, v543, v544);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v545, v546, v547);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 92,
    0);
  v562 = L"ThreadCount";
  v563 = std::_WChar_traits<wchar_t>::length(L"ThreadCount", v548, v549, v550);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v551, v552, v553);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    v5 + 96,
    0);
  v565 = v4;
  v562 = L"EdpEnforcement";
  v563 = std::_WChar_traits<wchar_t>::length(L"EdpEnforcement", v554, v555, v556);
  v560 = L"info";
  v561 = std::_WChar_traits<wchar_t>::length(L"info", v557, v558, v559);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
    a1,
    (unsigned int)&v560,
    (unsigned int)&v562,
    (unsigned int)&v565,
    0);
  Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v564);
}

```

## disassembly

```asm
0x18031b5d4  push    rbp
0x18031b5d6  push    rbx
0x18031b5d7  push    rsi
0x18031b5d8  push    rdi
0x18031b5d9  push    r12
0x18031b5db  push    r13
0x18031b5dd  push    r14
0x18031b5df  push    r15
0x18031b5e1  mov     rbp, rsp
0x18031b5e4  sub     rsp, 68h
0x18031b5e8  mov     esi, r9d
0x18031b5eb  mov     rdi, r8
0x18031b5ee  mov     rbx, rdx
0x18031b5f1  mov     r14, rcx
0x18031b5f4  lea     rcx, aSystemperforma; "systemperformanceinfo"
0x18031b5fb  mov     [rbp+var_38], rcx
0x18031b5ff  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b604  mov     [rbp+var_30], rax
0x18031b608  lea     r8, [rbp+var_38]
0x18031b60c  lea     rdx, [rbp+var_18]
0x18031b610  mov     rcx, r14
0x18031b613  call    ?CreateElement@XmlWriterFacade@Diagnostics@Microsoft@@QEAA?AVXmlWriterAutoElement@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::XmlWriterFacade::CreateElement(std::wstring_view)
0x18031b618  nop
0x18031b619  lea     rcx, aIdleprocesstim; "IdleProcessTime"
0x18031b620  mov     [rbp+var_38], rcx
0x18031b624  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b629  mov     [rbp+var_30], rax
0x18031b62d  lea     r13, aInfo_0; "info"
0x18031b634  mov     [rbp+var_28], r13
0x18031b638  mov     rcx, r13
0x18031b63b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b640  mov     [rbp+var_20], rax
0x18031b644  mov     r9, rbx
0x18031b647  lea     r8, [rbp+var_38]
0x18031b64b  lea     rdx, [rbp+var_28]
0x18031b64f  mov     rcx, r14
0x18031b652  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b657  lea     rcx, aIoreadtransfer; "IoReadTransferCount"
0x18031b65e  mov     [rbp+var_28], rcx
0x18031b662  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b667  mov     [rbp+var_20], rax
0x18031b66b  mov     [rbp+var_38], r13
0x18031b66f  mov     rcx, r13
0x18031b672  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b677  mov     [rbp+var_30], rax
0x18031b67b  lea     r9, [rbx+8]
0x18031b67f  lea     r8, [rbp+var_28]
0x18031b683  lea     rdx, [rbp+var_38]
0x18031b687  mov     rcx, r14
0x18031b68a  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b68f  lea     rcx, aIowritetransfe; "IoWriteTransferCount"
0x18031b696  mov     [rbp+var_28], rcx
0x18031b69a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b69f  mov     [rbp+var_20], rax
0x18031b6a3  mov     [rbp+var_38], r13
0x18031b6a7  mov     rcx, r13
0x18031b6aa  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6af  mov     [rbp+var_30], rax
0x18031b6b3  lea     r9, [rbx+10h]
0x18031b6b7  lea     r8, [rbp+var_28]
0x18031b6bb  lea     rdx, [rbp+var_38]
0x18031b6bf  mov     rcx, r14
0x18031b6c2  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b6c7  lea     rcx, aIoothertransfe; "IoOtherTransferCount"
0x18031b6ce  mov     [rbp+var_28], rcx
0x18031b6d2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6d7  mov     [rbp+var_20], rax
0x18031b6db  mov     [rbp+var_38], r13
0x18031b6df  mov     rcx, r13
0x18031b6e2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b6e7  mov     [rbp+var_30], rax
0x18031b6eb  lea     r9, [rbx+18h]
0x18031b6ef  lea     r8, [rbp+var_28]
0x18031b6f3  lea     rdx, [rbp+var_38]
0x18031b6f7  mov     rcx, r14
0x18031b6fa  call    ??$WriteInfoElement@_J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_J_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<__int64>(std::wstring_view,std::wstring_view,__int64 const &,bool)
0x18031b6ff  lea     rcx, aIoreadoperatio; "IoReadOperationCount"
0x18031b706  mov     [rbp+var_28], rcx
0x18031b70a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b70f  mov     [rbp+var_20], rax
0x18031b713  mov     [rbp+var_38], r13
0x18031b717  mov     rcx, r13
0x18031b71a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b71f  mov     [rbp+var_30], rax
0x18031b723  lea     r9, [rbx+20h]
0x18031b727  xor     r12d, r12d
0x18031b72a  mov     [rsp+68h+var_48], r12b
0x18031b72f  lea     r8, [rbp+var_28]
0x18031b733  lea     rdx, [rbp+var_38]
0x18031b737  mov     rcx, r14
0x18031b73a  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b73f  lea     rcx, aIowriteoperati; "IoWriteOperationCount"
0x18031b746  mov     [rbp+var_28], rcx
0x18031b74a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b74f  mov     [rbp+var_20], rax
0x18031b753  mov     [rbp+var_38], r13
0x18031b757  mov     rcx, r13
0x18031b75a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b75f  mov     [rbp+var_30], rax
0x18031b763  lea     r9, [rbx+24h]
0x18031b767  mov     [rsp+68h+var_48], r12b
0x18031b76c  lea     r8, [rbp+var_28]
0x18031b770  lea     rdx, [rbp+var_38]
0x18031b774  mov     rcx, r14
0x18031b777  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b77c  lea     rcx, aIootheroperati; "IoOtherOperationCount"
0x18031b783  mov     [rbp+var_28], rcx
0x18031b787  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b78c  mov     [rbp+var_20], rax
0x18031b790  mov     [rbp+var_38], r13
0x18031b794  mov     rcx, r13
0x18031b797  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b79c  mov     [rbp+var_30], rax
0x18031b7a0  lea     r9, [rbx+28h]
0x18031b7a4  mov     [rsp+68h+var_48], r12b
0x18031b7a9  lea     r8, [rbp+var_28]
0x18031b7ad  lea     rdx, [rbp+var_38]
0x18031b7b1  mov     rcx, r14
0x18031b7b4  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b7b9  lea     rcx, aAvailablepages; "AvailablePages"
0x18031b7c0  mov     [rbp+var_28], rcx
0x18031b7c4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b7c9  mov     [rbp+var_20], rax
0x18031b7cd  mov     [rbp+var_38], r13
0x18031b7d1  mov     rcx, r13
0x18031b7d4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b7d9  mov     [rbp+var_30], rax
0x18031b7dd  lea     r9, [rbx+2Ch]
0x18031b7e1  mov     [rsp+68h+var_48], r12b
0x18031b7e6  lea     r8, [rbp+var_28]
0x18031b7ea  lea     rdx, [rbp+var_38]
0x18031b7ee  mov     rcx, r14
0x18031b7f1  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b7f6  lea     rcx, aCommittedpages; "CommittedPages"
0x18031b7fd  mov     [rbp+var_28], rcx
0x18031b801  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b806  mov     [rbp+var_20], rax
0x18031b80a  mov     [rbp+var_38], r13
0x18031b80e  mov     rcx, r13
0x18031b811  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b816  mov     [rbp+var_30], rax
0x18031b81a  lea     r9, [rbx+30h]
0x18031b81e  mov     [rsp+68h+var_48], r12b
0x18031b823  lea     r8, [rbp+var_28]
0x18031b827  lea     rdx, [rbp+var_38]
0x18031b82b  mov     rcx, r14
0x18031b82e  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b833  lea     r15, aCommitlimit; "CommitLimit"
0x18031b83a  mov     [rbp+var_28], r15
0x18031b83e  mov     rcx, r15
0x18031b841  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b846  mov     [rbp+var_20], rax
0x18031b84a  mov     [rbp+var_38], r13
0x18031b84e  mov     rcx, r13
0x18031b851  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b856  mov     [rbp+var_30], rax
0x18031b85a  lea     r9, [rbx+34h]
0x18031b85e  mov     [rsp+68h+var_48], r12b
0x18031b863  lea     r8, [rbp+var_28]
0x18031b867  lea     rdx, [rbp+var_38]
0x18031b86b  mov     rcx, r14
0x18031b86e  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b873  lea     rcx, aPeakcommitment; "PeakCommitment"
0x18031b87a  mov     [rbp+var_28], rcx
0x18031b87e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b883  mov     [rbp+var_20], rax
0x18031b887  mov     [rbp+var_38], r13
0x18031b88b  mov     rcx, r13
0x18031b88e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b893  mov     [rbp+var_30], rax
0x18031b897  lea     r9, [rbx+38h]
0x18031b89b  mov     [rsp+68h+var_48], r12b
0x18031b8a0  lea     r8, [rbp+var_28]
0x18031b8a4  lea     rdx, [rbp+var_38]
0x18031b8a8  mov     rcx, r14
0x18031b8ab  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b8b0  lea     rcx, aPagefaultcount; "PageFaultCount"
0x18031b8b7  mov     [rbp+var_28], rcx
0x18031b8bb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8c0  mov     [rbp+var_20], rax
0x18031b8c4  mov     [rbp+var_38], r13
0x18031b8c8  mov     rcx, r13
0x18031b8cb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8d0  mov     [rbp+var_30], rax
0x18031b8d4  lea     r9, [rbx+3Ch]
0x18031b8d8  mov     [rsp+68h+var_48], r12b
0x18031b8dd  lea     r8, [rbp+var_28]
0x18031b8e1  lea     rdx, [rbp+var_38]
0x18031b8e5  mov     rcx, r14
0x18031b8e8  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b8ed  lea     rcx, aCopyonwritecou; "CopyOnWriteCount"
0x18031b8f4  mov     [rbp+var_28], rcx
0x18031b8f8  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b8fd  mov     [rbp+var_20], rax
0x18031b901  mov     [rbp+var_38], r13
0x18031b905  mov     rcx, r13
0x18031b908  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b90d  mov     [rbp+var_30], rax
0x18031b911  lea     r9, [rbx+40h]
0x18031b915  mov     [rsp+68h+var_48], r12b
0x18031b91a  lea     r8, [rbp+var_28]
0x18031b91e  lea     rdx, [rbp+var_38]
0x18031b922  mov     rcx, r14
0x18031b925  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b92a  lea     rcx, aTransitioncoun; "TransitionCount"
0x18031b931  mov     [rbp+var_28], rcx
0x18031b935  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b93a  mov     [rbp+var_20], rax
0x18031b93e  mov     [rbp+var_38], r13
0x18031b942  mov     rcx, r13
0x18031b945  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b94a  mov     [rbp+var_30], rax
0x18031b94e  lea     r9, [rbx+44h]
0x18031b952  mov     [rsp+68h+var_48], r12b
0x18031b957  lea     r8, [rbp+var_28]
0x18031b95b  lea     rdx, [rbp+var_38]
0x18031b95f  mov     rcx, r14
0x18031b962  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b967  lea     rcx, aCachetransitio; "CacheTransitionCount"
0x18031b96e  mov     [rbp+var_28], rcx
0x18031b972  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b977  mov     [rbp+var_20], rax
0x18031b97b  mov     [rbp+var_38], r13
0x18031b97f  mov     rcx, r13
0x18031b982  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b987  mov     [rbp+var_30], rax
0x18031b98b  lea     r9, [rbx+48h]
0x18031b98f  mov     [rsp+68h+var_48], r12b
0x18031b994  lea     r8, [rbp+var_28]
0x18031b998  lea     rdx, [rbp+var_38]
0x18031b99c  mov     rcx, r14
0x18031b99f  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b9a4  lea     rcx, aDemandzerocoun; "DemandZeroCount"
0x18031b9ab  mov     [rbp+var_28], rcx
0x18031b9af  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9b4  mov     [rbp+var_20], rax
0x18031b9b8  mov     [rbp+var_38], r13
0x18031b9bc  mov     rcx, r13
0x18031b9bf  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9c4  mov     [rbp+var_30], rax
0x18031b9c8  lea     r9, [rbx+4Ch]
0x18031b9cc  mov     [rsp+68h+var_48], r12b
0x18031b9d1  lea     r8, [rbp+var_28]
0x18031b9d5  lea     rdx, [rbp+var_38]
0x18031b9d9  mov     rcx, r14
0x18031b9dc  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031b9e1  lea     rcx, aPagereadcount; "PageReadCount"
0x18031b9e8  mov     [rbp+var_28], rcx
0x18031b9ec  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031b9f1  mov     [rbp+var_20], rax
0x18031b9f5  mov     [rbp+var_38], r13
0x18031b9f9  mov     rcx, r13
0x18031b9fc  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba01  mov     [rbp+var_30], rax
0x18031ba05  lea     r9, [rbx+50h]
0x18031ba09  mov     [rsp+68h+var_48], r12b
0x18031ba0e  lea     r8, [rbp+var_28]
0x18031ba12  lea     rdx, [rbp+var_38]
0x18031ba16  mov     rcx, r14
0x18031ba19  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba1e  lea     rcx, aPagereadiocoun; "PageReadIoCount"
0x18031ba25  mov     [rbp+var_28], rcx
0x18031ba29  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba2e  mov     [rbp+var_20], rax
0x18031ba32  mov     [rbp+var_38], r13
0x18031ba36  mov     rcx, r13
0x18031ba39  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba3e  mov     [rbp+var_30], rax
0x18031ba42  lea     r9, [rbx+54h]
0x18031ba46  mov     [rsp+68h+var_48], r12b
0x18031ba4b  lea     r8, [rbp+var_28]
0x18031ba4f  lea     rdx, [rbp+var_38]
0x18031ba53  mov     rcx, r14
0x18031ba56  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba5b  lea     rcx, aCachereadcount; "CacheReadCount"
0x18031ba62  mov     [rbp+var_28], rcx
0x18031ba66  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba6b  mov     [rbp+var_20], rax
0x18031ba6f  mov     [rbp+var_38], r13
0x18031ba73  mov     rcx, r13
0x18031ba76  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031ba7b  mov     [rbp+var_30], rax
0x18031ba7f  lea     r9, [rbx+58h]
0x18031ba83  mov     [rsp+68h+var_48], r12b
0x18031ba88  lea     r8, [rbp+var_28]
0x18031ba8c  lea     rdx, [rbp+var_38]
0x18031ba90  mov     rcx, r14
0x18031ba93  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x18031ba98  lea     rcx, aCacheiocount; "CacheIoCount"
0x18031ba9f  mov     [rbp+var_28], rcx
0x18031baa3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031baa8  mov     [rbp+var_20], rax
0x18031baac  mov     [rbp+var_38], r13
0x18031bab0  mov     rcx, r13
0x18031bab3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18031bab8  mov     [rbp+var_30], rax
0x18031babc  lea     r9, [rbx+5Ch]
0x18031bac0  mov     [rsp+68h+var_48], r12b
0x18031bac5  lea     r8, [rbp+var_28]
0x18031bac9  lea     rdx, [rbp+var_38]
  ... truncated ...
```
