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
  _QWORD *v10; // rax
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
  __int64 v26; // rax
  struct CUpdateEvaluator::FeatureRequest *v27; // rbx
  int v28; // edi
  __int64 *v29; // rbx
  _QWORD *v30; // rdx
  __int64 *v31; // rcx
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  int NameValuePairValue; // eax
  __int64 v35; // r9
  const struct std::nothrow_t *v36; // rdx
  _QWORD *v37; // r15
  const wchar_t *const *v38; // r12
  struct CCompositionDatabase::Feature *v39; // r14
  int v40; // edx
  bool v41; // zf
  __int64 *v42; // rbx
  __int64 v43; // r8
  char v44; // cl
  unsigned int v45; // eax
  struct CCompositionDatabase::ConditionSet *v46; // rdx
  const wchar_t *v47; // rax
  __int64 v48; // rax
  char v49; // cl
  wchar_t **v50; // rdi
  wchar_t **v51; // rsi
  wchar_t *v52; // r14
  __int64 v53; // r12
  wchar_t *v54; // r15
  int v55; // eax
  __int64 v56; // rcx
  unsigned int v57; // eax
  int v58; // eax
  int v59; // eax
  __int64 v60; // rdi
  __int64 v61; // rsi
  const wchar_t *const **v62; // rdi
  const wchar_t *const **v63; // rsi
  CCompositionDatabase *v64; // r12
  const wchar_t *const **v65; // rcx
  bool v66; // r15
  const wchar_t *const *v67; // rbx
  struct CUpdateEvaluator::FeatureGroup *FeatureGroupOnDevice; // rax
  wchar_t *v69; // rcx
  bool v70; // zf
  struct CCompositionDatabase::Feature *v71; // rdi
  char v72; // r12
  bool v73; // r14
  int QualifiedFeatureId; // eax
  __int64 v75; // rbx
  const char *v76; // rcx
  const wchar_t *const *v77; // rdx
  char *v78; // r9
  _QWORD *v79; // r11
  _QWORD *v80; // r10
  __int64 v81; // rax
  wchar_t *v82; // rax
  char v83; // cl
  bool v84; // zf
  int v85; // eax
  const char *v86; // rcx
  __int64 v87; // rbx
  __int64 v88; // rax
  int v89; // ecx
  int v90; // ecx
  unsigned int v91; // eax
  int v92; // ecx
  char v93; // cl
  struct CCompositionDatabase::ConditionSet *v94; // rdx
  struct CCompositionDatabase::ConditionSet *v95; // rdx
  __int64 v96; // rdx
  struct CCompositionDatabase::ConditionSet *v97; // rdx
  const wchar_t *const *v98; // rdx
  char *v99; // r8
  char *v100; // r9
  const char *v101; // rcx
  __int64 v102; // rax
  const char *v103; // rcx
  __int64 v104; // rcx
  __int128 v105; // xmm0
  __int64 v106; // rax
  __int64 v107; // rax
  struct CCompositionDatabase::ConditionSet *v108; // rdx
  const wchar_t *const *v109; // r12
  int v110; // eax
  __int64 v111; // rdx
  struct CCompositionDatabase::ConditionSet *v112; // rdx
  __int64 v113; // rdx
  char v114; // al
  int v115; // eax
  const struct std::nothrow_t *v116; // rdx
  bool v117; // r9
  const wchar_t *v118; // rbx
  wchar_t *v119; // r14
  const struct CDeviceInfo::Package *AppMainPackageFromInstalledFeature; // r14
  bool IsStubAppFeatureInstalled; // al
  __int64 v122; // r8
  __int64 v123; // rcx
  __int64 v124; // rdx
  const struct CDeviceInfo::Package *UUPPackageFromInstalledFeature; // rax
  unsigned int v126; // ecx
  unsigned int v127; // ecx
  unsigned int v128; // ecx
  unsigned int v129; // ecx
  unsigned int v130; // ecx
  bool v131; // zf
  unsigned int v132; // ecx
  unsigned int v133; // ecx
  unsigned int v134; // ecx
  unsigned int v135; // ecx
  char *v136; // r8
  char *v137; // rdx
  char *v138; // r9
  const char *v139; // rcx
  __int64 v140; // rax
  char v141; // cl
  struct CCompositionDatabase::ConditionSet *v142; // rdx
  struct CCompositionDatabase::ConditionSet *v143; // rdx
  const wchar_t *const *v144; // rbx
  __int64 v145; // rdx
  __int64 v146; // rdx
  unsigned __int64 v147; // r9
  __int64 v148; // rdx
  const struct std::nothrow_t *v149; // rdx
  int FeatureDependencyClosure; // eax
  __int64 *v151; // rbx
  __int64 *v152; // r14
  _QWORD *v153; // r15
  const wchar_t *const **v154; // r12
  const wchar_t *const *v155; // rdi
  struct CUpdateEvaluator::Feature *FeatureOnDevice; // rax
  __int64 v157; // rdx
  struct CCompositionDatabase::ConditionSet *v158; // rdx
  __int64 v159; // rcx
  _QWORD *v160; // rbx
  _QWORD *v161; // r14
  _QWORD *v162; // rdx
  int v163; // eax
  char v164; // r14
  __int64 *v165; // rdi
  __int64 *v166; // rbx
  const wchar_t ***v167; // rax
  const struct CCompositionDatabase::Feature *v168; // rbx
  _BYTE *v169; // rdi
  __int64 v170; // rax
  __int64 v171; // rbx
  const wchar_t *const **v172; // rdi
  const wchar_t *const **v173; // r12
  const wchar_t *const *v174; // r15
  int updated; // r14d
  __int64 v176; // rax
  const struct std::nothrow_t *v177; // rdx
  _QWORD *v178; // rdi
  _QWORD *v179; // rbx
  __int64 v180; // r14
  const struct std::nothrow_t *v181; // rdx
  int v182; // edx
  int v183; // r8d
  __int64 v184; // rax
  __int64 v185; // rcx
  __int64 v186; // r8
  __int64 v187; // r8
  CActionListCreator *v188; // r15
  int v189; // eax
  __int64 *v190; // rcx
  const wchar_t ***v191; // rdx
  const wchar_t **v192; // rbx
  char v193; // r12
  __int64 v194; // rax
  _QWORD *v195; // rcx
  struct CUpdateEvaluator::Feature *FeatureStateOnDevice; // rdi
  __int64 v197; // rax
  int v198; // r15d
  char v199; // r12
  _QWORD *v200; // r14
  _QWORD *v201; // r12
  const wchar_t *v202; // rdx
  _QWORD *v203; // rcx
  __int64 v204; // rax
  int v205; // r14d
  __int64 v206; // rdx
  struct CUpdateEvaluator::Package *PackageInAnyGroup; // rax
  __int64 v208; // r14
  __int64 k; // rbx
  const wchar_t *v210; // rdx
  struct CUpdateEvaluator::Package *v211; // rax
  unsigned int v212; // eax
  int v213; // ecx
  const wchar_t ***v214; // rdi
  __int64 v215; // rbx
  __int64 v216; // r8
  __int64 v217; // rax
  __int64 v218; // r14
  __int64 m; // rbx
  const wchar_t *v220; // rdx
  int v221; // edx
  int v222; // eax
  int v223; // edx
  int v224; // eax
  __int64 v225; // rdx
  struct CUpdateEvaluator::Package *v226; // rax
  const wchar_t ***v227; // rax
  __int64 v228; // rbx
  __int64 v229; // rdx
  __int64 v230; // rax
  unsigned __int64 v231; // xmm6_8
  __int64 v232; // rax
  const struct std::nothrow_t *v233; // rdx
  const struct std::nothrow_t *v234; // rdx
  __int64 v235; // rdx
  const struct std::nothrow_t *v236; // rdx
  _QWORD *v237; // rbx
  int v238; // ecx
  int v239; // eax
  const wchar_t *v240; // rax
  struct ActionList::Product **v241; // rbx
  struct ActionList::Product **v242; // r14
  __int64 v243; // rdx
  int v244; // eax
  const wchar_t *v246; // rax
  const struct std::nothrow_t *v247; // rdx
  int v248; // [rsp+28h] [rbp-E0h]
  int v249; // [rsp+28h] [rbp-E0h]
  bool v250[8]; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *const *v251; // [rsp+60h] [rbp-A8h] BYREF
  struct CCompositionDatabase::Feature *v252; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *const **n; // [rsp+70h] [rbp-98h] BYREF
  void *Buf1; // [rsp+78h] [rbp-90h] BYREF
  __int64 v255; // [rsp+80h] [rbp-88h] BYREF
  const wchar_t ***v256; // [rsp+88h] [rbp-80h] BYREF
  wchar_t *v257; // [rsp+90h] [rbp-78h] BYREF
  CCompositionDatabase *v258; // [rsp+98h] [rbp-70h]
  struct CCompositionDatabase::Feature *v259; // [rsp+A0h] [rbp-68h] BYREF
  CActionListCreator *v260; // [rsp+A8h] [rbp-60h]
  wchar_t *v261; // [rsp+B0h] [rbp-58h]
  __int128 v262; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *v264; // [rsp+D0h] [rbp-38h] BYREF
  struct CCompositionDatabase::Feature *v265; // [rsp+D8h] [rbp-30h]
  struct CCompositionDatabase::Feature *v266; // [rsp+E0h] [rbp-28h]
  _QWORD v267[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v268; // [rsp+F8h] [rbp-10h]
  _QWORD v269[2]; // [rsp+100h] [rbp-8h] BYREF
  _QWORD v270[2]; // [rsp+110h] [rbp+8h] BYREF
  struct CCompositionDatabase::Feature *v271; // [rsp+120h] [rbp+18h]
  _BYTE v272[16]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v273; // [rsp+138h] [rbp+30h] BYREF
  __int64 v274; // [rsp+148h] [rbp+40h]
  int v275[2]; // [rsp+150h] [rbp+48h] BYREF
  int v276[2]; // [rsp+158h] [rbp+50h] BYREF
  int *v277; // [rsp+160h] [rbp+58h] BYREF
  int v278[2]; // [rsp+168h] [rbp+60h] BYREF
  int *v279; // [rsp+170h] [rbp+68h] BYREF
  int v280[2]; // [rsp+178h] [rbp+70h] BYREF
  int *v281; // [rsp+180h] [rbp+78h] BYREF
  int v282[2]; // [rsp+188h] [rbp+80h] BYREF
  int *v283; // [rsp+190h] [rbp+88h] BYREF
  int v284[2]; // [rsp+198h] [rbp+90h] BYREF
  int *v285; // [rsp+1A0h] [rbp+98h] BYREF
  int v286[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  const wchar_t *const *v287; // [rsp+1B0h] [rbp+A8h]
  int *v288; // [rsp+1B8h] [rbp+B0h] BYREF
  int v289[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v290[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  int *v291; // [rsp+1D0h] [rbp+C8h] BYREF
  int v292[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  int *v293; // [rsp+1E0h] [rbp+D8h] BYREF
  int *v294; // [rsp+1E8h] [rbp+E0h] BYREF
  int v295[2]; // [rsp+1F0h] [rbp+E8h] BYREF
  int *v296; // [rsp+1F8h] [rbp+F0h] BYREF
  int *v297; // [rsp+200h] [rbp+F8h] BYREF
  int v298[2]; // [rsp+208h] [rbp+100h] BYREF
  int *v299; // [rsp+210h] [rbp+108h] BYREF
  int *v300; // [rsp+218h] [rbp+110h] BYREF
  int v301[2]; // [rsp+220h] [rbp+118h] BYREF
  int *v302; // [rsp+228h] [rbp+120h] BYREF
  int *v303; // [rsp+230h] [rbp+128h] BYREF
  int *v304; // [rsp+238h] [rbp+130h] BYREF
  int *v305; // [rsp+240h] [rbp+138h] BYREF
  int v306[2]; // [rsp+248h] [rbp+140h] BYREF
  int *v307; // [rsp+250h] [rbp+148h] BYREF
  const wchar_t *v308; // [rsp+258h] [rbp+150h] BYREF
  int *v309; // [rsp+260h] [rbp+158h] BYREF
  int v310[2]; // [rsp+268h] [rbp+160h] BYREF
  int v311[2]; // [rsp+270h] [rbp+168h] BYREF
  const wchar_t *v312; // [rsp+278h] [rbp+170h] BYREF
  int *v313; // [rsp+280h] [rbp+178h] BYREF
  int *v314; // [rsp+288h] [rbp+180h] BYREF
  int *v315; // [rsp+290h] [rbp+188h] BYREF
  int *v316; // [rsp+298h] [rbp+190h] BYREF
  int v317[2]; // [rsp+2A0h] [rbp+198h] BYREF
  int *v318; // [rsp+2A8h] [rbp+1A0h] BYREF
  int *v319; // [rsp+2B0h] [rbp+1A8h] BYREF
  int *v320; // [rsp+2B8h] [rbp+1B0h] BYREF
  int *v321; // [rsp+2C0h] [rbp+1B8h] BYREF
  int *v322; // [rsp+2C8h] [rbp+1C0h] BYREF
  int *v323; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v324[16]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v325[16]; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int128 v326; // [rsp+2F8h] [rbp+1F0h]
  _BYTE v327[48]; // [rsp+318h] [rbp+210h] BYREF
  __int64 v328; // [rsp+348h] [rbp+240h]
  __int128 v329; // [rsp+358h] [rbp+250h] BYREF
  __int64 v330; // [rsp+368h] [rbp+260h]
  __int128 v331; // [rsp+370h] [rbp+268h] BYREF
  __int64 v332; // [rsp+380h] [rbp+278h]
  _BYTE v333[32]; // [rsp+388h] [rbp+280h] BYREF
  char v334[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  char v335[16]; // [rsp+3B8h] [rbp+2B0h] BYREF
  char v336[16]; // [rsp+3C8h] [rbp+2C0h] BYREF
  char v337[16]; // [rsp+3D8h] [rbp+2D0h] BYREF
  char v338[16]; // [rsp+3E8h] [rbp+2E0h] BYREF
  char v339[16]; // [rsp+3F8h] [rbp+2F0h] BYREF
  char v340[16]; // [rsp+408h] [rbp+300h] BYREF
  char v341[16]; // [rsp+418h] [rbp+310h] BYREF
  char v342[16]; // [rsp+428h] [rbp+320h] BYREF
  char v343[16]; // [rsp+438h] [rbp+330h] BYREF
  char v344[16]; // [rsp+448h] [rbp+340h] BYREF
  char v345[16]; // [rsp+458h] [rbp+350h] BYREF
  char v346[16]; // [rsp+468h] [rbp+360h] BYREF
  char v347[16]; // [rsp+478h] [rbp+370h] BYREF
  char v348[16]; // [rsp+488h] [rbp+380h] BYREF
  __int64 v349[3]; // [rsp+498h] [rbp+390h] BYREF
  char v350[24]; // [rsp+4B0h] [rbp+3A8h] BYREF
  char v351[24]; // [rsp+4C8h] [rbp+3C0h] BYREF
  const wchar_t *v352; // [rsp+4E0h] [rbp+3D8h] BYREF
  _OWORD v353[3]; // [rsp+4E8h] [rbp+3E0h] BYREF
  __int128 v354; // [rsp+518h] [rbp+410h]
  __int128 v355; // [rsp+528h] [rbp+420h]
  char v356[64]; // [rsp+538h] [rbp+430h] BYREF
  char v357[16]; // [rsp+578h] [rbp+470h] BYREF
  char v358[64]; // [rsp+588h] [rbp+480h] BYREF
  char v359[64]; // [rsp+5C8h] [rbp+4C0h] BYREF
  char v360[64]; // [rsp+608h] [rbp+500h] BYREF
  __int128 v361; // [rsp+648h] [rbp+540h]
  __int64 v362; // [rsp+658h] [rbp+550h]
  __int64 v363; // [rsp+660h] [rbp+558h]
  char v364[64]; // [rsp+668h] [rbp+560h] BYREF
  __int64 v365; // [rsp+6A8h] [rbp+5A0h]
  __int64 v366; // [rsp+6B8h] [rbp+5B0h] BYREF
  _QWORD *v367; // [rsp+6C0h] [rbp+5B8h] BYREF
  unsigned __int64 v368; // [rsp+6C8h] [rbp+5C0h]
  __int64 v369[2]; // [rsp+6D0h] [rbp+5C8h] BYREF
  __int64 v370[2]; // [rsp+6E0h] [rbp+5D8h] BYREF
  bool v371; // [rsp+6F0h] [rbp+5E8h] BYREF
  bool v372; // [rsp+6F1h] [rbp+5E9h] BYREF
  __int128 v373; // [rsp+6F8h] [rbp+5F0h] BYREF
  _QWORD *v374; // [rsp+708h] [rbp+600h]
  wchar_t *Str; // [rsp+710h] [rbp+608h] BYREF
  __int128 v376; // [rsp+718h] [rbp+610h] BYREF
  __int64 v377; // [rsp+728h] [rbp+620h]
  __int64 v378[2]; // [rsp+730h] [rbp+628h] BYREF
  _QWORD v379[2]; // [rsp+740h] [rbp+638h] BYREF
  __int64 v380; // [rsp+750h] [rbp+648h] BYREF
  __int64 v381; // [rsp+758h] [rbp+650h]
  __int64 v382[2]; // [rsp+760h] [rbp+658h] BYREF
  int v383; // [rsp+770h] [rbp+668h] BYREF
  int v384; // [rsp+774h] [rbp+66Ch] BYREF
  __int64 v385[2]; // [rsp+778h] [rbp+670h] BYREF
  int v386; // [rsp+788h] [rbp+680h] BYREF
  int v387; // [rsp+78Ch] [rbp+684h] BYREF
  int v388; // [rsp+790h] [rbp+688h] BYREF
  int v389; // [rsp+794h] [rbp+68Ch] BYREF
  int v390; // [rsp+798h] [rbp+690h] BYREF
  int v391; // [rsp+79Ch] [rbp+694h] BYREF
  int v392; // [rsp+7A0h] [rbp+698h] BYREF
  int v393; // [rsp+7A4h] [rbp+69Ch] BYREF
  int v394; // [rsp+7A8h] [rbp+6A0h] BYREF
  int v395; // [rsp+7ACh] [rbp+6A4h] BYREF
  int v396; // [rsp+7B0h] [rbp+6A8h] BYREF
  int v397; // [rsp+7B4h] [rbp+6ACh] BYREF
  int v398; // [rsp+7B8h] [rbp+6B0h] BYREF
  int v399; // [rsp+7BCh] [rbp+6B4h] BYREF
  int v400; // [rsp+7C0h] [rbp+6B8h] BYREF
  int v401; // [rsp+7C4h] [rbp+6BCh] BYREF
  int v402; // [rsp+7C8h] [rbp+6C0h] BYREF
  int v403; // [rsp+7CCh] [rbp+6C4h] BYREF
  int v404; // [rsp+7D0h] [rbp+6C8h] BYREF
  int v405; // [rsp+7D4h] [rbp+6CCh] BYREF
  int v406; // [rsp+7D8h] [rbp+6D0h] BYREF
  int v407; // [rsp+7DCh] [rbp+6D4h] BYREF
  int v408; // [rsp+7E0h] [rbp+6D8h] BYREF
  int v409; // [rsp+7E4h] [rbp+6DCh] BYREF
  int v410; // [rsp+7E8h] [rbp+6E0h] BYREF
  int v411; // [rsp+7ECh] [rbp+6E4h] BYREF
  int v412; // [rsp+7F0h] [rbp+6E8h] BYREF
  int v413; // [rsp+7F4h] [rbp+6ECh] BYREF
  int v414; // [rsp+7F8h] [rbp+6F0h] BYREF
  int v415; // [rsp+7FCh] [rbp+6F4h] BYREF
  int v416; // [rsp+800h] [rbp+6F8h] BYREF
  int v417; // [rsp+804h] [rbp+6FCh] BYREF
  int v418; // [rsp+808h] [rbp+700h] BYREF
  int v419; // [rsp+80Ch] [rbp+704h] BYREF
  int v420; // [rsp+810h] [rbp+708h] BYREF
  int v421; // [rsp+814h] [rbp+70Ch] BYREF
  int v422; // [rsp+818h] [rbp+710h] BYREF
  int v423; // [rsp+81Ch] [rbp+714h] BYREF
  int v424; // [rsp+820h] [rbp+718h] BYREF
  int v425; // [rsp+824h] [rbp+71Ch] BYREF
  int v426; // [rsp+828h] [rbp+720h] BYREF
  int v427; // [rsp+82Ch] [rbp+724h] BYREF
  int v428; // [rsp+830h] [rbp+728h] BYREF
  int v429; // [rsp+834h] [rbp+72Ch] BYREF
  int v430; // [rsp+838h] [rbp+730h] BYREF
  int v431; // [rsp+83Ch] [rbp+734h] BYREF
  __int128 v432; // [rsp+840h] [rbp+738h] BYREF
  __int64 v433; // [rsp+850h] [rbp+748h]
  __int64 v434[2]; // [rsp+858h] [rbp+750h] BYREF
  __int128 v435; // [rsp+868h] [rbp+760h] BYREF
  __int64 v436; // [rsp+878h] [rbp+770h]
  __int128 v437; // [rsp+880h] [rbp+778h] BYREF
  __int64 v438; // [rsp+890h] [rbp+788h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]

  v328 = -2;
  v260 = a3;
  v258 = a2;
  LogAdapter::TraceInfo<>("arbiter: Evaluating features for installation");
  v250[4] = *(_BYTE *)(*((_QWORD *)this + 12) + 304LL);
  v381 = 0;
  v4 = operator new(0x40u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v380 = (__int64)v4;
  std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(
    v434,
    *((_QWORD *)this + 12) + 176LL);
  v6 = **(__int64 ***)(*((_QWORD *)this + 12) + 160LL);
  while ( !*((_BYTE *)v6 + 25) )
  {
    v250[0] = 1;
    if ( !*((_BYTE *)this + 121)
      || ((unsigned __int64)v6[7] <= 7 ? (v7 = (const wchar_t *)(v6 + 4)) : (v7 = (const wchar_t *)v6[4]),
          CDeviceInfo::MatchNameValueSetPair(*((CDeviceInfo **)this + 12), L"UserProfileLanguage", v7, v5, v250),
          v250[0]) )
    {
      v10 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
              (__int64)&v380,
              v349,
              v6 + 4);
      v11 = *(_OWORD *)v10;
      if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
              v12,
              v10[2],
              v6 + 4) )
      {
        if ( v381 == 0x3FFFFFFFFFFFFFFLL )
          std::_Throw_tree_length_error();
        v13 = v380;
        v267[1] = &v380;
        v268 = 0;
        v268 = (__int64 *)operator new(0x40u);
        std::wstring::wstring(v268 + 4, v6 + 4);
        *v268 = v13;
        v268[1] = v13;
        v268[2] = v13;
        *((_BYTE *)v268 + 24) = 0;
        *((_BYTE *)v268 + 25) = 0;
        v14 = v268;
        v268 = 0;
        v262 = v11;
        std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v380, &v262, v14);
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
  v379[0] = 0;
  v379[1] = 0;
  v16 = operator new(0x48u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  v379[0] = v16;
  v382[0] = 0;
  v382[1] = 0;
  v17 = operator new(0x30u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  v382[0] = (__int64)v17;
  v378[0] = 0;
  v378[1] = 0;
  v18 = operator new(0x30u);
  *v18 = v18;
  v18[1] = v18;
  v18[2] = v18;
  *((_WORD *)v18 + 12) = 257;
  v378[0] = (__int64)v18;
  v385[0] = 0;
  v385[1] = 0;
  v19 = operator new(0x30u);
  *v19 = v19;
  v19[1] = v19;
  v19[2] = v19;
  *((_WORD *)v19 + 12) = 257;
  v385[0] = (__int64)v19;
  v366 = 0;
  v367 = 0;
  v368 = 0;
  v20 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v20 = v20;
  *(_QWORD *)(v20 + 8) = v20;
  *(_QWORD *)(v20 + 16) = v20;
  *(_WORD *)(v20 + 24) = 257;
  v367 = (_QWORD *)v20;
  v369[0] = 0;
  v369[1] = 0;
  v21 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v21 = v21;
  *(_QWORD *)(v21 + 8) = v21;
  *(_QWORD *)(v21 + 16) = v21;
  *(_WORD *)(v21 + 24) = 257;
  v369[0] = v21;
  v370[0] = 0;
  v370[1] = 0;
  v22 = std::_Allocate<16,std::_Default_allocate_traits>(40);
  *(_QWORD *)v22 = v22;
  *(_QWORD *)(v22 + 8) = v22;
  *(_QWORD *)(v22 + 16) = v22;
  *(_WORD *)(v22 + 24) = 257;
  v370[0] = v22;
  DeferredUpdateRequests = CUpdateEvaluator::GetDeferredUpdateRequests(this, v258, v379);
  v24 = DeferredUpdateRequests;
  if ( DeferredUpdateRequests < 0 )
  {
    v403 = DeferredUpdateRequests;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get deferred updates");
      v309 = &v403;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v309);
    }
    v25 = 4676;
    goto LABEL_44;
  }
  v26 = *(_QWORD *)v379[0];
  v255 = *(_QWORD *)v379[0];
  while ( !*(_BYTE *)(v26 + 25) )
  {
    v384 = 0;
    v383 = 0;
    v371 = 0;
    v372 = 0;
    v27 = *(struct CUpdateEvaluator::FeatureRequest **)(v26 + 64);
    v259 = v27;
    v28 = CUpdateEvaluator::EvaluateModifyRequest(
            this,
            v27,
            (enum FeatureIntentFlags *)&v384,
            (enum FeatureIntentFlags *)&v383,
            &v371,
            &v372);
    if ( v28 < 0 )
    {
      v402 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to evaluate deferred update; skipping: {0}",
          (__int64)v27 + 24);
        *(_QWORD *)v310 = &v402;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v310);
      }
      v32 = 4687;
      goto LABEL_37;
    }
    *(_DWORD *)(*(_QWORD *)v27 + 16LL) = v384;
    *(_DWORD *)(*(_QWORD *)v27 + 20LL) = v383;
    v29 = (__int64 *)((char *)v27 + 8);
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v385,
      (__int64)&v262,
      v29,
      (__int64 *)&v259);
    if ( v372 )
    {
      v30 = v270;
      v31 = v378;
    }
    else
    {
      if ( !v371 )
        goto LABEL_33;
      v30 = v269;
      v31 = v382;
    }
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
      v31,
      (__int64)v30,
      v29,
      (__int64 *)&v259);
LABEL_33:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v255);
    v26 = v255;
  }
  v264 = 0;
  NameValuePairValue = CDeviceInfo::GetNameValuePairValue(
                         *((CDeviceInfo **)this + 12),
                         L"EditionVersion",
                         (const wchar_t **)&v264,
                         0);
  v24 = NameValuePairValue;
  if ( NameValuePairValue < 0 )
  {
    v400 = NameValuePairValue;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get device OS version");
      *(_QWORD *)v311 = &v400;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v311);
    }
    v25 = 4722;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      v248);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
    if ( !v366 )
      goto LABEL_716;
    goto LABEL_715;
  }
  v261 = 0;
  v259 = 0;
  String1 = 0;
  v255 = 0;
  v271 = 0;
  v37 = 0;
  Buf1 = 0;
  v265 = 0;
  v38 = 0;
  v251 = 0;
  v256 = 0;
  v39 = (struct CCompositionDatabase::Feature *)*((_QWORD *)v258 + 5);
  v266 = (struct CCompositionDatabase::Feature *)((char *)v39 + 8 * *((_QWORD *)v258 + 3));
  v40 = 4505604;
  v41 = v39 == v266;
  while ( 2 )
  {
    v252 = v39;
    if ( !v41 )
    {
      v42 = *(__int64 **)(*(_QWORD *)v39 + 48LL);
      n = (const wchar_t *const **)&v42[*(_QWORD *)(*(_QWORD *)v39 + 32LL)];
      if ( v42 == (__int64 *)n )
      {
LABEL_98:
        v39 = (struct CCompositionDatabase::Feature *)((char *)v39 + 8);
        v41 = v39 == v266;
        continue;
      }
      while ( 1 )
      {
        v43 = *v42;
        v44 = *(_BYTE *)(*v42 + 368);
        if ( ((v44 - 11) & 0xFA) != 0 || v44 == 16 )
          goto LABEL_97;
        LOBYTE(v35) = 0;
        if ( v44 == 12 )
        {
          v45 = *((_DWORD *)this + 12);
          if ( v45 <= 0x16 )
            LOBYTE(v35) = _bittest(&v40, v45);
        }
        v46 = *(struct CCompositionDatabase::ConditionSet **)v43;
        if ( *(_QWORD *)v43 )
        {
          v47 = L"repair";
        }
        else
        {
          v46 = *(struct CCompositionDatabase::ConditionSet **)(v43 + 8);
          v47 = L"install";
          if ( !v46 )
            v47 = &String2;
        }
        v352 = v47;
        v250[0] = 0;
        if ( v46 )
        {
          if ( (_BYTE)v35 )
          {
            LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
              (unsigned int)"Conditional evaluation skipped for {0}: Group: {1}, FMID: {2}, Feature: {3}",
              (unsigned int)&v352,
              *(_DWORD *)v42 + 72,
              *(_DWORD *)v42 + 64,
              *v42 + 56);
          }
          else
          {
            v28 = CUpdateEvaluator::EvaluateConditional(this, v46, v250);
            if ( v28 < 0 )
            {
              v399 = v28;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t const *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of {0} feature conditional FMID: {1}, Feature: {2}",
                  &v352,
                  *v42 + 64,
                  *v42 + 56);
                v313 = &v399;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)&v313);
              }
              v32 = 4770;
LABEL_37:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v32,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)(unsigned int)v28,
                v248);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
              if ( v366 )
                goto LABEL_38;
              goto LABEL_39;
            }
            if ( !v250[0] )
            {
              LogAdapter::TraceInfo<wchar_t const *,wchar_t *,wchar_t *,wchar_t *>(
                (unsigned int)"Feature not needed for {0}: Group: {1}, FMID: {2}, Feature: {3}",
                (unsigned int)&v352,
                *(_DWORD *)v42 + 72,
                *(_DWORD *)v42 + 64,
                *v42 + 56);
              goto LABEL_96;
            }
          }
        }
        v48 = *v42;
        v49 = *(_BYTE *)(*v42 + 368);
        if ( v49 == 11 )
        {
          v50 = *(wchar_t ***)(v48 + 120);
          v51 = &v50[*(_QWORD *)(v48 + 104)];
          if ( v50 != v51 )
          {
            v52 = String1;
            v53 = v255;
            v54 = v261;
            v35 = 0;
            do
            {
              if ( !v54
                || (v55 = CompareVersionString(*((_QWORD *)v54 + 2), *((_QWORD *)*v50 + 2), v43, 0), v35 = 0, v55 < 0) )
              {
                v54 = *v50;
                v259 = (struct CCompositionDatabase::Feature *)*v42;
              }
              if ( *((_DWORD *)*v50 + 80) == 16 )
              {
                if ( (v56 = *((_QWORD *)this + 12), *(_BYTE *)(v56 + 236))
                  || *(_QWORD *)(v56 + 240) != *(_QWORD *)(v56 + 248)
                  || !v264
                  || (v57 = *((_DWORD *)this + 12), v57 <= 0x16) && (v43 = 4505600, _bittest((const int *)&v43, v57))
                  || (v58 = CompareVersionString(v264, *((_QWORD *)*v50 + 3), v43, 0), v35 = 0, v58 < 0) )
                {
                  if ( !v52
                    || (v59 = CompareVersionString(*((_QWORD *)v52 + 2), *((_QWORD *)*v50 + 2), v43, 0), v35 = 0, v59 < 0) )
                  {
                    v271 = (struct CCompositionDatabase::Feature *)v53;
                    v52 = *v50;
                    v53 = *v42;
                  }
                }
              }
              ++v50;
            }
            while ( v50 != v51 );
            v261 = v54;
            v255 = v53;
            String1 = v52;
            v39 = v252;
            v37 = Buf1;
LABEL_78:
            v38 = v251;
          }
        }
        else
        {
          if ( v49 != 12 )
          {
            if ( v49 == 15 )
            {
              v62 = *(const wchar_t *const ***)(v48 + 120);
              v63 = &v62[*(_QWORD *)(v48 + 104)];
              if ( v62 != v63 )
              {
                do
                {
                  if ( !v38 || (int)CompareVersionString(*((_QWORD *)v38 + 2), *((_QWORD *)*v62 + 2), v43, v35) < 0 )
                  {
                    v38 = *v62;
                    v256 = (const wchar_t ***)*v42;
                  }
                  ++v62;
                }
                while ( v62 != v63 );
                v251 = v38;
                v39 = v252;
              }
            }
            goto LABEL_96;
          }
          v60 = *(_QWORD *)(v48 + 120);
          v61 = v60 + 8LL * *(_QWORD *)(v48 + 104);
          if ( v60 != v61 )
          {
            do
            {
              if ( !v37 || (int)CompareVersionString(v37[2], *(_QWORD *)(*(_QWORD *)v60 + 16LL), v43, v35) < 0 )
              {
                v37 = *(_QWORD **)v60;
                v265 = (struct CCompositionDatabase::Feature *)*v42;
              }
              v60 += 8;
            }
            while ( v60 != v61 );
            Buf1 = v37;
            goto LABEL_78;
          }
        }
LABEL_96:
        v40 = 4505604;
LABEL_97:
        if ( ++v42 == (__int64 *)n )
          goto LABEL_98;
      }
    }
    break;
  }
  v64 = v258;
  v266 = (struct CCompositionDatabase::Feature *)(*((_DWORD *)v258 + 108) & 0x800);
  v65 = (const wchar_t *const **)*((_QWORD *)v258 + 5);
  n = v65;
  *(_QWORD *)&v262 = &v65[*((_QWORD *)v258 + 3)];
  if ( v65 == (const wchar_t *const **)v262 )
    goto LABEL_124;
  v66 = 0;
  while ( 2 )
  {
    v67 = *v65;
    v251 = v67;
    FeatureGroupOnDevice = CUpdateEvaluator::FindFeatureGroupOnDevice(this, *v67);
    if ( FeatureGroupOnDevice )
      *((_BYTE *)FeatureGroupOnDevice + 8) = 1;
    else
      LogAdapter::TraceInfo<wchar_t const *>(
        "No installed features to update in Group {0}; evaluating features for conditional install",
        v67);
    v69 = (wchar_t *)*((_QWORD *)v67 + 6);
    v270[0] = &v69[4 * *((_QWORD *)v67 + 4)];
    v70 = v69 == (wchar_t *)v270[0];
    while ( 2 )
    {
      v264 = v69;
      if ( !v70 )
      {
        v71 = *(struct CCompositionDatabase::Feature **)v69;
        v252 = v71;
        v72 = 0;
        v250[2] = 0;
        v73 = 0;
        v250[0] = 0;
        v250[3] = 0;
        QualifiedFeatureId = GetQualifiedFeatureId(v71, &v366);
        v24 = QualifiedFeatureId;
        if ( QualifiedFeatureId < 0 )
        {
          v420 = QualifiedFeatureId;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              *(__int64 *)&LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting qualified feature Id");
            v291 = &v420;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&v291);
          }
          goto LABEL_714;
        }
        if ( *((_BYTE *)v71 + 368) == 11 )
        {
          v75 = v255;
          if ( v255 || v259 )
          {
            if ( CDeviceInfo::IsNameValuePairEqual(*((CDeviceInfo **)this + 12), L"WindowsPE", L"1") && v71 != v259 )
            {
              v76 = "Feature baselines not applicable for WinPE: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_116:
              v77 = v251;
LABEL_117:
              v78 = (char *)v71 + 56;
LABEL_118:
              LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v76, v77, (char *)v71 + 64, v78);
LABEL_119:
              v66 = 0;
LABEL_120:
              v69 = v264 + 4;
              v70 = v264 + 4 == (wchar_t *)v270[0];
              continue;
            }
            if ( v271 )
            {
              v82 = v261;
              if ( v71 == v271 )
              {
                if ( (struct CCompositionDatabase::Feature *)v75 == v259 )
                {
                  if ( *((_DWORD *)v261 + 80) == 16 )
                    goto LABEL_135;
                }
                else if ( *((_DWORD *)v261 + 80) != 16 )
                {
                  v76 = "Feature N-1 baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_116;
                }
              }
            }
            else
            {
              v82 = v261;
            }
            if ( v71 != (struct CCompositionDatabase::Feature *)v75 )
            {
              if ( v71 == v259 )
                goto LABEL_135;
LABEL_143:
              v76 = "Feature baseline not applicable: Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_116;
            }
            if ( (struct CCompositionDatabase::Feature *)v75 != v259 && *((_DWORD *)v82 + 80) == 16 )
              goto LABEL_143;
          }
        }
LABEL_135:
        v83 = *((_BYTE *)v71 + 368);
        if ( v83 == 12 )
        {
          v84 = v71 == v265;
        }
        else
        {
          if ( v83 != 15 )
            goto LABEL_147;
          v84 = v71 == (struct CCompositionDatabase::Feature *)v256;
        }
        if ( !v84 )
        {
LABEL_149:
          v76 = "Feature not applicable: Group: {0}, FMID: {1}, Feature: {2}";
          goto LABEL_116;
        }
LABEL_147:
        v85 = *((_DWORD *)this + 12);
        if ( v85 == 25 && v83 != 25 )
          goto LABEL_149;
        v250[1] = 0;
        if ( v266 )
        {
          v72 = 1;
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            (__int64 *)&v367,
            (__int64)v347,
            (__int64 *)&v252);
          v86 = "Feature added due to standalone compDB: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_152:
          v71 = v252;
          goto LABEL_153;
        }
        if ( v85 != 1 && v85 != 19 )
        {
          if ( (v85 == 2 || v85 == 22) && (*((_BYTE *)v71 + 368) == 14 || *((_BYTE *)v71 + 368) == 9) )
          {
            v72 = 1;
            std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
              (__int64 *)&v367,
              (__int64)v339,
              (__int64 *)&v252);
            v86 = "Feature added due to default desktop upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_152;
          }
          v91 = *((_DWORD *)this + 12);
          if ( v91 > 0x16 || (v92 = 4505604, !_bittest(&v92, v91)) )
          {
LABEL_181:
            if ( *((_DWORD *)this + 12) == 24 )
            {
              if ( *((_BYTE *)v71 + 368) == 27 )
              {
                v104 = *((_QWORD *)v71 + 7);
                v105 = 0;
                v106 = 0;
                v326 = 0;
                if ( v104 )
                {
                  v107 = -1;
                  do
                    ++v107;
                  while ( *(_WORD *)(v104 + 2 * v107) );
                  *(_QWORD *)&v326 = 2 * v107;
                  *((_QWORD *)&v326 + 1) = 2 * v107 + 2;
                  v106 = v104;
                  v105 = v326;
                }
                v329 = v105;
                v330 = v106;
                if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                                        ___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HH__0GJ__0GO__0HC__0GF__0FP__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                                        &v329,
                                        0) )
                  goto LABEL_183;
              }
              if ( *((_BYTE *)v71 + 368) == 12 )
                goto LABEL_183;
            }
            else if ( *((_BYTE *)v71 + 368) != 27 )
            {
LABEL_183:
              if ( CUpdateEvaluator::FindFeatureOnDevice(this, v71) )
              {
                v108 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 6);
                if ( v108 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v108, v250);
                  if ( v24 < 0 )
                  {
                    v391 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v305 = &v391;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&v305);
                    }
                    v111 = 5325;
LABEL_227:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v111,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      v248);
LABEL_714:
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
                    if ( !v366 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v73 = v250[0];
                  v109 = v251;
                  if ( v250[0] )
                  {
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v251,
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      v370,
                      (__int64)v335,
                      (__int64 *)&v252);
                    v71 = v252;
                    v110 = CActionListCreator::DisableFeature(v260, v252);
                    v24 = v110;
                    if ( v110 < 0 )
                    {
                      v392 = v110;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                          (char *)v71 + 72,
                          (char *)v71 + 64,
                          (char *)v71 + 56);
                        *(_QWORD *)v292 = &v392;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          1,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                          (__int64)v292);
                      }
                      v111 = 5336;
                      goto LABEL_227;
                    }
                  }
                }
                else
                {
                  v109 = v251;
                }
                v112 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 2);
                if ( v112 )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v112, &v250[3]);
                  if ( v24 < 0 )
                  {
                    v390 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of remove feature conditional FMID: {0}, Feature: {1}",
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v303 = &v390;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&v303);
                    }
                    v111 = 5348;
                    goto LABEL_227;
                  }
                  v66 = v250[3];
                  if ( v250[3] )
                  {
                    Buf1 = 0;
                    v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                    if ( v24 < 0 )
                    {
                      v412 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<AutoScz>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed creating pending request for {0}",
                          &v366);
                        v304 = &v412;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          1,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                          (__int64)&v304);
                      }
                      v146 = 5360;
                      goto LABEL_713;
                    }
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                      v378,
                      (__int64)v336,
                      (__int64 *)&v252,
                      (__int64 *)&Buf1);
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v109,
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                  }
                }
                if ( v73 && v66 )
                {
                  v24 = -2146467821;
                  v389 = -2146467821;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Conflicting preload and removal feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                      v109,
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                    v302 = &v389;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v302);
                  }
                  v113 = 5370;
                  goto LABEL_377;
                }
                if ( !v66 )
                {
                  if ( *((_BYTE *)this + 121) )
                  {
                    v114 = *((_BYTE *)v71 + 368);
                    if ( v114 == 6 || v114 == 13 || v114 == 5 && *(_BYTE *)(*((_QWORD *)this + 12) + 330LL) )
                    {
                      Str = 0;
                      v250[3] = 1;
                      Buf1 = 0;
                      String1 = 0;
                      v115 = SczAllocFromSz(&Str, *((_QWORD *)v71 + 7));
                      v24 = v115;
                      if ( v115 < 0 )
                      {
                        v147 = (unsigned int)v115;
                        v148 = 5390;
LABEL_382:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v148,
                          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                          (const char *)v147,
                          v248);
                        if ( Str )
                        {
                          operator delete(Str - 4, v149);
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
                        v387 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<AutoScz>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed shredding feature ID: {0}",
                            &Str);
                          v300 = &v387;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(__int64 *)&LogAdapter::g_Logger,
                            1,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                            (__int64)&v300);
                        }
                        v147 = (unsigned int)v24;
                        v148 = 5394;
                        goto LABEL_382;
                      }
                      v118 = (const wchar_t *)Buf1;
                      if ( Buf1 )
                      {
                        if ( *((_BYTE *)v71 + 368) == 5 )
                        {
                          v119 = String1;
                          if ( wcsicmp(String1, L"Language.TextToSpeech") )
                          {
                            if ( wcsicmp(v119, L"Language.Speech") && wcsicmp(v119, L"Language.LocaleData") )
                              v118 = 0;
                          }
                        }
                        if ( v118 )
                        {
                          CDeviceInfo::MatchNameValueSetPair(
                            *((CDeviceInfo **)this + 12),
                            L"UserProfileLanguage",
                            v118,
                            v117,
                            &v250[3]);
                          v66 = !v250[3];
                        }
                      }
                      if ( Str )
                      {
                        operator delete(Str - 4, v116);
                        Str = 0;
                      }
                      if ( v66 )
                      {
                        Buf1 = 0;
                        v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                        if ( v24 < 0 )
                        {
                          v388 = v24;
                          if ( *(_QWORD *)&LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<AutoScz>(
                              *(_QWORD *)&LogAdapter::g_Logger,
                              0,
                              3,
                              "Failed creating pending request for {0}",
                              &v366);
                            *(_QWORD *)v301 = &v388;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              *(__int64 *)&LogAdapter::g_Logger,
                              1,
                              3,
                              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                              (__int64)v301);
                          }
                          v113 = 5430;
LABEL_377:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v113,
                            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                            (const char *)(unsigned int)v24,
                            v248);
LABEL_384:
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
                          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
                          if ( !v366 )
                            goto LABEL_716;
LABEL_715:
                          operator delete((void *)(v366 - 8), v36);
                          v366 = 0;
                          goto LABEL_716;
                        }
                        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                          v378,
                          (__int64)v337,
                          (__int64 *)&v252,
                          (__int64 *)&Buf1);
                        LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                          "Feature (LanguagePack) removed because it was unused: Group: {0}, FMID: {1}, Feature: {2}",
                          v109,
                          (char *)v71 + 64,
                          (char *)v71 + 56);
                      }
                    }
                  }
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                  v378,
                  v267,
                  &v252);
                if ( v267[0] != v378[0] )
                {
                  *(_BYTE *)(*(_QWORD *)(v267[0] + 40LL) + 33LL) = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    v369,
                    (__int64)v338,
                    (__int64 *)&v252);
                  v71 = v252;
                  if ( !v66 )
                  {
                    v66 = 1;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature removed due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
                      (char *)v252 + 72,
                      (char *)v252 + 64,
                      (char *)v252 + 56);
                  }
                }
                if ( *((_BYTE *)v71 + 369) )
                  goto LABEL_119;
                if ( (unsigned __int8)(*((_BYTE *)v71 + 368) - 22) <= 1u )
                {
                  AppMainPackageFromInstalledFeature = CDeviceInfo::GetAppMainPackageFromInstalledFeature(
                                                         *((CDeviceInfo **)this + 12),
                                                         *((const wchar_t *const *)v71 + 7));
                  IsStubAppFeatureInstalled = CDeviceInfo::IsStubAppFeatureInstalled(
                                                *((CDeviceInfo **)this + 12),
                                                *((const wchar_t *const *)v71 + 7));
                  if ( AppMainPackageFromInstalledFeature )
                  {
                    LOBYTE(v122) = IsStubAppFeatureInstalled;
                    if ( !(unsigned __int8)IsPreInstalledAppApplicable(v71, AppMainPackageFromInstalledFeature, v122) )
                    {
                      v78 = (char *)v71 + 56;
                      v77 = v109;
                      v76 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as newer MSIX application is already installed";
                      goto LABEL_118;
                    }
                  }
                }
                if ( *((_BYTE *)v71 + 368) == 24
                  && CDeviceInfo::GetEdgePackageFromInstalledFeature(
                       *((CDeviceInfo **)this + 12),
                       *((const wchar_t *const *)v71 + 7)) )
                {
                  v123 = *((_QWORD *)v71 + 15);
                  v124 = v123 + 8LL * *((_QWORD *)v71 + 13);
                  while ( 1 )
                  {
                    if ( v123 == v124 )
                      goto LABEL_275;
                    if ( *(_DWORD *)(*(_QWORD *)v123 + 320LL) == 17 )
                      break;
                    v123 += 8;
                  }
                  v77 = v109;
                  v76 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as Edge package is not applicable";
                  goto LABEL_117;
                }
LABEL_275:
                if ( *((_BYTE *)v71 + 368) == 25 )
                {
                  UUPPackageFromInstalledFeature = CDeviceInfo::GetUUPPackageFromInstalledFeature(
                                                     *((CDeviceInfo **)this + 12),
                                                     *((const wchar_t *const *)v71 + 7));
                  if ( UUPPackageFromInstalledFeature )
                  {
                    if ( !(unsigned __int8)IsUUPProductApplicable(v71, UUPPackageFromInstalledFeature) )
                    {
                      v77 = v109;
                      v76 = "Not applicable Group: {0}, FMID: {1}, Feature: {2} as UUP product is not applicable";
                      goto LABEL_117;
                    }
                  }
                }
                v72 = 1;
                if ( v66 )
                  goto LABEL_154;
                v86 = "Feature added due to default upgrade evaluation: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_153:
                LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v86, v251, (char *)v71 + 64, (char *)v71 + 56);
LABEL_154:
                v66 = 0;
LABEL_155:
                Buf1 = 0;
                v24 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&Buf1);
                if ( v24 < 0 )
                {
                  v421 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<AutoScz>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed creating pending request for {0}",
                      &v366);
                    v315 = &v421;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v315);
                  }
                  v96 = 5524;
                  goto LABEL_392;
                }
                std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
                  v382,
                  (__int64)v327,
                  (__int64 *)&v252,
                  (__int64 *)&Buf1);
                goto LABEL_157;
              }
              v94 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 1);
              v66 = 0;
              if ( v94 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v94, &v250[2]);
                if ( v24 < 0 )
                {
                  v396 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                    v320 = &v396;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v320);
                  }
                  v96 = 5287;
                  goto LABEL_392;
                }
                v72 = v250[2];
                if ( v250[2] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v251,
                    (char *)v71 + 64,
                    (char *)v71 + 56);
                  v250[1] = 1;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    (__int64 *)&v367,
                    (__int64)v334,
                    (__int64 *)&v252);
                  v71 = v252;
                }
              }
              v95 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 6);
              if ( v95 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(this, v95, v250);
                if ( v24 < 0 )
                {
                  v393 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                    v323 = &v393;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v323);
                  }
                  v96 = 5302;
                  goto LABEL_392;
                }
                if ( v250[0] )
                {
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v251,
                    (char *)v71 + 64,
                    (char *)v71 + 56);
                  v24 = CActionListCreator::DisableFeature(v260, v71);
                  if ( v24 < 0 )
                  {
                    v394 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                        (char *)v71 + 72,
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v322 = &v394;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&v322);
                    }
                    v145 = 5311;
LABEL_403:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v145,
                      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                      (const char *)(unsigned int)v24,
                      v248);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
                    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
                    if ( !v366 )
                      goto LABEL_716;
                    goto LABEL_715;
                  }
                  v66 = 0;
                  if ( v72 )
                  {
                    v24 = -2146467821;
                    v395 = -2146467821;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                        v251,
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v321 = &v395;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&v321);
                    }
                    v96 = 5317;
                    goto LABEL_392;
                  }
                }
              }
              goto LABEL_345;
            }
            v77 = (const wchar_t *const *)((char *)v71 + 72);
            v76 = "Not including Group: {}, FMID: {}, Feature: {}";
            goto LABEL_117;
          }
          v93 = *((_BYTE *)v71 + 368);
          if ( v93 != 7 )
          {
            if ( (unsigned __int8)(v93 - 11) <= 1u || v93 == 8 )
            {
LABEL_201:
              v66 = 0;
LABEL_202:
              if ( *((_BYTE *)v71 + 368) == 20 )
              {
                Buf1 = 0;
                v24 = CDeviceInfo::GetNameValuePairValue(
                        *((CDeviceInfo **)this + 12),
                        L"HotPatchReadiness",
                        (const wchar_t **)&Buf1,
                        0);
                if ( v24 < 0 )
                {
                  v397 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get hotpatch status");
                    v319 = &v397;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v319);
                  }
                  v96 = 5212;
                  goto LABEL_392;
                }
                if ( !Buf1 )
                  goto LABEL_209;
                v102 = -1;
                do
                  ++v102;
                while ( *((_WORD *)Buf1 + v102) );
                if ( 2 * v102 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
                {
LABEL_209:
                  v103 = "Feature excluded due to no hotpatching support: Group: {0}, FMID: {1}, Feature: {2}";
                  goto LABEL_210;
                }
              }
              v72 = 1;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                (__int64 *)&v367,
                (__int64)v348,
                (__int64 *)&v252);
              v101 = "Feature added due to default desktop upgrade, image-based reset, or media-based upgrade evaluation:"
                     " Group: {0}, FMID: {1}, Feature: {2}";
              v98 = v251;
              goto LABEL_342;
            }
            if ( v93 != 15 )
            {
              if ( v93 != 20 )
                goto LABEL_181;
              goto LABEL_201;
            }
          }
          v97 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 1);
          v66 = 0;
          if ( v97 )
          {
            v24 = CUpdateEvaluator::EvaluateConditional(this, v97, &v250[2]);
            if ( v24 < 0 )
            {
              v398 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                  (char *)v71 + 64,
                  (char *)v71 + 56);
                v318 = &v398;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)&v318);
              }
              v96 = 5188;
LABEL_392:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v96,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)(unsigned int)v24,
                v248);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
              std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
              if ( !v366 )
                goto LABEL_716;
              goto LABEL_715;
            }
            v72 = v250[2];
            v98 = v251;
            v99 = (char *)v71 + 64;
            v100 = (char *)v71 + 56;
            if ( v250[2] )
              v101 = "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            else
              v101 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
            goto LABEL_344;
          }
          goto LABEL_202;
        }
        LogAdapter::TraceInfo<wchar_t const *>("Looking to see if feature should be included: {0}", (char *)v71 + 56);
        v66 = 0;
        Buf1 = 0;
        v126 = *((unsigned __int8 *)v71 + 368);
        if ( v126 > 0xC )
        {
          v132 = v126 - 15;
          if ( !v132 )
            goto LABEL_307;
          v133 = v132 - 4;
          if ( !v133 )
            goto LABEL_307;
          v134 = v133 - 1;
          if ( !v134 )
          {
            v24 = CDeviceInfo::GetNameValuePairValue(
                    *((CDeviceInfo **)this + 12),
                    L"HotPatchReadiness",
                    (const wchar_t **)&Buf1,
                    0);
            if ( v24 < 0 )
            {
              v430 = v24;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get hotpatch status");
                *(_QWORD *)v298 = &v430;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v298);
              }
              v96 = 4961;
              goto LABEL_392;
            }
            if ( !Buf1 )
              goto LABEL_386;
            v140 = -1;
            do
              ++v140;
            while ( *((_WORD *)Buf1 + v140) );
            if ( 2 * v140 != 2 || strcmp((const char *)Buf1, (const char *)L"1") )
            {
LABEL_386:
              v24 = -2146467822;
              v386 = -2146467822;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Hotpatching is not supported on this machine/image.");
                v299 = &v386;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)&v299);
              }
              v96 = 4965;
              goto LABEL_392;
            }
            goto LABEL_307;
          }
          v135 = v134 - 5;
          if ( !v135 )
            goto LABEL_307;
          v131 = v135 == 1;
        }
        else
        {
          if ( v126 == 12 )
            goto LABEL_307;
          v127 = v126 - 2;
          if ( !v127 )
            goto LABEL_307;
          v128 = v127 - 1;
          if ( !v128 )
            goto LABEL_307;
          v129 = v128 - 4;
          if ( !v129 )
            goto LABEL_307;
          v130 = v129 - 2;
          if ( !v130 )
          {
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl) )
            {
LABEL_299:
              v136 = (char *)v71 + 64;
              v137 = (char *)v71 + 72;
              v138 = (char *)v71 + 56;
              v139 = "Not including Group: {0}, FMID: {1}, Feature: {2}";
              goto LABEL_300;
            }
LABEL_307:
            v141 = *((_BYTE *)v71 + 368);
            if ( (unsigned __int8)(v141 - 2) <= 1u )
            {
              v144 = v251;
              if ( !CDeviceInfo::GetInstalledFeature(
                      *((CDeviceInfo **)this + 12),
                      *((const wchar_t *const *)v71 + 7),
                      *((const wchar_t *const *)v71 + 8),
                      *v251) )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                (__int64 *)&v367,
                (__int64)v345,
                (__int64 *)&v252);
              v98 = v144;
              v101 = "Feature added for processing because it's already installed: Group: {0}, FMID: {1}, Feature: {2}";
            }
            else
            {
              if ( *(_QWORD *)v71 )
              {
                v24 = CUpdateEvaluator::EvaluateConditional(
                        this,
                        *(struct CCompositionDatabase::ConditionSet **)v71,
                        &v250[2]);
                if ( v24 < 0 )
                {
                  v429 = v24;
                  if ( *(_QWORD *)&LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                      *(_QWORD *)&LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed evaluation of repair feature conditional FMID: {0}, Feature: {1}",
                      (char *)v71 + 64,
                      (char *)v71 + 56);
                    v297 = &v429;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      *(__int64 *)&LogAdapter::g_Logger,
                      1,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                      (__int64)&v297);
                  }
                  v96 = 5033;
                  goto LABEL_392;
                }
                v72 = v250[2];
                if ( v250[2] )
                {
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    (__int64 *)&v367,
                    (__int64)v346,
                    (__int64 *)&v252);
                  v101 = "Feature added due to repair conditional: Group: {0}, FMID: {1}, Feature: {2}";
                  v71 = v252;
                }
                else
                {
                  v101 = "Feature not needed for repair: Group: {0}, FMID: {1}, Feature: {2}";
                }
                v98 = (const wchar_t *const *)((char *)v71 + 72);
                goto LABEL_343;
              }
              v142 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 1);
              if ( v142 )
              {
                if ( v141 != 11 || *((_BYTE *)this + 116) )
                {
                  v24 = CUpdateEvaluator::EvaluateConditional(this, v142, &v250[2]);
                  if ( v24 < 0 )
                  {
                    v422 = v24;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                        *(_QWORD *)&LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed evaluation of install feature conditional FMID: {0}, Feature: {1}",
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v293 = &v422;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        *(__int64 *)&LogAdapter::g_Logger,
                        1,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                        (__int64)&v293);
                    }
                    v96 = 5064;
                    goto LABEL_392;
                  }
                  v72 = v250[2];
                  if ( v250[2] )
                  {
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      (__int64 *)&v367,
                      (__int64)v340,
                      (__int64 *)&v252);
                    v71 = v252;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                      v251,
                      (char *)v252 + 64,
                      (char *)v252 + 56);
                  }
                  v143 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v71 + 6);
                  if ( v143 )
                  {
                    v24 = CUpdateEvaluator::EvaluateConditional(this, v143, v250);
                    if ( v24 < 0 )
                    {
                      v423 = v24;
                      if ( *(_QWORD *)&LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                          *(_QWORD *)&LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed evaluation of preload feature conditional FMID: {0}, Feature: {1}",
                          (char *)v71 + 64,
                          (char *)v71 + 56);
                        v294 = &v423;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          *(__int64 *)&LogAdapter::g_Logger,
                          1,
                          3,
                          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                          (__int64)&v294);
                      }
                      v96 = 5077;
                      goto LABEL_392;
                    }
                    v73 = v250[0];
                    if ( v250[0] )
                    {
                      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                        "Feature added to the DisableFeature list due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                        v251,
                        (char *)v71 + 64,
                        (char *)v71 + 56);
                      v24 = CActionListCreator::DisableFeature(v260, v71);
                      if ( v24 < 0 )
                      {
                        v425 = v24;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed adding DisableFeature: Group: {}, FMID: {}, Feature: {}",
                            (char *)v71 + 72,
                            (char *)v71 + 64,
                            (char *)v71 + 56);
                          *(_QWORD *)v295 = &v425;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(__int64 *)&LogAdapter::g_Logger,
                            1,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                            (__int64)v295);
                        }
                        v145 = 5086;
                        goto LABEL_403;
                      }
                      v66 = 0;
                      if ( v72 )
                      {
                        v24 = -2146467821;
                        v428 = -2146467821;
                        if ( *(_QWORD *)&LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
                            *(_QWORD *)&LogAdapter::g_Logger,
                            0,
                            3,
                            "Conflicting preload and install feature conditions defined for: Group: {0}, FMID: {1}, Feature: {2}",
                            v251,
                            (char *)v71 + 64,
                            (char *)v71 + 56);
                          v296 = &v428;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            *(__int64 *)&LogAdapter::g_Logger,
                            1,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                            (__int64)&v296);
                        }
                        v96 = 5092;
                        goto LABEL_392;
                      }
                      v73 = v250[0];
                    }
                  }
                  if ( v72 )
                    goto LABEL_155;
                  if ( v73 )
                    goto LABEL_157;
                  v103 = "Feature excluded due to conditional: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_210:
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v103, v251, (char *)v71 + 64, (char *)v71 + 56);
                  goto LABEL_157;
                }
              }
              else if ( v141 != 11 )
              {
                if ( v141 == 15 )
                {
                  v72 = *((_BYTE *)this + 117);
                  if ( !v72 )
                    goto LABEL_157;
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    (__int64 *)&v367,
                    (__int64)v342,
                    (__int64 *)&v252);
                  v98 = v251;
                  v101 = "Feature added due to safe OS dynamic update: Group: {0}, FMID: {1}, Feature: {2}";
                }
                else
                {
                  if ( v141 != 9 )
                  {
                    v72 = 1;
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      (__int64 *)&v367,
                      (__int64)v344,
                      (__int64 *)&v252);
                    v71 = v252;
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                      "Feature added due to default desktop servicing evaluation: Group: {0}, FMID: {1}, Feature: {2}",
                      v251,
                      (char *)v252 + 64,
                      (char *)v252 + 56);
                    goto LABEL_155;
                  }
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImprovedLcuRollback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImprovedLcuRollback>::GetImpl'::`2'::impl)
                    || (v72 = *((_BYTE *)this + 116)) == 0 )
                  {
LABEL_157:
                    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
                      v382,
                      v269,
                      &v252);
                    v87 = v269[0];
                    if ( v269[0] == v382[0] )
                      goto LABEL_120;
                    *(_BYTE *)(*(_QWORD *)(v269[0] + 40LL) + 32LL) = 1;
                    if ( v72 )
                    {
                      if ( !*(_DWORD *)(**(_QWORD **)(v87 + 40) + 16LL)
                        && !CUpdateEvaluator::FindFeatureOnDevice(this, v71) )
                      {
                        *(_DWORD *)(**(_QWORD **)(v87 + 40) + 16LL) |= *((_DWORD *)v71 + 95);
                      }
                      v88 = *(_QWORD *)(v87 + 40);
                      v89 = *(_DWORD *)(*(_QWORD *)v88 + 16LL);
                      if ( (v89 & 0x6E) == 0 && (!v250[4] || v250[1]) )
                      {
                        if ( *((_BYTE *)v71 + 368) == 1 || *((_BYTE *)v71 + 368) == 4 )
                          v90 = v89 | 0x30;
                        else
                          v90 = v89 | 0x50;
                        *(_DWORD *)(*(_QWORD *)v88 + 16LL) = v90;
                      }
                      goto LABEL_120;
                    }
                    std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                      (__int64 *)&v367,
                      (__int64)v272,
                      (__int64 *)&v252);
                    v138 = (char *)v252 + 56;
                    v136 = (char *)v252 + 64;
                    v137 = (char *)v252 + 72;
                    v139 = "Feature added due to deferred update: Group: {0}, FMID: {1}, Feature: {2}";
LABEL_300:
                    LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v139, v137, v136, v138);
                    goto LABEL_120;
                  }
                  std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                    (__int64 *)&v367,
                    (__int64)v343,
                    (__int64 *)&v252);
                  v98 = v251;
                  v101 = "Feature added due to tools: Group: {0}, FMID: {1}, Feature: {2}";
                }
                goto LABEL_342;
              }
              v72 = *((_BYTE *)this + 116);
              if ( !v72 )
                goto LABEL_157;
              std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
                (__int64 *)&v367,
                (__int64)v341,
                (__int64 *)&v252);
              v98 = v251;
              v101 = "Feature added due to cumulative update or reoffer: Group: {0}, FMID: {1}, Feature: {2}";
            }
LABEL_342:
            v71 = v252;
LABEL_343:
            v100 = (char *)v71 + 56;
            v99 = (char *)v71 + 64;
LABEL_344:
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(v101, v98, v99, v100);
LABEL_345:
            if ( v72 )
              goto LABEL_155;
            goto LABEL_157;
          }
          v131 = v130 == 2;
        }
        if ( !v131 && !*(_QWORD *)v71 )
          goto LABEL_299;
        goto LABEL_307;
      }
      break;
    }
    v65 = n + 1;
    n = v65;
    if ( v65 != (const wchar_t *const **)v262 )
      continue;
    break;
  }
  v64 = v258;
LABEL_124:
  v373 = 0;
  v374 = 0;
  if ( v368 )
    std::vector<CCompositionDatabase::Feature *>::_Resize_reallocate<std::_Value_init_tag>((__int64)&v373, v368);
  v79 = (_QWORD *)v373;
  v80 = v367;
  v81 = *v367;
  n = (const wchar_t *const **)*v367;
  while ( (_QWORD *)v81 != v80 )
  {
    *v79 = *(_QWORD *)(v81 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v81 = (__int64)n;
  }
  v376 = 0;
  v377 = 0;
  std::vector<CCompositionDatabase::Feature *>::reserve(&v376, (__int64)(*((_QWORD *)&v373 + 1) - v373) >> 3);
  FeatureDependencyClosure = CUpdateEvaluator::GetFeatureDependencyClosure(this, v64, &v373, &v376);
  v24 = FeatureDependencyClosure;
  if ( FeatureDependencyClosure < 0 )
  {
    v419 = FeatureDependencyClosure;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to determine feature dependency closure");
      *(_QWORD *)v290 = &v419;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v290);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D8,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      v248);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
    goto LABEL_714;
  }
  if ( (_QWORD)v373 != *((_QWORD *)&v373 + 1) )
    *((_QWORD *)&v373 + 1) = v373;
  v152 = (__int64 *)*((_QWORD *)&v376 + 1);
  v151 = (__int64 *)v376;
  if ( (_QWORD)v376 != *((_QWORD *)&v376 + 1) )
  {
    while ( 1 )
    {
      n = (const wchar_t *const **)*v151;
      v28 = GetQualifiedFeatureId(n, &v366);
      if ( v28 < 0 )
        break;
      v28 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, 0);
      if ( v28 < 0 )
      {
        v418 = v28;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to create feature modification request");
          *(_QWORD *)v289 = &v418;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)v289);
        }
        v157 = 5601;
LABEL_441:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v157,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
          (const char *)(unsigned int)v28,
          v248);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
        std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
        if ( v366 )
          goto LABEL_38;
        goto LABEL_39;
      }
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        (__int64 *)&v367,
        (__int64)v272,
        (__int64 *)&n);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v369,
        &n);
      if ( ++v151 == v152 )
      {
        if ( (_QWORD)v376 != *((_QWORD *)&v376 + 1) )
          *((_QWORD *)&v376 + 1) = v376;
        goto LABEL_428;
      }
    }
    v406 = v28;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to determine qualified feature id");
      v288 = &v406;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v288);
    }
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
LABEL_446:
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
    std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
    if ( v366 )
      goto LABEL_38;
    goto LABEL_39;
  }
LABEL_428:
  v153 = (_QWORD *)*((_QWORD *)v64 + 5);
  v267[0] = &v153[*((_QWORD *)v64 + 3)];
  if ( v153 != (_QWORD *)v267[0] )
  {
    do
    {
      v270[0] = *v153;
      v154 = *(const wchar_t *const ***)(v270[0] + 48LL);
      for ( v269[0] = &v154[*(_QWORD *)(v270[0] + 32LL)]; v154 != (const wchar_t *const **)v269[0]; ++v154 )
      {
        v155 = *v154;
        v251 = *v154;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v367,
                &v251)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v369,
                &v251)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v370,
                &v251) )
        {
          FeatureOnDevice = CUpdateEvaluator::FindFeatureOnDevice(
                              this,
                              (const struct CCompositionDatabase::Feature *const)v155);
          if ( FeatureOnDevice && (!v250[4] || (*((_BYTE *)FeatureOnDevice + 52) & 0x6E) != 0) )
          {
            if ( *((_QWORD **)&v373 + 1) == v374 )
            {
              std::vector<SessionData::LocalSources>::_Emplace_reallocate<SessionData::LocalSources>(
                &v373,
                *((_QWORD *)&v373 + 1),
                &v251);
            }
            else
            {
              **((_QWORD **)&v373 + 1) = v155;
              *((_QWORD *)&v373 + 1) += 8LL;
            }
          }
          else if ( (*((_DWORD *)this + 12) == 1 || *((_DWORD *)this + 12) == 19)
                 && (unsigned __int8)(*((_BYTE *)v155 + 368) - 2) <= 1u )
          {
            v158 = (struct CCompositionDatabase::ConditionSet *)*((_QWORD *)v155 + 1);
            if ( v158 )
            {
              v250[1] = 0;
              if ( CUpdateEvaluator::EvaluateConditional(this, v158, &v250[1]) >= 0 && v250[1] )
              {
                v432 = 0;
                v433 = 0;
                std::vector<CCompositionDatabase::Feature *>::reserve(&v432, *((_QWORD *)v155 + 39) + 1LL);
                v287 = v155;
                v273 = 0;
                v274 = 0;
                std::vector<CCompositionDatabase::Feature *>::_Buy_nonzero(&v273, 1);
                v159 = v273;
                *(_QWORD *)v273 = v287;
                *((_QWORD *)&v273 + 1) = v159 + 8;
                *(_QWORD *)&v262 = 0;
                std::_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>::~_Tidy_guard<std::vector<CCompositionDatabase::Feature *>>(&v262);
                v24 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v258, &v273, &v432);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v273);
                if ( v24 < 0 )
                {
                  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v432);
                  goto LABEL_475;
                }
                v160 = (_QWORD *)*((_QWORD *)&v432 + 1);
                v161 = (_QWORD *)v432;
                if ( (_QWORD)v432 != *((_QWORD *)&v432 + 1) )
                {
                  v162 = (_QWORD *)*((_QWORD *)&v373 + 1);
                  do
                  {
                    if ( (const wchar_t *const *)*v161 != v155 )
                    {
                      if ( v162 == v374 )
                      {
                        std::vector<SessionData::LocalSources>::_Emplace_reallocate<SessionData::LocalSources>(
                          &v373,
                          v162,
                          v161);
                        v162 = (_QWORD *)*((_QWORD *)&v373 + 1);
                      }
                      else
                      {
                        *v162 = *v161;
                        v162 = (_QWORD *)(*((_QWORD *)&v373 + 1) + 8LL);
                        *((_QWORD *)&v373 + 1) += 8LL;
                      }
                    }
                    ++v161;
                  }
                  while ( v161 != v160 );
                  v160 = (_QWORD *)*((_QWORD *)&v432 + 1);
                  v161 = (_QWORD *)v432;
                }
                if ( (unsigned __int64)(v160 - v161) > 1 )
                  LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
                    "Edition feature dependencies included due to conditional: Group: {0}, FMID: {1}, Feature: {2}",
                    v270[0],
                    v155 + 8,
                    v155 + 7);
                std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v432);
              }
            }
          }
        }
      }
      ++v153;
    }
    while ( v153 != (_QWORD *)v267[0] );
    v64 = v258;
  }
  v163 = CUpdateEvaluator::GetFeatureDependencyClosure(this, v64, &v373, &v376);
  v24 = v163;
  v164 = 0;
  if ( v163 < 0 )
  {
    v405 = v163;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to determine feature dependency closure");
      *(_QWORD *)v286 = &v405;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v286);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1629,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
      (const char *)(unsigned int)v24,
      v248);
LABEL_475:
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
    std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
    goto LABEL_384;
  }
  if ( (_QWORD)v373 != *((_QWORD *)&v373 + 1) )
    *((_QWORD *)&v373 + 1) = v373;
  v165 = (__int64 *)*((_QWORD *)&v376 + 1);
  v166 = (__int64 *)v376;
  if ( (_QWORD)v376 != *((_QWORD *)&v376 + 1) )
  {
    do
    {
      v255 = *v166;
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
        (__int64 *)&v367,
        (__int64)v272,
        &v255);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v369,
        &v255);
      std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::erase(
        v370,
        &v255);
      ++v166;
    }
    while ( v166 != v165 );
    if ( (_QWORD)v376 != *((_QWORD *)&v376 + 1) )
      *((_QWORD *)&v376 + 1) = v376;
  }
  v167 = (const wchar_t ***)*v367;
  v256 = (const wchar_t ***)*v367;
  while ( !*((_BYTE *)v167 + 25) )
  {
    v168 = (const struct CCompositionDatabase::Feature *)v167[4];
    n = (const wchar_t *const **)v168;
    v28 = GetQualifiedFeatureId(v168, &v366);
    if ( v28 < 0 )
    {
      v431 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to determine qualified feature id");
        v283 = &v431;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v283);
      }
      goto LABEL_508;
    }
    v255 = 0;
    v28 = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v255);
    if ( v28 < 0 )
    {
      v401 = v28;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to create feature modification request");
        *(_QWORD *)v284 = &v401;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v284);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1641,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v28,
        v248);
LABEL_508:
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
      goto LABEL_509;
    }
    v169 = (_BYTE *)v255;
    v170 = *(_QWORD *)(v255 + 16);
    if ( !v170 || (v250[4] || *(_DWORD *)(v170 + 52)) && (*(_BYTE *)(v170 + 48) & 4) == 0 )
    {
      if ( !CUpdateEvaluator::IsFeatureInstallAllowed(this, v168) )
      {
        v28 = -2146467829;
        v404 = -2146467829;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,wchar_t *>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Required feature not available for install: Group: {0}, FMID: {1}, Feature: {2}",
            (char *)v168 + 72,
            (char *)v168 + 64,
            (char *)v168 + 56);
          v285 = &v404;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v285);
        }
        v157 = 5723;
        goto LABEL_441;
      }
    }
    else
    {
      v164 = 1;
    }
    if ( v169[32] || v164 )
    {
      v164 = 0;
    }
    else
    {
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature added due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v168 + 72,
        (char *)v168 + 64,
        (char *)v168 + 56);
      v169[32] = 1;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
        v382,
        (__int64)v272,
        (__int64 *)&n,
        &v255);
      v164 = 0;
      if ( !*(_DWORD *)(*(_QWORD *)v169 + 16LL) )
        *(_DWORD *)(*(_QWORD *)v169 + 16LL) = *((_DWORD *)v168 + 95);
    }
    if ( v169[33] )
      LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
        "Feature will not be removed due to dependency: Group: {0}, FMID: {1}, Feature: {2}",
        (char *)v168 + 72,
        (char *)v168 + 64,
        (char *)v168 + 56);
    v169[33] = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v378,
      &n);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v256);
    v167 = v256;
  }
  v171 = *((_QWORD *)v64 + 5);
  *(_QWORD *)&v262 = v171 + 8LL * *((_QWORD *)v64 + 3);
  if ( v171 != (_QWORD)v262 )
  {
    do
    {
      v172 = *(const wchar_t *const ***)(*(_QWORD *)v171 + 48LL);
      v173 = &v172[*(_QWORD *)(*(_QWORD *)v171 + 32LL)];
      while ( v172 != v173 )
      {
        v174 = *v172;
        v251 = *v172;
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                &v367,
                &v251)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v369,
                &v251)
          && !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v370,
                &v251)
          && CUpdateEvaluator::FindFeatureOnDevice(this, (const struct CCompositionDatabase::Feature *const)v174) )
        {
          updated = GetQualifiedFeatureId(v174, &v366);
          if ( updated < 0 )
          {
            v426 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(__int64 *)&LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to determine qualified feature id");
              v281 = &v426;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)&v281);
            }
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
LABEL_534:
            if ( v366 )
              goto LABEL_535;
            goto LABEL_536;
          }
          v255 = 0;
          updated = CUpdateEvaluator::EnsureModifyRequestExists(this, 0, (__int64)&v255);
          if ( updated < 0 )
          {
            v427 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(__int64 *)&LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to create feature modification request");
              *(_QWORD *)v282 = &v427;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)v282);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x168E,
              (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
              (const char *)(unsigned int)updated,
              v249);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
            std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
            std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
            if ( v366 )
            {
LABEL_535:
              operator delete((void *)(v366 - 8), v177);
              v366 = 0;
            }
LABEL_536:
            v24 = updated;
            goto LABEL_716;
          }
          *(_BYTE *)(v255 + 33) = 1;
          std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::emplace<CCompositionDatabase::Feature * const &,CUpdateEvaluator::FeatureRequest * &>(
            v378,
            (__int64)v272,
            (__int64 *)&v251,
            &v255);
          std::_Tree<std::_Tset_traits<CCompositionDatabase::Package *,std::less<CCompositionDatabase::Package *>,std::allocator<CCompositionDatabase::Package *>,0>>::emplace<CCompositionDatabase::Package * &>(
            v369,
            (__int64)v327,
            (__int64 *)&v251);
        }
        ++v172;
      }
      v171 += 8;
    }
    while ( v171 != (_QWORD)v262 );
    v64 = v258;
  }
  v176 = *(_QWORD *)v378[0];
  n = *(const wchar_t *const ***)v378[0];
  while ( !*(_BYTE *)(v176 + 25) )
  {
    *(_BYTE *)(*(_QWORD *)(v176 + 40) + 32LL) = 0;
    std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::erase(
      v382,
      *(_QWORD *)(v176 + 40) + 8LL);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v176 = (__int64)n;
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v376);
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v373);
  v435 = 0;
  v436 = 0;
  std::set_intersection<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<CCompositionDatabase::Feature *>>>,std::back_insert_iterator<std::vector<CCompositionDatabase::Feature *>>>(
    (unsigned int)&v262,
    *v367,
    (_DWORD)v367,
    *(_QWORD *)v369[0],
    v369[0],
    (__int64)&v435);
  v178 = (_QWORD *)*((_QWORD *)&v435 + 1);
  v179 = (_QWORD *)v435;
  if ( (_QWORD)v435 != *((_QWORD *)&v435 + 1) )
  {
    do
    {
      v180 = *v179;
      if ( (int)GetQualifiedFeatureId(*v179, &v366) >= 0 )
        LogAdapter::TraceAtLevelHr<long,AutoScz>(3, 2148499470LL, "Cannot remove required feature : {0}", &v366);
      else
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          3,
          2148499470LL,
          "Cannot remove required feature : {0}",
          v180 + 56);
      ++v179;
    }
    while ( v179 != v178 );
    v64 = v258;
    if ( (_QWORD)v435 != *((_QWORD *)&v435 + 1) )
    {
      v424 = -2146467826;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Operation requires removal of required features");
        *(_QWORD *)v280 = &v424;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v280);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B7,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)0x800F800ELL,
        v248);
      std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v435);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
      std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
      if ( v366 )
      {
        operator delete((void *)(v366 - 8), v181);
        v366 = 0;
      }
      v24 = -2146467826;
      goto LABEL_716;
    }
  }
  std::vector<CCompositionDatabase::Package *>::~vector<CCompositionDatabase::Package *>(&v435);
  v250[1] = 0;
  v250[3] = 0;
  v184 = *(_QWORD *)v379[0];
  n = *(const wchar_t *const ***)v379[0];
  while ( !*(_BYTE *)(v184 + 25) )
  {
    v185 = *(_QWORD *)(v184 + 64);
    LOBYTE(v183) = *(_BYTE *)(v185 + 33);
    LOBYTE(v182) = *(_BYTE *)(v185 + 32);
    EvaluateFeatureDeclares(
      *(_QWORD *)(v185 + 8),
      v182,
      v183,
      (unsigned int)&v380,
      (__int64)v434,
      (__int64)&v250[1],
      (__int64)&v250[3]);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v184 = (__int64)n;
  }
  if ( !*(_DWORD *)this && (v250[1] || v250[3]) )
  {
    std::wstring::wstring(v333, L"en-US");
    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
      &v380,
      (__int64)v272,
      (__int64)v333);
    std::wstring::~wstring(v333);
  }
  v186 = *(_QWORD *)v380;
  n = *(const wchar_t *const ***)v380;
  while ( !*(_BYTE *)(v186 + 25) )
  {
    LogAdapter::TraceAtLevel<std::wstring>(1, "Supported language: {0}", v186 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v186 = (__int64)n;
  }
  v187 = *(_QWORD *)v434[0];
  n = *(const wchar_t *const ***)v434[0];
  while ( !*(_BYTE *)(v187 + 25) )
  {
    LogAdapter::TraceAtLevel<std::wstring>(1, "Supported architecture: {0}", v187 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
    v187 = (__int64)n;
  }
  v188 = v260;
  v189 = CActionListCreator::DetermineOverlayPolicy(v260, *((const struct CDeviceInfo **)this + 12));
  v24 = v189;
  if ( v189 < 0 )
  {
    v417 = v189;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to fetch overlay policy");
      v279 = &v417;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v279);
    }
    v113 = 5856;
    goto LABEL_377;
  }
  v190 = (__int64 *)*((_QWORD *)v64 + 5);
  v265 = (struct CCompositionDatabase::Feature *)v190;
  v266 = (struct CCompositionDatabase::Feature *)&v190[*((_QWORD *)v64 + 3)];
  if ( v190 == (__int64 *)v266 )
    goto LABEL_610;
  while ( 2 )
  {
    n = (const wchar_t *const **)*v190;
    v191 = (const wchar_t ***)n[6];
    v256 = v191;
    v267[0] = &v191[(_QWORD)n[4]];
    if ( v191 == (const wchar_t ***)v267[0] )
      goto LABEL_608;
    while ( 2 )
    {
      v192 = *v191;
      v251 = *v191;
      v193 = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v382,
        &v262,
        &v251);
      v194 = v262;
      if ( (_QWORD)v262 != v382[0] )
      {
        v250[1] = 1;
        goto LABEL_569;
      }
      v250[1] = 0;
      std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
        v378,
        v270,
        &v251);
      v194 = v270[0];
      if ( v270[0] == v378[0] )
      {
        std::_Tree<std::_Tmap_traits<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *,std::less<CCompositionDatabase::Feature const *>,std::allocator<std::pair<CCompositionDatabase::Feature const * const,CUpdateEvaluator::FeatureRequest *>>,0>>::find(
          v385,
          v269,
          &v251);
        if ( v269[0] == v385[0] )
        {
          LODWORD(v252) = 0;
          v198 = 0;
          FeatureStateOnDevice = CUpdateEvaluator::FindFeatureStateOnDevice(
                                   this,
                                   (const struct CCompositionDatabase::Feature *const)v192);
          goto LABEL_570;
        }
        v203 = *(_QWORD **)(v269[0] + 40LL);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v203[2];
        v204 = *v203;
        v205 = *(_DWORD *)(*v203 + 16LL);
        LODWORD(v252) = v205;
        v198 = *(_DWORD *)(v204 + 20);
        if ( *((_BYTE *)v192 + 368) != 16 )
        {
          LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
            "Feature modified due to deferred update: Group: {0}, FMID: {1}, Feature: {2}",
            v192 + 9,
            v192 + 8,
            v192 + 7);
          if ( v205
            && (std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v325),
                updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v260, (_DWORD)v192, v205, 0, (__int64)v325, 1),
                std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v325),
                updated < 0) )
          {
            v416 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(__int64 *)&LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding feature for token updates");
              *(_QWORD *)v278 = &v416;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)v278);
            }
            v206 = 5902;
          }
          else
          {
            if ( !v198 )
              goto LABEL_570;
            std::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>::set<std::tuple<enum DeclareSatelliteType,std::wstring>,WstringCaseInsensitiveCompareDeclareToken,std::allocator<std::tuple<enum DeclareSatelliteType,std::wstring>>>(v324);
            updated = CActionListCreator::UpdateFeatureTokens((_DWORD)v260, (_DWORD)v192, v198, 0, (__int64)v324, 0);
            std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v324);
            if ( updated >= 0 )
              goto LABEL_570;
            v415 = updated;
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                *(__int64 *)&LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding feature for token updates");
              v277 = &v415;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                *(__int64 *)&LogAdapter::g_Logger,
                1,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                (__int64)&v277);
            }
            v206 = 5913;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v206,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)updated,
            v248);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
          std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
          goto LABEL_534;
        }
      }
      else
      {
        v193 = 1;
LABEL_569:
        v195 = *(_QWORD **)(v194 + 40);
        FeatureStateOnDevice = (struct CUpdateEvaluator::Feature *)v195[2];
        v197 = *v195;
        LODWORD(v252) = *(_DWORD *)(*v195 + 16LL);
        v198 = *(_DWORD *)(v197 + 20);
      }
LABEL_570:
      if ( FeatureStateOnDevice )
      {
        v199 = v193 ^ 1;
        *((_BYTE *)FeatureStateOnDevice + 1) = v199;
        if ( v199 )
        {
          if ( *((_BYTE *)v192 + 369) )
          {
            v200 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 3);
            v201 = (_QWORD *)*((_QWORD *)FeatureStateOnDevice + 4);
            if ( v200 != v201 )
            {
              while ( 1 )
              {
                v202 = v200[3] <= 7u ? (const wchar_t *)v200 : (const wchar_t *)*v200;
                PackageInAnyGroup = CUpdateEvaluator::FindPackageInAnyGroup(this, v202);
                if ( !PackageInAnyGroup )
                  break;
                *(_WORD *)PackageInAnyGroup = 1;
                v200 += 4;
                if ( v200 == v201 )
                  goto LABEL_591;
              }
              v28 = -2147023728;
              v414 = -2147023728;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<std::wstring>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed finding package: {0}",
                  v200);
                *(_QWORD *)v276 = &v414;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(__int64 *)&LogAdapter::g_Logger,
                  1,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
                  (__int64)v276);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1730,
                (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
                (const char *)0x80070490LL,
                v248);
              goto LABEL_446;
            }
          }
        }
      }
LABEL_591:
      if ( v250[1] )
      {
        v221 = 0;
        if ( *((_DWORD *)this + 12) == 1 )
        {
          if ( (unsigned __int8)(*((_BYTE *)v192 + 368) - 5) <= 1u )
            v221 = 8;
        }
        else if ( *((_DWORD *)this + 12) == 24 )
        {
          v221 = 32;
        }
        if ( FeatureStateOnDevice && (!v250[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          v222 = 1;
        else
          v222 = 2;
        v223 = v222 | v221;
        if ( v192 == (const wchar_t **)v259 && *((_DWORD *)v261 + 80) == 16 )
          v223 |= 0x10u;
        v64 = v258;
        v224 = CUpdateEvaluator::ServiceFeatureAndPackages(
                 (int)this,
                 v223,
                 (int)v252,
                 v198,
                 (__int64)&v380,
                 (__int64)v434,
                 (__int64)FeatureStateOnDevice,
                 (struct CCompositionDatabase::Feature *)v192,
                 (__int64)v258,
                 (__int64)v260);
        v28 = v224;
        if ( v224 < 0 )
        {
          v413 = v224;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t *>(
              (_DWORD)v192 + 64,
              3,
              (unsigned int)"Failed adding InstallPackage actions for feature: Group: {0}, FMID: {1}, Feature: {2}",
              (_DWORD)v192 + 72,
              (__int64)(v192 + 8),
              (__int64)(v192 + 7));
            *(_QWORD *)v275 = &v413;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)v275);
          }
          v225 = 6012;
          goto LABEL_641;
        }
      }
      else
      {
        if ( !std::_Tree<std::_Tset_traits<CCompositionDatabase::Feature *,std::less<CCompositionDatabase::Feature *>,std::allocator<CCompositionDatabase::Feature *>,0>>::count(
                v370,
                &v251) )
        {
          if ( FeatureStateOnDevice
            && *((_BYTE *)FeatureStateOnDevice + 1)
            && (!v250[4] || (*((_BYTE *)FeatureStateOnDevice + 48) & 4) != 0) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not updating Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v192 + 8,
              v192 + 7);
            v208 = *((_QWORD *)FeatureStateOnDevice + 4);
            for ( k = *((_QWORD *)FeatureStateOnDevice + 3); k != v208; k += 32 )
            {
              if ( *(_QWORD *)(k + 24) <= 7u )
                v210 = (const wchar_t *)k;
              else
                v210 = *(const wchar_t **)k;
              v211 = CUpdateEvaluator::FindPackageInAnyGroup(this, v210);
              if ( v211 )
                *(_WORD *)v211 = 1;
            }
          }
          else
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not applicable Group: {0}, FMID: {1}, Feature: {2}",
              n,
              v192 + 8,
              v192 + 7);
          }
        }
        v64 = v258;
      }
      v191 = v256 + 1;
      v256 = v191;
      if ( v191 != (const wchar_t ***)v267[0] )
        continue;
      break;
    }
    v190 = (__int64 *)v265;
LABEL_608:
    v265 = (struct CCompositionDatabase::Feature *)++v190;
    if ( v190 != (__int64 *)v266 )
      continue;
    break;
  }
  v188 = v260;
LABEL_610:
  if ( *(_DWORD *)this != 1 )
    goto LABEL_728;
  v212 = *((_DWORD *)this + 12);
  if ( v212 <= 0x13 )
  {
    v213 = 526338;
    if ( _bittest(&v213, v212) )
    {
      v214 = (const wchar_t ***)**((_QWORD **)this + 4);
      v256 = v214;
      while ( !*((_BYTE *)v214 + 25) )
      {
        v215 = *(_QWORD *)v214[4][2];
        n = (const wchar_t *const **)v215;
        while ( !*(_BYTE *)(v215 + 25) )
        {
          v216 = *(_QWORD *)(v215 + 32);
          if ( (*(_BYTE *)(v216 + 52) & 1) == 0
            && !CCompositionDatabase::FindFeature(
                  v64,
                  *v214[4],
                  *(const wchar_t *const *)(v216 + 8),
                  *(const wchar_t *const *)(v216 + 16)) )
          {
            LogAdapter::TraceInfo<wchar_t *,wchar_t *,wchar_t *>(
              "Not modifying Group: {}, FMID: {}, Feature: {}",
              v214[4],
              *(_QWORD *)(v215 + 32) + 8LL,
              *(_QWORD *)(v215 + 32) + 16LL);
            *(_BYTE *)(*(_QWORD *)(v215 + 32) + 1LL) = 1;
            v217 = *(_QWORD *)(v215 + 32);
            v218 = *(_QWORD *)(v217 + 32);
            for ( m = *(_QWORD *)(v217 + 24); m != v218; m += 32 )
            {
              if ( *(_QWORD *)(m + 24) <= 7u )
                v220 = (const wchar_t *)m;
              else
                v220 = *(const wchar_t **)m;
              v226 = CUpdateEvaluator::FindPackageInAnyGroup(this, v220);
              if ( v226 )
                *(_BYTE *)v226 = 1;
            }
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
          v215 = (__int64)n;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v256);
        v214 = v256;
      }
    }
  }
  if ( *(_DWORD *)this != 1
    || !v259
    || *((_DWORD *)this + 12) != 2
    && *((_DWORD *)this + 12) != 14
    && *((_DWORD *)this + 12) != 15
    && *((_DWORD *)this + 12) != 22 )
  {
    goto LABEL_728;
  }
  v227 = (const wchar_t ***)**((_QWORD **)this + 4);
  v256 = v227;
LABEL_662:
  if ( *((_BYTE *)v227 + 25) )
  {
LABEL_728:
    if ( *((_BYTE *)v188 + 78) )
    {
      if ( *((_BYTE *)v188 + 77) )
        *(_BYTE *)(*(_QWORD *)v188 + 1184LL) = 1;
    }
    else if ( *((_BYTE *)v188 + 77) )
    {
      v237 = *(_QWORD **)v188;
      free(*(void **)(*(_QWORD *)v188 + 1096LL));
      v237[137] = 0;
      v237[135] = 0;
      v237[136] = 0;
    }
    v238 = *((_DWORD *)this + 12);
    if ( v238 == 3 )
    {
      v239 = CUpdateEvaluator::RemoveFeaturesAndPackages(this, v64, v385, v188);
      v24 = v239;
      if ( v239 < 0 )
      {
        v409 = v239;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed removing features and packages");
          v314 = &v409;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v314);
        }
        v113 = 6134;
        goto LABEL_377;
      }
LABEL_702:
      v241 = (struct ActionList::Product **)*((_QWORD *)v64 + 13);
      v242 = &v241[*((_QWORD *)v64 + 11)];
      while ( v241 != v242 )
      {
        v28 = CActionListCreator::UpdateProduct(v188, *v241);
        if ( v28 < 0 )
        {
          v408 = v28;
          if ( *(_QWORD *)&LogAdapter::g_Logger )
          {
            v246 = &String2;
            if ( !*(_DWORD *)*v241 )
              v246 = L"SystemManifest";
            v308 = v246;
            LogAdapter::Logger::LogPartial<wchar_t *,wchar_t *,wchar_t const *>(
              &v308,
              v243,
              "Failed adding product update: Name {0}, Version {1}",
              (char *)*v241 + 8,
              (char *)*v241 + 16,
              &v308);
            v307 = &v408;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              *(__int64 *)&LogAdapter::g_Logger,
              1,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
              (__int64)&v307);
          }
          v225 = 6146;
LABEL_641:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v225,
            (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
            (const char *)(unsigned int)v28,
            v248);
          goto LABEL_509;
        }
        ++v241;
      }
      if ( *((_BYTE *)this + 119) )
      {
        LogAdapter::TraceInfo<>("Reordering packages for servicing based upgrade.");
        CActionListCreator::FinalizeActionListForServicingUpgrade(v188, v64);
      }
      if ( *((_DWORD *)this + 12) != 1
        || (v244 = CUpdateEvaluator::AddBaselinePackagesIfNeeded(this, v64, v188), v24 = v244, v244 >= 0) )
      {
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
        std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
        if ( v366 )
        {
          operator delete((void *)(v366 - 8), v247);
          v366 = 0;
        }
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v385);
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v378);
        std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v382);
        std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v379);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v434);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v380);
        return 0;
      }
      v407 = v244;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding baseline packages");
        *(_QWORD *)v306 = &v407;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v306);
      }
      v146 = 6162;
LABEL_713:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v146,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        v248);
      goto LABEL_714;
    }
    if ( (unsigned int)(v238 - 14) <= 1 )
      goto LABEL_699;
    if ( !*((_BYTE *)this + 119) )
      goto LABEL_702;
    v240 = L"servicing";
    if ( (unsigned int)(v238 - 14) <= 1 )
LABEL_699:
      v240 = L"media";
    v312 = v240;
    LogAdapter::TraceInfo<wchar_t const *>("Stripping media section, because this is {0}-based upgrade", &v312);
    if ( *(_QWORD *)v188 )
      *(_QWORD *)(*(_QWORD *)v188 + 80LL) = 0;
    goto LABEL_702;
  }
  v228 = *(_QWORD *)v227[4][2];
  for ( n = (const wchar_t *const **)v228; ; v228 = (__int64)n )
  {
    if ( *(_BYTE *)(v228 + 25) )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v256);
      v227 = v256;
      goto LABEL_662;
    }
    v229 = *(_QWORD *)(v228 + 32);
    if ( (*(_BYTE *)(v229 + 52) & 1) != 0 )
    {
      v230 = Windows::StringUtil::AsLUnicode(v350, *(_QWORD *)(v229 + 16));
      v331 = *(_OWORD *)v230;
      v231 = v331;
      v332 = *(_QWORD *)(v230 + 16);
      v232 = Windows::StringUtil::TrimPrefixIfPresent<_LUNICODE_STRING,_LUNICODE_STRING>(
               v351,
               ___LiteralObject__2U__BaseLiteralBuffer__03U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EP__0ED__0CN__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
               &v331);
      v437 = *(_OWORD *)v232;
      v438 = *(_QWORD *)(v232 + 16);
      if ( (unsigned __int64)v437 < v231 )
        break;
    }
LABEL_674:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&n);
  }
  v257 = 0;
  v28 = SczAllocFromLUnicodeString(&v257, &v437);
  if ( v28 < 0 )
  {
    v235 = 6090;
    goto LABEL_684;
  }
  if ( !(unsigned __int8)Windows::StringUtil::AreStringAndLowerCaseAsciiStringEqualCaseInvariant<_LUNICODE_STRING,_LUNICODE_STRING>(
                           &v437,
                           ___LiteralObject__2U__BaseLiteralBuffer__06U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0HC__0GF__0GD__0GB__0GM__0GM__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUNICODE_STRING__B) )
  {
LABEL_672:
    if ( v257 )
    {
      operator delete(v257 - 4, v233);
      v257 = 0;
    }
    goto LABEL_674;
  }
  LogAdapter::TraceInfo<_LUNICODE_STRING>("Feature removed due to device state: {}", &v437);
  v28 = CActionListCreator::RemoveInstalledFeature(v188, v257, 0, 0);
  if ( v28 >= 0 )
  {
    memset(v353, 0, sizeof(v353));
    v354 = 0;
    v355 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v356);
    std::set<CCompositionDatabase::Feature::FeaturePackageMediaState>::set<CCompositionDatabase::Feature::FeaturePackageMediaState>(v357);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v358);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v359);
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v360);
    v361 = 0;
    v362 = 0;
    v363 = 0;
    CCbsArray<CCompositionDatabase::Feature *>::CCbsArray<CCompositionDatabase::Feature *>(v364);
    v365 = 0;
    *((_QWORD *)&v354 + 1) = v257;
    v24 = CActionListCreator::UpdateFeatureTokens(
            (_DWORD)v188,
            (unsigned int)v353,
            64,
            *(_DWORD *)(*(_QWORD *)(v228 + 32) + 48LL),
            *(_QWORD *)(v228 + 32) + 56LL,
            0);
    if ( v24 < 0 )
    {
      v411 = v24;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding feature for token updates");
        *(_QWORD *)v317 = &v411;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)v317);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E2,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
        (const char *)(unsigned int)v24,
        v248);
      CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v353);
      if ( v257 )
      {
        operator delete(v257 - 4, v234);
        v257 = 0;
      }
      goto LABEL_384;
    }
    CCompositionDatabase::Feature::~Feature((CCompositionDatabase::Feature *)v353);
    goto LABEL_672;
  }
  v410 = v28;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<_LUNICODE_STRING>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed adding RemoveFeature: Feature: {}");
    v316 = &v410;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)&v316);
  }
  v235 = 6100;
LABEL_684:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v235,
    (unsigned int)"onecore\\base\\servicing\\arbiter\\cupdateevaluator.cpp",
    (const char *)(unsigned int)v28,
    v248);
  if ( v257 )
  {
    operator delete(v257 - 4, v236);
    v257 = 0;
  }
LABEL_509:
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v370);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(v369);
  std::_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>::~_Tree<std::_Tset_traits<CDeviceInfo::Feature *,std::less<CDeviceInfo::Feature *>,std::allocator<CDeviceInfo::Feature *>,0>>(&v367);
  if ( v366 )
  {
LABEL_38:
    operator delete((void *)(v366 - 8), v33);
    v366 = 0;
  }
LABEL_39:
  v24 = v28;
LABEL_716:
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v385);
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v378);
  std::map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>::~map<CCompositionDatabase::Feature const *,CUpdateEvaluator::FeatureRequest *>(v382);
  std::_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CUpdateEvaluator::FeatureRequest *,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,CUpdateEvaluator::FeatureRequest *>>,0>>(v379);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v434);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(&v380);
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
