# Uev::Configuration::InitializeSettings(void)

- ea: `0x14007a2cc`
- end: `0x140083deb`
- name: `?InitializeSettings@Configuration@Uev@@AEAAXXZ`
- size: `39711`
- prototype: `void __fastcall(Uev::Configuration *__hidden this)`
- caller_count: `2`
- callee_count: `139`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400754cc`
- `0x14007669c`

## callees

- `0x140003e50`
- `0x14000adb4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000d1d8`
- `0x14000e1c4`
- `0x14001397c`
- `0x140040d0c`
- `0x1400691bc`
- `0x140069224`
- `0x140069440`
- `0x140069a8c`
- `0x1400704d8`
- `0x140070518`
- `0x140070558`
- `0x140070598`
- `0x1400705d8`
- `0x140070618`
- `0x140070658`
- `0x140070698`
- `0x1400706d8`
- `0x140070718`
- `0x140070758`
- `0x140070798`
- `0x1400707d8`
- `0x140070818`
- `0x140070858`
- `0x140070898`
- `0x1400708d8`
- `0x140070918`
- `0x140070958`
- `0x140070998`
- `0x1400709d8`
- `0x140070a18`
- `0x140070a58`
- `0x140070a98`
- `0x140070ad8`
- `0x140070b18`
- `0x140070b58`
- `0x140070b98`
- `0x140070bd8`
- `0x140070c18`
- `0x140070c58`
- `0x140070c98`
- `0x140070cd8`
- `0x140070d18`
- `0x140070d58`
- `0x140070d98`
- `0x140070dd8`
- `0x140070e18`

## string_xrefs

- `0x14007b4ce`: `SettingsTemplateCatalogPath`
- `0x14007b74c`: `SettingsTemplateCatalogPath`
- `0x14007afee`: `SettingsStoragePath`
- `0x14007b270`: `SettingsStoragePath`
- `0x14007c208`: `LastWriterWins`
- `0x14007c01d`: `TemplateEnabled`
- `0x14007d063`: `OverrideMSTemplates`
- `0x14007cbab`: `LastWriterThreshold`
- `0x14007e521`: `CurrentSettingsStoragePath`
- `0x14007e322`: `ADSettingsStoragePath`
- `0x14007f3ca`: `ApplyExplorerCompatFix`
- `0x14007efc5`: `InstallTimestamp`
- `0x14007eda4`: `TemplateRegistrationTimestamp`
- `0x140081127`: `SettingsStoragePathADAttribute`
- `0x14008206d`: `WaitForWallpaperOverwriteTime`
- `0x1400836dc`: `TemplateProfile`
- `0x140083562`: `ProfileTemplateAssociation`
- `0x140083366`: `ProfileTemplateList`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Uev::Configuration::InitializeSettings(Uev::Configuration *this)
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
  Uev::Configuration *v616; // r13
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
  int v750; // [rsp+20h] [rbp-E0h]
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
  int v778; // [rsp+28h] [rbp-D8h]
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
  int v811; // [rsp+30h] [rbp-D0h]
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
  __int128 v844; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v845; // [rsp+70h] [rbp-90h]
  char v846; // [rsp+80h] [rbp-80h]
  __int64 v847; // [rsp+88h] [rbp-78h]
  int v848; // [rsp+90h] [rbp-70h] BYREF
  int v849; // [rsp+94h] [rbp-6Ch] BYREF
  int v850; // [rsp+98h] [rbp-68h] BYREF
  int v851; // [rsp+9Ch] [rbp-64h] BYREF
  int v852; // [rsp+A0h] [rbp-60h] BYREF
  int v853; // [rsp+A4h] [rbp-5Ch] BYREF
  int v854; // [rsp+A8h] [rbp-58h] BYREF
  int v855; // [rsp+ACh] [rbp-54h] BYREF
  int v856; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v857[40]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall *v858)(); // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v859[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v860[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v861[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v862[24]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v863[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v864[24]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v865[24]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v866[40]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v867[40]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v868[40]; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v869[40]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v870[32]; // [rsp+228h] [rbp+128h] BYREF
  __int64 (__fastcall *v871)(); // [rsp+248h] [rbp+148h] BYREF
  _BYTE v872[40]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v873; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v874[40]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v875; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v876[40]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v877[16]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v878[16]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v879[16]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v880[16]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v881[16]; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v882[16]; // [rsp+328h] [rbp+228h] BYREF
  _BYTE v883[16]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v884[16]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v885[16]; // [rsp+358h] [rbp+258h] BYREF
  _BYTE v886[16]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v887[16]; // [rsp+378h] [rbp+278h] BYREF
  _BYTE v888[16]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v889[16]; // [rsp+398h] [rbp+298h] BYREF
  _BYTE v890[16]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v891[16]; // [rsp+3B8h] [rbp+2B8h] BYREF
  _BYTE v892[16]; // [rsp+3C8h] [rbp+2C8h] BYREF
  _BYTE v893[16]; // [rsp+3D8h] [rbp+2D8h] BYREF
  _BYTE v894[16]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v895[16]; // [rsp+3F8h] [rbp+2F8h] BYREF
  _BYTE v896[32]; // [rsp+408h] [rbp+308h] BYREF
  _BYTE v897[32]; // [rsp+428h] [rbp+328h] BYREF
  _BYTE v898[32]; // [rsp+448h] [rbp+348h] BYREF
  _BYTE v899[32]; // [rsp+468h] [rbp+368h] BYREF
  _BYTE v900[32]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v901[32]; // [rsp+4A8h] [rbp+3A8h] BYREF
  _BYTE v902[32]; // [rsp+4C8h] [rbp+3C8h] BYREF
  _BYTE v903[32]; // [rsp+4E8h] [rbp+3E8h] BYREF
  _BYTE v904[32]; // [rsp+508h] [rbp+408h] BYREF
  _BYTE v905[32]; // [rsp+528h] [rbp+428h] BYREF
  _BYTE v906[32]; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v907[32]; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v908[32]; // [rsp+588h] [rbp+488h] BYREF
  _BYTE v909[32]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v910[32]; // [rsp+5C8h] [rbp+4C8h] BYREF
  _BYTE v911[32]; // [rsp+5E8h] [rbp+4E8h] BYREF
  _BYTE v912[32]; // [rsp+608h] [rbp+508h] BYREF
  _BYTE v913[32]; // [rsp+628h] [rbp+528h] BYREF
  _BYTE v914[32]; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v915[32]; // [rsp+668h] [rbp+568h] BYREF
  _BYTE v916[32]; // [rsp+688h] [rbp+588h] BYREF
  _BYTE v917[32]; // [rsp+6A8h] [rbp+5A8h] BYREF
  _BYTE v918[32]; // [rsp+6C8h] [rbp+5C8h] BYREF
  _BYTE v919[32]; // [rsp+6E8h] [rbp+5E8h] BYREF
  _BYTE v920[32]; // [rsp+708h] [rbp+608h] BYREF
  _BYTE v921[32]; // [rsp+728h] [rbp+628h] BYREF
  _BYTE v922[32]; // [rsp+748h] [rbp+648h] BYREF
  _BYTE v923[32]; // [rsp+768h] [rbp+668h] BYREF
  _BYTE v924[32]; // [rsp+788h] [rbp+688h] BYREF
  _BYTE v925[32]; // [rsp+7A8h] [rbp+6A8h] BYREF
  _BYTE v926[32]; // [rsp+7C8h] [rbp+6C8h] BYREF
  _BYTE v927[32]; // [rsp+7E8h] [rbp+6E8h] BYREF
  _BYTE v928[32]; // [rsp+808h] [rbp+708h] BYREF
  _BYTE v929[32]; // [rsp+828h] [rbp+728h] BYREF
  _BYTE v930[32]; // [rsp+848h] [rbp+748h] BYREF
  _BYTE v931[32]; // [rsp+868h] [rbp+768h] BYREF
  _BYTE v932[32]; // [rsp+888h] [rbp+788h] BYREF
  _BYTE v933[32]; // [rsp+8A8h] [rbp+7A8h] BYREF
  _BYTE v934[32]; // [rsp+8C8h] [rbp+7C8h] BYREF
  _BYTE v935[32]; // [rsp+8E8h] [rbp+7E8h] BYREF
  _BYTE v936[32]; // [rsp+908h] [rbp+808h] BYREF
  _BYTE v937[32]; // [rsp+928h] [rbp+828h] BYREF
  _BYTE v938[32]; // [rsp+948h] [rbp+848h] BYREF
  _BYTE v939[32]; // [rsp+968h] [rbp+868h] BYREF
  _BYTE v940[32]; // [rsp+988h] [rbp+888h] BYREF
  _BYTE v941[32]; // [rsp+9A8h] [rbp+8A8h] BYREF
  _BYTE v942[32]; // [rsp+9C8h] [rbp+8C8h] BYREF
  _BYTE v943[32]; // [rsp+9E8h] [rbp+8E8h] BYREF
  _BYTE v944[32]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v945[32]; // [rsp+A28h] [rbp+928h] BYREF
  _BYTE v946[32]; // [rsp+A48h] [rbp+948h] BYREF
  _BYTE v947[32]; // [rsp+A68h] [rbp+968h] BYREF
  _BYTE v948[32]; // [rsp+A88h] [rbp+988h] BYREF
  _BYTE v949[32]; // [rsp+AA8h] [rbp+9A8h] BYREF
  _BYTE v950[32]; // [rsp+AC8h] [rbp+9C8h] BYREF
  _BYTE v951[32]; // [rsp+AE8h] [rbp+9E8h] BYREF
  _BYTE v952[32]; // [rsp+B08h] [rbp+A08h] BYREF
  _BYTE v953[32]; // [rsp+B28h] [rbp+A28h] BYREF
  _BYTE v954[32]; // [rsp+B48h] [rbp+A48h] BYREF
  _BYTE v955[32]; // [rsp+B68h] [rbp+A68h] BYREF
  _BYTE v956[16]; // [rsp+B88h] [rbp+A88h] BYREF
  _BYTE v957[32]; // [rsp+B98h] [rbp+A98h] BYREF
  _BYTE v958[32]; // [rsp+BB8h] [rbp+AB8h] BYREF
  _BYTE v959[32]; // [rsp+BD8h] [rbp+AD8h] BYREF
  _BYTE v960[32]; // [rsp+BF8h] [rbp+AF8h] BYREF
  _BYTE v961[16]; // [rsp+C18h] [rbp+B18h] BYREF
  _BYTE v962[16]; // [rsp+C28h] [rbp+B28h] BYREF
  _BYTE v963[16]; // [rsp+C38h] [rbp+B38h] BYREF
  _BYTE v964[16]; // [rsp+C48h] [rbp+B48h] BYREF
  _BYTE v965[16]; // [rsp+C58h] [rbp+B58h] BYREF
  _BYTE v966[16]; // [rsp+C68h] [rbp+B68h] BYREF
  _BYTE v967[16]; // [rsp+C78h] [rbp+B78h] BYREF
  _BYTE v968[32]; // [rsp+C88h] [rbp+B88h] BYREF
  _BYTE v969[32]; // [rsp+CA8h] [rbp+BA8h] BYREF
  _BYTE v970[32]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v971[32]; // [rsp+CE8h] [rbp+BE8h] BYREF
  _BYTE v972[32]; // [rsp+D08h] [rbp+C08h] BYREF
  _BYTE v973[32]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v974[32]; // [rsp+D48h] [rbp+C48h] BYREF
  _BYTE v975[32]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v976[32]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v977[32]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v978[32]; // [rsp+DC8h] [rbp+CC8h] BYREF
  _BYTE v979[32]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v980[32]; // [rsp+E08h] [rbp+D08h] BYREF
  _BYTE v981[32]; // [rsp+E28h] [rbp+D28h] BYREF
  _BYTE v982[32]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v983[16]; // [rsp+E68h] [rbp+D68h] BYREF
  _BYTE v984[32]; // [rsp+E78h] [rbp+D78h] BYREF
  _BYTE v985[32]; // [rsp+E98h] [rbp+D98h] BYREF
  _BYTE v986[32]; // [rsp+EB8h] [rbp+DB8h] BYREF
  _BYTE v987[32]; // [rsp+ED8h] [rbp+DD8h] BYREF
  _BYTE v988[32]; // [rsp+EF8h] [rbp+DF8h] BYREF
  _BYTE v989[32]; // [rsp+F18h] [rbp+E18h] BYREF
  _BYTE v990[16]; // [rsp+F38h] [rbp+E38h] BYREF
  _BYTE v991[32]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v992[32]; // [rsp+F68h] [rbp+E68h] BYREF
  _BYTE v993[32]; // [rsp+F88h] [rbp+E88h] BYREF
  _BYTE v994[32]; // [rsp+FA8h] [rbp+EA8h] BYREF
  _BYTE v995[32]; // [rsp+FC8h] [rbp+EC8h] BYREF
  _BYTE v996[32]; // [rsp+FE8h] [rbp+EE8h] BYREF
  _BYTE v997[32]; // [rsp+1008h] [rbp+F08h] BYREF
  _BYTE v998[32]; // [rsp+1028h] [rbp+F28h] BYREF
  _BYTE v999[32]; // [rsp+1048h] [rbp+F48h] BYREF
  _BYTE v1000[32]; // [rsp+1068h] [rbp+F68h] BYREF
  _BYTE v1001[32]; // [rsp+1088h] [rbp+F88h] BYREF
  _BYTE v1002[32]; // [rsp+10A8h] [rbp+FA8h] BYREF
  _BYTE v1003[32]; // [rsp+10C8h] [rbp+FC8h] BYREF
  _BYTE v1004[32]; // [rsp+10E8h] [rbp+FE8h] BYREF
  _BYTE v1005[32]; // [rsp+1108h] [rbp+1008h] BYREF
  _BYTE v1006[32]; // [rsp+1128h] [rbp+1028h] BYREF
  _BYTE v1007[32]; // [rsp+1148h] [rbp+1048h] BYREF
  _BYTE v1008[32]; // [rsp+1168h] [rbp+1068h] BYREF
  _BYTE v1009[32]; // [rsp+1188h] [rbp+1088h] BYREF
  _BYTE v1010[32]; // [rsp+11A8h] [rbp+10A8h] BYREF
  _BYTE v1011[32]; // [rsp+11C8h] [rbp+10C8h] BYREF
  _BYTE v1012[32]; // [rsp+11E8h] [rbp+10E8h] BYREF
  _BYTE v1013[32]; // [rsp+1208h] [rbp+1108h] BYREF
  _BYTE v1014[32]; // [rsp+1228h] [rbp+1128h] BYREF
  _BYTE v1015[32]; // [rsp+1248h] [rbp+1148h] BYREF
  _BYTE v1016[32]; // [rsp+1268h] [rbp+1168h] BYREF
  _BYTE v1017[32]; // [rsp+1288h] [rbp+1188h] BYREF
  _BYTE v1018[32]; // [rsp+12A8h] [rbp+11A8h] BYREF
  _BYTE v1019[32]; // [rsp+12C8h] [rbp+11C8h] BYREF
  _BYTE v1020[32]; // [rsp+12E8h] [rbp+11E8h] BYREF
  _BYTE v1021[32]; // [rsp+1308h] [rbp+1208h] BYREF
  _BYTE v1022[32]; // [rsp+1328h] [rbp+1228h] BYREF
  _BYTE v1023[32]; // [rsp+1348h] [rbp+1248h] BYREF
  _BYTE v1024[32]; // [rsp+1368h] [rbp+1268h] BYREF
  _BYTE v1025[32]; // [rsp+1388h] [rbp+1288h] BYREF
  _BYTE v1026[32]; // [rsp+13A8h] [rbp+12A8h] BYREF
  _BYTE v1027[32]; // [rsp+13C8h] [rbp+12C8h] BYREF
  _BYTE v1028[32]; // [rsp+13E8h] [rbp+12E8h] BYREF
  _BYTE v1029[32]; // [rsp+1408h] [rbp+1308h] BYREF
  _BYTE v1030[32]; // [rsp+1428h] [rbp+1328h] BYREF
  _BYTE v1031[32]; // [rsp+1448h] [rbp+1348h] BYREF
  _BYTE v1032[32]; // [rsp+1468h] [rbp+1368h] BYREF
  _BYTE v1033[32]; // [rsp+1488h] [rbp+1388h] BYREF
  _BYTE v1034[32]; // [rsp+14A8h] [rbp+13A8h] BYREF
  _BYTE v1035[32]; // [rsp+14C8h] [rbp+13C8h] BYREF
  _BYTE v1036[32]; // [rsp+14E8h] [rbp+13E8h] BYREF
  _BYTE v1037[32]; // [rsp+1508h] [rbp+1408h] BYREF
  _BYTE v1038[32]; // [rsp+1528h] [rbp+1428h] BYREF
  _BYTE v1039[32]; // [rsp+1548h] [rbp+1448h] BYREF
  _BYTE v1040[32]; // [rsp+1568h] [rbp+1468h] BYREF
  _BYTE v1041[32]; // [rsp+1588h] [rbp+1488h] BYREF
  _BYTE v1042[32]; // [rsp+15A8h] [rbp+14A8h] BYREF
  _BYTE v1043[32]; // [rsp+15C8h] [rbp+14C8h] BYREF
  _BYTE v1044[32]; // [rsp+15E8h] [rbp+14E8h] BYREF
  _BYTE v1045[32]; // [rsp+1608h] [rbp+1508h] BYREF
  _BYTE v1046[32]; // [rsp+1628h] [rbp+1528h] BYREF
  _BYTE v1047[32]; // [rsp+1648h] [rbp+1548h] BYREF
  _BYTE v1048[32]; // [rsp+1668h] [rbp+1568h] BYREF
  _BYTE v1049[32]; // [rsp+1688h] [rbp+1588h] BYREF
  _BYTE v1050[32]; // [rsp+16A8h] [rbp+15A8h] BYREF
  _BYTE v1051[32]; // [rsp+16C8h] [rbp+15C8h] BYREF
  _BYTE v1052[32]; // [rsp+16E8h] [rbp+15E8h] BYREF
  _BYTE v1053[32]; // [rsp+1708h] [rbp+1608h] BYREF
  _BYTE v1054[32]; // [rsp+1728h] [rbp+1628h] BYREF
  _BYTE v1055[32]; // [rsp+1748h] [rbp+1648h] BYREF
  _BYTE v1056[32]; // [rsp+1768h] [rbp+1668h] BYREF
  _BYTE v1057[32]; // [rsp+1788h] [rbp+1688h] BYREF
  _BYTE v1058[32]; // [rsp+17A8h] [rbp+16A8h] BYREF
  _BYTE v1059[24]; // [rsp+17C8h] [rbp+16C8h] BYREF
  char v1060; // [rsp+17E0h] [rbp+16E0h] BYREF
  char v1061; // [rsp+1810h] [rbp+1710h] BYREF
  char v1062; // [rsp+1840h] [rbp+1740h] BYREF
  char v1063; // [rsp+1870h] [rbp+1770h] BYREF
  char v1064; // [rsp+18A0h] [rbp+17A0h] BYREF
  char v1065; // [rsp+18D0h] [rbp+17D0h] BYREF
  char v1066; // [rsp+1900h] [rbp+1800h] BYREF
  char v1067; // [rsp+1930h] [rbp+1830h] BYREF
  char v1068; // [rsp+1960h] [rbp+1860h] BYREF
  char v1069; // [rsp+1990h] [rbp+1890h] BYREF
  char v1070; // [rsp+19C0h] [rbp+18C0h] BYREF
  char v1071; // [rsp+19F0h] [rbp+18F0h] BYREF
  char v1072; // [rsp+1A20h] [rbp+1920h] BYREF
  char v1073; // [rsp+1A50h] [rbp+1950h] BYREF
  char v1074; // [rsp+1A80h] [rbp+1980h] BYREF
  char v1075; // [rsp+1AB0h] [rbp+19B0h] BYREF
  char v1076; // [rsp+1AE0h] [rbp+19E0h] BYREF
  char v1077; // [rsp+1B10h] [rbp+1A10h] BYREF
  char v1078; // [rsp+1B40h] [rbp+1A40h] BYREF
  char v1079; // [rsp+1B70h] [rbp+1A70h] BYREF
  char v1080; // [rsp+1BA0h] [rbp+1AA0h] BYREF
  char v1081; // [rsp+1BD0h] [rbp+1AD0h] BYREF
  char v1082; // [rsp+1C00h] [rbp+1B00h] BYREF
  char v1083; // [rsp+1C30h] [rbp+1B30h] BYREF
  char v1084; // [rsp+1C60h] [rbp+1B60h] BYREF
  char v1085; // [rsp+1C90h] [rbp+1B90h] BYREF
  char v1086; // [rsp+1CC0h] [rbp+1BC0h] BYREF
  char v1087; // [rsp+1CF0h] [rbp+1BF0h] BYREF
  char v1088; // [rsp+1D20h] [rbp+1C20h] BYREF
  char v1089; // [rsp+1D50h] [rbp+1C50h] BYREF
  char v1090; // [rsp+1D80h] [rbp+1C80h] BYREF
  char v1091; // [rsp+1DB0h] [rbp+1CB0h] BYREF
  char v1092; // [rsp+1DE0h] [rbp+1CE0h] BYREF
  char v1093; // [rsp+1E10h] [rbp+1D10h] BYREF
  char v1094; // [rsp+1E40h] [rbp+1D40h] BYREF
  char v1095; // [rsp+1E70h] [rbp+1D70h] BYREF
  char v1096; // [rsp+1EA0h] [rbp+1DA0h] BYREF
  char v1097; // [rsp+1ED0h] [rbp+1DD0h] BYREF
  char v1098; // [rsp+1F00h] [rbp+1E00h] BYREF
  char v1099; // [rsp+1F30h] [rbp+1E30h] BYREF
  char v1100; // [rsp+1F60h] [rbp+1E60h] BYREF
  char v1101; // [rsp+1F90h] [rbp+1E90h] BYREF
  char v1102; // [rsp+1FC0h] [rbp+1EC0h] BYREF
  char v1103; // [rsp+1FF0h] [rbp+1EF0h] BYREF
  char v1104; // [rsp+2020h] [rbp+1F20h] BYREF
  char v1105; // [rsp+2050h] [rbp+1F50h] BYREF
  char v1106; // [rsp+2080h] [rbp+1F80h] BYREF
  char v1107; // [rsp+20B0h] [rbp+1FB0h] BYREF
  char v1108; // [rsp+20E0h] [rbp+1FE0h] BYREF
  char v1109; // [rsp+2110h] [rbp+2010h] BYREF
  char v1110; // [rsp+2140h] [rbp+2040h] BYREF
  char v1111; // [rsp+2170h] [rbp+2070h] BYREF
  char v1112; // [rsp+21A0h] [rbp+20A0h] BYREF
  char v1113; // [rsp+21D0h] [rbp+20D0h] BYREF
  char v1114; // [rsp+2200h] [rbp+2100h] BYREF
  char v1115; // [rsp+2230h] [rbp+2130h] BYREF
  char v1116; // [rsp+2260h] [rbp+2160h] BYREF
  char v1117; // [rsp+2290h] [rbp+2190h] BYREF
  char v1118; // [rsp+22C0h] [rbp+21C0h] BYREF
  char v1119; // [rsp+22F0h] [rbp+21F0h] BYREF
  char v1120; // [rsp+2320h] [rbp+2220h] BYREF
  char v1121; // [rsp+2350h] [rbp+2250h] BYREF
  char v1122; // [rsp+2380h] [rbp+2280h] BYREF
  char v1123; // [rsp+23B0h] [rbp+22B0h] BYREF
  char v1124; // [rsp+23E0h] [rbp+22E0h] BYREF
  char v1125; // [rsp+2410h] [rbp+2310h] BYREF
  char v1126; // [rsp+2440h] [rbp+2340h] BYREF
  char v1127; // [rsp+2470h] [rbp+2370h] BYREF
  char v1128; // [rsp+24A0h] [rbp+23A0h] BYREF
  char v1129; // [rsp+24D0h] [rbp+23D0h] BYREF
  char v1130; // [rsp+2500h] [rbp+2400h] BYREF
  char v1131; // [rsp+2530h] [rbp+2430h] BYREF
  char v1132; // [rsp+2560h] [rbp+2460h] BYREF
  char v1133; // [rsp+2590h] [rbp+2490h] BYREF
  char v1134; // [rsp+25C0h] [rbp+24C0h] BYREF
  char v1135; // [rsp+25F0h] [rbp+24F0h] BYREF
  char v1136; // [rsp+2620h] [rbp+2520h] BYREF
  char v1137; // [rsp+2650h] [rbp+2550h] BYREF
  char v1138; // [rsp+2680h] [rbp+2580h] BYREF
  char v1139; // [rsp+26B0h] [rbp+25B0h] BYREF
  char v1140; // [rsp+26E0h] [rbp+25E0h] BYREF
  char v1141; // [rsp+2710h] [rbp+2610h] BYREF
  char v1142; // [rsp+2740h] [rbp+2640h] BYREF
  char v1143; // [rsp+2770h] [rbp+2670h] BYREF
  char v1144; // [rsp+27A0h] [rbp+26A0h] BYREF
  char v1145; // [rsp+27D0h] [rbp+26D0h] BYREF
  char v1146; // [rsp+2800h] [rbp+2700h] BYREF
  char v1147; // [rsp+2830h] [rbp+2730h] BYREF
  char v1148; // [rsp+2860h] [rbp+2760h] BYREF
  char v1149; // [rsp+2890h] [rbp+2790h] BYREF
  char v1150; // [rsp+28C0h] [rbp+27C0h] BYREF
  char v1151; // [rsp+28F0h] [rbp+27F0h] BYREF
  char v1152; // [rsp+2920h] [rbp+2820h] BYREF
  char v1153; // [rsp+2950h] [rbp+2850h] BYREF
  char v1154; // [rsp+2980h] [rbp+2880h] BYREF
  char v1155; // [rsp+29B0h] [rbp+28B0h] BYREF
  char v1156; // [rsp+29E0h] [rbp+28E0h] BYREF
  char v1157; // [rsp+2A10h] [rbp+2910h] BYREF
  char v1158; // [rsp+2A40h] [rbp+2940h] BYREF
  char v1159; // [rsp+2A70h] [rbp+2970h] BYREF
  char v1160; // [rsp+2AA0h] [rbp+29A0h] BYREF
  char v1161; // [rsp+2AD0h] [rbp+29D0h] BYREF
  char v1162; // [rsp+2B00h] [rbp+2A00h] BYREF
  char v1163; // [rsp+2B30h] [rbp+2A30h] BYREF
  char v1164; // [rsp+2B60h] [rbp+2A60h] BYREF
  char v1165; // [rsp+2B90h] [rbp+2A90h] BYREF
  char v1166; // [rsp+2BC0h] [rbp+2AC0h] BYREF
  char v1167; // [rsp+2BF0h] [rbp+2AF0h] BYREF
  char v1168; // [rsp+2C20h] [rbp+2B20h] BYREF
  char v1169; // [rsp+2C50h] [rbp+2B50h] BYREF
  char v1170; // [rsp+2C80h] [rbp+2B80h] BYREF
  char v1171; // [rsp+2CB0h] [rbp+2BB0h] BYREF
  char v1172; // [rsp+2CE0h] [rbp+2BE0h] BYREF
  char v1173; // [rsp+2D10h] [rbp+2C10h] BYREF
  char v1174; // [rsp+2D40h] [rbp+2C40h] BYREF
  char v1175; // [rsp+2D70h] [rbp+2C70h] BYREF
  char v1176; // [rsp+2DA0h] [rbp+2CA0h] BYREF
  char v1177; // [rsp+2DD0h] [rbp+2CD0h] BYREF
  char v1178; // [rsp+2E00h] [rbp+2D00h] BYREF
  char v1179; // [rsp+2E30h] [rbp+2D30h] BYREF
  char v1180; // [rsp+2E60h] [rbp+2D60h] BYREF
  char v1181; // [rsp+2E90h] [rbp+2D90h] BYREF
  char v1182; // [rsp+2EC0h] [rbp+2DC0h] BYREF
  char v1183; // [rsp+2EF0h] [rbp+2DF0h] BYREF
  char v1184; // [rsp+2F20h] [rbp+2E20h] BYREF
  char v1185; // [rsp+2F50h] [rbp+2E50h] BYREF
  char v1186; // [rsp+2F80h] [rbp+2E80h] BYREF
  char v1187; // [rsp+2FB0h] [rbp+2EB0h] BYREF
  char v1188; // [rsp+2FE0h] [rbp+2EE0h] BYREF
  char v1189; // [rsp+3010h] [rbp+2F10h] BYREF
  char v1190; // [rsp+3040h] [rbp+2F40h] BYREF
  char v1191; // [rsp+3070h] [rbp+2F70h] BYREF
  char v1192; // [rsp+30A0h] [rbp+2FA0h] BYREF
  char v1193; // [rsp+30D0h] [rbp+2FD0h] BYREF
  char v1194; // [rsp+3100h] [rbp+3000h] BYREF
  char v1195; // [rsp+3130h] [rbp+3030h] BYREF
  char v1196; // [rsp+3160h] [rbp+3060h] BYREF
  char v1197; // [rsp+3190h] [rbp+3090h] BYREF
  char v1198; // [rsp+31C0h] [rbp+30C0h] BYREF
  char v1199; // [rsp+31F0h] [rbp+30F0h] BYREF
  char v1200; // [rsp+3220h] [rbp+3120h] BYREF
  char v1201; // [rsp+3250h] [rbp+3150h] BYREF
  char v1202; // [rsp+3280h] [rbp+3180h] BYREF
  char v1203; // [rsp+32B0h] [rbp+31B0h] BYREF
  char v1204; // [rsp+32E0h] [rbp+31E0h] BYREF
  char v1205; // [rsp+3310h] [rbp+3210h] BYREF
  char v1206; // [rsp+3340h] [rbp+3240h] BYREF
  char v1207; // [rsp+3370h] [rbp+3270h] BYREF
  char v1208; // [rsp+33A8h] [rbp+32A8h] BYREF
  char v1209; // [rsp+33E0h] [rbp+32E0h] BYREF
  char v1210; // [rsp+3418h] [rbp+3318h] BYREF
  char v1211; // [rsp+3450h] [rbp+3350h] BYREF
  _BYTE v1212[32]; // [rsp+3488h] [rbp+3388h] BYREF
  _BYTE v1213[32]; // [rsp+34A8h] [rbp+33A8h] BYREF
  _BYTE v1214[32]; // [rsp+34C8h] [rbp+33C8h] BYREF
  _BYTE v1215[32]; // [rsp+34E8h] [rbp+33E8h] BYREF
  _BYTE v1216[32]; // [rsp+3508h] [rbp+3408h] BYREF
  _BYTE v1217[32]; // [rsp+3528h] [rbp+3428h] BYREF
  _BYTE v1218[32]; // [rsp+3548h] [rbp+3448h] BYREF
  _BYTE v1219[32]; // [rsp+3568h] [rbp+3468h] BYREF
  _BYTE v1220[32]; // [rsp+3588h] [rbp+3488h] BYREF
  _BYTE v1221[32]; // [rsp+35A8h] [rbp+34A8h] BYREF
  _BYTE v1222[32]; // [rsp+35C8h] [rbp+34C8h] BYREF
  _BYTE v1223[32]; // [rsp+35E8h] [rbp+34E8h] BYREF
  _BYTE v1224[32]; // [rsp+3608h] [rbp+3508h] BYREF
  _BYTE v1225[32]; // [rsp+3628h] [rbp+3528h] BYREF
  _BYTE v1226[32]; // [rsp+3648h] [rbp+3548h] BYREF
  _BYTE v1227[32]; // [rsp+3668h] [rbp+3568h] BYREF
  _BYTE v1228[32]; // [rsp+3688h] [rbp+3588h] BYREF
  _BYTE v1229[32]; // [rsp+36A8h] [rbp+35A8h] BYREF
  _BYTE v1230[32]; // [rsp+36C8h] [rbp+35C8h] BYREF
  _BYTE v1231[32]; // [rsp+36E8h] [rbp+35E8h] BYREF
  _BYTE v1232[32]; // [rsp+3708h] [rbp+3608h] BYREF
  _BYTE v1233[32]; // [rsp+3728h] [rbp+3628h] BYREF
  _BYTE v1234[32]; // [rsp+3748h] [rbp+3648h] BYREF
  _BYTE v1235[32]; // [rsp+3768h] [rbp+3668h] BYREF
  _BYTE v1236[32]; // [rsp+3788h] [rbp+3688h] BYREF
  _BYTE v1237[32]; // [rsp+37A8h] [rbp+36A8h] BYREF
  _BYTE v1238[32]; // [rsp+37C8h] [rbp+36C8h] BYREF
  _BYTE v1239[32]; // [rsp+37E8h] [rbp+36E8h] BYREF
  _BYTE v1240[32]; // [rsp+3808h] [rbp+3708h] BYREF
  _BYTE v1241[32]; // [rsp+3828h] [rbp+3728h] BYREF
  _BYTE v1242[32]; // [rsp+3848h] [rbp+3748h] BYREF
  _BYTE v1243[32]; // [rsp+3868h] [rbp+3768h] BYREF
  _BYTE v1244[32]; // [rsp+3888h] [rbp+3788h] BYREF
  _BYTE v1245[32]; // [rsp+38A8h] [rbp+37A8h] BYREF
  _BYTE v1246[32]; // [rsp+38C8h] [rbp+37C8h] BYREF
  _BYTE v1247[32]; // [rsp+38E8h] [rbp+37E8h] BYREF
  _BYTE v1248[32]; // [rsp+3908h] [rbp+3808h] BYREF
  _BYTE v1249[32]; // [rsp+3928h] [rbp+3828h] BYREF
  _BYTE v1250[32]; // [rsp+3948h] [rbp+3848h] BYREF
  _BYTE v1251[32]; // [rsp+3968h] [rbp+3868h] BYREF
  _BYTE v1252[32]; // [rsp+3988h] [rbp+3888h] BYREF
  _BYTE v1253[32]; // [rsp+39A8h] [rbp+38A8h] BYREF
  _BYTE v1254[32]; // [rsp+39C8h] [rbp+38C8h] BYREF
  _BYTE v1255[32]; // [rsp+39E8h] [rbp+38E8h] BYREF
  _BYTE v1256[32]; // [rsp+3A08h] [rbp+3908h] BYREF
  _BYTE v1257[32]; // [rsp+3A28h] [rbp+3928h] BYREF
  _BYTE v1258[32]; // [rsp+3A48h] [rbp+3948h] BYREF
  _BYTE v1259[32]; // [rsp+3A68h] [rbp+3968h] BYREF
  _BYTE v1260[32]; // [rsp+3A88h] [rbp+3988h] BYREF
  _BYTE v1261[32]; // [rsp+3AA8h] [rbp+39A8h] BYREF
  _BYTE v1262[32]; // [rsp+3AC8h] [rbp+39C8h] BYREF
  _BYTE v1263[32]; // [rsp+3AE8h] [rbp+39E8h] BYREF
  _BYTE v1264[32]; // [rsp+3B08h] [rbp+3A08h] BYREF
  _BYTE v1265[32]; // [rsp+3B28h] [rbp+3A28h] BYREF
  _BYTE v1266[32]; // [rsp+3B48h] [rbp+3A48h] BYREF
  _BYTE v1267[32]; // [rsp+3B68h] [rbp+3A68h] BYREF
  _BYTE v1268[32]; // [rsp+3B88h] [rbp+3A88h] BYREF
  _OWORD v1269[2]; // [rsp+3BA8h] [rbp+3AA8h] BYREF
  __int64 v1270; // [rsp+3BC8h] [rbp+3AC8h]
  _OWORD v1271[2]; // [rsp+3BD0h] [rbp+3AD0h] BYREF
  __int64 v1272; // [rsp+3BF0h] [rbp+3AF0h]
  _BYTE v1273[32]; // [rsp+3BF8h] [rbp+3AF8h] BYREF
  _BYTE v1274[32]; // [rsp+3C18h] [rbp+3B18h] BYREF
  _BYTE v1275[32]; // [rsp+3C38h] [rbp+3B38h] BYREF
  _BYTE v1276[32]; // [rsp+3C58h] [rbp+3B58h] BYREF
  _BYTE v1277[32]; // [rsp+3C78h] [rbp+3B78h] BYREF
  _BYTE v1278[32]; // [rsp+3C98h] [rbp+3B98h] BYREF
  _BYTE v1279[32]; // [rsp+3CB8h] [rbp+3BB8h] BYREF
  _BYTE v1280[32]; // [rsp+3CD8h] [rbp+3BD8h] BYREF
  _BYTE v1281[32]; // [rsp+3CF8h] [rbp+3BF8h] BYREF
  _BYTE v1282[32]; // [rsp+3D18h] [rbp+3C18h] BYREF
  _BYTE v1283[32]; // [rsp+3D38h] [rbp+3C38h] BYREF
  _BYTE v1284[32]; // [rsp+3D58h] [rbp+3C58h] BYREF
  _BYTE v1285[32]; // [rsp+3D78h] [rbp+3C78h] BYREF
  _BYTE v1286[40]; // [rsp+3D98h] [rbp+3C98h] BYREF
  _BYTE v1287[40]; // [rsp+3DC0h] [rbp+3CC0h] BYREF
  _BYTE v1288[40]; // [rsp+3DE8h] [rbp+3CE8h] BYREF
  _BYTE v1289[40]; // [rsp+3E10h] [rbp+3D10h] BYREF
  _BYTE v1290[40]; // [rsp+3E38h] [rbp+3D38h] BYREF
  _BYTE v1291[40]; // [rsp+3E60h] [rbp+3D60h] BYREF
  _BYTE v1292[40]; // [rsp+3E88h] [rbp+3D88h] BYREF
  _BYTE v1293[40]; // [rsp+3EB0h] [rbp+3DB0h] BYREF
  _BYTE v1294[40]; // [rsp+3ED8h] [rbp+3DD8h] BYREF
  _BYTE v1295[40]; // [rsp+3F00h] [rbp+3E00h] BYREF
  _BYTE v1296[40]; // [rsp+3F28h] [rbp+3E28h] BYREF
  _BYTE v1297[40]; // [rsp+3F50h] [rbp+3E50h] BYREF
  _BYTE v1298[40]; // [rsp+3F78h] [rbp+3E78h] BYREF
  _BYTE v1299[40]; // [rsp+3FA0h] [rbp+3EA0h] BYREF
  _BYTE v1300[40]; // [rsp+3FC8h] [rbp+3EC8h] BYREF
  _BYTE v1301[40]; // [rsp+3FF0h] [rbp+3EF0h] BYREF
  _BYTE v1302[40]; // [rsp+4018h] [rbp+3F18h] BYREF
  _BYTE v1303[40]; // [rsp+4040h] [rbp+3F40h] BYREF
  _BYTE v1304[40]; // [rsp+4068h] [rbp+3F68h] BYREF
  _BYTE v1305[40]; // [rsp+4090h] [rbp+3F90h] BYREF
  _BYTE v1306[40]; // [rsp+40B8h] [rbp+3FB8h] BYREF
  _BYTE v1307[40]; // [rsp+40E0h] [rbp+3FE0h] BYREF
  _BYTE v1308[40]; // [rsp+4108h] [rbp+4008h] BYREF
  _BYTE v1309[40]; // [rsp+4130h] [rbp+4030h] BYREF
  _BYTE v1310[40]; // [rsp+4158h] [rbp+4058h] BYREF
  _BYTE v1311[40]; // [rsp+4180h] [rbp+4080h] BYREF
  _BYTE v1312[40]; // [rsp+41A8h] [rbp+40A8h] BYREF
  _BYTE v1313[40]; // [rsp+41D0h] [rbp+40D0h] BYREF
  _BYTE v1314[40]; // [rsp+41F8h] [rbp+40F8h] BYREF
  _BYTE v1315[40]; // [rsp+4220h] [rbp+4120h] BYREF
  _BYTE v1316[40]; // [rsp+4248h] [rbp+4148h] BYREF
  _BYTE v1317[40]; // [rsp+4270h] [rbp+4170h] BYREF
  _BYTE v1318[40]; // [rsp+4298h] [rbp+4198h] BYREF
  _BYTE v1319[40]; // [rsp+42C0h] [rbp+41C0h] BYREF
  _BYTE v1320[40]; // [rsp+42E8h] [rbp+41E8h] BYREF
  _BYTE v1321[40]; // [rsp+4310h] [rbp+4210h] BYREF
  _BYTE v1322[40]; // [rsp+4338h] [rbp+4238h] BYREF
  _BYTE v1323[40]; // [rsp+4360h] [rbp+4260h] BYREF
  _BYTE v1324[40]; // [rsp+4388h] [rbp+4288h] BYREF
  _BYTE v1325[40]; // [rsp+43B0h] [rbp+42B0h] BYREF
  _BYTE v1326[40]; // [rsp+43D8h] [rbp+42D8h] BYREF
  _BYTE v1327[40]; // [rsp+4400h] [rbp+4300h] BYREF
  _BYTE v1328[40]; // [rsp+4428h] [rbp+4328h] BYREF
  _BYTE v1329[40]; // [rsp+4450h] [rbp+4350h] BYREF
  _BYTE v1330[40]; // [rsp+4478h] [rbp+4378h] BYREF
  _BYTE v1331[40]; // [rsp+44A0h] [rbp+43A0h] BYREF
  _BYTE v1332[40]; // [rsp+44C8h] [rbp+43C8h] BYREF
  _BYTE v1333[40]; // [rsp+44F0h] [rbp+43F0h] BYREF
  _BYTE v1334[40]; // [rsp+4518h] [rbp+4418h] BYREF
  _BYTE v1335[40]; // [rsp+4540h] [rbp+4440h] BYREF
  _BYTE v1336[40]; // [rsp+4568h] [rbp+4468h] BYREF
  _BYTE v1337[40]; // [rsp+4590h] [rbp+4490h] BYREF
  _BYTE v1338[40]; // [rsp+45B8h] [rbp+44B8h] BYREF
  _BYTE v1339[40]; // [rsp+45E0h] [rbp+44E0h] BYREF
  _BYTE v1340[40]; // [rsp+4608h] [rbp+4508h] BYREF
  _BYTE v1341[40]; // [rsp+4630h] [rbp+4530h] BYREF
  _BYTE v1342[40]; // [rsp+4658h] [rbp+4558h] BYREF
  _BYTE v1343[40]; // [rsp+4680h] [rbp+4580h] BYREF
  _BYTE v1344[40]; // [rsp+46A8h] [rbp+45A8h] BYREF
  _BYTE v1345[40]; // [rsp+46D0h] [rbp+45D0h] BYREF
  _BYTE v1346[40]; // [rsp+46F8h] [rbp+45F8h] BYREF
  _BYTE v1347[40]; // [rsp+4720h] [rbp+4620h] BYREF
  _BYTE v1348[40]; // [rsp+4748h] [rbp+4648h] BYREF
  _BYTE v1349[40]; // [rsp+4770h] [rbp+4670h] BYREF
  _BYTE v1350[40]; // [rsp+4798h] [rbp+4698h] BYREF
  _BYTE v1351[40]; // [rsp+47C0h] [rbp+46C0h] BYREF
  _BYTE v1352[40]; // [rsp+47E8h] [rbp+46E8h] BYREF
  _BYTE v1353[40]; // [rsp+4810h] [rbp+4710h] BYREF
  _BYTE v1354[40]; // [rsp+4838h] [rbp+4738h] BYREF
  _BYTE v1355[40]; // [rsp+4860h] [rbp+4760h] BYREF
  _BYTE v1356[40]; // [rsp+4888h] [rbp+4788h] BYREF
  _BYTE v1357[40]; // [rsp+48B0h] [rbp+47B0h] BYREF
  _BYTE v1358[40]; // [rsp+48D8h] [rbp+47D8h] BYREF
  _BYTE v1359[40]; // [rsp+4900h] [rbp+4800h] BYREF
  _BYTE v1360[40]; // [rsp+4928h] [rbp+4828h] BYREF
  _BYTE v1361[40]; // [rsp+4950h] [rbp+4850h] BYREF
  _BYTE v1362[40]; // [rsp+4978h] [rbp+4878h] BYREF
  _BYTE v1363[40]; // [rsp+49A0h] [rbp+48A0h] BYREF
  _BYTE v1364[40]; // [rsp+49C8h] [rbp+48C8h] BYREF
  _BYTE v1365[40]; // [rsp+49F0h] [rbp+48F0h] BYREF
  _BYTE v1366[40]; // [rsp+4A18h] [rbp+4918h] BYREF
  _BYTE v1367[40]; // [rsp+4A40h] [rbp+4940h] BYREF
  _BYTE v1368[40]; // [rsp+4A68h] [rbp+4968h] BYREF
  _BYTE v1369[40]; // [rsp+4A90h] [rbp+4990h] BYREF
  _BYTE v1370[40]; // [rsp+4AB8h] [rbp+49B8h] BYREF
  _BYTE v1371[40]; // [rsp+4AE0h] [rbp+49E0h] BYREF
  _BYTE v1372[40]; // [rsp+4B08h] [rbp+4A08h] BYREF
  _BYTE v1373[40]; // [rsp+4B30h] [rbp+4A30h] BYREF
  _BYTE v1374[40]; // [rsp+4B58h] [rbp+4A58h] BYREF
  _BYTE v1375[40]; // [rsp+4B80h] [rbp+4A80h] BYREF
  _BYTE v1376[40]; // [rsp+4BA8h] [rbp+4AA8h] BYREF
  _BYTE v1377[40]; // [rsp+4BD0h] [rbp+4AD0h] BYREF
  _BYTE v1378[40]; // [rsp+4BF8h] [rbp+4AF8h] BYREF
  _BYTE v1379[40]; // [rsp+4C20h] [rbp+4B20h] BYREF
  _BYTE v1380[40]; // [rsp+4C48h] [rbp+4B48h] BYREF
  _BYTE v1381[40]; // [rsp+4C70h] [rbp+4B70h] BYREF
  _BYTE v1382[40]; // [rsp+4C98h] [rbp+4B98h] BYREF
  _BYTE v1383[40]; // [rsp+4CC0h] [rbp+4BC0h] BYREF
  _BYTE v1384[40]; // [rsp+4CE8h] [rbp+4BE8h] BYREF
  _BYTE v1385[40]; // [rsp+4D10h] [rbp+4C10h] BYREF
  _BYTE v1386[40]; // [rsp+4D38h] [rbp+4C38h] BYREF
  _BYTE v1387[40]; // [rsp+4D60h] [rbp+4C60h] BYREF
  _BYTE v1388[40]; // [rsp+4D88h] [rbp+4C88h] BYREF
  _BYTE v1389[40]; // [rsp+4DB0h] [rbp+4CB0h] BYREF
  _BYTE v1390[40]; // [rsp+4DD8h] [rbp+4CD8h] BYREF
  _BYTE v1391[40]; // [rsp+4E00h] [rbp+4D00h] BYREF
  _BYTE v1392[40]; // [rsp+4E28h] [rbp+4D28h] BYREF
  _BYTE v1393[40]; // [rsp+4E50h] [rbp+4D50h] BYREF
  _BYTE v1394[40]; // [rsp+4E78h] [rbp+4D78h] BYREF
  _BYTE v1395[40]; // [rsp+4EA0h] [rbp+4DA0h] BYREF
  _BYTE v1396[40]; // [rsp+4EC8h] [rbp+4DC8h] BYREF
  _BYTE v1397[40]; // [rsp+4EF0h] [rbp+4DF0h] BYREF
  _BYTE v1398[40]; // [rsp+4F18h] [rbp+4E18h] BYREF
  _BYTE v1399[40]; // [rsp+4F40h] [rbp+4E40h] BYREF
  _BYTE v1400[40]; // [rsp+4F68h] [rbp+4E68h] BYREF
  _BYTE v1401[40]; // [rsp+4F90h] [rbp+4E90h] BYREF
  _BYTE v1402[40]; // [rsp+4FB8h] [rbp+4EB8h] BYREF
  _BYTE v1403[40]; // [rsp+4FE0h] [rbp+4EE0h] BYREF
  _BYTE v1404[40]; // [rsp+5008h] [rbp+4F08h] BYREF
  _BYTE v1405[40]; // [rsp+5030h] [rbp+4F30h] BYREF
  _BYTE v1406[40]; // [rsp+5058h] [rbp+4F58h] BYREF
  _BYTE v1407[40]; // [rsp+5080h] [rbp+4F80h] BYREF
  _BYTE v1408[40]; // [rsp+50A8h] [rbp+4FA8h] BYREF
  _BYTE v1409[40]; // [rsp+50D0h] [rbp+4FD0h] BYREF
  _BYTE v1410[40]; // [rsp+50F8h] [rbp+4FF8h] BYREF
  _BYTE v1411[40]; // [rsp+5120h] [rbp+5020h] BYREF
  _BYTE v1412[40]; // [rsp+5148h] [rbp+5048h] BYREF
  _BYTE v1413[40]; // [rsp+5170h] [rbp+5070h] BYREF
  _BYTE v1414[40]; // [rsp+5198h] [rbp+5098h] BYREF
  _BYTE v1415[40]; // [rsp+51C0h] [rbp+50C0h] BYREF
  _BYTE v1416[40]; // [rsp+51E8h] [rbp+50E8h] BYREF
  _BYTE v1417[40]; // [rsp+5210h] [rbp+5110h] BYREF
  _BYTE v1418[40]; // [rsp+5238h] [rbp+5138h] BYREF
  _BYTE v1419[40]; // [rsp+5260h] [rbp+5160h] BYREF
  _BYTE v1420[40]; // [rsp+5288h] [rbp+5188h] BYREF
  _BYTE v1421[40]; // [rsp+52B0h] [rbp+51B0h] BYREF
  _BYTE v1422[40]; // [rsp+52D8h] [rbp+51D8h] BYREF
  _BYTE v1423[40]; // [rsp+5300h] [rbp+5200h] BYREF
  _BYTE v1424[40]; // [rsp+5328h] [rbp+5228h] BYREF
  _BYTE v1425[40]; // [rsp+5350h] [rbp+5250h] BYREF
  _BYTE v1426[40]; // [rsp+5378h] [rbp+5278h] BYREF
  _BYTE v1427[40]; // [rsp+53A0h] [rbp+52A0h] BYREF
  _BYTE v1428[40]; // [rsp+53C8h] [rbp+52C8h] BYREF
  _BYTE v1429[40]; // [rsp+53F0h] [rbp+52F0h] BYREF
  _BYTE v1430[40]; // [rsp+5418h] [rbp+5318h] BYREF
  _BYTE v1431[40]; // [rsp+5440h] [rbp+5340h] BYREF
  _BYTE v1432[40]; // [rsp+5468h] [rbp+5368h] BYREF
  _BYTE v1433[40]; // [rsp+5490h] [rbp+5390h] BYREF
  _BYTE v1434[40]; // [rsp+54B8h] [rbp+53B8h] BYREF
  _BYTE v1435[40]; // [rsp+54E0h] [rbp+53E0h] BYREF
  _BYTE v1436[40]; // [rsp+5508h] [rbp+5408h] BYREF
  _BYTE v1437[40]; // [rsp+5530h] [rbp+5430h] BYREF
  _BYTE v1438[40]; // [rsp+5558h] [rbp+5458h] BYREF
  _BYTE v1439[40]; // [rsp+5580h] [rbp+5480h] BYREF
  _BYTE v1440[40]; // [rsp+55A8h] [rbp+54A8h] BYREF
  _BYTE v1441[40]; // [rsp+55D0h] [rbp+54D0h] BYREF
  _BYTE v1442[40]; // [rsp+55F8h] [rbp+54F8h] BYREF
  _BYTE v1443[40]; // [rsp+5620h] [rbp+5520h] BYREF
  _BYTE v1444[40]; // [rsp+5648h] [rbp+5548h] BYREF
  _BYTE v1445[40]; // [rsp+5670h] [rbp+5570h] BYREF
  _BYTE v1446[40]; // [rsp+5698h] [rbp+5598h] BYREF
  _BYTE v1447[40]; // [rsp+56C0h] [rbp+55C0h] BYREF
  _BYTE v1448[40]; // [rsp+56E8h] [rbp+55E8h] BYREF
  _BYTE v1449[40]; // [rsp+5710h] [rbp+5610h] BYREF
  _BYTE v1450[40]; // [rsp+5738h] [rbp+5638h] BYREF
  _BYTE v1451[40]; // [rsp+5760h] [rbp+5660h] BYREF
  _BYTE v1452[40]; // [rsp+5788h] [rbp+5688h] BYREF
  _BYTE v1453[40]; // [rsp+57B0h] [rbp+56B0h] BYREF
  _BYTE v1454[40]; // [rsp+57D8h] [rbp+56D8h] BYREF
  _BYTE v1455[40]; // [rsp+5800h] [rbp+5700h] BYREF
  _BYTE v1456[40]; // [rsp+5828h] [rbp+5728h] BYREF
  _BYTE v1457[40]; // [rsp+5850h] [rbp+5750h] BYREF
  _BYTE v1458[40]; // [rsp+5878h] [rbp+5778h] BYREF
  _BYTE v1459[40]; // [rsp+58A0h] [rbp+57A0h] BYREF
  _BYTE v1460[40]; // [rsp+58C8h] [rbp+57C8h] BYREF
  _BYTE v1461[40]; // [rsp+58F0h] [rbp+57F0h] BYREF
  _BYTE v1462[40]; // [rsp+5918h] [rbp+5818h] BYREF
  _BYTE v1463[40]; // [rsp+5940h] [rbp+5840h] BYREF
  _BYTE v1464[40]; // [rsp+5968h] [rbp+5868h] BYREF
  _BYTE v1465[40]; // [rsp+5990h] [rbp+5890h] BYREF
  _BYTE v1466[40]; // [rsp+59B8h] [rbp+58B8h] BYREF
  _BYTE v1467[40]; // [rsp+59E0h] [rbp+58E0h] BYREF
  _BYTE v1468[40]; // [rsp+5A08h] [rbp+5908h] BYREF
  _BYTE v1469[40]; // [rsp+5A30h] [rbp+5930h] BYREF
  _BYTE v1470[40]; // [rsp+5A58h] [rbp+5958h] BYREF
  _BYTE v1471[40]; // [rsp+5A80h] [rbp+5980h] BYREF
  _BYTE v1472[40]; // [rsp+5AA8h] [rbp+59A8h] BYREF
  _BYTE v1473[40]; // [rsp+5AD0h] [rbp+59D0h] BYREF
  _BYTE v1474[40]; // [rsp+5AF8h] [rbp+59F8h] BYREF
  _BYTE v1475[40]; // [rsp+5B20h] [rbp+5A20h] BYREF
  _BYTE v1476[40]; // [rsp+5B48h] [rbp+5A48h] BYREF
  _BYTE v1477[40]; // [rsp+5B70h] [rbp+5A70h] BYREF
  _BYTE v1478[40]; // [rsp+5B98h] [rbp+5A98h] BYREF
  _BYTE v1479[40]; // [rsp+5BC0h] [rbp+5AC0h] BYREF
  _BYTE v1480[40]; // [rsp+5BE8h] [rbp+5AE8h] BYREF
  _BYTE v1481[40]; // [rsp+5C10h] [rbp+5B10h] BYREF
  _BYTE v1482[40]; // [rsp+5C38h] [rbp+5B38h] BYREF
  _BYTE v1483[40]; // [rsp+5C60h] [rbp+5B60h] BYREF
  _BYTE v1484[40]; // [rsp+5C88h] [rbp+5B88h] BYREF
  _BYTE v1485[40]; // [rsp+5CB0h] [rbp+5BB0h] BYREF
  _BYTE v1486[40]; // [rsp+5CD8h] [rbp+5BD8h] BYREF
  _BYTE v1487[40]; // [rsp+5D00h] [rbp+5C00h] BYREF
  _BYTE v1488[40]; // [rsp+5D28h] [rbp+5C28h] BYREF
  _BYTE v1489[40]; // [rsp+5D50h] [rbp+5C50h] BYREF
  _BYTE v1490[40]; // [rsp+5D78h] [rbp+5C78h] BYREF
  _BYTE v1491[40]; // [rsp+5DA0h] [rbp+5CA0h] BYREF
  _BYTE v1492[40]; // [rsp+5DC8h] [rbp+5CC8h] BYREF
  _BYTE v1493[40]; // [rsp+5DF0h] [rbp+5CF0h] BYREF
  _BYTE v1494[40]; // [rsp+5E18h] [rbp+5D18h] BYREF
  _BYTE v1495[40]; // [rsp+5E40h] [rbp+5D40h] BYREF
  _BYTE v1496[40]; // [rsp+5E68h] [rbp+5D68h] BYREF
  _BYTE v1497[40]; // [rsp+5E90h] [rbp+5D90h] BYREF
  _BYTE v1498[40]; // [rsp+5EB8h] [rbp+5DB8h] BYREF
  _BYTE v1499[40]; // [rsp+5EE0h] [rbp+5DE0h] BYREF
  _BYTE v1500[40]; // [rsp+5F08h] [rbp+5E08h] BYREF
  _BYTE v1501[40]; // [rsp+5F30h] [rbp+5E30h] BYREF
  _BYTE v1502[40]; // [rsp+5F58h] [rbp+5E58h] BYREF
  _BYTE v1503[40]; // [rsp+5F80h] [rbp+5E80h] BYREF
  _BYTE v1504[40]; // [rsp+5FA8h] [rbp+5EA8h] BYREF
  _BYTE v1505[40]; // [rsp+5FD0h] [rbp+5ED0h] BYREF
  _BYTE v1506[40]; // [rsp+5FF8h] [rbp+5EF8h] BYREF
  _BYTE v1507[40]; // [rsp+6020h] [rbp+5F20h] BYREF
  _BYTE v1508[40]; // [rsp+6048h] [rbp+5F48h] BYREF
  _BYTE v1509[40]; // [rsp+6070h] [rbp+5F70h] BYREF
  _BYTE v1510[40]; // [rsp+6098h] [rbp+5F98h] BYREF
  _BYTE v1511[40]; // [rsp+60C0h] [rbp+5FC0h] BYREF
  _BYTE v1512[40]; // [rsp+60E8h] [rbp+5FE8h] BYREF
  _BYTE v1513[40]; // [rsp+6110h] [rbp+6010h] BYREF
  _BYTE v1514[40]; // [rsp+6138h] [rbp+6038h] BYREF
  _BYTE v1515[40]; // [rsp+6160h] [rbp+6060h] BYREF
  _BYTE v1516[40]; // [rsp+6188h] [rbp+6088h] BYREF
  _BYTE v1517[40]; // [rsp+61B0h] [rbp+60B0h] BYREF
  _BYTE v1518[40]; // [rsp+61D8h] [rbp+60D8h] BYREF
  _BYTE v1519[40]; // [rsp+6200h] [rbp+6100h] BYREF
  _BYTE v1520[40]; // [rsp+6228h] [rbp+6128h] BYREF
  _BYTE v1521[40]; // [rsp+6250h] [rbp+6150h] BYREF
  _BYTE v1522[40]; // [rsp+6278h] [rbp+6178h] BYREF
  _BYTE v1523[40]; // [rsp+62A0h] [rbp+61A0h] BYREF
  _BYTE v1524[40]; // [rsp+62C8h] [rbp+61C8h] BYREF
  _BYTE v1525[40]; // [rsp+62F0h] [rbp+61F0h] BYREF
  _BYTE v1526[40]; // [rsp+6318h] [rbp+6218h] BYREF
  _BYTE v1527[40]; // [rsp+6340h] [rbp+6240h] BYREF
  _BYTE v1528[40]; // [rsp+6368h] [rbp+6268h] BYREF
  _BYTE v1529[40]; // [rsp+6390h] [rbp+6290h] BYREF
  _BYTE v1530[40]; // [rsp+63B8h] [rbp+62B8h] BYREF
  _BYTE v1531[40]; // [rsp+63E0h] [rbp+62E0h] BYREF
  _BYTE v1532[40]; // [rsp+6408h] [rbp+6308h] BYREF
  _BYTE v1533[40]; // [rsp+6430h] [rbp+6330h] BYREF
  _BYTE v1534[40]; // [rsp+6458h] [rbp+6358h] BYREF
  _BYTE v1535[40]; // [rsp+6480h] [rbp+6380h] BYREF
  _BYTE v1536[40]; // [rsp+64A8h] [rbp+63A8h] BYREF
  _BYTE v1537[40]; // [rsp+64D0h] [rbp+63D0h] BYREF
  _BYTE v1538[40]; // [rsp+64F8h] [rbp+63F8h] BYREF
  _BYTE v1539[40]; // [rsp+6520h] [rbp+6420h] BYREF
  _BYTE v1540[40]; // [rsp+6548h] [rbp+6448h] BYREF
  _BYTE v1541[40]; // [rsp+6570h] [rbp+6470h] BYREF
  _BYTE v1542[40]; // [rsp+6598h] [rbp+6498h] BYREF
  _BYTE v1543[40]; // [rsp+65C0h] [rbp+64C0h] BYREF
  _BYTE v1544[40]; // [rsp+65E8h] [rbp+64E8h] BYREF
  _BYTE v1545[40]; // [rsp+6610h] [rbp+6510h] BYREF
  _BYTE v1546[40]; // [rsp+6638h] [rbp+6538h] BYREF
  _BYTE v1547[40]; // [rsp+6660h] [rbp+6560h] BYREF
  _BYTE v1548[40]; // [rsp+6688h] [rbp+6588h] BYREF
  _BYTE v1549[40]; // [rsp+66B0h] [rbp+65B0h] BYREF
  _BYTE v1550[40]; // [rsp+66D8h] [rbp+65D8h] BYREF
  _BYTE v1551[40]; // [rsp+6700h] [rbp+6600h] BYREF
  _BYTE v1552[40]; // [rsp+6728h] [rbp+6628h] BYREF
  _BYTE v1553[40]; // [rsp+6750h] [rbp+6650h] BYREF
  _BYTE v1554[40]; // [rsp+6778h] [rbp+6678h] BYREF
  _BYTE v1555[40]; // [rsp+67A0h] [rbp+66A0h] BYREF
  _BYTE v1556[40]; // [rsp+67C8h] [rbp+66C8h] BYREF
  _BYTE v1557[40]; // [rsp+67F0h] [rbp+66F0h] BYREF
  _BYTE v1558[40]; // [rsp+6818h] [rbp+6718h] BYREF
  _BYTE v1559[40]; // [rsp+6840h] [rbp+6740h] BYREF
  _BYTE v1560[40]; // [rsp+6868h] [rbp+6768h] BYREF
  _BYTE v1561[40]; // [rsp+6890h] [rbp+6790h] BYREF
  _BYTE v1562[40]; // [rsp+68B8h] [rbp+67B8h] BYREF
  _BYTE v1563[40]; // [rsp+68E0h] [rbp+67E0h] BYREF
  _BYTE v1564[40]; // [rsp+6908h] [rbp+6808h] BYREF
  _BYTE v1565[40]; // [rsp+6930h] [rbp+6830h] BYREF
  _BYTE v1566[40]; // [rsp+6958h] [rbp+6858h] BYREF
  _BYTE v1567[40]; // [rsp+6980h] [rbp+6880h] BYREF
  _BYTE v1568[40]; // [rsp+69A8h] [rbp+68A8h] BYREF
  _BYTE v1569[40]; // [rsp+69D0h] [rbp+68D0h] BYREF
  _BYTE v1570[40]; // [rsp+69F8h] [rbp+68F8h] BYREF
  _BYTE v1571[40]; // [rsp+6A20h] [rbp+6920h] BYREF
  _BYTE v1572[40]; // [rsp+6A48h] [rbp+6948h] BYREF
  _BYTE v1573[40]; // [rsp+6A70h] [rbp+6970h] BYREF
  _BYTE v1574[40]; // [rsp+6A98h] [rbp+6998h] BYREF
  _BYTE v1575[40]; // [rsp+6AC0h] [rbp+69C0h] BYREF
  _BYTE v1576[40]; // [rsp+6AE8h] [rbp+69E8h] BYREF
  _BYTE v1577[40]; // [rsp+6B10h] [rbp+6A10h] BYREF
  _BYTE v1578[40]; // [rsp+6B38h] [rbp+6A38h] BYREF
  _BYTE v1579[40]; // [rsp+6B60h] [rbp+6A60h] BYREF
  _BYTE v1580[40]; // [rsp+6B88h] [rbp+6A88h] BYREF
  _BYTE v1581[40]; // [rsp+6BB0h] [rbp+6AB0h] BYREF
  _BYTE v1582[40]; // [rsp+6BD8h] [rbp+6AD8h] BYREF
  _BYTE v1583[40]; // [rsp+6C00h] [rbp+6B00h] BYREF
  _BYTE v1584[40]; // [rsp+6C28h] [rbp+6B28h] BYREF
  _BYTE v1585[40]; // [rsp+6C50h] [rbp+6B50h] BYREF
  _BYTE v1586[40]; // [rsp+6C78h] [rbp+6B78h] BYREF
  _BYTE v1587[40]; // [rsp+6CA0h] [rbp+6BA0h] BYREF
  _BYTE v1588[40]; // [rsp+6CC8h] [rbp+6BC8h] BYREF
  _BYTE v1589[40]; // [rsp+6CF0h] [rbp+6BF0h] BYREF
  _BYTE v1590[40]; // [rsp+6D18h] [rbp+6C18h] BYREF
  _BYTE v1591[40]; // [rsp+6D40h] [rbp+6C40h] BYREF
  _BYTE v1592[40]; // [rsp+6D68h] [rbp+6C68h] BYREF
  _BYTE v1593[40]; // [rsp+6D90h] [rbp+6C90h] BYREF
  _BYTE v1594[40]; // [rsp+6DB8h] [rbp+6CB8h] BYREF
  _BYTE v1595[40]; // [rsp+6DE0h] [rbp+6CE0h] BYREF
  _BYTE v1596[40]; // [rsp+6E08h] [rbp+6D08h] BYREF
  _BYTE v1597[40]; // [rsp+6E30h] [rbp+6D30h] BYREF
  _BYTE v1598[40]; // [rsp+6E58h] [rbp+6D58h] BYREF
  _BYTE v1599[40]; // [rsp+6E80h] [rbp+6D80h] BYREF
  _BYTE v1600[40]; // [rsp+6EA8h] [rbp+6DA8h] BYREF
  _BYTE v1601[40]; // [rsp+6ED0h] [rbp+6DD0h] BYREF
  _BYTE v1602[40]; // [rsp+6EF8h] [rbp+6DF8h] BYREF
  _BYTE v1603[40]; // [rsp+6F20h] [rbp+6E20h] BYREF
  _BYTE v1604[40]; // [rsp+6F48h] [rbp+6E48h] BYREF
  _BYTE v1605[40]; // [rsp+6F70h] [rbp+6E70h] BYREF
  _BYTE v1606[40]; // [rsp+6F98h] [rbp+6E98h] BYREF
  _BYTE v1607[40]; // [rsp+6FC0h] [rbp+6EC0h] BYREF
  _BYTE v1608[40]; // [rsp+6FE8h] [rbp+6EE8h] BYREF
  _BYTE v1609[40]; // [rsp+7010h] [rbp+6F10h] BYREF
  _BYTE v1610[40]; // [rsp+7038h] [rbp+6F38h] BYREF
  _BYTE v1611[40]; // [rsp+7060h] [rbp+6F60h] BYREF
  _BYTE v1612[40]; // [rsp+7088h] [rbp+6F88h] BYREF
  _BYTE v1613[40]; // [rsp+70B0h] [rbp+6FB0h] BYREF
  _BYTE v1614[40]; // [rsp+70D8h] [rbp+6FD8h] BYREF
  _BYTE v1615[40]; // [rsp+7100h] [rbp+7000h] BYREF
  _BYTE v1616[40]; // [rsp+7128h] [rbp+7028h] BYREF
  _BYTE v1617[40]; // [rsp+7150h] [rbp+7050h] BYREF
  _BYTE v1618[40]; // [rsp+7178h] [rbp+7078h] BYREF
  _BYTE v1619[40]; // [rsp+71A0h] [rbp+70A0h] BYREF
  _BYTE v1620[40]; // [rsp+71C8h] [rbp+70C8h] BYREF
  _BYTE v1621[40]; // [rsp+71F0h] [rbp+70F0h] BYREF
  _BYTE v1622[40]; // [rsp+7218h] [rbp+7118h] BYREF
  _BYTE v1623[40]; // [rsp+7240h] [rbp+7140h] BYREF
  _BYTE v1624[40]; // [rsp+7268h] [rbp+7168h] BYREF
  _BYTE v1625[40]; // [rsp+7290h] [rbp+7190h] BYREF
  _BYTE v1626[40]; // [rsp+72B8h] [rbp+71B8h] BYREF
  _BYTE v1627[40]; // [rsp+72E0h] [rbp+71E0h] BYREF
  _BYTE v1628[40]; // [rsp+7308h] [rbp+7208h] BYREF
  _BYTE v1629[40]; // [rsp+7330h] [rbp+7230h] BYREF
  _BYTE v1630[40]; // [rsp+7358h] [rbp+7258h] BYREF
  _BYTE v1631[40]; // [rsp+7380h] [rbp+7280h] BYREF
  _BYTE v1632[40]; // [rsp+73A8h] [rbp+72A8h] BYREF
  _BYTE v1633[40]; // [rsp+73D0h] [rbp+72D0h] BYREF
  _BYTE v1634[40]; // [rsp+73F8h] [rbp+72F8h] BYREF
  _BYTE v1635[40]; // [rsp+7420h] [rbp+7320h] BYREF
  _BYTE v1636[32]; // [rsp+7448h] [rbp+7348h] BYREF
  _BYTE v1637[32]; // [rsp+7468h] [rbp+7368h] BYREF
  _BYTE v1638[8]; // [rsp+7488h] [rbp+7388h] BYREF
  _BYTE v1639[32]; // [rsp+7490h] [rbp+7390h] BYREF
  _BYTE v1640[272]; // [rsp+74B0h] [rbp+73B0h] BYREF
  _BYTE v1641[272]; // [rsp+75C0h] [rbp+74C0h] BYREF
  _BYTE v1642[272]; // [rsp+76D0h] [rbp+75D0h] BYREF
  _BYTE v1643[272]; // [rsp+77E0h] [rbp+76E0h] BYREF
  _BYTE v1644[272]; // [rsp+78F0h] [rbp+77F0h] BYREF
  _BYTE v1645[272]; // [rsp+7A00h] [rbp+7900h] BYREF
  _BYTE v1646[272]; // [rsp+7B10h] [rbp+7A10h] BYREF
  _BYTE v1647[272]; // [rsp+7C20h] [rbp+7B20h] BYREF
  _BYTE v1648[272]; // [rsp+7D30h] [rbp+7C30h] BYREF
  _BYTE v1649[272]; // [rsp+7E40h] [rbp+7D40h] BYREF
  _BYTE v1650[272]; // [rsp+7F50h] [rbp+7E50h] BYREF
  _BYTE v1651[304]; // [rsp+8060h] [rbp+7F60h] BYREF
  _BYTE v1652[304]; // [rsp+8190h] [rbp+8090h] BYREF
  _BYTE v1653[304]; // [rsp+82C0h] [rbp+81C0h] BYREF
  _BYTE v1654[304]; // [rsp+83F0h] [rbp+82F0h] BYREF
  _BYTE v1655[304]; // [rsp+8520h] [rbp+8420h] BYREF
  _BYTE v1656[304]; // [rsp+8650h] [rbp+8550h] BYREF
  _BYTE v1657[304]; // [rsp+8780h] [rbp+8680h] BYREF
  _BYTE v1658[304]; // [rsp+88B0h] [rbp+87B0h] BYREF
  _BYTE v1659[304]; // [rsp+89E0h] [rbp+88E0h] BYREF
  _BYTE v1660[304]; // [rsp+8B10h] [rbp+8A10h] BYREF
  _BYTE v1661[304]; // [rsp+8C40h] [rbp+8B40h] BYREF
  _BYTE v1662[304]; // [rsp+8D70h] [rbp+8C70h] BYREF
  _BYTE v1663[304]; // [rsp+8EA0h] [rbp+8DA0h] BYREF
  _BYTE v1664[304]; // [rsp+8FD0h] [rbp+8ED0h] BYREF
  _BYTE v1665[304]; // [rsp+9100h] [rbp+9000h] BYREF
  _BYTE v1666[304]; // [rsp+9230h] [rbp+9130h] BYREF
  _BYTE v1667[304]; // [rsp+9360h] [rbp+9260h] BYREF
  _BYTE v1668[304]; // [rsp+9490h] [rbp+9390h] BYREF
  _BYTE v1669[304]; // [rsp+95C0h] [rbp+94C0h] BYREF
  _BYTE v1670[304]; // [rsp+96F0h] [rbp+95F0h] BYREF
  _BYTE v1671[304]; // [rsp+9820h] [rbp+9720h] BYREF
  _BYTE v1672[304]; // [rsp+9950h] [rbp+9850h] BYREF
  _BYTE v1673[304]; // [rsp+9A80h] [rbp+9980h] BYREF
  _BYTE v1674[304]; // [rsp+9BB0h] [rbp+9AB0h] BYREF
  _BYTE v1675[304]; // [rsp+9CE0h] [rbp+9BE0h] BYREF
  _BYTE v1676[304]; // [rsp+9E10h] [rbp+9D10h] BYREF
  _BYTE v1677[304]; // [rsp+9F40h] [rbp+9E40h] BYREF
  _BYTE v1678[304]; // [rsp+A070h] [rbp+9F70h] BYREF
  _BYTE v1679[304]; // [rsp+A1A0h] [rbp+A0A0h] BYREF
  _BYTE v1680[304]; // [rsp+A2D0h] [rbp+A1D0h] BYREF
  _BYTE v1681[304]; // [rsp+A400h] [rbp+A300h] BYREF
  _BYTE v1682[304]; // [rsp+A530h] [rbp+A430h] BYREF
  _BYTE v1683[304]; // [rsp+A660h] [rbp+A560h] BYREF
  _BYTE v1684[304]; // [rsp+A790h] [rbp+A690h] BYREF
  _BYTE v1685[304]; // [rsp+A8C0h] [rbp+A7C0h] BYREF
  _BYTE v1686[304]; // [rsp+A9F0h] [rbp+A8F0h] BYREF
  _BYTE v1687[304]; // [rsp+AB20h] [rbp+AA20h] BYREF
  _BYTE v1688[304]; // [rsp+AC50h] [rbp+AB50h] BYREF
  _BYTE v1689[304]; // [rsp+AD80h] [rbp+AC80h] BYREF
  _BYTE v1690[304]; // [rsp+AEB0h] [rbp+ADB0h] BYREF
  _BYTE v1691[304]; // [rsp+AFE0h] [rbp+AEE0h] BYREF
  _BYTE v1692[304]; // [rsp+B110h] [rbp+B010h] BYREF
  _BYTE v1693[304]; // [rsp+B240h] [rbp+B140h] BYREF
  _BYTE v1694[304]; // [rsp+B370h] [rbp+B270h] BYREF
  _BYTE v1695[304]; // [rsp+B4A0h] [rbp+B3A0h] BYREF
  _BYTE v1696[304]; // [rsp+B5D0h] [rbp+B4D0h] BYREF
  _BYTE v1697[304]; // [rsp+B700h] [rbp+B600h] BYREF
  _BYTE v1698[304]; // [rsp+B830h] [rbp+B730h] BYREF
  _BYTE v1699[304]; // [rsp+B960h] [rbp+B860h] BYREF
  _BYTE v1700[304]; // [rsp+BA90h] [rbp+B990h] BYREF
  _BYTE v1701[304]; // [rsp+BBC0h] [rbp+BAC0h] BYREF
  _BYTE v1702[304]; // [rsp+BCF0h] [rbp+BBF0h] BYREF
  _BYTE v1703[304]; // [rsp+BE20h] [rbp+BD20h] BYREF
  _BYTE v1704[304]; // [rsp+BF50h] [rbp+BE50h] BYREF
  _BYTE v1705[304]; // [rsp+C080h] [rbp+BF80h] BYREF
  _BYTE v1706[304]; // [rsp+C1B0h] [rbp+C0B0h] BYREF
  _BYTE v1707[304]; // [rsp+C2E0h] [rbp+C1E0h] BYREF
  _BYTE v1708[304]; // [rsp+C410h] [rbp+C310h] BYREF
  _BYTE v1709[304]; // [rsp+C540h] [rbp+C440h] BYREF

  v848 = 5;
  std::deque<enum Uev::SettingSource>::deque<enum Uev::SettingSource>(v867);
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v867, &v848);
  LOBYTE(v2) = v846;
  boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert<std::vector<enum Uev::SettingSource>>(
    v867,
    v865,
    `boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert_to_container<std::vector<enum Uev::SettingSource>>'::`2'::c,
    v2);
  std::vector<enum Uev::SettingSource>::operator=((char *)this + 152, v865);
  std::vector<enum Uev::SettingSource>::_Tidy(v865);
  std::deque<enum Uev::SettingSource>::~deque<enum Uev::SettingSource>(v867);
  v849 = 0;
  std::deque<enum Uev::SettingSource>::deque<enum Uev::SettingSource>(v857);
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v857, &v849);
  v850 = 1;
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v857, &v850);
  v851 = 2;
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v857, &v851);
  v852 = 3;
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v857, &v852);
  LOBYTE(v3) = v846;
  boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert<std::vector<enum Uev::SettingSource>>(
    v857,
    v861,
    `boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert_to_container<std::vector<enum Uev::SettingSource>>'::`2'::c,
    v3);
  std::vector<enum Uev::SettingSource>::operator=((char *)this + 176, v861);
  std::vector<enum Uev::SettingSource>::_Tidy(v861);
  std::deque<enum Uev::SettingSource>::~deque<enum Uev::SettingSource>(v857);
  v853 = 1;
  std::deque<enum Uev::SettingSource>::deque<enum Uev::SettingSource>(v866);
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v866, &v853);
  v854 = 3;
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v866, &v854);
  LOBYTE(v4) = v846;
  boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert<std::vector<enum Uev::SettingSource>>(
    v866,
    v862,
    `boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert_to_container<std::vector<enum Uev::SettingSource>>'::`2'::c,
    v4);
  v5 = (_DWORD)this + 200;
  std::vector<enum Uev::SettingSource>::operator=((char *)this + 200, v862);
  std::vector<enum Uev::SettingSource>::_Tidy(v862);
  std::deque<enum Uev::SettingSource>::~deque<enum Uev::SettingSource>(v866);
  v855 = 2;
  std::deque<enum Uev::SettingSource>::deque<enum Uev::SettingSource>(v868);
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v868, &v855);
  LOBYTE(v6) = v846;
  boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert<std::vector<enum Uev::SettingSource>>(
    v868,
    v863,
    `boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert_to_container<std::vector<enum Uev::SettingSource>>'::`2'::c,
    v6);
  v7 = (_DWORD)this + 224;
  std::vector<enum Uev::SettingSource>::operator=((char *)this + 224, v863);
  std::vector<enum Uev::SettingSource>::_Tidy(v863);
  std::deque<enum Uev::SettingSource>::~deque<enum Uev::SettingSource>(v868);
  v856 = 3;
  std::deque<enum Uev::SettingSource>::deque<enum Uev::SettingSource>(v869);
  std::deque<enum Uev::SettingSource>::_Emplace_back_internal<enum Uev::SettingSource>(v869, &v856);
  LOBYTE(v8) = v846;
  boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert<std::vector<enum Uev::SettingSource>>(
    v869,
    v864,
    `boost::assign_detail::converter<boost::assign_detail::generic_list<enum Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<enum Uev::SettingSource>>>>::convert_to_container<std::vector<enum Uev::SettingSource>>'::`2'::c,
    v8);
  v9 = (_DWORD)this + 248;
  std::vector<enum Uev::SettingSource>::operator=((char *)this + 248, v864);
  std::vector<enum Uev::SettingSource>::_Tidy(v864);
  std::deque<enum Uev::SettingSource>::~deque<enum Uev::SettingSource>(v869);
  std::wstring::wstring(v1248, L"MaxPackageSizeInBytes");
  v1272 = 0;
  memset(v1271, 0, sizeof(v1271));
  v1270 = 0;
  memset(v1269, 0, sizeof(v1269));
  v847 = std::wstring::wstring(v968, v1248);
  v10 = *((_QWORD *)this + 17);
  std::wstring::wstring(v870, v847);
  LOBYTE(v11) = boost::placeholders::_4;
  v12 = boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(
          v1638,
          v10,
          v11,
          v870,
          boost::placeholders::_4);
  v858 =  Uev::ConfigUtil::`vcall'{176,{flat}};
  boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(
    v859,
    v12);
  std::wstring::_Tidy_deallocate(v1639);
  std::wstring::_Tidy_deallocate(v847);
  *(_QWORD *)&v844 = &v858;
  v871 = v858;
  boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(
    v872,
    v859);
  boost::function2<bool,enum Uev::SettingSource,long &>::function2<bool,enum Uev::SettingSource,long &>(v1635, &v871, 0);
  std::wstring::_Tidy_deallocate(v860);
  v13 = std::wstring::wstring(v969, v1248);
  LOBYTE(v14) = boost::placeholders::_4;
  *(_QWORD *)&v844 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
                       (unsigned int)&v1132,
                       (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
                       *((_QWORD *)this + 17),
                       v14,
                       v13);
  v875 = *(_QWORD *)v844;
  boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(
    v876,
    v844 + 8);
  boost::function3<bool,enum Uev::SettingSource,unsigned long const &,long &>::function3<bool,enum Uev::SettingSource,unsigned long const &,long &>(
    v1634,
    &v875,
    0);
  std::wstring::_Tidy_deallocate(v844 + 16);
  v15 = std::wstring::wstring(v970, v1248);
  LOBYTE(v16) = boost::placeholders::_4;
  *(_QWORD *)&v844 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
                       (unsigned int)&v1133,
                       (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
                       *((_QWORD *)this + 17),
                       v16,
                       v15);
  v873 = *(_QWORD *)v844;
  boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(
    v874,
    v844 + 8);
  boost::function3<bool,enum Uev::SettingSource,unsigned long &,long &>::function3<bool,enum Uev::SettingSource,unsigned long &,long &>(
    v1633,
    &v873,
    0);
  std::wstring::_Tidy_deallocate(v844 + 16);
  v17 = Uev::Setting<unsigned long>::Setting<unsigned long>(
          (unsigned int)v1651,
          (unsigned int)v1248,
          (int)this + 176,
          (unsigned int)v1633,
          (__int64)v1634,
          (__int64)v1635,
          (__int64)v1269,
          (__int64)v1271);
  Uev::Setting<unsigned long>::operator=((char *)this + 272, v17);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1651);
  boost::function<bool (void)>::~function<bool (void)>(v1633);
  boost::function<bool (void)>::~function<bool (void)>(v1634);
  boost::function<bool (void)>::~function<bool (void)>(v1635);
  boost::function<bool (void)>::~function<bool (void)>(v1269);
  boost::function<bool (void)>::~function<bool (void)>(v1271);
  Uev::Configuration::InsertSettingMap(this, v1248, (char *)this + 272);
  boost::filesystem::path::~path((boost::filesystem::path *)v1248);
  std::wstring::wstring(v1249, L"SyncEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_b515e3f4d38b63b42327e4d17ca6fbf7___(
    v1290,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1289, 0);
  v18 = std::wstring::wstring(v971, v1249);
  v19 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v20) = boost::placeholders::_4;
  v21 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1134,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v19,
          v20,
          v18);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1288, v21, 0);
  v22 = std::wstring::wstring(v972, v1249);
  v23 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v24) = boost::placeholders::_4;
  v25 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1135,
          (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
          v23,
          v24,
          v22);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1287,
    v25,
    0);
  v26 = std::wstring::wstring(v973, v1249);
  v27 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v28) = boost::placeholders::_4;
  v29 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1136,
          (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
          v27,
          v28,
          v26);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1286,
    v29,
    0);
  v30 = Uev::Setting<bool>::Setting<bool>(
          (unsigned int)v1652,
          (unsigned int)v1249,
          (int)this + 176,
          (unsigned int)v1286,
          (__int64)v1287,
          (__int64)v1288,
          (__int64)v1289,
          (__int64)v1290);
  Uev::Setting<unsigned long>::operator=((char *)this + 576, v30);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1652);
  boost::function<bool (void)>::~function<bool (void)>(v1286);
  boost::function<bool (void)>::~function<bool (void)>(v1287);
  boost::function<bool (void)>::~function<bool (void)>(v1288);
  boost::function<bool (void)>::~function<bool (void)>(v1289);
  boost::function<bool (void)>::~function<bool (void)>(v1290);
  Uev::Configuration::InsertSettingMap(this, v1249, (char *)this + 576);
  boost::filesystem::path::~path((boost::filesystem::path *)v1249);
  std::wstring::wstring(v1250, L"SyncTimeoutInMilliseconds");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_6ab8af53adab39dd1519741d436e1343___(
    v1295,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1294, 0);
  v31 = std::wstring::wstring(v974, v1250);
  v32 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v33) = boost::placeholders::_4;
  v34 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1137,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v32,
          v33,
          v31);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1293, v34, 0);
  v35 = std::wstring::wstring(v975, v1250);
  v36 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v37) = boost::placeholders::_4;
  v38 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1138,
          (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
          v36,
          v37,
          v35);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1292,
    v38,
    0);
  v39 = std::wstring::wstring(v976, v1250);
  v40 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v41) = boost::placeholders::_4;
  v42 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1139,
          (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
          v40,
          v41,
          v39);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1291,
    v42,
    0);
  v43 = Uev::Setting<unsigned long>::Setting<unsigned long>(
          (unsigned int)v1653,
          (unsigned int)v1250,
          (int)this + 176,
          (unsigned int)v1291,
          (__int64)v1292,
          (__int64)v1293,
          (__int64)v1294,
          (__int64)v1295);
  Uev::Setting<unsigned long>::operator=((char *)this + 880, v43);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1653);
  boost::function<bool (void)>::~function<bool (void)>(v1291);
  boost::function<bool (void)>::~function<bool (void)>(v1292);
  boost::function<bool (void)>::~function<bool (void)>(v1293);
  boost::function<bool (void)>::~function<bool (void)>(v1294);
  boost::function<bool (void)>::~function<bool (void)>(v1295);
  Uev::Configuration::InsertSettingMap(this, v1250, (char *)this + 880);
  boost::filesystem::path::~path((boost::filesystem::path *)v1250);
  std::wstring::wstring(v1251, L"SyncMethod");
  boost::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void__::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void____lambda_1a3dd1c6ac05a4f22462cba0041f4077___(
    v1300,
    0,
    0);
  v44 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v45) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,std::wstring const &,Uev::ConfigUtil *,boost::arg<1>>(
                      v956,
                       Uev::ConfigUtil::`vcall'{280,{flat}},
                      v44,
                      v45);
  boost::function<bool (std::wstring const &)>::function<bool (std::wstring const &)>(v1299, &v844, 0);
  v46 = std::wstring::wstring(v977, v1251);
  v47 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v48) = boost::placeholders::_4;
  v49 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1140,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v47,
          v48,
          v46);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1298, v49, 0);
  v50 = std::wstring::wstring(v978, v1251);
  v51 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v52) = boost::placeholders::_4;
  v53 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1141,
          (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
          v51,
          v52,
          v50);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1297,
    v53,
    0);
  v54 = std::wstring::wstring(v979, v1251);
  v55 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v56) = boost::placeholders::_4;
  v57 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1142,
          (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
          v55,
          v56,
          v54);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1296,
    v57,
    0);
  v58 = Uev::Setting<std::wstring>::Setting<std::wstring>(
          (unsigned int)v1654,
          (unsigned int)v1251,
          (int)this + 176,
          (unsigned int)v1296,
          (__int64)v1297,
          (__int64)v1298,
          (__int64)v1299,
          (__int64)v1300);
  Uev::Setting<std::wstring>::operator=((char *)this + 1184, v58);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1654);
  boost::function<bool (void)>::~function<bool (void)>(v1296);
  boost::function<bool (void)>::~function<bool (void)>(v1297);
  boost::function<bool (void)>::~function<bool (void)>(v1298);
  boost::function<bool (void)>::~function<bool (void)>(v1299);
  boost::function<bool (void)>::~function<bool (void)>(v1300);
  Uev::Configuration::InsertSettingMap(this, v1251, (char *)this + 1184);
  boost::filesystem::path::~path((boost::filesystem::path *)v1251);
  std::wstring::wstring(v1252, L"SettingsStoragePath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1305, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1304, 0);
  v59 = std::wstring::wstring(v980, v1252);
  v60 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v61) = boost::placeholders::_4;
  v62 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1143,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v60,
          v61,
          v59);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1303, v62, 0);
  v63 = std::wstring::wstring(v981, v1252);
  v64 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v65) = boost::placeholders::_4;
  v66 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1144,
          (unsigned int) Uev::ConfigUtil::`vcall'{128,{flat}},
          v64,
          v65,
          v63);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1302,
    v66,
    0);
  v67 = std::wstring::wstring(v982, v1252);
  v68 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v811) = boost::placeholders::_4;
  LOBYTE(v778) = boost::placeholders::_4;
  LOBYTE(v69) = boost::placeholders::_4;
  v70 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>,bool>(
          (unsigned int)&v1209,
          (unsigned int) Uev::ConfigUtil::`vcall'{80,{flat}},
          v68,
          v69,
          v67,
          v778,
          v811,
          1);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1301,
    v70,
    0);
  v71 = Uev::Setting<std::wstring>::Setting<std::wstring>(
          (unsigned int)v1655,
          (unsigned int)v1252,
          (int)this + 176,
          (unsigned int)v1301,
          (__int64)v1302,
          (__int64)v1303,
          (__int64)v1304,
          (__int64)v1305);
  Uev::Setting<std::wstring>::operator=((char *)this + 1488, v71);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1655);
  boost::function<bool (void)>::~function<bool (void)>(v1301);
  boost::function<bool (void)>::~function<bool (void)>(v1302);
  boost::function<bool (void)>::~function<bool (void)>(v1303);
  boost::function<bool (void)>::~function<bool (void)>(v1304);
  boost::function<bool (void)>::~function<bool (void)>(v1305);
  v72 = std::operator+<wchar_t>(v1637, v1252, Uev::Configuration::s_Expand);
  Uev::Configuration::InsertSettingMap(this, v72, (char *)this + 1488);
  boost::filesystem::path::~path((boost::filesystem::path *)v1637);
  boost::filesystem::path::~path((boost::filesystem::path *)v1252);
  std::wstring::wstring(v1212, L"SettingsStoragePath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1310, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1309, 0);
  v73 = std::wstring::wstring(v984, v1212);
  v74 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v75) = boost::placeholders::_4;
  v76 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1145,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v74,
          v75,
          v73);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1308, v76, 0);
  v77 = std::wstring::wstring(v985, v1212);
  v78 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v79) = boost::placeholders::_4;
  v80 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1146,
          (unsigned int) Uev::ConfigUtil::`vcall'{128,{flat}},
          v78,
          v79,
          v77);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1307,
    v80,
    0);
  v81 = std::wstring::wstring(v986, v1212);
  v82 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v812) = boost::placeholders::_4;
  LOBYTE(v779) = boost::placeholders::_4;
  LOBYTE(v83) = boost::placeholders::_4;
  v84 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>,bool>(
          (unsigned int)&v1208,
          (unsigned int) Uev::ConfigUtil::`vcall'{80,{flat}},
          v82,
          v83,
          v81,
          v779,
          v812,
          0);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1306,
    v84,
    0);
  v85 = Uev::Setting<std::wstring>::Setting<std::wstring>(
          (unsigned int)v1656,
          (unsigned int)v1212,
          (int)this + 176,
          (unsigned int)v1306,
          (__int64)v1307,
          (__int64)v1308,
          (__int64)v1309,
          (__int64)v1310);
  Uev::Setting<std::wstring>::operator=((char *)this + 1792, v85);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1656);
  boost::function<bool (void)>::~function<bool (void)>(v1306);
  boost::function<bool (void)>::~function<bool (void)>(v1307);
  boost::function<bool (void)>::~function<bool (void)>(v1308);
  boost::function<bool (void)>::~function<bool (void)>(v1309);
  boost::function<bool (void)>::~function<bool (void)>(v1310);
  Uev::Configuration::InsertSettingMap(this, v1212, (char *)this + 1792);
  boost::filesystem::path::~path((boost::filesystem::path *)v1212);
  std::wstring::wstring(v1213, L"SettingsTemplateCatalogPath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1315, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1314, 0);
  v86 = std::wstring::wstring(v987, v1213);
  v87 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v88) = boost::placeholders::_4;
  v89 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
          (unsigned int)&v1147,
          (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
          v87,
          v88,
          v86);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1313, v89, 0);
  v90 = std::wstring::wstring(v988, v1213);
  v91 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v92) = boost::placeholders::_4;
  v93 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
          (unsigned int)&v1148,
          (unsigned int) Uev::ConfigUtil::`vcall'{128,{flat}},
          v91,
          v92,
          v90);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1312,
    v93,
    0);
  v94 = std::wstring::wstring(v989, v1213);
  v95 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v813) = boost::placeholders::_4;
  LOBYTE(v780) = boost::placeholders::_4;
  LOBYTE(v96) = boost::placeholders::_4;
  v97 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>,bool>(
          (unsigned int)&v1210,
          (unsigned int) Uev::ConfigUtil::`vcall'{80,{flat}},
          v95,
          v96,
          v94,
          v780,
          v813,
          1);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1311,
    v97,
    0);
  v98 = Uev::Setting<std::wstring>::Setting<std::wstring>(
          (unsigned int)v1657,
          (unsigned int)v1213,
          v5,
          (unsigned int)v1311,
          (__int64)v1312,
          (__int64)v1313,
          (__int64)v1314,
          (__int64)v1315);
  Uev::Setting<std::wstring>::operator=((char *)this + 2096, v98);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1657);
  boost::function<bool (void)>::~function<bool (void)>(v1311);
  boost::function<bool (void)>::~function<bool (void)>(v1312);
  boost::function<bool (void)>::~function<bool (void)>(v1313);
  boost::function<bool (void)>::~function<bool (void)>(v1314);
  boost::function<bool (void)>::~function<bool (void)>(v1315);
  v99 = std::operator+<wchar_t>(v1636, v1213, Uev::Configuration::s_Expand);
  Uev::Configuration::InsertSettingMap(this, v99, (char *)this + 2096);
  boost::filesystem::path::~path((boost::filesystem::path *)v1636);
  boost::filesystem::path::~path((boost::filesystem::path *)v1213);
  std::wstring::wstring(v1214, L"SettingsTemplateCatalogPath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1320, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1319, 0);
  v100 = std::wstring::wstring(v991, v1214);
  v101 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v102) = boost::placeholders::_4;
  v103 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1149,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v101,
           v102,
           v100);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1318,
    v103,
    0);
  v104 = std::wstring::wstring(v992, v1214);
  v105 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v106) = boost::placeholders::_4;
  v107 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1150,
           (unsigned int) Uev::ConfigUtil::`vcall'{128,{flat}},
           v105,
           v106,
           v104);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1317,
    v107,
    0);
  v108 = std::wstring::wstring(v993, v1214);
  v109 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v814) = boost::placeholders::_4;
  LOBYTE(v781) = boost::placeholders::_4;
  LOBYTE(v110) = boost::placeholders::_4;
  v111 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>,bool>(
           (unsigned int)&v1211,
           (unsigned int) Uev::ConfigUtil::`vcall'{80,{flat}},
           v109,
           v110,
           v108,
           v781,
           v814,
           0);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1316,
    v111,
    0);
  v112 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1658,
           (unsigned int)v1214,
           v5,
           (unsigned int)v1316,
           (__int64)v1317,
           (__int64)v1318,
           (__int64)v1319,
           (__int64)v1320);
  Uev::Setting<std::wstring>::operator=((char *)this + 2400, v112);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1658);
  boost::function<bool (void)>::~function<bool (void)>(v1316);
  boost::function<bool (void)>::~function<bool (void)>(v1317);
  boost::function<bool (void)>::~function<bool (void)>(v1318);
  boost::function<bool (void)>::~function<bool (void)>(v1319);
  boost::function<bool (void)>::~function<bool (void)>(v1320);
  Uev::Configuration::InsertSettingMap(this, v1214, (char *)this + 2400);
  boost::filesystem::path::~path((boost::filesystem::path *)v1214);
  std::wstring::wstring(v1215, L"SettingsImportNotifyEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_ff83e295f3ecd6c676c01e7b150f93d1___(
    v1325,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1324, 0);
  v113 = std::wstring::wstring(v994, v1215);
  v114 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v115) = boost::placeholders::_4;
  v116 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1151,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v114,
           v115,
           v113);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1323,
    v116,
    0);
  v117 = std::wstring::wstring(v995, v1215);
  v118 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v119) = boost::placeholders::_4;
  v120 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1152,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v118,
           v119,
           v117);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1322,
    v120,
    0);
  v121 = std::wstring::wstring(v996, v1215);
  v122 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v123) = boost::placeholders::_4;
  v124 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1153,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v122,
           v123,
           v121);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1321,
    v124,
    0);
  v125 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1659,
           (unsigned int)v1215,
           (int)this + 176,
           (unsigned int)v1321,
           (__int64)v1322,
           (__int64)v1323,
           (__int64)v1324,
           (__int64)v1325);
  Uev::Setting<unsigned long>::operator=((char *)this + 2704, v125);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1659);
  boost::function<bool (void)>::~function<bool (void)>(v1321);
  boost::function<bool (void)>::~function<bool (void)>(v1322);
  boost::function<bool (void)>::~function<bool (void)>(v1323);
  boost::function<bool (void)>::~function<bool (void)>(v1324);
  boost::function<bool (void)>::~function<bool (void)>(v1325);
  Uev::Configuration::InsertSettingMap(this, v1215, (char *)this + 2704);
  boost::filesystem::path::~path((boost::filesystem::path *)v1215);
  std::wstring::wstring(v1216, L"SettingsImportNotifyDelayInSeconds");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_196be8d530a56c1d71f0d25446e1485d___(
    v1330,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1329, 0);
  v126 = std::wstring::wstring(v997, v1216);
  v127 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v128) = boost::placeholders::_4;
  v129 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1154,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v127,
           v128,
           v126);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1328,
    v129,
    0);
  v130 = std::wstring::wstring(v998, v1216);
  v131 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v132) = boost::placeholders::_4;
  v133 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1155,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v131,
           v132,
           v130);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1327,
    v133,
    0);
  v134 = std::wstring::wstring(v999, v1216);
  v135 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v136) = boost::placeholders::_4;
  v137 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1156,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v135,
           v136,
           v134);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1326,
    v137,
    0);
  v138 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1660,
           (unsigned int)v1216,
           (int)this + 176,
           (unsigned int)v1326,
           (__int64)v1327,
           (__int64)v1328,
           (__int64)v1329,
           (__int64)v1330);
  Uev::Setting<unsigned long>::operator=((char *)this + 3008, v138);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1660);
  boost::function<bool (void)>::~function<bool (void)>(v1326);
  boost::function<bool (void)>::~function<bool (void)>(v1327);
  boost::function<bool (void)>::~function<bool (void)>(v1328);
  boost::function<bool (void)>::~function<bool (void)>(v1329);
  boost::function<bool (void)>::~function<bool (void)>(v1330);
  Uev::Configuration::InsertSettingMap(this, v1216, (char *)this + 3008);
  boost::filesystem::path::~path((boost::filesystem::path *)v1216);
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_78628c2aa6757c44ba48a45c5e1b35de___(
    v1335,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1334, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1333, 0);
  v139 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v815) = boost::placeholders::_4;
  LOBYTE(v782) = boost::placeholders::_4;
  LOBYTE(v750) = boost::placeholders::_4;
  LOBYTE(v140) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v961,
                       Uev::ConfigUtil::`vcall'{296,{flat}},
                      v139,
                      v140,
                      v750,
                      v782,
                      v815);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,bool const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,bool const &,long &)>(
    v1332,
    &v844,
    0);
  v141 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v816) = boost::placeholders::_4;
  LOBYTE(v783) = boost::placeholders::_4;
  LOBYTE(v751) = boost::placeholders::_4;
  LOBYTE(v142) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v962,
                       Uev::ConfigUtil::`vcall'{288,{flat}},
                      v141,
                      v142,
                      v751,
                      v783,
                      v816);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,bool &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,bool &,long &)>(
    v1331,
    &v844,
    0);
  v143 = Uev::SettingGroup<bool>::SettingGroup<bool>(
           (unsigned int)v1640,
           (int)this + 176,
           (unsigned int)v1331,
           (unsigned int)v1332,
           (__int64)v1333,
           (__int64)v1334,
           (__int64)v1335);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 3312, v143);
  Uev::SettingGroup<bool>::~SettingGroup<bool>(v1640);
  boost::function<bool (void)>::~function<bool (void)>(v1331);
  boost::function<bool (void)>::~function<bool (void)>(v1332);
  boost::function<bool (void)>::~function<bool (void)>(v1333);
  boost::function<bool (void)>::~function<bool (void)>(v1334);
  boost::function<bool (void)>::~function<bool (void)>(v1335);
  std::wstring::wstring(v1275, L"TemplateEnabled");
  Uev::Configuration::InsertGroupSettingMap(this, v1275, (char *)this + 3312);
  boost::filesystem::path::~path((boost::filesystem::path *)v1275);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1340, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1339, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1338, 0);
  v144 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v817) = boost::placeholders::_4;
  LOBYTE(v784) = boost::placeholders::_4;
  LOBYTE(v752) = boost::placeholders::_4;
  LOBYTE(v145) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v963,
                       Uev::ConfigUtil::`vcall'{312,{flat}},
                      v144,
                      v145,
                      v752,
                      v784,
                      v817);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>(
    v1337,
    &v844,
    0);
  v146 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v818) = boost::placeholders::_4;
  LOBYTE(v785) = boost::placeholders::_4;
  LOBYTE(v753) = boost::placeholders::_4;
  LOBYTE(v147) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v964,
                       Uev::ConfigUtil::`vcall'{304,{flat}},
                      v146,
                      v147,
                      v753,
                      v785,
                      v818);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring &,long &)>(
    v1336,
    &v844,
    0);
  v148 = Uev::SettingGroup<std::wstring>::SettingGroup<std::wstring>(
           (unsigned int)v1641,
           v7,
           (unsigned int)v1336,
           (unsigned int)v1337,
           (__int64)v1338,
           (__int64)v1339,
           (__int64)v1340);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 10784, v148);
  Uev::SettingGroup<std::wstring>::~SettingGroup<std::wstring>(v1641);
  boost::function<bool (void)>::~function<bool (void)>(v1336);
  boost::function<bool (void)>::~function<bool (void)>(v1337);
  boost::function<bool (void)>::~function<bool (void)>(v1338);
  boost::function<bool (void)>::~function<bool (void)>(v1339);
  boost::function<bool (void)>::~function<bool (void)>(v1340);
  std::wstring::wstring(v1276, L"LastWriterWins");
  Uev::Configuration::InsertGroupSettingMap(this, v1276, (char *)this + 10784);
  boost::filesystem::path::~path((boost::filesystem::path *)v1276);
  std::wstring::wstring(v1217, L"OptimalMaxPackageSizeInBytes");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_b98ccdd594d80039023b4148c9f5c5a6___(
    v1345,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1344, 0);
  v149 = std::wstring::wstring(v1000, v1217);
  v150 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v151) = boost::placeholders::_4;
  v152 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1157,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v150,
           v151,
           v149);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1343,
    v152,
    0);
  v153 = std::wstring::wstring(v1001, v1217);
  v154 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v155) = boost::placeholders::_4;
  v156 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1158,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v154,
           v155,
           v153);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1342,
    v156,
    0);
  v157 = std::wstring::wstring(v1002, v1217);
  v158 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v159) = boost::placeholders::_4;
  v160 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1159,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v158,
           v159,
           v157);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1341,
    v160,
    0);
  v161 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1661,
           (unsigned int)v1217,
           (int)this + 176,
           (unsigned int)v1341,
           (__int64)v1342,
           (__int64)v1343,
           (__int64)v1344,
           (__int64)v1345);
  Uev::Setting<unsigned long>::operator=((char *)this + 11056, v161);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1661);
  boost::function<bool (void)>::~function<bool (void)>(v1341);
  boost::function<bool (void)>::~function<bool (void)>(v1342);
  boost::function<bool (void)>::~function<bool (void)>(v1343);
  boost::function<bool (void)>::~function<bool (void)>(v1344);
  boost::function<bool (void)>::~function<bool (void)>(v1345);
  Uev::Configuration::InsertSettingMap(this, v1217, (char *)this + 11056);
  boost::filesystem::path::~path((boost::filesystem::path *)v1217);
  std::wstring::wstring(v1218, L"OptimalMaxNumExternalFiles");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_00a7fa26a962e5711fec5fc8fc065262___(
    v1350,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1349, 0);
  v162 = std::wstring::wstring(v1003, v1218);
  v163 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v164) = boost::placeholders::_4;
  v165 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1160,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v163,
           v164,
           v162);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1348,
    v165,
    0);
  v166 = std::wstring::wstring(v1004, v1218);
  v167 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v168) = boost::placeholders::_4;
  v169 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1161,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v167,
           v168,
           v166);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1347,
    v169,
    0);
  v170 = std::wstring::wstring(v1005, v1218);
  v171 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v172) = boost::placeholders::_4;
  v173 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1162,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v171,
           v172,
           v170);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1346,
    v173,
    0);
  v174 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1662,
           (unsigned int)v1218,
           (int)this + 176,
           (unsigned int)v1346,
           (__int64)v1347,
           (__int64)v1348,
           (__int64)v1349,
           (__int64)v1350);
  Uev::Setting<unsigned long>::operator=((char *)this + 11360, v174);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1662);
  boost::function<bool (void)>::~function<bool (void)>(v1346);
  boost::function<bool (void)>::~function<bool (void)>(v1347);
  boost::function<bool (void)>::~function<bool (void)>(v1348);
  boost::function<bool (void)>::~function<bool (void)>(v1349);
  boost::function<bool (void)>::~function<bool (void)>(v1350);
  Uev::Configuration::InsertSettingMap(this, v1218, (char *)this + 11360);
  boost::filesystem::path::~path((boost::filesystem::path *)v1218);
  std::wstring::wstring(v1219, L"OptimalMinExternalFileSizeInBytes");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_145d2b15678ffa150139d9c40244bb49___(
    v1355,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1354, 0);
  v175 = std::wstring::wstring(v1006, v1219);
  v176 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v177) = boost::placeholders::_4;
  v178 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1163,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v176,
           v177,
           v175);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1353,
    v178,
    0);
  v179 = std::wstring::wstring(v1007, v1219);
  v180 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v181) = boost::placeholders::_4;
  v182 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1164,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v180,
           v181,
           v179);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1352,
    v182,
    0);
  v183 = std::wstring::wstring(v1008, v1219);
  v184 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v185) = boost::placeholders::_4;
  v186 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1165,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v184,
           v185,
           v183);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1351,
    v186,
    0);
  v187 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1663,
           (unsigned int)v1219,
           (int)this + 176,
           (unsigned int)v1351,
           (__int64)v1352,
           (__int64)v1353,
           (__int64)v1354,
           (__int64)v1355);
  Uev::Setting<unsigned long>::operator=((char *)this + 11664, v187);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1663);
  boost::function<bool (void)>::~function<bool (void)>(v1351);
  boost::function<bool (void)>::~function<bool (void)>(v1352);
  boost::function<bool (void)>::~function<bool (void)>(v1353);
  boost::function<bool (void)>::~function<bool (void)>(v1354);
  boost::function<bool (void)>::~function<bool (void)>(v1355);
  Uev::Configuration::InsertSettingMap(this, v1219, (char *)this + 11664);
  boost::filesystem::path::~path((boost::filesystem::path *)v1219);
  std::wstring::wstring(v1220, L"DebugEnableDifferenceLog");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_e2db3869f49042c5ba94f9b21209cc7c___(
    v1360,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1359, 0);
  v188 = std::wstring::wstring(v1009, v1220);
  v189 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v190) = boost::placeholders::_4;
  v191 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1166,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v189,
           v190,
           v188);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1358,
    v191,
    0);
  v192 = std::wstring::wstring(v1010, v1220);
  v193 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v194) = boost::placeholders::_4;
  v195 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1167,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v193,
           v194,
           v192);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1357,
    v195,
    0);
  v196 = std::wstring::wstring(v1011, v1220);
  v197 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v198) = boost::placeholders::_4;
  v199 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1168,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v197,
           v198,
           v196);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1356,
    v199,
    0);
  v200 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1664,
           (unsigned int)v1220,
           (int)this + 176,
           (unsigned int)v1356,
           (__int64)v1357,
           (__int64)v1358,
           (__int64)v1359,
           (__int64)v1360);
  Uev::Setting<unsigned long>::operator=((char *)this + 11968, v200);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1664);
  boost::function<bool (void)>::~function<bool (void)>(v1356);
  boost::function<bool (void)>::~function<bool (void)>(v1357);
  boost::function<bool (void)>::~function<bool (void)>(v1358);
  boost::function<bool (void)>::~function<bool (void)>(v1359);
  boost::function<bool (void)>::~function<bool (void)>(v1360);
  Uev::Configuration::InsertSettingMap(this, v1220, (char *)this + 11968);
  boost::filesystem::path::~path((boost::filesystem::path *)v1220);
  std::wstring::wstring(v1221, L"LastWriterThreshold");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_ac2aa9f215af2edecacc4d4bfa615465___(
    v1365,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1364, 0);
  v201 = std::wstring::wstring(v1012, v1221);
  v202 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v203) = boost::placeholders::_4;
  v204 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1169,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v202,
           v203,
           v201);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1363,
    v204,
    0);
  v205 = std::wstring::wstring(v1013, v1221);
  v206 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v207) = boost::placeholders::_4;
  v208 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1170,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v206,
           v207,
           v205);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1362,
    v208,
    0);
  v209 = std::wstring::wstring(v1014, v1221);
  v210 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v211) = boost::placeholders::_4;
  v212 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1171,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v210,
           v211,
           v209);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1361,
    v212,
    0);
  v213 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1665,
           (unsigned int)v1221,
           (int)this + 176,
           (unsigned int)v1361,
           (__int64)v1362,
           (__int64)v1363,
           (__int64)v1364,
           (__int64)v1365);
  Uev::Setting<unsigned long>::operator=((char *)this + 12272, v213);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1665);
  boost::function<bool (void)>::~function<bool (void)>(v1361);
  boost::function<bool (void)>::~function<bool (void)>(v1362);
  boost::function<bool (void)>::~function<bool (void)>(v1363);
  boost::function<bool (void)>::~function<bool (void)>(v1364);
  boost::function<bool (void)>::~function<bool (void)>(v1365);
  Uev::Configuration::InsertSettingMap(this, v1221, (char *)this + 12272);
  boost::filesystem::path::~path((boost::filesystem::path *)v1221);
  std::wstring::wstring(v1222, L"PreventOverlappingSynchronization");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_7909abc2ae44f82297bc7fd4cf7bf159___(
    v1370,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1369, 0);
  v214 = std::wstring::wstring(v1015, v1222);
  v215 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v216) = boost::placeholders::_4;
  v217 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1172,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v215,
           v216,
           v214);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1368,
    v217,
    0);
  v218 = std::wstring::wstring(v1016, v1222);
  v219 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v220) = boost::placeholders::_4;
  v221 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1173,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v219,
           v220,
           v218);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1367,
    v221,
    0);
  v222 = std::wstring::wstring(v1017, v1222);
  v223 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v224) = boost::placeholders::_4;
  v225 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1174,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v223,
           v224,
           v222);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1366,
    v225,
    0);
  v226 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1666,
           (unsigned int)v1222,
           (int)this + 176,
           (unsigned int)v1366,
           (__int64)v1367,
           (__int64)v1368,
           (__int64)v1369,
           (__int64)v1370);
  Uev::Setting<unsigned long>::operator=((char *)this + 12576, v226);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1666);
  boost::function<bool (void)>::~function<bool (void)>(v1366);
  boost::function<bool (void)>::~function<bool (void)>(v1367);
  boost::function<bool (void)>::~function<bool (void)>(v1368);
  boost::function<bool (void)>::~function<bool (void)>(v1369);
  boost::function<bool (void)>::~function<bool (void)>(v1370);
  Uev::Configuration::InsertSettingMap(this, v1222, (char *)this + 12576);
  boost::filesystem::path::~path((boost::filesystem::path *)v1222);
  std::wstring::wstring(v1223, L"OverrideMSTemplates");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_b92673aa1f92d85b20d816489705495f___(
    v1375,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1374, 0);
  v227 = std::wstring::wstring(v1018, v1223);
  v228 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v229) = boost::placeholders::_4;
  v230 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1175,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v228,
           v229,
           v227);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1373,
    v230,
    0);
  v231 = std::wstring::wstring(v1019, v1223);
  v232 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v233) = boost::placeholders::_4;
  v234 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1176,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v232,
           v233,
           v231);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1372,
    v234,
    0);
  v235 = std::wstring::wstring(v1020, v1223);
  v236 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v237) = boost::placeholders::_4;
  v238 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1177,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v236,
           v237,
           v235);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1371,
    v238,
    0);
  v239 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1667,
           (unsigned int)v1223,
           v5,
           (unsigned int)v1371,
           (__int64)v1372,
           (__int64)v1373,
           (__int64)v1374,
           (__int64)v1375);
  Uev::Setting<unsigned long>::operator=((char *)this + 12880, v239);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1667);
  boost::function<bool (void)>::~function<bool (void)>(v1371);
  boost::function<bool (void)>::~function<bool (void)>(v1372);
  boost::function<bool (void)>::~function<bool (void)>(v1373);
  boost::function<bool (void)>::~function<bool (void)>(v1374);
  boost::function<bool (void)>::~function<bool (void)>(v1375);
  Uev::Configuration::InsertSettingMap(this, v1223, (char *)this + 12880);
  boost::filesystem::path::~path((boost::filesystem::path *)v1223);
  std::wstring::wstring(v1224, L"Offline Timestamp");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1380, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1379, 0);
  v240 = std::wstring::wstring(v1021, v1224);
  v241 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v242) = boost::placeholders::_4;
  v243 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1178,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v241,
           v242,
           v240);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1378,
    v243,
    0);
  v244 = std::wstring::wstring(v1022, v1224);
  v245 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v246) = boost::placeholders::_4;
  v247 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1179,
           (unsigned int) Uev::ConfigUtil::`vcall'{160,{flat}},
           v245,
           v246,
           v244);
  boost::function<bool (enum Uev::SettingSource,unsigned __int64 const &,long &)>::function<bool (enum Uev::SettingSource,unsigned __int64 const &,long &)>(
    v1377,
    v247,
    0);
  v248 = std::wstring::wstring(v1023, v1224);
  v249 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v250) = boost::placeholders::_4;
  v251 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1180,
           (unsigned int) Uev::ConfigUtil::`vcall'{112,{flat}},
           v249,
           v250,
           v248);
  boost::function<bool (enum Uev::SettingSource,unsigned __int64 &,long &)>::function<bool (enum Uev::SettingSource,unsigned __int64 &,long &)>(
    v1376,
    v251,
    0);
  v252 = Uev::Setting<unsigned __int64>::Setting<unsigned __int64>(
           (unsigned int)v1668,
           (unsigned int)v1224,
           v7,
           (unsigned int)v1376,
           (__int64)v1377,
           (__int64)v1378,
           (__int64)v1379,
           (__int64)v1380);
  Uev::Setting<unsigned long>::operator=((char *)this + 13184, v252);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1668);
  boost::function<bool (void)>::~function<bool (void)>(v1376);
  boost::function<bool (void)>::~function<bool (void)>(v1377);
  boost::function<bool (void)>::~function<bool (void)>(v1378);
  boost::function<bool (void)>::~function<bool (void)>(v1379);
  boost::function<bool (void)>::~function<bool (void)>(v1380);
  Uev::Configuration::InsertSettingMap(this, v1224, (char *)this + 13184);
  boost::filesystem::path::~path((boost::filesystem::path *)v1224);
  std::wstring::wstring(v1262, L"DebugTraceLogFilter");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_600ef2de1c8a28e1cd3fe2c643600d55___(
    v1385,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1384, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1383, 0);
  v253 = std::wstring::wstring(v1024, v1262);
  v254 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v255) = boost::placeholders::_4;
  v256 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1181,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v254,
           v255,
           v253);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1382,
    v256,
    0);
  v257 = std::wstring::wstring(v1025, v1262);
  v258 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v259) = boost::placeholders::_4;
  v260 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1182,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v258,
           v259,
           v257);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1381,
    v260,
    0);
  v261 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1669,
           (unsigned int)v1262,
           (int)this + 176,
           (unsigned int)v1381,
           (__int64)v1382,
           (__int64)v1383,
           (__int64)v1384,
           (__int64)v1385);
  Uev::Setting<unsigned long>::operator=((char *)this + 13488, v261);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1669);
  boost::function<bool (void)>::~function<bool (void)>(v1381);
  boost::function<bool (void)>::~function<bool (void)>(v1382);
  boost::function<bool (void)>::~function<bool (void)>(v1383);
  boost::function<bool (void)>::~function<bool (void)>(v1384);
  boost::function<bool (void)>::~function<bool (void)>(v1385);
  Uev::Configuration::InsertSettingMap(this, v1262, (char *)this + 13488);
  boost::filesystem::path::~path((boost::filesystem::path *)v1262);
  std::wstring::wstring(v1263, L"RepositoryOwnerCheckEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_8c3966ab01c8bf543f6f27494327131b___(
    v1390,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1389, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1388, 0);
  v262 = std::wstring::wstring(v1026, v1263);
  v263 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v264) = boost::placeholders::_4;
  v265 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1183,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v263,
           v264,
           v262);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1387,
    v265,
    0);
  v266 = std::wstring::wstring(v1027, v1263);
  v267 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v268) = boost::placeholders::_4;
  v269 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1184,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v267,
           v268,
           v266);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1386,
    v269,
    0);
  v270 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1670,
           (unsigned int)v1263,
           v9,
           (unsigned int)v1386,
           (__int64)v1387,
           (__int64)v1388,
           (__int64)v1389,
           (__int64)v1390);
  Uev::Setting<unsigned long>::operator=((char *)this + 13792, v270);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1670);
  boost::function<bool (void)>::~function<bool (void)>(v1386);
  boost::function<bool (void)>::~function<bool (void)>(v1387);
  boost::function<bool (void)>::~function<bool (void)>(v1388);
  boost::function<bool (void)>::~function<bool (void)>(v1389);
  boost::function<bool (void)>::~function<bool (void)>(v1390);
  Uev::Configuration::InsertSettingMap(this, v1263, (char *)this + 13792);
  boost::filesystem::path::~path((boost::filesystem::path *)v1263);
  std::wstring::wstring(v1264, L"ExcludedFileTypes");
  boost::function_std::list_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t__________cdecl_void__::function_std::list_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t__________cdecl_void____lambda_64fa6d66b597fdea73785cc0b5ff4a73___(
    v1395,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1394, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1393, 0);
  v271 = std::wstring::wstring(v1028, v1264);
  v272 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v273) = boost::placeholders::_4;
  v274 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1185,
           (unsigned int) Uev::ConfigUtil::`vcall'{144,{flat}},
           v272,
           v273,
           v271);
  boost::function<bool (enum Uev::SettingSource,std::list<std::wstring> const &,long &)>::function<bool (enum Uev::SettingSource,std::list<std::wstring> const &,long &)>(
    v1392,
    v274,
    0);
  v275 = std::wstring::wstring(v1029, v1264);
  v276 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v277) = boost::placeholders::_4;
  v278 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1186,
           (unsigned int) Uev::ConfigUtil::`vcall'{96,{flat}},
           v276,
           v277,
           v275);
  boost::function<bool (enum Uev::SettingSource,std::list<std::wstring> &,long &)>::function<bool (enum Uev::SettingSource,std::list<std::wstring> &,long &)>(
    v1391,
    v278,
    0);
  v279 = Uev::Setting<std::list<std::wstring>>::Setting<std::list<std::wstring>>(
           (unsigned int)v1671,
           (unsigned int)v1264,
           v9,
           (unsigned int)v1391,
           (__int64)v1392,
           (__int64)v1393,
           (__int64)v1394,
           (__int64)v1395);
  Uev::Setting<unsigned long>::operator=((char *)this + 14096, v279);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1671);
  boost::function<bool (void)>::~function<bool (void)>(v1391);
  boost::function<bool (void)>::~function<bool (void)>(v1392);
  boost::function<bool (void)>::~function<bool (void)>(v1393);
  boost::function<bool (void)>::~function<bool (void)>(v1394);
  boost::function<bool (void)>::~function<bool (void)>(v1395);
  Uev::Configuration::InsertSettingMap(this, v1264, (char *)this + 14096);
  boost::filesystem::path::~path((boost::filesystem::path *)v1264);
  std::wstring::wstring(v1265, L"HideSettingsPackagesFolder");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_f777dd4ec435cf534e5ac769899e2edc___(
    v1400,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1399, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1398, 0);
  v280 = std::wstring::wstring(v1030, v1265);
  v281 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v282) = boost::placeholders::_4;
  v283 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1187,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v281,
           v282,
           v280);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1397,
    v283,
    0);
  v284 = std::wstring::wstring(v1031, v1265);
  v285 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v286) = boost::placeholders::_4;
  v287 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1188,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v285,
           v286,
           v284);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1396,
    v287,
    0);
  v288 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1672,
           (unsigned int)v1265,
           v9,
           (unsigned int)v1396,
           (__int64)v1397,
           (__int64)v1398,
           (__int64)v1399,
           (__int64)v1400);
  Uev::Setting<unsigned long>::operator=((char *)this + 14400, v288);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1672);
  boost::function<bool (void)>::~function<bool (void)>(v1396);
  boost::function<bool (void)>::~function<bool (void)>(v1397);
  boost::function<bool (void)>::~function<bool (void)>(v1398);
  boost::function<bool (void)>::~function<bool (void)>(v1399);
  boost::function<bool (void)>::~function<bool (void)>(v1400);
  Uev::Configuration::InsertSettingMap(this, v1265, (char *)this + 14400);
  boost::filesystem::path::~path((boost::filesystem::path *)v1265);
  std::wstring::wstring(v1266, L"InitialOsSettingsExportDelay");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_4d89be7e27cbebf0fe89f7519b01a092___(
    v1405,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1404, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1403, 0);
  v289 = std::wstring::wstring(v1032, v1266);
  v290 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v291) = boost::placeholders::_4;
  v292 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1189,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v290,
           v291,
           v289);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1402,
    v292,
    0);
  v293 = std::wstring::wstring(v1033, v1266);
  v294 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v295) = boost::placeholders::_4;
  v296 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1190,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v294,
           v295,
           v293);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1401,
    v296,
    0);
  v297 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1673,
           (unsigned int)v1266,
           v7,
           (unsigned int)v1401,
           (__int64)v1402,
           (__int64)v1403,
           (__int64)v1404,
           (__int64)v1405);
  Uev::Setting<unsigned long>::operator=((char *)this + 14704, v297);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1673);
  boost::function<bool (void)>::~function<bool (void)>(v1401);
  boost::function<bool (void)>::~function<bool (void)>(v1402);
  boost::function<bool (void)>::~function<bool (void)>(v1403);
  boost::function<bool (void)>::~function<bool (void)>(v1404);
  boost::function<bool (void)>::~function<bool (void)>(v1405);
  Uev::Configuration::InsertSettingMap(this, v1266, (char *)this + 14704);
  boost::filesystem::path::~path((boost::filesystem::path *)v1266);
  std::wstring::wstring(v1253, L"StdpFlags");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_eeac8ab3d37cca4bdffcf7b4ff14682a___(
    v1410,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1409, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1408, 0);
  v298 = std::wstring::wstring(v1034, v1253);
  v299 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v300) = boost::placeholders::_4;
  v301 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1191,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v299,
           v300,
           v298);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1407,
    v301,
    0);
  v302 = std::wstring::wstring(v1035, v1253);
  v303 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v304) = boost::placeholders::_4;
  v305 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1192,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v303,
           v304,
           v302);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1406,
    v305,
    0);
  v306 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1674,
           (unsigned int)v1253,
           v9,
           (unsigned int)v1406,
           (__int64)v1407,
           (__int64)v1408,
           (__int64)v1409,
           (__int64)v1410);
  Uev::Setting<unsigned long>::operator=((char *)this + 15008, v306);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1674);
  boost::function<bool (void)>::~function<bool (void)>(v1406);
  boost::function<bool (void)>::~function<bool (void)>(v1407);
  boost::function<bool (void)>::~function<bool (void)>(v1408);
  boost::function<bool (void)>::~function<bool (void)>(v1409);
  boost::function<bool (void)>::~function<bool (void)>(v1410);
  Uev::Configuration::InsertSettingMap(this, v1253, (char *)this + 15008);
  boost::filesystem::path::~path((boost::filesystem::path *)v1253);
  std::wstring::wstring(v1254, L"StdpInterval");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_01a10b1b6eb17c08c7462cb7ba103072___(
    v1415,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1414, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1413, 0);
  v307 = std::wstring::wstring(v1036, v1254);
  v308 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v309) = boost::placeholders::_4;
  v310 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1193,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v308,
           v309,
           v307);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1412,
    v310,
    0);
  v311 = std::wstring::wstring(v1037, v1254);
  v312 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v313) = boost::placeholders::_4;
  v314 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1194,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v312,
           v313,
           v311);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1411,
    v314,
    0);
  v315 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1675,
           (unsigned int)v1254,
           v9,
           (unsigned int)v1411,
           (__int64)v1412,
           (__int64)v1413,
           (__int64)v1414,
           (__int64)v1415);
  Uev::Setting<unsigned long>::operator=((char *)this + 15312, v315);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1675);
  boost::function<bool (void)>::~function<bool (void)>(v1411);
  boost::function<bool (void)>::~function<bool (void)>(v1412);
  boost::function<bool (void)>::~function<bool (void)>(v1413);
  boost::function<bool (void)>::~function<bool (void)>(v1414);
  boost::function<bool (void)>::~function<bool (void)>(v1415);
  Uev::Configuration::InsertSettingMap(this, v1254, (char *)this + 15312);
  boost::filesystem::path::~path((boost::filesystem::path *)v1254);
  std::wstring::wstring(v1255, L"ADSettingsStoragePath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1420, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1419, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1418, 0);
  v316 = std::wstring::wstring(v1038, v1255);
  v317 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v318) = boost::placeholders::_4;
  v319 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1195,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v317,
           v318,
           v316);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1417,
    v319,
    0);
  v320 = std::wstring::wstring(v1039, v1255);
  v321 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v322) = boost::placeholders::_4;
  v323 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1196,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v321,
           v322,
           v320);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1416,
    v323,
    0);
  v324 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1676,
           (unsigned int)v1255,
           v7,
           (unsigned int)v1416,
           (__int64)v1417,
           (__int64)v1418,
           (__int64)v1419,
           (__int64)v1420);
  Uev::Setting<std::wstring>::operator=((char *)this + 18656, v324);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1676);
  boost::function<bool (void)>::~function<bool (void)>(v1416);
  boost::function<bool (void)>::~function<bool (void)>(v1417);
  boost::function<bool (void)>::~function<bool (void)>(v1418);
  boost::function<bool (void)>::~function<bool (void)>(v1419);
  boost::function<bool (void)>::~function<bool (void)>(v1420);
  Uev::Configuration::InsertSettingMap(this, v1255, (char *)this + 18656);
  boost::filesystem::path::~path((boost::filesystem::path *)v1255);
  std::wstring::wstring(v1256, L"CurrentSettingsStoragePath");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1425, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1424, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1423, 0);
  v325 = std::wstring::wstring(v1040, v1256);
  v326 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v327) = boost::placeholders::_4;
  v328 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1197,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v326,
           v327,
           v325);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1422,
    v328,
    0);
  v329 = std::wstring::wstring(v1041, v1256);
  v330 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v331) = boost::placeholders::_4;
  v332 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1198,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v330,
           v331,
           v329);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1421,
    v332,
    0);
  v333 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1677,
           (unsigned int)v1256,
           v7,
           (unsigned int)v1421,
           (__int64)v1422,
           (__int64)v1423,
           (__int64)v1424,
           (__int64)v1425);
  Uev::Setting<std::wstring>::operator=((char *)this + 18960, v333);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1677);
  boost::function<bool (void)>::~function<bool (void)>(v1421);
  boost::function<bool (void)>::~function<bool (void)>(v1422);
  boost::function<bool (void)>::~function<bool (void)>(v1423);
  boost::function<bool (void)>::~function<bool (void)>(v1424);
  boost::function<bool (void)>::~function<bool (void)>(v1425);
  Uev::Configuration::InsertSettingMap(this, v1256, (char *)this + 18960);
  boost::filesystem::path::~path((boost::filesystem::path *)v1256);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1482, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1483, 0);
  v334 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v786) = boost::placeholders::_4;
  LOBYTE(v754) = boost::placeholders::_4;
  LOBYTE(v335) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v965,
                       Uev::ConfigUtil::`vcall'{336,{flat}},
                      v334,
                      v335,
                      v754,
                      v786,
                      v819);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1484,
    &v844,
    0);
  v336 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v820) = boost::placeholders::_4;
  LOBYTE(v787) = boost::placeholders::_4;
  LOBYTE(v755) = boost::placeholders::_4;
  LOBYTE(v337) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v966,
                       Uev::ConfigUtil::`vcall'{328,{flat}},
                      v336,
                      v337,
                      v755,
                      v787,
                      v820);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>(
    v1485,
    &v844,
    0);
  v338 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v821) = boost::placeholders::_4;
  LOBYTE(v788) = boost::placeholders::_4;
  LOBYTE(v756) = boost::placeholders::_4;
  LOBYTE(v339) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v967,
                       Uev::ConfigUtil::`vcall'{320,{flat}},
                      v338,
                      v339,
                      v756,
                      v788,
                      v821);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>(
    v1426,
    &v844,
    0);
  v340 = Uev::SettingGroup<unsigned __int64>::SettingGroup<unsigned __int64>(
           (unsigned int)v1642,
           v7,
           (unsigned int)v1426,
           (unsigned int)v1485,
           (__int64)v1484,
           (__int64)v1483,
           (__int64)v1482);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 19264, v340);
  Uev::SettingGroup<unsigned __int64>::~SettingGroup<unsigned __int64>(v1642);
  boost::function<bool (void)>::~function<bool (void)>(v1426);
  boost::function<bool (void)>::~function<bool (void)>(v1485);
  boost::function<bool (void)>::~function<bool (void)>(v1484);
  boost::function<bool (void)>::~function<bool (void)>(v1483);
  boost::function<bool (void)>::~function<bool (void)>(v1482);
  std::wstring::wstring(v1277, L"RestoreSettingPackageTimestamp");
  Uev::Configuration::InsertGroupSettingMap(this, v1277, (char *)this + 19264);
  boost::filesystem::path::~path((boost::filesystem::path *)v1277);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1489, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1488, 0);
  v341 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v789) = boost::placeholders::_4;
  LOBYTE(v757) = boost::placeholders::_4;
  LOBYTE(v342) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v983,
                       Uev::ConfigUtil::`vcall'{360,{flat}},
                      v341,
                      v342,
                      v757,
                      v789,
                      v822);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1487,
    &v844,
    0);
  v343 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v823) = boost::placeholders::_4;
  LOBYTE(v790) = boost::placeholders::_4;
  LOBYTE(v758) = boost::placeholders::_4;
  LOBYTE(v344) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v990,
                       Uev::ConfigUtil::`vcall'{352,{flat}},
                      v343,
                      v344,
                      v758,
                      v790,
                      v823);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>(
    v1486,
    &v844,
    0);
  v345 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v824) = boost::placeholders::_4;
  LOBYTE(v791) = boost::placeholders::_4;
  LOBYTE(v759) = boost::placeholders::_4;
  LOBYTE(v346) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v877,
                       Uev::ConfigUtil::`vcall'{344,{flat}},
                      v345,
                      v346,
                      v759,
                      v791,
                      v824);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>(
    v1600,
    &v844,
    0);
  v347 = Uev::SettingGroup<unsigned long>::SettingGroup<unsigned long>(
           (unsigned int)v1643,
           v7,
           (unsigned int)v1600,
           (unsigned int)v1486,
           (__int64)v1487,
           (__int64)v1488,
           (__int64)v1489);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 19536, v347);
  Uev::SettingGroup<unsigned long>::~SettingGroup<unsigned long>(v1643);
  boost::function<bool (void)>::~function<bool (void)>(v1600);
  boost::function<bool (void)>::~function<bool (void)>(v1486);
  boost::function<bool (void)>::~function<bool (void)>(v1487);
  boost::function<bool (void)>::~function<bool (void)>(v1488);
  boost::function<bool (void)>::~function<bool (void)>(v1489);
  std::wstring::wstring(v1278, L"RestoreSettingPackageType");
  Uev::Configuration::InsertGroupSettingMap(this, v1278, (char *)this + 19536);
  boost::filesystem::path::~path((boost::filesystem::path *)v1278);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1494, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1493, 0);
  v348 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v792) = boost::placeholders::_4;
  LOBYTE(v760) = boost::placeholders::_4;
  LOBYTE(v349) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v878,
                       Uev::ConfigUtil::`vcall'{384,{flat}},
                      v348,
                      v349,
                      v760,
                      v792,
                      v825);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1492,
    &v844,
    0);
  v350 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v826) = boost::placeholders::_4;
  LOBYTE(v793) = boost::placeholders::_4;
  LOBYTE(v761) = boost::placeholders::_4;
  LOBYTE(v351) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v879,
                       Uev::ConfigUtil::`vcall'{376,{flat}},
                      v350,
                      v351,
                      v761,
                      v793,
                      v826);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>(
    v1491,
    &v844,
    0);
  v352 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v827) = boost::placeholders::_4;
  LOBYTE(v794) = boost::placeholders::_4;
  LOBYTE(v762) = boost::placeholders::_4;
  LOBYTE(v353) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v880,
                       Uev::ConfigUtil::`vcall'{368,{flat}},
                      v352,
                      v353,
                      v762,
                      v794,
                      v827);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>(
    v1490,
    &v844,
    0);
  v354 = Uev::SettingGroup<unsigned __int64>::SettingGroup<unsigned __int64>(
           (unsigned int)v1644,
           v9,
           (unsigned int)v1490,
           (unsigned int)v1491,
           (__int64)v1492,
           (__int64)v1493,
           (__int64)v1494);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 19808, v354);
  Uev::SettingGroup<unsigned __int64>::~SettingGroup<unsigned __int64>(v1644);
  boost::function<bool (void)>::~function<bool (void)>(v1490);
  boost::function<bool (void)>::~function<bool (void)>(v1491);
  boost::function<bool (void)>::~function<bool (void)>(v1492);
  boost::function<bool (void)>::~function<bool (void)>(v1493);
  boost::function<bool (void)>::~function<bool (void)>(v1494);
  std::wstring::wstring(v1279, L"TemplateRegistrationTimestamp");
  Uev::Configuration::InsertGroupSettingMap(this, v1279, (char *)this + 19808);
  boost::filesystem::path::~path((boost::filesystem::path *)v1279);
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_d1062e626c0ae6ed1bd32a54c4e0d45f___(
    v1499,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1498, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1497, 0);
  v355 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v828) = boost::placeholders::_4;
  LOBYTE(v795) = boost::placeholders::_4;
  LOBYTE(v763) = boost::placeholders::_4;
  LOBYTE(v356) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v881,
                       Uev::ConfigUtil::`vcall'{400,{flat}},
                      v355,
                      v356,
                      v763,
                      v795,
                      v828);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>(
    v1496,
    &v844,
    0);
  v357 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v829) = boost::placeholders::_4;
  LOBYTE(v796) = boost::placeholders::_4;
  LOBYTE(v764) = boost::placeholders::_4;
  LOBYTE(v358) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v882,
                       Uev::ConfigUtil::`vcall'{392,{flat}},
                      v357,
                      v358,
                      v764,
                      v796,
                      v829);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>(
    v1495,
    &v844,
    0);
  v359 = Uev::SettingGroup<unsigned long>::SettingGroup<unsigned long>(
           (unsigned int)v1645,
           v7,
           (unsigned int)v1495,
           (unsigned int)v1496,
           (__int64)v1497,
           (__int64)v1498,
           (__int64)v1499);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 20080, v359);
  Uev::SettingGroup<unsigned long>::~SettingGroup<unsigned long>(v1645);
  boost::function<bool (void)>::~function<bool (void)>(v1495);
  boost::function<bool (void)>::~function<bool (void)>(v1496);
  boost::function<bool (void)>::~function<bool (void)>(v1497);
  boost::function<bool (void)>::~function<bool (void)>(v1498);
  boost::function<bool (void)>::~function<bool (void)>(v1499);
  std::wstring::wstring(v1280, L"RestoreCount");
  Uev::Configuration::InsertGroupSettingMap(this, v1280, (char *)this + 20080);
  boost::filesystem::path::~path((boost::filesystem::path *)v1280);
  std::wstring::wstring(v1257, L"InstallTimestamp");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1504, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1503, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1502, 0);
  v360 = std::wstring::wstring(v1042, v1257);
  v361 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v362) = boost::placeholders::_4;
  v363 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1199,
           (unsigned int) Uev::ConfigUtil::`vcall'{160,{flat}},
           v361,
           v362,
           v360);
  boost::function<bool (enum Uev::SettingSource,unsigned __int64 const &,long &)>::function<bool (enum Uev::SettingSource,unsigned __int64 const &,long &)>(
    v1501,
    v363,
    0);
  v364 = std::wstring::wstring(v1043, v1257);
  v365 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v366) = boost::placeholders::_4;
  v367 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1200,
           (unsigned int) Uev::ConfigUtil::`vcall'{112,{flat}},
           v365,
           v366,
           v364);
  boost::function<bool (enum Uev::SettingSource,unsigned __int64 &,long &)>::function<bool (enum Uev::SettingSource,unsigned __int64 &,long &)>(
    v1500,
    v367,
    0);
  v368 = Uev::Setting<unsigned __int64>::Setting<unsigned __int64>(
           (unsigned int)v1678,
           (unsigned int)v1257,
           v9,
           (unsigned int)v1500,
           (__int64)v1501,
           (__int64)v1502,
           (__int64)v1503,
           (__int64)v1504);
  Uev::Setting<unsigned long>::operator=((char *)this + 20352, v368);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1678);
  boost::function<bool (void)>::~function<bool (void)>(v1500);
  boost::function<bool (void)>::~function<bool (void)>(v1501);
  boost::function<bool (void)>::~function<bool (void)>(v1502);
  boost::function<bool (void)>::~function<bool (void)>(v1503);
  boost::function<bool (void)>::~function<bool (void)>(v1504);
  Uev::Configuration::InsertSettingMap(this, v1257, (char *)this + 20352);
  boost::filesystem::path::~path((boost::filesystem::path *)v1257);
  std::wstring::wstring(v1258, L"CustomerExperienceImprovementProgram");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_296d104528f8721030b617bdafc4d456___(
    v1509,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1508, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1507, 0);
  v369 = std::wstring::wstring(v1044, v1258);
  v370 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v371) = boost::placeholders::_4;
  v372 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1201,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v370,
           v371,
           v369);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1506,
    v372,
    0);
  v373 = std::wstring::wstring(v1045, v1258);
  v374 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v375) = boost::placeholders::_4;
  v376 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1202,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v374,
           v375,
           v373);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1505,
    v376,
    0);
  v377 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1679,
           (unsigned int)v1258,
           (int)this + 176,
           (unsigned int)v1505,
           (__int64)v1506,
           (__int64)v1507,
           (__int64)v1508,
           (__int64)v1509);
  Uev::Setting<unsigned long>::operator=((char *)this + 15616, v377);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1679);
  boost::function<bool (void)>::~function<bool (void)>(v1505);
  boost::function<bool (void)>::~function<bool (void)>(v1506);
  boost::function<bool (void)>::~function<bool (void)>(v1507);
  boost::function<bool (void)>::~function<bool (void)>(v1508);
  boost::function<bool (void)>::~function<bool (void)>(v1509);
  Uev::Configuration::InsertSettingMap(this, v1258, (char *)this + 15616);
  boost::filesystem::path::~path((boost::filesystem::path *)v1258);
  std::wstring::wstring(v1259, L"ApplyExplorerCompatFix");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_8568a241d72fb52ffdd086efe0aec76e___(
    v1514,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1513, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1512, 0);
  v378 = std::wstring::wstring(v1046, v1259);
  v379 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v380) = boost::placeholders::_4;
  v381 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1203,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v379,
           v380,
           v378);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1511,
    v381,
    0);
  v382 = std::wstring::wstring(v1047, v1259);
  v383 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v384) = boost::placeholders::_4;
  v385 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1204,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v383,
           v384,
           v382);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1510,
    v385,
    0);
  v386 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1680,
           (unsigned int)v1259,
           (int)this + 176,
           (unsigned int)v1510,
           (__int64)v1511,
           (__int64)v1512,
           (__int64)v1513,
           (__int64)v1514);
  Uev::Setting<unsigned long>::operator=((char *)this + 15920, v386);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1680);
  boost::function<bool (void)>::~function<bool (void)>(v1510);
  boost::function<bool (void)>::~function<bool (void)>(v1511);
  boost::function<bool (void)>::~function<bool (void)>(v1512);
  boost::function<bool (void)>::~function<bool (void)>(v1513);
  boost::function<bool (void)>::~function<bool (void)>(v1514);
  Uev::Configuration::InsertSettingMap(this, v1259, (char *)this + 15920);
  boost::filesystem::path::~path((boost::filesystem::path *)v1259);
  std::wstring::wstring(v1225, L"ContactITUrl");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1519, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1518, 0);
  v387 = std::wstring::wstring(v1048, v1225);
  v388 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v389) = boost::placeholders::_4;
  v390 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1205,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v388,
           v389,
           v387);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1517,
    v390,
    0);
  v391 = std::wstring::wstring(v1049, v1225);
  v392 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v393) = boost::placeholders::_4;
  v394 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1206,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v392,
           v393,
           v391);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1516,
    v394,
    0);
  v395 = std::wstring::wstring(v1050, v1225);
  v396 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v397) = boost::placeholders::_4;
  v398 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1060,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v396,
           v397,
           v395);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1515,
    v398,
    0);
  v399 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1681,
           (unsigned int)v1225,
           v5,
           (unsigned int)v1515,
           (__int64)v1516,
           (__int64)v1517,
           (__int64)v1518,
           (__int64)v1519);
  Uev::Setting<std::wstring>::operator=((char *)this + 3584, v399);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1681);
  boost::function<bool (void)>::~function<bool (void)>(v1515);
  boost::function<bool (void)>::~function<bool (void)>(v1516);
  boost::function<bool (void)>::~function<bool (void)>(v1517);
  boost::function<bool (void)>::~function<bool (void)>(v1518);
  boost::function<bool (void)>::~function<bool (void)>(v1519);
  Uev::Configuration::InsertSettingMap(this, v1225, (char *)this + 3584);
  boost::filesystem::path::~path((boost::filesystem::path *)v1225);
  std::wstring::wstring(v1226, L"ContactITDescription");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1524, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1523, 0);
  v400 = std::wstring::wstring(v1051, v1226);
  v401 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v402) = boost::placeholders::_4;
  v403 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1061,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v401,
           v402,
           v400);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1522,
    v403,
    0);
  v404 = std::wstring::wstring(v1052, v1226);
  v405 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v406) = boost::placeholders::_4;
  v407 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1062,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v405,
           v406,
           v404);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1521,
    v407,
    0);
  v408 = std::wstring::wstring(v1053, v1226);
  v409 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v410) = boost::placeholders::_4;
  v411 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1063,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v409,
           v410,
           v408);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1520,
    v411,
    0);
  v412 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1682,
           (unsigned int)v1226,
           v5,
           (unsigned int)v1520,
           (__int64)v1521,
           (__int64)v1522,
           (__int64)v1523,
           (__int64)v1524);
  Uev::Setting<std::wstring>::operator=((char *)this + 3888, v412);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1682);
  boost::function<bool (void)>::~function<bool (void)>(v1520);
  boost::function<bool (void)>::~function<bool (void)>(v1521);
  boost::function<bool (void)>::~function<bool (void)>(v1522);
  boost::function<bool (void)>::~function<bool (void)>(v1523);
  boost::function<bool (void)>::~function<bool (void)>(v1524);
  Uev::Configuration::InsertSettingMap(this, v1226, (char *)this + 3888);
  boost::filesystem::path::~path((boost::filesystem::path *)v1226);
  std::wstring::wstring(v1260, L"TrayIconEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_c5824d521a16254f38e2e43f872ddd16___(
    v1529,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1528, 0);
  v413 = std::wstring::wstring(v1054, v1260);
  v414 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v415) = boost::placeholders::_4;
  v416 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1064,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v414,
           v415,
           v413);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1527,
    v416,
    0);
  v417 = std::wstring::wstring(v1055, v1260);
  v418 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v419) = boost::placeholders::_4;
  v420 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1065,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v418,
           v419,
           v417);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1526,
    v420,
    0);
  v421 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  v422 = boost::bind<bool,Uev::ConfigUtil,bool,Uev::ConfigUtil *,bool>(
           v1059,
            Uev::ConfigUtil::`vcall'{272,{flat}},
           v421,
           0);
  v844 = *(_OWORD *)v422;
  v845 = *(_QWORD *)(v422 + 16);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1525,
    &v844,
    0);
  v423 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1683,
           (unsigned int)v1260,
           v5,
           (unsigned int)v1525,
           (__int64)v1526,
           (__int64)v1527,
           (__int64)v1528,
           (__int64)v1529);
  Uev::Setting<unsigned long>::operator=((char *)this + 4192, v423);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1683);
  boost::function<bool (void)>::~function<bool (void)>(v1525);
  boost::function<bool (void)>::~function<bool (void)>(v1526);
  boost::function<bool (void)>::~function<bool (void)>(v1527);
  boost::function<bool (void)>::~function<bool (void)>(v1528);
  boost::function<bool (void)>::~function<bool (void)>(v1529);
  Uev::Configuration::InsertSettingMap(this, v1260, (char *)this + 4192);
  boost::filesystem::path::~path((boost::filesystem::path *)v1260);
  std::wstring::wstring(v1227, L"FirstUseNotificationEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_6e023ceedadbee707f393b1be657a0cd___(
    v1534,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1533, 0);
  v424 = std::wstring::wstring(v1056, v1227);
  v425 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v426) = boost::placeholders::_4;
  v427 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1066,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v425,
           v426,
           v424);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1532,
    v427,
    0);
  v428 = std::wstring::wstring(v1057, v1227);
  v429 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v430) = boost::placeholders::_4;
  v431 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1067,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v429,
           v430,
           v428);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1531,
    v431,
    0);
  v432 = std::wstring::wstring(v1058, v1227);
  v433 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v434) = boost::placeholders::_4;
  v435 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1068,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v433,
           v434,
           v432);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1530,
    v435,
    0);
  v436 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1684,
           (unsigned int)v1227,
           v5,
           (unsigned int)v1530,
           (__int64)v1531,
           (__int64)v1532,
           (__int64)v1533,
           (__int64)v1534);
  Uev::Setting<unsigned long>::operator=((char *)this + 4496, v436);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1684);
  boost::function<bool (void)>::~function<bool (void)>(v1530);
  boost::function<bool (void)>::~function<bool (void)>(v1531);
  boost::function<bool (void)>::~function<bool (void)>(v1532);
  boost::function<bool (void)>::~function<bool (void)>(v1533);
  boost::function<bool (void)>::~function<bool (void)>(v1534);
  Uev::Configuration::InsertSettingMap(this, v1227, (char *)this + 4496);
  boost::filesystem::path::~path((boost::filesystem::path *)v1227);
  std::wstring::wstring(v1228, L"SyncProviderName");
  boost::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void__::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void____lambda_c25d39eec11bfdbd4cea5c4b20a5bf87___(
    v1539,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1538, 0);
  v437 = std::wstring::wstring(v896, v1228);
  v438 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v439) = boost::placeholders::_4;
  v440 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1069,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v438,
           v439,
           v437);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1537,
    v440,
    0);
  v441 = std::wstring::wstring(v897, v1228);
  v442 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v443) = boost::placeholders::_4;
  v444 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1070,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v442,
           v443,
           v441);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1536,
    v444,
    0);
  v445 = std::wstring::wstring(v898, v1228);
  v446 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v447) = boost::placeholders::_4;
  v448 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1071,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v446,
           v447,
           v445);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1535,
    v448,
    0);
  v449 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1685,
           (unsigned int)v1228,
           (int)this + 176,
           (unsigned int)v1535,
           (__int64)v1536,
           (__int64)v1537,
           (__int64)v1538,
           (__int64)v1539);
  Uev::Setting<std::wstring>::operator=((char *)this + 4800, v449);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1685);
  boost::function<bool (void)>::~function<bool (void)>(v1535);
  boost::function<bool (void)>::~function<bool (void)>(v1536);
  boost::function<bool (void)>::~function<bool (void)>(v1537);
  boost::function<bool (void)>::~function<bool (void)>(v1538);
  boost::function<bool (void)>::~function<bool (void)>(v1539);
  Uev::Configuration::InsertSettingMap(this, v1228, (char *)this + 4800);
  boost::filesystem::path::~path((boost::filesystem::path *)v1228);
  std::wstring::wstring(v1229, L"DontSyncWindows8AppSettings");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_6e9219e3c2f72be17f602672ff39e916___(
    v1544,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1543, 0);
  v450 = std::wstring::wstring(v899, v1229);
  v451 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v452) = boost::placeholders::_4;
  v453 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1072,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v451,
           v452,
           v450);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1542,
    v453,
    0);
  v454 = std::wstring::wstring(v900, v1229);
  v455 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v456) = boost::placeholders::_4;
  v457 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1073,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v455,
           v456,
           v454);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1541,
    v457,
    0);
  v458 = std::wstring::wstring(v901, v1229);
  v459 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v460) = boost::placeholders::_4;
  v461 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1074,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v459,
           v460,
           v458);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1540,
    v461,
    0);
  v462 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1686,
           (unsigned int)v1229,
           (int)this + 176,
           (unsigned int)v1540,
           (__int64)v1541,
           (__int64)v1542,
           (__int64)v1543,
           (__int64)v1544);
  Uev::Setting<unsigned long>::operator=((char *)this + 5408, v462);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1686);
  boost::function<bool (void)>::~function<bool (void)>(v1540);
  boost::function<bool (void)>::~function<bool (void)>(v1541);
  boost::function<bool (void)>::~function<bool (void)>(v1542);
  boost::function<bool (void)>::~function<bool (void)>(v1543);
  boost::function<bool (void)>::~function<bool (void)>(v1544);
  Uev::Configuration::InsertSettingMap(this, v1229, (char *)this + 5408);
  boost::filesystem::path::~path((boost::filesystem::path *)v1229);
  std::wstring::wstring(v1230, L"SyncUnlistedWindows8Apps");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_e5f7be803118221bb97c7da2ff451a05___(
    v1549,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1548, 0);
  v463 = std::wstring::wstring(v902, v1230);
  v464 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v465) = boost::placeholders::_4;
  v466 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1075,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v464,
           v465,
           v463);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1547,
    v466,
    0);
  v467 = std::wstring::wstring(v903, v1230);
  v468 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v469) = boost::placeholders::_4;
  v470 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1076,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v468,
           v469,
           v467);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1546,
    v470,
    0);
  v471 = std::wstring::wstring(v904, v1230);
  v472 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v473) = boost::placeholders::_4;
  v474 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1077,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v472,
           v473,
           v471);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1545,
    v474,
    0);
  v475 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1687,
           (unsigned int)v1230,
           (int)this + 176,
           (unsigned int)v1545,
           (__int64)v1546,
           (__int64)v1547,
           (__int64)v1548,
           (__int64)v1549);
  Uev::Setting<unsigned long>::operator=((char *)this + 5712, v475);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1687);
  boost::function<bool (void)>::~function<bool (void)>(v1545);
  boost::function<bool (void)>::~function<bool (void)>(v1546);
  boost::function<bool (void)>::~function<bool (void)>(v1547);
  boost::function<bool (void)>::~function<bool (void)>(v1548);
  boost::function<bool (void)>::~function<bool (void)>(v1549);
  Uev::Configuration::InsertSettingMap(this, v1230, (char *)this + 5712);
  boost::filesystem::path::~path((boost::filesystem::path *)v1230);
  std::wstring::wstring(v1231, L"DebugLogFileName");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1554, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1553, 0);
  v476 = std::wstring::wstring(v905, v1231);
  v477 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v478) = boost::placeholders::_4;
  v479 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1078,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v477,
           v478,
           v476);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1552,
    v479,
    0);
  v480 = std::wstring::wstring(v906, v1231);
  v481 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v482) = boost::placeholders::_4;
  v483 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1079,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v481,
           v482,
           v480);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1551,
    v483,
    0);
  v484 = std::wstring::wstring(v907, v1231);
  v485 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v486) = boost::placeholders::_4;
  v487 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1080,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v485,
           v486,
           v484);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1550,
    v487,
    0);
  v488 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1688,
           (unsigned int)v1231,
           v9,
           (unsigned int)v1550,
           (__int64)v1551,
           (__int64)v1552,
           (__int64)v1553,
           (__int64)v1554);
  Uev::Setting<std::wstring>::operator=((char *)this + 16224, v488);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1688);
  boost::function<bool (void)>::~function<bool (void)>(v1550);
  boost::function<bool (void)>::~function<bool (void)>(v1551);
  boost::function<bool (void)>::~function<bool (void)>(v1552);
  boost::function<bool (void)>::~function<bool (void)>(v1553);
  boost::function<bool (void)>::~function<bool (void)>(v1554);
  Uev::Configuration::InsertSettingMap(this, v1231, (char *)this + 16224);
  boost::filesystem::path::~path((boost::filesystem::path *)v1231);
  std::wstring::wstring(v1232, L"RunSyncOnTrigger");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_20efb2c191dedde8517f0f1f29ca0f90___(
    v1559,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1558, 0);
  v489 = std::wstring::wstring(v908, v1232);
  v490 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v491) = boost::placeholders::_4;
  v492 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1081,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v490,
           v491,
           v489);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1557,
    v492,
    0);
  v493 = std::wstring::wstring(v909, v1232);
  v494 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v495) = boost::placeholders::_4;
  v496 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1082,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v494,
           v495,
           v493);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1556,
    v496,
    0);
  v497 = std::wstring::wstring(v910, v1232);
  v498 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v499) = boost::placeholders::_4;
  v500 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1083,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v498,
           v499,
           v497);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1555,
    v500,
    0);
  v501 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1689,
           (unsigned int)v1232,
           (int)this + 176,
           (unsigned int)v1555,
           (__int64)v1556,
           (__int64)v1557,
           (__int64)v1558,
           (__int64)v1559);
  Uev::Setting<unsigned long>::operator=((char *)this + 6016, v501);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1689);
  boost::function<bool (void)>::~function<bool (void)>(v1555);
  boost::function<bool (void)>::~function<bool (void)>(v1556);
  boost::function<bool (void)>::~function<bool (void)>(v1557);
  boost::function<bool (void)>::~function<bool (void)>(v1558);
  boost::function<bool (void)>::~function<bool (void)>(v1559);
  Uev::Configuration::InsertSettingMap(this, v1232, (char *)this + 6016);
  boost::filesystem::path::~path((boost::filesystem::path *)v1232);
  std::wstring::wstring(v1233, L"WaitForSyncOnApplicationStart");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_0909bc1f4de7562b6ca68047934cef6b___(
    v1564,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1563, 0);
  v502 = std::wstring::wstring(v911, v1233);
  v503 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v504) = boost::placeholders::_4;
  v505 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1084,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v503,
           v504,
           v502);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1562,
    v505,
    0);
  v506 = std::wstring::wstring(v912, v1233);
  v507 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v508) = boost::placeholders::_4;
  v509 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1085,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v507,
           v508,
           v506);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1561,
    v509,
    0);
  v510 = std::wstring::wstring(v913, v1233);
  v511 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v512) = boost::placeholders::_4;
  v513 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1086,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v511,
           v512,
           v510);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1560,
    v513,
    0);
  v514 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1690,
           (unsigned int)v1233,
           (int)this + 176,
           (unsigned int)v1560,
           (__int64)v1561,
           (__int64)v1562,
           (__int64)v1563,
           (__int64)v1564);
  Uev::Setting<unsigned long>::operator=((char *)this + 6320, v514);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1690);
  boost::function<bool (void)>::~function<bool (void)>(v1560);
  boost::function<bool (void)>::~function<bool (void)>(v1561);
  boost::function<bool (void)>::~function<bool (void)>(v1562);
  boost::function<bool (void)>::~function<bool (void)>(v1563);
  boost::function<bool (void)>::~function<bool (void)>(v1564);
  Uev::Configuration::InsertSettingMap(this, v1233, (char *)this + 6320);
  boost::filesystem::path::~path((boost::filesystem::path *)v1233);
  std::wstring::wstring(v1234, L"WaitForSyncOnLogon");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_5c230d48c7cd022ef646a68477621f28___(
    v1569,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1568, 0);
  v515 = std::wstring::wstring(v914, v1234);
  v516 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v517) = boost::placeholders::_4;
  v518 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1087,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v516,
           v517,
           v515);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1567,
    v518,
    0);
  v519 = std::wstring::wstring(v915, v1234);
  v520 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v521) = boost::placeholders::_4;
  v522 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1088,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v520,
           v521,
           v519);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1566,
    v522,
    0);
  v523 = std::wstring::wstring(v916, v1234);
  v524 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v525) = boost::placeholders::_4;
  v526 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1089,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v524,
           v525,
           v523);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1565,
    v526,
    0);
  v527 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1691,
           (unsigned int)v1234,
           (int)this + 176,
           (unsigned int)v1565,
           (__int64)v1566,
           (__int64)v1567,
           (__int64)v1568,
           (__int64)v1569);
  Uev::Setting<unsigned long>::operator=((char *)this + 6624, v527);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1691);
  boost::function<bool (void)>::~function<bool (void)>(v1565);
  boost::function<bool (void)>::~function<bool (void)>(v1566);
  boost::function<bool (void)>::~function<bool (void)>(v1567);
  boost::function<bool (void)>::~function<bool (void)>(v1568);
  boost::function<bool (void)>::~function<bool (void)>(v1569);
  Uev::Configuration::InsertSettingMap(this, v1234, (char *)this + 6624);
  boost::filesystem::path::~path((boost::filesystem::path *)v1234);
  std::wstring::wstring(v1235, L"WaitForSyncTimeoutInMilliseconds");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_0ae09f119ac7948711cb49b313c92fa3___(
    v1574,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1573, 0);
  v528 = std::wstring::wstring(v917, v1235);
  v529 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v530) = boost::placeholders::_4;
  v531 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1090,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v529,
           v530,
           v528);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1572,
    v531,
    0);
  v532 = std::wstring::wstring(v918, v1235);
  v533 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v534) = boost::placeholders::_4;
  v535 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1091,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v533,
           v534,
           v532);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1571,
    v535,
    0);
  v536 = std::wstring::wstring(v919, v1235);
  v537 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v538) = boost::placeholders::_4;
  v539 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1092,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v537,
           v538,
           v536);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1570,
    v539,
    0);
  v540 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1692,
           (unsigned int)v1235,
           (int)this + 176,
           (unsigned int)v1570,
           (__int64)v1571,
           (__int64)v1572,
           (__int64)v1573,
           (__int64)v1574);
  Uev::Setting<unsigned long>::operator=((char *)this + 6928, v540);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1692);
  boost::function<bool (void)>::~function<bool (void)>(v1570);
  boost::function<bool (void)>::~function<bool (void)>(v1571);
  boost::function<bool (void)>::~function<bool (void)>(v1572);
  boost::function<bool (void)>::~function<bool (void)>(v1573);
  boost::function<bool (void)>::~function<bool (void)>(v1574);
  Uev::Configuration::InsertSettingMap(this, v1235, (char *)this + 6928);
  boost::filesystem::path::~path((boost::filesystem::path *)v1235);
  std::wstring::wstring(v1236, L"SettingsStoragePathADAttribute");
  boost::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void__::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void____lambda_e5f4bdf440dd6197a27b1f54b61e80a9___(
    v1579,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1578, 0);
  v541 = std::wstring::wstring(v920, v1236);
  v542 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v543) = boost::placeholders::_4;
  v544 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1093,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v542,
           v543,
           v541);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1577,
    v544,
    0);
  v545 = std::wstring::wstring(v921, v1236);
  v546 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v547) = boost::placeholders::_4;
  v548 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1094,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v546,
           v547,
           v545);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1576,
    v548,
    0);
  v549 = std::wstring::wstring(v922, v1236);
  v550 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v551) = boost::placeholders::_4;
  v552 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1095,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v550,
           v551,
           v549);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1575,
    v552,
    0);
  v553 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1693,
           (unsigned int)v1236,
           (int)this + 176,
           (unsigned int)v1575,
           (__int64)v1576,
           (__int64)v1577,
           (__int64)v1578,
           (__int64)v1579);
  Uev::Setting<std::wstring>::operator=((char *)this + 7232, v553);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1693);
  boost::function<bool (void)>::~function<bool (void)>(v1575);
  boost::function<bool (void)>::~function<bool (void)>(v1576);
  boost::function<bool (void)>::~function<bool (void)>(v1577);
  boost::function<bool (void)>::~function<bool (void)>(v1578);
  boost::function<bool (void)>::~function<bool (void)>(v1579);
  Uev::Configuration::InsertSettingMap(this, v1236, (char *)this + 7232);
  boost::filesystem::path::~path((boost::filesystem::path *)v1236);
  std::wstring::wstring(v1237, L"SyncConditionsAssemblyName");
  boost::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void__::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void____lambda_0bcbfd5f21a076b5a4dbf33b762a5b35___(
    v1584,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1583, 0);
  v554 = std::wstring::wstring(v923, v1237);
  v555 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v556) = boost::placeholders::_4;
  v557 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1096,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v555,
           v556,
           v554);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1582,
    v557,
    0);
  v558 = std::wstring::wstring(v924, v1237);
  v559 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v560) = boost::placeholders::_4;
  v561 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1097,
           (unsigned int) Uev::ConfigUtil::`vcall'{136,{flat}},
           v559,
           v560,
           v558);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1581,
    v561,
    0);
  v562 = std::wstring::wstring(v925, v1237);
  v563 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v564) = boost::placeholders::_4;
  v565 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1098,
           (unsigned int) Uev::ConfigUtil::`vcall'{88,{flat}},
           v563,
           v564,
           v562);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1580,
    v565,
    0);
  v566 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1694,
           (unsigned int)v1237,
           (int)this + 176,
           (unsigned int)v1580,
           (__int64)v1581,
           (__int64)v1582,
           (__int64)v1583,
           (__int64)v1584);
  Uev::Setting<std::wstring>::operator=((char *)this + 7536, v566);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1694);
  boost::function<bool (void)>::~function<bool (void)>(v1580);
  boost::function<bool (void)>::~function<bool (void)>(v1581);
  boost::function<bool (void)>::~function<bool (void)>(v1582);
  boost::function<bool (void)>::~function<bool (void)>(v1583);
  boost::function<bool (void)>::~function<bool (void)>(v1584);
  Uev::Configuration::InsertSettingMap(this, v1237, (char *)this + 7536);
  boost::filesystem::path::~path((boost::filesystem::path *)v1237);
  std::wstring::wstring(v1238, L"SyncOverMeteredNetwork");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_caddc917612cb3713747ee34b66266a9___(
    v1589,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1588, 0);
  v567 = std::wstring::wstring(v926, v1238);
  v568 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v569) = boost::placeholders::_4;
  v570 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1131,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v568,
           v569,
           v567);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1587,
    v570,
    0);
  v571 = std::wstring::wstring(v927, v1238);
  v572 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v573) = boost::placeholders::_4;
  v574 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1099,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v572,
           v573,
           v571);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1586,
    v574,
    0);
  v575 = std::wstring::wstring(v928, v1238);
  v576 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v577) = boost::placeholders::_4;
  v578 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1100,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v576,
           v577,
           v575);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1585,
    v578,
    0);
  v579 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1695,
           (unsigned int)v1238,
           (int)this + 176,
           (unsigned int)v1585,
           (__int64)v1586,
           (__int64)v1587,
           (__int64)v1588,
           (__int64)v1589);
  Uev::Setting<unsigned long>::operator=((char *)this + 7840, v579);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1695);
  boost::function<bool (void)>::~function<bool (void)>(v1585);
  boost::function<bool (void)>::~function<bool (void)>(v1586);
  boost::function<bool (void)>::~function<bool (void)>(v1587);
  boost::function<bool (void)>::~function<bool (void)>(v1588);
  boost::function<bool (void)>::~function<bool (void)>(v1589);
  Uev::Configuration::InsertSettingMap(this, v1238, (char *)this + 7840);
  boost::filesystem::path::~path((boost::filesystem::path *)v1238);
  std::wstring::wstring(v1239, L"SyncOverMeteredNetworkWhenRoaming");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_854f65a20d2899f2a401a3415930eacb___(
    v1594,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1593, 0);
  v580 = std::wstring::wstring(v929, v1239);
  v581 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v582) = boost::placeholders::_4;
  v583 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1101,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v581,
           v582,
           v580);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1592,
    v583,
    0);
  v584 = std::wstring::wstring(v930, v1239);
  v585 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v586) = boost::placeholders::_4;
  v587 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1102,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v585,
           v586,
           v584);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1591,
    v587,
    0);
  v588 = std::wstring::wstring(v931, v1239);
  v589 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v590) = boost::placeholders::_4;
  v591 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1103,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v589,
           v590,
           v588);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1590,
    v591,
    0);
  v592 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1696,
           (unsigned int)v1239,
           (int)this + 176,
           (unsigned int)v1590,
           (__int64)v1591,
           (__int64)v1592,
           (__int64)v1593,
           (__int64)v1594);
  Uev::Setting<unsigned long>::operator=((char *)this + 8144, v592);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1696);
  boost::function<bool (void)>::~function<bool (void)>(v1590);
  boost::function<bool (void)>::~function<bool (void)>(v1591);
  boost::function<bool (void)>::~function<bool (void)>(v1592);
  boost::function<bool (void)>::~function<bool (void)>(v1593);
  boost::function<bool (void)>::~function<bool (void)>(v1594);
  Uev::Configuration::InsertSettingMap(this, v1239, (char *)this + 8144);
  boost::filesystem::path::~path((boost::filesystem::path *)v1239);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1599, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1598, 0);
  v593 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v797) = boost::placeholders::_4;
  LOBYTE(v765) = boost::placeholders::_4;
  LOBYTE(v594) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v883,
                       Uev::ConfigUtil::`vcall'{424,{flat}},
                      v593,
                      v594,
                      v765,
                      v797,
                      v830);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1597,
    &v844,
    0);
  v595 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v831) = boost::placeholders::_4;
  LOBYTE(v798) = boost::placeholders::_4;
  LOBYTE(v766) = boost::placeholders::_4;
  LOBYTE(v596) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v884,
                       Uev::ConfigUtil::`vcall'{416,{flat}},
                      v595,
                      v596,
                      v766,
                      v798,
                      v831);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &)>(
    v1596,
    &v844,
    0);
  v597 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v832) = boost::placeholders::_4;
  LOBYTE(v799) = boost::placeholders::_4;
  LOBYTE(v767) = boost::placeholders::_4;
  LOBYTE(v598) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v885,
                       Uev::ConfigUtil::`vcall'{408,{flat}},
                      v597,
                      v598,
                      v767,
                      v799,
                      v832);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned __int64 &,long &)>(
    v1595,
    &v844,
    0);
  v599 = Uev::SettingGroup<unsigned __int64>::SettingGroup<unsigned __int64>(
           (unsigned int)v1646,
           v7,
           (unsigned int)v1595,
           (unsigned int)v1596,
           (__int64)v1597,
           (__int64)v1598,
           (__int64)v1599);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 20656, v599);
  Uev::SettingGroup<unsigned __int64>::~SettingGroup<unsigned __int64>(v1646);
  boost::function<bool (void)>::~function<bool (void)>(v1595);
  boost::function<bool (void)>::~function<bool (void)>(v1596);
  boost::function<bool (void)>::~function<bool (void)>(v1597);
  boost::function<bool (void)>::~function<bool (void)>(v1598);
  boost::function<bool (void)>::~function<bool (void)>(v1599);
  std::wstring::wstring(v1281, L"MissingExternalFileTimestamp");
  Uev::Configuration::InsertGroupSettingMap(this, v1281, (char *)this + 20656);
  boost::filesystem::path::~path((boost::filesystem::path *)v1281);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1605, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1604, 0);
  v600 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v800) = boost::placeholders::_4;
  LOBYTE(v768) = boost::placeholders::_4;
  LOBYTE(v601) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v886,
                       Uev::ConfigUtil::`vcall'{448,{flat}},
                      v600,
                      v601,
                      v768,
                      v800,
                      v833);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1603,
    &v844,
    0);
  v602 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v834) = boost::placeholders::_4;
  LOBYTE(v801) = boost::placeholders::_4;
  LOBYTE(v769) = boost::placeholders::_4;
  LOBYTE(v603) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v887,
                       Uev::ConfigUtil::`vcall'{440,{flat}},
                      v602,
                      v603,
                      v769,
                      v801,
                      v834);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &)>(
    v1602,
    &v844,
    0);
  v604 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v835) = boost::placeholders::_4;
  LOBYTE(v802) = boost::placeholders::_4;
  LOBYTE(v770) = boost::placeholders::_4;
  LOBYTE(v605) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v888,
                       Uev::ConfigUtil::`vcall'{432,{flat}},
                      v604,
                      v605,
                      v770,
                      v802,
                      v835);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,unsigned long &,long &)>(
    v1601,
    &v844,
    0);
  v606 = Uev::SettingGroup<unsigned long>::SettingGroup<unsigned long>(
           (unsigned int)v1647,
           v7,
           (unsigned int)v1601,
           (unsigned int)v1602,
           (__int64)v1603,
           (__int64)v1604,
           (__int64)v1605);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 20928, v606);
  Uev::SettingGroup<unsigned long>::~SettingGroup<unsigned long>(v1647);
  boost::function<bool (void)>::~function<bool (void)>(v1601);
  boost::function<bool (void)>::~function<bool (void)>(v1602);
  boost::function<bool (void)>::~function<bool (void)>(v1603);
  boost::function<bool (void)>::~function<bool (void)>(v1604);
  boost::function<bool (void)>::~function<bool (void)>(v1605);
  std::wstring::wstring(v1282, L"MissingExternalFileCount");
  Uev::Configuration::InsertGroupSettingMap(this, v1282, (char *)this + 20928);
  boost::filesystem::path::~path((boost::filesystem::path *)v1282);
  std::wstring::wstring(v1261, L"FirstTimeLogon");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_48453bd5d443e5515f893e7def290f90___(
    v1610,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1609, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1608, 0);
  v607 = std::wstring::wstring(v932, v1261);
  v608 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v609) = boost::placeholders::_4;
  v610 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1104,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v608,
           v609,
           v607);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1607,
    v610,
    0);
  v611 = std::wstring::wstring(v933, v1261);
  v612 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v613) = boost::placeholders::_4;
  v614 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1105,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v612,
           v613,
           v611);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1606,
    v614,
    0);
  v615 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1697,
           (unsigned int)v1261,
           v7,
           (unsigned int)v1606,
           (__int64)v1607,
           (__int64)v1608,
           (__int64)v1609,
           (__int64)v1610);
  v616 = this;
  Uev::Setting<unsigned long>::operator=((char *)this + 21200, v615);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1697);
  boost::function<bool (void)>::~function<bool (void)>(v1606);
  boost::function<bool (void)>::~function<bool (void)>(v1607);
  boost::function<bool (void)>::~function<bool (void)>(v1608);
  boost::function<bool (void)>::~function<bool (void)>(v1609);
  boost::function<bool (void)>::~function<bool (void)>(v1610);
  Uev::Configuration::InsertSettingMap(this, v1261, (char *)this + 21200);
  boost::filesystem::path::~path((boost::filesystem::path *)v1261);
  std::wstring::wstring(v1240, L"WaitForWallpaperOverwriteTime");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_bef5238a41524bf5b97bfb01414966ba___(
    v1615,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1614, 0);
  v617 = std::wstring::wstring(v934, v1240);
  v618 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v619) = boost::placeholders::_4;
  v620 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1106,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v618,
           v619,
           v617);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1613,
    v620,
    0);
  v621 = std::wstring::wstring(v935, v1240);
  v622 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v623) = boost::placeholders::_4;
  v624 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1107,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v622,
           v623,
           v621);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1612,
    v624,
    0);
  v625 = std::wstring::wstring(v936, v1240);
  v626 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v627) = boost::placeholders::_4;
  v628 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1108,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v626,
           v627,
           v625);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1611,
    v628,
    0);
  v629 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1698,
           (unsigned int)v1240,
           (int)this + 176,
           (unsigned int)v1611,
           (__int64)v1612,
           (__int64)v1613,
           (__int64)v1614,
           (__int64)v1615);
  Uev::Setting<unsigned long>::operator=((char *)this + 16528, v629);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1698);
  boost::function<bool (void)>::~function<bool (void)>(v1611);
  boost::function<bool (void)>::~function<bool (void)>(v1612);
  boost::function<bool (void)>::~function<bool (void)>(v1613);
  boost::function<bool (void)>::~function<bool (void)>(v1614);
  boost::function<bool (void)>::~function<bool (void)>(v1615);
  Uev::Configuration::InsertSettingMap(v616, v1240, (char *)v616 + 16528);
  boost::filesystem::path::~path((boost::filesystem::path *)v1240);
  std::wstring::wstring(v1241, L"SetWallpaperRetries");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_160a746f73309ce8669c4d223c272932___(
    v1620,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1619, 0);
  v630 = std::wstring::wstring(v937, v1241);
  v631 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v632) = boost::placeholders::_4;
  v633 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1109,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v631,
           v632,
           v630);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1618,
    v633,
    0);
  v634 = std::wstring::wstring(v938, v1241);
  v635 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v636) = boost::placeholders::_4;
  v637 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1110,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v635,
           v636,
           v634);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1617,
    v637,
    0);
  v638 = std::wstring::wstring(v939, v1241);
  v639 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v640) = boost::placeholders::_4;
  v641 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1111,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v639,
           v640,
           v638);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1616,
    v641,
    0);
  v642 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1699,
           (unsigned int)v1241,
           (int)this + 176,
           (unsigned int)v1616,
           (__int64)v1617,
           (__int64)v1618,
           (__int64)v1619,
           (__int64)v1620);
  Uev::Setting<unsigned long>::operator=((char *)this + 16832, v642);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1699);
  boost::function<bool (void)>::~function<bool (void)>(v1616);
  boost::function<bool (void)>::~function<bool (void)>(v1617);
  boost::function<bool (void)>::~function<bool (void)>(v1618);
  boost::function<bool (void)>::~function<bool (void)>(v1619);
  boost::function<bool (void)>::~function<bool (void)>(v1620);
  Uev::Configuration::InsertSettingMap(v616, v1241, (char *)v616 + 16832);
  boost::filesystem::path::~path((boost::filesystem::path *)v1241);
  std::wstring::wstring(v1242, L"SyncProviderPingEnabled");
  boost::function_bool___cdecl_void__::function_bool___cdecl_void____lambda_9593e404f0a8e266196fc09c155e984b___(
    v1625,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1624, 0);
  v643 = std::wstring::wstring(v940, v1242);
  v644 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v645) = boost::placeholders::_4;
  v646 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1112,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v644,
           v645,
           v643);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1623,
    v646,
    0);
  v647 = std::wstring::wstring(v941, v1242);
  v648 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v649) = boost::placeholders::_4;
  v650 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1113,
           (unsigned int) Uev::ConfigUtil::`vcall'{168,{flat}},
           v648,
           v649,
           v647);
  boost::function<bool (enum Uev::SettingSource,bool const &,long &)>::function<bool (enum Uev::SettingSource,bool const &,long &)>(
    v1622,
    v650,
    0);
  v651 = std::wstring::wstring(v942, v1242);
  v652 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v653) = boost::placeholders::_4;
  v654 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,bool &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1114,
           (unsigned int) Uev::ConfigUtil::`vcall'{120,{flat}},
           v652,
           v653,
           v651);
  boost::function<bool (enum Uev::SettingSource,bool &,long &)>::function<bool (enum Uev::SettingSource,bool &,long &)>(
    v1621,
    v654,
    0);
  v655 = Uev::Setting<bool>::Setting<bool>(
           (unsigned int)v1700,
           (unsigned int)v1242,
           (int)this + 176,
           (unsigned int)v1621,
           (__int64)v1622,
           (__int64)v1623,
           (__int64)v1624,
           (__int64)v1625);
  Uev::Setting<unsigned long>::operator=((char *)this + 5104, v655);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1700);
  boost::function<bool (void)>::~function<bool (void)>(v1621);
  boost::function<bool (void)>::~function<bool (void)>(v1622);
  boost::function<bool (void)>::~function<bool (void)>(v1623);
  boost::function<bool (void)>::~function<bool (void)>(v1624);
  boost::function<bool (void)>::~function<bool (void)>(v1625);
  Uev::Configuration::InsertSettingMap(v616, v1242, (char *)v616 + 5104);
  boost::filesystem::path::~path((boost::filesystem::path *)v1242);
  std::wstring::wstring(v1267, L"LkgFrequencyThreshold");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_29219e7d53bcd5354274605418f2297f___(
    v1630,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1629, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1628, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1627, 0);
  v656 = std::wstring::wstring(v943, v1267);
  v657 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v658) = boost::placeholders::_4;
  v659 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1115,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v657,
           v658,
           v656);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1626,
    v659,
    0);
  v660 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1701,
           (unsigned int)v1267,
           (int)this + 176,
           (unsigned int)v1626,
           (__int64)v1627,
           (__int64)v1628,
           (__int64)v1629,
           (__int64)v1630);
  Uev::Setting<unsigned long>::operator=((char *)this + 17440, v660);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1701);
  boost::function<bool (void)>::~function<bool (void)>(v1626);
  boost::function<bool (void)>::~function<bool (void)>(v1627);
  boost::function<bool (void)>::~function<bool (void)>(v1628);
  boost::function<bool (void)>::~function<bool (void)>(v1629);
  boost::function<bool (void)>::~function<bool (void)>(v1630);
  Uev::Configuration::InsertSettingMap(v616, v1267, (char *)v616 + 17440);
  boost::filesystem::path::~path((boost::filesystem::path *)v1267);
  std::wstring::wstring(v1268, L"LkgStableExportsThreshold");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_d110ec105b2e657bd12d8242e13c011f___(
    v1429,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1428, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1427, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1632, 0);
  v661 = std::wstring::wstring(v944, v1268);
  v662 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v663) = boost::placeholders::_4;
  v664 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1116,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v662,
           v663,
           v661);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1631,
    v664,
    0);
  v665 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1702,
           (unsigned int)v1268,
           (int)this + 176,
           (unsigned int)v1631,
           (__int64)v1632,
           (__int64)v1427,
           (__int64)v1428,
           (__int64)v1429);
  Uev::Setting<unsigned long>::operator=((char *)this + 17744, v665);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1702);
  boost::function<bool (void)>::~function<bool (void)>(v1631);
  boost::function<bool (void)>::~function<bool (void)>(v1632);
  boost::function<bool (void)>::~function<bool (void)>(v1427);
  boost::function<bool (void)>::~function<bool (void)>(v1428);
  boost::function<bool (void)>::~function<bool (void)>(v1429);
  Uev::Configuration::InsertSettingMap(v616, v1268, (char *)v616 + 17744);
  boost::filesystem::path::~path((boost::filesystem::path *)v1268);
  std::wstring::wstring(v1243, L"VolatilePooledVdiMode");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_bf596b5797113df4baf40e7015bee802___(
    v1434,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1433, 0);
  v666 = std::wstring::wstring(v945, v1243);
  v667 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v668) = boost::placeholders::_4;
  v669 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1117,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v667,
           v668,
           v666);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1432,
    v669,
    0);
  v670 = std::wstring::wstring(v946, v1243);
  v671 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v672) = boost::placeholders::_4;
  v673 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1118,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v671,
           v672,
           v670);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1431,
    v673,
    0);
  v674 = std::wstring::wstring(v947, v1243);
  v675 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v676) = boost::placeholders::_4;
  v677 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1119,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v675,
           v676,
           v674);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1430,
    v677,
    0);
  v678 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1703,
           (unsigned int)v1243,
           (int)this + 176,
           (unsigned int)v1430,
           (__int64)v1431,
           (__int64)v1432,
           (__int64)v1433,
           (__int64)v1434);
  Uev::Setting<unsigned long>::operator=((char *)this + 18048, v678);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1703);
  boost::function<bool (void)>::~function<bool (void)>(v1430);
  boost::function<bool (void)>::~function<bool (void)>(v1431);
  boost::function<bool (void)>::~function<bool (void)>(v1432);
  boost::function<bool (void)>::~function<bool (void)>(v1433);
  boost::function<bool (void)>::~function<bool (void)>(v1434);
  Uev::Configuration::InsertSettingMap(v616, v1243, (char *)v616 + 18048);
  boost::filesystem::path::~path((boost::filesystem::path *)v1243);
  std::wstring::wstring(v1244, L"MaxPackageSettingSizeInBytes");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1439, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1438, 0);
  v679 = std::wstring::wstring(v948, v1244);
  v680 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v681) = boost::placeholders::_4;
  v682 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1120,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v680,
           v681,
           v679);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1437,
    v682,
    0);
  v683 = std::wstring::wstring(v949, v1244);
  v684 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v685) = boost::placeholders::_4;
  v686 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1121,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v684,
           v685,
           v683);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1436,
    v686,
    0);
  v687 = std::wstring::wstring(v950, v1244);
  v688 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v689) = boost::placeholders::_4;
  v690 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1122,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v688,
           v689,
           v687);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1435,
    v690,
    0);
  v691 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1704,
           (unsigned int)v1244,
           (int)this + 176,
           (unsigned int)v1435,
           (__int64)v1436,
           (__int64)v1437,
           (__int64)v1438,
           (__int64)v1439);
  Uev::Setting<unsigned long>::operator=((char *)this + 8448, v691);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1704);
  boost::function<bool (void)>::~function<bool (void)>(v1435);
  boost::function<bool (void)>::~function<bool (void)>(v1436);
  boost::function<bool (void)>::~function<bool (void)>(v1437);
  boost::function<bool (void)>::~function<bool (void)>(v1438);
  boost::function<bool (void)>::~function<bool (void)>(v1439);
  Uev::Configuration::InsertSettingMap(v616, v1244, (char *)v616 + 8448);
  boost::filesystem::path::~path((boost::filesystem::path *)v1244);
  std::wstring::wstring(v1273, L"ProfileList");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1444, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1443, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1442, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1441, 0);
  v692 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v803) = boost::placeholders::_4;
  LOBYTE(v771) = boost::placeholders::_4;
  LOBYTE(v693) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::list<std::wstring> &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>>(
                      v889,
                       Uev::ConfigUtil::`vcall'{456,{flat}},
                      v692,
                      v693,
                      v771,
                      v803);
  boost::function<bool (enum Uev::SettingSource,std::list<std::wstring> &,long &)>::function<bool (enum Uev::SettingSource,std::list<std::wstring> &,long &)>(
    v1440,
    &v844,
    0);
  v694 = Uev::Setting<std::list<std::wstring>>::Setting<std::list<std::wstring>>(
           (unsigned int)v1705,
           (unsigned int)v1273,
           (int)this + 176,
           (unsigned int)v1440,
           (__int64)v1441,
           (__int64)v1442,
           (__int64)v1443,
           (__int64)v1444);
  Uev::Setting<unsigned long>::operator=((char *)this + 8752, v694);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1705);
  boost::function<bool (void)>::~function<bool (void)>(v1440);
  boost::function<bool (void)>::~function<bool (void)>(v1441);
  boost::function<bool (void)>::~function<bool (void)>(v1442);
  boost::function<bool (void)>::~function<bool (void)>(v1443);
  boost::function<bool (void)>::~function<bool (void)>(v1444);
  Uev::Configuration::InsertSettingMap(v616, v1273, (char *)v616 + 8752);
  boost::filesystem::path::~path((boost::filesystem::path *)v1273);
  std::wstring::wstring(v1274, L"Profile");
  v695 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v804) = boost::placeholders::_4;
  LOBYTE(v772) = boost::placeholders::_4;
  LOBYTE(v696) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v890,
                       Uev::ConfigUtil::`vcall'{472,{flat}},
                      v695,
                      v696,
                      v772,
                      v804,
                      v836);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1450,
    &v844,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1449, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1448, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1447, 0);
  v697 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v805) = boost::placeholders::_4;
  LOBYTE(v773) = boost::placeholders::_4;
  LOBYTE(v698) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v891,
                       Uev::ConfigUtil::`vcall'{464,{flat}},
                      v697,
                      v698,
                      v773,
                      v805,
                      v837);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1446,
    &v844,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1445, 0);
  v699 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1706,
           (unsigned int)v1274,
           (int)this + 176,
           (unsigned int)v1445,
           (__int64)v1446,
           (__int64)v1447,
           (__int64)v1448,
           (__int64)v1449,
           (__int64)v1450);
  Uev::Setting<std::wstring>::operator=((char *)this + 9056, v699);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1706);
  boost::function<bool (void)>::~function<bool (void)>(v1445);
  boost::function<bool (void)>::~function<bool (void)>(v1446);
  boost::function<bool (void)>::~function<bool (void)>(v1447);
  boost::function<bool (void)>::~function<bool (void)>(v1448);
  boost::function<bool (void)>::~function<bool (void)>(v1449);
  boost::function<bool (void)>::~function<bool (void)>(v1450);
  Uev::Configuration::InsertSettingMap(v616, v1274, (char *)v616 + 9056);
  boost::filesystem::path::~path((boost::filesystem::path *)v1274);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1455, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1454, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1453, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1452, 0);
  v700 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v838) = boost::placeholders::_4;
  LOBYTE(v806) = boost::placeholders::_4;
  LOBYTE(v774) = boost::placeholders::_4;
  LOBYTE(v701) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v892,
                       Uev::ConfigUtil::`vcall'{480,{flat}},
                      v700,
                      v701,
                      v774,
                      v806,
                      v838);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> &,long &)>(
    v1451,
    &v844,
    0);
  v702 = Uev::SettingGroup<std::list<std::wstring>>::SettingGroup<std::list<std::wstring>>(
           (unsigned int)v1648,
           (int)this + 176,
           (unsigned int)v1451,
           (unsigned int)v1452,
           (__int64)v1453,
           (__int64)v1454,
           (__int64)v1455);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 9360, v702);
  Uev::SettingGroup<std::list<std::wstring>>::~SettingGroup<std::list<std::wstring>>(v1648);
  boost::function<bool (void)>::~function<bool (void)>(v1451);
  boost::function<bool (void)>::~function<bool (void)>(v1452);
  boost::function<bool (void)>::~function<bool (void)>(v1453);
  boost::function<bool (void)>::~function<bool (void)>(v1454);
  boost::function<bool (void)>::~function<bool (void)>(v1455);
  std::wstring::wstring(v1285, L"ProfileTemplateList");
  Uev::Configuration::InsertGroupSettingMap(v616, v1285, (char *)v616 + 9360);
  boost::filesystem::path::~path((boost::filesystem::path *)v1285);
  v703 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v839) = boost::placeholders::_4;
  LOBYTE(v807) = boost::placeholders::_4;
  LOBYTE(v775) = boost::placeholders::_4;
  LOBYTE(v704) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v893,
                       Uev::ConfigUtil::`vcall'{496,{flat}},
                      v703,
                      v704,
                      v775,
                      v807,
                      v839);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>(
    v1461,
    &v844,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1460, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1459, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1458, 0);
  v705 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v840) = boost::placeholders::_4;
  LOBYTE(v808) = boost::placeholders::_4;
  LOBYTE(v776) = boost::placeholders::_4;
  LOBYTE(v706) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v894,
                       Uev::ConfigUtil::`vcall'{488,{flat}},
                      v705,
                      v706,
                      v776,
                      v808,
                      v840);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &)>(
    v1457,
    &v844,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1456, 0);
  v707 = Uev::SettingGroup<std::wstring>::SettingGroup<std::wstring>(
           (unsigned int)v1649,
           (int)this + 176,
           (unsigned int)v1456,
           (unsigned int)v1457,
           (__int64)v1458,
           (__int64)v1459,
           (__int64)v1460,
           (__int64)v1461);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 9632, v707);
  Uev::SettingGroup<std::wstring>::~SettingGroup<std::wstring>(v1649);
  boost::function<bool (void)>::~function<bool (void)>(v1456);
  boost::function<bool (void)>::~function<bool (void)>(v1457);
  boost::function<bool (void)>::~function<bool (void)>(v1458);
  boost::function<bool (void)>::~function<bool (void)>(v1459);
  boost::function<bool (void)>::~function<bool (void)>(v1460);
  boost::function<bool (void)>::~function<bool (void)>(v1461);
  std::wstring::wstring(v1283, L"ProfileTemplateAssociation");
  Uev::Configuration::InsertGroupSettingMap(v616, v1283, (char *)v616 + 9632);
  boost::filesystem::path::~path((boost::filesystem::path *)v1283);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1466, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1465, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1464, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1463, 0);
  v708 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v841) = boost::placeholders::_4;
  LOBYTE(v809) = boost::placeholders::_4;
  LOBYTE(v777) = boost::placeholders::_4;
  LOBYTE(v709) = boost::placeholders::_4;
  v844 = *(_OWORD *)boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,boost::arg<2>,boost::arg<3>,boost::arg<4>>(
                      v895,
                       Uev::ConfigUtil::`vcall'{504,{flat}},
                      v708,
                      v709,
                      v777,
                      v809,
                      v841);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,std::wstring &,long &)>(
    v1462,
    &v844,
    0);
  v710 = Uev::SettingGroup<std::wstring>::SettingGroup<std::wstring>(
           (unsigned int)v1650,
           (int)this + 176,
           (unsigned int)v1462,
           (unsigned int)v1463,
           (__int64)v1464,
           (__int64)v1465,
           (__int64)v1466);
  Uev::SettingGroup<unsigned __int64>::operator=((char *)this + 9904, v710);
  Uev::SettingGroup<std::wstring>::~SettingGroup<std::wstring>(v1650);
  boost::function<bool (void)>::~function<bool (void)>(v1462);
  boost::function<bool (void)>::~function<bool (void)>(v1463);
  boost::function<bool (void)>::~function<bool (void)>(v1464);
  boost::function<bool (void)>::~function<bool (void)>(v1465);
  boost::function<bool (void)>::~function<bool (void)>(v1466);
  std::wstring::wstring(v1284, L"TemplateProfile");
  Uev::Configuration::InsertGroupSettingMap(v616, v1284, (char *)v616 + 9904);
  boost::filesystem::path::~path((boost::filesystem::path *)v1284);
  std::wstring::wstring(v1245, L"ProfileWin8AppAssociation");
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1471, 0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1470, 0);
  v711 = std::wstring::wstring(v951, v1245);
  v712 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v713) = boost::placeholders::_4;
  v714 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1123,
           (unsigned int) Uev::ConfigUtil::`vcall'{528,{flat}},
           v712,
           v713,
           v711);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1469,
    v714,
    0);
  v715 = std::wstring::wstring(v952, v1245);
  v716 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v717) = boost::placeholders::_4;
  v718 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1124,
           (unsigned int) Uev::ConfigUtil::`vcall'{520,{flat}},
           v716,
           v717,
           v715);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1468,
    v718,
    0);
  v719 = std::wstring::wstring(v953, v1245);
  v720 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v721) = boost::placeholders::_4;
  v722 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1125,
           (unsigned int) Uev::ConfigUtil::`vcall'{512,{flat}},
           v720,
           v721,
           v719);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1467,
    v722,
    0);
  v723 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1707,
           (unsigned int)v1245,
           (int)this + 176,
           (unsigned int)v1467,
           (__int64)v1468,
           (__int64)v1469,
           (__int64)v1470,
           (__int64)v1471);
  Uev::Setting<std::wstring>::operator=((char *)this + 10176, v723);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1707);
  boost::function<bool (void)>::~function<bool (void)>(v1467);
  boost::function<bool (void)>::~function<bool (void)>(v1468);
  boost::function<bool (void)>::~function<bool (void)>(v1469);
  boost::function<bool (void)>::~function<bool (void)>(v1470);
  boost::function<bool (void)>::~function<bool (void)>(v1471);
  Uev::Configuration::InsertSettingMap(v616, v1245, (char *)v616 + 10176);
  boost::filesystem::path::~path((boost::filesystem::path *)v1245);
  std::wstring::wstring(v1246, L"VdiCollectionName");
  boost::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void__::function_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______cdecl_void____lambda_8af6cecf90231203876c99860bd73dc0___(
    v1476,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1475, 0);
  v724 = std::wstring::wstring(v954, v1246);
  v725 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v726) = boost::placeholders::_4;
  v727 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1126,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v725,
           v726,
           v724);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1474,
    v727,
    0);
  v728 = std::wstring::wstring(v955, v1246);
  v729 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v730) = boost::placeholders::_4;
  v731 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1127,
           (unsigned int) Uev::ConfigUtil::`vcall'{128,{flat}},
           v729,
           v730,
           v728);
  boost::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>::function<bool (enum Uev::SettingSource,std::wstring const &,long &)>(
    v1473,
    v731,
    0);
  v732 = std::wstring::wstring(v957, v1246);
  v733 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v842) = boost::placeholders::_4;
  LOBYTE(v810) = boost::placeholders::_4;
  LOBYTE(v734) = boost::placeholders::_4;
  v735 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>,bool>(
           (unsigned int)&v1207,
           (unsigned int) Uev::ConfigUtil::`vcall'{80,{flat}},
           v733,
           v734,
           v732,
           v810,
           v842,
           1);
  boost::function<bool (enum Uev::SettingSource,std::wstring &,long &)>::function<bool (enum Uev::SettingSource,std::wstring &,long &)>(
    v1472,
    v735,
    0);
  v736 = Uev::Setting<std::wstring>::Setting<std::wstring>(
           (unsigned int)v1708,
           (unsigned int)v1246,
           (int)this + 176,
           (unsigned int)v1472,
           (__int64)v1473,
           (__int64)v1474,
           (__int64)v1475,
           (__int64)v1476);
  Uev::Setting<std::wstring>::operator=((char *)this + 10480, v736);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1708);
  boost::function<bool (void)>::~function<bool (void)>(v1472);
  boost::function<bool (void)>::~function<bool (void)>(v1473);
  boost::function<bool (void)>::~function<bool (void)>(v1474);
  boost::function<bool (void)>::~function<bool (void)>(v1475);
  boost::function<bool (void)>::~function<bool (void)>(v1476);
  Uev::Configuration::InsertSettingMap(v616, v1246, (char *)v616 + 10480);
  boost::filesystem::path::~path((boost::filesystem::path *)v1246);
  std::wstring::wstring(v1247, L"LogOffWaitInterval");
  boost::function_unsigned_long___cdecl_void__::function_unsigned_long___cdecl_void____lambda_5faf98b309ca9252421baf90594ef652___(
    v1481,
    0,
    0);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(v1480, 0);
  v737 = std::wstring::wstring(v958, v1247);
  v738 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v739) = boost::placeholders::_4;
  v740 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>>(
           (unsigned int)&v1128,
           (unsigned int) Uev::ConfigUtil::`vcall'{176,{flat}},
           v738,
           v739,
           v737);
  boost::function<bool (enum Uev::SettingSource,long &)>::function<bool (enum Uev::SettingSource,long &)>(
    v1479,
    v740,
    0);
  v741 = std::wstring::wstring(v959, v1247);
  v742 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v743) = boost::placeholders::_4;
  v744 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1129,
           (unsigned int) Uev::ConfigUtil::`vcall'{152,{flat}},
           v742,
           v743,
           v741);
  boost::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>::function<bool (enum Uev::SettingSource,unsigned long const &,long &)>(
    v1478,
    v744,
    0);
  v745 = std::wstring::wstring(v960, v1247);
  v746 = std::_Ptr_base<Uev::ConfigUtil>::get((char *)this + 136);
  LOBYTE(v747) = boost::placeholders::_4;
  v748 = boost::bind<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(
           (unsigned int)&v1130,
           (unsigned int) Uev::ConfigUtil::`vcall'{104,{flat}},
           v746,
           v747,
           v745);
  boost::function<bool (enum Uev::SettingSource,unsigned long &,long &)>::function<bool (enum Uev::SettingSource,unsigned long &,long &)>(
    v1477,
    v748,
    0);
  v749 = Uev::Setting<unsigned long>::Setting<unsigned long>(
           (unsigned int)v1709,
           (unsigned int)v1247,
           (int)this + 176,
           (unsigned int)v1477,
           (__int64)v1478,
           (__int64)v1479,
           (__int64)v1480,
           (__int64)v1481);
  Uev::Setting<unsigned long>::operator=((char *)this + 18352, v749);
  Uev::Setting<std::wstring>::~Setting<std::wstring>(v1709);
  boost::function<bool (void)>::~function<bool (void)>(v1477);
  boost::function<bool (void)>::~function<bool (void)>(v1478);
  boost::function<bool (void)>::~function<bool (void)>(v1479);
  boost::function<bool (void)>::~function<bool (void)>(v1480);
  boost::function<bool (void)>::~function<bool (void)>(v1481);
  Uev::Configuration::InsertSettingMap(v616, v1247, (char *)v616 + 18352);
  boost::filesystem::path::~path((boost::filesystem::path *)v1247);
}

```

## disassembly

```asm
0x14007a2cc  push    rbp
0x14007a2ce  push    rbx
0x14007a2cf  push    rsi
0x14007a2d0  push    rdi
0x14007a2d1  push    r12
0x14007a2d3  push    r13
0x14007a2d5  push    r14
0x14007a2d7  push    r15
0x14007a2d9  lea     rbp, [rsp-0C588h]
0x14007a2e1  mov     eax, 0C688h
0x14007a2e6  call    _alloca_probe
0x14007a2eb  sub     rsp, rax
0x14007a2ee  mov     rax, cs:__security_cookie
0x14007a2f5  xor     rax, rsp
0x14007a2f8  mov     [rbp+0C5C0h+var_50], rax
0x14007a2ff  mov     rsi, rcx
0x14007a302  mov     [rsp+0C6C0h+var_C670], rcx
0x14007a307  mov     dword ptr [rbp+0C5C0h+var_C638], 0
0x14007a30e  mov     [rbp+0C5C0h+var_C630], 5
0x14007a315  lea     rcx, [rbp+0C5C0h+var_C510]
0x14007a31c  call    ??0?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::deque<Uev::SettingSource>(void)
0x14007a321  mov     dword ptr [rbp+0C5C0h+var_C638], 1
0x14007a328  lea     rdx, [rbp+0C5C0h+var_C630]
0x14007a32c  lea     rcx, [rbp+0C5C0h+var_C510]
0x14007a333  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a338  mov     r9b, [rbp+0C5C0h+var_C640]
0x14007a33c  mov     r8, cs:?c@?1???$convert_to_container@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@XZ@4PEAV45@EA; std::vector<Uev::SettingSource> * `boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert_to_container<std::vector<Uev::SettingSource>>(void)'::`2'::c
0x14007a343  lea     rdx, [rbp+0C5C0h+var_C550]
0x14007a347  lea     rcx, [rbp+0C5C0h+var_C510]
0x14007a34e  call    ??$convert@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@AEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@PEBV34@Udefault_type_tag@12@@Z; boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert<std::vector<Uev::SettingSource>>(std::vector<Uev::SettingSource> const *,boost::assign_detail::default_type_tag)
0x14007a353  lea     rcx, [rsi+98h]
0x14007a35a  lea     rdx, [rbp+0C5C0h+var_C550]
0x14007a35e  call    ??4?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Uev::SettingSource>::operator=(std::vector<Uev::SettingSource> &&)
0x14007a363  lea     rcx, [rbp+0C5C0h+var_C550]
0x14007a367  call    ?_Tidy@?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::SettingSource>::_Tidy(void)
0x14007a36c  mov     dword ptr [rbp+0C5C0h+var_C638], 6
0x14007a373  lea     rcx, [rbp+0C5C0h+var_C510]
0x14007a37a  call    ??1?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::~deque<Uev::SettingSource>(void)
0x14007a37f  mov     [rbp+0C5C0h+var_C62C], 0
0x14007a386  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a38a  call    ??0?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::deque<Uev::SettingSource>(void)
0x14007a38f  mov     dword ptr [rbp+0C5C0h+var_C638], 0Eh
0x14007a396  lea     rdx, [rbp+0C5C0h+var_C62C]
0x14007a39a  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a39e  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a3a3  mov     [rbp+0C5C0h+var_C628], 1
0x14007a3aa  lea     rdx, [rbp+0C5C0h+var_C628]
0x14007a3ae  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a3b2  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a3b7  mov     [rbp+0C5C0h+var_C624], 2
0x14007a3be  lea     rdx, [rbp+0C5C0h+var_C624]
0x14007a3c2  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a3c6  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a3cb  mov     [rbp+0C5C0h+var_C620], 3
0x14007a3d2  lea     rdx, [rbp+0C5C0h+var_C620]
0x14007a3d6  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a3da  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a3df  mov     r9b, [rbp+0C5C0h+var_C640]
0x14007a3e3  mov     r8, cs:?c@?1???$convert_to_container@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@XZ@4PEAV45@EA; std::vector<Uev::SettingSource> * `boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert_to_container<std::vector<Uev::SettingSource>>(void)'::`2'::c
0x14007a3ea  lea     rdx, [rbp+0C5C0h+var_C5B0]
0x14007a3ee  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a3f2  call    ??$convert@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@AEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@PEBV34@Udefault_type_tag@12@@Z; boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert<std::vector<Uev::SettingSource>>(std::vector<Uev::SettingSource> const *,boost::assign_detail::default_type_tag)
0x14007a3f7  lea     rcx, [rsi+0B0h]
0x14007a3fe  lea     rdx, [rbp+0C5C0h+var_C5B0]
0x14007a402  call    ??4?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Uev::SettingSource>::operator=(std::vector<Uev::SettingSource> &&)
0x14007a407  lea     rcx, [rbp+0C5C0h+var_C5B0]
0x14007a40b  call    ?_Tidy@?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::SettingSource>::_Tidy(void)
0x14007a410  mov     dword ptr [rbp+0C5C0h+var_C638], 36h ; '6'
0x14007a417  lea     rcx, [rbp+0C5C0h+var_C608]
0x14007a41b  call    ??1?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::~deque<Uev::SettingSource>(void)
0x14007a420  mov     [rbp+0C5C0h+var_C61C], 1
0x14007a427  lea     rcx, [rbp+0C5C0h+var_C538]
0x14007a42e  call    ??0?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::deque<Uev::SettingSource>(void)
0x14007a433  mov     dword ptr [rbp+0C5C0h+var_C638], 76h ; 'v'
0x14007a43a  lea     rdx, [rbp+0C5C0h+var_C61C]
0x14007a43e  lea     rcx, [rbp+0C5C0h+var_C538]
0x14007a445  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a44a  mov     [rbp+0C5C0h+var_C618], 3
0x14007a451  lea     rdx, [rbp+0C5C0h+var_C618]
0x14007a455  lea     rcx, [rbp+0C5C0h+var_C538]
0x14007a45c  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a461  mov     r9b, [rbp+0C5C0h+var_C640]
0x14007a465  mov     r8, cs:?c@?1???$convert_to_container@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@XZ@4PEAV45@EA; std::vector<Uev::SettingSource> * `boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert_to_container<std::vector<Uev::SettingSource>>(void)'::`2'::c
0x14007a46c  lea     rdx, [rbp+0C5C0h+var_C598]
0x14007a470  lea     rcx, [rbp+0C5C0h+var_C538]
0x14007a477  call    ??$convert@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@AEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@PEBV34@Udefault_type_tag@12@@Z; boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert<std::vector<Uev::SettingSource>>(std::vector<Uev::SettingSource> const *,boost::assign_detail::default_type_tag)
0x14007a47c  lea     r15, [rsi+0C8h]
0x14007a483  lea     rdx, [rbp+0C5C0h+var_C598]
0x14007a487  mov     rcx, r15
0x14007a48a  call    ??4?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Uev::SettingSource>::operator=(std::vector<Uev::SettingSource> &&)
0x14007a48f  lea     rcx, [rbp+0C5C0h+var_C598]
0x14007a493  call    ?_Tidy@?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::SettingSource>::_Tidy(void)
0x14007a498  mov     dword ptr [rbp+0C5C0h+var_C638], 1B6h
0x14007a49f  lea     rcx, [rbp+0C5C0h+var_C538]
0x14007a4a6  call    ??1?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::~deque<Uev::SettingSource>(void)
0x14007a4ab  mov     [rbp+0C5C0h+var_C614], 2
0x14007a4b2  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x14007a4b9  call    ??0?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::deque<Uev::SettingSource>(void)
0x14007a4be  mov     dword ptr [rbp+0C5C0h+var_C638], 3B6h
0x14007a4c5  lea     rdx, [rbp+0C5C0h+var_C614]
0x14007a4c9  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x14007a4d0  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a4d5  mov     r9b, [rbp+0C5C0h+var_C640]
0x14007a4d9  mov     r8, cs:?c@?1???$convert_to_container@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@XZ@4PEAV45@EA; std::vector<Uev::SettingSource> * `boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert_to_container<std::vector<Uev::SettingSource>>(void)'::`2'::c
0x14007a4e0  lea     rdx, [rbp+0C5C0h+var_C580]
0x14007a4e4  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x14007a4eb  call    ??$convert@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@AEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@PEBV34@Udefault_type_tag@12@@Z; boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert<std::vector<Uev::SettingSource>>(std::vector<Uev::SettingSource> const *,boost::assign_detail::default_type_tag)
0x14007a4f0  lea     r13, [rsi+0E0h]
0x14007a4f7  lea     rdx, [rbp+0C5C0h+var_C580]
0x14007a4fb  mov     rcx, r13
0x14007a4fe  call    ??4?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Uev::SettingSource>::operator=(std::vector<Uev::SettingSource> &&)
0x14007a503  lea     rcx, [rbp+0C5C0h+var_C580]
0x14007a507  call    ?_Tidy@?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::SettingSource>::_Tidy(void)
0x14007a50c  mov     dword ptr [rbp+0C5C0h+var_C638], 0DB6h
0x14007a513  lea     rcx, [rbp+0C5C0h+var_C4E8]
0x14007a51a  call    ??1?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::~deque<Uev::SettingSource>(void)
0x14007a51f  mov     [rbp+0C5C0h+var_C610], 3
0x14007a526  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x14007a52d  call    ??0?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::deque<Uev::SettingSource>(void)
0x14007a532  mov     dword ptr [rbp+0C5C0h+var_C638], 1DB6h
0x14007a539  lea     rdx, [rbp+0C5C0h+var_C610]
0x14007a53d  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x14007a544  call    ??$_Emplace_back_internal@W4SettingSource@Uev@@@?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAX$$QEAW4SettingSource@Uev@@@Z; std::deque<Uev::SettingSource>::_Emplace_back_internal<Uev::SettingSource>(Uev::SettingSource &&)
0x14007a549  mov     r9b, [rbp+0C5C0h+var_C640]
0x14007a54d  mov     r8, cs:?c@?1???$convert_to_container@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@QEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@XZ@4PEAV45@EA; std::vector<Uev::SettingSource> * `boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert_to_container<std::vector<Uev::SettingSource>>(void)'::`2'::c
0x14007a554  lea     rdx, [rbp+0C5C0h+var_C568]
0x14007a558  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x14007a55f  call    ??$convert@V?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@@?$converter@V?$generic_list@W4SettingSource@Uev@@@assign_detail@boost@@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@W4SettingSource@Uev@@@std@@@std@@@std@@@assign_detail@boost@@AEBA?AV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@PEBV34@Udefault_type_tag@12@@Z; boost::assign_detail::converter<boost::assign_detail::generic_list<Uev::SettingSource>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<Uev::SettingSource>>>>::convert<std::vector<Uev::SettingSource>>(std::vector<Uev::SettingSource> const *,boost::assign_detail::default_type_tag)
0x14007a564  lea     r12, [rsi+0F8h]
0x14007a56b  lea     rdx, [rbp+0C5C0h+var_C568]
0x14007a56f  mov     rcx, r12
0x14007a572  call    ??4?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Uev::SettingSource>::operator=(std::vector<Uev::SettingSource> &&)
0x14007a577  lea     rcx, [rbp+0C5C0h+var_C568]
0x14007a57b  call    ?_Tidy@?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@AEAAXXZ; std::vector<Uev::SettingSource>::_Tidy(void)
0x14007a580  nop
0x14007a581  lea     rcx, [rbp+0C5C0h+var_C4C0]
0x14007a588  call    ??1?$deque@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@std@@QEAA@XZ; std::deque<Uev::SettingSource>::~deque<Uev::SettingSource>(void)
0x14007a58d  lea     rdx, aMaxpackagesize; "MaxPackageSizeInBytes"
0x14007a594  lea     rcx, [rbp+0C5C0h+var_8DB8]
0x14007a59b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14007a5a0  nop
0x14007a5a1  xorps   xmm0, xmm0
0x14007a5a4  xor     eax, eax
0x14007a5a6  movups  [rbp+0C5C0h+var_8AF0], xmm0
0x14007a5ad  movups  [rbp+0C5C0h+var_8AE0], xmm0
0x14007a5b4  mov     [rbp+0C5C0h+var_8AD0], rax
0x14007a5bb  mov     qword ptr [rbp+0C5C0h+var_8AF0], rax
0x14007a5c2  movups  [rbp+0C5C0h+var_8B18], xmm0
0x14007a5c9  movups  [rbp+0C5C0h+var_8B08], xmm0
0x14007a5d0  mov     [rbp+0C5C0h+var_8AF8], rax
0x14007a5d7  mov     qword ptr [rbp+0C5C0h+var_8B18], rax
0x14007a5de  mov     dil, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a5e5  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x14007a5ec  lea     rcx, [rbp+0C5C0h+var_BA38]
0x14007a5f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007a5f8  mov     r14, rax
0x14007a5fb  mov     [rbp+0C5C0h+var_C638], rax
0x14007a5ff  mov     bl, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a605  mov     rsi, [rsi+88h]
0x14007a60c  mov     rdx, rax
0x14007a60f  lea     rcx, [rbp+0C5C0h+var_C498]
0x14007a616  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007a61b  mov     byte ptr [rsp+0C6C0h+var_C6A0], dil
0x14007a620  lea     r9, [rbp+0C5C0h+var_C498]
0x14007a627  mov     r8b, bl
0x14007a62a  mov     rdx, rsi
0x14007a62d  lea     rcx, [rbp+0C5C0h+var_5238]
0x14007a634  call    ??0?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@boost@@QEAA@V?$value@PEAVConfigUtil@Uev@@@12@U?$arg@$00@2@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@12@U?$arg@$01@2@@Z; boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>)
0x14007a639  nop
0x14007a63a  lea     rcx, ??_9ConfigUtil@Uev@@$BLA@AA; [thunk]: Uev::ConfigUtil::`vcall'{176,{flat}}
0x14007a641  mov     [rbp+0C5C0h+var_C5E0], rcx
0x14007a645  mov     rdx, rax
0x14007a648  lea     rcx, [rbp+0C5C0h+var_C5D8]
0x14007a64c  call    ??0?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@boost@@QEAA@AEBV012@@Z; boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>> const &)
0x14007a651  nop
0x14007a652  lea     rcx, [rbp+0C5C0h+var_5230]
0x14007a659  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a65e  nop
0x14007a65f  mov     rcx, r14
0x14007a662  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a667  lea     rax, [rbp+0C5C0h+var_C5E0]
0x14007a66b  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x14007a670  mov     rax, [rbp+0C5C0h+var_C5E0]
0x14007a674  mov     [rbp+0C5C0h+var_C478], rax
0x14007a67b  lea     rdx, [rbp+0C5C0h+var_C5D8]
0x14007a67f  lea     rcx, [rbp+0C5C0h+var_C470]
0x14007a686  call    ??0?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@boost@@QEAA@AEBV012@@Z; boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>> const &)
0x14007a68b  xor     r8d, r8d
0x14007a68e  lea     rdx, [rbp+0C5C0h+var_C478]
0x14007a695  lea     rcx, [rbp+0C5C0h+var_52A0]
0x14007a69c  call    ??$?0V?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@3@@_bi@boost@@@?$function2@_NW4SettingSource@Uev@@AEAJ@boost@@QEAA@V?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@3@@_bi@1@H@Z; boost::function2<bool,Uev::SettingSource,long &>::function2<bool,Uev::SettingSource,long &>(boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>>,int)
0x14007a6a1  nop
0x14007a6a2  lea     rcx, [rbp+0C5C0h+var_C5D0]
0x14007a6a6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a6ab  nop
0x14007a6ac  mov     dil, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a6b3  mov     bl, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a6b9  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x14007a6c0  lea     rcx, [rbp+0C5C0h+var_BA18]
0x14007a6c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007a6cc  mov     byte ptr [rsp+0C6C0h+var_C690], dil
0x14007a6d1  mov     byte ptr [rsp+0C6C0h+var_C698], bl
0x14007a6d5  mov     [rsp+0C6C0h+var_C6A0], rax
0x14007a6da  mov     r9b, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a6e1  mov     rsi, [rsp+0C6C0h+var_C670]
0x14007a6e6  lea     r14, [rsi+88h]
0x14007a6ed  mov     r8, [r14]
0x14007a6f0  lea     rdx, ??_9ConfigUtil@Uev@@$BJI@AA; [thunk]: Uev::ConfigUtil::`vcall'{152,{flat}}
0x14007a6f7  lea     rcx, [rbp+0C5C0h+var_A160]
0x14007a6fe  call    ??$bind@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJPEAV12@U?$arg@$00@boost@@V45@U?$arg@$01@7@U?$arg@$02@7@@boost@@YA?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@0@P8ConfigUtil@Uev@@EAA_NW4SettingSource@4@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@ZPEAV34@U?$arg@$00@0@V67@U?$arg@$01@0@U?$arg@$02@0@@Z; boost::bind<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong const &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(bool (Uev::ConfigUtil::*)(Uev::SettingSource,std::wstring const &,ulong const &,long &),Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>)
0x14007a703  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x14007a708  mov     rcx, [rax]
0x14007a70b  mov     [rbp+0C5C0h+var_C418], rcx
0x14007a712  lea     rbx, [rax+8]
0x14007a716  mov     rdx, rbx
0x14007a719  lea     rcx, [rbp+0C5C0h+var_C410]
0x14007a720  call    ??0?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@boost@@QEAA@AEBV012@@Z; boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>> const &)
0x14007a725  xor     r8d, r8d
0x14007a728  lea     rdx, [rbp+0C5C0h+var_C418]
0x14007a72f  lea     rcx, [rbp+0C5C0h+var_52C8]
0x14007a736  call    ??$?0V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@?$function3@_NW4SettingSource@Uev@@AEBKAEAJ@boost@@QEAA@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@1@H@Z; boost::function3<bool,Uev::SettingSource,ulong const &,long &>::function3<bool,Uev::SettingSource,ulong const &,long &>(boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>,int)
0x14007a73b  nop
0x14007a73c  lea     rcx, [rbx+8]
0x14007a740  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a745  nop
0x14007a746  mov     dil, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a74d  mov     bl, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a753  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x14007a75a  lea     rcx, [rbp+0C5C0h+var_B9F8]
0x14007a761  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14007a766  mov     byte ptr [rsp+0C6C0h+var_C690], dil
0x14007a76b  mov     byte ptr [rsp+0C6C0h+var_C698], bl
0x14007a76f  mov     [rsp+0C6C0h+var_C6A0], rax
0x14007a774  mov     r9b, cs:?_4@placeholders@boost@@3U?$arg@$03@2@B; boost::arg<4> const boost::placeholders::_4
0x14007a77b  mov     r8, [r14]
0x14007a77e  lea     rdx, ??_9ConfigUtil@Uev@@$BGI@AA; [thunk]: Uev::ConfigUtil::`vcall'{104,{flat}}
0x14007a785  lea     rcx, [rbp+0C5C0h+var_A130]
0x14007a78c  call    ??$bind@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJPEAV12@U?$arg@$00@boost@@V45@U?$arg@$01@7@U?$arg@$02@7@@boost@@YA?AV?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@0@P8ConfigUtil@Uev@@EBA_NW4SettingSource@4@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@ZPEAV34@U?$arg@$00@0@V67@U?$arg@$01@0@U?$arg@$02@0@@Z; boost::bind<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong &,long &,Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>>(bool (Uev::ConfigUtil::*)(Uev::SettingSource,std::wstring const &,ulong &,long &),Uev::ConfigUtil *,boost::arg<1>,std::wstring,boost::arg<2>,boost::arg<3>)
0x14007a791  mov     qword ptr [rsp+0C6C0h+var_C660], rax
0x14007a796  mov     rcx, [rax]
0x14007a799  mov     [rbp+0C5C0h+var_C448], rcx
0x14007a7a0  lea     rbx, [rax+8]
0x14007a7a4  mov     rdx, rbx
0x14007a7a7  lea     rcx, [rbp+0C5C0h+var_C440]
0x14007a7ae  call    ??0?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@boost@@QEAA@AEBV012@@Z; boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>(boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>> const &)
0x14007a7b3  xor     r8d, r8d
0x14007a7b6  lea     rdx, [rbp+0C5C0h+var_C448]
0x14007a7bd  lea     rcx, [rbp+0C5C0h+var_52F0]
0x14007a7c4  call    ??$?0V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@?$function3@_NW4SettingSource@Uev@@AEAKAEAJ@boost@@QEAA@V?$bind_t@_NV?$cmf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@1@H@Z; boost::function3<bool,Uev::SettingSource,ulong &,long &>::function3<bool,Uev::SettingSource,ulong &,long &>(boost::_bi::bind_t<bool,boost::_mfi::cmf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>,int)
0x14007a7c9  nop
0x14007a7ca  lea     rcx, [rbx+8]
0x14007a7ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a7d3  nop
0x14007a7d4  lea     rax, [rbp+0C5C0h+var_8AF0]
0x14007a7db  mov     [rsp+0C6C0h+var_C688], rax
0x14007a7e0  lea     rax, [rbp+0C5C0h+var_8B18]
0x14007a7e7  mov     [rsp+0C6C0h+var_C690], rax
0x14007a7ec  lea     rax, [rbp+0C5C0h+var_52A0]
0x14007a7f3  mov     [rsp+0C6C0h+var_C698], rax
0x14007a7f8  lea     rax, [rbp+0C5C0h+var_52C8]
0x14007a7ff  mov     [rsp+0C6C0h+var_C6A0], rax
0x14007a804  lea     r9, [rbp+0C5C0h+var_52F0]
0x14007a80b  lea     r8, [rsi+0B0h]
0x14007a812  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x14007a819  lea     rcx, [rbp+0C5C0h+var_4660]
0x14007a820  call    ??0?$Setting@K@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@W4SettingSource@Uev@@V?$allocator@W4SettingSource@Uev@@@std@@@3@AEBV?$function@$$A6A_NW4SettingSource@Uev@@AEAKAEAJ@Z@boost@@AEBV?$function@$$A6A_NW4SettingSource@Uev@@AEBKAEAJ@Z@6@AEBV?$function@$$A6A_NW4SettingSource@Uev@@AEAJ@Z@6@AEBV?$function@$$A6A_NAEBK@Z@6@AEBV?$function@$$A6AKXZ@6@@Z; Uev::Setting<ulong>::Setting<ulong>(std::wstring const &,std::vector<Uev::SettingSource> const &,boost::function<bool (Uev::SettingSource,ulong &,long &)> const &,boost::function<bool (Uev::SettingSource,ulong const &,long &)> const &,boost::function<bool (Uev::SettingSource,long &)> const &,boost::function<bool (ulong const &)> const &,boost::function<ulong (void)> const &)
0x14007a825  nop
0x14007a826  lea     rbx, [rsi+110h]
0x14007a82d  mov     rdx, rax
0x14007a830  mov     rcx, rbx
0x14007a833  call    ??4?$Setting@K@Uev@@QEAAAEAV01@$$QEAV01@@Z; Uev::Setting<ulong>::operator=(Uev::Setting<ulong> &&)
0x14007a838  nop
0x14007a839  lea     rcx, [rbp+0C5C0h+var_4660]
0x14007a840  call    ??1?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@UEAA@XZ; Uev::Setting<std::wstring>::~Setting<std::wstring>(void)
0x14007a845  nop
0x14007a846  lea     rcx, [rbp+0C5C0h+var_52F0]
0x14007a84d  call    ??1?$function@$$A6A_NXZ@boost@@QEAA@XZ; boost::function<bool (void)>::~function<bool (void)>(void)
0x14007a852  nop
0x14007a853  lea     rcx, [rbp+0C5C0h+var_52C8]
0x14007a85a  call    ??1?$function@$$A6A_NXZ@boost@@QEAA@XZ; boost::function<bool (void)>::~function<bool (void)>(void)
0x14007a85f  nop
0x14007a860  lea     rcx, [rbp+0C5C0h+var_52A0]
0x14007a867  call    ??1?$function@$$A6A_NXZ@boost@@QEAA@XZ; boost::function<bool (void)>::~function<bool (void)>(void)
0x14007a86c  nop
0x14007a86d  lea     rcx, [rbp+0C5C0h+var_8B18]
0x14007a874  call    ??1?$function@$$A6A_NXZ@boost@@QEAA@XZ; boost::function<bool (void)>::~function<bool (void)>(void)
0x14007a879  nop
0x14007a87a  lea     rcx, [rbp+0C5C0h+var_8AF0]
0x14007a881  call    ??1?$function@$$A6A_NXZ@boost@@QEAA@XZ; boost::function<bool (void)>::~function<bool (void)>(void)
0x14007a886  mov     r8, rbx
0x14007a889  lea     rdx, [rbp+0C5C0h+var_8DB8]
0x14007a890  mov     rcx, rsi
0x14007a893  call    ?InsertSettingMap@Configuration@Uev@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSettingBase@2@@Z; Uev::Configuration::InsertSettingMap(std::wstring const &,Uev::SettingBase &)
0x14007a898  nop
0x14007a899  lea     rcx, [rbp+0C5C0h+var_8DB8]; this
0x14007a8a0  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x14007a8a5  lea     rdx, aSyncenabled; "SyncEnabled"
0x14007a8ac  lea     rcx, [rbp+0C5C0h+var_8D98]
0x14007a8b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14007a8b8  nop
  ... truncated ...
```
