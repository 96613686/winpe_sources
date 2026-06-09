# Babylon::NativeEngine::Initialize(Napi::Env)

- ea: `0x180063370`
- end: `0x18006cbab`
- name: `?Initialize@NativeEngine@Babylon@@SAXVEnv@Napi@@@Z`
- size: `38971`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004e140`

## callees

- `0x180032b80`
- `0x180033070`
- `0x1800332f0`
- `0x180033480`
- `0x180034690`
- `0x180034870`
- `0x18003e840`
- `0x18004eb80`
- `0x18004ee10`
- `0x18004ef30`
- `0x1800613f0`
- `0x180063370`
- `0x18006cdd0`
- `0x18006cea0`
- `0x18039da00`
- `0x18039dd10`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ed40`
- `0x18039f8e0`
- `0x1803aceb0`

## string_xrefs

- `0x18006344f`: `PROTOCOL_VERSION`
- `0x180067d8c`: `ALPHA_COMBINE`
- `0x1800687f9`: `STENCIL_OP_FAIL_S_REPLACE`
- `0x180068c71`: `STENCIL_OP_FAIL_Z_REPLACE`
- `0x1800690e9`: `STENCIL_OP_PASS_Z_REPLACE`
- `0x18006946b`: `COMMAND_DELETEVERTEXARRAY`
- `0x180069522`: `COMMAND_DELETEINDEXBUFFER`
- `0x1800695d9`: `COMMAND_DELETEVERTEXBUFFER`
- `0x180069690`: `COMMAND_SETPROGRAM`
- `0x180069747`: `COMMAND_DELETEPROGRAM`
- `0x1800697fe`: `COMMAND_SETMATRICES`
- `0x1800698b5`: `COMMAND_SETMATRIX`
- `0x18006996c`: `COMMAND_SETMATRIX3X3`
- `0x180069a23`: `COMMAND_SETMATRIX2X2`
- `0x180069ada`: `COMMAND_SETINT`
- `0x180069b91`: `COMMAND_SETINTARRAY`
- `0x180069c48`: `COMMAND_SETINTARRAY2`
- `0x180069cff`: `COMMAND_SETINTARRAY3`
- `0x180069db6`: `COMMAND_SETINTARRAY4`
- `0x180069e6d`: `COMMAND_SETFLOATARRAY`
- `0x180069f24`: `COMMAND_SETFLOATARRAY2`
- `0x180069fdb`: `COMMAND_SETFLOATARRAY3`
- `0x18006a092`: `COMMAND_SETFLOATARRAY4`
- `0x18006a149`: `COMMAND_SETTEXTURESAMPLING`
- `0x18006a200`: `COMMAND_SETTEXTUREWRAPMODE`
- `0x18006a2b7`: `COMMAND_SETTEXTUREANISOTROPICLEVEL`
- `0x18006a36e`: `COMMAND_SETTEXTURE`
- `0x18006a425`: `COMMAND_UNSETTEXTURE`
- `0x18006a4dc`: `COMMAND_DISCARDALLTEXTURES`
- `0x18006a593`: `COMMAND_BINDVERTEXARRAY`
- `0x18006a64a`: `COMMAND_SETSTATE`
- `0x18006a701`: `COMMAND_SETZOFFSET`
- `0x18006a7b8`: `COMMAND_SETZOFFSETUNITS`
- `0x18006a86f`: `COMMAND_SETDEPTHTEST`
- `0x18006a926`: `COMMAND_SETDEPTHWRITE`
- `0x18006a9dd`: `COMMAND_SETCOLORWRITE`
- `0x18006aa94`: `COMMAND_SETBLENDMODE`
- `0x18006ab4b`: `COMMAND_SETFLOAT`
- `0x18006ac02`: `COMMAND_SETFLOAT2`
- `0x18006acb9`: `COMMAND_SETFLOAT3`
- `0x18006ad70`: `COMMAND_SETFLOAT4`
- `0x18006ae27`: `COMMAND_BINDFRAMEBUFFER`
- `0x18006aede`: `COMMAND_UNBINDFRAMEBUFFER`
- `0x18006af95`: `COMMAND_DELETEFRAMEBUFFER`
- `0x18006b04c`: `COMMAND_DRAWINDEXED`
- `0x18006b103`: `COMMAND_DRAWINDEXEDINSTANCED`
- `0x18006b1ba`: `COMMAND_DRAW`
- `0x18006b271`: `COMMAND_DRAWINSTANCED`
- `0x18006b328`: `COMMAND_CLEAR`
- `0x18006b3df`: `COMMAND_SETSTENCIL`
- `0x18006b496`: `COMMAND_SETVIEWPORT`
- `0x18006b54d`: `COMMAND_SETSCISSOR`
- `0x18006b601`: `COMMAND_COPYTEXTURE`
- `0x18006b7f5`: `createVertexArray`
- `0x18006b89e`: `createIndexBuffer`
- `0x18006b9e2`: `updateDynamicIndexBuffer`
- `0x18006ba84`: `createVertexBuffer`
- `0x18006bbc8`: `updateDynamicVertexBuffer`
- `0x18006bc6a`: `createProgram`
- `0x18006bd0c`: `createProgramAsync`
- `0x18006bef2`: `createTexture`
- `0x18006c4a4`: `deleteTexture`
- `0x18006c546`: `readTexture`
- `0x18006c5e8`: `createImageBitmap`
- `0x18006c72c`: `createFrameBuffer`
- `0x18006c98b`: `setCommandDataStream`
- `0x18006c9d4`: `submitCommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Babylon::NativeEngine::Initialize(__int64 a1)
{
  bgfx *v2; // rcx
  const struct bgfx::Caps *Caps; // rax
  __m128i v4; // xmm0
  __m128i v5; // xmm0
  __m128i v6; // xmm0
  __m128i v7; // xmm0
  __m128i v8; // xmm0
  __m128i v9; // xmm0
  __m128i v10; // xmm0
  __m128i v11; // xmm0
  __m128i v12; // xmm0
  __m128i v13; // xmm0
  __m128i v14; // xmm0
  __m128i v15; // xmm0
  __m128i v16; // xmm0
  __m128i v17; // xmm0
  __m128i v18; // xmm0
  __m128i v19; // xmm0
  __m128i v20; // xmm0
  __m128i v21; // xmm0
  __m128i v22; // xmm0
  __m128i v23; // xmm0
  __m128i v24; // xmm0
  __m128i v25; // xmm0
  __m128i v26; // xmm0
  __m128i v27; // xmm0
  __m128i v28; // xmm0
  __m128i v29; // xmm0
  __m128i v30; // xmm0
  __m128i v31; // xmm0
  __m128i v32; // xmm0
  __m128i v33; // xmm0
  __m128i v34; // xmm0
  __m128i v35; // xmm0
  __m128i v36; // xmm0
  __m128i v37; // xmm0
  __m128i v38; // xmm0
  __m128i v39; // xmm0
  __m128i v40; // xmm0
  __m128i v41; // xmm0
  __m128i v42; // xmm0
  __m128i v43; // xmm0
  __m128i v44; // xmm0
  __m128i v45; // xmm0
  __m128i v46; // xmm0
  __m128i v47; // xmm0
  __m128i v48; // xmm0
  __m128i v49; // xmm0
  __m128i v50; // xmm0
  __m128i v51; // xmm0
  __m128i v52; // xmm0
  __m128i v53; // xmm0
  __m128i v54; // xmm0
  __m128i v55; // xmm0
  __m128i v56; // xmm0
  __m128i v57; // xmm0
  __m128i v58; // xmm0
  __m128i v59; // xmm0
  __m128i v60; // xmm0
  __m128i v61; // xmm0
  __m128i v62; // xmm0
  __m128i v63; // xmm0
  __m128i v64; // xmm0
  __m128i v65; // xmm0
  __m128i v66; // xmm0
  __m128i v67; // xmm0
  __m128i v68; // xmm0
  __m128i v69; // xmm0
  __m128i v70; // xmm0
  __m128i v71; // xmm0
  __m128i v72; // xmm0
  __m128i v73; // xmm0
  __m128i v74; // xmm0
  __m128i v75; // xmm0
  __m128i v76; // xmm0
  __m128i v77; // xmm0
  __m128i v78; // xmm0
  __m128i v79; // xmm0
  __m128i v80; // xmm0
  __m128i v81; // xmm0
  __m128i v82; // xmm0
  __m128i v83; // xmm0
  __m128i v84; // xmm0
  __m128i v85; // xmm0
  __m128i v86; // xmm0
  __m128i v87; // xmm0
  __m128i v88; // xmm0
  __m128i v89; // xmm0
  __m128i v90; // xmm0
  __m128i v91; // xmm0
  __m128i v92; // xmm0
  __m128i v93; // xmm0
  __m128i v94; // xmm0
  __m128i v95; // xmm0
  __m128i v96; // xmm0
  __m128i v97; // xmm0
  __m128i v98; // xmm0
  __m128i v99; // xmm0
  __m128i v100; // xmm0
  __m128i v101; // xmm0
  __m128i v102; // xmm0
  __m128i v103; // xmm0
  __m128i v104; // xmm0
  __m128i v105; // xmm0
  __m128i v106; // xmm0
  __m128i v107; // xmm0
  __m128i v108; // xmm0
  __m128i v109; // xmm0
  __m128i v110; // xmm0
  __m128i v111; // xmm0
  __m128i v112; // xmm0
  __m128i v113; // xmm0
  __m128i v114; // xmm0
  __m128i v115; // xmm0
  __m128i v116; // xmm0
  __m128i v117; // xmm0
  __m128i v118; // xmm0
  __m128i v119; // xmm0
  __m128i v120; // xmm0
  __m128i v121; // xmm0
  __m128i v122; // xmm0
  __m128i v123; // xmm0
  __m128i v124; // xmm0
  __m128i v125; // xmm0
  __m128i v126; // xmm0
  __m128i v127; // xmm0
  __m128i v128; // xmm0
  __m128i v129; // xmm0
  __m128i v130; // xmm0
  __m128i v131; // xmm0
  __m128i v132; // xmm0
  __m128i v133; // xmm0
  __m128i v134; // xmm0
  __m128i v135; // xmm0
  __m128i v136; // xmm0
  __m128i v137; // xmm0
  __m128i v138; // xmm0
  __m128i v139; // xmm0
  __m128i v140; // xmm0
  __m128i v141; // xmm0
  __m128i v142; // xmm0
  __m128i v143; // xmm0
  __m128i v144; // xmm0
  __m128i v145; // xmm0
  __m128i v146; // xmm0
  __m128i v147; // xmm0
  __m128i v148; // xmm0
  __m128i v149; // xmm0
  __m128i v150; // xmm0
  __m128i v151; // xmm0
  __m128i v152; // xmm0
  __m128i v153; // xmm0
  __m128i v154; // xmm0
  __m128i v155; // xmm0
  __m128i v156; // xmm0
  __m128i v157; // xmm0
  __m128i v158; // xmm0
  __m128i v159; // xmm0
  __m128i v160; // xmm0
  __m128i v161; // xmm0
  __m128i v162; // xmm0
  __m128i v163; // xmm0
  __m128i v164; // xmm0
  __m128i v165; // xmm0
  __m128i v166; // xmm0
  __m128i v167; // xmm0
  __m128i v168; // xmm0
  __m128i v169; // xmm0
  __m128i v170; // xmm0
  __m128i v171; // xmm0
  __m128i v172; // xmm0
  __m128i v173; // xmm0
  __m128i v174; // xmm0
  __m128i v175; // xmm0
  __m128i v176; // xmm0
  __m128i v177; // xmm0
  __m128i v178; // xmm0
  __m128i v179; // xmm0
  __m128i v180; // xmm0
  __m128i v181; // xmm0
  __m128i v182; // xmm0
  __m128i v183; // xmm0
  __m128i v184; // xmm0
  __m128i v185; // xmm0
  __m128i v186; // xmm0
  __m128i v187; // xmm0
  __m128i v188; // xmm0
  __m128i v189; // xmm0
  __m128i v190; // xmm0
  __m128i v191; // xmm0
  __m128i v192; // xmm0
  __m128i v193; // xmm0
  __m128i v194; // xmm0
  __m128i v195; // xmm0
  __m128i v196; // xmm0
  __m128i v197; // xmm0
  __m128i v198; // xmm0
  __m128i v199; // xmm0
  __m128i v200; // xmm0
  __m128i v201; // xmm0
  __m128i v202; // xmm0
  __m128i v203; // xmm0
  __m128i v204; // xmm0
  __m128i v205; // xmm0
  __m128i v206; // xmm0
  __m128i v207; // xmm0
  __m128i v208; // xmm0
  __m128i v209; // xmm0
  __m128i v210; // xmm0
  __m128i v211; // xmm0
  __m128i v212; // xmm0
  __m128i v213; // xmm0
  __m128i v214; // xmm0
  __m128i v215; // xmm0
  __m128i v216; // xmm0
  __m128i v217; // xmm0
  __m128i v218; // xmm0
  __m128i v219; // xmm0
  __m128i v220; // xmm0
  __m128i v221; // xmm0
  __m128i v222; // xmm0
  __m128i v223; // xmm0
  __m128i v224; // xmm0
  _OWORD *v225; // rax
  _OWORD *v226; // rax
  _OWORD *v227; // rax
  _OWORD *v228; // rax
  _OWORD *v229; // rax
  _OWORD *v230; // rax
  _OWORD *v231; // rax
  _OWORD *v232; // rax
  _OWORD *v233; // rax
  _OWORD *v234; // rax
  _OWORD *v235; // rax
  _OWORD *v236; // rax
  _OWORD *v237; // rax
  _OWORD *v238; // rax
  _OWORD *v239; // rax
  _OWORD *v240; // rax
  _OWORD *v241; // rax
  _OWORD *v242; // rax
  _OWORD *v243; // rax
  _OWORD *v244; // rax
  _OWORD *v245; // rax
  _OWORD *v246; // rax
  _OWORD *v247; // rax
  _OWORD *v248; // rax
  _OWORD *v249; // rax
  _OWORD *v250; // rax
  _OWORD *v251; // rax
  _OWORD *v252; // rax
  _OWORD *v253; // rax
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 result; // rax
  const char *v257; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v258; // [rsp+38h] [rbp-C8h]
  __int128 v259; // [rsp+40h] [rbp-C0h]
  __int128 v260; // [rsp+50h] [rbp-B0h]
  __int128 v261; // [rsp+60h] [rbp-A0h]
  __int128 v262; // [rsp+70h] [rbp-90h] BYREF
  __int64 v263; // [rsp+80h] [rbp-80h]
  __int128 v264; // [rsp+90h] [rbp-70h] BYREF
  __int64 v265; // [rsp+A0h] [rbp-60h]
  __int64 v266; // [rsp+B0h] [rbp-50h]
  __int64 v267; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v268[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v269[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v270[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v271[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v272[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v273[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v274[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v275[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v276[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v277[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v278[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v279[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v280[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v281[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v282[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v283[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v284[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v285[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v286[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v287[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v288[16]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v289[16]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v290[16]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v291[16]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v292[16]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v293[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v294[16]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v295[16]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v296[16]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v297[16]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v298[16]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v299[16]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v300[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v301[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v302[16]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v303[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v304[16]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v305[16]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v306[16]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v307[16]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v308[16]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v309[16]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v310[16]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v311[16]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v312[16]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v313[16]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v314[16]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v315[16]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v316[16]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v317[16]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v318[16]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v319[16]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v320[16]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v321[16]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v322[16]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v323[16]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v324[16]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v325[16]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v326[16]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v327[16]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v328[16]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v329[16]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v330[16]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v331[16]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v332[16]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v333[16]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v334[16]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v335[16]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v336[16]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v337[16]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v338[16]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v339[16]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v340[16]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v341[16]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v342[16]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v343[16]; // [rsp+570h] [rbp+470h] BYREF
  _BYTE v344[16]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v345[16]; // [rsp+590h] [rbp+490h] BYREF
  _BYTE v346[16]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v347[16]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v348[16]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v349[16]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v350[16]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE v351[16]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v352[16]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v353[16]; // [rsp+610h] [rbp+510h] BYREF
  _BYTE v354[16]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v355[16]; // [rsp+630h] [rbp+530h] BYREF
  _BYTE v356[16]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v357[16]; // [rsp+650h] [rbp+550h] BYREF
  _BYTE v358[16]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v359[16]; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v360[16]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v361[16]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v362[16]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v363[16]; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v364[16]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v365[16]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v366[16]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v367[16]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _BYTE v368[16]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v369[16]; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v370[16]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v371[16]; // [rsp+730h] [rbp+630h] BYREF
  _BYTE v372[16]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v373[16]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v374[16]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v375[16]; // [rsp+770h] [rbp+670h] BYREF
  _BYTE v376[16]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v377[16]; // [rsp+790h] [rbp+690h] BYREF
  _BYTE v378[16]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v379[16]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _BYTE v380[16]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v381[16]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v382[16]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v383[16]; // [rsp+7F0h] [rbp+6F0h] BYREF
  _BYTE v384[16]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v385[16]; // [rsp+810h] [rbp+710h] BYREF
  _BYTE v386[16]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v387[16]; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v388[16]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v389[16]; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v390[16]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v391[16]; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v392[16]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v393[16]; // [rsp+890h] [rbp+790h] BYREF
  _BYTE v394[16]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v395[16]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _BYTE v396[16]; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v397[16]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v398[16]; // [rsp+8E0h] [rbp+7E0h] BYREF
  _BYTE v399[16]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v400[16]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v401[16]; // [rsp+910h] [rbp+810h] BYREF
  _BYTE v402[16]; // [rsp+920h] [rbp+820h] BYREF
  _BYTE v403[16]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v404[16]; // [rsp+940h] [rbp+840h] BYREF
  _BYTE v405[16]; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v406[16]; // [rsp+960h] [rbp+860h] BYREF
  _BYTE v407[16]; // [rsp+970h] [rbp+870h] BYREF
  _BYTE v408[16]; // [rsp+980h] [rbp+880h] BYREF
  _BYTE v409[16]; // [rsp+990h] [rbp+890h] BYREF
  _BYTE v410[16]; // [rsp+9A0h] [rbp+8A0h] BYREF
  _BYTE v411[16]; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v412[16]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v413[16]; // [rsp+9D0h] [rbp+8D0h] BYREF
  _BYTE v414[16]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v415[16]; // [rsp+9F0h] [rbp+8F0h] BYREF
  _BYTE v416[16]; // [rsp+A00h] [rbp+900h] BYREF
  _BYTE v417[16]; // [rsp+A10h] [rbp+910h] BYREF
  _BYTE v418[16]; // [rsp+A20h] [rbp+920h] BYREF
  _BYTE v419[16]; // [rsp+A30h] [rbp+930h] BYREF
  _BYTE v420[16]; // [rsp+A40h] [rbp+940h] BYREF
  _BYTE v421[16]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v422[16]; // [rsp+A60h] [rbp+960h] BYREF
  _BYTE v423[16]; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v424[16]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v425[16]; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v426[16]; // [rsp+AA0h] [rbp+9A0h] BYREF
  _BYTE v427[16]; // [rsp+AB0h] [rbp+9B0h] BYREF
  _BYTE v428[16]; // [rsp+AC0h] [rbp+9C0h] BYREF
  _BYTE v429[16]; // [rsp+AD0h] [rbp+9D0h] BYREF
  _BYTE v430[16]; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v431[16]; // [rsp+AF0h] [rbp+9F0h] BYREF
  _BYTE v432[16]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v433[16]; // [rsp+B10h] [rbp+A10h] BYREF
  _BYTE v434[16]; // [rsp+B20h] [rbp+A20h] BYREF
  _BYTE v435[16]; // [rsp+B30h] [rbp+A30h] BYREF
  _BYTE v436[16]; // [rsp+B40h] [rbp+A40h] BYREF
  _BYTE v437[16]; // [rsp+B50h] [rbp+A50h] BYREF
  _BYTE v438[16]; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v439[16]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v440[16]; // [rsp+B80h] [rbp+A80h] BYREF
  _BYTE v441[16]; // [rsp+B90h] [rbp+A90h] BYREF
  _BYTE v442[16]; // [rsp+BA0h] [rbp+AA0h] BYREF
  _BYTE v443[16]; // [rsp+BB0h] [rbp+AB0h] BYREF
  _BYTE v444[16]; // [rsp+BC0h] [rbp+AC0h] BYREF
  _BYTE v445[16]; // [rsp+BD0h] [rbp+AD0h] BYREF
  _BYTE v446[16]; // [rsp+BE0h] [rbp+AE0h] BYREF
  _BYTE v447[16]; // [rsp+BF0h] [rbp+AF0h] BYREF
  _BYTE v448[16]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v449[16]; // [rsp+C10h] [rbp+B10h] BYREF
  _BYTE v450[16]; // [rsp+C20h] [rbp+B20h] BYREF
  _BYTE v451[16]; // [rsp+C30h] [rbp+B30h] BYREF
  _BYTE v452[16]; // [rsp+C40h] [rbp+B40h] BYREF
  _BYTE v453[16]; // [rsp+C50h] [rbp+B50h] BYREF
  _BYTE v454[16]; // [rsp+C60h] [rbp+B60h] BYREF
  _BYTE v455[16]; // [rsp+C70h] [rbp+B70h] BYREF
  _BYTE v456[16]; // [rsp+C80h] [rbp+B80h] BYREF
  _BYTE v457[16]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v458[16]; // [rsp+CA0h] [rbp+BA0h] BYREF
  _BYTE v459[16]; // [rsp+CB0h] [rbp+BB0h] BYREF
  _BYTE v460[16]; // [rsp+CC0h] [rbp+BC0h] BYREF
  _BYTE v461[16]; // [rsp+CD0h] [rbp+BD0h] BYREF
  _BYTE v462[16]; // [rsp+CE0h] [rbp+BE0h] BYREF
  _BYTE v463[16]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v464[16]; // [rsp+D00h] [rbp+C00h] BYREF
  _BYTE v465[16]; // [rsp+D10h] [rbp+C10h] BYREF
  _BYTE v466[16]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v467[16]; // [rsp+D30h] [rbp+C30h] BYREF
  _BYTE v468[16]; // [rsp+D40h] [rbp+C40h] BYREF
  _BYTE v469[16]; // [rsp+D50h] [rbp+C50h] BYREF
  _BYTE v470[16]; // [rsp+D60h] [rbp+C60h] BYREF
  _BYTE v471[16]; // [rsp+D70h] [rbp+C70h] BYREF
  _BYTE v472[16]; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v473[16]; // [rsp+D90h] [rbp+C90h] BYREF
  _BYTE v474[16]; // [rsp+DA0h] [rbp+CA0h] BYREF
  _BYTE v475[16]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v476[16]; // [rsp+DC0h] [rbp+CC0h] BYREF
  _BYTE v477[16]; // [rsp+DD0h] [rbp+CD0h] BYREF
  _BYTE v478[16]; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v479[16]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _BYTE v480[16]; // [rsp+E00h] [rbp+D00h] BYREF
  _BYTE v481[16]; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE v482[16]; // [rsp+E20h] [rbp+D20h] BYREF
  _BYTE v483[16]; // [rsp+E30h] [rbp+D30h] BYREF
  _BYTE v484[16]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v485[16]; // [rsp+E50h] [rbp+D50h] BYREF
  _BYTE v486[16]; // [rsp+E60h] [rbp+D60h] BYREF
  _BYTE v487[16]; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v488[16]; // [rsp+E80h] [rbp+D80h] BYREF
  __int128 pExceptionObject; // [rsp+E90h] [rbp+D90h] BYREF
  __int128 v490; // [rsp+EA0h] [rbp+DA0h]
  __int128 v491; // [rsp+EB0h] [rbp+DB0h]
  __int128 v492; // [rsp+EC0h] [rbp+DC0h]
  __int128 v493; // [rsp+ED0h] [rbp+DD0h]
  __int128 v494; // [rsp+EE0h] [rbp+DE0h]
  _OWORD v495[1000]; // [rsp+EF0h] [rbp+DF0h] BYREF
  char v496; // [rsp+4D70h] [rbp+4C70h] BYREF
  char v497; // [rsp+4DB0h] [rbp+4CB0h] BYREF
  char v498; // [rsp+4DF0h] [rbp+4CF0h] BYREF
  char v499; // [rsp+4E30h] [rbp+4D30h] BYREF
  char v500; // [rsp+4E70h] [rbp+4D70h] BYREF
  char v501; // [rsp+4EB0h] [rbp+4DB0h] BYREF
  char v502; // [rsp+4EF0h] [rbp+4DF0h] BYREF

  v266 = a1;
  if ( (unsigned int)napi_open_handle_scope_0(a1, &v267) )
  {
    Napi::Error::New((struct napi_env__ *)&pExceptionObject);
    throw (Napi::Error *)&pExceptionObject;
  }
  Caps = bgfx::getCaps(v2);
  pExceptionObject = *(_OWORD *)((char *)Caps + 40);
  v490 = *(_OWORD *)((char *)Caps + 56);
  v491 = *(_OWORD *)((char *)Caps + 72);
  v492 = *(_OWORD *)((char *)Caps + 88);
  v493 = *(_OWORD *)((char *)Caps + 104);
  v494 = *(_OWORD *)((char *)Caps + 120);
  LODWORD(v262) = 9;
  v4 = *(__m128i *)Napi::Value::From<int>(v487, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "PROTOCOL_VERSION";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v4, 8).m128i_u64[0];
  v495[0] = (unsigned __int64)"PROTOCOL_VERSION";
  v495[1] = 0;
  v495[2] = v260;
  v495[3] = 0x400u;
  v5 = *(__m128i *)Napi::Value::From<unsigned int>(v488, a1, (char *)&pExceptionObject + 8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "CAPS_LIMITS_MAX_TEXTURE_SIZE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v5, 8).m128i_u64[0];
  v495[4] = (unsigned __int64)"CAPS_LIMITS_MAX_TEXTURE_SIZE";
  v495[5] = 0;
  v495[6] = v260;
  v495[7] = 0x400u;
  v6 = *(__m128i *)Napi::Value::From<unsigned int>(v269, a1, (char *)&pExceptionObject + 12);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "CAPS_LIMITS_MAX_TEXTURE_LAYERS";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v6, 8).m128i_u64[0];
  v495[8] = (unsigned __int64)"CAPS_LIMITS_MAX_TEXTURE_LAYERS";
  v495[9] = 0;
  v495[10] = v260;
  v495[11] = 0x400u;
  v7 = *(__m128i *)Napi::Value::From<unsigned int>(v270, a1, &dword_18054B794);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_NEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v7, 8).m128i_u64[0];
  v495[12] = (unsigned __int64)"TEXTURE_NEAREST_NEAREST";
  v495[13] = 0;
  v495[14] = v260;
  v495[15] = 0x400u;
  v8 = *(__m128i *)Napi::Value::From<unsigned int>(v271, a1, byte_18054B798);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_LINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v8, 8).m128i_u64[0];
  v495[16] = (unsigned __int64)"TEXTURE_LINEAR_LINEAR";
  v495[17] = 0;
  v495[18] = v260;
  v495[19] = 0x400u;
  v9 = *(__m128i *)Napi::Value::From<unsigned int>(v272, a1, &dword_18054B79C);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_LINEAR_MIPLINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v9, 8).m128i_u64[0];
  v495[20] = (unsigned __int64)"TEXTURE_LINEAR_LINEAR_MIPLINEAR";
  v495[21] = 0;
  v495[22] = v260;
  v495[23] = 0x400u;
  v10 = *(__m128i *)Napi::Value::From<unsigned int>(v273, a1, byte_18054B7A0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_NEAREST_MIPNEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v10, 8).m128i_u64[0];
  v495[24] = (unsigned __int64)"TEXTURE_NEAREST_NEAREST_MIPNEAREST";
  v495[25] = 0;
  v495[26] = v260;
  v495[27] = 0x400u;
  v11 = *(__m128i *)Napi::Value::From<unsigned int>(v274, a1, &dword_18054B7A4);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_LINEAR_MIPNEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v11, 8).m128i_u64[0];
  v495[28] = (unsigned __int64)"TEXTURE_NEAREST_LINEAR_MIPNEAREST";
  v495[29] = 0;
  v495[30] = v260;
  v495[31] = 0x400u;
  v12 = *(__m128i *)Napi::Value::From<unsigned int>(v275, a1, byte_18054B7A8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_LINEAR_MIPLINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v12, 8).m128i_u64[0];
  v495[32] = (unsigned __int64)"TEXTURE_NEAREST_LINEAR_MIPLINEAR";
  v495[33] = 0;
  v495[34] = v260;
  v495[35] = 0x400u;
  v13 = *(__m128i *)Napi::Value::From<unsigned int>(v276, a1, &dword_18054B7AC);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_LINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v13, 8).m128i_u64[0];
  v495[36] = (unsigned __int64)"TEXTURE_NEAREST_LINEAR";
  v495[37] = 0;
  v495[38] = v260;
  v495[39] = 0x400u;
  v14 = *(__m128i *)Napi::Value::From<unsigned int>(v277, a1, byte_18054B7B0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_NEAREST_NEAREST_MIPLINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v14, 8).m128i_u64[0];
  v495[40] = (unsigned __int64)"TEXTURE_NEAREST_NEAREST_MIPLINEAR";
  v495[41] = 0;
  v495[42] = v260;
  v495[43] = 0x400u;
  v15 = *(__m128i *)Napi::Value::From<unsigned int>(v278, a1, &dword_18054B7B4);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_NEAREST_MIPNEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v15, 8).m128i_u64[0];
  v495[44] = (unsigned __int64)"TEXTURE_LINEAR_NEAREST_MIPNEAREST";
  v495[45] = 0;
  v495[46] = v260;
  v495[47] = 0x400u;
  v16 = *(__m128i *)Napi::Value::From<unsigned int>(v279, a1, byte_18054B7B8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_NEAREST_MIPLINEAR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v16, 8).m128i_u64[0];
  v495[48] = (unsigned __int64)"TEXTURE_LINEAR_NEAREST_MIPLINEAR";
  v495[49] = 0;
  v495[50] = v260;
  v495[51] = 0x400u;
  v17 = *(__m128i *)Napi::Value::From<unsigned int>(v280, a1, &dword_18054B7BC);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_LINEAR_MIPNEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v17, 8).m128i_u64[0];
  v495[52] = (unsigned __int64)"TEXTURE_LINEAR_LINEAR_MIPNEAREST";
  v495[53] = 0;
  v495[54] = v260;
  v495[55] = 0x400u;
  v18 = *(__m128i *)Napi::Value::From<unsigned int>(v281, a1, &qword_18054B7C0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_LINEAR_NEAREST";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v18, 8).m128i_u64[0];
  v495[56] = (unsigned __int64)"TEXTURE_LINEAR_NEAREST";
  v495[57] = 0;
  v495[58] = v260;
  v495[59] = 0x400u;
  *(_QWORD *)&v262 = 16;
  v19 = *(__m128i *)Napi::Value::From<unsigned __int64>(v282, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_LESS";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v19, 8).m128i_u64[0];
  v495[60] = (unsigned __int64)"DEPTH_TEST_LESS";
  v495[61] = 0;
  v495[62] = v260;
  v495[63] = 0x400u;
  *(_QWORD *)&v262 = 32;
  v20 = *(__m128i *)Napi::Value::From<unsigned __int64>(v283, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_LEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v20, 8).m128i_u64[0];
  v495[64] = (unsigned __int64)"DEPTH_TEST_LEQUAL";
  v495[65] = 0;
  v495[66] = v260;
  v495[67] = 0x400u;
  *(_QWORD *)&v262 = 48;
  v21 = *(__m128i *)Napi::Value::From<unsigned __int64>(v284, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_EQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v21, 8).m128i_u64[0];
  v495[68] = (unsigned __int64)"DEPTH_TEST_EQUAL";
  v495[69] = 0;
  v495[70] = v260;
  v495[71] = 0x400u;
  *(_QWORD *)&v262 = 64;
  v22 = *(__m128i *)Napi::Value::From<unsigned __int64>(v285, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_GEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v22, 8).m128i_u64[0];
  v495[72] = (unsigned __int64)"DEPTH_TEST_GEQUAL";
  v495[73] = 0;
  v495[74] = v260;
  v495[75] = 0x400u;
  *(_QWORD *)&v262 = 80;
  v23 = *(__m128i *)Napi::Value::From<unsigned __int64>(v286, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_GREATER";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v23, 8).m128i_u64[0];
  v495[76] = (unsigned __int64)"DEPTH_TEST_GREATER";
  v495[77] = 0;
  v495[78] = v260;
  v495[79] = 0x400u;
  *(_QWORD *)&v262 = 96;
  v24 = *(__m128i *)Napi::Value::From<unsigned __int64>(v287, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_NOTEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v24, 8).m128i_u64[0];
  v495[80] = (unsigned __int64)"DEPTH_TEST_NOTEQUAL";
  v495[81] = 0;
  v495[82] = v260;
  v495[83] = 0x400u;
  *(_QWORD *)&v262 = 112;
  v25 = *(__m128i *)Napi::Value::From<unsigned __int64>(v288, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_NEVER";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v25, 8).m128i_u64[0];
  v495[84] = (unsigned __int64)"DEPTH_TEST_NEVER";
  v495[85] = 0;
  v495[86] = v260;
  v495[87] = 0x400u;
  *(_QWORD *)&v262 = 128;
  v26 = *(__m128i *)Napi::Value::From<unsigned __int64>(v289, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "DEPTH_TEST_ALWAYS";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v26, 8).m128i_u64[0];
  v495[88] = (unsigned __int64)"DEPTH_TEST_ALWAYS";
  v495[89] = 0;
  v495[90] = v260;
  v495[91] = 0x400u;
  LODWORD(v262) = 1;
  v27 = *(__m128i *)Napi::Value::From<int>(v290, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "CLEAR_FLAG_COLOR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v27, 8).m128i_u64[0];
  v495[92] = (unsigned __int64)"CLEAR_FLAG_COLOR";
  v495[93] = 0;
  v495[94] = v260;
  v495[95] = 0x400u;
  LODWORD(v262) = 2;
  v28 = *(__m128i *)Napi::Value::From<int>(v291, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "CLEAR_FLAG_DEPTH";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v28, 8).m128i_u64[0];
  v495[96] = (unsigned __int64)"CLEAR_FLAG_DEPTH";
  v495[97] = 0;
  v495[98] = v260;
  v495[99] = 0x400u;
  LODWORD(v262) = 4;
  v29 = *(__m128i *)Napi::Value::From<int>(v292, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "CLEAR_FLAG_STENCIL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v29, 8).m128i_u64[0];
  v495[100] = (unsigned __int64)"CLEAR_FLAG_STENCIL";
  v495[101] = 0;
  v495[102] = v260;
  v495[103] = 0x400u;
  LODWORD(v262) = 0;
  v30 = *(__m128i *)Napi::Value::From<int>(v293, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ADDRESS_MODE_WRAP";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v30, 8).m128i_u64[0];
  v495[104] = (unsigned __int64)"ADDRESS_MODE_WRAP";
  v495[105] = 0;
  v495[106] = v260;
  v495[107] = 0x400u;
  LODWORD(v262) = 1;
  v31 = *(__m128i *)Napi::Value::From<unsigned int>(v294, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ADDRESS_MODE_MIRROR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v31, 8).m128i_u64[0];
  v495[108] = (unsigned __int64)"ADDRESS_MODE_MIRROR";
  v495[109] = 0;
  v495[110] = v260;
  v495[111] = 0x400u;
  LODWORD(v262) = 2;
  v32 = *(__m128i *)Napi::Value::From<unsigned int>(v295, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ADDRESS_MODE_CLAMP";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v32, 8).m128i_u64[0];
  v495[112] = (unsigned __int64)"ADDRESS_MODE_CLAMP";
  v495[113] = 0;
  v495[114] = v260;
  v495[115] = 0x400u;
  LODWORD(v262) = 3;
  v33 = *(__m128i *)Napi::Value::From<unsigned int>(v296, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ADDRESS_MODE_BORDER";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v33, 8).m128i_u64[0];
  v495[116] = (unsigned __int64)"ADDRESS_MODE_BORDER";
  v495[117] = 0;
  v495[118] = v260;
  v495[119] = 0x400u;
  LODWORD(v262) = 1;
  v34 = *(__m128i *)Napi::Value::From<unsigned int>(v297, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ADDRESS_MODE_MIRROR_ONCE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v34, 8).m128i_u64[0];
  v495[120] = (unsigned __int64)"ADDRESS_MODE_MIRROR_ONCE";
  v495[121] = 0;
  v495[122] = v260;
  v495[123] = 0x400u;
  LODWORD(v262) = 0;
  v35 = *(__m128i *)Napi::Value::From<unsigned int>(v298, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v35, 8).m128i_u64[0];
  v495[124] = (unsigned __int64)"TEXTURE_FORMAT_BC1";
  v495[125] = 0;
  v495[126] = v260;
  v495[127] = 0x400u;
  LODWORD(v262) = 1;
  v36 = *(__m128i *)Napi::Value::From<unsigned int>(v299, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC2";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v36, 8).m128i_u64[0];
  v495[128] = (unsigned __int64)"TEXTURE_FORMAT_BC2";
  v495[129] = 0;
  v495[130] = v260;
  v495[131] = 0x400u;
  LODWORD(v262) = 2;
  v37 = *(__m128i *)Napi::Value::From<unsigned int>(v300, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC3";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v37, 8).m128i_u64[0];
  v495[132] = (unsigned __int64)"TEXTURE_FORMAT_BC3";
  v495[133] = 0;
  v495[134] = v260;
  v495[135] = 0x400u;
  LODWORD(v262) = 3;
  v38 = *(__m128i *)Napi::Value::From<unsigned int>(v301, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC4";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v38, 8).m128i_u64[0];
  v495[136] = (unsigned __int64)"TEXTURE_FORMAT_BC4";
  v495[137] = 0;
  v495[138] = v260;
  v495[139] = 0x400u;
  LODWORD(v262) = 4;
  v39 = *(__m128i *)Napi::Value::From<unsigned int>(v302, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v39, 8).m128i_u64[0];
  v495[140] = (unsigned __int64)"TEXTURE_FORMAT_BC5";
  v495[141] = 0;
  v495[142] = v260;
  v495[143] = 0x400u;
  LODWORD(v262) = 5;
  v40 = *(__m128i *)Napi::Value::From<unsigned int>(v303, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC6H";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v40, 8).m128i_u64[0];
  v495[144] = (unsigned __int64)"TEXTURE_FORMAT_BC6H";
  v495[145] = 0;
  v495[146] = v260;
  v495[147] = 0x400u;
  LODWORD(v262) = 6;
  v41 = *(__m128i *)Napi::Value::From<unsigned int>(v304, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BC7";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v41, 8).m128i_u64[0];
  v495[148] = (unsigned __int64)"TEXTURE_FORMAT_BC7";
  v495[149] = 0;
  v495[150] = v260;
  v495[151] = 0x400u;
  LODWORD(v262) = 7;
  v42 = *(__m128i *)Napi::Value::From<unsigned int>(v305, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ETC1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v42, 8).m128i_u64[0];
  v495[152] = (unsigned __int64)"TEXTURE_FORMAT_ETC1";
  v495[153] = 0;
  v495[154] = v260;
  v495[155] = 0x400u;
  LODWORD(v262) = 8;
  v43 = *(__m128i *)Napi::Value::From<unsigned int>(v306, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ETC2";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v43, 8).m128i_u64[0];
  v495[156] = (unsigned __int64)"TEXTURE_FORMAT_ETC2";
  v495[157] = 0;
  v495[158] = v260;
  v495[159] = 0x400u;
  LODWORD(v262) = 9;
  v44 = *(__m128i *)Napi::Value::From<unsigned int>(v307, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ETC2A";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v44, 8).m128i_u64[0];
  v495[160] = (unsigned __int64)"TEXTURE_FORMAT_ETC2A";
  v495[161] = 0;
  v495[162] = v260;
  v495[163] = 0x400u;
  LODWORD(v262) = 10;
  v45 = *(__m128i *)Napi::Value::From<unsigned int>(v308, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ETC2A1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v45, 8).m128i_u64[0];
  v495[164] = (unsigned __int64)"TEXTURE_FORMAT_ETC2A1";
  v495[165] = 0;
  v495[166] = v260;
  v495[167] = 0x400u;
  LODWORD(v262) = 11;
  v46 = *(__m128i *)Napi::Value::From<unsigned int>(v309, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC12";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v46, 8).m128i_u64[0];
  v495[168] = (unsigned __int64)"TEXTURE_FORMAT_PTC12";
  v495[169] = 0;
  v495[170] = v260;
  v495[171] = 0x400u;
  LODWORD(v262) = 12;
  v47 = *(__m128i *)Napi::Value::From<unsigned int>(v310, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC14";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v47, 8).m128i_u64[0];
  v495[172] = (unsigned __int64)"TEXTURE_FORMAT_PTC14";
  v495[173] = 0;
  v495[174] = v260;
  v495[175] = 0x400u;
  LODWORD(v262) = 13;
  v48 = *(__m128i *)Napi::Value::From<unsigned int>(v311, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC12A";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v48, 8).m128i_u64[0];
  v495[176] = (unsigned __int64)"TEXTURE_FORMAT_PTC12A";
  v495[177] = 0;
  v495[178] = v260;
  v495[179] = 0x400u;
  LODWORD(v262) = 14;
  v49 = *(__m128i *)Napi::Value::From<unsigned int>(v312, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC14A";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v49, 8).m128i_u64[0];
  v495[180] = (unsigned __int64)"TEXTURE_FORMAT_PTC14A";
  v495[181] = 0;
  v495[182] = v260;
  v495[183] = 0x400u;
  LODWORD(v262) = 15;
  v50 = *(__m128i *)Napi::Value::From<unsigned int>(v313, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC22";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v50, 8).m128i_u64[0];
  v495[184] = (unsigned __int64)"TEXTURE_FORMAT_PTC22";
  v495[185] = 0;
  v495[186] = v260;
  v495[187] = 0x400u;
  LODWORD(v262) = 16;
  v51 = *(__m128i *)Napi::Value::From<unsigned int>(v314, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_PTC24";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v51, 8).m128i_u64[0];
  v495[188] = (unsigned __int64)"TEXTURE_FORMAT_PTC24";
  v495[189] = 0;
  v495[190] = v260;
  v495[191] = 0x400u;
  LODWORD(v262) = 17;
  v52 = *(__m128i *)Napi::Value::From<unsigned int>(v315, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ATC";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v52, 8).m128i_u64[0];
  v495[192] = (unsigned __int64)"TEXTURE_FORMAT_ATC";
  v495[193] = 0;
  v495[194] = v260;
  v495[195] = 0x400u;
  LODWORD(v262) = 18;
  v53 = *(__m128i *)Napi::Value::From<unsigned int>(v316, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ATCE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v53, 8).m128i_u64[0];
  v495[196] = (unsigned __int64)"TEXTURE_FORMAT_ATCE";
  v495[197] = 0;
  v495[198] = v260;
  v495[199] = 0x400u;
  LODWORD(v262) = 19;
  v54 = *(__m128i *)Napi::Value::From<unsigned int>(v317, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ATCI";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v54, 8).m128i_u64[0];
  v495[200] = (unsigned __int64)"TEXTURE_FORMAT_ATCI";
  v495[201] = 0;
  v495[202] = v260;
  v495[203] = 0x400u;
  LODWORD(v262) = 20;
  v55 = *(__m128i *)Napi::Value::From<unsigned int>(v318, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC4x4";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v55, 8).m128i_u64[0];
  v495[204] = (unsigned __int64)"TEXTURE_FORMAT_ASTC4x4";
  v495[205] = 0;
  v495[206] = v260;
  v495[207] = 0x400u;
  LODWORD(v262) = 21;
  v56 = *(__m128i *)Napi::Value::From<unsigned int>(v319, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC5x4";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v56, 8).m128i_u64[0];
  v495[208] = (unsigned __int64)"TEXTURE_FORMAT_ASTC5x4";
  v495[209] = 0;
  v495[210] = v260;
  v495[211] = 0x400u;
  LODWORD(v262) = 22;
  v57 = *(__m128i *)Napi::Value::From<unsigned int>(v320, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC5x5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v57, 8).m128i_u64[0];
  v495[212] = (unsigned __int64)"TEXTURE_FORMAT_ASTC5x5";
  v495[213] = 0;
  v495[214] = v260;
  v495[215] = 0x400u;
  LODWORD(v262) = 23;
  v58 = *(__m128i *)Napi::Value::From<unsigned int>(v321, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC6x5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v58, 8).m128i_u64[0];
  v495[216] = (unsigned __int64)"TEXTURE_FORMAT_ASTC6x5";
  v495[217] = 0;
  v495[218] = v260;
  v495[219] = 0x400u;
  LODWORD(v262) = 24;
  v59 = *(__m128i *)Napi::Value::From<unsigned int>(v322, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC6x6";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v59, 8).m128i_u64[0];
  v495[220] = (unsigned __int64)"TEXTURE_FORMAT_ASTC6x6";
  v495[221] = 0;
  v495[222] = v260;
  v495[223] = 0x400u;
  LODWORD(v262) = 25;
  v60 = *(__m128i *)Napi::Value::From<unsigned int>(v323, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC8x5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v60, 8).m128i_u64[0];
  v495[224] = (unsigned __int64)"TEXTURE_FORMAT_ASTC8x5";
  v495[225] = 0;
  v495[226] = v260;
  v495[227] = 0x400u;
  LODWORD(v262) = 26;
  v61 = *(__m128i *)Napi::Value::From<unsigned int>(v324, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC8x6";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v61, 8).m128i_u64[0];
  v495[228] = (unsigned __int64)"TEXTURE_FORMAT_ASTC8x6";
  v495[229] = 0;
  v495[230] = v260;
  v495[231] = 0x400u;
  LODWORD(v262) = 27;
  v62 = *(__m128i *)Napi::Value::From<unsigned int>(v325, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC8x8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v62, 8).m128i_u64[0];
  v495[232] = (unsigned __int64)"TEXTURE_FORMAT_ASTC8x8";
  v495[233] = 0;
  v495[234] = v260;
  v495[235] = 0x400u;
  LODWORD(v262) = 28;
  v63 = *(__m128i *)Napi::Value::From<unsigned int>(v326, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC10x5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v63, 8).m128i_u64[0];
  v495[236] = (unsigned __int64)"TEXTURE_FORMAT_ASTC10x5";
  v495[237] = 0;
  v495[238] = v260;
  v495[239] = 0x400u;
  LODWORD(v262) = 29;
  v64 = *(__m128i *)Napi::Value::From<unsigned int>(v327, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC10x6";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v64, 8).m128i_u64[0];
  v495[240] = (unsigned __int64)"TEXTURE_FORMAT_ASTC10x6";
  v495[241] = 0;
  v495[242] = v260;
  v495[243] = 0x400u;
  LODWORD(v262) = 30;
  v65 = *(__m128i *)Napi::Value::From<unsigned int>(v328, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC10x8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v65, 8).m128i_u64[0];
  v495[244] = (unsigned __int64)"TEXTURE_FORMAT_ASTC10x8";
  v495[245] = 0;
  v495[246] = v260;
  v495[247] = 0x400u;
  LODWORD(v262) = 31;
  v66 = *(__m128i *)Napi::Value::From<unsigned int>(v329, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC10x10";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v66, 8).m128i_u64[0];
  v495[248] = (unsigned __int64)"TEXTURE_FORMAT_ASTC10x10";
  v495[249] = 0;
  v495[250] = v260;
  v495[251] = 0x400u;
  LODWORD(v262) = 32;
  v67 = *(__m128i *)Napi::Value::From<unsigned int>(v330, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC12x10";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v67, 8).m128i_u64[0];
  v495[252] = (unsigned __int64)"TEXTURE_FORMAT_ASTC12x10";
  v495[253] = 0;
  v495[254] = v260;
  v495[255] = 0x400u;
  LODWORD(v262) = 33;
  v68 = *(__m128i *)Napi::Value::From<unsigned int>(v331, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_ASTC12x12";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v68, 8).m128i_u64[0];
  v495[256] = (unsigned __int64)"TEXTURE_FORMAT_ASTC12x12";
  v495[257] = 0;
  v495[258] = v260;
  v495[259] = 0x400u;
  LODWORD(v262) = 35;
  v69 = *(__m128i *)Napi::Value::From<unsigned int>(v332, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v69, 8).m128i_u64[0];
  v495[260] = (unsigned __int64)"TEXTURE_FORMAT_R1";
  v495[261] = 0;
  v495[262] = v260;
  v495[263] = 0x400u;
  LODWORD(v262) = 36;
  v70 = *(__m128i *)Napi::Value::From<unsigned int>(v333, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_A8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v70, 8).m128i_u64[0];
  v495[264] = (unsigned __int64)"TEXTURE_FORMAT_A8";
  v495[265] = 0;
  v495[266] = v260;
  v495[267] = 0x400u;
  LODWORD(v262) = 37;
  v71 = *(__m128i *)Napi::Value::From<unsigned int>(v334, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v71, 8).m128i_u64[0];
  v495[268] = (unsigned __int64)"TEXTURE_FORMAT_R8";
  v495[269] = 0;
  v495[270] = v260;
  v495[271] = 0x400u;
  LODWORD(v262) = 38;
  v72 = *(__m128i *)Napi::Value::From<unsigned int>(v335, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R8I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v72, 8).m128i_u64[0];
  v495[272] = (unsigned __int64)"TEXTURE_FORMAT_R8I";
  v495[273] = 0;
  v495[274] = v260;
  v495[275] = 0x400u;
  LODWORD(v262) = 39;
  v73 = *(__m128i *)Napi::Value::From<unsigned int>(v336, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R8U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v73, 8).m128i_u64[0];
  v495[276] = (unsigned __int64)"TEXTURE_FORMAT_R8U";
  v495[277] = 0;
  v495[278] = v260;
  v495[279] = 0x400u;
  LODWORD(v262) = 40;
  v74 = *(__m128i *)Napi::Value::From<unsigned int>(v337, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R8S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v74, 8).m128i_u64[0];
  v495[280] = (unsigned __int64)"TEXTURE_FORMAT_R8S";
  v495[281] = 0;
  v495[282] = v260;
  v495[283] = 0x400u;
  LODWORD(v262) = 41;
  v75 = *(__m128i *)Napi::Value::From<unsigned int>(v338, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v75, 8).m128i_u64[0];
  v495[284] = (unsigned __int64)"TEXTURE_FORMAT_R16";
  v495[285] = 0;
  v495[286] = v260;
  v495[287] = 0x400u;
  LODWORD(v262) = 42;
  v76 = *(__m128i *)Napi::Value::From<unsigned int>(v339, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R16I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v76, 8).m128i_u64[0];
  v495[288] = (unsigned __int64)"TEXTURE_FORMAT_R16I";
  v495[289] = 0;
  v495[290] = v260;
  v495[291] = 0x400u;
  LODWORD(v262) = 43;
  v77 = *(__m128i *)Napi::Value::From<unsigned int>(v340, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R16U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v77, 8).m128i_u64[0];
  v495[292] = (unsigned __int64)"TEXTURE_FORMAT_R16U";
  v495[293] = 0;
  v495[294] = v260;
  v495[295] = 0x400u;
  LODWORD(v262) = 44;
  v78 = *(__m128i *)Napi::Value::From<unsigned int>(v341, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R16F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v78, 8).m128i_u64[0];
  v495[296] = (unsigned __int64)"TEXTURE_FORMAT_R16F";
  v495[297] = 0;
  v495[298] = v260;
  v495[299] = 0x400u;
  LODWORD(v262) = 45;
  v79 = *(__m128i *)Napi::Value::From<unsigned int>(v342, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R16S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v79, 8).m128i_u64[0];
  v495[300] = (unsigned __int64)"TEXTURE_FORMAT_R16S";
  v495[301] = 0;
  v495[302] = v260;
  v495[303] = 0x400u;
  LODWORD(v262) = 46;
  v80 = *(__m128i *)Napi::Value::From<unsigned int>(v343, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R32I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v80, 8).m128i_u64[0];
  v495[304] = (unsigned __int64)"TEXTURE_FORMAT_R32I";
  v495[305] = 0;
  v495[306] = v260;
  v495[307] = 0x400u;
  LODWORD(v262) = 47;
  v81 = *(__m128i *)Napi::Value::From<unsigned int>(v344, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R32U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v81, 8).m128i_u64[0];
  v495[308] = (unsigned __int64)"TEXTURE_FORMAT_R32U";
  v495[309] = 0;
  v495[310] = v260;
  v495[311] = 0x400u;
  LODWORD(v262) = 48;
  v82 = *(__m128i *)Napi::Value::From<unsigned int>(v345, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R32F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v82, 8).m128i_u64[0];
  v495[312] = (unsigned __int64)"TEXTURE_FORMAT_R32F";
  v495[313] = 0;
  v495[314] = v260;
  v495[315] = 0x400u;
  LODWORD(v262) = 49;
  v83 = *(__m128i *)Napi::Value::From<unsigned int>(v346, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v83, 8).m128i_u64[0];
  v495[316] = (unsigned __int64)"TEXTURE_FORMAT_RG8";
  v495[317] = 0;
  v495[318] = v260;
  v495[319] = 0x400u;
  LODWORD(v262) = 50;
  v84 = *(__m128i *)Napi::Value::From<unsigned int>(v347, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG8I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v84, 8).m128i_u64[0];
  v495[320] = (unsigned __int64)"TEXTURE_FORMAT_RG8I";
  v495[321] = 0;
  v495[322] = v260;
  v495[323] = 0x400u;
  LODWORD(v262) = 51;
  v85 = *(__m128i *)Napi::Value::From<unsigned int>(v348, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG8U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v85, 8).m128i_u64[0];
  v495[324] = (unsigned __int64)"TEXTURE_FORMAT_RG8U";
  v495[325] = 0;
  v495[326] = v260;
  v495[327] = 0x400u;
  LODWORD(v262) = 52;
  v86 = *(__m128i *)Napi::Value::From<unsigned int>(v349, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG8S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v86, 8).m128i_u64[0];
  v495[328] = (unsigned __int64)"TEXTURE_FORMAT_RG8S";
  v495[329] = 0;
  v495[330] = v260;
  v495[331] = 0x400u;
  LODWORD(v262) = 53;
  v87 = *(__m128i *)Napi::Value::From<unsigned int>(v350, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v87, 8).m128i_u64[0];
  v495[332] = (unsigned __int64)"TEXTURE_FORMAT_RG16";
  v495[333] = 0;
  v495[334] = v260;
  v495[335] = 0x400u;
  LODWORD(v262) = 54;
  v88 = *(__m128i *)Napi::Value::From<unsigned int>(v351, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG16I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v88, 8).m128i_u64[0];
  v495[336] = (unsigned __int64)"TEXTURE_FORMAT_RG16I";
  v495[337] = 0;
  v495[338] = v260;
  v495[339] = 0x400u;
  LODWORD(v262) = 55;
  v89 = *(__m128i *)Napi::Value::From<unsigned int>(v352, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG16U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v89, 8).m128i_u64[0];
  v495[340] = (unsigned __int64)"TEXTURE_FORMAT_RG16U";
  v495[341] = 0;
  v495[342] = v260;
  v495[343] = 0x400u;
  LODWORD(v262) = 56;
  v90 = *(__m128i *)Napi::Value::From<unsigned int>(v353, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG16F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v90, 8).m128i_u64[0];
  v495[344] = (unsigned __int64)"TEXTURE_FORMAT_RG16F";
  v495[345] = 0;
  v495[346] = v260;
  v495[347] = 0x400u;
  LODWORD(v262) = 57;
  v91 = *(__m128i *)Napi::Value::From<unsigned int>(v354, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG16S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v91, 8).m128i_u64[0];
  v495[348] = (unsigned __int64)"TEXTURE_FORMAT_RG16S";
  v495[349] = 0;
  v495[350] = v260;
  v495[351] = 0x400u;
  LODWORD(v262) = 58;
  v92 = *(__m128i *)Napi::Value::From<unsigned int>(v355, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG32I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v92, 8).m128i_u64[0];
  v495[352] = (unsigned __int64)"TEXTURE_FORMAT_RG32I";
  v495[353] = 0;
  v495[354] = v260;
  v495[355] = 0x400u;
  LODWORD(v262) = 59;
  v93 = *(__m128i *)Napi::Value::From<unsigned int>(v356, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG32U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v93, 8).m128i_u64[0];
  v495[356] = (unsigned __int64)"TEXTURE_FORMAT_RG32U";
  v495[357] = 0;
  v495[358] = v260;
  v495[359] = 0x400u;
  LODWORD(v262) = 60;
  v94 = *(__m128i *)Napi::Value::From<unsigned int>(v357, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG32F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v94, 8).m128i_u64[0];
  v495[360] = (unsigned __int64)"TEXTURE_FORMAT_RG32F";
  v495[361] = 0;
  v495[362] = v260;
  v495[363] = 0x400u;
  LODWORD(v262) = 61;
  v95 = *(__m128i *)Napi::Value::From<unsigned int>(v358, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v95, 8).m128i_u64[0];
  v495[364] = (unsigned __int64)"TEXTURE_FORMAT_RGB8";
  v495[365] = 0;
  v495[366] = v260;
  v495[367] = 0x400u;
  LODWORD(v262) = 62;
  v96 = *(__m128i *)Napi::Value::From<unsigned int>(v359, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB8I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v96, 8).m128i_u64[0];
  v495[368] = (unsigned __int64)"TEXTURE_FORMAT_RGB8I";
  v495[369] = 0;
  v495[370] = v260;
  v495[371] = 0x400u;
  LODWORD(v262) = 63;
  v97 = *(__m128i *)Napi::Value::From<unsigned int>(v360, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB8U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v97, 8).m128i_u64[0];
  v495[372] = (unsigned __int64)"TEXTURE_FORMAT_RGB8U";
  v495[373] = 0;
  v495[374] = v260;
  v495[375] = 0x400u;
  LODWORD(v262) = 64;
  v98 = *(__m128i *)Napi::Value::From<unsigned int>(v361, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB8S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v98, 8).m128i_u64[0];
  v495[376] = (unsigned __int64)"TEXTURE_FORMAT_RGB8S";
  v495[377] = 0;
  v495[378] = v260;
  v495[379] = 0x400u;
  LODWORD(v262) = 65;
  v99 = *(__m128i *)Napi::Value::From<unsigned int>(v362, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB9E5F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v99, 8).m128i_u64[0];
  v495[380] = (unsigned __int64)"TEXTURE_FORMAT_RGB9E5F";
  v495[381] = 0;
  v495[382] = v260;
  v495[383] = 0x400u;
  LODWORD(v262) = 66;
  v100 = *(__m128i *)Napi::Value::From<unsigned int>(v363, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BGRA8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v100, 8).m128i_u64[0];
  v495[384] = (unsigned __int64)"TEXTURE_FORMAT_BGRA8";
  v495[385] = 0;
  v495[386] = v260;
  v495[387] = 0x400u;
  LODWORD(v262) = 67;
  v101 = *(__m128i *)Napi::Value::From<unsigned int>(v364, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v101, 8).m128i_u64[0];
  v495[388] = (unsigned __int64)"TEXTURE_FORMAT_RGBA8";
  v495[389] = 0;
  v495[390] = v260;
  v495[391] = 0x400u;
  LODWORD(v262) = 68;
  v102 = *(__m128i *)Napi::Value::From<unsigned int>(v365, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA8I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v102, 8).m128i_u64[0];
  v495[392] = (unsigned __int64)"TEXTURE_FORMAT_RGBA8I";
  v495[393] = 0;
  v495[394] = v260;
  v495[395] = 0x400u;
  LODWORD(v262) = 69;
  v103 = *(__m128i *)Napi::Value::From<unsigned int>(v366, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA8U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v103, 8).m128i_u64[0];
  v495[396] = (unsigned __int64)"TEXTURE_FORMAT_RGBA8U";
  v495[397] = 0;
  v495[398] = v260;
  v495[399] = 0x400u;
  LODWORD(v262) = 70;
  v104 = *(__m128i *)Napi::Value::From<unsigned int>(v367, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA8S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v104, 8).m128i_u64[0];
  v495[400] = (unsigned __int64)"TEXTURE_FORMAT_RGBA8S";
  v495[401] = 0;
  v495[402] = v260;
  v495[403] = 0x400u;
  LODWORD(v262) = 71;
  v105 = *(__m128i *)Napi::Value::From<unsigned int>(v368, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v105, 8).m128i_u64[0];
  v495[404] = (unsigned __int64)"TEXTURE_FORMAT_RGBA16";
  v495[405] = 0;
  v495[406] = v260;
  v495[407] = 0x400u;
  LODWORD(v262) = 72;
  v106 = *(__m128i *)Napi::Value::From<unsigned int>(v369, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA16I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v106, 8).m128i_u64[0];
  v495[408] = (unsigned __int64)"TEXTURE_FORMAT_RGBA16I";
  v495[409] = 0;
  v495[410] = v260;
  v495[411] = 0x400u;
  LODWORD(v262) = 73;
  v107 = *(__m128i *)Napi::Value::From<unsigned int>(v370, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA16U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v107, 8).m128i_u64[0];
  v495[412] = (unsigned __int64)"TEXTURE_FORMAT_RGBA16U";
  v495[413] = 0;
  v495[414] = v260;
  v495[415] = 0x400u;
  LODWORD(v262) = 74;
  v108 = *(__m128i *)Napi::Value::From<unsigned int>(v371, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA16F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v108, 8).m128i_u64[0];
  v495[416] = (unsigned __int64)"TEXTURE_FORMAT_RGBA16F";
  v495[417] = 0;
  v495[418] = v260;
  v495[419] = 0x400u;
  LODWORD(v262) = 75;
  v109 = *(__m128i *)Napi::Value::From<unsigned int>(v372, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA16S";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v109, 8).m128i_u64[0];
  v495[420] = (unsigned __int64)"TEXTURE_FORMAT_RGBA16S";
  v495[421] = 0;
  v495[422] = v260;
  v495[423] = 0x400u;
  LODWORD(v262) = 76;
  v110 = *(__m128i *)Napi::Value::From<unsigned int>(v373, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA32I";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v110, 8).m128i_u64[0];
  v495[424] = (unsigned __int64)"TEXTURE_FORMAT_RGBA32I";
  v495[425] = 0;
  v495[426] = v260;
  v495[427] = 0x400u;
  LODWORD(v262) = 77;
  v111 = *(__m128i *)Napi::Value::From<unsigned int>(v374, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA32U";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v111, 8).m128i_u64[0];
  v495[428] = (unsigned __int64)"TEXTURE_FORMAT_RGBA32U";
  v495[429] = 0;
  v495[430] = v260;
  v495[431] = 0x400u;
  LODWORD(v262) = 78;
  v112 = *(__m128i *)Napi::Value::From<unsigned int>(v375, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA32F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v112, 8).m128i_u64[0];
  v495[432] = (unsigned __int64)"TEXTURE_FORMAT_RGBA32F";
  v495[433] = 0;
  v495[434] = v260;
  v495[435] = 0x400u;
  LODWORD(v262) = 79;
  v113 = *(__m128i *)Napi::Value::From<unsigned int>(v376, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_B5G6R5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v113, 8).m128i_u64[0];
  v495[436] = (unsigned __int64)"TEXTURE_FORMAT_B5G6R5";
  v495[437] = 0;
  v495[438] = v260;
  v495[439] = 0x400u;
  LODWORD(v262) = 80;
  v114 = *(__m128i *)Napi::Value::From<unsigned int>(v377, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_R5G6B5";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v114, 8).m128i_u64[0];
  v495[440] = (unsigned __int64)"TEXTURE_FORMAT_R5G6B5";
  v495[441] = 0;
  v495[442] = v260;
  v495[443] = 0x400u;
  LODWORD(v262) = 81;
  v115 = *(__m128i *)Napi::Value::From<unsigned int>(v378, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BGRA4";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v115, 8).m128i_u64[0];
  v495[444] = (unsigned __int64)"TEXTURE_FORMAT_BGRA4";
  v495[445] = 0;
  v495[446] = v260;
  v495[447] = 0x400u;
  LODWORD(v262) = 82;
  v116 = *(__m128i *)Napi::Value::From<unsigned int>(v379, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGBA4";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v116, 8).m128i_u64[0];
  v495[448] = (unsigned __int64)"TEXTURE_FORMAT_RGBA4";
  v495[449] = 0;
  v495[450] = v260;
  v495[451] = 0x400u;
  LODWORD(v262) = 83;
  v117 = *(__m128i *)Napi::Value::From<unsigned int>(v380, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_BGR5A1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v117, 8).m128i_u64[0];
  v495[452] = (unsigned __int64)"TEXTURE_FORMAT_BGR5A1";
  v495[453] = 0;
  v495[454] = v260;
  v495[455] = 0x400u;
  LODWORD(v262) = 84;
  v118 = *(__m128i *)Napi::Value::From<unsigned int>(v381, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB5A1";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v118, 8).m128i_u64[0];
  v495[456] = (unsigned __int64)"TEXTURE_FORMAT_RGB5A1";
  v495[457] = 0;
  v495[458] = v260;
  v495[459] = 0x400u;
  LODWORD(v262) = 85;
  v119 = *(__m128i *)Napi::Value::From<unsigned int>(v382, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RGB10A2";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v119, 8).m128i_u64[0];
  v495[460] = (unsigned __int64)"TEXTURE_FORMAT_RGB10A2";
  v495[461] = 0;
  v495[462] = v260;
  v495[463] = 0x400u;
  LODWORD(v262) = 86;
  v120 = *(__m128i *)Napi::Value::From<unsigned int>(v383, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_RG11B10F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v120, 8).m128i_u64[0];
  v495[464] = (unsigned __int64)"TEXTURE_FORMAT_RG11B10F";
  v495[465] = 0;
  v495[466] = v260;
  v495[467] = 0x400u;
  LODWORD(v262) = 88;
  v121 = *(__m128i *)Napi::Value::From<unsigned int>(v384, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v121, 8).m128i_u64[0];
  v495[468] = (unsigned __int64)"TEXTURE_FORMAT_D16";
  v495[469] = 0;
  v495[470] = v260;
  v495[471] = 0x400u;
  LODWORD(v262) = 89;
  v122 = *(__m128i *)Napi::Value::From<unsigned int>(v385, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D24";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v122, 8).m128i_u64[0];
  v495[472] = (unsigned __int64)"TEXTURE_FORMAT_D24";
  v495[473] = 0;
  v495[474] = v260;
  v495[475] = 0x400u;
  LODWORD(v262) = 90;
  v123 = *(__m128i *)Napi::Value::From<unsigned int>(v386, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D24S8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v123, 8).m128i_u64[0];
  v495[476] = (unsigned __int64)"TEXTURE_FORMAT_D24S8";
  v495[477] = 0;
  v495[478] = v260;
  v495[479] = 0x400u;
  LODWORD(v262) = 91;
  v124 = *(__m128i *)Napi::Value::From<unsigned int>(v387, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D32";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v124, 8).m128i_u64[0];
  v495[480] = (unsigned __int64)"TEXTURE_FORMAT_D32";
  v495[481] = 0;
  v495[482] = v260;
  v495[483] = 0x400u;
  LODWORD(v262) = 92;
  v125 = *(__m128i *)Napi::Value::From<unsigned int>(v388, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D16F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v125, 8).m128i_u64[0];
  v495[484] = (unsigned __int64)"TEXTURE_FORMAT_D16F";
  v495[485] = 0;
  v495[486] = v260;
  v495[487] = 0x400u;
  LODWORD(v262) = 93;
  v126 = *(__m128i *)Napi::Value::From<unsigned int>(v389, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D24F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v126, 8).m128i_u64[0];
  v495[488] = (unsigned __int64)"TEXTURE_FORMAT_D24F";
  v495[489] = 0;
  v495[490] = v260;
  v495[491] = 0x400u;
  LODWORD(v262) = 94;
  v127 = *(__m128i *)Napi::Value::From<unsigned int>(v390, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D32F";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v127, 8).m128i_u64[0];
  v495[492] = (unsigned __int64)"TEXTURE_FORMAT_D32F";
  v495[493] = 0;
  v495[494] = v260;
  v495[495] = 0x400u;
  LODWORD(v262) = 95;
  v128 = *(__m128i *)Napi::Value::From<unsigned int>(v391, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "TEXTURE_FORMAT_D0S8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v128, 8).m128i_u64[0];
  v495[496] = (unsigned __int64)"TEXTURE_FORMAT_D0S8";
  v495[497] = 0;
  v495[498] = v260;
  v495[499] = 0x400u;
  LODWORD(v262) = 0;
  v129 = *(__m128i *)Napi::Value::From<unsigned int>(v392, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ATTRIB_TYPE_INT8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v129, 8).m128i_u64[0];
  v495[500] = (unsigned __int64)"ATTRIB_TYPE_INT8";
  v495[501] = 0;
  v495[502] = v260;
  v495[503] = 0x400u;
  LODWORD(v262) = 1;
  v130 = *(__m128i *)Napi::Value::From<unsigned int>(v393, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ATTRIB_TYPE_UINT8";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v130, 8).m128i_u64[0];
  v495[504] = (unsigned __int64)"ATTRIB_TYPE_UINT8";
  v495[505] = 0;
  v495[506] = v260;
  v495[507] = 0x400u;
  LODWORD(v262) = 3;
  v131 = *(__m128i *)Napi::Value::From<unsigned int>(v394, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ATTRIB_TYPE_INT16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v131, 8).m128i_u64[0];
  v495[508] = (unsigned __int64)"ATTRIB_TYPE_INT16";
  v495[509] = 0;
  v495[510] = v260;
  v495[511] = 0x400u;
  LODWORD(v262) = 4;
  v132 = *(__m128i *)Napi::Value::From<unsigned int>(v395, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ATTRIB_TYPE_UINT16";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v132, 8).m128i_u64[0];
  v495[512] = (unsigned __int64)"ATTRIB_TYPE_UINT16";
  v495[513] = 0;
  v495[514] = v260;
  v495[515] = 0x400u;
  LODWORD(v262) = 6;
  v133 = *(__m128i *)Napi::Value::From<unsigned int>(v396, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ATTRIB_TYPE_FLOAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v133, 8).m128i_u64[0];
  v495[516] = (unsigned __int64)"ATTRIB_TYPE_FLOAT";
  v495[517] = 0;
  v495[518] = v260;
  v495[519] = 0x400u;
  v134 = *(__m128i *)Napi::Value::From<unsigned __int64>(v397, a1, &qword_18054B7C8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_DISABLE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v134, 8).m128i_u64[0];
  v495[520] = (unsigned __int64)"ALPHA_DISABLE";
  v495[521] = 0;
  v495[522] = v260;
  v495[523] = 0x400u;
  v135 = *(__m128i *)Napi::Value::From<unsigned __int64>(v398, a1, &qword_18054B7D0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_ADD";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v135, 8).m128i_u64[0];
  v495[524] = (unsigned __int64)"ALPHA_ADD";
  v495[525] = 0;
  v495[526] = v260;
  v495[527] = 0x400u;
  v136 = *(__m128i *)Napi::Value::From<unsigned __int64>(v399, a1, &qword_18054B7D8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_COMBINE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v136, 8).m128i_u64[0];
  v495[528] = (unsigned __int64)"ALPHA_COMBINE";
  v495[529] = 0;
  v495[530] = v260;
  v495[531] = 0x400u;
  v137 = *(__m128i *)Napi::Value::From<unsigned __int64>(v400, a1, &qword_18054B7E0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_SUBTRACT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v137, 8).m128i_u64[0];
  v495[532] = (unsigned __int64)"ALPHA_SUBTRACT";
  v495[533] = 0;
  v495[534] = v260;
  v495[535] = 0x400u;
  v138 = *(__m128i *)Napi::Value::From<unsigned __int64>(v401, a1, &qword_18054B7E8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_MULTIPLY";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v138, 8).m128i_u64[0];
  v495[536] = (unsigned __int64)"ALPHA_MULTIPLY";
  v495[537] = 0;
  v495[538] = v260;
  v495[539] = 0x400u;
  v139 = *(__m128i *)Napi::Value::From<unsigned __int64>(v402, a1, &qword_18054B7F0);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_MAXIMIZED";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v139, 8).m128i_u64[0];
  v495[540] = (unsigned __int64)"ALPHA_MAXIMIZED";
  v495[541] = 0;
  v495[542] = v260;
  v495[543] = 0x400u;
  v140 = *(__m128i *)Napi::Value::From<unsigned __int64>(v403, a1, &qword_18054B7F8);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_ONEONE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v140, 8).m128i_u64[0];
  v495[544] = (unsigned __int64)"ALPHA_ONEONE";
  v495[545] = 0;
  v495[546] = v260;
  v495[547] = 0x400u;
  v141 = *(__m128i *)Napi::Value::From<unsigned __int64>(v404, a1, &qword_18054B800);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_PREMULTIPLIED";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v141, 8).m128i_u64[0];
  v495[548] = (unsigned __int64)"ALPHA_PREMULTIPLIED";
  v495[549] = 0;
  v495[550] = v260;
  v495[551] = 0x400u;
  v142 = *(__m128i *)Napi::Value::From<unsigned __int64>(v405, a1, &qword_18054B808);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_PREMULTIPLIED_PORTERDUFF";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v142, 8).m128i_u64[0];
  v495[552] = (unsigned __int64)"ALPHA_PREMULTIPLIED_PORTERDUFF";
  v495[553] = 0;
  v495[554] = v260;
  v495[555] = 0x400u;
  v143 = *(__m128i *)Napi::Value::From<unsigned __int64>(v406, a1, &qword_18054B810);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_INTERPOLATE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v143, 8).m128i_u64[0];
  v495[556] = (unsigned __int64)"ALPHA_INTERPOLATE";
  v495[557] = 0;
  v495[558] = v260;
  v495[559] = 0x400u;
  v144 = *(__m128i *)Napi::Value::From<unsigned __int64>(v407, a1, &qword_18054B818);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "ALPHA_SCREENMODE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v144, 8).m128i_u64[0];
  v495[560] = (unsigned __int64)"ALPHA_SCREENMODE";
  v495[561] = 0;
  v495[562] = v260;
  v495[563] = 0x400u;
  LODWORD(v262) = 0x10000;
  v145 = *(__m128i *)Napi::Value::From<unsigned int>(v408, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_LESS";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v145, 8).m128i_u64[0];
  v495[564] = (unsigned __int64)"STENCIL_TEST_LESS";
  v495[565] = 0;
  v495[566] = v260;
  v495[567] = 0x400u;
  LODWORD(v262) = 0x20000;
  v146 = *(__m128i *)Napi::Value::From<unsigned int>(v409, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_LEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v146, 8).m128i_u64[0];
  v495[568] = (unsigned __int64)"STENCIL_TEST_LEQUAL";
  v495[569] = 0;
  v495[570] = v260;
  v495[571] = 0x400u;
  LODWORD(v262) = 196608;
  v147 = *(__m128i *)Napi::Value::From<unsigned int>(v410, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_EQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v147, 8).m128i_u64[0];
  v495[572] = (unsigned __int64)"STENCIL_TEST_EQUAL";
  v495[573] = 0;
  v495[574] = v260;
  v495[575] = 0x400u;
  LODWORD(v262) = 0x40000;
  v148 = *(__m128i *)Napi::Value::From<unsigned int>(v411, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_GEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v148, 8).m128i_u64[0];
  v495[576] = (unsigned __int64)"STENCIL_TEST_GEQUAL";
  v495[577] = 0;
  v495[578] = v260;
  v495[579] = 0x400u;
  LODWORD(v262) = 327680;
  v149 = *(__m128i *)Napi::Value::From<unsigned int>(v412, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_GREATER";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v149, 8).m128i_u64[0];
  v495[580] = (unsigned __int64)"STENCIL_TEST_GREATER";
  v495[581] = 0;
  v495[582] = v260;
  v495[583] = 0x400u;
  LODWORD(v262) = 393216;
  v150 = *(__m128i *)Napi::Value::From<unsigned int>(v413, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_NOTEQUAL";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v150, 8).m128i_u64[0];
  v495[584] = (unsigned __int64)"STENCIL_TEST_NOTEQUAL";
  v495[585] = 0;
  v495[586] = v260;
  v495[587] = 0x400u;
  LODWORD(v262) = 458752;
  v151 = *(__m128i *)Napi::Value::From<unsigned int>(v414, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_NEVER";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v151, 8).m128i_u64[0];
  v495[588] = (unsigned __int64)"STENCIL_TEST_NEVER";
  v495[589] = 0;
  v495[590] = v260;
  v495[591] = 0x400u;
  LODWORD(v262) = 0x80000;
  v152 = *(__m128i *)Napi::Value::From<unsigned int>(v415, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_TEST_ALWAYS";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v152, 8).m128i_u64[0];
  v495[592] = (unsigned __int64)"STENCIL_TEST_ALWAYS";
  v495[593] = 0;
  v495[594] = v260;
  v495[595] = 0x400u;
  LODWORD(v262) = 0;
  v153 = *(__m128i *)Napi::Value::From<unsigned int>(v416, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_ZERO";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v153, 8).m128i_u64[0];
  v495[596] = (unsigned __int64)"STENCIL_OP_FAIL_S_ZERO";
  v495[597] = 0;
  v495[598] = v260;
  v495[599] = 0x400u;
  LODWORD(v262) = 0x100000;
  v154 = *(__m128i *)Napi::Value::From<unsigned int>(v417, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_KEEP";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v154, 8).m128i_u64[0];
  v495[600] = (unsigned __int64)"STENCIL_OP_FAIL_S_KEEP";
  v495[601] = 0;
  v495[602] = v260;
  v495[603] = 0x400u;
  LODWORD(v262) = 0x200000;
  v155 = *(__m128i *)Napi::Value::From<unsigned int>(v418, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_REPLACE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v155, 8).m128i_u64[0];
  v495[604] = (unsigned __int64)"STENCIL_OP_FAIL_S_REPLACE";
  v495[605] = 0;
  v495[606] = v260;
  v495[607] = 0x400u;
  LODWORD(v262) = 3145728;
  v156 = *(__m128i *)Napi::Value::From<unsigned int>(v419, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_INCR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v156, 8).m128i_u64[0];
  v495[608] = (unsigned __int64)"STENCIL_OP_FAIL_S_INCR";
  v495[609] = 0;
  v495[610] = v260;
  v495[611] = 0x400u;
  LODWORD(v262) = 0x400000;
  v157 = *(__m128i *)Napi::Value::From<unsigned int>(v420, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_INCRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v157, 8).m128i_u64[0];
  v495[612] = (unsigned __int64)"STENCIL_OP_FAIL_S_INCRSAT";
  v495[613] = 0;
  v495[614] = v260;
  v495[615] = 0x400u;
  LODWORD(v262) = 5242880;
  v158 = *(__m128i *)Napi::Value::From<unsigned int>(v421, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_DECR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v158, 8).m128i_u64[0];
  v495[616] = (unsigned __int64)"STENCIL_OP_FAIL_S_DECR";
  v495[617] = 0;
  v495[618] = v260;
  v495[619] = 0x400u;
  LODWORD(v262) = 6291456;
  v159 = *(__m128i *)Napi::Value::From<unsigned int>(v422, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_DECRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v159, 8).m128i_u64[0];
  v495[620] = (unsigned __int64)"STENCIL_OP_FAIL_S_DECRSAT";
  v495[621] = 0;
  v495[622] = v260;
  v495[623] = 0x400u;
  LODWORD(v262) = 7340032;
  v160 = *(__m128i *)Napi::Value::From<unsigned int>(v423, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_S_INVERT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v160, 8).m128i_u64[0];
  v495[624] = (unsigned __int64)"STENCIL_OP_FAIL_S_INVERT";
  v495[625] = 0;
  v495[626] = v260;
  v495[627] = 0x400u;
  LODWORD(v262) = 0;
  v161 = *(__m128i *)Napi::Value::From<unsigned int>(v424, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_ZERO";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v161, 8).m128i_u64[0];
  v495[628] = (unsigned __int64)"STENCIL_OP_FAIL_Z_ZERO";
  v495[629] = 0;
  v495[630] = v260;
  v495[631] = 0x400u;
  LODWORD(v262) = 0x1000000;
  v162 = *(__m128i *)Napi::Value::From<unsigned int>(v425, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_KEEP";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v162, 8).m128i_u64[0];
  v495[632] = (unsigned __int64)"STENCIL_OP_FAIL_Z_KEEP";
  v495[633] = 0;
  v495[634] = v260;
  v495[635] = 0x400u;
  LODWORD(v262) = 0x2000000;
  v163 = *(__m128i *)Napi::Value::From<unsigned int>(v426, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_REPLACE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v163, 8).m128i_u64[0];
  v495[636] = (unsigned __int64)"STENCIL_OP_FAIL_Z_REPLACE";
  v495[637] = 0;
  v495[638] = v260;
  v495[639] = 0x400u;
  LODWORD(v262) = 50331648;
  v164 = *(__m128i *)Napi::Value::From<unsigned int>(v427, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_INCR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v164, 8).m128i_u64[0];
  v495[640] = (unsigned __int64)"STENCIL_OP_FAIL_Z_INCR";
  v495[641] = 0;
  v495[642] = v260;
  v495[643] = 0x400u;
  LODWORD(v262) = 0x4000000;
  v165 = *(__m128i *)Napi::Value::From<unsigned int>(v428, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_INCRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v165, 8).m128i_u64[0];
  v495[644] = (unsigned __int64)"STENCIL_OP_FAIL_Z_INCRSAT";
  v495[645] = 0;
  v495[646] = v260;
  v495[647] = 0x400u;
  LODWORD(v262) = 83886080;
  v166 = *(__m128i *)Napi::Value::From<unsigned int>(v429, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_DECR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v166, 8).m128i_u64[0];
  v495[648] = (unsigned __int64)"STENCIL_OP_FAIL_Z_DECR";
  v495[649] = 0;
  v495[650] = v260;
  v495[651] = 0x400u;
  LODWORD(v262) = 100663296;
  v167 = *(__m128i *)Napi::Value::From<unsigned int>(v430, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_DECRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v167, 8).m128i_u64[0];
  v495[652] = (unsigned __int64)"STENCIL_OP_FAIL_Z_DECRSAT";
  v495[653] = 0;
  v495[654] = v260;
  v495[655] = 0x400u;
  LODWORD(v262) = 117440512;
  v168 = *(__m128i *)Napi::Value::From<unsigned int>(v431, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_FAIL_Z_INVERT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v168, 8).m128i_u64[0];
  v495[656] = (unsigned __int64)"STENCIL_OP_FAIL_Z_INVERT";
  v495[657] = 0;
  v495[658] = v260;
  v495[659] = 0x400u;
  LODWORD(v262) = 0;
  v169 = *(__m128i *)Napi::Value::From<unsigned int>(v432, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_ZERO";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v169, 8).m128i_u64[0];
  v495[660] = (unsigned __int64)"STENCIL_OP_PASS_Z_ZERO";
  v495[661] = 0;
  v495[662] = v260;
  v495[663] = 0x400u;
  LODWORD(v262) = 0x10000000;
  v170 = *(__m128i *)Napi::Value::From<unsigned int>(v433, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_KEEP";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v170, 8).m128i_u64[0];
  v495[664] = (unsigned __int64)"STENCIL_OP_PASS_Z_KEEP";
  v495[665] = 0;
  v495[666] = v260;
  v495[667] = 0x400u;
  LODWORD(v262) = 0x20000000;
  v171 = *(__m128i *)Napi::Value::From<unsigned int>(v434, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_REPLACE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v171, 8).m128i_u64[0];
  v495[668] = (unsigned __int64)"STENCIL_OP_PASS_Z_REPLACE";
  v495[669] = 0;
  v495[670] = v260;
  v495[671] = 0x400u;
  LODWORD(v262) = 805306368;
  v172 = *(__m128i *)Napi::Value::From<unsigned int>(v435, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_INCR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v172, 8).m128i_u64[0];
  v495[672] = (unsigned __int64)"STENCIL_OP_PASS_Z_INCR";
  v495[673] = 0;
  v495[674] = v260;
  v495[675] = 0x400u;
  LODWORD(v262) = 0x40000000;
  v173 = *(__m128i *)Napi::Value::From<unsigned int>(v436, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_INCRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v173, 8).m128i_u64[0];
  v495[676] = (unsigned __int64)"STENCIL_OP_PASS_Z_INCRSAT";
  v495[677] = 0;
  v495[678] = v260;
  v495[679] = 0x400u;
  LODWORD(v262) = 1342177280;
  v174 = *(__m128i *)Napi::Value::From<unsigned int>(v437, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_DECR";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v174, 8).m128i_u64[0];
  v495[680] = (unsigned __int64)"STENCIL_OP_PASS_Z_DECR";
  v495[681] = 0;
  v495[682] = v260;
  v495[683] = 0x400u;
  LODWORD(v262) = 1610612736;
  v175 = *(__m128i *)Napi::Value::From<unsigned int>(v438, a1, &v262);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "STENCIL_OP_PASS_Z_DECRSAT";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v175, 8).m128i_u64[0];
  v495[684] = (unsigned __int64)"STENCIL_OP_PASS_Z_DECRSAT";
  v495[685] = 0;
  v495[686] = v260;
  v495[687] = 0x400u;
  LODWORD(v262) = 1879048192;
  v176 = *(__m128i *)Napi::Value::From<unsigned int>(v439, a1, &v262);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v176, 8).m128i_u64[0];
  v495[688] = (unsigned __int64)"STENCIL_OP_PASS_Z_INVERT";
  v495[689] = 0;
  v495[690] = v260;
  v495[691] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DeleteVertexArray;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DeleteVertexArray;
  v265 = v259;
  v177 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v440,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v177, 8).m128i_u64[0];
  v495[692] = (unsigned __int64)"COMMAND_DELETEVERTEXARRAY";
  v495[693] = 0;
  v495[694] = v260;
  v495[695] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DeleteIndexBuffer;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DeleteIndexBuffer;
  v265 = v259;
  v178 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v441,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v178, 8).m128i_u64[0];
  v495[696] = (unsigned __int64)"COMMAND_DELETEINDEXBUFFER";
  v495[697] = 0;
  v495[698] = v260;
  v495[699] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DeleteVertexBuffer;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DeleteVertexBuffer;
  v265 = v259;
  v179 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v442,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v179, 8).m128i_u64[0];
  v495[700] = (unsigned __int64)"COMMAND_DELETEVERTEXBUFFER";
  v495[701] = 0;
  v495[702] = v260;
  v495[703] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetProgram;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetProgram;
  v265 = v259;
  v180 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v443,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v180, 8).m128i_u64[0];
  v495[704] = (unsigned __int64)"COMMAND_SETPROGRAM";
  v495[705] = 0;
  v495[706] = v260;
  v495[707] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DeleteProgram;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DeleteProgram;
  v265 = v259;
  v181 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v444,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v181, 8).m128i_u64[0];
  v495[708] = (unsigned __int64)"COMMAND_DELETEPROGRAM";
  v495[709] = 0;
  v495[710] = v260;
  v495[711] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetMatrices;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetMatrices;
  v265 = v259;
  v182 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v445,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v182, 8).m128i_u64[0];
  v495[712] = (unsigned __int64)"COMMAND_SETMATRICES";
  v495[713] = 0;
  v495[714] = v260;
  v495[715] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetMatrix3x3;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetMatrix3x3;
  v265 = v259;
  v183 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v446,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v183, 8).m128i_u64[0];
  v495[716] = (unsigned __int64)"COMMAND_SETMATRIX";
  v495[717] = 0;
  v495[718] = v260;
  v495[719] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetMatrix3x3;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetMatrix3x3;
  v265 = v259;
  v184 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v447,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v184, 8).m128i_u64[0];
  v495[720] = (unsigned __int64)"COMMAND_SETMATRIX3X3";
  v495[721] = 0;
  v495[722] = v260;
  v495[723] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetMatrix2x2;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetMatrix2x2;
  v265 = v259;
  v185 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v448,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v185, 8).m128i_u64[0];
  v495[724] = (unsigned __int64)"COMMAND_SETMATRIX2X2";
  v495[725] = 0;
  v495[726] = v260;
  v495[727] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetInt;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetInt;
  v265 = v259;
  v186 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v449,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v186, 8).m128i_u64[0];
  v495[728] = (unsigned __int64)"COMMAND_SETINT";
  v495[729] = 0;
  v495[730] = v260;
  v495[731] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetIntArray;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetIntArray;
  v265 = v259;
  v187 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v450,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v187, 8).m128i_u64[0];
  v495[732] = (unsigned __int64)"COMMAND_SETINTARRAY";
  v495[733] = 0;
  v495[734] = v260;
  v495[735] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetIntArray2;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetIntArray2;
  v265 = v259;
  v188 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v451,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v188, 8).m128i_u64[0];
  v495[736] = (unsigned __int64)"COMMAND_SETINTARRAY2";
  v495[737] = 0;
  v495[738] = v260;
  v495[739] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetIntArray3;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetIntArray3;
  v265 = v259;
  v189 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v452,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v189, 8).m128i_u64[0];
  v495[740] = (unsigned __int64)"COMMAND_SETINTARRAY3";
  v495[741] = 0;
  v495[742] = v260;
  v495[743] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetIntArray4;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetIntArray4;
  v265 = v259;
  v190 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v453,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v190, 8).m128i_u64[0];
  v495[744] = (unsigned __int64)"COMMAND_SETINTARRAY4";
  v495[745] = 0;
  v495[746] = v260;
  v495[747] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloatArray;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloatArray;
  v265 = v259;
  v191 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v454,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v191, 8).m128i_u64[0];
  v495[748] = (unsigned __int64)"COMMAND_SETFLOATARRAY";
  v495[749] = 0;
  v495[750] = v260;
  v495[751] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloatArray2;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloatArray2;
  v265 = v259;
  v192 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v455,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v192, 8).m128i_u64[0];
  v495[752] = (unsigned __int64)"COMMAND_SETFLOATARRAY2";
  v495[753] = 0;
  v495[754] = v260;
  v495[755] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloatArray3;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloatArray3;
  v265 = v259;
  v193 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v456,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v193, 8).m128i_u64[0];
  v495[756] = (unsigned __int64)"COMMAND_SETFLOATARRAY3";
  v495[757] = 0;
  v495[758] = v260;
  v495[759] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloatArray4;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloatArray4;
  v265 = v259;
  v194 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v457,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v194, 8).m128i_u64[0];
  v495[760] = (unsigned __int64)"COMMAND_SETFLOATARRAY4";
  v495[761] = 0;
  v495[762] = v260;
  v495[763] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetTextureSampling;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetTextureSampling;
  v265 = v259;
  v195 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v458,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v195, 8).m128i_u64[0];
  v495[764] = (unsigned __int64)"COMMAND_SETTEXTURESAMPLING";
  v495[765] = 0;
  v495[766] = v260;
  v495[767] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetTextureWrapMode;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetTextureWrapMode;
  v265 = v259;
  v196 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v459,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v196, 8).m128i_u64[0];
  v495[768] = (unsigned __int64)"COMMAND_SETTEXTUREWRAPMODE";
  v495[769] = 0;
  v495[770] = v260;
  v495[771] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetTextureAnisotropicLevel;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetTextureAnisotropicLevel;
  v265 = v259;
  v197 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v460,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v197, 8).m128i_u64[0];
  v495[772] = (unsigned __int64)"COMMAND_SETTEXTUREANISOTROPICLEVEL";
  v495[773] = 0;
  v495[774] = v260;
  v495[775] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetTexture;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetTexture;
  v265 = v259;
  v198 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v461,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v198, 8).m128i_u64[0];
  v495[776] = (unsigned __int64)"COMMAND_SETTEXTURE";
  v495[777] = 0;
  v495[778] = v260;
  v495[779] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::UnsetTexture;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::UnsetTexture;
  v265 = v259;
  v199 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v462,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v199, 8).m128i_u64[0];
  v495[780] = (unsigned __int64)"COMMAND_UNSETTEXTURE";
  v495[781] = 0;
  v495[782] = v260;
  v495[783] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DiscardAllTextures;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DiscardAllTextures;
  v265 = v259;
  v200 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v463,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v200, 8).m128i_u64[0];
  v495[784] = (unsigned __int64)"COMMAND_DISCARDALLTEXTURES";
  v495[785] = 0;
  v495[786] = v260;
  v495[787] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::BindVertexArray;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::BindVertexArray;
  v265 = v259;
  v201 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v464,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v201, 8).m128i_u64[0];
  v495[788] = (unsigned __int64)"COMMAND_BINDVERTEXARRAY";
  v495[789] = 0;
  v495[790] = v260;
  v495[791] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetState;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetState;
  v265 = v259;
  v202 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v465,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v202, 8).m128i_u64[0];
  v495[792] = (unsigned __int64)"COMMAND_SETSTATE";
  v495[793] = 0;
  v495[794] = v260;
  v495[795] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetZOffset;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetZOffset;
  v265 = v259;
  v203 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v466,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v203, 8).m128i_u64[0];
  v495[796] = (unsigned __int64)"COMMAND_SETZOFFSET";
  v495[797] = 0;
  v495[798] = v260;
  v495[799] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetZOffset;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetZOffset;
  v265 = v259;
  v204 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v467,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v204, 8).m128i_u64[0];
  v495[800] = (unsigned __int64)"COMMAND_SETZOFFSETUNITS";
  v495[801] = 0;
  v495[802] = v260;
  v495[803] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetDepthTest;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetDepthTest;
  v265 = v259;
  v205 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v468,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v205, 8).m128i_u64[0];
  v495[804] = (unsigned __int64)"COMMAND_SETDEPTHTEST";
  v495[805] = 0;
  v495[806] = v260;
  v495[807] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetDepthWrite;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetDepthWrite;
  v265 = v259;
  v206 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v469,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v206, 8).m128i_u64[0];
  v495[808] = (unsigned __int64)"COMMAND_SETDEPTHWRITE";
  v495[809] = 0;
  v495[810] = v260;
  v495[811] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetColorWrite;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetColorWrite;
  v265 = v259;
  v207 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v470,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v207, 8).m128i_u64[0];
  v495[812] = (unsigned __int64)"COMMAND_SETCOLORWRITE";
  v495[813] = 0;
  v495[814] = v260;
  v495[815] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetBlendMode;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetBlendMode;
  v265 = v259;
  v208 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v471,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v208, 8).m128i_u64[0];
  v495[816] = (unsigned __int64)"COMMAND_SETBLENDMODE";
  v495[817] = 0;
  v495[818] = v260;
  v495[819] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloat;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloat;
  v265 = v259;
  v209 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v472,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v209, 8).m128i_u64[0];
  v495[820] = (unsigned __int64)"COMMAND_SETFLOAT";
  v495[821] = 0;
  v495[822] = v260;
  v495[823] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloat2;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloat2;
  v265 = v259;
  v210 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v473,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v210, 8).m128i_u64[0];
  v495[824] = (unsigned __int64)"COMMAND_SETFLOAT2";
  v495[825] = 0;
  v495[826] = v260;
  v495[827] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloat3;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloat3;
  v265 = v259;
  v211 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v474,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v211, 8).m128i_u64[0];
  v495[828] = (unsigned __int64)"COMMAND_SETFLOAT3";
  v495[829] = 0;
  v495[830] = v260;
  v495[831] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetFloat4;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetFloat4;
  v265 = v259;
  v212 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v475,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v212, 8).m128i_u64[0];
  v495[832] = (unsigned __int64)"COMMAND_SETFLOAT4";
  v495[833] = 0;
  v495[834] = v260;
  v495[835] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::BindFrameBuffer;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::BindFrameBuffer;
  v265 = v259;
  v213 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v476,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v213, 8).m128i_u64[0];
  v495[836] = (unsigned __int64)"COMMAND_BINDFRAMEBUFFER";
  v495[837] = 0;
  v495[838] = v260;
  v495[839] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::UnbindFrameBuffer;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::UnbindFrameBuffer;
  v265 = v259;
  v214 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v477,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v214, 8).m128i_u64[0];
  v495[840] = (unsigned __int64)"COMMAND_UNBINDFRAMEBUFFER";
  v495[841] = 0;
  v495[842] = v260;
  v495[843] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DeleteFrameBuffer;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DeleteFrameBuffer;
  v265 = v259;
  v215 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v478,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v215, 8).m128i_u64[0];
  v495[844] = (unsigned __int64)"COMMAND_DELETEFRAMEBUFFER";
  v495[845] = 0;
  v495[846] = v260;
  v495[847] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DrawIndexed;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DrawIndexed;
  v265 = v259;
  v216 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v479,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v216, 8).m128i_u64[0];
  v495[848] = (unsigned __int64)"COMMAND_DRAWINDEXED";
  v495[849] = 0;
  v495[850] = v260;
  v495[851] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DrawIndexedInstanced;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DrawIndexedInstanced;
  v265 = v259;
  v217 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v480,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v217, 8).m128i_u64[0];
  v495[852] = (unsigned __int64)"COMMAND_DRAWINDEXEDINSTANCED";
  v495[853] = 0;
  v495[854] = v260;
  v495[855] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::Draw;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::Draw;
  v265 = v259;
  v218 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v481,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v218, 8).m128i_u64[0];
  v495[856] = (unsigned __int64)"COMMAND_DRAW";
  v495[857] = 0;
  v495[858] = v260;
  v495[859] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::DrawInstanced;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::DrawInstanced;
  v265 = v259;
  v219 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v482,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v219, 8).m128i_u64[0];
  v495[860] = (unsigned __int64)"COMMAND_DRAWINSTANCED";
  v495[861] = 0;
  v495[862] = v260;
  v495[863] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::Clear;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::Clear;
  v265 = v259;
  v220 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v483,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v220, 8).m128i_u64[0];
  v495[864] = (unsigned __int64)"COMMAND_CLEAR";
  v495[865] = 0;
  v495[866] = v260;
  v495[867] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetStencil;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetStencil;
  v265 = v259;
  v221 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v484,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v221, 8).m128i_u64[0];
  v495[868] = (unsigned __int64)"COMMAND_SETSTENCIL";
  v495[869] = 0;
  v495[870] = v260;
  v495[871] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetViewPort;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetViewPort;
  v265 = v259;
  v222 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v485,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v222, 8).m128i_u64[0];
  v495[872] = (unsigned __int64)"COMMAND_SETVIEWPORT";
  v495[873] = 0;
  v495[874] = v260;
  v495[875] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::SetScissor;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::SetScissor;
  v265 = v259;
  v223 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v486,
                       a1,
                       &v264);
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v223, 8).m128i_u64[0];
  v495[876] = (unsigned __int64)"COMMAND_SETSCISSOR";
  v495[877] = 0;
  v495[878] = v260;
  v495[879] = 0x400u;
  v257 = (const char *)Babylon::NativeEngine::CopyTexture;
  v258 = 0;
  LODWORD(v259) = 0;
  v264 = (unsigned __int64)Babylon::NativeEngine::CopyTexture;
  v265 = v259;
  v224 = *(__m128i *)Napi::FunctionPointer::Create<Babylon::NativeEngine,void,Babylon::NativeDataStream::Reader &>(
                       v268,
                       a1,
                       &v264);
  v258 = 0;
  *(_QWORD *)&v260 = 0;
  v261 = 0x400u;
  v257 = "COMMAND_COPYTEXTURE";
  *((_QWORD *)&v260 + 1) = _mm_srli_si128(v224, 8).m128i_u64[0];
  v495[880] = (unsigned __int64)"COMMAND_COPYTEXTURE";
  v495[881] = 0;
  v495[882] = v260;
  v495[883] = 0x400u;
  v225 = operator new(0x20u);
  if ( v225 )
  {
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v225 = (unsigned __int64)Babylon::NativeEngine::Dispose;
    v225[1] = v259;
  }
  else
  {
    v225 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v225;
  v495[884] = (unsigned __int64)"dispose";
  v495[885] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[886] = 0;
  v495[887] = v261;
  v226 = operator new(0x20u);
  if ( v226 )
  {
    v257 = (const char *)Babylon::NativeEngine::RequestAnimationFrame;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v226 = (unsigned __int64)Babylon::NativeEngine::RequestAnimationFrame;
    v226[1] = v259;
  }
  else
  {
    v226 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v226;
  v495[888] = (unsigned __int64)"requestAnimationFrame";
  v495[889] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[890] = 0;
  v495[891] = v261;
  v227 = operator new(0x20u);
  if ( v227 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateVertexArray;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v227 = (unsigned __int64)&Babylon::NativeEngine::CreateVertexArray;
    v227[1] = v259;
  }
  else
  {
    v227 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v227;
  v495[892] = (unsigned __int64)"createVertexArray";
  v495[893] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[894] = 0;
  v495[895] = v261;
  v228 = operator new(0x20u);
  if ( v228 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateIndexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v228 = (unsigned __int64)&Babylon::NativeEngine::CreateIndexBuffer;
    v228[1] = v259;
  }
  else
  {
    v228 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v228;
  v495[896] = (unsigned __int64)"createIndexBuffer";
  v495[897] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[898] = 0;
  v495[899] = v261;
  v229 = operator new(0x20u);
  if ( v229 )
  {
    v257 = (const char *)Babylon::NativeEngine::RecordIndexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v229 = (unsigned __int64)Babylon::NativeEngine::RecordIndexBuffer;
    v229[1] = v259;
  }
  else
  {
    v229 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v229;
  v495[900] = (unsigned __int64)"recordIndexBuffer";
  v495[901] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[902] = 0;
  v495[903] = v261;
  v230 = operator new(0x20u);
  if ( v230 )
  {
    v257 = (const char *)Babylon::NativeEngine::UpdateDynamicIndexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v230 = (unsigned __int64)Babylon::NativeEngine::UpdateDynamicIndexBuffer;
    v230[1] = v259;
  }
  else
  {
    v230 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v230;
  v495[904] = (unsigned __int64)"updateDynamicIndexBuffer";
  v495[905] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[906] = 0;
  v495[907] = v261;
  v231 = operator new(0x20u);
  if ( v231 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateVertexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v231 = (unsigned __int64)&Babylon::NativeEngine::CreateVertexBuffer;
    v231[1] = v259;
  }
  else
  {
    v231 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v231;
  v495[908] = (unsigned __int64)"createVertexBuffer";
  v495[909] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[910] = 0;
  v495[911] = v261;
  v232 = operator new(0x20u);
  if ( v232 )
  {
    v257 = (const char *)Babylon::NativeEngine::RecordVertexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v232 = (unsigned __int64)Babylon::NativeEngine::RecordVertexBuffer;
    v232[1] = v259;
  }
  else
  {
    v232 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v232;
  v495[912] = (unsigned __int64)"recordVertexBuffer";
  v495[913] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[914] = 0;
  v495[915] = v261;
  v233 = operator new(0x20u);
  if ( v233 )
  {
    v257 = (const char *)Babylon::NativeEngine::UpdateDynamicVertexBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v233 = (unsigned __int64)Babylon::NativeEngine::UpdateDynamicVertexBuffer;
    v233[1] = v259;
  }
  else
  {
    v233 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v233;
  v495[916] = (unsigned __int64)"updateDynamicVertexBuffer";
  v495[917] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[918] = 0;
  v495[919] = v261;
  v234 = operator new(0x20u);
  if ( v234 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateProgram;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v234 = (unsigned __int64)&Babylon::NativeEngine::CreateProgram;
    v234[1] = v259;
  }
  else
  {
    v234 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v234;
  v495[920] = (unsigned __int64)"createProgram";
  v495[921] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[922] = 0;
  v495[923] = v261;
  v235 = operator new(0x20u);
  if ( v235 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateProgramAsync;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v235 = (unsigned __int64)&Babylon::NativeEngine::CreateProgramAsync;
    v235[1] = v259;
  }
  else
  {
    v235 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v235;
  v495[924] = (unsigned __int64)"createProgramAsync";
  v495[925] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[926] = 0;
  v495[927] = v261;
  v236 = operator new(0x20u);
  if ( v236 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetUniforms;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v236 = (unsigned __int64)&Babylon::NativeEngine::GetUniforms;
    v236[1] = v259;
  }
  else
  {
    v236 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v236;
  v495[928] = (unsigned __int64)"getUniforms";
  v495[929] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[930] = 0;
  v495[931] = v261;
  v237 = operator new(0x20u);
  if ( v237 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetAttributes;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v237 = (unsigned __int64)&Babylon::NativeEngine::GetAttributes;
    v237[1] = v259;
  }
  else
  {
    v237 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v237;
  v495[932] = (unsigned __int64)"getAttributes";
  v495[933] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[934] = 0;
  v495[935] = v261;
  v238 = operator new(0x20u);
  if ( v238 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v238 = (unsigned __int64)&Babylon::NativeEngine::CreateTexture;
    v238[1] = v259;
  }
  else
  {
    v238 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v238;
  v495[936] = (unsigned __int64)"createTexture";
  v495[937] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[938] = 0;
  v495[939] = v261;
  v239 = operator new(0x20u);
  if ( v239 )
  {
    v257 = (const char *)Babylon::NativeEngine::InitializeTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v239 = (unsigned __int64)Babylon::NativeEngine::InitializeTexture;
    v239[1] = v259;
  }
  else
  {
    v239 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v239;
  v495[940] = (unsigned __int64)"initializeTexture";
  v495[941] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[942] = 0;
  v495[943] = v261;
  v240 = operator new(0x20u);
  if ( v240 )
  {
    v257 = (const char *)Babylon::NativeEngine::LoadTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v240 = (unsigned __int64)Babylon::NativeEngine::LoadTexture;
    v240[1] = v259;
  }
  else
  {
    v240 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v240;
  v495[944] = (unsigned __int64)"loadTexture";
  v495[945] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[946] = 0;
  v495[947] = v261;
  v241 = operator new(0x20u);
  if ( v241 )
  {
    v257 = (const char *)Babylon::NativeEngine::LoadRawTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v241 = (unsigned __int64)Babylon::NativeEngine::LoadRawTexture;
    v241[1] = v259;
  }
  else
  {
    v241 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v241;
  v495[948] = (unsigned __int64)"loadRawTexture";
  v495[949] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[950] = 0;
  v495[951] = v261;
  v242 = operator new(0x20u);
  if ( v242 )
  {
    v257 = (const char *)Babylon::NativeEngine::LoadRawTexture2DArray;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v242 = (unsigned __int64)Babylon::NativeEngine::LoadRawTexture2DArray;
    v242[1] = v259;
  }
  else
  {
    v242 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v242;
  v495[952] = (unsigned __int64)"loadRawTexture2DArray";
  v495[953] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[954] = 0;
  v495[955] = v261;
  v243 = operator new(0x20u);
  if ( v243 )
  {
    v257 = (const char *)Babylon::NativeEngine::LoadCubeTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v243 = (unsigned __int64)Babylon::NativeEngine::LoadCubeTexture;
    v243[1] = v259;
  }
  else
  {
    v243 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v243;
  v495[956] = (unsigned __int64)"loadCubeTexture";
  v495[957] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[958] = 0;
  v495[959] = v261;
  v244 = operator new(0x20u);
  if ( v244 )
  {
    v257 = (const char *)Babylon::NativeEngine::LoadCubeTextureWithMips;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v244 = (unsigned __int64)Babylon::NativeEngine::LoadCubeTextureWithMips;
    v244[1] = v259;
  }
  else
  {
    v244 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v244;
  v495[960] = (unsigned __int64)"loadCubeTextureWithMips";
  v495[961] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[962] = 0;
  v495[963] = v261;
  v245 = operator new(0x20u);
  if ( v245 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetTextureWidth;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v245 = (unsigned __int64)&Babylon::NativeEngine::GetTextureWidth;
    v245[1] = v259;
  }
  else
  {
    v245 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v245;
  v495[964] = (unsigned __int64)"getTextureWidth";
  v495[965] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[966] = 0;
  v495[967] = v261;
  v246 = operator new(0x20u);
  if ( v246 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetTextureHeight;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v246 = (unsigned __int64)&Babylon::NativeEngine::GetTextureHeight;
    v246[1] = v259;
  }
  else
  {
    v246 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v246;
  v495[968] = (unsigned __int64)"getTextureHeight";
  v495[969] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[970] = 0;
  v495[971] = v261;
  v247 = operator new(0x20u);
  if ( v247 )
  {
    v257 = (const char *)Babylon::NativeEngine::DeleteTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v247 = (unsigned __int64)Babylon::NativeEngine::DeleteTexture;
    v247[1] = v259;
  }
  else
  {
    v247 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v247;
  v495[972] = (unsigned __int64)"deleteTexture";
  v495[973] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::Window>::InstanceVoidMethodCallbackWrapper;
  v495[974] = 0;
  v495[975] = v261;
  v248 = operator new(0x20u);
  if ( v248 )
  {
    v257 = (const char *)&Babylon::NativeEngine::ReadTexture;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v248 = (unsigned __int64)&Babylon::NativeEngine::ReadTexture;
    v248[1] = v259;
  }
  else
  {
    v248 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v248;
  v495[976] = (unsigned __int64)"readTexture";
  v495[977] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[978] = 0;
  v495[979] = v261;
  v249 = operator new(0x20u);
  if ( v249 )
  {
    v257 = (const char *)Babylon::NativeEngine::CreateImageBitmap;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v249 = (unsigned __int64)Babylon::NativeEngine::CreateImageBitmap;
    v249[1] = v259;
  }
  else
  {
    v249 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v249;
  v495[980] = (unsigned __int64)"createImageBitmap";
  v495[981] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[982] = 0;
  v495[983] = v261;
  v250 = operator new(0x20u);
  if ( v250 )
  {
    v257 = (const char *)Babylon::NativeEngine::ResizeImageBitmap;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v250 = (unsigned __int64)Babylon::NativeEngine::ResizeImageBitmap;
    v250[1] = v259;
  }
  else
  {
    v250 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v250;
  v495[984] = (unsigned __int64)"resizeImageBitmap";
  v495[985] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[986] = 0;
  v495[987] = v261;
  v251 = operator new(0x20u);
  if ( v251 )
  {
    v257 = (const char *)&Babylon::NativeEngine::CreateFrameBuffer;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v251 = (unsigned __int64)&Babylon::NativeEngine::CreateFrameBuffer;
    v251[1] = v259;
  }
  else
  {
    v251 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v251;
  v495[988] = (unsigned __int64)"createFrameBuffer";
  v495[989] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[990] = 0;
  v495[991] = v261;
  v252 = operator new(0x20u);
  if ( v252 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetRenderWidth;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v252 = (unsigned __int64)&Babylon::NativeEngine::GetRenderWidth;
    v252[1] = v259;
  }
  else
  {
    v252 = 0;
  }
  v258 = 0;
  *((_QWORD *)&v259 + 1) = 0;
  *(_QWORD *)&v261 = 0;
  v257 = "getRenderWidth";
  *(_QWORD *)&v259 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v261 + 1) = v252;
  v495[992] = (unsigned __int64)"getRenderWidth";
  v495[993] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[994] = 0;
  v495[995] = v261;
  v253 = operator new(0x20u);
  if ( v253 )
  {
    v257 = (const char *)&Babylon::NativeEngine::GetRenderHeight;
    v258 = 0;
    LODWORD(v259) = 0;
    *((_QWORD *)&v259 + 1) = 0;
    *v253 = (unsigned __int64)&Babylon::NativeEngine::GetRenderHeight;
    v253[1] = v259;
  }
  else
  {
    v253 = 0;
  }
  *((_QWORD *)&pExceptionObject + 1) = 0;
  *((_QWORD *)&v490 + 1) = 0;
  *(_QWORD *)&v492 = 0;
  *(_QWORD *)&pExceptionObject = "getRenderHeight";
  *(_QWORD *)&v490 = Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  *((_QWORD *)&v492 + 1) = v253;
  v495[996] = (unsigned __int64)"getRenderHeight";
  v495[997] = (unsigned __int64)Napi::InstanceWrap<Babylon::Polyfills::Internal::XMLHttpRequest>::InstanceMethodCallbackWrapper;
  v495[998] = 0;
  v495[999] = v492;
  *(_QWORD *)&v264 = &Babylon::NativeEngine::GetHardwareScalingLevel;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)&Babylon::NativeEngine::GetHardwareScalingLevel;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v496,
    (unsigned int)"getHardwareScalingLevel",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::SetHardwareScalingLevel;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::SetHardwareScalingLevel;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v497,
    (unsigned int)"setHardwareScalingLevel",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::SetCommandDataStream;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::SetCommandDataStream;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v498,
    (unsigned int)"setCommandDataStream",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::SubmitCommands;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::SubmitCommands;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v499,
    (unsigned int)"submitCommands",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::PopulateFrameStats;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::PopulateFrameStats;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v500,
    (unsigned int)"populateFrameStats",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::GetFrameBufferData;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::GetFrameBufferData;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v501,
    (unsigned int)"getFrameBufferData",
    (unsigned int)&v262,
    0,
    0);
  *(_QWORD *)&v264 = Babylon::NativeEngine::SetRenderResetCallback;
  *((_QWORD *)&v264 + 1) = 0;
  LODWORD(v265) = 0;
  v262 = (unsigned __int64)Babylon::NativeEngine::SetRenderResetCallback;
  v263 = v265;
  Napi::InstanceWrap<Babylon::NativeEngine>::InstanceMethod(
    (unsigned int)&v502,
    (unsigned int)"setDeviceLostCallback",
    (unsigned int)&v262,
    0,
    0);
  Napi::ObjectWrap<Babylon::NativeEngine>::DefineClass(
    (unsigned int)&v264,
    a1,
    (unsigned int)"_NativeEngine",
    257,
    (__int64)v495,
    0);
  *(_QWORD *)&v262 = a1;
  v254 = Napi::Env::Global(&v262, &v257);
  v255 = Napi::Object::Get(v254, v268, "_native");
  Napi::Value::As<Napi::Object>(v255, &v262);
  Napi::Object::Set<Napi::External<Babylon::Graphics::DeviceImpl>>(&v262, "Engine", &v264);
  result = napi_close_handle_scope_0(v266, v267);
  if ( (_DWORD)result )
    Napi::Error::Fatal("HandleScope::~HandleScope", "napi_close_handle_scope");
  return result;
}

```

## disassembly

```asm
0x180063370  mov     [rsp-8+arg_0], rbx
0x180063375  mov     [rsp-8+arg_8], rsi
0x18006337a  mov     [rsp-8+arg_10], rdi
0x18006337f  mov     [rsp-8+arg_18], r14
0x180063384  push    rbp
0x180063385  lea     rbp, [rsp-4E40h]
0x18006338d  mov     eax, 4F40h
0x180063392  call    _alloca_probe
0x180063397  sub     rsp, rax
0x18006339a  mov     rax, cs:__security_cookie
0x1800633a1  xor     rax, rsp
0x1800633a4  mov     [rbp+4E40h+var_10], rax
0x1800633ab  mov     rbx, rcx
0x1800633ae  mov     [rbp+4E40h+var_4E90], rcx
0x1800633b2  lea     rdx, [rbp+4E40h+var_4E88]
0x1800633b6  call    napi_open_handle_scope_0
0x1800633bb  test    eax, eax
0x1800633bd  jnz     loc_18006CB87
0x1800633c3  call    ?getCaps@bgfx@@YAPEBUCaps@1@XZ; bgfx::getCaps(void)
0x1800633c8  movups  xmm0, xmmword ptr [rax+28h]
0x1800633cc  movaps  [rbp+4E40h+pExceptionObject], xmm0
0x1800633d3  movups  xmm1, xmmword ptr [rax+38h]
0x1800633d7  movaps  [rbp+4E40h+var_40A0], xmm1
0x1800633de  movups  xmm0, xmmword ptr [rax+48h]
0x1800633e2  movaps  [rbp+4E40h+var_4090], xmm0
0x1800633e9  movups  xmm1, xmmword ptr [rax+58h]
0x1800633ed  movaps  [rbp+4E40h+var_4080], xmm1
0x1800633f4  movups  xmm0, xmmword ptr [rax+68h]
0x1800633f8  movaps  [rbp+4E40h+var_4070], xmm0
0x1800633ff  movups  xmm1, xmmword ptr [rax+78h]
0x180063403  movaps  [rbp+4E40h+var_4060], xmm1
0x18006340a  mov     dword ptr [rsp+4F40h+var_4ED0], 9
0x180063412  lea     r8, [rsp+4F40h+var_4ED0]
0x180063417  mov     rdx, rbx
0x18006341a  lea     rcx, [rbp+4E40h+var_40D0]
0x180063421  call    ??$From@H@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBH@Z; Napi::Value::From<int>(napi_env__ *,int const &)
0x180063426  movups  xmm0, xmmword ptr [rax]
0x180063429  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x180063432  xorps   xmm1, xmm1
0x180063435  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x18006343e  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063447  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x18006344f  lea     rax, aProtocolVersio; "PROTOCOL_VERSION"
0x180063456  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x18006345b  psrldq  xmm0, 8
0x180063460  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063466  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x18006346e  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063473  movaps  [rbp+4E40h+var_4050], xmm0
0x18006347a  movaps  [rbp+4E40h+var_4040], xmm1
0x180063481  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x180063486  movaps  [rbp+4E40h+var_4030], xmm0
0x18006348d  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x180063492  movaps  [rbp+4E40h+var_4020], xmm1
0x180063499  lea     r8, [rbp+4E40h+pExceptionObject+8]
0x1800634a0  mov     rdx, rbx
0x1800634a3  lea     rcx, [rbp+4E40h+var_40C0]
0x1800634aa  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800634af  movups  xmm0, xmmword ptr [rax]
0x1800634b2  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800634bb  xorps   xmm1, xmm1
0x1800634be  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x1800634c7  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x1800634d0  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x1800634d8  lea     rax, aCapsLimitsMaxT; "CAPS_LIMITS_MAX_TEXTURE_SIZE"
0x1800634df  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x1800634e4  psrldq  xmm0, 8
0x1800634e9  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x1800634ef  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x1800634f7  movaps  xmm0, [rsp+4F40h+var_4F10]
0x1800634fc  movaps  [rbp+4E40h+var_4010], xmm0
0x180063503  movaps  [rbp+4E40h+var_4000], xmm1
0x18006350a  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x18006350f  movaps  [rbp+4E40h+var_3FF0], xmm0
0x180063516  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x18006351b  movaps  [rbp+4E40h+var_3FE0], xmm1
0x180063522  lea     r8, [rbp+4E40h+pExceptionObject+0Ch]
0x180063529  mov     rdx, rbx
0x18006352c  lea     rcx, [rbp+4E40h+var_4E70]
0x180063530  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x180063535  movups  xmm0, xmmword ptr [rax]
0x180063538  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x180063541  xorps   xmm1, xmm1
0x180063544  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x18006354d  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063556  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x18006355e  lea     rax, aCapsLimitsMaxT_0; "CAPS_LIMITS_MAX_TEXTURE_LAYERS"
0x180063565  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x18006356a  psrldq  xmm0, 8
0x18006356f  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063575  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x18006357d  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063582  movaps  [rbp+4E40h+var_3FD0], xmm0
0x180063589  movaps  [rbp+4E40h+var_3FC0], xmm1
0x180063590  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x180063595  movaps  [rbp+4E40h+var_3FB0], xmm0
0x18006359c  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x1800635a1  movaps  [rbp+4E40h+var_3FA0], xmm1
0x1800635a8  lea     r8, dword_18054B794
0x1800635af  mov     rdx, rbx
0x1800635b2  lea     rcx, [rbp+4E40h+var_4E60]
0x1800635b6  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800635bb  movups  xmm0, xmmword ptr [rax]
0x1800635be  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800635c7  xorps   xmm1, xmm1
0x1800635ca  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x1800635d3  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x1800635dc  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x1800635e4  lea     rax, aTextureNearest_4; "TEXTURE_NEAREST_NEAREST"
0x1800635eb  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x1800635f0  psrldq  xmm0, 8
0x1800635f5  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x1800635fb  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x180063603  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063608  movaps  [rbp+4E40h+var_3F90], xmm0
0x18006360f  movaps  [rbp+4E40h+var_3F80], xmm1
0x180063616  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x18006361b  movaps  [rbp+4E40h+var_3F70], xmm0
0x180063622  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x180063627  movaps  [rbp+4E40h+var_3F60], xmm1
0x18006362e  lea     r8, byte_18054B798
0x180063635  mov     rdx, rbx
0x180063638  lea     rcx, [rbp+4E40h+var_4E50]
0x18006363c  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x180063641  movups  xmm0, xmmword ptr [rax]
0x180063644  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x18006364d  xorps   xmm1, xmm1
0x180063650  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x180063659  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063662  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x18006366a  lea     rax, aTextureLinearL_1; "TEXTURE_LINEAR_LINEAR"
0x180063671  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x180063676  psrldq  xmm0, 8
0x18006367b  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063681  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x180063689  movaps  xmm0, [rsp+4F40h+var_4F10]
0x18006368e  movaps  [rbp+4E40h+var_3F50], xmm0
0x180063695  movaps  [rbp+4E40h+var_3F40], xmm1
0x18006369c  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x1800636a1  movaps  [rbp+4E40h+var_3F30], xmm0
0x1800636a8  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x1800636ad  movaps  [rbp+4E40h+var_3F20], xmm1
0x1800636b4  lea     r8, dword_18054B79C
0x1800636bb  mov     rdx, rbx
0x1800636be  lea     rcx, [rbp+4E40h+var_4E40]
0x1800636c2  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800636c7  movups  xmm0, xmmword ptr [rax]
0x1800636ca  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800636d3  xorps   xmm1, xmm1
0x1800636d6  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x1800636df  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x1800636e8  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x1800636f0  lea     rax, aTextureLinearL_0; "TEXTURE_LINEAR_LINEAR_MIPLINEAR"
0x1800636f7  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x1800636fc  psrldq  xmm0, 8
0x180063701  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063707  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x18006370f  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063714  movaps  [rbp+4E40h+var_3F10], xmm0
0x18006371b  movaps  [rbp+4E40h+var_3F00], xmm1
0x180063722  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x180063727  movaps  [rbp+4E40h+var_3EF0], xmm0
0x18006372e  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x180063733  movaps  [rbp+4E40h+var_3EE0], xmm1
0x18006373a  lea     r8, byte_18054B7A0
0x180063741  mov     rdx, rbx
0x180063744  lea     rcx, [rbp+4E40h+var_4E30]
0x180063748  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x18006374d  movups  xmm0, xmmword ptr [rax]
0x180063750  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x180063759  xorps   xmm1, xmm1
0x18006375c  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x180063765  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x18006376e  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x180063776  lea     rax, aTextureNearest_2; "TEXTURE_NEAREST_NEAREST_MIPNEAREST"
0x18006377d  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x180063782  psrldq  xmm0, 8
0x180063787  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x18006378d  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x180063795  movaps  xmm0, [rsp+4F40h+var_4F10]
0x18006379a  movaps  [rbp+4E40h+var_3ED0], xmm0
0x1800637a1  movaps  [rbp+4E40h+var_3EC0], xmm1
0x1800637a8  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x1800637ad  movaps  [rbp+4E40h+var_3EB0], xmm0
0x1800637b4  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x1800637b9  movaps  [rbp+4E40h+var_3EA0], xmm1
0x1800637c0  lea     r8, dword_18054B7A4
0x1800637c7  mov     rdx, rbx
0x1800637ca  lea     rcx, [rbp+4E40h+var_4E20]
0x1800637ce  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800637d3  movups  xmm0, xmmword ptr [rax]
0x1800637d6  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800637df  xorps   xmm1, xmm1
0x1800637e2  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x1800637eb  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x1800637f4  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x1800637fc  lea     rax, aTextureNearest_1; "TEXTURE_NEAREST_LINEAR_MIPNEAREST"
0x180063803  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x180063808  psrldq  xmm0, 8
0x18006380d  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063813  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x18006381b  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063820  movaps  [rbp+4E40h+var_3E90], xmm0
0x180063827  movaps  [rbp+4E40h+var_3E80], xmm1
0x18006382e  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x180063833  movaps  [rbp+4E40h+var_3E70], xmm0
0x18006383a  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x18006383f  movaps  [rbp+4E40h+var_3E60], xmm1
0x180063846  lea     r8, byte_18054B7A8
0x18006384d  mov     rdx, rbx
0x180063850  lea     rcx, [rbp+4E40h+var_4E10]
0x180063854  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x180063859  movups  xmm0, xmmword ptr [rax]
0x18006385c  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x180063865  xorps   xmm1, xmm1
0x180063868  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x180063871  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x18006387a  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x180063882  lea     rax, aTextureNearest; "TEXTURE_NEAREST_LINEAR_MIPLINEAR"
0x180063889  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x18006388e  psrldq  xmm0, 8
0x180063893  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063899  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x1800638a1  movaps  xmm0, [rsp+4F40h+var_4F10]
0x1800638a6  movaps  [rbp+4E40h+var_3E50], xmm0
0x1800638ad  movaps  [rbp+4E40h+var_3E40], xmm1
0x1800638b4  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x1800638b9  movaps  [rbp+4E40h+var_3E30], xmm0
0x1800638c0  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x1800638c5  movaps  [rbp+4E40h+var_3E20], xmm1
0x1800638cc  lea     r8, dword_18054B7AC
0x1800638d3  mov     rdx, rbx
0x1800638d6  lea     rcx, [rbp+4E40h+var_4E00]
0x1800638da  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800638df  movups  xmm0, xmmword ptr [rax]
0x1800638e2  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800638eb  xorps   xmm1, xmm1
0x1800638ee  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x1800638f7  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063900  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x180063908  lea     rax, aTextureNearest_0; "TEXTURE_NEAREST_LINEAR"
0x18006390f  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x180063914  psrldq  xmm0, 8
0x180063919  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x18006391f  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x180063927  movaps  xmm0, [rsp+4F40h+var_4F10]
0x18006392c  movaps  [rbp+4E40h+var_3E10], xmm0
0x180063933  movaps  [rbp+4E40h+var_3E00], xmm1
0x18006393a  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x18006393f  movaps  [rbp+4E40h+var_3DF0], xmm0
0x180063946  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x18006394b  movaps  [rbp+4E40h+var_3DE0], xmm1
0x180063952  lea     r8, byte_18054B7B0
0x180063959  mov     rdx, rbx
0x18006395c  lea     rcx, [rbp+4E40h+var_4DF0]
0x180063960  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x180063965  movups  xmm0, xmmword ptr [rax]
0x180063968  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x180063971  xorps   xmm1, xmm1
0x180063974  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x18006397d  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063986  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x18006398e  lea     rax, aTextureNearest_3; "TEXTURE_NEAREST_NEAREST_MIPLINEAR"
0x180063995  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x18006399a  psrldq  xmm0, 8
0x18006399f  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x1800639a5  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x1800639ad  movaps  xmm0, [rsp+4F40h+var_4F10]
0x1800639b2  movaps  [rbp+4E40h+var_3DD0], xmm0
0x1800639b9  movaps  [rbp+4E40h+var_3DC0], xmm1
0x1800639c0  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x1800639c5  movaps  [rbp+4E40h+var_3DB0], xmm0
0x1800639cc  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x1800639d1  movaps  [rbp+4E40h+var_3DA0], xmm1
0x1800639d8  lea     r8, dword_18054B7B4
0x1800639df  mov     rdx, rbx
0x1800639e2  lea     rcx, [rbp+4E40h+var_4DE0]
0x1800639e6  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
0x1800639eb  movups  xmm0, xmmword ptr [rax]
0x1800639ee  mov     qword ptr [rsp+4F40h+var_4F10+8], 0
0x1800639f7  xorps   xmm1, xmm1
0x1800639fa  mov     qword ptr [rsp+4F40h+var_4EF0], 0
0x180063a03  mov     qword ptr [rsp+4F40h+var_4EE0+4], 0
0x180063a0c  mov     dword ptr [rsp+4F40h+var_4EE0+0Ch], 0
0x180063a14  lea     rax, aTextureLinearN_0; "TEXTURE_LINEAR_NEAREST_MIPNEAREST"
0x180063a1b  mov     qword ptr [rsp+4F40h+var_4F10], rax
0x180063a20  psrldq  xmm0, 8
0x180063a25  movq    qword ptr [rsp+4F40h+var_4EF0+8], xmm0
0x180063a2b  mov     dword ptr [rsp+4F40h+var_4EE0], 400h
0x180063a33  movaps  xmm0, [rsp+4F40h+var_4F10]
0x180063a38  movaps  [rbp+4E40h+var_3D90], xmm0
0x180063a3f  movaps  [rbp+4E40h+var_3D80], xmm1
0x180063a46  movaps  xmm0, [rsp+4F40h+var_4EF0]
0x180063a4b  movaps  [rbp+4E40h+var_3D70], xmm0
0x180063a52  movaps  xmm1, [rsp+4F40h+var_4EE0]
0x180063a57  movaps  [rbp+4E40h+var_3D60], xmm1
0x180063a5e  lea     r8, byte_18054B7B8
0x180063a65  mov     rdx, rbx
0x180063a68  lea     rcx, [rbp+4E40h+var_4DD0]
0x180063a6c  call    ??$From@I@Value@Napi@@SA?AV01@PEAUnapi_env__@@AEBI@Z; Napi::Value::From<uint>(napi_env__ *,uint const &)
  ... truncated ...
```
