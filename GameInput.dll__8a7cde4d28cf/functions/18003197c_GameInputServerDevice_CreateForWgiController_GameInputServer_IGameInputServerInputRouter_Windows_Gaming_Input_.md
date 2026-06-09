# GameInputServerDevice::CreateForWgiController(GameInputServer *,IGameInputServerInputRouter *,Windows::Gaming::Input::IRawGameController *,GameInputServerDevice * *)

- ea: `0x18003197c`
- end: `0x18003ac3a`
- name: `?CreateForWgiController@GameInputServerDevice@@SAJPEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEAUIRawGameController@Input@Gaming@Windows@@PEAPEAV1@@Z`
- size: `37566`
- prototype: `__int64 __fastcall(struct GameInputServer *, struct IGameInputServerInputRouter *, struct Windows::Gaming::Input::IRawGameController *, struct GameInputServerDevice **)`
- caller_count: `1`
- callee_count: `78`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ee94`

## callees

- `0x180001008`
- `0x180001304`
- `0x1800013c8`
- `0x1800013d8`
- `0x1800013e8`
- `0x1800023a4`
- `0x18000248c`
- `0x180002584`
- `0x18000391c`
- `0x1800041c4`
- `0x180004260`
- `0x1800042dc`
- `0x1800042e8`
- `0x1800042f4`
- `0x180004300`
- `0x180007050`
- `0x18000c00c`
- `0x18000c0f8`
- `0x180012684`
- `0x1800149dc`
- `0x1800230d8`
- `0x18002312c`
- `0x1800231fc`
- `0x1800232b4`
- `0x180023558`
- `0x180023c4c`
- `0x180023db0`
- `0x18002cc78`
- `0x18002cc88`
- `0x18002cd80`
- `0x18002cda0`
- `0x18002cdd4`
- `0x18002ce50`
- `0x18002d1c8`
- `0x18002d380`
- `0x18002d4a4`
- `0x18002d4e0`
- `0x18002d610`
- `0x18002dd4c`
- `0x18002de48`
- `0x18002dea0`
- `0x18002deb4`
- `0x18002dee8`
- `0x18002e010`
- `0x18002e020`
- `0x18002e02c`
- `0x18002e06c`
- `0x18002e214`
- `0x18002e24c`
- `0x18002e274`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800319e0`
- `ntdll!RtlAllocateHeap` at `0x1800319e0`
- `ntdll!wcsncpy_s` at `0x180039a92`
- `ntdll!wcsncpy_s` at `0x180039a92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800334ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800334ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031c2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031d09`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031de6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031ec2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031f9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031c2f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031d09`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031de6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031ec2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039a61`

## pseudocode

```c
__int64 __fastcall GameInputServerDevice::CreateForWgiController(
        struct GameInputServer *a1,
        struct IGameInputServerInputRouter *a2,
        struct Windows::Gaming::Input::IRawGameController *a3,
        struct GameInputServerDevice **a4)
{
  GameInputServerDevice *Heap; // rax
  __int64 v8; // rdx
  int v9; // ebx
  int ActivationFactory; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 *v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  bool v61; // bl
  char v62; // bl
  char v63; // bl
  bool v64; // bl
  bool v65; // bl
  bool v66; // bl
  bool v67; // bl
  bool v68; // bl
  bool v69; // bl
  __int64 v70; // rax
  __int64 v71; // rax
  unsigned int v72; // eax
  __int64 v73; // rax
  _QWORD *v74; // rax
  LPVOID *v75; // rax
  __int64 v76; // rdi
  int (__fastcall *v77)(__int64, __int64); // rbx
  __int64 v78; // rax
  __int64 v79; // rax
  _QWORD *v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rbx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  struct XusbWatcher **v87; // rdi
  __int64 (__fastcall ***v88)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *); // rbx
  struct GameInputServerDevice *v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rdi
  __int64 (__fastcall *v97)(__int64, HSTRING *); // rbx
  HSTRING *AddressOf; // rax
  __int64 v99; // rax
  Microsoft::WRL::Wrappers::HString *v100; // rcx
  __int64 v101; // rdi
  __int64 (__fastcall *v102)(__int64, HSTRING *); // rbx
  HSTRING *v103; // rax
  __int64 v104; // rax
  UCHAR *RawBuffer; // rax
  __int64 v106; // rax
  UCHAR *v107; // rax
  __int64 v108; // rax
  __int64 v109; // rdi
  __int64 (__fastcall *v110)(__int64, _QWORD, UCHAR *); // rbx
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rbx
  __int64 v115; // rax
  unsigned int v116; // ebx
  __int16 v117; // ax
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int16 v122; // ax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rdi
  __int64 (__fastcall *v126)(__int64, HSTRING *); // rbx
  HSTRING *v127; // rax
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 v130; // rdi
  __int64 (__fastcall *v131)(__int64, __int64); // rbx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rdi
  __int64 (__fastcall *v135)(__int64, __int64); // rbx
  __int64 v136; // rax
  __int64 v137; // rax
  __int64 v138; // rdi
  __int64 (__fastcall *v139)(__int64, __int64); // rbx
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  unsigned int v144; // edi
  __int64 v145; // rax
  unsigned int v146; // ebx
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 v151; // rax
  __int64 v152; // rax
  int v153; // edi
  __int64 v154; // rbx
  unsigned __int64 v155; // rax
  void *v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  __int64 v159; // rbx
  void *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rbx
  unsigned __int64 v164; // rax
  void *v165; // rax
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rax
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rax
  __int64 v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rax
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rax
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rax
  __int64 v202; // rax
  __int64 v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // rax
  __int64 v207; // rax
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 v216; // rax
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rax
  __int64 v222; // rax
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 v225; // rax
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // rax
  __int64 v229; // rax
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // rax
  __int64 v234; // rax
  __int64 v235; // rax
  __int64 v236; // rax
  __int64 v237; // rax
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rax
  __int64 v242; // rax
  __int64 v243; // rax
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // rax
  __int64 v248; // rax
  __int64 v249; // rax
  __int64 v250; // rax
  __int64 v251; // rax
  __int64 v252; // rax
  __int64 v253; // rax
  __int64 v254; // rax
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // rax
  __int64 v260; // rax
  __int64 v261; // rax
  __int64 v262; // rax
  __int64 v263; // rax
  __int64 v264; // rax
  int v265; // eax
  __int64 v266; // rax
  __int64 v267; // rax
  __int64 v268; // rax
  __int64 v269; // rax
  __int64 v270; // rax
  __int64 v271; // rax
  __int64 v272; // rax
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rax
  __int64 v277; // rax
  __int64 v278; // rax
  __int64 v279; // rax
  __int64 v280; // rax
  __int64 v281; // rax
  __int64 v282; // rax
  __int64 v283; // rax
  __int64 v284; // rax
  __int64 v285; // rax
  __int64 v286; // rax
  __int64 v287; // rax
  __int64 v288; // rax
  __int64 v289; // rax
  __int64 v290; // rax
  __int64 v291; // rax
  __int64 v292; // rax
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rax
  __int64 v296; // rax
  __int64 v297; // rax
  __int64 v298; // rax
  __int64 v299; // rax
  __int64 v300; // rax
  __int64 v301; // rax
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rax
  __int64 v305; // rax
  __int64 v306; // rax
  __int64 v307; // rax
  __int64 v308; // rax
  __int64 v309; // rax
  bool v310; // bl
  __int64 v311; // rax
  __int64 v312; // rax
  int v313; // eax
  __int64 v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  __int64 v317; // rax
  HANDLE **v318; // rbx
  struct IGameInputServerDevice *v319; // rax
  __int64 v320; // rax
  __int64 v321; // rax
  __int64 v322; // rax
  FeedbackManager *v323; // rax
  const struct FeedbackDeviceInfo *DeviceInfo; // rbx
  __int64 v325; // rax
  __int64 v326; // rax
  __int64 v327; // rax
  __int64 v328; // rax
  char *v329; // rax
  char *v330; // rsi
  __int64 v331; // rdi
  __int64 (__fastcall *v332)(__int64, __int64); // rbx
  __int64 v333; // rax
  __int64 v334; // rax
  HSTRING v335; // rax
  const wchar_t *StringRawBuffer; // rax
  __int64 v337; // rax
  __int64 v338; // rbx
  __int64 v339; // rax
  __int64 v340; // rax
  __int64 v341; // rbx
  CallbackDataLayout *v342; // rax
  __int64 v343; // rax
  __int64 v344; // rax
  ReadingDataLayout *v345; // rax
  ReadingDataLayout *v346; // rdi
  struct GameInputDeviceInfo *v347; // rbx
  __int64 v348; // rax
  __int64 v349; // rax
  __int64 v350; // rax
  InputDataLayout *v351; // rax
  InputDataLayout *v352; // rdi
  struct GameInputDeviceInfo *v353; // rbx
  __int64 v354; // rax
  const struct ReadingDataLayout *v355; // rax
  __int64 v356; // rax
  __int64 v357; // rax
  __int64 v358; // rax
  __int64 v359; // rax
  FeedbackManager *v360; // rax
  const struct FeedbackDeviceInfo *v361; // rbx
  __int64 v362; // rdi
  FeedbackDataLayout *v363; // rax
  __int64 v364; // rax
  __int64 v365; // rax
  SharedBufferLayout *v366; // rax
  __int64 v367; // rax
  __int64 v368; // rax
  struct GameInputDeviceInfo *v369; // rsi
  const struct FeedbackDataLayout *v370; // rdi
  __int64 v371; // rax
  const struct InputDataLayout *v372; // rbx
  __int64 v373; // rax
  const struct CallbackDataLayout *v374; // rax
  __int64 v375; // rax
  __int64 v376; // rax
  __int64 v377; // rax
  LayoutBase *v378; // rax
  unsigned int RequiredBufferSize; // ebx
  __int64 v380; // rbx
  __int64 v381; // rax
  void *v382; // rax
  __int64 v383; // rax
  __int64 v384; // rax
  unsigned int v385; // ebx
  __int64 v386; // rax
  void *v387; // rax
  __int64 v388; // rax
  ReadingDataLayout *v389; // rbx
  __int64 v390; // rax
  void *v391; // rax
  struct GameInputCommonReadingData *CommonDataPtr; // rbx
  unsigned int v393; // eax
  __int64 v394; // rbx
  __int64 v395; // rax
  void *v396; // rax
  __int64 v397; // rax
  __int64 v398; // rax
  __int64 v399; // rbx
  __int64 v400; // rax
  void *v401; // rax
  __int64 v402; // rax
  __int64 v403; // rax
  GameInputServerDevice *v404; // rax
  unsigned int v405; // ebx
  __int64 v406; // rax
  __int64 v407; // rbx
  __int64 v408; // rdi
  void *v409; // rax
  __int64 v410; // rax
  __int64 v411; // rax
  struct IGameInputServerInputRouter *v412; // r15
  unsigned __int8 (__fastcall *v413)(struct IGameInputServerInputRouter *, _QWORD, __int64, __int64, int); // r14
  char v414; // si
  char v415; // di
  char v416; // bl
  __int64 v417; // rax
  unsigned int v418; // eax
  __int64 v419; // r9
  __int64 v420; // r8
  __int64 v421; // rax
  GameInputServerDevice *v422; // rax
  __int64 v423; // rax
  __int64 v425; // rax
  __int64 v426; // rax
  __int64 v427; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v429; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v430; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v431; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v432)(_QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v433)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v434)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v435; // [rsp+80h] [rbp-80h] BYREF
  __int64 v436; // [rsp+88h] [rbp-78h] BYREF
  __int64 v437; // [rsp+90h] [rbp-70h] BYREF
  __int64 v438; // [rsp+98h] [rbp-68h] BYREF
  __int64 v439; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v440; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v441; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v442; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v443; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v444; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v445; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v446; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v447; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v448[8]; // [rsp+E8h] [rbp-18h] BYREF
  GameInputServerDevice *v449; // [rsp+F0h] [rbp-10h] BYREF
  char v450; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v451[7]; // [rsp+F9h] [rbp-7h] BYREF
  _BYTE v452[8]; // [rsp+100h] [rbp+0h] BYREF
  char v453; // [rsp+108h] [rbp+8h] BYREF
  char v454; // [rsp+109h] [rbp+9h] BYREF
  char v455; // [rsp+10Ah] [rbp+Ah] BYREF
  char v456; // [rsp+10Bh] [rbp+Bh] BYREF
  _BYTE v457[4]; // [rsp+10Ch] [rbp+Ch] BYREF
  __int64 v458; // [rsp+110h] [rbp+10h] BYREF
  char v459; // [rsp+118h] [rbp+18h] BYREF
  char v460; // [rsp+119h] [rbp+19h] BYREF
  char v461; // [rsp+11Ah] [rbp+1Ah] BYREF
  char v462; // [rsp+11Bh] [rbp+1Bh] BYREF
  char v463; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v464[3]; // [rsp+11Dh] [rbp+1Dh] BYREF
  unsigned int v465; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v466; // [rsp+124h] [rbp+24h] BYREF
  unsigned __int16 v467[2]; // [rsp+128h] [rbp+28h] BYREF
  UINT32 length; // [rsp+12Ch] [rbp+2Ch] BYREF
  unsigned int v469; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v470; // [rsp+134h] [rbp+34h] BYREF
  unsigned int v471; // [rsp+138h] [rbp+38h] BYREF
  GUID v472; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v473; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v474[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v475[8]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v476[8]; // [rsp+168h] [rbp+68h] BYREF
  struct GameInputDeviceInfo *v477; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v478; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v479; // [rsp+17Ch] [rbp+7Ch] BYREF
  unsigned int v480; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v481; // [rsp+184h] [rbp+84h] BYREF
  unsigned int v482; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v483; // [rsp+18Ch] [rbp+8Ch] BYREF
  unsigned int v484; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v485; // [rsp+194h] [rbp+94h] BYREF
  int v486; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v487[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v488[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v489[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v490; // [rsp+1B8h] [rbp+B8h] BYREF
  int v491; // [rsp+1BCh] [rbp+BCh] BYREF
  int v492; // [rsp+1C0h] [rbp+C0h] BYREF
  int v493; // [rsp+1C4h] [rbp+C4h] BYREF
  int v494; // [rsp+1C8h] [rbp+C8h] BYREF
  int v495; // [rsp+1CCh] [rbp+CCh] BYREF
  int v496; // [rsp+1D0h] [rbp+D0h] BYREF
  int v497; // [rsp+1D4h] [rbp+D4h] BYREF
  int v498; // [rsp+1D8h] [rbp+D8h] BYREF
  int v499; // [rsp+1DCh] [rbp+DCh] BYREF
  int v500; // [rsp+1E0h] [rbp+E0h] BYREF
  int v501; // [rsp+1E4h] [rbp+E4h] BYREF
  int v502; // [rsp+1E8h] [rbp+E8h] BYREF
  int v503; // [rsp+1ECh] [rbp+ECh] BYREF
  int v504; // [rsp+1F0h] [rbp+F0h] BYREF
  int v505; // [rsp+1F4h] [rbp+F4h] BYREF
  int v506; // [rsp+1F8h] [rbp+F8h] BYREF
  int AppLocalDeviceId; // [rsp+1FCh] [rbp+FCh] BYREF
  int v508; // [rsp+200h] [rbp+100h] BYREF
  int v509; // [rsp+204h] [rbp+104h] BYREF
  int v510; // [rsp+208h] [rbp+108h] BYREF
  int v511; // [rsp+20Ch] [rbp+10Ch] BYREF
  int v512; // [rsp+210h] [rbp+110h] BYREF
  unsigned int v513[2]; // [rsp+214h] [rbp+114h] BYREF
  int v514; // [rsp+21Ch] [rbp+11Ch] BYREF
  int v515; // [rsp+220h] [rbp+120h] BYREF
  int v516; // [rsp+224h] [rbp+124h] BYREF
  int v517; // [rsp+228h] [rbp+128h] BYREF
  int v518; // [rsp+22Ch] [rbp+12Ch] BYREF
  int v519; // [rsp+230h] [rbp+130h] BYREF
  int v520; // [rsp+234h] [rbp+134h] BYREF
  int v521; // [rsp+238h] [rbp+138h] BYREF
  int v522; // [rsp+23Ch] [rbp+13Ch] BYREF
  int v523; // [rsp+240h] [rbp+140h] BYREF
  int v524; // [rsp+244h] [rbp+144h] BYREF
  int v525; // [rsp+248h] [rbp+148h] BYREF
  int v526; // [rsp+24Ch] [rbp+14Ch] BYREF
  int v527; // [rsp+250h] [rbp+150h] BYREF
  int v528; // [rsp+254h] [rbp+154h] BYREF
  int v529; // [rsp+258h] [rbp+158h] BYREF
  int v530; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v531; // [rsp+260h] [rbp+160h] BYREF
  int v532; // [rsp+264h] [rbp+164h] BYREF
  int v533; // [rsp+268h] [rbp+168h] BYREF
  int v534; // [rsp+26Ch] [rbp+16Ch] BYREF
  int v535; // [rsp+270h] [rbp+170h] BYREF
  int v536; // [rsp+274h] [rbp+174h] BYREF
  int v537; // [rsp+278h] [rbp+178h] BYREF
  unsigned int v538; // [rsp+27Ch] [rbp+17Ch] BYREF
  unsigned int v539; // [rsp+280h] [rbp+180h] BYREF
  unsigned int v540; // [rsp+284h] [rbp+184h] BYREF
  unsigned int v541; // [rsp+288h] [rbp+188h] BYREF
  unsigned int v542; // [rsp+28Ch] [rbp+18Ch] BYREF
  unsigned int v543; // [rsp+290h] [rbp+190h] BYREF
  unsigned int v544; // [rsp+294h] [rbp+194h] BYREF
  unsigned int v545; // [rsp+298h] [rbp+198h] BYREF
  unsigned int v546; // [rsp+29Ch] [rbp+19Ch] BYREF
  unsigned int v547; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned int v548; // [rsp+2A4h] [rbp+1A4h] BYREF
  unsigned int v549; // [rsp+2A8h] [rbp+1A8h] BYREF
  unsigned int v550; // [rsp+2ACh] [rbp+1ACh] BYREF
  unsigned int v551; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned int v552; // [rsp+2B4h] [rbp+1B4h] BYREF
  unsigned int v553; // [rsp+2B8h] [rbp+1B8h] BYREF
  unsigned int v554; // [rsp+2BCh] [rbp+1BCh] BYREF
  unsigned int v555; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned int v556; // [rsp+2C4h] [rbp+1C4h] BYREF
  unsigned int v557; // [rsp+2C8h] [rbp+1C8h] BYREF
  unsigned int v558; // [rsp+2CCh] [rbp+1CCh] BYREF
  unsigned int v559; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v560; // [rsp+2D4h] [rbp+1D4h] BYREF
  int v561; // [rsp+2D8h] [rbp+1D8h] BYREF
  int v562; // [rsp+2DCh] [rbp+1DCh] BYREF
  int v563; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v564; // [rsp+2E4h] [rbp+1E4h] BYREF
  int v565; // [rsp+2E8h] [rbp+1E8h] BYREF
  int v566; // [rsp+2ECh] [rbp+1ECh] BYREF
  int v567; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v568; // [rsp+2F4h] [rbp+1F4h] BYREF
  int v569; // [rsp+2F8h] [rbp+1F8h] BYREF
  int v570; // [rsp+2FCh] [rbp+1FCh] BYREF
  int v571; // [rsp+300h] [rbp+200h] BYREF
  int v572; // [rsp+304h] [rbp+204h] BYREF
  int v573; // [rsp+308h] [rbp+208h] BYREF
  unsigned int v574; // [rsp+30Ch] [rbp+20Ch] BYREF
  unsigned int v575; // [rsp+310h] [rbp+210h] BYREF
  unsigned int v576; // [rsp+314h] [rbp+214h] BYREF
  unsigned int v577; // [rsp+318h] [rbp+218h] BYREF
  unsigned int v578; // [rsp+31Ch] [rbp+21Ch] BYREF
  unsigned int v579; // [rsp+320h] [rbp+220h] BYREF
  int v580; // [rsp+324h] [rbp+224h] BYREF
  int v581; // [rsp+328h] [rbp+228h] BYREF
  int v582; // [rsp+32Ch] [rbp+22Ch] BYREF
  int v583; // [rsp+330h] [rbp+230h] BYREF
  int v584; // [rsp+334h] [rbp+234h] BYREF
  int v585; // [rsp+338h] [rbp+238h] BYREF
  int v586; // [rsp+33Ch] [rbp+23Ch] BYREF
  int v587; // [rsp+340h] [rbp+240h] BYREF
  int v588; // [rsp+344h] [rbp+244h] BYREF
  int v589; // [rsp+348h] [rbp+248h] BYREF
  int v590; // [rsp+34Ch] [rbp+24Ch] BYREF
  int v591; // [rsp+350h] [rbp+250h] BYREF
  int v592; // [rsp+354h] [rbp+254h] BYREF
  int v593; // [rsp+358h] [rbp+258h] BYREF
  int v594; // [rsp+35Ch] [rbp+25Ch] BYREF
  int v595; // [rsp+360h] [rbp+260h] BYREF
  int v596; // [rsp+364h] [rbp+264h] BYREF
  int v597; // [rsp+368h] [rbp+268h] BYREF
  int v598; // [rsp+36Ch] [rbp+26Ch] BYREF
  int v599; // [rsp+370h] [rbp+270h] BYREF
  int v600; // [rsp+374h] [rbp+274h] BYREF
  int v601; // [rsp+378h] [rbp+278h] BYREF
  unsigned int v602; // [rsp+37Ch] [rbp+27Ch] BYREF
  unsigned int v603; // [rsp+380h] [rbp+280h] BYREF
  int v604; // [rsp+384h] [rbp+284h] BYREF
  unsigned int v605; // [rsp+388h] [rbp+288h] BYREF
  unsigned int v606; // [rsp+38Ch] [rbp+28Ch] BYREF
  unsigned int v607; // [rsp+390h] [rbp+290h] BYREF
  unsigned int v608; // [rsp+394h] [rbp+294h] BYREF
  unsigned int v609; // [rsp+398h] [rbp+298h] BYREF
  unsigned int v610; // [rsp+39Ch] [rbp+29Ch] BYREF
  unsigned int v611; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned int v612; // [rsp+3A4h] [rbp+2A4h] BYREF
  unsigned int v613; // [rsp+3A8h] [rbp+2A8h] BYREF
  unsigned int v614; // [rsp+3ACh] [rbp+2ACh] BYREF
  unsigned int v615; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned int v616; // [rsp+3B4h] [rbp+2B4h] BYREF
  unsigned int v617; // [rsp+3B8h] [rbp+2B8h] BYREF
  unsigned int v618; // [rsp+3BCh] [rbp+2BCh] BYREF
  unsigned int v619; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned int v620; // [rsp+3C4h] [rbp+2C4h] BYREF
  unsigned int v621; // [rsp+3C8h] [rbp+2C8h] BYREF
  int v622; // [rsp+3CCh] [rbp+2CCh] BYREF
  int v623; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v624; // [rsp+3D4h] [rbp+2D4h] BYREF
  int v625; // [rsp+3D8h] [rbp+2D8h] BYREF
  int v626; // [rsp+3DCh] [rbp+2DCh] BYREF
  int v627; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v628; // [rsp+3E4h] [rbp+2E4h] BYREF
  int v629; // [rsp+3E8h] [rbp+2E8h] BYREF
  int v630; // [rsp+3ECh] [rbp+2ECh] BYREF
  int v631; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v632; // [rsp+3F4h] [rbp+2F4h] BYREF
  int v633; // [rsp+3F8h] [rbp+2F8h] BYREF
  int v634; // [rsp+3FCh] [rbp+2FCh] BYREF
  int v635; // [rsp+400h] [rbp+300h] BYREF
  int v636; // [rsp+404h] [rbp+304h] BYREF
  int v637; // [rsp+408h] [rbp+308h] BYREF
  int v638; // [rsp+40Ch] [rbp+30Ch] BYREF
  int v639; // [rsp+410h] [rbp+310h] BYREF
  int v640; // [rsp+414h] [rbp+314h] BYREF
  int v641; // [rsp+418h] [rbp+318h] BYREF
  int v642; // [rsp+41Ch] [rbp+31Ch] BYREF
  int v643; // [rsp+420h] [rbp+320h] BYREF
  int v644; // [rsp+424h] [rbp+324h] BYREF
  int v645; // [rsp+428h] [rbp+328h] BYREF
  int v646; // [rsp+42Ch] [rbp+32Ch] BYREF
  unsigned int v647; // [rsp+430h] [rbp+330h] BYREF
  unsigned int v648; // [rsp+434h] [rbp+334h] BYREF
  int v649; // [rsp+438h] [rbp+338h] BYREF
  int v650; // [rsp+43Ch] [rbp+33Ch] BYREF
  int v651; // [rsp+440h] [rbp+340h] BYREF
  int v652; // [rsp+444h] [rbp+344h] BYREF
  int v653; // [rsp+448h] [rbp+348h] BYREF
  int v654; // [rsp+44Ch] [rbp+34Ch] BYREF
  unsigned int v655; // [rsp+450h] [rbp+350h] BYREF
  unsigned int v656; // [rsp+454h] [rbp+354h] BYREF
  unsigned int v657; // [rsp+458h] [rbp+358h] BYREF
  unsigned int v658; // [rsp+45Ch] [rbp+35Ch] BYREF
  int v659; // [rsp+460h] [rbp+360h] BYREF
  int v660; // [rsp+464h] [rbp+364h] BYREF
  SharedBufferLayout *v661; // [rsp+468h] [rbp+368h]
  unsigned int v662; // [rsp+470h] [rbp+370h] BYREF
  int v663; // [rsp+474h] [rbp+374h] BYREF
  int v664; // [rsp+478h] [rbp+378h] BYREF
  int v665; // [rsp+47Ch] [rbp+37Ch] BYREF
  _BYTE v666[4]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v667[4]; // [rsp+484h] [rbp+384h] BYREF
  int v668; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v669[4]; // [rsp+48Ch] [rbp+38Ch] BYREF
  _BYTE v670[4]; // [rsp+490h] [rbp+390h] BYREF
  int v671; // [rsp+494h] [rbp+394h] BYREF
  _BYTE v672[4]; // [rsp+498h] [rbp+398h] BYREF
  _BYTE v673[4]; // [rsp+49Ch] [rbp+39Ch] BYREF
  int v674; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v675[4]; // [rsp+4A4h] [rbp+3A4h] BYREF
  _BYTE v676[4]; // [rsp+4A8h] [rbp+3A8h] BYREF
  int v677; // [rsp+4ACh] [rbp+3ACh] BYREF
  _BYTE v678[4]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v679[4]; // [rsp+4B4h] [rbp+3B4h] BYREF
  int v680; // [rsp+4B8h] [rbp+3B8h] BYREF
  _BYTE v681[4]; // [rsp+4BCh] [rbp+3BCh] BYREF
  _BYTE v682[4]; // [rsp+4C0h] [rbp+3C0h] BYREF
  int v683; // [rsp+4C4h] [rbp+3C4h] BYREF
  _BYTE v684[4]; // [rsp+4C8h] [rbp+3C8h] BYREF
  _BYTE v685[4]; // [rsp+4CCh] [rbp+3CCh] BYREF
  int v686; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v687[4]; // [rsp+4D4h] [rbp+3D4h] BYREF
  _BYTE v688[4]; // [rsp+4D8h] [rbp+3D8h] BYREF
  int v689; // [rsp+4DCh] [rbp+3DCh] BYREF
  _BYTE v690[4]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v691[4]; // [rsp+4E4h] [rbp+3E4h] BYREF
  int v692; // [rsp+4E8h] [rbp+3E8h] BYREF
  _BYTE v693[4]; // [rsp+4ECh] [rbp+3ECh] BYREF
  _BYTE v694[4]; // [rsp+4F0h] [rbp+3F0h] BYREF
  int v695; // [rsp+4F4h] [rbp+3F4h] BYREF
  _BYTE v696[4]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v697[4]; // [rsp+4FCh] [rbp+3FCh] BYREF
  int v698; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v699[4]; // [rsp+504h] [rbp+404h] BYREF
  _BYTE v700[4]; // [rsp+508h] [rbp+408h] BYREF
  int v701; // [rsp+50Ch] [rbp+40Ch] BYREF
  _BYTE v702[4]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v703[4]; // [rsp+514h] [rbp+414h] BYREF
  int v704; // [rsp+518h] [rbp+418h] BYREF
  _BYTE v705[4]; // [rsp+51Ch] [rbp+41Ch] BYREF
  int v706; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v707[4]; // [rsp+524h] [rbp+424h] BYREF
  _BYTE v708[4]; // [rsp+528h] [rbp+428h] BYREF
  int v709; // [rsp+52Ch] [rbp+42Ch] BYREF
  _BYTE v710[4]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v711[4]; // [rsp+534h] [rbp+434h] BYREF
  int v712; // [rsp+538h] [rbp+438h] BYREF
  _BYTE v713[4]; // [rsp+53Ch] [rbp+43Ch] BYREF
  _BYTE v714[4]; // [rsp+540h] [rbp+440h] BYREF
  int v715; // [rsp+544h] [rbp+444h] BYREF
  _BYTE v716[4]; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v717[4]; // [rsp+54Ch] [rbp+44Ch] BYREF
  int v718; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v719[4]; // [rsp+554h] [rbp+454h] BYREF
  _BYTE v720[4]; // [rsp+558h] [rbp+458h] BYREF
  int v721; // [rsp+55Ch] [rbp+45Ch] BYREF
  _BYTE v722[4]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v723[4]; // [rsp+564h] [rbp+464h] BYREF
  int v724; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v725[4]; // [rsp+56Ch] [rbp+46Ch] BYREF
  _BYTE v726[4]; // [rsp+570h] [rbp+470h] BYREF
  int v727; // [rsp+574h] [rbp+474h] BYREF
  _BYTE v728[4]; // [rsp+578h] [rbp+478h] BYREF
  _BYTE v729[4]; // [rsp+57Ch] [rbp+47Ch] BYREF
  int v730; // [rsp+580h] [rbp+480h] BYREF
  int v731; // [rsp+584h] [rbp+484h] BYREF
  _BYTE v732[4]; // [rsp+588h] [rbp+488h] BYREF
  _BYTE v733[4]; // [rsp+58Ch] [rbp+48Ch] BYREF
  int v734; // [rsp+590h] [rbp+490h] BYREF
  _BYTE v735[4]; // [rsp+594h] [rbp+494h] BYREF
  _BYTE v736[4]; // [rsp+598h] [rbp+498h] BYREF
  int v737; // [rsp+59Ch] [rbp+49Ch] BYREF
  _BYTE v738[4]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v739[4]; // [rsp+5A4h] [rbp+4A4h] BYREF
  int v740; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v741[4]; // [rsp+5ACh] [rbp+4ACh] BYREF
  _BYTE v742[4]; // [rsp+5B0h] [rbp+4B0h] BYREF
  int v743; // [rsp+5B4h] [rbp+4B4h] BYREF
  _BYTE v744[4]; // [rsp+5B8h] [rbp+4B8h] BYREF
  _BYTE v745[4]; // [rsp+5BCh] [rbp+4BCh] BYREF
  int v746; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v747[4]; // [rsp+5C4h] [rbp+4C4h] BYREF
  _BYTE v748[4]; // [rsp+5C8h] [rbp+4C8h] BYREF
  int v749; // [rsp+5CCh] [rbp+4CCh] BYREF
  _BYTE v750[4]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v751[4]; // [rsp+5D4h] [rbp+4D4h] BYREF
  int v752; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v753[4]; // [rsp+5DCh] [rbp+4DCh] BYREF
  _BYTE v754[4]; // [rsp+5E0h] [rbp+4E0h] BYREF
  int v755; // [rsp+5E4h] [rbp+4E4h] BYREF
  _BYTE v756[4]; // [rsp+5E8h] [rbp+4E8h] BYREF
  _BYTE v757[4]; // [rsp+5ECh] [rbp+4ECh] BYREF
  int v758; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v759[4]; // [rsp+5F4h] [rbp+4F4h] BYREF
  _BYTE v760[4]; // [rsp+5F8h] [rbp+4F8h] BYREF
  int v761; // [rsp+5FCh] [rbp+4FCh] BYREF
  _BYTE v762[4]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v763[4]; // [rsp+604h] [rbp+504h] BYREF
  int v764; // [rsp+608h] [rbp+508h] BYREF
  _BYTE v765[4]; // [rsp+60Ch] [rbp+50Ch] BYREF
  _BYTE v766[4]; // [rsp+610h] [rbp+510h] BYREF
  int v767; // [rsp+614h] [rbp+514h] BYREF
  _BYTE v768[4]; // [rsp+618h] [rbp+518h] BYREF
  _BYTE v769[4]; // [rsp+61Ch] [rbp+51Ch] BYREF
  int v770; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v771[4]; // [rsp+624h] [rbp+524h] BYREF
  _BYTE v772[4]; // [rsp+628h] [rbp+528h] BYREF
  int v773; // [rsp+62Ch] [rbp+52Ch] BYREF
  _BYTE v774[4]; // [rsp+630h] [rbp+530h] BYREF
  _BYTE v775[4]; // [rsp+634h] [rbp+534h] BYREF
  int v776; // [rsp+638h] [rbp+538h] BYREF
  _BYTE v777[4]; // [rsp+63Ch] [rbp+53Ch] BYREF
  _BYTE v778[4]; // [rsp+640h] [rbp+540h] BYREF
  int v779; // [rsp+644h] [rbp+544h] BYREF
  int v780; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v781[4]; // [rsp+64Ch] [rbp+54Ch] BYREF
  _BYTE v782[4]; // [rsp+650h] [rbp+550h] BYREF
  int v783; // [rsp+654h] [rbp+554h] BYREF
  int v784; // [rsp+658h] [rbp+558h] BYREF
  _BYTE v785[4]; // [rsp+65Ch] [rbp+55Ch] BYREF
  _BYTE v786[4]; // [rsp+660h] [rbp+560h] BYREF
  int v787; // [rsp+664h] [rbp+564h] BYREF
  int v788; // [rsp+668h] [rbp+568h] BYREF
  _BYTE v789[4]; // [rsp+66Ch] [rbp+56Ch] BYREF
  _BYTE v790[4]; // [rsp+670h] [rbp+570h] BYREF
  int v791; // [rsp+674h] [rbp+574h] BYREF
  _BYTE v792[4]; // [rsp+678h] [rbp+578h] BYREF
  _BYTE v793[4]; // [rsp+67Ch] [rbp+57Ch] BYREF
  int v794; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v795[4]; // [rsp+684h] [rbp+584h] BYREF
  _BYTE v796[4]; // [rsp+688h] [rbp+588h] BYREF
  int v797; // [rsp+68Ch] [rbp+58Ch] BYREF
  _BYTE v798[4]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v799[4]; // [rsp+694h] [rbp+594h] BYREF
  int v800; // [rsp+698h] [rbp+598h] BYREF
  _BYTE v801[4]; // [rsp+69Ch] [rbp+59Ch] BYREF
  _BYTE v802[4]; // [rsp+6A0h] [rbp+5A0h] BYREF
  int v803; // [rsp+6A4h] [rbp+5A4h] BYREF
  _BYTE v804[4]; // [rsp+6A8h] [rbp+5A8h] BYREF
  _BYTE v805[4]; // [rsp+6ACh] [rbp+5ACh] BYREF
  int v806; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v807[4]; // [rsp+6B4h] [rbp+5B4h] BYREF
  _BYTE v808[4]; // [rsp+6B8h] [rbp+5B8h] BYREF
  int v809; // [rsp+6BCh] [rbp+5BCh] BYREF
  _BYTE v810[4]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v811[4]; // [rsp+6C4h] [rbp+5C4h] BYREF
  int v812; // [rsp+6C8h] [rbp+5C8h] BYREF
  _BYTE v813[4]; // [rsp+6CCh] [rbp+5CCh] BYREF
  _BYTE v814[4]; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v815; // [rsp+6D4h] [rbp+5D4h] BYREF
  _BYTE v816[4]; // [rsp+6D8h] [rbp+5D8h] BYREF
  _BYTE v817[4]; // [rsp+6DCh] [rbp+5DCh] BYREF
  int v818; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v819[4]; // [rsp+6E4h] [rbp+5E4h] BYREF
  _BYTE v820[4]; // [rsp+6E8h] [rbp+5E8h] BYREF
  int v821; // [rsp+6ECh] [rbp+5ECh] BYREF
  _BYTE v822[4]; // [rsp+6F0h] [rbp+5F0h] BYREF
  _BYTE v823[4]; // [rsp+6F4h] [rbp+5F4h] BYREF
  int v824; // [rsp+6F8h] [rbp+5F8h] BYREF
  _BYTE v825[4]; // [rsp+6FCh] [rbp+5FCh] BYREF
  _BYTE v826[4]; // [rsp+700h] [rbp+600h] BYREF
  int v827; // [rsp+704h] [rbp+604h] BYREF
  _BYTE v828[4]; // [rsp+708h] [rbp+608h] BYREF
  _BYTE v829[4]; // [rsp+70Ch] [rbp+60Ch] BYREF
  int v830; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v831[4]; // [rsp+714h] [rbp+614h] BYREF
  _BYTE v832[4]; // [rsp+718h] [rbp+618h] BYREF
  int v833; // [rsp+71Ch] [rbp+61Ch] BYREF
  _BYTE v834[4]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v835[4]; // [rsp+724h] [rbp+624h] BYREF
  int v836; // [rsp+728h] [rbp+628h] BYREF
  _BYTE v837[4]; // [rsp+72Ch] [rbp+62Ch] BYREF
  _BYTE v838[4]; // [rsp+730h] [rbp+630h] BYREF
  int v839; // [rsp+734h] [rbp+634h] BYREF
  _BYTE v840[4]; // [rsp+738h] [rbp+638h] BYREF
  _BYTE v841[4]; // [rsp+73Ch] [rbp+63Ch] BYREF
  int v842; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v843[4]; // [rsp+744h] [rbp+644h] BYREF
  _BYTE v844[4]; // [rsp+748h] [rbp+648h] BYREF
  int v845; // [rsp+74Ch] [rbp+64Ch] BYREF
  _BYTE v846[4]; // [rsp+750h] [rbp+650h] BYREF
  _BYTE v847[4]; // [rsp+754h] [rbp+654h] BYREF
  int v848; // [rsp+758h] [rbp+658h] BYREF
  _BYTE v849[4]; // [rsp+75Ch] [rbp+65Ch] BYREF
  _BYTE v850[4]; // [rsp+760h] [rbp+660h] BYREF
  int v851; // [rsp+764h] [rbp+664h] BYREF
  _BYTE v852[4]; // [rsp+768h] [rbp+668h] BYREF
  _BYTE v853[4]; // [rsp+76Ch] [rbp+66Ch] BYREF
  int v854; // [rsp+770h] [rbp+670h] BYREF
  _BYTE v855[4]; // [rsp+774h] [rbp+674h] BYREF
  _BYTE v856[4]; // [rsp+778h] [rbp+678h] BYREF
  int v857; // [rsp+77Ch] [rbp+67Ch] BYREF
  _BYTE v858[4]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v859[4]; // [rsp+784h] [rbp+684h] BYREF
  int v860; // [rsp+788h] [rbp+688h] BYREF
  _BYTE v861[4]; // [rsp+78Ch] [rbp+68Ch] BYREF
  _BYTE v862[4]; // [rsp+790h] [rbp+690h] BYREF
  int v863; // [rsp+794h] [rbp+694h] BYREF
  _BYTE v864[4]; // [rsp+798h] [rbp+698h] BYREF
  _BYTE v865[4]; // [rsp+79Ch] [rbp+69Ch] BYREF
  int v866; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v867[4]; // [rsp+7A4h] [rbp+6A4h] BYREF
  _BYTE v868[4]; // [rsp+7A8h] [rbp+6A8h] BYREF
  int v869; // [rsp+7ACh] [rbp+6ACh] BYREF
  _BYTE v870[4]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _BYTE v871[4]; // [rsp+7B4h] [rbp+6B4h] BYREF
  int v872; // [rsp+7B8h] [rbp+6B8h] BYREF
  _BYTE v873[4]; // [rsp+7BCh] [rbp+6BCh] BYREF
  _BYTE v874[4]; // [rsp+7C0h] [rbp+6C0h] BYREF
  int v875; // [rsp+7C4h] [rbp+6C4h] BYREF
  _BYTE v876[4]; // [rsp+7C8h] [rbp+6C8h] BYREF
  _BYTE v877[4]; // [rsp+7CCh] [rbp+6CCh] BYREF
  int v878; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v879[4]; // [rsp+7D4h] [rbp+6D4h] BYREF
  _BYTE v880[4]; // [rsp+7D8h] [rbp+6D8h] BYREF
  int v881; // [rsp+7DCh] [rbp+6DCh] BYREF
  _BYTE v882[4]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v883[4]; // [rsp+7E4h] [rbp+6E4h] BYREF
  int v884; // [rsp+7E8h] [rbp+6E8h] BYREF
  _BYTE v885[4]; // [rsp+7ECh] [rbp+6ECh] BYREF
  _BYTE v886[4]; // [rsp+7F0h] [rbp+6F0h] BYREF
  int v887; // [rsp+7F4h] [rbp+6F4h] BYREF
  _BYTE v888[4]; // [rsp+7F8h] [rbp+6F8h] BYREF
  _BYTE v889[4]; // [rsp+7FCh] [rbp+6FCh] BYREF
  int v890; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v891[4]; // [rsp+804h] [rbp+704h] BYREF
  _BYTE v892[4]; // [rsp+808h] [rbp+708h] BYREF
  int v893; // [rsp+80Ch] [rbp+70Ch] BYREF
  _BYTE v894[4]; // [rsp+810h] [rbp+710h] BYREF
  _BYTE v895[4]; // [rsp+814h] [rbp+714h] BYREF
  int v896; // [rsp+818h] [rbp+718h] BYREF
  _BYTE v897[4]; // [rsp+81Ch] [rbp+71Ch] BYREF
  _BYTE v898[4]; // [rsp+820h] [rbp+720h] BYREF
  int v899; // [rsp+824h] [rbp+724h] BYREF
  _BYTE v900[4]; // [rsp+828h] [rbp+728h] BYREF
  _BYTE v901[4]; // [rsp+82Ch] [rbp+72Ch] BYREF
  int v902; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v903[4]; // [rsp+834h] [rbp+734h] BYREF
  _BYTE v904[4]; // [rsp+838h] [rbp+738h] BYREF
  int v905; // [rsp+83Ch] [rbp+73Ch] BYREF
  _BYTE v906[4]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v907[4]; // [rsp+844h] [rbp+744h] BYREF
  int v908; // [rsp+848h] [rbp+748h] BYREF
  _BYTE v909[4]; // [rsp+84Ch] [rbp+74Ch] BYREF
  _BYTE v910[4]; // [rsp+850h] [rbp+750h] BYREF
  int v911; // [rsp+854h] [rbp+754h] BYREF
  _BYTE v912[4]; // [rsp+858h] [rbp+758h] BYREF
  _BYTE v913[4]; // [rsp+85Ch] [rbp+75Ch] BYREF
  int v914; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v915[4]; // [rsp+864h] [rbp+764h] BYREF
  _BYTE v916[4]; // [rsp+868h] [rbp+768h] BYREF
  int v917; // [rsp+86Ch] [rbp+76Ch] BYREF
  _BYTE v918[4]; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v919[4]; // [rsp+874h] [rbp+774h] BYREF
  int v920; // [rsp+878h] [rbp+778h] BYREF
  _BYTE v921[4]; // [rsp+87Ch] [rbp+77Ch] BYREF
  _BYTE v922[4]; // [rsp+880h] [rbp+780h] BYREF
  int v923; // [rsp+884h] [rbp+784h] BYREF
  _BYTE v924[4]; // [rsp+888h] [rbp+788h] BYREF
  _BYTE v925[4]; // [rsp+88Ch] [rbp+78Ch] BYREF
  int v926; // [rsp+890h] [rbp+790h] BYREF
  _BYTE v927[4]; // [rsp+894h] [rbp+794h] BYREF
  _BYTE v928[4]; // [rsp+898h] [rbp+798h] BYREF
  int v929; // [rsp+89Ch] [rbp+79Ch] BYREF
  _BYTE v930[4]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v931[4]; // [rsp+8A4h] [rbp+7A4h] BYREF
  int v932; // [rsp+8A8h] [rbp+7A8h] BYREF
  _BYTE v933[4]; // [rsp+8ACh] [rbp+7ACh] BYREF
  _BYTE v934[4]; // [rsp+8B0h] [rbp+7B0h] BYREF
  int v935; // [rsp+8B4h] [rbp+7B4h] BYREF
  _BYTE v936[4]; // [rsp+8B8h] [rbp+7B8h] BYREF
  _BYTE v937[4]; // [rsp+8BCh] [rbp+7BCh] BYREF
  int v938; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v939[4]; // [rsp+8C4h] [rbp+7C4h] BYREF
  _BYTE v940[4]; // [rsp+8C8h] [rbp+7C8h] BYREF
  int v941; // [rsp+8CCh] [rbp+7CCh] BYREF
  _BYTE v942[4]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v943[4]; // [rsp+8D4h] [rbp+7D4h] BYREF
  int v944; // [rsp+8D8h] [rbp+7D8h] BYREF
  _BYTE v945[4]; // [rsp+8DCh] [rbp+7DCh] BYREF
  _BYTE v946[4]; // [rsp+8E0h] [rbp+7E0h] BYREF
  int v947; // [rsp+8E4h] [rbp+7E4h] BYREF
  _BYTE v948[4]; // [rsp+8E8h] [rbp+7E8h] BYREF
  _BYTE v949[4]; // [rsp+8ECh] [rbp+7ECh] BYREF
  int v950; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v951[4]; // [rsp+8F4h] [rbp+7F4h] BYREF
  _BYTE v952[4]; // [rsp+8F8h] [rbp+7F8h] BYREF
  int v953; // [rsp+8FCh] [rbp+7FCh] BYREF
  _BYTE v954[4]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v955[4]; // [rsp+904h] [rbp+804h] BYREF
  int v956; // [rsp+908h] [rbp+808h] BYREF
  _BYTE v957[4]; // [rsp+90Ch] [rbp+80Ch] BYREF
  _BYTE v958[4]; // [rsp+910h] [rbp+810h] BYREF
  int v959; // [rsp+914h] [rbp+814h] BYREF
  _BYTE v960[4]; // [rsp+918h] [rbp+818h] BYREF
  _BYTE v961[4]; // [rsp+91Ch] [rbp+81Ch] BYREF
  int v962; // [rsp+920h] [rbp+820h] BYREF
  _BYTE v963[4]; // [rsp+924h] [rbp+824h] BYREF
  _BYTE v964[4]; // [rsp+928h] [rbp+828h] BYREF
  int v965; // [rsp+92Ch] [rbp+82Ch] BYREF
  _BYTE v966[4]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v967[4]; // [rsp+934h] [rbp+834h] BYREF
  int v968; // [rsp+938h] [rbp+838h] BYREF
  _BYTE v969[4]; // [rsp+93Ch] [rbp+83Ch] BYREF
  _BYTE v970[4]; // [rsp+940h] [rbp+840h] BYREF
  int v971; // [rsp+944h] [rbp+844h] BYREF
  _BYTE v972[4]; // [rsp+948h] [rbp+848h] BYREF
  _BYTE v973[4]; // [rsp+94Ch] [rbp+84Ch] BYREF
  int v974; // [rsp+950h] [rbp+850h] BYREF
  _BYTE v975[4]; // [rsp+954h] [rbp+854h] BYREF
  _BYTE v976[4]; // [rsp+958h] [rbp+858h] BYREF
  int v977; // [rsp+95Ch] [rbp+85Ch] BYREF
  _BYTE v978[4]; // [rsp+960h] [rbp+860h] BYREF
  _BYTE v979[4]; // [rsp+964h] [rbp+864h] BYREF
  int v980; // [rsp+968h] [rbp+868h] BYREF
  _BYTE v981[4]; // [rsp+96Ch] [rbp+86Ch] BYREF
  _BYTE v982[4]; // [rsp+970h] [rbp+870h] BYREF
  int v983; // [rsp+974h] [rbp+874h] BYREF
  _BYTE v984[4]; // [rsp+978h] [rbp+878h] BYREF
  _BYTE v985[4]; // [rsp+97Ch] [rbp+87Ch] BYREF
  int v986; // [rsp+980h] [rbp+880h] BYREF
  _BYTE v987[4]; // [rsp+984h] [rbp+884h] BYREF
  _BYTE v988[4]; // [rsp+988h] [rbp+888h] BYREF
  int v989; // [rsp+98Ch] [rbp+88Ch] BYREF
  _BYTE v990[4]; // [rsp+990h] [rbp+890h] BYREF
  _BYTE v991[4]; // [rsp+994h] [rbp+894h] BYREF
  int v992; // [rsp+998h] [rbp+898h] BYREF
  _BYTE v993[4]; // [rsp+99Ch] [rbp+89Ch] BYREF
  _BYTE v994[4]; // [rsp+9A0h] [rbp+8A0h] BYREF
  int v995; // [rsp+9A4h] [rbp+8A4h] BYREF
  _BYTE v996[4]; // [rsp+9A8h] [rbp+8A8h] BYREF
  _BYTE v997[4]; // [rsp+9ACh] [rbp+8ACh] BYREF
  int v998; // [rsp+9B0h] [rbp+8B0h] BYREF
  _BYTE v999[4]; // [rsp+9B4h] [rbp+8B4h] BYREF
  _BYTE v1000[4]; // [rsp+9B8h] [rbp+8B8h] BYREF
  int v1001; // [rsp+9BCh] [rbp+8BCh] BYREF
  _BYTE v1002[4]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v1003[4]; // [rsp+9C4h] [rbp+8C4h] BYREF
  int v1004; // [rsp+9C8h] [rbp+8C8h] BYREF
  _BYTE v1005[4]; // [rsp+9CCh] [rbp+8CCh] BYREF
  _BYTE v1006[4]; // [rsp+9D0h] [rbp+8D0h] BYREF
  int v1007; // [rsp+9D4h] [rbp+8D4h] BYREF
  _BYTE v1008[4]; // [rsp+9D8h] [rbp+8D8h] BYREF
  _BYTE v1009[4]; // [rsp+9DCh] [rbp+8DCh] BYREF
  int v1010; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v1011[4]; // [rsp+9E4h] [rbp+8E4h] BYREF
  _BYTE v1012[4]; // [rsp+9E8h] [rbp+8E8h] BYREF
  int v1013; // [rsp+9ECh] [rbp+8ECh] BYREF
  _BYTE v1014[4]; // [rsp+9F0h] [rbp+8F0h] BYREF
  _BYTE v1015[4]; // [rsp+9F4h] [rbp+8F4h] BYREF
  int v1016; // [rsp+9F8h] [rbp+8F8h] BYREF
  _BYTE v1017[4]; // [rsp+9FCh] [rbp+8FCh] BYREF
  _BYTE v1018[4]; // [rsp+A00h] [rbp+900h] BYREF
  int v1019; // [rsp+A04h] [rbp+904h] BYREF
  _BYTE v1020[4]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v1021[4]; // [rsp+A0Ch] [rbp+90Ch] BYREF
  int v1022; // [rsp+A10h] [rbp+910h] BYREF
  _BYTE v1023[4]; // [rsp+A14h] [rbp+914h] BYREF
  _BYTE v1024[4]; // [rsp+A18h] [rbp+918h] BYREF
  int v1025; // [rsp+A1Ch] [rbp+91Ch] BYREF
  _BYTE v1026[4]; // [rsp+A20h] [rbp+920h] BYREF
  _BYTE v1027[4]; // [rsp+A24h] [rbp+924h] BYREF
  int v1028; // [rsp+A28h] [rbp+928h] BYREF
  _BYTE v1029[4]; // [rsp+A2Ch] [rbp+92Ch] BYREF
  _BYTE v1030[4]; // [rsp+A30h] [rbp+930h] BYREF
  int v1031; // [rsp+A34h] [rbp+934h] BYREF
  _BYTE v1032[4]; // [rsp+A38h] [rbp+938h] BYREF
  _BYTE v1033[4]; // [rsp+A3Ch] [rbp+93Ch] BYREF
  int v1034; // [rsp+A40h] [rbp+940h] BYREF
  _BYTE v1035[4]; // [rsp+A44h] [rbp+944h] BYREF
  _BYTE v1036[4]; // [rsp+A48h] [rbp+948h] BYREF
  int v1037; // [rsp+A4Ch] [rbp+94Ch] BYREF
  int v1038; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v1039[4]; // [rsp+A54h] [rbp+954h] BYREF
  _BYTE v1040[4]; // [rsp+A58h] [rbp+958h] BYREF
  int v1041; // [rsp+A5Ch] [rbp+95Ch] BYREF
  int v1042; // [rsp+A60h] [rbp+960h] BYREF
  _BYTE v1043[4]; // [rsp+A64h] [rbp+964h] BYREF
  _BYTE v1044[4]; // [rsp+A68h] [rbp+968h] BYREF
  int v1045; // [rsp+A6Ch] [rbp+96Ch] BYREF
  int v1046; // [rsp+A70h] [rbp+970h] BYREF
  _BYTE v1047[4]; // [rsp+A74h] [rbp+974h] BYREF
  _BYTE v1048[4]; // [rsp+A78h] [rbp+978h] BYREF
  int v1049; // [rsp+A7Ch] [rbp+97Ch] BYREF
  int v1050; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v1051[4]; // [rsp+A84h] [rbp+984h] BYREF
  _BYTE v1052[4]; // [rsp+A88h] [rbp+988h] BYREF
  int v1053; // [rsp+A8Ch] [rbp+98Ch] BYREF
  int v1054; // [rsp+A90h] [rbp+990h] BYREF
  _BYTE v1055[4]; // [rsp+A94h] [rbp+994h] BYREF
  _BYTE v1056[4]; // [rsp+A98h] [rbp+998h] BYREF
  int v1057; // [rsp+A9Ch] [rbp+99Ch] BYREF
  int v1058; // [rsp+AA0h] [rbp+9A0h] BYREF
  _BYTE v1059[4]; // [rsp+AA4h] [rbp+9A4h] BYREF
  _BYTE v1060[4]; // [rsp+AA8h] [rbp+9A8h] BYREF
  int v1061; // [rsp+AACh] [rbp+9ACh] BYREF
  int v1062; // [rsp+AB0h] [rbp+9B0h] BYREF
  _BYTE v1063[4]; // [rsp+AB4h] [rbp+9B4h] BYREF
  _BYTE v1064[4]; // [rsp+AB8h] [rbp+9B8h] BYREF
  int v1065; // [rsp+ABCh] [rbp+9BCh] BYREF
  int v1066; // [rsp+AC0h] [rbp+9C0h] BYREF
  _BYTE v1067[4]; // [rsp+AC4h] [rbp+9C4h] BYREF
  _BYTE v1068[4]; // [rsp+AC8h] [rbp+9C8h] BYREF
  int v1069; // [rsp+ACCh] [rbp+9CCh] BYREF
  int v1070; // [rsp+AD0h] [rbp+9D0h] BYREF
  _BYTE v1071[4]; // [rsp+AD4h] [rbp+9D4h] BYREF
  _BYTE v1072[4]; // [rsp+AD8h] [rbp+9D8h] BYREF
  int v1073; // [rsp+ADCh] [rbp+9DCh] BYREF
  int v1074; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v1075[4]; // [rsp+AE4h] [rbp+9E4h] BYREF
  _BYTE v1076[4]; // [rsp+AE8h] [rbp+9E8h] BYREF
  int v1077; // [rsp+AECh] [rbp+9ECh] BYREF
  int v1078; // [rsp+AF0h] [rbp+9F0h] BYREF
  _BYTE v1079[4]; // [rsp+AF4h] [rbp+9F4h] BYREF
  _BYTE v1080[4]; // [rsp+AF8h] [rbp+9F8h] BYREF
  int v1081; // [rsp+AFCh] [rbp+9FCh] BYREF
  int v1082; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE v1083[4]; // [rsp+B04h] [rbp+A04h] BYREF
  _BYTE v1084[4]; // [rsp+B08h] [rbp+A08h] BYREF
  int v1085; // [rsp+B0Ch] [rbp+A0Ch] BYREF
  int v1086; // [rsp+B10h] [rbp+A10h] BYREF
  int v1087; // [rsp+B14h] [rbp+A14h] BYREF
  int v1088; // [rsp+B18h] [rbp+A18h] BYREF
  int v1089; // [rsp+B1Ch] [rbp+A1Ch] BYREF
  int v1090; // [rsp+B20h] [rbp+A20h] BYREF
  int v1091; // [rsp+B24h] [rbp+A24h] BYREF
  int v1092; // [rsp+B28h] [rbp+A28h] BYREF
  int v1093; // [rsp+B2Ch] [rbp+A2Ch] BYREF
  int v1094; // [rsp+B30h] [rbp+A30h] BYREF
  int v1095; // [rsp+B34h] [rbp+A34h] BYREF
  int v1096; // [rsp+B38h] [rbp+A38h] BYREF
  int v1097; // [rsp+B3Ch] [rbp+A3Ch] BYREF
  int v1098; // [rsp+B40h] [rbp+A40h] BYREF
  int v1099; // [rsp+B44h] [rbp+A44h] BYREF
  int v1100; // [rsp+B48h] [rbp+A48h] BYREF
  int v1101; // [rsp+B4Ch] [rbp+A4Ch] BYREF
  int v1102; // [rsp+B50h] [rbp+A50h] BYREF
  int v1103; // [rsp+B54h] [rbp+A54h] BYREF
  int v1104; // [rsp+B58h] [rbp+A58h] BYREF
  int v1105; // [rsp+B5Ch] [rbp+A5Ch] BYREF
  int v1106; // [rsp+B60h] [rbp+A60h] BYREF
  int v1107; // [rsp+B64h] [rbp+A64h] BYREF
  int v1108; // [rsp+B68h] [rbp+A68h] BYREF
  int v1109; // [rsp+B6Ch] [rbp+A6Ch] BYREF
  int v1110; // [rsp+B70h] [rbp+A70h] BYREF
  int v1111; // [rsp+B74h] [rbp+A74h] BYREF
  int v1112; // [rsp+B78h] [rbp+A78h] BYREF
  int v1113; // [rsp+B7Ch] [rbp+A7Ch] BYREF
  int v1114; // [rsp+B80h] [rbp+A80h] BYREF
  int v1115; // [rsp+B84h] [rbp+A84h] BYREF
  int v1116; // [rsp+B88h] [rbp+A88h] BYREF
  _BYTE v1117[8]; // [rsp+B90h] [rbp+A90h] BYREF
  _BYTE v1118[8]; // [rsp+B98h] [rbp+A98h] BYREF
  int v1119; // [rsp+BA0h] [rbp+AA0h] BYREF
  int v1120; // [rsp+BA4h] [rbp+AA4h] BYREF
  double v1121; // [rsp+BA8h] [rbp+AA8h] BYREF
  struct IGameInputServerInputRouter *v1122; // [rsp+BB0h] [rbp+AB0h]
  __int64 v1123; // [rsp+BB8h] [rbp+AB8h] BYREF
  __int64 v1124; // [rsp+BC0h] [rbp+AC0h] BYREF
  const char *v1125; // [rsp+BC8h] [rbp+AC8h] BYREF
  const char *v1126; // [rsp+BD0h] [rbp+AD0h] BYREF
  const char *v1127; // [rsp+BD8h] [rbp+AD8h] BYREF
  const char *v1128; // [rsp+BE0h] [rbp+AE0h] BYREF
  const char *v1129; // [rsp+BE8h] [rbp+AE8h] BYREF
  const char *v1130; // [rsp+BF0h] [rbp+AF0h] BYREF
  const char *v1131; // [rsp+BF8h] [rbp+AF8h] BYREF
  const char *v1132; // [rsp+C00h] [rbp+B00h] BYREF
  const char *v1133; // [rsp+C08h] [rbp+B08h] BYREF
  const char *v1134; // [rsp+C10h] [rbp+B10h] BYREF
  const char *v1135; // [rsp+C18h] [rbp+B18h] BYREF
  const char *v1136; // [rsp+C20h] [rbp+B20h] BYREF
  const char *v1137; // [rsp+C28h] [rbp+B28h] BYREF
  const char *v1138; // [rsp+C30h] [rbp+B30h] BYREF
  const char *v1139; // [rsp+C38h] [rbp+B38h] BYREF
  const char *v1140; // [rsp+C40h] [rbp+B40h] BYREF
  const char *v1141; // [rsp+C48h] [rbp+B48h] BYREF
  __int64 v1142; // [rsp+C50h] [rbp+B50h] BYREF
  _BYTE v1143[8]; // [rsp+C58h] [rbp+B58h] BYREF
  _BYTE v1144[8]; // [rsp+C60h] [rbp+B60h] BYREF
  struct GameInputDeviceInfoPrivate *v1145; // [rsp+C68h] [rbp+B68h]
  struct GameInputServerDevice **v1146; // [rsp+C70h] [rbp+B70h]
  const char *v1147; // [rsp+C78h] [rbp+B78h] BYREF
  _BYTE v1148[8]; // [rsp+C80h] [rbp+B80h] BYREF
  _BYTE v1149[8]; // [rsp+C88h] [rbp+B88h] BYREF
  _BYTE v1150[8]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v1151[8]; // [rsp+C98h] [rbp+B98h] BYREF
  _BYTE v1152[8]; // [rsp+CA0h] [rbp+BA0h] BYREF
  _BYTE v1153[8]; // [rsp+CA8h] [rbp+BA8h] BYREF
  _BYTE v1154[8]; // [rsp+CB0h] [rbp+BB0h] BYREF
  _BYTE v1155[8]; // [rsp+CB8h] [rbp+BB8h] BYREF
  _BYTE v1156[8]; // [rsp+CC0h] [rbp+BC0h] BYREF
  _BYTE v1157[8]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v1158[8]; // [rsp+CD0h] [rbp+BD0h] BYREF
  _BYTE v1159[8]; // [rsp+CD8h] [rbp+BD8h] BYREF
  _BYTE v1160[8]; // [rsp+CE0h] [rbp+BE0h] BYREF
  _BYTE v1161[8]; // [rsp+CE8h] [rbp+BE8h] BYREF
  _BYTE v1162[8]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v1163[8]; // [rsp+CF8h] [rbp+BF8h] BYREF
  _BYTE v1164[8]; // [rsp+D00h] [rbp+C00h] BYREF
  _BYTE v1165[8]; // [rsp+D08h] [rbp+C08h] BYREF
  _BYTE v1166[8]; // [rsp+D10h] [rbp+C10h] BYREF
  _BYTE v1167[8]; // [rsp+D18h] [rbp+C18h] BYREF
  _BYTE v1168[8]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v1169[8]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v1170[8]; // [rsp+D30h] [rbp+C30h] BYREF
  _BYTE v1171[8]; // [rsp+D38h] [rbp+C38h] BYREF
  _BYTE v1172[8]; // [rsp+D40h] [rbp+C40h] BYREF
  _BYTE v1173[8]; // [rsp+D48h] [rbp+C48h] BYREF
  _BYTE v1174[8]; // [rsp+D50h] [rbp+C50h] BYREF
  _BYTE v1175[8]; // [rsp+D58h] [rbp+C58h] BYREF
  _BYTE v1176[8]; // [rsp+D60h] [rbp+C60h] BYREF
  _BYTE v1177[8]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v1178[8]; // [rsp+D70h] [rbp+C70h] BYREF
  _BYTE v1179[8]; // [rsp+D78h] [rbp+C78h] BYREF
  _BYTE v1180[8]; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v1181[8]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v1182[8]; // [rsp+D90h] [rbp+C90h] BYREF
  _BYTE v1183[8]; // [rsp+D98h] [rbp+C98h] BYREF
  _BYTE v1184[8]; // [rsp+DA0h] [rbp+CA0h] BYREF
  _BYTE v1185[8]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v1186[8]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v1187[8]; // [rsp+DB8h] [rbp+CB8h] BYREF
  _BYTE v1188[8]; // [rsp+DC0h] [rbp+CC0h] BYREF
  _BYTE v1189[8]; // [rsp+DC8h] [rbp+CC8h] BYREF
  _BYTE v1190[8]; // [rsp+DD0h] [rbp+CD0h] BYREF
  _BYTE v1191[8]; // [rsp+DD8h] [rbp+CD8h] BYREF
  _BYTE v1192[8]; // [rsp+DE0h] [rbp+CE0h] BYREF
  _BYTE v1193[8]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v1194[8]; // [rsp+DF0h] [rbp+CF0h] BYREF
  _BYTE v1195[8]; // [rsp+DF8h] [rbp+CF8h] BYREF
  _BYTE v1196[8]; // [rsp+E00h] [rbp+D00h] BYREF
  _BYTE v1197[8]; // [rsp+E08h] [rbp+D08h] BYREF
  _BYTE v1198[8]; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE v1199[8]; // [rsp+E18h] [rbp+D18h] BYREF
  _BYTE v1200[8]; // [rsp+E20h] [rbp+D20h] BYREF
  _BYTE v1201[8]; // [rsp+E28h] [rbp+D28h] BYREF
  _BYTE v1202[8]; // [rsp+E30h] [rbp+D30h] BYREF
  _BYTE v1203[8]; // [rsp+E38h] [rbp+D38h] BYREF
  _BYTE v1204[8]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v1205[8]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v1206[8]; // [rsp+E50h] [rbp+D50h] BYREF
  _BYTE v1207[8]; // [rsp+E58h] [rbp+D58h] BYREF
  _BYTE v1208[8]; // [rsp+E60h] [rbp+D60h] BYREF
  _BYTE v1209[8]; // [rsp+E68h] [rbp+D68h] BYREF
  _BYTE v1210[8]; // [rsp+E70h] [rbp+D70h] BYREF
  _BYTE v1211[8]; // [rsp+E78h] [rbp+D78h] BYREF
  _BYTE v1212[8]; // [rsp+E80h] [rbp+D80h] BYREF
  _BYTE v1213[8]; // [rsp+E88h] [rbp+D88h] BYREF
  _BYTE v1214[8]; // [rsp+E90h] [rbp+D90h] BYREF
  _BYTE v1215[8]; // [rsp+E98h] [rbp+D98h] BYREF
  _BYTE v1216[8]; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v1217[8]; // [rsp+EA8h] [rbp+DA8h] BYREF
  _BYTE v1218[8]; // [rsp+EB0h] [rbp+DB0h] BYREF
  _BYTE v1219[8]; // [rsp+EB8h] [rbp+DB8h] BYREF
  _BYTE v1220[8]; // [rsp+EC0h] [rbp+DC0h] BYREF
  _BYTE v1221[8]; // [rsp+EC8h] [rbp+DC8h] BYREF
  _BYTE v1222[8]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v1223[8]; // [rsp+ED8h] [rbp+DD8h] BYREF
  _BYTE v1224[8]; // [rsp+EE0h] [rbp+DE0h] BYREF
  _BYTE v1225[8]; // [rsp+EE8h] [rbp+DE8h] BYREF
  _BYTE v1226[8]; // [rsp+EF0h] [rbp+DF0h] BYREF
  _BYTE v1227[8]; // [rsp+EF8h] [rbp+DF8h] BYREF
  _BYTE v1228[8]; // [rsp+F00h] [rbp+E00h] BYREF
  _BYTE v1229[8]; // [rsp+F08h] [rbp+E08h] BYREF
  _BYTE v1230[8]; // [rsp+F10h] [rbp+E10h] BYREF
  _BYTE v1231[8]; // [rsp+F18h] [rbp+E18h] BYREF
  _BYTE v1232[8]; // [rsp+F20h] [rbp+E20h] BYREF
  _BYTE v1233[8]; // [rsp+F28h] [rbp+E28h] BYREF
  _BYTE v1234[8]; // [rsp+F30h] [rbp+E30h] BYREF
  _BYTE v1235[8]; // [rsp+F38h] [rbp+E38h] BYREF
  _BYTE v1236[8]; // [rsp+F40h] [rbp+E40h] BYREF
  _BYTE v1237[8]; // [rsp+F48h] [rbp+E48h] BYREF
  _BYTE v1238[8]; // [rsp+F50h] [rbp+E50h] BYREF
  _BYTE v1239[8]; // [rsp+F58h] [rbp+E58h] BYREF
  _BYTE v1240[8]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v1241[8]; // [rsp+F68h] [rbp+E68h] BYREF
  _BYTE v1242[8]; // [rsp+F70h] [rbp+E70h] BYREF
  _BYTE v1243[8]; // [rsp+F78h] [rbp+E78h] BYREF
  _BYTE v1244[8]; // [rsp+F80h] [rbp+E80h] BYREF
  _BYTE v1245[8]; // [rsp+F88h] [rbp+E88h] BYREF
  _BYTE v1246[8]; // [rsp+F90h] [rbp+E90h] BYREF
  _BYTE v1247[8]; // [rsp+F98h] [rbp+E98h] BYREF
  _BYTE v1248[8]; // [rsp+FA0h] [rbp+EA0h] BYREF
  _BYTE v1249[8]; // [rsp+FA8h] [rbp+EA8h] BYREF
  _BYTE v1250[8]; // [rsp+FB0h] [rbp+EB0h] BYREF
  _BYTE v1251[8]; // [rsp+FB8h] [rbp+EB8h] BYREF
  _BYTE v1252[8]; // [rsp+FC0h] [rbp+EC0h] BYREF
  _BYTE v1253[8]; // [rsp+FC8h] [rbp+EC8h] BYREF
  _BYTE v1254[8]; // [rsp+FD0h] [rbp+ED0h] BYREF
  _BYTE v1255[8]; // [rsp+FD8h] [rbp+ED8h] BYREF
  _BYTE v1256[8]; // [rsp+FE0h] [rbp+EE0h] BYREF
  _BYTE v1257[8]; // [rsp+FE8h] [rbp+EE8h] BYREF
  _BYTE v1258[8]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v1259[8]; // [rsp+FF8h] [rbp+EF8h] BYREF
  _BYTE v1260[8]; // [rsp+1000h] [rbp+F00h] BYREF
  _BYTE v1261[8]; // [rsp+1008h] [rbp+F08h] BYREF
  _BYTE v1262[8]; // [rsp+1010h] [rbp+F10h] BYREF
  _BYTE v1263[8]; // [rsp+1018h] [rbp+F18h] BYREF
  _BYTE v1264[8]; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v1265[8]; // [rsp+1028h] [rbp+F28h] BYREF
  _BYTE v1266[8]; // [rsp+1030h] [rbp+F30h] BYREF
  _BYTE v1267[8]; // [rsp+1038h] [rbp+F38h] BYREF
  _BYTE v1268[8]; // [rsp+1040h] [rbp+F40h] BYREF
  _BYTE v1269[8]; // [rsp+1048h] [rbp+F48h] BYREF
  _BYTE v1270[8]; // [rsp+1050h] [rbp+F50h] BYREF
  _BYTE v1271[8]; // [rsp+1058h] [rbp+F58h] BYREF
  _BYTE v1272[8]; // [rsp+1060h] [rbp+F60h] BYREF
  _BYTE v1273[8]; // [rsp+1068h] [rbp+F68h] BYREF
  _BYTE v1274[8]; // [rsp+1070h] [rbp+F70h] BYREF
  _BYTE v1275[8]; // [rsp+1078h] [rbp+F78h] BYREF
  _BYTE v1276[8]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v1277[8]; // [rsp+1088h] [rbp+F88h] BYREF
  _BYTE v1278[8]; // [rsp+1090h] [rbp+F90h] BYREF
  _BYTE v1279[8]; // [rsp+1098h] [rbp+F98h] BYREF
  _BYTE v1280[8]; // [rsp+10A0h] [rbp+FA0h] BYREF
  _BYTE v1281[8]; // [rsp+10A8h] [rbp+FA8h] BYREF
  _BYTE v1282[8]; // [rsp+10B0h] [rbp+FB0h] BYREF
  _BYTE v1283[8]; // [rsp+10B8h] [rbp+FB8h] BYREF
  _BYTE v1284[8]; // [rsp+10C0h] [rbp+FC0h] BYREF
  _BYTE v1285[8]; // [rsp+10C8h] [rbp+FC8h] BYREF
  _BYTE v1286[8]; // [rsp+10D0h] [rbp+FD0h] BYREF
  _BYTE v1287[8]; // [rsp+10D8h] [rbp+FD8h] BYREF
  _BYTE v1288[8]; // [rsp+10E0h] [rbp+FE0h] BYREF
  _BYTE v1289[24]; // [rsp+10E8h] [rbp+FE8h] BYREF
  __int128 v1290; // [rsp+1100h] [rbp+1000h] BYREF
  int v1291; // [rsp+1110h] [rbp+1010h]
  __int128 v1292; // [rsp+1118h] [rbp+1018h] BYREF
  __int64 v1293; // [rsp+1128h] [rbp+1028h]
  __int128 v1294; // [rsp+1130h] [rbp+1030h] BYREF
  __int128 v1295; // [rsp+1140h] [rbp+1040h]
  __int128 v1296; // [rsp+1150h] [rbp+1050h]
  UCHAR pbOutput[16]; // [rsp+1160h] [rbp+1060h] BYREF
  __int128 v1298; // [rsp+1170h] [rbp+1070h]
  __int128 v1299; // [rsp+1180h] [rbp+1080h] BYREF
  __int128 v1300; // [rsp+1190h] [rbp+1090h]
  __int128 v1301; // [rsp+11A0h] [rbp+10A0h]
  __int64 v1302; // [rsp+11B0h] [rbp+10B0h]
  __int128 v1303; // [rsp+11B8h] [rbp+10B8h] BYREF
  __int128 v1304; // [rsp+11C8h] [rbp+10C8h]
  __int128 v1305; // [rsp+11D8h] [rbp+10D8h]
  __int64 v1306; // [rsp+11E8h] [rbp+10E8h]
  __int64 v1307; // [rsp+11F0h] [rbp+10F0h] BYREF
  int v1308; // [rsp+11F8h] [rbp+10F8h]
  _DWORD v1309[24]; // [rsp+1200h] [rbp+1100h] BYREF
  _BYTE v1310[912]; // [rsp+1260h] [rbp+1160h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+15F0h] [rbp+14F0h] BYREF
  __int64 v1312; // [rsp+1608h] [rbp+1508h]
  HSTRING_HEADER v1313; // [rsp+1610h] [rbp+1510h] BYREF
  __int64 v1314; // [rsp+1628h] [rbp+1528h]
  HSTRING_HEADER v1315; // [rsp+1630h] [rbp+1530h] BYREF
  __int64 v1316; // [rsp+1648h] [rbp+1548h]
  HSTRING_HEADER v1317; // [rsp+1650h] [rbp+1550h] BYREF
  __int64 v1318; // [rsp+1668h] [rbp+1568h]
  HSTRING_HEADER v1319; // [rsp+1670h] [rbp+1570h] BYREF
  __int64 v1320; // [rsp+1688h] [rbp+1588h]
  _OWORD v1321[2]; // [rsp+1690h] [rbp+1590h] BYREF
  _BYTE v1322[60]; // [rsp+16B0h] [rbp+15B0h] BYREF
  int v1323; // [rsp+16ECh] [rbp+15ECh]

  v1122 = a2;
  v1146 = a4;
  *a4 = 0;
  Heap = (GameInputServerDevice *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x260u);
  if ( Heap )
  {
    v449 = GameInputServerDevice::GameInputServerDevice(Heap, a1, a2, a3);
    if ( v449 )
    {
      v446 = 0;
      v445 = 0;
      v444 = 0;
      v443 = 0;
      v447 = 0;
      v433 = 0;
      v440 = 0;
      v430 = 0;
      v437 = 0;
      v436 = 0;
      v431 = 0;
      v429 = 0;
      v441 = 0;
      v432 = 0;
      v438 = 0;
      v442 = 0;
      v439 = 0;
      v434 = 0;
      v435 = 0;
      memset_0(v1322, 0, 0x40u);
      v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD))v449 + 66))(
             *((_QWORD *)v449 + 66),
             &GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd,
             &v433);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1087 = v9;
            v1088 = 670;
            v1125 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_18005EEDF,
              0,
              0,
              (__int64)&v1125,
              (__int64)&v1088,
              (__int64)&v1087);
          }
        }
        goto LABEL_91;
      }
      v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v449 + 66))(
             *((_QWORD *)v449 + 66),
             &GUID_43c0c035_bb73_4756_a787_3ed6bea617bd,
             &v440);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1089 = v9;
            v1090 = 671;
            v1126 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061561,
              0,
              0,
              (__int64)&v1126,
              (__int64)&v1090,
              (__int64)&v1089);
          }
        }
        goto LABEL_91;
      }
      v1312 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Gaming.Input.ArcadeStick",
        0x21u,
        0x20u);
      ActivationFactory = RoGetActivationFactory(v1312, &GUID_52b5d744_bb86_445a_b59c_596f0e2a49df, &v446);
      v1312 = 0;
      v9 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1091 = ActivationFactory;
            v1092 = 673;
            v1127 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180062624,
              0,
              0,
              (__int64)&v1127,
              (__int64)&v1092,
              (__int64)&v1091);
          }
        }
        goto LABEL_91;
      }
      v1314 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v1313,
        L"Windows.Gaming.Input.FlightStick",
        0x21u,
        0x20u);
      v11 = RoGetActivationFactory(v1314, &GUID_5514924a_fecc_435e_83dc_5cec8a18a520, &v445);
      v1314 = 0;
      v9 = v11;
      if ( v11 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1093 = v11;
            v1094 = 674;
            v1128 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18005F3B6,
              0,
              0,
              (__int64)&v1128,
              (__int64)&v1094,
              (__int64)&v1093);
          }
        }
        goto LABEL_91;
      }
      v1316 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v1315, L"Windows.Gaming.Input.Gamepad", 0x1Du, 0x1Cu);
      v12 = RoGetActivationFactory(v1316, &GUID_42676dc5_0856_47c4_9213_b395504c3a3c, &v444);
      v1316 = 0;
      v9 = v12;
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1095 = v12;
            v1096 = 675;
            v1129 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005EDEB,
              0,
              0,
              (__int64)&v1129,
              (__int64)&v1096,
              (__int64)&v1095);
          }
        }
        goto LABEL_91;
      }
      v1318 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v1317,
        L"Windows.Gaming.Input.RacingWheel",
        0x21u,
        0x20u);
      v13 = RoGetActivationFactory(v1318, &GUID_e666bcaa_edfd_4323_a9f6_3c384048d1ed, &v443);
      v1318 = 0;
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1097 = v13;
            v1098 = 676;
            v1130 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_180060717,
              0,
              0,
              (__int64)&v1130,
              (__int64)&v1098,
              (__int64)&v1097);
          }
        }
        goto LABEL_91;
      }
      v1320 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v1319,
        L"Windows.Gaming.Input.UINavigationController",
        0x2Cu,
        0x2Bu);
      v14 = RoGetActivationFactory(v1320, &GUID_e0cb28e3_b20b_4b0b_9ed4_f3d53cec0de4, &v447);
      v1320 = 0;
      v9 = v14;
      if ( v14 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1099 = v14;
            v1100 = 677;
            v1131 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180060120,
              0,
              0,
              (__int64)&v1131,
              (__int64)&v1100,
              (__int64)&v1099);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v446 + 48LL))(v446, v433, &v430);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1101 = v9;
            v1102 = 682;
            v1132 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060331,
              0,
              0,
              (__int64)&v1132,
              (__int64)&v1102,
              (__int64)&v1101);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v445 + 88LL))(v445, v433, &v437);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1103 = v9;
            v1104 = 683;
            v1133 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F785,
              0,
              0,
              (__int64)&v1133,
              (__int64)&v1104,
              (__int64)&v1103);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v444 + 48LL))(v444, v433, &v436);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1105 = v9;
            v1106 = 684;
            v1134 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_18005FB1A,
              0,
              0,
              (__int64)&v1134,
              (__int64)&v1106,
              (__int64)&v1105);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v443 + 48LL))(v443, v433, &v431);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1107 = v9;
            v1108 = 685;
            v1135 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_180060462,
              0,
              0,
              (__int64)&v1135,
              (__int64)&v1108,
              (__int64)&v1107);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v447 + 48LL))(v447, v433, &v429);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1109 = v9;
            v1110 = 686;
            v1136 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_18005F430,
              0,
              0,
              (__int64)&v1136,
              (__int64)&v1110,
              (__int64)&v1109);
          }
        }
        goto LABEL_91;
      }
      v9 = (**v433)(v433, &GUID_debcfefe_f763_4670_940b_57aae2b143ff, &v441);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1111 = v9;
            v1112 = 688;
            v1137 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_18005FE10,
              0,
              0,
              (__int64)&v1137,
              (__int64)&v1112,
              (__int64)&v1111);
          }
        }
        goto LABEL_91;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v441 + 48LL))(
             v441,
             &v432);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1113 = v9;
            v1114 = 689;
            v1138 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_18005EB9A,
              0,
              0,
              (__int64)&v1138,
              (__int64)&v1114,
              (__int64)&v1113);
          }
        }
        goto LABEL_91;
      }
      v9 = (**v432)(v432, &GUID_c3542377_1ea7_4454_8deb_8aa6070db645, &v434);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 )
        {
          v8 = qword_180069018;
          if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1115 = v9;
            v1116 = 690;
            v1139 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180061EC6,
              0,
              0,
              (__int64)&v1139,
              (__int64)&v1116,
              (__int64)&v1115);
          }
        }
        goto LABEL_91;
      }
      (**v432)(v432, &GUID_dbcf1e19_1af5_45a8_bf02_a0ee50c823fc, &v442);
      (**v432)(v432, &GUID_95ce3af4_abf0_4b68_a081_3b7de73ff0e7, &v438);
      (**v432)(v432, &GUID_6e2971eb_0efb_48b4_808b_837643b2f216, &v439);
      (**v434)(v434, &GUID_f6d99cef_3636_46f4_a0a9_00751df46bcb, &v435);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 520, &v434);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 536, &v430);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 544, &v437);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 552, &v436);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 560, &v431);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IUINavigationController>::operator=((char *)v449 + 568, &v429);
      GameInputDeviceInfoBuilder::GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
      v451[0] = 0;
      v461 = 0;
      v450 = 0;
      if ( v435 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v435 + 64LL))(v435, (__int64)v449 + 216);
        if ( v9 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2
            && (qword_180069010 & 0x400) != 0
            && (qword_180069018 & 0x400) == qword_180069018 )
          {
            v1119 = v9;
            v1120 = 713;
            v1140 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180062858,
              0,
              0,
              (__int64)&v1140,
              (__int64)&v1120,
              (__int64)&v1119);
          }
LABEL_90:
          GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
LABEL_91:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v435,
            v8);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v434,
            v16);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v439,
            v17);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v442,
            v18);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v438,
            v19);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v432,
            v20);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v441,
            v21);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v429,
            v22);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v431,
            v23);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v436,
            v24);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v437,
            v25);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v430,
            v26);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v440,
            v27);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v433,
            v28);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v447,
            v29);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v443,
            v30);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v444,
            v31);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v445,
            v32);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v446,
            v33);
LABEL_856:
          utl::unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>::~unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>(&v449);
          return (unsigned int)v9;
        }
        v458 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v435 + 120LL))(v435, &v458);
        if ( v9 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 )
          {
            v15 = qword_180069018;
            if ( (qword_180069010 & 0x400) != 0 && (qword_180069018 & 0x400) == qword_180069018 )
            {
              v663 = v9;
              v664 = 716;
              v1141 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&unk_18005EB20,
                0,
                0,
                (__int64)&v1141,
                (__int64)&v664,
                (__int64)&v663);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::Internal::IGipGameControllerProviderPrivate>::InternalRelease(
            &v458,
            v15);
          goto LABEL_90;
        }
        v464[0] = 0;
        v463 = 0;
        v453 = 0;
        v454 = 0;
        v459 = 0;
        v462 = 0;
        v34 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v35 = *v34;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_IRREMOTEDEVICE;
        v659 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _BYTE *))(v35 + 120))(v34, &v472, v464);
        if ( v659 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v666, &v659);
            v665 = 719;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v667, &v665);
            v36 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1148,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18005F5EE,
              0,
              0,
              v36,
              (__int64)v667,
              (__int64)v666);
          }
          v9 = v659;
LABEL_97:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v458);
LABEL_98:
          GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v435);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v434);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v439);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v442);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v438);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v432);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v441);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v429);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v431);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v436);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v437);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v430);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v440);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v433);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v447);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v443);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v444);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v445);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v446);
          goto LABEL_856;
        }
        v37 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v38 = *v37;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_IGAMEPAD;
        v660 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v38 + 120))(v37, &v472, &v463);
        if ( v660 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v669, &v660);
            v668 = 720;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v670, &v668);
            v39 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1149,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18005F29E,
              0,
              0,
              v39,
              (__int64)v670,
              (__int64)v669);
          }
          v9 = v660;
          goto LABEL_97;
        }
        v40 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v41 = *v40;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_IELITEGAMEPAD;
        v490 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v41 + 120))(v40, &v472, &v453);
        if ( v490 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v672, &v490);
            v671 = 721;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v673, &v671);
            v42 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1150,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_180062047,
              0,
              0,
              v42,
              (__int64)v673,
              (__int64)v672);
          }
          v9 = v490;
          goto LABEL_97;
        }
        v43 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v44 = *v43;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_ICONSOLEFUNCTIONMAP;
        v491 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v44 + 120))(v43, &v472, &v454);
        if ( v491 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v675, &v491);
            v674 = 722;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v676, &v674);
            v45 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1151,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_1800613CA,
              0,
              0,
              v45,
              (__int64)v676,
              (__int64)v675);
          }
          v9 = v491;
          goto LABEL_97;
        }
        v46 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v47 = *v46;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_ICONSOLEFUNCTIONMAPALT;
        v492 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v47 + 120))(v46, &v472, &v459);
        if ( v492 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v678, &v492);
            v677 = 723;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v679, &v677);
            v48 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1152,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180062124,
              0,
              0,
              v48,
              (__int64)v679,
              (__int64)v678);
          }
          v9 = v492;
          goto LABEL_97;
        }
        v49 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v50 = *v49;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_DLI;
        v493 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _BYTE *))(v50 + 120))(v49, &v472, v451);
        if ( v493 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v681, &v493);
            v680 = 724;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v682, &v680);
            v51 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1153,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061D55,
              0,
              0,
              v51,
              (__int64)v682,
              (__int64)v681);
          }
          v9 = v493;
          goto LABEL_97;
        }
        v52 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v53 = *v52;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_IPROGRAMMABLEGAMEPAD;
        v494 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v53 + 120))(v52, &v472, &v462);
        if ( v494 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v684, &v494);
            v683 = 725;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v685, &v683);
            v54 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1154,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18006251D,
              0,
              0,
              v54,
              (__int64)v685,
              (__int64)v684);
          }
          v9 = v494;
          goto LABEL_97;
        }
        v55 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v56 = *v55;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_ISTREAMINGGAMEPAD;
        v495 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v56 + 120))(v55, &v472, &v450);
        if ( v495 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v687, &v495);
            v686 = 726;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v688, &v686);
            v57 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1155,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_18005FC88,
              0,
              0,
              v57,
              (__int64)v688,
              (__int64)v687);
          }
          v9 = v495;
          goto LABEL_97;
        }
        v58 = (__int64 *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v458);
        v59 = *v58;
        v472 = GUID_GIP_MICROSOFT_XBOX_INPUT_IVIRTUALDEVICE;
        v496 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(v59 + 120))(v58, &v472, &v461);
        if ( v496 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v690, &v496);
            v689 = 727;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v691, &v689);
            v60 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1156,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_18005FA60,
              0,
              0,
              v60,
              (__int64)v691,
              (__int64)v690);
          }
          v9 = v496;
          goto LABEL_97;
        }
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 226) = 1;
        v61 = v464[0] != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 224) = v61;
        if ( v453 || (v62 = 0, v454) )
          v62 = 1;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 225) = v62;
        if ( !v463 || (v63 = 1, v450) )
          v63 = 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 227) = v63;
        v64 = v453 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 231) = v64;
        v65 = v454 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 232) = v65;
        v66 = v459 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 233) = v66;
        v67 = v462 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 235) = v67;
        v68 = v451[0] != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 234) = v68;
        v69 = v450 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 236) = v69;
        v1142 = 0;
        v70 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v432);
        v497 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 48LL))(v70, &v1142);
        if ( v497 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v693, &v497);
            v692 = 741;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v694, &v692);
            v71 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1157,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_180061D92,
              0,
              0,
              v71,
              (__int64)v694,
              (__int64)v693);
          }
          v9 = v497;
          goto LABEL_97;
        }
        if ( v451[0] )
          v72 = operator|(1, 2);
        else
          v72 = 1;
        v498 = GameInputDeviceInfoBuilder::AddSystemButtonInfo(v1310, v72);
        if ( v498 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v696, &v498);
            v695 = 750;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v697, &v695);
            v73 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1158,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_1800615DB,
              0,
              0,
              v73,
              (__int64)v697,
              (__int64)v696);
          }
          v9 = v498;
          goto LABEL_97;
        }
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v458);
      }
      else if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v439) != -1 )
      {
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 226) = 1;
        v499 = GameInputDeviceInfoBuilder::AddSystemButtonInfo(v1310, 1);
        if ( v499 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v699, &v499);
            v698 = 757;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v700, &v698);
            v86 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1159,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180061C78,
              0,
              0,
              v86,
              (__int64)v700,
              (__int64)v699);
          }
          v9 = v499;
          goto LABEL_98;
        }
        v87 = (struct XusbWatcher **)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                    + 600);
        v88 = (__int64 (__fastcall ***)(struct Windows::Gaming::Input::Internal::IGameControllerProviderPrivate *, GUID *, __int64 *))utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v434);
        v89 = (struct GameInputServerDevice *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        v500 = XusbWatcher::Create(v89, v88, v87);
        if ( v500 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v702, &v500);
            v701 = 758;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v703, &v701);
            v90 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                    v1160,
                    "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005EB5D,
              0,
              0,
              v90,
              (__int64)v703,
              (__int64)v702);
          }
          v9 = v500;
          goto LABEL_98;
        }
      }
      HString::HString((HString *)v448);
      if ( v450 )
      {
        HString::HString((HString *)v1118);
        HString::HString((HString *)v1117);
        v74 = (_QWORD *)Microsoft::WRL::ComPtr<IUnknown>::operator&(v1118, v1161);
        v75 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ICloudStreamingServiceProvider>>(*v74);
        if ( CoCreateInstance(
               &CLSID_CloudStreamingServiceProvider,
               0,
               4u,
               &GUID_7d880b6a_0894_4c3f_9732_cc36449795e5,
               v75) < 0
          || (v76 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v1118),
              v77 = *(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v76 + 24LL),
              v78 = Microsoft::WRL::ComPtr<IUnknown>::operator&(v1117, v1162),
              v79 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>::operator IUnknown * *(v78),
              v77(v76, v79) < 0)
          || (v80 = (_QWORD *)Microsoft::WRL::ComPtr<IUnknown>::operator&(v448, v1163),
              (int)Microsoft::WRL::ComPtr<IUnknown>::As<IGameInputStreamingControllerSource>(v1117, *v80) < 0) )
        {
          v450 = 0;
          if ( (unsigned int)dword_180069000 > 2 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              v81 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
              _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(v1143, v81 + 216);
              v82 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1164, "Failed to get the streaming controller source");
              v704 = 774;
              v83 = v82;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v705, &v704);
              v84 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                      v1165,
                      "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&byte_1800624D7,
                0,
                0,
                v84,
                (__int64)v705,
                v83,
                (__int64)v1143);
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v1117);
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v1118);
      }
      v466 = 0;
      v467[0] = 0;
      v501 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, unsigned __int16 *))(*(_QWORD *)a3 + 80LL))(
               a3,
               &v466);
      if ( v501 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v707, &v501);
          v706 = 783;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v708, &v706);
          v85 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1166, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&dword_1800617EC,
            0,
            0,
            v85,
            (__int64)v708,
            (__int64)v707);
        }
        v9 = v501;
        goto LABEL_172;
      }
      v502 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, unsigned __int16 *))(*(_QWORD *)a3 + 72LL))(
               a3,
               v467);
      if ( v502 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v710, &v502);
          v709 = 784;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v711, &v709);
          v91 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1167, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&unk_18005EA58,
            0,
            0,
            v91,
            (__int64)v711,
            (__int64)v710);
        }
        v9 = v502;
        goto LABEL_172;
      }
      GameInputDeviceInfoBuilder::AddPnpInfo((GameInputDeviceInfoBuilder *)v1310, v466, v467[0], 0, 0, 0);
      v1124 = 0;
      v1123 = 0;
      v92 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v432);
      v503 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v92 + 72LL))(v92, &v1124);
      if ( v503 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v713, &v503);
          v712 = 801;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v714, &v712);
          v93 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1168, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)word_180061A7A,
            0,
            0,
            v93,
            (__int64)v714,
            (__int64)v713);
        }
        v9 = v503;
        goto LABEL_172;
      }
      v94 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v432);
      v504 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v94 + 48LL))(v94, &v1123);
      if ( v504 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v716, &v504);
          v715 = 802;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v717, &v715);
          v95 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1169, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)byte_180060B5D,
            0,
            0,
            v95,
            (__int64)v717,
            (__int64)v716);
        }
        v9 = v504;
        goto LABEL_172;
      }
      GameInputDeviceInfoBuilder::AddVersionInfo(v1310, v1124, v1123);
      *(_OWORD *)pbOutput = 0;
      v1298 = 0;
      HString::HString((HString *)v487);
      HString::HString((HString *)v476);
      v96 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v434);
      v97 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v96 + 136LL);
      AddressOf = Microsoft::WRL::Wrappers::HString::GetAddressOf((Microsoft::WRL::Wrappers::HString *)v487);
      v505 = v97(v96, AddressOf);
      if ( v505 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v719, &v505);
          v718 = 811;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v720, &v718);
          v99 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1170, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)word_1800628D2,
            0,
            0,
            v99,
            (__int64)v720,
            (__int64)v719);
        }
        v9 = v505;
LABEL_204:
        Microsoft::WRL::Wrappers::HString::~HString((Microsoft::WRL::Wrappers::HString *)v476);
        v100 = (Microsoft::WRL::Wrappers::HString *)v487;
LABEL_205:
        Microsoft::WRL::Wrappers::HString::~HString(v100);
LABEL_172:
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v448);
        goto LABEL_98;
      }
      v101 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v434);
      v102 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v101 + 128LL);
      v103 = Microsoft::WRL::Wrappers::HString::GetAddressOf((Microsoft::WRL::Wrappers::HString *)v476);
      v506 = v102(v101, v103);
      if ( v506 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v722, &v506);
          v721 = 812;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v723, &v721);
          v104 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1171,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&byte_1800601D7,
            0,
            0,
            v104,
            (__int64)v723,
            (__int64)v722);
        }
        v9 = v506;
        goto LABEL_204;
      }
      v471 = 0;
      RawBuffer = (UCHAR *)Microsoft::WRL::Wrappers::HString::GetRawBuffer(
                             (Microsoft::WRL::Wrappers::HString *)v487,
                             &v471);
      AppLocalDeviceId = GameInputServerDevice::GenerateAppLocalDeviceId(2 * v471, RawBuffer, pbOutput);
      if ( AppLocalDeviceId < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v725, &AppLocalDeviceId);
          v724 = 817;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v726, &v724);
          v106 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1172,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)word_180060B9A,
            0,
            0,
            v106,
            (__int64)v726,
            (__int64)v725);
        }
        v9 = AppLocalDeviceId;
        goto LABEL_204;
      }
      v1321[0] = *(_OWORD *)pbOutput;
      v1321[1] = v1298;
      if ( Microsoft::WRL::Wrappers::HString::IsValid((Microsoft::WRL::Wrappers::HString *)v476) )
      {
        v107 = (UCHAR *)Microsoft::WRL::Wrappers::HString::GetRawBuffer(
                          (Microsoft::WRL::Wrappers::HString *)v476,
                          &v471);
        v508 = GameInputServerDevice::GenerateAppLocalDeviceId(2 * v471, v107, pbOutput);
        if ( v508 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v728, &v508);
            v727 = 823;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v729, &v727);
            v108 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1173,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061C3B,
              0,
              0,
              v108,
              (__int64)v729,
              (__int64)v728);
          }
          v9 = v508;
          goto LABEL_204;
        }
      }
      if ( v450 )
      {
        v109 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v448);
        v110 = *(__int64 (__fastcall **)(__int64, _QWORD, UCHAR *))(*(_QWORD *)v109 + 24LL);
        v111 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        v730 = v110(v109, *(_QWORD *)(v111 + 216), pbOutput);
        if ( v730 < 0 )
        {
          v450 = 0;
          if ( (unsigned int)dword_180069000 > 2 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v732, &v730);
              v112 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
              _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(v1144, v112 + 216);
              v113 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1174, "Failed to set device id for the streaming controller");
              v731 = 833;
              v114 = v113;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v733, &v731);
              v115 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1175,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)byte_18005FE4D,
                0,
                0,
                v115,
                (__int64)v733,
                v114,
                (__int64)v1144,
                (__int64)v732);
            }
          }
        }
      }
      GameInputDeviceInfoBuilder::AddDeviceIds(
        (GameInputDeviceInfoBuilder *)v1310,
        (const struct APP_LOCAL_DEVICE_ID *)pbOutput,
        (const struct APP_LOCAL_DEVICE_ID *)v1321);
      Microsoft::WRL::Wrappers::HString::~HString((Microsoft::WRL::Wrappers::HString *)v476);
      Microsoft::WRL::Wrappers::HString::~HString((Microsoft::WRL::Wrappers::HString *)v487);
      v465 = 0;
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v442) == -1 )
      {
        if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v438) == -1 )
        {
          if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v439) == -1 )
          {
            v9 = -2147024809;
            v1081 = -2147024809;
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1083, &v1081);
              v1082 = 867;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1084, &v1082);
              v427 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1288,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&byte_1800617AF,
                0,
                0,
                v427,
                (__int64)v1084,
                (__int64)v1083);
            }
            goto LABEL_172;
          }
          LOWORD(v465) = 1;
          if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v436) == -1 )
            v122 = 4;
          else
            v122 = 5;
          HIWORD(v465) = v122;
          v116 = 2;
        }
        else
        {
          v118 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v438);
          v509 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v118 + 56LL))(v118, &v465);
          if ( v509 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v735, &v509);
              v734 = 855;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v736, &v734);
              v119 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1176,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)byte_1800618A3,
                0,
                0,
                v119,
                (__int64)v736,
                (__int64)v735);
            }
            v9 = v509;
            goto LABEL_172;
          }
          v120 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v438);
          v510 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v120 + 48LL))(v120, (char *)&v465 + 2);
          if ( v510 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v738, &v510);
              v737 = 856;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v739, &v737);
              v121 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1177,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&dword_1800604DC,
                0,
                0,
                v121,
                (__int64)v739,
                (__int64)v738);
            }
            v9 = v510;
            goto LABEL_172;
          }
          v116 = 3;
        }
      }
      else
      {
        v116 = 1;
        LOWORD(v465) = 1;
        if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v436) == -1 )
          v117 = 4;
        else
          v117 = 5;
        HIWORD(v465) = v117;
        if ( v461 && !v450 )
          v116 = -1;
      }
      v460 = 0;
      v123 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v433);
      v511 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v123 + 104LL))(v123, &v460);
      if ( v511 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v741, &v511);
          v740 = 871;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v742, &v740);
          v124 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1178,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&dword_18006221C,
            0,
            0,
            v124,
            (__int64)v742,
            (__int64)v741);
        }
        v9 = v511;
        goto LABEL_172;
      }
      v478 = 0;
      if ( v460 )
        operator|=(&v478, 16);
      if ( v451[0] )
        operator|=(&v478, 8);
      GameInputDeviceInfoBuilder::AddDeviceInfo(v1310, v465, v116, v478);
      HString::HString((HString *)v488);
      v125 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v440);
      v126 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v125 + 64LL);
      v127 = Microsoft::WRL::Wrappers::HString::GetAddressOf((Microsoft::WRL::Wrappers::HString *)v488);
      v512 = v126(v125, v127);
      if ( v512 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v744, &v512);
          v743 = 888;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v745, &v743);
          v128 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1179,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)word_18005EEA2,
            0,
            0,
            v128,
            (__int64)v745,
            (__int64)v744);
        }
        v9 = v512;
LABEL_265:
        v100 = (Microsoft::WRL::Wrappers::HString *)v488;
        goto LABEL_205;
      }
      if ( Microsoft::WRL::Wrappers::HString::IsValid((Microsoft::WRL::Wrappers::HString *)v488) )
      {
        v513[0] = 0;
        Microsoft::WRL::Wrappers::HString::GetRawBuffer((Microsoft::WRL::Wrappers::HString *)v488, v513);
        v513[1] = GameInputServerDevice::OnInputSuspended((GameInputServerDevice *)v1310, v513[0]);
        if ( (v513[1] & 0x80000000) != 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v747, &v513[1]);
            v746 = 893;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v748, &v746);
            v129 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1180,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F3F3,
              0,
              0,
              v129,
              (__int64)v748,
              (__int64)v747);
          }
          v9 = v513[1];
          goto LABEL_265;
        }
      }
      Microsoft::WRL::Wrappers::HString::~HString((Microsoft::WRL::Wrappers::HString *)v488);
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v435) != -1 )
      {
        v130 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v435);
        v131 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v130 + 64LL);
        v132 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        v514 = v131(v130, v132 + 216);
        if ( v514 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v750, &v514);
            v749 = 900;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v751, &v749);
            v133 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1181,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180061BFE,
              0,
              0,
              v133,
              (__int64)v751,
              (__int64)v750);
          }
          v9 = v514;
          goto LABEL_172;
        }
        HString::HString((HString *)v474);
        v134 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v435);
        v135 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 120LL);
        v136 = Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad2>::GetAddressOf(v474);
        v515 = v135(v134, v136);
        if ( v515 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v753, &v515);
            v752 = 903;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v754, &v752);
            v137 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1182,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005ED21,
              0,
              0,
              v137,
              (__int64)v754,
              (__int64)v753);
          }
          v9 = v515;
          goto LABEL_283;
        }
        HString::HString((HString *)v475);
        v138 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v474);
        v139 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v138 + 48LL);
        v140 = Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad2>::GetAddressOf(v475);
        v516 = v139(v138, v140);
        if ( v516 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v756, &v516);
            v755 = 906;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v757, &v755);
            v141 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1183,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F261,
              0,
              0,
              v141,
              (__int64)v757,
              (__int64)v756);
          }
          v9 = v516;
LABEL_289:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v475);
LABEL_283:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v474);
          goto LABEL_172;
        }
        v479 = 0;
        v142 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v475);
        v517 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v142 + 56LL))(v142, &v479);
        if ( v517 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v759, &v517);
            v758 = 909;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v760, &v758);
            v143 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1184,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060E85,
              0,
              0,
              v143,
              (__int64)v760,
              (__int64)v759);
          }
          v9 = v517;
          goto LABEL_289;
        }
        v144 = 0;
        if ( v479 )
        {
          while ( 1 )
          {
            v1292 = 0;
            v1293 = 0;
            v145 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v475);
            v520 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v145 + 48LL))(v145, v144, &v1292);
            if ( v520 < 0 )
              break;
            v146 = BYTE8(v1292) & 0x1F | (32 * (v1292 & 7));
            if ( (_BYTE)v1293 )
            {
              v518 = GameInputDeviceInfoBuilder::AddRawDeviceReportInfo(v1310, 0, v146, WORD5(v1292));
              if ( v518 < 0 )
              {
                if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                {
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v762, &v518);
                  v761 = 923;
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v763, &v761);
                  v149 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                           v1185,
                           "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_180069000,
                    (unsigned int)&unk_180060AD0,
                    0,
                    0,
                    v149,
                    (__int64)v763,
                    (__int64)v762);
                }
                v9 = v518;
                goto LABEL_289;
              }
            }
            if ( BYTE13(v1292) )
            {
              v519 = GameInputDeviceInfoBuilder::AddRawDeviceReportInfo(v1310, 1, v146, WORD5(v1292));
              if ( v519 < 0 )
              {
                if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                {
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v765, &v519);
                  v764 = 930;
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v766, &v764);
                  v147 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                           v1186,
                           "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_180069000,
                    (unsigned int)&dword_180060F3C,
                    0,
                    0,
                    v147,
                    (__int64)v766,
                    (__int64)v765);
                }
                v9 = v519;
                goto LABEL_289;
              }
            }
            if ( ++v144 >= v479 )
              goto LABEL_306;
          }
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v768, &v520);
            v767 = 914;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v769, &v767);
            v150 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1187,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_18006019A,
              0,
              0,
              v150,
              (__int64)v769,
              (__int64)v768);
          }
          v9 = v520;
          goto LABEL_289;
        }
LABEL_306:
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v475);
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v474);
      }
      v470 = 0;
      v473 = 0;
      v469 = 0;
      v521 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, unsigned int *))(*(_QWORD *)a3 + 48LL))(
               a3,
               &v470);
      if ( v521 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v771, &v521);
          v770 = 938;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v772, &v770);
          v148 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1188,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&word_18005F066,
            0,
            0,
            v148,
            (__int64)v772,
            (__int64)v771);
        }
        v9 = v521;
        goto LABEL_172;
      }
      v522 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, unsigned int *))(*(_QWORD *)a3 + 56LL))(
               a3,
               &v473);
      if ( v522 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v774, &v522);
          v773 = 939;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v775, &v773);
          v151 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1189,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&dword_18005FB94,
            0,
            0,
            v151,
            (__int64)v775,
            (__int64)v774);
        }
        v9 = v522;
        goto LABEL_172;
      }
      v523 = (*(__int64 (__fastcall **)(struct Windows::Gaming::Input::IRawGameController *, unsigned int *))(*(_QWORD *)a3 + 88LL))(
               a3,
               &v469);
      if ( v523 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v777, &v523);
          v776 = 940;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v778, &v776);
          v152 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1190,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&unk_18005F130,
            0,
            0,
            v152,
            (__int64)v778,
            (__int64)v777);
        }
        v9 = v523;
        goto LABEL_172;
      }
      if ( (v470 & 0x80000000) != 0 || (v473 & 0x80000000) != 0 || (v469 & 0x80000000) != 0 )
      {
        v153 = -2147418113;
        v1077 = -2147418113;
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1079, &v1077);
          v1078 = 941;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1080, &v1078);
          v426 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1287,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)byte_1800608D5,
            0,
            0,
            v426,
            (__int64)v1080,
            (__int64)v1079);
        }
        goto LABEL_855;
      }
      GameInputDeviceInfoBuilder::AddControllerInfo((GameInputDeviceInfoBuilder *)v1310, v470, v473, v469);
      v153 = -2147024882;
      if ( v470 )
      {
        v154 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 576;
        v155 = 8LL * (int)v470;
        if ( !is_mul_ok((int)v470, 8u) )
          v155 = -1;
        v156 = operator new[](v155, (const struct std::nothrow_t *)&std::nothrow);
        utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v154, v156);
        v157 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        if ( !utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v157 + 576) )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            v779 = -2147024882;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v781, &v779);
            v780 = 954;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v782, &v780);
            v158 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1191,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060B0D,
              0,
              0,
              v158,
              (__int64)v782,
              (__int64)v781);
          }
LABEL_855:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v448);
          GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v435);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v434);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v439);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v442);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v438);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v432);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v441);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v429);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v431);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v436);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v437);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v430);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v440);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v433);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v447);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v443);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v444);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v445);
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v446);
          v9 = v153;
          goto LABEL_856;
        }
      }
      if ( v473 )
      {
        v159 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 584;
        v160 = operator new[]((int)v473, (const struct std::nothrow_t *)&std::nothrow);
        utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v159, v160);
        v161 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        if ( !utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v161 + 584) )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            v783 = -2147024882;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v785, &v783);
            v784 = 960;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v786, &v784);
            v162 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1192,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180061494,
              0,
              0,
              v162,
              (__int64)v786,
              (__int64)v785);
          }
          goto LABEL_855;
        }
      }
      if ( v469 )
      {
        v163 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 592;
        v164 = 4LL * (int)v469;
        if ( !is_mul_ok((int)v469, 4u) )
          v164 = -1;
        v165 = operator new[](v164, (const struct std::nothrow_t *)&std::nothrow);
        utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v163, v165);
        v166 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        if ( !utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v166 + 592) )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            v787 = -2147024882;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v789, &v787);
            v788 = 966;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v790, &v788);
            v167 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1193,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180060214,
              0,
              0,
              v167,
              (__int64)v790,
              (__int64)v789);
          }
          goto LABEL_855;
        }
      }
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v430) != -1 )
      {
        v480 = 0;
        v481 = 0;
        v538 = 0;
        v539 = 0;
        v540 = 0;
        v541 = 0;
        v542 = 0;
        v543 = 0;
        v544 = 0;
        v545 = 0;
        v546 = 0;
        v657 = 0;
        v656 = 0;
        v655 = 0;
        if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v429) == -1 )
        {
          v480 = 0;
          v481 = 0;
        }
        else
        {
          v168 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v524 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v168 + 64LL))(v168, 1, &v480);
          if ( v524 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v792, &v524);
              v791 = 980;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v793, &v791);
              v169 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1194,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&unk_18005F748,
                0,
                0,
                v169,
                (__int64)v793,
                (__int64)v792);
            }
            v9 = v524;
            goto LABEL_172;
          }
          v170 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v525 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v170 + 64LL))(v170, 2, &v481);
          if ( v525 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v795, &v525);
              v794 = 981;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v796, &v794);
              v171 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1195,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&word_1800627DE,
                0,
                0,
                v171,
                (__int64)v796,
                (__int64)v795);
            }
            v9 = v525;
            goto LABEL_172;
          }
        }
        v172 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v526 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v172 + 48LL))(v172, 1, &v538);
        if ( v526 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v798, &v526);
            v797 = 989;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v799, &v797);
            v173 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1196,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_18005F537,
              0,
              0,
              v173,
              (__int64)v799,
              (__int64)v798);
          }
          v9 = v526;
          goto LABEL_172;
        }
        v174 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v527 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v174 + 48LL))(v174, 2, &v539);
        if ( v527 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v801, &v527);
            v800 = 990;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v802, &v800);
            v175 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1197,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18006294C,
              0,
              0,
              v175,
              (__int64)v802,
              (__int64)v801);
          }
          v9 = v527;
          goto LABEL_172;
        }
        v176 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v528 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v176 + 48LL))(v176, 4, &v540);
        if ( v528 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v804, &v528);
            v803 = 991;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v805, &v803);
            v177 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1198,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005FA23,
              0,
              0,
              v177,
              (__int64)v805,
              (__int64)v804);
          }
          v9 = v528;
          goto LABEL_172;
        }
        v178 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v529 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v178 + 48LL))(v178, 8, &v541);
        if ( v529 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v807, &v529);
            v806 = 992;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v808, &v806);
            v179 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1199,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_1800605D0,
              0,
              0,
              v179,
              (__int64)v808,
              (__int64)v807);
          }
          v9 = v529;
          goto LABEL_172;
        }
        v180 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v530 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v180 + 48LL))(v180, 16, &v542);
        if ( v530 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v810, &v530);
            v809 = 993;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v811, &v809);
            v181 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1200,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060425,
              0,
              0,
              v181,
              (__int64)v811,
              (__int64)v810);
          }
          v9 = v530;
          goto LABEL_172;
        }
        v182 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v531 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v182 + 48LL))(v182, 32, &v543);
        if ( v531 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v813, &v531);
            v812 = 994;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v814, &v812);
            v183 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1201,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061829,
              0,
              0,
              v183,
              (__int64)v814,
              (__int64)v813);
          }
          v9 = v531;
          goto LABEL_172;
        }
        v184 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v532 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v184 + 48LL))(v184, 64, &v544);
        if ( v532 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v816, &v532);
            v815 = 995;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v817, &v815);
            v185 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1202,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180062764,
              0,
              0,
              v185,
              (__int64)v817,
              (__int64)v816);
          }
          v9 = v532;
          goto LABEL_172;
        }
        v186 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v533 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v186 + 48LL))(v186, 128, &v545);
        if ( v533 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v819, &v533);
            v818 = 996;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v820, &v818);
            v187 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1203,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_1800621A2,
              0,
              0,
              v187,
              (__int64)v820,
              (__int64)v819);
          }
          v9 = v533;
          goto LABEL_172;
        }
        v188 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v534 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v188 + 48LL))(v188, 256, &v546);
        if ( v534 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v822, &v534);
            v821 = 997;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v823, &v821);
            v189 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1204,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_1800606DA,
              0,
              0,
              v189,
              (__int64)v823,
              (__int64)v822);
          }
          v9 = v534;
          goto LABEL_172;
        }
        v190 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v535 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v190 + 48LL))(v190, 512, &v657);
        if ( v535 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v825, &v535);
            v824 = 998;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v826, &v824);
            v191 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1205,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18005EC14,
              0,
              0,
              v191,
              (__int64)v826,
              (__int64)v825);
          }
          v9 = v535;
          goto LABEL_172;
        }
        v192 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v536 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v192 + 48LL))(v192, 1024, &v656);
        if ( v536 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v828, &v536);
            v827 = 999;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v829, &v827);
            v193 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1206,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18006159E,
              0,
              0,
              v193,
              (__int64)v829,
              (__int64)v828);
          }
          v9 = v536;
          goto LABEL_172;
        }
        v194 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v430);
        v537 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v194 + 48LL))(v194, 2048, &v655);
        if ( v537 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v831, &v537);
            v830 = 1000;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v832, &v830);
            v195 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1207,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060CCB,
              0,
              0,
              v195,
              (__int64)v832,
              (__int64)v831);
          }
          v9 = v537;
          goto LABEL_172;
        }
        v1299 = 0;
        v1302 = 0;
        v1300 = 0;
        v1301 = 0;
        LODWORD(v1299) = anonymous_namespace_::ConvertWgiButtonLabel(v480);
        DWORD1(v1299) = anonymous_namespace_::ConvertWgiButtonLabel(v481);
        DWORD2(v1299) = anonymous_namespace_::ConvertWgiButtonLabel(v538);
        HIDWORD(v1299) = anonymous_namespace_::ConvertWgiButtonLabel(v539);
        LODWORD(v1300) = anonymous_namespace_::ConvertWgiButtonLabel(v540);
        DWORD1(v1300) = anonymous_namespace_::ConvertWgiButtonLabel(v541);
        DWORD2(v1300) = anonymous_namespace_::ConvertWgiButtonLabel(v542);
        HIDWORD(v1300) = anonymous_namespace_::ConvertWgiButtonLabel(v543);
        LODWORD(v1301) = anonymous_namespace_::ConvertWgiButtonLabel(v544);
        DWORD1(v1301) = anonymous_namespace_::ConvertWgiButtonLabel(v545);
        DWORD2(v1301) = anonymous_namespace_::ConvertWgiButtonLabel(v546);
        HIDWORD(v1301) = anonymous_namespace_::ConvertWgiButtonLabel(v657);
        LODWORD(v1302) = anonymous_namespace_::ConvertWgiButtonLabel(v656);
        HIDWORD(v1302) = anonymous_namespace_::ConvertWgiButtonLabel(v655);
        v654 = GameInputDeviceInfoBuilder::AddArcadeStickInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputArcadeStickInfo *)&v1299);
        if ( v654 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v834, &v654);
            v833 = 1018;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v835, &v833);
            v196 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1208,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180061300,
              0,
              0,
              v196,
              (__int64)v835,
              (__int64)v834);
          }
          v9 = v654;
          goto LABEL_172;
        }
      }
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v437) != -1 )
      {
        v482 = 0;
        v483 = 0;
        v648 = 0;
        v647 = 0;
        if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v429) == -1 )
        {
          v482 = 0;
          v483 = 0;
        }
        else
        {
          v197 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v653 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v197 + 64LL))(v197, 1, &v482);
          if ( v653 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v837, &v653);
              v836 = 1028;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v838, &v836);
              v198 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1209,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)byte_180062ABD,
                0,
                0,
                v198,
                (__int64)v838,
                (__int64)v837);
            }
            v9 = v653;
            goto LABEL_172;
          }
          v199 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v652 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v199 + 64LL))(v199, 2, &v483);
          if ( v652 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v840, &v652);
              v839 = 1029;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v841, &v839);
              v200 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1210,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)word_18006240A,
                0,
                0,
                v200,
                (__int64)v841,
                (__int64)v840);
            }
            v9 = v652;
            goto LABEL_172;
          }
        }
        v201 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v437);
        v651 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v201 + 56LL))(v201, 1, &v648);
        if ( v651 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v843, &v651);
            v842 = 1037;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v844, &v842);
            v202 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1211,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061CB5,
              0,
              0,
              v202,
              (__int64)v844,
              (__int64)v843);
          }
          v9 = v651;
          goto LABEL_172;
        }
        v203 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v437);
        v650 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v203 + 56LL))(v203, 2, &v647);
        if ( v650 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v846, &v650);
            v845 = 1038;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v847, &v845);
            v204 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1212,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18006060D,
              0,
              0,
              v204,
              (__int64)v847,
              (__int64)v846);
          }
          v9 = v650;
          goto LABEL_172;
        }
        v646 = 0;
        v205 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v437);
        v649 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v205 + 48LL))(v205, &v646);
        if ( v649 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v849, &v649);
            v848 = 1041;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v850, &v848);
            v206 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1213,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_180060912,
              0,
              0,
              v206,
              (__int64)v850,
              (__int64)v849);
          }
          v9 = v649;
          goto LABEL_172;
        }
        v1290 = 0;
        v1291 = 0;
        LODWORD(v1290) = anonymous_namespace_::ConvertWgiButtonLabel(v482);
        DWORD1(v1290) = anonymous_namespace_::ConvertWgiButtonLabel(v483);
        DWORD2(v1290) = anonymous_namespace_::ConvertWgiButtonLabel(v648);
        HIDWORD(v1290) = anonymous_namespace_::ConvertWgiButtonLabel(v647);
        if ( v646 )
          v1291 = (v646 != 1) + 1;
        else
          v1291 = 0;
        v645 = GameInputDeviceInfoBuilder::AddFlightStickInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputFlightStickInfo *)&v1290);
        if ( v645 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v852, &v645);
            v851 = 1053;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v853, &v851);
            v207 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1214,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180061524,
              0,
              0,
              v207,
              (__int64)v853,
              (__int64)v852);
          }
          v9 = v645;
          goto LABEL_172;
        }
      }
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v436) != -1 )
      {
        HString::HString((HString *)v452);
        v208 = Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad2>::GetAddressOf(v452);
        v644 = Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad>::CopyTo<Windows::Gaming::Input::IGamepad2>(
                 &v436,
                 v208);
        if ( v644 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v855, &v644);
            v854 = 1060;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v856, &v854);
            v209 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1215,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005FFA3,
              0,
              0,
              v209,
              (__int64)v856,
              (__int64)v855);
          }
          v9 = v644;
LABEL_472:
          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v452);
          goto LABEL_172;
        }
        v658 = 0;
        v547 = 0;
        v548 = 0;
        v549 = 0;
        v550 = 0;
        v551 = 0;
        v552 = 0;
        v553 = 0;
        v554 = 0;
        v555 = 0;
        v556 = 0;
        v557 = 0;
        v558 = 0;
        v559 = 0;
        v210 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v643 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v210 + 48LL))(v210, 1, &v658);
        if ( v643 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v858, &v643);
            v857 = 1067;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v859, &v857);
            v211 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1216,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180061006,
              0,
              0,
              v211,
              (__int64)v859,
              (__int64)v858);
          }
          v9 = v643;
          goto LABEL_472;
        }
        v212 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v642 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v212 + 48LL))(v212, 2, &v547);
        if ( v642 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v861, &v642);
            v860 = 1068;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v862, &v860);
            v213 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1217,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_1800600E3,
              0,
              0,
              v213,
              (__int64)v862,
              (__int64)v861);
          }
          v9 = v642;
          goto LABEL_472;
        }
        v214 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v641 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v214 + 48LL))(v214, 4, &v548);
        if ( v641 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v864, &v641);
            v863 = 1069;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v865, &v863);
            v215 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1218,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005FD55,
              0,
              0,
              v215,
              (__int64)v865,
              (__int64)v864);
          }
          v9 = v641;
          goto LABEL_472;
        }
        v216 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v640 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v216 + 48LL))(v216, 8, &v549);
        if ( v640 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v867, &v640);
            v866 = 1070;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v868, &v866);
            v217 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1219,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18005EC94,
              0,
              0,
              v217,
              (__int64)v868,
              (__int64)v867);
          }
          v9 = v640;
          goto LABEL_472;
        }
        v218 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v639 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v218 + 48LL))(v218, 16, &v550);
        if ( v639 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v870, &v639);
            v869 = 1071;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v871, &v869);
            v219 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1220,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F46D,
              0,
              0,
              v219,
              (__int64)v871,
              (__int64)v870);
          }
          v9 = v639;
          goto LABEL_472;
        }
        v220 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v638 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v220 + 48LL))(v220, 32, &v551);
        if ( v638 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v873, &v638);
            v872 = 1072;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v874, &v872);
            v221 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1221,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061F03,
              0,
              0,
              v221,
              (__int64)v874,
              (__int64)v873);
          }
          v9 = v638;
          goto LABEL_472;
        }
        v222 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v637 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v222 + 48LL))(v222, 64, &v552);
        if ( v637 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v876, &v637);
            v875 = 1073;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v877, &v875);
            v223 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1222,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_180062727,
              0,
              0,
              v223,
              (__int64)v877,
              (__int64)v876);
          }
          v9 = v637;
          goto LABEL_472;
        }
        v224 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v636 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v224 + 48LL))(v224, 128, &v553);
        if ( v636 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v879, &v636);
            v878 = 1074;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v880, &v878);
            v225 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1223,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18006036E,
              0,
              0,
              v225,
              (__int64)v880,
              (__int64)v879);
          }
          v9 = v636;
          goto LABEL_472;
        }
        v226 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v635 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v226 + 48LL))(v226, 256, &v554);
        if ( v635 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v882, &v635);
            v881 = 1075;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v883, &v881);
            v227 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1224,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18005EF1C,
              0,
              0,
              v227,
              (__int64)v883,
              (__int64)v882);
          }
          v9 = v635;
          goto LABEL_472;
        }
        v228 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v634 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v228 + 48LL))(v228, 512, &v555);
        if ( v634 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v885, &v634);
            v884 = 1076;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v886, &v884);
            v229 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1225,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18006269E,
              0,
              0,
              v229,
              (__int64)v886,
              (__int64)v885);
          }
          v9 = v634;
          goto LABEL_472;
        }
        v230 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v632 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v230 + 48LL))(v230, 1024, &v556);
        if ( v632 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v888, &v632);
            v887 = 1077;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v889, &v887);
            v231 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1226,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F70B,
              0,
              0,
              v231,
              (__int64)v889,
              (__int64)v888);
          }
          v9 = v632;
          goto LABEL_472;
        }
        v232 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v631 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v232 + 48LL))(v232, 2048, &v557);
        if ( v631 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v891, &v631);
            v890 = 1078;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v892, &v890);
            v233 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1227,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180060898,
              0,
              0,
              v233,
              (__int64)v892,
              (__int64)v891);
          }
          v9 = v631;
          goto LABEL_472;
        }
        v234 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v604 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v234 + 48LL))(v234, 4096, &v558);
        if ( v604 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v894, &v604);
            v893 = 1079;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v895, &v893);
            v235 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1228,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_18005F1AA,
              0,
              0,
              v235,
              (__int64)v895,
              (__int64)v894);
          }
          v9 = v604;
          goto LABEL_472;
        }
        v236 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v452);
        v633 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v236 + 48LL))(
                 v236,
                 0x2000,
                 &v559);
        if ( v633 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v897, &v633);
            v896 = 1080;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v898, &v896);
            v237 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1229,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180060C8E,
              0,
              0,
              v237,
              (__int64)v898,
              (__int64)v897);
          }
          v9 = v633;
          goto LABEL_472;
        }
        v1303 = 0;
        v1306 = 0;
        v1304 = 0;
        v1305 = 0;
        LODWORD(v1303) = anonymous_namespace_::ConvertWgiButtonLabel(v658);
        DWORD1(v1303) = anonymous_namespace_::ConvertWgiButtonLabel(v547);
        DWORD2(v1303) = anonymous_namespace_::ConvertWgiButtonLabel(v548);
        HIDWORD(v1303) = anonymous_namespace_::ConvertWgiButtonLabel(v549);
        LODWORD(v1304) = anonymous_namespace_::ConvertWgiButtonLabel(v550);
        DWORD1(v1304) = anonymous_namespace_::ConvertWgiButtonLabel(v551);
        DWORD2(v1304) = anonymous_namespace_::ConvertWgiButtonLabel(v552);
        HIDWORD(v1304) = anonymous_namespace_::ConvertWgiButtonLabel(v553);
        LODWORD(v1305) = anonymous_namespace_::ConvertWgiButtonLabel(v554);
        DWORD1(v1305) = anonymous_namespace_::ConvertWgiButtonLabel(v555);
        DWORD2(v1305) = anonymous_namespace_::ConvertWgiButtonLabel(v556);
        HIDWORD(v1305) = anonymous_namespace_::ConvertWgiButtonLabel(v557);
        LODWORD(v1306) = anonymous_namespace_::ConvertWgiButtonLabel(v558);
        HIDWORD(v1306) = anonymous_namespace_::ConvertWgiButtonLabel(v559);
        v560 = GameInputDeviceInfoBuilder::AddGamepadInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputGamepadInfo *)&v1303);
        if ( v560 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v900, &v560);
            v899 = 1098;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v901, &v899);
            v238 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1230,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18006098C,
              0,
              0,
              v238,
              (__int64)v901,
              (__int64)v900);
          }
          v9 = v560;
          goto LABEL_472;
        }
        Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v452);
      }
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v431) != -1 )
      {
        v484 = 0;
        v1121 = 0.0;
        v485 = 0;
        v574 = 0;
        v575 = 0;
        v576 = 0;
        v577 = 0;
        v578 = 0;
        v579 = 0;
        v457[0] = 0;
        v456 = 0;
        v455 = 0;
        v580 = 0;
        if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v429) == -1 )
        {
          v484 = 0;
          v485 = 0;
        }
        else
        {
          v239 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v561 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v239 + 64LL))(v239, 1, &v484);
          if ( v561 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v903, &v561);
              v902 = 1113;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v904, &v902);
              v240 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1231,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&unk_180062A80,
                0,
                0,
                v240,
                (__int64)v904,
                (__int64)v903);
            }
            v9 = v561;
            goto LABEL_172;
          }
          v241 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
          v562 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v241 + 64LL))(v241, 2, &v485);
          if ( v562 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v906, &v562);
              v905 = 1114;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v907, &v905);
              v242 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1232,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)byte_18005F5B1,
                0,
                0,
                v242,
                (__int64)v907,
                (__int64)v906);
            }
            v9 = v562;
            goto LABEL_172;
          }
        }
        v243 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v563 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v243 + 96LL))(v243, 1, &v574);
        if ( v563 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v909, &v563);
            v908 = 1122;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v910, &v908);
            v244 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1233,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_18006094F,
              0,
              0,
              v244,
              (__int64)v910,
              (__int64)v909);
          }
          v9 = v563;
          goto LABEL_172;
        }
        v245 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v564 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v245 + 96LL))(v245, 2, &v575);
        if ( v564 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v912, &v564);
            v911 = 1123;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v913, &v911);
            v246 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1234,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005F0F3,
              0,
              0,
              v246,
              (__int64)v913,
              (__int64)v912);
          }
          v9 = v564;
          goto LABEL_172;
        }
        v247 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v565 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v247 + 96LL))(v247, 4, &v576);
        if ( v565 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v915, &v565);
            v914 = 1124;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v916, &v914);
            v248 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1235,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_18005FD92,
              0,
              0,
              v248,
              (__int64)v916,
              (__int64)v915);
          }
          v9 = v565;
          goto LABEL_172;
        }
        v249 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v566 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v249 + 96LL))(v249, 8, &v577);
        if ( v566 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v918, &v566);
            v917 = 1125;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v919, &v917);
            v250 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1236,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_1800619FD,
              0,
              0,
              v250,
              (__int64)v919,
              (__int64)v918);
          }
          v9 = v566;
          goto LABEL_172;
        }
        v251 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v567 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v251 + 96LL))(v251, 16, &v578);
        if ( v567 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v921, &v567);
            v920 = 1126;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v922, &v920);
            v252 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1237,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180060264,
              0,
              0,
              v252,
              (__int64)v922,
              (__int64)v921);
          }
          v9 = v567;
          goto LABEL_172;
        }
        v253 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v568 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v253 + 96LL))(v253, 32, &v579);
        if ( v568 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v924, &v568);
            v923 = 1127;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v925, &v923);
            v254 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1238,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060FC9,
              0,
              0,
              v254,
              (__int64)v925,
              (__int64)v924);
          }
          v9 = v568;
          goto LABEL_172;
        }
        v255 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v569 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v255 + 48LL))(v255, v457);
        if ( v569 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v927, &v569);
            v926 = 1128;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v928, &v926);
            v256 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1239,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005FC4B,
              0,
              0,
              v256,
              (__int64)v928,
              (__int64)v927);
          }
          v9 = v569;
          goto LABEL_172;
        }
        v257 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v570 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v257 + 56LL))(v257, &v456);
        if ( v570 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v930, &v570);
            v929 = 1129;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v931, &v929);
            v258 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1240,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061FCD,
              0,
              0,
              v258,
              (__int64)v931,
              (__int64)v930);
          }
          v9 = v570;
          goto LABEL_172;
        }
        v259 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v571 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v259 + 64LL))(v259, &v455);
        if ( v571 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v933, &v571);
            v932 = 1130;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v934, &v932);
            v260 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1241,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061043,
              0,
              0,
              v260,
              (__int64)v934,
              (__int64)v933);
          }
          v9 = v571;
          goto LABEL_172;
        }
        v261 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v572 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v261 + 72LL))(v261, &v580);
        if ( v572 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v936, &v572);
            v935 = 1131;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v937, &v935);
            v262 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1242,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18005FE9C,
              0,
              0,
              v262,
              (__int64)v937,
              (__int64)v936);
          }
          v9 = v572;
          goto LABEL_172;
        }
        v263 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v431);
        v573 = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v263 + 80LL))(v263, &v1121);
        if ( v573 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v939, &v573);
            v938 = 1132;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v940, &v938);
            v264 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1243,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_18005EE28,
              0,
              0,
              v264,
              (__int64)v940,
              (__int64)v939);
          }
          v9 = v573;
          goto LABEL_172;
        }
        v1294 = 0;
        v1295 = 0;
        v1296 = 0;
        LODWORD(v1294) = anonymous_namespace_::ConvertWgiButtonLabel(v484);
        DWORD1(v1294) = anonymous_namespace_::ConvertWgiButtonLabel(v485);
        DWORD2(v1294) = anonymous_namespace_::ConvertWgiButtonLabel(v574);
        HIDWORD(v1294) = anonymous_namespace_::ConvertWgiButtonLabel(v575);
        LODWORD(v1295) = anonymous_namespace_::ConvertWgiButtonLabel(v576);
        DWORD1(v1295) = anonymous_namespace_::ConvertWgiButtonLabel(v577);
        DWORD2(v1295) = anonymous_namespace_::ConvertWgiButtonLabel(v578);
        v265 = anonymous_namespace_::ConvertWgiButtonLabel(v579);
        LOBYTE(v1296) = v457[0] != 0;
        HIDWORD(v1295) = v265;
        BYTE1(v1296) = v456 != 0;
        DWORD2(v1296) = v580;
        BYTE2(v1296) = v455 != 0;
        *((float *)&v1296 + 3) = v1121;
        DWORD1(v1296) = v580 != 0;
        v581 = GameInputDeviceInfoBuilder::AddRacingWheelInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputRacingWheelInfo *)&v1294);
        if ( v581 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v942, &v581);
            v941 = 1150;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v943, &v941);
            v266 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1244,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180061080,
              0,
              0,
              v266,
              (__int64)v943,
              (__int64)v942);
          }
          v9 = v581;
          goto LABEL_172;
        }
      }
      if ( (unsigned int)Microsoft::WRL::ComPtr<Windows::Gaming::Input::Custom::IXusbGameControllerProvider>::operator int Microsoft::WRL::Details::BoolStruct::*(&v429) != -1 )
      {
        v602 = 0;
        v603 = 0;
        v662 = 0;
        v605 = 0;
        v606 = 0;
        v607 = 0;
        v608 = 0;
        v609 = 0;
        v610 = 0;
        v611 = 0;
        v612 = 0;
        v613 = 0;
        v614 = 0;
        v615 = 0;
        v616 = 0;
        v617 = 0;
        v618 = 0;
        v619 = 0;
        v620 = 0;
        v621 = 0;
        v267 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v582 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v267 + 64LL))(v267, 1, &v602);
        if ( v582 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v945, &v582);
            v944 = 1163;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v946, &v944);
            v268 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1245,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18005FC0E,
              0,
              0,
              v268,
              (__int64)v946,
              (__int64)v945);
          }
          v9 = v582;
          goto LABEL_172;
        }
        v269 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v583 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v269 + 64LL))(v269, 2, &v603);
        if ( v583 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v948, &v583);
            v947 = 1164;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v949, &v947);
            v270 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1246,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_1800625E7,
              0,
              0,
              v270,
              (__int64)v949,
              (__int64)v948);
          }
          v9 = v583;
          goto LABEL_172;
        }
        v271 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v584 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v271 + 64LL))(v271, 4, &v662);
        if ( v584 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v951, &v584);
            v950 = 1165;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v952, &v950);
            v272 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1247,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_180062AFA,
              0,
              0,
              v272,
              (__int64)v952,
              (__int64)v951);
          }
          v9 = v584;
          goto LABEL_172;
        }
        v273 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v585 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v273 + 64LL))(v273, 8, &v605);
        if ( v585 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v954, &v585);
            v953 = 1166;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v955, &v953);
            v274 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1248,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180061980,
              0,
              0,
              v274,
              (__int64)v955,
              (__int64)v954);
          }
          v9 = v585;
          goto LABEL_172;
        }
        v275 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v586 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v275 + 64LL))(v275, 16, &v606);
        if ( v586 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v957, &v586);
            v956 = 1167;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v958, &v956);
            v276 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1249,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005EE65,
              0,
              0,
              v276,
              (__int64)v958,
              (__int64)v957);
          }
          v9 = v586;
          goto LABEL_172;
        }
        v277 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v587 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v277 + 64LL))(v277, 32, &v607);
        if ( v587 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v960, &v587);
            v959 = 1168;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v961, &v959);
            v278 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1250,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&byte_180061457,
              0,
              0,
              v278,
              (__int64)v961,
              (__int64)v960);
          }
          v9 = v587;
          goto LABEL_172;
        }
        v279 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v588 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v279 + 64LL))(v279, 64, &v608);
        if ( v588 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v963, &v588);
            v962 = 1169;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v964, &v962);
            v280 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1251,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180062296,
              0,
              0,
              v280,
              (__int64)v964,
              (__int64)v963);
          }
          v9 = v588;
          goto LABEL_172;
        }
        v281 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v589 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v281 + 64LL))(v281, 128, &v609);
        if ( v589 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v966, &v589);
            v965 = 1170;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v967, &v965);
            v282 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1252,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_18005FF16,
              0,
              0,
              v282,
              (__int64)v967,
              (__int64)v966);
          }
          v9 = v589;
          goto LABEL_172;
        }
        v283 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v590 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v283 + 56LL))(v283, 1, &v610);
        if ( v590 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v969, &v590);
            v968 = 1171;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v970, &v968);
            v284 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1253,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_1800603AB,
              0,
              0,
              v284,
              (__int64)v970,
              (__int64)v969);
          }
          v9 = v590;
          goto LABEL_172;
        }
        v285 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v591 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v285 + 56LL))(v285, 2, &v611);
        if ( v591 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v972, &v591);
            v971 = 1172;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v973, &v971);
            v286 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1254,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18006015D,
              0,
              0,
              v286,
              (__int64)v973,
              (__int64)v972);
          }
          v9 = v591;
          goto LABEL_172;
        }
        v287 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v592 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v287 + 56LL))(v287, 4, &v612);
        if ( v592 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v975, &v592);
            v974 = 1173;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v976, &v974);
            v288 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1255,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&unk_180061618,
              0,
              0,
              v288,
              (__int64)v976,
              (__int64)v975);
          }
          v9 = v592;
          goto LABEL_172;
        }
        v289 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v593 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v289 + 56LL))(v289, 8, &v613);
        if ( v593 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v978, &v593);
            v977 = 1174;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v979, &v977);
            v290 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1256,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_180060C14,
              0,
              0,
              v290,
              (__int64)v979,
              (__int64)v978);
          }
          v9 = v593;
          goto LABEL_172;
        }
        v291 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v594 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v291 + 56LL))(v291, 16, &v614);
        if ( v594 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v981, &v594);
            v980 = 1175;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v982, &v980);
            v292 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1257,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18006138D,
              0,
              0,
              v292,
              (__int64)v982,
              (__int64)v981);
          }
          v9 = v594;
          goto LABEL_172;
        }
        v293 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v595 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v293 + 56LL))(v293, 32, &v615);
        if ( v595 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v984, &v595);
            v983 = 1176;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v985, &v983);
            v294 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1258,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_1800629C9,
              0,
              0,
              v294,
              (__int64)v985,
              (__int64)v984);
          }
          v9 = v595;
          goto LABEL_172;
        }
        v295 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v596 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v295 + 56LL))(v295, 64, &v616);
        if ( v596 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v987, &v596);
            v986 = 1177;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v988, &v986);
            v296 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1259,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_18005F224,
              0,
              0,
              v296,
              (__int64)v988,
              (__int64)v987);
          }
          v9 = v596;
          goto LABEL_172;
        }
        v297 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v597 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v297 + 56LL))(v297, 128, &v617);
        if ( v597 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v990, &v597);
            v989 = 1178;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v991, &v989);
            v298 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1260,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180061866,
              0,
              0,
              v298,
              (__int64)v991,
              (__int64)v990);
          }
          v9 = v597;
          goto LABEL_172;
        }
        v299 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v598 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v299 + 56LL))(v299, 256, &v618);
        if ( v598 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v993, &v598);
            v992 = 1179;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v994, &v992);
            v300 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1261,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180060A56,
              0,
              0,
              v300,
              (__int64)v994,
              (__int64)v993);
          }
          v9 = v598;
          goto LABEL_172;
        }
        v301 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v599 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v301 + 56LL))(v301, 512, &v619);
        if ( v599 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v996, &v599);
            v995 = 1180;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v997, &v995);
            v302 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1262,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180061E89,
              0,
              0,
              v302,
              (__int64)v997,
              (__int64)v996);
          }
          v9 = v599;
          goto LABEL_172;
        }
        v303 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v600 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v303 + 56LL))(v303, 1024, &v620);
        if ( v600 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v999, &v600);
            v998 = 1181;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1000, &v998);
            v304 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1263,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180062259,
              0,
              0,
              v304,
              (__int64)v1000,
              (__int64)v999);
          }
          v9 = v600;
          goto LABEL_172;
        }
        v305 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v429);
        v601 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v305 + 56LL))(v305, 2048, &v621);
        if ( v601 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1002, &v601);
            v1001 = 1182;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1003, &v1001);
            v306 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1264,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180062336,
              0,
              0,
              v306,
              (__int64)v1003,
              (__int64)v1002);
          }
          v9 = v601;
          goto LABEL_172;
        }
        memset_0(v1309, 0, 0x54u);
        v1309[0] = anonymous_namespace_::ConvertWgiButtonLabel(v602);
        v1309[1] = anonymous_namespace_::ConvertWgiButtonLabel(v603);
        v1309[2] = anonymous_namespace_::ConvertWgiButtonLabel(v662);
        v1309[3] = anonymous_namespace_::ConvertWgiButtonLabel(v605);
        v1309[4] = anonymous_namespace_::ConvertWgiButtonLabel(v606);
        v1309[5] = anonymous_namespace_::ConvertWgiButtonLabel(v607);
        v1309[6] = anonymous_namespace_::ConvertWgiButtonLabel(v608);
        v1309[7] = anonymous_namespace_::ConvertWgiButtonLabel(v609);
        v1309[8] = anonymous_namespace_::ConvertWgiButtonLabel(v610);
        v1309[9] = anonymous_namespace_::ConvertWgiButtonLabel(v611);
        v1309[10] = anonymous_namespace_::ConvertWgiButtonLabel(v612);
        v1309[11] = anonymous_namespace_::ConvertWgiButtonLabel(v613);
        v1309[12] = anonymous_namespace_::ConvertWgiButtonLabel(v614);
        v1309[13] = anonymous_namespace_::ConvertWgiButtonLabel(v615);
        v1309[14] = anonymous_namespace_::ConvertWgiButtonLabel(v616);
        v1309[15] = anonymous_namespace_::ConvertWgiButtonLabel(v617);
        v1309[16] = anonymous_namespace_::ConvertWgiButtonLabel(v618);
        v1309[17] = anonymous_namespace_::ConvertWgiButtonLabel(v619);
        v1309[18] = anonymous_namespace_::ConvertWgiButtonLabel(v620);
        v1309[19] = anonymous_namespace_::ConvertWgiButtonLabel(v621);
        v1309[20] = -1;
        v622 = GameInputDeviceInfoBuilder::AddUiNavigationInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputUiNavigationInfo *)v1309);
        if ( v622 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1005, &v622);
            v1004 = 1207;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1006, &v1004);
            v307 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1265,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)word_180061242,
              0,
              0,
              v307,
              (__int64)v1006,
              (__int64)v1005);
          }
          v9 = v622;
          goto LABEL_172;
        }
      }
      if ( v450 )
      {
        v308 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v448);
        v623 = (*(__int64 (__fastcall **)(__int64, UCHAR *, _BYTE *))(*(_QWORD *)v308 + 32LL))(v308, pbOutput, v1322);
        if ( v623 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1008, &v623);
            v1007 = 1213;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1009, &v1007);
            v309 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1266,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180060A93,
              0,
              0,
              v309,
              (__int64)v1009,
              (__int64)v1008);
          }
          v9 = v623;
          goto LABEL_172;
        }
        v310 = v1323 != 0;
        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 237) = v310;
      }
      if ( *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 237) )
      {
        v624 = GameInputDeviceInfoBuilder::AddTouchSensorInfo(
                 (GameInputDeviceInfoBuilder *)v1310,
                 (const struct GameInputTouchSensorInfo *)v1322);
        if ( v624 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1011, &v624);
            v1010 = 1219;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1012, &v1010);
            v311 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1267,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&dword_1800607A4,
              0,
              0,
              v311,
              (__int64)v1012,
              (__int64)v1011);
          }
          v9 = v624;
          goto LABEL_172;
        }
      }
      v1307 = 0;
      v1308 = 0;
      if ( v450 )
      {
        v312 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v448);
        v313 = (*(__int64 (__fastcall **)(__int64, UCHAR *, __int64 *))(*(_QWORD *)v312 + 40LL))(v312, pbOutput, &v1307);
        v625 = v313;
        if ( v313 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1014, &v625);
            v1013 = 1228;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1015, &v1013);
            v314 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1268,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)&word_180062A06,
              0,
              0,
              v314,
              (__int64)v1015,
              (__int64)v1014);
          }
          v9 = v625;
          goto LABEL_172;
        }
        if ( !v313 )
        {
          v626 = GameInputDeviceInfoBuilder::AddMotionInfo(
                   (GameInputDeviceInfoBuilder *)v1310,
                   (const struct GameInputMotionInfo *)&v1307);
          if ( v626 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1017, &v626);
              v1016 = 1233;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1018, &v1016);
              v315 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1269,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)byte_180062A43,
                0,
                0,
                v315,
                (__int64)v1018,
                (__int64)v1017);
            }
            v9 = v626;
            goto LABEL_172;
          }
        }
      }
      v316 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      v317 = utl::out_ptr<void,utl::unique_ptr<FeedbackManager,utl::default_delete<FeedbackManager>>,>(
               v1289,
               v316 + 104);
      v318 = (HANDLE **)Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad2>::GetAddressOf(v317);
      v319 = (struct IGameInputServerDevice *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      v486 = FeedbackManager::Create(v319, (const struct APP_LOCAL_DEVICE_ID *)pbOutput, v318);
      utl::out_ptr_t<utl::unique_ptr<FeedbackManager,utl::default_delete<FeedbackManager>>,FeedbackManager *,>::~out_ptr_t<utl::unique_ptr<FeedbackManager,utl::default_delete<FeedbackManager>>,FeedbackManager *,>(v1289);
      if ( v486 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1020, &v486);
          v1019 = 1238;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1021, &v1019);
          v320 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1270,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&unk_180060D58,
            0,
            0,
            v320,
            (__int64)v1021,
            (__int64)v1020);
        }
        v9 = v486;
        goto LABEL_172;
      }
      v321 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      if ( Microsoft::WRL::Wrappers::HString::IsValid((Microsoft::WRL::Wrappers::HString *)(v321 + 104)) )
      {
        v322 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        v323 = (FeedbackManager *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v322 + 104);
        DeviceInfo = FeedbackManager::GetDeviceInfo(v323);
        v627 = GameInputDeviceInfoBuilder::AddHapticFeedbackMotorInfo(v1310, *((unsigned int *)DeviceInfo + 8));
        if ( v627 < 0 )
        {
          if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1023, &v627);
            v1022 = 1244;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1024, &v1022);
            v325 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1271,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_180062661,
              0,
              0,
              v325,
              (__int64)v1024,
              (__int64)v1023);
          }
          v9 = v627;
          goto LABEL_172;
        }
        if ( *(_DWORD *)DeviceInfo )
        {
          v628 = GameInputDeviceInfoBuilder::AddForceFeedbackMotorInfos(
                   (GameInputDeviceInfoBuilder *)v1310,
                   *(_DWORD *)DeviceInfo,
                   *((const struct GameInputForceFeedbackMotorInfo **)DeviceInfo + 2));
          if ( v628 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1026, &v628);
              v1025 = 1251;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1027, &v1025);
              v326 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1272,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&byte_180061E0F,
                0,
                0,
                v326,
                (__int64)v1027,
                (__int64)v1026);
            }
            v9 = v628;
            goto LABEL_172;
          }
        }
      }
      v477 = 0;
      v629 = GameInputDeviceInfoBuilder::Make((GameInputDeviceInfoBuilder *)v1310, &v477);
      if ( v629 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1029, &v629);
          v1028 = 1257;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1030, &v1028);
          v327 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1273,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&byte_18006290F,
            0,
            0,
            v327,
            (__int64)v1030,
            (__int64)v1029);
        }
        v9 = v629;
        goto LABEL_172;
      }
      v328 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v328 + 88, v477);
      v329 = (char *)operator new[](0x340u, (const struct std::nothrow_t *)&std::nothrow);
      v1145 = (struct GameInputDeviceInfoPrivate *)v329;
      v330 = v329;
      if ( !v329 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          v1073 = -2147024882;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1075, &v1073);
          v1074 = 1261;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1076, &v1074);
          v425 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1286,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)&byte_18005F84F,
            0,
            0,
            v425,
            (__int64)v1076,
            (__int64)v1075);
        }
        goto LABEL_855;
      }
      memset_0(v329 + 4, 0, 0x33Cu);
      memset_0(v330 + 4, 0, 0x33Cu);
      *(_DWORD *)v330 = 832;
      *((_QWORD *)v330 + 1) = *(_QWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                        + 216);
      HString::HString((HString *)v489);
      v331 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v434);
      v332 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v331 + 136LL);
      v333 = Microsoft::WRL::ComPtr<Windows::Gaming::Input::IGamepad2>::GetAddressOf(v489);
      v630 = v332(v331, v333);
      if ( v630 < 0 )
      {
        if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1032, &v630);
          v1031 = 1274;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1033, &v1031);
          v334 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1274,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)word_180060EC2,
            0,
            0,
            v334,
            (__int64)v1033,
            (__int64)v1032);
        }
        v9 = v630;
        HString::~HString((HString *)v489);
        goto LABEL_172;
      }
      length = 0;
      v335 = (HSTRING)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v489);
      StringRawBuffer = WindowsGetStringRawBuffer(v335, &length);
      if ( StringRawBuffer && length - 1 <= 0xC6 )
      {
        wcsncpy_s((wchar_t *)v330 + 208, 0xC7u, StringRawBuffer, length);
        *(_WORD *)&v330[2 * length + 416] = 0;
      }
      else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
      {
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1035, &length);
        v337 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1275, "Unexpected PnP device string length");
        v1034 = 1289;
        v338 = v337;
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1036, &v1034);
        v339 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1276, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180069000,
          (unsigned int)byte_18005EC51,
          0,
          0,
          v339,
          (__int64)v1036,
          v338,
          (__int64)v1035);
      }
      v340 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v340 + 96, v330);
      v341 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 112;
      v342 = (CallbackDataLayout *)operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v342 )
        v342 = CallbackDataLayout::CallbackDataLayout(v342, v477);
      utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v341, v342);
      v343 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
      if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v343 + 112) )
      {
        v661 = (SharedBufferLayout *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                    + 120);
        v345 = (ReadingDataLayout *)operator new[](0xA8u, (const struct std::nothrow_t *)&std::nothrow);
        v346 = v345;
        if ( v345 )
        {
          v347 = v477;
          v348 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
          v345 = ReadingDataLayout::ReadingDataLayout(v346, *(_BYTE *)(v348 + 236), 0, v347);
        }
        utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v661, v345);
        v349 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
        if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v349 + 120) )
        {
          v661 = (SharedBufferLayout *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                      + 128);
          v351 = (InputDataLayout *)operator new[](0x30u, (const struct std::nothrow_t *)&std::nothrow);
          v352 = v351;
          if ( v351 )
          {
            v353 = v477;
            v354 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
            v355 = (const struct ReadingDataLayout *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v354 + 120);
            v351 = InputDataLayout::InputDataLayout(v352, 0x200u, v355, v353);
          }
          utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v661, v351);
          v356 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
          if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v356 + 128) )
          {
            v358 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
            if ( !Microsoft::WRL::Wrappers::HString::IsValid((Microsoft::WRL::Wrappers::HString *)(v358 + 104)) )
              goto LABEL_812;
            v359 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
            v360 = (FeedbackManager *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v359 + 104);
            v361 = FeedbackManager::GetDeviceInfo(v360);
            v362 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 136;
            v363 = (FeedbackDataLayout *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v363 )
              v363 = FeedbackDataLayout::FeedbackDataLayout(
                       v363,
                       v477,
                       *((const struct ForceFeedbackResourceProfile **)v361 + 1));
            utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v362, v363);
            v364 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
            if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v364 + 136) )
            {
LABEL_812:
              *(_QWORD *)&v472.Data1 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                     + 144;
              v366 = (SharedBufferLayout *)operator new[](0x24u, (const struct std::nothrow_t *)&std::nothrow);
              v661 = v366;
              if ( v366 )
              {
                v367 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                v368 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v367 + 136);
                v369 = v477;
                v370 = (const struct FeedbackDataLayout *)v368;
                v371 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                v372 = (const struct InputDataLayout *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v371 + 128);
                v373 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                v374 = (const struct CallbackDataLayout *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v373 + 112);
                v366 = SharedBufferLayout::SharedBufferLayout(v661, v374, v372, v1145, v369, v370);
              }
              utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(
                *(_QWORD *)&v472.Data1,
                v366);
              v375 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
              if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v375 + 144) )
              {
                v377 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                v378 = (LayoutBase *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v377 + 120);
                RequiredBufferSize = LayoutBase::GetRequiredBufferSize(v378);
                *(_DWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 188) = RequiredBufferSize;
                v380 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 152;
                v381 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                v382 = operator new[](*(unsigned int *)(v381 + 188), (const struct std::nothrow_t *)&std::nothrow);
                utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v380, v382);
                v383 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v383 + 152) )
                {
                  v385 = *(_DWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                   + 188);
                  v386 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                  v387 = (void *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v386 + 152);
                  memset_0(v387, 0, v385);
                  v388 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                  v389 = (ReadingDataLayout *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v388 + 120);
                  v390 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                  v391 = (void *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v390 + 152);
                  CommonDataPtr = ReadingDataLayout::GetCommonDataPtr(v389, v391);
                  v393 = operator~(1);
                  *((_DWORD *)CommonDataPtr + 3) = operator&(*((unsigned int *)v477 + 26), v393);
                  v394 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 160;
                  v395 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                  v396 = operator new[](*(unsigned int *)(v395 + 188), (const struct std::nothrow_t *)&std::nothrow);
                  utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v394, v396);
                  v397 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                  if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v397 + 160) )
                  {
                    v399 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449) + 168;
                    v400 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                    v401 = operator new[](*(unsigned int *)(v400 + 188), (const struct std::nothrow_t *)&std::nothrow);
                    utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v399, v401);
                    v402 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                    if ( utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v402 + 168) )
                    {
                      v404 = (GameInputServerDevice *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                      GameInputServerDevice::SendGamepadVibration(v404, 0);
                      if ( v1122 )
                      {
                        v405 = (*(__int64 (__fastcall **)(struct IGameInputServerInputRouter *))(*(_QWORD *)v1122 + 40LL))(v1122);
                        v406 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                        utl::atomic<unsigned int>::operator=(v406 + 212, v405);
                        *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                 + 230) = 1;
                        if ( *(_QWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                       + 80) )
                        {
                          v407 = *(unsigned int *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                                 + 188);
                          v408 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                               + 176;
                          v409 = operator new[](v407 + 16, (const struct std::nothrow_t *)&std::nothrow);
                          utl::unique_ptr<ReadingDataLayout,utl::default_delete<ReadingDataLayout>>::reset(v408, v409);
                          v410 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                          if ( !utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(v410 + 176) )
                          {
                            if ( (unsigned int)dword_180069000 > 2
                              && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                            {
                              v1069 = -2147024882;
                              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1071, &v1069);
                              v1070 = 1357;
                              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1072, &v1070);
                              v411 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                                       v1285,
                                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                (unsigned int)&dword_180069000,
                                (unsigned int)byte_1800610BD,
                                0,
                                0,
                                v411,
                                (__int64)v1072,
                                (__int64)v1071);
                            }
                            goto LABEL_836;
                          }
                        }
                        v412 = v1122;
                        v413 = *(unsigned __int8 (__fastcall **)(struct IGameInputServerInputRouter *, _QWORD, __int64, __int64, int))(*(_QWORD *)v1122 + 48LL);
                        if ( *(_QWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                       + 80) )
                          v414 = 0;
                        else
                          v414 = *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                          + 226);
                        if ( *(_QWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                       + 80) )
                          v415 = 0;
                        else
                          v415 = *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                          + 225);
                        if ( *(_QWORD *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                       + 80) )
                          v416 = 0;
                        else
                          v416 = *(_BYTE *)(utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449)
                                          + 224);
                        v417 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                        v418 = utl::atomic<unsigned int>::operator unsigned int(v417 + 212);
                        LOBYTE(ppv) = v414;
                        LOBYTE(v419) = v415;
                        LOBYTE(v420) = v416;
                        if ( !v413(v412, v418, v420, v419, ppv) )
                        {
                          v421 = utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                          utl::atomic<unsigned int>::operator=(v421 + 212, 0);
                          HString::~HString((HString *)v489);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v448);
                          GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v435);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v434);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v439);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v442);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v438);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v432);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v441);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v429);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v431);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v436);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v437);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v430);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v440);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v433);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v447);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v443);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v444);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v445);
                          Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v446);
                          v9 = 1;
                          goto LABEL_856;
                        }
                      }
                      v422 = (GameInputServerDevice *)utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::get(&v449);
                      GameInputServerDevice::LogDeviceCreated(v422);
                      v423 = utl::unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>::release(&v449);
                      *v1146 = (struct GameInputServerDevice *)v423;
                      HString::~HString((HString *)v489);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v448);
                      GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v435);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v434);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v439);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v442);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v438);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v432);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v441);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v429);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v431);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v436);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v437);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v430);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v440);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v433);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v447);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v443);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v444);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v445);
                      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v446);
                      utl::unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>::~unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>(&v449);
                      return 0;
                    }
                    if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                    {
                      v1065 = -2147024882;
                      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1067, &v1065);
                      v1066 = 1340;
                      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1068, &v1066);
                      v403 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                               v1284,
                               "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                        (unsigned int)&dword_180069000,
                        (unsigned int)byte_18005ECD1,
                        0,
                        0,
                        v403,
                        (__int64)v1068,
                        (__int64)v1067);
                    }
                  }
                  else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                  {
                    v1061 = -2147024882;
                    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1063, &v1061);
                    v1062 = 1338;
                    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1064, &v1062);
                    v398 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                             v1283,
                             "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      (unsigned int)&dword_180069000,
                      (unsigned int)byte_18005F9D3,
                      0,
                      0,
                      v398,
                      (__int64)v1064,
                      (__int64)v1063);
                  }
                }
                else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
                {
                  v1057 = -2147024882;
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1059, &v1057);
                  v1058 = 1318;
                  _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1060, &v1058);
                  v384 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                           v1282,
                           "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_180069000,
                    (unsigned int)byte_18005FF53,
                    0,
                    0,
                    v384,
                    (__int64)v1060,
                    (__int64)v1059);
                }
              }
              else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
              {
                v1053 = -2147024882;
                _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1055, &v1053);
                v1054 = 1313;
                _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1056, &v1054);
                v376 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                         v1281,
                         "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_180069000,
                  (unsigned int)&byte_18006171F,
                  0,
                  0,
                  v376,
                  (__int64)v1056,
                  (__int64)v1055);
              }
            }
            else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
            {
              v1049 = -2147024882;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1051, &v1049);
              v1050 = 1309;
              _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1052, &v1050);
              v365 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                       v1280,
                       "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180069000,
                (unsigned int)&unk_1800618E0,
                0,
                0,
                v365,
                (__int64)v1052,
                (__int64)v1051);
            }
          }
          else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
          {
            v1045 = -2147024882;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1047, &v1045);
            v1046 = 1303;
            _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1048, &v1046);
            v357 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                     v1279,
                     "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180069000,
              (unsigned int)byte_18005EF59,
              0,
              0,
              v357,
              (__int64)v1048,
              (__int64)v1047);
          }
        }
        else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
        {
          v1041 = -2147024882;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1043, &v1041);
          v1042 = 1300;
          _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1044, &v1042);
          v350 = _tlgWrapSz<char>::_tlgWrapSz<char>(
                   v1278,
                   "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_180069000,
            (unsigned int)byte_180060DE5,
            0,
            0,
            v350,
            (__int64)v1044,
            (__int64)v1043);
        }
      }
      else if ( (unsigned int)dword_180069000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180069000, 1024) )
      {
        v1037 = -2147024882;
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1039, &v1037);
        v1038 = 1297;
        _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v1040, &v1038);
        v344 = _tlgWrapSz<char>::_tlgWrapSz<char>(v1277, "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180069000,
          (unsigned int)&unk_180061930,
          0,
          0,
          v344,
          (__int64)v1040,
          (__int64)v1039);
      }
LABEL_836:
      HString::~HString((HString *)v489);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(v448);
      GameInputDeviceInfoBuilder::~GameInputDeviceInfoBuilder((GameInputDeviceInfoBuilder *)v1310);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v435);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v434);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v439);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v442);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v438);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v432);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v441);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v429);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v431);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v436);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v437);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v430);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v440);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v433);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v447);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v443);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v444);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v445);
      Microsoft::WRL::ComPtr<Windows::Gaming::Input::IRawGameController2>::~ComPtr<Windows::Gaming::Input::IRawGameController2>(&v446);
      v9 = -2147024882;
      goto LABEL_856;
    }
  }
  else
  {
    v449 = 0;
  }
  if ( (unsigned int)dword_180069000 > 2
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v1085 = -2147024882;
    v1086 = 646;
    v1147 = "onecore\\xbox\\gameinput\\server\\GameInputServerDevice.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180069000,
      (unsigned int)&unk_180061F40,
      0,
      0,
      (__int64)&v1147,
      (__int64)&v1086,
      (__int64)&v1085);
  }
  utl::unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>::~unique_ptr<GameInputServerDevice,utl::default_delete<GameInputServerDevice>>(&v449);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003197c  push    rbp
0x18003197e  push    rbx
0x18003197f  push    rsi
0x180031980  push    rdi
0x180031981  push    r12
0x180031983  push    r13
0x180031985  push    r14
0x180031987  push    r15
0x180031989  lea     rbp, [rsp-1608h]
0x180031991  mov     eax, 1708h
0x180031996  call    __chkstk_0
0x18003199b  sub     rsp, rax
0x18003199e  mov     rax, cs:__security_cookie
0x1800319a5  xor     rax, rsp
0x1800319a8  mov     [rbp+1640h+var_50], rax
0x1800319af  mov     rbx, rcx
0x1800319b2  mov     [rbp+1640h+var_B90], rdx
0x1800319b9  mov     rsi, r8
0x1800319bc  mov     [rbp+1640h+var_AD0], r9
0x1800319c3  mov     r15, rdx
0x1800319c6  xor     edi, edi
0x1800319c8  mov     [r9], rdi
0x1800319cb  xor     edx, edx; Flags
0x1800319cd  mov     rcx, gs:60h
0x1800319d6  mov     r8d, 260h; Size
0x1800319dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800319e0  call    cs:__imp_RtlAllocateHeap
0x1800319e7  nop     dword ptr [rax+rax+00h]
0x1800319ec  test    rax, rax
0x1800319ef  jz      loc_18003AB72
0x1800319f5  mov     r9, rsi; struct Windows::Gaming::Input::IRawGameController *
0x1800319f8  mov     r8, r15; struct IGameInputServerInputRouter *
0x1800319fb  mov     rdx, rbx; struct GameInputServer *
0x1800319fe  mov     rcx, rax; this
0x180031a01  call    ??0GameInputServerDevice@@AEAA@PEAVGameInputServer@@PEAUIGameInputServerInputRouter@@PEAUIRawGameController@Input@Gaming@Windows@@@Z; GameInputServerDevice::GameInputServerDevice(GameInputServer *,IGameInputServerInputRouter *,Windows::Gaming::Input::IRawGameController *)
0x180031a06  mov     [rbp+1640h+var_1650], rax
0x180031a0a  mov     rbx, rax
0x180031a0d  test    rax, rax
0x180031a10  jz      loc_18003AB76
0x180031a16  xor     edx, edx; Val
0x180031a18  mov     [rbp+1640h+var_1668], rdi
0x180031a1c  lea     r8d, [rdi+40h]; Size
0x180031a20  mov     [rbp+1640h+var_1670], rdi
0x180031a24  lea     rcx, [rbp+1640h+var_90]; void *
0x180031a2b  mov     [rbp+1640h+var_1678], rdi
0x180031a2f  mov     [rbp+1640h+var_1680], rdi
0x180031a33  mov     [rbp+1640h+var_1660], rdi
0x180031a37  mov     [rsp+1740h+var_16D0], rdi
0x180031a3c  mov     [rbp+1640h+var_1698], rdi
0x180031a40  mov     [rsp+1740h+var_16E8], rdi
0x180031a45  mov     [rbp+1640h+var_16B0], rdi
0x180031a49  mov     [rbp+1640h+var_16B8], rdi
0x180031a4d  mov     [rsp+1740h+var_16E0], rdi
0x180031a52  mov     [rsp+1740h+var_16F0], rdi
0x180031a57  mov     [rbp+1640h+var_1690], rdi
0x180031a5b  mov     [rsp+1740h+var_16D8], rdi
0x180031a60  mov     [rbp+1640h+var_16A8], rdi
0x180031a64  mov     [rbp+1640h+var_1688], rdi
0x180031a68  mov     [rbp+1640h+var_16A0], rdi
0x180031a6c  mov     [rsp+1740h+var_16C8], rdi
0x180031a71  mov     [rbp+1640h+var_16C0], rdi
0x180031a75  call    memset_0
0x180031a7a  mov     rcx, [rbx+210h]
0x180031a81  lea     r8, [rsp+1740h+var_16D0]
0x180031a86  lea     rdx, _GUID_1baf6522_5f64_42c5_8267_b9fe2215bfbd
0x180031a8d  mov     rax, [rcx]
0x180031a90  mov     rax, [rax]
0x180031a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a98  mov     ebx, eax
0x180031a9a  test    eax, eax
0x180031a9c  jns     loc_180031B2A
0x180031aa2  mov     ecx, cs:dword_180069000
0x180031aa8  lea     r12d, [rdi+2]
0x180031aac  cmp     ecx, r12d
0x180031aaf  jbe     loc_180032847
0x180031ab5  mov     rdx, cs:qword_180069018
0x180031abc  mov     r15d, 400h
0x180031ac2  mov     rcx, cs:qword_180069010
0x180031ac9  test    r15, rcx
0x180031acc  jz      loc_180032847
0x180031ad2  mov     rax, rdx
0x180031ad5  and     rax, r15
0x180031ad8  cmp     rax, rdx
0x180031adb  jnz     loc_180032847
0x180031ae1  lea     rax, [rbp+1640h+var_C2C]
0x180031ae8  mov     [rbp+1640h+var_C2C], ebx
0x180031aee  mov     [rsp+1740h+var_1710], rax
0x180031af3  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031afa  lea     rax, [rbp+1640h+var_C28]
0x180031b01  mov     [rbp+1640h+var_C28], 29Eh
0x180031b0b  mov     [rsp+1740h+var_1718], rax
0x180031b10  lea     rdx, byte_18005EEDF
0x180031b17  lea     rax, [rbp+1640h+var_B78]
0x180031b1e  mov     [rbp+1640h+var_B78], r13
0x180031b25  jmp     loc_180031BDA
0x180031b2a  mov     rax, [rbp+1640h+var_1650]
0x180031b2e  lea     r8, [rbp+1640h+var_1698]
0x180031b32  lea     rdx, _GUID_43c0c035_bb73_4756_a787_3ed6bea617bd
0x180031b39  mov     rcx, [rax+210h]
0x180031b40  mov     rax, [rcx]
0x180031b43  mov     rax, [rax]
0x180031b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b4b  mov     ebx, eax
0x180031b4d  test    eax, eax
0x180031b4f  jns     loc_180031BF6
0x180031b55  mov     ecx, cs:dword_180069000
0x180031b5b  mov     r12d, 2
0x180031b61  cmp     ecx, r12d
0x180031b64  jbe     loc_180032847
0x180031b6a  mov     rdx, cs:qword_180069018
0x180031b71  mov     r15d, 400h
0x180031b77  mov     rcx, cs:qword_180069010
0x180031b7e  test    r15, rcx
0x180031b81  jz      loc_180032847
0x180031b87  mov     rax, rdx
0x180031b8a  and     rax, r15
0x180031b8d  cmp     rax, rdx
0x180031b90  jnz     loc_180032847
0x180031b96  lea     rax, [rbp+1640h+var_C24]
0x180031b9d  mov     [rbp+1640h+var_C24], ebx
0x180031ba3  mov     [rsp+1740h+var_1710], rax
0x180031ba8  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031baf  lea     rax, [rbp+1640h+var_C20]
0x180031bb6  mov     [rbp+1640h+var_C20], 29Fh
0x180031bc0  mov     [rsp+1740h+var_1718], rax
0x180031bc5  lea     rdx, byte_180061561
0x180031bcc  lea     rax, [rbp+1640h+var_B70]
0x180031bd3  mov     [rbp+1640h+var_B70], r13
0x180031bda  xor     r9d, r9d
0x180031bdd  mov     [rsp+1740h+ppv], rax
0x180031be2  xor     r8d, r8d
0x180031be5  lea     rcx, dword_180069000
0x180031bec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180031bf1  jmp     loc_180032847
0x180031bf6  mov     r9d, 20h ; ' '; unsigned int
0x180031bfc  mov     [rbp+1640h+var_138], rdi
0x180031c03  lea     rdx, ?RuntimeClass_Windows_Gaming_Input_ArcadeStick@@3QBGB; "Windows.Gaming.Input.ArcadeStick"
0x180031c0a  lea     rcx, [rbp+1640h+hstringHeader]; hstringHeader
0x180031c11  lea     r14d, [r9+1]
0x180031c15  mov     r8d, r14d; unsigned int
0x180031c18  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031c1d  mov     rcx, [rbp+1640h+var_138]
0x180031c24  lea     r8, [rbp+1640h+var_1668]
0x180031c28  lea     rdx, _GUID_52b5d744_bb86_445a_b59c_596f0e2a49df
0x180031c2f  call    cs:__imp_RoGetActivationFactory
0x180031c36  nop     dword ptr [rax+rax+00h]
0x180031c3b  mov     [rbp+1640h+var_138], rdi
0x180031c42  mov     ebx, eax
0x180031c44  test    eax, eax
0x180031c46  jns     loc_180031CD4
0x180031c4c  mov     ecx, cs:dword_180069000
0x180031c52  lea     r12d, [r14-1Fh]
0x180031c56  cmp     ecx, r12d
0x180031c59  jbe     loc_180032847
0x180031c5f  mov     rdx, cs:qword_180069018
0x180031c66  mov     r15d, 400h
0x180031c6c  mov     rcx, cs:qword_180069010
0x180031c73  test    r15, rcx
0x180031c76  jz      loc_180032847
0x180031c7c  mov     rax, rdx
0x180031c7f  and     rax, r15
0x180031c82  cmp     rax, rdx
0x180031c85  jnz     loc_180032847
0x180031c8b  lea     rax, [rbp+1640h+var_C1C]
0x180031c92  mov     [rbp+1640h+var_C1C], ebx
0x180031c98  mov     [rsp+1740h+var_1710], rax
0x180031c9d  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031ca4  lea     rax, [rbp+1640h+var_C18]
0x180031cab  mov     [rbp+1640h+var_C18], 2A1h
0x180031cb5  mov     [rsp+1740h+var_1718], rax
0x180031cba  lea     rdx, dword_180062624
0x180031cc1  lea     rax, [rbp+1640h+var_B68]
0x180031cc8  mov     [rbp+1640h+var_B68], r13
0x180031ccf  jmp     loc_180031BDA
0x180031cd4  mov     r9d, 20h ; ' '; unsigned int
0x180031cda  mov     [rbp+1640h+var_118], rdi
0x180031ce1  mov     r8d, r14d; unsigned int
0x180031ce4  lea     rdx, ?RuntimeClass_Windows_Gaming_Input_FlightStick@@3QBGB; "Windows.Gaming.Input.FlightStick"
0x180031ceb  lea     rcx, [rbp+1640h+var_130]; hstringHeader
0x180031cf2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031cf7  mov     rcx, [rbp+1640h+var_118]
0x180031cfe  lea     r8, [rbp+1640h+var_1670]
0x180031d02  lea     rdx, _GUID_5514924a_fecc_435e_83dc_5cec8a18a520
0x180031d09  call    cs:__imp_RoGetActivationFactory
0x180031d10  nop     dword ptr [rax+rax+00h]
0x180031d15  mov     [rbp+1640h+var_118], rdi
0x180031d1c  mov     ebx, eax
0x180031d1e  test    eax, eax
0x180031d20  jns     loc_180031DB0
0x180031d26  mov     ecx, cs:dword_180069000
0x180031d2c  mov     r12d, 2
0x180031d32  cmp     ecx, r12d
0x180031d35  jbe     loc_180032847
0x180031d3b  mov     rdx, cs:qword_180069018
0x180031d42  mov     r15d, 400h
0x180031d48  mov     rcx, cs:qword_180069010
0x180031d4f  test    r15, rcx
0x180031d52  jz      loc_180032847
0x180031d58  mov     rax, rdx
0x180031d5b  and     rax, r15
0x180031d5e  cmp     rax, rdx
0x180031d61  jnz     loc_180032847
0x180031d67  lea     rax, [rbp+1640h+var_C14]
0x180031d6e  mov     [rbp+1640h+var_C14], ebx
0x180031d74  mov     [rsp+1740h+var_1710], rax
0x180031d79  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031d80  lea     rax, [rbp+1640h+var_C10]
0x180031d87  mov     [rbp+1640h+var_C10], 2A2h
0x180031d91  mov     [rsp+1740h+var_1718], rax
0x180031d96  lea     rdx, word_18005F3B6
0x180031d9d  lea     rax, [rbp+1640h+var_B60]
0x180031da4  mov     [rbp+1640h+var_B60], r13
0x180031dab  jmp     loc_180031BDA
0x180031db0  mov     r9d, 1Ch; unsigned int
0x180031db6  mov     [rbp+1640h+var_F8], rdi
0x180031dbd  lea     rdx, ?RuntimeClass_Windows_Gaming_Input_Gamepad@@3QBGB; "Windows.Gaming.Input.Gamepad"
0x180031dc4  lea     rcx, [rbp+1640h+var_110]; hstringHeader
0x180031dcb  lea     r8d, [r9+1]; unsigned int
0x180031dcf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031dd4  mov     rcx, [rbp+1640h+var_F8]
0x180031ddb  lea     r8, [rbp+1640h+var_1678]
0x180031ddf  lea     rdx, _GUID_42676dc5_0856_47c4_9213_b395504c3a3c
0x180031de6  call    cs:__imp_RoGetActivationFactory
0x180031ded  nop     dword ptr [rax+rax+00h]
0x180031df2  mov     [rbp+1640h+var_F8], rdi
0x180031df9  mov     ebx, eax
0x180031dfb  test    eax, eax
0x180031dfd  jns     loc_180031E8D
0x180031e03  mov     ecx, cs:dword_180069000
0x180031e09  mov     r12d, 2
0x180031e0f  cmp     ecx, r12d
0x180031e12  jbe     loc_180032847
0x180031e18  mov     rdx, cs:qword_180069018
0x180031e1f  mov     r15d, 400h
0x180031e25  mov     rcx, cs:qword_180069010
0x180031e2c  test    r15, rcx
0x180031e2f  jz      loc_180032847
0x180031e35  mov     rax, rdx
0x180031e38  and     rax, r15
0x180031e3b  cmp     rax, rdx
0x180031e3e  jnz     loc_180032847
0x180031e44  lea     rax, [rbp+1640h+var_C0C]
0x180031e4b  mov     [rbp+1640h+var_C0C], ebx
0x180031e51  mov     [rsp+1740h+var_1710], rax
0x180031e56  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031e5d  lea     rax, [rbp+1640h+var_C08]
0x180031e64  mov     [rbp+1640h+var_C08], 2A3h
0x180031e6e  mov     [rsp+1740h+var_1718], rax
0x180031e73  lea     rdx, byte_18005EDEB
0x180031e7a  lea     rax, [rbp+1640h+var_B58]
0x180031e81  mov     [rbp+1640h+var_B58], r13
0x180031e88  jmp     loc_180031BDA
0x180031e8d  mov     r9d, 20h ; ' '; unsigned int
0x180031e93  mov     [rbp+1640h+var_D8], rdi
0x180031e9a  mov     r8d, r14d; unsigned int
0x180031e9d  lea     rdx, ?RuntimeClass_Windows_Gaming_Input_RacingWheel@@3QBGB; "Windows.Gaming.Input.RacingWheel"
0x180031ea4  lea     rcx, [rbp+1640h+var_F0]; hstringHeader
0x180031eab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031eb0  mov     rcx, [rbp+1640h+var_D8]
0x180031eb7  lea     r8, [rbp+1640h+var_1680]
0x180031ebb  lea     rdx, _GUID_e666bcaa_edfd_4323_a9f6_3c384048d1ed
0x180031ec2  call    cs:__imp_RoGetActivationFactory
0x180031ec9  nop     dword ptr [rax+rax+00h]
0x180031ece  mov     [rbp+1640h+var_D8], rdi
0x180031ed5  mov     ebx, eax
0x180031ed7  test    eax, eax
0x180031ed9  jns     loc_180031F69
0x180031edf  mov     ecx, cs:dword_180069000
0x180031ee5  mov     r12d, 2
0x180031eeb  cmp     ecx, r12d
0x180031eee  jbe     loc_180032847
0x180031ef4  mov     rdx, cs:qword_180069018
0x180031efb  mov     r15d, 400h
0x180031f01  mov     rcx, cs:qword_180069010
0x180031f08  test    r15, rcx
0x180031f0b  jz      loc_180032847
0x180031f11  mov     rax, rdx
0x180031f14  and     rax, r15
0x180031f17  cmp     rax, rdx
0x180031f1a  jnz     loc_180032847
0x180031f20  lea     rax, [rbp+1640h+var_C04]
0x180031f27  mov     [rbp+1640h+var_C04], ebx
0x180031f2d  mov     [rsp+1740h+var_1710], rax
0x180031f32  lea     r13, aOnecoreXboxGam_47; "onecore\\xbox\\gameinput\\server\\GameI"...
0x180031f39  lea     rax, [rbp+1640h+var_C00]
0x180031f40  mov     [rbp+1640h+var_C00], 2A4h
0x180031f4a  mov     [rsp+1740h+var_1718], rax
0x180031f4f  lea     rdx, byte_180060717
0x180031f56  lea     rax, [rbp+1640h+var_B50]
0x180031f5d  mov     [rbp+1640h+var_B50], r13
0x180031f64  jmp     loc_180031BDA
0x180031f69  mov     r9d, 2Bh ; '+'; unsigned int
0x180031f6f  mov     [rbp+1640h+var_B8], rdi
0x180031f76  lea     rdx, ?RuntimeClass_Windows_Gaming_Input_UINavigationController@@3QBGB; "Windows.Gaming.Input.UINavigationContro"...
0x180031f7d  lea     rcx, [rbp+1640h+var_D0]; hstringHeader
0x180031f84  lea     r8d, [r9+1]; unsigned int
0x180031f88  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031f8d  mov     rcx, [rbp+1640h+var_B8]
0x180031f94  lea     r8, [rbp+1640h+var_1660]
0x180031f98  lea     rdx, _GUID_e0cb28e3_b20b_4b0b_9ed4_f3d53cec0de4
  ... truncated ...
```
