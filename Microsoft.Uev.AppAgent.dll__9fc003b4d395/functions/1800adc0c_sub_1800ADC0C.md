# sub_1800ADC0C

- ea: `0x1800adc0c`
- end: `0x1800b772b`
- name: `sub_1800ADC0C`
- size: `39711`
- prototype: ``
- caller_count: `1`
- callee_count: `139`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a99e4`

## callees

- `0x1800048f0`
- `0x18001d71c`
- `0x18001d80c`
- `0x180020e60`
- `0x1800212ac`
- `0x180028810`
- `0x180037524`
- `0x18005f7f0`
- `0x1800854a8`
- `0x1800a45a8`
- `0x1800a45e8`
- `0x1800a4628`
- `0x1800a4668`
- `0x1800a46a8`
- `0x1800a46e8`
- `0x1800a4728`
- `0x1800a4768`
- `0x1800a47a8`
- `0x1800a47e8`
- `0x1800a4828`
- `0x1800a4868`
- `0x1800a48a8`
- `0x1800a48e8`
- `0x1800a4928`
- `0x1800a4968`
- `0x1800a49a8`
- `0x1800a49e8`
- `0x1800a4a28`
- `0x1800a4a68`
- `0x1800a4aa8`
- `0x1800a4ae8`
- `0x1800a4b28`
- `0x1800a4b68`
- `0x1800a4ba8`
- `0x1800a4be8`
- `0x1800a4c28`
- `0x1800a4c68`
- `0x1800a4ca8`
- `0x1800a4ce8`
- `0x1800a4d28`
- `0x1800a4d68`
- `0x1800a4da8`
- `0x1800a4de8`
- `0x1800a4e28`
- `0x1800a4e68`
- `0x1800a4ea8`
- `0x1800a4ee8`
- `0x1800a4f28`
- `0x1800a4f68`
- `0x1800a4fa8`

## string_xrefs

- `0x1800aee0e`: `SettingsTemplateCatalogPath`
- `0x1800af08c`: `SettingsTemplateCatalogPath`
- `0x1800ae92e`: `SettingsStoragePath`
- `0x1800aebb0`: `SettingsStoragePath`
- `0x1800b09a3`: `OverrideMSTemplates`
- `0x1800b04eb`: `LastWriterThreshold`
- `0x1800afb48`: `LastWriterWins`
- `0x1800af95d`: `TemplateEnabled`
- `0x1800b26e4`: `TemplateRegistrationTimestamp`
- `0x1800b2905`: `InstallTimestamp`
- `0x1800b1e61`: `CurrentSettingsStoragePath`
- `0x1800b1c62`: `ADSettingsStoragePath`
- `0x1800b2d0a`: `ApplyExplorerCompatFix`
- `0x1800b4a67`: `SettingsStoragePathADAttribute`
- `0x1800b59ad`: `WaitForWallpaperOverwriteTime`
- `0x1800b6ca6`: `ProfileTemplateList`
- `0x1800b701c`: `TemplateProfile`
- `0x1800b6ea2`: `ProfileTemplateAssociation`

## pseudocode

```c
__int64 __fastcall sub_1800ADC0C(__int64 a1)
{
  __int64 v2; // r9
  __int64 v3; // r9
  __int64 v4; // r9
  int v5; // r15d
  __int64 v6; // r9
  int v7; // r13d
  __int64 v8; // r9
  int v9; // r12d
  __int64 v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // r9d
  __int64 v15; // rax
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rsi
  int v19; // eax
  int v20; // r9d
  __int64 v21; // rax
  __int64 v22; // r14
  int v23; // eax
  int v24; // r9d
  __int64 v25; // rax
  __int64 v26; // r14
  int v27; // eax
  int v28; // r9d
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rsi
  int v32; // eax
  int v33; // r9d
  __int64 v34; // rax
  __int64 v35; // r14
  int v36; // eax
  int v37; // r9d
  __int64 v38; // rax
  __int64 v39; // r14
  int v40; // eax
  int v41; // r9d
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rsi
  int v47; // eax
  int v48; // r9d
  __int64 v49; // rax
  __int64 v50; // r14
  int v51; // eax
  int v52; // r9d
  __int64 v53; // rax
  __int64 v54; // r14
  int v55; // eax
  int v56; // r9d
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rsi
  int v60; // eax
  int v61; // r9d
  __int64 v62; // rax
  __int64 v63; // r14
  int v64; // eax
  int v65; // r9d
  __int64 v66; // rax
  __int64 v67; // r14
  int v68; // eax
  int v69; // r9d
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rsi
  int v74; // eax
  int v75; // r9d
  __int64 v76; // rax
  __int64 v77; // r14
  int v78; // eax
  int v79; // r9d
  __int64 v80; // rax
  __int64 v81; // r14
  int v82; // eax
  int v83; // r9d
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rsi
  int v87; // eax
  int v88; // r9d
  __int64 v89; // rax
  __int64 v90; // r14
  int v91; // eax
  int v92; // r9d
  __int64 v93; // rax
  __int64 v94; // r14
  int v95; // eax
  int v96; // r9d
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rsi
  int v101; // eax
  int v102; // r9d
  __int64 v103; // rax
  __int64 v104; // r14
  int v105; // eax
  int v106; // r9d
  __int64 v107; // rax
  __int64 v108; // r14
  int v109; // eax
  int v110; // r9d
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rsi
  int v114; // eax
  int v115; // r9d
  __int64 v116; // rax
  __int64 v117; // r14
  int v118; // eax
  int v119; // r9d
  __int64 v120; // rax
  __int64 v121; // r14
  int v122; // eax
  int v123; // r9d
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rsi
  int v127; // eax
  int v128; // r9d
  __int64 v129; // rax
  __int64 v130; // r14
  int v131; // eax
  int v132; // r9d
  __int64 v133; // rax
  __int64 v134; // r14
  int v135; // eax
  int v136; // r9d
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 v140; // r9
  __int64 v141; // rax
  __int64 v142; // r9
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // r9
  __int64 v146; // rax
  __int64 v147; // r9
  __int64 v148; // rax
  __int64 v149; // rsi
  int v150; // eax
  int v151; // r9d
  __int64 v152; // rax
  __int64 v153; // r14
  int v154; // eax
  int v155; // r9d
  __int64 v156; // rax
  __int64 v157; // r14
  int v158; // eax
  int v159; // r9d
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rsi
  int v163; // eax
  int v164; // r9d
  __int64 v165; // rax
  __int64 v166; // r14
  int v167; // eax
  int v168; // r9d
  __int64 v169; // rax
  __int64 v170; // r14
  int v171; // eax
  int v172; // r9d
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rsi
  int v176; // eax
  int v177; // r9d
  __int64 v178; // rax
  __int64 v179; // r14
  int v180; // eax
  int v181; // r9d
  __int64 v182; // rax
  __int64 v183; // r14
  int v184; // eax
  int v185; // r9d
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rsi
  int v189; // eax
  int v190; // r9d
  __int64 v191; // rax
  __int64 v192; // r14
  int v193; // eax
  int v194; // r9d
  __int64 v195; // rax
  __int64 v196; // r14
  int v197; // eax
  int v198; // r9d
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rsi
  int v202; // eax
  int v203; // r9d
  __int64 v204; // rax
  __int64 v205; // r14
  int v206; // eax
  int v207; // r9d
  __int64 v208; // rax
  __int64 v209; // r14
  int v210; // eax
  int v211; // r9d
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // rsi
  int v215; // eax
  int v216; // r9d
  __int64 v217; // rax
  __int64 v218; // r14
  int v219; // eax
  int v220; // r9d
  __int64 v221; // rax
  __int64 v222; // r14
  int v223; // eax
  int v224; // r9d
  __int64 v225; // rax
  __int64 v226; // rax
  __int64 v227; // rsi
  int v228; // eax
  int v229; // r9d
  __int64 v230; // rax
  __int64 v231; // r14
  int v232; // eax
  int v233; // r9d
  __int64 v234; // rax
  __int64 v235; // r14
  int v236; // eax
  int v237; // r9d
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rsi
  int v241; // eax
  int v242; // r9d
  __int64 v243; // rax
  __int64 v244; // r14
  int v245; // eax
  int v246; // r9d
  __int64 v247; // rax
  __int64 v248; // r14
  int v249; // eax
  int v250; // r9d
  __int64 v251; // rax
  __int64 v252; // rax
  __int64 v253; // r14
  int v254; // eax
  int v255; // r9d
  __int64 v256; // rax
  __int64 v257; // r14
  int v258; // eax
  int v259; // r9d
  __int64 v260; // rax
  __int64 v261; // rax
  __int64 v262; // r14
  int v263; // eax
  int v264; // r9d
  __int64 v265; // rax
  __int64 v266; // r14
  int v267; // eax
  int v268; // r9d
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // r14
  int v272; // eax
  int v273; // r9d
  __int64 v274; // rax
  __int64 v275; // r14
  int v276; // eax
  int v277; // r9d
  __int64 v278; // rax
  __int64 v279; // rax
  __int64 v280; // r14
  int v281; // eax
  int v282; // r9d
  __int64 v283; // rax
  __int64 v284; // r14
  int v285; // eax
  int v286; // r9d
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // r14
  int v290; // eax
  int v291; // r9d
  __int64 v292; // rax
  __int64 v293; // r14
  int v294; // eax
  int v295; // r9d
  __int64 v296; // rax
  __int64 v297; // rax
  __int64 v298; // r14
  int v299; // eax
  int v300; // r9d
  __int64 v301; // rax
  __int64 v302; // r14
  int v303; // eax
  int v304; // r9d
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // r14
  int v308; // eax
  int v309; // r9d
  __int64 v310; // rax
  __int64 v311; // r14
  int v312; // eax
  int v313; // r9d
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // r14
  int v317; // eax
  int v318; // r9d
  __int64 v319; // rax
  __int64 v320; // r14
  int v321; // eax
  int v322; // r9d
  __int64 v323; // rax
  __int64 v324; // rax
  __int64 v325; // r14
  int v326; // eax
  int v327; // r9d
  __int64 v328; // rax
  __int64 v329; // r14
  int v330; // eax
  int v331; // r9d
  __int64 v332; // rax
  __int64 v333; // rax
  __int64 v334; // rax
  __int64 v335; // r9
  __int64 v336; // rax
  __int64 v337; // r9
  __int64 v338; // rax
  __int64 v339; // r9
  __int64 v340; // rax
  __int64 v341; // rax
  __int64 v342; // r9
  __int64 v343; // rax
  __int64 v344; // r9
  __int64 v345; // rax
  __int64 v346; // r9
  __int64 v347; // rax
  __int64 v348; // rax
  __int64 v349; // r9
  __int64 v350; // rax
  __int64 v351; // r9
  __int64 v352; // rax
  __int64 v353; // r9
  __int64 v354; // rax
  __int64 v355; // rax
  __int64 v356; // r9
  __int64 v357; // rax
  __int64 v358; // r9
  __int64 v359; // rax
  __int64 v360; // r14
  int v361; // eax
  int v362; // r9d
  __int64 v363; // rax
  __int64 v364; // r14
  int v365; // eax
  int v366; // r9d
  __int64 v367; // rax
  __int64 v368; // rax
  __int64 v369; // r14
  int v370; // eax
  int v371; // r9d
  __int64 v372; // rax
  __int64 v373; // r14
  int v374; // eax
  int v375; // r9d
  __int64 v376; // rax
  __int64 v377; // rax
  __int64 v378; // r14
  int v379; // eax
  int v380; // r9d
  __int64 v381; // rax
  __int64 v382; // r14
  int v383; // eax
  int v384; // r9d
  __int64 v385; // rax
  __int64 v386; // rax
  __int64 v387; // rsi
  int v388; // eax
  int v389; // r9d
  __int64 v390; // rax
  __int64 v391; // r14
  int v392; // eax
  int v393; // r9d
  __int64 v394; // rax
  __int64 v395; // r14
  int v396; // eax
  int v397; // r9d
  __int64 v398; // rax
  __int64 v399; // rax
  __int64 v400; // rsi
  int v401; // eax
  int v402; // r9d
  __int64 v403; // rax
  __int64 v404; // r14
  int v405; // eax
  int v406; // r9d
  __int64 v407; // rax
  __int64 v408; // r14
  int v409; // eax
  int v410; // r9d
  __int64 v411; // rax
  __int64 v412; // rax
  __int64 v413; // rsi
  int v414; // eax
  int v415; // r9d
  __int64 v416; // rax
  __int64 v417; // r14
  int v418; // eax
  int v419; // r9d
  __int64 v420; // rax
  __int64 v421; // rax
  __int64 v422; // rax
  __int64 v423; // rax
  __int64 v424; // rsi
  int v425; // eax
  int v426; // r9d
  __int64 v427; // rax
  __int64 v428; // r14
  int v429; // eax
  int v430; // r9d
  __int64 v431; // rax
  __int64 v432; // r14
  int v433; // eax
  int v434; // r9d
  __int64 v435; // rax
  __int64 v436; // rax
  __int64 v437; // rsi
  int v438; // eax
  int v439; // r9d
  __int64 v440; // rax
  __int64 v441; // r14
  int v442; // eax
  int v443; // r9d
  __int64 v444; // rax
  __int64 v445; // r14
  int v446; // eax
  int v447; // r9d
  __int64 v448; // rax
  __int64 v449; // rax
  __int64 v450; // rsi
  int v451; // eax
  int v452; // r9d
  __int64 v453; // rax
  __int64 v454; // r14
  int v455; // eax
  int v456; // r9d
  __int64 v457; // rax
  __int64 v458; // r14
  int v459; // eax
  int v460; // r9d
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rsi
  int v464; // eax
  int v465; // r9d
  __int64 v466; // rax
  __int64 v467; // r14
  int v468; // eax
  int v469; // r9d
  __int64 v470; // rax
  __int64 v471; // r14
  int v472; // eax
  int v473; // r9d
  __int64 v474; // rax
  __int64 v475; // rax
  __int64 v476; // rsi
  int v477; // eax
  int v478; // r9d
  __int64 v479; // rax
  __int64 v480; // r14
  int v481; // eax
  int v482; // r9d
  __int64 v483; // rax
  __int64 v484; // r14
  int v485; // eax
  int v486; // r9d
  __int64 v487; // rax
  __int64 v488; // rax
  __int64 v489; // rsi
  int v490; // eax
  int v491; // r9d
  __int64 v492; // rax
  __int64 v493; // r14
  int v494; // eax
  int v495; // r9d
  __int64 v496; // rax
  __int64 v497; // r14
  int v498; // eax
  int v499; // r9d
  __int64 v500; // rax
  __int64 v501; // rax
  __int64 v502; // rsi
  int v503; // eax
  int v504; // r9d
  __int64 v505; // rax
  __int64 v506; // r14
  int v507; // eax
  int v508; // r9d
  __int64 v509; // rax
  __int64 v510; // r14
  int v511; // eax
  int v512; // r9d
  __int64 v513; // rax
  __int64 v514; // rax
  __int64 v515; // rsi
  int v516; // eax
  int v517; // r9d
  __int64 v518; // rax
  __int64 v519; // r14
  int v520; // eax
  int v521; // r9d
  __int64 v522; // rax
  __int64 v523; // r14
  int v524; // eax
  int v525; // r9d
  __int64 v526; // rax
  __int64 v527; // rax
  __int64 v528; // rsi
  int v529; // eax
  int v530; // r9d
  __int64 v531; // rax
  __int64 v532; // r14
  int v533; // eax
  int v534; // r9d
  __int64 v535; // rax
  __int64 v536; // r14
  int v537; // eax
  int v538; // r9d
  __int64 v539; // rax
  __int64 v540; // rax
  __int64 v541; // rsi
  int v542; // eax
  int v543; // r9d
  __int64 v544; // rax
  __int64 v545; // r14
  int v546; // eax
  int v547; // r9d
  __int64 v548; // rax
  __int64 v549; // r14
  int v550; // eax
  int v551; // r9d
  __int64 v552; // rax
  __int64 v553; // rax
  __int64 v554; // rsi
  int v555; // eax
  int v556; // r9d
  __int64 v557; // rax
  __int64 v558; // r14
  int v559; // eax
  int v560; // r9d
  __int64 v561; // rax
  __int64 v562; // r14
  int v563; // eax
  int v564; // r9d
  __int64 v565; // rax
  __int64 v566; // rax
  __int64 v567; // rsi
  int v568; // eax
  int v569; // r9d
  __int64 v570; // rax
  __int64 v571; // r14
  int v572; // eax
  int v573; // r9d
  __int64 v574; // rax
  __int64 v575; // r14
  int v576; // eax
  int v577; // r9d
  __int64 v578; // rax
  __int64 v579; // rax
  __int64 v580; // rsi
  int v581; // eax
  int v582; // r9d
  __int64 v583; // rax
  __int64 v584; // r14
  int v585; // eax
  int v586; // r9d
  __int64 v587; // rax
  __int64 v588; // r14
  int v589; // eax
  int v590; // r9d
  __int64 v591; // rax
  __int64 v592; // rax
  __int64 v593; // rax
  __int64 v594; // r9
  __int64 v595; // rax
  __int64 v596; // r9
  __int64 v597; // rax
  __int64 v598; // r9
  __int64 v599; // rax
  __int64 v600; // rax
  __int64 v601; // r9
  __int64 v602; // rax
  __int64 v603; // r9
  __int64 v604; // rax
  __int64 v605; // r9
  __int64 v606; // rax
  __int64 v607; // r14
  int v608; // eax
  int v609; // r9d
  __int64 v610; // rax
  __int64 v611; // r14
  int v612; // eax
  int v613; // r9d
  __int64 v614; // rax
  __int64 v615; // rax
  __int64 v616; // r13
  __int64 v617; // rsi
  int v618; // eax
  int v619; // r9d
  __int64 v620; // rax
  __int64 v621; // r14
  int v622; // eax
  int v623; // r9d
  __int64 v624; // rax
  __int64 v625; // r14
  int v626; // eax
  int v627; // r9d
  __int64 v628; // rax
  __int64 v629; // rax
  __int64 v630; // rsi
  int v631; // eax
  int v632; // r9d
  __int64 v633; // rax
  __int64 v634; // r14
  int v635; // eax
  int v636; // r9d
  __int64 v637; // rax
  __int64 v638; // r14
  int v639; // eax
  int v640; // r9d
  __int64 v641; // rax
  __int64 v642; // rax
  __int64 v643; // rsi
  int v644; // eax
  int v645; // r9d
  __int64 v646; // rax
  __int64 v647; // r14
  int v648; // eax
  int v649; // r9d
  __int64 v650; // rax
  __int64 v651; // r14
  int v652; // eax
  int v653; // r9d
  __int64 v654; // rax
  __int64 v655; // rax
  __int64 v656; // r14
  int v657; // eax
  int v658; // r9d
  __int64 v659; // rax
  __int64 v660; // rax
  __int64 v661; // r14
  int v662; // eax
  int v663; // r9d
  __int64 v664; // rax
  __int64 v665; // rax
  __int64 v666; // rsi
  int v667; // eax
  int v668; // r9d
  __int64 v669; // rax
  __int64 v670; // r14
  int v671; // eax
  int v672; // r9d
  __int64 v673; // rax
  __int64 v674; // r14
  int v675; // eax
  int v676; // r9d
  __int64 v677; // rax
  __int64 v678; // rax
  __int64 v679; // rsi
  int v680; // eax
  int v681; // r9d
  __int64 v682; // rax
  __int64 v683; // r14
  int v684; // eax
  int v685; // r9d
  __int64 v686; // rax
  __int64 v687; // r14
  int v688; // eax
  int v689; // r9d
  __int64 v690; // rax
  __int64 v691; // rax
  __int64 v692; // rax
  __int64 v693; // r9
  __int64 v694; // rax
  __int64 v695; // rax
  __int64 v696; // r9
  __int64 v697; // rax
  __int64 v698; // r9
  __int64 v699; // rax
  __int64 v700; // rax
  __int64 v701; // r9
  __int64 v702; // rax
  __int64 v703; // rax
  __int64 v704; // r9
  __int64 v705; // rax
  __int64 v706; // r9
  __int64 v707; // rax
  __int64 v708; // rax
  __int64 v709; // r9
  __int64 v710; // rax
  __int64 v711; // rsi
  int v712; // eax
  int v713; // r9d
  __int64 v714; // rax
  __int64 v715; // r14
  int v716; // eax
  int v717; // r9d
  __int64 v718; // rax
  __int64 v719; // r14
  int v720; // eax
  int v721; // r9d
  __int64 v722; // rax
  __int64 v723; // rax
  __int64 v724; // rsi
  int v725; // eax
  int v726; // r9d
  __int64 v727; // rax
  __int64 v728; // r14
  int v729; // eax
  int v730; // r9d
  __int64 v731; // rax
  __int64 v732; // r14
  int v733; // eax
  int v734; // r9d
  __int64 v735; // rax
  __int64 v736; // rax
  __int64 v737; // rsi
  int v738; // eax
  int v739; // r9d
  __int64 v740; // rax
  __int64 v741; // r14
  int v742; // eax
  int v743; // r9d
  __int64 v744; // rax
  __int64 v745; // r14
  int v746; // eax
  int v747; // r9d
  __int64 v748; // rax
  __int64 v749; // rax
  int v751; // [rsp+20h] [rbp-E0h]
  int v752; // [rsp+20h] [rbp-E0h]
  int v753; // [rsp+20h] [rbp-E0h]
  int v754; // [rsp+20h] [rbp-E0h]
  int v755; // [rsp+20h] [rbp-E0h]
  int v756; // [rsp+20h] [rbp-E0h]
  int v757; // [rsp+20h] [rbp-E0h]
  int v758; // [rsp+20h] [rbp-E0h]
  int v759; // [rsp+20h] [rbp-E0h]
  int v760; // [rsp+20h] [rbp-E0h]
  int v761; // [rsp+20h] [rbp-E0h]
  int v762; // [rsp+20h] [rbp-E0h]
  int v763; // [rsp+20h] [rbp-E0h]
  int v764; // [rsp+20h] [rbp-E0h]
  int v765; // [rsp+20h] [rbp-E0h]
  int v766; // [rsp+20h] [rbp-E0h]
  int v767; // [rsp+20h] [rbp-E0h]
  int v768; // [rsp+20h] [rbp-E0h]
  int v769; // [rsp+20h] [rbp-E0h]
  int v770; // [rsp+20h] [rbp-E0h]
  int v771; // [rsp+20h] [rbp-E0h]
  int v772; // [rsp+20h] [rbp-E0h]
  int v773; // [rsp+20h] [rbp-E0h]
  int v774; // [rsp+20h] [rbp-E0h]
  int v775; // [rsp+20h] [rbp-E0h]
  int v776; // [rsp+20h] [rbp-E0h]
  int v777; // [rsp+20h] [rbp-E0h]
  int v778; // [rsp+20h] [rbp-E0h]
  int v779; // [rsp+28h] [rbp-D8h]
  int v780; // [rsp+28h] [rbp-D8h]
  int v781; // [rsp+28h] [rbp-D8h]
  int v782; // [rsp+28h] [rbp-D8h]
  int v783; // [rsp+28h] [rbp-D8h]
  int v784; // [rsp+28h] [rbp-D8h]
  int v785; // [rsp+28h] [rbp-D8h]
  int v786; // [rsp+28h] [rbp-D8h]
  int v787; // [rsp+28h] [rbp-D8h]
  int v788; // [rsp+28h] [rbp-D8h]
  int v789; // [rsp+28h] [rbp-D8h]
  int v790; // [rsp+28h] [rbp-D8h]
  int v791; // [rsp+28h] [rbp-D8h]
  int v792; // [rsp+28h] [rbp-D8h]
  int v793; // [rsp+28h] [rbp-D8h]
  int v794; // [rsp+28h] [rbp-D8h]
  int v795; // [rsp+28h] [rbp-D8h]
  int v796; // [rsp+28h] [rbp-D8h]
  int v797; // [rsp+28h] [rbp-D8h]
  int v798; // [rsp+28h] [rbp-D8h]
  int v799; // [rsp+28h] [rbp-D8h]
  int v800; // [rsp+28h] [rbp-D8h]
  int v801; // [rsp+28h] [rbp-D8h]
  int v802; // [rsp+28h] [rbp-D8h]
  int v803; // [rsp+28h] [rbp-D8h]
  int v804; // [rsp+28h] [rbp-D8h]
  int v805; // [rsp+28h] [rbp-D8h]
  int v806; // [rsp+28h] [rbp-D8h]
  int v807; // [rsp+28h] [rbp-D8h]
  int v808; // [rsp+28h] [rbp-D8h]
  int v809; // [rsp+28h] [rbp-D8h]
  int v810; // [rsp+28h] [rbp-D8h]
  int v811; // [rsp+28h] [rbp-D8h]
  int v812; // [rsp+30h] [rbp-D0h]
  int v813; // [rsp+30h] [rbp-D0h]
  int v814; // [rsp+30h] [rbp-D0h]
  int v815; // [rsp+30h] [rbp-D0h]
  int v816; // [rsp+30h] [rbp-D0h]
  int v817; // [rsp+30h] [rbp-D0h]
  int v818; // [rsp+30h] [rbp-D0h]
  int v819; // [rsp+30h] [rbp-D0h]
  int v820; // [rsp+30h] [rbp-D0h]
  int v821; // [rsp+30h] [rbp-D0h]
  int v822; // [rsp+30h] [rbp-D0h]
  int v823; // [rsp+30h] [rbp-D0h]
  int v824; // [rsp+30h] [rbp-D0h]
  int v825; // [rsp+30h] [rbp-D0h]
  int v826; // [rsp+30h] [rbp-D0h]
  int v827; // [rsp+30h] [rbp-D0h]
  int v828; // [rsp+30h] [rbp-D0h]
  int v829; // [rsp+30h] [rbp-D0h]
  int v830; // [rsp+30h] [rbp-D0h]
  int v831; // [rsp+30h] [rbp-D0h]
  int v832; // [rsp+30h] [rbp-D0h]
  int v833; // [rsp+30h] [rbp-D0h]
  int v834; // [rsp+30h] [rbp-D0h]
  int v835; // [rsp+30h] [rbp-D0h]
  int v836; // [rsp+30h] [rbp-D0h]
  int v837; // [rsp+30h] [rbp-D0h]
  int v838; // [rsp+30h] [rbp-D0h]
  int v839; // [rsp+30h] [rbp-D0h]
  int v840; // [rsp+30h] [rbp-D0h]
  int v841; // [rsp+30h] [rbp-D0h]
  int v842; // [rsp+30h] [rbp-D0h]
  int v843; // [rsp+30h] [rbp-D0h]
  __int128 v845; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v846; // [rsp+70h] [rbp-90h]
  char v847; // [rsp+80h] [rbp-80h]
  _QWORD *v848; // [rsp+88h] [rbp-78h]
  int v849; // [rsp+90h] [rbp-70h] BYREF
  int v850; // [rsp+94h] [rbp-6Ch] BYREF
  int v851; // [rsp+98h] [rbp-68h] BYREF
  int v852; // [rsp+9Ch] [rbp-64h] BYREF
  int v853; // [rsp+A0h] [rbp-60h] BYREF
  int v854; // [rsp+A4h] [rbp-5Ch] BYREF
  int v855; // [rsp+A8h] [rbp-58h] BYREF
  int v856; // [rsp+ACh] [rbp-54h] BYREF
  int v857; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v858[40]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall *v859)(); // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v860[8]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v861[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v862[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v863[24]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v864[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v865[24]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v866[24]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v867[40]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v868[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v869[40]; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v870[40]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v871[32]; // [rsp+228h] [rbp+128h] BYREF
  __int64 (__fastcall *v872)(); // [rsp+248h] [rbp+148h] BYREF
  _BYTE v873[40]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v874; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v875[40]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v876; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v877[40]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v878[16]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v879[16]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v880[16]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v881[16]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v882[16]; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v883[16]; // [rsp+328h] [rbp+228h] BYREF
  _BYTE v884[16]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v885[16]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v886[16]; // [rsp+358h] [rbp+258h] BYREF
  _BYTE v887[16]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v888[16]; // [rsp+378h] [rbp+278h] BYREF
  _BYTE v889[16]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v890[16]; // [rsp+398h] [rbp+298h] BYREF
  _BYTE v891[16]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v892[16]; // [rsp+3B8h] [rbp+2B8h] BYREF
  _BYTE v893[16]; // [rsp+3C8h] [rbp+2C8h] BYREF
  _BYTE v894[16]; // [rsp+3D8h] [rbp+2D8h] BYREF
  _BYTE v895[16]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v896[16]; // [rsp+3F8h] [rbp+2F8h] BYREF
  _BYTE v897[32]; // [rsp+408h] [rbp+308h] BYREF
  _BYTE v898[32]; // [rsp+428h] [rbp+328h] BYREF
  _BYTE v899[32]; // [rsp+448h] [rbp+348h] BYREF
  _BYTE v900[32]; // [rsp+468h] [rbp+368h] BYREF
  _BYTE v901[32]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v902[32]; // [rsp+4A8h] [rbp+3A8h] BYREF
  _BYTE v903[32]; // [rsp+4C8h] [rbp+3C8h] BYREF
  _BYTE v904[32]; // [rsp+4E8h] [rbp+3E8h] BYREF
  _BYTE v905[32]; // [rsp+508h] [rbp+408h] BYREF
  _BYTE v906[32]; // [rsp+528h] [rbp+428h] BYREF
  _BYTE v907[32]; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v908[32]; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v909[32]; // [rsp+588h] [rbp+488h] BYREF
  _BYTE v910[32]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v911[32]; // [rsp+5C8h] [rbp+4C8h] BYREF
  _BYTE v912[32]; // [rsp+5E8h] [rbp+4E8h] BYREF
  _BYTE v913[32]; // [rsp+608h] [rbp+508h] BYREF
  _BYTE v914[32]; // [rsp+628h] [rbp+528h] BYREF
  _BYTE v915[32]; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v916[32]; // [rsp+668h] [rbp+568h] BYREF
  _BYTE v917[32]; // [rsp+688h] [rbp+588h] BYREF
  _BYTE v918[32]; // [rsp+6A8h] [rbp+5A8h] BYREF
  _BYTE v919[32]; // [rsp+6C8h] [rbp+5C8h] BYREF
  _BYTE v920[32]; // [rsp+6E8h] [rbp+5E8h] BYREF
  _BYTE v921[32]; // [rsp+708h] [rbp+608h] BYREF
  _BYTE v922[32]; // [rsp+728h] [rbp+628h] BYREF
  _BYTE v923[32]; // [rsp+748h] [rbp+648h] BYREF
  _BYTE v924[32]; // [rsp+768h] [rbp+668h] BYREF
  _BYTE v925[32]; // [rsp+788h] [rbp+688h] BYREF
  _BYTE v926[32]; // [rsp+7A8h] [rbp+6A8h] BYREF
  _BYTE v927[32]; // [rsp+7C8h] [rbp+6C8h] BYREF
  _BYTE v928[32]; // [rsp+7E8h] [rbp+6E8h] BYREF
  _BYTE v929[32]; // [rsp+808h] [rbp+708h] BYREF
  _BYTE v930[32]; // [rsp+828h] [rbp+728h] BYREF
  _BYTE v931[32]; // [rsp+848h] [rbp+748h] BYREF
  _BYTE v932[32]; // [rsp+868h] [rbp+768h] BYREF
  _BYTE v933[32]; // [rsp+888h] [rbp+788h] BYREF
  _BYTE v934[32]; // [rsp+8A8h] [rbp+7A8h] BYREF
  _BYTE v935[32]; // [rsp+8C8h] [rbp+7C8h] BYREF
  _BYTE v936[32]; // [rsp+8E8h] [rbp+7E8h] BYREF
  _BYTE v937[32]; // [rsp+908h] [rbp+808h] BYREF
  _BYTE v938[32]; // [rsp+928h] [rbp+828h] BYREF
  _BYTE v939[32]; // [rsp+948h] [rbp+848h] BYREF
  _BYTE v940[32]; // [rsp+968h] [rbp+868h] BYREF
  _BYTE v941[32]; // [rsp+988h] [rbp+888h] BYREF
  _BYTE v942[32]; // [rsp+9A8h] [rbp+8A8h] BYREF
  _BYTE v943[32]; // [rsp+9C8h] [rbp+8C8h] BYREF
  _BYTE v944[32]; // [rsp+9E8h] [rbp+8E8h] BYREF
  _BYTE v945[32]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v946[32]; // [rsp+A28h] [rbp+928h] BYREF
  _BYTE v947[32]; // [rsp+A48h] [rbp+948h] BYREF
  _BYTE v948[32]; // [rsp+A68h] [rbp+968h] BYREF
  _BYTE v949[32]; // [rsp+A88h] [rbp+988h] BYREF
  _BYTE v950[32]; // [rsp+AA8h] [rbp+9A8h] BYREF
  _BYTE v951[32]; // [rsp+AC8h] [rbp+9C8h] BYREF
  _BYTE v952[32]; // [rsp+AE8h] [rbp+9E8h] BYREF
  _BYTE v953[32]; // [rsp+B08h] [rbp+A08h] BYREF
  _BYTE v954[32]; // [rsp+B28h] [rbp+A28h] BYREF
  _BYTE v955[32]; // [rsp+B48h] [rbp+A48h] BYREF
  _BYTE v956[32]; // [rsp+B68h] [rbp+A68h] BYREF
  _BYTE v957[16]; // [rsp+B88h] [rbp+A88h] BYREF
  _BYTE v958[32]; // [rsp+B98h] [rbp+A98h] BYREF
  _BYTE v959[32]; // [rsp+BB8h] [rbp+AB8h] BYREF
  _BYTE v960[32]; // [rsp+BD8h] [rbp+AD8h] BYREF
  _BYTE v961[32]; // [rsp+BF8h] [rbp+AF8h] BYREF
  _BYTE v962[16]; // [rsp+C18h] [rbp+B18h] BYREF
  _BYTE v963[16]; // [rsp+C28h] [rbp+B28h] BYREF
  _BYTE v964[16]; // [rsp+C38h] [rbp+B38h] BYREF
  _BYTE v965[16]; // [rsp+C48h] [rbp+B48h] BYREF
  _BYTE v966[16]; // [rsp+C58h] [rbp+B58h] BYREF
  _BYTE v967[16]; // [rsp+C68h] [rbp+B68h] BYREF
  _BYTE v968[16]; // [rsp+C78h] [rbp+B78h] BYREF
  _BYTE v969[32]; // [rsp+C88h] [rbp+B88h] BYREF
  _BYTE v970[32]; // [rsp+CA8h] [rbp+BA8h] BYREF
  _BYTE v971[32]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v972[32]; // [rsp+CE8h] [rbp+BE8h] BYREF
  _BYTE v973[32]; // [rsp+D08h] [rbp+C08h] BYREF
  _BYTE v974[32]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v975[32]; // [rsp+D48h] [rbp+C48h] BYREF
  _BYTE v976[32]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v977[32]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v978[32]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v979[32]; // [rsp+DC8h] [rbp+CC8h] BYREF
  _BYTE v980[32]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v981[32]; // [rsp+E08h] [rbp+D08h] BYREF
  _BYTE v982[32]; // [rsp+E28h] [rbp+D28h] BYREF
  _BYTE v983[32]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v984[16]; // [rsp+E68h] [rbp+D68h] BYREF
  _BYTE v985[32]; // [rsp+E78h] [rbp+D78h] BYREF
  _BYTE v986[32]; // [rsp+E98h] [rbp+D98h] BYREF
  _BYTE v987[32]; // [rsp+EB8h] [rbp+DB8h] BYREF
  _BYTE v988[32]; // [rsp+ED8h] [rbp+DD8h] BYREF
  _BYTE v989[32]; // [rsp+EF8h] [rbp+DF8h] BYREF
  _BYTE v990[32]; // [rsp+F18h] [rbp+E18h] BYREF
  _BYTE v991[16]; // [rsp+F38h] [rbp+E38h] BYREF
  _BYTE v992[32]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v993[32]; // [rsp+F68h] [rbp+E68h] BYREF
  _BYTE v994[32]; // [rsp+F88h] [rbp+E88h] BYREF
  _BYTE v995[32]; // [rsp+FA8h] [rbp+EA8h] BYREF
  _BYTE v996[32]; // [rsp+FC8h] [rbp+EC8h] BYREF
  _BYTE v997[32]; // [rsp+FE8h] [rbp+EE8h] BYREF
  _BYTE v998[32]; // [rsp+1008h] [rbp+F08h] BYREF
  _BYTE v999[32]; // [rsp+1028h] [rbp+F28h] BYREF
  _BYTE v1000[32]; // [rsp+1048h] [rbp+F48h] BYREF
  _BYTE v1001[32]; // [rsp+1068h] [rbp+F68h] BYREF
  _BYTE v1002[32]; // [rsp+1088h] [rbp+F88h] BYREF
  _BYTE v1003[32]; // [rsp+10A8h] [rbp+FA8h] BYREF
  _BYTE v1004[32]; // [rsp+10C8h] [rbp+FC8h] BYREF
  _BYTE v1005[32]; // [rsp+10E8h] [rbp+FE8h] BYREF
  _BYTE v1006[32]; // [rsp+1108h] [rbp+1008h] BYREF
  _BYTE v1007[32]; // [rsp+1128h] [rbp+1028h] BYREF
  _BYTE v1008[32]; // [rsp+1148h] [rbp+1048h] BYREF
  _BYTE v1009[32]; // [rsp+1168h] [rbp+1068h] BYREF
  _BYTE v1010[32]; // [rsp+1188h] [rbp+1088h] BYREF
  _BYTE v1011[32]; // [rsp+11A8h] [rbp+10A8h] BYREF
  _BYTE v1012[32]; // [rsp+11C8h] [rbp+10C8h] BYREF
  _BYTE v1013[32]; // [rsp+11E8h] [rbp+10E8h] BYREF
  _BYTE v1014[32]; // [rsp+1208h] [rbp+1108h] BYREF
  _BYTE v1015[32]; // [rsp+1228h] [rbp+1128h] BYREF
  _BYTE v1016[32]; // [rsp+1248h] [rbp+1148h] BYREF
  _BYTE v1017[32]; // [rsp+1268h] [rbp+1168h] BYREF
  _BYTE v1018[32]; // [rsp+1288h] [rbp+1188h] BYREF
  _BYTE v1019[32]; // [rsp+12A8h] [rbp+11A8h] BYREF
  _BYTE v1020[32]; // [rsp+12C8h] [rbp+11C8h] BYREF
  _BYTE v1021[32]; // [rsp+12E8h] [rbp+11E8h] BYREF
  _BYTE v1022[32]; // [rsp+1308h] [rbp+1208h] BYREF
  _BYTE v1023[32]; // [rsp+1328h] [rbp+1228h] BYREF
  _BYTE v1024[32]; // [rsp+1348h] [rbp+1248h] BYREF
  _BYTE v1025[32]; // [rsp+1368h] [rbp+1268h] BYREF
  _BYTE v1026[32]; // [rsp+1388h] [rbp+1288h] BYREF
  _BYTE v1027[32]; // [rsp+13A8h] [rbp+12A8h] BYREF
  _BYTE v1028[32]; // [rsp+13C8h] [rbp+12C8h] BYREF
  _BYTE v1029[32]; // [rsp+13E8h] [rbp+12E8h] BYREF
  _BYTE v1030[32]; // [rsp+1408h] [rbp+1308h] BYREF
  _BYTE v1031[32]; // [rsp+1428h] [rbp+1328h] BYREF
  _BYTE v1032[32]; // [rsp+1448h] [rbp+1348h] BYREF
  _BYTE v1033[32]; // [rsp+1468h] [rbp+1368h] BYREF
  _BYTE v1034[32]; // [rsp+1488h] [rbp+1388h] BYREF
  _BYTE v1035[32]; // [rsp+14A8h] [rbp+13A8h] BYREF
  _BYTE v1036[32]; // [rsp+14C8h] [rbp+13C8h] BYREF
  _BYTE v1037[32]; // [rsp+14E8h] [rbp+13E8h] BYREF
  _BYTE v1038[32]; // [rsp+1508h] [rbp+1408h] BYREF
  _BYTE v1039[32]; // [rsp+1528h] [rbp+1428h] BYREF
  _BYTE v1040[32]; // [rsp+1548h] [rbp+1448h] BYREF
  _BYTE v1041[32]; // [rsp+1568h] [rbp+1468h] BYREF
  _BYTE v1042[32]; // [rsp+1588h] [rbp+1488h] BYREF
  _BYTE v1043[32]; // [rsp+15A8h] [rbp+14A8h] BYREF
  _BYTE v1044[32]; // [rsp+15C8h] [rbp+14C8h] BYREF
  _BYTE v1045[32]; // [rsp+15E8h] [rbp+14E8h] BYREF
  _BYTE v1046[32]; // [rsp+1608h] [rbp+1508h] BYREF
  _BYTE v1047[32]; // [rsp+1628h] [rbp+1528h] BYREF
  _BYTE v1048[32]; // [rsp+1648h] [rbp+1548h] BYREF
  _BYTE v1049[32]; // [rsp+1668h] [rbp+1568h] BYREF
  _BYTE v1050[32]; // [rsp+1688h] [rbp+1588h] BYREF
  _BYTE v1051[32]; // [rsp+16A8h] [rbp+15A8h] BYREF
  _BYTE v1052[32]; // [rsp+16C8h] [rbp+15C8h] BYREF
  _BYTE v1053[32]; // [rsp+16E8h] [rbp+15E8h] BYREF
  _BYTE v1054[32]; // [rsp+1708h] [rbp+1608h] BYREF
  _BYTE v1055[32]; // [rsp+1728h] [rbp+1628h] BYREF
  _BYTE v1056[32]; // [rsp+1748h] [rbp+1648h] BYREF
  _BYTE v1057[32]; // [rsp+1768h] [rbp+1668h] BYREF
  _BYTE v1058[32]; // [rsp+1788h] [rbp+1688h] BYREF
  _BYTE v1059[32]; // [rsp+17A8h] [rbp+16A8h] BYREF
  _BYTE v1060[24]; // [rsp+17C8h] [rbp+16C8h] BYREF
  char v1061; // [rsp+17E0h] [rbp+16E0h] BYREF
  char v1062; // [rsp+1810h] [rbp+1710h] BYREF
  char v1063; // [rsp+1840h] [rbp+1740h] BYREF
  char v1064; // [rsp+1870h] [rbp+1770h] BYREF
  char v1065; // [rsp+18A0h] [rbp+17A0h] BYREF
  char v1066; // [rsp+18D0h] [rbp+17D0h] BYREF
  char v1067; // [rsp+1900h] [rbp+1800h] BYREF
  char v1068; // [rsp+1930h] [rbp+1830h] BYREF
  char v1069; // [rsp+1960h] [rbp+1860h] BYREF
  char v1070; // [rsp+1990h] [rbp+1890h] BYREF
  char v1071; // [rsp+19C0h] [rbp+18C0h] BYREF
  char v1072; // [rsp+19F0h] [rbp+18F0h] BYREF
  char v1073; // [rsp+1A20h] [rbp+1920h] BYREF
  char v1074; // [rsp+1A50h] [rbp+1950h] BYREF
  char v1075; // [rsp+1A80h] [rbp+1980h] BYREF
  char v1076; // [rsp+1AB0h] [rbp+19B0h] BYREF
  char v1077; // [rsp+1AE0h] [rbp+19E0h] BYREF
  char v1078; // [rsp+1B10h] [rbp+1A10h] BYREF
  char v1079; // [rsp+1B40h] [rbp+1A40h] BYREF
  char v1080; // [rsp+1B70h] [rbp+1A70h] BYREF
  char v1081; // [rsp+1BA0h] [rbp+1AA0h] BYREF
  char v1082; // [rsp+1BD0h] [rbp+1AD0h] BYREF
  char v1083; // [rsp+1C00h] [rbp+1B00h] BYREF
  char v1084; // [rsp+1C30h] [rbp+1B30h] BYREF
  char v1085; // [rsp+1C60h] [rbp+1B60h] BYREF
  char v1086; // [rsp+1C90h] [rbp+1B90h] BYREF
  char v1087; // [rsp+1CC0h] [rbp+1BC0h] BYREF
  char v1088; // [rsp+1CF0h] [rbp+1BF0h] BYREF
  char v1089; // [rsp+1D20h] [rbp+1C20h] BYREF
  char v1090; // [rsp+1D50h] [rbp+1C50h] BYREF
  char v1091; // [rsp+1D80h] [rbp+1C80h] BYREF
  char v1092; // [rsp+1DB0h] [rbp+1CB0h] BYREF
  char v1093; // [rsp+1DE0h] [rbp+1CE0h] BYREF
  char v1094; // [rsp+1E10h] [rbp+1D10h] BYREF
  char v1095; // [rsp+1E40h] [rbp+1D40h] BYREF
  char v1096; // [rsp+1E70h] [rbp+1D70h] BYREF
  char v1097; // [rsp+1EA0h] [rbp+1DA0h] BYREF
  char v1098; // [rsp+1ED0h] [rbp+1DD0h] BYREF
  char v1099; // [rsp+1F00h] [rbp+1E00h] BYREF
  char v1100; // [rsp+1F30h] [rbp+1E30h] BYREF
  char v1101; // [rsp+1F60h] [rbp+1E60h] BYREF
  char v1102; // [rsp+1F90h] [rbp+1E90h] BYREF
  char v1103; // [rsp+1FC0h] [rbp+1EC0h] BYREF
  char v1104; // [rsp+1FF0h] [rbp+1EF0h] BYREF
  char v1105; // [rsp+2020h] [rbp+1F20h] BYREF
  char v1106; // [rsp+2050h] [rbp+1F50h] BYREF
  char v1107; // [rsp+2080h] [rbp+1F80h] BYREF
  char v1108; // [rsp+20B0h] [rbp+1FB0h] BYREF
  char v1109; // [rsp+20E0h] [rbp+1FE0h] BYREF
  char v1110; // [rsp+2110h] [rbp+2010h] BYREF
  char v1111; // [rsp+2140h] [rbp+2040h] BYREF
  char v1112; // [rsp+2170h] [rbp+2070h] BYREF
  char v1113; // [rsp+21A0h] [rbp+20A0h] BYREF
  char v1114; // [rsp+21D0h] [rbp+20D0h] BYREF
  char v1115; // [rsp+2200h] [rbp+2100h] BYREF
  char v1116; // [rsp+2230h] [rbp+2130h] BYREF
  char v1117; // [rsp+2260h] [rbp+2160h] BYREF
  char v1118; // [rsp+2290h] [rbp+2190h] BYREF
  char v1119; // [rsp+22C0h] [rbp+21C0h] BYREF
  char v1120; // [rsp+22F0h] [rbp+21F0h] BYREF
  char v1121; // [rsp+2320h] [rbp+2220h] BYREF
  char v1122; // [rsp+2350h] [rbp+2250h] BYREF
  char v1123; // [rsp+2380h] [rbp+2280h] BYREF
  char v1124; // [rsp+23B0h] [rbp+22B0h] BYREF
  char v1125; // [rsp+23E0h] [rbp+22E0h] BYREF
  char v1126; // [rsp+2410h] [rbp+2310h] BYREF
  char v1127; // [rsp+2440h] [rbp+2340h] BYREF
  char v1128; // [rsp+2470h] [rbp+2370h] BYREF
  char v1129; // [rsp+24A0h] [rbp+23A0h] BYREF
  char v1130; // [rsp+24D0h] [rbp+23D0h] BYREF
  char v1131; // [rsp+2500h] [rbp+2400h] BYREF
  char v1132; // [rsp+2530h] [rbp+2430h] BYREF
  char v1133; // [rsp+2560h] [rbp+2460h] BYREF
  char v1134; // [rsp+2590h] [rbp+2490h] BYREF
  char v1135; // [rsp+25C0h] [rbp+24C0h] BYREF
  char v1136; // [rsp+25F0h] [rbp+24F0h] BYREF
  char v1137; // [rsp+2620h] [rbp+2520h] BYREF
  char v1138; // [rsp+2650h] [rbp+2550h] BYREF
  char v1139; // [rsp+2680h] [rbp+2580h] BYREF
  char v1140; // [rsp+26B0h] [rbp+25B0h] BYREF
  char v1141; // [rsp+26E0h] [rbp+25E0h] BYREF
  char v1142; // [rsp+2710h] [rbp+2610h] BYREF
  char v1143; // [rsp+2740h] [rbp+2640h] BYREF
  char v1144; // [rsp+2770h] [rbp+2670h] BYREF
  char v1145; // [rsp+27A0h] [rbp+26A0h] BYREF
  char v1146; // [rsp+27D0h] [rbp+26D0h] BYREF
  char v1147; // [rsp+2800h] [rbp+2700h] BYREF
  char v1148; // [rsp+2830h] [rbp+2730h] BYREF
  char v1149; // [rsp+2860h] [rbp+2760h] BYREF
  char v1150; // [rsp+2890h] [rbp+2790h] BYREF
  char v1151; // [rsp+28C0h] [rbp+27C0h] BYREF
  char v1152; // [rsp+28F0h] [rbp+27F0h] BYREF
  char v1153; // [rsp+2920h] [rbp+2820h] BYREF
  char v1154; // [rsp+2950h] [rbp+2850h] BYREF
  char v1155; // [rsp+2980h] [rbp+2880h] BYREF
  char v1156; // [rsp+29B0h] [rbp+28B0h] BYREF
  char v1157; // [rsp+29E0h] [rbp+28E0h] BYREF
  char v1158; // [rsp+2A10h] [rbp+2910h] BYREF
  char v1159; // [rsp+2A40h] [rbp+2940h] BYREF
  char v1160; // [rsp+2A70h] [rbp+2970h] BYREF
  char v1161; // [rsp+2AA0h] [rbp+29A0h] BYREF
  char v1162; // [rsp+2AD0h] [rbp+29D0h] BYREF
  char v1163; // [rsp+2B00h] [rbp+2A00h] BYREF
  char v1164; // [rsp+2B30h] [rbp+2A30h] BYREF
  char v1165; // [rsp+2B60h] [rbp+2A60h] BYREF
  char v1166; // [rsp+2B90h] [rbp+2A90h] BYREF
  char v1167; // [rsp+2BC0h] [rbp+2AC0h] BYREF
  char v1168; // [rsp+2BF0h] [rbp+2AF0h] BYREF
  char v1169; // [rsp+2C20h] [rbp+2B20h] BYREF
  char v1170; // [rsp+2C50h] [rbp+2B50h] BYREF
  char v1171; // [rsp+2C80h] [rbp+2B80h] BYREF
  char v1172; // [rsp+2CB0h] [rbp+2BB0h] BYREF
  char v1173; // [rsp+2CE0h] [rbp+2BE0h] BYREF
  char v1174; // [rsp+2D10h] [rbp+2C10h] BYREF
  char v1175; // [rsp+2D40h] [rbp+2C40h] BYREF
  char v1176; // [rsp+2D70h] [rbp+2C70h] BYREF
  char v1177; // [rsp+2DA0h] [rbp+2CA0h] BYREF
  char v1178; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  char v1179; // [rsp+2E00h] [rbp+2D00h] BYREF
  char v1180; // [rsp+2E30h] [rbp+2D30h] BYREF
  char v1181; // [rsp+2E60h] [rbp+2D60h] BYREF
  char v1182; // [rsp+2E90h] [rbp+2D90h] BYREF
  char v1183; // [rsp+2EC0h] [rbp+2DC0h] BYREF
  char v1184; // [rsp+2EF0h] [rbp+2DF0h] BYREF
  char v1185; // [rsp+2F20h] [rbp+2E20h] BYREF
  char v1186; // [rsp+2F50h] [rbp+2E50h] BYREF
  char v1187; // [rsp+2F80h] [rbp+2E80h] BYREF
  char v1188; // [rsp+2FB0h] [rbp+2EB0h] BYREF
  char v1189; // [rsp+2FE0h] [rbp+2EE0h] BYREF
  char v1190; // [rsp+3010h] [rbp+2F10h] BYREF
  char v1191; // [rsp+3040h] [rbp+2F40h] BYREF
  char v1192; // [rsp+3070h] [rbp+2F70h] BYREF
  char v1193; // [rsp+30A0h] [rbp+2FA0h] BYREF
  char v1194; // [rsp+30D0h] [rbp+2FD0h] BYREF
  char v1195; // [rsp+3100h] [rbp+3000h] BYREF
  char v1196; // [rsp+3130h] [rbp+3030h] BYREF
  char v1197; // [rsp+3160h] [rbp+3060h] BYREF
  char v1198; // [rsp+3190h] [rbp+3090h] BYREF
  char v1199; // [rsp+31C0h] [rbp+30C0h] BYREF
  char v1200; // [rsp+31F0h] [rbp+30F0h] BYREF
  char v1201; // [rsp+3220h] [rbp+3120h] BYREF
  char v1202; // [rsp+3250h] [rbp+3150h] BYREF
  char v1203; // [rsp+3280h] [rbp+3180h] BYREF
  char v1204; // [rsp+32B0h] [rbp+31B0h] BYREF
  char v1205; // [rsp+32E0h] [rbp+31E0h] BYREF
  char v1206; // [rsp+3310h] [rbp+3210h] BYREF
  char v1207; // [rsp+3340h] [rbp+3240h] BYREF
  char v1208; // [rsp+3370h] [rbp+3270h] BYREF
  char v1209; // [rsp+33A8h] [rbp+32A8h] BYREF
  char v1210; // [rsp+33E0h] [rbp+32E0h] BYREF
  char v1211; // [rsp+3418h] [rbp+3318h] BYREF
  char v1212; // [rsp+3450h] [rbp+3350h] BYREF
  _QWORD v1213[4]; // [rsp+3488h] [rbp+3388h] BYREF
  _QWORD v1214[4]; // [rsp+34A8h] [rbp+33A8h] BYREF
  _QWORD v1215[4]; // [rsp+34C8h] [rbp+33C8h] BYREF
  _QWORD v1216[4]; // [rsp+34E8h] [rbp+33E8h] BYREF
  _QWORD v1217[4]; // [rsp+3508h] [rbp+3408h] BYREF
  _QWORD v1218[4]; // [rsp+3528h] [rbp+3428h] BYREF
  _QWORD v1219[4]; // [rsp+3548h] [rbp+3448h] BYREF
  _QWORD v1220[4]; // [rsp+3568h] [rbp+3468h] BYREF
  _QWORD v1221[4]; // [rsp+3588h] [rbp+3488h] BYREF
  _QWORD v1222[4]; // [rsp+35A8h] [rbp+34A8h] BYREF
  _QWORD v1223[4]; // [rsp+35C8h] [rbp+34C8h] BYREF
  _QWORD v1224[4]; // [rsp+35E8h] [rbp+34E8h] BYREF
  _QWORD v1225[4]; // [rsp+3608h] [rbp+3508h] BYREF
  _QWORD v1226[4]; // [rsp+3628h] [rbp+3528h] BYREF
  _QWORD v1227[4]; // [rsp+3648h] [rbp+3548h] BYREF
  _QWORD v1228[4]; // [rsp+3668h] [rbp+3568h] BYREF
  _QWORD v1229[4]; // [rsp+3688h] [rbp+3588h] BYREF
  _QWORD v1230[4]; // [rsp+36A8h] [rbp+35A8h] BYREF
  _QWORD v1231[4]; // [rsp+36C8h] [rbp+35C8h] BYREF
  _QWORD v1232[4]; // [rsp+36E8h] [rbp+35E8h] BYREF
  _QWORD v1233[4]; // [rsp+3708h] [rbp+3608h] BYREF
  _QWORD v1234[4]; // [rsp+3728h] [rbp+3628h] BYREF
  _QWORD v1235[4]; // [rsp+3748h] [rbp+3648h] BYREF
  _QWORD v1236[4]; // [rsp+3768h] [rbp+3668h] BYREF
  _QWORD v1237[4]; // [rsp+3788h] [rbp+3688h] BYREF
  _QWORD v1238[4]; // [rsp+37A8h] [rbp+36A8h] BYREF
  _QWORD v1239[4]; // [rsp+37C8h] [rbp+36C8h] BYREF
  _QWORD v1240[4]; // [rsp+37E8h] [rbp+36E8h] BYREF
  _QWORD v1241[4]; // [rsp+3808h] [rbp+3708h] BYREF
  _QWORD v1242[4]; // [rsp+3828h] [rbp+3728h] BYREF
  _QWORD v1243[4]; // [rsp+3848h] [rbp+3748h] BYREF
  _QWORD v1244[4]; // [rsp+3868h] [rbp+3768h] BYREF
  _QWORD v1245[4]; // [rsp+3888h] [rbp+3788h] BYREF
  _QWORD v1246[4]; // [rsp+38A8h] [rbp+37A8h] BYREF
  _QWORD v1247[4]; // [rsp+38C8h] [rbp+37C8h] BYREF
  _QWORD v1248[4]; // [rsp+38E8h] [rbp+37E8h] BYREF
  _QWORD v1249[4]; // [rsp+3908h] [rbp+3808h] BYREF
  _QWORD v1250[4]; // [rsp+3928h] [rbp+3828h] BYREF
  _QWORD v1251[4]; // [rsp+3948h] [rbp+3848h] BYREF
  _QWORD v1252[4]; // [rsp+3968h] [rbp+3868h] BYREF
  _QWORD v1253[4]; // [rsp+3988h] [rbp+3888h] BYREF
  _QWORD v1254[4]; // [rsp+39A8h] [rbp+38A8h] BYREF
  _QWORD v1255[4]; // [rsp+39C8h] [rbp+38C8h] BYREF
  _QWORD v1256[4]; // [rsp+39E8h] [rbp+38E8h] BYREF
  _QWORD v1257[4]; // [rsp+3A08h] [rbp+3908h] BYREF
  _QWORD v1258[4]; // [rsp+3A28h] [rbp+3928h] BYREF
  _QWORD v1259[4]; // [rsp+3A48h] [rbp+3948h] BYREF
  _QWORD v1260[4]; // [rsp+3A68h] [rbp+3968h] BYREF
  _QWORD v1261[4]; // [rsp+3A88h] [rbp+3988h] BYREF
  _QWORD v1262[4]; // [rsp+3AA8h] [rbp+39A8h] BYREF
  _QWORD v1263[4]; // [rsp+3AC8h] [rbp+39C8h] BYREF
  _QWORD v1264[4]; // [rsp+3AE8h] [rbp+39E8h] BYREF
  _QWORD v1265[4]; // [rsp+3B08h] [rbp+3A08h] BYREF
  _QWORD v1266[4]; // [rsp+3B28h] [rbp+3A28h] BYREF
  _QWORD v1267[4]; // [rsp+3B48h] [rbp+3A48h] BYREF
  _QWORD v1268[4]; // [rsp+3B68h] [rbp+3A68h] BYREF
  _QWORD v1269[4]; // [rsp+3B88h] [rbp+3A88h] BYREF
  _OWORD v1270[2]; // [rsp+3BA8h] [rbp+3AA8h] BYREF
  __int64 v1271; // [rsp+3BC8h] [rbp+3AC8h]
  _OWORD v1272[2]; // [rsp+3BD0h] [rbp+3AD0h] BYREF
  __int64 v1273; // [rsp+3BF0h] [rbp+3AF0h]
  _QWORD v1274[4]; // [rsp+3BF8h] [rbp+3AF8h] BYREF
  _QWORD v1275[4]; // [rsp+3C18h] [rbp+3B18h] BYREF
  _QWORD v1276[4]; // [rsp+3C38h] [rbp+3B38h] BYREF
  _QWORD v1277[4]; // [rsp+3C58h] [rbp+3B58h] BYREF
  _QWORD v1278[4]; // [rsp+3C78h] [rbp+3B78h] BYREF
  _QWORD v1279[4]; // [rsp+3C98h] [rbp+3B98h] BYREF
  _QWORD v1280[4]; // [rsp+3CB8h] [rbp+3BB8h] BYREF
  _QWORD v1281[4]; // [rsp+3CD8h] [rbp+3BD8h] BYREF
  _QWORD v1282[4]; // [rsp+3CF8h] [rbp+3BF8h] BYREF
  _QWORD v1283[4]; // [rsp+3D18h] [rbp+3C18h] BYREF
  _QWORD v1284[4]; // [rsp+3D38h] [rbp+3C38h] BYREF
  _QWORD v1285[4]; // [rsp+3D58h] [rbp+3C58h] BYREF
  _QWORD v1286[4]; // [rsp+3D78h] [rbp+3C78h] BYREF
  _BYTE v1287[40]; // [rsp+3D98h] [rbp+3C98h] BYREF
  _BYTE v1288[40]; // [rsp+3DC0h] [rbp+3CC0h] BYREF
  _BYTE v1289[40]; // [rsp+3DE8h] [rbp+3CE8h] BYREF
  _BYTE v1290[40]; // [rsp+3E10h] [rbp+3D10h] BYREF
  _BYTE v1291[40]; // [rsp+3E38h] [rbp+3D38h] BYREF
  _BYTE v1292[40]; // [rsp+3E60h] [rbp+3D60h] BYREF
  _BYTE v1293[40]; // [rsp+3E88h] [rbp+3D88h] BYREF
  _BYTE v1294[40]; // [rsp+3EB0h] [rbp+3DB0h] BYREF
  _BYTE v1295[40]; // [rsp+3ED8h] [rbp+3DD8h] BYREF
  _BYTE v1296[40]; // [rsp+3F00h] [rbp+3E00h] BYREF
  _BYTE v1297[40]; // [rsp+3F28h] [rbp+3E28h] BYREF
  _BYTE v1298[40]; // [rsp+3F50h] [rbp+3E50h] BYREF
  _BYTE v1299[40]; // [rsp+3F78h] [rbp+3E78h] BYREF
  _BYTE v1300[40]; // [rsp+3FA0h] [rbp+3EA0h] BYREF
  _BYTE v1301[40]; // [rsp+3FC8h] [rbp+3EC8h] BYREF
  _BYTE v1302[40]; // [rsp+3FF0h] [rbp+3EF0h] BYREF
  _BYTE v1303[40]; // [rsp+4018h] [rbp+3F18h] BYREF
  _BYTE v1304[40]; // [rsp+4040h] [rbp+3F40h] BYREF
  _BYTE v1305[40]; // [rsp+4068h] [rbp+3F68h] BYREF
  _BYTE v1306[40]; // [rsp+4090h] [rbp+3F90h] BYREF
  _BYTE v1307[40]; // [rsp+40B8h] [rbp+3FB8h] BYREF
  _BYTE v1308[40]; // [rsp+40E0h] [rbp+3FE0h] BYREF
  _BYTE v1309[40]; // [rsp+4108h] [rbp+4008h] BYREF
  _BYTE v1310[40]; // [rsp+4130h] [rbp+4030h] BYREF
  _BYTE v1311[40]; // [rsp+4158h] [rbp+4058h] BYREF
  _BYTE v1312[40]; // [rsp+4180h] [rbp+4080h] BYREF
  _BYTE v1313[40]; // [rsp+41A8h] [rbp+40A8h] BYREF
  _BYTE v1314[40]; // [rsp+41D0h] [rbp+40D0h] BYREF
  _BYTE v1315[40]; // [rsp+41F8h] [rbp+40F8h] BYREF
  _BYTE v1316[40]; // [rsp+4220h] [rbp+4120h] BYREF
  _BYTE v1317[40]; // [rsp+4248h] [rbp+4148h] BYREF
  _BYTE v1318[40]; // [rsp+4270h] [rbp+4170h] BYREF
  _BYTE v1319[40]; // [rsp+4298h] [rbp+4198h] BYREF
  _BYTE v1320[40]; // [rsp+42C0h] [rbp+41C0h] BYREF
  _BYTE v1321[40]; // [rsp+42E8h] [rbp+41E8h] BYREF
  _BYTE v1322[40]; // [rsp+4310h] [rbp+4210h] BYREF
  _BYTE v1323[40]; // [rsp+4338h] [rbp+4238h] BYREF
  _BYTE v1324[40]; // [rsp+4360h] [rbp+4260h] BYREF
  _BYTE v1325[40]; // [rsp+4388h] [rbp+4288h] BYREF
  _BYTE v1326[40]; // [rsp+43B0h] [rbp+42B0h] BYREF
  _BYTE v1327[40]; // [rsp+43D8h] [rbp+42D8h] BYREF
  _BYTE v1328[40]; // [rsp+4400h] [rbp+4300h] BYREF
  _BYTE v1329[40]; // [rsp+4428h] [rbp+4328h] BYREF
  _BYTE v1330[40]; // [rsp+4450h] [rbp+4350h] BYREF
  _BYTE v1331[40]; // [rsp+4478h] [rbp+4378h] BYREF
  _BYTE v1332[40]; // [rsp+44A0h] [rbp+43A0h] BYREF
  _BYTE v1333[40]; // [rsp+44C8h] [rbp+43C8h] BYREF
  _BYTE v1334[40]; // [rsp+44F0h] [rbp+43F0h] BYREF
  _BYTE v1335[40]; // [rsp+4518h] [rbp+4418h] BYREF
  _BYTE v1336[40]; // [rsp+4540h] [rbp+4440h] BYREF
  _BYTE v1337[40]; // [rsp+4568h] [rbp+4468h] BYREF
  _BYTE v1338[40]; // [rsp+4590h] [rbp+4490h] BYREF
  _BYTE v1339[40]; // [rsp+45B8h] [rbp+44B8h] BYREF
  _BYTE v1340[40]; // [rsp+45E0h] [rbp+44E0h] BYREF
  _BYTE v1341[40]; // [rsp+4608h] [rbp+4508h] BYREF
  _BYTE v1342[40]; // [rsp+4630h] [rbp+4530h] BYREF
  _BYTE v1343[40]; // [rsp+4658h] [rbp+4558h] BYREF
  _BYTE v1344[40]; // [rsp+4680h] [rbp+4580h] BYREF
  _BYTE v1345[40]; // [rsp+46A8h] [rbp+45A8h] BYREF
  _BYTE v1346[40]; // [rsp+46D0h] [rbp+45D0h] BYREF
  _BYTE v1347[40]; // [rsp+46F8h] [rbp+45F8h] BYREF
  _BYTE v1348[40]; // [rsp+4720h] [rbp+4620h] BYREF
  _BYTE v1349[40]; // [rsp+4748h] [rbp+4648h] BYREF
  _BYTE v1350[40]; // [rsp+4770h] [rbp+4670h] BYREF
  _BYTE v1351[40]; // [rsp+4798h] [rbp+4698h] BYREF
  _BYTE v1352[40]; // [rsp+47C0h] [rbp+46C0h] BYREF
  _BYTE v1353[40]; // [rsp+47E8h] [rbp+46E8h] BYREF
  _BYTE v1354[40]; // [rsp+4810h] [rbp+4710h] BYREF
  _BYTE v1355[40]; // [rsp+4838h] [rbp+4738h] BYREF
  _BYTE v1356[40]; // [rsp+4860h] [rbp+4760h] BYREF
  _BYTE v1357[40]; // [rsp+4888h] [rbp+4788h] BYREF
  _BYTE v1358[40]; // [rsp+48B0h] [rbp+47B0h] BYREF
  _BYTE v1359[40]; // [rsp+48D8h] [rbp+47D8h] BYREF
  _BYTE v1360[40]; // [rsp+4900h] [rbp+4800h] BYREF
  _BYTE v1361[40]; // [rsp+4928h] [rbp+4828h] BYREF
  _BYTE v1362[40]; // [rsp+4950h] [rbp+4850h] BYREF
  _BYTE v1363[40]; // [rsp+4978h] [rbp+4878h] BYREF
  _BYTE v1364[40]; // [rsp+49A0h] [rbp+48A0h] BYREF
  _BYTE v1365[40]; // [rsp+49C8h] [rbp+48C8h] BYREF
  _BYTE v1366[40]; // [rsp+49F0h] [rbp+48F0h] BYREF
  _BYTE v1367[40]; // [rsp+4A18h] [rbp+4918h] BYREF
  _BYTE v1368[40]; // [rsp+4A40h] [rbp+4940h] BYREF
  _BYTE v1369[40]; // [rsp+4A68h] [rbp+4968h] BYREF
  _BYTE v1370[40]; // [rsp+4A90h] [rbp+4990h] BYREF
  _BYTE v1371[40]; // [rsp+4AB8h] [rbp+49B8h] BYREF
  _BYTE v1372[40]; // [rsp+4AE0h] [rbp+49E0h] BYREF
  _BYTE v1373[40]; // [rsp+4B08h] [rbp+4A08h] BYREF
  _BYTE v1374[40]; // [rsp+4B30h] [rbp+4A30h] BYREF
  _BYTE v1375[40]; // [rsp+4B58h] [rbp+4A58h] BYREF
  _BYTE v1376[40]; // [rsp+4B80h] [rbp+4A80h] BYREF
  _BYTE v1377[40]; // [rsp+4BA8h] [rbp+4AA8h] BYREF
  _BYTE v1378[40]; // [rsp+4BD0h] [rbp+4AD0h] BYREF
  _BYTE v1379[40]; // [rsp+4BF8h] [rbp+4AF8h] BYREF
  _BYTE v1380[40]; // [rsp+4C20h] [rbp+4B20h] BYREF
  _BYTE v1381[40]; // [rsp+4C48h] [rbp+4B48h] BYREF
  _BYTE v1382[40]; // [rsp+4C70h] [rbp+4B70h] BYREF
  _BYTE v1383[40]; // [rsp+4C98h] [rbp+4B98h] BYREF
  _BYTE v1384[40]; // [rsp+4CC0h] [rbp+4BC0h] BYREF
  _BYTE v1385[40]; // [rsp+4CE8h] [rbp+4BE8h] BYREF
  _BYTE v1386[40]; // [rsp+4D10h] [rbp+4C10h] BYREF
  _BYTE v1387[40]; // [rsp+4D38h] [rbp+4C38h] BYREF
  _BYTE v1388[40]; // [rsp+4D60h] [rbp+4C60h] BYREF
  _BYTE v1389[40]; // [rsp+4D88h] [rbp+4C88h] BYREF
  _BYTE v1390[40]; // [rsp+4DB0h] [rbp+4CB0h] BYREF
  _BYTE v1391[40]; // [rsp+4DD8h] [rbp+4CD8h] BYREF
  _BYTE v1392[40]; // [rsp+4E00h] [rbp+4D00h] BYREF
  _BYTE v1393[40]; // [rsp+4E28h] [rbp+4D28h] BYREF
  _BYTE v1394[40]; // [rsp+4E50h] [rbp+4D50h] BYREF
  _BYTE v1395[40]; // [rsp+4E78h] [rbp+4D78h] BYREF
  _BYTE v1396[40]; // [rsp+4EA0h] [rbp+4DA0h] BYREF
  _BYTE v1397[40]; // [rsp+4EC8h] [rbp+4DC8h] BYREF
  _BYTE v1398[40]; // [rsp+4EF0h] [rbp+4DF0h] BYREF
  _BYTE v1399[40]; // [rsp+4F18h] [rbp+4E18h] BYREF
  _BYTE v1400[40]; // [rsp+4F40h] [rbp+4E40h] BYREF
  _BYTE v1401[40]; // [rsp+4F68h] [rbp+4E68h] BYREF
  _BYTE v1402[40]; // [rsp+4F90h] [rbp+4E90h] BYREF
  _BYTE v1403[40]; // [rsp+4FB8h] [rbp+4EB8h] BYREF
  _BYTE v1404[40]; // [rsp+4FE0h] [rbp+4EE0h] BYREF
  _BYTE v1405[40]; // [rsp+5008h] [rbp+4F08h] BYREF
  _BYTE v1406[40]; // [rsp+5030h] [rbp+4F30h] BYREF
  _BYTE v1407[40]; // [rsp+5058h] [rbp+4F58h] BYREF
  _BYTE v1408[40]; // [rsp+5080h] [rbp+4F80h] BYREF
  _BYTE v1409[40]; // [rsp+50A8h] [rbp+4FA8h] BYREF
  _BYTE v1410[40]; // [rsp+50D0h] [rbp+4FD0h] BYREF
  _BYTE v1411[40]; // [rsp+50F8h] [rbp+4FF8h] BYREF
  _BYTE v1412[40]; // [rsp+5120h] [rbp+5020h] BYREF
  _BYTE v1413[40]; // [rsp+5148h] [rbp+5048h] BYREF
  _BYTE v1414[40]; // [rsp+5170h] [rbp+5070h] BYREF
  _BYTE v1415[40]; // [rsp+5198h] [rbp+5098h] BYREF
  _BYTE v1416[40]; // [rsp+51C0h] [rbp+50C0h] BYREF
  _BYTE v1417[40]; // [rsp+51E8h] [rbp+50E8h] BYREF
  _BYTE v1418[40]; // [rsp+5210h] [rbp+5110h] BYREF
  _BYTE v1419[40]; // [rsp+5238h] [rbp+5138h] BYREF
  _BYTE v1420[40]; // [rsp+5260h] [rbp+5160h] BYREF
  _BYTE v1421[40]; // [rsp+5288h] [rbp+5188h] BYREF
  _BYTE v1422[40]; // [rsp+52B0h] [rbp+51B0h] BYREF
  _BYTE v1423[40]; // [rsp+52D8h] [rbp+51D8h] BYREF
  _BYTE v1424[40]; // [rsp+5300h] [rbp+5200h] BYREF
  _BYTE v1425[40]; // [rsp+5328h] [rbp+5228h] BYREF
  _BYTE v1426[40]; // [rsp+5350h] [rbp+5250h] BYREF
  _BYTE v1427[40]; // [rsp+5378h] [rbp+5278h] BYREF
  _BYTE v1428[40]; // [rsp+53A0h] [rbp+52A0h] BYREF
  _BYTE v1429[40]; // [rsp+53C8h] [rbp+52C8h] BYREF
  _BYTE v1430[40]; // [rsp+53F0h] [rbp+52F0h] BYREF
  _BYTE v1431[40]; // [rsp+5418h] [rbp+5318h] BYREF
  _BYTE v1432[40]; // [rsp+5440h] [rbp+5340h] BYREF
  _BYTE v1433[40]; // [rsp+5468h] [rbp+5368h] BYREF
  _BYTE v1434[40]; // [rsp+5490h] [rbp+5390h] BYREF
  _BYTE v1435[40]; // [rsp+54B8h] [rbp+53B8h] BYREF
  _BYTE v1436[40]; // [rsp+54E0h] [rbp+53E0h] BYREF
  _BYTE v1437[40]; // [rsp+5508h] [rbp+5408h] BYREF
  _BYTE v1438[40]; // [rsp+5530h] [rbp+5430h] BYREF
  _BYTE v1439[40]; // [rsp+5558h] [rbp+5458h] BYREF
  _BYTE v1440[40]; // [rsp+5580h] [rbp+5480h] BYREF
  _BYTE v1441[40]; // [rsp+55A8h] [rbp+54A8h] BYREF
  _BYTE v1442[40]; // [rsp+55D0h] [rbp+54D0h] BYREF
  _BYTE v1443[40]; // [rsp+55F8h] [rbp+54F8h] BYREF
  _BYTE v1444[40]; // [rsp+5620h] [rbp+5520h] BYREF
  _BYTE v1445[40]; // [rsp+5648h] [rbp+5548h] BYREF
  _BYTE v1446[40]; // [rsp+5670h] [rbp+5570h] BYREF
  _BYTE v1447[40]; // [rsp+5698h] [rbp+5598h] BYREF
  _BYTE v1448[40]; // [rsp+56C0h] [rbp+55C0h] BYREF
  _BYTE v1449[40]; // [rsp+56E8h] [rbp+55E8h] BYREF
  _BYTE v1450[40]; // [rsp+5710h] [rbp+5610h] BYREF
  _BYTE v1451[40]; // [rsp+5738h] [rbp+5638h] BYREF
  _BYTE v1452[40]; // [rsp+5760h] [rbp+5660h] BYREF
  _BYTE v1453[40]; // [rsp+5788h] [rbp+5688h] BYREF
  _BYTE v1454[40]; // [rsp+57B0h] [rbp+56B0h] BYREF
  _BYTE v1455[40]; // [rsp+57D8h] [rbp+56D8h] BYREF
  _BYTE v1456[40]; // [rsp+5800h] [rbp+5700h] BYREF
  _BYTE v1457[40]; // [rsp+5828h] [rbp+5728h] BYREF
  _BYTE v1458[40]; // [rsp+5850h] [rbp+5750h] BYREF
  _BYTE v1459[40]; // [rsp+5878h] [rbp+5778h] BYREF
  _BYTE v1460[40]; // [rsp+58A0h] [rbp+57A0h] BYREF
  _BYTE v1461[40]; // [rsp+58C8h] [rbp+57C8h] BYREF
  _BYTE v1462[40]; // [rsp+58F0h] [rbp+57F0h] BYREF
  _BYTE v1463[40]; // [rsp+5918h] [rbp+5818h] BYREF
  _BYTE v1464[40]; // [rsp+5940h] [rbp+5840h] BYREF
  _BYTE v1465[40]; // [rsp+5968h] [rbp+5868h] BYREF
  _BYTE v1466[40]; // [rsp+5990h] [rbp+5890h] BYREF
  _BYTE v1467[40]; // [rsp+59B8h] [rbp+58B8h] BYREF
  _BYTE v1468[40]; // [rsp+59E0h] [rbp+58E0h] BYREF
  _BYTE v1469[40]; // [rsp+5A08h] [rbp+5908h] BYREF
  _BYTE v1470[40]; // [rsp+5A30h] [rbp+5930h] BYREF
  _BYTE v1471[40]; // [rsp+5A58h] [rbp+5958h] BYREF
  _BYTE v1472[40]; // [rsp+5A80h] [rbp+5980h] BYREF
  _BYTE v1473[40]; // [rsp+5AA8h] [rbp+59A8h] BYREF
  _BYTE v1474[40]; // [rsp+5AD0h] [rbp+59D0h] BYREF
  _BYTE v1475[40]; // [rsp+5AF8h] [rbp+59F8h] BYREF
  _BYTE v1476[40]; // [rsp+5B20h] [rbp+5A20h] BYREF
  _BYTE v1477[40]; // [rsp+5B48h] [rbp+5A48h] BYREF
  _BYTE v1478[40]; // [rsp+5B70h] [rbp+5A70h] BYREF
  _BYTE v1479[40]; // [rsp+5B98h] [rbp+5A98h] BYREF
  _BYTE v1480[40]; // [rsp+5BC0h] [rbp+5AC0h] BYREF
  _BYTE v1481[40]; // [rsp+5BE8h] [rbp+5AE8h] BYREF
  _BYTE v1482[40]; // [rsp+5C10h] [rbp+5B10h] BYREF
  _BYTE v1483[40]; // [rsp+5C38h] [rbp+5B38h] BYREF
  _BYTE v1484[40]; // [rsp+5C60h] [rbp+5B60h] BYREF
  _BYTE v1485[40]; // [rsp+5C88h] [rbp+5B88h] BYREF
  _BYTE v1486[40]; // [rsp+5CB0h] [rbp+5BB0h] BYREF
  _BYTE v1487[40]; // [rsp+5CD8h] [rbp+5BD8h] BYREF
  _BYTE v1488[40]; // [rsp+5D00h] [rbp+5C00h] BYREF
  _BYTE v1489[40]; // [rsp+5D28h] [rbp+5C28h] BYREF
  _BYTE v1490[40]; // [rsp+5D50h] [rbp+5C50h] BYREF
  _BYTE v1491[40]; // [rsp+5D78h] [rbp+5C78h] BYREF
  _BYTE v1492[40]; // [rsp+5DA0h] [rbp+5CA0h] BYREF
  _BYTE v1493[40]; // [rsp+5DC8h] [rbp+5CC8h] BYREF
  _BYTE v1494[40]; // [rsp+5DF0h] [rbp+5CF0h] BYREF
  _BYTE v1495[40]; // [rsp+5E18h] [rbp+5D18h] BYREF
  _BYTE v1496[40]; // [rsp+5E40h] [rbp+5D40h] BYREF
  _BYTE v1497[40]; // [rsp+5E68h] [rbp+5D68h] BYREF
  _BYTE v1498[40]; // [rsp+5E90h] [rbp+5D90h] BYREF
  _BYTE v1499[40]; // [rsp+5EB8h] [rbp+5DB8h] BYREF
  _BYTE v1500[40]; // [rsp+5EE0h] [rbp+5DE0h] BYREF
  _BYTE v1501[40]; // [rsp+5F08h] [rbp+5E08h] BYREF
  _BYTE v1502[40]; // [rsp+5F30h] [rbp+5E30h] BYREF
  _BYTE v1503[40]; // [rsp+5F58h] [rbp+5E58h] BYREF
  _BYTE v1504[40]; // [rsp+5F80h] [rbp+5E80h] BYREF
  _BYTE v1505[40]; // [rsp+5FA8h] [rbp+5EA8h] BYREF
  _BYTE v1506[40]; // [rsp+5FD0h] [rbp+5ED0h] BYREF
  _BYTE v1507[40]; // [rsp+5FF8h] [rbp+5EF8h] BYREF
  _BYTE v1508[40]; // [rsp+6020h] [rbp+5F20h] BYREF
  _BYTE v1509[40]; // [rsp+6048h] [rbp+5F48h] BYREF
  _BYTE v1510[40]; // [rsp+6070h] [rbp+5F70h] BYREF
  _BYTE v1511[40]; // [rsp+6098h] [rbp+5F98h] BYREF
  _BYTE v1512[40]; // [rsp+60C0h] [rbp+5FC0h] BYREF
  _BYTE v1513[40]; // [rsp+60E8h] [rbp+5FE8h] BYREF
  _BYTE v1514[40]; // [rsp+6110h] [rbp+6010h] BYREF
  _BYTE v1515[40]; // [rsp+6138h] [rbp+6038h] BYREF
  _BYTE v1516[40]; // [rsp+6160h] [rbp+6060h] BYREF
  _BYTE v1517[40]; // [rsp+6188h] [rbp+6088h] BYREF
  _BYTE v1518[40]; // [rsp+61B0h] [rbp+60B0h] BYREF
  _BYTE v1519[40]; // [rsp+61D8h] [rbp+60D8h] BYREF
  _BYTE v1520[40]; // [rsp+6200h] [rbp+6100h] BYREF
  _BYTE v1521[40]; // [rsp+6228h] [rbp+6128h] BYREF
  _BYTE v1522[40]; // [rsp+6250h] [rbp+6150h] BYREF
  _BYTE v1523[40]; // [rsp+6278h] [rbp+6178h] BYREF
  _BYTE v1524[40]; // [rsp+62A0h] [rbp+61A0h] BYREF
  _BYTE v1525[40]; // [rsp+62C8h] [rbp+61C8h] BYREF
  _BYTE v1526[40]; // [rsp+62F0h] [rbp+61F0h] BYREF
  _BYTE v1527[40]; // [rsp+6318h] [rbp+6218h] BYREF
  _BYTE v1528[40]; // [rsp+6340h] [rbp+6240h] BYREF
  _BYTE v1529[40]; // [rsp+6368h] [rbp+6268h] BYREF
  _BYTE v1530[40]; // [rsp+6390h] [rbp+6290h] BYREF
  _BYTE v1531[40]; // [rsp+63B8h] [rbp+62B8h] BYREF
  _BYTE v1532[40]; // [rsp+63E0h] [rbp+62E0h] BYREF
  _BYTE v1533[40]; // [rsp+6408h] [rbp+6308h] BYREF
  _BYTE v1534[40]; // [rsp+6430h] [rbp+6330h] BYREF
  _BYTE v1535[40]; // [rsp+6458h] [rbp+6358h] BYREF
  _BYTE v1536[40]; // [rsp+6480h] [rbp+6380h] BYREF
  _BYTE v1537[40]; // [rsp+64A8h] [rbp+63A8h] BYREF
  _BYTE v1538[40]; // [rsp+64D0h] [rbp+63D0h] BYREF
  _BYTE v1539[40]; // [rsp+64F8h] [rbp+63F8h] BYREF
  _BYTE v1540[40]; // [rsp+6520h] [rbp+6420h] BYREF
  _BYTE v1541[40]; // [rsp+6548h] [rbp+6448h] BYREF
  _BYTE v1542[40]; // [rsp+6570h] [rbp+6470h] BYREF
  _BYTE v1543[40]; // [rsp+6598h] [rbp+6498h] BYREF
  _BYTE v1544[40]; // [rsp+65C0h] [rbp+64C0h] BYREF
  _BYTE v1545[40]; // [rsp+65E8h] [rbp+64E8h] BYREF
  _BYTE v1546[40]; // [rsp+6610h] [rbp+6510h] BYREF
  _BYTE v1547[40]; // [rsp+6638h] [rbp+6538h] BYREF
  _BYTE v1548[40]; // [rsp+6660h] [rbp+6560h] BYREF
  _BYTE v1549[40]; // [rsp+6688h] [rbp+6588h] BYREF
  _BYTE v1550[40]; // [rsp+66B0h] [rbp+65B0h] BYREF
  _BYTE v1551[40]; // [rsp+66D8h] [rbp+65D8h] BYREF
  _BYTE v1552[40]; // [rsp+6700h] [rbp+6600h] BYREF
  _BYTE v1553[40]; // [rsp+6728h] [rbp+6628h] BYREF
  _BYTE v1554[40]; // [rsp+6750h] [rbp+6650h] BYREF
  _BYTE v1555[40]; // [rsp+6778h] [rbp+6678h] BYREF
  _BYTE v1556[40]; // [rsp+67A0h] [rbp+66A0h] BYREF
  _BYTE v1557[40]; // [rsp+67C8h] [rbp+66C8h] BYREF
  _BYTE v1558[40]; // [rsp+67F0h] [rbp+66F0h] BYREF
  _BYTE v1559[40]; // [rsp+6818h] [rbp+6718h] BYREF
  _BYTE v1560[40]; // [rsp+6840h] [rbp+6740h] BYREF
  _BYTE v1561[40]; // [rsp+6868h] [rbp+6768h] BYREF
  _BYTE v1562[40]; // [rsp+6890h] [rbp+6790h] BYREF
  _BYTE v1563[40]; // [rsp+68B8h] [rbp+67B8h] BYREF
  _BYTE v1564[40]; // [rsp+68E0h] [rbp+67E0h] BYREF
  _BYTE v1565[40]; // [rsp+6908h] [rbp+6808h] BYREF
  _BYTE v1566[40]; // [rsp+6930h] [rbp+6830h] BYREF
  _BYTE v1567[40]; // [rsp+6958h] [rbp+6858h] BYREF
  _BYTE v1568[40]; // [rsp+6980h] [rbp+6880h] BYREF
  _BYTE v1569[40]; // [rsp+69A8h] [rbp+68A8h] BYREF
  _BYTE v1570[40]; // [rsp+69D0h] [rbp+68D0h] BYREF
  _BYTE v1571[40]; // [rsp+69F8h] [rbp+68F8h] BYREF
  _BYTE v1572[40]; // [rsp+6A20h] [rbp+6920h] BYREF
  _BYTE v1573[40]; // [rsp+6A48h] [rbp+6948h] BYREF
  _BYTE v1574[40]; // [rsp+6A70h] [rbp+6970h] BYREF
  _BYTE v1575[40]; // [rsp+6A98h] [rbp+6998h] BYREF
  _BYTE v1576[40]; // [rsp+6AC0h] [rbp+69C0h] BYREF
  _BYTE v1577[40]; // [rsp+6AE8h] [rbp+69E8h] BYREF
  _BYTE v1578[40]; // [rsp+6B10h] [rbp+6A10h] BYREF
  _BYTE v1579[40]; // [rsp+6B38h] [rbp+6A38h] BYREF
  _BYTE v1580[40]; // [rsp+6B60h] [rbp+6A60h] BYREF
  _BYTE v1581[40]; // [rsp+6B88h] [rbp+6A88h] BYREF
  _BYTE v1582[40]; // [rsp+6BB0h] [rbp+6AB0h] BYREF
  _BYTE v1583[40]; // [rsp+6BD8h] [rbp+6AD8h] BYREF
  _BYTE v1584[40]; // [rsp+6C00h] [rbp+6B00h] BYREF
  _BYTE v1585[40]; // [rsp+6C28h] [rbp+6B28h] BYREF
  _BYTE v1586[40]; // [rsp+6C50h] [rbp+6B50h] BYREF
  _BYTE v1587[40]; // [rsp+6C78h] [rbp+6B78h] BYREF
  _BYTE v1588[40]; // [rsp+6CA0h] [rbp+6BA0h] BYREF
  _BYTE v1589[40]; // [rsp+6CC8h] [rbp+6BC8h] BYREF
  _BYTE v1590[40]; // [rsp+6CF0h] [rbp+6BF0h] BYREF
  _BYTE v1591[40]; // [rsp+6D18h] [rbp+6C18h] BYREF
  _BYTE v1592[40]; // [rsp+6D40h] [rbp+6C40h] BYREF
  _BYTE v1593[40]; // [rsp+6D68h] [rbp+6C68h] BYREF
  _BYTE v1594[40]; // [rsp+6D90h] [rbp+6C90h] BYREF
  _BYTE v1595[40]; // [rsp+6DB8h] [rbp+6CB8h] BYREF
  _BYTE v1596[40]; // [rsp+6DE0h] [rbp+6CE0h] BYREF
  _BYTE v1597[40]; // [rsp+6E08h] [rbp+6D08h] BYREF
  _BYTE v1598[40]; // [rsp+6E30h] [rbp+6D30h] BYREF
  _BYTE v1599[40]; // [rsp+6E58h] [rbp+6D58h] BYREF
  _BYTE v1600[40]; // [rsp+6E80h] [rbp+6D80h] BYREF
  _BYTE v1601[40]; // [rsp+6EA8h] [rbp+6DA8h] BYREF
  _BYTE v1602[40]; // [rsp+6ED0h] [rbp+6DD0h] BYREF
  _BYTE v1603[40]; // [rsp+6EF8h] [rbp+6DF8h] BYREF
  _BYTE v1604[40]; // [rsp+6F20h] [rbp+6E20h] BYREF
  _BYTE v1605[40]; // [rsp+6F48h] [rbp+6E48h] BYREF
  _BYTE v1606[40]; // [rsp+6F70h] [rbp+6E70h] BYREF
  _BYTE v1607[40]; // [rsp+6F98h] [rbp+6E98h] BYREF
  _BYTE v1608[40]; // [rsp+6FC0h] [rbp+6EC0h] BYREF
  _BYTE v1609[40]; // [rsp+6FE8h] [rbp+6EE8h] BYREF
  _BYTE v1610[40]; // [rsp+7010h] [rbp+6F10h] BYREF
  _BYTE v1611[40]; // [rsp+7038h] [rbp+6F38h] BYREF
  _BYTE v1612[40]; // [rsp+7060h] [rbp+6F60h] BYREF
  _BYTE v1613[40]; // [rsp+7088h] [rbp+6F88h] BYREF
  _BYTE v1614[40]; // [rsp+70B0h] [rbp+6FB0h] BYREF
  _BYTE v1615[40]; // [rsp+70D8h] [rbp+6FD8h] BYREF
  _BYTE v1616[40]; // [rsp+7100h] [rbp+7000h] BYREF
  _BYTE v1617[40]; // [rsp+7128h] [rbp+7028h] BYREF
  _BYTE v1618[40]; // [rsp+7150h] [rbp+7050h] BYREF
  _BYTE v1619[40]; // [rsp+7178h] [rbp+7078h] BYREF
  _BYTE v1620[40]; // [rsp+71A0h] [rbp+70A0h] BYREF
  _BYTE v1621[40]; // [rsp+71C8h] [rbp+70C8h] BYREF
  _BYTE v1622[40]; // [rsp+71F0h] [rbp+70F0h] BYREF
  _BYTE v1623[40]; // [rsp+7218h] [rbp+7118h] BYREF
  _BYTE v1624[40]; // [rsp+7240h] [rbp+7140h] BYREF
  _BYTE v1625[40]; // [rsp+7268h] [rbp+7168h] BYREF
  _BYTE v1626[40]; // [rsp+7290h] [rbp+7190h] BYREF
  _BYTE v1627[40]; // [rsp+72B8h] [rbp+71B8h] BYREF
  _BYTE v1628[40]; // [rsp+72E0h] [rbp+71E0h] BYREF
  _BYTE v1629[40]; // [rsp+7308h] [rbp+7208h] BYREF
  _BYTE v1630[40]; // [rsp+7330h] [rbp+7230h] BYREF
  _BYTE v1631[40]; // [rsp+7358h] [rbp+7258h] BYREF
  _BYTE v1632[40]; // [rsp+7380h] [rbp+7280h] BYREF
  _BYTE v1633[40]; // [rsp+73A8h] [rbp+72A8h] BYREF
  _BYTE v1634[40]; // [rsp+73D0h] [rbp+72D0h] BYREF
  _BYTE v1635[40]; // [rsp+73F8h] [rbp+72F8h] BYREF
  _BYTE v1636[40]; // [rsp+7420h] [rbp+7320h] BYREF
  _BYTE v1637[32]; // [rsp+7448h] [rbp+7348h] BYREF
  _BYTE v1638[32]; // [rsp+7468h] [rbp+7368h] BYREF
  _BYTE v1639[8]; // [rsp+7488h] [rbp+7388h] BYREF
  _QWORD v1640[4]; // [rsp+7490h] [rbp+7390h] BYREF
  _BYTE v1641[272]; // [rsp+74B0h] [rbp+73B0h] BYREF
  _BYTE v1642[272]; // [rsp+75C0h] [rbp+74C0h] BYREF
  _BYTE v1643[272]; // [rsp+76D0h] [rbp+75D0h] BYREF
  _BYTE v1644[272]; // [rsp+77E0h] [rbp+76E0h] BYREF
  _BYTE v1645[272]; // [rsp+78F0h] [rbp+77F0h] BYREF
  _BYTE v1646[272]; // [rsp+7A00h] [rbp+7900h] BYREF
  _BYTE v1647[272]; // [rsp+7B10h] [rbp+7A10h] BYREF
  _BYTE v1648[272]; // [rsp+7C20h] [rbp+7B20h] BYREF
  _BYTE v1649[272]; // [rsp+7D30h] [rbp+7C30h] BYREF
  _BYTE v1650[272]; // [rsp+7E40h] [rbp+7D40h] BYREF
  _BYTE v1651[272]; // [rsp+7F50h] [rbp+7E50h] BYREF
  _BYTE v1652[304]; // [rsp+8060h] [rbp+7F60h] BYREF
  _BYTE v1653[304]; // [rsp+8190h] [rbp+8090h] BYREF
  _BYTE v1654[304]; // [rsp+82C0h] [rbp+81C0h] BYREF
  _BYTE v1655[304]; // [rsp+83F0h] [rbp+82F0h] BYREF
  _BYTE v1656[304]; // [rsp+8520h] [rbp+8420h] BYREF
  _BYTE v1657[304]; // [rsp+8650h] [rbp+8550h] BYREF
  _BYTE v1658[304]; // [rsp+8780h] [rbp+8680h] BYREF
  _BYTE v1659[304]; // [rsp+88B0h] [rbp+87B0h] BYREF
  _BYTE v1660[304]; // [rsp+89E0h] [rbp+88E0h] BYREF
  _BYTE v1661[304]; // [rsp+8B10h] [rbp+8A10h] BYREF
  _BYTE v1662[304]; // [rsp+8C40h] [rbp+8B40h] BYREF
  _BYTE v1663[304]; // [rsp+8D70h] [rbp+8C70h] BYREF
  _BYTE v1664[304]; // [rsp+8EA0h] [rbp+8DA0h] BYREF
  _BYTE v1665[304]; // [rsp+8FD0h] [rbp+8ED0h] BYREF
  _BYTE v1666[304]; // [rsp+9100h] [rbp+9000h] BYREF
  _BYTE v1667[304]; // [rsp+9230h] [rbp+9130h] BYREF
  _BYTE v1668[304]; // [rsp+9360h] [rbp+9260h] BYREF
  _BYTE v1669[304]; // [rsp+9490h] [rbp+9390h] BYREF
  _BYTE v1670[304]; // [rsp+95C0h] [rbp+94C0h] BYREF
  _BYTE v1671[304]; // [rsp+96F0h] [rbp+95F0h] BYREF
  _BYTE v1672[304]; // [rsp+9820h] [rbp+9720h] BYREF
  _BYTE v1673[304]; // [rsp+9950h] [rbp+9850h] BYREF
  _BYTE v1674[304]; // [rsp+9A80h] [rbp+9980h] BYREF
  _BYTE v1675[304]; // [rsp+9BB0h] [rbp+9AB0h] BYREF
  _BYTE v1676[304]; // [rsp+9CE0h] [rbp+9BE0h] BYREF
  _BYTE v1677[304]; // [rsp+9E10h] [rbp+9D10h] BYREF
  _BYTE v1678[304]; // [rsp+9F40h] [rbp+9E40h] BYREF
  _BYTE v1679[304]; // [rsp+A070h] [rbp+9F70h] BYREF
  _BYTE v1680[304]; // [rsp+A1A0h] [rbp+A0A0h] BYREF
  _BYTE v1681[304]; // [rsp+A2D0h] [rbp+A1D0h] BYREF
  _BYTE v1682[304]; // [rsp+A400h] [rbp+A300h] BYREF
  _BYTE v1683[304]; // [rsp+A530h] [rbp+A430h] BYREF
  _BYTE v1684[304]; // [rsp+A660h] [rbp+A560h] BYREF
  _BYTE v1685[304]; // [rsp+A790h] [rbp+A690h] BYREF
  _BYTE v1686[304]; // [rsp+A8C0h] [rbp+A7C0h] BYREF
  _BYTE v1687[304]; // [rsp+A9F0h] [rbp+A8F0h] BYREF
  _BYTE v1688[304]; // [rsp+AB20h] [rbp+AA20h] BYREF
  _BYTE v1689[304]; // [rsp+AC50h] [rbp+AB50h] BYREF
  _BYTE v1690[304]; // [rsp+AD80h] [rbp+AC80h] BYREF
  _BYTE v1691[304]; // [rsp+AEB0h] [rbp+ADB0h] BYREF
  _BYTE v1692[304]; // [rsp+AFE0h] [rbp+AEE0h] BYREF
  _BYTE v1693[304]; // [rsp+B110h] [rbp+B010h] BYREF
  _BYTE v1694[304]; // [rsp+B240h] [rbp+B140h] BYREF
  _BYTE v1695[304]; // [rsp+B370h] [rbp+B270h] BYREF
  _BYTE v1696[304]; // [rsp+B4A0h] [rbp+B3A0h] BYREF
  _BYTE v1697[304]; // [rsp+B5D0h] [rbp+B4D0h] BYREF
  _BYTE v1698[304]; // [rsp+B700h] [rbp+B600h] BYREF
  _BYTE v1699[304]; // [rsp+B830h] [rbp+B730h] BYREF
  _BYTE v1700[304]; // [rsp+B960h] [rbp+B860h] BYREF
  _BYTE v1701[304]; // [rsp+BA90h] [rbp+B990h] BYREF
  _BYTE v1702[304]; // [rsp+BBC0h] [rbp+BAC0h] BYREF
  _BYTE v1703[304]; // [rsp+BCF0h] [rbp+BBF0h] BYREF
  _BYTE v1704[304]; // [rsp+BE20h] [rbp+BD20h] BYREF
  _BYTE v1705[304]; // [rsp+BF50h] [rbp+BE50h] BYREF
  _BYTE v1706[304]; // [rsp+C080h] [rbp+BF80h] BYREF
  _BYTE v1707[304]; // [rsp+C1B0h] [rbp+C0B0h] BYREF
  _BYTE v1708[304]; // [rsp+C2E0h] [rbp+C1E0h] BYREF
  _BYTE v1709[304]; // [rsp+C410h] [rbp+C310h] BYREF
  _BYTE v1710[304]; // [rsp+C540h] [rbp+C440h] BYREF

  v849 = 5;
  sub_1800A9740(v868);
  sub_1800A70D4(v868, &v849);
  LOBYTE(v2) = v847;
  sub_1800A7BFC(v868, v866, qword_1801B8AD8, v2);
  sub_1800AC4E4(a1 + 152, v866);
  sub_1800212AC(v866);
  sub_18005F7F0(v868);
  v850 = 0;
  sub_1800A9740(v858);
  sub_1800A70D4(v858, &v850);
  v851 = 1;
  sub_1800A70D4(v858, &v851);
  v852 = 2;
  sub_1800A70D4(v858, &v852);
  v853 = 3;
  sub_1800A70D4(v858, &v853);
  LOBYTE(v3) = v847;
  sub_1800A7BFC(v858, v862, qword_1801B8AD8, v3);
  sub_1800AC4E4(a1 + 176, v862);
  sub_1800212AC(v862);
  sub_18005F7F0(v858);
  v854 = 1;
  sub_1800A9740(v867);
  sub_1800A70D4(v867, &v854);
  v855 = 3;
  sub_1800A70D4(v867, &v855);
  LOBYTE(v4) = v847;
  sub_1800A7BFC(v867, v863, qword_1801B8AD8, v4);
  v5 = a1 + 200;
  sub_1800AC4E4(a1 + 200, v863);
  sub_1800212AC(v863);
  sub_18005F7F0(v867);
  v856 = 2;
  sub_1800A9740(v869);
  sub_1800A70D4(v869, &v856);
  LOBYTE(v6) = v847;
  sub_1800A7BFC(v869, v864, qword_1801B8AD8, v6);
  v7 = a1 + 224;
  sub_1800AC4E4(a1 + 224, v864);
  sub_1800212AC(v864);
  sub_18005F7F0(v869);
  v857 = 3;
  sub_1800A9740(v870);
  sub_1800A70D4(v870, &v857);
  LOBYTE(v8) = v847;
  sub_1800A7BFC(v870, v865, qword_1801B8AD8, v8);
  v9 = a1 + 248;
  sub_1800AC4E4(a1 + 248, v865);
  sub_1800212AC(v865);
  sub_18005F7F0(v870);
  sub_18001D80C(v1249, L"MaxPackageSizeInBytes");
  v1273 = 0;
  memset(v1272, 0, sizeof(v1272));
  v1271 = 0;
  memset(v1270, 0, sizeof(v1270));
  v848 = (_QWORD *)sub_18001D71C((__int64)v969, (__int64)v1249);
  v10 = *(_QWORD *)(a1 + 136);
  sub_18001D71C((__int64)v871, (__int64)v848);
  LOBYTE(v11) = 0;
  v12 = sub_1800A9864(v1639, v10, v11, v871, 0);
  v859 = sub_1800ACE10;
  sub_1800A9838(v860, v12);
  sub_180028810(v1640);
  sub_180028810(v848);
  *(_QWORD *)&v845 = &v859;
  v872 = v859;
  sub_1800A9838(v873, v860);
  sub_1800A5FA8(v1636, &v872, 0);
  sub_180028810(v861);
  v13 = sub_18001D71C((__int64)v970, (__int64)v1249);
  LOBYTE(v14) = 0;
  *(_QWORD *)&v845 = sub_1800A7884((unsigned int)&v1133, (unsigned int)sub_1800ACDB0, *(_QWORD *)(a1 + 136), v14, v13);
  v876 = *(_QWORD *)v845;
  sub_1800A9838(v877, v845 + 8);
  sub_1800A63E4(v1635, &v876, 0);
  sub_180028810((_QWORD *)(v845 + 16));
  v15 = sub_18001D71C((__int64)v971, (__int64)v1249);
  LOBYTE(v16) = 0;
  *(_QWORD *)&v845 = sub_1800A7360((unsigned int)&v1134, (unsigned int)sub_1800ACCF0, *(_QWORD *)(a1 + 136), v16, v15);
  v874 = *(_QWORD *)v845;
  sub_1800A9838(v875, v845 + 8);
  sub_1800A51EC(v1634, &v874, 0);
  sub_180028810((_QWORD *)(v845 + 16));
  v17 = sub_1800A7E30(
          (unsigned int)v1652,
          (unsigned int)v1249,
          (int)a1 + 176,
          (unsigned int)v1634,
          (__int64)v1635,
          (__int64)v1636,
          (__int64)v1270,
          (__int64)v1272);
  sub_1800ABA8C(a1 + 272, v17);
  sub_1800AABD8(v1652);
  sub_1800AB520(v1634);
  sub_1800AB520(v1635);
  sub_1800AB520(v1636);
  sub_1800AB520(v1270);
  sub_1800AB520(v1272);
  sub_1800B783C(a1, v1249, a1 + 272);
  sub_180020E60((__int64)v1249);
  sub_18001D80C(v1250, L"SyncEnabled");
  sub_1800A4CE8(v1291, 0, 0);
  sub_1800A9798(v1290, 0);
  v18 = sub_18001D71C((__int64)v972, (__int64)v1250);
  v19 = sub_180037524(a1 + 136);
  LOBYTE(v20) = 0;
  v21 = sub_1800A725C((unsigned int)&v1135, (unsigned int)sub_1800ACE10, v19, v20, v18);
  sub_1800A6134(v1289, v21, 0);
  v22 = sub_18001D71C((__int64)v973, (__int64)v1250);
  v23 = sub_180037524(a1 + 136);
  LOBYTE(v24) = 0;
  v25 = sub_1800A7ADC((unsigned int)&v1136, (unsigned int)sub_1800ACDF0, v23, v24, v22);
  sub_1800A6D60(v1288, v25, 0);
  v26 = sub_18001D71C((__int64)v974, (__int64)v1250);
  v27 = sub_180037524(a1 + 136);
  LOBYTE(v28) = 0;
  v29 = sub_1800A77C4((unsigned int)&v1137, (unsigned int)sub_1800ACD30, v27, v28, v26);
  sub_1800A5B68(v1287, v29, 0);
  v30 = sub_1800A8910(
          (unsigned int)v1653,
          (unsigned int)v1250,
          (int)a1 + 176,
          (unsigned int)v1287,
          (__int64)v1288,
          (__int64)v1289,
          (__int64)v1290,
          (__int64)v1291);
  sub_1800ABA8C(a1 + 576, v30);
  sub_1800AABD8(v1653);
  sub_1800AB520(v1287);
  sub_1800AB520(v1288);
  sub_1800AB520(v1289);
  sub_1800AB520(v1290);
  sub_1800AB520(v1291);
  sub_1800B783C(a1, v1250, a1 + 576);
  sub_180020E60((__int64)v1250);
  sub_18001D80C(v1251, L"SyncTimeoutInMilliseconds");
  sub_1800A4A28(v1296, 0, 0);
  sub_1800A9798(v1295, 0);
  v31 = sub_18001D71C((__int64)v975, (__int64)v1251);
  v32 = sub_180037524(a1 + 136);
  LOBYTE(v33) = 0;
  v34 = sub_1800A725C((unsigned int)&v1138, (unsigned int)sub_1800ACE10, v32, v33, v31);
  sub_1800A6134(v1294, v34, 0);
  v35 = sub_18001D71C((__int64)v976, (__int64)v1251);
  v36 = sub_180037524(a1 + 136);
  LOBYTE(v37) = 0;
  v38 = sub_1800A7884((unsigned int)&v1139, (unsigned int)sub_1800ACDB0, v36, v37, v35);
  sub_1800A6570(v1293, v38, 0);
  v39 = sub_18001D71C((__int64)v977, (__int64)v1251);
  v40 = sub_180037524(a1 + 136);
  LOBYTE(v41) = 0;
  v42 = sub_1800A7360((unsigned int)&v1140, (unsigned int)sub_1800ACCF0, v40, v41, v39);
  sub_1800A5378(v1292, v42, 0);
  v43 = sub_1800A7E30(
          (unsigned int)v1654,
          (unsigned int)v1251,
          (int)a1 + 176,
          (unsigned int)v1292,
          (__int64)v1293,
          (__int64)v1294,
          (__int64)v1295,
          (__int64)v1296);
  sub_1800ABA8C(a1 + 880, v43);
  sub_1800AABD8(v1654);
  sub_1800AB520(v1292);
  sub_1800AB520(v1293);
  sub_1800AB520(v1294);
  sub_1800AB520(v1295);
  sub_1800AB520(v1296);
  sub_1800B783C(a1, v1251, a1 + 880);
  sub_180020E60((__int64)v1251);
  sub_18001D80C(v1252, L"SyncMethod");
  sub_1800A47A8(v1301, 0, 0);
  v44 = sub_180037524(a1 + 136);
  LOBYTE(v45) = 0;
  v845 = *(_OWORD *)sub_1800A7218(v957, sub_1800AC890, v44, v45);
  sub_1800A50E8(v1300, &v845, 0);
  v46 = sub_18001D71C((__int64)v978, (__int64)v1252);
  v47 = sub_180037524(a1 + 136);
  LOBYTE(v48) = 0;
  v49 = sub_1800A725C((unsigned int)&v1141, (unsigned int)sub_1800ACE10, v47, v48, v46);
  sub_1800A6134(v1299, v49, 0);
  v50 = sub_18001D71C((__int64)v979, (__int64)v1252);
  v51 = sub_180037524(a1 + 136);
  LOBYTE(v52) = 0;
  v53 = sub_1800A7450((unsigned int)&v1142, (unsigned int)sub_1800ACD70, v51, v52, v50);
  sub_1800A6780(v1298, v53, 0);
  v54 = sub_18001D71C((__int64)v980, (__int64)v1252);
  v55 = sub_180037524(a1 + 136);
  LOBYTE(v56) = 0;
  v57 = sub_1800A7450((unsigned int)&v1143, (unsigned int)sub_1800ACCB0, v55, v56, v54);
  sub_1800A5588(v1297, v57, 0);
  v58 = sub_1800A8268(
          (unsigned int)v1655,
          (unsigned int)v1252,
          (int)a1 + 176,
          (unsigned int)v1297,
          (__int64)v1298,
          (__int64)v1299,
          (__int64)v1300,
          (__int64)v1301);
  sub_1800ABCC0(a1 + 1184, v58);
  sub_1800AABD8(v1655);
  sub_1800AB520(v1297);
  sub_1800AB520(v1298);
  sub_1800AB520(v1299);
  sub_1800AB520(v1300);
  sub_1800AB520(v1301);
  sub_1800B783C(a1, v1252, a1 + 1184);
  sub_180020E60((__int64)v1252);
  sub_18001D80C(v1253, L"SettingsStoragePath");
  sub_1800A9798(v1306, 0);
  sub_1800A9798(v1305, 0);
  v59 = sub_18001D71C((__int64)v981, (__int64)v1253);
  v60 = sub_180037524(a1 + 136);
  LOBYTE(v61) = 0;
  v62 = sub_1800A725C((unsigned int)&v1144, (unsigned int)sub_1800ACE10, v60, v61, v59);
  sub_1800A6134(v1304, v62, 0);
  v63 = sub_18001D71C((__int64)v982, (__int64)v1253);
  v64 = sub_180037524(a1 + 136);
  LOBYTE(v65) = 0;
  v66 = sub_1800A7450((unsigned int)&v1145, (unsigned int)sub_1800ACD50, v64, v65, v63);
  sub_1800A6780(v1303, v66, 0);
  v67 = sub_18001D71C((__int64)v983, (__int64)v1253);
  v68 = sub_180037524(a1 + 136);
  LOBYTE(v812) = 0;
  LOBYTE(v779) = 0;
  LOBYTE(v69) = 0;
  v70 = sub_1800A7524((unsigned int)&v1210, (unsigned int)sub_1800ACC90, v68, v69, v67, v779, v812, 1);
  sub_1800A5D28(v1302, v70, 0);
  v71 = sub_1800A8268(
          (unsigned int)v1656,
          (unsigned int)v1253,
          (int)a1 + 176,
          (unsigned int)v1302,
          (__int64)v1303,
          (__int64)v1304,
          (__int64)v1305,
          (__int64)v1306);
  sub_1800ABCC0(a1 + 1488, v71);
  sub_1800AABD8(v1656);
  sub_1800AB520(v1302);
  sub_1800AB520(v1303);
  sub_1800AB520(v1304);
  sub_1800AB520(v1305);
  sub_1800AB520(v1306);
  v72 = sub_1800854A8(v1638, v1253, &unk_1801B8910);
  sub_1800B783C(a1, v72, a1 + 1488);
  sub_180020E60((__int64)v1638);
  sub_180020E60((__int64)v1253);
  sub_18001D80C(v1213, L"SettingsStoragePath");
  sub_1800A9798(v1311, 0);
  sub_1800A9798(v1310, 0);
  v73 = sub_18001D71C((__int64)v985, (__int64)v1213);
  v74 = sub_180037524(a1 + 136);
  LOBYTE(v75) = 0;
  v76 = sub_1800A725C((unsigned int)&v1146, (unsigned int)sub_1800ACE10, v74, v75, v73);
  sub_1800A6134(v1309, v76, 0);
  v77 = sub_18001D71C((__int64)v986, (__int64)v1213);
  v78 = sub_180037524(a1 + 136);
  LOBYTE(v79) = 0;
  v80 = sub_1800A7450((unsigned int)&v1147, (unsigned int)sub_1800ACD50, v78, v79, v77);
  sub_1800A6780(v1308, v80, 0);
  v81 = sub_18001D71C((__int64)v987, (__int64)v1213);
  v82 = sub_180037524(a1 + 136);
  LOBYTE(v813) = 0;
  LOBYTE(v780) = 0;
  LOBYTE(v83) = 0;
  v84 = sub_1800A7524((unsigned int)&v1209, (unsigned int)sub_1800ACC90, v82, v83, v81, v780, v813, 0);
  sub_1800A5D28(v1307, v84, 0);
  v85 = sub_1800A8268(
          (unsigned int)v1657,
          (unsigned int)v1213,
          (int)a1 + 176,
          (unsigned int)v1307,
          (__int64)v1308,
          (__int64)v1309,
          (__int64)v1310,
          (__int64)v1311);
  sub_1800ABCC0(a1 + 1792, v85);
  sub_1800AABD8(v1657);
  sub_1800AB520(v1307);
  sub_1800AB520(v1308);
  sub_1800AB520(v1309);
  sub_1800AB520(v1310);
  sub_1800AB520(v1311);
  sub_1800B783C(a1, v1213, a1 + 1792);
  sub_180020E60((__int64)v1213);
  sub_18001D80C(v1214, L"SettingsTemplateCatalogPath");
  sub_1800A9798(v1316, 0);
  sub_1800A9798(v1315, 0);
  v86 = sub_18001D71C((__int64)v988, (__int64)v1214);
  v87 = sub_180037524(a1 + 136);
  LOBYTE(v88) = 0;
  v89 = sub_1800A725C((unsigned int)&v1148, (unsigned int)sub_1800ACE10, v87, v88, v86);
  sub_1800A6134(v1314, v89, 0);
  v90 = sub_18001D71C((__int64)v989, (__int64)v1214);
  v91 = sub_180037524(a1 + 136);
  LOBYTE(v92) = 0;
  v93 = sub_1800A7450((unsigned int)&v1149, (unsigned int)sub_1800ACD50, v91, v92, v90);
  sub_1800A6780(v1313, v93, 0);
  v94 = sub_18001D71C((__int64)v990, (__int64)v1214);
  v95 = sub_180037524(a1 + 136);
  LOBYTE(v814) = 0;
  LOBYTE(v781) = 0;
  LOBYTE(v96) = 0;
  v97 = sub_1800A7524((unsigned int)&v1211, (unsigned int)sub_1800ACC90, v95, v96, v94, v781, v814, 1);
  sub_1800A5D28(v1312, v97, 0);
  v98 = sub_1800A8268(
          (unsigned int)v1658,
          (unsigned int)v1214,
          v5,
          (unsigned int)v1312,
          (__int64)v1313,
          (__int64)v1314,
          (__int64)v1315,
          (__int64)v1316);
  sub_1800ABCC0(a1 + 2096, v98);
  sub_1800AABD8(v1658);
  sub_1800AB520(v1312);
  sub_1800AB520(v1313);
  sub_1800AB520(v1314);
  sub_1800AB520(v1315);
  sub_1800AB520(v1316);
  v99 = sub_1800854A8(v1637, v1214, &unk_1801B8910);
  sub_1800B783C(a1, v99, a1 + 2096);
  sub_180020E60((__int64)v1637);
  sub_180020E60((__int64)v1214);
  sub_18001D80C(v1215, L"SettingsTemplateCatalogPath");
  sub_1800A9798(v1321, 0);
  sub_1800A9798(v1320, 0);
  v100 = sub_18001D71C((__int64)v992, (__int64)v1215);
  v101 = sub_180037524(a1 + 136);
  LOBYTE(v102) = 0;
  v103 = sub_1800A725C((unsigned int)&v1150, (unsigned int)sub_1800ACE10, v101, v102, v100);
  sub_1800A6134(v1319, v103, 0);
  v104 = sub_18001D71C((__int64)v993, (__int64)v1215);
  v105 = sub_180037524(a1 + 136);
  LOBYTE(v106) = 0;
  v107 = sub_1800A7450((unsigned int)&v1151, (unsigned int)sub_1800ACD50, v105, v106, v104);
  sub_1800A6780(v1318, v107, 0);
  v108 = sub_18001D71C((__int64)v994, (__int64)v1215);
  v109 = sub_180037524(a1 + 136);
  LOBYTE(v815) = 0;
  LOBYTE(v782) = 0;
  LOBYTE(v110) = 0;
  v111 = sub_1800A7524((unsigned int)&v1212, (unsigned int)sub_1800ACC90, v109, v110, v108, v782, v815, 0);
  sub_1800A5D28(v1317, v111, 0);
  v112 = sub_1800A8268(
           (unsigned int)v1659,
           (unsigned int)v1215,
           v5,
           (unsigned int)v1317,
           (__int64)v1318,
           (__int64)v1319,
           (__int64)v1320,
           (__int64)v1321);
  sub_1800ABCC0(a1 + 2400, v112);
  sub_1800AABD8(v1659);
  sub_1800AB520(v1317);
  sub_1800AB520(v1318);
  sub_1800AB520(v1319);
  sub_1800AB520(v1320);
  sub_1800AB520(v1321);
  sub_1800B783C(a1, v1215, a1 + 2400);
  sub_180020E60((__int64)v1215);
  sub_18001D80C(v1216, L"SettingsImportNotifyEnabled");
  sub_1800A50A8(v1326, 0, 0);
  sub_1800A9798(v1325, 0);
  v113 = sub_18001D71C((__int64)v995, (__int64)v1216);
  v114 = sub_180037524(a1 + 136);
  LOBYTE(v115) = 0;
  v116 = sub_1800A725C((unsigned int)&v1152, (unsigned int)sub_1800ACE10, v114, v115, v113);
  sub_1800A6134(v1324, v116, 0);
  v117 = sub_18001D71C((__int64)v996, (__int64)v1216);
  v118 = sub_180037524(a1 + 136);
  LOBYTE(v119) = 0;
  v120 = sub_1800A7ADC((unsigned int)&v1153, (unsigned int)sub_1800ACDF0, v118, v119, v117);
  sub_1800A6D60(v1323, v120, 0);
  v121 = sub_18001D71C((__int64)v997, (__int64)v1216);
  v122 = sub_180037524(a1 + 136);
  LOBYTE(v123) = 0;
  v124 = sub_1800A77C4((unsigned int)&v1154, (unsigned int)sub_1800ACD30, v122, v123, v121);
  sub_1800A5B68(v1322, v124, 0);
  v125 = sub_1800A8910(
           (unsigned int)v1660,
           (unsigned int)v1216,
           (int)a1 + 176,
           (unsigned int)v1322,
           (__int64)v1323,
           (__int64)v1324,
           (__int64)v1325,
           (__int64)v1326);
  sub_1800ABA8C(a1 + 2704, v125);
  sub_1800AABD8(v1660);
  sub_1800AB520(v1322);
  sub_1800AB520(v1323);
  sub_1800AB520(v1324);
  sub_1800AB520(v1325);
  sub_1800AB520(v1326);
  sub_1800B783C(a1, v1216, a1 + 2704);
  sub_180020E60((__int64)v1216);
  sub_18001D80C(v1217, L"SettingsImportNotifyDelayInSeconds");
  sub_1800A4768(v1331, 0, 0);
  sub_1800A9798(v1330, 0);
  v126 = sub_18001D71C((__int64)v998, (__int64)v1217);
  v127 = sub_180037524(a1 + 136);
  LOBYTE(v128) = 0;
  v129 = sub_1800A725C((unsigned int)&v1155, (unsigned int)sub_1800ACE10, v127, v128, v126);
  sub_1800A6134(v1329, v129, 0);
  v130 = sub_18001D71C((__int64)v999, (__int64)v1217);
  v131 = sub_180037524(a1 + 136);
  LOBYTE(v132) = 0;
  v133 = sub_1800A7884((unsigned int)&v1156, (unsigned int)sub_1800ACDB0, v131, v132, v130);
  sub_1800A6570(v1328, v133, 0);
  v134 = sub_18001D71C((__int64)v1000, (__int64)v1217);
  v135 = sub_180037524(a1 + 136);
  LOBYTE(v136) = 0;
  v137 = sub_1800A7360((unsigned int)&v1157, (unsigned int)sub_1800ACCF0, v135, v136, v134);
  sub_1800A5378(v1327, v137, 0);
  v138 = sub_1800A7E30(
           (unsigned int)v1661,
           (unsigned int)v1217,
           (int)a1 + 176,
           (unsigned int)v1327,
           (__int64)v1328,
           (__int64)v1329,
           (__int64)v1330,
           (__int64)v1331);
  sub_1800ABA8C(a1 + 3008, v138);
  sub_1800AABD8(v1661);
  sub_1800AB520(v1327);
  sub_1800AB520(v1328);
  sub_1800AB520(v1329);
  sub_1800AB520(v1330);
  sub_1800AB520(v1331);
  sub_1800B783C(a1, v1217, a1 + 3008);
  sub_180020E60((__int64)v1217);
  sub_1800A4AE8(v1336, 0, 0);
  sub_1800A9798(v1335, 0);
  sub_1800A9798(v1334, 0);
  v139 = sub_180037524(a1 + 136);
  LOBYTE(v816) = 0;
  LOBYTE(v783) = 0;
  LOBYTE(v751) = 0;
  LOBYTE(v140) = 0;
  v845 = *(_OWORD *)sub_1800A7AC4(v962, sub_1800AC8D0, v139, v140, v751, v783, v816);
  sub_1800A6D10(v1333, &v845, 0);
  v141 = sub_180037524(a1 + 136);
  LOBYTE(v817) = 0;
  LOBYTE(v784) = 0;
  LOBYTE(v752) = 0;
  LOBYTE(v142) = 0;
  v845 = *(_OWORD *)sub_1800A77AC(v963, sub_1800AC8B0, v141, v142, v752, v784, v817);
  sub_1800A5B18(v1332, &v845, 0);
  v143 = sub_1800A955C(
           (unsigned int)v1641,
           (int)a1 + 176,
           (unsigned int)v1332,
           (unsigned int)v1333,
           (__int64)v1334,
           (__int64)v1335,
           (__int64)v1336);
  sub_1800ABF70(a1 + 3312, v143);
  sub_1800AB34C(v1641);
  sub_1800AB520(v1332);
  sub_1800AB520(v1333);
  sub_1800AB520(v1334);
  sub_1800AB520(v1335);
  sub_1800AB520(v1336);
  sub_18001D80C(v1276, L"TemplateEnabled");
  sub_1800B7734(a1, v1276, a1 + 3312);
  sub_180020E60((__int64)v1276);
  sub_1800A9798(v1341, 0);
  sub_1800A9798(v1340, 0);
  sub_1800A9798(v1339, 0);
  v144 = sub_180037524(a1 + 136);
  LOBYTE(v818) = 0;
  LOBYTE(v785) = 0;
  LOBYTE(v753) = 0;
  LOBYTE(v145) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v964, sub_1800AC910, v144, v145, v753, v785, v818);
  sub_1800A6730(v1338, &v845, 0);
  v146 = sub_180037524(a1 + 136);
  LOBYTE(v819) = 0;
  LOBYTE(v786) = 0;
  LOBYTE(v754) = 0;
  LOBYTE(v147) = 0;
  v845 = *(_OWORD *)sub_1800A7420(v965, sub_1800AC8F0, v146, v147, v754, v786, v819);
  sub_1800A5538(v1337, &v845, 0);
  v148 = sub_1800A8F6C(
           (unsigned int)v1642,
           v7,
           (unsigned int)v1337,
           (unsigned int)v1338,
           (__int64)v1339,
           (__int64)v1340,
           (__int64)v1341);
  sub_1800ABF70(a1 + 10784, v148);
  sub_1800AAED8(v1642);
  sub_1800AB520(v1337);
  sub_1800AB520(v1338);
  sub_1800AB520(v1339);
  sub_1800AB520(v1340);
  sub_1800AB520(v1341);
  sub_18001D80C(v1277, L"LastWriterWins");
  sub_1800B7734(a1, v1277, a1 + 10784);
  sub_180020E60((__int64)v1277);
  sub_18001D80C(v1218, L"OptimalMaxPackageSizeInBytes");
  sub_1800A4D68(v1346, 0, 0);
  sub_1800A9798(v1345, 0);
  v149 = sub_18001D71C((__int64)v1001, (__int64)v1218);
  v150 = sub_180037524(a1 + 136);
  LOBYTE(v151) = 0;
  v152 = sub_1800A725C((unsigned int)&v1158, (unsigned int)sub_1800ACE10, v150, v151, v149);
  sub_1800A6134(v1344, v152, 0);
  v153 = sub_18001D71C((__int64)v1002, (__int64)v1218);
  v154 = sub_180037524(a1 + 136);
  LOBYTE(v155) = 0;
  v156 = sub_1800A7884((unsigned int)&v1159, (unsigned int)sub_1800ACDB0, v154, v155, v153);
  sub_1800A6570(v1343, v156, 0);
  v157 = sub_18001D71C((__int64)v1003, (__int64)v1218);
  v158 = sub_180037524(a1 + 136);
  LOBYTE(v159) = 0;
  v160 = sub_1800A7360((unsigned int)&v1160, (unsigned int)sub_1800ACCF0, v158, v159, v157);
  sub_1800A5378(v1342, v160, 0);
  v161 = sub_1800A7E30(
           (unsigned int)v1662,
           (unsigned int)v1218,
           (int)a1 + 176,
           (unsigned int)v1342,
           (__int64)v1343,
           (__int64)v1344,
           (__int64)v1345,
           (__int64)v1346);
  sub_1800ABA8C(a1 + 11056, v161);
  sub_1800AABD8(v1662);
  sub_1800AB520(v1342);
  sub_1800AB520(v1343);
  sub_1800AB520(v1344);
  sub_1800AB520(v1345);
  sub_1800AB520(v1346);
  sub_1800B783C(a1, v1218, a1 + 11056);
  sub_180020E60((__int64)v1218);
  sub_18001D80C(v1219, L"OptimalMaxNumExternalFiles");
  sub_1800A45A8(v1351, 0, 0);
  sub_1800A9798(v1350, 0);
  v162 = sub_18001D71C((__int64)v1004, (__int64)v1219);
  v163 = sub_180037524(a1 + 136);
  LOBYTE(v164) = 0;
  v165 = sub_1800A725C((unsigned int)&v1161, (unsigned int)sub_1800ACE10, v163, v164, v162);
  sub_1800A6134(v1349, v165, 0);
  v166 = sub_18001D71C((__int64)v1005, (__int64)v1219);
  v167 = sub_180037524(a1 + 136);
  LOBYTE(v168) = 0;
  v169 = sub_1800A7884((unsigned int)&v1162, (unsigned int)sub_1800ACDB0, v167, v168, v166);
  sub_1800A6570(v1348, v169, 0);
  v170 = sub_18001D71C((__int64)v1006, (__int64)v1219);
  v171 = sub_180037524(a1 + 136);
  LOBYTE(v172) = 0;
  v173 = sub_1800A7360((unsigned int)&v1163, (unsigned int)sub_1800ACCF0, v171, v172, v170);
  sub_1800A5378(v1347, v173, 0);
  v174 = sub_1800A7E30(
           (unsigned int)v1663,
           (unsigned int)v1219,
           (int)a1 + 176,
           (unsigned int)v1347,
           (__int64)v1348,
           (__int64)v1349,
           (__int64)v1350,
           (__int64)v1351);
  sub_1800ABA8C(a1 + 11360, v174);
  sub_1800AABD8(v1663);
  sub_1800AB520(v1347);
  sub_1800AB520(v1348);
  sub_1800AB520(v1349);
  sub_1800AB520(v1350);
  sub_1800AB520(v1351);
  sub_1800B783C(a1, v1219, a1 + 11360);
  sub_180020E60((__int64)v1219);
  sub_18001D80C(v1220, L"OptimalMinExternalFileSizeInBytes");
  sub_1800A46E8(v1356, 0, 0);
  sub_1800A9798(v1355, 0);
  v175 = sub_18001D71C((__int64)v1007, (__int64)v1220);
  v176 = sub_180037524(a1 + 136);
  LOBYTE(v177) = 0;
  v178 = sub_1800A725C((unsigned int)&v1164, (unsigned int)sub_1800ACE10, v176, v177, v175);
  sub_1800A6134(v1354, v178, 0);
  v179 = sub_18001D71C((__int64)v1008, (__int64)v1220);
  v180 = sub_180037524(a1 + 136);
  LOBYTE(v181) = 0;
  v182 = sub_1800A7884((unsigned int)&v1165, (unsigned int)sub_1800ACDB0, v180, v181, v179);
  sub_1800A6570(v1353, v182, 0);
  v183 = sub_18001D71C((__int64)v1009, (__int64)v1220);
  v184 = sub_180037524(a1 + 136);
  LOBYTE(v185) = 0;
  v186 = sub_1800A7360((unsigned int)&v1166, (unsigned int)sub_1800ACCF0, v184, v185, v183);
  sub_1800A5378(v1352, v186, 0);
  v187 = sub_1800A7E30(
           (unsigned int)v1664,
           (unsigned int)v1220,
           (int)a1 + 176,
           (unsigned int)v1352,
           (__int64)v1353,
           (__int64)v1354,
           (__int64)v1355,
           (__int64)v1356);
  sub_1800ABA8C(a1 + 11664, v187);
  sub_1800AABD8(v1664);
  sub_1800AB520(v1352);
  sub_1800AB520(v1353);
  sub_1800AB520(v1354);
  sub_1800AB520(v1355);
  sub_1800AB520(v1356);
  sub_1800B783C(a1, v1220, a1 + 11664);
  sub_180020E60((__int64)v1220);
  sub_18001D80C(v1221, L"DebugEnableDifferenceLog");
  sub_1800A4F68(v1361, 0, 0);
  sub_1800A9798(v1360, 0);
  v188 = sub_18001D71C((__int64)v1010, (__int64)v1221);
  v189 = sub_180037524(a1 + 136);
  LOBYTE(v190) = 0;
  v191 = sub_1800A725C((unsigned int)&v1167, (unsigned int)sub_1800ACE10, v189, v190, v188);
  sub_1800A6134(v1359, v191, 0);
  v192 = sub_18001D71C((__int64)v1011, (__int64)v1221);
  v193 = sub_180037524(a1 + 136);
  LOBYTE(v194) = 0;
  v195 = sub_1800A7ADC((unsigned int)&v1168, (unsigned int)sub_1800ACDF0, v193, v194, v192);
  sub_1800A6D60(v1358, v195, 0);
  v196 = sub_18001D71C((__int64)v1012, (__int64)v1221);
  v197 = sub_180037524(a1 + 136);
  LOBYTE(v198) = 0;
  v199 = sub_1800A77C4((unsigned int)&v1169, (unsigned int)sub_1800ACD30, v197, v198, v196);
  sub_1800A5B68(v1357, v199, 0);
  v200 = sub_1800A8910(
           (unsigned int)v1665,
           (unsigned int)v1221,
           (int)a1 + 176,
           (unsigned int)v1357,
           (__int64)v1358,
           (__int64)v1359,
           (__int64)v1360,
           (__int64)v1361);
  sub_1800ABA8C(a1 + 11968, v200);
  sub_1800AABD8(v1665);
  sub_1800AB520(v1357);
  sub_1800AB520(v1358);
  sub_1800AB520(v1359);
  sub_1800AB520(v1360);
  sub_1800AB520(v1361);
  sub_1800B783C(a1, v1221, a1 + 11968);
  sub_180020E60((__int64)v1221);
  sub_18001D80C(v1222, L"LastWriterThreshold");
  sub_1800A4CA8(v1366, 0, 0);
  sub_1800A9798(v1365, 0);
  v201 = sub_18001D71C((__int64)v1013, (__int64)v1222);
  v202 = sub_180037524(a1 + 136);
  LOBYTE(v203) = 0;
  v204 = sub_1800A725C((unsigned int)&v1170, (unsigned int)sub_1800ACE10, v202, v203, v201);
  sub_1800A6134(v1364, v204, 0);
  v205 = sub_18001D71C((__int64)v1014, (__int64)v1222);
  v206 = sub_180037524(a1 + 136);
  LOBYTE(v207) = 0;
  v208 = sub_1800A7884((unsigned int)&v1171, (unsigned int)sub_1800ACDB0, v206, v207, v205);
  sub_1800A6570(v1363, v208, 0);
  v209 = sub_18001D71C((__int64)v1015, (__int64)v1222);
  v210 = sub_180037524(a1 + 136);
  LOBYTE(v211) = 0;
  v212 = sub_1800A7360((unsigned int)&v1172, (unsigned int)sub_1800ACCF0, v210, v211, v209);
  sub_1800A5378(v1362, v212, 0);
  v213 = sub_1800A7E30(
           (unsigned int)v1666,
           (unsigned int)v1222,
           (int)a1 + 176,
           (unsigned int)v1362,
           (__int64)v1363,
           (__int64)v1364,
           (__int64)v1365,
           (__int64)v1366);
  sub_1800ABA8C(a1 + 12272, v213);
  sub_1800AABD8(v1666);
  sub_1800AB520(v1362);
  sub_1800AB520(v1363);
  sub_1800AB520(v1364);
  sub_1800AB520(v1365);
  sub_1800AB520(v1366);
  sub_1800B783C(a1, v1222, a1 + 12272);
  sub_180020E60((__int64)v1222);
  sub_18001D80C(v1223, L"PreventOverlappingSynchronization");
  sub_1800A4B28(v1371, 0, 0);
  sub_1800A9798(v1370, 0);
  v214 = sub_18001D71C((__int64)v1016, (__int64)v1223);
  v215 = sub_180037524(a1 + 136);
  LOBYTE(v216) = 0;
  v217 = sub_1800A725C((unsigned int)&v1173, (unsigned int)sub_1800ACE10, v215, v216, v214);
  sub_1800A6134(v1369, v217, 0);
  v218 = sub_18001D71C((__int64)v1017, (__int64)v1223);
  v219 = sub_180037524(a1 + 136);
  LOBYTE(v220) = 0;
  v221 = sub_1800A7ADC((unsigned int)&v1174, (unsigned int)sub_1800ACDF0, v219, v220, v218);
  sub_1800A6D60(v1368, v221, 0);
  v222 = sub_18001D71C((__int64)v1018, (__int64)v1223);
  v223 = sub_180037524(a1 + 136);
  LOBYTE(v224) = 0;
  v225 = sub_1800A77C4((unsigned int)&v1175, (unsigned int)sub_1800ACD30, v223, v224, v222);
  sub_1800A5B68(v1367, v225, 0);
  v226 = sub_1800A8910(
           (unsigned int)v1667,
           (unsigned int)v1223,
           (int)a1 + 176,
           (unsigned int)v1367,
           (__int64)v1368,
           (__int64)v1369,
           (__int64)v1370,
           (__int64)v1371);
  sub_1800ABA8C(a1 + 12576, v226);
  sub_1800AABD8(v1667);
  sub_1800AB520(v1367);
  sub_1800AB520(v1368);
  sub_1800AB520(v1369);
  sub_1800AB520(v1370);
  sub_1800AB520(v1371);
  sub_1800B783C(a1, v1223, a1 + 12576);
  sub_180020E60((__int64)v1223);
  sub_18001D80C(v1224, L"OverrideMSTemplates");
  sub_1800A4D28(v1376, 0, 0);
  sub_1800A9798(v1375, 0);
  v227 = sub_18001D71C((__int64)v1019, (__int64)v1224);
  v228 = sub_180037524(a1 + 136);
  LOBYTE(v229) = 0;
  v230 = sub_1800A725C((unsigned int)&v1176, (unsigned int)sub_1800ACE10, v228, v229, v227);
  sub_1800A6134(v1374, v230, 0);
  v231 = sub_18001D71C((__int64)v1020, (__int64)v1224);
  v232 = sub_180037524(a1 + 136);
  LOBYTE(v233) = 0;
  v234 = sub_1800A7ADC((unsigned int)&v1177, (unsigned int)sub_1800ACDF0, v232, v233, v231);
  sub_1800A6D60(v1373, v234, 0);
  v235 = sub_18001D71C((__int64)v1021, (__int64)v1224);
  v236 = sub_180037524(a1 + 136);
  LOBYTE(v237) = 0;
  v238 = sub_1800A77C4((unsigned int)&v1178, (unsigned int)sub_1800ACD30, v236, v237, v235);
  sub_1800A5B68(v1372, v238, 0);
  v239 = sub_1800A8910(
           (unsigned int)v1668,
           (unsigned int)v1224,
           v5,
           (unsigned int)v1372,
           (__int64)v1373,
           (__int64)v1374,
           (__int64)v1375,
           (__int64)v1376);
  sub_1800ABA8C(a1 + 12880, v239);
  sub_1800AABD8(v1668);
  sub_1800AB520(v1372);
  sub_1800AB520(v1373);
  sub_1800AB520(v1374);
  sub_1800AB520(v1375);
  sub_1800AB520(v1376);
  sub_1800B783C(a1, v1224, a1 + 12880);
  sub_180020E60((__int64)v1224);
  sub_18001D80C(v1225, L"Offline Timestamp");
  sub_1800A9798(v1381, 0);
  sub_1800A9798(v1380, 0);
  v240 = sub_18001D71C((__int64)v1022, (__int64)v1225);
  v241 = sub_180037524(a1 + 136);
  LOBYTE(v242) = 0;
  v243 = sub_1800A725C((unsigned int)&v1179, (unsigned int)sub_1800ACE10, v241, v242, v240);
  sub_1800A6134(v1379, v243, 0);
  v244 = sub_18001D71C((__int64)v1023, (__int64)v1225);
  v245 = sub_180037524(a1 + 136);
  LOBYTE(v246) = 0;
  v247 = sub_1800A7A04((unsigned int)&v1180, (unsigned int)sub_1800ACDD0, v245, v246, v244);
  sub_1800A6B50(v1378, v247, 0);
  v248 = sub_18001D71C((__int64)v1024, (__int64)v1225);
  v249 = sub_180037524(a1 + 136);
  LOBYTE(v250) = 0;
  v251 = sub_1800A76EC((unsigned int)&v1181, (unsigned int)sub_1800ACD10, v249, v250, v248);
  sub_1800A5958(v1377, v251, 0);
  v252 = sub_1800A86D8(
           (unsigned int)v1669,
           (unsigned int)v1225,
           v7,
           (unsigned int)v1377,
           (__int64)v1378,
           (__int64)v1379,
           (__int64)v1380,
           (__int64)v1381);
  sub_1800ABA8C(a1 + 13184, v252);
  sub_1800AABD8(v1669);
  sub_1800AB520(v1377);
  sub_1800AB520(v1378);
  sub_1800AB520(v1379);
  sub_1800AB520(v1380);
  sub_1800AB520(v1381);
  sub_1800B783C(a1, v1225, a1 + 13184);
  sub_180020E60((__int64)v1225);
  sub_18001D80C(v1263, L"DebugTraceLogFilter");
  sub_1800A49A8(v1386, 0, 0);
  sub_1800A9798(v1385, 0);
  sub_1800A9798(v1384, 0);
  v253 = sub_18001D71C((__int64)v1025, (__int64)v1263);
  v254 = sub_180037524(a1 + 136);
  LOBYTE(v255) = 0;
  v256 = sub_1800A7884((unsigned int)&v1182, (unsigned int)sub_1800ACDB0, v254, v255, v253);
  sub_1800A6570(v1383, v256, 0);
  v257 = sub_18001D71C((__int64)v1026, (__int64)v1263);
  v258 = sub_180037524(a1 + 136);
  LOBYTE(v259) = 0;
  v260 = sub_1800A7360((unsigned int)&v1183, (unsigned int)sub_1800ACCF0, v258, v259, v257);
  sub_1800A5378(v1382, v260, 0);
  v261 = sub_1800A7E30(
           (unsigned int)v1670,
           (unsigned int)v1263,
           (int)a1 + 176,
           (unsigned int)v1382,
           (__int64)v1383,
           (__int64)v1384,
           (__int64)v1385,
           (__int64)v1386);
  sub_1800ABA8C(a1 + 13488, v261);
  sub_1800AABD8(v1670);
  sub_1800AB520(v1382);
  sub_1800AB520(v1383);
  sub_1800AB520(v1384);
  sub_1800AB520(v1385);
  sub_1800AB520(v1386);
  sub_1800B783C(a1, v1263, a1 + 13488);
  sub_180020E60((__int64)v1263);
  sub_18001D80C(v1264, L"RepositoryOwnerCheckEnabled");
  sub_1800A4C28(v1391, 0, 0);
  sub_1800A9798(v1390, 0);
  sub_1800A9798(v1389, 0);
  v262 = sub_18001D71C((__int64)v1027, (__int64)v1264);
  v263 = sub_180037524(a1 + 136);
  LOBYTE(v264) = 0;
  v265 = sub_1800A7ADC((unsigned int)&v1184, (unsigned int)sub_1800ACDF0, v263, v264, v262);
  sub_1800A6D60(v1388, v265, 0);
  v266 = sub_18001D71C((__int64)v1028, (__int64)v1264);
  v267 = sub_180037524(a1 + 136);
  LOBYTE(v268) = 0;
  v269 = sub_1800A77C4((unsigned int)&v1185, (unsigned int)sub_1800ACD30, v267, v268, v266);
  sub_1800A5B68(v1387, v269, 0);
  v270 = sub_1800A8910(
           (unsigned int)v1671,
           (unsigned int)v1264,
           v9,
           (unsigned int)v1387,
           (__int64)v1388,
           (__int64)v1389,
           (__int64)v1390,
           (__int64)v1391);
  sub_1800ABA8C(a1 + 13792, v270);
  sub_1800AABD8(v1671);
  sub_1800AB520(v1387);
  sub_1800AB520(v1388);
  sub_1800AB520(v1389);
  sub_1800AB520(v1390);
  sub_1800AB520(v1391);
  sub_1800B783C(a1, v1264, a1 + 13792);
  sub_180020E60((__int64)v1264);
  sub_18001D80C(v1265, L"ExcludedFileTypes");
  sub_1800A49E8(v1396, 0, 0);
  sub_1800A9798(v1395, 0);
  sub_1800A9798(v1394, 0);
  v271 = sub_18001D71C((__int64)v1029, (__int64)v1265);
  v272 = sub_180037524(a1 + 136);
  LOBYTE(v273) = 0;
  v274 = sub_1800A7944((unsigned int)&v1186, (unsigned int)sub_1800ACD90, v272, v273, v271);
  sub_1800A6940(v1393, v274, 0);
  v275 = sub_18001D71C((__int64)v1030, (__int64)v1265);
  v276 = sub_180037524(a1 + 136);
  LOBYTE(v277) = 0;
  v278 = sub_1800A762C((unsigned int)&v1187, (unsigned int)sub_1800ACCD0, v276, v277, v275);
  sub_1800A5748(v1392, v278, 0);
  v279 = sub_1800A84A0(
           (unsigned int)v1672,
           (unsigned int)v1265,
           v9,
           (unsigned int)v1392,
           (__int64)v1393,
           (__int64)v1394,
           (__int64)v1395,
           (__int64)v1396);
  sub_1800ABA8C(a1 + 14096, v279);
  sub_1800AABD8(v1672);
  sub_1800AB520(v1392);
  sub_1800AB520(v1393);
  sub_1800AB520(v1394);
  sub_1800AB520(v1395);
  sub_1800AB520(v1396);
  sub_1800B783C(a1, v1265, a1 + 14096);
  sub_180020E60((__int64)v1265);
  sub_18001D80C(v1266, L"HideSettingsPackagesFolder");
  sub_1800A5068(v1401, 0, 0);
  sub_1800A9798(v1400, 0);
  sub_1800A9798(v1399, 0);
  v280 = sub_18001D71C((__int64)v1031, (__int64)v1266);
  v281 = sub_180037524(a1 + 136);
  LOBYTE(v282) = 0;
  v283 = sub_1800A7ADC((unsigned int)&v1188, (unsigned int)sub_1800ACDF0, v281, v282, v280);
  sub_1800A6D60(v1398, v283, 0);
  v284 = sub_18001D71C((__int64)v1032, (__int64)v1266);
  v285 = sub_180037524(a1 + 136);
  LOBYTE(v286) = 0;
  v287 = sub_1800A77C4((unsigned int)&v1189, (unsigned int)sub_1800ACD30, v285, v286, v284);
  sub_1800A5B68(v1397, v287, 0);
  v288 = sub_1800A8910(
           (unsigned int)v1673,
           (unsigned int)v1266,
           v9,
           (unsigned int)v1397,
           (__int64)v1398,
           (__int64)v1399,
           (__int64)v1400,
           (__int64)v1401);
  sub_1800ABA8C(a1 + 14400, v288);
  sub_1800AABD8(v1673);
  sub_1800AB520(v1397);
  sub_1800AB520(v1398);
  sub_1800AB520(v1399);
  sub_1800AB520(v1400);
  sub_1800AB520(v1401);
  sub_1800B783C(a1, v1266, a1 + 14400);
  sub_180020E60((__int64)v1266);
  sub_18001D80C(v1267, L"InitialOsSettingsExportDelay");
  sub_1800A48E8(v1406, 0, 0);
  sub_1800A9798(v1405, 0);
  sub_1800A9798(v1404, 0);
  v289 = sub_18001D71C((__int64)v1033, (__int64)v1267);
  v290 = sub_180037524(a1 + 136);
  LOBYTE(v291) = 0;
  v292 = sub_1800A7884((unsigned int)&v1190, (unsigned int)sub_1800ACDB0, v290, v291, v289);
  sub_1800A6570(v1403, v292, 0);
  v293 = sub_18001D71C((__int64)v1034, (__int64)v1267);
  v294 = sub_180037524(a1 + 136);
  LOBYTE(v295) = 0;
  v296 = sub_1800A7360((unsigned int)&v1191, (unsigned int)sub_1800ACCF0, v294, v295, v293);
  sub_1800A5378(v1402, v296, 0);
  v297 = sub_1800A7E30(
           (unsigned int)v1674,
           (unsigned int)v1267,
           v7,
           (unsigned int)v1402,
           (__int64)v1403,
           (__int64)v1404,
           (__int64)v1405,
           (__int64)v1406);
  sub_1800ABA8C(a1 + 14704, v297);
  sub_1800AABD8(v1674);
  sub_1800AB520(v1402);
  sub_1800AB520(v1403);
  sub_1800AB520(v1404);
  sub_1800AB520(v1405);
  sub_1800AB520(v1406);
  sub_1800B783C(a1, v1267, a1 + 14704);
  sub_180020E60((__int64)v1267);
  sub_18001D80C(v1254, L"StdpFlags");
  sub_1800A5028(v1411, 0, 0);
  sub_1800A9798(v1410, 0);
  sub_1800A9798(v1409, 0);
  v298 = sub_18001D71C((__int64)v1035, (__int64)v1254);
  v299 = sub_180037524(a1 + 136);
  LOBYTE(v300) = 0;
  v301 = sub_1800A7884((unsigned int)&v1192, (unsigned int)sub_1800ACDB0, v299, v300, v298);
  sub_1800A6570(v1408, v301, 0);
  v302 = sub_18001D71C((__int64)v1036, (__int64)v1254);
  v303 = sub_180037524(a1 + 136);
  LOBYTE(v304) = 0;
  v305 = sub_1800A7360((unsigned int)&v1193, (unsigned int)sub_1800ACCF0, v303, v304, v302);
  sub_1800A5378(v1407, v305, 0);
  v306 = sub_1800A7E30(
           (unsigned int)v1675,
           (unsigned int)v1254,
           v9,
           (unsigned int)v1407,
           (__int64)v1408,
           (__int64)v1409,
           (__int64)v1410,
           (__int64)v1411);
  sub_1800ABA8C(a1 + 15008, v306);
  sub_1800AABD8(v1675);
  sub_1800AB520(v1407);
  sub_1800AB520(v1408);
  sub_1800AB520(v1409);
  sub_1800AB520(v1410);
  sub_1800AB520(v1411);
  sub_1800B783C(a1, v1254, a1 + 15008);
  sub_180020E60((__int64)v1254);
  sub_18001D80C(v1255, L"StdpInterval");
  sub_1800A45E8(v1416, 0, 0);
  sub_1800A9798(v1415, 0);
  sub_1800A9798(v1414, 0);
  v307 = sub_18001D71C((__int64)v1037, (__int64)v1255);
  v308 = sub_180037524(a1 + 136);
  LOBYTE(v309) = 0;
  v310 = sub_1800A7884((unsigned int)&v1194, (unsigned int)sub_1800ACDB0, v308, v309, v307);
  sub_1800A6570(v1413, v310, 0);
  v311 = sub_18001D71C((__int64)v1038, (__int64)v1255);
  v312 = sub_180037524(a1 + 136);
  LOBYTE(v313) = 0;
  v314 = sub_1800A7360((unsigned int)&v1195, (unsigned int)sub_1800ACCF0, v312, v313, v311);
  sub_1800A5378(v1412, v314, 0);
  v315 = sub_1800A7E30(
           (unsigned int)v1676,
           (unsigned int)v1255,
           v9,
           (unsigned int)v1412,
           (__int64)v1413,
           (__int64)v1414,
           (__int64)v1415,
           (__int64)v1416);
  sub_1800ABA8C(a1 + 15312, v315);
  sub_1800AABD8(v1676);
  sub_1800AB520(v1412);
  sub_1800AB520(v1413);
  sub_1800AB520(v1414);
  sub_1800AB520(v1415);
  sub_1800AB520(v1416);
  sub_1800B783C(a1, v1255, a1 + 15312);
  sub_180020E60((__int64)v1255);
  sub_18001D80C(v1256, L"ADSettingsStoragePath");
  sub_1800A9798(v1421, 0);
  sub_1800A9798(v1420, 0);
  sub_1800A9798(v1419, 0);
  v316 = sub_18001D71C((__int64)v1039, (__int64)v1256);
  v317 = sub_180037524(a1 + 136);
  LOBYTE(v318) = 0;
  v319 = sub_1800A7450((unsigned int)&v1196, (unsigned int)sub_1800ACD70, v317, v318, v316);
  sub_1800A6780(v1418, v319, 0);
  v320 = sub_18001D71C((__int64)v1040, (__int64)v1256);
  v321 = sub_180037524(a1 + 136);
  LOBYTE(v322) = 0;
  v323 = sub_1800A7450((unsigned int)&v1197, (unsigned int)sub_1800ACCB0, v321, v322, v320);
  sub_1800A5588(v1417, v323, 0);
  v324 = sub_1800A8268(
           (unsigned int)v1677,
           (unsigned int)v1256,
           v7,
           (unsigned int)v1417,
           (__int64)v1418,
           (__int64)v1419,
           (__int64)v1420,
           (__int64)v1421);
  sub_1800ABCC0(a1 + 18656, v324);
  sub_1800AABD8(v1677);
  sub_1800AB520(v1417);
  sub_1800AB520(v1418);
  sub_1800AB520(v1419);
  sub_1800AB520(v1420);
  sub_1800AB520(v1421);
  sub_1800B783C(a1, v1256, a1 + 18656);
  sub_180020E60((__int64)v1256);
  sub_18001D80C(v1257, L"CurrentSettingsStoragePath");
  sub_1800A9798(v1426, 0);
  sub_1800A9798(v1425, 0);
  sub_1800A9798(v1424, 0);
  v325 = sub_18001D71C((__int64)v1041, (__int64)v1257);
  v326 = sub_180037524(a1 + 136);
  LOBYTE(v327) = 0;
  v328 = sub_1800A7450((unsigned int)&v1198, (unsigned int)sub_1800ACD70, v326, v327, v325);
  sub_1800A6780(v1423, v328, 0);
  v329 = sub_18001D71C((__int64)v1042, (__int64)v1257);
  v330 = sub_180037524(a1 + 136);
  LOBYTE(v331) = 0;
  v332 = sub_1800A7450((unsigned int)&v1199, (unsigned int)sub_1800ACCB0, v330, v331, v329);
  sub_1800A5588(v1422, v332, 0);
  v333 = sub_1800A8268(
           (unsigned int)v1678,
           (unsigned int)v1257,
           v7,
           (unsigned int)v1422,
           (__int64)v1423,
           (__int64)v1424,
           (__int64)v1425,
           (__int64)v1426);
  sub_1800ABCC0(a1 + 18960, v333);
  sub_1800AABD8(v1678);
  sub_1800AB520(v1422);
  sub_1800AB520(v1423);
  sub_1800AB520(v1424);
  sub_1800AB520(v1425);
  sub_1800AB520(v1426);
  sub_1800B783C(a1, v1257, a1 + 18960);
  sub_180020E60((__int64)v1257);
  sub_1800A9798(v1483, 0);
  sub_1800A9798(v1484, 0);
  v334 = sub_180037524(a1 + 136);
  LOBYTE(v787) = 0;
  LOBYTE(v755) = 0;
  LOBYTE(v335) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v966, sub_1800AC970, v334, v335, v755, v787, v820);
  sub_1800A5F58(v1485, &v845, 0);
  v336 = sub_180037524(a1 + 136);
  LOBYTE(v821) = 0;
  LOBYTE(v788) = 0;
  LOBYTE(v756) = 0;
  LOBYTE(v337) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v967, sub_1800AC950, v336, v337, v756, v788, v821);
  sub_1800A6B00(v1486, &v845, 0);
  v338 = sub_180037524(a1 + 136);
  LOBYTE(v822) = 0;
  LOBYTE(v789) = 0;
  LOBYTE(v757) = 0;
  LOBYTE(v339) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v968, sub_1800AC930, v338, v339, v757, v789, v822);
  sub_1800A5908(v1427, &v845, 0);
  v340 = sub_1800A9334(
           (unsigned int)v1643,
           v7,
           (unsigned int)v1427,
           (unsigned int)v1486,
           (__int64)v1485,
           (__int64)v1484,
           (__int64)v1483);
  sub_1800ABF70(a1 + 19264, v340);
  sub_1800AB1D0(v1643);
  sub_1800AB520(v1427);
  sub_1800AB520(v1486);
  sub_1800AB520(v1485);
  sub_1800AB520(v1484);
  sub_1800AB520(v1483);
  sub_18001D80C(v1278, L"RestoreSettingPackageTimestamp");
  sub_1800B7734(a1, v1278, a1 + 19264);
  sub_180020E60((__int64)v1278);
  sub_1800A9798(v1490, 0);
  sub_1800A9798(v1489, 0);
  v341 = sub_180037524(a1 + 136);
  LOBYTE(v790) = 0;
  LOBYTE(v758) = 0;
  LOBYTE(v342) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v984, sub_1800AC9D0, v341, v342, v758, v790, v823);
  sub_1800A5F58(v1488, &v845, 0);
  v343 = sub_180037524(a1 + 136);
  LOBYTE(v824) = 0;
  LOBYTE(v791) = 0;
  LOBYTE(v759) = 0;
  LOBYTE(v344) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v991, sub_1800AC9B0, v343, v344, v759, v791, v824);
  sub_1800A6394(v1487, &v845, 0);
  v345 = sub_180037524(a1 + 136);
  LOBYTE(v825) = 0;
  LOBYTE(v792) = 0;
  LOBYTE(v760) = 0;
  LOBYTE(v346) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v878, sub_1800AC990, v345, v346, v760, v792, v825);
  sub_1800A519C(v1601, &v845, 0);
  v347 = sub_1800A8B48(
           (unsigned int)v1644,
           v7,
           (unsigned int)v1601,
           (unsigned int)v1487,
           (__int64)v1488,
           (__int64)v1489,
           (__int64)v1490);
  sub_1800ABF70(a1 + 19536, v347);
  sub_1800AAD5C(v1644);
  sub_1800AB520(v1601);
  sub_1800AB520(v1487);
  sub_1800AB520(v1488);
  sub_1800AB520(v1489);
  sub_1800AB520(v1490);
  sub_18001D80C(v1279, L"RestoreSettingPackageType");
  sub_1800B7734(a1, v1279, a1 + 19536);
  sub_180020E60((__int64)v1279);
  sub_1800A9798(v1495, 0);
  sub_1800A9798(v1494, 0);
  v348 = sub_180037524(a1 + 136);
  LOBYTE(v793) = 0;
  LOBYTE(v761) = 0;
  LOBYTE(v349) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v879, sub_1800ACA30, v348, v349, v761, v793, v826);
  sub_1800A5F58(v1493, &v845, 0);
  v350 = sub_180037524(a1 + 136);
  LOBYTE(v827) = 0;
  LOBYTE(v794) = 0;
  LOBYTE(v762) = 0;
  LOBYTE(v351) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v880, sub_1800ACA10, v350, v351, v762, v794, v827);
  sub_1800A6B00(v1492, &v845, 0);
  v352 = sub_180037524(a1 + 136);
  LOBYTE(v828) = 0;
  LOBYTE(v795) = 0;
  LOBYTE(v763) = 0;
  LOBYTE(v353) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v881, sub_1800AC9F0, v352, v353, v763, v795, v828);
  sub_1800A5908(v1491, &v845, 0);
  v354 = sub_1800A9334(
           (unsigned int)v1645,
           v9,
           (unsigned int)v1491,
           (unsigned int)v1492,
           (__int64)v1493,
           (__int64)v1494,
           (__int64)v1495);
  sub_1800ABF70(a1 + 19808, v354);
  sub_1800AB1D0(v1645);
  sub_1800AB520(v1491);
  sub_1800AB520(v1492);
  sub_1800AB520(v1493);
  sub_1800AB520(v1494);
  sub_1800AB520(v1495);
  sub_18001D80C(v1280, L"TemplateRegistrationTimestamp");
  sub_1800B7734(a1, v1280, a1 + 19808);
  sub_180020E60((__int64)v1280);
  sub_1800A4EE8(v1500, 0, 0);
  sub_1800A9798(v1499, 0);
  sub_1800A9798(v1498, 0);
  v355 = sub_180037524(a1 + 136);
  LOBYTE(v829) = 0;
  LOBYTE(v796) = 0;
  LOBYTE(v764) = 0;
  LOBYTE(v356) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v882, sub_1800ACA70, v355, v356, v764, v796, v829);
  sub_1800A6394(v1497, &v845, 0);
  v357 = sub_180037524(a1 + 136);
  LOBYTE(v830) = 0;
  LOBYTE(v797) = 0;
  LOBYTE(v765) = 0;
  LOBYTE(v358) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v883, sub_1800ACA50, v357, v358, v765, v797, v830);
  sub_1800A519C(v1496, &v845, 0);
  v359 = sub_1800A8B48(
           (unsigned int)v1646,
           v7,
           (unsigned int)v1496,
           (unsigned int)v1497,
           (__int64)v1498,
           (__int64)v1499,
           (__int64)v1500);
  sub_1800ABF70(a1 + 20080, v359);
  sub_1800AAD5C(v1646);
  sub_1800AB520(v1496);
  sub_1800AB520(v1497);
  sub_1800AB520(v1498);
  sub_1800AB520(v1499);
  sub_1800AB520(v1500);
  sub_18001D80C(v1281, L"RestoreCount");
  sub_1800B7734(a1, v1281, a1 + 20080);
  sub_180020E60((__int64)v1281);
  sub_18001D80C(v1258, L"InstallTimestamp");
  sub_1800A9798(v1505, 0);
  sub_1800A9798(v1504, 0);
  sub_1800A9798(v1503, 0);
  v360 = sub_18001D71C((__int64)v1043, (__int64)v1258);
  v361 = sub_180037524(a1 + 136);
  LOBYTE(v362) = 0;
  v363 = sub_1800A7A04((unsigned int)&v1200, (unsigned int)sub_1800ACDD0, v361, v362, v360);
  sub_1800A6B50(v1502, v363, 0);
  v364 = sub_18001D71C((__int64)v1044, (__int64)v1258);
  v365 = sub_180037524(a1 + 136);
  LOBYTE(v366) = 0;
  v367 = sub_1800A76EC((unsigned int)&v1201, (unsigned int)sub_1800ACD10, v365, v366, v364);
  sub_1800A5958(v1501, v367, 0);
  v368 = sub_1800A86D8(
           (unsigned int)v1679,
           (unsigned int)v1258,
           v9,
           (unsigned int)v1501,
           (__int64)v1502,
           (__int64)v1503,
           (__int64)v1504,
           (__int64)v1505);
  sub_1800ABA8C(a1 + 20352, v368);
  sub_1800AABD8(v1679);
  sub_1800AB520(v1501);
  sub_1800AB520(v1502);
  sub_1800AB520(v1503);
  sub_1800AB520(v1504);
  sub_1800AB520(v1505);
  sub_1800B783C(a1, v1258, a1 + 20352);
  sub_180020E60((__int64)v1258);
  sub_18001D80C(v1259, L"CustomerExperienceImprovementProgram");
  sub_1800A4868(v1510, 0, 0);
  sub_1800A9798(v1509, 0);
  sub_1800A9798(v1508, 0);
  v369 = sub_18001D71C((__int64)v1045, (__int64)v1259);
  v370 = sub_180037524(a1 + 136);
  LOBYTE(v371) = 0;
  v372 = sub_1800A7ADC((unsigned int)&v1202, (unsigned int)sub_1800ACDF0, v370, v371, v369);
  sub_1800A6D60(v1507, v372, 0);
  v373 = sub_18001D71C((__int64)v1046, (__int64)v1259);
  v374 = sub_180037524(a1 + 136);
  LOBYTE(v375) = 0;
  v376 = sub_1800A77C4((unsigned int)&v1203, (unsigned int)sub_1800ACD30, v374, v375, v373);
  sub_1800A5B68(v1506, v376, 0);
  v377 = sub_1800A8910(
           (unsigned int)v1680,
           (unsigned int)v1259,
           (int)a1 + 176,
           (unsigned int)v1506,
           (__int64)v1507,
           (__int64)v1508,
           (__int64)v1509,
           (__int64)v1510);
  sub_1800ABA8C(a1 + 15616, v377);
  sub_1800AABD8(v1680);
  sub_1800AB520(v1506);
  sub_1800AB520(v1507);
  sub_1800AB520(v1508);
  sub_1800AB520(v1509);
  sub_1800AB520(v1510);
  sub_1800B783C(a1, v1259, a1 + 15616);
  sub_180020E60((__int64)v1259);
  sub_18001D80C(v1260, L"ApplyExplorerCompatFix");
  sub_1800A4BA8(v1515, 0, 0);
  sub_1800A9798(v1514, 0);
  sub_1800A9798(v1513, 0);
  v378 = sub_18001D71C((__int64)v1047, (__int64)v1260);
  v379 = sub_180037524(a1 + 136);
  LOBYTE(v380) = 0;
  v381 = sub_1800A7ADC((unsigned int)&v1204, (unsigned int)sub_1800ACDF0, v379, v380, v378);
  sub_1800A6D60(v1512, v381, 0);
  v382 = sub_18001D71C((__int64)v1048, (__int64)v1260);
  v383 = sub_180037524(a1 + 136);
  LOBYTE(v384) = 0;
  v385 = sub_1800A77C4((unsigned int)&v1205, (unsigned int)sub_1800ACD30, v383, v384, v382);
  sub_1800A5B68(v1511, v385, 0);
  v386 = sub_1800A8910(
           (unsigned int)v1681,
           (unsigned int)v1260,
           (int)a1 + 176,
           (unsigned int)v1511,
           (__int64)v1512,
           (__int64)v1513,
           (__int64)v1514,
           (__int64)v1515);
  sub_1800ABA8C(a1 + 15920, v386);
  sub_1800AABD8(v1681);
  sub_1800AB520(v1511);
  sub_1800AB520(v1512);
  sub_1800AB520(v1513);
  sub_1800AB520(v1514);
  sub_1800AB520(v1515);
  sub_1800B783C(a1, v1260, a1 + 15920);
  sub_180020E60((__int64)v1260);
  sub_18001D80C(v1226, L"ContactITUrl");
  sub_1800A9798(v1520, 0);
  sub_1800A9798(v1519, 0);
  v387 = sub_18001D71C((__int64)v1049, (__int64)v1226);
  v388 = sub_180037524(a1 + 136);
  LOBYTE(v389) = 0;
  v390 = sub_1800A725C((unsigned int)&v1206, (unsigned int)sub_1800ACE10, v388, v389, v387);
  sub_1800A6134(v1518, v390, 0);
  v391 = sub_18001D71C((__int64)v1050, (__int64)v1226);
  v392 = sub_180037524(a1 + 136);
  LOBYTE(v393) = 0;
  v394 = sub_1800A7450((unsigned int)&v1207, (unsigned int)sub_1800ACD70, v392, v393, v391);
  sub_1800A6780(v1517, v394, 0);
  v395 = sub_18001D71C((__int64)v1051, (__int64)v1226);
  v396 = sub_180037524(a1 + 136);
  LOBYTE(v397) = 0;
  v398 = sub_1800A7450((unsigned int)&v1061, (unsigned int)sub_1800ACCB0, v396, v397, v395);
  sub_1800A5588(v1516, v398, 0);
  v399 = sub_1800A8268(
           (unsigned int)v1682,
           (unsigned int)v1226,
           v5,
           (unsigned int)v1516,
           (__int64)v1517,
           (__int64)v1518,
           (__int64)v1519,
           (__int64)v1520);
  sub_1800ABCC0(a1 + 3584, v399);
  sub_1800AABD8(v1682);
  sub_1800AB520(v1516);
  sub_1800AB520(v1517);
  sub_1800AB520(v1518);
  sub_1800AB520(v1519);
  sub_1800AB520(v1520);
  sub_1800B783C(a1, v1226, a1 + 3584);
  sub_180020E60((__int64)v1226);
  sub_18001D80C(v1227, L"ContactITDescription");
  sub_1800A9798(v1525, 0);
  sub_1800A9798(v1524, 0);
  v400 = sub_18001D71C((__int64)v1052, (__int64)v1227);
  v401 = sub_180037524(a1 + 136);
  LOBYTE(v402) = 0;
  v403 = sub_1800A725C((unsigned int)&v1062, (unsigned int)sub_1800ACE10, v401, v402, v400);
  sub_1800A6134(v1523, v403, 0);
  v404 = sub_18001D71C((__int64)v1053, (__int64)v1227);
  v405 = sub_180037524(a1 + 136);
  LOBYTE(v406) = 0;
  v407 = sub_1800A7450((unsigned int)&v1063, (unsigned int)sub_1800ACD70, v405, v406, v404);
  sub_1800A6780(v1522, v407, 0);
  v408 = sub_18001D71C((__int64)v1054, (__int64)v1227);
  v409 = sub_180037524(a1 + 136);
  LOBYTE(v410) = 0;
  v411 = sub_1800A7450((unsigned int)&v1064, (unsigned int)sub_1800ACCB0, v409, v410, v408);
  sub_1800A5588(v1521, v411, 0);
  v412 = sub_1800A8268(
           (unsigned int)v1683,
           (unsigned int)v1227,
           v5,
           (unsigned int)v1521,
           (__int64)v1522,
           (__int64)v1523,
           (__int64)v1524,
           (__int64)v1525);
  sub_1800ABCC0(a1 + 3888, v412);
  sub_1800AABD8(v1683);
  sub_1800AB520(v1521);
  sub_1800AB520(v1522);
  sub_1800AB520(v1523);
  sub_1800AB520(v1524);
  sub_1800AB520(v1525);
  sub_1800B783C(a1, v1227, a1 + 3888);
  sub_180020E60((__int64)v1227);
  sub_18001D80C(v1261, L"TrayIconEnabled");
  sub_1800A4E68(v1530, 0, 0);
  sub_1800A9798(v1529, 0);
  v413 = sub_18001D71C((__int64)v1055, (__int64)v1261);
  v414 = sub_180037524(a1 + 136);
  LOBYTE(v415) = 0;
  v416 = sub_1800A725C((unsigned int)&v1065, (unsigned int)sub_1800ACE10, v414, v415, v413);
  sub_1800A6134(v1528, v416, 0);
  v417 = sub_18001D71C((__int64)v1056, (__int64)v1261);
  v418 = sub_180037524(a1 + 136);
  LOBYTE(v419) = 0;
  v420 = sub_1800A7ADC((unsigned int)&v1066, (unsigned int)sub_1800ACDF0, v418, v419, v417);
  sub_1800A6D60(v1527, v420, 0);
  v421 = sub_180037524(a1 + 136);
  v422 = sub_1800A7BCC(v1060, sub_1800AC870, v421, 0);
  v845 = *(_OWORD *)v422;
  v846 = *(_QWORD *)(v422 + 16);
  sub_1800A5138(v1526, &v845, 0);
  v423 = sub_1800A8910(
           (unsigned int)v1684,
           (unsigned int)v1261,
           v5,
           (unsigned int)v1526,
           (__int64)v1527,
           (__int64)v1528,
           (__int64)v1529,
           (__int64)v1530);
  sub_1800ABA8C(a1 + 4192, v423);
  sub_1800AABD8(v1684);
  sub_1800AB520(v1526);
  sub_1800AB520(v1527);
  sub_1800AB520(v1528);
  sub_1800AB520(v1529);
  sub_1800AB520(v1530);
  sub_1800B783C(a1, v1261, a1 + 4192);
  sub_180020E60((__int64)v1261);
  sub_18001D80C(v1228, L"FirstUseNotificationEnabled");
  sub_1800A4A68(v1535, 0, 0);
  sub_1800A9798(v1534, 0);
  v424 = sub_18001D71C((__int64)v1057, (__int64)v1228);
  v425 = sub_180037524(a1 + 136);
  LOBYTE(v426) = 0;
  v427 = sub_1800A725C((unsigned int)&v1067, (unsigned int)sub_1800ACE10, v425, v426, v424);
  sub_1800A6134(v1533, v427, 0);
  v428 = sub_18001D71C((__int64)v1058, (__int64)v1228);
  v429 = sub_180037524(a1 + 136);
  LOBYTE(v430) = 0;
  v431 = sub_1800A7ADC((unsigned int)&v1068, (unsigned int)sub_1800ACDF0, v429, v430, v428);
  sub_1800A6D60(v1532, v431, 0);
  v432 = sub_18001D71C((__int64)v1059, (__int64)v1228);
  v433 = sub_180037524(a1 + 136);
  LOBYTE(v434) = 0;
  v435 = sub_1800A77C4((unsigned int)&v1069, (unsigned int)sub_1800ACD30, v433, v434, v432);
  sub_1800A5B68(v1531, v435, 0);
  v436 = sub_1800A8910(
           (unsigned int)v1685,
           (unsigned int)v1228,
           v5,
           (unsigned int)v1531,
           (__int64)v1532,
           (__int64)v1533,
           (__int64)v1534,
           (__int64)v1535);
  sub_1800ABA8C(a1 + 4496, v436);
  sub_1800AABD8(v1685);
  sub_1800AB520(v1531);
  sub_1800AB520(v1532);
  sub_1800AB520(v1533);
  sub_1800AB520(v1534);
  sub_1800AB520(v1535);
  sub_1800B783C(a1, v1228, a1 + 4496);
  sub_180020E60((__int64)v1228);
  sub_18001D80C(v1229, L"SyncProviderName");
  sub_1800A4E28(v1540, 0, 0);
  sub_1800A9798(v1539, 0);
  v437 = sub_18001D71C((__int64)v897, (__int64)v1229);
  v438 = sub_180037524(a1 + 136);
  LOBYTE(v439) = 0;
  v440 = sub_1800A725C((unsigned int)&v1070, (unsigned int)sub_1800ACE10, v438, v439, v437);
  sub_1800A6134(v1538, v440, 0);
  v441 = sub_18001D71C((__int64)v898, (__int64)v1229);
  v442 = sub_180037524(a1 + 136);
  LOBYTE(v443) = 0;
  v444 = sub_1800A7450((unsigned int)&v1071, (unsigned int)sub_1800ACD70, v442, v443, v441);
  sub_1800A6780(v1537, v444, 0);
  v445 = sub_18001D71C((__int64)v899, (__int64)v1229);
  v446 = sub_180037524(a1 + 136);
  LOBYTE(v447) = 0;
  v448 = sub_1800A7450((unsigned int)&v1072, (unsigned int)sub_1800ACCB0, v446, v447, v445);
  sub_1800A5588(v1536, v448, 0);
  v449 = sub_1800A8268(
           (unsigned int)v1686,
           (unsigned int)v1229,
           (int)a1 + 176,
           (unsigned int)v1536,
           (__int64)v1537,
           (__int64)v1538,
           (__int64)v1539,
           (__int64)v1540);
  sub_1800ABCC0(a1 + 4800, v449);
  sub_1800AABD8(v1686);
  sub_1800AB520(v1536);
  sub_1800AB520(v1537);
  sub_1800AB520(v1538);
  sub_1800AB520(v1539);
  sub_1800AB520(v1540);
  sub_1800B783C(a1, v1229, a1 + 4800);
  sub_180020E60((__int64)v1229);
  sub_18001D80C(v1230, L"DontSyncWindows8AppSettings");
  sub_1800A4AA8(v1545, 0, 0);
  sub_1800A9798(v1544, 0);
  v450 = sub_18001D71C((__int64)v900, (__int64)v1230);
  v451 = sub_180037524(a1 + 136);
  LOBYTE(v452) = 0;
  v453 = sub_1800A725C((unsigned int)&v1073, (unsigned int)sub_1800ACE10, v451, v452, v450);
  sub_1800A6134(v1543, v453, 0);
  v454 = sub_18001D71C((__int64)v901, (__int64)v1230);
  v455 = sub_180037524(a1 + 136);
  LOBYTE(v456) = 0;
  v457 = sub_1800A7ADC((unsigned int)&v1074, (unsigned int)sub_1800ACDF0, v455, v456, v454);
  sub_1800A6D60(v1542, v457, 0);
  v458 = sub_18001D71C((__int64)v902, (__int64)v1230);
  v459 = sub_180037524(a1 + 136);
  LOBYTE(v460) = 0;
  v461 = sub_1800A77C4((unsigned int)&v1075, (unsigned int)sub_1800ACD30, v459, v460, v458);
  sub_1800A5B68(v1541, v461, 0);
  v462 = sub_1800A8910(
           (unsigned int)v1687,
           (unsigned int)v1230,
           (int)a1 + 176,
           (unsigned int)v1541,
           (__int64)v1542,
           (__int64)v1543,
           (__int64)v1544,
           (__int64)v1545);
  sub_1800ABA8C(a1 + 5408, v462);
  sub_1800AABD8(v1687);
  sub_1800AB520(v1541);
  sub_1800AB520(v1542);
  sub_1800AB520(v1543);
  sub_1800AB520(v1544);
  sub_1800AB520(v1545);
  sub_1800B783C(a1, v1230, a1 + 5408);
  sub_180020E60((__int64)v1230);
  sub_18001D80C(v1231, L"SyncUnlistedWindows8Apps");
  sub_1800A4FE8(v1550, 0, 0);
  sub_1800A9798(v1549, 0);
  v463 = sub_18001D71C((__int64)v903, (__int64)v1231);
  v464 = sub_180037524(a1 + 136);
  LOBYTE(v465) = 0;
  v466 = sub_1800A725C((unsigned int)&v1076, (unsigned int)sub_1800ACE10, v464, v465, v463);
  sub_1800A6134(v1548, v466, 0);
  v467 = sub_18001D71C((__int64)v904, (__int64)v1231);
  v468 = sub_180037524(a1 + 136);
  LOBYTE(v469) = 0;
  v470 = sub_1800A7ADC((unsigned int)&v1077, (unsigned int)sub_1800ACDF0, v468, v469, v467);
  sub_1800A6D60(v1547, v470, 0);
  v471 = sub_18001D71C((__int64)v905, (__int64)v1231);
  v472 = sub_180037524(a1 + 136);
  LOBYTE(v473) = 0;
  v474 = sub_1800A77C4((unsigned int)&v1078, (unsigned int)sub_1800ACD30, v472, v473, v471);
  sub_1800A5B68(v1546, v474, 0);
  v475 = sub_1800A8910(
           (unsigned int)v1688,
           (unsigned int)v1231,
           (int)a1 + 176,
           (unsigned int)v1546,
           (__int64)v1547,
           (__int64)v1548,
           (__int64)v1549,
           (__int64)v1550);
  sub_1800ABA8C(a1 + 5712, v475);
  sub_1800AABD8(v1688);
  sub_1800AB520(v1546);
  sub_1800AB520(v1547);
  sub_1800AB520(v1548);
  sub_1800AB520(v1549);
  sub_1800AB520(v1550);
  sub_1800B783C(a1, v1231, a1 + 5712);
  sub_180020E60((__int64)v1231);
  sub_18001D80C(v1232, L"DebugLogFileName");
  sub_1800A9798(v1555, 0);
  sub_1800A9798(v1554, 0);
  v476 = sub_18001D71C((__int64)v906, (__int64)v1232);
  v477 = sub_180037524(a1 + 136);
  LOBYTE(v478) = 0;
  v479 = sub_1800A725C((unsigned int)&v1079, (unsigned int)sub_1800ACE10, v477, v478, v476);
  sub_1800A6134(v1553, v479, 0);
  v480 = sub_18001D71C((__int64)v907, (__int64)v1232);
  v481 = sub_180037524(a1 + 136);
  LOBYTE(v482) = 0;
  v483 = sub_1800A7450((unsigned int)&v1080, (unsigned int)sub_1800ACD70, v481, v482, v480);
  sub_1800A6780(v1552, v483, 0);
  v484 = sub_18001D71C((__int64)v908, (__int64)v1232);
  v485 = sub_180037524(a1 + 136);
  LOBYTE(v486) = 0;
  v487 = sub_1800A7450((unsigned int)&v1081, (unsigned int)sub_1800ACCB0, v485, v486, v484);
  sub_1800A5588(v1551, v487, 0);
  v488 = sub_1800A8268(
           (unsigned int)v1689,
           (unsigned int)v1232,
           v9,
           (unsigned int)v1551,
           (__int64)v1552,
           (__int64)v1553,
           (__int64)v1554,
           (__int64)v1555);
  sub_1800ABCC0(a1 + 16224, v488);
  sub_1800AABD8(v1689);
  sub_1800AB520(v1551);
  sub_1800AB520(v1552);
  sub_1800AB520(v1553);
  sub_1800AB520(v1554);
  sub_1800AB520(v1555);
  sub_1800B783C(a1, v1232, a1 + 16224);
  sub_180020E60((__int64)v1232);
  sub_18001D80C(v1233, L"RunSyncOnTrigger");
  sub_1800A47E8(v1560, 0, 0);
  sub_1800A9798(v1559, 0);
  v489 = sub_18001D71C((__int64)v909, (__int64)v1233);
  v490 = sub_180037524(a1 + 136);
  LOBYTE(v491) = 0;
  v492 = sub_1800A725C((unsigned int)&v1082, (unsigned int)sub_1800ACE10, v490, v491, v489);
  sub_1800A6134(v1558, v492, 0);
  v493 = sub_18001D71C((__int64)v910, (__int64)v1233);
  v494 = sub_180037524(a1 + 136);
  LOBYTE(v495) = 0;
  v496 = sub_1800A7ADC((unsigned int)&v1083, (unsigned int)sub_1800ACDF0, v494, v495, v493);
  sub_1800A6D60(v1557, v496, 0);
  v497 = sub_18001D71C((__int64)v911, (__int64)v1233);
  v498 = sub_180037524(a1 + 136);
  LOBYTE(v499) = 0;
  v500 = sub_1800A77C4((unsigned int)&v1084, (unsigned int)sub_1800ACD30, v498, v499, v497);
  sub_1800A5B68(v1556, v500, 0);
  v501 = sub_1800A8910(
           (unsigned int)v1690,
           (unsigned int)v1233,
           (int)a1 + 176,
           (unsigned int)v1556,
           (__int64)v1557,
           (__int64)v1558,
           (__int64)v1559,
           (__int64)v1560);
  sub_1800ABA8C(a1 + 6016, v501);
  sub_1800AABD8(v1690);
  sub_1800AB520(v1556);
  sub_1800AB520(v1557);
  sub_1800AB520(v1558);
  sub_1800AB520(v1559);
  sub_1800AB520(v1560);
  sub_1800B783C(a1, v1233, a1 + 6016);
  sub_180020E60((__int64)v1233);
  sub_18001D80C(v1234, L"WaitForSyncOnApplicationStart");
  sub_1800A4628(v1565, 0, 0);
  sub_1800A9798(v1564, 0);
  v502 = sub_18001D71C((__int64)v912, (__int64)v1234);
  v503 = sub_180037524(a1 + 136);
  LOBYTE(v504) = 0;
  v505 = sub_1800A725C((unsigned int)&v1085, (unsigned int)sub_1800ACE10, v503, v504, v502);
  sub_1800A6134(v1563, v505, 0);
  v506 = sub_18001D71C((__int64)v913, (__int64)v1234);
  v507 = sub_180037524(a1 + 136);
  LOBYTE(v508) = 0;
  v509 = sub_1800A7ADC((unsigned int)&v1086, (unsigned int)sub_1800ACDF0, v507, v508, v506);
  sub_1800A6D60(v1562, v509, 0);
  v510 = sub_18001D71C((__int64)v914, (__int64)v1234);
  v511 = sub_180037524(a1 + 136);
  LOBYTE(v512) = 0;
  v513 = sub_1800A77C4((unsigned int)&v1087, (unsigned int)sub_1800ACD30, v511, v512, v510);
  sub_1800A5B68(v1561, v513, 0);
  v514 = sub_1800A8910(
           (unsigned int)v1691,
           (unsigned int)v1234,
           (int)a1 + 176,
           (unsigned int)v1561,
           (__int64)v1562,
           (__int64)v1563,
           (__int64)v1564,
           (__int64)v1565);
  sub_1800ABA8C(a1 + 6320, v514);
  sub_1800AABD8(v1691);
  sub_1800AB520(v1561);
  sub_1800AB520(v1562);
  sub_1800AB520(v1563);
  sub_1800AB520(v1564);
  sub_1800AB520(v1565);
  sub_1800B783C(a1, v1234, a1 + 6320);
  sub_180020E60((__int64)v1234);
  sub_18001D80C(v1235, L"WaitForSyncOnLogon");
  sub_1800A4928(v1570, 0, 0);
  sub_1800A9798(v1569, 0);
  v515 = sub_18001D71C((__int64)v915, (__int64)v1235);
  v516 = sub_180037524(a1 + 136);
  LOBYTE(v517) = 0;
  v518 = sub_1800A725C((unsigned int)&v1088, (unsigned int)sub_1800ACE10, v516, v517, v515);
  sub_1800A6134(v1568, v518, 0);
  v519 = sub_18001D71C((__int64)v916, (__int64)v1235);
  v520 = sub_180037524(a1 + 136);
  LOBYTE(v521) = 0;
  v522 = sub_1800A7ADC((unsigned int)&v1089, (unsigned int)sub_1800ACDF0, v520, v521, v519);
  sub_1800A6D60(v1567, v522, 0);
  v523 = sub_18001D71C((__int64)v917, (__int64)v1235);
  v524 = sub_180037524(a1 + 136);
  LOBYTE(v525) = 0;
  v526 = sub_1800A77C4((unsigned int)&v1090, (unsigned int)sub_1800ACD30, v524, v525, v523);
  sub_1800A5B68(v1566, v526, 0);
  v527 = sub_1800A8910(
           (unsigned int)v1692,
           (unsigned int)v1235,
           (int)a1 + 176,
           (unsigned int)v1566,
           (__int64)v1567,
           (__int64)v1568,
           (__int64)v1569,
           (__int64)v1570);
  sub_1800ABA8C(a1 + 6624, v527);
  sub_1800AABD8(v1692);
  sub_1800AB520(v1566);
  sub_1800AB520(v1567);
  sub_1800AB520(v1568);
  sub_1800AB520(v1569);
  sub_1800AB520(v1570);
  sub_1800B783C(a1, v1235, a1 + 6624);
  sub_180020E60((__int64)v1235);
  sub_18001D80C(v1236, L"WaitForSyncTimeoutInMilliseconds");
  sub_1800A4668(v1575, 0, 0);
  sub_1800A9798(v1574, 0);
  v528 = sub_18001D71C((__int64)v918, (__int64)v1236);
  v529 = sub_180037524(a1 + 136);
  LOBYTE(v530) = 0;
  v531 = sub_1800A725C((unsigned int)&v1091, (unsigned int)sub_1800ACE10, v529, v530, v528);
  sub_1800A6134(v1573, v531, 0);
  v532 = sub_18001D71C((__int64)v919, (__int64)v1236);
  v533 = sub_180037524(a1 + 136);
  LOBYTE(v534) = 0;
  v535 = sub_1800A7884((unsigned int)&v1092, (unsigned int)sub_1800ACDB0, v533, v534, v532);
  sub_1800A6570(v1572, v535, 0);
  v536 = sub_18001D71C((__int64)v920, (__int64)v1236);
  v537 = sub_180037524(a1 + 136);
  LOBYTE(v538) = 0;
  v539 = sub_1800A7360((unsigned int)&v1093, (unsigned int)sub_1800ACCF0, v537, v538, v536);
  sub_1800A5378(v1571, v539, 0);
  v540 = sub_1800A7E30(
           (unsigned int)v1693,
           (unsigned int)v1236,
           (int)a1 + 176,
           (unsigned int)v1571,
           (__int64)v1572,
           (__int64)v1573,
           (__int64)v1574,
           (__int64)v1575);
  sub_1800ABA8C(a1 + 6928, v540);
  sub_1800AABD8(v1693);
  sub_1800AB520(v1571);
  sub_1800AB520(v1572);
  sub_1800AB520(v1573);
  sub_1800AB520(v1574);
  sub_1800AB520(v1575);
  sub_1800B783C(a1, v1236, a1 + 6928);
  sub_180020E60((__int64)v1236);
  sub_18001D80C(v1237, L"SettingsStoragePathADAttribute");
  sub_1800A4FA8(v1580, 0, 0);
  sub_1800A9798(v1579, 0);
  v541 = sub_18001D71C((__int64)v921, (__int64)v1237);
  v542 = sub_180037524(a1 + 136);
  LOBYTE(v543) = 0;
  v544 = sub_1800A725C((unsigned int)&v1094, (unsigned int)sub_1800ACE10, v542, v543, v541);
  sub_1800A6134(v1578, v544, 0);
  v545 = sub_18001D71C((__int64)v922, (__int64)v1237);
  v546 = sub_180037524(a1 + 136);
  LOBYTE(v547) = 0;
  v548 = sub_1800A7450((unsigned int)&v1095, (unsigned int)sub_1800ACD70, v546, v547, v545);
  sub_1800A6780(v1577, v548, 0);
  v549 = sub_18001D71C((__int64)v923, (__int64)v1237);
  v550 = sub_180037524(a1 + 136);
  LOBYTE(v551) = 0;
  v552 = sub_1800A7450((unsigned int)&v1096, (unsigned int)sub_1800ACCB0, v550, v551, v549);
  sub_1800A5588(v1576, v552, 0);
  v553 = sub_1800A8268(
           (unsigned int)v1694,
           (unsigned int)v1237,
           (int)a1 + 176,
           (unsigned int)v1576,
           (__int64)v1577,
           (__int64)v1578,
           (__int64)v1579,
           (__int64)v1580);
  sub_1800ABCC0(a1 + 7232, v553);
  sub_1800AABD8(v1694);
  sub_1800AB520(v1576);
  sub_1800AB520(v1577);
  sub_1800AB520(v1578);
  sub_1800AB520(v1579);
  sub_1800AB520(v1580);
  sub_1800B783C(a1, v1237, a1 + 7232);
  sub_180020E60((__int64)v1237);
  sub_18001D80C(v1238, L"SyncConditionsAssemblyName");
  sub_1800A46A8(v1585, 0, 0);
  sub_1800A9798(v1584, 0);
  v554 = sub_18001D71C((__int64)v924, (__int64)v1238);
  v555 = sub_180037524(a1 + 136);
  LOBYTE(v556) = 0;
  v557 = sub_1800A725C((unsigned int)&v1097, (unsigned int)sub_1800ACE10, v555, v556, v554);
  sub_1800A6134(v1583, v557, 0);
  v558 = sub_18001D71C((__int64)v925, (__int64)v1238);
  v559 = sub_180037524(a1 + 136);
  LOBYTE(v560) = 0;
  v561 = sub_1800A7450((unsigned int)&v1098, (unsigned int)sub_1800ACD70, v559, v560, v558);
  sub_1800A6780(v1582, v561, 0);
  v562 = sub_18001D71C((__int64)v926, (__int64)v1238);
  v563 = sub_180037524(a1 + 136);
  LOBYTE(v564) = 0;
  v565 = sub_1800A7450((unsigned int)&v1099, (unsigned int)sub_1800ACCB0, v563, v564, v562);
  sub_1800A5588(v1581, v565, 0);
  v566 = sub_1800A8268(
           (unsigned int)v1695,
           (unsigned int)v1238,
           (int)a1 + 176,
           (unsigned int)v1581,
           (__int64)v1582,
           (__int64)v1583,
           (__int64)v1584,
           (__int64)v1585);
  sub_1800ABCC0(a1 + 7536, v566);
  sub_1800AABD8(v1695);
  sub_1800AB520(v1581);
  sub_1800AB520(v1582);
  sub_1800AB520(v1583);
  sub_1800AB520(v1584);
  sub_1800AB520(v1585);
  sub_1800B783C(a1, v1238, a1 + 7536);
  sub_180020E60((__int64)v1238);
  sub_18001D80C(v1239, L"SyncOverMeteredNetwork");
  sub_1800A4EA8(v1590, 0, 0);
  sub_1800A9798(v1589, 0);
  v567 = sub_18001D71C((__int64)v927, (__int64)v1239);
  v568 = sub_180037524(a1 + 136);
  LOBYTE(v569) = 0;
  v570 = sub_1800A725C((unsigned int)&v1132, (unsigned int)sub_1800ACE10, v568, v569, v567);
  sub_1800A6134(v1588, v570, 0);
  v571 = sub_18001D71C((__int64)v928, (__int64)v1239);
  v572 = sub_180037524(a1 + 136);
  LOBYTE(v573) = 0;
  v574 = sub_1800A7ADC((unsigned int)&v1100, (unsigned int)sub_1800ACDF0, v572, v573, v571);
  sub_1800A6D60(v1587, v574, 0);
  v575 = sub_18001D71C((__int64)v929, (__int64)v1239);
  v576 = sub_180037524(a1 + 136);
  LOBYTE(v577) = 0;
  v578 = sub_1800A77C4((unsigned int)&v1101, (unsigned int)sub_1800ACD30, v576, v577, v575);
  sub_1800A5B68(v1586, v578, 0);
  v579 = sub_1800A8910(
           (unsigned int)v1696,
           (unsigned int)v1239,
           (int)a1 + 176,
           (unsigned int)v1586,
           (__int64)v1587,
           (__int64)v1588,
           (__int64)v1589,
           (__int64)v1590);
  sub_1800ABA8C(a1 + 7840, v579);
  sub_1800AABD8(v1696);
  sub_1800AB520(v1586);
  sub_1800AB520(v1587);
  sub_1800AB520(v1588);
  sub_1800AB520(v1589);
  sub_1800AB520(v1590);
  sub_1800B783C(a1, v1239, a1 + 7840);
  sub_180020E60((__int64)v1239);
  sub_18001D80C(v1240, L"SyncOverMeteredNetworkWhenRoaming");
  sub_1800A4B68(v1595, 0, 0);
  sub_1800A9798(v1594, 0);
  v580 = sub_18001D71C((__int64)v930, (__int64)v1240);
  v581 = sub_180037524(a1 + 136);
  LOBYTE(v582) = 0;
  v583 = sub_1800A725C((unsigned int)&v1102, (unsigned int)sub_1800ACE10, v581, v582, v580);
  sub_1800A6134(v1593, v583, 0);
  v584 = sub_18001D71C((__int64)v931, (__int64)v1240);
  v585 = sub_180037524(a1 + 136);
  LOBYTE(v586) = 0;
  v587 = sub_1800A7ADC((unsigned int)&v1103, (unsigned int)sub_1800ACDF0, v585, v586, v584);
  sub_1800A6D60(v1592, v587, 0);
  v588 = sub_18001D71C((__int64)v932, (__int64)v1240);
  v589 = sub_180037524(a1 + 136);
  LOBYTE(v590) = 0;
  v591 = sub_1800A77C4((unsigned int)&v1104, (unsigned int)sub_1800ACD30, v589, v590, v588);
  sub_1800A5B68(v1591, v591, 0);
  v592 = sub_1800A8910(
           (unsigned int)v1697,
           (unsigned int)v1240,
           (int)a1 + 176,
           (unsigned int)v1591,
           (__int64)v1592,
           (__int64)v1593,
           (__int64)v1594,
           (__int64)v1595);
  sub_1800ABA8C(a1 + 8144, v592);
  sub_1800AABD8(v1697);
  sub_1800AB520(v1591);
  sub_1800AB520(v1592);
  sub_1800AB520(v1593);
  sub_1800AB520(v1594);
  sub_1800AB520(v1595);
  sub_1800B783C(a1, v1240, a1 + 8144);
  sub_180020E60((__int64)v1240);
  sub_1800A9798(v1600, 0);
  sub_1800A9798(v1599, 0);
  v593 = sub_180037524(a1 + 136);
  LOBYTE(v798) = 0;
  LOBYTE(v766) = 0;
  LOBYTE(v594) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v884, sub_1800ACAD0, v593, v594, v766, v798, v831);
  sub_1800A5F58(v1598, &v845, 0);
  v595 = sub_180037524(a1 + 136);
  LOBYTE(v832) = 0;
  LOBYTE(v799) = 0;
  LOBYTE(v767) = 0;
  LOBYTE(v596) = 0;
  v845 = *(_OWORD *)sub_1800A7BB4(v885, sub_1800ACAB0, v595, v596, v767, v799, v832);
  sub_1800A6F70(v1597, &v845, 0);
  v597 = sub_180037524(a1 + 136);
  LOBYTE(v833) = 0;
  LOBYTE(v800) = 0;
  LOBYTE(v768) = 0;
  LOBYTE(v598) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v886, sub_1800ACA90, v597, v598, v768, v800, v833);
  sub_1800A5908(v1596, &v845, 0);
  v599 = sub_1800A9334(
           (unsigned int)v1647,
           v7,
           (unsigned int)v1596,
           (unsigned int)v1597,
           (__int64)v1598,
           (__int64)v1599,
           (__int64)v1600);
  sub_1800ABF70(a1 + 20656, v599);
  sub_1800AB1D0(v1647);
  sub_1800AB520(v1596);
  sub_1800AB520(v1597);
  sub_1800AB520(v1598);
  sub_1800AB520(v1599);
  sub_1800AB520(v1600);
  sub_18001D80C(v1282, L"MissingExternalFileTimestamp");
  sub_1800B7734(a1, v1282, a1 + 20656);
  sub_180020E60((__int64)v1282);
  sub_1800A9798(v1606, 0);
  sub_1800A9798(v1605, 0);
  v600 = sub_180037524(a1 + 136);
  LOBYTE(v801) = 0;
  LOBYTE(v769) = 0;
  LOBYTE(v601) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v887, sub_1800ACB30, v600, v601, v769, v801, v834);
  sub_1800A5F58(v1604, &v845, 0);
  v602 = sub_180037524(a1 + 136);
  LOBYTE(v835) = 0;
  LOBYTE(v802) = 0;
  LOBYTE(v770) = 0;
  LOBYTE(v603) = 0;
  v845 = *(_OWORD *)sub_1800A7B9C(v888, sub_1800ACB10, v602, v603, v770, v802, v835);
  sub_1800A6F20(v1603, &v845, 0);
  v604 = sub_180037524(a1 + 136);
  LOBYTE(v836) = 0;
  LOBYTE(v803) = 0;
  LOBYTE(v771) = 0;
  LOBYTE(v605) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v889, sub_1800ACAF0, v604, v605, v771, v803, v836);
  sub_1800A519C(v1602, &v845, 0);
  v606 = sub_1800A8B48(
           (unsigned int)v1648,
           v7,
           (unsigned int)v1602,
           (unsigned int)v1603,
           (__int64)v1604,
           (__int64)v1605,
           (__int64)v1606);
  sub_1800ABF70(a1 + 20928, v606);
  sub_1800AAD5C(v1648);
  sub_1800AB520(v1602);
  sub_1800AB520(v1603);
  sub_1800AB520(v1604);
  sub_1800AB520(v1605);
  sub_1800AB520(v1606);
  sub_18001D80C(v1283, L"MissingExternalFileCount");
  sub_1800B7734(a1, v1283, a1 + 20928);
  sub_180020E60((__int64)v1283);
  sub_18001D80C(v1262, L"FirstTimeLogon");
  sub_1800A48A8(v1611, 0, 0);
  sub_1800A9798(v1610, 0);
  sub_1800A9798(v1609, 0);
  v607 = sub_18001D71C((__int64)v933, (__int64)v1262);
  v608 = sub_180037524(a1 + 136);
  LOBYTE(v609) = 0;
  v610 = sub_1800A7ADC((unsigned int)&v1105, (unsigned int)sub_1800ACDF0, v608, v609, v607);
  sub_1800A6D60(v1608, v610, 0);
  v611 = sub_18001D71C((__int64)v934, (__int64)v1262);
  v612 = sub_180037524(a1 + 136);
  LOBYTE(v613) = 0;
  v614 = sub_1800A77C4((unsigned int)&v1106, (unsigned int)sub_1800ACD30, v612, v613, v611);
  sub_1800A5B68(v1607, v614, 0);
  v615 = sub_1800A8910(
           (unsigned int)v1698,
           (unsigned int)v1262,
           v7,
           (unsigned int)v1607,
           (__int64)v1608,
           (__int64)v1609,
           (__int64)v1610,
           (__int64)v1611);
  v616 = a1;
  sub_1800ABA8C(a1 + 21200, v615);
  sub_1800AABD8(v1698);
  sub_1800AB520(v1607);
  sub_1800AB520(v1608);
  sub_1800AB520(v1609);
  sub_1800AB520(v1610);
  sub_1800AB520(v1611);
  sub_1800B783C(a1, v1262, a1 + 21200);
  sub_180020E60((__int64)v1262);
  sub_18001D80C(v1241, L"WaitForWallpaperOverwriteTime");
  sub_1800A4DA8(v1616, 0, 0);
  sub_1800A9798(v1615, 0);
  v617 = sub_18001D71C((__int64)v935, (__int64)v1241);
  v618 = sub_180037524(a1 + 136);
  LOBYTE(v619) = 0;
  v620 = sub_1800A725C((unsigned int)&v1107, (unsigned int)sub_1800ACE10, v618, v619, v617);
  sub_1800A6134(v1614, v620, 0);
  v621 = sub_18001D71C((__int64)v936, (__int64)v1241);
  v622 = sub_180037524(a1 + 136);
  LOBYTE(v623) = 0;
  v624 = sub_1800A7884((unsigned int)&v1108, (unsigned int)sub_1800ACDB0, v622, v623, v621);
  sub_1800A6570(v1613, v624, 0);
  v625 = sub_18001D71C((__int64)v937, (__int64)v1241);
  v626 = sub_180037524(a1 + 136);
  LOBYTE(v627) = 0;
  v628 = sub_1800A7360((unsigned int)&v1109, (unsigned int)sub_1800ACCF0, v626, v627, v625);
  sub_1800A5378(v1612, v628, 0);
  v629 = sub_1800A7E30(
           (unsigned int)v1699,
           (unsigned int)v1241,
           (int)a1 + 176,
           (unsigned int)v1612,
           (__int64)v1613,
           (__int64)v1614,
           (__int64)v1615,
           (__int64)v1616);
  sub_1800ABA8C(a1 + 16528, v629);
  sub_1800AABD8(v1699);
  sub_1800AB520(v1612);
  sub_1800AB520(v1613);
  sub_1800AB520(v1614);
  sub_1800AB520(v1615);
  sub_1800AB520(v1616);
  sub_1800B783C(v616, v1241, v616 + 16528);
  sub_180020E60((__int64)v1241);
  sub_18001D80C(v1242, L"SetWallpaperRetries");
  sub_1800A4728(v1621, 0, 0);
  sub_1800A9798(v1620, 0);
  v630 = sub_18001D71C((__int64)v938, (__int64)v1242);
  v631 = sub_180037524(a1 + 136);
  LOBYTE(v632) = 0;
  v633 = sub_1800A725C((unsigned int)&v1110, (unsigned int)sub_1800ACE10, v631, v632, v630);
  sub_1800A6134(v1619, v633, 0);
  v634 = sub_18001D71C((__int64)v939, (__int64)v1242);
  v635 = sub_180037524(a1 + 136);
  LOBYTE(v636) = 0;
  v637 = sub_1800A7884((unsigned int)&v1111, (unsigned int)sub_1800ACDB0, v635, v636, v634);
  sub_1800A6570(v1618, v637, 0);
  v638 = sub_18001D71C((__int64)v940, (__int64)v1242);
  v639 = sub_180037524(a1 + 136);
  LOBYTE(v640) = 0;
  v641 = sub_1800A7360((unsigned int)&v1112, (unsigned int)sub_1800ACCF0, v639, v640, v638);
  sub_1800A5378(v1617, v641, 0);
  v642 = sub_1800A7E30(
           (unsigned int)v1700,
           (unsigned int)v1242,
           (int)a1 + 176,
           (unsigned int)v1617,
           (__int64)v1618,
           (__int64)v1619,
           (__int64)v1620,
           (__int64)v1621);
  sub_1800ABA8C(a1 + 16832, v642);
  sub_1800AABD8(v1700);
  sub_1800AB520(v1617);
  sub_1800AB520(v1618);
  sub_1800AB520(v1619);
  sub_1800AB520(v1620);
  sub_1800AB520(v1621);
  sub_1800B783C(v616, v1242, v616 + 16832);
  sub_180020E60((__int64)v1242);
  sub_18001D80C(v1243, L"SyncProviderPingEnabled");
  sub_1800A4C68(v1626, 0, 0);
  sub_1800A9798(v1625, 0);
  v643 = sub_18001D71C((__int64)v941, (__int64)v1243);
  v644 = sub_180037524(a1 + 136);
  LOBYTE(v645) = 0;
  v646 = sub_1800A725C((unsigned int)&v1113, (unsigned int)sub_1800ACE10, v644, v645, v643);
  sub_1800A6134(v1624, v646, 0);
  v647 = sub_18001D71C((__int64)v942, (__int64)v1243);
  v648 = sub_180037524(a1 + 136);
  LOBYTE(v649) = 0;
  v650 = sub_1800A7ADC((unsigned int)&v1114, (unsigned int)sub_1800ACDF0, v648, v649, v647);
  sub_1800A6D60(v1623, v650, 0);
  v651 = sub_18001D71C((__int64)v943, (__int64)v1243);
  v652 = sub_180037524(a1 + 136);
  LOBYTE(v653) = 0;
  v654 = sub_1800A77C4((unsigned int)&v1115, (unsigned int)sub_1800ACD30, v652, v653, v651);
  sub_1800A5B68(v1622, v654, 0);
  v655 = sub_1800A8910(
           (unsigned int)v1701,
           (unsigned int)v1243,
           (int)a1 + 176,
           (unsigned int)v1622,
           (__int64)v1623,
           (__int64)v1624,
           (__int64)v1625,
           (__int64)v1626);
  sub_1800ABA8C(a1 + 5104, v655);
  sub_1800AABD8(v1701);
  sub_1800AB520(v1622);
  sub_1800AB520(v1623);
  sub_1800AB520(v1624);
  sub_1800AB520(v1625);
  sub_1800AB520(v1626);
  sub_1800B783C(v616, v1243, v616 + 5104);
  sub_180020E60((__int64)v1243);
  sub_18001D80C(v1268, L"LkgFrequencyThreshold");
  sub_1800A4828(v1631, 0, 0);
  sub_1800A9798(v1630, 0);
  sub_1800A9798(v1629, 0);
  sub_1800A9798(v1628, 0);
  v656 = sub_18001D71C((__int64)v944, (__int64)v1268);
  v657 = sub_180037524(a1 + 136);
  LOBYTE(v658) = 0;
  v659 = sub_1800A7360((unsigned int)&v1116, (unsigned int)sub_1800ACCF0, v657, v658, v656);
  sub_1800A5378(v1627, v659, 0);
  v660 = sub_1800A7E30(
           (unsigned int)v1702,
           (unsigned int)v1268,
           (int)a1 + 176,
           (unsigned int)v1627,
           (__int64)v1628,
           (__int64)v1629,
           (__int64)v1630,
           (__int64)v1631);
  sub_1800ABA8C(a1 + 17440, v660);
  sub_1800AABD8(v1702);
  sub_1800AB520(v1627);
  sub_1800AB520(v1628);
  sub_1800AB520(v1629);
  sub_1800AB520(v1630);
  sub_1800AB520(v1631);
  sub_1800B783C(v616, v1268, v616 + 17440);
  sub_180020E60((__int64)v1268);
  sub_18001D80C(v1269, L"LkgStableExportsThreshold");
  sub_1800A4F28(v1430, 0, 0);
  sub_1800A9798(v1429, 0);
  sub_1800A9798(v1428, 0);
  sub_1800A9798(v1633, 0);
  v661 = sub_18001D71C((__int64)v945, (__int64)v1269);
  v662 = sub_180037524(a1 + 136);
  LOBYTE(v663) = 0;
  v664 = sub_1800A7360((unsigned int)&v1117, (unsigned int)sub_1800ACCF0, v662, v663, v661);
  sub_1800A5378(v1632, v664, 0);
  v665 = sub_1800A7E30(
           (unsigned int)v1703,
           (unsigned int)v1269,
           (int)a1 + 176,
           (unsigned int)v1632,
           (__int64)v1633,
           (__int64)v1428,
           (__int64)v1429,
           (__int64)v1430);
  sub_1800ABA8C(a1 + 17744, v665);
  sub_1800AABD8(v1703);
  sub_1800AB520(v1632);
  sub_1800AB520(v1633);
  sub_1800AB520(v1428);
  sub_1800AB520(v1429);
  sub_1800AB520(v1430);
  sub_1800B783C(v616, v1269, v616 + 17744);
  sub_180020E60((__int64)v1269);
  sub_18001D80C(v1244, L"VolatilePooledVdiMode");
  sub_1800A4DE8(v1435, 0, 0);
  sub_1800A9798(v1434, 0);
  v666 = sub_18001D71C((__int64)v946, (__int64)v1244);
  v667 = sub_180037524(a1 + 136);
  LOBYTE(v668) = 0;
  v669 = sub_1800A725C((unsigned int)&v1118, (unsigned int)sub_1800ACE10, v667, v668, v666);
  sub_1800A6134(v1433, v669, 0);
  v670 = sub_18001D71C((__int64)v947, (__int64)v1244);
  v671 = sub_180037524(a1 + 136);
  LOBYTE(v672) = 0;
  v673 = sub_1800A7884((unsigned int)&v1119, (unsigned int)sub_1800ACDB0, v671, v672, v670);
  sub_1800A6570(v1432, v673, 0);
  v674 = sub_18001D71C((__int64)v948, (__int64)v1244);
  v675 = sub_180037524(a1 + 136);
  LOBYTE(v676) = 0;
  v677 = sub_1800A7360((unsigned int)&v1120, (unsigned int)sub_1800ACCF0, v675, v676, v674);
  sub_1800A5378(v1431, v677, 0);
  v678 = sub_1800A7E30(
           (unsigned int)v1704,
           (unsigned int)v1244,
           (int)a1 + 176,
           (unsigned int)v1431,
           (__int64)v1432,
           (__int64)v1433,
           (__int64)v1434,
           (__int64)v1435);
  sub_1800ABA8C(a1 + 18048, v678);
  sub_1800AABD8(v1704);
  sub_1800AB520(v1431);
  sub_1800AB520(v1432);
  sub_1800AB520(v1433);
  sub_1800AB520(v1434);
  sub_1800AB520(v1435);
  sub_1800B783C(v616, v1244, v616 + 18048);
  sub_180020E60((__int64)v1244);
  sub_18001D80C(v1245, L"MaxPackageSettingSizeInBytes");
  sub_1800A9798(v1440, 0);
  sub_1800A9798(v1439, 0);
  v679 = sub_18001D71C((__int64)v949, (__int64)v1245);
  v680 = sub_180037524(a1 + 136);
  LOBYTE(v681) = 0;
  v682 = sub_1800A725C((unsigned int)&v1121, (unsigned int)sub_1800ACE10, v680, v681, v679);
  sub_1800A6134(v1438, v682, 0);
  v683 = sub_18001D71C((__int64)v950, (__int64)v1245);
  v684 = sub_180037524(a1 + 136);
  LOBYTE(v685) = 0;
  v686 = sub_1800A7884((unsigned int)&v1122, (unsigned int)sub_1800ACDB0, v684, v685, v683);
  sub_1800A6570(v1437, v686, 0);
  v687 = sub_18001D71C((__int64)v951, (__int64)v1245);
  v688 = sub_180037524(a1 + 136);
  LOBYTE(v689) = 0;
  v690 = sub_1800A7360((unsigned int)&v1123, (unsigned int)sub_1800ACCF0, v688, v689, v687);
  sub_1800A5378(v1436, v690, 0);
  v691 = sub_1800A7E30(
           (unsigned int)v1705,
           (unsigned int)v1245,
           (int)a1 + 176,
           (unsigned int)v1436,
           (__int64)v1437,
           (__int64)v1438,
           (__int64)v1439,
           (__int64)v1440);
  sub_1800ABA8C(a1 + 8448, v691);
  sub_1800AABD8(v1705);
  sub_1800AB520(v1436);
  sub_1800AB520(v1437);
  sub_1800AB520(v1438);
  sub_1800AB520(v1439);
  sub_1800AB520(v1440);
  sub_1800B783C(v616, v1245, v616 + 8448);
  sub_180020E60((__int64)v1245);
  sub_18001D80C(v1274, L"ProfileList");
  sub_1800A9798(v1445, 0);
  sub_1800A9798(v1444, 0);
  sub_1800A9798(v1443, 0);
  sub_1800A9798(v1442, 0);
  v692 = sub_180037524(a1 + 136);
  LOBYTE(v804) = 0;
  LOBYTE(v772) = 0;
  LOBYTE(v693) = 0;
  v845 = *(_OWORD *)sub_1800A7230(v890, sub_1800ACB50, v692, v693, v772, v804);
  sub_1800A5F08(v1441, &v845, 0);
  v694 = sub_1800A84A0(
           (unsigned int)v1706,
           (unsigned int)v1274,
           (int)a1 + 176,
           (unsigned int)v1441,
           (__int64)v1442,
           (__int64)v1443,
           (__int64)v1444,
           (__int64)v1445);
  sub_1800ABA8C(a1 + 8752, v694);
  sub_1800AABD8(v1706);
  sub_1800AB520(v1441);
  sub_1800AB520(v1442);
  sub_1800AB520(v1443);
  sub_1800AB520(v1444);
  sub_1800AB520(v1445);
  sub_1800B783C(v616, v1274, v616 + 8752);
  sub_180020E60((__int64)v1274);
  sub_18001D80C(v1275, L"Profile");
  v695 = sub_180037524(a1 + 136);
  LOBYTE(v805) = 0;
  LOBYTE(v773) = 0;
  LOBYTE(v696) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v891, sub_1800ACB90, v695, v696, v773, v805, v837);
  sub_1800A5F58(v1451, &v845, 0);
  sub_1800A9798(v1450, 0);
  sub_1800A9798(v1449, 0);
  sub_1800A9798(v1448, 0);
  v697 = sub_180037524(a1 + 136);
  LOBYTE(v806) = 0;
  LOBYTE(v774) = 0;
  LOBYTE(v698) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v892, sub_1800ACB70, v697, v698, v774, v806, v838);
  sub_1800A5F58(v1447, &v845, 0);
  sub_1800A9798(v1446, 0);
  v699 = sub_1800A8068(
           (unsigned int)v1707,
           (unsigned int)v1275,
           (int)a1 + 176,
           (unsigned int)v1446,
           (__int64)v1447,
           (__int64)v1448,
           (__int64)v1449,
           (__int64)v1450,
           (__int64)v1451);
  sub_1800ABCC0(a1 + 9056, v699);
  sub_1800AABD8(v1707);
  sub_1800AB520(v1446);
  sub_1800AB520(v1447);
  sub_1800AB520(v1448);
  sub_1800AB520(v1449);
  sub_1800AB520(v1450);
  sub_1800AB520(v1451);
  sub_1800B783C(v616, v1275, v616 + 9056);
  sub_180020E60((__int64)v1275);
  sub_1800A9798(v1456, 0);
  sub_1800A9798(v1455, 0);
  sub_1800A9798(v1454, 0);
  sub_1800A9798(v1453, 0);
  v700 = sub_180037524(a1 + 136);
  LOBYTE(v839) = 0;
  LOBYTE(v807) = 0;
  LOBYTE(v775) = 0;
  LOBYTE(v701) = 0;
  v845 = *(_OWORD *)sub_1800A7614(v893, sub_1800ACBB0, v700, v701, v775, v807, v839);
  sub_1800A6344(v1452, &v845, 0);
  v702 = sub_1800A9150(
           (unsigned int)v1649,
           (int)a1 + 176,
           (unsigned int)v1452,
           (unsigned int)v1453,
           (__int64)v1454,
           (__int64)v1455,
           (__int64)v1456);
  sub_1800ABF70(a1 + 9360, v702);
  sub_1800AB054(v1649);
  sub_1800AB520(v1452);
  sub_1800AB520(v1453);
  sub_1800AB520(v1454);
  sub_1800AB520(v1455);
  sub_1800AB520(v1456);
  sub_18001D80C(v1286, L"ProfileTemplateList");
  sub_1800B7734(v616, v1286, v616 + 9360);
  sub_180020E60((__int64)v1286);
  v703 = sub_180037524(a1 + 136);
  LOBYTE(v840) = 0;
  LOBYTE(v808) = 0;
  LOBYTE(v776) = 0;
  LOBYTE(v704) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v894, sub_1800ACBF0, v703, v704, v776, v808, v840);
  sub_1800A6730(v1462, &v845, 0);
  sub_1800A9798(v1461, 0);
  sub_1800A9798(v1460, 0);
  sub_1800A9798(v1459, 0);
  v705 = sub_180037524(a1 + 136);
  LOBYTE(v841) = 0;
  LOBYTE(v809) = 0;
  LOBYTE(v777) = 0;
  LOBYTE(v706) = 0;
  v845 = *(_OWORD *)sub_1800A7248(v895, sub_1800ACBD0, v705, v706, v777, v809, v841);
  sub_1800A6730(v1458, &v845, 0);
  sub_1800A9798(v1457, 0);
  v707 = sub_1800A8D70(
           (unsigned int)v1650,
           (int)a1 + 176,
           (unsigned int)v1457,
           (unsigned int)v1458,
           (__int64)v1459,
           (__int64)v1460,
           (__int64)v1461,
           (__int64)v1462);
  sub_1800ABF70(a1 + 9632, v707);
  sub_1800AAED8(v1650);
  sub_1800AB520(v1457);
  sub_1800AB520(v1458);
  sub_1800AB520(v1459);
  sub_1800AB520(v1460);
  sub_1800AB520(v1461);
  sub_1800AB520(v1462);
  sub_18001D80C(v1284, L"ProfileTemplateAssociation");
  sub_1800B7734(v616, v1284, v616 + 9632);
  sub_180020E60((__int64)v1284);
  sub_1800A9798(v1467, 0);
  sub_1800A9798(v1466, 0);
  sub_1800A9798(v1465, 0);
  sub_1800A9798(v1464, 0);
  v708 = sub_180037524(a1 + 136);
  LOBYTE(v842) = 0;
  LOBYTE(v810) = 0;
  LOBYTE(v778) = 0;
  LOBYTE(v709) = 0;
  v845 = *(_OWORD *)sub_1800A7438(v896, sub_1800ACC10, v708, v709, v778, v810, v842);
  sub_1800A62F4(v1463, &v845, 0);
  v710 = sub_1800A8F6C(
           (unsigned int)v1651,
           (int)a1 + 176,
           (unsigned int)v1463,
           (unsigned int)v1464,
           (__int64)v1465,
           (__int64)v1466,
           (__int64)v1467);
  sub_1800ABF70(a1 + 9904, v710);
  sub_1800AAED8(v1651);
  sub_1800AB520(v1463);
  sub_1800AB520(v1464);
  sub_1800AB520(v1465);
  sub_1800AB520(v1466);
  sub_1800AB520(v1467);
  sub_18001D80C(v1285, L"TemplateProfile");
  sub_1800B7734(v616, v1285, v616 + 9904);
  sub_180020E60((__int64)v1285);
  sub_18001D80C(v1246, L"ProfileWin8AppAssociation");
  sub_1800A9798(v1472, 0);
  sub_1800A9798(v1471, 0);
  v711 = sub_18001D71C((__int64)v952, (__int64)v1246);
  v712 = sub_180037524(a1 + 136);
  LOBYTE(v713) = 0;
  v714 = sub_1800A725C((unsigned int)&v1124, (unsigned int)sub_1800ACC70, v712, v713, v711);
  sub_1800A6134(v1470, v714, 0);
  v715 = sub_18001D71C((__int64)v953, (__int64)v1246);
  v716 = sub_180037524(a1 + 136);
  LOBYTE(v717) = 0;
  v718 = sub_1800A7450((unsigned int)&v1125, (unsigned int)sub_1800ACC50, v716, v717, v715);
  sub_1800A6780(v1469, v718, 0);
  v719 = sub_18001D71C((__int64)v954, (__int64)v1246);
  v720 = sub_180037524(a1 + 136);
  LOBYTE(v721) = 0;
  v722 = sub_1800A7450((unsigned int)&v1126, (unsigned int)sub_1800ACC30, v720, v721, v719);
  sub_1800A5588(v1468, v722, 0);
  v723 = sub_1800A8268(
           (unsigned int)v1708,
           (unsigned int)v1246,
           (int)a1 + 176,
           (unsigned int)v1468,
           (__int64)v1469,
           (__int64)v1470,
           (__int64)v1471,
           (__int64)v1472);
  sub_1800ABCC0(a1 + 10176, v723);
  sub_1800AABD8(v1708);
  sub_1800AB520(v1468);
  sub_1800AB520(v1469);
  sub_1800AB520(v1470);
  sub_1800AB520(v1471);
  sub_1800AB520(v1472);
  sub_1800B783C(v616, v1246, v616 + 10176);
  sub_180020E60((__int64)v1246);
  sub_18001D80C(v1247, L"VdiCollectionName");
  sub_1800A4BE8(v1477, 0, 0);
  sub_1800A9798(v1476, 0);
  v724 = sub_18001D71C((__int64)v955, (__int64)v1247);
  v725 = sub_180037524(a1 + 136);
  LOBYTE(v726) = 0;
  v727 = sub_1800A725C((unsigned int)&v1127, (unsigned int)sub_1800ACE10, v725, v726, v724);
  sub_1800A6134(v1475, v727, 0);
  v728 = sub_18001D71C((__int64)v956, (__int64)v1247);
  v729 = sub_180037524(a1 + 136);
  LOBYTE(v730) = 0;
  v731 = sub_1800A7450((unsigned int)&v1128, (unsigned int)sub_1800ACD50, v729, v730, v728);
  sub_1800A6780(v1474, v731, 0);
  v732 = sub_18001D71C((__int64)v958, (__int64)v1247);
  v733 = sub_180037524(a1 + 136);
  LOBYTE(v843) = 0;
  LOBYTE(v811) = 0;
  LOBYTE(v734) = 0;
  v735 = sub_1800A7524((unsigned int)&v1208, (unsigned int)sub_1800ACC90, v733, v734, v732, v811, v843, 1);
  sub_1800A5D28(v1473, v735, 0);
  v736 = sub_1800A8268(
           (unsigned int)v1709,
           (unsigned int)v1247,
           (int)a1 + 176,
           (unsigned int)v1473,
           (__int64)v1474,
           (__int64)v1475,
           (__int64)v1476,
           (__int64)v1477);
  sub_1800ABCC0(a1 + 10480, v736);
  sub_1800AABD8(v1709);
  sub_1800AB520(v1473);
  sub_1800AB520(v1474);
  sub_1800AB520(v1475);
  sub_1800AB520(v1476);
  sub_1800AB520(v1477);
  sub_1800B783C(v616, v1247, v616 + 10480);
  sub_180020E60((__int64)v1247);
  sub_18001D80C(v1248, L"LogOffWaitInterval");
  sub_1800A4968(v1482, 0, 0);
  sub_1800A9798(v1481, 0);
  v737 = sub_18001D71C((__int64)v959, (__int64)v1248);
  v738 = sub_180037524(a1 + 136);
  LOBYTE(v739) = 0;
  v740 = sub_1800A725C((unsigned int)&v1129, (unsigned int)sub_1800ACE10, v738, v739, v737);
  sub_1800A6134(v1480, v740, 0);
  v741 = sub_18001D71C((__int64)v960, (__int64)v1248);
  v742 = sub_180037524(a1 + 136);
  LOBYTE(v743) = 0;
  v744 = sub_1800A7884((unsigned int)&v1130, (unsigned int)sub_1800ACDB0, v742, v743, v741);
  sub_1800A6570(v1479, v744, 0);
  v745 = sub_18001D71C((__int64)v961, (__int64)v1248);
  v746 = sub_180037524(a1 + 136);
  LOBYTE(v747) = 0;
  v748 = sub_1800A7360((unsigned int)&v1131, (unsigned int)sub_1800ACCF0, v746, v747, v745);
  sub_1800A5378(v1478, v748, 0);
  v749 = sub_1800A7E30(
           (unsigned int)v1710,
           (unsigned int)v1248,
           (int)a1 + 176,
           (unsigned int)v1478,
           (__int64)v1479,
           (__int64)v1480,
           (__int64)v1481,
           (__int64)v1482);
  sub_1800ABA8C(a1 + 18352, v749);
  sub_1800AABD8(v1710);
  sub_1800AB520(v1478);
  sub_1800AB520(v1479);
  sub_1800AB520(v1480);
  sub_1800AB520(v1481);
  sub_1800AB520(v1482);
  sub_1800B783C(v616, v1248, v616 + 18352);
  return sub_180020E60((__int64)v1248);
}

```

## disassembly

```asm
0x1800adc0c  push    rbp
0x1800adc0e  push    rbx
0x1800adc0f  push    rsi
0x1800adc10  push    rdi
0x1800adc11  push    r12
0x1800adc13  push    r13
0x1800adc15  push    r14
0x1800adc17  push    r15
0x1800adc19  lea     rbp, [rsp-0C588h]
0x1800adc21  mov     eax, 0C688h
0x1800adc26  call    __alloca_probe
0x1800adc2b  sub     rsp, rax
0x1800adc2e  mov     rax, cs:__security_cookie
0x1800adc35  xor     rax, rsp
0x1800adc38  mov     [rbp+0C5C0h+var_50], rax
0x1800adc3f  mov     rsi, rcx
0x1800adc42  mov     [rsp+0C6C0h+var_C670], rcx
0x1800adc47  mov     dword ptr [rbp+0C5C0h+var_C638], 0
0x1800adc4e  mov     [rbp+0C5C0h+var_C630], 5
0x1800adc55  lea     rcx, [rbp+0C5C0h+var_C510]
0x1800adc5c  call    sub_1800A9740
0x1800adc61  mov     dword ptr [rbp+0C5C0h+var_C638], 1
0x1800adc68  lea     rdx, [rbp+0C5C0h+var_C630]
0x1800adc6c  lea     rcx, [rbp+0C5C0h+var_C510]
0x1800adc73  call    sub_1800A70D4
0x1800adc78  mov     r9b, [rbp+0C5C0h+var_C640]
0x1800adc7c  mov     r8, cs:qword_1801B8AD8
0x1800adc83  lea     rdx, [rbp+0C5C0h+var_C550]
0x1800adc87  lea     rcx, [rbp+0C5C0h+var_C510]
0x1800adc8e  call    sub_1800A7BFC
0x1800adc93  lea     rcx, [rsi+98h]
0x1800adc9a  lea     rdx, [rbp+0C5C0h+var_C550]
0x1800adc9e  call    sub_1800AC4E4
0x1800adca3  lea     rcx, [rbp+0C5C0h+var_C550]
0x1800adca7  call    sub_1800212AC
0x1800adcac  mov     dword ptr [rbp+0C5C0h+var_C638], 6
0x1800adcb3  lea     rcx, [rbp+0C5C0h+var_C510]
0x1800adcba  call    sub_18005F7F0
0x1800adcbf  mov     [rbp+0C5C0h+var_C62C], 0
0x1800adcc6  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800adcca  call    sub_1800A9740
0x1800adccf  mov     dword ptr [rbp+0C5C0h+var_C638], 0Eh
0x1800adcd6  lea     rdx, [rbp+0C5C0h+var_C62C]
0x1800adcda  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800adcde  call    sub_1800A70D4
0x1800adce3  mov     [rbp+0C5C0h+var_C628], 1
0x1800adcea  lea     rdx, [rbp+0C5C0h+var_C628]
0x1800adcee  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800adcf2  call    sub_1800A70D4
0x1800adcf7  mov     [rbp+0C5C0h+var_C624], 2
0x1800adcfe  lea     rdx, [rbp+0C5C0h+var_C624]
0x1800add02  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800add06  call    sub_1800A70D4
0x1800add0b  mov     [rbp+0C5C0h+var_C620], 3
0x1800add12  lea     rdx, [rbp+0C5C0h+var_C620]
0x1800add16  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800add1a  call    sub_1800A70D4
0x1800add1f  mov     r9b, [rbp+0C5C0h+var_C640]
0x1800add23  mov     r8, cs:qword_1801B8AD8
0x1800add2a  lea     rdx, [rbp+0C5C0h+var_C5B0]
0x1800add2e  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800add32  call    sub_1800A7BFC
0x1800add37  lea     rcx, [rsi+0B0h]
0x1800add3e  lea     rdx, [rbp+0C5C0h+var_C5B0]
0x1800add42  call    sub_1800AC4E4
0x1800add47  lea     rcx, [rbp+0C5C0h+var_C5B0]
0x1800add4b  call    sub_1800212AC
0x1800add50  mov     dword ptr [rbp+0C5C0h+var_C638], 36h ; '6'
0x1800add57  lea     rcx, [rbp+0C5C0h+var_C608]
0x1800add5b  call    sub_18005F7F0
0x1800add60  mov     [rbp+0C5C0h+var_C61C], 1
0x1800add67  lea     rcx, [rbp+0C5C0h+var_C538]
0x1800add6e  call    sub_1800A9740
0x1800add73  mov     dword ptr [rbp+0C5C0h+var_C638], 76h ; 'v'
0x1800add7a  lea     rdx, [rbp+0C5C0h+var_C61C]
0x1800add7e  lea     rcx, [rbp+0C5C0h+var_C538]
0x1800add85  call    sub_1800A70D4
0x1800add8a  mov     [rbp+0C5C0h+var_C618], 3
0x1800add91  lea     rdx, [rbp+0C5C0h+var_C618]
0x1800add95  lea     rcx, [rbp+0C5C0h+var_C538]
0x1800add9c  call    sub_1800A70D4
0x1800adda1  mov     r9b, [rbp+0C5C0h+var_C640]
0x1800adda5  mov     r8, cs:qword_1801B8AD8
0x1800addac  lea     rdx, [rbp+0C5C0h+var_C598]
0x1800addb0  lea     rcx, [rbp+0C5C0h+var_C538]
0x1800addb7  call    sub_1800A7BFC
0x1800addbc  lea     r15, [rsi+0C8h]
0x1800addc3  lea     rdx, [rbp+0C5C0h+var_C598]
0x1800addc7  mov     rcx, r15
0x1800addca  call    sub_1800AC4E4
0x1800addcf  lea     rcx, [rbp+0C5C0h+var_C598]
0x1800addd3  call    sub_1800212AC
0x1800addd8  mov     dword ptr [rbp+0C5C0h+var_C638], 1B6h
0x1800adddf  lea     rcx, [rbp+0C5C0h+var_C538]
0x1800adde6  call    sub_18005F7F0
0x1800addeb  mov     [rbp+0C5C0h+var_C614], 2
0x1800addf2  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x1800addf9  call    sub_1800A9740
0x1800addfe  mov     dword ptr [rbp+0C5C0h+var_C638], 3B6h
0x1800ade05  lea     rdx, [rbp+0C5C0h+var_C614]
0x1800ade09  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x1800ade10  call    sub_1800A70D4
0x1800ade15  mov     r9b, [rbp+0C5C0h+var_C640]
0x1800ade19  mov     r8, cs:qword_1801B8AD8
0x1800ade20  lea     rdx, [rbp+0C5C0h+var_C580]
0x1800ade24  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x1800ade2b  call    sub_1800A7BFC
0x1800ade30  lea     r13, [rsi+0E0h]
0x1800ade37  lea     rdx, [rbp+0C5C0h+var_C580]
0x1800ade3b  mov     rcx, r13
0x1800ade3e  call    sub_1800AC4E4
0x1800ade43  lea     rcx, [rbp+0C5C0h+var_C580]
0x1800ade47  call    sub_1800212AC
0x1800ade4c  mov     dword ptr [rbp+0C5C0h+var_C638], 0DB6h
0x1800ade53  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x1800ade5a  call    sub_18005F7F0
0x1800ade5f  mov     [rbp+0C5C0h+var_C610], 3
0x1800ade66  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x1800ade6d  call    sub_1800A9740
0x1800ade72  mov     dword ptr [rbp+0C5C0h+var_C638], 1DB6h
0x1800ade79  lea     rdx, [rbp+0C5C0h+var_C610]
0x1800ade7d  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x1800ade84  call    sub_1800A70D4
0x1800ade89  mov     r9b, [rbp+0C5C0h+var_C640]
0x1800ade8d  mov     r8, cs:qword_1801B8AD8
0x1800ade94  lea     rdx, [rbp+0C5C0h+var_C568]
0x1800ade98  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x1800ade9f  call    sub_1800A7BFC
0x1800adea4  lea     r12, [rsi+0F8h]
0x1800adeab  lea     rdx, [rbp+0C5C0h+var_C568]
0x1800adeaf  mov     rcx, r12
0x1800adeb2  call    sub_1800AC4E4
0x1800adeb7  lea     rcx, [rbp+0C5C0h+var_C568]
0x1800adebb  call    sub_1800212AC
0x1800adec0  nop
0x1800adec1  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x1800adec8  call    sub_18005F7F0
0x1800adecd  lea     rdx, aMaxpackagesize; "MaxPackageSizeInBytes"
0x1800aded4  lea     rcx, [rbp+0C5C0h+var_8DB8]
0x1800adedb  call    sub_18001D80C
0x1800adee0  nop
0x1800adee1  xorps   xmm0, xmm0
0x1800adee4  xor     eax, eax
0x1800adee6  movups  [rbp+0C5C0h+var_8AF0], xmm0
0x1800adeed  movups  [rbp+0C5C0h+var_8AE0], xmm0
0x1800adef4  mov     [rbp+0C5C0h+var_8AD0], rax
0x1800adefb  mov     qword ptr [rbp+0C5C0h+var_8AF0], rax
0x1800adf02  movups  [rbp+0C5C0h+var_8B18], xmm0
0x1800adf09  movups  [rbp+0C5C0h+var_8B08], xmm0
0x1800adf10  mov     [rbp+0C5C0h+var_8AF8], rax
0x1800adf17  mov     qword ptr [rbp+0C5C0h+var_8B18], rax
0x1800adf1e  mov     dil, cs:byte_180155726
0x1800adf25  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x1800adf2c  lea     rcx, [rbp+0C5C0h+var_BA38]
0x1800adf33  call    sub_18001D71C
0x1800adf38  mov     r14, rax
0x1800adf3b  mov     [rbp+0C5C0h+var_C638], rax
0x1800adf3f  mov     bl, cs:byte_180155726
0x1800adf45  mov     rsi, [rsi+88h]
0x1800adf4c  mov     rdx, rax
0x1800adf4f  lea     rcx, [rbp+0C5C0h+var_C498]
0x1800adf56  call    sub_18001D71C
0x1800adf5b  mov     byte ptr [rsp+0C6C0h+var_C6A0], dil
0x1800adf60  lea     r9, [rbp+0C5C0h+var_C498]
0x1800adf67  mov     r8b, bl
0x1800adf6a  mov     rdx, rsi
0x1800adf6d  lea     rcx, [rbp+0C5C0h+var_5238]
0x1800adf74  call    sub_1800A9864
0x1800adf79  nop
0x1800adf7a  lea     rcx, sub_1800ACE10
0x1800adf81  mov     [rbp+0C5C0h+var_C5E0], rcx
0x1800adf85  mov     rdx, rax
0x1800adf88  lea     rcx, [rbp+0C5C0h+var_C5D8]
0x1800adf8c  call    sub_1800A9838
0x1800adf91  nop
0x1800adf92  lea     rcx, [rbp+0C5C0h+var_5230]
0x1800adf99  call    sub_180028810
0x1800adf9e  nop
0x1800adf9f  mov     rcx, r14
0x1800adfa2  call    sub_180028810
0x1800adfa7  lea     rax, [rbp+0C5C0h+var_C5E0]
0x1800adfab  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x1800adfb0  mov     rax, [rbp+0C5C0h+var_C5E0]
0x1800adfb4  mov     [rbp+0C5C0h+var_C478], rax
0x1800adfbb  lea     rdx, [rbp+0C5C0h+var_C5D8]
0x1800adfbf  lea     rcx, [rbp+0C5C0h+var_C470]
0x1800adfc6  call    sub_1800A9838
0x1800adfcb  xor     r8d, r8d
0x1800adfce  lea     rdx, [rbp+0C5C0h+var_C478]
0x1800adfd5  lea     rcx, [rbp+0C5C0h+var_52A0]
0x1800adfdc  call    sub_1800A5FA8
0x1800adfe1  nop
0x1800adfe2  lea     rcx, [rbp+0C5C0h+var_C5D0]
0x1800adfe6  call    sub_180028810
0x1800adfeb  nop
0x1800adfec  mov     dil, cs:byte_180155726
0x1800adff3  mov     bl, cs:byte_180155726
0x1800adff9  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x1800ae000  lea     rcx, [rbp+0C5C0h+var_BA18]
0x1800ae007  call    sub_18001D71C
0x1800ae00c  mov     byte ptr [rsp+0C6C0h+var_C690], dil
0x1800ae011  mov     byte ptr [rsp+0C6C0h+var_C698], bl
0x1800ae015  mov     [rsp+0C6C0h+var_C6A0], rax
0x1800ae01a  mov     r9b, cs:byte_180155726
0x1800ae021  mov     rsi, [rsp+0C6C0h+var_C670]
0x1800ae026  lea     r14, [rsi+88h]
0x1800ae02d  mov     r8, [r14]
0x1800ae030  lea     rdx, sub_1800ACDB0
0x1800ae037  lea     rcx, [rbp+0C5C0h+var_A160]
0x1800ae03e  call    sub_1800A7884
0x1800ae043  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x1800ae048  mov     rcx, [rax]
0x1800ae04b  mov     [rbp+0C5C0h+var_C418], rcx
0x1800ae052  lea     rbx, [rax+8]
0x1800ae056  mov     rdx, rbx
0x1800ae059  lea     rcx, [rbp+0C5C0h+var_C410]
0x1800ae060  call    sub_1800A9838
0x1800ae065  xor     r8d, r8d
0x1800ae068  lea     rdx, [rbp+0C5C0h+var_C418]
0x1800ae06f  lea     rcx, [rbp+0C5C0h+var_52C8]
0x1800ae076  call    sub_1800A63E4
0x1800ae07b  nop
0x1800ae07c  lea     rcx, [rbx+8]
0x1800ae080  call    sub_180028810
0x1800ae085  nop
0x1800ae086  mov     dil, cs:byte_180155726
0x1800ae08d  mov     bl, cs:byte_180155726
0x1800ae093  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x1800ae09a  lea     rcx, [rbp+0C5C0h+var_B9F8]
0x1800ae0a1  call    sub_18001D71C
0x1800ae0a6  mov     byte ptr [rsp+0C6C0h+var_C690], dil
0x1800ae0ab  mov     byte ptr [rsp+0C6C0h+var_C698], bl
0x1800ae0af  mov     [rsp+0C6C0h+var_C6A0], rax
0x1800ae0b4  mov     r9b, cs:byte_180155726
0x1800ae0bb  mov     r8, [r14]
0x1800ae0be  lea     rdx, sub_1800ACCF0
0x1800ae0c5  lea     rcx, [rbp+0C5C0h+var_A130]
0x1800ae0cc  call    sub_1800A7360
0x1800ae0d1  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x1800ae0d6  mov     rcx, [rax]
0x1800ae0d9  mov     [rbp+0C5C0h+var_C448], rcx
0x1800ae0e0  lea     rbx, [rax+8]
0x1800ae0e4  mov     rdx, rbx
0x1800ae0e7  lea     rcx, [rbp+0C5C0h+var_C440]
0x1800ae0ee  call    sub_1800A9838
0x1800ae0f3  xor     r8d, r8d
0x1800ae0f6  lea     rdx, [rbp+0C5C0h+var_C448]
0x1800ae0fd  lea     rcx, [rbp+0C5C0h+var_52F0]
0x1800ae104  call    sub_1800A51EC
0x1800ae109  nop
0x1800ae10a  lea     rcx, [rbx+8]
0x1800ae10e  call    sub_180028810
0x1800ae113  nop
0x1800ae114  lea     rax, [rbp+0C5C0h+var_8AF0]
0x1800ae11b  mov     [rsp+0C6C0h+var_C688], rax
0x1800ae120  lea     rax, [rbp+0C5C0h+var_8B18]
0x1800ae127  mov     [rsp+0C6C0h+var_C690], rax
0x1800ae12c  lea     rax, [rbp+0C5C0h+var_52A0]
0x1800ae133  mov     [rsp+0C6C0h+var_C698], rax
0x1800ae138  lea     rax, [rbp+0C5C0h+var_52C8]
0x1800ae13f  mov     [rsp+0C6C0h+var_C6A0], rax
0x1800ae144  lea     r9, [rbp+0C5C0h+var_52F0]
0x1800ae14b  lea     r8, [rsi+0B0h]
0x1800ae152  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x1800ae159  lea     rcx, [rbp+0C5C0h+var_4660]
0x1800ae160  call    sub_1800A7E30
0x1800ae165  nop
0x1800ae166  lea     rbx, [rsi+110h]
0x1800ae16d  mov     rdx, rax
0x1800ae170  mov     rcx, rbx
0x1800ae173  call    sub_1800ABA8C
0x1800ae178  nop
0x1800ae179  lea     rcx, [rbp+0C5C0h+var_4660]
0x1800ae180  call    sub_1800AABD8
0x1800ae185  nop
0x1800ae186  lea     rcx, [rbp+0C5C0h+var_52F0]
0x1800ae18d  call    sub_1800AB520
0x1800ae192  nop
0x1800ae193  lea     rcx, [rbp+0C5C0h+var_52C8]
0x1800ae19a  call    sub_1800AB520
0x1800ae19f  nop
0x1800ae1a0  lea     rcx, [rbp+0C5C0h+var_52A0]
0x1800ae1a7  call    sub_1800AB520
0x1800ae1ac  nop
0x1800ae1ad  lea     rcx, [rbp+0C5C0h+var_8B18]
0x1800ae1b4  call    sub_1800AB520
0x1800ae1b9  nop
0x1800ae1ba  lea     rcx, [rbp+0C5C0h+var_8AF0]
0x1800ae1c1  call    sub_1800AB520
0x1800ae1c6  mov     r8, rbx
0x1800ae1c9  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x1800ae1d0  mov     rcx, rsi
0x1800ae1d3  call    sub_1800B783C
0x1800ae1d8  nop
0x1800ae1d9  lea     rcx, [rbp+0C5C0h+var_8DB8]
0x1800ae1e0  call    sub_180020E60
0x1800ae1e5  lea     rdx, aSyncenabled; "SyncEnabled"
0x1800ae1ec  lea     rcx, [rbp+0C5C0h+var_8D98]
0x1800ae1f3  call    sub_18001D80C
0x1800ae1f8  nop
  ... truncated ...
```
