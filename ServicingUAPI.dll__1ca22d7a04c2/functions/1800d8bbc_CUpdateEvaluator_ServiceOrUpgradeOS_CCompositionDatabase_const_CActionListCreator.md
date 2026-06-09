# CUpdateEvaluator::ServiceOrUpgradeOS(CCompositionDatabase const *,CActionListCreator *)

- ea: `0x1800d8bbc`
- end: `0x1800dcfaf`
- name: `?ServiceOrUpgradeOS@CUpdateEvaluator@@AEAAJPEBVCCompositionDatabase@@PEAVCActionListCreator@@@Z`
- size: `17395`
- prototype: `__int64 __fastcall(CUpdateEvaluator *__hidden this, const struct CCompositionDatabase *, struct CActionListCreator *)`
- caller_count: `2`
- callee_count: `100`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d3df8`
- `0x1800d4a84`

## callees

- `0x1800031d0`
- `0x180003ba4`
- `0x180003bd4`
- `0x180006198`
- `0x1800062b8`
- `0x180006932`
- `0x180007e1c`
- `0x180008aa8`
- `0x180008b78`
- `0x1800095f0`
- `0x180009660`
- `0x180009750`
- `0x180009a60`
- `0x18000ba40`
- `0x18000ca2c`
- `0x18000cc98`
- `0x18000f614`
- `0x18000f874`
- `0x18000fb10`
- `0x180013760`
- `0x180013c24`
- `0x1800167d4`
- `0x180017394`
- `0x18001a2d0`
- `0x18001a810`
- `0x18001b964`
- `0x18001b9e4`
- `0x18001ba4c`
- `0x18001bb9c`
- `0x18001be70`
- `0x18001c3c4`
- `0x18001c478`
- `0x18001d368`
- `0x18002aa74`
- `0x18003ddc8`
- `0x180051468`
- `0x180051984`
- `0x180051c1c`
- `0x180051c5c`
- `0x1800662cc`
- `0x180067014`
- `0x1800670c8`
- `0x180067600`
- `0x1800721b4`
- `0x1800806b4`
- `0x180081b38`
- `0x180081b78`
- `0x1800843b8`
- `0x180087b08`
- `0x1800884b0`

## string_xrefs

- `0x1800dce67`: `SystemManifest`
- `0x1800d9c24`: `HotPatchReadiness`
- `0x1800da3a1`: `HotPatchReadiness`
- `0x1800d910e`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d91f5`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800d9e50`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800daafa`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dab88`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dacc9`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dae89`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800db14d`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800db383`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800db70a`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dba06`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dbcc8`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dbf26`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dc6ac`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dc71e`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dc7c4`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dcae7`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dcb92`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dcda7`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1800dc34f`: `Failed adding feature for token updates`
- `0x1800dc6dc`: `Failed adding feature for token updates`
- `0x1800dca9a`: `Failed adding feature for token updates`
- `0x1800da733`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x1800da806`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x1800daf84`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x1800dbe7e`: `Cannot remove required feature : {0}`
- `0x1800d8cca`: `Removing unused language: {0} from satellite consideration`
- `0x1800d8c07`: `arbiter: Evaluating features for installation`
- `0x1800d9319`: `install`
- `0x1800d9309`: `repair`
- `0x1800d90bf`: `Failed to evaluate deferred update; skipping: {0}`
- `0x1800d8f61`: `Failed to get deferred updates`
- `0x1800d9678`: `No installed features to update in Group {0}; evaluating features for conditional install`
- `0x1800d9895`: `Feature added due to standalone compDB: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da44b`: `Feature added due to repair conditional: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800dad46`: `Failed evaluation of repair feature conditional FMID: {0}, Feature: {1}`
- `0x1800da6aa`: `Feature added for processing because it's already installed: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da459`: `Feature not needed for repair: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da599`: `Feature added due to cumulative update or reoffer: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d9b69`: `Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800dadc9`: `Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da5d4`: `Feature added due to safe OS dynamic update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800daa44`: `Failed evaluation of remove feature conditional FMID: {0}, Feature: {1}`
- `0x1800da151`: `Feature (LanguagePack) removed because it was unused: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800d9f1f`: `Feature removed due to conditional: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da219`: `Not applicable Group: {0}, FMID: {1}, Feature: {2} as newer MSIX application is already installed`
- `0x1800da1b8`: `Feature removed due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800da703`: `Feature added due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800db957`: `Required feature not available for install: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800db33b`: `Unable to create feature modification request`
- `0x1800db9b9`: `Unable to create feature modification request`
- `0x1800dbc7b`: `Unable to create feature modification request`
- `0x1800dc28d`: `Feature modified due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800db8f2`: `Feature will not be removed due to dependency: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800dc66d`: `Failed adding InstallPackage actions for feature: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1800dcb43`: `Failed adding RemoveFeature: Feature: {}`
- `0x1800dc938`: `Feature removed due to device state: {}`
- `0x1800dce9f`: `Failed adding product update: Name {0}, Version {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CUpdateEvaluator::ServiceOrUpgradeOS(
        CUpdateEvaluator *this,
        const struct CCompositionDatabase *a2,
        struct CActionListCreator *a3)
{
  _QWORD *v4; // rax
  bool v5; // r9
  __int64 *v6; // rbx
  const wchar_t *v7; // r8
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 v10; // rax
  __int128 v11; // xmm6
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 *v14; // r8
  __int64 *j; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int DeferredUpdateRequests; // eax
  int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rax
  struct CUpdateEvaluator::FeatureRequest *v28; // rbx
  int v29; // edi
  char *v30; // rbx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  int NameValuePairValue; // eax
  __int64 v36; // r9
  __int64 v37; // rdx
  _QWORD *v38; // r15
  const wchar_t *const *v39; // r12
  struct CCompositionDatabase::Feature *v40; // r14
  int v41; // edx
  bool v42; // zf
  __int64 *v43; // rbx
  __int64 v44; // r8
  char v45; // cl
  unsigned int v46; // eax
  struct CCompositionDatabase::ConditionSet *v47; // rdx
  const wchar_t *v48; // rax
  __int64 v49; // rax
  char v50; // cl
  wchar_t **v51; // rdi
  wchar_t **v52; // rsi
  wchar_t *v53; // r14
  __int64 v54; // r12
  wchar_t *v55; // r15
  int v56; // eax
  __int64 v57; // rcx
  unsigned int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdi
  __int64 v62; // rsi
  const wchar_t *const **v63; // rdi
  const wchar_t *const **v64; // rsi
  CCompositionDatabase *v65; // r12
  const struct CCompositionDatabase::Feature *v66; // rcx
  bool v67; // r15
  __int64 v68; // rbx
  struct CUpdateEvaluator::FeatureGroup *FeatureGroupOnDevice; // rax
  __int64 v70; // rdx
  wchar_t *v71; // rcx
  bool v72; // zf
  struct CCompositionDatabase::Feature *v73; // rdi
  char v74; // r12
  bool v75; // r14
  int QualifiedFeatureId; // eax
  __int64 v77; // rbx
  const char *v78; // rcx
  const wchar_t *const *v79; // rdx
  char *v80; // r9
  _QWORD *v81; // r11
  const struct CCompositionDatabase::Feature *v82; // r10
  const struct CCompositionDatabase::Feature *v83; // rax
  wchar_t *v84; // rax
  char v85; // cl
  bool v86; // zf
  int v87; // eax
  const char *v88; // rcx
  __int64 v89; // rbx
  __int64 v90; // rax
  int v91; // ecx
  int v92; // ecx
  unsigned int v93; // eax
  int v94; // ecx
  char v95; // cl
  struct CCompositionDatabase::ConditionSet *v96; // rdx
  struct CCompositionDatabase::ConditionSet *v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rdx
  struct CCompositionDatabase::ConditionSet *v100; // rdx
  const wchar_t *const *v101; // rdx
  char *v102; // r8
  char *v103; // r9
  const char *v104; // rcx
  __int64 v105; // rax
  const char *v106; // rcx
  __int64 v107; // rcx
  __int128 v108; // xmm0
  __int64 v109; // rax
  __int64 v110; // rax
  struct CCompositionDatabase::ConditionSet *v111; // rdx
  const wchar_t *const *v112; // r12
  int v113; // eax
  __int64 v114; // rdx
  __int64 v115; // rdx
  struct CCompositionDatabase::ConditionSet *v116; // rdx
  __int64 v117; // rdx
  __int64 v118; // rdx
  char v119; // al
  int v120; // eax
  bool v121; // r9
  const wchar_t *v122; // rbx
  wchar_t *v123; // r14
  const struct CDeviceInfo::Package *AppMainPackageFromInstalledFeature; // r14
  bool IsStubAppFeatureInstalled; // al
  __int64 v126; // r8
  __int64 v127; // rcx
  __int64 v128; // rdx
  const struct CDeviceInfo::Package *UUPPackageFromInstalledFeature; // rax
  unsigned int v130; // ecx
  unsigned int v131; // ecx
  unsigned int v132; // ecx
  unsigned int v133; // ecx
  unsigned int v134; // ecx
  bool v135; // zf
  unsigned int v136; // ecx
  unsigned int v137; // ecx
  unsigned int v138; // ecx
  unsigned int v139; // ecx
  char *v140; // r8
  char *v141; // rdx
  char *v142; // r9
  const char *v143; // rcx
  __int64 v144; // rax
  char v145; // cl
  struct CCompositionDatabase::ConditionSet *v146; // rdx
  struct CCompositionDatabase::ConditionSet *v147; // rdx
  const wchar_t *const *v148; // rbx
  __int64 v149; // rdx
  __int64 v150; // rdx
  __int64 v151; // rdx
  __int64 v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rdx
  __int64 v155; // rdx
  __int64 v156; // rdx
  __int64 v157; // rdx
  __int64 v158; // rdx
  __int64 v159; // rdx
  __int64 v160; // rdx
  unsigned __int64 v161; // r9
  __int64 v162; // rdx
  __int64 v163; // rdx
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int64 v166; // rdx
  __int64 v167; // rdx
  __int64 v168; // rdx
  __int64 v169; // rdx
  __int64 v170; // rdx
  __int64 v171; // rdx
  int FeatureDependencyClosure; // eax
  __int64 v173; // rdx
  const struct CCompositionDatabase::Feature **v174; // rbx
  const struct CCompositionDatabase::Feature **v175; // r14
  _QWORD *v176; // r15
  const wchar_t *const **v177; // r12
  const wchar_t *const *v178; // rdi
  struct CUpdateEvaluator::Feature *FeatureOnDevice; // rax
  __int64 v180; // rdx
  __int64 v181; // rdx
  __int64 v182; // rdx
  struct CCompositionDatabase::ConditionSet *v183; // rdx
  __int64 v184; // rcx
  _QWORD *v185; // rbx
  _QWORD *v186; // r14
  _QWORD *v187; // rdx
  int v188; // eax
  char v189; // r14
  __int64 v190; // rdx
  __int64 *v191; // rdi
  __int64 *v192; // rbx
  const wchar_t *const **v193; // rax
  const struct CCompositionDatabase::Feature *v194; // rbx
  _BYTE *v195; // rdi
  __int64 v196; // rax
  __int64 v197; // rdx
  __int64 v198; // rdx
  __int64 v199; // rdx
  __int64 v200; // rbx
  const struct CCompositionDatabase::Feature **v201; // rdi
  const struct CCompositionDatabase::Feature **v202; // r12
  const struct CCompositionDatabase::Feature *v203; // r15
  int updated; // r14d
  const struct CCompositionDatabase::Feature *v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rdx
  _QWORD *v208; // rdi
  _QWORD *v209; // rbx
  __int64 v210; // r14
  __int64 v211; // rdx
  int v212; // edx
  int v213; // r8d
  const struct CCompositionDatabase::Feature *v214; // rax
  __int64 v215; // rcx
  const struct CCompositionDatabase::Feature *v216; // rdx
  const struct CCompositionDatabase::Feature *v217; // rdx
  CActionListCreator *v218; // r15
  int v219; // eax
  __int64 v220; // rdx
  struct CCompositionDatabase::Feature *v221; // rcx
  const wchar_t *const **v222; // rdx
  const wchar_t **v223; // rbx
  char v224; // r12
  __int64 v225; // rax
  _QWORD *v226; // rcx
  struct CUpdateEvaluator::Feature *FeatureStateOnDevice; // rdi
  __int64 v228; // rax
  int v229; // r15d
  char v230; // r12
  _QWORD *v231; // r14
  _QWORD *v232; // r12
  const wchar_t *v233; // rdx
  _QWORD *v234; // rcx
  __int64 v235; // rax
  int v236; // r14d
  __int64 v237; // rdx
  __int64 v238; // rdx
  struct CUpdateEvaluator::Package *PackageInAnyGroup; // rax
  __int64 v240; // r14
  __int64 k; // rbx
  const wchar_t *v242; // rdx
  struct CUpdateEvaluator::Package *v243; // rax
  unsigned int v244; // eax
  int v245; // ecx
  const wchar_t *const **v246; // rdi
  const struct CCompositionDatabase::Feature *v247; // rbx
  __int64 v248; // r8
  __int64 v249; // rax
  __int64 v250; // r14
  __int64 m; // rbx
  const wchar_t *v252; // rdx
  int v253; // edx
  int v254; // eax
  int v255; // edx
  int v256; // eax
  __int64 v257; // rdx
  __int64 v258; // rdx
  __int64 v259; // rdx
  __int64 v260; // rdx
  struct CUpdateEvaluator::Package *v261; // rax
  const wchar_t *const **v262; // rax
  const struct CCompositionDatabase::Feature *v263; // rbx
  __int64 v264; // rdx
  __int64 v265; // rax
  unsigned __int64 v266; // xmm6_8
  __int64 v267; // rax
  __int64 v268; // rdx
  __int64 v269; // rdx
  __int64 v270; // rdx
  _QWORD *v271; // rbx
  int v272; // ecx
  int v273; // eax
  __int64 v274; // rdx
  const wchar_t *v275; // rax
  struct ActionList::Product **v276; // rbx
  struct ActionList::Product **v277; // r14
  __int64 v278; // rdx
  int v279; // eax
  __int64 v280; // rdx
  int *v282; // rax
  __int64 v283; // rdx
  int **v284; // [rsp+28h] [rbp-E0h]
  int *v285; // [rsp+28h] [rbp-E0h]
  bool v286[8]; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *const *v287; // [rsp+60h] [rbp-A8h] BYREF
  struct CCompositionDatabase::Feature *v288; // [rsp+68h] [rbp-A0h] BYREF
  const struct CCompositionDatabase::Feature *n; // [rsp+70h] [rbp-98h] BYREF
  void *Buf1; // [rsp+78h] [rbp-90h] BYREF
  __int64 v291; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *const **v292; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v293; // [rsp+90h] [rbp-78h] BYREF
  CCompositionDatabase *v294; // [rsp+98h] [rbp-70h]
  struct CCompositionDatabase::Feature *v295; // [rsp+A0h] [rbp-68h] BYREF
  CActionListCreator *v296; // [rsp+A8h] [rbp-60h]
  wchar_t *v297; // [rsp+B0h] [rbp-58h]
  __int128 v298; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *v300; // [rsp+D0h] [rbp-38h] BYREF
  struct CCompositionDatabase::Feature *v301; // [rsp+D8h] [rbp-30h]
  struct CCompositionDatabase::Feature *v302; // [rsp+E0h] [rbp-28h]
  _QWORD v303[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v304; // [rsp+F8h] [rbp-10h]
  _QWORD v305[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v306[2]; // [rsp+110h] [rbp+8h] BYREF
  struct CCompositionDatabase::Feature *v307; // [rsp+120h] [rbp+18h]
  _BYTE v308[16]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v309; // [rsp+138h] [rbp+30h] BYREF
  __int64 v310; // [rsp+148h] [rbp+40h]
  int v311[2]; // [rsp+150h] [rbp+48h] BYREF
  int v312[2]; // [rsp+158h] [rbp+50h] BYREF
  int *v313; // [rsp+160h] [rbp+58h] BYREF
  int v314[2]; // [rsp+168h] [rbp+60h] BYREF
  int *v315; // [rsp+170h] [rbp+68h] BYREF
  int v316[2]; // [rsp+178h] [rbp+70h] BYREF
  int *v317; // [rsp+180h] [rbp+78h]
  int v318[2]; // [rsp+188h] [rbp+80h] BYREF
  int *v319; // [rsp+190h] [rbp+88h]
  int v320[2]; // [rsp+198h] [rbp+90h] BYREF
  int *v321; // [rsp+1A0h] [rbp+98h] BYREF
  int v322[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  const wchar_t *const *v323; // [rsp+1B0h] [rbp+A8h]
  int *v324; // [rsp+1B8h] [rbp+B0h]
  int v325[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v326[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  int *v327; // [rsp+1D0h] [rbp+C8h]
  int v328[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  int *v329; // [rsp+1E0h] [rbp+D8h] BYREF
  int *v330; // [rsp+1E8h] [rbp+E0h] BYREF
  int v331[2]; // [rsp+1F0h] [rbp+E8h] BYREF
  int *v332; // [rsp+1F8h] [rbp+F0h] BYREF
  int *v333; // [rsp+200h] [rbp+F8h] BYREF
  int v334[2]; // [rsp+208h] [rbp+100h] BYREF
  int *v335; // [rsp+210h] [rbp+108h] BYREF
  int *v336; // [rsp+218h] [rbp+110h] BYREF
  int v337[2]; // [rsp+220h] [rbp+118h] BYREF
  int *v338; // [rsp+228h] [rbp+120h] BYREF
  int *v339; // [rsp+230h] [rbp+128h] BYREF
  int *v340; // [rsp+238h] [rbp+130h] BYREF
  int *v341; // [rsp+240h] [rbp+138h] BYREF
  int v342[2]; // [rsp+248h] [rbp+140h] BYREF
  int *v343; // [rsp+250h] [rbp+148h] BYREF
  int *v344; // [rsp+258h] [rbp+150h] BYREF
  int *v345; // [rsp+260h] [rbp+158h] BYREF
  int v346[2]; // [rsp+268h] [rbp+160h] BYREF
  int v347[2]; // [rsp+270h] [rbp+168h] BYREF
  const wchar_t *v348; // [rsp+278h] [rbp+170h] BYREF
  int *v349; // [rsp+280h] [rbp+178h] BYREF
  int *v350; // [rsp+288h] [rbp+180h] BYREF
  int *v351; // [rsp+290h] [rbp+188h] BYREF
  int *v352; // [rsp+298h] [rbp+190h] BYREF
  int v353[2]; // [rsp+2A0h] [rbp+198h] BYREF
  int *v354; // [rsp+2A8h] [rbp+1A0h] BYREF
  int *v355; // [rsp+2B0h] [rbp+1A8h] BYREF
  int *v356; // [rsp+2B8h] [rbp+1B0h] BYREF
  int *v357; // [rsp+2C0h] [rbp+1B8h] BYREF
  int *v358; // [rsp+2C8h] [rbp+1C0h] BYREF
  int *v359; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v360[16]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v361[16]; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int128 v362; // [rsp+2F8h] [rbp+1F0h]
  _BYTE v363[48]; // [rsp+318h] [rbp+210h] BYREF
  __int64 v364; // [rsp+348h] [rbp+240h]
  __int128 v365; // [rsp+358h] [rbp+250h] BYREF
  __int64 v366; // [rsp+368h] [rbp+260h]
  __int128 v367; // [rsp+370h] [rbp+268h] BYREF
  __int64 v368; // [rsp+380h] [rbp+278h]
  _BYTE v369[32]; // [rsp+388h] [rbp+280h] BYREF
  char v370[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  char v371[16]; // [rsp+3B8h] [rbp+2B0h] BYREF
  char v372[16]; // [rsp+3C8h] [rbp+2C0h] BYREF
  char v373[16]; // [rsp+3D8h] [rbp+2D0h] BYREF
  char v374[16]; // [rsp+3E8h] [rbp+2E0h] BYREF
  char v375[16]; // [rsp+3F8h] [rbp+2F0h] BYREF
  char v376[16]; // [rsp+408h] [rbp+300h] BYREF
  char v377[16]; // [rsp+418h] [rbp+310h] BYREF
  char v378[16]; // [rsp+428h] [rbp+320h] BYREF
  char v379[16]; // [rsp+438h] [rbp+330h] BYREF
  char v380[16]; // [rsp+448h] [rbp+340h] BYREF
  char v381[16]; // [rsp+458h] [rbp+350h] BYREF
  char v382[16]; // [rsp+468h] [rbp+360h] BYREF
  char v383[16]; // [rsp+478h] [rbp+370h] BYREF
  char v384[16]; // [rsp+488h] [rbp+380h] BYREF
  char v385[24]; // [rsp+498h] [rbp+390h] BYREF
  char v386[24]; // [rsp+4B0h] [rbp+3A8h] BYREF
  char v387[24]; // [rsp+4C8h] [rbp+3C0h] BYREF
  const wchar_t *v388; // [rsp+4E0h] [rbp+3D8h] BYREF
  _OWORD v389[3]; // [rsp+4E8h] [rbp+3E0h] BYREF
  __int128 v390; // [rsp+518h] [rbp+410h]
  __int128 v391; // [rsp+528h] [rbp+420h]
  char v392[64]; // [rsp+538h] [rbp+430h] BYREF
  char v393[16]; // [rsp+578h] [rbp+470h] BYREF
  char v394[64]; // [rsp+588h] [rbp+480h] BYREF
  char v395[64]; // [rsp+5C8h] [rbp+4C0h] BYREF
  char v396[64]; // [rsp+608h] [rbp+500h] BYREF
  __int128 v397; // [rsp+648h] [rbp+540h]
  __int64 v398; // [rsp+658h] [rbp+550h]
  __int64 v399; // [rsp+660h] [rbp+558h]
  char v400[64]; // [rsp+668h] [rbp+560h] BYREF
  __int64 v401; // [rsp+6A8h] [rbp+5A0h]
  __int64 v402; // [rsp+6B8h] [rbp+5B0h] BYREF
  const struct CCompositionDatabase::Feature *v403; // [rsp+6C0h] [rbp+5B8h] BYREF
  __int64 v404; // [rsp+6C8h] [rbp+5C0h]
  __int64 v405[2]; // [rsp+6D0h] [rbp+5C8h] BYREF
  _QWORD v406[2]; // [rsp+6E0h] [rbp+5D8h] BYREF
  bool v407; // [rsp+6F0h] [rbp+5E8h] BYREF
  bool v408; // [rsp+6F1h] [rbp+5E9h] BYREF
  __int128 v409; // [rsp+6F8h] [rbp+5F0h] BYREF
  _QWORD *v410; // [rsp+708h] [rbp+600h]
  wchar_t *Str; // [rsp+710h] [rbp+608h] BYREF
  __int128 v412; // [rsp+718h] [rbp+610h] BYREF
  __int64 v413; // [rsp+728h] [rbp+620h]
  _QWORD v414[2]; // [rsp+730h] [rbp+628h] BYREF
  _QWORD v415[2]; // [rsp+740h] [rbp+638h] BYREF
  __int64 v416; // [rsp+750h] [rbp+648h] BYREF
  __int64 v417; // [rsp+758h] [rbp+650h]
  _QWORD v418[2]; // [rsp+760h] [rbp+658h] BYREF
  int v419; // [rsp+770h] [rbp+668h] BYREF
  int v420; // [rsp+774h] [rbp+66Ch] BYREF
  _QWORD v421[2]; // [rsp+778h] [rbp+670h] BYREF
  int v422; // [rsp+788h] [rbp+680h] BYREF
  int v423; // [rsp+78Ch] [rbp+684h] BYREF
  int v424; // [rsp+790h] [rbp+688h] BYREF
  int v425; // [rsp+794h] [rbp+68Ch] BYREF
  int v426; // [rsp+798h] [rbp+690h] BYREF
  int v427; // [rsp+79Ch] [rbp+694h] BYREF
  int v428; // [rsp+7A0h] [rbp+698h] BYREF
  int v429; // [rsp+7A4h] [rbp+69Ch] BYREF
  int v430; // [rsp+7A8h] [rbp+6A0h] BYREF
  int v431; // [rsp+7ACh] [rbp+6A4h] BYREF
  int v432; // [rsp+7B0h] [rbp+6A8h] BYREF
  int v433; // [rsp+7B4h] [rbp+6ACh] BYREF
  int v434; // [rsp+7B8h] [rbp+6B0h] BYREF
  int v435; // [rsp+7BCh] [rbp+6B4h] BYREF
  int v436; // [rsp+7C0h] [rbp+6B8h] BYREF
  int v437; // [rsp+7C4h] [rbp+6BCh] BYREF
  int v438; // [rsp+7C8h] [rbp+6C0h] BYREF
  int v439; // [rsp+7CCh] [rbp+6C4h] BYREF
  int v440; // [rsp+7D0h] [rbp+6C8h] BYREF
  int v441; // [rsp+7D4h] [rbp+6CCh] BYREF
  int v442; // [rsp+7D8h] [rbp+6D0h] BYREF
  int v443; // [rsp+7DCh] [rbp+6D4h] BYREF
  int v444; // [rsp+7E0h] [rbp+6D8h] BYREF
  int v445; // [rsp+7E4h] [rbp+6DCh] BYREF
  int v446; // [rsp+7E8h] [rbp+6E0h] BYREF
  int v447; // [rsp+7ECh] [rbp+6E4h] BYREF
  int v448; // [rsp+7F0h] [rbp+6E8h] BYREF
  int v449; // [rsp+7F4h] [rbp+6ECh] BYREF
  int v450; // [rsp+7F8h] [rbp+6F0h] BYREF
  int v451; // [rsp+7FCh] [rbp+6F4h] BYREF
  int v452; // [rsp+800h] [rbp+6F8h] BYREF
  int v453; // [rsp+804h] [rbp+6FCh] BYREF
  int v454; // [rsp+808h] [rbp+700h] BYREF
  int v455; // [rsp+80Ch] [rbp+704h] BYREF
  int v456; // [rsp+810h] [rbp+708h] BYREF
  int v457; // [rsp+814h] [rbp+70Ch] BYREF
  int v458; // [rsp+818h] [rbp+710h] BYREF
  int v459; // [rsp+81Ch] [rbp+714h] BYREF
  int v460; // [rsp+820h] [rbp+718h] BYREF
  int v461; // [rsp+824h] [rbp+71Ch] BYREF
  int v462; // [rsp+828h] [rbp+720h] BYREF
  int v463; // [rsp+82Ch] [rbp+724h] BYREF
  int v464; // [rsp+830h] [rbp+728h] BYREF
  int v465; // [rsp+834h] [rbp+72Ch] BYREF
  int v466; // [rsp+838h] [rbp+730h] BYREF
  int v467; // [rsp+83Ch] [rbp+734h] BYREF
  __int128 v468; // [rsp+840h] [rbp+738h] BYREF
  __int64 v469; // [rsp+850h] [rbp+748h]
  __int64 v470[2]; // [rsp+858h] [rbp+750h] BYREF
  __int128 v471; // [rsp+868h] [rbp+760h] BYREF
  __int64 v472; // [rsp+878h] [rbp+770h]
  __int128 v473; // [rsp+880h] [rbp+778h] BYREF
  __int64 v474; // [rsp+890h] [rbp+788h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]

  v364 = -2;
  v296 = a3;
  v294 = a2;
  LogAdapter::TraceInfo<>("arbiter: Evaluating features for installation");
  v286[4] = *(_BYTE *)(*((_QWORD *)this + 12) + 304LL);
  v417 = 0;
  v4 = operator new(0x40u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v416 = (__int64)v4;
  std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(
    v470,
    *((_QWORD *)this + 12) + 176LL);
  v6 = **(__int64 ***)(*((_QWORD *)this + 12) + 160LL);
  while ( !*((_BYTE *)v6 + 25) )
  {
    v286[0] = 1;
    if ( !*((_BYTE *)this + 121)
      || ((unsigned __int64)v6[7] <= 7 ? (v7 = (const wchar_t *)(v6 + 4)) : (v7 = (const wchar_t *)v6[4]),
          CDeviceInfo::MatchNameValueSetPair(*((CDeviceInfo **)this + 12), L"UserProfileLanguage", v7, v5, v286),
          v286[0]) )
    {
      v10 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              &v416,
              v385,
              v6 + 4);
      v11 = *(_OWORD *)v10;
      if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                               v12,
                               *(_QWORD *)(v10 + 16),
                               v6 + 4) )
      {
        if ( v417 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v13 = v416;
        v303[1] = &v416;
        v304 = 0;
        v304 = (__int64 *)operator new(0x40u);
        std::wstring::wstring(v304 + 4, v6 + 4);
        *v304 = v13;
        v304[1] = v13;
        v304[2] = v13;
        *((_BYTE *)v304 + 24) = 0;
        *((_BYTE *)v304 + 25) = 0;
        v14 = v304;
        v304 = 0;
        v298 = v11;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActionList::FeatureAction>>>::_Insert_node(
          &v416,
          &v298,
          v14);
      }
    }
    else
    {
      LogAdapter::TraceInfo<std::wstring>("Removing unused language: {0} from satellite consideration", v6 + 4);
    }
    v8 = (__int64 **)v6[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  v415[0] = 0;
  v415[1] = 0;
  v16 = operator new(0x48u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  v415[0] = v16;
  v418[0] = 0;
  v418[1] = 0;
  v17 = operator new(0x30u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  v418[0] = v17;
  v414[0] = 0;
  v414[1] = 0;
  v18 = operator new(0x30u);
  *v18 = v18;
  v18[1] = v18;
  v18[2] = v18;
  *((_WORD *)v18 + 12) = 257;
  v414[0] = v18;
  v421[0] = 0;
  v421[1] = 0;
  v19 = operator new(0x30u);
  *v19 = v19;
  v19[1] = v19;
  v19[2] = v19;
  *((_WORD *)v19 + 12) = 257;
  v421[0] = v19;
  v402 = 0;
  v403 = 0;
  v404 = 0;
  v20 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v20 = v20;
  *(_QWORD *)(v20 + 8) = v20;
  *(_QWORD *)(v20 + 16) = v20;
  *(_WORD *)(v20 + 24) = 257;
  v403 = (const struct CCompositionDatabase::Feature *)v20;
  v405[0] = 0;
  v405[1] = 0;
  v21 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v21 = v21;
  *(_QWORD *)(v21 + 8) = v21;
  *(_QWORD *)(v21 + 16) = v21;
  *(_WORD *)(v21 + 24) = 257;
  v405[0] = v21;
  v406[0] = 0;
  v406[1] = 0;
  v22 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v22 = v22;
  *(_QWORD *)(v22 + 8) = v22;
  *(_QWORD *)(v22 + 16) = v22;
  *(_WORD *)(v22 + 24) = 257;
  v406[0] = v22;
  DeferredUpdateRequests = CUpdateEvaluator::GetDeferredUpdateRequests(this, v294, v415);
  v24 = DeferredUpdateRequests;
  if ( DeferredUpdateRequests < 0 )
  {
    v439 = DeferredUpdateRequests;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get deferred updates");
      v345 = &v439;
      v284 = &v345;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v25,
        3,
        ": {}");
    }
    v26 = 4676;
    goto LABEL_44;
  }
  v27 = *(_QWORD *)v415[0];
  v291 = *(_QWORD *)v415[0];
  while ( !*(_BYTE *)(v27 + 25) )
  {
    v420 = 0;
    v419 = 0;
    v407 = 0;
    v408 = 0;
    v28 = *(struct CUpdateEvaluator::FeatureRequest **)(v27 + 64);
    v295 = v28;
    v29 = CUpdateEvaluator::EvaluateModifyRequest(
            this,
            v28,
            (enum FeatureIntentFlags *)&v420,
            (enum FeatureIntentFlags *)&v419,
            &v407,
            &v408);
    if ( v29 < 0 )
    {
      v438 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to evaluate deferred update; skipping: {0}",
          (char *)v28 + 24);
        *(_QWORD *)v346 = &v438;
        v284 = (int **)v346;
        LOBYTE(v33) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v33,
          3,
          ": {}");
      }
      v34 = 4687;
      goto LABEL_37;
    }
    *(_DWORD *)(*(_QWORD *)v28 + 16LL) = v420;
    *(_DWORD *)(*(_QWORD *)v28 + 20LL) = v419;
    v30 = (char *)v28 + 8;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v421,
      &v298,
      v30,
      &v295);
    if ( v408 )
    {
      v31 = v306;
      v32 = v414;
    }
    else
    {
      if ( !v407 )
        goto LABEL_33;
      v31 = v305;
      v32 = v418;
    }
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v32,
      v31,
      v30,
      &v295);
LABEL_33:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v291);
    v27 = v291;
  }
  v300 = 0;
  NameValuePairValue = CDeviceInfo::GetNameValuePairValue(
                         *((CDeviceInfo **)this + 12),
                         L"EditionVersion",
                         (const wchar_t **)&v300,
                         0);
  v24 = NameValuePairValue;
  if ( NameValuePairValue < 0 )
  {
    v436 = NameValuePairValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get device OS version");
      *(_QWORD *)v347 = &v436;
      v284 = (int **)v347;
      LOBYTE(v37) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v37,
        3,
        ": {}");
    }
    v26 = 4722;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      (int)v284);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
    if ( !v402 )
      goto LABEL_716;
    goto LABEL_715;
  }
  v297 = 0;
  v295 = 0;
  String1 = 0;
  v291 = 0;
  v307 = 0;
  v38 = 0;
  Buf1 = 0;
  v301 = 0;
  v39 = 0;
  v287 = 0;
  v292 = 0;
  v40 = (struct CCompositionDatabase::Feature *)*((_QWORD *)v294 + 5);
  v302 = (struct CCompositionDatabase::Feature *)((char *)v40 + 8 * *((_QWORD *)v294 + 3));
  v41 = 4505604;
  v42 = v40 == v302;
  while ( 2 )
  {
    v288 = v40;
    if ( !v42 )
    {
      v43 = *(__int64 **)(*(_QWORD *)v40 + 48LL);
      n = (const struct CCompositionDatabase::Feature *)&v43[*(_QWORD *)(*(_QWORD *)v40 + 32LL)];
      if ( v43 == (__int64 *)n )
      {
LABEL_98:
        v40 = (struct CCompositionDatabase::Feature *)((char *)v40 + 8);
        v42 = v40 == v302;
        continue;
      }
      while ( 1 )
      {
        v44 = *v43;
        v45 = *(_BYTE *)(*v43 + 368);
        if ( ((v45 - 11) & 0xFA) != 0 || v45 == 16 )
          goto LABEL_97;
        LOBYTE(v36) = 0;
        if ( v45 == 12 )
        {
          v46 = *((_DWORD *)this + 12);
          if ( v46 <= 0x16 )
            LOBYTE(v36) = _bittest(&v41, v46);
        }
        v47 = *(struct CCompositionDatabase::ConditionSet **)v44;
        if ( *(_QWORD *)v44 )
        {
          v48 = L"repair";
        }
        else
        {
          v47 = *(struct CCompositionDatabase::ConditionSet **)(v44 + 8);
          v48 = L"install";
          if ( !v47 )
            v48 = (const wchar_t *)&dword_1801CAD7C;
        }
        v388 = v48;
        v286[0] = 0;
        if ( v47 )
        {
          if ( (_BYTE)v36 )
          {
            LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
              (unsigned int)"Conditional evaluation skipped for {0}: Group: {1}, FMID: {2}, Feature: {3}",
              (unsigned int)&v388,
              *(_DWORD *)v43 + 72,
              *(_DWORD *)v43 + 64,
              *v43 + 56);
          }
          else
          {
            v29 = CUpdateEvaluator::EvaluateConditional(this, v47, v286);
            if ( v29 < 0 )
            {
              v435 = v29;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of {0} feature conditional FMID: {1}, Feature: {2}",
                  &v388,
                  *v43 + 64,
                  *v43 + 56);
                v349 = &v435;
                v284 = &v349;
                LOBYTE(v70) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v70,
                  3,
                  ": {}");
              }
              v34 = 4770;
LABEL_37:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v34,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)(unsigned int)v29,
                (int)v284);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
              if ( v402 )
                goto LABEL_38;
              goto LABEL_39;
            }
            if ( !v286[0] )
            {
              LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
                (unsigned int)"Feature not needed for {0}: Group: {1}, FMID: {2}, Feature: {3}",
                (unsigned int)&v388,
                *(_DWORD *)v43 + 72,
                *(_DWORD *)v43 + 64,
                *v43 + 56);
              goto LABEL_96;
            }
          }
        }
        v49 = *v43;
        v50 = *(_BYTE *)(*v43 + 368);
        if ( v50 == 11 )
        {
          v51 = *(wchar_t ***)(v49 + 120);
          v52 = &v51[*(_QWORD *)(v49 + 104)];
          if ( v51 != v52 )
          {
            v53 = String1;
            v54 = v291;
            v55 = v297;
            v36 = 0;
            do
            {
              if ( !v55
                || (v56 = CompareVersionString(*((_QWORD *)v55 + 2), *((_QWORD *)*v51 + 2), v44, 0), v36 = 0, v56 < 0) )
              {
                v55 = *v51;
                v295 = (struct CCompositionDatabase::Feature *)*v43;
              }
              if ( *((_DWORD *)*v51 + 80) == 16 )
              {
                if ( (v57 = *((_QWORD *)this + 12), *(_BYTE *)(v57 + 236))
                  || *(_QWORD *)(v57 + 240) != *(_QWORD *)(v57 + 248)
                  || !v300
                  || (v58 = *((_DWORD *)this + 12), v58 <= 0x16) && (v44 = 4505600, _bittest((const int *)&v44, v58))
                  || (v59 = CompareVersionString(v300, *((_QWORD *)*v51 + 3), v44, 0), v36 = 0, v59 < 0) )
                {
                  if ( !v53
                    || (v60 = CompareVersionString(*((_QWORD *)v53 + 2), *((_QWORD *)*v51 + 2), v44, 0), v36 = 0, v60 < 0) )
                  {
                    v307 = (struct CCompositionDatabase::Feature *)v54;
                    v53 = *v51;
                    v54 = *v43;
                  }
                }
              }
              ++v51;
            }
            while ( v51 != v52 );
            v297 = v55;
            v291 = v54;
            String1 = v53;
            v40 = v288;
            v38 = Buf1;
LABEL_78:
            v39 = v287;
          }
        }
        else
        {
          if ( v50 != 12 )
          {
            if ( v50 == 15 )
            {
              v63 = *(const wchar_t *const ***)(v49 + 120);
              v64 = &v63[*(_QWORD *)(v49 + 104)];
              if ( v63 != v64 )
              {
                do
                {
                  if ( !v39 || (int)CompareVersionString(*((_QWORD *)v39 + 2), *((_QWORD *)*v63 + 2), v44, v36) < 0 )
                  {
                    v39 = *v63;
                    v292 = (const wchar_t *const **)*v43;
                  }
                  ++v63;
                }
                while ( v63 != v64 );
                v287 = v39;
                v40 = v288;
              }
            }
            goto LABEL_96;
          }
          v61 = *(_QWORD *)(v49 + 120);
          v62 = v61 + 8LL * *(_QWORD *)(v49 + 104);
          if ( v61 != v62 )
          {
            do
            {
              if ( !v38 || (int)CompareVersionString(v38[2], *(_QWORD *)(*(_QWORD *)v61 + 16LL), v44, v36) < 0 )
              {
                v38 = *(_QWORD **)v61;
                v301 = (struct CCompositionDatabase::Feature *)*v43;
              }
              v61 += 8;
            }
            while ( v61 != v62 );
            Buf1 = v38;
            goto LABEL_78;
          }
        }
LABEL_96:
        v41 = 4505604;
LABEL_97:
        if ( ++v43 == (__int64 *)n )
          goto LABEL_98;
      }
    }
    break;
  }
  v65 = v294;
  v302 = (struct CCompositionDatabase::Feature *)(*((_DWORD *)v294 + 108) & 0x800);
  v66 = (const struct CCompositionDatabase::Feature *)*((_QWORD *)v294 + 5);
  n = v66;
  *(_QWORD *)&v298 = (char *)v66 + 8 * *((_QWORD *)v294 + 3);
  if ( v66 == (const struct CCompositionDatabase::Feature *)v298 )
    goto LABEL_124;
  v67 = 0;
  while ( 2 )
  {
    v68 = *(_QWORD *)v66;
    v287 = (const wchar_t *const *)v68;
    FeatureGroupOnDevice = CUpdateEvaluator::FindFeatureGroupOnDevice(this, *(const wchar_t *const *)v68);
    if ( FeatureGroupOnDevice )
      *((_BYTE *)FeatureGroupOnDevice + 8) = 1;
    else
      LogAdapter::TraceInfo<wchar_t const *>(
        "No installed features to update in Group {0}; evaluating features for conditional install",
        v68);
    v71 = *(wchar_t **)(v68 + 48);
    v306[0] = &v71[4 * *(_QWORD *)(v68 + 32)];
    v72 = v71 == (wchar_t *)v306[0];
    while ( 2 )
    {
      v300 = v71;
      if ( !v72 )
      {
        v73 = *(struct CCompositionDatabase::Feature **)v71;
        v288 = v73;
        v74 = 0;
        v286[2] = 0;
        v75 = 0;
        v286[0] = 0;
        v286[3] = 0;
        QualifiedFeatureId = GetQualifiedFeatureId(v73, &v402);
        v24 = QualifiedFeatureId;
        if ( QualifiedFeatureId < 0 )
        {
          v456 = QualifiedFeatureId;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed getting qualified feature Id");
            v327 = &v456;
            LOBYTE(v171) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v171,
              3,
              ": {}");
          }
          goto LABEL_714;
        }
        if ( *((_BYTE *)v73 + 368) == 11 )
        {
          v77 = v291;
          if ( v291 || v295 )
          {
            if ( CDeviceInfo::IsNameValuePairEqual(*((CDeviceInfo **)this + 12), L"WindowsPE", L"1") && v73 != v295 )
            {
              v78 = "Feature baselines not applicable for WinPE: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_116:
              v79 = v287;
LABEL_117:
              v80 = (char *)v73 + 56;
LABEL_118:
              LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v78, v79, (char *)v73 + 64, v80);
LABEL_119:
              v67 = 0;
LABEL_120:
              v71 = v300 + 4;
              v72 = v300 + 4 == (wchar_t *)v306[0];
              continue;
            }
            if ( v307 )
            {
              v84 = v297;
              if ( v73 == v307 )
              {
                if ( (struct CCompositionDatabase::Feature *)v77 == v295 )
                {
                  if ( *((_DWORD *)v297 + 80) == 16 )
                    goto LABEL_135;
                }
                else if ( *((_DWORD *)v297 + 80) != 16 )
                {
                  v78 = "Feature N-1 baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_116;
                }
              }
            }
            else
            {
              v84 = v297;
            }
            if ( v73 != (struct CCompositionDatabase::Feature *)v77 )
            {
              if ( v73 == v295 )
                goto LABEL_135;
LABEL_143:
              v78 = "Feature baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_116;
            }
            if ( (struct CCompositionDatabase::Feature *)v77 != v295 && *((_DWORD *)v84 + 80) == 16 )
              goto LABEL_143;
          }
        }
LABEL_135:
        v85 = *((_BYTE *)v73 + 368);
        if ( v85 == 12 )
        {
          v86 = v73 == v301;
        }
        else
        {
          if ( v85 != 15 )
            goto LABEL_147;
          v86 = v73 == (struct CCompositionDatabase::Feature *)v292;
        }
        if ( !v86 )
        {
LABEL_149:
          v78 = "Feature not applicable: Group: {0}, FMID: {1}, Feature: {2}";
          goto LABEL_116;
        }
LABEL_147:
        v87 = *((_DWORD *)this + 12);
        if ( v87 == 25 && v85 != 25 )
          goto LABEL_149;
        v286[1] = 0;
        if ( v302 )
        {
          v74 = 1;
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            &v403,
            v383,
            &v288);
          v88 = "Feature added due to standalone compDB: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_152:
          v73 = v288;
          goto LABEL_153;
        }
        if ( v87 != 1 && v87 != 19 )
        {
          if ( (v87 == 2 || v87 == 22) && (*((_BYTE *)v73 + 368) == 14 || *((_BYTE *)v73 + 368) == 9) )
          {
            v74 = 1;
            std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
              &v403,
              v375,
              &v288);
            v88 = "Feature added due to default desktop upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_152;
          }
          v93 = *((_DWORD *)this + 12);
          if ( v93 > 0x16 || (v94 = 4505604, !_bittest(&v94, v93)) )
          {
LABEL_181:
            if ( *((_DWORD *)this + 12) == 24 )
            {
              if ( *((_BYTE *)v73 + 368) == 27 )
              {
                v107 = *((_QWORD *)v73 + 7);
                v108 = 0;
                v109 = 0;
                v362 = 0;
                if ( v107 )
                {
                  v110 = -1;
                  do
                    ++v110;
                  while ( *(_WORD *)(v107 + 2 * v110) );
                  *(_QWORD *)&v362 = 2 * v110;
                  *((_QWORD *)&v362 + 1) = 2 * v110 + 2;
                  v109 = v107;
                  v108 = v362;
                }
                v365 = v108;
                v366 = v109;
                if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                        ___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HH__0GJ__0GO__0HC__0GF__0FP__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                                        &v365,
                                        0) )
                  goto LABEL_183;
              }
              if ( *((_BYTE *)v73 + 368) == 12 )
                goto LABEL_183;
            }
            else if ( *((_BYTE *)v73 + 368) != 27 )
            {
LABEL_183:
              if ( CUpdateEvaluator::FindFeatureOnDevice(this, v73) )
              {
                v111 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 6);
                if ( v111 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v111, v286);
                  if ( v24 < 0 )
                  {
                    v427 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v341 = &v427;
                      v284 = &v341;
                      LOBYTE(v155) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v155,
                        3,
                        ": {}");
                    }
                    v115 = 5325;
LABEL_227:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v115,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      (int)v284);
LABEL_714:
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
                    if ( !v402 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v75 = v286[0];
                  v112 = v287;
                  if ( v286[0] )
                  {
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v287,
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      v406,
                      v371,
                      &v288);
                    v73 = v288;
                    v113 = CActionListCreator::DisableFeature(v296, v288);
                    v24 = v113;
                    if ( v113 < 0 )
                    {
                      v428 = v113;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                          (char *)v73 + 72,
                          (char *)v73 + 64,
                          (char *)v73 + 56);
                        *(_QWORD *)v328 = &v428;
                        v284 = (int **)v328;
                        LOBYTE(v114) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v114,
                          3,
                          ": {}");
                      }
                      v115 = 5336;
                      goto LABEL_227;
                    }
                  }
                }
                else
                {
                  v112 = v287;
                }
                v116 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 2);
                if ( v116 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v116, &v286[3]);
                  if ( v24 < 0 )
                  {
                    v426 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of remove feature conditional FMID: {0}, Feature: {1}",
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v339 = &v426;
                      v284 = &v339;
                      LOBYTE(v158) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v158,
                        3,
                        ": {}");
                    }
                    v115 = 5348;
                    goto LABEL_227;
                  }
                  v67 = v286[3];
                  if ( v286[3] )
                  {
                    Buf1 = 0;
                    v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                    if ( v24 < 0 )
                    {
                      v448 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<AutoScz>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed creating pending request for {0}",
                          &v402);
                        v340 = &v448;
                        v284 = &v340;
                        LOBYTE(v156) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v156,
                          3,
                          ": {}");
                      }
                      v157 = 5360;
                      goto LABEL_713;
                    }
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                      v414,
                      v372,
                      &v288,
                      &Buf1);
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v112,
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                  }
                }
                if ( v75 && v67 )
                {
                  v24 = -2146467821;
                  v425 = -2146467821;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Conflicting preload and removal feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                      v112,
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                    v338 = &v425;
                    v284 = &v338;
                    LOBYTE(v117) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v117,
                      3,
                      ": {}");
                  }
                  v118 = 5370;
                  goto LABEL_377;
                }
                if ( !v67 )
                {
                  if ( *((_BYTE *)this + 121) )
                  {
                    v119 = *((_BYTE *)v73 + 368);
                    if ( v119 == 6 || v119 == 13 || v119 == 5 && *(_BYTE *)(*((_QWORD *)this + 12) + 330LL) )
                    {
                      Str = 0;
                      v286[3] = 1;
                      Buf1 = 0;
                      String1 = 0;
                      v120 = SczAllocFromSz(&Str);
                      v24 = v120;
                      if ( v120 < 0 )
                      {
                        v161 = (unsigned int)v120;
                        v162 = 5390;
LABEL_382:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v162,
                          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                          (const char *)v161,
                          (int)v284);
                        if ( Str )
                        {
                          operator delete(Str - 4);
                          Str = 0;
                        }
                        goto LABEL_384;
                      }
                      v24 = ShredFeatureStringIdIntoAttributes(
                              Str,
                              (const wchar_t **)&String1,
                              (const wchar_t **)&Buf1,
                              0);
                      if ( v24 < 0 )
                      {
                        v423 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<AutoScz>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed shredding feature ID: {0}",
                            &Str);
                          v336 = &v423;
                          v284 = &v336;
                          LOBYTE(v160) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v160,
                            3,
                            ": {}");
                        }
                        v161 = (unsigned int)v24;
                        v162 = 5394;
                        goto LABEL_382;
                      }
                      v122 = (const wchar_t *)Buf1;
                      if ( Buf1 )
                      {
                        if ( *((_BYTE *)v73 + 368) == 5 )
                        {
                          v123 = String1;
                          if ( wcsicmp(String1, L"Language.TextToSpeech") )
                          {
                            if ( wcsicmp(v123, L"Language.Speech") && wcsicmp(v123, L"Language.LocaleData") )
                              v122 = 0;
                          }
                        }
                        if ( v122 )
                        {
                          CDeviceInfo::MatchNameValueSetPair(
                            *((CDeviceInfo **)this + 12),
                            L"UserProfileLanguage",
                            v122,
                            v121,
                            &v286[3]);
                          v67 = !v286[3];
                        }
                      }
                      if ( Str )
                      {
                        operator delete(Str - 4);
                        Str = 0;
                      }
                      if ( v67 )
                      {
                        Buf1 = 0;
                        v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                        if ( v24 < 0 )
                        {
                          v424 = v24;
                          if ( *(_QWORD *)&LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<AutoScz>(
                              *(_QWORD *)&LogAdapter::g_Logger,
                              0,
                              3,
                              "Failed creating pending request for {0}",
                              &v402);
                            *(_QWORD *)v337 = &v424;
                            v284 = (int **)v337;
                            LOBYTE(v159) = 1;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              *(_QWORD *)&LogAdapter::g_Logger,
                              v159,
                              3,
                              ": {}");
                          }
                          v118 = 5430;
LABEL_377:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v118,
                            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                            (const char *)(unsigned int)v24,
                            (int)v284);
LABEL_384:
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
                          if ( !v402 )
                            goto LABEL_716;
LABEL_715:
                          operator delete((void *)(v402 - 8));
                          v402 = 0;
                          goto LABEL_716;
                        }
                        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                          v414,
                          v373,
                          &v288,
                          &Buf1);
                        LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                          "Feature (LanguagePack) removed because it was unused: Group: {0}, FMID: {1}, Feature: {2}",
                          v112,
                          (char *)v73 + 64,
                          (char *)v73 + 56);
                      }
                    }
                  }
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                  v414,
                  v303,
                  &v288);
                if ( v303[0] != v414[0] )
                {
                  *(_BYTE *)(*(_QWORD *)(v303[0] + 40LL) + 33LL) = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    v405,
                    v374,
                    &v288);
                  v73 = v288;
                  if ( !v67 )
                  {
                    v67 = 1;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
                      (char *)v288 + 72,
                      (char *)v288 + 64,
                      (char *)v288 + 56);
                  }
                }
                if ( *((_BYTE *)v73 + 369) )
                  goto LABEL_119;
                if ( (unsigned __int8)(*((_BYTE *)v73 + 368) - 22) <= 1u )
                {
                  AppMainPackageFromInstalledFeature = CDeviceInfo::GetAppMainPackageFromInstalledFeature(
                                                         *((CDeviceInfo **)this + 12),
                                                         *((const wchar_t *const *)v73 + 7));
                  IsStubAppFeatureInstalled = CDeviceInfo::IsStubAppFeatureInstalled(
                                                *((CDeviceInfo **)this + 12),
                                                *((const wchar_t *const *)v73 + 7));
                  if ( AppMainPackageFromInstalledFeature )
                  {
                    LOBYTE(v126) = IsStubAppFeatureInstalled;
                    if ( !(unsigned __int8)IsPreInstalledAppApplicable(v73, AppMainPackageFromInstalledFeature, v126) )
                    {
                      v80 = (char *)v73 + 56;
                      v79 = v112;
                      v78 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as newer MSIX application is already installed";
                      goto LABEL_118;
                    }
                  }
                }
                if ( *((_BYTE *)v73 + 368) == 24
                  && CDeviceInfo::GetEdgePackageFromInstalledFeature(
                       *((CDeviceInfo **)this + 12),
                       *((const wchar_t *const *)v73 + 7)) )
                {
                  v127 = *((_QWORD *)v73 + 15);
                  v128 = v127 + 8LL * *((_QWORD *)v73 + 13);
                  while ( 1 )
                  {
                    if ( v127 == v128 )
                      goto LABEL_275;
                    if ( *(_DWORD *)(*(_QWORD *)v127 + 320LL) == 17 )
                      break;
                    v127 += 8;
                  }
                  v79 = v112;
                  v78 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as Edge package is not applicable";
                  goto LABEL_117;
                }
LABEL_275:
                if ( *((_BYTE *)v73 + 368) == 25 )
                {
                  UUPPackageFromInstalledFeature = CDeviceInfo::GetUUPPackageFromInstalledFeature(
                                                     *((CDeviceInfo **)this + 12),
                                                     *((const wchar_t *const *)v73 + 7));
                  if ( UUPPackageFromInstalledFeature )
                  {
                    if ( !(unsigned __int8)IsUUPProductApplicable(v73, UUPPackageFromInstalledFeature) )
                    {
                      v79 = v112;
                      v78 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as UUP product is not applicable";
                      goto LABEL_117;
                    }
                  }
                }
                v74 = 1;
                if ( v67 )
                  goto LABEL_154;
                v88 = "Feature added due to default upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_153:
                LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v88, v287, (char *)v73 + 64, (char *)v73 + 56);
LABEL_154:
                v67 = 0;
LABEL_155:
                Buf1 = 0;
                v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                if ( v24 < 0 )
                {
                  v457 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<AutoScz>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed creating pending request for {0}",
                      &v402);
                    v351 = &v457;
                    v284 = &v351;
                    LOBYTE(v170) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v170,
                      3,
                      ": {}");
                  }
                  v99 = 5524;
                  goto LABEL_392;
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                  v418,
                  v363,
                  &v288,
                  &Buf1);
                goto LABEL_157;
              }
              v96 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 1);
              v67 = 0;
              if ( v96 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v96, &v286[2]);
                if ( v24 < 0 )
                {
                  v432 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                    v356 = &v432;
                    v284 = &v356;
                    LOBYTE(v151) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v151,
                      3,
                      ": {}");
                  }
                  v99 = 5287;
                  goto LABEL_392;
                }
                v74 = v286[2];
                if ( v286[2] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v287,
                    (char *)v73 + 64,
                    (char *)v73 + 56);
                  v286[1] = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v403,
                    v370,
                    &v288);
                  v73 = v288;
                }
              }
              v97 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 6);
              if ( v97 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v97, v286);
                if ( v24 < 0 )
                {
                  v429 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                    v359 = &v429;
                    v284 = &v359;
                    LOBYTE(v154) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v154,
                      3,
                      ": {}");
                  }
                  v99 = 5302;
                  goto LABEL_392;
                }
                if ( v286[0] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v287,
                    (char *)v73 + 64,
                    (char *)v73 + 56);
                  v24 = CActionListCreator::DisableFeature(v296, v73);
                  if ( v24 < 0 )
                  {
                    v430 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                        (char *)v73 + 72,
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v358 = &v430;
                      v284 = &v358;
                      LOBYTE(v152) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v152,
                        3,
                        ": {}");
                    }
                    v153 = 5311;
LABEL_403:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v153,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      (int)v284);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
                    if ( !v402 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v67 = 0;
                  if ( v74 )
                  {
                    v24 = -2146467821;
                    v431 = -2146467821;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                        v287,
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v357 = &v431;
                      v284 = &v357;
                      LOBYTE(v98) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v98,
                        3,
                        ": {}");
                    }
                    v99 = 5317;
                    goto LABEL_392;
                  }
                }
              }
              goto LABEL_345;
            }
            v79 = (const wchar_t *const *)((char *)v73 + 72);
            v78 = "Not including Group: {}, FMID: {}, Feature: {}";
            goto LABEL_117;
          }
          v95 = *((_BYTE *)v73 + 368);
          if ( v95 != 7 )
          {
            if ( (unsigned __int8)(v95 - 11) <= 1u || v95 == 8 )
            {
LABEL_201:
              v67 = 0;
LABEL_202:
              if ( *((_BYTE *)v73 + 368) == 20 )
              {
                Buf1 = 0;
                v24 = CDeviceInfo::GetNameValuePairValue(
                        *((CDeviceInfo **)this + 12),
                        L"HotPatchReadiness",
                        (const wchar_t **)&Buf1,
                        0);
                if ( v24 < 0 )
                {
                  v433 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to get hotpatch status");
                    v355 = &v433;
                    v284 = &v355;
                    LOBYTE(v150) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v150,
                      3,
                      ": {}");
                  }
                  v99 = 5212;
                  goto LABEL_392;
                }
                if ( !Buf1 )
                  goto LABEL_209;
                v105 = -1;
                do
                  ++v105;
                while ( *((_WORD *)Buf1 + v105) );
                if ( 2 * v105 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
                {
LABEL_209:
                  v106 = "Feature excluded due to no hotpatching support: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_210;
                }
              }
              v74 = 1;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v403,
                v384,
                &v288);
              v104 = "Feature added due to default desktop upgrade, image-based reset, or media-based upgrade evaluation:"
                     " Group: {0}, FMID: {1}, Feature: {2}";
              v101 = v287;
              goto LABEL_342;
            }
            if ( v95 != 15 )
            {
              if ( v95 != 20 )
                goto LABEL_181;
              goto LABEL_201;
            }
          }
          v100 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 1);
          v67 = 0;
          if ( v100 )
          {
            v24 = CUpdateEvaluator::EvaluateConditional(this, v100, &v286[2]);
            if ( v24 < 0 )
            {
              v434 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                  (char *)v73 + 64,
                  (char *)v73 + 56);
                v354 = &v434;
                v284 = &v354;
                LOBYTE(v149) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v149,
                  3,
                  ": {}");
              }
              v99 = 5188;
LABEL_392:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v99,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)(unsigned int)v24,
                (int)v284);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
              if ( !v402 )
                goto LABEL_716;
              goto LABEL_715;
            }
            v74 = v286[2];
            v101 = v287;
            v102 = (char *)v73 + 64;
            v103 = (char *)v73 + 56;
            if ( v286[2] )
              v104 = "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            else
              v104 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_344;
          }
          goto LABEL_202;
        }
        LogAdapter::TraceInfo<wchar_t const *>("Looking to see if feature should be included: {0}", (char *)v73 + 56);
        v67 = 0;
        Buf1 = 0;
        v130 = *((unsigned __int8 *)v73 + 368);
        if ( v130 > 0xC )
        {
          v136 = v130 - 15;
          if ( !v136 )
            goto LABEL_307;
          v137 = v136 - 4;
          if ( !v137 )
            goto LABEL_307;
          v138 = v137 - 1;
          if ( !v138 )
          {
            v24 = CDeviceInfo::GetNameValuePairValue(
                    *((CDeviceInfo **)this + 12),
                    L"HotPatchReadiness",
                    (const wchar_t **)&Buf1,
                    0);
            if ( v24 < 0 )
            {
              v466 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get hotpatch status");
                *(_QWORD *)v334 = &v466;
                v284 = (int **)v334;
                LOBYTE(v164) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v164,
                  3,
                  ": {}");
              }
              v99 = 4961;
              goto LABEL_392;
            }
            if ( !Buf1 )
              goto LABEL_386;
            v144 = -1;
            do
              ++v144;
            while ( *((_WORD *)Buf1 + v144) );
            if ( 2 * v144 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
            {
LABEL_386:
              v24 = -2146467822;
              v422 = -2146467822;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Hotpatching is not supported on this machine/image.");
                v335 = &v422;
                v284 = &v335;
                LOBYTE(v163) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v163,
                  3,
                  ": {}");
              }
              v99 = 4965;
              goto LABEL_392;
            }
            goto LABEL_307;
          }
          v139 = v138 - 5;
          if ( !v139 )
            goto LABEL_307;
          v135 = v139 == 1;
        }
        else
        {
          if ( v130 == 12 )
            goto LABEL_307;
          v131 = v130 - 2;
          if ( !v131 )
            goto LABEL_307;
          v132 = v131 - 1;
          if ( !v132 )
            goto LABEL_307;
          v133 = v132 - 4;
          if ( !v133 )
            goto LABEL_307;
          v134 = v133 - 2;
          if ( !v134 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl) )
            {
LABEL_299:
              v140 = (char *)v73 + 64;
              v141 = (char *)v73 + 72;
              v142 = (char *)v73 + 56;
              v143 = "Not including Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_300;
            }
LABEL_307:
            v145 = *((_BYTE *)v73 + 368);
            if ( (unsigned __int8)(v145 - 2) <= 1u )
            {
              v148 = v287;
              if ( !CDeviceInfo::GetInstalledFeature(
                      *((CDeviceInfo **)this + 12),
                      *((const wchar_t *const *)v73 + 7),
                      *((const wchar_t *const *)v73 + 8),
                      *v287) )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v403,
                v381,
                &v288);
              v101 = v148;
              v104 = "Feature added for processing because it's already installed: Group: {0}, FMID: {1}, Feature: {2}";
            }
            else
            {
              if ( *(_QWORD *)v73 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(
                        this,
                        *(struct CCompositionDatabase::ConditionSet **)v73,
                        &v286[2]);
                if ( v24 < 0 )
                {
                  v465 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of repair feature conditional FMID: {0}, Feature: {1}",
                      (char *)v73 + 64,
                      (char *)v73 + 56);
                    v333 = &v465;
                    v284 = &v333;
                    LOBYTE(v165) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v165,
                      3,
                      ": {}");
                  }
                  v99 = 5033;
                  goto LABEL_392;
                }
                v74 = v286[2];
                if ( v286[2] )
                {
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v403,
                    v382,
                    &v288);
                  v104 = "Feature added due to repair conditional: Group: {0}, FMID: {1}, Feature: {2}";
                  v73 = v288;
                }
                else
                {
                  v104 = "Feature not needed for repair: Group: {0}, FMID: {1}, Feature: {2}";
                }
                v101 = (const wchar_t *const *)((char *)v73 + 72);
                goto LABEL_343;
              }
              v146 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 1);
              if ( v146 )
              {
                if ( v145 != 11 || *((_BYTE *)this + 116) )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v146, &v286[2]);
                  if ( v24 < 0 )
                  {
                    v458 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v329 = &v458;
                      v284 = &v329;
                      LOBYTE(v169) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v169,
                        3,
                        ": {}");
                    }
                    v99 = 5064;
                    goto LABEL_392;
                  }
                  v74 = v286[2];
                  if ( v286[2] )
                  {
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v403,
                      v376,
                      &v288);
                    v73 = v288;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v287,
                      (char *)v288 + 64,
                      (char *)v288 + 56);
                  }
                  v147 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v73 + 6);
                  if ( v147 )
                  {
                    v24 = CUpdateEvaluator::EvaluateConditional(this, v147, v286);
                    if ( v24 < 0 )
                    {
                      v459 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                          (char *)v73 + 64,
                          (char *)v73 + 56);
                        v330 = &v459;
                        v284 = &v330;
                        LOBYTE(v168) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v168,
                          3,
                          ": {}");
                      }
                      v99 = 5077;
                      goto LABEL_392;
                    }
                    v75 = v286[0];
                    if ( v286[0] )
                    {
                      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                        "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                        v287,
                        (char *)v73 + 64,
                        (char *)v73 + 56);
                      v24 = CActionListCreator::DisableFeature(v296, v73);
                      if ( v24 < 0 )
                      {
                        v461 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                            (char *)v73 + 72,
                            (char *)v73 + 64,
                            (char *)v73 + 56);
                          *(_QWORD *)v331 = &v461;
                          v284 = (int **)v331;
                          LOBYTE(v167) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v167,
                            3,
                            ": {}");
                        }
                        v153 = 5086;
                        goto LABEL_403;
                      }
                      v67 = 0;
                      if ( v74 )
                      {
                        v24 = -2146467821;
                        v464 = -2146467821;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                            v287,
                            (char *)v73 + 64,
                            (char *)v73 + 56);
                          v332 = &v464;
                          v284 = &v332;
                          LOBYTE(v166) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v166,
                            3,
                            ": {}");
                        }
                        v99 = 5092;
                        goto LABEL_392;
                      }
                      v75 = v286[0];
                    }
                  }
                  if ( v74 )
                    goto LABEL_155;
                  if ( v75 )
                    goto LABEL_157;
                  v106 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_210:
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v106, v287, (char *)v73 + 64, (char *)v73 + 56);
                  goto LABEL_157;
                }
              }
              else if ( v145 != 11 )
              {
                if ( v145 == 15 )
                {
                  v74 = *((_BYTE *)this + 117);
                  if ( !v74 )
                    goto LABEL_157;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v403,
                    v378,
                    &v288);
                  v101 = v287;
                  v104 = "Feature added due to safe OS dynamic update: Group: {0}, FMID: {1}, Feature: {2}";
                }
                else
                {
                  if ( v145 != 9 )
                  {
                    v74 = 1;
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v403,
                      v380,
                      &v288);
                    v73 = v288;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to default desktop servicing evaluation: Group: {0}, FMID: {1}, Feature: {2}",
                      v287,
                      (char *)v288 + 64,
                      (char *)v288 + 56);
                    goto LABEL_155;
                  }
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl)
                    || (v74 = *((_BYTE *)this + 116)) == 0 )
                  {
LABEL_157:
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                      v418,
                      v305,
                      &v288);
                    v89 = v305[0];
                    if ( v305[0] == v418[0] )
                      goto LABEL_120;
                    *(_BYTE *)(*(_QWORD *)(v305[0] + 40LL) + 32LL) = 1;
                    if ( v74 )
                    {
                      if ( !*(_DWORD *)(**(_QWORD **)(v89 + 40) + 16LL)
                        && !CUpdateEvaluator::FindFeatureOnDevice(this, v73) )
                      {
                        *(_DWORD *)(**(_QWORD **)(v89 + 40) + 16LL) |= *((_DWORD *)v73 + 95);
                      }
                      v90 = *(_QWORD *)(v89 + 40);
                      v91 = *(_DWORD *)(*(_QWORD *)v90 + 16LL);
                      if ( (v91 & 0x6E) == 0 && (!v286[4] || v286[1]) )
                      {
                        if ( *((_BYTE *)v73 + 368) == 1 || *((_BYTE *)v73 + 368) == 4 )
                          v92 = v91 | 0x30;
                        else
                          v92 = v91 | 0x50;
                        *(_DWORD *)(*(_QWORD *)v90 + 16LL) = v92;
                      }
                      goto LABEL_120;
                    }
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v403,
                      v308,
                      &v288);
                    v142 = (char *)v288 + 56;
                    v140 = (char *)v288 + 64;
                    v141 = (char *)v288 + 72;
                    v143 = "Feature added due to deferred update: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_300:
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v143, v141, v140, v142);
                    goto LABEL_120;
                  }
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v403,
                    v379,
                    &v288);
                  v101 = v287;
                  v104 = "Feature added due to tools: Group: {0}, FMID: {1}, Feature: {2}";
                }
                goto LABEL_342;
              }
              v74 = *((_BYTE *)this + 116);
              if ( !v74 )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v403,
                v377,
                &v288);
              v101 = v287;
              v104 = "Feature added due to cumulative update or reoffer: Group: {0}, FMID: {1}, Feature: {2}";
            }
LABEL_342:
            v73 = v288;
LABEL_343:
            v103 = (char *)v73 + 56;
            v102 = (char *)v73 + 64;
LABEL_344:
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v104, v101, v102, v103);
LABEL_345:
            if ( v74 )
              goto LABEL_155;
            goto LABEL_157;
          }
          v135 = v134 == 2;
        }
        if ( !v135 && !*(_QWORD *)v73 )
          goto LABEL_299;
        goto LABEL_307;
      }
      break;
    }
    v66 = (const struct CCompositionDatabase::Feature *)((char *)n + 8);
    n = v66;
    if ( v66 != (const struct CCompositionDatabase::Feature *)v298 )
      continue;
    break;
  }
  v65 = v294;
LABEL_124:
  v409 = 0;
  v410 = 0;
  if ( v404 )
    std::vector<CCompositionDatabase::Feature *>::_Resize_reallocate<std::_Value_init_tag>(&v409);
  v81 = (_QWORD *)v409;
  v82 = v403;
  v83 = *(const struct CCompositionDatabase::Feature **)v403;
  n = *(const struct CCompositionDatabase::Feature **)v403;
  while ( v83 != v82 )
  {
    *v81 = *((_QWORD *)v83 + 4);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v83 = n;
  }
  v412 = 0;
  v413 = 0;
  std::vector<CCompositionDatabase::Feature *>::reserve(&v412, (__int64)(*((_QWORD *)&v409 + 1) - v409) >> 3);
  FeatureDependencyClosure = CUpdateEvaluator::GetFeatureDependencyClosure(this, v65, &v409, &v412);
  v24 = FeatureDependencyClosure;
  if ( FeatureDependencyClosure < 0 )
  {
    v455 = FeatureDependencyClosure;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to determine feature dependency closure");
      *(_QWORD *)v326 = &v455;
      v284 = (int **)v326;
      LOBYTE(v173) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v173,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D8,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      (int)v284);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
    goto LABEL_714;
  }
  if ( (_QWORD)v409 != *((_QWORD *)&v409 + 1) )
    *((_QWORD *)&v409 + 1) = v409;
  v175 = (const struct CCompositionDatabase::Feature **)*((_QWORD *)&v412 + 1);
  v174 = (const struct CCompositionDatabase::Feature **)v412;
  if ( (_QWORD)v412 != *((_QWORD *)&v412 + 1) )
  {
    while ( 1 )
    {
      n = *v174;
      v29 = GetQualifiedFeatureId(n, &v402);
      if ( v29 < 0 )
        break;
      v29 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, 0);
      if ( v29 < 0 )
      {
        v454 = v29;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unable to create feature modification request");
          *(_QWORD *)v325 = &v454;
          v284 = (int **)v325;
          LOBYTE(v180) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v180,
            3,
            ": {}");
        }
        v181 = 5601;
LABEL_441:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v181,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
          (const char *)(unsigned int)v29,
          (int)v284);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
        if ( v402 )
          goto LABEL_38;
        goto LABEL_39;
      }
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        &v403,
        v308,
        &n);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v405,
        &n);
      if ( ++v174 == v175 )
      {
        if ( (_QWORD)v412 != *((_QWORD *)&v412 + 1) )
          *((_QWORD *)&v412 + 1) = v412;
        goto LABEL_428;
      }
    }
    v442 = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Unable to determine qualified feature id");
      v324 = &v442;
      LOBYTE(v182) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v182,
        3,
        ": {}");
    }
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
LABEL_446:
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
    if ( v402 )
      goto LABEL_38;
    goto LABEL_39;
  }
LABEL_428:
  v176 = (_QWORD *)*((_QWORD *)v65 + 5);
  v303[0] = &v176[*((_QWORD *)v65 + 3)];
  if ( v176 != (_QWORD *)v303[0] )
  {
    do
    {
      v306[0] = *v176;
      v177 = *(const wchar_t *const ***)(v306[0] + 48LL);
      for ( v305[0] = &v177[*(_QWORD *)(v306[0] + 32LL)]; v177 != (const wchar_t *const **)v305[0]; ++v177 )
      {
        v178 = *v177;
        v287 = *v177;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v403,
                &v287)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v405,
                &v287)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v406,
                &v287) )
        {
          FeatureOnDevice = CUpdateEvaluator::FindFeatureOnDevice(
                              this,
                              (const struct CCompositionDatabase::Feature *const)v178);
          if ( FeatureOnDevice && (!v286[4] || (*((_BYTE *)FeatureOnDevice + 52) & 0x6E) != 0) )
          {
            if ( *((_QWORD **)&v409 + 1) == v410 )
            {
              std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
                &v409,
                *((_QWORD *)&v409 + 1),
                &v287);
            }
            else
            {
              **((_QWORD **)&v409 + 1) = v178;
              *((_QWORD *)&v409 + 1) += 8LL;
            }
          }
          else if ( (*((_DWORD *)this + 12) == 1 || *((_DWORD *)this + 12) == 19)
                 && (unsigned __int8)(*((_BYTE *)v178 + 368) - 2) <= 1u )
          {
            v183 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v178 + 1);
            if ( v183 )
            {
              v286[1] = 0;
              if ( CUpdateEvaluator::EvaluateConditional(this, v183, &v286[1]) >= 0 && v286[1] )
              {
                v468 = 0;
                v469 = 0;
                std::vector<CCompositionDatabase::Feature *>::reserve(&v468, *((_QWORD *)v178 + 39) + 1LL);
                v323 = v178;
                v309 = 0;
                v310 = 0;
                std::vector<CCompositionDatabase::Feature *>::_Buy_nonzero(&v309, 1);
                v184 = v309;
                *(_QWORD *)v309 = v323;
                *((_QWORD *)&v309 + 1) = v184 + 8;
                *(_QWORD *)&v298 = 0;
                std::_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>::~_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>(&v298);
                v24 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v294, &v309, &v468);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v309);
                if ( v24 < 0 )
                {
                  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v468);
                  goto LABEL_475;
                }
                v185 = (_QWORD *)*((_QWORD *)&v468 + 1);
                v186 = (_QWORD *)v468;
                if ( (_QWORD)v468 != *((_QWORD *)&v468 + 1) )
                {
                  v187 = (_QWORD *)*((_QWORD *)&v409 + 1);
                  do
                  {
                    if ( (const wchar_t *const *)*v186 != v178 )
                    {
                      if ( v187 == v410 )
                      {
                        std::vector<CCompositionDatabase::Feature *>::_Emplace_reallocate<CCompositionDatabase::Feature * const &>(
                          &v409,
                          v187,
                          v186);
                        v187 = (_QWORD *)*((_QWORD *)&v409 + 1);
                      }
                      else
                      {
                        *v187 = *v186;
                        v187 = (_QWORD *)(*((_QWORD *)&v409 + 1) + 8LL);
                        *((_QWORD *)&v409 + 1) += 8LL;
                      }
                    }
                    ++v186;
                  }
                  while ( v186 != v185 );
                  v185 = (_QWORD *)*((_QWORD *)&v468 + 1);
                  v186 = (_QWORD *)v468;
                }
                if ( (unsigned __int64)(v185 - v186) > 1 )
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Edition feature dependencies included due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v306[0],
                    v178 + 8,
                    v178 + 7);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v468);
              }
            }
          }
        }
      }
      ++v176;
    }
    while ( v176 != (_QWORD *)v303[0] );
    v65 = v294;
  }
  v188 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v65, &v409, &v412);
  v24 = v188;
  v189 = 0;
  if ( v188 < 0 )
  {
    v441 = v188;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to determine feature dependency closure");
      *(_QWORD *)v322 = &v441;
      v284 = (int **)v322;
      LOBYTE(v190) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v190,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1629,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      (int)v284);
LABEL_475:
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
    goto LABEL_384;
  }
  if ( (_QWORD)v409 != *((_QWORD *)&v409 + 1) )
    *((_QWORD *)&v409 + 1) = v409;
  v191 = (__int64 *)*((_QWORD *)&v412 + 1);
  v192 = (__int64 *)v412;
  if ( (_QWORD)v412 != *((_QWORD *)&v412 + 1) )
  {
    do
    {
      v291 = *v192;
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        &v403,
        v308,
        &v291);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v405,
        &v291);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v406,
        &v291);
      ++v192;
    }
    while ( v192 != v191 );
    if ( (_QWORD)v412 != *((_QWORD *)&v412 + 1) )
      *((_QWORD *)&v412 + 1) = v412;
  }
  v193 = *(const wchar_t *const ***)v403;
  v292 = *(const wchar_t *const ***)v403;
  while ( !*((_BYTE *)v193 + 25) )
  {
    v194 = (const struct CCompositionDatabase::Feature *)v193[4];
    n = v194;
    v29 = GetQualifiedFeatureId(v194, &v402);
    if ( v29 < 0 )
    {
      v467 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Unable to determine qualified feature id");
        v319 = &v467;
        LOBYTE(v199) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v199,
          3,
          ": {}");
      }
      goto LABEL_508;
    }
    v291 = 0;
    v29 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v291);
    if ( v29 < 0 )
    {
      v437 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Unable to create feature modification request");
        *(_QWORD *)v320 = &v437;
        v284 = (int **)v320;
        LOBYTE(v198) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v198,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1641,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v29,
        (int)v284);
LABEL_508:
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
      goto LABEL_509;
    }
    v195 = (_BYTE *)v291;
    v196 = *(_QWORD *)(v291 + 16);
    if ( !v196 || (v286[4] || *(_DWORD *)(v196 + 52)) && (*(_BYTE *)(v196 + 48) & 4) == 0 )
    {
      if ( !CUpdateEvaluator::IsFeatureInstallAllowed(this, v194) )
      {
        v29 = -2146467829;
        v440 = -2146467829;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Required feature not available for install: Group: {0}, FMID: {1}, Feature: {2}",
            (char *)v194 + 72,
            (char *)v194 + 64,
            (char *)v194 + 56);
          v321 = &v440;
          v284 = &v321;
          LOBYTE(v197) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v197,
            3,
            ": {}");
        }
        v181 = 5723;
        goto LABEL_441;
      }
    }
    else
    {
      v189 = 1;
    }
    if ( v195[32] || v189 )
    {
      v189 = 0;
    }
    else
    {
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature added due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v194 + 72,
        (char *)v194 + 64,
        (char *)v194 + 56);
      v195[32] = 1;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
        v418,
        v308,
        &n,
        &v291);
      v189 = 0;
      if ( !*(_DWORD *)(*(_QWORD *)v195 + 16LL) )
        *(_DWORD *)(*(_QWORD *)v195 + 16LL) = *((_DWORD *)v194 + 95);
    }
    if ( v195[33] )
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature will not be removed due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v194 + 72,
        (char *)v194 + 64,
        (char *)v194 + 56);
    v195[33] = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v414,
      &n);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v292);
    v193 = v292;
  }
  v200 = *((_QWORD *)v65 + 5);
  *(_QWORD *)&v298 = v200 + 8LL * *((_QWORD *)v65 + 3);
  if ( v200 != (_QWORD)v298 )
  {
    do
    {
      v201 = *(const struct CCompositionDatabase::Feature ***)(*(_QWORD *)v200 + 48LL);
      v202 = &v201[*(_QWORD *)(*(_QWORD *)v200 + 32LL)];
      while ( v201 != v202 )
      {
        v203 = *v201;
        v287 = (const wchar_t *const *)*v201;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v403,
                &v287)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v405,
                &v287)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v406,
                &v287)
          && CUpdateEvaluator::FindFeatureOnDevice(this, v203) )
        {
          updated = GetQualifiedFeatureId(v203, &v402);
          if ( updated < 0 )
          {
            v462 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Unable to determine qualified feature id");
              v317 = &v462;
              LOBYTE(v207) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v207,
                3,
                ": {}");
            }
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
LABEL_534:
            if ( v402 )
              goto LABEL_535;
            goto LABEL_536;
          }
          v291 = 0;
          updated = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v291);
          if ( updated < 0 )
          {
            v463 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Unable to create feature modification request");
              *(_QWORD *)v318 = &v463;
              v285 = v318;
              LOBYTE(v206) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v206,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x168E,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
              (const char *)(unsigned int)updated,
              (int)v285);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
            if ( v402 )
            {
LABEL_535:
              operator delete((void *)(v402 - 8));
              v402 = 0;
            }
LABEL_536:
            v24 = updated;
            goto LABEL_716;
          }
          *(_BYTE *)(v291 + 33) = 1;
          std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
            v414,
            v308,
            &v287,
            &v291);
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            v405,
            v363,
            &v287);
        }
        ++v201;
      }
      v200 += 8;
    }
    while ( v200 != (_QWORD)v298 );
    v65 = v294;
  }
  v205 = *(const struct CCompositionDatabase::Feature **)v414[0];
  n = *(const struct CCompositionDatabase::Feature **)v414[0];
  while ( !*((_BYTE *)v205 + 25) )
  {
    *(_BYTE *)(*((_QWORD *)v205 + 5) + 32LL) = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v418,
      *((_QWORD *)v205 + 5) + 8LL);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v205 = n;
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v412);
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v409);
  v471 = 0;
  v472 = 0;
  std::set_intersection<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::back_insert_iterator<std::vector<CCompositionDatabase::Feature *>>>(
    (unsigned int)&v298,
    *(_QWORD *)v403,
    (_DWORD)v403,
    *(_QWORD *)v405[0],
    v405[0],
    (__int64)&v471);
  v208 = (_QWORD *)*((_QWORD *)&v471 + 1);
  v209 = (_QWORD *)v471;
  if ( (_QWORD)v471 != *((_QWORD *)&v471 + 1) )
  {
    do
    {
      v210 = *v209;
      if ( (int)GetQualifiedFeatureId(*v209, &v402) >= 0 )
        LogAdapter::TraceAtLevelHr<long,AutoScz>(3, 2148499470LL, "Cannot remove required feature : {0}", &v402);
      else
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          3,
          2148499470LL,
          "Cannot remove required feature : {0}",
          v210 + 56);
      ++v209;
    }
    while ( v209 != v208 );
    v65 = v294;
    if ( (_QWORD)v471 != *((_QWORD *)&v471 + 1) )
    {
      v460 = -2146467826;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Operation requires removal of required features");
        *(_QWORD *)v316 = &v460;
        v284 = (int **)v316;
        LOBYTE(v211) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v211,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B7,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)0x800F800ELL,
        (int)v284);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v471);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
      if ( v402 )
      {
        operator delete((void *)(v402 - 8));
        v402 = 0;
      }
      v24 = -2146467826;
      goto LABEL_716;
    }
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v471);
  v286[1] = 0;
  v286[3] = 0;
  v214 = *(const struct CCompositionDatabase::Feature **)v415[0];
  n = *(const struct CCompositionDatabase::Feature **)v415[0];
  while ( !*((_BYTE *)v214 + 25) )
  {
    v215 = *((_QWORD *)v214 + 8);
    LOBYTE(v213) = *(_BYTE *)(v215 + 33);
    LOBYTE(v212) = *(_BYTE *)(v215 + 32);
    EvaluateFeatureDeclares(
      *(_QWORD *)(v215 + 8),
      v212,
      v213,
      (unsigned int)&v416,
      (__int64)v470,
      (__int64)&v286[1],
      (__int64)&v286[3]);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v214 = n;
  }
  if ( !*(_DWORD *)this && (v286[1] || v286[3]) )
  {
    std::wstring::wstring(v369, L"en-US");
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
      &v416,
      v308,
      v369);
    std::wstring::~wstring(v369);
  }
  v216 = *(const struct CCompositionDatabase::Feature **)v416;
  n = *(const struct CCompositionDatabase::Feature **)v416;
  while ( !*((_BYTE *)v216 + 25) )
  {
    LogAdapter::TraceInfo<std::wstring>("Supported language: {0}", (char *)v216 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v216 = n;
  }
  v217 = *(const struct CCompositionDatabase::Feature **)v470[0];
  n = *(const struct CCompositionDatabase::Feature **)v470[0];
  while ( !*((_BYTE *)v217 + 25) )
  {
    LogAdapter::TraceInfo<std::wstring>("Supported architecture: {0}", (char *)v217 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v217 = n;
  }
  v218 = v296;
  v219 = CActionListCreator::DetermineOverlayPolicy(v296, *((const struct CDeviceInfo **)this + 12));
  v24 = v219;
  if ( v219 < 0 )
  {
    v453 = v219;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to fetch overlay policy");
      v315 = &v453;
      v284 = &v315;
      LOBYTE(v220) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v220,
        3,
        ": {}");
    }
    v118 = 5856;
    goto LABEL_377;
  }
  v221 = (struct CCompositionDatabase::Feature *)*((_QWORD *)v65 + 5);
  v301 = v221;
  v302 = (struct CCompositionDatabase::Feature *)((char *)v221 + 8 * *((_QWORD *)v65 + 3));
  if ( v221 == v302 )
    goto LABEL_610;
  while ( 2 )
  {
    n = *(const struct CCompositionDatabase::Feature **)v221;
    v222 = (const wchar_t *const **)*((_QWORD *)n + 6);
    v292 = v222;
    v303[0] = &v222[*((_QWORD *)n + 4)];
    if ( v222 == (const wchar_t *const **)v303[0] )
      goto LABEL_608;
    while ( 2 )
    {
      v223 = (const wchar_t **)*v222;
      v287 = *v222;
      v224 = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v418,
        &v298,
        &v287);
      v225 = v298;
      if ( (_QWORD)v298 != v418[0] )
      {
        v286[1] = 1;
        goto LABEL_569;
      }
      v286[1] = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v414,
        v306,
        &v287);
      v225 = v306[0];
      if ( v306[0] == v414[0] )
      {
        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
          v421,
          v305,
          &v287);
        if ( v305[0] == v421[0] )
        {
          LODWORD(v288) = 0;
          v229 = 0;
          FeatureStateOnDevice = CUpdateEvaluator::FindFeatureStateOnDevice(
                                   this,
                                   (const struct CCompositionDatabase::Feature *const)v223);
          goto LABEL_570;
        }
        v234 = *(_QWORD **)(v305[0] + 40LL);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v234[2];
        v235 = *v234;
        v236 = *(_DWORD *)(*v234 + 16LL);
        LODWORD(v288) = v236;
        v229 = *(_DWORD *)(v235 + 20);
        if ( *((_BYTE *)v223 + 368) != 16 )
        {
          LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
            "Feature modified due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
            v223 + 9,
            v223 + 8,
            v223 + 7);
          if ( v236
            && (std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v361),
                updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v296, (_DWORD)v223, v236, 0, (__int64)v361, 1),
                std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v361),
                updated < 0) )
          {
            v452 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed adding feature for token updates");
              *(_QWORD *)v314 = &v452;
              v284 = (int **)v314;
              LOBYTE(v259) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v259,
                3,
                ": {}");
            }
            v238 = 5902;
          }
          else
          {
            if ( !v229 )
              goto LABEL_570;
            std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v360);
            updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v296, (_DWORD)v223, v229, 0, (__int64)v360, 0);
            std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v360);
            if ( updated >= 0 )
              goto LABEL_570;
            v451 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed adding feature for token updates");
              v313 = &v451;
              v284 = &v313;
              LOBYTE(v237) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v237,
                3,
                ": {}");
            }
            v238 = 5913;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v238,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)updated,
            (int)v284);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
          goto LABEL_534;
        }
      }
      else
      {
        v224 = 1;
LABEL_569:
        v226 = *(_QWORD **)(v225 + 40);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v226[2];
        v228 = *v226;
        LODWORD(v288) = *(_DWORD *)(*v226 + 16LL);
        v229 = *(_DWORD *)(v228 + 20);
      }
LABEL_570:
      if ( FeatureStateOnDevice )
      {
        v230 = v224 ^ 1;
        *((_BYTE *)FeatureStateOnDevice + 1) = v230;
        if ( v230 )
        {
          if ( *((_BYTE *)v223 + 369) )
          {
            v231 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 3);
            v232 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 4);
            if ( v231 != v232 )
            {
              while ( 1 )
              {
                v233 = v231[3] <= 7u ? (const wchar_t *)v231 : (const wchar_t *)*v231;
                PackageInAnyGroup = CUpdateEvaluator::FindPackageInAnyGroup(this, v233);
                if ( !PackageInAnyGroup )
                  break;
                *(_WORD *)PackageInAnyGroup = 1;
                v231 += 4;
                if ( v231 == v232 )
                  goto LABEL_591;
              }
              v29 = -2147023728;
              v450 = -2147023728;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<std::wstring>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed finding package: {0}",
                  v231);
                *(_QWORD *)v312 = &v450;
                v284 = (int **)v312;
                LOBYTE(v260) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v260,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1730,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)0x80070490LL,
                (int)v284);
              goto LABEL_446;
            }
          }
        }
      }
LABEL_591:
      if ( v286[1] )
      {
        v253 = 0;
        if ( *((_DWORD *)this + 12) == 1 )
        {
          if ( (unsigned __int8)(*((_BYTE *)v223 + 368) - 5) <= 1u )
            v253 = 8;
        }
        else if ( *((_DWORD *)this + 12) == 24 )
        {
          v253 = 32;
        }
        if ( FeatureStateOnDevice && (!v286[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          v254 = 1;
        else
          v254 = 2;
        v255 = v254 | v253;
        if ( v223 == (const wchar_t **)v295 && *((_DWORD *)v297 + 80) == 16 )
          v255 |= 0x10u;
        v65 = v294;
        v256 = CUpdateEvaluator::ServiceFeatureAndPackages(
                 (int)this,
                 v255,
                 (int)v288,
                 v229,
                 (__int64)&v416,
                 (__int64)v470,
                 (__int64)FeatureStateOnDevice,
                 (struct CCompositionDatabase::Feature *)v223,
                 (__int64)v294,
                 (__int64)v296);
        v29 = v256;
        if ( v256 < 0 )
        {
          v449 = v256;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t *>(
              (_DWORD)v223 + 64,
              3,
              (unsigned int)"Failed adding InstallPackage actions for feature: Group: {0}, FMID: {1}, Feature: {2}",
              (_DWORD)v223 + 72,
              (__int64)(v223 + 8),
              (__int64)(v223 + 7));
            *(_QWORD *)v311 = &v449;
            v284 = (int **)v311;
            LOBYTE(v257) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v257,
              3,
              ": {}");
          }
          v258 = 6012;
          goto LABEL_641;
        }
      }
      else
      {
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v406,
                &v287) )
        {
          if ( FeatureStateOnDevice
            && *((_BYTE *)FeatureStateOnDevice + 1)
            && (!v286[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not updating Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v223 + 8,
              v223 + 7);
            v240 = *((_QWORD *)FeatureStateOnDevice + 4);
            for ( k = *((_QWORD *)FeatureStateOnDevice + 3); k != v240; k += 32 )
            {
              if ( *(_QWORD *)(k + 24) <= 7u )
                v242 = (const wchar_t *)k;
              else
                v242 = *(const wchar_t **)k;
              v243 = CUpdateEvaluator::FindPackageInAnyGroup(this, v242);
              if ( v243 )
                *(_WORD *)v243 = 1;
            }
          }
          else
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not applicable Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v223 + 8,
              v223 + 7);
          }
        }
        v65 = v294;
      }
      v222 = v292 + 1;
      v292 = v222;
      if ( v222 != (const wchar_t *const **)v303[0] )
        continue;
      break;
    }
    v221 = v301;
LABEL_608:
    v221 = (struct CCompositionDatabase::Feature *)((char *)v221 + 8);
    v301 = v221;
    if ( v221 != v302 )
      continue;
    break;
  }
  v218 = v296;
LABEL_610:
  if ( *(_DWORD *)this != 1 )
    goto LABEL_728;
  v244 = *((_DWORD *)this + 12);
  if ( v244 <= 0x13 )
  {
    v245 = 526338;
    if ( _bittest(&v245, v244) )
    {
      v246 = (const wchar_t *const **)**((_QWORD **)this + 4);
      v292 = v246;
      while ( !*((_BYTE *)v246 + 25) )
      {
        v247 = (const struct CCompositionDatabase::Feature *)**((_QWORD **)v246[4] + 2);
        n = v247;
        while ( !*((_BYTE *)v247 + 25) )
        {
          v248 = *((_QWORD *)v247 + 4);
          if ( (*(_BYTE *)(v248 + 52) & 1) == 0
            && !CCompositionDatabase::FindFeature(
                  v65,
                  *v246[4],
                  *(const wchar_t *const *)(v248 + 8),
                  *(const wchar_t *const *)(v248 + 16)) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not modifying Group: {}, FMID: {}, Feature: {}",
              v246[4],
              *((_QWORD *)v247 + 4) + 8LL,
              *((_QWORD *)v247 + 4) + 16LL);
            *(_BYTE *)(*((_QWORD *)v247 + 4) + 1LL) = 1;
            v249 = *((_QWORD *)v247 + 4);
            v250 = *(_QWORD *)(v249 + 32);
            for ( m = *(_QWORD *)(v249 + 24); m != v250; m += 32 )
            {
              if ( *(_QWORD *)(m + 24) <= 7u )
                v252 = (const wchar_t *)m;
              else
                v252 = *(const wchar_t **)m;
              v261 = CUpdateEvaluator::FindPackageInAnyGroup(this, v252);
              if ( v261 )
                *(_BYTE *)v261 = 1;
            }
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
          v247 = n;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v292);
        v246 = v292;
      }
    }
  }
  if ( *(_DWORD *)this != 1
    || !v295
    || *((_DWORD *)this + 12) != 2
    && *((_DWORD *)this + 12) != 14
    && *((_DWORD *)this + 12) != 15
    && *((_DWORD *)this + 12) != 22 )
  {
    goto LABEL_728;
  }
  v262 = (const wchar_t *const **)**((_QWORD **)this + 4);
  v292 = v262;
LABEL_662:
  if ( *((_BYTE *)v262 + 25) )
  {
LABEL_728:
    if ( *((_BYTE *)v218 + 78) )
    {
      if ( *((_BYTE *)v218 + 77) )
        *(_BYTE *)(*(_QWORD *)v218 + 1184LL) = 1;
    }
    else if ( *((_BYTE *)v218 + 77) )
    {
      v271 = *(_QWORD **)v218;
      free(*(void **)(*(_QWORD *)v218 + 1096LL));
      v271[137] = 0;
      v271[135] = 0;
      v271[136] = 0;
    }
    v272 = *((_DWORD *)this + 12);
    if ( v272 == 3 )
    {
      v273 = CUpdateEvaluator::RemoveFeaturesAndPackages(this, v65, v421, v218);
      v24 = v273;
      if ( v273 < 0 )
      {
        v445 = v273;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed removing features and packages");
          v350 = &v445;
          v284 = &v350;
          LOBYTE(v274) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v274,
            3,
            ": {}");
        }
        v118 = 6134;
        goto LABEL_377;
      }
LABEL_702:
      v276 = (struct ActionList::Product **)*((_QWORD *)v65 + 13);
      v277 = &v276[*((_QWORD *)v65 + 11)];
      while ( v276 != v277 )
      {
        v29 = CActionListCreator::UpdateProduct(v218, *v276);
        if ( v29 < 0 )
        {
          v444 = v29;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            v282 = &dword_1801CAD7C;
            if ( !*(_DWORD *)*v276 )
              v282 = (int *)L"SystemManifest";
            v344 = v282;
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t const *>(
              &v344,
              v278,
              "Failed adding product update: Name {0}, Version {1}",
              (char *)*v276 + 8,
              (char *)*v276 + 16,
              &v344);
            v343 = &v444;
            v284 = &v343;
            LOBYTE(v283) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v283,
              3,
              ": {}");
          }
          v258 = 6146;
LABEL_641:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v258,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)v29,
            (int)v284);
          goto LABEL_509;
        }
        ++v276;
      }
      if ( *((_BYTE *)this + 119) )
      {
        LogAdapter::TraceInfo<>("Reordering packages for servicing based upgrade.");
        CActionListCreator::FinalizeActionListForServicingUpgrade(v218, v65);
      }
      if ( *((_DWORD *)this + 12) != 1
        || (v279 = CUpdateEvaluator::AddBaselinePackagesIfNeeded(this, v65, v218), v24 = v279, v279 >= 0) )
      {
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
        if ( v402 )
        {
          operator delete((void *)(v402 - 8));
          v402 = 0;
        }
        std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v421);
        std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v414);
        std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v418);
        std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v415);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v470);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v416);
        return 0;
      }
      v443 = v279;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed adding baseline packages");
        *(_QWORD *)v342 = &v443;
        v284 = (int **)v342;
        LOBYTE(v280) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v280,
          3,
          ": {}");
      }
      v157 = 6162;
LABEL_713:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v157,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        (int)v284);
      goto LABEL_714;
    }
    if ( (unsigned int)(v272 - 14) <= 1 )
      goto LABEL_699;
    if ( !*((_BYTE *)this + 119) )
      goto LABEL_702;
    v275 = L"servicing";
    if ( (unsigned int)(v272 - 14) <= 1 )
LABEL_699:
      v275 = L"media";
    v348 = v275;
    LogAdapter::TraceInfo<wchar_t const *>("Stripping media section, because this is {0}-based upgrade", &v348);
    if ( *(_QWORD *)v218 )
      *(_QWORD *)(*(_QWORD *)v218 + 80LL) = 0;
    goto LABEL_702;
  }
  v263 = (const struct CCompositionDatabase::Feature *)**((_QWORD **)v262[4] + 2);
  for ( n = v263; ; v263 = n )
  {
    if ( *((_BYTE *)v263 + 25) )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v292);
      v262 = v292;
      goto LABEL_662;
    }
    v264 = *((_QWORD *)v263 + 4);
    if ( (*(_BYTE *)(v264 + 52) & 1) != 0 )
    {
      v265 = Windows::StringUtil::AsLUnicode(v386, *(_QWORD *)(v264 + 16));
      v367 = *(_OWORD *)v265;
      v266 = v367;
      v368 = *(_QWORD *)(v265 + 16);
      v267 = Windows::StringUtil::TrimPrefixIfPresent<_LUNICODE_STRING,_LUNICODE_STRING>(
               v387,
               ___LiteralObject__2U__BaseLiteralBuffer__03U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EP__0ED__0CN__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
               &v367);
      v473 = *(_OWORD *)v267;
      v474 = *(_QWORD *)(v267 + 16);
      if ( (unsigned __int64)v473 < v266 )
        break;
    }
LABEL_674:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
  }
  v293 = 0;
  v29 = SczAllocFromLUnicodeString(&v293, &v473);
  if ( v29 < 0 )
  {
    v270 = 6090;
    goto LABEL_684;
  }
  if ( !(unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                           &v473,
                           ___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HC__0GF__0GD__0GB__0GM__0GM__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
LABEL_672:
    if ( v293 )
    {
      operator delete(v293 - 4);
      v293 = 0;
    }
    goto LABEL_674;
  }
  LogAdapter::TraceInfo<_LUNICODE_STRING>("Feature removed due to device state: {}", &v473);
  v29 = CActionListCreator::RemoveInstalledFeature(v218, v293, 0, 0);
  if ( v29 >= 0 )
  {
    memset(v389, 0, sizeof(v389));
    v390 = 0;
    v391 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v392);
    std::set<CCompositionDatabase::Feature::FeaturePackageMediaState>::set<CCompositionDatabase::Feature::FeaturePackageMediaState>(v393);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v394);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v395);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v396);
    v397 = 0;
    v398 = 0;
    v399 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v400);
    v401 = 0;
    *((_QWORD *)&v390 + 1) = v293;
    v24 = CActionListCreator::UpdateFeatureTokens(
            (_DWORD)v218,
            (unsigned int)v389,
            64,
            *(_DWORD *)(*((_QWORD *)v263 + 4) + 48LL),
            *((_QWORD *)v263 + 4) + 56LL,
            0);
    if ( v24 < 0 )
    {
      v447 = v24;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed adding feature for token updates");
        *(_QWORD *)v353 = &v447;
        v284 = (int **)v353;
        LOBYTE(v268) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v268,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E2,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        (int)v284);
      CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v389);
      if ( v293 )
      {
        operator delete(v293 - 4);
        v293 = 0;
      }
      goto LABEL_384;
    }
    CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v389);
    goto LABEL_672;
  }
  v446 = v29;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<_LUNICODE_STRING>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed adding RemoveFeature: Feature: {}",
      &v473);
    v352 = &v446;
    v284 = &v352;
    LOBYTE(v269) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v269,
      3,
      ": {}");
  }
  v270 = 6100;
LABEL_684:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v270,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
    (const char *)(unsigned int)v29,
    (int)v284);
  if ( v293 )
  {
    operator delete(v293 - 4);
    v293 = 0;
  }
LABEL_509:
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v406);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v405);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v403);
  if ( v402 )
  {
LABEL_38:
    operator delete((void *)(v402 - 8));
    v402 = 0;
  }
LABEL_39:
  v24 = v29;
LABEL_716:
  std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v421);
  std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v414);
  std::map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>::~map<wchar_t const * const,FeatureTokenInfo const * const,WcstringCaseInsensitiveCompare,std::allocator<std::pair<wchar_t const * const,FeatureTokenInfo const * const>>>(v418);
  std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v415);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v470);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v416);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800d8bbc  mov     rax, rsp
0x1800d8bbf  push    rbp
0x1800d8bc0  push    rsi
0x1800d8bc1  push    rdi
0x1800d8bc2  push    r12
0x1800d8bc4  push    r13
0x1800d8bc6  push    r14
0x1800d8bc8  push    r15
0x1800d8bca  lea     rbp, [rax-7E8h]
0x1800d8bd1  sub     rsp, 8B0h
0x1800d8bd8  mov     [rbp+7E0h+var_5A0], 0FFFFFFFFFFFFFFFEh
0x1800d8be3  mov     [rax+20h], rbx
0x1800d8be7  movaps  xmmword ptr [rax-48h], xmm6
0x1800d8beb  mov     rax, cs:__security_cookie
0x1800d8bf2  xor     rax, rsp
0x1800d8bf5  mov     [rbp+7E0h+var_50], rax
0x1800d8bfc  mov     [rbp+7E0h+var_840], r8
0x1800d8c00  mov     [rbp+7E0h+var_850], rdx
0x1800d8c04  mov     r13, rcx
0x1800d8c07  lea     rcx, aArbiterEvaluat; "arbiter: Evaluating features for instal"...
0x1800d8c0e  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800d8c13  mov     rax, [r13+60h]
0x1800d8c17  mov     al, [rax+130h]
0x1800d8c1d  mov     [rsp+8E0h+var_890+4], al
0x1800d8c21  xor     esi, esi
0x1800d8c23  mov     [rbp+7E0h+var_198], rsi
0x1800d8c2a  mov     [rbp+7E0h+var_190], rsi
0x1800d8c31  lea     r15d, [rsi+40h]
0x1800d8c35  mov     ecx, r15d; Size
0x1800d8c38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8c3d  mov     [rax], rax
0x1800d8c40  mov     [rax+8], rax
0x1800d8c44  mov     [rax+10h], rax
0x1800d8c48  mov     word ptr [rax+18h], 101h
0x1800d8c4e  mov     [rbp+7E0h+var_198], rax
0x1800d8c55  mov     rdx, [r13+60h]
0x1800d8c59  add     rdx, 0B0h
0x1800d8c60  lea     rcx, [rbp+7E0h+var_90]
0x1800d8c67  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>> const &)
0x1800d8c6c  nop
0x1800d8c6d  mov     rax, [r13+60h]
0x1800d8c71  mov     rbx, [rax+0A0h]
0x1800d8c78  mov     rbx, [rbx]
0x1800d8c7b  cmp     [rbx+19h], sil
0x1800d8c7f  jnz     loc_1800D8DE7
0x1800d8c85  lea     rsi, [rbx+20h]
0x1800d8c89  mov     [rsp+8E0h+var_890], 1
0x1800d8c8e  xor     r14d, r14d
0x1800d8c91  cmp     [r13+79h], r14b
0x1800d8c95  jz      short loc_1800D8CEF
0x1800d8c97  cmp     qword ptr [rsi+18h], 7
0x1800d8c9c  jbe     short loc_1800D8CA3
0x1800d8c9e  mov     r8, [rsi]
0x1800d8ca1  jmp     short loc_1800D8CA6
0x1800d8ca3  mov     r8, rsi; wchar_t *
0x1800d8ca6  lea     rax, [rsp+8E0h+var_890]
0x1800d8cab  mov     [rsp+8E0h+var_8C0], rax; bool *
0x1800d8cb0  lea     rdx, aUserprofilelan_0; "UserProfileLanguage"
0x1800d8cb7  mov     rcx, [r13+60h]; this
0x1800d8cbb  call    ?MatchNameValueSetPair@CDeviceInfo@@QEBAJQEB_W0_NPEA_N@Z; CDeviceInfo::MatchNameValueSetPair(wchar_t const * const,wchar_t const * const,bool,bool *)
0x1800d8cc0  cmp     [rsp+8E0h+var_890], r14b
0x1800d8cc5  jnz     short loc_1800D8CEF
0x1800d8cc7  mov     rdx, rsi
0x1800d8cca  lea     rcx, aRemovingUnused; "Removing unused language: {0} from sate"...
0x1800d8cd1  call    ??$TraceInfo@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXQEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceInfo<std::wstring>(char const * const,std::wstring const &)
0x1800d8cd6  xor     esi, esi
0x1800d8cd8  mov     rcx, [rbx+10h]
0x1800d8cdc  cmp     [rcx+19h], sil
0x1800d8ce0  jz      loc_1800D8DC3
0x1800d8ce6  mov     rax, [rbx+8]
0x1800d8cea  jmp     loc_1800D8DB5
0x1800d8cef  mov     r8, rsi
0x1800d8cf2  lea     rdx, [rbp+7E0h+var_450]
0x1800d8cf9  lea     rcx, [rbp+7E0h+var_198]
0x1800d8d00  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800d8d05  movups  xmm6, xmmword ptr [rax]
0x1800d8d08  mov     r8, rsi
0x1800d8d0b  mov     rdx, [rax+10h]
0x1800d8d0f  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x1800d8d14  test    al, al
0x1800d8d16  jnz     short loc_1800D8CD6
0x1800d8d18  mov     rax, 3FFFFFFFFFFFFFFh
0x1800d8d22  cmp     [rbp+7E0h+var_190], rax
0x1800d8d29  jz      loc_1800DCFA9
0x1800d8d2f  mov     rdi, [rbp+7E0h+var_198]
0x1800d8d36  lea     rax, [rbp+7E0h+var_198]
0x1800d8d3d  mov     [rbp+7E0h+var_7F8], rax
0x1800d8d41  mov     [rbp+7E0h+var_7F0], r14
0x1800d8d45  mov     rcx, r15; Size
0x1800d8d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8d4d  mov     [rbp+7E0h+var_7F0], rax
0x1800d8d51  lea     rcx, [rax+20h]
0x1800d8d55  mov     rdx, rsi
0x1800d8d58  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800d8d5d  mov     rax, [rbp+7E0h+var_7F0]
0x1800d8d61  mov     [rax], rdi
0x1800d8d64  mov     rax, [rbp+7E0h+var_7F0]
0x1800d8d68  mov     [rax+8], rdi
0x1800d8d6c  mov     rax, [rbp+7E0h+var_7F0]
0x1800d8d70  mov     [rax+10h], rdi
0x1800d8d74  mov     rax, [rbp+7E0h+var_7F0]
0x1800d8d78  xor     esi, esi
0x1800d8d7a  mov     [rax+18h], sil
0x1800d8d7e  mov     rax, [rbp+7E0h+var_7F0]
0x1800d8d82  mov     [rax+19h], sil
0x1800d8d86  mov     r8, [rbp+7E0h+var_7F0]
0x1800d8d8a  mov     [rbp+7E0h+var_7F0], rsi
0x1800d8d8e  movdqu  [rbp+7E0h+var_830], xmm6
0x1800d8d93  lea     rdx, [rbp+7E0h+var_830]
0x1800d8d97  lea     rcx, [rbp+7E0h+var_198]
0x1800d8d9e  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFeatureAction@ActionList@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFeatureAction@ActionList@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFeatureAction@ActionList@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ActionList::FeatureAction>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,ActionList::FeatureAction>,void *> *>,std::_Tree_node<std::pair<std::wstring const,ActionList::FeatureAction>,void *> * const)
0x1800d8da3  jmp     loc_1800D8CD8
0x1800d8da8  cmp     rbx, [rax+10h]
0x1800d8dac  jnz     short loc_1800D8DBB
0x1800d8dae  mov     rbx, rax
0x1800d8db1  mov     rax, [rax+8]
0x1800d8db5  cmp     [rax+19h], sil
0x1800d8db9  jz      short loc_1800D8DA8
0x1800d8dbb  mov     rbx, rax
0x1800d8dbe  jmp     loc_1800D8C7B
0x1800d8dc3  mov     rbx, rcx
0x1800d8dc6  mov     rcx, [rcx]
0x1800d8dc9  cmp     [rcx+19h], sil
0x1800d8dcd  jnz     loc_1800D8C7B
0x1800d8dd3  mov     rbx, rcx
0x1800d8dd6  mov     rax, [rcx]
0x1800d8dd9  mov     rcx, rax
0x1800d8ddc  cmp     [rax+19h], sil
0x1800d8de0  jz      short loc_1800D8DD3
0x1800d8de2  jmp     loc_1800D8C7B
0x1800d8de7  mov     [rbp+7E0h+var_1A8], rsi
0x1800d8dee  mov     [rbp+7E0h+var_1A0], rsi
0x1800d8df5  mov     ecx, 48h ; 'H'; Size
0x1800d8dfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8dff  mov     [rax], rax
0x1800d8e02  mov     [rax+8], rax
0x1800d8e06  mov     [rax+10h], rax
0x1800d8e0a  mov     word ptr [rax+18h], 101h
0x1800d8e10  mov     [rbp+7E0h+var_1A8], rax
0x1800d8e17  mov     [rbp+7E0h+var_188], rsi
0x1800d8e1e  mov     [rbp+7E0h+var_180], rsi
0x1800d8e25  mov     ebx, 30h ; '0'
0x1800d8e2a  mov     ecx, ebx; Size
0x1800d8e2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8e31  mov     [rax], rax
0x1800d8e34  mov     [rax+8], rax
0x1800d8e38  mov     [rax+10h], rax
0x1800d8e3c  mov     word ptr [rax+18h], 101h
0x1800d8e42  mov     [rbp+7E0h+var_188], rax
0x1800d8e49  mov     [rbp+7E0h+var_1B8], rsi
0x1800d8e50  mov     [rbp+7E0h+var_1B0], rsi
0x1800d8e57  mov     ecx, ebx; Size
0x1800d8e59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8e5e  mov     [rax], rax
0x1800d8e61  mov     [rax+8], rax
0x1800d8e65  mov     [rax+10h], rax
0x1800d8e69  mov     word ptr [rax+18h], 101h
0x1800d8e6f  mov     [rbp+7E0h+var_1B8], rax
0x1800d8e76  mov     [rbp+7E0h+var_170], rsi
0x1800d8e7d  mov     [rbp+7E0h+var_168], rsi
0x1800d8e84  mov     ecx, ebx; Size
0x1800d8e86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8e8b  mov     [rax], rax
0x1800d8e8e  mov     [rax+8], rax
0x1800d8e92  mov     [rax+10h], rax
0x1800d8e96  mov     word ptr [rax+18h], 101h
0x1800d8e9c  mov     [rbp+7E0h+var_170], rax
0x1800d8ea3  mov     [rbp+7E0h+var_230], rsi
0x1800d8eaa  mov     [rbp+7E0h+var_228], rsi
0x1800d8eb1  mov     [rbp+7E0h+var_220], rsi
0x1800d8eb8  mov     ebx, 28h ; '('
0x1800d8ebd  mov     ecx, ebx
0x1800d8ebf  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800d8ec4  mov     [rax], rax
0x1800d8ec7  mov     [rax+8], rax
0x1800d8ecb  mov     [rax+10h], rax
0x1800d8ecf  mov     word ptr [rax+18h], 101h
0x1800d8ed5  mov     [rbp+7E0h+var_228], rax
0x1800d8edc  mov     [rbp+7E0h+var_218], rsi
0x1800d8ee3  mov     [rbp+7E0h+var_210], rsi
0x1800d8eea  mov     ecx, ebx
0x1800d8eec  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800d8ef1  mov     [rax], rax
0x1800d8ef4  mov     [rax+8], rax
0x1800d8ef8  mov     [rax+10h], rax
0x1800d8efc  mov     word ptr [rax+18h], 101h
0x1800d8f02  mov     [rbp+7E0h+var_218], rax
0x1800d8f09  mov     [rbp+7E0h+var_208], rsi
0x1800d8f10  mov     [rbp+7E0h+var_200], rsi
0x1800d8f17  mov     ecx, ebx
0x1800d8f19  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800d8f1e  mov     [rax], rax
0x1800d8f21  mov     [rax+8], rax
0x1800d8f25  mov     [rax+10h], rax
0x1800d8f29  mov     word ptr [rax+18h], 101h
0x1800d8f2f  mov     [rbp+7E0h+var_208], rax
0x1800d8f36  lea     r8, [rbp+7E0h+var_1A8]
0x1800d8f3d  mov     rdx, [rbp+7E0h+var_850]
0x1800d8f41  mov     rcx, r13
0x1800d8f44  call    ?GetDeferredUpdateRequests@CUpdateEvaluator@@AEAAJPEBVCCompositionDatabase@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUFeatureRequest@CUpdateEvaluator@@UWstringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@2@@std@@@Z; CUpdateEvaluator::GetDeferredUpdateRequests(CCompositionDatabase const *,std::map<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>> &)
0x1800d8f49  mov     ebx, eax
0x1800d8f4b  test    eax, eax
0x1800d8f4d  jns     short loc_1800D8FB5
0x1800d8f4f  mov     [rbp+7E0h+var_11C], eax
0x1800d8f55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8f5c  test    rcx, rcx
0x1800d8f5f  jz      short loc_1800D8FAB
0x1800d8f61  lea     r9, aFailedToGetDef; "Failed to get deferred updates"
0x1800d8f68  mov     esi, 3
0x1800d8f6d  mov     r8d, esi
0x1800d8f70  xor     edx, edx
0x1800d8f72  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d8f77  lea     rax, [rbp+7E0h+var_11C]
0x1800d8f7e  mov     [rbp+7E0h+var_688], rax
0x1800d8f85  lea     rax, [rbp+7E0h+var_688]
0x1800d8f8c  mov     [rsp+8E0h+var_8C0], rax
0x1800d8f91  lea     r9, asc_1801CAFB4; ": {}"
0x1800d8f98  mov     r8d, esi
0x1800d8f9b  mov     dl, 1
0x1800d8f9d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8fa4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d8fa9  xor     esi, esi
0x1800d8fab  mov     edx, 1244h
0x1800d8fb0  jmp     loc_1800D91F5
0x1800d8fb5  mov     rax, [rbp+7E0h+var_1A8]
0x1800d8fbc  mov     rax, [rax]
0x1800d8fbf  mov     [rsp+8E0h+var_868], rax
0x1800d8fc4  cmp     [rax+19h], sil
0x1800d8fc8  jnz     loc_1800D916F
0x1800d8fce  mov     [rbp+7E0h+var_174], esi
0x1800d8fd4  mov     [rbp+7E0h+var_178], esi
0x1800d8fda  mov     [rbp+7E0h+var_1F8], sil
0x1800d8fe1  mov     [rbp+7E0h+var_1F7], sil
0x1800d8fe8  mov     rbx, [rax+40h]
0x1800d8fec  mov     [rbp+7E0h+var_848], rbx
0x1800d8ff0  lea     rax, [rbp+7E0h+var_1F7]
0x1800d8ff7  mov     [rsp+8E0h+var_8B8], rax; bool *
0x1800d8ffc  lea     rax, [rbp+7E0h+var_1F8]
0x1800d9003  mov     [rsp+8E0h+var_8C0], rax; bool *
0x1800d9008  lea     r9, [rbp+7E0h+var_178]; enum FeatureIntentFlags *
0x1800d900f  lea     r8, [rbp+7E0h+var_174]; enum FeatureIntentFlags *
0x1800d9016  mov     rdx, rbx; struct CUpdateEvaluator::FeatureRequest *
0x1800d9019  mov     rcx, r13; this
0x1800d901c  call    ?EvaluateModifyRequest@CUpdateEvaluator@@AEAAJPEAUFeatureRequest@1@AEAW4FeatureIntentFlags@@1AEA_N2@Z; CUpdateEvaluator::EvaluateModifyRequest(CUpdateEvaluator::FeatureRequest *,FeatureIntentFlags &,FeatureIntentFlags &,bool &,bool &)
0x1800d9021  mov     edi, eax
0x1800d9023  test    eax, eax
0x1800d9025  js      short loc_1800D90A4
0x1800d9027  mov     rcx, [rbx]
0x1800d902a  mov     eax, [rbp+7E0h+var_174]
0x1800d9030  mov     [rcx+10h], eax
0x1800d9033  mov     rcx, [rbx]
0x1800d9036  mov     eax, [rbp+7E0h+var_178]
0x1800d903c  mov     [rcx+14h], eax
0x1800d903f  add     rbx, 8
0x1800d9043  lea     r9, [rbp+7E0h+var_848]
0x1800d9047  mov     r8, rbx
0x1800d904a  lea     rdx, [rbp+7E0h+var_830]
0x1800d904e  lea     rcx, [rbp+7E0h+var_170]
0x1800d9055  call    ??$emplace@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@?$_Tree@V?$_Tmap_traits@PEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@U?$less@PEBUFeature@CCompositionDatabase@@@std@@V?$allocator@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@std@@@std@@@std@@_N@1@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@Z; std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &)
0x1800d905a  cmp     [rbp+7E0h+var_1F7], sil
0x1800d9061  jz      short loc_1800D9070
0x1800d9063  lea     rdx, [rbp+7E0h+var_7D8]
0x1800d9067  lea     rcx, [rbp+7E0h+var_1B8]
0x1800d906e  jmp     short loc_1800D9084
0x1800d9070  cmp     [rbp+7E0h+var_1F8], sil
0x1800d9077  jz      short loc_1800D9090
0x1800d9079  lea     rdx, [rbp+7E0h+var_7E8]
0x1800d907d  lea     rcx, [rbp+7E0h+var_188]
0x1800d9084  lea     r9, [rbp+7E0h+var_848]
0x1800d9088  mov     r8, rbx
0x1800d908b  call    ??$emplace@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@?$_Tree@V?$_Tmap_traits@PEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@U?$less@PEBUFeature@CCompositionDatabase@@@std@@V?$allocator@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@std@@@std@@@std@@_N@1@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@Z; std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &)
0x1800d9090  lea     rcx, [rsp+8E0h+var_868]
0x1800d9095  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800d909a  mov     rax, [rsp+8E0h+var_868]
0x1800d909f  jmp     loc_1800D8FC4
0x1800d90a4  mov     [rbp+7E0h+var_120], edi
0x1800d90aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d90b1  test    rcx, rcx
0x1800d90b4  jz      short loc_1800D9109
0x1800d90b6  lea     rax, [rbx+18h]
0x1800d90ba  mov     [rsp+8E0h+var_8C0], rax
0x1800d90bf  lea     r9, aFailedToEvalua_1; "Failed to evaluate deferred update; ski"...
0x1800d90c6  mov     esi, 3
0x1800d90cb  mov     r8d, esi
0x1800d90ce  xor     edx, edx
0x1800d90d0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800d90d5  lea     rax, [rbp+7E0h+var_120]
0x1800d90dc  mov     qword ptr [rbp+7E0h+var_680], rax
0x1800d90e3  lea     rax, [rbp+7E0h+var_680]
0x1800d90ea  mov     [rsp+8E0h+var_8C0], rax; int
0x1800d90ef  lea     r9, asc_1801CAFB4; ": {}"
0x1800d90f6  mov     r8d, esi
0x1800d90f9  mov     dl, 1
0x1800d90fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d9102  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d9107  xor     esi, esi
0x1800d9109  mov     edx, 124Fh; void *
0x1800d910e  lea     r8, aOnecoreBaseSer_14; "onecore\\base\\servicing\\arbiter\\cupd"...
0x1800d9115  mov     r9d, edi; char *
0x1800d9118  mov     rcx, [rbp+7E8h]; this
  ... truncated ...
```
