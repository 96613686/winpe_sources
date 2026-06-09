# CUpdateEvaluator::ServiceOrUpgradeOS(CCompositionDatabase const *,CActionListCreator *)

- ea: `0x18012eafc`
- end: `0x180132efe`
- name: `?ServiceOrUpgradeOS@CUpdateEvaluator@@AEAAJPEBVCCompositionDatabase@@PEAVCActionListCreator@@@Z`
- size: `17410`
- prototype: `__int64 __fastcall(CUpdateEvaluator *__hidden this, const struct CCompositionDatabase *, struct CActionListCreator *)`
- caller_count: `2`
- callee_count: `100`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180129d38`
- `0x18012a9c4`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x180006934`
- `0x18000697c`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000b7a4`
- `0x18000c4c4`
- `0x18000d2fc`
- `0x180012430`
- `0x18001270c`
- `0x180012770`
- `0x180012a30`
- `0x180012fe4`
- `0x1800143a4`
- `0x180016014`
- `0x1800192f8`
- `0x180020254`
- `0x180020324`
- `0x180023384`
- `0x18002374c`
- `0x180023b20`
- `0x1800285c4`
- `0x1800369dc`
- `0x18008b38c`
- `0x18009af9c`
- `0x18009b848`
- `0x1800a71c0`
- `0x1800a76dc`
- `0x1800a7974`
- `0x1800a79b4`
- `0x1800a7ba8`
- `0x1800bd2a8`
- `0x1800bdd54`
- `0x1800bddd4`
- `0x1800bde54`
- `0x1800beb90`
- `0x1800bee74`
- `0x1800c9660`
- `0x1800ca3fc`
- `0x1800cbafc`
- `0x1800cbb3c`
- `0x1800ce5b4`
- `0x1800d1ee4`
- `0x1800d249c`
- `0x1800d2b2c`
- `0x1800d2bc0`
- `0x1800d33cc`
- `0x1800d3818`

## string_xrefs

- `0x180132db6`: `SystemManifest`
- `0x18012fb69`: `HotPatchReadiness`
- `0x1801302e6`: `HotPatchReadiness`
- `0x18012f053`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18012f13a`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18012fd95`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180130a3f`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180130acd`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180130c0e`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180130dce`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180131092`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1801312c8`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18013164f`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18013194b`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180131c0d`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180131e6b`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x1801325fb`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18013266d`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180132713`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180132a36`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180132ae1`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x180132cf6`: `onecore\base\servicing\arbiter\cupdateevaluator.cpp`
- `0x18013229e`: `Failed adding feature for token updates`
- `0x18013262b`: `Failed adding feature for token updates`
- `0x1801329e9`: `Failed adding feature for token updates`
- `0x180130678`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x18013074b`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x180130ec9`: `Failed evaluation of install feature conditional FMID: {0}, Feature: {1}`
- `0x180131dc3`: `Cannot remove required feature : {0}`
- `0x18012ec0a`: `Removing unused language: {0} from satellite consideration`
- `0x18012eb47`: `arbiter: Evaluating features for installation`
- `0x18012f004`: `Failed to evaluate deferred update; skipping: {0}`
- `0x18012eea6`: `Failed to get deferred updates`
- `0x18012f25e`: `install`
- `0x18012f24e`: `repair`
- `0x18012f5bd`: `No installed features to update in Group {0}; evaluating features for conditional install`
- `0x18012f7da`: `Feature added due to standalone compDB: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1801305ef`: `Feature added for processing because it's already installed: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130390`: `Feature added due to repair conditional: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130c8b`: `Failed evaluation of repair feature conditional FMID: {0}, Feature: {1}`
- `0x18013039e`: `Feature not needed for repair: Group: {0}, FMID: {1}, Feature: {2}`
- `0x18012faae`: `Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130d0e`: `Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1801304de`: `Feature added due to cumulative update or reoffer: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130519`: `Feature added due to safe OS dynamic update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130989`: `Failed evaluation of remove feature conditional FMID: {0}, Feature: {1}`
- `0x18012fe64`: `Feature removed due to conditional: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130096`: `Feature (LanguagePack) removed because it was unused: Group: {0}, FMID: {1}, Feature: {2}`
- `0x18013015e`: `Not applicable Group: {0}, FMID: {1}, Feature: {2} as newer MSIX application is already installed`
- `0x1801300fd`: `Feature removed due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180130648`: `Feature added due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180131280`: `Unable to create feature modification request`
- `0x1801318fe`: `Unable to create feature modification request`
- `0x180131bc0`: `Unable to create feature modification request`
- `0x18013189c`: `Required feature not available for install: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180131837`: `Feature will not be removed due to dependency: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1801321dc`: `Feature modified due to deferred update: Group: {0}, FMID: {1}, Feature: {2}`
- `0x1801325bc`: `Failed adding InstallPackage actions for feature: Group: {0}, FMID: {1}, Feature: {2}`
- `0x180132887`: `Feature removed due to device state: {}`
- `0x180132a92`: `Failed adding RemoveFeature: Feature: {}`
- `0x180132dee`: `Failed adding product update: Name {0}, Version {1}`

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
  const struct std::nothrow_t *v35; // rdx
  int NameValuePairValue; // eax
  __int64 v37; // r9
  __int64 v38; // rdx
  const struct std::nothrow_t *v39; // rdx
  _QWORD *v40; // r15
  const wchar_t *const *v41; // r12
  struct CCompositionDatabase::Feature *v42; // r14
  int v43; // edx
  bool v44; // zf
  __int64 *v45; // rbx
  __int64 v46; // r8
  char v47; // cl
  unsigned int v48; // eax
  struct CCompositionDatabase::ConditionSet *v49; // rdx
  const wchar_t *v50; // rax
  __int64 v51; // rax
  char v52; // cl
  wchar_t **v53; // rdi
  wchar_t **v54; // rsi
  wchar_t *v55; // r14
  __int64 v56; // r12
  wchar_t *v57; // r15
  int v58; // eax
  __int64 v59; // rcx
  unsigned int v60; // eax
  int v61; // eax
  int v62; // eax
  __int64 v63; // rdi
  __int64 v64; // rsi
  const wchar_t *const **v65; // rdi
  const wchar_t *const **v66; // rsi
  CCompositionDatabase *v67; // r12
  const struct CCompositionDatabase::Feature *v68; // rcx
  bool v69; // r15
  __int64 v70; // rbx
  struct CUpdateEvaluator::FeatureGroup *FeatureGroupOnDevice; // rax
  __int64 v72; // rdx
  wchar_t *v73; // rcx
  bool v74; // zf
  struct CCompositionDatabase::Feature *v75; // rdi
  char v76; // r12
  bool v77; // r14
  int QualifiedFeatureId; // eax
  __int64 v79; // rbx
  const char *v80; // rcx
  const wchar_t *const *v81; // rdx
  char *v82; // r9
  _QWORD *v83; // r11
  const struct CCompositionDatabase::Feature *v84; // r10
  const struct CCompositionDatabase::Feature *v85; // rax
  wchar_t *v86; // rax
  char v87; // cl
  bool v88; // zf
  int v89; // eax
  const char *v90; // rcx
  __int64 v91; // rbx
  __int64 v92; // rax
  int v93; // ecx
  int v94; // ecx
  unsigned int v95; // eax
  int v96; // ecx
  char v97; // cl
  struct CCompositionDatabase::ConditionSet *v98; // rdx
  struct CCompositionDatabase::ConditionSet *v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rdx
  struct CCompositionDatabase::ConditionSet *v102; // rdx
  const wchar_t *const *v103; // rdx
  char *v104; // r8
  char *v105; // r9
  const char *v106; // rcx
  __int64 v107; // rax
  const char *v108; // rcx
  __int64 v109; // rcx
  __int128 v110; // xmm0
  __int64 v111; // rax
  __int64 v112; // rax
  struct CCompositionDatabase::ConditionSet *v113; // rdx
  const wchar_t *const *v114; // r12
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rdx
  struct CCompositionDatabase::ConditionSet *v118; // rdx
  __int64 v119; // rdx
  __int64 v120; // rdx
  char v121; // al
  int v122; // eax
  const struct std::nothrow_t *v123; // rdx
  bool v124; // r9
  const wchar_t *v125; // rbx
  wchar_t *v126; // r14
  const struct CDeviceInfo::Package *AppMainPackageFromInstalledFeature; // r14
  bool IsStubAppFeatureInstalled; // al
  __int64 v129; // r8
  __int64 v130; // rcx
  __int64 v131; // rdx
  const struct CDeviceInfo::Package *UUPPackageFromInstalledFeature; // rax
  unsigned int v133; // ecx
  unsigned int v134; // ecx
  unsigned int v135; // ecx
  unsigned int v136; // ecx
  unsigned int v137; // ecx
  bool v138; // zf
  unsigned int v139; // ecx
  unsigned int v140; // ecx
  unsigned int v141; // ecx
  unsigned int v142; // ecx
  char *v143; // r8
  char *v144; // rdx
  char *v145; // r9
  const char *v146; // rcx
  __int64 v147; // rax
  char v148; // cl
  struct CCompositionDatabase::ConditionSet *v149; // rdx
  struct CCompositionDatabase::ConditionSet *v150; // rdx
  const wchar_t *const *v151; // rbx
  __int64 v152; // rdx
  __int64 v153; // rdx
  __int64 v154; // rdx
  __int64 v155; // rdx
  __int64 v156; // rdx
  __int64 v157; // rdx
  __int64 v158; // rdx
  __int64 v159; // rdx
  __int64 v160; // rdx
  __int64 v161; // rdx
  __int64 v162; // rdx
  __int64 v163; // rdx
  unsigned __int64 v164; // r9
  __int64 v165; // rdx
  const struct std::nothrow_t *v166; // rdx
  __int64 v167; // rdx
  __int64 v168; // rdx
  __int64 v169; // rdx
  __int64 v170; // rdx
  __int64 v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // rdx
  __int64 v174; // rdx
  __int64 v175; // rdx
  int FeatureDependencyClosure; // eax
  __int64 v177; // rdx
  const struct CCompositionDatabase::Feature **v178; // rbx
  const struct CCompositionDatabase::Feature **v179; // r14
  _QWORD *v180; // r15
  const wchar_t *const **v181; // r12
  const wchar_t *const *v182; // rdi
  struct CUpdateEvaluator::Feature *FeatureOnDevice; // rax
  __int64 v184; // rdx
  __int64 v185; // rdx
  __int64 v186; // rdx
  struct CCompositionDatabase::ConditionSet *v187; // rdx
  __int64 v188; // rcx
  _QWORD *v189; // rbx
  _QWORD *v190; // r14
  _QWORD *v191; // rdx
  int v192; // eax
  char v193; // r14
  __int64 v194; // rdx
  __int64 *v195; // rdi
  __int64 *v196; // rbx
  const wchar_t *const **v197; // rax
  const struct CCompositionDatabase::Feature *v198; // rbx
  _BYTE *v199; // rdi
  __int64 v200; // rax
  __int64 v201; // rdx
  __int64 v202; // rdx
  __int64 v203; // rdx
  __int64 v204; // rbx
  const struct CCompositionDatabase::Feature **v205; // rdi
  const struct CCompositionDatabase::Feature **v206; // r12
  const struct CCompositionDatabase::Feature *v207; // r15
  int updated; // r14d
  const struct CCompositionDatabase::Feature *v209; // rax
  __int64 v210; // rdx
  const struct std::nothrow_t *v211; // rdx
  __int64 v212; // rdx
  _QWORD *v213; // rdi
  _QWORD *v214; // rbx
  __int64 v215; // r14
  __int64 v216; // rdx
  const struct std::nothrow_t *v217; // rdx
  int v218; // edx
  int v219; // r8d
  const struct CCompositionDatabase::Feature *v220; // rax
  __int64 v221; // rcx
  const struct CCompositionDatabase::Feature *v222; // r8
  const struct CCompositionDatabase::Feature *v223; // r8
  CActionListCreator *v224; // r15
  int v225; // eax
  __int64 v226; // rdx
  struct CCompositionDatabase::Feature *v227; // rcx
  const wchar_t *const **v228; // rdx
  const wchar_t **v229; // rbx
  char v230; // r12
  __int64 v231; // rax
  _QWORD *v232; // rcx
  struct CUpdateEvaluator::Feature *FeatureStateOnDevice; // rdi
  __int64 v234; // rax
  int v235; // r15d
  char v236; // r12
  _QWORD *v237; // r14
  _QWORD *v238; // r12
  const wchar_t *v239; // rdx
  _QWORD *v240; // rcx
  __int64 v241; // rax
  int v242; // r14d
  __int64 v243; // rdx
  __int64 v244; // rdx
  struct CUpdateEvaluator::Package *PackageInAnyGroup; // rax
  __int64 v246; // r14
  __int64 k; // rbx
  const wchar_t *v248; // rdx
  struct CUpdateEvaluator::Package *v249; // rax
  unsigned int v250; // eax
  int v251; // ecx
  const wchar_t *const **v252; // rdi
  const struct CCompositionDatabase::Feature *v253; // rbx
  __int64 v254; // r8
  __int64 v255; // rax
  __int64 v256; // r14
  __int64 m; // rbx
  const wchar_t *v258; // rdx
  int v259; // edx
  int v260; // eax
  int v261; // edx
  int v262; // eax
  __int64 v263; // rdx
  __int64 v264; // rdx
  __int64 v265; // rdx
  __int64 v266; // rdx
  struct CUpdateEvaluator::Package *v267; // rax
  const wchar_t *const **v268; // rax
  const struct CCompositionDatabase::Feature *v269; // rbx
  __int64 v270; // rdx
  __int64 v271; // rax
  unsigned __int64 v272; // xmm6_8
  __int64 v273; // rax
  const struct std::nothrow_t *v274; // rdx
  __int64 v275; // rdx
  __int64 v276; // rdx
  __int64 v277; // rdx
  __int64 v278; // rdx
  __int64 v279; // rdx
  __int64 v280; // rdx
  const struct std::nothrow_t *v281; // rdx
  __int64 v282; // rdx
  __int64 v283; // rdx
  const struct std::nothrow_t *v284; // rdx
  _QWORD *v285; // rbx
  int v286; // ecx
  int v287; // eax
  __int64 v288; // rdx
  const wchar_t *v289; // rax
  struct ActionList::Product **v290; // rbx
  struct ActionList::Product **v291; // r14
  __int64 v292; // rdx
  int v293; // eax
  __int64 v294; // rdx
  const wchar_t *v296; // rax
  __int64 v297; // rdx
  const struct std::nothrow_t *v298; // rdx
  int **v299; // [rsp+28h] [rbp-E0h]
  int *v300; // [rsp+28h] [rbp-E0h]
  bool v301[8]; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *const *v302; // [rsp+60h] [rbp-A8h] BYREF
  struct CCompositionDatabase::Feature *v303; // [rsp+68h] [rbp-A0h] BYREF
  const struct CCompositionDatabase::Feature *n; // [rsp+70h] [rbp-98h] BYREF
  void *Buf1; // [rsp+78h] [rbp-90h] BYREF
  __int64 v306; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t *const **v307; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v308; // [rsp+90h] [rbp-78h] BYREF
  CCompositionDatabase *v309; // [rsp+98h] [rbp-70h]
  struct CCompositionDatabase::Feature *v310; // [rsp+A0h] [rbp-68h] BYREF
  CActionListCreator *v311; // [rsp+A8h] [rbp-60h]
  wchar_t *v312; // [rsp+B0h] [rbp-58h]
  __int128 v313; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *v315; // [rsp+D0h] [rbp-38h] BYREF
  struct CCompositionDatabase::Feature *v316; // [rsp+D8h] [rbp-30h]
  struct CCompositionDatabase::Feature *v317; // [rsp+E0h] [rbp-28h]
  _QWORD v318[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v319; // [rsp+F8h] [rbp-10h]
  _QWORD v320[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v321[2]; // [rsp+110h] [rbp+8h] BYREF
  struct CCompositionDatabase::Feature *v322; // [rsp+120h] [rbp+18h]
  _BYTE v323[16]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v324; // [rsp+138h] [rbp+30h] BYREF
  __int64 v325; // [rsp+148h] [rbp+40h]
  int v326[2]; // [rsp+150h] [rbp+48h] BYREF
  int v327[2]; // [rsp+158h] [rbp+50h] BYREF
  int *v328; // [rsp+160h] [rbp+58h] BYREF
  int v329[2]; // [rsp+168h] [rbp+60h] BYREF
  int *v330; // [rsp+170h] [rbp+68h] BYREF
  int v331[2]; // [rsp+178h] [rbp+70h] BYREF
  int *v332; // [rsp+180h] [rbp+78h]
  int v333[2]; // [rsp+188h] [rbp+80h] BYREF
  int *v334; // [rsp+190h] [rbp+88h]
  int v335[2]; // [rsp+198h] [rbp+90h] BYREF
  int *v336; // [rsp+1A0h] [rbp+98h] BYREF
  int v337[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  const wchar_t *const *v338; // [rsp+1B0h] [rbp+A8h]
  int *v339; // [rsp+1B8h] [rbp+B0h]
  int v340[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v341[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  int *v342; // [rsp+1D0h] [rbp+C8h]
  int v343[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  int *v344; // [rsp+1E0h] [rbp+D8h] BYREF
  int *v345; // [rsp+1E8h] [rbp+E0h] BYREF
  int v346[2]; // [rsp+1F0h] [rbp+E8h] BYREF
  int *v347; // [rsp+1F8h] [rbp+F0h] BYREF
  int *v348; // [rsp+200h] [rbp+F8h] BYREF
  int v349[2]; // [rsp+208h] [rbp+100h] BYREF
  int *v350; // [rsp+210h] [rbp+108h] BYREF
  int *v351; // [rsp+218h] [rbp+110h] BYREF
  int v352[2]; // [rsp+220h] [rbp+118h] BYREF
  int *v353; // [rsp+228h] [rbp+120h] BYREF
  int *v354; // [rsp+230h] [rbp+128h] BYREF
  int *v355; // [rsp+238h] [rbp+130h] BYREF
  int *v356; // [rsp+240h] [rbp+138h] BYREF
  int v357[2]; // [rsp+248h] [rbp+140h] BYREF
  int *v358; // [rsp+250h] [rbp+148h] BYREF
  const wchar_t *v359; // [rsp+258h] [rbp+150h] BYREF
  int *v360; // [rsp+260h] [rbp+158h] BYREF
  int v361[2]; // [rsp+268h] [rbp+160h] BYREF
  int v362[2]; // [rsp+270h] [rbp+168h] BYREF
  const wchar_t *v363; // [rsp+278h] [rbp+170h] BYREF
  int *v364; // [rsp+280h] [rbp+178h] BYREF
  int *v365; // [rsp+288h] [rbp+180h] BYREF
  int *v366; // [rsp+290h] [rbp+188h] BYREF
  int *v367; // [rsp+298h] [rbp+190h] BYREF
  int v368[2]; // [rsp+2A0h] [rbp+198h] BYREF
  int *v369; // [rsp+2A8h] [rbp+1A0h] BYREF
  int *v370; // [rsp+2B0h] [rbp+1A8h] BYREF
  int *v371; // [rsp+2B8h] [rbp+1B0h] BYREF
  int *v372; // [rsp+2C0h] [rbp+1B8h] BYREF
  int *v373; // [rsp+2C8h] [rbp+1C0h] BYREF
  int *v374; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v375[16]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v376[16]; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int128 v377; // [rsp+2F8h] [rbp+1F0h]
  _BYTE v378[48]; // [rsp+318h] [rbp+210h] BYREF
  __int64 v379; // [rsp+348h] [rbp+240h]
  __int128 v380; // [rsp+358h] [rbp+250h] BYREF
  __int64 v381; // [rsp+368h] [rbp+260h]
  __int128 v382; // [rsp+370h] [rbp+268h] BYREF
  __int64 v383; // [rsp+380h] [rbp+278h]
  _BYTE v384[32]; // [rsp+388h] [rbp+280h] BYREF
  char v385[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  char v386[16]; // [rsp+3B8h] [rbp+2B0h] BYREF
  char v387[16]; // [rsp+3C8h] [rbp+2C0h] BYREF
  char v388[16]; // [rsp+3D8h] [rbp+2D0h] BYREF
  char v389[16]; // [rsp+3E8h] [rbp+2E0h] BYREF
  char v390[16]; // [rsp+3F8h] [rbp+2F0h] BYREF
  char v391[16]; // [rsp+408h] [rbp+300h] BYREF
  char v392[16]; // [rsp+418h] [rbp+310h] BYREF
  char v393[16]; // [rsp+428h] [rbp+320h] BYREF
  char v394[16]; // [rsp+438h] [rbp+330h] BYREF
  char v395[16]; // [rsp+448h] [rbp+340h] BYREF
  char v396[16]; // [rsp+458h] [rbp+350h] BYREF
  char v397[16]; // [rsp+468h] [rbp+360h] BYREF
  char v398[16]; // [rsp+478h] [rbp+370h] BYREF
  char v399[16]; // [rsp+488h] [rbp+380h] BYREF
  char v400[24]; // [rsp+498h] [rbp+390h] BYREF
  char v401[24]; // [rsp+4B0h] [rbp+3A8h] BYREF
  char v402[24]; // [rsp+4C8h] [rbp+3C0h] BYREF
  const wchar_t *v403; // [rsp+4E0h] [rbp+3D8h] BYREF
  _OWORD v404[3]; // [rsp+4E8h] [rbp+3E0h] BYREF
  __int128 v405; // [rsp+518h] [rbp+410h]
  __int128 v406; // [rsp+528h] [rbp+420h]
  char v407[64]; // [rsp+538h] [rbp+430h] BYREF
  char v408[16]; // [rsp+578h] [rbp+470h] BYREF
  char v409[64]; // [rsp+588h] [rbp+480h] BYREF
  char v410[64]; // [rsp+5C8h] [rbp+4C0h] BYREF
  char v411[64]; // [rsp+608h] [rbp+500h] BYREF
  __int128 v412; // [rsp+648h] [rbp+540h]
  __int64 v413; // [rsp+658h] [rbp+550h]
  __int64 v414; // [rsp+660h] [rbp+558h]
  char v415[64]; // [rsp+668h] [rbp+560h] BYREF
  __int64 v416; // [rsp+6A8h] [rbp+5A0h]
  __int64 v417; // [rsp+6B8h] [rbp+5B0h] BYREF
  const struct CCompositionDatabase::Feature *v418; // [rsp+6C0h] [rbp+5B8h] BYREF
  __int64 v419; // [rsp+6C8h] [rbp+5C0h]
  __int64 v420[2]; // [rsp+6D0h] [rbp+5C8h] BYREF
  _QWORD v421[2]; // [rsp+6E0h] [rbp+5D8h] BYREF
  bool v422; // [rsp+6F0h] [rbp+5E8h] BYREF
  bool v423; // [rsp+6F1h] [rbp+5E9h] BYREF
  __int128 v424; // [rsp+6F8h] [rbp+5F0h] BYREF
  _QWORD *v425; // [rsp+708h] [rbp+600h]
  wchar_t *Str; // [rsp+710h] [rbp+608h] BYREF
  __int128 v427; // [rsp+718h] [rbp+610h] BYREF
  __int64 v428; // [rsp+728h] [rbp+620h]
  _QWORD v429[2]; // [rsp+730h] [rbp+628h] BYREF
  _QWORD v430[2]; // [rsp+740h] [rbp+638h] BYREF
  __int64 v431; // [rsp+750h] [rbp+648h] BYREF
  __int64 v432; // [rsp+758h] [rbp+650h]
  _QWORD v433[2]; // [rsp+760h] [rbp+658h] BYREF
  int v434; // [rsp+770h] [rbp+668h] BYREF
  int v435; // [rsp+774h] [rbp+66Ch] BYREF
  _QWORD v436[2]; // [rsp+778h] [rbp+670h] BYREF
  int v437; // [rsp+788h] [rbp+680h] BYREF
  int v438; // [rsp+78Ch] [rbp+684h] BYREF
  int v439; // [rsp+790h] [rbp+688h] BYREF
  int v440; // [rsp+794h] [rbp+68Ch] BYREF
  int v441; // [rsp+798h] [rbp+690h] BYREF
  int v442; // [rsp+79Ch] [rbp+694h] BYREF
  int v443; // [rsp+7A0h] [rbp+698h] BYREF
  int v444; // [rsp+7A4h] [rbp+69Ch] BYREF
  int v445; // [rsp+7A8h] [rbp+6A0h] BYREF
  int v446; // [rsp+7ACh] [rbp+6A4h] BYREF
  int v447; // [rsp+7B0h] [rbp+6A8h] BYREF
  int v448; // [rsp+7B4h] [rbp+6ACh] BYREF
  int v449; // [rsp+7B8h] [rbp+6B0h] BYREF
  int v450; // [rsp+7BCh] [rbp+6B4h] BYREF
  int v451; // [rsp+7C0h] [rbp+6B8h] BYREF
  int v452; // [rsp+7C4h] [rbp+6BCh] BYREF
  int v453; // [rsp+7C8h] [rbp+6C0h] BYREF
  int v454; // [rsp+7CCh] [rbp+6C4h] BYREF
  int v455; // [rsp+7D0h] [rbp+6C8h] BYREF
  int v456; // [rsp+7D4h] [rbp+6CCh] BYREF
  int v457; // [rsp+7D8h] [rbp+6D0h] BYREF
  int v458; // [rsp+7DCh] [rbp+6D4h] BYREF
  int v459; // [rsp+7E0h] [rbp+6D8h] BYREF
  int v460; // [rsp+7E4h] [rbp+6DCh] BYREF
  int v461; // [rsp+7E8h] [rbp+6E0h] BYREF
  int v462; // [rsp+7ECh] [rbp+6E4h] BYREF
  int v463; // [rsp+7F0h] [rbp+6E8h] BYREF
  int v464; // [rsp+7F4h] [rbp+6ECh] BYREF
  int v465; // [rsp+7F8h] [rbp+6F0h] BYREF
  int v466; // [rsp+7FCh] [rbp+6F4h] BYREF
  int v467; // [rsp+800h] [rbp+6F8h] BYREF
  int v468; // [rsp+804h] [rbp+6FCh] BYREF
  int v469; // [rsp+808h] [rbp+700h] BYREF
  int v470; // [rsp+80Ch] [rbp+704h] BYREF
  int v471; // [rsp+810h] [rbp+708h] BYREF
  int v472; // [rsp+814h] [rbp+70Ch] BYREF
  int v473; // [rsp+818h] [rbp+710h] BYREF
  int v474; // [rsp+81Ch] [rbp+714h] BYREF
  int v475; // [rsp+820h] [rbp+718h] BYREF
  int v476; // [rsp+824h] [rbp+71Ch] BYREF
  int v477; // [rsp+828h] [rbp+720h] BYREF
  int v478; // [rsp+82Ch] [rbp+724h] BYREF
  int v479; // [rsp+830h] [rbp+728h] BYREF
  int v480; // [rsp+834h] [rbp+72Ch] BYREF
  int v481; // [rsp+838h] [rbp+730h] BYREF
  int v482; // [rsp+83Ch] [rbp+734h] BYREF
  __int128 v483; // [rsp+840h] [rbp+738h] BYREF
  __int64 v484; // [rsp+850h] [rbp+748h]
  __int64 v485[2]; // [rsp+858h] [rbp+750h] BYREF
  __int128 v486; // [rsp+868h] [rbp+760h] BYREF
  __int64 v487; // [rsp+878h] [rbp+770h]
  __int128 v488; // [rsp+880h] [rbp+778h] BYREF
  __int64 v489; // [rsp+890h] [rbp+788h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]

  v379 = -2;
  v311 = a3;
  v309 = a2;
  LogAdapter::TraceInfo<>("arbiter: Evaluating features for installation");
  v301[4] = *(_BYTE *)(*((_QWORD *)this + 12) + 304LL);
  v432 = 0;
  v4 = operator new(0x40u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v431 = (__int64)v4;
  std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(
    v485,
    *((_QWORD *)this + 12) + 176LL);
  v6 = **(__int64 ***)(*((_QWORD *)this + 12) + 160LL);
  while ( !*((_BYTE *)v6 + 25) )
  {
    v301[0] = 1;
    if ( !*((_BYTE *)this + 121)
      || ((unsigned __int64)v6[7] <= 7 ? (v7 = (const wchar_t *)(v6 + 4)) : (v7 = (const wchar_t *)v6[4]),
          CDeviceInfo::MatchNameValueSetPair(*((CDeviceInfo **)this + 12), L"UserProfileLanguage", v7, v5, v301),
          v301[0]) )
    {
      v10 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              &v431,
              v400,
              v6 + 4);
      v11 = *(_OWORD *)v10;
      if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                               v12,
                               *(_QWORD *)(v10 + 16),
                               v6 + 4) )
      {
        if ( v432 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v13 = v431;
        v318[1] = &v431;
        v319 = 0;
        v319 = (__int64 *)operator new(0x40u);
        std::wstring::wstring(v319 + 4, v6 + 4);
        *v319 = v13;
        v319[1] = v13;
        v319[2] = v13;
        *((_BYTE *)v319 + 24) = 0;
        *((_BYTE *)v319 + 25) = 0;
        v14 = v319;
        v319 = 0;
        v313 = v11;
        std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v431, &v313, v14);
      }
    }
    else
    {
      LogAdapter::TraceAtLevel<std::wstring>(1, "Removing unused language: {0} from satellite consideration", v6 + 4);
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
  v430[0] = 0;
  v430[1] = 0;
  v16 = operator new(0x48u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  v430[0] = v16;
  v433[0] = 0;
  v433[1] = 0;
  v17 = operator new(0x30u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  v433[0] = v17;
  v429[0] = 0;
  v429[1] = 0;
  v18 = operator new(0x30u);
  *v18 = v18;
  v18[1] = v18;
  v18[2] = v18;
  *((_WORD *)v18 + 12) = 257;
  v429[0] = v18;
  v436[0] = 0;
  v436[1] = 0;
  v19 = operator new(0x30u);
  *v19 = v19;
  v19[1] = v19;
  v19[2] = v19;
  *((_WORD *)v19 + 12) = 257;
  v436[0] = v19;
  v417 = 0;
  v418 = 0;
  v419 = 0;
  v20 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v20 = v20;
  *(_QWORD *)(v20 + 8) = v20;
  *(_QWORD *)(v20 + 16) = v20;
  *(_WORD *)(v20 + 24) = 257;
  v418 = (const struct CCompositionDatabase::Feature *)v20;
  v420[0] = 0;
  v420[1] = 0;
  v21 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v21 = v21;
  *(_QWORD *)(v21 + 8) = v21;
  *(_QWORD *)(v21 + 16) = v21;
  *(_WORD *)(v21 + 24) = 257;
  v420[0] = v21;
  v421[0] = 0;
  v421[1] = 0;
  v22 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v22 = v22;
  *(_QWORD *)(v22 + 8) = v22;
  *(_QWORD *)(v22 + 16) = v22;
  *(_WORD *)(v22 + 24) = 257;
  v421[0] = v22;
  DeferredUpdateRequests = CUpdateEvaluator::GetDeferredUpdateRequests(this, v309, v430);
  v24 = DeferredUpdateRequests;
  if ( DeferredUpdateRequests < 0 )
  {
    v454 = DeferredUpdateRequests;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get deferred updates");
      v360 = &v454;
      v299 = &v360;
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
  v27 = *(_QWORD *)v430[0];
  v306 = *(_QWORD *)v430[0];
  while ( !*(_BYTE *)(v27 + 25) )
  {
    v435 = 0;
    v434 = 0;
    v422 = 0;
    v423 = 0;
    v28 = *(struct CUpdateEvaluator::FeatureRequest **)(v27 + 64);
    v310 = v28;
    v29 = CUpdateEvaluator::EvaluateModifyRequest(
            this,
            v28,
            (enum FeatureIntentFlags *)&v435,
            (enum FeatureIntentFlags *)&v434,
            &v422,
            &v423);
    if ( v29 < 0 )
    {
      v453 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to evaluate deferred update; skipping: {0}");
        *(_QWORD *)v361 = &v453;
        v299 = (int **)v361;
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
    *(_DWORD *)(*(_QWORD *)v28 + 16LL) = v435;
    *(_DWORD *)(*(_QWORD *)v28 + 20LL) = v434;
    v30 = (char *)v28 + 8;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v436,
      &v313,
      v30,
      &v310);
    if ( v423 )
    {
      v31 = v321;
      v32 = v429;
    }
    else
    {
      if ( !v422 )
        goto LABEL_33;
      v31 = v320;
      v32 = v433;
    }
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v32,
      v31,
      v30,
      &v310);
LABEL_33:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v306);
    v27 = v306;
  }
  v315 = 0;
  NameValuePairValue = CDeviceInfo::GetNameValuePairValue(
                         *((CDeviceInfo **)this + 12),
                         L"EditionVersion",
                         (const wchar_t **)&v315,
                         0);
  v24 = NameValuePairValue;
  if ( NameValuePairValue < 0 )
  {
    v451 = NameValuePairValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get device OS version");
      *(_QWORD *)v362 = &v451;
      v299 = (int **)v362;
      LOBYTE(v38) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v38,
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
      (int)v299);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
    if ( !v417 )
      goto LABEL_716;
    goto LABEL_715;
  }
  v312 = 0;
  v310 = 0;
  String1 = 0;
  v306 = 0;
  v322 = 0;
  v40 = 0;
  Buf1 = 0;
  v316 = 0;
  v41 = 0;
  v302 = 0;
  v307 = 0;
  v42 = (struct CCompositionDatabase::Feature *)*((_QWORD *)v309 + 5);
  v317 = (struct CCompositionDatabase::Feature *)((char *)v42 + 8 * *((_QWORD *)v309 + 3));
  v43 = 4505604;
  v44 = v42 == v317;
  while ( 2 )
  {
    v303 = v42;
    if ( !v44 )
    {
      v45 = *(__int64 **)(*(_QWORD *)v42 + 48LL);
      n = (const struct CCompositionDatabase::Feature *)&v45[*(_QWORD *)(*(_QWORD *)v42 + 32LL)];
      if ( v45 == (__int64 *)n )
      {
LABEL_98:
        v42 = (struct CCompositionDatabase::Feature *)((char *)v42 + 8);
        v44 = v42 == v317;
        continue;
      }
      while ( 1 )
      {
        v46 = *v45;
        v47 = *(_BYTE *)(*v45 + 368);
        if ( ((v47 - 11) & 0xFA) != 0 || v47 == 16 )
          goto LABEL_97;
        LOBYTE(v37) = 0;
        if ( v47 == 12 )
        {
          v48 = *((_DWORD *)this + 12);
          if ( v48 <= 0x16 )
            LOBYTE(v37) = _bittest(&v43, v48);
        }
        v49 = *(struct CCompositionDatabase::ConditionSet **)v46;
        if ( *(_QWORD *)v46 )
        {
          v50 = L"repair";
        }
        else
        {
          v49 = *(struct CCompositionDatabase::ConditionSet **)(v46 + 8);
          v50 = L"install";
          if ( !v49 )
            v50 = &String2;
        }
        v403 = v50;
        v301[0] = 0;
        if ( v49 )
        {
          if ( (_BYTE)v37 )
          {
            LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
              (unsigned int)"Conditional evaluation skipped for {0}: Group: {1}, FMID: {2}, Feature: {3}",
              (unsigned int)&v403,
              *(_DWORD *)v45 + 72,
              *(_DWORD *)v45 + 64,
              *v45 + 56);
          }
          else
          {
            v29 = CUpdateEvaluator::EvaluateConditional(this, v49, v301);
            if ( v29 < 0 )
            {
              v450 = v29;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of {0} feature conditional FMID: {1}, Feature: {2}",
                  &v403,
                  *v45 + 64,
                  *v45 + 56);
                v364 = &v450;
                v299 = &v364;
                LOBYTE(v72) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v72,
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
                (int)v299);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
              if ( v417 )
                goto LABEL_38;
              goto LABEL_39;
            }
            if ( !v301[0] )
            {
              LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
                (unsigned int)"Feature not needed for {0}: Group: {1}, FMID: {2}, Feature: {3}",
                (unsigned int)&v403,
                *(_DWORD *)v45 + 72,
                *(_DWORD *)v45 + 64,
                *v45 + 56);
              goto LABEL_96;
            }
          }
        }
        v51 = *v45;
        v52 = *(_BYTE *)(*v45 + 368);
        if ( v52 == 11 )
        {
          v53 = *(wchar_t ***)(v51 + 120);
          v54 = &v53[*(_QWORD *)(v51 + 104)];
          if ( v53 != v54 )
          {
            v55 = String1;
            v56 = v306;
            v57 = v312;
            v37 = 0;
            do
            {
              if ( !v57
                || (v58 = CompareVersionString(*((_QWORD *)v57 + 2), *((_QWORD *)*v53 + 2), v46, 0), v37 = 0, v58 < 0) )
              {
                v57 = *v53;
                v310 = (struct CCompositionDatabase::Feature *)*v45;
              }
              if ( *((_DWORD *)*v53 + 80) == 16 )
              {
                if ( (v59 = *((_QWORD *)this + 12), *(_BYTE *)(v59 + 236))
                  || *(_QWORD *)(v59 + 240) != *(_QWORD *)(v59 + 248)
                  || !v315
                  || (v60 = *((_DWORD *)this + 12), v60 <= 0x16) && (v46 = 4505600, _bittest((const int *)&v46, v60))
                  || (v61 = CompareVersionString(v315, *((_QWORD *)*v53 + 3), v46, 0), v37 = 0, v61 < 0) )
                {
                  if ( !v55
                    || (v62 = CompareVersionString(*((_QWORD *)v55 + 2), *((_QWORD *)*v53 + 2), v46, 0), v37 = 0, v62 < 0) )
                  {
                    v322 = (struct CCompositionDatabase::Feature *)v56;
                    v55 = *v53;
                    v56 = *v45;
                  }
                }
              }
              ++v53;
            }
            while ( v53 != v54 );
            v312 = v57;
            v306 = v56;
            String1 = v55;
            v42 = v303;
            v40 = Buf1;
LABEL_78:
            v41 = v302;
          }
        }
        else
        {
          if ( v52 != 12 )
          {
            if ( v52 == 15 )
            {
              v65 = *(const wchar_t *const ***)(v51 + 120);
              v66 = &v65[*(_QWORD *)(v51 + 104)];
              if ( v65 != v66 )
              {
                do
                {
                  if ( !v41 || (int)CompareVersionString(*((_QWORD *)v41 + 2), *((_QWORD *)*v65 + 2), v46, v37) < 0 )
                  {
                    v41 = *v65;
                    v307 = (const wchar_t *const **)*v45;
                  }
                  ++v65;
                }
                while ( v65 != v66 );
                v302 = v41;
                v42 = v303;
              }
            }
            goto LABEL_96;
          }
          v63 = *(_QWORD *)(v51 + 120);
          v64 = v63 + 8LL * *(_QWORD *)(v51 + 104);
          if ( v63 != v64 )
          {
            do
            {
              if ( !v40 || (int)CompareVersionString(v40[2], *(_QWORD *)(*(_QWORD *)v63 + 16LL), v46, v37) < 0 )
              {
                v40 = *(_QWORD **)v63;
                v316 = (struct CCompositionDatabase::Feature *)*v45;
              }
              v63 += 8;
            }
            while ( v63 != v64 );
            Buf1 = v40;
            goto LABEL_78;
          }
        }
LABEL_96:
        v43 = 4505604;
LABEL_97:
        if ( ++v45 == (__int64 *)n )
          goto LABEL_98;
      }
    }
    break;
  }
  v67 = v309;
  v317 = (struct CCompositionDatabase::Feature *)(*((_DWORD *)v309 + 108) & 0x800);
  v68 = (const struct CCompositionDatabase::Feature *)*((_QWORD *)v309 + 5);
  n = v68;
  *(_QWORD *)&v313 = (char *)v68 + 8 * *((_QWORD *)v309 + 3);
  if ( v68 == (const struct CCompositionDatabase::Feature *)v313 )
    goto LABEL_124;
  v69 = 0;
  while ( 2 )
  {
    v70 = *(_QWORD *)v68;
    v302 = (const wchar_t *const *)v70;
    FeatureGroupOnDevice = CUpdateEvaluator::FindFeatureGroupOnDevice(this, *(const wchar_t *const *)v70);
    if ( FeatureGroupOnDevice )
      *((_BYTE *)FeatureGroupOnDevice + 8) = 1;
    else
      LogAdapter::TraceInfo<wchar_t const *>(
        "No installed features to update in Group {0}; evaluating features for conditional install",
        v70);
    v73 = *(wchar_t **)(v70 + 48);
    v321[0] = &v73[4 * *(_QWORD *)(v70 + 32)];
    v74 = v73 == (wchar_t *)v321[0];
    while ( 2 )
    {
      v315 = v73;
      if ( !v74 )
      {
        v75 = *(struct CCompositionDatabase::Feature **)v73;
        v303 = v75;
        v76 = 0;
        v301[2] = 0;
        v77 = 0;
        v301[0] = 0;
        v301[3] = 0;
        QualifiedFeatureId = GetQualifiedFeatureId(v75, &v417);
        v24 = QualifiedFeatureId;
        if ( QualifiedFeatureId < 0 )
        {
          v471 = QualifiedFeatureId;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(_QWORD *)&LogAdapter::g_Logger,
              0,
              3,
              "Failed getting qualified feature Id");
            v342 = &v471;
            LOBYTE(v175) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v175,
              3,
              ": {}");
          }
          goto LABEL_714;
        }
        if ( *((_BYTE *)v75 + 368) == 11 )
        {
          v79 = v306;
          if ( v306 || v310 )
          {
            if ( CDeviceInfo::IsNameValuePairEqual(*((CDeviceInfo **)this + 12), L"WindowsPE", L"1") && v75 != v310 )
            {
              v80 = "Feature baselines not applicable for WinPE: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_116:
              v81 = v302;
LABEL_117:
              v82 = (char *)v75 + 56;
LABEL_118:
              LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v80, v81, (char *)v75 + 64, v82);
LABEL_119:
              v69 = 0;
LABEL_120:
              v73 = v315 + 4;
              v74 = v315 + 4 == (wchar_t *)v321[0];
              continue;
            }
            if ( v322 )
            {
              v86 = v312;
              if ( v75 == v322 )
              {
                if ( (struct CCompositionDatabase::Feature *)v79 == v310 )
                {
                  if ( *((_DWORD *)v312 + 80) == 16 )
                    goto LABEL_135;
                }
                else if ( *((_DWORD *)v312 + 80) != 16 )
                {
                  v80 = "Feature N-1 baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_116;
                }
              }
            }
            else
            {
              v86 = v312;
            }
            if ( v75 != (struct CCompositionDatabase::Feature *)v79 )
            {
              if ( v75 == v310 )
                goto LABEL_135;
LABEL_143:
              v80 = "Feature baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_116;
            }
            if ( (struct CCompositionDatabase::Feature *)v79 != v310 && *((_DWORD *)v86 + 80) == 16 )
              goto LABEL_143;
          }
        }
LABEL_135:
        v87 = *((_BYTE *)v75 + 368);
        if ( v87 == 12 )
        {
          v88 = v75 == v316;
        }
        else
        {
          if ( v87 != 15 )
            goto LABEL_147;
          v88 = v75 == (struct CCompositionDatabase::Feature *)v307;
        }
        if ( !v88 )
        {
LABEL_149:
          v80 = "Feature not applicable: Group: {0}, FMID: {1}, Feature: {2}";
          goto LABEL_116;
        }
LABEL_147:
        v89 = *((_DWORD *)this + 12);
        if ( v89 == 25 && v87 != 25 )
          goto LABEL_149;
        v301[1] = 0;
        if ( v317 )
        {
          v76 = 1;
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            &v418,
            v398,
            &v303);
          v90 = "Feature added due to standalone compDB: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_152:
          v75 = v303;
          goto LABEL_153;
        }
        if ( v89 != 1 && v89 != 19 )
        {
          if ( (v89 == 2 || v89 == 22) && (*((_BYTE *)v75 + 368) == 14 || *((_BYTE *)v75 + 368) == 9) )
          {
            v76 = 1;
            std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
              &v418,
              v390,
              &v303);
            v90 = "Feature added due to default desktop upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_152;
          }
          v95 = *((_DWORD *)this + 12);
          if ( v95 > 0x16 || (v96 = 4505604, !_bittest(&v96, v95)) )
          {
LABEL_181:
            if ( *((_DWORD *)this + 12) == 24 )
            {
              if ( *((_BYTE *)v75 + 368) == 27 )
              {
                v109 = *((_QWORD *)v75 + 7);
                v110 = 0;
                v111 = 0;
                v377 = 0;
                if ( v109 )
                {
                  v112 = -1;
                  do
                    ++v112;
                  while ( *(_WORD *)(v109 + 2 * v112) );
                  *(_QWORD *)&v377 = 2 * v112;
                  *((_QWORD *)&v377 + 1) = 2 * v112 + 2;
                  v111 = v109;
                  v110 = v377;
                }
                v380 = v110;
                v381 = v111;
                if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                        &___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HH__0GJ__0GO__0HC__0GF__0FP__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                                        &v380,
                                        0) )
                  goto LABEL_183;
              }
              if ( *((_BYTE *)v75 + 368) == 12 )
                goto LABEL_183;
            }
            else if ( *((_BYTE *)v75 + 368) != 27 )
            {
LABEL_183:
              if ( CUpdateEvaluator::FindFeatureOnDevice(this, v75) )
              {
                v113 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 6);
                if ( v113 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v113, v301);
                  if ( v24 < 0 )
                  {
                    v442 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v356 = &v442;
                      v299 = &v356;
                      LOBYTE(v158) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v158,
                        3,
                        ": {}");
                    }
                    v117 = 5325;
LABEL_227:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v117,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      (int)v299);
LABEL_714:
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
                    if ( !v417 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v77 = v301[0];
                  v114 = v302;
                  if ( v301[0] )
                  {
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v302,
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      v421,
                      v386,
                      &v303);
                    v75 = v303;
                    v115 = CActionListCreator::DisableFeature(v311, v303);
                    v24 = v115;
                    if ( v115 < 0 )
                    {
                      v443 = v115;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                          (char *)v75 + 72,
                          (char *)v75 + 64,
                          (char *)v75 + 56);
                        *(_QWORD *)v343 = &v443;
                        v299 = (int **)v343;
                        LOBYTE(v116) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v116,
                          3,
                          ": {}");
                      }
                      v117 = 5336;
                      goto LABEL_227;
                    }
                  }
                }
                else
                {
                  v114 = v302;
                }
                v118 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 2);
                if ( v118 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v118, &v301[3]);
                  if ( v24 < 0 )
                  {
                    v441 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of remove feature conditional FMID: {0}, Feature: {1}",
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v354 = &v441;
                      v299 = &v354;
                      LOBYTE(v161) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v161,
                        3,
                        ": {}");
                    }
                    v117 = 5348;
                    goto LABEL_227;
                  }
                  v69 = v301[3];
                  if ( v301[3] )
                  {
                    Buf1 = 0;
                    v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                    if ( v24 < 0 )
                    {
                      v463 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<AutoScz>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed creating pending request for {0}",
                          &v417);
                        v355 = &v463;
                        v299 = &v355;
                        LOBYTE(v159) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v159,
                          3,
                          ": {}");
                      }
                      v160 = 5360;
                      goto LABEL_713;
                    }
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                      v429,
                      v387,
                      &v303,
                      &Buf1);
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v114,
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                  }
                }
                if ( v77 && v69 )
                {
                  v24 = -2146467821;
                  v440 = -2146467821;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Conflicting preload and removal feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                      v114,
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                    v353 = &v440;
                    v299 = &v353;
                    LOBYTE(v119) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v119,
                      3,
                      ": {}");
                  }
                  v120 = 5370;
                  goto LABEL_377;
                }
                if ( !v69 )
                {
                  if ( *((_BYTE *)this + 121) )
                  {
                    v121 = *((_BYTE *)v75 + 368);
                    if ( v121 == 6 || v121 == 13 || v121 == 5 && *(_BYTE *)(*((_QWORD *)this + 12) + 330LL) )
                    {
                      Str = 0;
                      v301[3] = 1;
                      Buf1 = 0;
                      String1 = 0;
                      v122 = SczAllocFromSz(&Str, *((_QWORD *)v75 + 7));
                      v24 = v122;
                      if ( v122 < 0 )
                      {
                        v164 = (unsigned int)v122;
                        v165 = 5390;
LABEL_382:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v165,
                          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                          (const char *)v164,
                          (int)v299);
                        if ( Str )
                        {
                          operator delete(Str - 4, v166);
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
                        v438 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<AutoScz>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed shredding feature ID: {0}",
                            &Str);
                          v351 = &v438;
                          v299 = &v351;
                          LOBYTE(v163) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v163,
                            3,
                            ": {}");
                        }
                        v164 = (unsigned int)v24;
                        v165 = 5394;
                        goto LABEL_382;
                      }
                      v125 = (const wchar_t *)Buf1;
                      if ( Buf1 )
                      {
                        if ( *((_BYTE *)v75 + 368) == 5 )
                        {
                          v126 = String1;
                          if ( wcsicmp(String1, L"Language.TextToSpeech") )
                          {
                            if ( wcsicmp(v126, L"Language.Speech") && wcsicmp(v126, L"Language.LocaleData") )
                              v125 = 0;
                          }
                        }
                        if ( v125 )
                        {
                          CDeviceInfo::MatchNameValueSetPair(
                            *((CDeviceInfo **)this + 12),
                            L"UserProfileLanguage",
                            v125,
                            v124,
                            &v301[3]);
                          v69 = !v301[3];
                        }
                      }
                      if ( Str )
                      {
                        operator delete(Str - 4, v123);
                        Str = 0;
                      }
                      if ( v69 )
                      {
                        Buf1 = 0;
                        v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                        if ( v24 < 0 )
                        {
                          v439 = v24;
                          if ( *(_QWORD *)&LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<AutoScz>(
                              *(_QWORD *)&LogAdapter::g_Logger,
                              0,
                              3,
                              "Failed creating pending request for {0}",
                              &v417);
                            *(_QWORD *)v352 = &v439;
                            v299 = (int **)v352;
                            LOBYTE(v162) = 1;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              *(_QWORD *)&LogAdapter::g_Logger,
                              v162,
                              3,
                              ": {}");
                          }
                          v120 = 5430;
LABEL_377:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v120,
                            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                            (const char *)(unsigned int)v24,
                            (int)v299);
LABEL_384:
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
                          if ( !v417 )
                            goto LABEL_716;
LABEL_715:
                          operator delete((void *)(v417 - 8), v39);
                          v417 = 0;
                          goto LABEL_716;
                        }
                        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                          v429,
                          v388,
                          &v303,
                          &Buf1);
                        LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                          "Feature (LanguagePack) removed because it was unused: Group: {0}, FMID: {1}, Feature: {2}",
                          v114,
                          (char *)v75 + 64,
                          (char *)v75 + 56);
                      }
                    }
                  }
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                  v429,
                  v318,
                  &v303);
                if ( v318[0] != v429[0] )
                {
                  *(_BYTE *)(*(_QWORD *)(v318[0] + 40LL) + 33LL) = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    v420,
                    v389,
                    &v303);
                  v75 = v303;
                  if ( !v69 )
                  {
                    v69 = 1;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
                      (char *)v303 + 72,
                      (char *)v303 + 64,
                      (char *)v303 + 56);
                  }
                }
                if ( *((_BYTE *)v75 + 369) )
                  goto LABEL_119;
                if ( (unsigned __int8)(*((_BYTE *)v75 + 368) - 22) <= 1u )
                {
                  AppMainPackageFromInstalledFeature = CDeviceInfo::GetAppMainPackageFromInstalledFeature(
                                                         *((CDeviceInfo **)this + 12),
                                                         *((const wchar_t *const *)v75 + 7));
                  IsStubAppFeatureInstalled = CDeviceInfo::IsStubAppFeatureInstalled(
                                                *((CDeviceInfo **)this + 12),
                                                *((const wchar_t *const *)v75 + 7));
                  if ( AppMainPackageFromInstalledFeature )
                  {
                    LOBYTE(v129) = IsStubAppFeatureInstalled;
                    if ( !(unsigned __int8)IsPreInstalledAppApplicable(v75, AppMainPackageFromInstalledFeature, v129) )
                    {
                      v82 = (char *)v75 + 56;
                      v81 = v114;
                      v80 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as newer MSIX application is already installed";
                      goto LABEL_118;
                    }
                  }
                }
                if ( *((_BYTE *)v75 + 368) == 24
                  && CDeviceInfo::GetEdgePackageFromInstalledFeature(
                       *((CDeviceInfo **)this + 12),
                       *((const wchar_t *const *)v75 + 7)) )
                {
                  v130 = *((_QWORD *)v75 + 15);
                  v131 = v130 + 8LL * *((_QWORD *)v75 + 13);
                  while ( 1 )
                  {
                    if ( v130 == v131 )
                      goto LABEL_275;
                    if ( *(_DWORD *)(*(_QWORD *)v130 + 320LL) == 17 )
                      break;
                    v130 += 8;
                  }
                  v81 = v114;
                  v80 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as Edge package is not applicable";
                  goto LABEL_117;
                }
LABEL_275:
                if ( *((_BYTE *)v75 + 368) == 25 )
                {
                  UUPPackageFromInstalledFeature = CDeviceInfo::GetUUPPackageFromInstalledFeature(
                                                     *((CDeviceInfo **)this + 12),
                                                     *((const wchar_t *const *)v75 + 7));
                  if ( UUPPackageFromInstalledFeature )
                  {
                    if ( !(unsigned __int8)IsUUPProductApplicable(v75, UUPPackageFromInstalledFeature) )
                    {
                      v81 = v114;
                      v80 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as UUP product is not applicable";
                      goto LABEL_117;
                    }
                  }
                }
                v76 = 1;
                if ( v69 )
                  goto LABEL_154;
                v90 = "Feature added due to default upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_153:
                LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v90, v302, (char *)v75 + 64, (char *)v75 + 56);
LABEL_154:
                v69 = 0;
LABEL_155:
                Buf1 = 0;
                v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                if ( v24 < 0 )
                {
                  v472 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<AutoScz>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed creating pending request for {0}",
                      &v417);
                    v366 = &v472;
                    v299 = &v366;
                    LOBYTE(v174) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v174,
                      3,
                      ": {}");
                  }
                  v101 = 5524;
                  goto LABEL_392;
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                  v433,
                  v378,
                  &v303,
                  &Buf1);
                goto LABEL_157;
              }
              v98 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 1);
              v69 = 0;
              if ( v98 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v98, &v301[2]);
                if ( v24 < 0 )
                {
                  v447 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                    v371 = &v447;
                    v299 = &v371;
                    LOBYTE(v154) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v154,
                      3,
                      ": {}");
                  }
                  v101 = 5287;
                  goto LABEL_392;
                }
                v76 = v301[2];
                if ( v301[2] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v302,
                    (char *)v75 + 64,
                    (char *)v75 + 56);
                  v301[1] = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v418,
                    v385,
                    &v303);
                  v75 = v303;
                }
              }
              v99 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 6);
              if ( v99 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v99, v301);
                if ( v24 < 0 )
                {
                  v444 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                    v374 = &v444;
                    v299 = &v374;
                    LOBYTE(v157) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v157,
                      3,
                      ": {}");
                  }
                  v101 = 5302;
                  goto LABEL_392;
                }
                if ( v301[0] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v302,
                    (char *)v75 + 64,
                    (char *)v75 + 56);
                  v24 = CActionListCreator::DisableFeature(v311, v75);
                  if ( v24 < 0 )
                  {
                    v445 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                        (char *)v75 + 72,
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v373 = &v445;
                      v299 = &v373;
                      LOBYTE(v155) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v155,
                        3,
                        ": {}");
                    }
                    v156 = 5311;
LABEL_403:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v156,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      (int)v299);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
                    if ( !v417 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v69 = 0;
                  if ( v76 )
                  {
                    v24 = -2146467821;
                    v446 = -2146467821;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                        v302,
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v372 = &v446;
                      v299 = &v372;
                      LOBYTE(v100) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v100,
                        3,
                        ": {}");
                    }
                    v101 = 5317;
                    goto LABEL_392;
                  }
                }
              }
              goto LABEL_345;
            }
            v81 = (const wchar_t *const *)((char *)v75 + 72);
            v80 = "Not including Group: {}, FMID: {}, Feature: {}";
            goto LABEL_117;
          }
          v97 = *((_BYTE *)v75 + 368);
          if ( v97 != 7 )
          {
            if ( (unsigned __int8)(v97 - 11) <= 1u || v97 == 8 )
            {
LABEL_201:
              v69 = 0;
LABEL_202:
              if ( *((_BYTE *)v75 + 368) == 20 )
              {
                Buf1 = 0;
                v24 = CDeviceInfo::GetNameValuePairValue(
                        *((CDeviceInfo **)this + 12),
                        L"HotPatchReadiness",
                        (const wchar_t **)&Buf1,
                        0);
                if ( v24 < 0 )
                {
                  v448 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to get hotpatch status");
                    v370 = &v448;
                    v299 = &v370;
                    LOBYTE(v153) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v153,
                      3,
                      ": {}");
                  }
                  v101 = 5212;
                  goto LABEL_392;
                }
                if ( !Buf1 )
                  goto LABEL_209;
                v107 = -1;
                do
                  ++v107;
                while ( *((_WORD *)Buf1 + v107) );
                if ( 2 * v107 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
                {
LABEL_209:
                  v108 = "Feature excluded due to no hotpatching support: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_210;
                }
              }
              v76 = 1;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v418,
                v399,
                &v303);
              v106 = "Feature added due to default desktop upgrade, image-based reset, or media-based upgrade evaluation:"
                     " Group: {0}, FMID: {1}, Feature: {2}";
              v103 = v302;
              goto LABEL_342;
            }
            if ( v97 != 15 )
            {
              if ( v97 != 20 )
                goto LABEL_181;
              goto LABEL_201;
            }
          }
          v102 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 1);
          v69 = 0;
          if ( v102 )
          {
            v24 = CUpdateEvaluator::EvaluateConditional(this, v102, &v301[2]);
            if ( v24 < 0 )
            {
              v449 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                  (char *)v75 + 64,
                  (char *)v75 + 56);
                v369 = &v449;
                v299 = &v369;
                LOBYTE(v152) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v152,
                  3,
                  ": {}");
              }
              v101 = 5188;
LABEL_392:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v101,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)(unsigned int)v24,
                (int)v299);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
              if ( !v417 )
                goto LABEL_716;
              goto LABEL_715;
            }
            v76 = v301[2];
            v103 = v302;
            v104 = (char *)v75 + 64;
            v105 = (char *)v75 + 56;
            if ( v301[2] )
              v106 = "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            else
              v106 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_344;
          }
          goto LABEL_202;
        }
        LogAdapter::TraceInfo<wchar_t const *>("Looking to see if feature should be included: {0}", (char *)v75 + 56);
        v69 = 0;
        Buf1 = 0;
        v133 = *((unsigned __int8 *)v75 + 368);
        if ( v133 > 0xC )
        {
          v139 = v133 - 15;
          if ( !v139 )
            goto LABEL_307;
          v140 = v139 - 4;
          if ( !v140 )
            goto LABEL_307;
          v141 = v140 - 1;
          if ( !v141 )
          {
            v24 = CDeviceInfo::GetNameValuePairValue(
                    *((CDeviceInfo **)this + 12),
                    L"HotPatchReadiness",
                    (const wchar_t **)&Buf1,
                    0);
            if ( v24 < 0 )
            {
              v481 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to get hotpatch status");
                *(_QWORD *)v349 = &v481;
                v299 = (int **)v349;
                LOBYTE(v168) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v168,
                  3,
                  ": {}");
              }
              v101 = 4961;
              goto LABEL_392;
            }
            if ( !Buf1 )
              goto LABEL_386;
            v147 = -1;
            do
              ++v147;
            while ( *((_WORD *)Buf1 + v147) );
            if ( 2 * v147 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
            {
LABEL_386:
              v24 = -2146467822;
              v437 = -2146467822;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Hotpatching is not supported on this machine/image.");
                v350 = &v437;
                v299 = &v350;
                LOBYTE(v167) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v167,
                  3,
                  ": {}");
              }
              v101 = 4965;
              goto LABEL_392;
            }
            goto LABEL_307;
          }
          v142 = v141 - 5;
          if ( !v142 )
            goto LABEL_307;
          v138 = v142 == 1;
        }
        else
        {
          if ( v133 == 12 )
            goto LABEL_307;
          v134 = v133 - 2;
          if ( !v134 )
            goto LABEL_307;
          v135 = v134 - 1;
          if ( !v135 )
            goto LABEL_307;
          v136 = v135 - 4;
          if ( !v136 )
            goto LABEL_307;
          v137 = v136 - 2;
          if ( !v137 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl) )
            {
LABEL_299:
              v143 = (char *)v75 + 64;
              v144 = (char *)v75 + 72;
              v145 = (char *)v75 + 56;
              v146 = "Not including Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_300;
            }
LABEL_307:
            v148 = *((_BYTE *)v75 + 368);
            if ( (unsigned __int8)(v148 - 2) <= 1u )
            {
              v151 = v302;
              if ( !CDeviceInfo::GetInstalledFeature(
                      *((CDeviceInfo **)this + 12),
                      *((const wchar_t *const *)v75 + 7),
                      *((const wchar_t *const *)v75 + 8),
                      *v302) )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v418,
                v396,
                &v303);
              v103 = v151;
              v106 = "Feature added for processing because it's already installed: Group: {0}, FMID: {1}, Feature: {2}";
            }
            else
            {
              if ( *(_QWORD *)v75 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(
                        this,
                        *(struct CCompositionDatabase::ConditionSet **)v75,
                        &v301[2]);
                if ( v24 < 0 )
                {
                  v480 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of repair feature conditional FMID: {0}, Feature: {1}",
                      (char *)v75 + 64,
                      (char *)v75 + 56);
                    v348 = &v480;
                    v299 = &v348;
                    LOBYTE(v169) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      v169,
                      3,
                      ": {}");
                  }
                  v101 = 5033;
                  goto LABEL_392;
                }
                v76 = v301[2];
                if ( v301[2] )
                {
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v418,
                    v397,
                    &v303);
                  v106 = "Feature added due to repair conditional: Group: {0}, FMID: {1}, Feature: {2}";
                  v75 = v303;
                }
                else
                {
                  v106 = "Feature not needed for repair: Group: {0}, FMID: {1}, Feature: {2}";
                }
                v103 = (const wchar_t *const *)((char *)v75 + 72);
                goto LABEL_343;
              }
              v149 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 1);
              if ( v149 )
              {
                if ( v148 != 11 || *((_BYTE *)this + 116) )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v149, &v301[2]);
                  if ( v24 < 0 )
                  {
                    v473 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v344 = &v473;
                      v299 = &v344;
                      LOBYTE(v173) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        v173,
                        3,
                        ": {}");
                    }
                    v101 = 5064;
                    goto LABEL_392;
                  }
                  v76 = v301[2];
                  if ( v301[2] )
                  {
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v418,
                      v391,
                      &v303);
                    v75 = v303;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v302,
                      (char *)v303 + 64,
                      (char *)v303 + 56);
                  }
                  v150 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v75 + 6);
                  if ( v150 )
                  {
                    v24 = CUpdateEvaluator::EvaluateConditional(this, v150, v301);
                    if ( v24 < 0 )
                    {
                      v474 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                          (char *)v75 + 64,
                          (char *)v75 + 56);
                        v345 = &v474;
                        v299 = &v345;
                        LOBYTE(v172) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          v172,
                          3,
                          ": {}");
                      }
                      v101 = 5077;
                      goto LABEL_392;
                    }
                    v77 = v301[0];
                    if ( v301[0] )
                    {
                      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                        "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                        v302,
                        (char *)v75 + 64,
                        (char *)v75 + 56);
                      v24 = CActionListCreator::DisableFeature(v311, v75);
                      if ( v24 < 0 )
                      {
                        v476 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                            (char *)v75 + 72,
                            (char *)v75 + 64,
                            (char *)v75 + 56);
                          *(_QWORD *)v346 = &v476;
                          v299 = (int **)v346;
                          LOBYTE(v171) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v171,
                            3,
                            ": {}");
                        }
                        v156 = 5086;
                        goto LABEL_403;
                      }
                      v69 = 0;
                      if ( v76 )
                      {
                        v24 = -2146467821;
                        v479 = -2146467821;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                            v302,
                            (char *)v75 + 64,
                            (char *)v75 + 56);
                          v347 = &v479;
                          v299 = &v347;
                          LOBYTE(v170) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            v170,
                            3,
                            ": {}");
                        }
                        v101 = 5092;
                        goto LABEL_392;
                      }
                      v77 = v301[0];
                    }
                  }
                  if ( v76 )
                    goto LABEL_155;
                  if ( v77 )
                    goto LABEL_157;
                  v108 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_210:
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v108, v302, (char *)v75 + 64, (char *)v75 + 56);
                  goto LABEL_157;
                }
              }
              else if ( v148 != 11 )
              {
                if ( v148 == 15 )
                {
                  v76 = *((_BYTE *)this + 117);
                  if ( !v76 )
                    goto LABEL_157;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v418,
                    v393,
                    &v303);
                  v103 = v302;
                  v106 = "Feature added due to safe OS dynamic update: Group: {0}, FMID: {1}, Feature: {2}";
                }
                else
                {
                  if ( v148 != 9 )
                  {
                    v76 = 1;
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v418,
                      v395,
                      &v303);
                    v75 = v303;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to default desktop servicing evaluation: Group: {0}, FMID: {1}, Feature: {2}",
                      v302,
                      (char *)v303 + 64,
                      (char *)v303 + 56);
                    goto LABEL_155;
                  }
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl)
                    || (v76 = *((_BYTE *)this + 116)) == 0 )
                  {
LABEL_157:
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                      v433,
                      v320,
                      &v303);
                    v91 = v320[0];
                    if ( v320[0] == v433[0] )
                      goto LABEL_120;
                    *(_BYTE *)(*(_QWORD *)(v320[0] + 40LL) + 32LL) = 1;
                    if ( v76 )
                    {
                      if ( !*(_DWORD *)(**(_QWORD **)(v91 + 40) + 16LL)
                        && !CUpdateEvaluator::FindFeatureOnDevice(this, v75) )
                      {
                        *(_DWORD *)(**(_QWORD **)(v91 + 40) + 16LL) |= *((_DWORD *)v75 + 95);
                      }
                      v92 = *(_QWORD *)(v91 + 40);
                      v93 = *(_DWORD *)(*(_QWORD *)v92 + 16LL);
                      if ( (v93 & 0x6E) == 0 && (!v301[4] || v301[1]) )
                      {
                        if ( *((_BYTE *)v75 + 368) == 1 || *((_BYTE *)v75 + 368) == 4 )
                          v94 = v93 | 0x30;
                        else
                          v94 = v93 | 0x50;
                        *(_DWORD *)(*(_QWORD *)v92 + 16LL) = v94;
                      }
                      goto LABEL_120;
                    }
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      &v418,
                      v323,
                      &v303);
                    v145 = (char *)v303 + 56;
                    v143 = (char *)v303 + 64;
                    v144 = (char *)v303 + 72;
                    v146 = "Feature added due to deferred update: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_300:
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v146, v144, v143, v145);
                    goto LABEL_120;
                  }
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    &v418,
                    v394,
                    &v303);
                  v103 = v302;
                  v106 = "Feature added due to tools: Group: {0}, FMID: {1}, Feature: {2}";
                }
                goto LABEL_342;
              }
              v76 = *((_BYTE *)this + 116);
              if ( !v76 )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                &v418,
                v392,
                &v303);
              v103 = v302;
              v106 = "Feature added due to cumulative update or reoffer: Group: {0}, FMID: {1}, Feature: {2}";
            }
LABEL_342:
            v75 = v303;
LABEL_343:
            v105 = (char *)v75 + 56;
            v104 = (char *)v75 + 64;
LABEL_344:
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v106, v103, v104, v105);
LABEL_345:
            if ( v76 )
              goto LABEL_155;
            goto LABEL_157;
          }
          v138 = v137 == 2;
        }
        if ( !v138 && !*(_QWORD *)v75 )
          goto LABEL_299;
        goto LABEL_307;
      }
      break;
    }
    v68 = (const struct CCompositionDatabase::Feature *)((char *)n + 8);
    n = v68;
    if ( v68 != (const struct CCompositionDatabase::Feature *)v313 )
      continue;
    break;
  }
  v67 = v309;
LABEL_124:
  v424 = 0;
  v425 = 0;
  if ( v419 )
    std::vector<CCompositionDatabase::Feature *>::_Resize_reallocate<std::_Value_init_tag>(&v424);
  v83 = (_QWORD *)v424;
  v84 = v418;
  v85 = *(const struct CCompositionDatabase::Feature **)v418;
  n = *(const struct CCompositionDatabase::Feature **)v418;
  while ( v85 != v84 )
  {
    *v83 = *((_QWORD *)v85 + 4);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v85 = n;
  }
  v427 = 0;
  v428 = 0;
  std::vector<CCompositionDatabase::Feature *>::reserve(&v427, (__int64)(*((_QWORD *)&v424 + 1) - v424) >> 3);
  FeatureDependencyClosure = CUpdateEvaluator::GetFeatureDependencyClosure(this, v67, &v424, &v427);
  v24 = FeatureDependencyClosure;
  if ( FeatureDependencyClosure < 0 )
  {
    v470 = FeatureDependencyClosure;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to determine feature dependency closure");
      *(_QWORD *)v341 = &v470;
      v299 = (int **)v341;
      LOBYTE(v177) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v177,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D8,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      (int)v299);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
    goto LABEL_714;
  }
  if ( (_QWORD)v424 != *((_QWORD *)&v424 + 1) )
    *((_QWORD *)&v424 + 1) = v424;
  v179 = (const struct CCompositionDatabase::Feature **)*((_QWORD *)&v427 + 1);
  v178 = (const struct CCompositionDatabase::Feature **)v427;
  if ( (_QWORD)v427 != *((_QWORD *)&v427 + 1) )
  {
    while ( 1 )
    {
      n = *v178;
      v29 = GetQualifiedFeatureId(n, &v417);
      if ( v29 < 0 )
        break;
      v29 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, 0);
      if ( v29 < 0 )
      {
        v469 = v29;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Unable to create feature modification request");
          *(_QWORD *)v340 = &v469;
          v299 = (int **)v340;
          LOBYTE(v184) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v184,
            3,
            ": {}");
        }
        v185 = 5601;
LABEL_441:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v185,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
          (const char *)(unsigned int)v29,
          (int)v299);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
        if ( v417 )
          goto LABEL_38;
        goto LABEL_39;
      }
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        &v418,
        v323,
        &n);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v420,
        &n);
      if ( ++v178 == v179 )
      {
        if ( (_QWORD)v427 != *((_QWORD *)&v427 + 1) )
          *((_QWORD *)&v427 + 1) = v427;
        goto LABEL_428;
      }
    }
    v457 = v29;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Unable to determine qualified feature id");
      v339 = &v457;
      LOBYTE(v186) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v186,
        3,
        ": {}");
    }
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
LABEL_446:
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
    if ( v417 )
      goto LABEL_38;
    goto LABEL_39;
  }
LABEL_428:
  v180 = (_QWORD *)*((_QWORD *)v67 + 5);
  v318[0] = &v180[*((_QWORD *)v67 + 3)];
  if ( v180 != (_QWORD *)v318[0] )
  {
    do
    {
      v321[0] = *v180;
      v181 = *(const wchar_t *const ***)(v321[0] + 48LL);
      for ( v320[0] = &v181[*(_QWORD *)(v321[0] + 32LL)]; v181 != (const wchar_t *const **)v320[0]; ++v181 )
      {
        v182 = *v181;
        v302 = *v181;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v418,
                &v302)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v420,
                &v302)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v421,
                &v302) )
        {
          FeatureOnDevice = CUpdateEvaluator::FindFeatureOnDevice(
                              this,
                              (const struct CCompositionDatabase::Feature *const)v182);
          if ( FeatureOnDevice && (!v301[4] || (*((_BYTE *)FeatureOnDevice + 52) & 0x6E) != 0) )
          {
            if ( *((_QWORD **)&v424 + 1) == v425 )
            {
              std::vector<SessionData::LocalSources>::_Emplace_reallocate<SessionData::LocalSources>(
                &v424,
                *((_QWORD *)&v424 + 1),
                &v302);
            }
            else
            {
              **((_QWORD **)&v424 + 1) = v182;
              *((_QWORD *)&v424 + 1) += 8LL;
            }
          }
          else if ( (*((_DWORD *)this + 12) == 1 || *((_DWORD *)this + 12) == 19)
                 && (unsigned __int8)(*((_BYTE *)v182 + 368) - 2) <= 1u )
          {
            v187 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v182 + 1);
            if ( v187 )
            {
              v301[1] = 0;
              if ( CUpdateEvaluator::EvaluateConditional(this, v187, &v301[1]) >= 0 && v301[1] )
              {
                v483 = 0;
                v484 = 0;
                std::vector<CCompositionDatabase::Feature *>::reserve(&v483, *((_QWORD *)v182 + 39) + 1LL);
                v338 = v182;
                v324 = 0;
                v325 = 0;
                std::vector<CCompositionDatabase::Feature *>::_Buy_nonzero(&v324, 1);
                v188 = v324;
                *(_QWORD *)v324 = v338;
                *((_QWORD *)&v324 + 1) = v188 + 8;
                *(_QWORD *)&v313 = 0;
                std::_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>::~_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>(&v313);
                v24 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v309, &v324, &v483);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v324);
                if ( v24 < 0 )
                {
                  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v483);
                  goto LABEL_475;
                }
                v189 = (_QWORD *)*((_QWORD *)&v483 + 1);
                v190 = (_QWORD *)v483;
                if ( (_QWORD)v483 != *((_QWORD *)&v483 + 1) )
                {
                  v191 = (_QWORD *)*((_QWORD *)&v424 + 1);
                  do
                  {
                    if ( (const wchar_t *const *)*v190 != v182 )
                    {
                      if ( v191 == v425 )
                      {
                        std::vector<SessionData::LocalSources>::_Emplace_reallocate<SessionData::LocalSources>(
                          &v424,
                          v191,
                          v190);
                        v191 = (_QWORD *)*((_QWORD *)&v424 + 1);
                      }
                      else
                      {
                        *v191 = *v190;
                        v191 = (_QWORD *)(*((_QWORD *)&v424 + 1) + 8LL);
                        *((_QWORD *)&v424 + 1) += 8LL;
                      }
                    }
                    ++v190;
                  }
                  while ( v190 != v189 );
                  v189 = (_QWORD *)*((_QWORD *)&v483 + 1);
                  v190 = (_QWORD *)v483;
                }
                if ( (unsigned __int64)(v189 - v190) > 1 )
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Edition feature dependencies included due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v321[0],
                    v182 + 8,
                    v182 + 7);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v483);
              }
            }
          }
        }
      }
      ++v180;
    }
    while ( v180 != (_QWORD *)v318[0] );
    v67 = v309;
  }
  v192 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v67, &v424, &v427);
  v24 = v192;
  v193 = 0;
  if ( v192 < 0 )
  {
    v456 = v192;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to determine feature dependency closure");
      *(_QWORD *)v337 = &v456;
      v299 = (int **)v337;
      LOBYTE(v194) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v194,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1629,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      (int)v299);
LABEL_475:
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
    goto LABEL_384;
  }
  if ( (_QWORD)v424 != *((_QWORD *)&v424 + 1) )
    *((_QWORD *)&v424 + 1) = v424;
  v195 = (__int64 *)*((_QWORD *)&v427 + 1);
  v196 = (__int64 *)v427;
  if ( (_QWORD)v427 != *((_QWORD *)&v427 + 1) )
  {
    do
    {
      v306 = *v196;
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        &v418,
        v323,
        &v306);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v420,
        &v306);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v421,
        &v306);
      ++v196;
    }
    while ( v196 != v195 );
    if ( (_QWORD)v427 != *((_QWORD *)&v427 + 1) )
      *((_QWORD *)&v427 + 1) = v427;
  }
  v197 = *(const wchar_t *const ***)v418;
  v307 = *(const wchar_t *const ***)v418;
  while ( !*((_BYTE *)v197 + 25) )
  {
    v198 = (const struct CCompositionDatabase::Feature *)v197[4];
    n = v198;
    v29 = GetQualifiedFeatureId(v198, &v417);
    if ( v29 < 0 )
    {
      v482 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Unable to determine qualified feature id");
        v334 = &v482;
        LOBYTE(v203) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v203,
          3,
          ": {}");
      }
      goto LABEL_508;
    }
    v306 = 0;
    v29 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v306);
    if ( v29 < 0 )
    {
      v452 = v29;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Unable to create feature modification request");
        *(_QWORD *)v335 = &v452;
        v299 = (int **)v335;
        LOBYTE(v202) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v202,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1641,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v29,
        (int)v299);
LABEL_508:
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
      goto LABEL_509;
    }
    v199 = (_BYTE *)v306;
    v200 = *(_QWORD *)(v306 + 16);
    if ( !v200 || (v301[4] || *(_DWORD *)(v200 + 52)) && (*(_BYTE *)(v200 + 48) & 4) == 0 )
    {
      if ( !CUpdateEvaluator::IsFeatureInstallAllowed(this, v198) )
      {
        v29 = -2146467829;
        v455 = -2146467829;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Required feature not available for install: Group: {0}, FMID: {1}, Feature: {2}",
            (char *)v198 + 72,
            (char *)v198 + 64,
            (char *)v198 + 56);
          v336 = &v455;
          v299 = &v336;
          LOBYTE(v201) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v201,
            3,
            ": {}");
        }
        v185 = 5723;
        goto LABEL_441;
      }
    }
    else
    {
      v193 = 1;
    }
    if ( v199[32] || v193 )
    {
      v193 = 0;
    }
    else
    {
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature added due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v198 + 72,
        (char *)v198 + 64,
        (char *)v198 + 56);
      v199[32] = 1;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
        v433,
        v323,
        &n,
        &v306);
      v193 = 0;
      if ( !*(_DWORD *)(*(_QWORD *)v199 + 16LL) )
        *(_DWORD *)(*(_QWORD *)v199 + 16LL) = *((_DWORD *)v198 + 95);
    }
    if ( v199[33] )
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature will not be removed due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v198 + 72,
        (char *)v198 + 64,
        (char *)v198 + 56);
    v199[33] = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v429,
      &n);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v307);
    v197 = v307;
  }
  v204 = *((_QWORD *)v67 + 5);
  *(_QWORD *)&v313 = v204 + 8LL * *((_QWORD *)v67 + 3);
  if ( v204 != (_QWORD)v313 )
  {
    do
    {
      v205 = *(const struct CCompositionDatabase::Feature ***)(*(_QWORD *)v204 + 48LL);
      v206 = &v205[*(_QWORD *)(*(_QWORD *)v204 + 32LL)];
      while ( v205 != v206 )
      {
        v207 = *v205;
        v302 = (const wchar_t *const *)*v205;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v418,
                &v302)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v420,
                &v302)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v421,
                &v302)
          && CUpdateEvaluator::FindFeatureOnDevice(this, v207) )
        {
          updated = GetQualifiedFeatureId(v207, &v417);
          if ( updated < 0 )
          {
            v477 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Unable to determine qualified feature id");
              v332 = &v477;
              LOBYTE(v212) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v212,
                3,
                ": {}");
            }
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
LABEL_534:
            if ( v417 )
              goto LABEL_535;
            goto LABEL_536;
          }
          v306 = 0;
          updated = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v306);
          if ( updated < 0 )
          {
            v478 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Unable to create feature modification request");
              *(_QWORD *)v333 = &v478;
              v300 = v333;
              LOBYTE(v210) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v210,
                3,
                ": {}");
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x168E,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
              (const char *)(unsigned int)updated,
              (int)v300);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
            if ( v417 )
            {
LABEL_535:
              operator delete((void *)(v417 - 8), v211);
              v417 = 0;
            }
LABEL_536:
            v24 = updated;
            goto LABEL_716;
          }
          *(_BYTE *)(v306 + 33) = 1;
          std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
            v429,
            v323,
            &v302,
            &v306);
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            v420,
            v378,
            &v302);
        }
        ++v205;
      }
      v204 += 8;
    }
    while ( v204 != (_QWORD)v313 );
    v67 = v309;
  }
  v209 = *(const struct CCompositionDatabase::Feature **)v429[0];
  n = *(const struct CCompositionDatabase::Feature **)v429[0];
  while ( !*((_BYTE *)v209 + 25) )
  {
    *(_BYTE *)(*((_QWORD *)v209 + 5) + 32LL) = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v433,
      *((_QWORD *)v209 + 5) + 8LL);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v209 = n;
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v427);
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v424);
  v486 = 0;
  v487 = 0;
  std::set_intersection<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::back_insert_iterator<std::vector<CCompositionDatabase::Feature *>>>(
    (unsigned int)&v313,
    *(_QWORD *)v418,
    (_DWORD)v418,
    *(_QWORD *)v420[0],
    v420[0],
    (__int64)&v486);
  v213 = (_QWORD *)*((_QWORD *)&v486 + 1);
  v214 = (_QWORD *)v486;
  if ( (_QWORD)v486 != *((_QWORD *)&v486 + 1) )
  {
    do
    {
      v215 = *v214;
      if ( (int)GetQualifiedFeatureId(*v214, &v417) >= 0 )
        LogAdapter::TraceAtLevelHr<long,AutoScz>(3, 2148499470LL, "Cannot remove required feature : {0}", &v417);
      else
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          3,
          2148499470LL,
          "Cannot remove required feature : {0}",
          v215 + 56);
      ++v214;
    }
    while ( v214 != v213 );
    v67 = v309;
    if ( (_QWORD)v486 != *((_QWORD *)&v486 + 1) )
    {
      v475 = -2146467826;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Operation requires removal of required features");
        *(_QWORD *)v331 = &v475;
        v299 = (int **)v331;
        LOBYTE(v216) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v216,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B7,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)0x800F800ELL,
        (int)v299);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v486);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
      if ( v417 )
      {
        operator delete((void *)(v417 - 8), v217);
        v417 = 0;
      }
      v24 = -2146467826;
      goto LABEL_716;
    }
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v486);
  v301[1] = 0;
  v301[3] = 0;
  v220 = *(const struct CCompositionDatabase::Feature **)v430[0];
  n = *(const struct CCompositionDatabase::Feature **)v430[0];
  while ( !*((_BYTE *)v220 + 25) )
  {
    v221 = *((_QWORD *)v220 + 8);
    LOBYTE(v219) = *(_BYTE *)(v221 + 33);
    LOBYTE(v218) = *(_BYTE *)(v221 + 32);
    EvaluateFeatureDeclares(
      *(_QWORD *)(v221 + 8),
      v218,
      v219,
      (unsigned int)&v431,
      (__int64)v485,
      (__int64)&v301[1],
      (__int64)&v301[3]);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v220 = n;
  }
  if ( !*(_DWORD *)this && (v301[1] || v301[3]) )
  {
    std::wstring::wstring(v384, L"en-US");
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
      &v431,
      v323,
      v384);
    std::wstring::~wstring(v384);
  }
  v222 = *(const struct CCompositionDatabase::Feature **)v431;
  n = *(const struct CCompositionDatabase::Feature **)v431;
  while ( !*((_BYTE *)v222 + 25) )
  {
    LogAdapter::TraceAtLevel<std::wstring>(1, "Supported language: {0}", (char *)v222 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v222 = n;
  }
  v223 = *(const struct CCompositionDatabase::Feature **)v485[0];
  n = *(const struct CCompositionDatabase::Feature **)v485[0];
  while ( !*((_BYTE *)v223 + 25) )
  {
    LogAdapter::TraceAtLevel<std::wstring>(1, "Supported architecture: {0}", (char *)v223 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v223 = n;
  }
  v224 = v311;
  v225 = CActionListCreator::DetermineOverlayPolicy(v311, *((const struct CDeviceInfo **)this + 12));
  v24 = v225;
  if ( v225 < 0 )
  {
    v468 = v225;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to fetch overlay policy");
      v330 = &v468;
      v299 = &v330;
      LOBYTE(v226) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v226,
        3,
        ": {}");
    }
    v120 = 5856;
    goto LABEL_377;
  }
  v227 = (struct CCompositionDatabase::Feature *)*((_QWORD *)v67 + 5);
  v316 = v227;
  v317 = (struct CCompositionDatabase::Feature *)((char *)v227 + 8 * *((_QWORD *)v67 + 3));
  if ( v227 == v317 )
    goto LABEL_610;
  while ( 2 )
  {
    n = *(const struct CCompositionDatabase::Feature **)v227;
    v228 = (const wchar_t *const **)*((_QWORD *)n + 6);
    v307 = v228;
    v318[0] = &v228[*((_QWORD *)n + 4)];
    if ( v228 == (const wchar_t *const **)v318[0] )
      goto LABEL_608;
    while ( 2 )
    {
      v229 = (const wchar_t **)*v228;
      v302 = *v228;
      v230 = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v433,
        &v313,
        &v302);
      v231 = v313;
      if ( (_QWORD)v313 != v433[0] )
      {
        v301[1] = 1;
        goto LABEL_569;
      }
      v301[1] = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v429,
        v321,
        &v302);
      v231 = v321[0];
      if ( v321[0] == v429[0] )
      {
        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
          v436,
          v320,
          &v302);
        if ( v320[0] == v436[0] )
        {
          LODWORD(v303) = 0;
          v235 = 0;
          FeatureStateOnDevice = CUpdateEvaluator::FindFeatureStateOnDevice(
                                   this,
                                   (const struct CCompositionDatabase::Feature *const)v229);
          goto LABEL_570;
        }
        v240 = *(_QWORD **)(v320[0] + 40LL);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v240[2];
        v241 = *v240;
        v242 = *(_DWORD *)(*v240 + 16LL);
        LODWORD(v303) = v242;
        v235 = *(_DWORD *)(v241 + 20);
        if ( *((_BYTE *)v229 + 368) != 16 )
        {
          LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
            "Feature modified due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
            v229 + 9,
            v229 + 8,
            v229 + 7);
          if ( v242
            && (std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v376),
                updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v311, (_DWORD)v229, v242, 0, (__int64)v376, 1),
                std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v376),
                updated < 0) )
          {
            v467 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed adding feature for token updates");
              *(_QWORD *)v329 = &v467;
              v299 = (int **)v329;
              LOBYTE(v265) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v265,
                3,
                ": {}");
            }
            v244 = 5902;
          }
          else
          {
            if ( !v235 )
              goto LABEL_570;
            std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v375);
            updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v311, (_DWORD)v229, v235, 0, (__int64)v375, 0);
            std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v375);
            if ( updated >= 0 )
              goto LABEL_570;
            v466 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(_QWORD *)&LogAdapter::g_Logger,
                0,
                3,
                "Failed adding feature for token updates");
              v328 = &v466;
              v299 = &v328;
              LOBYTE(v243) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v243,
                3,
                ": {}");
            }
            v244 = 5913;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v244,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)updated,
            (int)v299);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
          goto LABEL_534;
        }
      }
      else
      {
        v230 = 1;
LABEL_569:
        v232 = *(_QWORD **)(v231 + 40);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v232[2];
        v234 = *v232;
        LODWORD(v303) = *(_DWORD *)(*v232 + 16LL);
        v235 = *(_DWORD *)(v234 + 20);
      }
LABEL_570:
      if ( FeatureStateOnDevice )
      {
        v236 = v230 ^ 1;
        *((_BYTE *)FeatureStateOnDevice + 1) = v236;
        if ( v236 )
        {
          if ( *((_BYTE *)v229 + 369) )
          {
            v237 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 3);
            v238 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 4);
            if ( v237 != v238 )
            {
              while ( 1 )
              {
                v239 = v237[3] <= 7u ? (const wchar_t *)v237 : (const wchar_t *)*v237;
                PackageInAnyGroup = CUpdateEvaluator::FindPackageInAnyGroup(this, v239);
                if ( !PackageInAnyGroup )
                  break;
                *(_WORD *)PackageInAnyGroup = 1;
                v237 += 4;
                if ( v237 == v238 )
                  goto LABEL_591;
              }
              v29 = -2147023728;
              v465 = -2147023728;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<std::wstring>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed finding package: {0}",
                  v237);
                *(_QWORD *)v327 = &v465;
                v299 = (int **)v327;
                LOBYTE(v266) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v266,
                  3,
                  ": {}");
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1730,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)0x80070490LL,
                (int)v299);
              goto LABEL_446;
            }
          }
        }
      }
LABEL_591:
      if ( v301[1] )
      {
        v259 = 0;
        if ( *((_DWORD *)this + 12) == 1 )
        {
          if ( (unsigned __int8)(*((_BYTE *)v229 + 368) - 5) <= 1u )
            v259 = 8;
        }
        else if ( *((_DWORD *)this + 12) == 24 )
        {
          v259 = 32;
        }
        if ( FeatureStateOnDevice && (!v301[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          v260 = 1;
        else
          v260 = 2;
        v261 = v260 | v259;
        if ( v229 == (const wchar_t **)v310 && *((_DWORD *)v312 + 80) == 16 )
          v261 |= 0x10u;
        v67 = v309;
        v262 = CUpdateEvaluator::ServiceFeatureAndPackages(
                 (int)this,
                 v261,
                 (int)v303,
                 v235,
                 (__int64)&v431,
                 (__int64)v485,
                 (__int64)FeatureStateOnDevice,
                 (struct CCompositionDatabase::Feature *)v229,
                 (__int64)v309,
                 (__int64)v311);
        v29 = v262;
        if ( v262 < 0 )
        {
          v464 = v262;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t *>(
              (_DWORD)v229 + 64,
              3,
              (unsigned int)"Failed adding InstallPackage actions for feature: Group: {0}, FMID: {1}, Feature: {2}",
              (_DWORD)v229 + 72,
              (__int64)(v229 + 8),
              (__int64)(v229 + 7));
            *(_QWORD *)v326 = &v464;
            v299 = (int **)v326;
            LOBYTE(v263) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v263,
              3,
              ": {}");
          }
          v264 = 6012;
          goto LABEL_641;
        }
      }
      else
      {
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v421,
                &v302) )
        {
          if ( FeatureStateOnDevice
            && *((_BYTE *)FeatureStateOnDevice + 1)
            && (!v301[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not updating Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v229 + 8,
              v229 + 7);
            v246 = *((_QWORD *)FeatureStateOnDevice + 4);
            for ( k = *((_QWORD *)FeatureStateOnDevice + 3); k != v246; k += 32 )
            {
              if ( *(_QWORD *)(k + 24) <= 7u )
                v248 = (const wchar_t *)k;
              else
                v248 = *(const wchar_t **)k;
              v249 = CUpdateEvaluator::FindPackageInAnyGroup(this, v248);
              if ( v249 )
                *(_WORD *)v249 = 1;
            }
          }
          else
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not applicable Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v229 + 8,
              v229 + 7);
          }
        }
        v67 = v309;
      }
      v228 = v307 + 1;
      v307 = v228;
      if ( v228 != (const wchar_t *const **)v318[0] )
        continue;
      break;
    }
    v227 = v316;
LABEL_608:
    v227 = (struct CCompositionDatabase::Feature *)((char *)v227 + 8);
    v316 = v227;
    if ( v227 != v317 )
      continue;
    break;
  }
  v224 = v311;
LABEL_610:
  if ( *(_DWORD *)this != 1 )
    goto LABEL_728;
  v250 = *((_DWORD *)this + 12);
  if ( v250 <= 0x13 )
  {
    v251 = 526338;
    if ( _bittest(&v251, v250) )
    {
      v252 = (const wchar_t *const **)**((_QWORD **)this + 4);
      v307 = v252;
      while ( !*((_BYTE *)v252 + 25) )
      {
        v253 = (const struct CCompositionDatabase::Feature *)**((_QWORD **)v252[4] + 2);
        n = v253;
        while ( !*((_BYTE *)v253 + 25) )
        {
          v254 = *((_QWORD *)v253 + 4);
          if ( (*(_BYTE *)(v254 + 52) & 1) == 0
            && !CCompositionDatabase::FindFeature(
                  v67,
                  *v252[4],
                  *(const wchar_t *const *)(v254 + 8),
                  *(const wchar_t *const *)(v254 + 16)) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not modifying Group: {}, FMID: {}, Feature: {}",
              v252[4],
              *((_QWORD *)v253 + 4) + 8LL,
              *((_QWORD *)v253 + 4) + 16LL);
            *(_BYTE *)(*((_QWORD *)v253 + 4) + 1LL) = 1;
            v255 = *((_QWORD *)v253 + 4);
            v256 = *(_QWORD *)(v255 + 32);
            for ( m = *(_QWORD *)(v255 + 24); m != v256; m += 32 )
            {
              if ( *(_QWORD *)(m + 24) <= 7u )
                v258 = (const wchar_t *)m;
              else
                v258 = *(const wchar_t **)m;
              v267 = CUpdateEvaluator::FindPackageInAnyGroup(this, v258);
              if ( v267 )
                *(_BYTE *)v267 = 1;
            }
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
          v253 = n;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v307);
        v252 = v307;
      }
    }
  }
  if ( *(_DWORD *)this != 1
    || !v310
    || *((_DWORD *)this + 12) != 2
    && *((_DWORD *)this + 12) != 14
    && *((_DWORD *)this + 12) != 15
    && *((_DWORD *)this + 12) != 22 )
  {
    goto LABEL_728;
  }
  v268 = (const wchar_t *const **)**((_QWORD **)this + 4);
  v307 = v268;
LABEL_662:
  if ( *((_BYTE *)v268 + 25) )
  {
LABEL_728:
    if ( *((_BYTE *)v224 + 78) )
    {
      if ( *((_BYTE *)v224 + 77) )
        *(_BYTE *)(*(_QWORD *)v224 + 1184LL) = 1;
    }
    else if ( *((_BYTE *)v224 + 77) )
    {
      v285 = *(_QWORD **)v224;
      free(*(void **)(*(_QWORD *)v224 + 1096LL));
      v285[137] = 0;
      v285[135] = 0;
      v285[136] = 0;
    }
    v286 = *((_DWORD *)this + 12);
    if ( v286 == 3 )
    {
      v287 = CUpdateEvaluator::RemoveFeaturesAndPackages(this, v67, v436, v224);
      v24 = v287;
      if ( v287 < 0 )
      {
        v460 = v287;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed removing features and packages");
          v365 = &v460;
          v299 = &v365;
          LOBYTE(v288) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v288,
            3,
            ": {}");
        }
        v120 = 6134;
        goto LABEL_377;
      }
LABEL_702:
      v290 = (struct ActionList::Product **)*((_QWORD *)v67 + 13);
      v291 = &v290[*((_QWORD *)v67 + 11)];
      while ( v290 != v291 )
      {
        v29 = CActionListCreator::UpdateProduct(v224, *v290);
        if ( v29 < 0 )
        {
          v459 = v29;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            v296 = &String2;
            if ( !*(_DWORD *)*v290 )
              v296 = L"SystemManifest";
            v359 = v296;
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t const *>(
              &v359,
              v292,
              "Failed adding product update: Name {0}, Version {1}",
              (char *)*v290 + 8,
              (char *)*v290 + 16,
              &v359);
            v358 = &v459;
            v299 = &v358;
            LOBYTE(v297) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(_QWORD *)&LogAdapter::g_Logger,
              v297,
              3,
              ": {}");
          }
          v264 = 6146;
LABEL_641:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v264,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)v29,
            (int)v299);
          goto LABEL_509;
        }
        ++v290;
      }
      if ( *((_BYTE *)this + 119) )
      {
        LogAdapter::TraceInfo<>("Reordering packages for servicing based upgrade.");
        CActionListCreator::FinalizeActionListForServicingUpgrade(v224, v67);
      }
      if ( *((_DWORD *)this + 12) != 1
        || (v293 = CUpdateEvaluator::AddBaselinePackagesIfNeeded(this, v67, v224), v24 = v293, v293 >= 0) )
      {
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
        if ( v417 )
        {
          operator delete((void *)(v417 - 8), v298);
          v417 = 0;
        }
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v436);
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v429);
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v433);
        std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v430);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v485);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v431);
        return 0;
      }
      v458 = v293;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed adding baseline packages");
        *(_QWORD *)v357 = &v458;
        v299 = (int **)v357;
        LOBYTE(v294) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v294,
          3,
          ": {}");
      }
      v160 = 6162;
LABEL_713:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v160,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        (int)v299);
      goto LABEL_714;
    }
    if ( (unsigned int)(v286 - 14) <= 1 )
      goto LABEL_699;
    if ( !*((_BYTE *)this + 119) )
      goto LABEL_702;
    v289 = L"servicing";
    if ( (unsigned int)(v286 - 14) <= 1 )
LABEL_699:
      v289 = L"media";
    v363 = v289;
    LogAdapter::TraceInfo<wchar_t const *>("Stripping media section, because this is {0}-based upgrade", &v363);
    if ( *(_QWORD *)v224 )
      *(_QWORD *)(*(_QWORD *)v224 + 80LL) = 0;
    goto LABEL_702;
  }
  v269 = (const struct CCompositionDatabase::Feature *)**((_QWORD **)v268[4] + 2);
  for ( n = v269; ; v269 = n )
  {
    if ( *((_BYTE *)v269 + 25) )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v307);
      v268 = v307;
      goto LABEL_662;
    }
    v270 = *((_QWORD *)v269 + 4);
    if ( (*(_BYTE *)(v270 + 52) & 1) != 0 )
    {
      v271 = Windows::StringUtil::AsLUnicode(v401, *(_QWORD *)(v270 + 16));
      v382 = *(_OWORD *)v271;
      v272 = v382;
      v383 = *(_QWORD *)(v271 + 16);
      v273 = Windows::StringUtil::TrimPrefixIfPresent<_LUNICODE_STRING,_LUNICODE_STRING>(
               v402,
               &___LiteralObject__2U__BaseLiteralBuffer__03U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EP__0ED__0CN__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
               &v382);
      v488 = *(_OWORD *)v273;
      v489 = *(_QWORD *)(v273 + 16);
      if ( (unsigned __int64)v488 < v272 )
        break;
    }
LABEL_674:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
  }
  v308 = 0;
  v29 = SczAllocFromLUnicodeString(&v308, &v488);
  if ( v29 < 0 )
  {
    v283 = 6090;
    goto LABEL_684;
  }
  if ( !(unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                           &v488,
                           &___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HC__0GF__0GD__0GB__0GM__0GM__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
LABEL_672:
    if ( v308 )
    {
      operator delete(v308 - 4, v274);
      v308 = 0;
    }
    goto LABEL_674;
  }
  LogAdapter::TraceInfo<_LUNICODE_STRING>("Feature removed due to device state: {}", &v488);
  v29 = CActionListCreator::RemoveInstalledFeature(v224, v308, 0, 0);
  if ( v29 >= 0 )
  {
    memset(v404, 0, sizeof(v404));
    v405 = 0;
    v406 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v407, v275);
    std::set<CCompositionDatabase::Feature::FeaturePackageMediaState>::set<CCompositionDatabase::Feature::FeaturePackageMediaState>(v408);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v409, v276);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v410, v277);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v411, v278);
    v412 = 0;
    v413 = 0;
    v414 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v415, v279);
    v416 = 0;
    *((_QWORD *)&v405 + 1) = v308;
    v24 = CActionListCreator::UpdateFeatureTokens(
            (_DWORD)v224,
            (unsigned int)v404,
            64,
            *(_DWORD *)(*((_QWORD *)v269 + 4) + 48LL),
            *((_QWORD *)v269 + 4) + 56LL,
            0);
    if ( v24 < 0 )
    {
      v462 = v24;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed adding feature for token updates");
        *(_QWORD *)v368 = &v462;
        v299 = (int **)v368;
        LOBYTE(v280) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v280,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E2,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        (int)v299);
      CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v404);
      if ( v308 )
      {
        operator delete(v308 - 4, v281);
        v308 = 0;
      }
      goto LABEL_384;
    }
    CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v404);
    goto LABEL_672;
  }
  v461 = v29;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<_LUNICODE_STRING>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed adding RemoveFeature: Feature: {}",
      &v488);
    v367 = &v461;
    v299 = &v367;
    LOBYTE(v282) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v282,
      3,
      ": {}");
  }
  v283 = 6100;
LABEL_684:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v283,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
    (const char *)(unsigned int)v29,
    (int)v299);
  if ( v308 )
  {
    operator delete(v308 - 4, v284);
    v308 = 0;
  }
LABEL_509:
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v421);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v420);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v418);
  if ( v417 )
  {
LABEL_38:
    operator delete((void *)(v417 - 8), v35);
    v417 = 0;
  }
LABEL_39:
  v24 = v29;
LABEL_716:
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v436);
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v429);
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v433);
  std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v430);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v485);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v431);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18012eafc  mov     rax, rsp
0x18012eaff  push    rbp
0x18012eb00  push    rsi
0x18012eb01  push    rdi
0x18012eb02  push    r12
0x18012eb04  push    r13
0x18012eb06  push    r14
0x18012eb08  push    r15
0x18012eb0a  lea     rbp, [rax-7E8h]
0x18012eb11  sub     rsp, 8B0h
0x18012eb18  mov     [rbp+7E0h+var_5A0], 0FFFFFFFFFFFFFFFEh
0x18012eb23  mov     [rax+20h], rbx
0x18012eb27  movaps  xmmword ptr [rax-48h], xmm6
0x18012eb2b  mov     rax, cs:__security_cookie
0x18012eb32  xor     rax, rsp
0x18012eb35  mov     [rbp+7E0h+var_50], rax
0x18012eb3c  mov     [rbp+7E0h+var_840], r8
0x18012eb40  mov     [rbp+7E0h+var_850], rdx
0x18012eb44  mov     r13, rcx
0x18012eb47  lea     rcx, aArbiterEvaluat; "arbiter: Evaluating features for instal"...
0x18012eb4e  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18012eb53  mov     rax, [r13+60h]
0x18012eb57  mov     al, [rax+130h]
0x18012eb5d  mov     [rsp+8E0h+var_890+4], al
0x18012eb61  xor     esi, esi
0x18012eb63  mov     [rbp+7E0h+var_198], rsi
0x18012eb6a  mov     [rbp+7E0h+var_190], rsi
0x18012eb71  lea     r15d, [rsi+40h]
0x18012eb75  mov     ecx, r15d; Size
0x18012eb78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012eb7d  mov     [rax], rax
0x18012eb80  mov     [rax+8], rax
0x18012eb84  mov     [rax+10h], rax
0x18012eb88  mov     word ptr [rax+18h], 101h
0x18012eb8e  mov     [rbp+7E0h+var_198], rax
0x18012eb95  mov     rdx, [r13+60h]
0x18012eb99  add     rdx, 0B0h
0x18012eba0  lea     rcx, [rbp+7E0h+var_90]
0x18012eba7  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>> const &)
0x18012ebac  nop
0x18012ebad  mov     rax, [r13+60h]
0x18012ebb1  mov     rbx, [rax+0A0h]
0x18012ebb8  mov     rbx, [rbx]
0x18012ebbb  cmp     [rbx+19h], sil
0x18012ebbf  jnz     loc_18012ED2C
0x18012ebc5  lea     rsi, [rbx+20h]
0x18012ebc9  mov     [rsp+8E0h+var_890], 1
0x18012ebce  xor     r14d, r14d
0x18012ebd1  cmp     [r13+79h], r14b
0x18012ebd5  jz      short loc_18012EC34
0x18012ebd7  cmp     qword ptr [rsi+18h], 7
0x18012ebdc  jbe     short loc_18012EBE3
0x18012ebde  mov     r8, [rsi]
0x18012ebe1  jmp     short loc_18012EBE6
0x18012ebe3  mov     r8, rsi; wchar_t *
0x18012ebe6  lea     rax, [rsp+8E0h+var_890]
0x18012ebeb  mov     [rsp+8E0h+var_8C0], rax; bool *
0x18012ebf0  lea     rdx, aUserprofilelan_0; "UserProfileLanguage"
0x18012ebf7  mov     rcx, [r13+60h]; this
0x18012ebfb  call    ?MatchNameValueSetPair@CDeviceInfo@@QEBAJQEB_W0_NPEA_N@Z; CDeviceInfo::MatchNameValueSetPair(wchar_t const * const,wchar_t const * const,bool,bool *)
0x18012ec00  cmp     [rsp+8E0h+var_890], r14b
0x18012ec05  jnz     short loc_18012EC34
0x18012ec07  mov     r8, rsi
0x18012ec0a  lea     rdx, aRemovingUnused; "Removing unused language: {0} from sate"...
0x18012ec11  mov     ecx, 1
0x18012ec16  call    ??$TraceAtLevel@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXW4LogLevel@0@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceAtLevel<std::wstring>(LogAdapter::LogLevel,char const * const,std::wstring const &)
0x18012ec1b  xor     esi, esi
0x18012ec1d  mov     rcx, [rbx+10h]
0x18012ec21  cmp     [rcx+19h], sil
0x18012ec25  jz      loc_18012ED08
0x18012ec2b  mov     rax, [rbx+8]
0x18012ec2f  jmp     loc_18012ECFA
0x18012ec34  mov     r8, rsi
0x18012ec37  lea     rdx, [rbp+7E0h+var_450]
0x18012ec3e  lea     rcx, [rbp+7E0h+var_198]
0x18012ec45  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18012ec4a  movups  xmm6, xmmword ptr [rax]
0x18012ec4d  mov     r8, rsi
0x18012ec50  mov     rdx, [rax+10h]
0x18012ec54  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x18012ec59  test    al, al
0x18012ec5b  jnz     short loc_18012EC1B
0x18012ec5d  mov     rax, 3FFFFFFFFFFFFFFh
0x18012ec67  cmp     [rbp+7E0h+var_190], rax
0x18012ec6e  jz      loc_180132EF8
0x18012ec74  mov     rdi, [rbp+7E0h+var_198]
0x18012ec7b  lea     rax, [rbp+7E0h+var_198]
0x18012ec82  mov     [rbp+7E0h+var_7F8], rax
0x18012ec86  mov     [rbp+7E0h+var_7F0], r14
0x18012ec8a  mov     rcx, r15; Size
0x18012ec8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012ec92  mov     [rbp+7E0h+var_7F0], rax
0x18012ec96  lea     rcx, [rax+20h]
0x18012ec9a  mov     rdx, rsi
0x18012ec9d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18012eca2  mov     rax, [rbp+7E0h+var_7F0]
0x18012eca6  mov     [rax], rdi
0x18012eca9  mov     rax, [rbp+7E0h+var_7F0]
0x18012ecad  mov     [rax+8], rdi
0x18012ecb1  mov     rax, [rbp+7E0h+var_7F0]
0x18012ecb5  mov     [rax+10h], rdi
0x18012ecb9  mov     rax, [rbp+7E0h+var_7F0]
0x18012ecbd  xor     esi, esi
0x18012ecbf  mov     [rax+18h], sil
0x18012ecc3  mov     rax, [rbp+7E0h+var_7F0]
0x18012ecc7  mov     [rax+19h], sil
0x18012eccb  mov     r8, [rbp+7E0h+var_7F0]
0x18012eccf  mov     [rbp+7E0h+var_7F0], rsi
0x18012ecd3  movdqu  [rbp+7E0h+var_830], xmm6
0x18012ecd8  lea     rdx, [rbp+7E0h+var_830]
0x18012ecdc  lea     rcx, [rbp+7E0h+var_198]
0x18012ece3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::wstring_view,void *> *>,std::_Tree_node<std::wstring_view,void *> * const)
0x18012ece8  jmp     loc_18012EC1D
0x18012eced  cmp     rbx, [rax+10h]
0x18012ecf1  jnz     short loc_18012ED00
0x18012ecf3  mov     rbx, rax
0x18012ecf6  mov     rax, [rax+8]
0x18012ecfa  cmp     [rax+19h], sil
0x18012ecfe  jz      short loc_18012ECED
0x18012ed00  mov     rbx, rax
0x18012ed03  jmp     loc_18012EBBB
0x18012ed08  mov     rbx, rcx
0x18012ed0b  mov     rcx, [rcx]
0x18012ed0e  cmp     [rcx+19h], sil
0x18012ed12  jnz     loc_18012EBBB
0x18012ed18  mov     rbx, rcx
0x18012ed1b  mov     rax, [rcx]
0x18012ed1e  mov     rcx, rax
0x18012ed21  cmp     [rax+19h], sil
0x18012ed25  jz      short loc_18012ED18
0x18012ed27  jmp     loc_18012EBBB
0x18012ed2c  mov     [rbp+7E0h+var_1A8], rsi
0x18012ed33  mov     [rbp+7E0h+var_1A0], rsi
0x18012ed3a  mov     ecx, 48h ; 'H'; Size
0x18012ed3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012ed44  mov     [rax], rax
0x18012ed47  mov     [rax+8], rax
0x18012ed4b  mov     [rax+10h], rax
0x18012ed4f  mov     word ptr [rax+18h], 101h
0x18012ed55  mov     [rbp+7E0h+var_1A8], rax
0x18012ed5c  mov     [rbp+7E0h+var_188], rsi
0x18012ed63  mov     [rbp+7E0h+var_180], rsi
0x18012ed6a  mov     ebx, 30h ; '0'
0x18012ed6f  mov     ecx, ebx; Size
0x18012ed71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012ed76  mov     [rax], rax
0x18012ed79  mov     [rax+8], rax
0x18012ed7d  mov     [rax+10h], rax
0x18012ed81  mov     word ptr [rax+18h], 101h
0x18012ed87  mov     [rbp+7E0h+var_188], rax
0x18012ed8e  mov     [rbp+7E0h+var_1B8], rsi
0x18012ed95  mov     [rbp+7E0h+var_1B0], rsi
0x18012ed9c  mov     ecx, ebx; Size
0x18012ed9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012eda3  mov     [rax], rax
0x18012eda6  mov     [rax+8], rax
0x18012edaa  mov     [rax+10h], rax
0x18012edae  mov     word ptr [rax+18h], 101h
0x18012edb4  mov     [rbp+7E0h+var_1B8], rax
0x18012edbb  mov     [rbp+7E0h+var_170], rsi
0x18012edc2  mov     [rbp+7E0h+var_168], rsi
0x18012edc9  mov     ecx, ebx; Size
0x18012edcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012edd0  mov     [rax], rax
0x18012edd3  mov     [rax+8], rax
0x18012edd7  mov     [rax+10h], rax
0x18012eddb  mov     word ptr [rax+18h], 101h
0x18012ede1  mov     [rbp+7E0h+var_170], rax
0x18012ede8  mov     [rbp+7E0h+var_230], rsi
0x18012edef  mov     [rbp+7E0h+var_228], rsi
0x18012edf6  mov     [rbp+7E0h+var_220], rsi
0x18012edfd  mov     ebx, 28h ; '('
0x18012ee02  mov     ecx, ebx
0x18012ee04  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012ee09  mov     [rax], rax
0x18012ee0c  mov     [rax+8], rax
0x18012ee10  mov     [rax+10h], rax
0x18012ee14  mov     word ptr [rax+18h], 101h
0x18012ee1a  mov     [rbp+7E0h+var_228], rax
0x18012ee21  mov     [rbp+7E0h+var_218], rsi
0x18012ee28  mov     [rbp+7E0h+var_210], rsi
0x18012ee2f  mov     ecx, ebx
0x18012ee31  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012ee36  mov     [rax], rax
0x18012ee39  mov     [rax+8], rax
0x18012ee3d  mov     [rax+10h], rax
0x18012ee41  mov     word ptr [rax+18h], 101h
0x18012ee47  mov     [rbp+7E0h+var_218], rax
0x18012ee4e  mov     [rbp+7E0h+var_208], rsi
0x18012ee55  mov     [rbp+7E0h+var_200], rsi
0x18012ee5c  mov     ecx, ebx
0x18012ee5e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18012ee63  mov     [rax], rax
0x18012ee66  mov     [rax+8], rax
0x18012ee6a  mov     [rax+10h], rax
0x18012ee6e  mov     word ptr [rax+18h], 101h
0x18012ee74  mov     [rbp+7E0h+var_208], rax
0x18012ee7b  lea     r8, [rbp+7E0h+var_1A8]
0x18012ee82  mov     rdx, [rbp+7E0h+var_850]
0x18012ee86  mov     rcx, r13
0x18012ee89  call    ?GetDeferredUpdateRequests@CUpdateEvaluator@@AEAAJPEBVCCompositionDatabase@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUFeatureRequest@CUpdateEvaluator@@UWstringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@2@@std@@@Z; CUpdateEvaluator::GetDeferredUpdateRequests(CCompositionDatabase const *,std::map<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>> &)
0x18012ee8e  mov     ebx, eax
0x18012ee90  test    eax, eax
0x18012ee92  jns     short loc_18012EEFA
0x18012ee94  mov     [rbp+7E0h+var_11C], eax
0x18012ee9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18012eea1  test    rcx, rcx
0x18012eea4  jz      short loc_18012EEF0
0x18012eea6  lea     r9, aFailedToGetDef; "Failed to get deferred updates"
0x18012eead  mov     esi, 3
0x18012eeb2  mov     r8d, esi
0x18012eeb5  xor     edx, edx
0x18012eeb7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18012eebc  lea     rax, [rbp+7E0h+var_11C]
0x18012eec3  mov     [rbp+7E0h+var_688], rax
0x18012eeca  lea     rax, [rbp+7E0h+var_688]
0x18012eed1  mov     [rsp+8E0h+var_8C0], rax
0x18012eed6  lea     r9, asc_1802C6678; ": {}"
0x18012eedd  mov     r8d, esi
0x18012eee0  mov     dl, 1
0x18012eee2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18012eee9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18012eeee  xor     esi, esi
0x18012eef0  mov     edx, 1244h
0x18012eef5  jmp     loc_18012F13A
0x18012eefa  mov     rax, [rbp+7E0h+var_1A8]
0x18012ef01  mov     rax, [rax]
0x18012ef04  mov     [rsp+8E0h+var_868], rax
0x18012ef09  cmp     [rax+19h], sil
0x18012ef0d  jnz     loc_18012F0B4
0x18012ef13  mov     [rbp+7E0h+var_174], esi
0x18012ef19  mov     [rbp+7E0h+var_178], esi
0x18012ef1f  mov     [rbp+7E0h+var_1F8], sil
0x18012ef26  mov     [rbp+7E0h+var_1F7], sil
0x18012ef2d  mov     rbx, [rax+40h]
0x18012ef31  mov     [rbp+7E0h+var_848], rbx
0x18012ef35  lea     rax, [rbp+7E0h+var_1F7]
0x18012ef3c  mov     [rsp+8E0h+var_8B8], rax; bool *
0x18012ef41  lea     rax, [rbp+7E0h+var_1F8]
0x18012ef48  mov     [rsp+8E0h+var_8C0], rax; bool *
0x18012ef4d  lea     r9, [rbp+7E0h+var_178]; enum FeatureIntentFlags *
0x18012ef54  lea     r8, [rbp+7E0h+var_174]; enum FeatureIntentFlags *
0x18012ef5b  mov     rdx, rbx; struct CUpdateEvaluator::FeatureRequest *
0x18012ef5e  mov     rcx, r13; this
0x18012ef61  call    ?EvaluateModifyRequest@CUpdateEvaluator@@AEAAJPEAUFeatureRequest@1@AEAW4FeatureIntentFlags@@1AEA_N2@Z; CUpdateEvaluator::EvaluateModifyRequest(CUpdateEvaluator::FeatureRequest *,FeatureIntentFlags &,FeatureIntentFlags &,bool &,bool &)
0x18012ef66  mov     edi, eax
0x18012ef68  test    eax, eax
0x18012ef6a  js      short loc_18012EFE9
0x18012ef6c  mov     rcx, [rbx]
0x18012ef6f  mov     eax, [rbp+7E0h+var_174]
0x18012ef75  mov     [rcx+10h], eax
0x18012ef78  mov     rcx, [rbx]
0x18012ef7b  mov     eax, [rbp+7E0h+var_178]
0x18012ef81  mov     [rcx+14h], eax
0x18012ef84  add     rbx, 8
0x18012ef88  lea     r9, [rbp+7E0h+var_848]
0x18012ef8c  mov     r8, rbx
0x18012ef8f  lea     rdx, [rbp+7E0h+var_830]
0x18012ef93  lea     rcx, [rbp+7E0h+var_170]
0x18012ef9a  call    ??$emplace@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@?$_Tree@V?$_Tmap_traits@PEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@U?$less@PEBUFeature@CCompositionDatabase@@@std@@V?$allocator@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@std@@@std@@@std@@_N@1@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@Z; std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &)
0x18012ef9f  cmp     [rbp+7E0h+var_1F7], sil
0x18012efa6  jz      short loc_18012EFB5
0x18012efa8  lea     rdx, [rbp+7E0h+var_7D8]
0x18012efac  lea     rcx, [rbp+7E0h+var_1B8]
0x18012efb3  jmp     short loc_18012EFC9
0x18012efb5  cmp     [rbp+7E0h+var_1F8], sil
0x18012efbc  jz      short loc_18012EFD5
0x18012efbe  lea     rdx, [rbp+7E0h+var_7E8]
0x18012efc2  lea     rcx, [rbp+7E0h+var_188]
0x18012efc9  lea     r9, [rbp+7E0h+var_848]
0x18012efcd  mov     r8, rbx
0x18012efd0  call    ??$emplace@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@?$_Tree@V?$_Tmap_traits@PEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@U?$less@PEBUFeature@CCompositionDatabase@@@std@@V?$allocator@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUFeature@CCompositionDatabase@@PEAUFeatureRequest@CUpdateEvaluator@@@std@@@std@@@std@@@std@@_N@1@AEBQEAUFeature@CCompositionDatabase@@AEAPEAUFeatureRequest@CUpdateEvaluator@@@Z; std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &)
0x18012efd5  lea     rcx, [rsp+8E0h+var_868]
0x18012efda  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x18012efdf  mov     rax, [rsp+8E0h+var_868]
0x18012efe4  jmp     loc_18012EF09
0x18012efe9  mov     [rbp+7E0h+var_120], edi
0x18012efef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18012eff6  test    rcx, rcx
0x18012eff9  jz      short loc_18012F04E
0x18012effb  lea     rax, [rbx+18h]
0x18012efff  mov     [rsp+8E0h+var_8C0], rax
0x18012f004  lea     r9, aFailedToEvalua_1; "Failed to evaluate deferred update; ski"...
0x18012f00b  mov     esi, 3
0x18012f010  mov     r8d, esi
0x18012f013  xor     edx, edx
0x18012f015  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x18012f01a  lea     rax, [rbp+7E0h+var_120]
0x18012f021  mov     qword ptr [rbp+7E0h+var_680], rax
0x18012f028  lea     rax, [rbp+7E0h+var_680]
0x18012f02f  mov     [rsp+8E0h+var_8C0], rax; int
0x18012f034  lea     r9, asc_1802C6678; ": {}"
0x18012f03b  mov     r8d, esi
0x18012f03e  mov     dl, 1
0x18012f040  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18012f047  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18012f04c  xor     esi, esi
0x18012f04e  mov     edx, 124Fh; void *
0x18012f053  lea     r8, aOnecoreBaseSer_15; "onecore\\base\\servicing\\arbiter\\cupd"...
0x18012f05a  mov     r9d, edi; char *
  ... truncated ...
```
