# Spectre::Engine::Configuration::LoadDefaults(Spectre::Utils::IConfigurationManager &,Spectre::Utils::IConfigurationManager::LoadPolicy)

- ea: `0x18006d368`
- end: `0x180072af1`
- name: `?LoadDefaults@Configuration@Engine@Spectre@@YAXAEAVIConfigurationManager@Utils@3@W4LoadPolicy@453@@Z`
- size: `22409`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180033b70`

## callees

- `0x18000ca90`
- `0x1800142d0`
- `0x18001e1b0`
- `0x1800e7010`

## string_xrefs

- `0x18006eec8`: `/Internal/Renderer.RenderPasses.DepthPrepassReadable`
- `0x18006e66c`: `/Internal/Renderer.AlphaCompositingOutputMode`
- `0x180072a42`: `Renderer.Compatibility.GLTFComplianceEnabled`
- `0x18006e818`: `/Internal/Renderer.Compatibility.WorkflowStandard`
- `0x18006e7db`: `/Internal/Renderer.Compatibility.SmoothnessMode`
- `0x180071925`: `Lighting.Light0_ShadowFrustumSize`
- `0x180071f05`: `Lighting.Light1_ShadowFrustumSize`
- `0x1800724e6`: `Lighting.Light2_ShadowFrustumSize`
- `0x1800711fc`: `Lighting.BackgroundShadowAmount`
- `0x1800710c1`: `Lighting.BackgroundColorAmount`
- `0x18006d97a`: `/Internal/ImageProcessing.PlanarReflectionCameraComponentName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spectre::Engine::Configuration::LoadDefaults(__int64 a1)
{
  void (__fastcall *v2)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v3)(__int64, _BYTE *, __int64); // rbx
  __int64 v4; // r8
  void (__fastcall *v5)(__int64, _BYTE *, __int64); // rbx
  __int64 v6; // r8
  void (__fastcall *v7)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v8)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v9)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v10; // r8
  void (__fastcall *v11)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v12; // r8
  void (__fastcall *v13)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v14; // r8
  void (__fastcall *v15)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v16)(__int64, _BYTE *, __int64); // rbx
  __int64 v17; // r8
  void (__fastcall *v18)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v19; // r8
  void (__fastcall *v20)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v21)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v22)(__int64, _BYTE *, __int64); // rbx
  __int64 v23; // r8
  void (__fastcall *v24)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v25)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v26)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v27)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v28)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v29)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v30)(__int64, _BYTE *, __int64); // rbx
  __int64 v31; // r8
  void (__fastcall *v32)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v33)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v34)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v35; // rax
  __int64 v36; // rbx
  void (__fastcall *v37)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v38; // rax
  __int64 v39; // rbx
  void (__fastcall *v40)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v41)(__int64, _BYTE *, __int64, __int64); // rbx
  void (__fastcall *v42)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v43; // r8
  void (__fastcall *v44)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v45; // r8
  void (__fastcall *v46)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v47; // r8
  void (__fastcall *v48)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v49; // r8
  void (__fastcall *v50)(__int64, _BYTE *, __int64); // rbx
  __int64 v51; // r8
  void (__fastcall *v52)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v53; // r8
  void (__fastcall *v54)(__int64, _BYTE *, __int64); // rbx
  __int64 v55; // r8
  void (__fastcall *v56)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v57; // r8
  void (__fastcall *v58)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v59)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v60)(__int64, _BYTE *, __int64); // rbx
  __int64 v61; // r8
  void (__fastcall *v62)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v63; // r8
  void (__fastcall *v64)(__int64, _BYTE *, __int64); // rbx
  __int64 v65; // r8
  void (__fastcall *v66)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v67; // r8
  void (__fastcall *v68)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v69)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v70)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v71)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v72; // r8
  void (__fastcall *v73)(__int64, _BYTE *, __int64); // rbx
  __int64 v74; // r8
  void (__fastcall *v75)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v76; // r8
  void (__fastcall *v77)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v78)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v79)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v80)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v81)(__int64, _BYTE *, __int64); // rbx
  __int64 v82; // r8
  void (__fastcall *v83)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v84; // r8
  void (__fastcall *v85)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v86; // r8
  void (__fastcall *v87)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v88; // r8
  void (__fastcall *v89)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v90)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v91)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v92)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v93; // r8
  void (__fastcall *v94)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v95; // r8
  void (__fastcall *v96)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v97; // r8
  void (__fastcall *v98)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v99; // r8
  void (__fastcall *v100)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v101)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v102; // r8
  void (__fastcall *v103)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v104)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v105)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v106; // r8
  void (__fastcall *v107)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v108; // r8
  void (__fastcall *v109)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v110)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v111; // r8
  void (__fastcall *v112)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v113; // r8
  void (__fastcall *v114)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v115; // r8
  void (__fastcall *v116)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v117; // r8
  void (__fastcall *v118)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v119)(__int64, _BYTE *, __int64, __int64); // rbx
  void (__fastcall *v120)(__int64, _BYTE *, __int64); // rbx
  __int64 v121; // r8
  void (__fastcall *v122)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v123)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v124)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v125)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v126)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v127)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v128)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v129)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v130)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v131)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v132)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v133)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v134)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v135)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v136)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v137)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v138)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v139)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v140)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v141)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v142)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v143)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v144)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v145)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v146)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v147)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v148)(__int64, _BYTE *, __int64); // rbx
  __int64 v149; // r8
  void (__fastcall *v150)(__int64, _BYTE *, __int64); // rbx
  __int64 v151; // r8
  void (__fastcall *v152)(__int64, _BYTE *, __int64); // rbx
  __int64 v153; // r8
  void (__fastcall *v154)(__int64, _BYTE *, __int64); // rbx
  __int64 v155; // r8
  void (__fastcall *v156)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v157)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v158)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v159)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v160)(__int64, _BYTE *, __int64); // rbx
  __int64 v161; // r8
  void (__fastcall *v162)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v163)(__int64, _BYTE *, __int64); // rbx
  __int64 v164; // r8
  void (__fastcall *v165)(__int64, _BYTE *, __int64); // rbx
  __int64 v166; // r8
  void (__fastcall *v167)(__int64, _BYTE *, __int64); // rbx
  __int64 v168; // r8
  void (__fastcall *v169)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v170; // r8
  void (__fastcall *v171)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v172; // r8
  void (__fastcall *v173)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v174)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v175)(__int64, _BYTE *, __int64); // rbx
  __int64 v176; // r8
  void (__fastcall *v177)(__int64, _BYTE *, __int64); // rbx
  __int64 v178; // r8
  void (__fastcall *v179)(__int64, _BYTE *, __int64); // rbx
  __int64 v180; // r8
  void (__fastcall *v181)(__int64, _BYTE *, __int64); // rbx
  __int64 v182; // r8
  void (__fastcall *v183)(__int64, _BYTE *, __int64); // rbx
  __int64 v184; // r8
  void (__fastcall *v185)(__int64, _BYTE *, __int64); // rbx
  __int64 v186; // r8
  void (__fastcall *v187)(__int64, _BYTE *, __int64); // rbx
  __int64 v188; // r8
  void (__fastcall *v189)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v190)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v191)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v192)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v193; // r8
  void (__fastcall *v194)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v195; // r8
  void (__fastcall *v196)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v197)(__int64, _BYTE *, __int64); // rbx
  __int64 v198; // r8
  void (__fastcall *v199)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v200; // r8
  void (__fastcall *v201)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v202; // r8
  void (__fastcall *v203)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v204; // r8
  void (__fastcall *v205)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v206; // r8
  void (__fastcall *v207)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v208; // r8
  void (__fastcall *v209)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v210; // r8
  void (__fastcall *v211)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v212; // r8
  void (__fastcall *v213)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v214; // r8
  void (__fastcall *v215)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v216; // r8
  void (__fastcall *v217)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v218; // r8
  void (__fastcall *v219)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v220; // r8
  void (__fastcall *v221)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v222; // r8
  void (__fastcall *v223)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v224; // r8
  void (__fastcall *v225)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v226; // r8
  void (__fastcall *v227)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v228; // r8
  void (__fastcall *v229)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v230; // rax
  __int64 v231; // rbx
  void (__fastcall *v232)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v233; // rax
  __int64 v234; // rbx
  void (__fastcall *v235)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v236; // r8
  void (__fastcall *v237)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v238; // r8
  void (__fastcall *v239)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v240; // r8
  void (__fastcall *v241)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v242; // r8
  void (__fastcall *v243)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v244; // r8
  void (__fastcall *v245)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v246; // r8
  void (__fastcall *v247)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v248; // r8
  void (__fastcall *v249)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v250; // r8
  void (__fastcall *v251)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v252; // r8
  void (__fastcall *v253)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v254; // r8
  void (__fastcall *v255)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v256; // r8
  void (__fastcall *v257)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v258; // r8
  void (__fastcall *v259)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v260; // r8
  void (__fastcall *v261)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v262; // r8
  void (__fastcall *v263)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v264; // r8
  void (__fastcall *v265)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v266; // r8
  void (__fastcall *v267)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v268; // r8
  void (__fastcall *v269)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v270; // r8
  void (__fastcall *v271)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v272; // r8
  void (__fastcall *v273)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v274; // r8
  void (__fastcall *v275)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v276; // r8
  void (__fastcall *v277)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v278)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v279; // r8
  void (__fastcall *v280)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v281; // r8
  void (__fastcall *v282)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v283; // r8
  void (__fastcall *v284)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v285; // r8
  void (__fastcall *v286)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v287; // r8
  void (__fastcall *v288)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v289; // r8
  void (__fastcall *v290)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v291; // r8
  void (__fastcall *v292)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v293; // r8
  void (__fastcall *v294)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v295)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v296; // r8
  void (__fastcall *v297)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v298; // r8
  void (__fastcall *v299)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v300; // r8
  void (__fastcall *v301)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v302; // r8
  void (__fastcall *v303)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v304; // r8
  void (__fastcall *v305)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v306; // r8
  void (__fastcall *v307)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v308; // r8
  void (__fastcall *v309)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v310)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v311; // r8
  void (__fastcall *v312)(__int64, _BYTE *, __int64); // rbx
  __int64 v313; // r8
  void (__fastcall *v314)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v315)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v316; // r8
  void (__fastcall *v317)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v318; // r8
  void (__fastcall *v319)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v320; // r8
  void (__fastcall *v321)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v322; // r8
  void (__fastcall *v323)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v324; // r8
  void (__fastcall *v325)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v326; // r8
  void (__fastcall *v327)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v328; // r8
  void (__fastcall *v329)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v330; // r8
  void (__fastcall *v331)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v332; // r8
  void (__fastcall *v333)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v334; // r8
  void (__fastcall *v335)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v336; // r8
  void (__fastcall *v337)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v338; // r8
  void (__fastcall *v339)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v340; // r8
  void (__fastcall *v341)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v342; // r8
  void (__fastcall *v343)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v344; // r8
  void (__fastcall *v345)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v346; // r8
  void (__fastcall *v347)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v348; // r8
  void (__fastcall *v349)(__int64, _BYTE *, __int64); // rbx
  __int64 v350; // r8
  void (__fastcall *v351)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v352)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v353; // r8
  void (__fastcall *v354)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v355; // r8
  void (__fastcall *v356)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v357; // r8
  void (__fastcall *v358)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v359; // r8
  void (__fastcall *v360)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v361; // r8
  void (__fastcall *v362)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v363; // r8
  void (__fastcall *v364)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v365; // r8
  void (__fastcall *v366)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v367; // r8
  void (__fastcall *v368)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v369; // r8
  void (__fastcall *v370)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v371; // r8
  void (__fastcall *v372)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v373; // r8
  void (__fastcall *v374)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v375; // r8
  void (__fastcall *v376)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v377; // r8
  void (__fastcall *v378)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v379; // r8
  void (__fastcall *v380)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v381; // r8
  void (__fastcall *v382)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v383; // rax
  __int64 v384; // rbx
  void (__fastcall *v385)(__int64, _BYTE *, __int64, __int64); // rdi
  __int64 v386; // rax
  __int64 v387; // rbx
  void (__fastcall *v388)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v389; // r8
  void (__fastcall *v390)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v391; // r8
  void (__fastcall *v392)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v393)(__int64, _BYTE *, __int64); // rbx
  __int64 v394; // r8
  void (__fastcall *v395)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v396)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v397; // r8
  void (__fastcall *v398)(__int64, _BYTE *, __int64); // rbx
  __int64 v399; // r8
  void (__fastcall *v400)(__int64, _BYTE *, __int64); // rbx
  __int64 v401; // r8
  void (__fastcall *v402)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v403)(__int64, _BYTE *, __int64); // rbx
  __int64 v404; // r8
  void (__fastcall *v405)(__int64, _BYTE *, __int64); // rbx
  void (__fastcall *v406)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v407; // r8
  void (__fastcall *v408)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v409)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v410; // r8
  void (__fastcall *v411)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v412; // r8
  void (__fastcall *v413)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v414; // r8
  void (__fastcall *v415)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v416; // r8
  void (__fastcall *v417)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v418; // r8
  void (__fastcall *v419)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v420; // r8
  void (__fastcall *v421)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v422; // r8
  void (__fastcall *v423)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v424; // r8
  void (__fastcall *v425)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v426; // r8
  void (__fastcall *v427)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v428; // r8
  void (__fastcall *v429)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v430; // r8
  void (__fastcall *v431)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v432; // r8
  void (__fastcall *v433)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v434; // r8
  void (__fastcall *v435)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v436; // r8
  void (__fastcall *v437)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v438; // r8
  void (__fastcall *v439)(__int64, _BYTE *, __int64); // rbx
  __int64 v440; // r8
  void (__fastcall *v441)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v442; // r8
  void (__fastcall *v443)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v444; // r8
  void (__fastcall *v445)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v446; // r8
  void (__fastcall *v447)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v448; // r8
  void (__fastcall *v449)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v450; // r8
  void (__fastcall *v451)(__int64, _BYTE *, __int64); // rbx
  __int64 v452; // r8
  void (__fastcall *v453)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v454)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v455; // r8
  void (__fastcall *v456)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v457; // r8
  void (__fastcall *v458)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v459)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v460)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v461; // r8
  void (__fastcall *v462)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v463; // r8
  void (__fastcall *v464)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v465; // r8
  void (__fastcall *v466)(__int64, _BYTE *, __int64); // rbx
  __int64 v467; // r8
  void (__fastcall *v468)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v469; // r8
  void (__fastcall *v470)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v471; // r8
  void (__fastcall *v472)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v473)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v474; // r8
  void (__fastcall *v475)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v476; // r8
  void (__fastcall *v477)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v478; // r8
  void (__fastcall *v479)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v480; // r8
  void (__fastcall *v481)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v482; // r8
  void (__fastcall *v483)(__int64, _BYTE *, __int64); // rbx
  __int64 v484; // r8
  void (__fastcall *v485)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v486; // r8
  void (__fastcall *v487)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v488; // r8
  void (__fastcall *v489)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v490; // r8
  void (__fastcall *v491)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v492; // r8
  void (__fastcall *v493)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v494; // r8
  void (__fastcall *v495)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v496; // r8
  void (__fastcall *v497)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v498; // r8
  void (__fastcall *v499)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v500; // r8
  void (__fastcall *v501)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v502)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v503)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v504)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v505; // r8
  void (__fastcall *v506)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v507; // r8
  void (__fastcall *v508)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v509; // r8
  void (__fastcall *v510)(__int64, _BYTE *, __int64); // rbx
  __int64 v511; // r8
  void (__fastcall *v512)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v513; // r8
  void (__fastcall *v514)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v515; // r8
  void (__fastcall *v516)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v517)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v518; // r8
  void (__fastcall *v519)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v520; // r8
  void (__fastcall *v521)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v522; // r8
  void (__fastcall *v523)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v524; // r8
  void (__fastcall *v525)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v526; // r8
  void (__fastcall *v527)(__int64, _BYTE *, __int64); // rbx
  __int64 v528; // r8
  void (__fastcall *v529)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v530; // r8
  void (__fastcall *v531)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v532; // r8
  void (__fastcall *v533)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v534; // r8
  void (__fastcall *v535)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v536; // r8
  void (__fastcall *v537)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v538; // r8
  void (__fastcall *v539)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v540; // r8
  void (__fastcall *v541)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v542; // r8
  void (__fastcall *v543)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v544; // r8
  void (__fastcall *v545)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v546)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v547)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v548)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v549; // r8
  void (__fastcall *v550)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v551; // r8
  void (__fastcall *v552)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v553; // r8
  void (__fastcall *v554)(__int64, _BYTE *, __int64); // rbx
  __int64 v555; // r8
  void (__fastcall *v556)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v557; // r8
  void (__fastcall *v558)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v559; // r8
  void (__fastcall *v560)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v561)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v562; // r8
  void (__fastcall *v563)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v564; // r8
  void (__fastcall *v565)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v566; // r8
  void (__fastcall *v567)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v568; // r8
  void (__fastcall *v569)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v570; // r8
  void (__fastcall *v571)(__int64, _BYTE *, __int64); // rbx
  __int64 v572; // r8
  void (__fastcall *v573)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v574; // r8
  void (__fastcall *v575)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v576; // r8
  void (__fastcall *v577)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v578; // r8
  void (__fastcall *v579)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v580; // r8
  void (__fastcall *v581)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v582; // r8
  void (__fastcall *v583)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v584; // r8
  void (__fastcall *v585)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v586; // r8
  void (__fastcall *v587)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v588; // r8
  void (__fastcall *v589)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v590)(__int64, _BYTE *, __int64); // rbx
  __int64 v591; // r8
  void (__fastcall *v592)(__int64, _BYTE *, __int64); // rbx
  __int64 v593; // r8
  void (__fastcall *v594)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v595; // r8
  void (__fastcall *v596)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v597; // r8
  void (__fastcall *v598)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v599; // r8
  void (__fastcall *v600)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v601; // r8
  void (__fastcall *v602)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v603; // r8
  void (__fastcall *v604)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v605; // r8
  void (__fastcall *v606)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v607; // r8
  void (__fastcall *v608)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v609; // r8
  void (__fastcall *v610)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v611; // r8
  void (__fastcall *v612)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v613; // r8
  void (__fastcall *v614)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v615; // r8
  void (__fastcall *v616)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v617)(__int64, _BYTE *, __int64, __int64); // rbx
  __int64 v618; // r8
  void (__fastcall *v619)(__int64, _BYTE *, _QWORD, __int64); // rbx
  void (__fastcall *v620)(__int64, _BYTE *, _QWORD, __int64); // rbx
  _BYTE v622[32]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v623[32]; // [rsp+60h] [rbp-61h] BYREF

  v2 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Application.KeyboardDeveloperMode");
  v2(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v3 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Background.EnableBackgroundCube");
  LOBYTE(v4) = 1;
  v3(a1, v623, v4);
  std::wstring::_Tidy_deallocate(v623);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Background.ImageProcessing.Enabled");
  LOBYTE(v6) = 1;
  v5(a1, v623, v6);
  std::wstring::_Tidy_deallocate(v623);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/BugWorkaroundOverride.MetalDepthOnlyAlphaToCoverage.ForceWorkaroundOff");
  v7(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v8 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/BugWorkaroundOverride.MetalIntelIrisDepthPrepass.ForceWorkaroundOff");
  v8(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v9 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Camera.Distance");
  v9(a1, v623, v10, 1);
  std::wstring::_Tidy_deallocate(v623);
  v11 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Camera.Elevation (degrees)");
  v11(a1, v623, v12, 1);
  std::wstring::_Tidy_deallocate(v623);
  v13 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Camera.Rotation (degrees)");
  v13(a1, v623, v14, 1);
  std::wstring::_Tidy_deallocate(v623);
  v15 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/CpuProfiling.DisplayFrameTimings");
  v15(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v16 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/CpuProfiling.Enabled");
  LOBYTE(v17) = 1;
  v16(a1, v623, v17);
  std::wstring::_Tidy_deallocate(v623);
  v18 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Debug.Value");
  v18(a1, v623, v19, 1);
  std::wstring::_Tidy_deallocate(v623);
  v20 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayClippingPrimitivesEmitted");
  v20(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v21 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayClippingPrimitivesInvoked");
  v21(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v22 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayDetailFrameTimings");
  LOBYTE(v23) = 1;
  v22(a1, v623, v23);
  std::wstring::_Tidy_deallocate(v623);
  v24 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayFrameTimings");
  v24(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v25 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayPixelShaderInvocations");
  v25(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v26 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplaySceneTiming");
  v26(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v27 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplaySubmittedPrimitives");
  v27(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v28 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplaySubmittedVertices");
  v28(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v29 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.DisplayVertexShaderInvocations");
  v29(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v30 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.Enabled");
  LOBYTE(v31) = 1;
  v30(a1, v623, v31);
  std::wstring::_Tidy_deallocate(v623);
  v32 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/GpuProfiling.HighFidelity");
  v32(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v33 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/ImageProcessing.BloomBlurBlendMode");
  v33(a1, v623, 14);
  std::wstring::_Tidy_deallocate(v623);
  v34 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, L"MainCamera");
  v36 = v35;
  std::wstring::wstring(v623, L"/Internal/ImageProcessing.PlanarReflectionCameraComponentName");
  v34(a1, v623, v36, 1);
  std::wstring::_Tidy_deallocate(v623);
  v37 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, L"PlanarReflection");
  v39 = v38;
  std::wstring::wstring(v623, L"/Internal/ImageProcessing.PlanarReflectionPlaneNodeName");
  v37(a1, v623, v39, 1);
  std::wstring::_Tidy_deallocate(v623);
  v40 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Input.CaptureInput");
  v40(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v41 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Input.DepthStencilEvictionWindowInMs");
  v41(a1, v623, 60000, 1);
  std::wstring::_Tidy_deallocate(v623);
  v42 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.EnvironmentDisplay");
  v42(a1, v623, v43, 1);
  std::wstring::_Tidy_deallocate(v623);
  v44 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.EnvironmentDisplayLOD");
  v44(a1, v623, v45, 1);
  std::wstring::_Tidy_deallocate(v623);
  v46 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.EnvironmentFilterOffset");
  v46(a1, v623, v47, 1);
  std::wstring::_Tidy_deallocate(v623);
  v48 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.EnvironmentFilterScale");
  v48(a1, v623, v49, 1);
  std::wstring::_Tidy_deallocate(v623);
  v50 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_CalculateNearFarClipEnabled");
  LOBYTE(v51) = 1;
  v50(a1, v623, v51);
  std::wstring::_Tidy_deallocate(v623);
  v52 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_ShadowBias");
  v52(a1, v623, v53, 1);
  std::wstring::_Tidy_deallocate(v623);
  v54 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_ShadowBlurEnabled");
  LOBYTE(v55) = 1;
  v54(a1, v623, v55);
  std::wstring::_Tidy_deallocate(v623);
  v56 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_ShadowJitterFactor");
  v56(a1, v623, v57, 1);
  std::wstring::_Tidy_deallocate(v623);
  v58 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_ShadowTechnique");
  v58(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v59 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light0_ShadowTechniqueCSSMFormat");
  v59(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v60 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_CalculateNearFarClipEnabled");
  LOBYTE(v61) = 1;
  v60(a1, v623, v61);
  std::wstring::_Tidy_deallocate(v623);
  v62 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_ShadowBias");
  v62(a1, v623, v63, 1);
  std::wstring::_Tidy_deallocate(v623);
  v64 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_ShadowBlurEnabled");
  LOBYTE(v65) = 1;
  v64(a1, v623, v65);
  std::wstring::_Tidy_deallocate(v623);
  v66 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_ShadowJitterFactor");
  v66(a1, v623, v67, 1);
  std::wstring::_Tidy_deallocate(v623);
  v68 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_ShadowTechnique");
  v68(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v69 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light1_ShadowTechniqueCSSMFormat");
  v69(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v70 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_CalculateNearFarClipEnabled");
  v70(a1, v623, 1);
  std::wstring::_Tidy_deallocate(v623);
  v71 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_ShadowBias");
  v71(a1, v623, v72, 1);
  std::wstring::_Tidy_deallocate(v623);
  v73 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_ShadowBlurEnabled");
  LOBYTE(v74) = 1;
  v73(a1, v623, v74);
  std::wstring::_Tidy_deallocate(v623);
  v75 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_ShadowJitterFactor");
  v75(a1, v623, v76, 1);
  std::wstring::_Tidy_deallocate(v623);
  v77 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_ShadowTechnique");
  v77(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v78 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.Light2_ShadowTechniqueCSSMFormat");
  v78(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v79 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ShadowZDirection");
  v79(a1, v623, 1);
  std::wstring::_Tidy_deallocate(v623);
  v80 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ReceiverSlopePlaneBiasEnabled");
  v80(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v81 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ShadowBiasingMasterToggle");
  LOBYTE(v82) = 1;
  v81(a1, v623, v82);
  std::wstring::_Tidy_deallocate(v623);
  v83 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ShadowBufferCreationDepthBias");
  v83(a1, v623, v84, 1);
  std::wstring::_Tidy_deallocate(v623);
  v85 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ShadowBufferCreationDepthBiasClamp");
  v85(a1, v623, v86, 1);
  std::wstring::_Tidy_deallocate(v623);
  v87 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Lighting.ShadowBufferCreationSlopedDepthBias");
  v87(a1, v623, v88, 1);
  std::wstring::_Tidy_deallocate(v623);
  v89 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Loading.EnableAnimationLoading");
  v89(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v90 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Loading.ForceMinecraftBlendMaterialsToMask");
  v90(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v91 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Loading.ForceTranscoding");
  v91(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v92 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.DiffuseColorH");
  v92(a1, v623, v93, 1);
  std::wstring::_Tidy_deallocate(v623);
  v94 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.DiffuseColorS");
  v94(a1, v623, v95, 1);
  std::wstring::_Tidy_deallocate(v623);
  v96 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.DiffuseColorV");
  v96(a1, v623, v97, 1);
  std::wstring::_Tidy_deallocate(v623);
  v98 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.DiffuseMode");
  v98(a1, v623, v99, 1);
  std::wstring::_Tidy_deallocate(v623);
  v100 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.DiffuseOverride");
  v100(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v101 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.Opacity");
  v101(a1, v623, v102, 1);
  std::wstring::_Tidy_deallocate(v623);
  v103 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.OpacityFresnel");
  v103(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v104 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.OpacityOverride");
  v104(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v105 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.Smoothness");
  v105(a1, v623, v106, 1);
  std::wstring::_Tidy_deallocate(v623);
  v107 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SmoothnessMode");
  v107(a1, v623, v108, 1);
  std::wstring::_Tidy_deallocate(v623);
  v109 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SmoothnessOverride");
  v109(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v110 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SpecularColorH");
  v110(a1, v623, v111, 1);
  std::wstring::_Tidy_deallocate(v623);
  v112 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SpecularColorS");
  v112(a1, v623, v113, 1);
  std::wstring::_Tidy_deallocate(v623);
  v114 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SpecularColorV");
  v114(a1, v623, v115, 1);
  std::wstring::_Tidy_deallocate(v623);
  v116 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SpecularMode");
  v116(a1, v623, v117, 1);
  std::wstring::_Tidy_deallocate(v623);
  v118 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/MaterialOverride.SpecularOverride");
  v118(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v119 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Metal.PsoEvictionWindowInMs");
  v119(a1, v623, 60000, 1);
  std::wstring::_Tidy_deallocate(v623);
  v120 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Model.TransformEnabled");
  LOBYTE(v121) = 1;
  v120(a1, v623, v121);
  std::wstring::_Tidy_deallocate(v623);
  v122 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.AlphaCompositingOutputMode");
  v122(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v123 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Antialiasing");
  v123(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v124 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.BufferFormat.Render");
  v124(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v125 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.CameraEffect.ColorSwatchMode");
  v125(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v126 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.CameraEffect.DisplayDepth");
  v126(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v127 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.CameraEffect.DisplayDepthGrid");
  v127(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v128 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Compatibility.SmoothnessMode");
  v128(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v129 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Compatibility.WorkflowStandard");
  v129(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v130 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Concurrent");
  v130(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v131 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplayPerformanceStats");
  v131(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v132 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbols");
  v132(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v133 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsBound");
  v133(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v134 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsCamera");
  v134(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v135 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsLight");
  v135(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v136 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsMesh");
  v136(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v137 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsNode");
  v137(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v138 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsNodeScale");
  v138(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v139 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsNodeTree");
  v139(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v140 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsSkeleton");
  v140(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v141 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DisplaySymbolsAnimBBox");
  v141(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v142 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.DynamicResolutionScalingEnabled");
  v142(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v143 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.FrameLatencyMaximum");
  v143(a1, v623, 1);
  std::wstring::_Tidy_deallocate(v623);
  v144 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.GeometryDisplayMode");
  v144(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v145 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.GeometryLOD");
  v145(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v146 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.GeometryNormalMode");
  v146(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v147 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Grid");
  v147(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v148 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.LayerBackground");
  LOBYTE(v149) = 1;
  v148(a1, v623, v149);
  std::wstring::_Tidy_deallocate(v623);
  v150 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.LayerForeground");
  LOBYTE(v151) = 1;
  v150(a1, v623, v151);
  std::wstring::_Tidy_deallocate(v623);
  v152 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.MaterialPrimary");
  LOBYTE(v153) = 1;
  v152(a1, v623, v153);
  std::wstring::_Tidy_deallocate(v623);
  v154 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.MaterialSecondary");
  LOBYTE(v155) = 1;
  v154(a1, v623, v155);
  std::wstring::_Tidy_deallocate(v623);
  v156 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderingModeOverride_Blend");
  v156(a1, v623, 3);
  std::wstring::_Tidy_deallocate(v623);
  v157 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderingModeOverride_Mask");
  v157(a1, v623, 1);
  std::wstring::_Tidy_deallocate(v623);
  v158 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderingModeOverride_MaskBlend");
  v158(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v159 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderingModeOverride_Opaque");
  v159(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v160 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderPasses.DepthPrepass");
  LOBYTE(v161) = 1;
  v160(a1, v623, v161);
  std::wstring::_Tidy_deallocate(v623);
  v162 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderPasses.DepthPrepassReadable");
  v162(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v163 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderPasses.Opaque");
  LOBYTE(v164) = 1;
  v163(a1, v623, v164);
  std::wstring::_Tidy_deallocate(v623);
  v165 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderPasses.OpaqueMasked");
  LOBYTE(v166) = 1;
  v165(a1, v623, v166);
  std::wstring::_Tidy_deallocate(v623);
  v167 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.RenderPasses.Transparent");
  LOBYTE(v168) = 1;
  v167(a1, v623, v168);
  std::wstring::_Tidy_deallocate(v623);
  v169 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.ResolutionScalingX");
  v169(a1, v623, v170, 1);
  std::wstring::_Tidy_deallocate(v623);
  v171 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.ResolutionScalingY");
  v171(a1, v623, v172, 1);
  std::wstring::_Tidy_deallocate(v623);
  v173 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.SyncInterval");
  v173(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v174 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TextureLOD");
  v174(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v175 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Textures");
  LOBYTE(v176) = 1;
  v175(a1, v623, v176);
  std::wstring::_Tidy_deallocate(v623);
  v177 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesDiffuse");
  LOBYTE(v178) = 1;
  v177(a1, v623, v178);
  std::wstring::_Tidy_deallocate(v623);
  v179 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesEmissive");
  LOBYTE(v180) = 1;
  v179(a1, v623, v180);
  std::wstring::_Tidy_deallocate(v623);
  v181 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesNormal");
  LOBYTE(v182) = 1;
  v181(a1, v623, v182);
  std::wstring::_Tidy_deallocate(v623);
  v183 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesOcclusion");
  LOBYTE(v184) = 1;
  v183(a1, v623, v184);
  std::wstring::_Tidy_deallocate(v623);
  v185 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesOpacity");
  LOBYTE(v186) = 1;
  v185(a1, v623, v186);
  std::wstring::_Tidy_deallocate(v623);
  v187 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.TexturesSpecular");
  LOBYTE(v188) = 1;
  v187(a1, v623, v188);
  std::wstring::_Tidy_deallocate(v623);
  v189 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Renderer.Wireframe");
  v189(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v190 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"/Internal/Shader.DiagnosticsEnabled");
  v190(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v191 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"/Internal/SkinnedAnimation.Behaviour");
  v191(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v192 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.Camera.Contrast");
  v192(a1, v623, v193, 1);
  std::wstring::_Tidy_deallocate(v623);
  v194 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.Camera.ExposureValue");
  v194(a1, v623, v195, 1);
  std::wstring::_Tidy_deallocate(v623);
  v196 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Background.Camera.ExposureValueIsBrightness");
  v196(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v197 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Background.Camera.ToneMappingEnabled");
  LOBYTE(v198) = 1;
  v197(a1, v623, v198);
  std::wstring::_Tidy_deallocate(v623);
  v199 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterDensityGlobal");
  v199(a1, v623, v200, 1);
  std::wstring::_Tidy_deallocate(v623);
  v201 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterDensityHighlights");
  v201(a1, v623, v202, 1);
  std::wstring::_Tidy_deallocate(v623);
  v203 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterDensityMidtones");
  v203(a1, v623, v204, 1);
  std::wstring::_Tidy_deallocate(v623);
  v205 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterDensityShadows");
  v205(a1, v623, v206, 1);
  std::wstring::_Tidy_deallocate(v623);
  v207 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterHueGlobal");
  v207(a1, v623, v208, 1);
  std::wstring::_Tidy_deallocate(v623);
  v209 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterHueHighlights");
  v209(a1, v623, v210, 1);
  std::wstring::_Tidy_deallocate(v623);
  v211 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterHueMidtones");
  v211(a1, v623, v212, 1);
  std::wstring::_Tidy_deallocate(v623);
  v213 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ColorFilterHueShadows");
  v213(a1, v623, v214, 1);
  std::wstring::_Tidy_deallocate(v623);
  v215 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ExposureHighlights");
  v215(a1, v623, v216, 1);
  std::wstring::_Tidy_deallocate(v623);
  v217 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ExposureMidtones");
  v217(a1, v623, v218, 1);
  std::wstring::_Tidy_deallocate(v623);
  v219 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.ExposureShadows");
  v219(a1, v623, v220, 1);
  std::wstring::_Tidy_deallocate(v623);
  v221 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.SaturationGlobal");
  v221(a1, v623, v222, 1);
  std::wstring::_Tidy_deallocate(v623);
  v223 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.SaturationHighlights");
  v223(a1, v623, v224, 1);
  std::wstring::_Tidy_deallocate(v623);
  v225 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.SaturationMidtones");
  v225(a1, v623, v226, 1);
  std::wstring::_Tidy_deallocate(v623);
  v227 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.SaturationShadows");
  v227(a1, v623, v228, 1);
  std::wstring::_Tidy_deallocate(v623);
  v229 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, &dword_180169474);
  v231 = v230;
  std::wstring::wstring(v623, L"Background.ColorGrading.TransformData");
  v229(a1, v623, v231, 1);
  std::wstring::_Tidy_deallocate(v623);
  v232 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, &dword_180169474);
  v234 = v233;
  std::wstring::wstring(v623, L"Background.ColorGrading.TransformDataFormat");
  v232(a1, v623, v234, 1);
  std::wstring::_Tidy_deallocate(v623);
  v235 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ColorGrading.TransformWeight");
  v235(a1, v623, v236, 1);
  std::wstring::_Tidy_deallocate(v623);
  v237 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientOriginColorA");
  v237(a1, v623, v238, 1);
  std::wstring::_Tidy_deallocate(v623);
  v239 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientOriginColorB");
  v239(a1, v623, v240, 1);
  std::wstring::_Tidy_deallocate(v623);
  v241 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientOriginColorG");
  v241(a1, v623, v242, 1);
  std::wstring::_Tidy_deallocate(v623);
  v243 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientOriginColorR");
  v243(a1, v623, v244, 1);
  std::wstring::_Tidy_deallocate(v623);
  v245 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing1ColorA");
  v245(a1, v623, v246, 1);
  std::wstring::_Tidy_deallocate(v623);
  v247 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing1ColorB");
  v247(a1, v623, v248, 1);
  std::wstring::_Tidy_deallocate(v623);
  v249 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing1ColorG");
  v249(a1, v623, v250, 1);
  std::wstring::_Tidy_deallocate(v623);
  v251 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing1ColorR");
  v251(a1, v623, v252, 1);
  std::wstring::_Tidy_deallocate(v623);
  v253 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing1Width");
  v253(a1, v623, v254, 1);
  std::wstring::_Tidy_deallocate(v623);
  v255 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing2ColorA");
  v255(a1, v623, v256, 1);
  std::wstring::_Tidy_deallocate(v623);
  v257 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing2ColorB");
  v257(a1, v623, v258, 1);
  std::wstring::_Tidy_deallocate(v623);
  v259 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing2ColorG");
  v259(a1, v623, v260, 1);
  std::wstring::_Tidy_deallocate(v623);
  v261 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing2ColorR");
  v261(a1, v623, v262, 1);
  std::wstring::_Tidy_deallocate(v623);
  v263 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing2Width");
  v263(a1, v623, v264, 1);
  std::wstring::_Tidy_deallocate(v623);
  v265 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing3ColorA");
  v265(a1, v623, v266, 1);
  std::wstring::_Tidy_deallocate(v623);
  v267 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing3ColorB");
  v267(a1, v623, v268, 1);
  std::wstring::_Tidy_deallocate(v623);
  v269 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing3ColorG");
  v269(a1, v623, v270, 1);
  std::wstring::_Tidy_deallocate(v623);
  v271 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing3ColorR");
  v271(a1, v623, v272, 1);
  std::wstring::_Tidy_deallocate(v623);
  v273 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.GradientRing3Width");
  v273(a1, v623, v274, 1);
  std::wstring::_Tidy_deallocate(v623);
  v275 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.GroundPlane.ShadowWeight");
  v275(a1, v623, v276, 1);
  std::wstring::_Tidy_deallocate(v623);
  v277 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteBlendMode");
  v277(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v278 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteCentreX");
  v278(a1, v623, v279, 1);
  std::wstring::_Tidy_deallocate(v623);
  v280 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteCentreY");
  v280(a1, v623, v281, 1);
  std::wstring::_Tidy_deallocate(v623);
  v282 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteColorA");
  v282(a1, v623, v283, 1);
  std::wstring::_Tidy_deallocate(v623);
  v284 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteColorB");
  v284(a1, v623, v285, 1);
  std::wstring::_Tidy_deallocate(v623);
  v286 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteColorG");
  v286(a1, v623, v287, 1);
  std::wstring::_Tidy_deallocate(v623);
  v288 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteColorR");
  v288(a1, v623, v289, 1);
  std::wstring::_Tidy_deallocate(v623);
  v290 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteStretch");
  v290(a1, v623, v291, 1);
  std::wstring::_Tidy_deallocate(v623);
  v292 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Background.ImageProcessing.VignetteWeight");
  v292(a1, v623, v293, 1);
  std::wstring::_Tidy_deallocate(v623);
  v294 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Camera.Behaviour");
  v294(a1, v623, 1);
  std::wstring::_Tidy_deallocate(v623);
  v295 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.Contrast");
  v295(a1, v623, v296, 1);
  std::wstring::_Tidy_deallocate(v623);
  v297 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.DefaultElevation");
  v297(a1, v623, v298, 1);
  std::wstring::_Tidy_deallocate(v623);
  v299 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.ElevationLowerLimit (degrees)");
  v299(a1, v623, v300, 1);
  std::wstring::_Tidy_deallocate(v623);
  v301 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.ElevationReturnTime (s)");
  v301(a1, v623, v302, 1);
  std::wstring::_Tidy_deallocate(v623);
  v303 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.ElevationReturnWaitTime (s)");
  v303(a1, v623, v304, 1);
  std::wstring::_Tidy_deallocate(v623);
  v305 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.ElevationUpperLimit (degrees)");
  v305(a1, v623, v306, 1);
  std::wstring::_Tidy_deallocate(v623);
  v307 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.ExposureValue");
  v307(a1, v623, v308, 1);
  std::wstring::_Tidy_deallocate(v623);
  v309 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Camera.ExposureValueIsBrightness");
  v309(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v310 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FieldOfView (Degrees)");
  v310(a1, v623, v311, 1);
  std::wstring::_Tidy_deallocate(v623);
  v312 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Camera.FrameOnModelLoad");
  LOBYTE(v313) = 1;
  v312(a1, v623, v313);
  std::wstring::_Tidy_deallocate(v623);
  v314 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Camera.FramingBehaviour");
  v314(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v315 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FramingElevation");
  v315(a1, v623, v316, 1);
  std::wstring::_Tidy_deallocate(v623);
  v317 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FramingPositionY");
  v317(a1, v623, v318, 1);
  std::wstring::_Tidy_deallocate(v623);
  v319 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FramingRadius");
  v319(a1, v623, v320, 1);
  std::wstring::_Tidy_deallocate(v623);
  v321 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FramingRotation");
  v321(a1, v623, v322, 1);
  std::wstring::_Tidy_deallocate(v623);
  v323 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.FramingTime");
  v323(a1, v623, v324, 1);
  std::wstring::_Tidy_deallocate(v623);
  v325 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.IdleRotationSpeed (degrees/s)");
  v325(a1, v623, v326, 1);
  std::wstring::_Tidy_deallocate(v623);
  v327 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.IdleRotationSpinupTime (s)");
  v327(a1, v623, v328, 1);
  std::wstring::_Tidy_deallocate(v623);
  v329 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.IdleRotationWaitTime (s)");
  v329(a1, v623, v330, 1);
  std::wstring::_Tidy_deallocate(v623);
  v331 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.MaxDistance");
  v331(a1, v623, v332, 1);
  std::wstring::_Tidy_deallocate(v623);
  v333 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.MinDistance");
  v333(a1, v623, v334, 1);
  std::wstring::_Tidy_deallocate(v623);
  v335 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Position.X");
  v335(a1, v623, v336, 1);
  std::wstring::_Tidy_deallocate(v623);
  v337 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Position.Y");
  v337(a1, v623, v338, 1);
  std::wstring::_Tidy_deallocate(v623);
  v339 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Position.Z");
  v339(a1, v623, v340, 1);
  std::wstring::_Tidy_deallocate(v623);
  v341 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Rotation.W");
  v341(a1, v623, v342, 1);
  std::wstring::_Tidy_deallocate(v623);
  v343 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Rotation.X");
  v343(a1, v623, v344, 1);
  std::wstring::_Tidy_deallocate(v623);
  v345 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Rotation.Y");
  v345(a1, v623, v346, 1);
  std::wstring::_Tidy_deallocate(v623);
  v347 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Camera.State.Rotation.Z");
  v347(a1, v623, v348, 1);
  std::wstring::_Tidy_deallocate(v623);
  v349 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Camera.ToneMappingEnabled");
  LOBYTE(v350) = 1;
  v349(a1, v623, v350);
  std::wstring::_Tidy_deallocate(v623);
  v351 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Camera.ZoomStopsAnimation");
  v351(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v352 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterDensityGlobal");
  v352(a1, v623, v353, 1);
  std::wstring::_Tidy_deallocate(v623);
  v354 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterDensityHighlights");
  v354(a1, v623, v355, 1);
  std::wstring::_Tidy_deallocate(v623);
  v356 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterDensityMidtones");
  v356(a1, v623, v357, 1);
  std::wstring::_Tidy_deallocate(v623);
  v358 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterDensityShadows");
  v358(a1, v623, v359, 1);
  std::wstring::_Tidy_deallocate(v623);
  v360 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterHueGlobal");
  v360(a1, v623, v361, 1);
  std::wstring::_Tidy_deallocate(v623);
  v362 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterHueHighlights");
  v362(a1, v623, v363, 1);
  std::wstring::_Tidy_deallocate(v623);
  v364 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterHueMidtones");
  v364(a1, v623, v365, 1);
  std::wstring::_Tidy_deallocate(v623);
  v366 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ColorFilterHueShadows");
  v366(a1, v623, v367, 1);
  std::wstring::_Tidy_deallocate(v623);
  v368 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ExposureHighlights");
  v368(a1, v623, v369, 1);
  std::wstring::_Tidy_deallocate(v623);
  v370 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ExposureMidtones");
  v370(a1, v623, v371, 1);
  std::wstring::_Tidy_deallocate(v623);
  v372 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.ExposureShadows");
  v372(a1, v623, v373, 1);
  std::wstring::_Tidy_deallocate(v623);
  v374 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.SaturationGlobal");
  v374(a1, v623, v375, 1);
  std::wstring::_Tidy_deallocate(v623);
  v376 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.SaturationHighlights");
  v376(a1, v623, v377, 1);
  std::wstring::_Tidy_deallocate(v623);
  v378 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.SaturationMidtones");
  v378(a1, v623, v379, 1);
  std::wstring::_Tidy_deallocate(v623);
  v380 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.SaturationShadows");
  v380(a1, v623, v381, 1);
  std::wstring::_Tidy_deallocate(v623);
  v382 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, &dword_180169474);
  v384 = v383;
  std::wstring::wstring(v623, L"ColorGrading.TransformData");
  v382(a1, v623, v384, 1);
  std::wstring::_Tidy_deallocate(v623);
  v385 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 176LL);
  std::wstring::wstring(v622, &dword_180169474);
  v387 = v386;
  std::wstring::wstring(v623, L"ColorGrading.TransformDataFormat");
  v385(a1, v623, v387, 1);
  std::wstring::_Tidy_deallocate(v623);
  v388 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ColorGrading.TransformWeight");
  v388(a1, v623, v389, 1);
  std::wstring::_Tidy_deallocate(v623);
  v390 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"GroundPlane.BottomGridOpacity");
  v390(a1, v623, v391, 1);
  std::wstring::_Tidy_deallocate(v623);
  v392 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"GroundPlane.BottomVisible");
  v392(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v393 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"ImageProcessing.BloomEnabled");
  LOBYTE(v394) = 1;
  v393(a1, v623, v394);
  std::wstring::_Tidy_deallocate(v623);
  v395 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"ImageProcessing.BloomQuality");
  v395(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v396 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.BloomWeight");
  v396(a1, v623, v397, 1);
  std::wstring::_Tidy_deallocate(v623);
  v398 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"ImageProcessing.Enabled");
  LOBYTE(v399) = 1;
  v398(a1, v623, v399);
  std::wstring::_Tidy_deallocate(v623);
  v400 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"ImageProcessing.PlanarReflectionBlur");
  LOBYTE(v401) = 1;
  v400(a1, v623, v401);
  std::wstring::_Tidy_deallocate(v623);
  v402 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"ImageProcessing.PlanarReflectionDirect");
  v402(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v403 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"ImageProcessing.PlanarReflectionEnabled");
  LOBYTE(v404) = 1;
  v403(a1, v623, v404);
  std::wstring::_Tidy_deallocate(v623);
  v405 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"ImageProcessing.PlanarReflectionQuality");
  v405(a1, v623, 2);
  std::wstring::_Tidy_deallocate(v623);
  v406 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.PlanarReflectionWeight");
  v406(a1, v623, v407, 1);
  std::wstring::_Tidy_deallocate(v623);
  v408 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteBlendMode");
  v408(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v409 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteCentreX");
  v409(a1, v623, v410, 1);
  std::wstring::_Tidy_deallocate(v623);
  v411 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteCentreY");
  v411(a1, v623, v412, 1);
  std::wstring::_Tidy_deallocate(v623);
  v413 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteColorA");
  v413(a1, v623, v414, 1);
  std::wstring::_Tidy_deallocate(v623);
  v415 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteColorB");
  v415(a1, v623, v416, 1);
  std::wstring::_Tidy_deallocate(v623);
  v417 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteColorG");
  v417(a1, v623, v418, 1);
  std::wstring::_Tidy_deallocate(v623);
  v419 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteColorR");
  v419(a1, v623, v420, 1);
  std::wstring::_Tidy_deallocate(v623);
  v421 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteStretch");
  v421(a1, v623, v422, 1);
  std::wstring::_Tidy_deallocate(v623);
  v423 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"ImageProcessing.VignetteWeight");
  v423(a1, v623, v424, 1);
  std::wstring::_Tidy_deallocate(v623);
  v425 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundColorAmount");
  v425(a1, v623, v426, 1);
  std::wstring::_Tidy_deallocate(v623);
  v427 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundColorB");
  v427(a1, v623, v428, 1);
  std::wstring::_Tidy_deallocate(v623);
  v429 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundColorG");
  v429(a1, v623, v430, 1);
  std::wstring::_Tidy_deallocate(v623);
  v431 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundColorR");
  v431(a1, v623, v432, 1);
  std::wstring::_Tidy_deallocate(v623);
  v433 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundLighting");
  v433(a1, v623, v434, 1);
  std::wstring::_Tidy_deallocate(v623);
  v435 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundShadowAmount");
  v435(a1, v623, v436, 1);
  std::wstring::_Tidy_deallocate(v623);
  v437 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.BackgroundShadowFalloff");
  v437(a1, v623, v438, 1);
  std::wstring::_Tidy_deallocate(v623);
  v439 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.DirectEnabled");
  LOBYTE(v440) = 1;
  v439(a1, v623, v440);
  std::wstring::_Tidy_deallocate(v623);
  v441 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.DirectIntensity");
  v441(a1, v623, v442, 1);
  std::wstring::_Tidy_deallocate(v623);
  v443 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EmissiveIntensity");
  v443(a1, v623, v444, 1);
  std::wstring::_Tidy_deallocate(v623);
  v445 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentColorB");
  v445(a1, v623, v446, 1);
  std::wstring::_Tidy_deallocate(v623);
  v447 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentColorG");
  v447(a1, v623, v448, 1);
  std::wstring::_Tidy_deallocate(v623);
  v449 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentColorR");
  v449(a1, v623, v450, 1);
  std::wstring::_Tidy_deallocate(v623);
  v451 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentEnabled");
  LOBYTE(v452) = 1;
  v451(a1, v623, v452);
  std::wstring::_Tidy_deallocate(v623);
  v453 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentIndex");
  v453(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v454 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentIntensity");
  v454(a1, v623, v455, 1);
  std::wstring::_Tidy_deallocate(v623);
  v456 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.EnvironmentRotation");
  v456(a1, v623, v457, 1);
  std::wstring::_Tidy_deallocate(v623);
  v458 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light0_CameraOrientationTracking");
  v458(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v459 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light0_CameraRelative");
  v459(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v460 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ColorB");
  v460(a1, v623, v461, 1);
  std::wstring::_Tidy_deallocate(v623);
  v462 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ColorG");
  v462(a1, v623, v463, 1);
  std::wstring::_Tidy_deallocate(v623);
  v464 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ColorR");
  v464(a1, v623, v465, 1);
  std::wstring::_Tidy_deallocate(v623);
  v466 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light0_Enabled");
  LOBYTE(v467) = 1;
  v466(a1, v623, v467);
  std::wstring::_Tidy_deallocate(v623);
  v468 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_FrustumEdgeFalloff");
  v468(a1, v623, v469, 1);
  std::wstring::_Tidy_deallocate(v623);
  v470 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_Intensity");
  v470(a1, v623, v471, 1);
  std::wstring::_Tidy_deallocate(v623);
  v472 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light0_IntensityMode");
  v472(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v473 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_PositionX");
  v473(a1, v623, v474, 1);
  std::wstring::_Tidy_deallocate(v623);
  v475 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_PositionY");
  v475(a1, v623, v476, 1);
  std::wstring::_Tidy_deallocate(v623);
  v477 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_PositionZ");
  v477(a1, v623, v478, 1);
  std::wstring::_Tidy_deallocate(v623);
  v479 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_Radius");
  v479(a1, v623, v480, 1);
  std::wstring::_Tidy_deallocate(v623);
  v481 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowBufferSize");
  v481(a1, v623, v482, 1);
  std::wstring::_Tidy_deallocate(v623);
  v483 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowEnabled");
  LOBYTE(v484) = 1;
  v483(a1, v623, v484);
  std::wstring::_Tidy_deallocate(v623);
  v485 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowFarClip");
  v485(a1, v623, v486, 1);
  std::wstring::_Tidy_deallocate(v623);
  v487 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowFieldOfView");
  v487(a1, v623, v488, 1);
  std::wstring::_Tidy_deallocate(v623);
  v489 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowFrustumSize");
  v489(a1, v623, v490, 1);
  std::wstring::_Tidy_deallocate(v623);
  v491 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_ShadowNearClip");
  v491(a1, v623, v492, 1);
  std::wstring::_Tidy_deallocate(v623);
  v493 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_SpotAngle");
  v493(a1, v623, v494, 1);
  std::wstring::_Tidy_deallocate(v623);
  v495 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_TargetX");
  v495(a1, v623, v496, 1);
  std::wstring::_Tidy_deallocate(v623);
  v497 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_TargetY");
  v497(a1, v623, v498, 1);
  std::wstring::_Tidy_deallocate(v623);
  v499 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light0_TargetZ");
  v499(a1, v623, v500, 1);
  std::wstring::_Tidy_deallocate(v623);
  v501 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light0_Type");
  v501(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v502 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light1_CameraOrientationTracking");
  v502(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v503 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light1_CameraRelative");
  v503(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v504 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ColorB");
  v504(a1, v623, v505, 1);
  std::wstring::_Tidy_deallocate(v623);
  v506 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ColorG");
  v506(a1, v623, v507, 1);
  std::wstring::_Tidy_deallocate(v623);
  v508 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ColorR");
  v508(a1, v623, v509, 1);
  std::wstring::_Tidy_deallocate(v623);
  v510 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light1_Enabled");
  LOBYTE(v511) = 1;
  v510(a1, v623, v511);
  std::wstring::_Tidy_deallocate(v623);
  v512 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_FrustumEdgeFalloff");
  v512(a1, v623, v513, 1);
  std::wstring::_Tidy_deallocate(v623);
  v514 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_Intensity");
  v514(a1, v623, v515, 1);
  std::wstring::_Tidy_deallocate(v623);
  v516 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light1_IntensityMode");
  v516(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v517 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_PositionX");
  v517(a1, v623, v518, 1);
  std::wstring::_Tidy_deallocate(v623);
  v519 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_PositionY");
  v519(a1, v623, v520, 1);
  std::wstring::_Tidy_deallocate(v623);
  v521 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_PositionZ");
  v521(a1, v623, v522, 1);
  std::wstring::_Tidy_deallocate(v623);
  v523 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_Radius");
  v523(a1, v623, v524, 1);
  std::wstring::_Tidy_deallocate(v623);
  v525 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowBufferSize");
  v525(a1, v623, v526, 1);
  std::wstring::_Tidy_deallocate(v623);
  v527 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowEnabled");
  LOBYTE(v528) = 1;
  v527(a1, v623, v528);
  std::wstring::_Tidy_deallocate(v623);
  v529 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowFarClip");
  v529(a1, v623, v530, 1);
  std::wstring::_Tidy_deallocate(v623);
  v531 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowFieldOfView");
  v531(a1, v623, v532, 1);
  std::wstring::_Tidy_deallocate(v623);
  v533 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowFrustumSize");
  v533(a1, v623, v534, 1);
  std::wstring::_Tidy_deallocate(v623);
  v535 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_ShadowNearClip");
  v535(a1, v623, v536, 1);
  std::wstring::_Tidy_deallocate(v623);
  v537 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_SpotAngle");
  v537(a1, v623, v538, 1);
  std::wstring::_Tidy_deallocate(v623);
  v539 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_TargetX");
  v539(a1, v623, v540, 1);
  std::wstring::_Tidy_deallocate(v623);
  v541 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_TargetY");
  v541(a1, v623, v542, 1);
  std::wstring::_Tidy_deallocate(v623);
  v543 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light1_TargetZ");
  v543(a1, v623, v544, 1);
  std::wstring::_Tidy_deallocate(v623);
  v545 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light1_Type");
  v545(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v546 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light2_CameraOrientationTracking");
  v546(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v547 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light2_CameraRelative");
  v547(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v548 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ColorB");
  v548(a1, v623, v549, 1);
  std::wstring::_Tidy_deallocate(v623);
  v550 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ColorG");
  v550(a1, v623, v551, 1);
  std::wstring::_Tidy_deallocate(v623);
  v552 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ColorR");
  v552(a1, v623, v553, 1);
  std::wstring::_Tidy_deallocate(v623);
  v554 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light2_Enabled");
  LOBYTE(v555) = 1;
  v554(a1, v623, v555);
  std::wstring::_Tidy_deallocate(v623);
  v556 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_FrustumEdgeFalloff");
  v556(a1, v623, v557, 1);
  std::wstring::_Tidy_deallocate(v623);
  v558 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_Intensity");
  v558(a1, v623, v559, 1);
  std::wstring::_Tidy_deallocate(v623);
  v560 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light2_IntensityMode");
  v560(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v561 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_PositionX");
  v561(a1, v623, v562, 1);
  std::wstring::_Tidy_deallocate(v623);
  v563 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_PositionY");
  v563(a1, v623, v564, 1);
  std::wstring::_Tidy_deallocate(v623);
  v565 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_PositionZ");
  v565(a1, v623, v566, 1);
  std::wstring::_Tidy_deallocate(v623);
  v567 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_Radius");
  v567(a1, v623, v568, 1);
  std::wstring::_Tidy_deallocate(v623);
  v569 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowBufferSize");
  v569(a1, v623, v570, 1);
  std::wstring::_Tidy_deallocate(v623);
  v571 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowEnabled");
  LOBYTE(v572) = 1;
  v571(a1, v623, v572);
  std::wstring::_Tidy_deallocate(v623);
  v573 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowFarClip");
  v573(a1, v623, v574, 1);
  std::wstring::_Tidy_deallocate(v623);
  v575 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowFieldOfView");
  v575(a1, v623, v576, 1);
  std::wstring::_Tidy_deallocate(v623);
  v577 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowFrustumSize");
  v577(a1, v623, v578, 1);
  std::wstring::_Tidy_deallocate(v623);
  v579 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_ShadowNearClip");
  v579(a1, v623, v580, 1);
  std::wstring::_Tidy_deallocate(v623);
  v581 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_SpotAngle");
  v581(a1, v623, v582, 1);
  std::wstring::_Tidy_deallocate(v623);
  v583 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_TargetX");
  v583(a1, v623, v584, 1);
  std::wstring::_Tidy_deallocate(v623);
  v585 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_TargetY");
  v585(a1, v623, v586, 1);
  std::wstring::_Tidy_deallocate(v623);
  v587 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Lighting.Light2_TargetZ");
  v587(a1, v623, v588, 1);
  std::wstring::_Tidy_deallocate(v623);
  v589 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 152LL);
  std::wstring::wstring(v623, L"Lighting.Light2_Type");
  v589(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v590 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Lighting.MasterEnabled");
  LOBYTE(v591) = 1;
  v590(a1, v623, v591);
  std::wstring::_Tidy_deallocate(v623);
  v592 = *(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Model.PositionAlignBase");
  LOBYTE(v593) = 1;
  v592(a1, v623, v593);
  std::wstring::_Tidy_deallocate(v623);
  v594 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.PositionOffsetX");
  v594(a1, v623, v595, 1);
  std::wstring::_Tidy_deallocate(v623);
  v596 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.PositionOffsetY");
  v596(a1, v623, v597, 1);
  std::wstring::_Tidy_deallocate(v623);
  v598 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.PositionOffsetZ");
  v598(a1, v623, v599, 1);
  std::wstring::_Tidy_deallocate(v623);
  v600 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.RelativeModelLoadScale");
  v600(a1, v623, v601, 1);
  std::wstring::_Tidy_deallocate(v623);
  v602 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.RotationOffsetAngle");
  v602(a1, v623, v603, 1);
  std::wstring::_Tidy_deallocate(v623);
  v604 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.RotationOffsetAxisX");
  v604(a1, v623, v605, 1);
  std::wstring::_Tidy_deallocate(v623);
  v606 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.RotationOffsetAxisY");
  v606(a1, v623, v607, 1);
  std::wstring::_Tidy_deallocate(v623);
  v608 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Model.RotationOffsetAxisZ");
  v608(a1, v623, v609, 1);
  std::wstring::_Tidy_deallocate(v623);
  v610 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Renderer.ClearColorA");
  v610(a1, v623, v611, 1);
  std::wstring::_Tidy_deallocate(v623);
  v612 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Renderer.ClearColorB");
  v612(a1, v623, v613, 1);
  std::wstring::_Tidy_deallocate(v623);
  v614 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Renderer.ClearColorG");
  v614(a1, v623, v615, 1);
  std::wstring::_Tidy_deallocate(v623);
  v616 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Renderer.ClearColorOverride");
  v616(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v617 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 168LL);
  std::wstring::wstring(v623, L"Renderer.ClearColorR");
  v617(a1, v623, v618, 1);
  std::wstring::_Tidy_deallocate(v623);
  v619 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Renderer.Compatibility.GLTFComplianceEnabled");
  v619(a1, v623, 0, 1);
  std::wstring::_Tidy_deallocate(v623);
  v620 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64))(*(_QWORD *)a1 + 144LL);
  std::wstring::wstring(v623, L"Shader.ForceNormalsForward");
  v620(a1, v623, 0, 1);
  return std::wstring::_Tidy_deallocate(v623);
}

```

## disassembly

```asm
0x18006d368  mov     rax, rsp
0x18006d36b  push    rbp
0x18006d36c  push    rbx
0x18006d36d  push    rsi
0x18006d36e  push    rdi
0x18006d36f  lea     rbp, [rax-5Fh]
0x18006d373  sub     rsp, 0F8h
0x18006d37a  movaps  xmmword ptr [rax-38h], xmm6
0x18006d37e  movaps  xmmword ptr [rax-48h], xmm8
0x18006d383  movaps  xmmword ptr [rax-58h], xmm9
0x18006d388  movaps  xmmword ptr [rax-68h], xmm11
0x18006d38d  movaps  xmmword ptr [rax-78h], xmm12
0x18006d392  movaps  xmmword ptr [rax-88h], xmm13
0x18006d39a  movaps  xmmword ptr [rax-98h], xmm14
0x18006d3a2  mov     rax, cs:__security_cookie
0x18006d3a9  xor     rax, rsp
0x18006d3ac  mov     [rbp+57h+var_98], rax
0x18006d3b0  mov     rsi, rcx
0x18006d3b3  mov     rax, [rcx]
0x18006d3b6  mov     rbx, [rax+90h]
0x18006d3bd  lea     rdx, aInternalApplic; "/Internal/Application.KeyboardDeveloper"...
0x18006d3c4  lea     rcx, [rbp+57h+var_B8]
0x18006d3c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d3cd  nop
0x18006d3ce  mov     r9d, 1
0x18006d3d4  xor     r8d, r8d
0x18006d3d7  lea     rdx, [rbp+57h+var_B8]
0x18006d3db  mov     rcx, rsi
0x18006d3de  mov     rax, rbx
0x18006d3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d3e6  nop
0x18006d3e7  lea     rcx, [rbp+57h+var_B8]
0x18006d3eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d3f0  mov     rax, [rsi]
0x18006d3f3  mov     rbx, [rax+90h]
0x18006d3fa  lea     rdx, aInternalBackgr; "/Internal/Background.EnableBackgroundCu"...
0x18006d401  lea     rcx, [rbp+57h+var_B8]
0x18006d405  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d40a  nop
0x18006d40b  mov     r9d, 1
0x18006d411  mov     r8b, r9b
0x18006d414  lea     rdx, [rbp+57h+var_B8]
0x18006d418  mov     rcx, rsi
0x18006d41b  mov     rax, rbx
0x18006d41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d423  nop
0x18006d424  lea     rcx, [rbp+57h+var_B8]
0x18006d428  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d42d  mov     rax, [rsi]
0x18006d430  mov     rbx, [rax+90h]
0x18006d437  lea     rdx, aInternalBackgr_0; "/Internal/Background.ImageProcessing.En"...
0x18006d43e  lea     rcx, [rbp+57h+var_B8]
0x18006d442  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d447  nop
0x18006d448  mov     r9d, 1
0x18006d44e  mov     r8b, r9b
0x18006d451  lea     rdx, [rbp+57h+var_B8]
0x18006d455  mov     rcx, rsi
0x18006d458  mov     rax, rbx
0x18006d45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d460  nop
0x18006d461  lea     rcx, [rbp+57h+var_B8]
0x18006d465  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d46a  mov     rax, [rsi]
0x18006d46d  mov     rbx, [rax+90h]
0x18006d474  lea     rdx, aInternalBugwor; "/Internal/BugWorkaroundOverride.MetalDe"...
0x18006d47b  lea     rcx, [rbp+57h+var_B8]
0x18006d47f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d484  nop
0x18006d485  mov     r9d, 1
0x18006d48b  xor     r8d, r8d
0x18006d48e  lea     rdx, [rbp+57h+var_B8]
0x18006d492  mov     rcx, rsi
0x18006d495  mov     rax, rbx
0x18006d498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d49d  nop
0x18006d49e  lea     rcx, [rbp+57h+var_B8]
0x18006d4a2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d4a7  mov     rax, [rsi]
0x18006d4aa  mov     rbx, [rax+90h]
0x18006d4b1  lea     rdx, aInternalBugwor_0; "/Internal/BugWorkaroundOverride.MetalIn"...
0x18006d4b8  lea     rcx, [rbp+57h+var_B8]
0x18006d4bc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d4c1  nop
0x18006d4c2  mov     r9d, 1
0x18006d4c8  xor     r8d, r8d
0x18006d4cb  lea     rdx, [rbp+57h+var_B8]
0x18006d4cf  mov     rcx, rsi
0x18006d4d2  mov     rax, rbx
0x18006d4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d4da  nop
0x18006d4db  lea     rcx, [rbp+57h+var_B8]
0x18006d4df  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d4e4  mov     rax, [rsi]
0x18006d4e7  mov     rbx, [rax+0A8h]
0x18006d4ee  lea     rdx, aInternalCamera; "/Internal/Camera.Distance"
0x18006d4f5  lea     rcx, [rbp+57h+var_B8]
0x18006d4f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d4fe  nop
0x18006d4ff  mov     r9d, 1
0x18006d505  movss   xmm2, cs:__real@3fe00000
0x18006d50d  lea     rdx, [rbp+57h+var_B8]
0x18006d511  mov     rcx, rsi
0x18006d514  mov     rax, rbx
0x18006d517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d51c  nop
0x18006d51d  lea     rcx, [rbp+57h+var_B8]
0x18006d521  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d526  mov     rax, [rsi]
0x18006d529  mov     rbx, [rax+0A8h]
0x18006d530  lea     rdx, aInternalCamera_1; "/Internal/Camera.Elevation (degrees)"
0x18006d537  lea     rcx, [rbp+57h+var_B8]
0x18006d53b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d540  nop
0x18006d541  mov     r9d, 1
0x18006d547  movss   xmm13, cs:__real@41700000
0x18006d550  movaps  xmm2, xmm13
0x18006d554  lea     rdx, [rbp+57h+var_B8]
0x18006d558  mov     rcx, rsi
0x18006d55b  mov     rax, rbx
0x18006d55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d563  nop
0x18006d564  lea     rcx, [rbp+57h+var_B8]
0x18006d568  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d56d  mov     rax, [rsi]
0x18006d570  mov     rbx, [rax+0A8h]
0x18006d577  lea     rdx, aInternalCamera_0; "/Internal/Camera.Rotation (degrees)"
0x18006d57e  lea     rcx, [rbp+57h+var_B8]
0x18006d582  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d587  nop
0x18006d588  mov     r9d, 1
0x18006d58e  movss   xmm14, cs:__real@c2b40000
0x18006d597  movaps  xmm2, xmm14
0x18006d59b  lea     rdx, [rbp+57h+var_B8]
0x18006d59f  mov     rcx, rsi
0x18006d5a2  mov     rax, rbx
0x18006d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5aa  nop
0x18006d5ab  lea     rcx, [rbp+57h+var_B8]
0x18006d5af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d5b4  mov     rax, [rsi]
0x18006d5b7  mov     rbx, [rax+90h]
0x18006d5be  lea     rdx, aInternalCpupro_0; "/Internal/CpuProfiling.DisplayFrameTimi"...
0x18006d5c5  lea     rcx, [rbp+57h+var_B8]
0x18006d5c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d5ce  nop
0x18006d5cf  mov     r9d, 1
0x18006d5d5  xor     r8d, r8d
0x18006d5d8  lea     rdx, [rbp+57h+var_B8]
0x18006d5dc  mov     rcx, rsi
0x18006d5df  mov     rax, rbx
0x18006d5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5e7  nop
0x18006d5e8  lea     rcx, [rbp+57h+var_B8]
0x18006d5ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d5f1  mov     rax, [rsi]
0x18006d5f4  mov     rbx, [rax+90h]
0x18006d5fb  lea     rdx, aInternalCpupro; "/Internal/CpuProfiling.Enabled"
0x18006d602  lea     rcx, [rbp+57h+var_B8]
0x18006d606  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d60b  nop
0x18006d60c  mov     r9d, 1
0x18006d612  mov     r8b, r9b
0x18006d615  lea     rdx, [rbp+57h+var_B8]
0x18006d619  mov     rcx, rsi
0x18006d61c  mov     rax, rbx
0x18006d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d624  nop
0x18006d625  lea     rcx, [rbp+57h+var_B8]
0x18006d629  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d62e  mov     rax, [rsi]
0x18006d631  mov     rbx, [rax+0A8h]
0x18006d638  lea     rdx, aInternalDebugV; "/Internal/Debug.Value"
0x18006d63f  lea     rcx, [rbp+57h+var_B8]
0x18006d643  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d648  nop
0x18006d649  mov     r9d, 1
0x18006d64f  movss   xmm11, cs:__real@3f800000
0x18006d658  movaps  xmm2, xmm11
0x18006d65c  lea     rdx, [rbp+57h+var_B8]
0x18006d660  mov     rcx, rsi
0x18006d663  mov     rax, rbx
0x18006d666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d66b  nop
0x18006d66c  lea     rcx, [rbp+57h+var_B8]
0x18006d670  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d675  mov     rax, [rsi]
0x18006d678  mov     rbx, [rax+90h]
0x18006d67f  lea     rdx, aInternalGpupro_4; "/Internal/GpuProfiling.DisplayClippingP"...
0x18006d686  lea     rcx, [rbp+57h+var_B8]
0x18006d68a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d68f  nop
0x18006d690  mov     r9d, 1
0x18006d696  xor     r8d, r8d
0x18006d699  lea     rdx, [rbp+57h+var_B8]
0x18006d69d  mov     rcx, rsi
0x18006d6a0  mov     rax, rbx
0x18006d6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6a8  nop
0x18006d6a9  lea     rcx, [rbp+57h+var_B8]
0x18006d6ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d6b2  mov     rax, [rsi]
0x18006d6b5  mov     rbx, [rax+90h]
0x18006d6bc  lea     rdx, aInternalGpupro_1; "/Internal/GpuProfiling.DisplayClippingP"...
0x18006d6c3  lea     rcx, [rbp+57h+var_B8]
0x18006d6c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d6cc  nop
0x18006d6cd  mov     r9d, 1
0x18006d6d3  xor     r8d, r8d
0x18006d6d6  lea     rdx, [rbp+57h+var_B8]
0x18006d6da  mov     rcx, rsi
0x18006d6dd  mov     rax, rbx
0x18006d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6e5  nop
0x18006d6e6  lea     rcx, [rbp+57h+var_B8]
0x18006d6ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d6ef  mov     rax, [rsi]
0x18006d6f2  mov     rbx, [rax+90h]
0x18006d6f9  lea     rdx, aInternalGpupro_3; "/Internal/GpuProfiling.DisplayDetailFra"...
0x18006d700  lea     rcx, [rbp+57h+var_B8]
0x18006d704  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d709  nop
0x18006d70a  mov     r9d, 1
0x18006d710  mov     r8b, r9b
0x18006d713  lea     rdx, [rbp+57h+var_B8]
0x18006d717  mov     rcx, rsi
0x18006d71a  mov     rax, rbx
0x18006d71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d722  nop
0x18006d723  lea     rcx, [rbp+57h+var_B8]
0x18006d727  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d72c  mov     rax, [rsi]
0x18006d72f  mov     rbx, [rax+90h]
0x18006d736  lea     rdx, aInternalGpupro_8; "/Internal/GpuProfiling.DisplayFrameTimi"...
0x18006d73d  lea     rcx, [rbp+57h+var_B8]
0x18006d741  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d746  nop
0x18006d747  mov     r9d, 1
0x18006d74d  xor     r8d, r8d
0x18006d750  lea     rdx, [rbp+57h+var_B8]
0x18006d754  mov     rcx, rsi
0x18006d757  mov     rax, rbx
0x18006d75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d75f  nop
0x18006d760  lea     rcx, [rbp+57h+var_B8]
0x18006d764  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d769  mov     rax, [rsi]
0x18006d76c  mov     rbx, [rax+90h]
0x18006d773  lea     rdx, aInternalGpupro_6; "/Internal/GpuProfiling.DisplayPixelShad"...
0x18006d77a  lea     rcx, [rbp+57h+var_B8]
0x18006d77e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d783  nop
0x18006d784  mov     r9d, 1
0x18006d78a  xor     r8d, r8d
0x18006d78d  lea     rdx, [rbp+57h+var_B8]
0x18006d791  mov     rcx, rsi
0x18006d794  mov     rax, rbx
0x18006d797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d79c  nop
0x18006d79d  lea     rcx, [rbp+57h+var_B8]
0x18006d7a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d7a6  mov     rax, [rsi]
0x18006d7a9  mov     rbx, [rax+90h]
0x18006d7b0  lea     rdx, aInternalGpupro_7; "/Internal/GpuProfiling.DisplaySceneTimi"...
0x18006d7b7  lea     rcx, [rbp+57h+var_B8]
0x18006d7bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d7c0  nop
0x18006d7c1  mov     r9d, 1
0x18006d7c7  xor     r8d, r8d
0x18006d7ca  lea     rdx, [rbp+57h+var_B8]
0x18006d7ce  mov     rcx, rsi
0x18006d7d1  mov     rax, rbx
0x18006d7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7d9  nop
0x18006d7da  lea     rcx, [rbp+57h+var_B8]
0x18006d7de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d7e3  mov     rax, [rsi]
0x18006d7e6  mov     rbx, [rax+90h]
0x18006d7ed  lea     rdx, aInternalGpupro_5; "/Internal/GpuProfiling.DisplaySubmitted"...
0x18006d7f4  lea     rcx, [rbp+57h+var_B8]
0x18006d7f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d7fd  nop
0x18006d7fe  mov     r9d, 1
0x18006d804  xor     r8d, r8d
0x18006d807  lea     rdx, [rbp+57h+var_B8]
0x18006d80b  mov     rcx, rsi
0x18006d80e  mov     rax, rbx
0x18006d811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d816  nop
0x18006d817  lea     rcx, [rbp+57h+var_B8]
0x18006d81b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d820  mov     rax, [rsi]
0x18006d823  mov     rbx, [rax+90h]
0x18006d82a  lea     rdx, aInternalGpupro_2; "/Internal/GpuProfiling.DisplaySubmitted"...
0x18006d831  lea     rcx, [rbp+57h+var_B8]
0x18006d835  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006d83a  nop
0x18006d83b  mov     r9d, 1
0x18006d841  xor     r8d, r8d
0x18006d844  lea     rdx, [rbp+57h+var_B8]
  ... truncated ...
```
