# FiringAgent::GetSubscriptions(_GUID const &,ushort *,ushort *,int *,IEventObjectCollection * *)

- ea: `0x180003df0`
- end: `0x180005ce9`
- name: `?GetSubscriptions@FiringAgent@@UEAAJAEBU_GUID@@PEAG1PEAHPEAPEAUIEventObjectCollection@@@Z`
- size: `7929`
- prototype: `int(FiringAgent *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned __int16 *, int *, struct IEventObjectCollection **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003d54`
- `0x180003df0`
- `0x180005cf0`
- `0x180006194`
- `0x180008938`
- `0x18000c910`
- `0x180012f50`
- `0x18001f494`
- `0x180024850`
- `0x18002fb30`
- `0x18003ecb0`
- `0x1800434c6`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000458b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000488d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000458b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800046ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000488d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005c55`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003ed0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004fba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800058e6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003ed0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180004fba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800058e6`

## string_xrefs

- `0x180004b37`: `(((EventClassID=`
- `0x180004ef7`: `)) | (EventClassID=null & PublisherID=null & InterfaceID=(`
- `0x180004963`: `com\complus\src\events\tier1\enum.cpp`
- `0x180004a87`: `com\complus\src\events\tier1\enum.cpp`
- `0x180004983`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800049a5`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800049c5`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800049e5`: `com\complus\src\events\tier1\agent.cpp`
- `0x180004a05`: `com\complus\src\events\tier1\agent.cpp`
- `0x180004a25`: `com\complus\src\events\tier1\agent.cpp`
- `0x180004a45`: `com\complus\src\events\tier1\agent.cpp`
- `0x180004a65`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005324`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005347`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005367`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005387`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800053a7`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800053ca`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800053ea`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800059ce`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005a06`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005aa1`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005ad9`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005b14`: `com\complus\src\events\tier1\agent.cpp`
- `0x180005ba7`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
__int64 __fastcall FiringAgent::GetSubscriptions(
        FiringAgent *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        struct IEventObjectCollection **a6)
{
  FiringAgent *v8; // r15
  unsigned __int16 *v9; // r14
  __int64 v10; // rsi
  __int64 v11; // r9
  _QWORD *i; // rax
  __int64 v13; // rcx
  __int64 v14; // r10
  unsigned __int64 v15; // rcx
  unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // rax
  int v18; // r11d
  bool v19; // zf
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  OLECHAR *v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int16 *v24; // r9
  OLECHAR v25; // ax
  int k; // ebx
  unsigned __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  int v29; // r11d
  bool v30; // zf
  unsigned __int64 v31; // r8
  __int64 v32; // rcx
  const wchar_t *v33; // rdx
  unsigned __int64 v34; // rax
  unsigned __int16 *v35; // r8
  __int64 v36; // r10
  wchar_t v37; // r9
  unsigned __int64 v38; // rcx
  unsigned __int16 *v39; // rax
  int v40; // r11d
  bool v41; // zf
  unsigned __int64 v42; // r8
  __int64 v43; // rcx
  const wchar_t *v44; // rdx
  unsigned __int64 v45; // rax
  unsigned __int16 *v46; // r8
  __int64 v47; // r10
  wchar_t v48; // r9
  unsigned __int64 v49; // rcx
  unsigned __int16 *v50; // rax
  int v51; // r10d
  bool v52; // zf
  unsigned __int64 v53; // rdx
  __int64 v54; // rcx
  unsigned __int64 v55; // rax
  unsigned __int16 *v56; // rdx
  __int64 v57; // r9
  unsigned __int16 v58; // r8
  unsigned __int64 v59; // rax
  unsigned __int16 *v60; // rcx
  int v61; // r9d
  bool v62; // zf
  unsigned __int64 v63; // rcx
  const wchar_t *v64; // rax
  __int64 v65; // rsi
  unsigned __int16 *v66; // rcx
  __int64 v67; // r8
  wchar_t v68; // dx
  __int64 v69; // r13
  __int64 v70; // rax
  __int64 v71; // rbx
  int v72; // esi
  int v73; // edi
  LPVOID v74; // rax
  _QWORD *v75; // rdx
  int v76; // r12d
  EventObjectCollection *v77; // rbx
  FiringAgent::AutoUpdateListElement *v78; // r13
  FiringAgent::AutoUpdateListElement *v79; // rax
  char *v80; // rcx
  __int64 v81; // rdi
  _QWORD *v82; // rax
  int v83; // r9d
  _QWORD *m; // r8
  _QWORD *v85; // rcx
  int v86; // eax
  _QWORD *v87; // rax
  LPVOID v88; // rax
  int v89; // eax
  __int64 v90; // r9
  unsigned __int64 v91; // rsi
  unsigned __int64 v92; // rax
  unsigned __int16 *v93; // rcx
  int v94; // r11d
  bool v95; // zf
  unsigned __int64 v96; // rcx
  __int64 v97; // rdx
  const wchar_t *v98; // r8
  unsigned __int64 v99; // rax
  unsigned __int16 *v100; // r9
  __int64 v101; // r10
  wchar_t v102; // cx
  _WORD *v103; // r10
  unsigned __int64 v104; // rcx
  unsigned __int16 *v105; // rax
  int v106; // r11d
  bool v107; // zf
  unsigned __int64 v108; // rcx
  __int64 v109; // rdx
  unsigned __int64 v110; // rax
  unsigned __int16 *v111; // r8
  unsigned __int16 v112; // cx
  unsigned __int64 v113; // rcx
  unsigned __int16 *v114; // rax
  int v115; // r11d
  bool v116; // zf
  unsigned __int64 v117; // rdx
  __int64 v118; // rcx
  const wchar_t *v119; // r8
  unsigned __int64 v120; // rax
  unsigned __int16 *v121; // r9
  __int64 v122; // r10
  wchar_t v123; // dx
  int j; // ebx
  unsigned __int64 v125; // rcx
  unsigned __int16 *v126; // r9
  unsigned __int16 *v127; // rax
  int v128; // r11d
  bool v129; // zf
  unsigned __int64 v130; // rcx
  __int64 v131; // rdx
  const wchar_t *v132; // r8
  unsigned __int64 v133; // rax
  unsigned __int16 *v134; // r9
  __int64 v135; // r10
  wchar_t v136; // cx
  __int64 v137; // r10
  unsigned __int64 v138; // rcx
  unsigned __int16 *v139; // r9
  unsigned __int16 *v140; // rax
  int v141; // r11d
  bool v142; // zf
  unsigned __int64 v143; // rax
  __int64 v144; // rdx
  const unsigned __int16 *v145; // r8
  unsigned __int64 v146; // rcx
  unsigned __int16 *v147; // r9
  unsigned __int16 v148; // ax
  unsigned __int64 v149; // rcx
  unsigned __int16 *v150; // r9
  unsigned __int16 *v151; // rax
  int v152; // r11d
  bool v153; // zf
  unsigned __int64 v154; // rax
  __int64 v155; // rdx
  OLECHAR *v156; // r8
  unsigned __int64 v157; // rcx
  unsigned __int16 *v158; // r9
  OLECHAR v159; // ax
  unsigned __int64 v160; // rdi
  __int64 v161; // rcx
  unsigned __int64 v162; // rcx
  void *v163; // rsp
  void *v164; // rsp
  unsigned __int64 v165; // r10
  unsigned __int64 v166; // rcx
  unsigned __int16 *v167; // rax
  int v168; // r11d
  bool v169; // zf
  unsigned __int64 v170; // rdx
  __int64 v171; // rax
  unsigned __int16 *v172; // rcx
  __int64 v173; // r10
  unsigned __int16 *v174; // rdx
  unsigned __int16 v175; // r8
  int v176; // eax
  unsigned __int64 v177; // rcx
  __int64 v178; // r9
  unsigned __int64 v179; // rcx
  void *v180; // rsp
  void *v181; // rsp
  _QWORD *v182; // r8
  __int64 v183; // rdx
  int v184; // eax
  __int64 v185; // rdx
  const unsigned __int16 *v186; // rcx
  __int64 v187; // r8
  __int64 v188; // rax
  __int64 v189; // rcx
  __int64 v190; // r10
  unsigned int v191; // r9d
  unsigned __int16 *v192; // rax
  int v193; // ecx
  int v194; // edx
  __int64 v195; // rcx
  int v196; // r14d
  unsigned __int64 v197; // rcx
  unsigned int v198; // edx
  __int64 v200; // rsi
  __int64 v201; // rax
  __int64 *v202; // rbx
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rax
  __int64 v208; // rax
  GUID *v209; // rcx
  __int64 v210; // rbx
  __int64 v211; // r9
  unsigned __int64 v212; // r9
  void *v213; // rsp
  void *v214; // rsp
  int v215; // [rsp+50h] [rbp+0h] BYREF
  unsigned __int16 v216[2]; // [rsp+54h] [rbp+4h] BYREF
  unsigned __int16 *v217; // [rsp+58h] [rbp+8h] BYREF
  int v218; // [rsp+60h] [rbp+10h] BYREF
  FiringAgent *v219; // [rsp+68h] [rbp+18h]
  int v220; // [rsp+70h] [rbp+20h]
  int v221; // [rsp+74h] [rbp+24h] BYREF
  BOOL v222; // [rsp+7Ch] [rbp+2Ch]
  int v223; // [rsp+80h] [rbp+30h]
  int v224; // [rsp+84h] [rbp+34h]
  int v225; // [rsp+88h] [rbp+38h]
  int v226; // [rsp+90h] [rbp+40h]
  unsigned __int64 v227; // [rsp+98h] [rbp+48h]
  unsigned __int64 v228; // [rsp+A0h] [rbp+50h]
  unsigned __int64 v229; // [rsp+A8h] [rbp+58h]
  unsigned __int64 v230; // [rsp+B0h] [rbp+60h]
  unsigned __int64 v231; // [rsp+B8h] [rbp+68h]
  unsigned __int64 v232; // [rsp+C0h] [rbp+70h]
  unsigned __int64 v233; // [rsp+C8h] [rbp+78h]
  unsigned __int64 v234; // [rsp+D0h] [rbp+80h]
  unsigned __int64 v235; // [rsp+D8h] [rbp+88h]
  unsigned __int64 v236; // [rsp+E0h] [rbp+90h]
  unsigned __int64 v237; // [rsp+E8h] [rbp+98h]
  unsigned __int64 v238; // [rsp+F0h] [rbp+A0h]
  unsigned __int16 *v239; // [rsp+F8h] [rbp+A8h]
  __int64 v240; // [rsp+100h] [rbp+B0h]
  unsigned __int16 *v241; // [rsp+108h] [rbp+B8h]
  __int64 v242; // [rsp+110h] [rbp+C0h]
  unsigned __int16 *v243; // [rsp+118h] [rbp+C8h]
  __int64 v244; // [rsp+120h] [rbp+D0h]
  unsigned __int16 *v245; // [rsp+128h] [rbp+D8h]
  __int64 v246; // [rsp+130h] [rbp+E0h]
  unsigned __int16 *v247; // [rsp+138h] [rbp+E8h]
  __int64 v248; // [rsp+140h] [rbp+F0h]
  unsigned __int16 *v249; // [rsp+148h] [rbp+F8h]
  __int64 v250; // [rsp+150h] [rbp+100h]
  unsigned __int16 *v251; // [rsp+158h] [rbp+108h]
  __int64 v252; // [rsp+160h] [rbp+110h]
  unsigned __int16 *v253; // [rsp+168h] [rbp+118h]
  __int64 v254; // [rsp+170h] [rbp+120h]
  unsigned __int16 *v255; // [rsp+178h] [rbp+128h]
  __int64 v256; // [rsp+180h] [rbp+130h]
  unsigned __int16 *v257; // [rsp+188h] [rbp+138h]
  __int64 v258; // [rsp+190h] [rbp+140h]
  unsigned __int16 *v259; // [rsp+198h] [rbp+148h]
  __int64 v260; // [rsp+1A0h] [rbp+150h]
  unsigned __int16 *v261; // [rsp+1A8h] [rbp+158h]
  __int64 v262; // [rsp+1B0h] [rbp+160h]
  __int64 v263; // [rsp+1B8h] [rbp+168h]
  _QWORD *v264; // [rsp+1C0h] [rbp+170h]
  int *v265; // [rsp+1C8h] [rbp+178h]
  unsigned __int16 *v266; // [rsp+1D0h] [rbp+180h]
  unsigned __int64 v267; // [rsp+1D8h] [rbp+188h]
  unsigned __int16 *v268; // [rsp+1E0h] [rbp+190h]
  __int64 v269; // [rsp+1E8h] [rbp+198h]
  __int64 v270; // [rsp+1F0h] [rbp+1A0h]
  unsigned __int16 *v271; // [rsp+1F8h] [rbp+1A8h]
  unsigned __int64 v272; // [rsp+200h] [rbp+1B0h]
  const wchar_t *v273; // [rsp+208h] [rbp+1B8h]
  __int64 v274; // [rsp+210h] [rbp+1C0h]
  __int64 v275; // [rsp+218h] [rbp+1C8h]
  unsigned __int16 *v276; // [rsp+220h] [rbp+1D0h]
  unsigned __int64 v277; // [rsp+228h] [rbp+1D8h]
  _WORD *v278; // [rsp+230h] [rbp+1E0h]
  __int64 v279; // [rsp+238h] [rbp+1E8h]
  __int64 v280; // [rsp+240h] [rbp+1F0h]
  unsigned __int16 *v281; // [rsp+248h] [rbp+1F8h]
  unsigned __int64 v282; // [rsp+250h] [rbp+200h]
  const wchar_t *v283; // [rsp+258h] [rbp+208h]
  __int64 v284; // [rsp+260h] [rbp+210h]
  __int64 v285; // [rsp+268h] [rbp+218h]
  unsigned __int16 *v286; // [rsp+270h] [rbp+220h]
  unsigned __int64 v287; // [rsp+278h] [rbp+228h]
  const unsigned __int16 *v288; // [rsp+280h] [rbp+230h]
  __int64 v289; // [rsp+288h] [rbp+238h]
  __int64 v290; // [rsp+290h] [rbp+240h]
  unsigned __int16 *v291; // [rsp+298h] [rbp+248h]
  unsigned __int64 v292; // [rsp+2A0h] [rbp+250h]
  OLECHAR *v293; // [rsp+2A8h] [rbp+258h]
  __int64 v294; // [rsp+2B0h] [rbp+260h]
  __int64 v295; // [rsp+2B8h] [rbp+268h]
  unsigned __int16 *v296; // [rsp+2C0h] [rbp+270h]
  unsigned __int64 v297; // [rsp+2C8h] [rbp+278h]
  const wchar_t *v298; // [rsp+2D0h] [rbp+280h]
  __int64 v299; // [rsp+2D8h] [rbp+288h]
  __int64 v300; // [rsp+2E0h] [rbp+290h]
  unsigned __int16 *v301; // [rsp+2E8h] [rbp+298h]
  unsigned __int64 v302; // [rsp+2F0h] [rbp+2A0h]
  OLECHAR *v303; // [rsp+2F8h] [rbp+2A8h]
  __int64 v304; // [rsp+300h] [rbp+2B0h]
  __int64 v305; // [rsp+308h] [rbp+2B8h]
  unsigned __int16 *v306; // [rsp+310h] [rbp+2C0h]
  unsigned __int64 v307; // [rsp+318h] [rbp+2C8h]
  const wchar_t *v308; // [rsp+320h] [rbp+2D0h]
  __int64 v309; // [rsp+328h] [rbp+2D8h]
  __int64 v310; // [rsp+330h] [rbp+2E0h]
  unsigned __int16 *v311; // [rsp+338h] [rbp+2E8h]
  unsigned __int64 v312; // [rsp+340h] [rbp+2F0h]
  const wchar_t *v313; // [rsp+348h] [rbp+2F8h]
  __int64 v314; // [rsp+350h] [rbp+300h]
  __int64 v315; // [rsp+358h] [rbp+308h]
  unsigned __int16 *v316; // [rsp+360h] [rbp+310h]
  unsigned __int64 v317; // [rsp+368h] [rbp+318h]
  unsigned __int16 *v318; // [rsp+370h] [rbp+320h]
  __int64 v319; // [rsp+378h] [rbp+328h]
  __int64 v320; // [rsp+380h] [rbp+330h]
  unsigned __int16 *v321; // [rsp+388h] [rbp+338h]
  unsigned __int64 v322; // [rsp+390h] [rbp+340h]
  const wchar_t *v323; // [rsp+398h] [rbp+348h]
  __int64 v324; // [rsp+3A0h] [rbp+350h]
  __int64 v325; // [rsp+3A8h] [rbp+358h]
  unsigned __int16 *v326; // [rsp+3B0h] [rbp+360h]
  int *v327; // [rsp+3B8h] [rbp+368h]
  _QWORD *v328; // [rsp+3C0h] [rbp+370h]
  FiringAgent::AutoUpdateListElement *v329; // [rsp+3C8h] [rbp+378h]
  struct IEventObjectCollection **v330; // [rsp+3D0h] [rbp+380h]
  __int64 v331; // [rsp+3D8h] [rbp+388h]
  unsigned __int64 v332; // [rsp+3E0h] [rbp+390h]
  __int64 v333; // [rsp+3E8h] [rbp+398h]
  __int64 v334; // [rsp+3F0h] [rbp+3A0h]
  FiringAgent::AutoUpdateListElement *v335; // [rsp+3F8h] [rbp+3A8h]
  OLECHAR sz[40]; // [rsp+400h] [rbp+3B0h] BYREF
  unsigned __int16 v337[144]; // [rsp+450h] [rbp+400h] BYREF

  v8 = this;
  v219 = this;
  v327 = a5;
  v330 = a6;
  v215 = 0;
  v263 = 0;
  if ( !a6 )
    return 2147500035LL;
  v9 = a4;
  v10 = 0;
  v222 = 1;
  v329 = 0;
  *a6 = 0;
  v11 = *((_QWORD *)this + 7);
  if ( v11 )
  {
    for ( i = *(_QWORD **)(v11 + 8LL * (a2->Data1 % *((_DWORD *)this + 16))); i; i = (_QWORD *)*i )
    {
      v13 = *(_QWORD *)((char *)i + 12) - *(_QWORD *)&a2->Data1;
      if ( !v13 )
        v13 = *(_QWORD *)((char *)i + 20) - *(_QWORD *)a2->Data4;
      if ( !v13 )
        goto LABEL_395;
    }
  }
  i = 0;
LABEL_395:
  v202 = 0;
  if ( i )
    v202 = (__int64 *)i[4];
  if ( !v202 )
    return 2147500034LL;
  v203 = *((_QWORD *)v8 + 29) - *(_QWORD *)&CLSID_EventObjectChange.Data1;
  if ( !v203 )
    v203 = *((_QWORD *)v8 + 30) - *(_QWORD *)CLSID_EventObjectChange.Data4;
  if ( !v203 )
    goto LABEL_378;
  v204 = *((_QWORD *)v8 + 29) - *(_QWORD *)&CLSID_EventObjectChange2.Data1;
  if ( !v204 )
    v204 = *((_QWORD *)v8 + 30) - *(_QWORD *)CLSID_EventObjectChange2.Data4;
  if ( v204 )
  {
    v205 = *((_QWORD *)v8 + 27) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v205 )
      v205 = *((_QWORD *)v8 + 28) - *(_QWORD *)GUID_NULL.Data4;
    v222 = v205 != 0;
    v206 = *((_QWORD *)v8 + 27) - *(_QWORD *)&GUID_DefaultAppPartition.Data1;
    if ( !v206 )
      v206 = *((_QWORD *)v8 + 28) - *(_QWORD *)GUID_DefaultAppPartition.Data4;
    if ( !v206 )
      goto LABEL_412;
    v207 = *((_QWORD *)v8 + 27) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v207 )
      v207 = *((_QWORD *)v8 + 28) - *(_QWORD *)GUID_NULL.Data4;
    if ( v207 )
    {
      v218 = 1;
      v200 = 71;
      v215 = StringCchPrintfW(v337, 0x8Fu, L"(EventClassPartitionID='%s') AND ", *((_QWORD *)v8 + 25));
      if ( v215 < 0 )
        return (unsigned int)v215;
    }
    else
    {
LABEL_412:
      memset_0(sz, 0, 0x4Eu);
      v218 = 0;
      v208 = *((_QWORD *)v8 + 27) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v208 )
        v208 = *((_QWORD *)v8 + 28) - *(_QWORD *)GUID_NULL.Data4;
      v209 = &GUID_DefaultAppPartition;
      if ( v208 )
        v209 = &GUID_NULL;
      StringFromGUID2(v209, sz, 39);
      v200 = 142;
      v215 = StringCchPrintfW(
               v337,
               0x8Fu,
               L"((EventClassPartitionID='%s') OR (EventClassPartitionID='%s')) AND ",
               *((_QWORD *)v8 + 25),
               sz);
      if ( v215 < 0 )
        return (unsigned int)v215;
    }
    v201 = -1;
    do
      ++v201;
    while ( v337[v201] );
    v265 = (int *)v201;
    v263 = (int)v201;
    v331 = (int)v201;
    v10 = 2 * v200;
    v9 = a4;
  }
  else
  {
LABEL_378:
    v218 = 0;
  }
  if ( a4 && *a4 )
  {
    if ( v10 )
    {
      v210 = v10 + 2LL * (int)safe_lstrlenW(a4);
      v211 = v210 + 21;
      if ( v210 + 21 <= (unsigned __int64)(v210 + 6) )
        v211 = 0xFFFFFFFFFFFFFF0LL;
      v212 = v211 & 0xFFFFFFFFFFFFFFF0uLL;
      v213 = alloca(v212);
      v214 = alloca(v212);
      v9 = v216;
      v326 = v216;
      v216[0] = 0;
      v215 = StringCbCatW(v216, v210 + 2, v337);
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15CCu, 0x12u, v215);
      v215 = StringCbCatW(v216, v210 + 2, a4);
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15CEu, 0x12u, v215);
    }
    goto LABEL_128;
  }
  if ( !a3 )
  {
LABEL_381:
    v195 = 0xFFFFFFFFLL;
    v196 = *((_DWORD *)v202 + 12) + 1;
    if ( v196 >= 0 )
      v195 = (unsigned int)v196;
    v215 = (v196 >> 31) & 0x80070216;
    if ( v196 >> 31 == -1 )
      return (unsigned int)v215;
    v197 = 8 * v195;
    v332 = v197;
    v198 = v197;
    if ( v197 > 0xFFFFFFFF )
      v198 = -1;
    v176 = 0;
    if ( v197 > 0xFFFFFFFF )
      v176 = -2147024362;
    v215 = v176;
    if ( v176 < 0 )
      return (unsigned int)v215;
    v177 = v198 + 15LL;
    v178 = 0xFFFFFFFFFFFFFF0LL;
    if ( v177 <= v198 )
      v177 = 0xFFFFFFFFFFFFFF0LL;
    v179 = v177 & 0xFFFFFFFFFFFFFFF0uLL;
    v180 = alloca(v179);
    v181 = alloca(v179);
    v182 = (_QWORD *)v202[4];
    v183 = 0;
    v224 = 0;
    while ( v182 )
    {
      if ( (unsigned int)v183 >= v196 )
        goto LABEL_370;
      v189 = v182[2];
      v182 = (_QWORD *)*v182;
      *(_QWORD *)&v216[4 * v183 - 2] = v189 + 8;
      v183 = (unsigned int)(v183 + 1);
      v224 = v183;
    }
    if ( (unsigned int)v183 < v196 )
    {
      *(_QWORD *)&v216[4 * v183 - 2] = v202 + 1;
      v184 = 0;
      goto LABEL_361;
    }
LABEL_370:
    v184 = -2147024809;
LABEL_361:
    v215 = v184;
    if ( v184 < 0 )
      return (unsigned int)v215;
    v185 = 56;
    v186 = (const unsigned __int16 *)*((_QWORD *)v219 + 13);
    if ( v186 )
      v185 = (int)safe_lstrlenW(v186) + 74LL;
    v187 = 86LL * v196 + v185 + 85;
    if ( a3 )
    {
      v188 = -1;
      do
        ++v188;
      while ( a3[v188] );
      v333 = v188;
      v187 += (int)v188 + 26LL;
    }
    v160 = v10 + 2 * v187;
    v161 = v160 + 19;
    if ( v160 + 19 <= v160 + 4 )
      v161 = v178;
    v162 = v161 & 0xFFFFFFFFFFFFFFF0uLL;
    v163 = alloca(v162);
    v164 = alloca(v162);
    v265 = &v215;
    v217 = v216;
    v326 = v216;
    v90 = 0;
    v216[0] = 0;
    v220 = 0;
    v69 = 2147483646;
    if ( v10 )
    {
      v227 = 0;
      v165 = v160 >> 1;
      if ( (v160 >> 1) - 1 > 0x7FFFFFFE )
      {
        v168 = -2147024809;
        v170 = 0;
        v227 = 0;
      }
      else
      {
        v166 = v160 >> 1;
        v267 = v160 >> 1;
        v167 = v216;
        v266 = v216;
        v168 = 0;
        while ( 1 )
        {
          v169 = v166 == 0;
          if ( !v166 )
            break;
          if ( !*v167 )
          {
            v169 = v166 == 0;
            break;
          }
          v266 = ++v167;
          v267 = --v166;
        }
        if ( v169 )
          v168 = -2147024809;
        if ( v168 < 0 )
          v227 = 0;
        else
          v227 = v165 - v166;
        v170 = v227;
      }
      if ( v168 >= 0 )
      {
        v171 = 2147483646;
        v270 = 2147483646;
        v172 = v337;
        v268 = v337;
        v173 = v165 - v170;
        v269 = v173;
        v174 = &v216[v170];
        v239 = v174;
        v168 = 0;
        v240 = 0;
        while ( v173 )
        {
          if ( !v171 )
            goto LABEL_185;
          v175 = *v172;
          if ( !*v172 )
            goto LABEL_185;
          v268 = ++v172;
          *v174++ = v175;
          v239 = v174;
          v269 = --v173;
          v270 = --v171;
          v240 = ++v90;
        }
        v239 = --v174;
        v240 = v90 - 1;
        v168 = -2147024774;
LABEL_185:
        v90 = 0;
        *v174 = 0;
      }
      v215 = v168;
      if ( v168 < 0 )
      {
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1583u, 0x12u, v215);
        v90 = 0;
      }
    }
    v228 = 0;
    v91 = v160 >> 1;
    if ( (v160 >> 1) - 1 > 0x7FFFFFFE )
    {
      v94 = -2147024809;
      v96 = 0;
      v228 = 0;
    }
    else
    {
      v92 = v160 >> 1;
      v272 = v160 >> 1;
      v93 = v216;
      v271 = v216;
      v94 = 0;
      while ( 1 )
      {
        v95 = v92 == 0;
        if ( !v92 )
          break;
        if ( !*v93 )
        {
          v95 = v92 == 0;
          break;
        }
        v271 = ++v93;
        v272 = --v92;
      }
      if ( v95 )
        v94 = -2147024809;
      if ( v94 < 0 )
        v228 = 0;
      else
        v228 = v91 - v92;
      v96 = v228;
    }
    if ( v94 >= 0 )
    {
      v97 = 2147483646;
      v275 = 2147483646;
      v98 = L"(((EventClassID=";
      v273 = L"(((EventClassID=";
      v99 = v91 - v96;
      v274 = v91 - v96;
      v100 = &v216[v96];
      v241 = v100;
      v94 = 0;
      v101 = 0;
      v242 = 0;
      while ( v99 )
      {
        if ( !v97 )
          goto LABEL_205;
        v102 = *v98;
        if ( !*v98 )
          goto LABEL_205;
        v273 = ++v98;
        *v100++ = v102;
        v241 = v100;
        v274 = --v99;
        v275 = --v97;
        v242 = ++v101;
      }
      v241 = --v100;
      v242 = v101 - 1;
      v94 = -2147024774;
LABEL_205:
      *v100 = 0;
      v90 = 0;
    }
    v215 = v94;
    if ( v94 < 0 )
    {
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1586u, 0x12u, v215);
      v90 = 0;
    }
    v103 = (_WORD *)*((_QWORD *)v219 + 12);
    v229 = 0;
    if ( v91 && v91 <= 0x7FFFFFFF )
    {
      v104 = v160 >> 1;
      v277 = v160 >> 1;
      v105 = v216;
      v276 = v216;
      v106 = 0;
      while ( 1 )
      {
        v107 = v104 == 0;
        if ( !v104 )
          break;
        if ( !*v105 )
        {
          v107 = v104 == 0;
          break;
        }
        v276 = ++v105;
        v277 = --v104;
      }
      if ( v107 )
        v106 = -2147024809;
      if ( v106 < 0 )
        v229 = 0;
      else
        v229 = v91 - v104;
      v108 = v229;
    }
    else
    {
      v106 = -2147024809;
      v108 = 0;
      v229 = 0;
    }
    if ( v106 >= 0 )
    {
      v109 = 2147483646;
      v280 = 2147483646;
      v278 = v103;
      v110 = v91 - v108;
      v279 = v91 - v108;
      v111 = &v216[v108];
      v243 = v111;
      v106 = 0;
      v244 = 0;
      while ( v110 )
      {
        if ( !v109 )
          goto LABEL_226;
        v112 = *v103;
        if ( !*v103 )
          goto LABEL_226;
        v278 = ++v103;
        *v111++ = v112;
        v243 = v111;
        v279 = --v110;
        v280 = --v109;
        v244 = ++v90;
      }
      v243 = --v111;
      v244 = v90 - 1;
      v106 = -2147024774;
LABEL_226:
      *v111 = 0;
    }
    v215 = v106;
    if ( v106 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1588u, 0x12u, v215);
    if ( *((_QWORD *)v219 + 13) )
    {
      v215 = StringCbCatW(v216, v160, L" | PublisherID='");
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x158Cu, 0x12u, v215);
      v215 = StringCbCatW(v216, v160, *((const unsigned __int16 **)v219 + 13));
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x158Eu, 0x12u, v215);
      v215 = StringCbCatW(v216, v160, L"'");
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1590u, 0x12u, v215);
    }
    v230 = 0;
    if ( v91 && v91 <= 0x7FFFFFFF )
    {
      v113 = v160 >> 1;
      v282 = v160 >> 1;
      v114 = v216;
      v281 = v216;
      v115 = 0;
      while ( 1 )
      {
        v116 = v113 == 0;
        if ( !v113 )
          break;
        if ( !*v114 )
        {
          v116 = v113 == 0;
          break;
        }
        v281 = ++v114;
        v282 = --v113;
      }
      if ( v116 )
        v115 = -2147024809;
      if ( v115 < 0 )
        v230 = 0;
      else
        v230 = v91 - v113;
      v117 = v230;
    }
    else
    {
      v117 = 0;
      v115 = -2147024809;
      v230 = 0;
    }
    if ( v115 >= 0 )
    {
      v118 = 2147483646;
      v285 = 2147483646;
      v119 = L") & InterfaceID=(null";
      v283 = L") & InterfaceID=(null";
      v120 = v91 - v117;
      v284 = v91 - v117;
      v121 = &v216[v117];
      v245 = v121;
      v115 = 0;
      v122 = 0;
      v246 = 0;
      while ( v120 )
      {
        if ( !v118 )
          goto LABEL_248;
        v123 = *v119;
        if ( !*v119 )
          goto LABEL_248;
        v283 = ++v119;
        *v121++ = v123;
        v245 = v121;
        v284 = --v120;
        v285 = --v118;
        v246 = ++v122;
      }
      v245 = --v121;
      v246 = v122 - 1;
      v115 = -2147024774;
LABEL_248:
      *v121 = 0;
    }
    v215 = v115;
    if ( v115 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1593u, 0x12u, v215);
    for ( j = 0; ; ++j )
    {
      v220 = j;
      if ( j >= v196 )
        break;
      v215 = StringFromGUID2(*(const GUID *const *)&v216[4 * j - 2], sz, 39);
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1598u, 0x12u, v215);
      v137 = 0;
      v231 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v138 = v160 >> 1;
        v287 = v160 >> 1;
        v139 = v217;
        v140 = v217;
        v286 = v217;
        v141 = 0;
        while ( 1 )
        {
          v142 = v138 == 0;
          if ( !v138 )
            break;
          if ( !*v140 )
          {
            v142 = v138 == 0;
            break;
          }
          v286 = ++v140;
          v287 = --v138;
        }
        if ( v142 )
          v141 = -2147024809;
        if ( v141 < 0 )
          v231 = 0;
        else
          v231 = v91 - v138;
        v143 = v231;
      }
      else
      {
        v141 = -2147024809;
        v143 = 0;
        v231 = 0;
        v139 = v217;
      }
      if ( v141 >= 0 )
      {
        v144 = 2147483646;
        v290 = 2147483646;
        v145 = L" | ";
        v288 = L" | ";
        v146 = v91 - v143;
        v289 = v91 - v143;
        v147 = &v139[v143];
        v247 = v147;
        v141 = 0;
        v248 = 0;
        while ( v146 )
        {
          if ( !v144 )
            goto LABEL_293;
          v148 = *v145;
          if ( !*v145 )
            goto LABEL_293;
          v288 = ++v145;
          *v147++ = v148;
          v247 = v147;
          v289 = --v146;
          v290 = --v144;
          v248 = ++v137;
        }
        v247 = --v147;
        v248 = v137 - 1;
        v141 = -2147024774;
LABEL_293:
        v137 = 0;
        *v147 = 0;
      }
      v215 = v141;
      if ( v141 < 0 )
      {
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x159Au, 0x12u, v215);
        v137 = 0;
      }
      v232 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v149 = v160 >> 1;
        v292 = v160 >> 1;
        v150 = v217;
        v151 = v217;
        v291 = v217;
        v152 = 0;
        while ( 1 )
        {
          v153 = v149 == 0;
          if ( !v149 )
            break;
          if ( !*v151 )
          {
            v153 = v149 == 0;
            break;
          }
          v291 = ++v151;
          v292 = --v149;
        }
        if ( v153 )
          v152 = -2147024809;
        if ( v152 < 0 )
          v232 = 0;
        else
          v232 = v91 - v149;
        v154 = v232;
      }
      else
      {
        v152 = -2147024809;
        v154 = 0;
        v232 = 0;
        v150 = v217;
      }
      if ( v152 >= 0 )
      {
        v155 = 2147483646;
        v295 = 2147483646;
        v156 = sz;
        v293 = sz;
        v157 = v91 - v154;
        v294 = v91 - v154;
        v158 = &v150[v154];
        v249 = v158;
        v152 = 0;
        v250 = 0;
        while ( v157 )
        {
          if ( !v155 )
            goto LABEL_314;
          v159 = *v156;
          if ( !*v156 )
            goto LABEL_314;
          v293 = ++v156;
          *v158++ = v159;
          v249 = v158;
          v294 = --v157;
          v295 = --v155;
          v250 = ++v137;
        }
        v249 = --v158;
        v250 = v137 - 1;
        v152 = -2147024774;
LABEL_314:
        *v158 = 0;
      }
      v215 = v152;
      if ( v152 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x159Cu, 0x12u, v215);
    }
    v233 = 0;
    if ( v91 && v91 <= 0x7FFFFFFF )
    {
      v125 = v160 >> 1;
      v297 = v160 >> 1;
      v126 = v217;
      v127 = v217;
      v296 = v217;
      v128 = 0;
      while ( 1 )
      {
        v129 = v125 == 0;
        if ( !v125 )
          break;
        if ( !*v127 )
        {
          v129 = v125 == 0;
          break;
        }
        v296 = ++v127;
        v297 = --v125;
      }
      if ( v129 )
        v128 = -2147024809;
      if ( v128 < 0 )
        v233 = 0;
      else
        v233 = v91 - v125;
      v130 = v233;
    }
    else
    {
      v130 = 0;
      v128 = -2147024809;
      v233 = 0;
      v126 = v217;
    }
    if ( v128 >= 0 )
    {
      v131 = 2147483646;
      v300 = 2147483646;
      v132 = L")) | (EventClassID=null & PublisherID=null & InterfaceID=(";
      v298 = L")) | (EventClassID=null & PublisherID=null & InterfaceID=(";
      v133 = v91 - v130;
      v299 = v91 - v130;
      v134 = &v126[v130];
      v251 = v134;
      v128 = 0;
      v135 = 0;
      v252 = 0;
      while ( v133 )
      {
        if ( !v131 )
          goto LABEL_34;
        v136 = *v132;
        if ( !*v132 )
          goto LABEL_34;
        v298 = ++v132;
        *v134++ = v136;
        v251 = v134;
        v299 = --v133;
        v300 = --v131;
        v252 = ++v135;
      }
      v251 = --v134;
      v252 = v135 - 1;
      v128 = -2147024774;
LABEL_34:
      *v134 = 0;
    }
    v215 = v128;
    if ( v128 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x159Fu, 0x12u, v215);
    for ( k = 0; ; ++k )
    {
      v220 = k;
      if ( k >= v196 )
        break;
      v215 = StringFromGUID2(*(const GUID *const *)&v216[4 * k - 2], sz, 39);
      if ( v215 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15A2u, 0x12u, v215);
      if ( k )
      {
        v215 = StringCbCatW(v217, v160, L" | ");
        if ( v215 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15A7u, 0x12u, v215);
      }
      v14 = 0;
      v234 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v15 = v160 >> 1;
        v302 = v160 >> 1;
        v16 = v217;
        v17 = v217;
        v301 = v217;
        v18 = 0;
        while ( 1 )
        {
          v19 = v15 == 0;
          if ( !v15 )
            break;
          if ( !*v17 )
          {
            v19 = v15 == 0;
            break;
          }
          v301 = ++v17;
          v302 = --v15;
        }
        if ( v19 )
          v18 = -2147024809;
        if ( v18 < 0 )
          v234 = 0;
        else
          v234 = v91 - v15;
        v20 = v234;
      }
      else
      {
        v18 = -2147024809;
        v20 = 0;
        v234 = 0;
        v16 = v217;
      }
      if ( v18 >= 0 )
      {
        v21 = 2147483646;
        v305 = 2147483646;
        v22 = sz;
        v303 = sz;
        v23 = v91 - v20;
        v304 = v91 - v20;
        v24 = &v16[v20];
        v253 = v24;
        v18 = 0;
        v254 = 0;
        while ( v23 )
        {
          if ( !v21 )
            goto LABEL_30;
          v25 = *v22;
          if ( !*v22 )
            goto LABEL_30;
          v303 = ++v22;
          *v24++ = v25;
          v253 = v24;
          v304 = --v23;
          v305 = --v21;
          v254 = ++v14;
        }
        v253 = --v24;
        v254 = v14 - 1;
        v18 = -2147024774;
LABEL_30:
        *v24 = 0;
      }
      v215 = v18;
      if ( v18 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15AAu, 0x12u, v215);
    }
    v235 = 0;
    if ( v91 && v91 <= 0x7FFFFFFF )
    {
      v27 = v160 >> 1;
      v307 = v160 >> 1;
      v9 = v217;
      v28 = v217;
      v306 = v217;
      v29 = 0;
      while ( 1 )
      {
        v30 = v27 == 0;
        if ( !v27 )
          break;
        if ( !*v28 )
        {
          v30 = v27 == 0;
          break;
        }
        v306 = ++v28;
        v307 = --v27;
      }
      if ( v30 )
        v29 = -2147024809;
      if ( v29 < 0 )
        v235 = 0;
      else
        v235 = v91 - v27;
      v31 = v235;
    }
    else
    {
      v29 = -2147024809;
      v31 = 0;
      v235 = 0;
      v9 = v217;
    }
    if ( v29 >= 0 )
    {
      v32 = 2147483646;
      v310 = 2147483646;
      v33 = L")))";
      v308 = L")))";
      v34 = v91 - v31;
      v309 = v91 - v31;
      v35 = &v9[v31];
      v255 = v35;
      v29 = 0;
      v36 = 0;
      v256 = 0;
      while ( v34 )
      {
        if ( !v32 )
          goto LABEL_57;
        v37 = *v33;
        if ( !*v33 )
          goto LABEL_57;
        v308 = ++v33;
        *v35++ = v37;
        v255 = v35;
        v309 = --v34;
        v310 = --v32;
        v256 = ++v36;
      }
      v255 = --v35;
      v256 = v36 - 1;
      v29 = -2147024774;
LABEL_57:
      *v35 = 0;
    }
    v215 = v29;
    if ( v29 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15ADu, 0x12u, v215);
    if ( a3 )
    {
      v236 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v38 = v160 >> 1;
        v312 = v160 >> 1;
        v39 = v9;
        v311 = v9;
        v40 = 0;
        while ( 1 )
        {
          v41 = v38 == 0;
          if ( !v38 )
            break;
          if ( !*v39 )
          {
            v41 = v38 == 0;
            break;
          }
          v311 = ++v39;
          v312 = --v38;
        }
        if ( v41 )
          v40 = -2147024809;
        if ( v40 < 0 )
          v236 = 0;
        else
          v236 = v91 - v38;
        v42 = v236;
      }
      else
      {
        v40 = -2147024809;
        v42 = 0;
        v236 = 0;
      }
      if ( v40 >= 0 )
      {
        v43 = 2147483646;
        v315 = 2147483646;
        v44 = L" & MethodName=(null | '";
        v313 = L" & MethodName=(null | '";
        v45 = v91 - v42;
        v314 = v91 - v42;
        v46 = &v9[v42];
        v257 = v46;
        v40 = 0;
        v47 = 0;
        v258 = 0;
        while ( v45 )
        {
          if ( !v43 )
            goto LABEL_79;
          v48 = *v44;
          if ( !*v44 )
            goto LABEL_79;
          v313 = ++v44;
          *v46++ = v48;
          v257 = v46;
          v314 = --v45;
          v315 = --v43;
          v258 = ++v47;
        }
        v257 = --v46;
        v258 = v47 - 1;
        v40 = -2147024774;
LABEL_79:
        *v46 = 0;
      }
      v215 = v40;
      if ( v40 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15B1u, 0x12u, v215);
      v237 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v49 = v160 >> 1;
        v317 = v160 >> 1;
        v50 = v9;
        v316 = v9;
        v51 = 0;
        while ( 1 )
        {
          v52 = v49 == 0;
          if ( !v49 )
            break;
          if ( !*v50 )
          {
            v52 = v49 == 0;
            break;
          }
          v316 = ++v50;
          v317 = --v49;
        }
        if ( v52 )
          v51 = -2147024809;
        if ( v51 < 0 )
          v237 = 0;
        else
          v237 = v91 - v49;
        v53 = v237;
      }
      else
      {
        v51 = -2147024809;
        v53 = 0;
        v237 = 0;
      }
      if ( v51 >= 0 )
      {
        v54 = 2147483646;
        v320 = 2147483646;
        v318 = a3;
        v55 = v91 - v53;
        v319 = v91 - v53;
        v56 = &v9[v53];
        v259 = v56;
        v51 = 0;
        v57 = 0;
        v260 = 0;
        while ( v55 )
        {
          if ( !v54 )
            goto LABEL_100;
          v58 = *a3;
          if ( !*a3 )
            goto LABEL_100;
          v318 = ++a3;
          *v56++ = v58;
          v259 = v56;
          v319 = --v55;
          v320 = --v54;
          v260 = ++v57;
        }
        v259 = --v56;
        v260 = v57 - 1;
        v51 = -2147024774;
LABEL_100:
        *v56 = 0;
      }
      v215 = v51;
      if ( v51 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15B3u, 0x12u, v215);
      v238 = 0;
      if ( v91 && v91 <= 0x7FFFFFFF )
      {
        v59 = v160 >> 1;
        v322 = v160 >> 1;
        v60 = v9;
        v321 = v9;
        v61 = 0;
        while ( 1 )
        {
          v62 = v59 == 0;
          if ( !v59 )
            break;
          if ( !*v60 )
          {
            v62 = v59 == 0;
            break;
          }
          v321 = ++v60;
          v322 = --v59;
        }
        if ( v62 )
          v61 = -2147024809;
        if ( v61 < 0 )
          v238 = 0;
        else
          v238 = v91 - v59;
        v63 = v238;
      }
      else
      {
        v61 = -2147024809;
        v63 = 0;
        v238 = 0;
      }
      if ( v61 >= 0 )
      {
        v325 = 2147483646;
        v64 = L"')";
        v323 = L"')";
        v65 = v91 - v63;
        v324 = v65;
        v66 = &v9[v63];
        v261 = v66;
        v61 = 0;
        v67 = 0;
        v262 = 0;
        while ( v65 )
        {
          if ( !v69 )
            goto LABEL_121;
          v68 = *v64;
          if ( !*v64 )
            goto LABEL_121;
          v323 = ++v64;
          *v66++ = v68;
          v261 = v66;
          v324 = --v65;
          v325 = --v69;
          v262 = ++v67;
        }
        v261 = --v66;
        v262 = v67 - 1;
        v61 = -2147024774;
LABEL_121:
        *v66 = 0;
      }
      v215 = v61;
      if ( v61 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15B5u, 0x12u, v215);
    }
    if ( v9 )
    {
      v70 = -1;
      do
        ++v70;
      while ( v9[v70] );
    }
    else
    {
      v70 = 0;
    }
    v334 = v70;
    *v265 = v70;
    v8 = v219;
LABEL_128:
    if ( !v9 )
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x15D2u, 0x80001203, 0x12u);
    v221 = 0;
    v219 = 0;
    v71 = *((_QWORD *)v8 + 4);
    v72 = -2147024882;
    v73 = -2147024882;
    if ( v218 )
    {
      LODWORD(v217) = -2147024882;
      v88 = CoTaskMemAlloc(0xA0u);
      v76 = 1;
      if ( v88 )
      {
        v77 = (EventObjectCollection *)EventObjectCollection::EventObjectCollection(
                                         v88,
                                         1,
                                         v9,
                                         &v221,
                                         v71,
                                         1,
                                         0,
                                         v222,
                                         1,
                                         &v217);
        v73 = (int)v217;
      }
      else
      {
        v77 = 0;
      }
      v219 = v77;
      if ( !v77 )
        InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x299u, 0xC0001204, 0x10u);
      if ( v73 >= 0 )
        goto LABEL_136;
      if ( v77 )
      {
        EventObjectCollection::~EventObjectCollection(v77);
        CoTaskMemFree(v77);
      }
      v77 = 0;
    }
    else
    {
      v218 = -2147024882;
      v74 = CoTaskMemAlloc(0xA0u);
      v76 = 1;
      if ( v74 )
      {
        v77 = (EventObjectCollection *)EventObjectCollection::EventObjectCollection(
                                         v74,
                                         1,
                                         v9,
                                         &v221,
                                         v71,
                                         1,
                                         0,
                                         0,
                                         0,
                                         &v218);
        v73 = v218;
      }
      else
      {
        v77 = 0;
      }
      v219 = v77;
      if ( !v77 )
        InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x27Fu, 0xC0001204, 0x10u);
      if ( v73 >= 0 )
      {
LABEL_136:
        (*(void (__fastcall **)(EventObjectCollection *))(*(_QWORD *)v77 + 8LL))(v77);
        goto LABEL_137;
      }
      if ( v77 )
      {
        EventObjectCollection::~EventObjectCollection(v77);
        CoTaskMemFree(v77);
      }
      v77 = 0;
    }
    v219 = 0;
LABEL_137:
    v215 = v73;
    if ( v327 )
    {
      v89 = v221;
      if ( v221 )
      {
        LODWORD(v75) = v263;
        if ( v263 )
        {
          v89 = v221 - v263;
          v221 -= v263;
        }
      }
      *v327 = v89;
    }
    if ( v215 < 0 )
    {
      v78 = v329;
LABEL_140:
      if ( v215 < 0 )
      {
        if ( v78 )
          FiringAgent::AutoUpdateListElement::`scalar deleting destructor'(v78, (unsigned int)v75);
        if ( v77 )
          (*(void (__fastcall **)(EventObjectCollection *))(*(_QWORD *)v77 + 16LL))(v77);
      }
      else
      {
        *v330 = (struct IEventObjectCollection *)v77;
      }
      return (unsigned int)v215;
    }
    v79 = (FiringAgent::AutoUpdateListElement *)CoTaskMemAlloc(0x18u);
    v78 = v79;
    if ( v79 )
    {
      *(GUID *)v79 = GUID_NULL;
      *((_QWORD *)v79 + 2) = 0;
    }
    else
    {
      v78 = 0;
    }
    v335 = v78;
    if ( !v78 )
      v215 = -2147024882;
    if ( v215 < 0 )
      goto LABEL_140;
    if ( v77 )
      v80 = (char *)v77 + 8;
    else
      v80 = 0;
    *((_QWORD *)v78 + 2) = v80;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v80 + 8LL))(v80);
    v81 = *((_QWORD *)v8 + 18);
    if ( !*((_QWORD *)v8 + 20) )
    {
      v82 = CoTaskMemAlloc((unsigned int)(24 * *((_DWORD *)v8 + 44)) + 8LL);
      if ( !v82 )
      {
LABEL_166:
        v215 = v72;
        if ( v72 >= 0 )
        {
          v215 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, FiringAgent::AutoUpdateListElement *))(**((_QWORD **)v8 + 4)
                                                                                                 + 24LL))(
                   *((_QWORD *)v8 + 4),
                   *((_QWORD *)v78 + 2),
                   v78);
          if ( v215 < 0 )
            CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveTail((char *)v8 + 136);
        }
        goto LABEL_140;
      }
      *v82 = *((_QWORD *)v8 + 21);
      *((_QWORD *)v8 + 21) = v82;
      v264 = v82 + 1;
      v83 = *((_DWORD *)v8 + 44) - 1;
      for ( m = &v82[3 * v83 + 1]; ; m -= 3 )
      {
        v225 = v83;
        v264 = m;
        if ( v83 < 0 )
          break;
        *m = *((_QWORD *)v8 + 20);
        *((_QWORD *)v8 + 20) = m;
        --v83;
      }
    }
    v85 = (_QWORD *)*((_QWORD *)v8 + 20);
    *((_QWORD *)v8 + 20) = *v85;
    v85[1] = v81;
    *v85 = 0;
    ++*((_DWORD *)v8 + 38);
    v226 = 1;
    v75 = v85 + 2;
    v85[2] = 0;
    while ( 1 )
    {
      v328 = v75;
      v86 = v76--;
      v226 = v76;
      if ( !v86 )
        break;
      ++v75;
    }
    if ( v85 )
    {
      v85[2] = v78;
      v87 = (_QWORD *)*((_QWORD *)v8 + 18);
      if ( v87 )
        *v87 = v85;
      else
        *((_QWORD *)v8 + 17) = v85;
      *((_QWORD *)v8 + 18) = v85;
      v72 = 0;
    }
    goto LABEL_166;
  }
  v190 = *v202;
  v191 = 0;
  v223 = 0;
  while ( v191 < *(_DWORD *)(v190 + 40) )
  {
    v192 = a3;
    do
    {
      v193 = *(unsigned __int16 *)((char *)v192
                                 + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v190 + 48) + 8LL * v191) + 8LL)
                                 - (_QWORD)a3);
      v194 = *v192 - v193;
      if ( v194 )
        break;
      ++v192;
    }
    while ( v193 );
    if ( !v194 )
      goto LABEL_381;
    v223 = ++v191;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180003df0  push    rbp
0x180003df2  push    rbx
0x180003df3  push    rsi
0x180003df4  push    rdi
0x180003df5  push    r12
0x180003df7  push    r13
0x180003df9  push    r14
0x180003dfb  push    r15
0x180003dfd  sub     rsp, 588h
0x180003e04  lea     rbp, [rsp+50h]
0x180003e09  mov     rax, cs:__security_cookie
0x180003e10  xor     rax, rbp
0x180003e13  mov     [rbp+570h+var_50], rax
0x180003e1a  mov     rdi, r9
0x180003e1d  mov     r12, r8
0x180003e20  mov     r8, rdx
0x180003e23  mov     r15, rcx
0x180003e26  mov     [rbp+570h+var_558], rcx
0x180003e2a  mov     rax, [rbp+570h+arg_20]
0x180003e31  mov     [rbp+570h+var_208], rax
0x180003e38  mov     rax, [rbp+570h+arg_28]
0x180003e3f  mov     [rbp+570h+var_1F0], rax
0x180003e46  xor     r11d, r11d
0x180003e49  mov     [rbp+570h+var_570], r11d
0x180003e4d  mov     [rbp+570h+var_408], r11
0x180003e54  test    rax, rax
0x180003e57  jz      loc_180005CE2
0x180003e5d  mov     r14, r9
0x180003e60  mov     esi, r11d
0x180003e63  mov     ecx, 1
0x180003e68  mov     [rbp+570h+var_544], ecx
0x180003e6b  mov     [rbp+570h+var_1F8], r11
0x180003e72  mov     [rax], r11
0x180003e75  mov     r9, [r15+38h]
0x180003e79  test    r9, r9
0x180003e7c  jz      loc_1800057C4
0x180003e82  xor     edx, edx
0x180003e84  mov     eax, [r8]
0x180003e87  div     dword ptr [r15+40h]
0x180003e8b  mov     rax, [r9+rdx*8]
0x180003e8f  test    rax, rax
0x180003e92  jz      loc_1800057BF
0x180003e98  mov     rcx, [rax+0Ch]
0x180003e9c  sub     rcx, [r8]
0x180003e9f  jnz     short loc_180003EA9
0x180003ea1  mov     rcx, [rax+14h]
0x180003ea5  sub     rcx, [r8+8]
0x180003ea9  test    rcx, rcx
0x180003eac  jnz     loc_18000592C
0x180003eb2  mov     ecx, 1
0x180003eb7  jmp     loc_1800057C7
0x180003ebc  movsxd  rcx, ebx
0x180003ebf  mov     r8d, 27h ; '''; cchMax
0x180003ec5  lea     rdx, [rbp+570h+sz]; lpsz
0x180003ecc  mov     rcx, [r15+rcx*8]; rguid
0x180003ed0  call    cs:__imp_StringFromGUID2
0x180003ed6  mov     [rbp+570h+var_570], eax
0x180003ed9  mov     eax, [rbp+570h+var_570]
0x180003edc  test    eax, eax
0x180003ede  js      loc_1800049D6
0x180003ee4  test    ebx, ebx
0x180003ee6  jnz     loc_180005B77
0x180003eec  xor     r10d, r10d
0x180003eef  mov     [rbp+570h+var_4F0], r10
0x180003ef6  test    rsi, rsi
0x180003ef9  jz      loc_180005BB8
0x180003eff  cmp     rsi, 7FFFFFFFh
0x180003f06  ja      loc_180005BB8
0x180003f0c  lea     rdx, [rbp+570h+var_4F0]
0x180003f13  mov     rcx, rsi
0x180003f16  mov     [rbp+570h+var_2D0], rcx
0x180003f1d  mov     r9, [rbp+570h+var_568]
0x180003f21  mov     rax, r9
0x180003f24  mov     [rbp+570h+var_2D8], rax
0x180003f2b  mov     r11d, r10d
0x180003f2e  xchg    ax, ax
0x180003f30  test    rcx, rcx
0x180003f33  jz      short loc_180003F55
0x180003f35  cmp     [rax], r10w
0x180003f39  jz      short loc_180003F52
0x180003f3b  add     rax, 2
0x180003f3f  mov     [rbp+570h+var_2D8], rax
0x180003f46  dec     rcx
0x180003f49  mov     [rbp+570h+var_2D0], rcx
0x180003f50  jmp     short loc_180003F30
0x180003f52  test    rcx, rcx
0x180003f55  mov     eax, 80070057h
0x180003f5a  cmovz   r11d, eax
0x180003f5e  test    r11d, r11d
0x180003f61  js      loc_180004918
0x180003f67  mov     rax, rsi
0x180003f6a  sub     rax, rcx
0x180003f6d  mov     [rdx], rax
0x180003f70  mov     rax, [rbp+570h+var_4F0]
0x180003f77  test    r11d, r11d
0x180003f7a  js      loc_180004020
0x180003f80  mov     rdx, r13
0x180003f83  mov     [rbp+570h+var_2B8], rdx
0x180003f8a  lea     r8, [rbp+570h+sz]
0x180003f91  mov     [rbp+570h+var_2C8], r8
0x180003f98  mov     rcx, rsi
0x180003f9b  sub     rcx, rax
0x180003f9e  mov     [rbp+570h+var_2C0], rcx
0x180003fa5  lea     r9, [r9+rax*2]
0x180003fa9  mov     [rbp+570h+var_458], r9
0x180003fb0  mov     r11d, r10d
0x180003fb3  mov     [rbp+570h+var_450], r10
0x180003fba  nop     word ptr [rax+rax+00h]
0x180003fc0  test    rcx, rcx
0x180003fc3  jz      loc_180004640
0x180003fc9  test    rdx, rdx
0x180003fcc  jz      short loc_180004011
0x180003fce  movzx   eax, word ptr [r8]
0x180003fd2  test    ax, ax
0x180003fd5  jz      short loc_180004011
0x180003fd7  add     r8, 2
0x180003fdb  mov     [rbp+570h+var_2C8], r8
0x180003fe2  mov     [r9], ax
0x180003fe6  add     r9, 2
0x180003fea  mov     [rbp+570h+var_458], r9
0x180003ff1  dec     rcx
0x180003ff4  mov     [rbp+570h+var_2C0], rcx
0x180003ffb  dec     rdx
0x180003ffe  mov     [rbp+570h+var_2B8], rdx
0x180004005  inc     r10
0x180004008  mov     [rbp+570h+var_450], r10
0x18000400f  jmp     short loc_180003FC0
0x180004011  test    rcx, rcx
0x180004014  jz      loc_180004640
0x18000401a  xor     eax, eax
0x18000401c  mov     [r9], ax
0x180004020  mov     [rbp+570h+var_570], r11d
0x180004024  mov     eax, [rbp+570h+var_570]
0x180004027  test    eax, eax
0x180004029  js      loc_180004974
0x18000402f  inc     ebx
0x180004031  jmp     short loc_18000404A
0x180004033  xor     eax, eax
0x180004035  mov     [r9], ax
0x180004039  mov     [rbp+570h+var_570], r11d
0x18000403d  mov     eax, [rbp+570h+var_570]
0x180004040  test    eax, eax
0x180004042  js      loc_1800049B6
0x180004048  xor     ebx, ebx
0x18000404a  mov     [rbp+570h+var_550], ebx
0x18000404d  cmp     ebx, r14d
0x180004050  jl      loc_180003EBC
0x180004056  xor     edi, edi
0x180004058  mov     [rbp+570h+var_4E8], rdi
0x18000405f  test    rsi, rsi
0x180004062  jz      loc_180005BD1
0x180004068  cmp     rsi, 7FFFFFFFh
0x18000406f  ja      loc_180005BD1
0x180004075  lea     rdx, [rbp+570h+var_4E8]
0x18000407c  mov     rcx, rsi
0x18000407f  mov     [rbp+570h+var_2A8], rcx
0x180004086  mov     r14, [rbp+570h+var_568]
0x18000408a  mov     rax, r14
0x18000408d  mov     [rbp+570h+var_2B0], rax
0x180004094  mov     r11d, edi
0x180004097  test    rcx, rcx
0x18000409a  jz      short loc_1800040BB
0x18000409c  cmp     [rax], di
0x18000409f  jz      short loc_1800040B8
0x1800040a1  add     rax, 2
0x1800040a5  mov     [rbp+570h+var_2B0], rax
0x1800040ac  dec     rcx
0x1800040af  mov     [rbp+570h+var_2A8], rcx
0x1800040b6  jmp     short loc_180004097
0x1800040b8  test    rcx, rcx
0x1800040bb  mov     ebx, 80070057h
0x1800040c0  cmovz   r11d, ebx
0x1800040c4  test    r11d, r11d
0x1800040c7  js      loc_180004920
0x1800040cd  mov     rax, rsi
0x1800040d0  sub     rax, rcx
0x1800040d3  mov     [rdx], rax
0x1800040d6  mov     r8, [rbp+570h+var_4E8]
0x1800040dd  test    r11d, r11d
0x1800040e0  js      loc_180004182
0x1800040e6  mov     rcx, r13
0x1800040e9  mov     [rbp+570h+var_290], rcx
0x1800040f0  lea     rdx, asc_180052A38; ")))"
0x1800040f7  mov     [rbp+570h+var_2A0], rdx
0x1800040fe  mov     rax, rsi
0x180004101  sub     rax, r8
0x180004104  mov     [rbp+570h+var_298], rax
0x18000410b  lea     r8, [r14+r8*2]
0x18000410f  mov     [rbp+570h+var_448], r8
0x180004116  mov     r11d, edi
0x180004119  mov     r10, rdi
0x18000411c  mov     [rbp+570h+var_440], rdi
0x180004123  test    rax, rax
0x180004126  jz      loc_180004660
0x18000412c  test    rcx, rcx
0x18000412f  jz      short loc_180004175
0x180004131  movzx   r9d, word ptr [rdx]
0x180004135  test    r9w, r9w
0x180004139  jz      short loc_180004175
0x18000413b  add     rdx, 2
0x18000413f  mov     [rbp+570h+var_2A0], rdx
0x180004146  mov     [r8], r9w
0x18000414a  add     r8, 2
0x18000414e  mov     [rbp+570h+var_448], r8
0x180004155  dec     rax
0x180004158  mov     [rbp+570h+var_298], rax
0x18000415f  dec     rcx
0x180004162  mov     [rbp+570h+var_290], rcx
0x180004169  inc     r10
0x18000416c  mov     [rbp+570h+var_440], r10
0x180004173  jmp     short loc_180004123
0x180004175  test    rax, rax
0x180004178  jz      loc_180004660
0x18000417e  mov     [r8], di
0x180004182  mov     [rbp+570h+var_570], r11d
0x180004186  mov     eax, [rbp+570h+var_570]
0x180004189  test    eax, eax
0x18000418b  js      loc_1800049F6
0x180004191  test    r12, r12
0x180004194  jz      loc_18000452B
0x18000419a  mov     [rbp+570h+var_4E0], rdi
0x1800041a1  test    rsi, rsi
0x1800041a4  jz      loc_180005BEC
0x1800041aa  cmp     rsi, 7FFFFFFFh
0x1800041b1  ja      loc_180005BEC
0x1800041b7  lea     rdx, [rbp+570h+var_4E0]
0x1800041be  mov     rcx, rsi
0x1800041c1  mov     [rbp+570h+var_280], rcx
0x1800041c8  mov     rax, r14
0x1800041cb  mov     [rbp+570h+var_288], rax
0x1800041d2  mov     r11d, edi
0x1800041d5  test    rcx, rcx
0x1800041d8  jz      short loc_1800041F9
0x1800041da  cmp     [rax], di
0x1800041dd  jz      short loc_1800041F6
0x1800041df  add     rax, 2
0x1800041e3  mov     [rbp+570h+var_288], rax
0x1800041ea  dec     rcx
0x1800041ed  mov     [rbp+570h+var_280], rcx
0x1800041f4  jmp     short loc_1800041D5
0x1800041f6  test    rcx, rcx
0x1800041f9  cmovz   r11d, ebx
0x1800041fd  test    r11d, r11d
0x180004200  js      loc_180004928
0x180004206  mov     rax, rsi
0x180004209  sub     rax, rcx
0x18000420c  mov     [rdx], rax
0x18000420f  mov     r8, [rbp+570h+var_4E0]
0x180004216  test    r11d, r11d
0x180004219  js      loc_1800042BF
0x18000421f  mov     rcx, r13
0x180004222  mov     [rbp+570h+var_268], rcx
0x180004229  lea     rdx, aMethodnameNull; " & MethodName=(null | '"
0x180004230  mov     [rbp+570h+var_278], rdx
0x180004237  mov     rax, rsi
0x18000423a  sub     rax, r8
0x18000423d  mov     [rbp+570h+var_270], rax
0x180004244  lea     r8, [r14+r8*2]
0x180004248  mov     [rbp+570h+var_438], r8
0x18000424f  mov     r11d, edi
0x180004252  mov     r10, rdi
0x180004255  mov     [rbp+570h+var_430], rdi
0x18000425c  nop     dword ptr [rax+00h]
0x180004260  test    rax, rax
0x180004263  jz      loc_180004680
0x180004269  test    rcx, rcx
0x18000426c  jz      short loc_1800042B2
0x18000426e  movzx   r9d, word ptr [rdx]
0x180004272  test    r9w, r9w
0x180004276  jz      short loc_1800042B2
0x180004278  add     rdx, 2
0x18000427c  mov     [rbp+570h+var_278], rdx
0x180004283  mov     [r8], r9w
0x180004287  add     r8, 2
0x18000428b  mov     [rbp+570h+var_438], r8
0x180004292  dec     rax
0x180004295  mov     [rbp+570h+var_270], rax
0x18000429c  dec     rcx
0x18000429f  mov     [rbp+570h+var_268], rcx
0x1800042a6  inc     r10
0x1800042a9  mov     [rbp+570h+var_430], r10
0x1800042b0  jmp     short loc_180004260
0x1800042b2  test    rax, rax
0x1800042b5  jz      loc_180004680
0x1800042bb  mov     [r8], di
0x1800042bf  mov     [rbp+570h+var_570], r11d
0x1800042c3  mov     eax, [rbp+570h+var_570]
0x1800042c6  test    eax, eax
0x1800042c8  js      loc_180004A16
0x1800042ce  mov     [rbp+570h+var_4D8], rdi
0x1800042d5  test    rsi, rsi
0x1800042d8  jz      loc_180005BFE
0x1800042de  cmp     rsi, 7FFFFFFFh
0x1800042e5  ja      loc_180005BFE
0x1800042eb  lea     rdx, [rbp+570h+var_4D8]
0x1800042f2  mov     rcx, rsi
0x1800042f5  mov     [rbp+570h+var_258], rcx
0x1800042fc  mov     rax, r14
0x1800042ff  mov     [rbp+570h+var_260], rax
0x180004306  mov     r10d, edi
  ... truncated ...
```
