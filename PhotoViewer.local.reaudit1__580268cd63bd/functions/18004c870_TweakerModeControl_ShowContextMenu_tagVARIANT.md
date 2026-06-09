# TweakerModeControl::ShowContextMenu(tagVARIANT *)

- ea: `0x18004c870`
- end: `0x180056fad`
- name: `?ShowContextMenu@TweakerModeControl@@AEAAXPEAUtagVARIANT@@@Z`
- size: `42813`
- prototype: `void __fastcall(TweakerModeControl *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c400`

## callees

- `0x1800037d8`
- `0x180004908`
- `0x18000cb74`
- `0x18001f078`
- `0x1800271ec`
- `0x18002923c`
- `0x18002a0b4`
- `0x18002a0e0`
- `0x18002a10c`
- `0x18002b768`
- `0x18002c4ec`
- `0x1800355d4`
- `0x1800363a8`
- `0x18003f800`
- `0x180040264`
- `0x18004c870`
- `0x18006ad60`
- `0x18006b2dc`
- `0x18006b4b8`
- `0x18006f850`
- `0x18006f8ac`
- `0x180077a74`
- `0x180077aa0`
- `0x180077b1c`
- `0x180077b3c`
- `0x18007aff4`
- `0x18007b024`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004d037`
- `KERNEL32!GetCurrentThreadId` at `0x18004d037`
- `KERNEL32!FreeLibrary` at `0x18004cd2c`
- `KERNEL32!FreeLibrary` at `0x180050760`
- `KERNEL32!FreeLibrary` at `0x180050d54`
- `KERNEL32!FreeLibrary` at `0x1800523b9`
- `KERNEL32!FreeLibrary` at `0x180053f31`
- `KERNEL32!FreeLibrary` at `0x18005439b`
- `KERNEL32!FreeLibrary` at `0x18005462b`
- `KERNEL32!FreeLibrary` at `0x180056d52`
- `KERNEL32!FreeLibrary` at `0x18004cd2c`
- `KERNEL32!FreeLibrary` at `0x180050760`
- `KERNEL32!FreeLibrary` at `0x180050d54`
- `KERNEL32!FreeLibrary` at `0x1800523b9`
- `KERNEL32!FreeLibrary` at `0x180053f31`
- `KERNEL32!FreeLibrary` at `0x18005439b`
- `KERNEL32!FreeLibrary` at `0x18005462b`
- `KERNEL32!FreeLibrary` at `0x180056d52`
- `KERNEL32!GetModuleHandleExW` at `0x18004ce4e`
- `KERNEL32!GetModuleHandleExW` at `0x18004f0ed`
- `KERNEL32!GetModuleHandleExW` at `0x180050804`
- `KERNEL32!GetModuleHandleExW` at `0x180050df8`
- `KERNEL32!GetModuleHandleExW` at `0x180054434`
- `KERNEL32!GetModuleHandleExW` at `0x180055c28`
- `KERNEL32!GetModuleHandleExW` at `0x18004ce4e`
- `KERNEL32!GetModuleHandleExW` at `0x18004f0ed`
- `KERNEL32!GetModuleHandleExW` at `0x180050804`
- `KERNEL32!GetModuleHandleExW` at `0x180050df8`
- `KERNEL32!GetModuleHandleExW` at `0x180054434`
- `KERNEL32!GetModuleHandleExW` at `0x180055c28`
- `KERNEL32!GetModuleFileNameW` at `0x18004d743`
- `KERNEL32!GetModuleFileNameW` at `0x18004d743`
- `KERNEL32!GetProcAddress` at `0x18004cef0`
- `KERNEL32!GetProcAddress` at `0x18004f136`
- `KERNEL32!GetProcAddress` at `0x1800508c9`
- `KERNEL32!GetProcAddress` at `0x180050ebd`
- `KERNEL32!GetProcAddress` at `0x1800544ee`
- `KERNEL32!GetProcAddress` at `0x180055c65`
- `KERNEL32!GetProcAddress` at `0x18004cef0`
- `KERNEL32!GetProcAddress` at `0x18004f136`
- `KERNEL32!GetProcAddress` at `0x1800508c9`
- `KERNEL32!GetProcAddress` at `0x180050ebd`
- `KERNEL32!GetProcAddress` at `0x1800544ee`
- `KERNEL32!GetProcAddress` at `0x180055c65`
- `KERNEL32!GetLastError` at `0x18004ce0d`
- `KERNEL32!GetLastError` at `0x18004cfa9`
- `KERNEL32!GetLastError` at `0x18004d094`
- `KERNEL32!GetLastError` at `0x18004d17e`
- `KERNEL32!GetLastError` at `0x18004d758`
- `KERNEL32!GetLastError` at `0x18004d78a`
- `KERNEL32!GetLastError` at `0x18004f0f7`
- `KERNEL32!GetLastError` at `0x180050fde`
- `KERNEL32!GetLastError` at `0x18005106a`
- `KERNEL32!GetLastError` at `0x180051105`
- `KERNEL32!GetLastError` at `0x180051874`
- `KERNEL32!GetLastError` at `0x1800519b4`
- `KERNEL32!GetLastError` at `0x180051b4d`
- `KERNEL32!GetLastError` at `0x180051c33`
- `KERNEL32!GetLastError` at `0x180051ef5`
- `KERNEL32!GetLastError` at `0x180051f7c`
- `KERNEL32!GetLastError` at `0x1800526eb`
- `KERNEL32!GetLastError` at `0x180052c48`
- `KERNEL32!GetLastError` at `0x180052fff`
- `KERNEL32!GetLastError` at `0x180053047`
- `KERNEL32!GetLastError` at `0x1800531da`
- `KERNEL32!GetLastError` at `0x1800532ce`
- `KERNEL32!GetLastError` at `0x1800533be`
- `KERNEL32!GetLastError` at `0x1800538fb`
- `KERNEL32!GetLastError` at `0x180055c32`
- `KERNEL32!GetLastError` at `0x18004ce0d`
- `KERNEL32!GetLastError` at `0x18004cfa9`
- `KERNEL32!GetLastError` at `0x18004d094`
- `KERNEL32!GetLastError` at `0x18004d17e`
- `KERNEL32!GetLastError` at `0x18004d758`
- `KERNEL32!GetLastError` at `0x18004d78a`
- `KERNEL32!GetLastError` at `0x18004f0f7`
- `KERNEL32!GetLastError` at `0x180050fde`
- `KERNEL32!GetLastError` at `0x18005106a`
- `KERNEL32!GetLastError` at `0x180051105`
- `KERNEL32!GetLastError` at `0x180051874`
- `KERNEL32!GetLastError` at `0x1800519b4`
- `KERNEL32!GetLastError` at `0x180051b4d`
- `KERNEL32!GetLastError` at `0x180051c33`
- `KERNEL32!GetLastError` at `0x180051ef5`
- `KERNEL32!GetLastError` at `0x180051f7c`
- `KERNEL32!GetLastError` at `0x1800526eb`
- `KERNEL32!GetLastError` at `0x180052c48`
- `KERNEL32!GetLastError` at `0x180052fff`
- `KERNEL32!GetLastError` at `0x180053047`
- `KERNEL32!GetLastError` at `0x1800531da`
- `KERNEL32!GetLastError` at `0x1800532ce`
- `KERNEL32!GetLastError` at `0x1800533be`
- `KERNEL32!GetLastError` at `0x1800538fb`
- `KERNEL32!GetLastError` at `0x180055c32`
- `KERNEL32!LocalAlloc` at `0x18004d1d6`
- `KERNEL32!LocalAlloc` at `0x18004d1d6`
- `KERNEL32!HeapFree` at `0x18004cda0`
- `KERNEL32!HeapFree` at `0x18004d6b1`
- `KERNEL32!HeapFree` at `0x18004d6d6`
- `KERNEL32!HeapFree` at `0x18004d6ef`
- `KERNEL32!HeapFree` at `0x18004d708`
- `KERNEL32!HeapFree` at `0x18004e11c`
- `KERNEL32!HeapFree` at `0x18004e83a`
- `KERNEL32!HeapFree` at `0x18004e869`
- `KERNEL32!HeapFree` at `0x18004e898`
- `KERNEL32!HeapFree` at `0x18004e8bb`
- `KERNEL32!HeapFree` at `0x18004e908`
- `KERNEL32!HeapFree` at `0x18004e939`
- `KERNEL32!HeapFree` at `0x18004e965`
- `KERNEL32!HeapFree` at `0x18004e991`
- `KERNEL32!HeapFree` at `0x18004e9b2`
- `KERNEL32!HeapFree` at `0x18004eac5`
- `KERNEL32!HeapFree` at `0x18004eaf0`
- `KERNEL32!HeapFree` at `0x18004eb19`
- `KERNEL32!HeapFree` at `0x18004eb42`
- `KERNEL32!HeapFree` at `0x18004eb5e`
- `KERNEL32!HeapFree` at `0x18004eb7b`
- `KERNEL32!HeapFree` at `0x18004eb94`
- `KERNEL32!HeapFree` at `0x18004ebbe`
- `KERNEL32!HeapFree` at `0x18004ebe2`
- `KERNEL32!HeapFree` at `0x18004ec06`
- `KERNEL32!HeapFree` at `0x18004ec22`
- `KERNEL32!HeapFree` at `0x18004ec3f`
- `KERNEL32!HeapFree` at `0x18004edb5`
- `KERNEL32!HeapFree` at `0x18004f50f`
- `KERNEL32!HeapFree` at `0x18004f53b`
- `KERNEL32!HeapFree` at `0x18004f567`
- `KERNEL32!HeapFree` at `0x18004f588`
- `KERNEL32!HeapFree` at `0x18004f619`
- `KERNEL32!HeapFree` at `0x18004f646`
- `KERNEL32!HeapFree` at `0x18004f673`
- `KERNEL32!HeapFree` at `0x18004f694`
- `KERNEL32!HeapFree` at `0x180050952`
- `KERNEL32!HeapFree` at `0x180050f46`
- `KERNEL32!HeapFree` at `0x180054569`
- `KERNEL32!HeapFree` at `0x1800549c7`
- `KERNEL32!HeapFree` at `0x1800549e7`
- `KERNEL32!HeapFree` at `0x180054a00`
- `KERNEL32!HeapFree` at `0x180054a19`
- `KERNEL32!HeapFree` at `0x180054e83`
- `KERNEL32!HeapFree` at `0x18005559b`
- `KERNEL32!HeapFree` at `0x1800555c9`
- `KERNEL32!HeapFree` at `0x1800555f7`
- `KERNEL32!HeapFree` at `0x180055618`
- `KERNEL32!HeapFree` at `0x18005566e`
- `KERNEL32!HeapFree` at `0x1800556a1`
- `KERNEL32!HeapFree` at `0x1800556cf`
- `KERNEL32!HeapFree` at `0x1800556fd`
- `KERNEL32!HeapFree` at `0x180055720`
- `KERNEL32!HeapFree` at `0x180055938`
- `KERNEL32!HeapFree` at `0x180056029`
- `KERNEL32!HeapFree` at `0x180056055`
- `KERNEL32!HeapFree` at `0x180056081`
- `KERNEL32!HeapFree` at `0x1800560a2`
- `KERNEL32!HeapFree` at `0x180056133`
- `KERNEL32!HeapFree` at `0x180056161`
- `KERNEL32!HeapFree` at `0x18005618f`
- `KERNEL32!HeapFree` at `0x1800561b2`
- `KERNEL32!HeapFree` at `0x180056aa2`
- `KERNEL32!HeapFree` at `0x180056acb`
- `KERNEL32!HeapFree` at `0x180056aef`
- `KERNEL32!HeapFree` at `0x180056b13`
- `KERNEL32!HeapFree` at `0x180056b2f`
- `KERNEL32!HeapFree` at `0x180056b4f`
- `KERNEL32!HeapFree` at `0x180056b6b`
- `KERNEL32!HeapFree` at `0x180056b98`
- `KERNEL32!HeapFree` at `0x180056bbc`
- `KERNEL32!HeapFree` at `0x180056be0`
- `KERNEL32!HeapFree` at `0x180056bfc`
- `KERNEL32!HeapFree` at `0x180056c18`
- `KERNEL32!HeapFree` at `0x18004cda0`
- `KERNEL32!HeapFree` at `0x18004d6b1`
- `KERNEL32!HeapFree` at `0x18004d6d6`
- `KERNEL32!HeapFree` at `0x18004d6ef`
- `KERNEL32!HeapFree` at `0x18004d708`
- `KERNEL32!HeapFree` at `0x18004e11c`
- `KERNEL32!HeapFree` at `0x18004e83a`
- `KERNEL32!HeapFree` at `0x18004e869`
- `KERNEL32!HeapFree` at `0x18004e898`
- `KERNEL32!HeapFree` at `0x18004e8bb`
- `KERNEL32!HeapFree` at `0x18004e908`
- `KERNEL32!HeapFree` at `0x18004e939`
- `KERNEL32!HeapFree` at `0x18004e965`
- `KERNEL32!HeapFree` at `0x18004e991`
- `KERNEL32!HeapFree` at `0x18004e9b2`
- `KERNEL32!HeapFree` at `0x18004eac5`
- `KERNEL32!HeapFree` at `0x18004eaf0`
- `KERNEL32!HeapFree` at `0x18004eb19`
- `KERNEL32!HeapFree` at `0x18004eb42`
- `KERNEL32!HeapFree` at `0x18004eb5e`
- `KERNEL32!HeapFree` at `0x18004eb7b`
- `KERNEL32!HeapFree` at `0x18004eb94`
- `KERNEL32!HeapFree` at `0x18004ebbe`
- `KERNEL32!HeapFree` at `0x18004ebe2`
- `KERNEL32!HeapFree` at `0x18004ec06`
- `KERNEL32!HeapFree` at `0x18004ec22`
- `KERNEL32!HeapFree` at `0x18004ec3f`
- `KERNEL32!HeapFree` at `0x18004edb5`
- `KERNEL32!HeapFree` at `0x18004f50f`
- `KERNEL32!HeapFree` at `0x18004f53b`

## string_xrefs

- `0x18004f0e1`: `ntdll.dll`
- `0x180055c1c`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TweakerModeControl::ShowContextMenu(ModularWindow::ContextMenu **this, struct tagVARIANT *a2)
{
  ModularWindow::ContextMenu *v3; // rsi
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  _BYTE *v8; // rdi
  unsigned __int8 *v9; // rsi
  _BYTE *v10; // r14
  int v11; // r12d
  int v12; // r13d
  int v13; // r10d
  int v14; // r8d
  __int64 v15; // r15
  int v16; // ebx
  int v17; // r11d
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // r9d
  unsigned int v21; // r10d
  int v22; // r8d
  unsigned int v23; // r9d
  int v24; // r10d
  int v25; // edx
  int v26; // r8d
  unsigned int v27; // r9d
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // r10d
  unsigned int v31; // r8d
  int v32; // r9d
  int v33; // edx
  unsigned int v34; // r8d
  int v35; // r9d
  int v36; // edx
  int v37; // r8d
  unsigned int v38; // r9d
  int v39; // r10d
  unsigned __int64 v40; // rax
  char v41; // cl
  __int64 i; // rbx
  HMODULE v43; // rcx
  unsigned int v44; // r12d
  void *v45; // r13
  int v46; // ebx
  HANDLE v47; // rax
  const wchar_t *v48; // rsi
  const wchar_t *v49; // r14
  int v50; // r13d
  int v51; // r12d
  __int64 v52; // r15
  signed int LastError; // ebx
  bool v54; // sf
  __int64 v55; // rbx
  HMODULE *v56; // r14
  _BYTE *v57; // rdi
  __int64 v58; // rax
  char *v59; // rdx
  unsigned int v60; // eax
  unsigned int i9; // r15d
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(); // rax
  __int64 v64; // r9
  wchar_t *v65; // rdi
  wchar_t *v66; // r8
  __int64 (__fastcall *v67)(); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v69; // r15
  __int64 v70; // r9
  const wchar_t *v71; // rdi
  const wchar_t *v72; // r8
  HANDLE CurrentProcess; // rax
  bool v74; // sf
  int v75; // edi
  HLOCAL v76; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *v78; // rax
  void *v79; // r12
  int v80; // r15d
  _QWORD *v81; // r13
  HANDLE v82; // rax
  int v83; // eax
  int v84; // ecx
  unsigned int v85; // r11d
  int v86; // eax
  unsigned int v87; // r11d
  int v88; // r9d
  int v89; // eax
  unsigned int v90; // r11d
  int v91; // r9d
  int v92; // eax
  size_t v93; // rdx
  int v94; // r9d
  int v95; // r11d
  int v96; // eax
  unsigned int v97; // r11d
  int v98; // eax
  unsigned int v99; // r11d
  int v100; // r9d
  int v101; // eax
  int v102; // r9d
  unsigned int v103; // ebx
  HANDLE v104; // rax
  _DWORD *v105; // rbx
  int v106; // r9d
  unsigned int v107; // r11d
  unsigned int v108; // ebx
  int v109; // r10d
  int v110; // eax
  void *v111; // rbx
  HANDLE v112; // rax
  void *v113; // rbx
  HANDLE v114; // rax
  HANDLE v115; // rax
  HANDLE v116; // rax
  DWORD ModuleFileNameW; // eax
  _BYTE *v118; // r13
  unsigned int *v119; // r9
  __int64 v120; // r9
  unsigned int v121; // r10d
  unsigned int *v122; // r9
  unsigned int v123; // r11d
  int v124; // r10d
  unsigned int *v125; // r9
  int v126; // r11d
  int v127; // r10d
  __int64 v128; // r9
  unsigned int v129; // r10d
  int v130; // r11d
  unsigned int *v131; // r9
  unsigned int *v132; // r9
  size_t v133; // rdx
  __int64 v134; // r9
  unsigned int v135; // r10d
  int v136; // r11d
  _DWORD *v137; // r9
  int v138; // r11d
  unsigned int *v139; // r9
  unsigned int v140; // ebx
  __int64 v141; // r9
  unsigned int v142; // r11d
  _DWORD *v143; // r9
  __int64 v144; // r10
  int v145; // r10d
  unsigned int *v146; // r9
  int v147; // r11d
  __int64 v148; // r9
  unsigned int v149; // r10d
  int v150; // r11d
  _DWORD *v151; // r9
  int v152; // r10d
  unsigned int *v153; // r9
  int v154; // r11d
  __int64 v155; // r9
  unsigned int v156; // r10d
  int v157; // r11d
  _DWORD *v158; // r9
  __int64 v159; // rcx
  unsigned int v160; // r9d
  unsigned int v161; // r9d
  int v162; // r15d
  unsigned int v163; // eax
  unsigned int v164; // ebx
  HANDLE v165; // rax
  char *v166; // rax
  char *v167; // rbx
  int v168; // r9d
  unsigned int v169; // r10d
  size_t v170; // rcx
  HANDLE v171; // rax
  unsigned int *v172; // rdi
  _DWORD *v173; // rbx
  unsigned __int8 *v174; // r15
  void *v175; // rdx
  unsigned __int8 v176; // al
  unsigned int v177; // r9d
  unsigned __int64 v178; // rcx
  unsigned __int16 *v179; // r10
  unsigned __int8 *v180; // r11
  int v181; // edx
  unsigned int v182; // r8d
  int v183; // r14d
  int v184; // esi
  int v185; // r8d
  unsigned int v186; // r9d
  unsigned int v187; // ecx
  int v188; // r11d
  _BYTE *v189; // r14
  char v190; // si
  unsigned int v191; // r9d
  int v192; // r13d
  unsigned __int64 v193; // r14
  _BYTE *v194; // r15
  int v195; // edi
  int v196; // eax
  int v197; // ebx
  int v198; // r11d
  int v199; // r10d
  int v200; // r8d
  int v201; // r10d
  int v202; // r9d
  int v203; // r8d
  unsigned int v204; // edx
  int v205; // r9d
  int v206; // ecx
  int v207; // edx
  int v208; // r9d
  int v209; // edx
  unsigned int v210; // r8d
  unsigned int v211; // r9d
  int v212; // edx
  int v213; // r8d
  int v214; // r9d
  int v215; // edx
  int v216; // r8d
  int v217; // r9d
  int v218; // r10d
  int v219; // r8d
  unsigned int v220; // edx
  int v221; // r9d
  HANDLE v222; // rax
  _DWORD *v223; // rax
  int v224; // r15d
  HANDLE v225; // rax
  void *v226; // rcx
  unsigned __int64 v227; // r15
  HANDLE v228; // rax
  _OWORD *v229; // rax
  HANDLE v230; // rax
  _QWORD *v231; // rax
  unsigned __int64 v232; // rax
  HANDLE v233; // rax
  HANDLE v234; // rax
  HANDLE v235; // rax
  HANDLE v236; // rax
  HANDLE v237; // rax
  _QWORD *v238; // rax
  HANDLE v239; // rax
  HANDLE v240; // rax
  HANDLE v241; // rax
  HANDLE v242; // rax
  unsigned int v243; // r9d
  int v244; // r15d
  unsigned int v245; // r9d
  unsigned int v246; // ebx
  HANDLE v247; // rax
  _DWORD *v248; // rax
  LPVOID v249; // rax
  HANDLE v250; // rax
  HANDLE v251; // rax
  HANDLE v252; // rax
  HANDLE v253; // rax
  HANDLE v254; // rax
  void *v255; // rdi
  HANDLE v256; // rax
  HANDLE v257; // rax
  _QWORD *v258; // rbx
  void *v259; // rdi
  HANDLE v260; // rax
  void *v261; // rdi
  HANDLE v262; // rax
  void *v263; // rdi
  HANDLE v264; // rax
  HANDLE v265; // rax
  void *v266; // rbx
  HANDLE v267; // rax
  void *v268; // rbx
  void *v269; // rcx
  int v270; // r9d
  SIZE_T v271; // rcx
  unsigned int *v272; // r9
  SIZE_T v273; // rcx
  unsigned int *v274; // r9
  HANDLE v275; // rax
  int v276; // eax
  int v277; // r9d
  __int64 v278; // rcx
  int v279; // r11d
  LPVOID v280; // rcx
  unsigned int v281; // r11d
  int v282; // r10d
  unsigned int v283; // ebx
  LPVOID v284; // rcx
  unsigned int v285; // ebx
  HANDLE v286; // rax
  _DWORD *v287; // rax
  unsigned int v288; // r11d
  int v289; // r10d
  int v290; // r11d
  unsigned int v291; // ecx
  int v292; // r11d
  unsigned int v293; // r10d
  signed int v294; // eax
  FARPROC ProcAddress; // rax
  int v296; // eax
  unsigned int v297; // r9d
  int v298; // r11d
  int v299; // r15d
  int v300; // r9d
  size_t v301; // r10
  unsigned int v302; // r10d
  int v303; // r9d
  int v304; // r9d
  void *v305; // r11
  unsigned int v306; // r11d
  int v307; // r9d
  int v308; // r9d
  unsigned int v309; // r10d
  int v310; // r9d
  int v311; // r10d
  int v312; // r11d
  SIZE_T v313; // r15
  HANDLE v314; // rax
  _DWORD *v315; // rcx
  HANDLE v316; // rax
  void *v317; // rcx
  HANDLE v318; // rax
  void *v319; // rcx
  void *v320; // rax
  size_t v321; // rax
  unsigned int v322; // r15d
  HANDLE v323; // rax
  void *v324; // rcx
  _QWORD *v325; // rax
  HANDLE v326; // rax
  HANDLE v327; // rax
  HANDLE v328; // rax
  HANDLE v329; // rax
  size_t *v330; // rdx
  unsigned int *v331; // rcx
  HANDLE v332; // rax
  HANDLE v333; // rax
  HANDLE v334; // rax
  HANDLE v335; // rax
  unsigned __int64 v336; // r15
  void *v337; // r11
  unsigned __int8 v338; // al
  int v339; // r9d
  unsigned int v340; // r8d
  int v341; // r10d
  unsigned __int8 *v342; // rsi
  unsigned int v343; // r14d
  unsigned int v344; // eax
  int v345; // r8d
  unsigned int v346; // r10d
  int v347; // ecx
  int v348; // edx
  _BYTE *v349; // r14
  char v350; // si
  int v351; // r11d
  int v352; // r9d
  unsigned __int8 *v353; // rsi
  unsigned __int16 *v354; // r15
  size_t v355; // rax
  int v356; // r13d
  int v357; // r12d
  int v358; // edi
  int v359; // ebx
  int v360; // edx
  int v361; // r8d
  int v362; // r9d
  unsigned int v363; // edx
  int v364; // r8d
  int v365; // r9d
  unsigned int v366; // edx
  int v367; // r8d
  int v368; // r10d
  int v369; // r11d
  unsigned int v370; // r9d
  int v371; // r8d
  unsigned int v372; // r9d
  int v373; // edx
  int v374; // r8d
  int v375; // r9d
  int v376; // edx
  int v377; // r8d
  int v378; // r9d
  int v379; // edx
  int v380; // r8d
  unsigned int v381; // r9d
  int v382; // edx
  unsigned __int64 j; // rcx
  int v384; // r15d
  void *v385; // r9
  void *v386; // r10
  _DWORD *v387; // r11
  void *v388; // rcx
  void *v389; // r11
  void *v390; // r10
  void *v391; // r9
  SIZE_T v392; // rax
  void *v393; // r9
  void *v394; // r10
  void *v395; // r11
  LPVOID v396; // rcx
  int v397; // eax
  unsigned __int16 *v398; // rax
  unsigned int v399; // ecx
  HANDLE v400; // rax
  unsigned __int64 v401; // rcx
  int v402; // r9d
  _DWORD *v403; // r11
  unsigned __int16 *v404; // r15
  int v405; // ebx
  unsigned int v406; // r10d
  int v407; // r9d
  int v408; // r9d
  void *v409; // r11
  size_t *v410; // rdx
  unsigned __int64 v411; // rcx
  unsigned int v412; // r10d
  int v413; // r9d
  int v414; // r9d
  void *v415; // r11
  _DWORD *v416; // rdx
  unsigned __int64 v417; // rcx
  const void *v418; // rbx
  unsigned int v419; // r10d
  int v420; // r9d
  int v421; // r10d
  _DWORD *v422; // r11
  _DWORD *v423; // rcx
  int v424; // r9d
  int v425; // r9d
  void *v426; // r11
  _DWORD *v427; // rdx
  unsigned __int64 v428; // rcx
  unsigned int v429; // r11d
  int v430; // r9d
  int v431; // r9d
  size_t v432; // r10
  int *v433; // r11
  int *v434; // rax
  unsigned int v435; // edi
  int v436; // eax
  _BYTE *v437; // r13
  unsigned __int8 *v438; // r12
  _BYTE *v439; // rsi
  int v440; // edi
  int v441; // ecx
  int v442; // r10d
  int v443; // r8d
  __int64 v444; // r14
  int v445; // ebx
  int v446; // r11d
  int v447; // edx
  unsigned int v448; // r8d
  int v449; // r9d
  unsigned int v450; // r10d
  int v451; // r8d
  unsigned int v452; // r9d
  int v453; // r10d
  int v454; // edx
  int v455; // r8d
  unsigned int v456; // r9d
  int v457; // edx
  int v458; // r8d
  unsigned int v459; // r10d
  unsigned int v460; // r8d
  int v461; // r9d
  int v462; // edx
  unsigned int v463; // r8d
  int v464; // r9d
  int v465; // edx
  int v466; // r8d
  unsigned int v467; // r9d
  int v468; // r10d
  unsigned __int64 v469; // rax
  char v470; // cl
  __int64 m; // rbx
  HMODULE v472; // rcx
  unsigned int v473; // r12d
  __int64 v474; // rbx
  HMODULE *v475; // r12
  _BYTE *v476; // r13
  int v477; // ebx
  unsigned __int64 v478; // rcx
  __int64 v479; // rax
  char *v480; // rdx
  unsigned int v481; // edx
  unsigned int v482; // eax
  __int64 v483; // r12
  __int64 (__fastcall *v484)(); // rax
  void *v485; // r12
  HANDLE v486; // rax
  int v487; // eax
  _BYTE *v488; // r13
  unsigned __int8 *v489; // r12
  _BYTE *v490; // r14
  int v491; // edi
  int v492; // ecx
  int v493; // r9d
  int v494; // r8d
  __int64 v495; // rsi
  int v496; // ebx
  int v497; // r11d
  int v498; // edx
  unsigned int v499; // r8d
  int v500; // r9d
  unsigned int v501; // r10d
  int v502; // r8d
  unsigned int v503; // r9d
  int v504; // r10d
  int v505; // edx
  int v506; // r8d
  unsigned int v507; // r9d
  int v508; // edx
  int v509; // r8d
  unsigned int v510; // r10d
  unsigned int v511; // r8d
  int v512; // r9d
  int v513; // edx
  unsigned int v514; // r8d
  int v515; // r9d
  int v516; // edx
  int v517; // r8d
  unsigned int v518; // r9d
  int v519; // edx
  unsigned __int64 v520; // rax
  char v521; // cl
  __int64 n; // rbx
  HMODULE v523; // rcx
  unsigned int v524; // r12d
  __int64 v525; // rbx
  HMODULE *v526; // r12
  _BYTE *v527; // r13
  int v528; // ebx
  unsigned __int64 v529; // rcx
  __int64 v530; // rax
  char *v531; // rdx
  unsigned int v532; // edx
  unsigned int v533; // eax
  __int64 v534; // r12
  __int64 (__fastcall *v535)(); // rax
  void *v536; // r12
  HANDLE v537; // rax
  signed int v538; // eax
  signed int v539; // ebx
  SIZE_T v540; // r12
  bool v541; // sf
  void *v542; // rax
  char *v543; // r12
  void *v544; // rax
  bool v545; // sf
  unsigned int i2; // esi
  __int64 v547; // rax
  unsigned int v548; // r9d
  unsigned int v549; // edx
  unsigned int i3; // ecx
  __int64 v551; // r12
  const wchar_t *v552; // rcx
  __int64 i4; // rdx
  __int64 v554; // rax
  _BYTE *v555; // rax
  _BYTE *v556; // r12
  unsigned __int8 *v557; // rbx
  _BYTE *v558; // r13
  int v559; // esi
  int v560; // edi
  int v561; // r8d
  int v562; // edx
  __int64 v563; // r14
  int v564; // r11d
  int v565; // r10d
  int v566; // ecx
  unsigned int v567; // edx
  int v568; // r8d
  unsigned int v569; // ecx
  int v570; // edx
  unsigned int v571; // r8d
  int v572; // r9d
  int v573; // ecx
  int v574; // edx
  unsigned int v575; // r8d
  int v576; // ecx
  int v577; // edx
  unsigned int v578; // r9d
  unsigned int v579; // edx
  int v580; // r8d
  int v581; // ecx
  unsigned int v582; // edx
  int v583; // r8d
  int v584; // ecx
  int v585; // edx
  unsigned int v586; // r8d
  int v587; // ecx
  unsigned __int64 v588; // rax
  __m128 v589; // xmm1
  __int64 v590; // r13
  __m128 v591; // xmm0
  __m128 v592; // xmm1
  __m128 v593; // xmm1
  __m128 v594; // xmm1
  unsigned int v595; // edx
  int v596; // r8d
  unsigned int i5; // ecx
  __int64 v598; // rax
  void *v599; // rax
  void **v600; // r12
  unsigned int v601; // ecx
  unsigned int v602; // eax
  __int64 v603; // r13
  __int64 v604; // r9
  signed int v605; // eax
  void *v606; // rax
  __int64 v607; // r9
  signed int v608; // eax
  __int64 i6; // r13
  _BYTE *v610; // rax
  __int64 v611; // rcx
  __int64 i7; // rcx
  _BYTE *v613; // rax
  signed int v614; // eax
  int v615; // r13d
  int v616; // eax
  unsigned int v617; // ebx
  signed int v618; // r12d
  size_t v619; // rax
  __int64 v620; // rax
  bool v621; // sf
  const unsigned __int16 *v622; // rbx
  __int64 v623; // rax
  bool v624; // sf
  unsigned int v625; // eax
  int v626; // eax
  signed int v627; // r12d
  void *v628; // rbx
  void *v629; // rbx
  __int64 v630; // rdx
  signed int v631; // eax
  __int64 v632; // rax
  bool v633; // sf
  void *v634; // rbx
  __int64 v635; // r12
  unsigned int v636; // eax
  int v637; // eax
  unsigned int v638; // ebx
  int v639; // r12d
  int v640; // ebx
  int v641; // r13d
  int v642; // r13d
  __int64 v643; // rax
  int v644; // r13d
  __int64 v645; // rax
  int v646; // edx
  int v647; // eax
  __int64 ii; // r12
  HMODULE v649; // rcx
  unsigned int v650; // ebx
  __int64 v651; // rax
  int v652; // edi
  int v653; // r12d
  LPVOID v654; // rbx
  int v655; // eax
  signed int v656; // r13d
  __int64 v657; // rax
  size_t v658; // rax
  size_t v659; // rbx
  size_t v660; // rax
  signed int v661; // eax
  signed int v662; // edi
  __int64 (__fastcall *v663)(); // rbx
  __int64 v664; // rax
  int v665; // r11d
  int v666; // eax
  int v667; // r8d
  int v668; // r10d
  int v669; // r9d
  __int64 v670; // rdx
  int v671; // ecx
  int v672; // edi
  char *v673; // rbx
  unsigned __int16 *v674; // rax
  unsigned __int8 v675; // r14
  signed int v676; // esi
  unsigned __int8 *v677; // r8
  unsigned __int16 *v678; // r10
  signed int v679; // r9d
  char v680; // r15
  char v681; // di
  unsigned __int8 v682; // dl
  int v683; // r8d
  int v684; // r9d
  int v685; // edx
  LPVOID v686; // rbx
  __int64 v687; // rax
  void *v688; // rax
  void *v689; // r13
  size_t v690; // rax
  size_t v691; // rbx
  bool v692; // sf
  __int64 (__fastcall *v693)(); // rbx
  __int64 v694; // rax
  int v695; // r8d
  int v696; // r9d
  int v697; // ecx
  int v698; // r10d
  int v699; // r12d
  int v700; // r11d
  SIZE_T v701; // r14
  unsigned __int16 *v702; // rax
  unsigned __int8 *v703; // r8
  unsigned __int16 *v704; // r10
  int v705; // r9d
  char v706; // r13
  char v707; // si
  unsigned __int8 v708; // r11
  unsigned __int8 v709; // dl
  int v710; // r8d
  int v711; // r9d
  int v712; // edx
  unsigned __int64 v713; // rbx
  LPVOID v714; // r12
  int v715; // r13d
  char v716; // al
  void *v717; // rdi
  int v718; // ebx
  int v719; // edx
  unsigned int v720; // r10d
  int v721; // edi
  int v722; // r9d
  unsigned __int64 v723; // rax
  __int64 v724; // rax
  size_t v725; // rcx
  int v726; // ebx
  signed int v727; // edi
  void *v728; // rax
  signed int v729; // eax
  unsigned __int16 *v730; // r13
  size_t v731; // rbx
  __int64 (__fastcall *v732)(); // rbx
  __int64 v733; // rax
  size_t v734; // rbx
  int v735; // eax
  int v736; // r9d
  int v737; // r11d
  int v738; // edx
  int v739; // r10d
  __int64 v740; // r13
  int v741; // r8d
  int v742; // ecx
  size_t v743; // r14
  unsigned __int16 *v744; // rax
  unsigned __int8 v745; // si
  unsigned __int8 *v746; // r9
  unsigned __int16 *v747; // r10
  int v748; // r11d
  char v749; // r13
  char v750; // r15
  unsigned __int8 v751; // dl
  int v752; // r8d
  int v753; // r9d
  int v754; // edx
  __int64 v755; // rax
  size_t v756; // rax
  size_t v757; // rbx
  int v758; // r13d
  signed int v759; // edi
  size_t v760; // rax
  signed int v761; // eax
  __int64 (__fastcall *v762)(); // rbx
  __int64 v763; // rax
  int v764; // edx
  int v765; // r9d
  int v766; // r8d
  __int64 v767; // r10
  int v768; // ecx
  int v769; // r11d
  char *v770; // rdx
  unsigned __int16 *v771; // rax
  signed int v772; // r13d
  unsigned int v773; // ebx
  unsigned __int8 *v774; // r8
  unsigned __int16 *v775; // r10
  signed int v776; // r9d
  char v777; // si
  unsigned __int8 v778; // r14
  unsigned __int8 v779; // dl
  int v780; // r8d
  int v781; // r9d
  int v782; // edx
  bool v783; // zf
  _BYTE *v784; // rax
  __int64 v785; // rcx
  __int64 jj; // rcx
  _BYTE *v787; // rax
  __int64 v788; // rcx
  __int64 kk; // rcx
  _BYTE *v790; // rcx
  __int64 v791; // rax
  __int64 v792; // rax
  int v793; // eax
  __int64 mm; // rbx
  HMODULE v795; // rcx
  int v796; // r13d
  int v797; // ebx
  void *v798; // r12
  int v799; // eax
  const WCHAR *v800; // rax
  int v801; // r8d
  WCHAR *v802; // r12
  int v803; // r13d
  int v804; // esi
  int v805; // r9d
  unsigned __int8 *v806; // r14
  __int64 v807; // rcx
  int v808; // ebx
  int v809; // r11d
  int v810; // edx
  unsigned int v811; // r8d
  int v812; // r9d
  unsigned int v813; // r10d
  int v814; // r8d
  unsigned int v815; // r9d
  int v816; // r10d
  int v817; // edx
  int v818; // r8d
  unsigned int v819; // r9d
  int v820; // edx
  int v821; // r8d
  unsigned int v822; // r10d
  unsigned int v823; // r8d
  int v824; // r9d
  int v825; // edx
  unsigned int v826; // r8d
  int v827; // r9d
  int v828; // edx
  int v829; // r8d
  unsigned int v830; // r9d
  int v831; // edx
  unsigned __int64 v832; // rax
  char v833; // cl
  WCHAR *v834; // rdi
  __int64 nn; // rbx
  HMODULE v836; // rcx
  unsigned int v837; // r12d
  __int64 v838; // rbx
  __int64 v839; // r12
  HMODULE *v840; // r13
  WCHAR *v841; // rdi
  int v842; // ebx
  __int64 v843; // rax
  char *v844; // rdx
  unsigned int v845; // eax
  int v846; // ecx
  unsigned int v847; // edx
  __int64 v848; // r12
  __int64 (__fastcall *v849)(); // rax
  HANDLE v850; // rax
  int v851; // eax
  __int64 i1; // rbx
  HMODULE v853; // rcx
  _DWORD *v854; // rdi
  HANDLE v855; // rax
  _OWORD *v856; // rax
  void *v857; // r12
  HANDLE v858; // rax
  _QWORD *v859; // rax
  _BYTE *v860; // rdi
  _DWORD *v861; // r11
  _DWORD *v862; // rcx
  unsigned int v863; // r10d
  unsigned int v864; // r11d
  int v865; // eax
  unsigned int v866; // r10d
  int v867; // r9d
  int v868; // eax
  unsigned int v869; // r10d
  int v870; // r9d
  int v871; // eax
  int v872; // r9d
  unsigned int v873; // ebx
  HANDLE v874; // rax
  _DWORD *v875; // rax
  _DWORD *v876; // rbx
  int v877; // r10d
  unsigned int v878; // r11d
  unsigned int v879; // ebx
  int v880; // r10d
  unsigned int *v881; // r9
  int v882; // eax
  unsigned int v883; // r11d
  void *v884; // rbx
  HANDLE v885; // rax
  HANDLE v886; // rax
  HANDLE v887; // rax
  HANDLE v888; // rax
  unsigned int v889; // edi
  unsigned int v890; // edi
  __int64 v891; // r9
  unsigned int v892; // r10d
  unsigned int *v893; // r9
  unsigned int v894; // r11d
  size_t v895; // r8
  int v896; // r10d
  unsigned int *v897; // r9
  __int64 v898; // r9
  unsigned int v899; // r10d
  int v900; // r11d
  int v901; // eax
  unsigned int *v902; // r9
  int v903; // r9d
  unsigned int *v904; // r10
  unsigned int v905; // r10d
  unsigned int v906; // r11d
  __int64 v907; // r10
  unsigned int v908; // r9d
  int v909; // r11d
  int v910; // eax
  _DWORD *v911; // r10
  __int64 v912; // rcx
  unsigned int v913; // r11d
  unsigned int v914; // r9d
  void *v915; // r11
  int v916; // edi
  int v917; // ecx
  void *v918; // r9
  unsigned int v919; // r10d
  unsigned int *v920; // r11
  unsigned int v921; // eax
  unsigned int v922; // ebx
  HANDLE v923; // rax
  char *v924; // rax
  char *v925; // rbx
  unsigned int v926; // r9d
  size_t v927; // rcx
  HANDLE v928; // rax
  unsigned int *v929; // rdi
  _DWORD *v930; // rbx
  int v931; // ecx
  void *v932; // rcx
  unsigned __int8 v933; // al
  unsigned __int64 v934; // r8
  unsigned __int64 v935; // r11
  unsigned __int8 *v936; // r9
  int v937; // r10d
  unsigned int v938; // r14d
  unsigned int v939; // esi
  int v940; // edi
  int v941; // r8d
  unsigned int v942; // r8d
  unsigned int v943; // r9d
  int v944; // ecx
  int v945; // edx
  _BYTE *v946; // rsi
  unsigned int v947; // r14d
  char v948; // bl
  unsigned int v949; // r9d
  int v950; // r12d
  unsigned __int8 *v951; // r14
  _BYTE *v952; // rdi
  unsigned int v953; // eax
  int v954; // r15d
  unsigned __int64 v955; // r13
  int v956; // ebx
  int v957; // r11d
  int v958; // r10d
  int v959; // r8d
  int v960; // r10d
  int v961; // r9d
  int v962; // r8d
  unsigned int v963; // edx
  int v964; // r9d
  int v965; // ecx
  int v966; // edx
  int v967; // r8d
  int v968; // r9d
  int v969; // edx
  unsigned int v970; // r8d
  unsigned int v971; // r9d
  int v972; // edx
  int v973; // r8d
  int v974; // r9d
  int v975; // edx
  int v976; // r8d
  int v977; // r10d
  int v978; // edx
  int v979; // r9d
  unsigned int v980; // r8d
  int v981; // ecx
  HANDLE v982; // rax
  _DWORD *v983; // rax
  void *v984; // rsi
  unsigned int v985; // esi
  HANDLE v986; // rax
  void *v987; // rcx
  int v988; // eax
  HANDLE v989; // rax
  _OWORD *v990; // rcx
  _DWORD *v991; // rax
  HANDLE v992; // rax
  _QWORD *v993; // rax
  LPVOID v994; // rax
  HANDLE v995; // rax
  HANDLE v996; // rax
  HANDLE v997; // rax
  HANDLE v998; // rax
  LPVOID v999; // rcx
  HANDLE v1000; // rax
  unsigned __int64 v1001; // rax
  HANDLE v1002; // rax
  HANDLE v1003; // rax
  HANDLE v1004; // rax
  HANDLE v1005; // rax
  unsigned int v1006; // r9d
  unsigned int v1007; // r9d
  unsigned int v1008; // ebx
  HANDLE v1009; // rax
  _DWORD *v1010; // rax
  unsigned int v1011; // ebx
  unsigned __int64 v1012; // rcx
  LPVOID v1013; // rcx
  unsigned int *v1014; // r9
  LPVOID v1015; // rcx
  unsigned int *v1016; // r9
  int v1017; // eax
  HANDLE v1018; // rax
  int v1019; // eax
  int v1020; // eax
  int v1021; // r9d
  __int64 v1022; // rcx
  size_t v1023; // rcx
  unsigned int v1024; // r11d
  int v1025; // r10d
  unsigned int v1026; // ebx
  size_t v1027; // rcx
  unsigned int v1028; // r11d
  int v1029; // r10d
  unsigned int v1030; // ecx
  unsigned int v1031; // r10d
  unsigned int v1032; // ebx
  HANDLE v1033; // rax
  _DWORD *v1034; // rax
  void *v1035; // r14
  int v1036; // eax
  bool v1037; // sf
  FARPROC v1038; // rax
  unsigned int v1039; // r9d
  int v1040; // ecx
  int v1041; // r9d
  SIZE_T v1042; // r10
  unsigned int v1043; // r10d
  int v1044; // r9d
  int v1045; // r9d
  size_t v1046; // r11
  unsigned int v1047; // r11d
  int v1048; // r9d
  int v1049; // r9d
  unsigned int v1050; // r10d
  int v1051; // r9d
  int v1052; // r10d
  int v1053; // r11d
  HANDLE v1054; // rax
  _QWORD *v1055; // rax
  SIZE_T v1056; // rcx
  HANDLE v1057; // rax
  void *v1058; // rcx
  LPVOID *v1059; // rax
  HANDLE v1060; // rax
  void *v1061; // rcx
  SIZE_T v1062; // rax
  HANDLE v1063; // rax
  void *v1064; // rcx
  HANDLE v1065; // rax
  HANDLE v1066; // rax
  HANDLE v1067; // rax
  HANDLE v1068; // rax
  LPVOID *v1069; // rdx
  unsigned int *v1070; // rax
  HANDLE v1071; // rax
  HANDLE v1072; // rax
  HANDLE v1073; // rax
  HANDLE v1074; // rax
  _BYTE *v1075; // r9
  unsigned __int8 v1076; // al
  unsigned __int16 *v1077; // r11
  size_t v1078; // r8
  int v1079; // r14d
  unsigned int v1080; // eax
  unsigned int v1081; // r8d
  unsigned int v1082; // edx
  _BYTE *v1083; // rcx
  unsigned int v1084; // r10d
  unsigned int v1085; // r11d
  int v1086; // r14d
  int v1087; // eax
  unsigned int v1088; // r8d
  char v1089; // r9
  int v1090; // r11d
  int v1091; // r12d
  unsigned __int8 *v1092; // rax
  _BYTE *v1093; // rsi
  unsigned int v1094; // r13d
  LPVOID v1095; // r15
  int v1096; // edi
  int v1097; // ebx
  unsigned int v1098; // r8d
  int v1099; // r9d
  unsigned int v1100; // edx
  int v1101; // r8d
  int v1102; // r9d
  unsigned int v1103; // edx
  int v1104; // r8d
  int v1105; // r10d
  int v1106; // r11d
  unsigned int v1107; // r9d
  int v1108; // r8d
  unsigned int v1109; // r9d
  int v1110; // edx
  int v1111; // r8d
  int v1112; // r9d
  int v1113; // edx
  unsigned int v1114; // r8d
  int v1115; // r9d
  int v1116; // r10d
  int v1117; // edx
  unsigned int v1118; // r8d
  int v1119; // r11d
  size_t v1120; // rcx
  unsigned int k; // r10d
  void *v1122; // r14
  int v1123; // r8d
  void *v1124; // rcx
  void *v1125; // r9
  int v1126; // r10d
  _DWORD *v1127; // r9
  int v1128; // r10d
  unsigned int v1129; // r11d
  unsigned int v1130; // r10d
  __int64 v1131; // r11
  __int64 v1132; // rdx
  size_t v1133; // rcx
  unsigned __int16 *v1134; // r10
  SIZE_T v1135; // r9
  unsigned __int16 *v1136; // r11
  unsigned __int64 v1137; // rax
  unsigned int *v1138; // r11
  __int64 v1139; // r11
  SIZE_T v1140; // r12
  int v1141; // eax
  void *v1142; // rcx
  unsigned int v1143; // edx
  HANDLE v1144; // rax
  int v1145; // eax
  HANDLE v1146; // rax
  void *v1147; // rsi
  HANDLE v1148; // rax
  void *v1149; // rsi
  HANDLE v1150; // rax
  void *v1151; // rsi
  HANDLE v1152; // rax
  HANDLE v1153; // rax
  void *v1154; // rdi
  HANDLE v1155; // rax
  HANDLE v1156; // rax
  _QWORD *v1157; // rbx
  void *v1158; // rdi
  HANDLE v1159; // rax
  void *v1160; // rdi
  HANDLE v1161; // rax
  void *v1162; // rdi
  HANDLE v1163; // rax
  HANDLE v1164; // rax
  HANDLE v1165; // rax
  unsigned int v1166; // r9d
  unsigned int v1167; // r10d
  _DWORD *v1168; // r11
  _DWORD *v1169; // rcx
  unsigned __int64 v1170; // rcx
  __int64 v1171; // rbx
  unsigned int v1172; // r10d
  int v1173; // r9d
  int v1174; // eax
  __int64 i8; // rbx
  HMODULE v1176; // rcx
  int v1177; // ebx
  HMENU v1178; // r15
  HMENU SubMenu; // rax
  HMENU v1180; // rbx
  struct IModularWindow **v1181; // r14
  OpenWithHelper *v1182; // rsi
  HMENU v1183; // rax
  int v1184; // eax
  int v1185; // edx
  HWND *v1186; // rdi
  unsigned int v1187; // r8d
  int v1188; // eax
  int v1189; // ebx
  __int16 v1190; // [rsp+38h] [rbp-C8h]
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v1192; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v1193; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T v1194; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v1195; // [rsp+80h] [rbp-80h]
  SIZE_T v1196; // [rsp+88h] [rbp-78h] BYREF
  SIZE_T v1197; // [rsp+90h] [rbp-70h] BYREF
  void *v1198; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v1199; // [rsp+A0h] [rbp-60h]
  int v1200; // [rsp+A8h] [rbp-58h]
  size_t v1201; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID v1202; // [rsp+B8h] [rbp-48h]
  LPVOID v1203; // [rsp+C0h] [rbp-40h] BYREF
  SIZE_T v1204; // [rsp+C8h] [rbp-38h] BYREF
  size_t pcchLength; // [rsp+D0h] [rbp-30h] BYREF
  size_t v1206; // [rsp+D8h] [rbp-28h]
  LPVOID v1207; // [rsp+E0h] [rbp-20h] BYREF
  SIZE_T v1208; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v1209; // [rsp+F0h] [rbp-10h] BYREF
  SIZE_T v1210; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v1211; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v1212; // [rsp+108h] [rbp+8h]
  unsigned __int64 v1213; // [rsp+110h] [rbp+10h]
  void *Src; // [rsp+118h] [rbp+18h] BYREF
  LPVOID v1215; // [rsp+120h] [rbp+20h]
  unsigned __int64 v1216; // [rsp+128h] [rbp+28h]
  SIZE_T Size; // [rsp+130h] [rbp+30h] BYREF
  LPVOID lpMem[2]; // [rsp+138h] [rbp+38h] BYREF
  LPVOID v1219; // [rsp+148h] [rbp+48h] BYREF
  int *v1220; // [rsp+150h] [rbp+50h] BYREF
  LPVOID v1221; // [rsp+158h] [rbp+58h]
  void *v1222; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v1223; // [rsp+168h] [rbp+68h] BYREF
  size_t v1224[2]; // [rsp+170h] [rbp+70h] BYREF
  LPCWSTR lpModuleName; // [rsp+180h] [rbp+80h]
  void *v1226; // [rsp+188h] [rbp+88h] BYREF
  unsigned int v1227; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v1228; // [rsp+194h] [rbp+94h] BYREF
  unsigned int v1229; // [rsp+198h] [rbp+98h] BYREF
  __int128 v1230; // [rsp+1A0h] [rbp+A0h]
  __int64 v1231; // [rsp+1B0h] [rbp+B0h]
  unsigned int v1232; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v1233; // [rsp+1BCh] [rbp+BCh] BYREF
  unsigned int v1234; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v1235; // [rsp+1C4h] [rbp+C4h] BYREF
  unsigned int v1236; // [rsp+1C8h] [rbp+C8h] BYREF
  void *v1237; // [rsp+1D0h] [rbp+D0h]
  int v1238; // [rsp+1D8h] [rbp+D8h]
  unsigned int v1239; // [rsp+1DCh] [rbp+DCh] BYREF
  unsigned int v1240; // [rsp+1E0h] [rbp+E0h]
  unsigned int v1241; // [rsp+1E4h] [rbp+E4h] BYREF
  int v1242; // [rsp+1E8h] [rbp+E8h] BYREF
  int *v1243; // [rsp+1F0h] [rbp+F0h] BYREF
  struct IDataObject *v1244; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE *v1245; // [rsp+200h] [rbp+100h] BYREF
  HMODULE hModule; // [rsp+208h] [rbp+108h] BYREF
  HMODULE phModule; // [rsp+210h] [rbp+110h] BYREF
  void *v1248; // [rsp+220h] [rbp+120h]
  HMENU hMenu; // [rsp+228h] [rbp+128h]
  __int128 v1250; // [rsp+230h] [rbp+130h] BYREF
  __int128 v1251; // [rsp+240h] [rbp+140h]
  __int128 v1252; // [rsp+250h] [rbp+150h] BYREF
  __int128 v1253; // [rsp+260h] [rbp+160h]
  __int64 v1254; // [rsp+280h] [rbp+180h] BYREF
  __int64 v1255; // [rsp+288h] [rbp+188h] BYREF
  __int64 v1256; // [rsp+290h] [rbp+190h] BYREF
  TweakerModeControl *v1257; // [rsp+298h] [rbp+198h]
  char v1258[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v1259[8]; // [rsp+2A8h] [rbp+1A8h] BYREF
  LONGLONG llVal; // [rsp+2B0h] [rbp+1B0h]
  __int64 v1261; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v1262; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v1263; // [rsp+2C8h] [rbp+1C8h] BYREF
  _OWORD v1264[3]; // [rsp+350h] [rbp+250h] BYREF
  _QWORD v1265[20]; // [rsp+380h] [rbp+280h] BYREF
  int v1266; // [rsp+420h] [rbp+320h] BYREF
  int v1267; // [rsp+424h] [rbp+324h]
  void *v1268; // [rsp+428h] [rbp+328h]
  void *v1269; // [rsp+430h] [rbp+330h]
  void *v1270; // [rsp+438h] [rbp+338h]
  size_t v1271; // [rsp+440h] [rbp+340h]
  const WCHAR *v1272; // [rsp+448h] [rbp+348h]
  __int64 v1273; // [rsp+450h] [rbp+350h]
  int v1274; // [rsp+458h] [rbp+358h]
  int v1275; // [rsp+45Ch] [rbp+35Ch] BYREF
  int v1276; // [rsp+460h] [rbp+360h]
  signed int v1277; // [rsp+464h] [rbp+364h]
  int v1278; // [rsp+468h] [rbp+368h]
  int v1279; // [rsp+46Ch] [rbp+36Ch] BYREF
  int v1280; // [rsp+470h] [rbp+370h]
  signed int v1281; // [rsp+474h] [rbp+374h]
  unsigned int v1282; // [rsp+478h] [rbp+378h]
  unsigned int v1283; // [rsp+47Ch] [rbp+37Ch] BYREF
  unsigned int v1284; // [rsp+480h] [rbp+380h]
  unsigned int v1285; // [rsp+484h] [rbp+384h]
  unsigned int v1286; // [rsp+488h] [rbp+388h]
  int v1287; // [rsp+490h] [rbp+390h] BYREF
  _DWORD v1288[3]; // [rsp+494h] [rbp+394h] BYREF
  __int16 v1289; // [rsp+4A2h] [rbp+3A2h]
  __int64 v1290; // [rsp+4A8h] [rbp+3A8h]
  int v1291; // [rsp+500h] [rbp+400h] BYREF
  _DWORD v1292[5]; // [rsp+504h] [rbp+404h] BYREF
  unsigned __int16 *v1293; // [rsp+518h] [rbp+418h]
  int v1294; // [rsp+570h] [rbp+470h] BYREF
  _DWORD v1295[5]; // [rsp+574h] [rbp+474h] BYREF
  unsigned __int16 *v1296; // [rsp+588h] [rbp+488h]
  int v1297; // [rsp+5E0h] [rbp+4E0h] BYREF
  _DWORD v1298[5]; // [rsp+5E4h] [rbp+4E4h] BYREF
  unsigned __int16 *v1299; // [rsp+5F8h] [rbp+4F8h]
  int v1300; // [rsp+650h] [rbp+550h] BYREF
  _DWORD v1301[5]; // [rsp+654h] [rbp+554h] BYREF
  unsigned __int16 *v1302; // [rsp+668h] [rbp+568h]
  int v1303; // [rsp+6C0h] [rbp+5C0h] BYREF
  char v1304[20]; // [rsp+6C4h] [rbp+5C4h] BYREF
  SIZE_T v1305; // [rsp+6D8h] [rbp+5D8h]
  int v1306; // [rsp+730h] [rbp+630h] BYREF
  char v1307[20]; // [rsp+734h] [rbp+634h] BYREF
  SIZE_T v1308; // [rsp+748h] [rbp+648h]
  int v1309; // [rsp+7A0h] [rbp+6A0h] BYREF
  char v1310[20]; // [rsp+7A4h] [rbp+6A4h] BYREF
  SIZE_T v1311; // [rsp+7B8h] [rbp+6B8h]
  int v1312; // [rsp+810h] [rbp+710h] BYREF
  char v1313[20]; // [rsp+814h] [rbp+714h] BYREF
  SIZE_T v1314; // [rsp+828h] [rbp+728h]
  __int128 v1315; // [rsp+880h] [rbp+780h] BYREF
  __int128 v1316; // [rsp+890h] [rbp+790h] BYREF
  __int128 v1317; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int128 v1318; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v1319; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v1320; // [rsp+8C8h] [rbp+7C8h]
  int v1321; // [rsp+8CCh] [rbp+7CCh]
  _DWORD v1322[12]; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int128 v1323; // [rsp+900h] [rbp+800h] BYREF
  __int128 v1324; // [rsp+910h] [rbp+810h] BYREF
  __int64 v1325; // [rsp+920h] [rbp+820h]
  __int128 v1326; // [rsp+928h] [rbp+828h] BYREF
  _OWORD v1327[2]; // [rsp+938h] [rbp+838h] BYREF
  __int128 v1328; // [rsp+958h] [rbp+858h] BYREF
  _OWORD v1329[2]; // [rsp+968h] [rbp+868h] BYREF
  __int128 v1330; // [rsp+988h] [rbp+888h] BYREF
  _OWORD v1331[2]; // [rsp+998h] [rbp+898h] BYREF
  __int128 v1332; // [rsp+9B8h] [rbp+8B8h] BYREF
  _OWORD v1333[2]; // [rsp+9C8h] [rbp+8C8h] BYREF
  __int128 v1334; // [rsp+9E8h] [rbp+8E8h] BYREF
  __int128 v1335; // [rsp+9F8h] [rbp+8F8h] BYREF
  __int64 v1336; // [rsp+A08h] [rbp+908h]
  _OWORD v1337[2]; // [rsp+A10h] [rbp+910h] BYREF
  _DWORD v1338[6]; // [rsp+A30h] [rbp+930h] BYREF
  char v1339; // [rsp+A4Ah] [rbp+94Ah]
  unsigned __int16 v1340[34]; // [rsp+A4Ch] [rbp+94Ch] BYREF
  _DWORD v1341[6]; // [rsp+A90h] [rbp+990h] BYREF
  char v1342; // [rsp+AAAh] [rbp+9AAh]
  unsigned __int16 v1343[34]; // [rsp+AACh] [rbp+9ACh] BYREF
  _DWORD v1344[6]; // [rsp+AF0h] [rbp+9F0h] BYREF
  char v1345; // [rsp+B0Ah] [rbp+A0Ah]
  unsigned __int16 v1346[34]; // [rsp+B0Ch] [rbp+A0Ch] BYREF
  _BYTE v1347[68]; // [rsp+B50h] [rbp+A50h] BYREF
  __int16 v1348; // [rsp+B94h] [rbp+A94h]
  unsigned __int16 v1349; // [rsp+BF6h] [rbp+AF6h]
  int v1350; // [rsp+BFCh] [rbp+AFCh]
  int v1351; // [rsp+C00h] [rbp+B00h]
  int v1352; // [rsp+C30h] [rbp+B30h] BYREF
  __int128 v1353; // [rsp+C38h] [rbp+B38h]
  __int128 v1354; // [rsp+C48h] [rbp+B48h]
  __int128 v1355; // [rsp+C58h] [rbp+B58h]
  __int64 v1356; // [rsp+C68h] [rbp+B68h]
  _BYTE v1357[176]; // [rsp+C70h] [rbp+B70h] BYREF
  WCHAR Filename[264]; // [rsp+D20h] [rbp+C20h] BYREF

  v1257 = (TweakerModeControl *)this;
  if ( !a2 )
  {
    Base::Throw((Base *)0x80004003LL, 0);
    JUMPOUT(0x180056FACLL);
  }
  if ( a2->vt != 0x4000 )
  {
    Base::Throw((Base *)0x80070057LL, (_DWORD)a2);
    __debugbreak();
  }
  llVal = a2->llVal;
  v3 = this[20];
  v4 = *(_QWORD *)llVal;
  if ( !IsWindow(*((HWND *)v3 + 1)) )
  {
    if ( !qword_1800A2FA0 )
      qword_1800A2FA0 = 0;
    v1190 = ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(
              v6,
              v5,
              &`ATL::CWindowImpl<ModularWindow::ContextMenu,ATL::CWindow,ATL::CWinTraits<1107296256,65536>>::GetWndClassInfo'::`2'::wc,
              (char *)v3 + 64);
    ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(
      v3,
      v4,
      0,
      0,
      1107296256,
      0x10000,
      0,
      v1190);
  }
  hMenu = ModularWindow::ContextMenu::LoadContextMenu(this[20], v5);
  if ( hMenu )
  {
    v1238 = 0;
    v1243 = 0;
    v1193 = 0;
    v1222 = 0;
    while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
      ;
    v1223 = -1;
    v7 = dword_1800A471C;
    if ( !dword_1800A471C )
    {
      v8 = MemoryAlloc(0x338u);
      if ( !v8 )
        goto LABEL_18;
      v9 = (unsigned __int8 *)qword_18008D3E0;
      v10 = v8;
      v11 = 0;
      v12 = -1;
      v13 = 0;
      v14 = 0;
      v15 = 103;
      do
      {
        v16 = v9[3] | ((v9[2] | ((v9[1] | (*v9 << 8)) << 8)) << 8);
        v17 = v9[7] | ((v9[6] | ((v9[5] | (v9[4] << 8)) << 8)) << 8);
        v9 += 8;
        v18 = v14 ^ v16;
        v19 = v14 ^ v16 ^ v13 ^ v17 ^ 0xAC987321;
        v20 = v18 ^ (__ROR4__(v19, 22) + 4991 * __ROR4__(v19 + 1419157410, 27));
        v21 = v19 ^ (43881 * __ROR4__(v20 + 133239679, 9) - __ROR4__(v20, 30));
        v22 = v21
            ^ (2033 * __ROR4__(v20 ^ (24670 * v21 - (v21 >> 13) - 123127970) ^ 0xAB69, 26)
             - __ROR4__(v20 ^ (24670 * v21 - (v21 >> 13) - 123127970), 30));
        v23 = v20 ^ (24670 * v21 - (v21 >> 13) - 123127970) ^ (133239679 - (v22 ^ 0xAB69605E));
        v24 = v22 ^ (43881 * (v23 ^ 0x137F)) ^ __ROR4__(v23, 6);
        v25 = v23 ^ (__ROR4__(v24, 30) + 24670 * __ROR4__(v24 + 133239679, 15));
        v26 = v24 ^ (2033 * __ROR4__(v25 + 1419157410, 14) - __ROR4__(v25, 24));
        v27 = v25 ^ __ROR4__(v26, 10) ^ (4991 * __ROR4__(v26 ^ 0xAB69605E, 12));
        v28 = v26 ^ (v27 >> 10) ^ (43881 * (v27 ^ 0x7F1));
        v29 = v27 ^ (2033 * (__ROR4__(~v28, 5) + 24670));
        v30 = v29 ^ (((v28 ^ (v29 - 2033) ^ 0xAB69605E) >> 2) + 4991 * __ROR4__(v28 ^ (v29 - 2033) ^ 0xAB6967AF, 30));
        v31 = v28 ^ (v29 - 2033) ^ 0xAB69605E ^ (__ROR4__(v30, 25) + 43881 * __ROR4__(v30 - 133239679, 6));
        v32 = v30 ^ (24670 * (v31 ^ 0x137F) + __ROR4__(v31, 9));
        v33 = v31 ^ (__ROR4__(v32, 25) + 2033 * __ROR4__(v32 ^ 0xAB69, 27));
        v34 = v32 ^ v33 ^ 0xAC987321;
        v35 = v33 ^ (4991 * __ROR4__(v34, 3) - 219010071);
        v36 = v34 ^ (24670 * __ROR4__(v35 - 133239679, 1) - __ROR4__(v35, 6));
        v37 = v35 ^ (__ROR4__(v36, 18) + 2033 * __ROR4__(v36 - 1419157410, 29));
        v38 = v36 ^ (4991 * __ROR4__(v37 - 1419157410, 17) - __ROR4__(v37, 14));
        v39 = v37 ^ (v38 >> 3) ^ (43881 * (v38 ^ 0x605E));
        v14 = v11 ^ v38 ^ __ROR4__(v39, 30) ^ (24670 * __ROR4__(v39 ^ 0x7F1137F, 28));
        v13 = v12 ^ v39;
        v10[3] = v14;
        v10[7] = v13;
        v10[2] = __ROR4__(v14, 8);
        v10[6] = __ROR4__(v13, 8);
        v10[1] = __ROR4__(v14, 16);
        v10[5] = __ROR4__(v13, 16);
        *v10 = __ROR4__(v14, 24);
        v10[4] = __ROR4__(v13, 24);
        v11 = v16;
        v12 = v17;
        v10 += 8;
        --v15;
      }
      while ( v15 );
      v40 = 0;
      v41 = 0;
      do
        v41 ^= v8[v40++];
      while ( v40 < 0x338 );
      if ( v41 != 64 )
      {
        MemoryFree(v8);
LABEL_18:
        for ( i = 0; i != 4; ++i )
        {
          v43 = (HMODULE)qword_1800A3D20[3 * i];
          if ( v43 )
            FreeLibrary(v43);
        }
        memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
        memcpy_0(off_1800A3550, off_180085080, 0x170u);
LABEL_28:
        _InterlockedExchange(&dword_1800A4720, 0);
        v48 = 0;
        Src = 0;
        v49 = 0;
        pcchLength = 0;
        v50 = 0;
        if ( NtCurrentPeb()->SessionId )
        {
          v51 = 0;
          v52 = off_1800A3660[0]();
          if ( !v52 )
          {
LABEL_30:
            LastError = GetLastError();
            v54 = LastError < 0;
            if ( LastError > 0 )
            {
              LastError = (unsigned __int16)LastError | 0x80070000;
              v54 = LastError < 0;
            }
            if ( !v54 )
              LastError = -2147467259;
            goto LABEL_104;
          }
          v1236 = 0;
          v1192 = 0;
          v64 = 0;
          v65 = 0;
          while ( 1 )
          {
            v66 = 0;
            if ( v65 )
              v66 = v65;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, wchar_t *, __int64, unsigned int *))off_1800A3680[0])(
                   v52,
                   2,
                   v66,
                   v64,
                   &v1236) )
            {
              LastError = 0;
              v48 = v65;
              Src = v65;
              goto LABEL_71;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( v65 )
              goto LABEL_66;
            v65 = (wchar_t *)MemoryAlloc(v1236);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1192);
            if ( !v65 )
            {
              LastError = -2147024882;
LABEL_71:
              v1192 = 0;
              goto LABEL_72;
            }
            v1192 = (unsigned __int64)v65;
            v64 = v1236;
          }
          if ( !LastError )
          {
LABEL_66:
            LastError = -2147467259;
            goto LABEL_72;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_72:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1192);
          if ( LastError < 0 )
            goto LABEL_104;
          v67 = off_1800A3678[0];
          CurrentThreadId = GetCurrentThreadId();
          v69 = ((__int64 (__fastcall *)(_QWORD))v67)(CurrentThreadId);
          if ( !v69 )
            goto LABEL_30;
          v1235 = 0;
          v1192 = 0;
          v70 = 0;
          v71 = 0;
          while ( 1 )
          {
            v72 = 0;
            if ( v71 )
              v72 = v71;
            if ( ((unsigned int (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned int *))off_1800A3680[0])(
                   v69,
                   2,
                   v72,
                   v70,
                   &v1235) )
            {
              LastError = 0;
              v49 = v71;
              pcchLength = (size_t)v71;
              goto LABEL_88;
            }
            LastError = GetLastError();
            if ( LastError != 122 )
              break;
            if ( v71 )
              goto LABEL_83;
            v71 = (const wchar_t *)MemoryAlloc(v1235);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1192);
            if ( !v71 )
            {
              LastError = -2147024882;
LABEL_88:
              v1192 = 0;
              goto LABEL_89;
            }
            v1192 = (unsigned __int64)v71;
            v70 = v1235;
          }
          if ( !LastError )
          {
LABEL_83:
            LastError = -2147467259;
            goto LABEL_89;
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_89:
          SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1192);
          if ( LastError < 0 )
          {
LABEL_104:
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&pcchLength);
            SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Src);
            v75 = 0;
            if ( LastError >= 0 )
              v75 = v51;
            LODWORD(v1213) = v75;
            v76 = LocalAlloc(0x40u, 4u);
            SP<unsigned char,SP_HLOCAL<unsigned char>>::operator=(&v1222, v76);
            v1248 = v1222;
            if ( !v1222 )
            {
              v80 = -2147024882;
              v889 = 0;
              goto LABEL_1593;
            }
            v1240 = 0;
            *(_OWORD *)lpMem = 0;
            v1203 = 0;
            ProcessHeap = GetProcessHeap();
            v78 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
            v79 = v78;
            v1200 = -805306345;
            v80 = -1073741801;
            if ( !v78 )
            {
              v81 = 0;
              LODWORD(dwBytes) = -1073741801;
              goto LABEL_140;
            }
            *v78 = xmmword_1800A39E0;
            v78[1] = xmmword_1800A39F0;
            v78[2] = xmmword_1800A3A00;
            v78[3] = xmmword_1800A3A10;
            v78[4] = xmmword_1800A3A20;
            v78[5] = xmmword_1800A3A30;
            v78[6] = xmmword_1800A3A40;
            v78[7] = xmmword_1800A3A50;
            v78[8] = xmmword_1800A3A60;
            v78[9] = xmmword_1800A3A70;
            v82 = GetProcessHeap();
            v81 = HeapAlloc(v82, 8u, 8u);
            if ( !v81 )
            {
              LODWORD(dwBytes) = -1073741801;
              v81 = 0;
              goto LABEL_140;
            }
            *v81 = qword_1800A3920;
            v1210 = __rdtsc();
            LODWORD(v1194) = 0;
            v80 = RtlUIntAdd(4, 4, &v1194);
            dwBytes = (unsigned int)v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v83 = RtlUIntAdd(0, (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v83 | 0x10000000;
            LODWORD(dwBytes) = v83 | 0x10000000;
            if ( v83 < 0 )
              goto LABEL_140;
            LODWORD(v1194) = v84;
            v80 = RtlUIntAdd(v85, 160, &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v86 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v88 | v86;
            LODWORD(dwBytes) = v88 | v86;
            if ( (v88 | v86) < 0 )
              goto LABEL_140;
            LODWORD(v1194) = 0;
            v80 = RtlUIntAdd(v87, 8, &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v89 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v91 | v89;
            LODWORD(dwBytes) = v91 | v89;
            if ( (v91 | v89) < 0 )
              goto LABEL_140;
            LODWORD(v1194) = 0;
            v80 = RtlUIntAdd(v90, 8, &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v92 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v94 | v92;
            LODWORD(dwBytes) = v94 | v92;
            if ( (v94 | v92) < 0 )
              goto LABEL_140;
            pcchLength = 0;
            if ( StringCchLengthW(L"ChangeDesktopBackground-Enabled", v93, &pcchLength) < 0 )
            {
              v80 = -1073741762;
LABEL_339:
              LODWORD(dwBytes) = v80;
              goto LABEL_140;
            }
            LODWORD(v1194) = v95;
            v80 = RtlUIntAdd(4, (unsigned int)(2 * (pcchLength + 1)), &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v96 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v96 | 0x10000000;
            LODWORD(dwBytes) = v96 | 0x10000000;
            if ( v96 < 0 )
              goto LABEL_140;
            LODWORD(v1194) = 0;
            v80 = RtlUIntAdd(v97, v97, &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v98 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v100 | v98;
            LODWORD(dwBytes) = v100 | v98;
            if ( (v100 | v98) < 0 )
              goto LABEL_140;
            LODWORD(v1194) = 0;
            v80 = RtlUIntAdd(v99, v99, &v1194);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            v101 = RtlUIntAdd(HIDWORD(dwBytes), (unsigned int)v1194, (char *)&dwBytes + 4);
            v80 = v102 | v101;
            LODWORD(dwBytes) = v102 | v101;
            if ( (v102 | v101) < 0 )
              goto LABEL_140;
            HIDWORD(lpMem[0]) = HIDWORD(dwBytes);
            v103 = HIDWORD(dwBytes);
            v104 = GetProcessHeap();
            v105 = HeapAlloc(v104, 8u, v103);
            if ( !v105 )
            {
              v80 = -1073741801;
              goto LABEL_339;
            }
            LODWORD(v1197) = 0;
            lpMem[1] = v105;
            LODWORD(lpMem[0]) = 0;
            LODWORD(v1220) = 0;
            v1219 = 0;
            v1201 = (size_t)v105;
            LODWORD(Size) = 8;
            v80 = RtlULongLongAdd(v105, 4, &v1220);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            if ( v105 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
              goto LABEL_131;
            *v105 = 4;
            *v1220 = v106;
            v108 = Size;
            v109 = ++LODWORD(lpMem[0]);
            LODWORD(v1220) = 0;
            v1219 = 0;
            if ( v79 )
            {
              if ( !v107 )
                goto LABEL_134;
            }
            else if ( v107 )
            {
LABEL_134:
              v80 = -1073741811;
              goto LABEL_135;
            }
            v119 = (unsigned int *)lpMem[1];
            if ( lpMem[1] )
            {
              v1201 = (size_t)lpMem[1];
              LODWORD(Size) = 0;
              if ( v109 )
              {
                do
                {
                  LODWORD(v1194) = 0;
                  v80 = RtlUIntAdd(4, *v119, &v1194);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v80 = RtlULongLongAdd(v120, (unsigned int)v1194, &v1201);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  LODWORD(Size) = Size + 1;
                  v119 = (unsigned int *)v1201;
                }
                while ( (unsigned int)Size < v121 );
              }
              v80 = RtlULongLongAdd(v119, 4, &v1220);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              if ( (char *)v122 + v123 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                goto LABEL_131;
              *v122 = v123;
              if ( v79 )
                memcpy_0(v1220, v79, v123);
            }
            else
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, v107, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
            }
            v124 = ++LODWORD(lpMem[0]);
            LODWORD(v1220) = 0;
            v1219 = 0;
            if ( !v108 )
              goto LABEL_134;
            v125 = (unsigned int *)lpMem[1];
            if ( lpMem[1] )
            {
              v1201 = (size_t)lpMem[1];
              if ( v124 )
              {
                do
                {
                  LODWORD(v1194) = 0;
                  v80 = RtlUIntAdd(4, *v125, &v1194);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v80 = RtlULongLongAdd(v128, (unsigned int)v1194, &v1201);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v125 = (unsigned int *)v1201;
                }
                while ( v130 + 1 < v129 );
              }
              v80 = RtlULongLongAdd(v125, 4, &v1220);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              if ( (char *)v131 + v108 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                goto LABEL_131;
              *v131 = v108;
              memcpy_0(v1220, v81, v108);
              v127 = LODWORD(lpMem[0]) + 1;
            }
            else
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, v108, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v127 = v126 + LODWORD(lpMem[0]);
            }
            LODWORD(lpMem[0]) = v127;
            LODWORD(v1220) = 0;
            v1219 = 0;
            v132 = (unsigned int *)lpMem[1];
            if ( lpMem[1] )
            {
              v1201 = (size_t)lpMem[1];
              if ( v127 )
              {
                do
                {
                  LODWORD(v1194) = 0;
                  v80 = RtlUIntAdd(4, *v132, &v1194);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v80 = RtlULongLongAdd(v134, (unsigned int)v1194, &v1201);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v132 = (unsigned int *)v1201;
                }
                while ( v136 + 1 < v135 );
              }
              v80 = RtlULongLongAdd(v132, 4, &v1220);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              if ( v137 + 3 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                goto LABEL_131;
              *v137 = 8;
              *(_QWORD *)v1220 = v1210;
            }
            else
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 8, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
            }
            ++LODWORD(lpMem[0]);
            v1201 = 0;
            if ( StringCchLengthW(L"ChangeDesktopBackground-Enabled", v133, &v1201) < 0 )
            {
              v80 = -1073741762;
              goto LABEL_135;
            }
            v80 = RtlULongLongAdd(v1201, 1, &v1201);
            LODWORD(dwBytes) = v80;
            if ( v80 < 0 )
              goto LABEL_140;
            LODWORD(v1220) = 0;
            v1219 = 0;
            if ( !(2 * (_DWORD)v1201) )
              goto LABEL_134;
            v139 = (unsigned int *)lpMem[1];
            if ( lpMem[1] )
            {
              v1201 = (size_t)lpMem[1];
              v140 = 0;
              if ( v138 )
              {
                do
                {
                  LODWORD(v1194) = 0;
                  v80 = RtlUIntAdd(4, *v139, &v1194);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v80 = RtlULongLongAdd(v141, (unsigned int)v1194, &v1201);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  ++v140;
                  v139 = (unsigned int *)v1201;
                }
                while ( v140 < v142 );
              }
              v80 = RtlULongLongAdd(v139, 4, &v1220);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              if ( (char *)v143 + v144 + 4 > (char *)lpMem[1] + HIDWORD(lpMem[0]) )
                goto LABEL_131;
              *v143 = v144;
              memcpy_0(v1220, L"ChangeDesktopBackground-Enabled", (unsigned int)v144);
            }
            else
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, (unsigned int)(2 * v1201), &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
            }
            v145 = ++LODWORD(lpMem[0]);
            LODWORD(v1220) = 0;
            v1219 = 0;
            v146 = (unsigned int *)lpMem[1];
            if ( lpMem[1] )
            {
              v1201 = (size_t)lpMem[1];
              if ( v145 )
              {
                do
                {
                  LODWORD(v1194) = 0;
                  v80 = RtlUIntAdd(4, *v146, &v1194);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v80 = RtlULongLongAdd(v148, (unsigned int)v1194, &v1201);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v146 = (unsigned int *)v1201;
                }
                while ( v150 + 1 < v149 );
              }
              v80 = RtlULongLongAdd(v146, 4, &v1220);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              if ( v151 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                goto LABEL_131;
              *v151 = 4;
              *v1220 = v75;
              v147 = 1;
            }
            else
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
            }
            v152 = v147 + LODWORD(lpMem[0]);
            LODWORD(lpMem[0]) += v147;
            LODWORD(v1220) = 0;
            v1219 = 0;
            v153 = (unsigned int *)lpMem[1];
            if ( !lpMem[1] )
            {
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(HIDWORD(lpMem[0]), (unsigned int)v1194, (char *)lpMem + 4);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(lpMem[0]) += v154;
              goto LABEL_228;
            }
            v1201 = (size_t)lpMem[1];
            if ( v152 )
            {
              do
              {
                LODWORD(v1194) = 0;
                v80 = RtlUIntAdd(4, *v153, &v1194);
                LODWORD(dwBytes) = v80;
                if ( v80 < 0 )
                  goto LABEL_140;
                v80 = RtlULongLongAdd(v155, (unsigned int)v1194, &v1201);
                LODWORD(dwBytes) = v80;
                if ( v80 < 0 )
                  goto LABEL_140;
                v153 = (unsigned int *)v1201;
              }
              while ( v157 + 1 < v156 );
            }
            v80 = RtlULongLongAdd(v153, 4, &v1220);
            LODWORD(dwBytes) = v80;
            if ( v80 >= 0 )
            {
              if ( v158 + 2 > (_DWORD *)((char *)lpMem[1] + HIDWORD(lpMem[0])) )
                goto LABEL_131;
              *v158 = 4;
              *v1220 = 4;
              ++LODWORD(lpMem[0]);
LABEL_228:
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(v1208) = v1194;
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(v159, 8, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd(v160, (unsigned int)v1194, &v1208);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd((unsigned int)v1208, (unsigned int)v1194, &v1208);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd((unsigned int)v1208, (unsigned int)v1194, &v1208);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd((unsigned int)v1208, (unsigned int)v1194, &v1208);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              LODWORD(v1194) = 0;
              v80 = RtlUIntAdd(4, 4, &v1194);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v80 = RtlUIntAdd((unsigned int)v1208, (unsigned int)v1194, &v1208);
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_140;
              v1212 = 0;
              HIDWORD(dwBytes) = v1208;
              v1199 = 0;
              v1209 = (unsigned __int16 *)__rdtsc();
              LODWORD(v1196) = 0;
              v1227 = 8;
              v162 = RtlUIntAdd(8, HIDWORD(lpMem[0]), &v1227);
              if ( v162 < 0 )
              {
                v1211 = v81;
                v1221 = v79;
              }
              else
              {
                v163 = (v1227 + 7) & 0xFFFFFFF8;
                if ( v163 < v1227 )
                {
                  v80 = -805306219;
                  goto LABEL_339;
                }
                v1227 = (v1227 + 7) & 0xFFFFFFF8;
                v164 = v163;
                v165 = GetProcessHeap();
                v166 = (char *)HeapAlloc(v165, 8u, v164);
                v167 = v166;
                if ( !v166 )
                {
                  v80 = -805306345;
                  LODWORD(dwBytes) = -805306345;
                  goto LABEL_336;
                }
                v1221 = v79;
                v1211 = v81;
                v1201 = (size_t)v166;
                *(_DWORD *)v166 = lpMem[0];
                v162 = RtlULongLongAdd(v166, 4, &v1201);
                if ( v162 < 0
                  || (v170 = v1201,
                      *(_DWORD *)v1201 = HIDWORD(lpMem[0]),
                      v162 = RtlULongLongAdd(v170, v169, &v1201),
                      v162 < 0) )
                {
                  v1221 = v79;
                  v1211 = v81;
                  HIDWORD(dwBytes) = v168;
                  v171 = GetProcessHeap();
                  HeapFree(v171, 0, v167);
                  v161 = v1196;
                }
                else
                {
                  *(_QWORD *)&v167[v1227 - 8] = v1209;
                  memcpy_0((void *)v1201, lpMem[1], HIDWORD(lpMem[0]));
                  v1199 = v167;
                  v161 = v1227;
                }
              }
              v172 = 0;
              pcchLength = 0;
              v173 = 0;
              v1198 = 0;
              v1207 = 0;
              v1215 = 0;
              v80 = v162 | 0x10000000;
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
                goto LABEL_310;
              v174 = (unsigned __int8 *)v1199;
              if ( !v1199 )
              {
                v80 = -805306355;
                LODWORD(dwBytes) = -805306355;
                v75 = v1213;
                goto LABEL_140;
              }
              v1209 = (unsigned __int16 *)v161;
              if ( !v161 || (Size = v161 + 8LL, v175 = MemoryAlloc(Size), Src = v175, v176 = 0, !v175) )
              {
                v80 = -805306367;
                LODWORD(dwBytes) = -805306367;
                goto LABEL_312;
              }
              v1202 = 0;
              v1195 = 0;
              v177 = 0;
              v178 = 0;
              v179 = v1209;
              if ( v1209 )
              {
                do
                  v176 ^= v174[v178++];
                while ( v178 < (unsigned __int64)v1209 );
                v1195 = v176;
              }
              v1196 = 0xC81ECB17B1B54A58uLL;
              v180 = v174;
              v1204 = (SIZE_T)v174;
              v1201 = (size_t)v175;
              v181 = (unsigned __int8)v1209 & 7;
              v182 = 0;
              if ( ((unsigned __int8)v1209 & 7) != 0 )
              {
                LODWORD(v1208) = 0;
                LODWORD(dwBytes) = 0;
                v183 = 0;
                v184 = 0;
                do
                {
                  v185 = *v180++;
                  LODWORD(v1194) = 8 * v177;
                  if ( v177 >= 4 )
                    v183 |= v185 << (56 - v1194);
                  else
                    v184 |= v185 << (24 - v1194);
                  ++v177;
                }
                while ( (int)v177 < v181 );
                LODWORD(dwBytes) = v184;
                LODWORD(v1208) = v183;
                v1204 = (SIZE_T)v180;
                v1199 = v174;
                v1211 = v81;
                v1221 = v79;
                v172 = 0;
                v182 = v184 ^ 0xB17A307A;
                v186 = v183 ^ 0x42F6B18D;
                v187 = v184 ^ 0xB17A307A;
                v188 = v183 ^ 0x42F6B18D;
                LODWORD(v1216) = 0;
                if ( ((unsigned __int8)v1209 & 7) != 0 )
                {
                  v189 = (_BYTE *)v1201;
                  do
                  {
                    v1201 = (size_t)(v189 + 1);
                    if ( (unsigned int)v1216 >= 4 )
                    {
                      v188 = __ROR4__(v188, 24);
                      v190 = v188;
                    }
                    else
                    {
                      v187 = __ROR4__(v187, 24);
                      v190 = v187;
                    }
                    *v189 = v190;
                    LODWORD(v1216) = v1216 + 1;
                    v189 = (_BYTE *)v1201;
                  }
                  while ( (int)v1216 < v181 );
                }
                if ( (unsigned int)v181 <= 4 )
                {
                  v191 = 0;
                  if ( (unsigned int)v181 < 4 )
                    v182 = v182 >> (8 * (4 - v181)) << (8 * (4 - v181));
                }
                else
                {
                  v191 = v186 >> (8 * (8 - v181)) << (8 * (8 - v181));
                }
                v180 = (unsigned __int8 *)v1204;
              }
              else
              {
                v191 = -1;
                LODWORD(dwBytes) = 0;
                LODWORD(v1208) = 0;
              }
              if ( (unsigned __int64)v179 >> 3 )
              {
                v1216 = 0;
                LODWORD(v1194) = WORD1(v1196);
                v192 = WORD2(v1196);
                v193 = (unsigned __int64)v179 >> 3;
                v194 = (_BYTE *)v1201;
                v195 = v1208;
                v196 = dwBytes;
                do
                {
                  v197 = v180[3] | ((v180[2] | (((*v180 << 8) | v180[1]) << 8)) << 8);
                  v198 = *(unsigned __int8 *)(v1204 + 7)
                       | ((*(unsigned __int8 *)(v1204 + 6) | ((*(unsigned __int8 *)(v1204 + 5) | (v180[4] << 8)) << 8)) << 8);
                  v1204 += 8LL;
                  v199 = v182 ^ v197 ^ ((v191 ^ v198) - 19032);
                  v200 = HIDWORD(v1196) ^ v199;
                  v201 = v191 ^ v198 ^ (__ROR4__(HIDWORD(v1196) ^ v199, 7) + WORD1(v1196) * __ROR4__(v199, 15));
                  v202 = v200 ^ (v192 * __ROR4__(v201 - 1313519016, 9) - __ROR4__(v201, 10));
                  v203 = v201 ^ (__ROR4__(v202, 27) + HIWORD(v1196) * __ROR4__(v192 ^ v202, 28));
                  v204 = v202 ^ (HIDWORD(v1196) - (v203 ^ 0xB1B54A58));
                  v205 = v203 ^ (WORD1(v1196) * (v204 - 19032) - (v204 >> 6));
                  v206 = v204 ^ (19032 * (v192 ^ __ROR4__(v205, 15)));
                  v207 = v205 ^ (v192 * (HIWORD(v1196) + __ROR4__(~v206, 3)));
                  v208 = v207
                       ^ (v1194 * (HIWORD(v1196) ^ v206 ^ (v207 - 19032 - HIDWORD(v1196))))
                       ^ __ROR4__(v206 ^ (v207 - 19032 - HIDWORD(v1196)), 10);
                  v209 = v206
                       ^ (v207 - 19032 - HIDWORD(v1196))
                       ^ __ROR4__(v208, 3)
                       ^ (v192 * __ROR4__(v208 ^ 0x4A58, 26));
                  v210 = v208 ^ (19032 * (__ROR4__(v209, 15) - HIWORD(v1196)));
                  v211 = v209
                       ^ ((v210 ^ (v210 >> 14)) >> 1)
                       ^ (19032 * (HIWORD(v1196) ^ v210))
                       ^ (19032 * ((8 * (v210 - v192)) | ((v210 - v192) >> 29)));
                  v212 = v210 ^ (WORD1(v1196) * (v211 - v192) - (v211 >> 13));
                  v213 = v211 ^ __ROR4__(v212, 11) ^ (v192 * __ROR4__(-1313519016 - v212, 9));
                  v214 = v212 ^ (v213 - HIWORD(v1196) + 1313519016);
                  v215 = v213 ^ (19032 * (v1194 ^ v214) - __ROR4__(v214, 7));
                  v216 = v214 ^ (WORD1(v1196) * __ROR4__(HIWORD(v1196) ^ v215, 28) - __ROR4__(v215, 16));
                  v217 = v215 ^ (__ROR4__(v216, 4) + v192 * __ROR4__(-1313519016 - v216, 10));
                  v218 = v216 ^ __ROR4__(v217, 9) ^ (HIWORD(v1196) * __ROR4__(v217 + 1313519016, 4));
                  v219 = v217 ^ (19032 * __ROR4__(HIDWORD(v1196) ^ v218, 24) - __ROR4__(v218, 30));
                  v220 = v218 ^ (WORD1(v1196) * __ROR4__(HIDWORD(v1196) - v219, 11) - __ROR4__(v219, 12));
                  v221 = v219 ^ (v220 >> 8) ^ (v192 * (WORD1(v1196) ^ v220));
                  v182 = v196 ^ v221;
                  v191 = HIDWORD(v1196) ^ v195 ^ v220 ^ v221 ^ 0xB1B54A58;
                  v194[3] = v182;
                  v194[7] = v191;
                  v194[2] = __ROR4__(v182, 8);
                  v194[6] = __ROR4__(v191, 8);
                  v194[1] = __ROR4__(v182, 16);
                  v194[5] = __ROR4__(v191, 16);
                  *v194 = __ROR4__(v182, 24);
                  v194[4] = __ROR4__(v191, 24);
                  v196 = v197;
                  v195 = v198;
                  v194 += 8;
                  ++v1216;
                  v180 = (unsigned __int8 *)v1204;
                }
                while ( v1216 < v193 );
                v176 = v1195;
                v79 = v1221;
                v81 = v1211;
                v173 = v1198;
                v172 = (unsigned int *)v1198;
                v174 = (unsigned __int8 *)v1199;
                v179 = v1209;
              }
              *(_QWORD *)((char *)v179 + (_QWORD)Src) = v176;
              v222 = GetProcessHeap();
              v223 = HeapAlloc(v222, 8u, 0x30u);
              v1192 = (unsigned __int64)v223;
              if ( v223 )
              {
                *v223 = Size;
                v225 = GetProcessHeap();
                v226 = HeapAlloc(v225, 8u, (unsigned int)Size);
                if ( !v226 )
                  goto LABEL_284;
                v1199 = v174;
                v227 = v1192;
                *(_QWORD *)(v1192 + 8) = v226;
                memcpy_0(v226, Src, (unsigned int)Size);
                *(_DWORD *)(v227 + 16) = 160;
                v228 = GetProcessHeap();
                v229 = HeapAlloc(v228, 8u, 0xA0u);
                if ( !v229 )
                  goto LABEL_284;
                *(_QWORD *)(v227 + 24) = v229;
                *v229 = xmmword_1800A3930;
                v229[1] = xmmword_1800A3940;
                v229[2] = xmmword_1800A3950;
                v229[3] = xmmword_1800A3960;
                v229[4] = xmmword_1800A3970;
                v229[5] = xmmword_1800A3980;
                v229[6] = xmmword_1800A3990;
                v229[7] = xmmword_1800A39A0;
                v229[8] = xmmword_1800A39B0;
                v229[9] = xmmword_1800A39C0;
                *(_DWORD *)(v227 + 32) = 8;
                v230 = GetProcessHeap();
                v231 = HeapAlloc(v230, 8u, 8u);
                if ( v231 )
                {
                  *(_QWORD *)(v227 + 40) = v231;
                  *v231 = qword_1800A39D0;
                  v1202 = (LPVOID)v227;
                  v224 = 0;
                  v172 = (unsigned int *)v1202;
                  v1202 = 0;
                }
                else
                {
LABEL_284:
                  v224 = -1073741801;
                  v232 = v1192;
                  v1206 = *(_QWORD *)(v1192 + 8);
                  if ( v1206 )
                  {
                    v233 = GetProcessHeap();
                    HeapFree(v233, 0, (LPVOID)v1206);
                    v232 = v1192;
                    *(_QWORD *)(v1192 + 8) = 0;
                  }
                  v1206 = *(_QWORD *)(v232 + 24);
                  if ( v1206 )
                  {
                    v234 = GetProcessHeap();
                    HeapFree(v234, 0, (LPVOID)v1206);
                    v232 = v1192;
                    *(_QWORD *)(v1192 + 24) = 0;
                  }
                  v1206 = *(_QWORD *)(v232 + 40);
                  if ( v1206 )
                  {
                    v235 = GetProcessHeap();
                    HeapFree(v235, 0, (LPVOID)v1206);
                    *(_QWORD *)(v1192 + 40) = 0;
                  }
                  v236 = GetProcessHeap();
                  HeapFree(v236, 0, (LPVOID)v1192);
                }
              }
              else
              {
                v224 = -1073741801;
              }
              v237 = GetProcessHeap();
              HeapFree(v237, 0, Src);
              v238 = v1202;
              if ( v1202 )
              {
                v1206 = *((_QWORD *)v1202 + 1);
                if ( v1206 )
                {
                  v239 = GetProcessHeap();
                  HeapFree(v239, 0, (LPVOID)v1206);
                  v238 = v1202;
                  *((_QWORD *)v1202 + 1) = 0;
                }
                v1206 = v238[3];
                if ( v1206 )
                {
                  v240 = GetProcessHeap();
                  HeapFree(v240, 0, (LPVOID)v1206);
                  v238 = v1202;
                  *((_QWORD *)v1202 + 3) = 0;
                }
                v1206 = v238[5];
                if ( v1206 )
                {
                  v241 = GetProcessHeap();
                  HeapFree(v241, 0, (LPVOID)v1206);
                  *((_QWORD *)v1202 + 5) = 0;
                }
                v242 = GetProcessHeap();
                HeapFree(v242, 0, v1202);
              }
              v80 = v224 | 0x10000000;
              LODWORD(dwBytes) = v80;
              if ( v80 < 0 )
              {
                v249 = v1199;
LABEL_311:
                if ( !v249 )
                {
LABEL_313:
                  if ( v172 )
                  {
                    v1206 = *((_QWORD *)v172 + 1);
                    if ( v1206 )
                    {
                      v251 = GetProcessHeap();
                      HeapFree(v251, 0, (LPVOID)v1206);
                      *((_QWORD *)v172 + 1) = 0;
                    }
                    v1206 = *((_QWORD *)v172 + 3);
                    if ( v1206 )
                    {
                      v252 = GetProcessHeap();
                      HeapFree(v252, 0, (LPVOID)v1206);
                      *((_QWORD *)v172 + 3) = 0;
                    }
                    v1206 = *((_QWORD *)v172 + 5);
                    if ( v1206 )
                    {
                      v253 = GetProcessHeap();
                      HeapFree(v253, 0, (LPVOID)v1206);
                      *((_QWORD *)v172 + 5) = 0;
                    }
                    v254 = GetProcessHeap();
                    HeapFree(v254, 0, v172);
                  }
                  v255 = (void *)pcchLength;
                  if ( pcchLength )
                  {
                    v256 = GetProcessHeap();
                    HeapFree(v256, 0, v255);
                  }
                  if ( v173 )
                  {
                    v257 = GetProcessHeap();
                    HeapFree(v257, 0, v173);
                  }
                  v258 = v1207;
                  if ( v1207 )
                  {
                    v259 = (void *)*((_QWORD *)v1207 + 1);
                    if ( v259 )
                    {
                      v260 = GetProcessHeap();
                      HeapFree(v260, 0, v259);
                      v258[1] = 0;
                    }
                    v261 = (void *)v258[3];
                    if ( v261 )
                    {
                      v262 = GetProcessHeap();
                      HeapFree(v262, 0, v261);
                      v258[3] = 0;
                    }
                    v263 = (void *)v258[5];
                    if ( v263 )
                    {
                      v264 = GetProcessHeap();
                      HeapFree(v264, 0, v263);
                      v258[5] = 0;
                    }
                    v265 = GetProcessHeap();
                    HeapFree(v265, 0, v258);
                  }
                  v266 = v1215;
                  if ( v1215 )
                  {
                    v267 = GetProcessHeap();
                    HeapFree(v267, 0, v266);
                  }
                  v75 = v1213;
LABEL_336:
                  if ( v80 < 0 )
                    goto LABEL_140;
                  if ( !v1212 )
                    goto LABEL_338;
                  if ( !v1203 )
                    goto LABEL_134;
                  v1209 = (unsigned __int16 *)v1203;
                  v80 = RtlULongLongAdd(v1203, 4, &v1209);
                  LODWORD(dwBytes) = v80;
                  v1203 = v403;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v404 = v1209;
                  if ( !*v403 )
                    v404 = 0;
                  if ( *v403 != 4 )
                    goto LABEL_131;
                  v80 = *(_DWORD *)v404;
                  LODWORD(dwBytes) = v80;
                  if ( v80 == -805306333 )
                  {
                    v405 = -2147024774;
                  }
                  else
                  {
                    v405 = v80;
                    if ( v80 != -2147024774 )
                    {
                      LODWORD(v1197) = v80;
                      if ( v80 < 0 )
                        goto LABEL_140;
                      goto LABEL_537;
                    }
                  }
                  LODWORD(v1197) = v405;
LABEL_537:
                  v1203 = v403;
                  if ( v402 != 6 )
                  {
LABEL_338:
                    v80 = -1073425151;
                    goto LABEL_339;
                  }
                  v1192 = v401;
                  do
                  {
                    v80 = RtlULongLongAdd(v401, 4, &v1192);
                    LODWORD(dwBytes) = v80;
                    if ( v80 < 0 )
                      goto LABEL_140;
                    v80 = RtlULongLongAdd(v1192, v406, &v1192);
                    LODWORD(dwBytes) = v80;
                    if ( v80 < 0 )
                      goto LABEL_140;
                    v401 = v1192;
                  }
                  while ( v407 == -1 );
                  v80 = RtlULongLongAdd(v1192, 4, &v1192);
                  LODWORD(dwBytes) = v80;
                  if ( v80 < 0 )
                    goto LABEL_140;
                  v410 = (size_t *)v1192;
                  if ( !v408 )
                    v410 = 0;
                  if ( v408 == 8 )
                  {
                    LODWORD(v1197) = v405;
                    v1203 = v409;
                    if ( !v409 )
                      goto LABEL_134;
                    v411 = (unsigned __int64)v409;
                    v1192 = (unsigned __int64)v409;
                    v1206 = *v410;
                    do
                    {
                      v80 = RtlULongLongAdd(v411, 4, &v1192);
                      LODWORD(dwBytes) = v80;
                      if ( v80 < 0 )
                        goto LABEL_140;
                      v80 = RtlULongLongAdd(v1192, v412, &v1192);
                      LODWORD(dwBytes) = v80;
                      if ( v80 < 0 )
                        goto LABEL_140;
                      v411 = v1192;
                    }
                    while ( (unsigned int)(v413 + 1) < 2 );
                    v80 = RtlULongLongAdd(v1192, 4, &v1192);
                    LODWORD(dwBytes) = v80;
                    if ( v80 < 0 )
                      goto LABEL_140;
                    v416 = (_DWORD *)v1192;
                    if ( !v414 )
                      v416 = 0;
                    if ( v414 == 4 )
                    {
                      LODWORD(v1197) = v405;
                      v1203 = v415;
                      if ( !v415 )
                        goto LABEL_134;
                      v417 = (unsigned __int64)v415;
                      v1192 = (unsigned __int64)v415;
                      LODWORD(v1202) = *v416;
                      v418 = 0;
                      do
                      {
                        v80 = RtlULongLongAdd(v417, 4, &v1192);
                        LODWORD(dwBytes) = v80;
                        if ( v80 < 0 )
                          goto LABEL_140;
                        v80 = RtlULongLongAdd(v1192, v419, &v1192);
                        LODWORD(dwBytes) = v80;
                        if ( v80 < 0 )
                          goto LABEL_140;
                        v417 = v1192;
                      }
                      while ( (unsigned int)(v420 + 1) < 3 );
                      v80 = RtlULongLongAdd(v1192, 4, &v1192);
                      LODWORD(dwBytes) = v80;
                      if ( v80 < 0 )
                        goto LABEL_140;
                      if ( v421 )
                        v418 = (const void *)v1192;
                      v423 = v422;
                      v1192 = (unsigned __int64)v422;
                      do
                      {
                        LODWORD(v1196) = *v423;
                        v80 = RtlULongLongAdd(v423, 4, &v1192);
                        LODWORD(dwBytes) = v80;
                        if ( v80 < 0 )
                          goto LABEL_140;
                        v80 = RtlULongLongAdd(v1192, (unsigned int)v1196, &v1192);
                        LODWORD(dwBytes) = v80;
                        if ( v80 < 0 )
                          goto LABEL_140;
                        v423 = (_DWORD *)v1192;
                      }
                      while ( (unsigned int)(v424 + 1) < 4 );
                      v80 = RtlULongLongAdd(v1192, 4, &v1192);
                      LODWORD(dwBytes) = v80;
                      if ( v80 < 0 )
                        goto LABEL_140;
                      v427 = (_DWORD *)v1192;
                      if ( !v425 )
                        v427 = 0;
                      if ( v425 == 4 )
                      {
                        v1203 = v426;
                        if ( !v426 )
                        {
                          v80 = -1073741811;
                          goto LABEL_339;
                        }
                        v428 = (unsigned __int64)v426;
                        v1192 = (unsigned __int64)v426;
                        LODWORD(v1196) = *v427;
                        do
                        {
                          v80 = RtlULongLongAdd(v428, 4, &v1192);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_140;
                          v80 = RtlULongLongAdd(v1192, v429, &v1192);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_140;
                          v428 = v1192;
                        }
                        while ( (unsigned int)(v430 + 1) < 5 );
                        v110 = RtlULongLongAdd(v1192, 4, &v1192);
                        v80 = v110;
                        LODWORD(dwBytes) = v110;
                        if ( v110 >= 0 )
                        {
                          v434 = (int *)v1192;
                          if ( !v431 )
                            v434 = v433;
                          if ( v431 != 4 )
                          {
                            v80 = -1073741789;
                            goto LABEL_339;
                          }
                          if ( v1210 != v1206 )
                            goto LABEL_338;
                          v75 = *v434;
                          v1240 = (unsigned int)v1202;
                          if ( (unsigned int)v1196 > 4 || (unsigned int)v432 > 4 )
                          {
                            v80 = -2147024774;
                            goto LABEL_339;
                          }
                          memcpy_0(v1248, v418, v432);
                          v110 = v1197;
                          if ( !(_DWORD)v1197 )
                            goto LABEL_140;
                          v80 = v1197;
                        }
                        LODWORD(dwBytes) = v110;
                        goto LABEL_140;
                      }
                    }
                  }
LABEL_131:
                  v80 = -1073741789;
LABEL_135:
                  LODWORD(dwBytes) = v80;
                  goto LABEL_140;
                }
LABEL_312:
                v250 = GetProcessHeap();
                HeapFree(v250, 0, v1199);
                goto LABEL_313;
              }
              LODWORD(v1194) = 0;
              LODWORD(dwBytes) = 4;
              v244 = RtlUIntAdd(4, *v172, &dwBytes);
              if ( v244 < 0
                || (v244 = RtlUIntAdd((unsigned int)dwBytes, v243, &dwBytes), v244 < 0)
                || (v1209 = (unsigned __int16 *)(v172 + 4),
                    v244 = RtlUIntAdd((unsigned int)dwBytes, v172[4], &dwBytes),
                    v244 < 0)
                || (v244 = RtlUIntAdd((unsigned int)dwBytes, v245, &dwBytes), v244 < 0)
                || (Src = v172 + 8, v244 = RtlUIntAdd((unsigned int)dwBytes, v172[8], &dwBytes), v244 < 0) )
              {
                v268 = v1199;
                goto LABEL_352;
              }
              v246 = dwBytes;
              v247 = GetProcessHeap();
              v248 = HeapAlloc(v247, 8u, v246);
              v1211 = v248;
              if ( !v248 )
              {
                v80 = -805306345;
LABEL_308:
                LODWORD(dwBytes) = v80;
LABEL_309:
                v173 = v1198;
LABEL_310:
                v249 = v1199;
                goto LABEL_311;
              }
              v268 = v1199;
              v1196 = (SIZE_T)v248;
              *v248 = *v172;
              v244 = RtlULongLongAdd(v248, 4, &v1196);
              if ( v244 < 0 )
              {
                HIDWORD(dwBytes) = v270;
                v1211 = v269;
              }
              else
              {
                memcpy_0((void *)v1196, *((const void **)v172 + 1), *v172);
                v244 = RtlULongLongAdd(v1196, *v172, &v1196);
                if ( v244 >= 0 )
                {
                  v271 = v1196;
                  *(_DWORD *)v1196 = *(_DWORD *)v1209;
                  v244 = RtlULongLongAdd(v271, 4, &v1196);
                  if ( v244 >= 0 )
                  {
                    memcpy_0((void *)v1196, *((const void **)v172 + 3), *v272);
                    v244 = RtlULongLongAdd(v1196, *(unsigned int *)v1209, &v1196);
                    if ( v244 >= 0 )
                    {
                      v273 = v1196;
                      *(_DWORD *)v1196 = *(_DWORD *)Src;
                      v244 = RtlULongLongAdd(v273, 4, &v1196);
                      if ( v244 >= 0 )
                      {
                        memcpy_0((void *)v1196, *((const void **)v172 + 5), *v274);
                        v244 = RtlULongLongAdd(v1196, *(unsigned int *)Src, &v1196);
                        if ( v244 >= 0 )
                        {
                          pcchLength = (size_t)v1211;
                          LODWORD(v1194) = dwBytes;
LABEL_352:
                          v80 = v244 | 0x10000000;
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v1234 = 8;
                          v276 = RtlUIntAdd(8, HIDWORD(dwBytes), &v1234);
                          v80 = v277 | v276;
                          LODWORD(dwBytes) = v277 | v276;
                          if ( (v277 | v276) < 0 )
                            goto LABEL_309;
                          v278 = (v1234 + 7) & 0xFFFFFFF8;
                          if ( (unsigned int)v278 < v1234 )
                          {
                            v80 = -1073741675;
                            goto LABEL_308;
                          }
                          v1241 = (v1234 + 7) & 0xFFFFFFF8;
                          v80 = RtlUIntAdd(v278, 8, &v1241);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v1221 = v79;
                          v1211 = v81;
                          v1199 = v268;
                          v1192 = (unsigned __int64)v172;
                          LODWORD(v1216) = v279;
                          v280 = lpMem[1];
                          if ( !lpMem[1] )
                            goto LABEL_365;
                          v1192 = (unsigned __int64)v172;
                          v1199 = v268;
                          v1211 = v81;
                          v1221 = v79;
                          if ( LODWORD(lpMem[0]) <= 1 )
                            goto LABEL_365;
                          v1196 = (SIZE_T)lpMem[1];
                          do
                          {
                            v80 = RtlULongLongAdd(v280, 4, &v1196);
                            LODWORD(dwBytes) = v80;
                            if ( v80 < 0 )
                              goto LABEL_309;
                            v80 = RtlULongLongAdd(v1196, v281, &v1196);
                            LODWORD(dwBytes) = v80;
                            if ( v80 < 0 )
                              goto LABEL_309;
                            v280 = (LPVOID)v1196;
                          }
                          while ( v282 == -1 );
                          v283 = *(_DWORD *)v1196;
                          v80 = RtlULongLongAdd(v1196, 4, &v1196);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v284 = lpMem[1];
                          if ( !lpMem[1] || LODWORD(lpMem[0]) <= 2 )
                          {
LABEL_365:
                            v80 = -1073741811;
                            LODWORD(dwBytes) = -1073741811;
                            goto LABEL_309;
                          }
                          v1196 = (SIZE_T)lpMem[1];
                          do
                          {
                            v80 = RtlULongLongAdd(v284, 4, &v1196);
                            LODWORD(dwBytes) = v80;
                            if ( v80 < 0 )
                              goto LABEL_309;
                            v80 = RtlULongLongAdd(v1196, v288, &v1196);
                            LODWORD(dwBytes) = v80;
                            if ( v80 < 0 )
                              goto LABEL_309;
                            v284 = (LPVOID)v1196;
                          }
                          while ( (unsigned int)(v289 + 1) < 2 );
                          v80 = RtlULongLongAdd(v1196, 4, &v1196);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          LODWORD(v1216) = v290;
                          LODWORD(v1208) = 4;
                          v80 = RtlUIntAdd((unsigned int)(v290 + 4), v1241, &v1208);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v80 = RtlUIntAdd((unsigned int)v1208, v291, &v1208);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v80 = RtlUIntAdd((unsigned int)v1208, v283, &v1208);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v80 = RtlUIntAdd((unsigned int)v1208, (unsigned int)(v292 + 4), &v1208);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          v80 = RtlUIntAdd((unsigned int)v1208, v293, &v1208);
                          LODWORD(dwBytes) = v80;
                          if ( v80 < 0 )
                            goto LABEL_309;
                          LODWORD(v1216) = v1208;
                          if ( (unsigned int)v1208 > 0x400000 )
                          {
                            v80 = -2147418113;
                            goto LABEL_308;
                          }
                          v285 = v1208;
                          v286 = GetProcessHeap();
                          v287 = HeapAlloc(v286, 8u, v285);
                          v173 = v287;
                          if ( !v287 )
                          {
                            v80 = -805306345;
                            LODWORD(dwBytes) = -805306345;
                            v173 = 0;
                            goto LABEL_310;
                          }
                          v1250 = 0;
                          v1251 = 0;
                          phModule = 0;
                          if ( !pcchLength )
                          {
                            v80 = -2147024809;
LABEL_396:
                            LODWORD(dwBytes) = v80;
                            goto LABEL_310;
                          }
                          *(_QWORD *)&v1250 = pcchLength;
                          LODWORD(v1251) = v1194;
                          *((_QWORD *)&v1250 + 1) = v287;
                          *(_QWORD *)((char *)&v1251 + 4) = (unsigned int)v1216;
                          if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                            && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                          {
                            v296 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(134, &v1250);
                            v80 = v296 | 0x10000000;
                            LODWORD(dwBytes) = v296 | 0x10000000;
                            if ( v296 >= 0 )
                            {
                              v297 = DWORD1(v1251);
                              goto LABEL_399;
                            }
                          }
                          else
                          {
                            v294 = GetLastError();
                            LODWORD(dwBytes) = v294;
                            v80 = v294;
                            if ( v294 > 0 )
                            {
                              v80 = (unsigned __int16)v294 | 0x80070000;
                              LODWORD(dwBytes) = v80;
                            }
                            if ( v80 >= 0 )
                            {
                              v80 = -2147467259;
                              goto LABEL_396;
                            }
                          }
                          if ( v80 == -805306333 )
                          {
                            v80 = -2147024774;
                            goto LABEL_396;
                          }
                          if ( v80 < 0 )
                            goto LABEL_310;
                          v297 = v1216;
LABEL_399:
                          HIDWORD(dwBytes) = 0;
                          v1198 = v173;
                          if ( v297 < 4 )
                          {
LABEL_400:
                            v80 = -805306306;
                            goto LABEL_396;
                          }
                          LODWORD(v1196) = *v173;
                          v299 = RtlULongLongAdd(v173, 4, &v1198);
                          if ( v299 >= 0 )
                          {
                            v299 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                            if ( v299 >= 0 )
                            {
                              if ( v300 - HIDWORD(dwBytes) < (unsigned int)v301 )
                                goto LABEL_400;
                              v1209 = (unsigned __int16 *)v1198;
                              v1206 = v301;
                              v299 = RtlULongLongAdd(v1198, (unsigned int)v301, &v1198);
                              if ( v299 >= 0 )
                              {
                                v299 = RtlUIntAdd(HIDWORD(dwBytes), v302, (char *)&dwBytes + 4);
                                if ( v299 >= 0 )
                                {
                                  if ( (unsigned int)(v303 - HIDWORD(dwBytes)) < 4 )
                                    goto LABEL_400;
                                  LODWORD(v1202) = *(_DWORD *)v1198;
                                  v299 = RtlULongLongAdd(v1198, 4, &v1198);
                                  if ( v299 >= 0 )
                                  {
                                    v299 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                    if ( v299 >= 0 )
                                    {
                                      if ( v304 - HIDWORD(dwBytes) < (unsigned int)v305 )
                                        goto LABEL_400;
                                      v1201 = (size_t)v1198;
                                      Src = v305;
                                      v299 = RtlULongLongAdd(v1198, (unsigned int)v305, &v1198);
                                      if ( v299 >= 0 )
                                      {
                                        v299 = RtlUIntAdd(HIDWORD(dwBytes), v306, (char *)&dwBytes + 4);
                                        if ( v299 >= 0 )
                                        {
                                          if ( (unsigned int)(v307 - HIDWORD(dwBytes)) < 4 )
                                            goto LABEL_400;
                                          LODWORD(v1204) = *(_DWORD *)v1198;
                                          v299 = RtlULongLongAdd(v1198, 4, &v1198);
                                          if ( v299 >= 0 )
                                          {
                                            v299 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                            if ( v299 >= 0 )
                                            {
                                              if ( v308 - HIDWORD(dwBytes) < v309 )
                                                goto LABEL_400;
                                              v299 = RtlUIntAdd(HIDWORD(dwBytes), v309, (char *)&dwBytes + 4);
                                              if ( v299 >= 0 )
                                              {
                                                if ( v310 != HIDWORD(dwBytes) )
                                                  goto LABEL_400;
                                                v313 = (unsigned int)v1196;
                                                if ( (unsigned int)(v1196 + v311 + v312) + 12LL != v310 )
                                                  goto LABEL_400;
                                                v314 = GetProcessHeap();
                                                v315 = HeapAlloc(v314, 8u, 0x30u);
                                                v1207 = v315;
                                                v298 = 0;
                                                v249 = v1199;
                                                if ( !v315 )
                                                {
                                                  v1207 = 0;
                                                  v80 = -805306345;
                                                  LODWORD(dwBytes) = -805306345;
                                                  goto LABEL_311;
                                                }
                                                v1221 = v79;
                                                v1211 = v81;
                                                v1192 = (unsigned __int64)v172;
                                                v1196 = 0;
                                                if ( v1209 )
                                                {
                                                  *v315 = v313;
                                                  v316 = GetProcessHeap();
                                                  v317 = HeapAlloc(v316, 8u, v313);
                                                  if ( !v317 )
                                                  {
LABEL_432:
                                                    v299 = -1073741801;
                                                    v1198 = v173;
                                                    v325 = v1207;
                                                    v1206 = *((_QWORD *)v1207 + 1);
                                                    if ( v1206 )
                                                    {
                                                      v326 = GetProcessHeap();
                                                      HeapFree(v326, 0, (LPVOID)v1206);
                                                      v325 = v1207;
                                                      *((_QWORD *)v1207 + 1) = 0;
                                                    }
                                                    v1206 = v325[3];
                                                    if ( v1206 )
                                                    {
                                                      v327 = GetProcessHeap();
                                                      HeapFree(v327, 0, (LPVOID)v1206);
                                                      v325 = v1207;
                                                      *((_QWORD *)v1207 + 3) = 0;
                                                    }
                                                    v1206 = v325[5];
                                                    if ( v1206 )
                                                    {
                                                      v328 = GetProcessHeap();
                                                      HeapFree(v328, 0, (LPVOID)v1206);
                                                      *((_QWORD *)v1207 + 5) = 0;
                                                    }
                                                    v329 = GetProcessHeap();
                                                    HeapFree(v329, 0, v1207);
                                                    v330 = (size_t *)v1196;
                                                    v298 = 0;
                                                    goto LABEL_442;
                                                  }
                                                  *((_QWORD *)v1207 + 1) = v317;
                                                  v299 = 0;
                                                  memcpy_0(v317, v1209, v1206);
                                                  v315 = v1207;
                                                  v298 = 0;
                                                }
                                                else
                                                {
                                                  *v315 = 0;
                                                  *((_QWORD *)v315 + 1) = 0;
                                                  v299 = 0;
                                                }
                                                if ( v1201 )
                                                {
                                                  v315[4] = (_DWORD)v1202;
                                                  v318 = GetProcessHeap();
                                                  v319 = HeapAlloc(v318, 8u, (SIZE_T)Src);
                                                  v320 = v1207;
                                                  if ( !v319 )
                                                  {
LABEL_431:
                                                    v1207 = v320;
                                                    v1221 = v79;
                                                    v1211 = v81;
                                                    v1192 = (unsigned __int64)v172;
                                                    goto LABEL_432;
                                                  }
                                                  *((_QWORD *)v1207 + 3) = v319;
                                                  v299 = 0;
                                                  memcpy_0(v319, (const void *)v1201, (size_t)Src);
                                                  v315 = v1207;
                                                  v298 = 0;
                                                }
                                                else
                                                {
                                                  v315[4] = 0;
                                                  *((_QWORD *)v315 + 3) = 0;
                                                }
                                                if ( v1198 )
                                                {
                                                  v321 = (unsigned int)v1204;
                                                  v315[8] = v1204;
                                                  v322 = v321;
                                                  v1206 = v321;
                                                  v323 = GetProcessHeap();
                                                  v324 = HeapAlloc(v323, 8u, v322);
                                                  v320 = v1207;
                                                  if ( !v324 )
                                                    goto LABEL_431;
                                                  *((_QWORD *)v1207 + 5) = v324;
                                                  v299 = 0;
                                                  memcpy_0(v324, v1198, v1206);
                                                  v315 = v1207;
                                                  v298 = 0;
                                                }
                                                else
                                                {
                                                  v315[8] = 0;
                                                  *((_QWORD *)v315 + 5) = 0;
                                                }
                                                v330 = (size_t *)v315;
                                                v1196 = (SIZE_T)v315;
                                                v1198 = v173;
                                                v1192 = (unsigned __int64)v172;
                                                v1211 = v81;
                                                v1221 = v79;
LABEL_442:
                                                if ( v299 < 0 )
                                                {
                                                  v331 = 0;
                                                  v1207 = 0;
                                                  if ( v330 )
                                                  {
                                                    v1206 = v330[1];
                                                    if ( v1206 )
                                                    {
                                                      v332 = GetProcessHeap();
                                                      HeapFree(v332, 0, (LPVOID)v1206);
                                                      v330 = (size_t *)v1196;
                                                      *(_QWORD *)(v1196 + 8) = 0;
                                                    }
                                                    v1206 = v330[3];
                                                    if ( v1206 )
                                                    {
                                                      v333 = GetProcessHeap();
                                                      HeapFree(v333, 0, (LPVOID)v1206);
                                                      v330 = (size_t *)v1196;
                                                      *(_QWORD *)(v1196 + 24) = 0;
                                                    }
                                                    v1206 = v330[5];
                                                    if ( v1206 )
                                                    {
                                                      v334 = GetProcessHeap();
                                                      HeapFree(v334, 0, (LPVOID)v1206);
                                                      *(_QWORD *)(v1196 + 40) = 0;
                                                    }
                                                    v335 = GetProcessHeap();
                                                    HeapFree(v335, 0, (LPVOID)v1196);
                                                    v298 = 0;
                                                    v331 = 0;
                                                    v1207 = 0;
                                                  }
                                                }
                                                else
                                                {
                                                  v331 = (unsigned int *)v330;
                                                  v1207 = v330;
                                                }
LABEL_454:
                                                v80 = v299 | 0x10000000;
                                                LODWORD(dwBytes) = v80;
                                                if ( v80 < 0 )
                                                  goto LABEL_310;
                                                if ( !v331 || (v1204 = *((_QWORD *)v331 + 1)) == 0 || *v331 == v298 )
                                                {
                                                  v80 = -805306355;
                                                  goto LABEL_396;
                                                }
                                                v336 = *v331 - 8LL;
                                                v1202 = (LPVOID)v336;
                                                v337 = MemoryAlloc(v336);
                                                v1215 = v337;
                                                if ( !v337 )
                                                {
LABEL_486:
                                                  v1215 = 0;
                                                  v80 = -805306367;
                                                  goto LABEL_396;
                                                }
                                                v338 = 0;
                                                v1195 = 0;
                                                v1196 = 0x7F1137FAB69605ELL;
                                                Src = (void *)v1204;
                                                v1209 = (unsigned __int16 *)v337;
                                                v339 = v336 & 7;
                                                v340 = 0;
                                                LODWORD(dwBytes) = 0;
                                                v341 = 0;
                                                if ( (v336 & 7) != 0 )
                                                {
                                                  HIDWORD(dwBytes) = 0;
                                                  v342 = (unsigned __int8 *)Src;
                                                  v343 = 0;
                                                  v344 = 0;
                                                  do
                                                  {
                                                    v345 = *v342++;
                                                    LODWORD(v1194) = 8 * v341;
                                                    if ( (unsigned int)v341 >= 4 )
                                                      v343 |= v345 << (56 - v1194);
                                                    else
                                                      v344 |= v345 << (24 - v1194);
                                                    ++v341;
                                                  }
                                                  while ( v341 < v339 );
                                                  dwBytes = __PAIR64__(v343, v344);
                                                  Src = v342;
                                                  v1198 = v173;
                                                  v1192 = (unsigned __int64)v172;
                                                  v1211 = v81;
                                                  v1221 = v79;
                                                  v338 = v1195;
                                                  v336 = (unsigned __int64)v1202;
                                                  v340 = dwBytes ^ 0x92F65A5;
                                                  v346 = v343 ^ 0x699A899C;
                                                  v347 = dwBytes ^ 0x92F65A5;
                                                  v348 = v343 ^ 0x699A899C;
                                                  LODWORD(v1216) = 0;
                                                  if ( v339 )
                                                  {
                                                    v349 = v337;
                                                    do
                                                    {
                                                      v1206 = (size_t)(v349 + 1);
                                                      if ( (unsigned int)v1216 >= 4 )
                                                      {
                                                        v348 = __ROR4__(v348, 24);
                                                        v350 = v348;
                                                      }
                                                      else
                                                      {
                                                        v347 = __ROR4__(v347, 24);
                                                        v350 = v347;
                                                      }
                                                      *v349 = v350;
                                                      LODWORD(v1216) = v1216 + 1;
                                                      v349 = (_BYTE *)v1206;
                                                    }
                                                    while ( (int)v1216 < v339 );
                                                    v1209 = (unsigned __int16 *)v1206;
                                                  }
                                                  if ( (unsigned int)v339 <= 4 )
                                                  {
                                                    v341 = 0;
                                                    if ( (unsigned int)v339 < 4 )
                                                      v340 = v340 >> (8 * (4 - v339)) << (8 * (4 - v339));
                                                  }
                                                  else
                                                  {
                                                    v341 = v346 >> (8 * (8 - v339)) << (8 * (8 - v339));
                                                  }
                                                }
                                                else
                                                {
                                                  HIDWORD(dwBytes) = -1;
                                                }
                                                v1206 = v336 >> 3;
                                                if ( v336 >> 3 )
                                                {
                                                  v1201 = 0;
                                                  v351 = HIDWORD(v1196);
                                                  v352 = HIDWORD(v1196) ^ 0xAB69605E;
                                                  LODWORD(Size) = HIDWORD(v1196) ^ 0xAB69605E;
                                                  LODWORD(v1194) = WORD2(v1196);
                                                  LODWORD(v1208) = 24670;
                                                  v353 = (unsigned __int8 *)Src;
                                                  v354 = v1209;
                                                  v355 = v1206;
                                                  v356 = HIDWORD(dwBytes);
                                                  v357 = dwBytes;
                                                  do
                                                  {
                                                    v358 = v353[3] | ((v353[2] | ((v353[1] | (*v353 << 8)) << 8)) << 8);
                                                    v359 = v353[7]
                                                         | ((v353[6] | ((v353[5] | (v353[4] << 8)) << 8)) << 8);
                                                    v353 += 8;
                                                    v360 = v340 ^ v358;
                                                    v361 = v340 ^ v358 ^ v341 ^ v359 ^ v352;
                                                    v362 = v360
                                                         ^ (__ROR4__(v361, 22) + v1194 * __ROR4__(v361 + 1419157410, 27));
                                                    v363 = v361
                                                         ^ (WORD1(v1196) * __ROR4__(v351 + v362, 9) - __ROR4__(v362, 30));
                                                    v364 = v362 ^ (v1208 * (v363 - v1194) - (v363 >> 13));
                                                    v365 = v363
                                                         ^ (HIWORD(v1196) * __ROR4__(v364 ^ WORD1(v1196), 26)
                                                          - __ROR4__(v364, 30));
                                                    v366 = v364 ^ (v351 - (v365 ^ 0xAB69605E));
                                                    v367 = v365 ^ (WORD1(v1196) * (v366 ^ v1194)) ^ __ROR4__(v366, 6);
                                                    v368 = v366
                                                         ^ (__ROR4__(v367, 30) + v1208 * __ROR4__(v351 + v367, 15));
                                                    v369 = v367
                                                         ^ (HIWORD(v1196) * __ROR4__(v368 + 1419157410, 14)
                                                          - __ROR4__(v368, 24));
                                                    v370 = v368
                                                         ^ __ROR4__(v369, 10)
                                                         ^ (v1194 * __ROR4__(v369 ^ 0xAB69605E, 12));
                                                    v371 = v370
                                                         ^ (HIWORD(v1196)
                                                          * (v1208
                                                           + __ROR4__(
                                                               ~(v369
                                                               ^ (v370 >> 10)
                                                               ^ (WORD1(v1196) * (HIWORD(v1196) ^ v370))),
                                                               5)));
                                                    v372 = v369
                                                         ^ (v370 >> 10)
                                                         ^ (WORD1(v1196) * (HIWORD(v1196) ^ v370))
                                                         ^ (v371 - HIWORD(v1196))
                                                         ^ 0xAB69605E;
                                                    v373 = v371
                                                         ^ ((v372 >> 2) + v1194 * __ROR4__(v372 ^ HIWORD(v1196), 30));
                                                    v351 = HIDWORD(v1196);
                                                    v374 = v372
                                                         ^ (__ROR4__(v373, 25)
                                                          + WORD1(v1196) * __ROR4__(v373 - HIDWORD(v1196), 6));
                                                    v375 = v373 ^ (v1208 * (v374 ^ v1194) + __ROR4__(v374, 9));
                                                    v376 = v374
                                                         ^ (__ROR4__(v375, 25)
                                                          + HIWORD(v1196) * __ROR4__(v375 ^ WORD1(v1196), 27));
                                                    v377 = v375 ^ v376 ^ Size;
                                                    v378 = v376 ^ (v1194 * (__ROR4__(v377, 3) - WORD1(v1196)));
                                                    v379 = v377
                                                         ^ (v1208 * __ROR4__(v378 - HIDWORD(v1196), 1)
                                                          - __ROR4__(v378, 6));
                                                    v380 = v378
                                                         ^ (__ROR4__(v379, 18)
                                                          + HIWORD(v1196) * __ROR4__(v379 - 1419157410, 29));
                                                    v381 = v379
                                                         ^ (v1194 * __ROR4__(v380 - 1419157410, 17) - __ROR4__(v380, 14));
                                                    v382 = v380 ^ (v381 >> 3) ^ (WORD1(v1196) * (v381 ^ v1208));
                                                    v340 = v381
                                                         ^ v357
                                                         ^ __ROR4__(v382, 30)
                                                         ^ (v1208 * __ROR4__(v382 ^ HIDWORD(v1196), 28));
                                                    v341 = v382 ^ v356;
                                                    *((_BYTE *)v354 + 3) = v340;
                                                    *((_BYTE *)v354 + 7) = v382 ^ v356;
                                                    *((_BYTE *)v354 + 2) = __ROR4__(v340, 8);
                                                    *((_BYTE *)v354 + 6) = __ROR4__(v382 ^ v356, 8);
                                                    *((_BYTE *)v354 + 1) = __ROR4__(v340, 16);
                                                    *((_BYTE *)v354 + 5) = __ROR4__(v382 ^ v356, 16);
                                                    *(_BYTE *)v354 = __ROR4__(v340, 24);
                                                    *((_BYTE *)v354 + 4) = __ROR4__(v382 ^ v356, 24);
                                                    v357 = v358;
                                                    v356 = v359;
                                                    v354 += 4;
                                                    ++v1201;
                                                    v352 = Size;
                                                  }
                                                  while ( v1201 < v355 );
                                                  v338 = v1195;
                                                  v79 = v1221;
                                                  v81 = v1211;
                                                  v173 = v1198;
                                                  v172 = (unsigned int *)v1192;
                                                  v337 = v1215;
                                                  v336 = (unsigned __int64)v1202;
                                                }
                                                for ( j = 0; j < v336; ++j )
                                                  v338 ^= *((_BYTE *)v337 + j);
                                                if ( v338 != *(_QWORD *)(v336 + v1204) )
                                                {
                                                  MemoryFree(v337);
                                                  goto LABEL_486;
                                                }
                                                LODWORD(v1208) = 0;
                                                v1192 = (unsigned __int64)v337;
                                                if ( (unsigned int)v336 < 4 )
                                                {
LABEL_488:
                                                  v384 = -1073741762;
LABEL_526:
                                                  v80 = v384 | 0x10000000;
                                                  goto LABEL_396;
                                                }
                                                v384 = RtlULongLongAdd(v337, 4, &v1192);
                                                if ( v384 >= 0 )
                                                {
                                                  v384 = RtlUIntAdd(0, 4, &v1208);
                                                  if ( v384 >= 0 )
                                                  {
                                                    if ( (unsigned int)((_DWORD)v1202 - v1208) < 4 )
                                                      goto LABEL_524;
                                                    HIDWORD(dwBytes) = *(_DWORD *)v1192;
                                                    v384 = RtlULongLongAdd(v1192, 4, &v1192);
                                                    if ( v384 < 0 )
                                                      goto LABEL_525;
                                                    v384 = RtlUIntAdd((unsigned int)v1208, 4, &v1208);
                                                    if ( v384 < 0 )
                                                      goto LABEL_525;
                                                    if ( (unsigned int)((_DWORD)v1202 - v1208) < HIDWORD(dwBytes) )
                                                      goto LABEL_524;
                                                    v384 = RtlUIntAdd((unsigned int)v1208, HIDWORD(dwBytes), &v1208);
                                                    if ( v384 >= 0 )
                                                    {
                                                      if ( (unsigned __int64)v387 + (unsigned int)v1202 >= HIDWORD(dwBytes) + v1192
                                                        && (unsigned __int64)v387
                                                         + (unsigned int)v1202
                                                         - HIDWORD(dwBytes)
                                                         - v1192 < 8 )
                                                      {
                                                        LODWORD(v1196) = *v387;
                                                        v1211 = 0;
                                                        v1209 = 0;
                                                        v1204 = 0;
                                                        LODWORD(v1194) = 0;
                                                        if ( v1192 )
                                                        {
                                                          v384 = RtlULongLongAdd(v1192, HIDWORD(dwBytes), &v1211);
                                                          v1215 = v389;
                                                          v1207 = v390;
                                                          v1199 = v391;
                                                          if ( v384 < 0 )
                                                          {
LABEL_511:
                                                            v397 = v1212;
                                                            goto LABEL_521;
                                                          }
                                                          v392 = (SIZE_T)v388;
                                                          Src = v388;
                                                          if ( v388 < v1211 )
                                                          {
                                                            while ( 1 )
                                                            {
                                                              v384 = RtlULongLongAdd(v392, 4, &v1209);
                                                              if ( v384 < 0 )
                                                                break;
                                                              if ( v1209 > v1211 )
                                                                goto LABEL_510;
                                                              LODWORD(Size) = 0;
                                                              v384 = RtlUIntAdd(4, *(unsigned int *)Src, &Size);
                                                              if ( v384 < 0 )
                                                                goto LABEL_526;
                                                              v384 = RtlULongLongAdd(Src, (unsigned int)Size, &v1204);
                                                              v1215 = v395;
                                                              v1207 = v394;
                                                              v1199 = v393;
                                                              if ( v384 < 0 )
                                                                goto LABEL_511;
                                                              v392 = v1204;
                                                              Src = (void *)v1204;
                                                              v396 = v1211;
                                                              v1215 = v395;
                                                              v1207 = v394;
                                                              v1199 = v393;
                                                              if ( v1204 > (unsigned __int64)v1211 )
                                                                goto LABEL_510;
                                                              LODWORD(v1194) = v1194 + 1;
                                                              if ( v1204 >= (unsigned __int64)v1211 )
                                                              {
                                                                v1215 = v395;
                                                                v1207 = v394;
                                                                v1199 = v393;
                                                                goto LABEL_509;
                                                              }
                                                            }
                                                            v397 = 0;
LABEL_521:
                                                            if ( v384 < 0 || (_DWORD)v1196 == v397 )
                                                              goto LABEL_526;
                                                            goto LABEL_488;
                                                          }
                                                          v396 = v1211;
LABEL_509:
                                                          if ( (LPVOID)v392 != v396 )
                                                          {
LABEL_510:
                                                            v384 = -1073741811;
                                                            goto LABEL_526;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v384 = 0;
                                                          v1215 = v387;
                                                          v1207 = v386;
                                                          v1199 = v385;
                                                        }
                                                        v398 = 0;
                                                        v1209 = 0;
                                                        v399 = HIDWORD(dwBytes);
                                                        if ( HIDWORD(dwBytes) )
                                                        {
                                                          v400 = GetProcessHeap();
                                                          v398 = (unsigned __int16 *)HeapAlloc(
                                                                                       v400,
                                                                                       8u,
                                                                                       HIDWORD(dwBytes));
                                                          v1209 = v398;
                                                          if ( !v398 )
                                                          {
                                                            v384 = -1073741801;
                                                            goto LABEL_526;
                                                          }
                                                          v384 = 0;
                                                          v399 = HIDWORD(dwBytes);
                                                        }
                                                        if ( v1192 )
                                                          memcpy_0(v398, (const void *)v1192, v399);
                                                        v1203 = v1209;
                                                        v397 = v1194;
                                                        v1212 = v1194;
                                                        goto LABEL_521;
                                                      }
LABEL_524:
                                                      v384 = -1073741762;
                                                    }
                                                  }
                                                }
LABEL_525:
                                                v1215 = v387;
                                                v1199 = v385;
                                                v1207 = v386;
                                                goto LABEL_526;
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v298 = 0;
                                }
                              }
                            }
                          }
                          v1198 = v173;
                          v331 = (unsigned int *)v1207;
                          goto LABEL_454;
                        }
                      }
                    }
                  }
                }
              }
              v1199 = v268;
              v275 = GetProcessHeap();
              HeapFree(v275, 0, v1211);
              goto LABEL_352;
            }
LABEL_140:
            lpMem[0] = 0;
            v111 = lpMem[1];
            if ( lpMem[1] )
            {
              v112 = GetProcessHeap();
              HeapFree(v112, 0, v111);
              lpMem[1] = 0;
            }
            v113 = v1203;
            if ( v1203 )
            {
              v114 = GetProcessHeap();
              HeapFree(v114, 0, v113);
            }
            if ( v79 )
            {
              v115 = GetProcessHeap();
              HeapFree(v115, 0, v79);
            }
            if ( v81 )
            {
              v116 = GetProcessHeap();
              HeapFree(v116, 0, v81);
            }
            if ( v80 >= 0 )
            {
              if ( !v75 )
              {
LABEL_1235:
                v889 = v1240;
                v1222 = 0;
                v1243 = (int *)v1248;
                goto LABEL_1593;
              }
              v1219 = 0;
              dword_1800A3D18 = v75;
              ModuleFileNameW = GetModuleFileNameW(&_ImageBase, Filename, 0x104u);
              v118 = 0;
              if ( !ModuleFileNameW || ModuleFileNameW == 260 && GetLastError() == 122 )
              {
LABEL_1203:
                ATL::CHandle::Close((ATL::CHandle *)&v1219);
                *(_OWORD *)v1224 = 0;
                v854 = 0;
                v1202 = 0;
                v855 = GetProcessHeap();
                v856 = HeapAlloc(v855, 8u, 0xA0u);
                v857 = v856;
                if ( !v856 )
                {
                  v857 = 0;
LABEL_1227:
                  v1224[0] = 0;
                  v884 = (void *)v1224[1];
                  if ( v1224[1] )
                  {
                    v885 = GetProcessHeap();
                    HeapFree(v885, 0, v884);
                    v1224[1] = 0;
                  }
                  if ( v854 )
                  {
                    v886 = GetProcessHeap();
                    HeapFree(v886, 0, v854);
                  }
                  if ( v857 )
                  {
                    v887 = GetProcessHeap();
                    HeapFree(v887, 0, v857);
                  }
                  if ( v118 )
                  {
                    v888 = GetProcessHeap();
                    HeapFree(v888, 0, v118);
                  }
                  goto LABEL_1235;
                }
                *v856 = xmmword_1800A39E0;
                v856[1] = xmmword_1800A39F0;
                v856[2] = xmmword_1800A3A00;
                v856[3] = xmmword_1800A3A10;
                v856[4] = xmmword_1800A3A20;
                v856[5] = xmmword_1800A3A30;
                v856[6] = xmmword_1800A3A40;
                v856[7] = xmmword_1800A3A50;
                v856[8] = xmmword_1800A3A60;
                v856[9] = xmmword_1800A3A70;
                v858 = GetProcessHeap();
                v859 = HeapAlloc(v858, 8u, 8u);
                v860 = v859;
                v861 = 0;
                if ( !v859 )
                {
LABEL_1216:
                  v854 = v861;
                  goto LABEL_1227;
                }
                *v859 = qword_1800A3920;
                v1219 = (LPVOID)__rdtsc();
                LODWORD(v1197) = 0;
                v1193 = 0;
                if ( (int)RtlUIntAdd(4, 4, &v1193) < 0 )
                  goto LABEL_1215;
                if ( (int)RtlUIntAdd(0, v1193, &v1197) < 0 )
                {
                  v118 = v860;
                  v854 = v862;
                  goto LABEL_1227;
                }
                v1193 = v864;
                if ( (int)RtlUIntAdd(v863, 160, &v1193) < 0 )
                  goto LABEL_1215;
                v865 = RtlUIntAdd((unsigned int)v1197, v1193, &v1197);
                if ( (v867 | v865) < 0 )
                  goto LABEL_1215;
                v1193 = (unsigned int)v861;
                if ( (int)RtlUIntAdd(v866, 8, &v1193) < 0 )
                  goto LABEL_1215;
                v868 = RtlUIntAdd((unsigned int)v1197, v1193, &v1197);
                if ( (v870 | v868) < 0 )
                  goto LABEL_1215;
                v1193 = (unsigned int)v861;
                if ( (int)RtlUIntAdd(v869, 8, &v1193) < 0
                  || (v871 = RtlUIntAdd((unsigned int)v1197, v1193, &v1197), (v872 | v871) < 0)
                  || (HIDWORD(v1224[0]) = v1197,
                      v873 = v1197,
                      v874 = GetProcessHeap(),
                      v875 = HeapAlloc(v874, 8u, v873),
                      v876 = v875,
                      v861 = 0,
                      !v875) )
                {
LABEL_1215:
                  v118 = v860;
                  goto LABEL_1216;
                }
                v1224[1] = (size_t)v875;
                LODWORD(v1224[0]) = 0;
                LODWORD(v1226) = 0;
                lpModuleName = 0;
                pcchLength = (size_t)v875;
                LODWORD(v1196) = 8;
                v118 = v860;
                v854 = 0;
                if ( (int)RtlULongLongAdd(v875, 4, &v1226) < 0
                  || (unsigned __int64)(v876 + 2) > v1224[1] + HIDWORD(v1224[0]) )
                {
                  goto LABEL_1227;
                }
                *v876 = v877;
                *(_DWORD *)v1226 = v877;
                v879 = v1196;
                v880 = ++LODWORD(v1224[0]);
                LODWORD(v1226) = 0;
                lpModuleName = 0;
                if ( v857 )
                {
                  if ( !v878 )
                    goto LABEL_1226;
                }
                else if ( v878 )
                {
LABEL_1221:
                  v854 = 0;
                  goto LABEL_1227;
                }
                v881 = (unsigned int *)v1224[1];
                if ( v1224[1] )
                {
                  pcchLength = v1224[1];
                  v890 = 0;
                  if ( v880 )
                  {
                    do
                    {
                      v1193 = 0;
                      if ( (int)RtlUIntAdd(4, *v881, &v1193) < 0 || (int)RtlULongLongAdd(v891, v1193, &pcchLength) < 0 )
                        goto LABEL_1226;
                      ++v890;
                      v881 = (unsigned int *)pcchLength;
                    }
                    while ( v890 < v892 );
                  }
                  if ( (int)RtlULongLongAdd(v881, 4, &v1226) < 0
                    || (v895 = v894, (unsigned __int64)v893 + v894 + 4 > v1224[1] + HIDWORD(v1224[0])) )
                  {
LABEL_1226:
                    v854 = v1202;
                    goto LABEL_1227;
                  }
                  *v893 = v894;
                  v883 = 0;
                  if ( v857 )
                  {
                    memcpy_0(v1226, v857, v895);
                    v883 = 0;
                  }
                }
                else
                {
                  v1193 = 0;
                  v882 = RtlUIntAdd(4, v878, &v1193);
                  v861 = 0;
                  if ( v882 < 0 )
                    goto LABEL_1216;
                  if ( (int)RtlUIntAdd(HIDWORD(v1224[0]), v1193, (char *)v1224 + 4) < 0 )
                    goto LABEL_1226;
                }
                v896 = ++LODWORD(v1224[0]);
                LODWORD(v1226) = 0;
                lpModuleName = 0;
                if ( v118 )
                {
                  if ( !v879 )
                    goto LABEL_1226;
                }
                else if ( v879 )
                {
                  goto LABEL_1221;
                }
                v897 = (unsigned int *)v1224[1];
                if ( v1224[1] )
                {
                  pcchLength = v1224[1];
                  v854 = 0;
                  if ( v896 )
                  {
                    do
                    {
                      v1193 = 0;
                      if ( (int)RtlUIntAdd(4, *v897, &v1193) < 0 || (int)RtlULongLongAdd(v898, v1193, &pcchLength) < 0 )
                        goto LABEL_1227;
                      v897 = (unsigned int *)pcchLength;
                    }
                    while ( v900 + 1 < v899 );
                  }
                  v901 = RtlULongLongAdd(v897, 4, &v1226);
                  v861 = 0;
                  if ( v901 < 0 || (unsigned __int64)v902 + v879 + 4 > v1224[1] + HIDWORD(v1224[0]) )
                    goto LABEL_1216;
                  *v902 = v879;
                  if ( v118 )
                  {
                    memcpy_0(v1226, v118, v879);
                    LODWORD(v861) = 0;
                  }
                }
                else
                {
                  v1193 = v883;
                  if ( (int)RtlUIntAdd(4, v879, &v1193) < 0
                    || (int)RtlUIntAdd(HIDWORD(v1224[0]), v1193, (char *)v1224 + 4) < 0 )
                  {
                    goto LABEL_1226;
                  }
                }
                v903 = ++LODWORD(v1224[0]);
                LODWORD(v1226) = 0;
                lpModuleName = 0;
                v904 = (unsigned int *)v1224[1];
                if ( !v1224[1] )
                {
                  v1193 = (unsigned int)v861;
                  if ( (int)RtlUIntAdd(4, 8, &v1193) < 0
                    || (int)RtlUIntAdd(HIDWORD(v1224[0]), v1193, (char *)v1224 + 4) < 0 )
                  {
                    goto LABEL_1226;
                  }
                  ++LODWORD(v1224[0]);
LABEL_1271:
                  v1193 = v906;
                  if ( (int)RtlUIntAdd(v905, v905, &v1193) < 0 )
                    goto LABEL_1226;
                  LODWORD(v1196) = v1193;
                  v1193 = v913;
                  if ( (int)RtlUIntAdd(v912, 8, &v1193) < 0 || (int)RtlUIntAdd(v914, v1193, &v1196) < 0 )
                    goto LABEL_1226;
                  LODWORD(v1216) = (_DWORD)v915;
                  v916 = v1196;
                  HIDWORD(dwBytes) = v1196;
                  v1198 = v915;
                  v1219 = (LPVOID)__rdtsc();
                  v1228 = 8;
                  v917 = RtlUIntAdd(8, HIDWORD(v1224[0]), &v1228);
                  if ( v917 < 0 )
                  {
                    v1211 = v118;
                    v1203 = v857;
                  }
                  else
                  {
                    v921 = (v1228 + 7) & 0xFFFFFFF8;
                    if ( v921 < v1228 )
                      goto LABEL_1226;
                    v1228 = (v1228 + 7) & 0xFFFFFFF8;
                    v922 = v921;
                    v923 = GetProcessHeap();
                    v924 = (char *)HeapAlloc(v923, 8u, v922);
                    v925 = v924;
                    LODWORD(v920) = 0;
                    if ( !v924 )
                    {
LABEL_1575:
                      if ( v1200 >= (int)v920 )
                      {
                        v854 = v1202;
                        if ( (_DWORD)v1216 )
                        {
                          if ( v1202 )
                          {
                            v1210 = (SIZE_T)v1202;
                            if ( (int)RtlULongLongAdd(v1202, 4, &v1210) >= 0 )
                            {
                              v1169 = (_DWORD *)v1210;
                              if ( *v854 == (_DWORD)v1168 )
                                v1169 = v1168;
                              if ( *v854 == v1167 && *v1169 >= (int)v1168 && v1166 > 1 )
                              {
                                v1170 = (unsigned __int64)v854;
                                v1192 = (unsigned __int64)v854;
                                v1171 = v1167;
                                while ( (int)RtlULongLongAdd(v1170, v1171, &v1192) >= 0
                                     && (int)RtlULongLongAdd(v1192, v1172, &v1192) >= 0 )
                                {
                                  v1170 = v1192;
                                  if ( v1173 != -1 )
                                  {
                                    RtlULongLongAdd(v1192, v1171, &v1192);
                                    goto LABEL_1227;
                                  }
                                }
                              }
                            }
                          }
                        }
                        goto LABEL_1227;
                      }
                      goto LABEL_1226;
                    }
                    v1203 = v857;
                    v1211 = v118;
                    HIDWORD(dwBytes) = v916;
                    v1201 = (size_t)v924;
                    *(_DWORD *)v924 = v1224[0];
                    LODWORD(v1194) = RtlULongLongAdd(v924, 4, &v1201);
                    if ( (v1194 & 0x80000000) != 0LL
                      || (v927 = v1201,
                          *(_DWORD *)v1201 = HIDWORD(v1224[0]),
                          LODWORD(v1194) = RtlULongLongAdd(v927, v926, &v1201),
                          (v1194 & 0x80000000) != 0LL) )
                    {
                      v1203 = v857;
                      v1211 = v118;
                      HIDWORD(dwBytes) = v916;
                      v928 = GetProcessHeap();
                      HeapFree(v928, 0, v925);
                      v918 = v1198;
                      v919 = (unsigned int)v1198;
                    }
                    else
                    {
                      *(_QWORD *)&v925[v1228 - 8] = v1219;
                      memcpy_0((void *)v1201, (const void *)v1224[1], HIDWORD(v1224[0]));
                      v918 = v925;
                      v1198 = v925;
                      v919 = v1228;
                    }
                    v917 = v1194;
                    v920 = 0;
                  }
                  v929 = v920;
                  v1221 = v920;
                  v930 = v920;
                  v1215 = v920;
                  v1204 = (SIZE_T)v920;
                  v1196 = (SIZE_T)v920;
                  v931 = v917 | 0x10000000;
                  if ( v931 < 0 )
                  {
                    v1200 = v931;
                    goto LABEL_1549;
                  }
                  if ( !v918 )
                    goto LABEL_1226;
                  Src = (void *)v919;
                  if ( !v919 || (v1201 = v919 + 8LL, v932 = MemoryAlloc(v1201), (v1222 = v932) == 0) )
                  {
                    v1200 = -805306367;
                    v984 = v1198;
                    v1035 = v930;
                    goto LABEL_1552;
                  }
                  v1192 = 0;
                  v933 = 0;
                  v1195 = 0;
                  v934 = 0;
                  v935 = (unsigned __int64)Src;
                  if ( Src )
                  {
                    do
                      v933 ^= *((_BYTE *)v1198 + v934++);
                    while ( v934 < (unsigned __int64)Src );
                    v1195 = v933;
                  }
                  v1213 = 0xC81ECB17B1B54A58uLL;
                  v936 = (unsigned __int8 *)v1198;
                  v1210 = (SIZE_T)v1198;
                  pcchLength = (size_t)v932;
                  v937 = (unsigned __int8)Src & 7;
                  if ( ((unsigned __int8)Src & 7) != 0 )
                  {
                    v1212 = 0;
                    LODWORD(v1197) = 0;
                    v938 = 0;
                    v939 = 0;
                    v940 = 0;
                    do
                    {
                      v941 = *v936++;
                      v1193 = 8 * v938;
                      if ( v938 >= 4 )
                        v939 |= v941 << (56 - v1193);
                      else
                        v940 |= v941 << (24 - v1193);
                      ++v938;
                    }
                    while ( (int)v938 < v937 );
                    LODWORD(v1197) = v940;
                    v1212 = v939;
                    v1210 = (SIZE_T)v936;
                    v1211 = v118;
                    v1203 = v857;
                    v933 = v1195;
                    v929 = v930;
                    v942 = v1197 ^ 0xB17A307A;
                    v943 = v939 ^ 0x42F6B18D;
                    v944 = v1197 ^ 0xB17A307A;
                    v945 = v939 ^ 0x42F6B18D;
                    LODWORD(v1199) = 0;
                    if ( ((unsigned __int8)Src & 7) != 0 )
                    {
                      v946 = (_BYTE *)pcchLength;
                      v947 = (unsigned int)v1199;
                      do
                      {
                        v1219 = v946 + 1;
                        if ( v947 >= 4 )
                        {
                          v945 = __ROR4__(v945, 24);
                          v948 = v945;
                        }
                        else
                        {
                          v944 = __ROR4__(v944, 24);
                          v948 = v944;
                        }
                        *v946 = v948;
                        ++v947;
                        v946 = v1219;
                      }
                      while ( (int)v947 < v937 );
                      pcchLength = (size_t)v1219;
                      v930 = v1215;
                    }
                    if ( (unsigned int)v937 <= 4 )
                    {
                      v949 = 0;
                      if ( (unsigned int)v937 < 4 )
                        v942 = v942 >> (8 * (4 - v937)) << (8 * (4 - v937));
                    }
                    else
                    {
                      v949 = v943 >> (8 * (8 - v937)) << (8 * (8 - v937));
                    }
                  }
                  else
                  {
                    v942 = 0;
                    v949 = -1;
                    LODWORD(v1197) = 0;
                    v1212 = 0;
                  }
                  if ( v935 >> 3 )
                  {
                    v1209 = 0;
                    LODWORD(v1194) = 19032;
                    LODWORD(v1199) = WORD1(v1213);
                    v950 = WORD2(v1213);
                    v951 = (unsigned __int8 *)v1210;
                    v952 = (_BYTE *)pcchLength;
                    v953 = v1212;
                    v954 = v1197;
                    v955 = v935 >> 3;
                    do
                    {
                      v956 = v951[3] | ((v951[2] | (((*v951 << 8) | v951[1]) << 8)) << 8);
                      v957 = v951[7] | ((v951[6] | ((v951[5] | (v951[4] << 8)) << 8)) << 8);
                      v951 += 8;
                      v958 = v942 ^ v956 ^ ((v949 ^ v957) - v1194);
                      v959 = HIDWORD(v1213) ^ v958;
                      v960 = v949 ^ v957 ^ (__ROR4__(HIDWORD(v1213) ^ v958, 7) + WORD1(v1213) * __ROR4__(v958, 15));
                      v961 = v959 ^ (v950 * __ROR4__(v960 - 1313519016, 9) - __ROR4__(v960, 10));
                      v962 = v960 ^ (__ROR4__(v961, 27) + HIWORD(v1213) * __ROR4__(v961 ^ v950, 28));
                      v963 = v961 ^ (HIDWORD(v1213) - (v962 ^ 0xB1B54A58));
                      v964 = v962 ^ (WORD1(v1213) * (v963 - v1194) - (v963 >> 6));
                      v965 = v963 ^ (v1194 * (v950 ^ __ROR4__(v964, 15)));
                      v966 = v964 ^ (v950 * (HIWORD(v1213) + __ROR4__(~v965, 3)));
                      v967 = v965 ^ (v966 - HIDWORD(v1213) - v1194);
                      v968 = v966 ^ ((_DWORD)v1199 * (v967 ^ HIWORD(v1213))) ^ __ROR4__(v967, 10);
                      v969 = v967 ^ __ROR4__(v968, 3) ^ (v950 * __ROR4__(v1194 ^ v968, 26));
                      v970 = v968 ^ (v1194 * (__ROR4__(v969, 15) - HIWORD(v1213)));
                      v971 = v969
                           ^ (v1194 * (v970 ^ HIWORD(v1213)))
                           ^ ((v970 ^ (v970 >> 14)) >> 1)
                           ^ (v1194 * ((8 * (v970 - v950)) | ((v970 - v950) >> 29)));
                      v972 = v970 ^ (WORD1(v1213) * (v971 - v950) - (v971 >> 13));
                      v973 = v971 ^ __ROR4__(v972, 11) ^ (v950 * __ROR4__(-1313519016 - v972, 9));
                      v974 = v972 ^ (v973 - HIWORD(v1213) + 1313519016);
                      v975 = v973 ^ (v1194 * (v974 ^ WORD1(v1213)) - __ROR4__(v974, 7));
                      v976 = v974 ^ (WORD1(v1213) * __ROR4__(v975 ^ HIWORD(v1213), 28) - __ROR4__(v975, 16));
                      v977 = v975 ^ (__ROR4__(v976, 4) + v950 * __ROR4__(-1313519016 - v976, 10));
                      v978 = v976 ^ __ROR4__(v977, 9) ^ (HIWORD(v1213) * __ROR4__(v977 + 1313519016, 4));
                      v979 = v977 ^ (v1194 * __ROR4__(HIDWORD(v1213) ^ v978, 24) - __ROR4__(v978, 30));
                      v980 = v978 ^ (WORD1(v1213) * __ROR4__(HIDWORD(v1213) - v979, 11) - __ROR4__(v979, 12));
                      v981 = v954 ^ v979 ^ (v980 >> 8) ^ (v950 * (v980 ^ WORD1(v1213)));
                      LODWORD(v1207) = v981;
                      v949 = v980
                           ^ v953
                           ^ v979
                           ^ (v980 >> 8)
                           ^ (v950 * (v980 ^ WORD1(v1213)))
                           ^ HIDWORD(v1213)
                           ^ 0xB1B54A58;
                      v942 = v981;
                      v952[3] = v981;
                      v952[7] = v949;
                      v952[2] = __ROR4__(v981, 8);
                      v952[6] = __ROR4__(v949, 8);
                      v952[1] = __ROR4__(v981, 16);
                      v952[5] = __ROR4__(v949, 16);
                      *v952 = __ROR4__(v981, 24);
                      v952[4] = __ROR4__(v949, 24);
                      v954 = v956;
                      v953 = v957;
                      v952 += 8;
                      v1209 = (unsigned __int16 *)((char *)v1209 + 1);
                    }
                    while ( (unsigned __int64)v1209 < v955 );
                    v933 = v1195;
                    v80 = dwBytes;
                    v857 = v1203;
                    v118 = v1211;
                    v930 = v1215;
                    v929 = (unsigned int *)v1215;
                    v935 = (unsigned __int64)Src;
                  }
                  *(_QWORD *)((char *)v1222 + v935) = v933;
                  v982 = GetProcessHeap();
                  v983 = HeapAlloc(v982, 8u, 0x30u);
                  v1203 = v983;
                  if ( !v983 )
                  {
                    LODWORD(v1197) = -1073741801;
                    v984 = v1198;
                    goto LABEL_1329;
                  }
                  v985 = v1201;
                  *v983 = v1201;
                  v986 = GetProcessHeap();
                  v987 = HeapAlloc(v986, 8u, v985);
                  v984 = v1198;
                  v988 = HIDWORD(dwBytes);
                  if ( v987 )
                  {
                    *((_QWORD *)v1203 + 1) = v987;
                    memcpy_0(v987, v1222, (unsigned int)v1201);
                    *((_DWORD *)v1203 + 4) = 160;
                    v989 = GetProcessHeap();
                    v990 = HeapAlloc(v989, 8u, 0xA0u);
                    v991 = v1203;
                    if ( v990 )
                    {
                      *((_QWORD *)v1203 + 3) = v990;
                      *v990 = xmmword_1800A3930;
                      v990[1] = xmmword_1800A3940;
                      v990[2] = xmmword_1800A3950;
                      v990[3] = xmmword_1800A3960;
                      v990[4] = xmmword_1800A3970;
                      v990[5] = xmmword_1800A3980;
                      v990[6] = xmmword_1800A3990;
                      v990[7] = xmmword_1800A39A0;
                      v990[8] = xmmword_1800A39B0;
                      v990[9] = xmmword_1800A39C0;
                      v991[8] = 8;
                      v992 = GetProcessHeap();
                      v993 = HeapAlloc(v992, 8u, 8u);
                      if ( v993 )
                      {
                        v999 = v1203;
                        *((_QWORD *)v1203 + 5) = v993;
                        *v993 = qword_1800A39D0;
                        v1192 = (unsigned __int64)v999;
                        LODWORD(v1197) = 0;
                        v1198 = v984;
                        goto LABEL_1328;
                      }
                      v991 = v1203;
                    }
                    v1203 = v991;
                    v988 = HIDWORD(dwBytes);
                  }
                  LODWORD(v1197) = -1073741801;
                  HIDWORD(dwBytes) = v988;
                  v1198 = v984;
                  v994 = v1203;
                  v1219 = (LPVOID)*((_QWORD *)v1203 + 1);
                  if ( v1219 )
                  {
                    v995 = GetProcessHeap();
                    HeapFree(v995, 0, v1219);
                    v994 = v1203;
                    *((_QWORD *)v1203 + 1) = 0;
                  }
                  v1219 = (LPVOID)*((_QWORD *)v994 + 3);
                  if ( v1219 )
                  {
                    v996 = GetProcessHeap();
                    HeapFree(v996, 0, v1219);
                    v994 = v1203;
                    *((_QWORD *)v1203 + 3) = 0;
                  }
                  v1219 = (LPVOID)*((_QWORD *)v994 + 5);
                  if ( v1219 )
                  {
                    v997 = GetProcessHeap();
                    HeapFree(v997, 0, v1219);
                    *((_QWORD *)v1203 + 5) = 0;
                  }
                  v998 = GetProcessHeap();
                  HeapFree(v998, 0, v1203);
                  if ( (v1197 & 0x80000000) != 0LL )
                  {
LABEL_1329:
                    v1000 = GetProcessHeap();
                    HeapFree(v1000, 0, v1222);
                    v1001 = v1192;
                    LODWORD(v920) = 0;
                    if ( v1192 )
                    {
                      v1219 = *(LPVOID *)(v1192 + 8);
                      if ( v1219 )
                      {
                        v1002 = GetProcessHeap();
                        HeapFree(v1002, 0, v1219);
                        v1001 = v1192;
                        *(_QWORD *)(v1192 + 8) = 0;
                      }
                      v1219 = *(LPVOID *)(v1001 + 24);
                      if ( v1219 )
                      {
                        v1003 = GetProcessHeap();
                        HeapFree(v1003, 0, v1219);
                        v1001 = v1192;
                        *(_QWORD *)(v1192 + 24) = 0;
                      }
                      v1219 = *(LPVOID *)(v1001 + 40);
                      if ( v1219 )
                      {
                        v1004 = GetProcessHeap();
                        HeapFree(v1004, 0, v1219);
                        *(_QWORD *)(v1192 + 40) = 0;
                      }
                      v1005 = GetProcessHeap();
                      HeapFree(v1005, 0, (LPVOID)v1192);
                      LODWORD(v920) = 0;
                    }
                    if ( (v1197 & 0x80000000) != 0LL )
                    {
                      v1200 = v1197 | 0x10000000;
                      v1035 = (void *)v1196;
                      goto LABEL_1551;
                    }
                    v1193 = 0;
                    LODWORD(v1208) = 4;
                    v1200 = RtlUIntAdd(4, *v929, &v1208);
                    if ( v1200 < 0
                      || (v1200 = RtlUIntAdd((unsigned int)v1208, v1006, &v1208), v1200 < 0)
                      || (v1210 = (SIZE_T)(v929 + 4), v1200 = RtlUIntAdd((unsigned int)v1208, v929[4], &v1208),
                                                      v1200 < 0)
                      || (v1200 = RtlUIntAdd((unsigned int)v1208, v1007, &v1208), v1200 < 0)
                      || (v1209 = (unsigned __int16 *)(v929 + 8),
                          v1200 = RtlUIntAdd((unsigned int)v1208, v929[8], &v1208),
                          v1200 < 0) )
                    {
                      v1198 = v984;
                      v1011 = HIDWORD(dwBytes);
                    }
                    else
                    {
                      v1008 = v1208;
                      v1009 = GetProcessHeap();
                      v1010 = HeapAlloc(v1009, 8u, v1008);
                      v1192 = (unsigned __int64)v1010;
                      LODWORD(v920) = 0;
                      if ( !v1010 )
                      {
                        v1200 = -805306345;
LABEL_1345:
                        v930 = v1215;
LABEL_1549:
                        v1035 = v930;
                        goto LABEL_1550;
                      }
                      v1011 = HIDWORD(dwBytes);
                      v1198 = v984;
                      v1203 = v1010;
                      *v1010 = *v929;
                      v1200 = RtlULongLongAdd(v1010, 4, &v1203);
                      if ( v1200 < 0 )
                      {
                        v1192 = v1012;
                      }
                      else
                      {
                        memcpy_0(v1203, *((const void **)v929 + 1), *v929);
                        v1200 = RtlULongLongAdd(v1203, *v929, &v1203);
                        if ( v1200 >= 0 )
                        {
                          v1013 = v1203;
                          *(_DWORD *)v1203 = *(_DWORD *)v1210;
                          v1200 = RtlULongLongAdd(v1013, 4, &v1203);
                          if ( v1200 >= 0 )
                          {
                            memcpy_0(v1203, *((const void **)v929 + 3), *v1014);
                            v1200 = RtlULongLongAdd(v1203, *(unsigned int *)v1210, &v1203);
                            if ( v1200 >= 0 )
                            {
                              v1015 = v1203;
                              *(_DWORD *)v1203 = *(_DWORD *)v1209;
                              v1200 = RtlULongLongAdd(v1015, 4, &v1203);
                              if ( v1200 >= 0 )
                              {
                                memcpy_0(v1203, *((const void **)v929 + 5), *v1016);
                                v1017 = RtlULongLongAdd(v1203, *(unsigned int *)v1209, &v1203);
                                v1200 = v1017;
                                LODWORD(v920) = 0;
                                if ( v1017 >= 0 )
                                {
                                  v1221 = (LPVOID)v1192;
                                  v1193 = v1208;
LABEL_1358:
                                  v1019 = v1017 | 0x10000000;
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1233 = 8;
                                  v1020 = RtlUIntAdd(8, v1011, &v1233);
                                  v1019 = v1021 | v1020;
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1022 = (v1233 + 7) & 0xFFFFFFF8;
                                  if ( (unsigned int)v1022 < v1233 )
                                  {
                                    v1019 = -1073741675;
LABEL_1362:
                                    v1200 = v1019;
                                    goto LABEL_1345;
                                  }
                                  v1239 = (v1233 + 7) & 0xFFFFFFF8;
                                  v1019 = RtlUIntAdd(v1022, 8, &v1239);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1203 = v857;
                                  v1211 = v118;
                                  v1198 = v984;
                                  Size = (SIZE_T)v929;
                                  LODWORD(v1194) = (_DWORD)v920;
                                  v1023 = v1224[1];
                                  if ( !v1224[1] )
                                    goto LABEL_1365;
                                  Size = (SIZE_T)v929;
                                  v1198 = v984;
                                  v1211 = v118;
                                  v1203 = v857;
                                  if ( LODWORD(v1224[0]) <= 1 )
                                    goto LABEL_1365;
                                  v1192 = v1224[1];
                                  do
                                  {
                                    v1019 = RtlULongLongAdd(v1023, 4, &v1192);
                                    if ( v1019 < 0 )
                                    {
LABEL_1386:
                                      LODWORD(v920) = 0;
                                      goto LABEL_1362;
                                    }
                                    v1019 = RtlULongLongAdd(v1192, v1024, &v1192);
                                    LODWORD(v920) = 0;
                                    if ( v1019 < 0 )
                                      goto LABEL_1362;
                                    v1023 = v1192;
                                  }
                                  while ( v1025 == -1 );
                                  v1026 = *(_DWORD *)v1192;
                                  v1019 = RtlULongLongAdd(v1192, 4, &v1192);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1027 = v1224[1];
                                  if ( !v1224[1] || LODWORD(v1224[0]) <= 2 )
                                  {
LABEL_1365:
                                    v1019 = -1073741811;
                                    goto LABEL_1362;
                                  }
                                  v1192 = v1224[1];
                                  do
                                  {
                                    v1019 = RtlULongLongAdd(v1027, 4, &v1192);
                                    if ( v1019 < 0 )
                                      goto LABEL_1386;
                                    v1019 = RtlULongLongAdd(v1192, v1028, &v1192);
                                    LODWORD(v920) = 0;
                                    if ( v1019 < 0 )
                                      goto LABEL_1362;
                                    v1027 = v1192;
                                  }
                                  while ( (unsigned int)(v1029 + 1) < 2 );
                                  v1019 = RtlULongLongAdd(v1192, 4, &v1192);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  LODWORD(v1194) = (_DWORD)v920;
                                  LODWORD(v1197) = 4;
                                  v1019 = RtlUIntAdd((unsigned int)((_DWORD)v920 + 4), v1239, &v1197);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1019 = RtlUIntAdd((unsigned int)v1197, v1030, &v1197);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1019 = RtlUIntAdd((unsigned int)v1197, v1026, &v1197);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1019 = RtlUIntAdd((unsigned int)v1197, (unsigned int)((_DWORD)v920 + 4), &v1197);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  v1019 = RtlUIntAdd((unsigned int)v1197, v1031, &v1197);
                                  if ( v1019 < 0 )
                                    goto LABEL_1362;
                                  LODWORD(v1194) = v1197;
                                  if ( (unsigned int)v1197 > 0x400000 )
                                  {
                                    v1019 = -2147418113;
                                    goto LABEL_1362;
                                  }
                                  v1032 = v1197;
                                  v1033 = GetProcessHeap();
                                  v1034 = HeapAlloc(v1033, 8u, v1032);
                                  v930 = v1034;
                                  LODWORD(v920) = 0;
                                  if ( !v1034 )
                                  {
                                    v930 = 0;
                                    goto LABEL_1389;
                                  }
                                  v1252 = 0;
                                  v1253 = 0;
                                  hModule = 0;
                                  if ( !v1221 )
                                  {
                                    v1200 = -2147024809;
                                    goto LABEL_1390;
                                  }
                                  *(_QWORD *)&v1252 = v1221;
                                  LODWORD(v1253) = v1193;
                                  *((_QWORD *)&v1252 + 1) = v1034;
                                  *(_QWORD *)((char *)&v1253 + 4) = (unsigned int)v1194;
                                  if ( GetModuleHandleExW(1u, L"ntdll.dll", &hModule)
                                    && (v1038 = GetProcAddress(hModule, "NtQuerySystemInformation")) != 0 )
                                  {
                                    v1036 = ((__int64 (__fastcall *)(__int64, __int128 *))v1038)(134, &v1252)
                                          | 0x10000000;
                                    if ( v1036 >= 0 )
                                    {
                                      v1039 = DWORD1(v1253);
                                      LODWORD(v920) = 0;
                                      goto LABEL_1406;
                                    }
                                    LODWORD(v920) = 0;
                                  }
                                  else
                                  {
                                    v1036 = GetLastError();
                                    LODWORD(v920) = 0;
                                    v1037 = v1036 < 0;
                                    if ( v1036 > 0 )
                                    {
                                      v1036 = (unsigned __int16)v1036 | 0x80070000;
                                      v1037 = v1036 < 0;
                                    }
                                    if ( !v1037 )
                                    {
                                      v1200 = -2147467259;
                                      goto LABEL_1390;
                                    }
                                  }
                                  if ( v1036 == -805306333 )
                                  {
                                    v1200 = -2147024774;
                                    goto LABEL_1390;
                                  }
                                  if ( v1036 < 0 )
                                  {
                                    v1200 = v1036;
                                    goto LABEL_1390;
                                  }
                                  v1039 = v1194;
LABEL_1406:
                                  HIDWORD(dwBytes) = 0;
                                  v1192 = (unsigned __int64)v930;
                                  if ( v1039 < 4 )
                                  {
LABEL_1407:
                                    v1200 = -805306306;
                                    goto LABEL_1390;
                                  }
                                  v1193 = *v930;
                                  v1040 = RtlULongLongAdd(v930, 4, &v1192);
                                  if ( v1040 >= 0 )
                                  {
                                    v1040 = RtlUIntAdd(0, 4, (char *)&dwBytes + 4);
                                    if ( v1040 >= 0 )
                                    {
                                      if ( v1041 - HIDWORD(dwBytes) < (unsigned int)v1042 )
                                        goto LABEL_1407;
                                      v1209 = (unsigned __int16 *)v1192;
                                      v1210 = v1042;
                                      v1040 = RtlULongLongAdd(v1192, (unsigned int)v1042, &v1192);
                                      if ( v1040 >= 0 )
                                      {
                                        v1040 = RtlUIntAdd(HIDWORD(dwBytes), v1043, (char *)&dwBytes + 4);
                                        if ( v1040 >= 0 )
                                        {
                                          if ( (unsigned int)(v1044 - HIDWORD(dwBytes)) < 4 )
                                            goto LABEL_1407;
                                          LODWORD(v1199) = *(_DWORD *)v1192;
                                          v1040 = RtlULongLongAdd(v1192, 4, &v1192);
                                          if ( v1040 >= 0 )
                                          {
                                            v1040 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                            if ( v1040 >= 0 )
                                            {
                                              if ( v1045 - HIDWORD(dwBytes) < (unsigned int)v1046 )
                                              {
LABEL_1417:
                                                v1200 = -805306306;
                                                v1035 = (void *)v1196;
                                                LODWORD(v920) = 0;
LABEL_1550:
                                                v984 = v1198;
LABEL_1551:
                                                if ( !v984 )
                                                {
LABEL_1553:
                                                  if ( v929 )
                                                  {
                                                    v1147 = (void *)*((_QWORD *)v929 + 1);
                                                    if ( v1147 )
                                                    {
                                                      v1148 = GetProcessHeap();
                                                      HeapFree(v1148, 0, v1147);
                                                      *((_QWORD *)v929 + 1) = 0;
                                                    }
                                                    v1149 = (void *)*((_QWORD *)v929 + 3);
                                                    if ( v1149 )
                                                    {
                                                      v1150 = GetProcessHeap();
                                                      HeapFree(v1150, 0, v1149);
                                                      *((_QWORD *)v929 + 3) = 0;
                                                    }
                                                    v1151 = (void *)*((_QWORD *)v929 + 5);
                                                    if ( v1151 )
                                                    {
                                                      v1152 = GetProcessHeap();
                                                      HeapFree(v1152, 0, v1151);
                                                      *((_QWORD *)v929 + 5) = 0;
                                                    }
                                                    v1153 = GetProcessHeap();
                                                    HeapFree(v1153, 0, v929);
                                                    LODWORD(v920) = 0;
                                                  }
                                                  v1154 = v1221;
                                                  if ( v1221 )
                                                  {
                                                    v1155 = GetProcessHeap();
                                                    HeapFree(v1155, 0, v1154);
                                                    LODWORD(v920) = 0;
                                                  }
                                                  if ( v930 )
                                                  {
                                                    v1156 = GetProcessHeap();
                                                    HeapFree(v1156, 0, v930);
                                                    LODWORD(v920) = 0;
                                                  }
                                                  v1157 = (_QWORD *)v1204;
                                                  if ( v1204 )
                                                  {
                                                    v1158 = *(void **)(v1204 + 8);
                                                    if ( v1158 )
                                                    {
                                                      v1159 = GetProcessHeap();
                                                      HeapFree(v1159, 0, v1158);
                                                      v1157[1] = 0;
                                                    }
                                                    v1160 = (void *)v1157[3];
                                                    if ( v1160 )
                                                    {
                                                      v1161 = GetProcessHeap();
                                                      HeapFree(v1161, 0, v1160);
                                                      v1157[3] = 0;
                                                    }
                                                    v1162 = (void *)v1157[5];
                                                    if ( v1162 )
                                                    {
                                                      v1163 = GetProcessHeap();
                                                      HeapFree(v1163, 0, v1162);
                                                      v1157[5] = 0;
                                                    }
                                                    v1164 = GetProcessHeap();
                                                    HeapFree(v1164, 0, v1157);
                                                    LODWORD(v920) = 0;
                                                  }
                                                  if ( v1035 )
                                                  {
                                                    v1165 = GetProcessHeap();
                                                    HeapFree(v1165, 0, v1035);
                                                    LODWORD(v920) = 0;
                                                  }
                                                  goto LABEL_1575;
                                                }
LABEL_1552:
                                                v1146 = GetProcessHeap();
                                                HeapFree(v1146, 0, v984);
                                                LODWORD(v920) = 0;
                                                goto LABEL_1553;
                                              }
                                              Src = (void *)v1192;
                                              pcchLength = v1046;
                                              v1040 = RtlULongLongAdd(v1192, v1046, &v1192);
                                              if ( v1040 >= 0 )
                                              {
                                                v1040 = RtlUIntAdd(HIDWORD(dwBytes), v1047, (char *)&dwBytes + 4);
                                                if ( v1040 >= 0 )
                                                {
                                                  if ( (unsigned int)(v1048 - HIDWORD(dwBytes)) < 4 )
                                                    goto LABEL_1417;
                                                  LODWORD(v1207) = *(_DWORD *)v1192;
                                                  v1040 = RtlULongLongAdd(v1192, 4, &v1192);
                                                  if ( v1040 >= 0 )
                                                  {
                                                    v1040 = RtlUIntAdd(HIDWORD(dwBytes), 4, (char *)&dwBytes + 4);
                                                    if ( v1040 >= 0 )
                                                    {
                                                      if ( v1049 - HIDWORD(dwBytes) < v1050 )
                                                        goto LABEL_1417;
                                                      v1040 = RtlUIntAdd(HIDWORD(dwBytes), v1050, (char *)&dwBytes + 4);
                                                      if ( v1040 >= 0 )
                                                      {
                                                        if ( v1051 != HIDWORD(dwBytes)
                                                          || v1052 + v1053 + v1193 + 12LL != v1051 )
                                                        {
                                                          goto LABEL_1417;
                                                        }
                                                        v1054 = GetProcessHeap();
                                                        v1055 = HeapAlloc(v1054, 8u, 0x30u);
                                                        v1056 = (SIZE_T)v1055;
                                                        v1204 = (SIZE_T)v1055;
                                                        LODWORD(v920) = 0;
                                                        if ( !v1055 )
                                                        {
                                                          v1204 = 0;
LABEL_1389:
                                                          v1200 = -805306345;
LABEL_1390:
                                                          v1035 = (void *)v1196;
                                                          goto LABEL_1550;
                                                        }
                                                        v1203 = v857;
                                                        v1211 = v118;
                                                        v1198 = v984;
                                                        Size = (SIZE_T)v929;
                                                        v1194 = 0;
                                                        if ( v1209 )
                                                        {
                                                          *(_DWORD *)v1055 = v1193;
                                                          v1057 = GetProcessHeap();
                                                          v1058 = HeapAlloc(v1057, 8u, v1210);
                                                          v1059 = (LPVOID *)v1204;
                                                          if ( !v1058 )
                                                          {
LABEL_1440:
                                                            LODWORD(v1197) = -1073741801;
                                                            v1215 = v930;
                                                            v1219 = v1059[1];
                                                            if ( v1219 )
                                                            {
                                                              v1065 = GetProcessHeap();
                                                              HeapFree(v1065, 0, v1219);
                                                              v1059 = (LPVOID *)v1204;
                                                              *(_QWORD *)(v1204 + 8) = 0;
                                                            }
                                                            v1219 = v1059[3];
                                                            if ( v1219 )
                                                            {
                                                              v1066 = GetProcessHeap();
                                                              HeapFree(v1066, 0, v1219);
                                                              v1059 = (LPVOID *)v1204;
                                                              *(_QWORD *)(v1204 + 24) = 0;
                                                            }
                                                            v1219 = v1059[5];
                                                            if ( v1219 )
                                                            {
                                                              v1067 = GetProcessHeap();
                                                              HeapFree(v1067, 0, v1219);
                                                              *(_QWORD *)(v1204 + 40) = 0;
                                                            }
                                                            v1068 = GetProcessHeap();
                                                            HeapFree(v1068, 0, (LPVOID)v1204);
                                                            v1069 = (LPVOID *)v1194;
                                                            LODWORD(v920) = 0;
                                                            goto LABEL_1450;
                                                          }
                                                          *(_QWORD *)(v1204 + 8) = v1058;
                                                          LODWORD(v1197) = 0;
                                                          memcpy_0(v1058, v1209, v1210);
                                                          v1056 = v1204;
                                                          LODWORD(v920) = 0;
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)v1055 = 0;
                                                          v1055[1] = 0;
                                                          LODWORD(v1197) = 0;
                                                        }
                                                        if ( Src )
                                                        {
                                                          *(_DWORD *)(v1056 + 16) = (_DWORD)v1199;
                                                          v1060 = GetProcessHeap();
                                                          v1061 = HeapAlloc(v1060, 8u, pcchLength);
                                                          v1059 = (LPVOID *)v1204;
                                                          if ( !v1061 )
                                                          {
LABEL_1439:
                                                            v1203 = v857;
                                                            v1211 = v118;
                                                            v1198 = v984;
                                                            Size = (SIZE_T)v929;
                                                            v1204 = (SIZE_T)v1059;
                                                            goto LABEL_1440;
                                                          }
                                                          *(_QWORD *)(v1204 + 24) = v1061;
                                                          LODWORD(v1197) = 0;
                                                          memcpy_0(v1061, Src, pcchLength);
                                                          v1056 = v1204;
                                                          LODWORD(v920) = 0;
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)(v1056 + 16) = 0;
                                                          *(_QWORD *)(v1056 + 24) = 0;
                                                        }
                                                        if ( v1192 )
                                                        {
                                                          v1062 = (unsigned int)v1207;
                                                          *(_DWORD *)(v1056 + 32) = (_DWORD)v1207;
                                                          v1210 = v1062;
                                                          v1063 = GetProcessHeap();
                                                          v1064 = HeapAlloc(v1063, 8u, v1210);
                                                          v1059 = (LPVOID *)v1204;
                                                          if ( !v1064 )
                                                            goto LABEL_1439;
                                                          *(_QWORD *)(v1204 + 40) = v1064;
                                                          LODWORD(v1197) = 0;
                                                          memcpy_0(v1064, (const void *)v1192, v1210);
                                                          v1056 = v1204;
                                                          LODWORD(v920) = 0;
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)(v1056 + 32) = 0;
                                                          *(_QWORD *)(v1056 + 40) = 0;
                                                        }
                                                        v1069 = (LPVOID *)v1056;
                                                        v1194 = v1056;
                                                        v1215 = v930;
                                                        Size = (SIZE_T)v929;
                                                        v1198 = v984;
                                                        v1211 = v118;
                                                        v1203 = v857;
LABEL_1450:
                                                        v1040 = v1197;
                                                        if ( (v1197 & 0x80000000) != 0LL )
                                                        {
                                                          v1070 = 0;
                                                          v1204 = 0;
                                                          if ( v1069 )
                                                          {
                                                            v1219 = v1069[1];
                                                            if ( v1219 )
                                                            {
                                                              v1071 = GetProcessHeap();
                                                              HeapFree(v1071, 0, v1219);
                                                              v1069 = (LPVOID *)v1194;
                                                              *(_QWORD *)(v1194 + 8) = 0;
                                                            }
                                                            v1219 = v1069[3];
                                                            if ( v1219 )
                                                            {
                                                              v1072 = GetProcessHeap();
                                                              HeapFree(v1072, 0, v1219);
                                                              v1069 = (LPVOID *)v1194;
                                                              *(_QWORD *)(v1194 + 24) = 0;
                                                            }
                                                            v1219 = v1069[5];
                                                            if ( v1219 )
                                                            {
                                                              v1073 = GetProcessHeap();
                                                              HeapFree(v1073, 0, v1219);
                                                              *(_QWORD *)(v1194 + 40) = 0;
                                                            }
                                                            v1074 = GetProcessHeap();
                                                            HeapFree(v1074, 0, (LPVOID)v1194);
                                                            LODWORD(v920) = 0;
                                                            v1070 = 0;
                                                            v1204 = 0;
                                                            v1040 = v1197;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v1070 = (unsigned int *)v1069;
                                                          v1204 = (SIZE_T)v1069;
                                                        }
                                                        goto LABEL_1462;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                          LODWORD(v920) = 0;
                                        }
                                      }
                                    }
                                  }
                                  v1215 = v930;
                                  v1070 = (unsigned int *)v1204;
LABEL_1462:
                                  v1200 = v1040 | 0x10000000;
                                  if ( v1040 < 0 )
                                    goto LABEL_1390;
                                  if ( !v1070 || (Src = (void *)*((_QWORD *)v1070 + 1)) == 0 || *v1070 == (_DWORD)v920 )
                                  {
                                    v1200 = -805306355;
                                    goto LABEL_1390;
                                  }
                                  v1201 = *v1070 - 8LL;
                                  v1075 = MemoryAlloc(v1201);
                                  v1196 = (SIZE_T)v1075;
                                  LODWORD(v920) = 0;
                                  if ( !v1075 )
                                    goto LABEL_1494;
                                  v1076 = 0;
                                  v1195 = 0;
                                  v1192 = 0x7F1137FAB69605ELL;
                                  v1077 = (unsigned __int16 *)Src;
                                  v1209 = (unsigned __int16 *)Src;
                                  pcchLength = (size_t)v1075;
                                  v1078 = v1201;
                                  v1210 = v1201 & 7;
                                  if ( (v1201 & 7) != 0 )
                                  {
                                    v1223 = 0;
                                    v1212 = 0;
                                    LODWORD(v1199) = 0;
                                    v1079 = 0;
                                    v1080 = 0;
                                    v1081 = 0;
                                    do
                                    {
                                      LODWORD(v1197) = *(unsigned __int8 *)v1077;
                                      v1077 = (unsigned __int16 *)((char *)v1077 + 1);
                                      v1193 = 8 * v1079;
                                      if ( (unsigned int)v1079 >= 4 )
                                      {
                                        LODWORD(v1197) = (_DWORD)v1197 << (56 - v1193);
                                        v1081 |= v1197;
                                      }
                                      else
                                      {
                                        LODWORD(v1197) = (_DWORD)v1197 << (24 - v1193);
                                        v1080 |= v1197;
                                      }
                                      ++v1079;
                                    }
                                    while ( v1079 < (int)v1210 );
                                    v1223 = v1081;
                                    v1212 = v1080;
                                    v1209 = v1077;
                                    v1215 = v930;
                                    Size = (SIZE_T)v929;
                                    v1198 = v984;
                                    v1211 = v118;
                                    v1203 = v857;
                                    v1076 = v1195;
                                    v1078 = v1201;
                                    v1082 = v1210;
                                    v1083 = v1075;
                                    v1084 = v1212 ^ 0x92F65A5;
                                    v1085 = v1223 ^ 0x699A899C;
                                    LODWORD(v1199) = 0;
                                    if ( (_DWORD)v1210 )
                                    {
                                      v1086 = v1212 ^ 0x92F65A5;
                                      v1087 = v1223 ^ 0x699A899C;
                                      v1088 = (unsigned int)v1199;
                                      do
                                      {
                                        v1219 = v1083 + 1;
                                        if ( v1088 >= 4 )
                                        {
                                          v1087 = __ROR4__(v1087, 24);
                                          v1089 = v1087;
                                        }
                                        else
                                        {
                                          v1086 = __ROR4__(v1086, 24);
                                          v1089 = v1086;
                                        }
                                        *v1083 = v1089;
                                        ++v1088;
                                        v1083 = v1219;
                                      }
                                      while ( (int)v1088 < (int)v1082 );
                                      pcchLength = (size_t)v1219;
                                      v1076 = v1195;
                                      v930 = v1215;
                                      v1075 = (_BYTE *)v1196;
                                      v1078 = v1201;
                                    }
                                    if ( v1082 <= 4 )
                                    {
                                      v1090 = 0;
                                      if ( v1082 < 4 )
                                        v1084 = v1084 >> (8 * (4 - v1082)) << (8 * (4 - v1082));
                                    }
                                    else
                                    {
                                      v1090 = v1085 >> (8 * (8 - v1082)) << (8 * (8 - v1082));
                                    }
                                  }
                                  else
                                  {
                                    v1212 = 0;
                                    v1090 = 0;
                                    v1084 = 0;
                                  }
                                  v1219 = (LPVOID)(v1078 >> 3);
                                  if ( v1078 >> 3 )
                                  {
                                    v1210 = 0;
                                    v1091 = HIDWORD(v1192);
                                    LODWORD(v1194) = WORD2(v1192);
                                    LODWORD(v1197) = 24670;
                                    LODWORD(v1199) = HIDWORD(v1192) ^ 0xAB69605E;
                                    v1092 = (unsigned __int8 *)v1209;
                                    v1093 = (_BYTE *)pcchLength;
                                    v1094 = v1212;
                                    v1095 = v1219;
                                    do
                                    {
                                      v1096 = v1092[3] | ((v1092[2] | ((v1092[1] | (*v1092 << 8)) << 8)) << 8);
                                      v1097 = v1092[7] | ((v1092[6] | ((v1092[5] | (v1092[4] << 8)) << 8)) << 8);
                                      v1092 += 8;
                                      v1098 = v1090 ^ v1097 ^ v1091 ^ v1084 ^ v1096 ^ 0xAB69605E;
                                      v1099 = v1084
                                            ^ v1096
                                            ^ (__ROR4__(v1098, 22) + v1194 * __ROR4__(v1098 + 1419157410, 27));
                                      v1100 = v1098 ^ (WORD1(v1192) * __ROR4__(v1099 + v1091, 9) - __ROR4__(v1099, 30));
                                      v1101 = v1099 ^ (v1197 * (v1100 - v1194) - (v1100 >> 13));
                                      v1102 = v1100
                                            ^ (HIWORD(v1192) * __ROR4__(WORD1(v1192) ^ v1101, 26) - __ROR4__(v1101, 30));
                                      v1103 = v1101 ^ (v1091 - (v1102 ^ 0xAB69605E));
                                      v1104 = v1102 ^ (WORD1(v1192) * (v1194 ^ v1103)) ^ __ROR4__(v1103, 6);
                                      v1105 = v1103 ^ (__ROR4__(v1104, 30) + v1197 * __ROR4__(v1104 + v1091, 15));
                                      v1106 = v1104
                                            ^ (HIWORD(v1192) * __ROR4__(v1105 + 1419157410, 14) - __ROR4__(v1105, 24));
                                      v1107 = v1105 ^ __ROR4__(v1106, 10) ^ (v1194 * __ROR4__(v1106 ^ 0xAB69605E, 12));
                                      v1108 = v1107
                                            ^ (HIWORD(v1192)
                                             * (v1197
                                              + __ROR4__(
                                                  ~(v1106 ^ (v1107 >> 10) ^ (WORD1(v1192) * (v1107 ^ HIWORD(v1192)))),
                                                  5)));
                                      v1109 = v1106
                                            ^ (v1107 >> 10)
                                            ^ (WORD1(v1192) * (v1107 ^ HIWORD(v1192)))
                                            ^ (v1108 - HIWORD(v1192))
                                            ^ 0xAB69605E;
                                      v1110 = v1108 ^ ((v1109 >> 2) + v1194 * __ROR4__(v1109 ^ HIWORD(v1192), 30));
                                      v1111 = v1109 ^ (__ROR4__(v1110, 25) + WORD1(v1192) * __ROR4__(v1110 - v1091, 6));
                                      v1112 = v1110 ^ (v1197 * (v1111 ^ v1194) + __ROR4__(v1111, 9));
                                      v1113 = v1111
                                            ^ (__ROR4__(v1112, 25) + HIWORD(v1192) * __ROR4__(v1112 ^ WORD1(v1192), 27));
                                      v1114 = v1112 ^ v1113 ^ (unsigned int)v1199;
                                      v1115 = v1113 ^ (v1194 * (__ROR4__(v1114, 3) - WORD1(v1192)));
                                      v1116 = v1114 ^ (v1197 * __ROR4__(v1115 - v1091, 1) - __ROR4__(v1115, 6));
                                      v1117 = v1115
                                            ^ (__ROR4__(v1116, 18) + HIWORD(v1192) * __ROR4__(v1116 - 1419157410, 29));
                                      v1118 = v1116 ^ (v1194 * __ROR4__(v1117 - 1419157410, 17) - __ROR4__(v1117, 14));
                                      v1119 = v1117 ^ (v1118 >> 3) ^ (WORD1(v1192) * (v1118 ^ v1197));
                                      v1084 = v1094
                                            ^ v1118
                                            ^ __ROR4__(v1119, 30)
                                            ^ (v1197 * __ROR4__(v1119 ^ v1091, 28));
                                      v1090 = v1223 ^ v1119;
                                      v1093[3] = v1084;
                                      v1093[7] = v1090;
                                      v1093[2] = __ROR4__(v1084, 8);
                                      v1093[6] = __ROR4__(v1090, 8);
                                      v1093[1] = __ROR4__(v1084, 16);
                                      v1093[5] = __ROR4__(v1090, 16);
                                      *v1093 = __ROR4__(v1084, 24);
                                      v1093[4] = __ROR4__(v1090, 24);
                                      v1094 = v1096;
                                      v1223 = v1097;
                                      v1093 += 8;
                                      ++v1210;
                                    }
                                    while ( v1210 < (unsigned __int64)v1095 );
                                    v1076 = v1195;
                                    v80 = dwBytes;
                                    v857 = v1203;
                                    v118 = v1211;
                                    v930 = v1215;
                                    v929 = (unsigned int *)Size;
                                    v984 = v1198;
                                    v1075 = (_BYTE *)v1196;
                                  }
                                  LODWORD(v920) = 0;
                                  v1120 = 0;
                                  for ( k = v1201; v1120 < v1201; ++v1120 )
                                    v1076 ^= v1075[v1120];
                                  if ( v1076 != *(_QWORD *)((char *)Src + v1201) )
                                  {
                                    MemoryFree(v1075);
                                    LODWORD(v920) = 0;
LABEL_1494:
                                    v1200 = -805306367;
                                    v1035 = 0;
                                    goto LABEL_1550;
                                  }
                                  v1122 = (void *)v1204;
                                  v1223 = 0;
                                  v1201 = (size_t)v1075;
                                  if ( k < 4 )
                                  {
                                    v1123 = -1073741762;
                                    v1035 = (void *)v1196;
LABEL_1544:
                                    v1200 = v1123 | 0x10000000;
                                    goto LABEL_1551;
                                  }
                                  v1123 = RtlULongLongAdd(v1075, 4, &v1201);
                                  if ( v1123 < 0 )
                                  {
                                    v1204 = (SIZE_T)v1122;
                                    v1035 = v1124;
                                    goto LABEL_1544;
                                  }
                                  v1123 = RtlUIntAdd(0, 4, &v1223);
                                  if ( v1123 < 0 )
                                  {
LABEL_1501:
                                    v1204 = (SIZE_T)v1122;
                                    v1035 = v1125;
                                    goto LABEL_1544;
                                  }
                                  if ( v1126 - v1223 < 4 )
                                  {
                                    v1123 = -1073741762;
                                    goto LABEL_1501;
                                  }
                                  LODWORD(v1194) = *(_DWORD *)v1201;
                                  v1123 = RtlULongLongAdd(v1201, 4, &v1201);
                                  if ( v1123 < 0 )
                                    goto LABEL_1506;
                                  v1123 = RtlUIntAdd(v1223, 4, &v1223);
                                  if ( v1123 < 0 )
                                    goto LABEL_1506;
                                  if ( v1128 - v1223 < v1129 )
                                    goto LABEL_1505;
                                  v1123 = RtlUIntAdd(v1223, v1129, &v1223);
                                  if ( v1123 < 0 )
                                    goto LABEL_1506;
                                  v1132 = v1130;
                                  v1133 = (size_t)v1127 + v1130;
                                  v1134 = (unsigned __int16 *)v1201;
                                  if ( v1133 < v1131 + v1201 || (unsigned __int64)v1127 + v1132 - v1131 - v1201 >= 8 )
                                  {
LABEL_1505:
                                    v1123 = -1073741762;
LABEL_1506:
                                    v1204 = (SIZE_T)v1122;
                                    v1035 = v1127;
LABEL_1507:
                                    LODWORD(v920) = 0;
                                    goto LABEL_1544;
                                  }
                                  LODWORD(v1199) = *v1127;
                                  v1192 = 0;
                                  v1210 = 0;
                                  v1209 = 0;
                                  LODWORD(v1213) = 0;
                                  if ( v1201 )
                                  {
                                    v1123 = RtlULongLongAdd(v1201, v1131, &v1192);
                                    v1200 = v1123;
                                    LODWORD(v920) = 0;
                                    v1204 = (SIZE_T)v1122;
                                    if ( v1123 < 0 )
                                    {
                                      v1035 = (void *)v1135;
LABEL_1539:
                                      v1145 = v1216;
                                      goto LABEL_1540;
                                    }
                                    v1136 = v1134;
                                    v1137 = v1192;
                                    if ( (unsigned __int64)v1134 < v1192 )
                                    {
                                      v1196 = v1135;
                                      v1198 = v984;
                                      while ( 1 )
                                      {
                                        v1123 = RtlULongLongAdd(v1136, 4, &v1210);
                                        if ( v1123 < 0 )
                                        {
                                          v984 = v1198;
                                          v1035 = (void *)v1196;
                                          LODWORD(v920) = 0;
                                          goto LABEL_1539;
                                        }
                                        if ( v1210 > v1192 )
                                        {
                                          v1123 = -1073741811;
LABEL_1526:
                                          v984 = v1198;
                                          v1035 = (void *)v1196;
                                          goto LABEL_1507;
                                        }
                                        v1193 = 0;
                                        v1123 = RtlUIntAdd(4, *v1138, &v1193);
                                        if ( v1123 < 0 )
                                          goto LABEL_1526;
                                        lpModuleName = (LPCWSTR)v857;
                                        v1140 = (SIZE_T)v1122;
                                        v1203 = v1122;
                                        v1141 = RtlULongLongAdd(v1139, v1193, &v1209);
                                        v1200 = v1141;
                                        v1035 = (void *)v1135;
                                        v1204 = v1140;
                                        v857 = (void *)lpModuleName;
                                        LODWORD(v920) = 0;
                                        if ( v1141 < 0 )
                                          break;
                                        v1136 = v1209;
                                        v1137 = v1192;
                                        if ( (unsigned __int64)v1209 > v1192 )
                                        {
                                          v1200 = -1073741811;
                                          v1204 = (SIZE_T)v1203;
                                          v1123 = -1073741811;
                                          goto LABEL_1507;
                                        }
                                        LODWORD(v1213) = v1213 + 1;
                                        v1196 = v1135;
                                        v1122 = v1203;
                                        v1204 = (SIZE_T)v1203;
                                        v1198 = v984;
                                        if ( (unsigned __int64)v1209 >= v1192 )
                                        {
                                          v1204 = (SIZE_T)v1203;
                                          goto LABEL_1522;
                                        }
                                      }
                                      v1123 = v1141;
                                      goto LABEL_1539;
                                    }
LABEL_1522:
                                    v1035 = (void *)v1135;
                                    if ( v1136 != (unsigned __int16 *)v1137 )
                                    {
                                      v1123 = -1073741811;
                                      goto LABEL_1507;
                                    }
                                    LODWORD(v920) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v920) = 0;
                                    v1200 = 0;
                                    v1204 = (SIZE_T)v1122;
                                    v1035 = v1127;
                                  }
                                  v1142 = 0;
                                  v1210 = 0;
                                  v1143 = v1194;
                                  if ( (_DWORD)v1194 )
                                  {
                                    v1144 = GetProcessHeap();
                                    v1142 = HeapAlloc(v1144, 8u, (unsigned int)v1194);
                                    v1210 = (SIZE_T)v1142;
                                    LODWORD(v920) = 0;
                                    if ( !v1142 )
                                    {
                                      v1123 = -1073741801;
                                      goto LABEL_1544;
                                    }
                                    v1200 = 0;
                                    v1134 = (unsigned __int16 *)v1201;
                                    v1143 = v1194;
                                  }
                                  if ( v1134 )
                                  {
                                    memcpy_0(v1142, v1134, v1143);
                                    LODWORD(v920) = 0;
                                  }
                                  v1202 = (LPVOID)v1210;
                                  v1145 = v1213;
                                  LODWORD(v1216) = v1213;
                                  v1123 = v1200;
LABEL_1540:
                                  if ( v1123 >= 0 && (_DWORD)v1199 != v1145 )
                                    v1123 = -1073741762;
                                  goto LABEL_1544;
                                }
                              }
                            }
                          }
                        }
                      }
                      v1198 = v984;
                      v1018 = GetProcessHeap();
                      HeapFree(v1018, 0, (LPVOID)v1192);
                      LODWORD(v920) = 0;
                    }
                    v1017 = v1200;
                    goto LABEL_1358;
                  }
LABEL_1328:
                  v929 = (unsigned int *)v1192;
                  v1192 = 0;
                  goto LABEL_1329;
                }
                pcchLength = v1224[1];
                if ( v903 )
                {
                  while ( 1 )
                  {
                    v1193 = 0;
                    if ( (int)RtlUIntAdd(4, *v904, &v1193) < 0 || (int)RtlULongLongAdd(v907, v1193, &pcchLength) < 0 )
                      break;
                    v904 = (unsigned int *)pcchLength;
                    if ( v909 + 1 >= v908 )
                      goto LABEL_1268;
                  }
                }
                else
                {
LABEL_1268:
                  v910 = RtlULongLongAdd(v904, 4, &v1226);
                  v906 = 0;
                  if ( v910 >= 0 && (unsigned __int64)(v911 + 3) <= v1224[1] + HIDWORD(v1224[0]) )
                  {
                    *v911 = 8;
                    *(_QWORD *)v1226 = v1219;
                    ++LODWORD(v1224[0]);
                    v905 = 4;
                    goto LABEL_1271;
                  }
                }
                v854 = 0;
                goto LABEL_1227;
              }
              v1211 = (LPVOID)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3648[0])(0, 0, 1027);
              if ( !v1211 )
              {
                GetLastError();
                goto LABEL_1203;
              }
              qword_1800A4710 = off_1800A35E8[0]();
              v435 = dword_1800A3D18;
              LODWORD(v1213) = dword_1800A3D18;
              memset_0(&v1266, 0, 0x70u);
              v1230 = 0;
              memset(v1322, 0, 44);
              while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                ;
              v436 = dword_1800A471C;
              if ( dword_1800A471C )
                goto LABEL_635;
              v437 = MemoryAlloc(0x338u);
              v1206 = (size_t)v437;
              if ( !v437 )
              {
LABEL_600:
                LODWORD(v118) = 0;
                goto LABEL_601;
              }
              v438 = (unsigned __int8 *)qword_18008D3E0;
              v439 = v437;
              v440 = 0;
              v441 = -1;
              v442 = 0;
              v443 = 0;
              v444 = 103;
              do
              {
                v445 = v438[3] | ((v438[2] | ((v438[1] | (*v438 << 8)) << 8)) << 8);
                v446 = v438[7] | ((v438[6] | ((v438[5] | (v438[4] << 8)) << 8)) << 8);
                v438 += 8;
                v447 = v443 ^ v445;
                v448 = v442 ^ v446 ^ v443 ^ v445 ^ 0xAC987321;
                v449 = v447 ^ (__ROR4__(v448, 22) + 4991 * __ROR4__(v448 + 1419157410, 27));
                v450 = v448 ^ (43881 * __ROR4__(v449 + 133239679, 9) - __ROR4__(v449, 30));
                v451 = v450
                     ^ (2033 * __ROR4__(v449 ^ (24670 * v450 - (v450 >> 13) - 123127970) ^ 0xAB69, 26)
                      - __ROR4__(v449 ^ (24670 * v450 - (v450 >> 13) - 123127970), 30));
                v452 = v449 ^ (24670 * v450 - (v450 >> 13) - 123127970) ^ (133239679 - (v451 ^ 0xAB69605E));
                v453 = v451 ^ (43881 * (v452 ^ 0x137F)) ^ __ROR4__(v452, 6);
                v454 = v452 ^ (__ROR4__(v453, 30) + 24670 * __ROR4__(v453 + 133239679, 15));
                v455 = v453 ^ (2033 * __ROR4__(v454 + 1419157410, 14) - __ROR4__(v454, 24));
                v456 = v454 ^ __ROR4__(v455, 10) ^ (4991 * __ROR4__(v455 ^ 0xAB69605E, 12));
                v457 = v455 ^ (v456 >> 10) ^ (43881 * (v456 ^ 0x7F1));
                v458 = v456 ^ (2033 * (__ROR4__(~v457, 5) + 24670));
                v459 = v458
                     ^ (((v457 ^ (v458 - 2033) ^ 0xAB69605E) >> 2)
                      + 4991 * __ROR4__(v457 ^ (v458 - 2033) ^ 0xAB6967AF, 30));
                v460 = v457 ^ (v458 - 2033) ^ 0xAB69605E ^ (__ROR4__(v459, 25) + 43881 * __ROR4__(v459 - 133239679, 6));
                v461 = v459 ^ (24670 * (v460 ^ 0x137F) + __ROR4__(v460, 9));
                v462 = v460 ^ (__ROR4__(v461, 25) + 2033 * __ROR4__(v461 ^ 0xAB69, 27));
                v463 = v461 ^ v462 ^ 0xAC987321;
                v464 = v462 ^ (4991 * __ROR4__(v463, 3) - 219010071);
                v465 = v463 ^ (24670 * __ROR4__(v464 - 133239679, 1) - __ROR4__(v464, 6));
                v466 = v464 ^ (__ROR4__(v465, 18) + 2033 * __ROR4__(v465 - 1419157410, 29));
                v467 = v465 ^ (4991 * __ROR4__(v466 - 1419157410, 17) - __ROR4__(v466, 14));
                v468 = v466 ^ (v467 >> 3) ^ (43881 * (v467 ^ 0x605E));
                v443 = v440 ^ v467 ^ __ROR4__(v468, 30) ^ (24670 * __ROR4__(v468 ^ 0x7F1137F, 28));
                v442 = v441 ^ v468;
                v439[3] = v443;
                v439[7] = v442;
                v439[2] = __ROR4__(v443, 8);
                v439[6] = __ROR4__(v442, 8);
                v439[1] = __ROR4__(v443, 16);
                v439[5] = __ROR4__(v442, 16);
                *v439 = __ROR4__(v443, 24);
                v439[4] = __ROR4__(v442, 24);
                v440 = v445;
                v441 = v446;
                v439 += 8;
                --v444;
              }
              while ( v444 );
              v469 = 0;
              v470 = 0;
              v435 = v1213;
              v118 = (_BYTE *)v1206;
              do
              {
                v470 ^= *(_BYTE *)(v469 + v1206);
                ++v469;
              }
              while ( v469 < 0x338 );
              if ( v470 != 64 )
              {
                MemoryFree((void *)v1206);
                goto LABEL_600;
              }
              LODWORD(v1194) = 0;
              v473 = 0;
              LODWORD(v1221) = 0;
              *(_BYTE *)(v1206 + 823) = 0;
              memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
              if ( *v118 )
              {
                pcchLength = (size_t)v118;
                while ( 1 )
                {
                  v474 = -1;
                  do
                    ++v474;
                  while ( *(_WORD *)&v118[2 * v474] );
                  v1192 = 3LL * v473;
                  v475 = (HMODULE *)&qword_1800A3D20[3 * v473];
                  if ( !GetModuleHandleExW(0, (LPCWSTR)v118, v475) )
                    break;
                  v476 = &v118[2 * v474];
                  if ( *(_WORD *)*v475 == 23117
                    && (v479 = *((int *)*v475 + 15), (unsigned int)v479 < 0x10000000)
                    && (v480 = (char *)*v475 + v479, v480 >= (char *)*v475)
                    && *(_DWORD *)v480 == 17744 )
                  {
                    v478 = v1192;
                    if ( ((*((_WORD *)v480 + 12) - 267) & 0xFEFF) != 0 )
                    {
                      v477 = -1073741811;
                    }
                    else
                    {
                      v477 = 0;
                      *(__int64 *)((char *)&qword_1800A3D20[v1192 + 1] + 4) = *((_QWORD *)v480 + 17);
                      LODWORD(qword_1800A3D20[v478 + 1]) = *((_DWORD *)v480 + 20);
                    }
                  }
                  else
                  {
                    v477 = -1073741701;
                    v478 = v1192;
                  }
                  v481 = *(_DWORD *)(v476 + 2);
                  v1193 = v481;
                  v118 = v476 + 6;
                  v482 = 0;
                  for ( LODWORD(Size) = 0; v482 < v481; v478 = v1192 )
                  {
                    v483 = -1;
                    do
                      ++v483;
                    while ( v118[v483] );
                    if ( v477 >= 0 )
                    {
                      v484 = GetProcAddress((HMODULE)qword_1800A3D20[v478], v118);
                      if ( !v484 )
                        goto LABEL_629;
                      off_1800A3550[(unsigned int)v1194] = v484;
                      v482 = Size;
                      v481 = v1193;
                    }
                    v118 += v483 + 1;
                    LODWORD(v1194) = v1194 + 1;
                    LODWORD(Size) = ++v482;
                  }
                  v473 = (_DWORD)v1221 + 1;
                  LODWORD(v1221) = (_DWORD)v1221 + 1;
                  if ( !*v118 )
                    goto LABEL_629;
                }
                v477 = -1073741702;
LABEL_629:
                v485 = (void *)pcchLength;
                LODWORD(v118) = 0;
                if ( !pcchLength )
                  goto LABEL_633;
              }
              else
              {
                v477 = 0;
                v485 = v118;
                LODWORD(v118) = 0;
              }
              v486 = GetProcessHeap();
              HeapFree(v486, 0, v485);
LABEL_633:
              if ( v477 < 0 )
              {
LABEL_601:
                for ( m = 0; m != 4; ++m )
                {
                  v472 = (HMODULE)qword_1800A3D20[3 * m];
                  if ( v472 )
                    FreeLibrary(v472);
                }
                memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                memcpy_0(off_1800A3550, off_180085080, 0x170u);
LABEL_636:
                _InterlockedExchange(&dword_1800A4720, 0);
                v1203 = 0;
                v1222 = 0;
                while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                  ;
                v487 = dword_1800A471C;
                if ( dword_1800A471C )
                  goto LABEL_681;
                v488 = MemoryAlloc(0x338u);
                v1206 = (size_t)v488;
                if ( !v488 )
                {
LABEL_646:
                  LODWORD(v118) = 0;
                  goto LABEL_647;
                }
                v489 = (unsigned __int8 *)qword_18008D3E0;
                v490 = v488;
                v491 = 0;
                v492 = -1;
                v493 = 0;
                v494 = 0;
                v495 = 103;
                do
                {
                  v496 = v489[3] | ((v489[2] | (((*v489 << 8) | v489[1]) << 8)) << 8);
                  v497 = v489[7] | ((v489[6] | ((v489[5] | (v489[4] << 8)) << 8)) << 8);
                  v489 += 8;
                  v498 = v494 ^ v496;
                  v499 = v494 ^ v496 ^ v493 ^ v497 ^ 0xAC987321;
                  v500 = v498 ^ (__ROR4__(v499, 22) + 4991 * __ROR4__(v499 + 1419157410, 27));
                  v501 = v499 ^ (43881 * __ROR4__(v500 + 133239679, 9) - __ROR4__(v500, 30));
                  v502 = v501
                       ^ (2033 * __ROR4__(v500 ^ (24670 * v501 - (v501 >> 13) - 123127970) ^ 0xAB69, 26)
                        - __ROR4__(v500 ^ (24670 * v501 - (v501 >> 13) - 123127970), 30));
                  v503 = v500 ^ (24670 * v501 - (v501 >> 13) - 123127970) ^ (133239679 - (v502 ^ 0xAB69605E));
                  v504 = v502 ^ (43881 * (v503 ^ 0x137F)) ^ __ROR4__(v503, 6);
                  v505 = v503 ^ (__ROR4__(v504, 30) + 24670 * __ROR4__(v504 + 133239679, 15));
                  v506 = v504 ^ (2033 * __ROR4__(v505 + 1419157410, 14) - __ROR4__(v505, 24));
                  v507 = v505 ^ __ROR4__(v506, 10) ^ (4991 * __ROR4__(v506 ^ 0xAB69605E, 12));
                  v508 = v506 ^ (v507 >> 10) ^ (43881 * (v507 ^ 0x7F1));
                  v509 = v507 ^ (2033 * (__ROR4__(~v508, 5) + 24670));
                  v510 = v509
                       ^ (((v508 ^ (v509 - 2033) ^ 0xAB69605E) >> 2)
                        + 4991 * __ROR4__(v508 ^ (v509 - 2033) ^ 0xAB6967AF, 30));
                  v511 = v508
                       ^ (v509 - 2033)
                       ^ 0xAB69605E
                       ^ (__ROR4__(v510, 25) + 43881 * __ROR4__(v510 - 133239679, 6));
                  v512 = v510 ^ (24670 * (v511 ^ 0x137F) + __ROR4__(v511, 9));
                  v513 = v511 ^ (__ROR4__(v512, 25) + 2033 * __ROR4__(v512 ^ 0xAB69, 27));
                  v514 = v512 ^ v513 ^ 0xAC987321;
                  v515 = v513 ^ (4991 * __ROR4__(v514, 3) - 219010071);
                  v516 = v514 ^ (24670 * __ROR4__(v515 - 133239679, 1) - __ROR4__(v515, 6));
                  v517 = v515 ^ (__ROR4__(v516, 18) + 2033 * __ROR4__(v516 - 1419157410, 29));
                  v518 = v516 ^ (4991 * __ROR4__(v517 - 1419157410, 17) - __ROR4__(v517, 14));
                  v519 = v517 ^ (v518 >> 3) ^ (43881 * (v518 ^ 0x605E));
                  v494 = v518 ^ v491 ^ __ROR4__(v519, 30) ^ (24670 * __ROR4__(v519 ^ 0x7F1137F, 28));
                  v493 = v519 ^ v492;
                  v490[3] = v494;
                  v490[7] = v519 ^ v492;
                  v490[2] = __ROR4__(v494, 8);
                  v490[6] = __ROR4__(v519 ^ v492, 8);
                  v490[1] = __ROR4__(v494, 16);
                  v490[5] = __ROR4__(v519 ^ v492, 16);
                  *v490 = __ROR4__(v494, 24);
                  v490[4] = __ROR4__(v519 ^ v492, 24);
                  v491 = v496;
                  v492 = v497;
                  v490 += 8;
                  --v495;
                }
                while ( v495 );
                v520 = 0;
                v521 = 0;
                v435 = v1213;
                v118 = (_BYTE *)v1206;
                do
                {
                  v521 ^= *(_BYTE *)(v520 + v1206);
                  ++v520;
                }
                while ( v520 < 0x338 );
                if ( v521 != 64 )
                {
                  MemoryFree((void *)v1206);
                  goto LABEL_646;
                }
                LODWORD(v1194) = 0;
                v524 = 0;
                LODWORD(v1221) = 0;
                *(_BYTE *)(v1206 + 823) = 0;
                memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                if ( *v118 )
                {
                  pcchLength = (size_t)v118;
                  while ( 1 )
                  {
                    v525 = -1;
                    do
                      ++v525;
                    while ( *(_WORD *)&v118[2 * v525] );
                    v1192 = 3LL * v524;
                    v526 = (HMODULE *)&qword_1800A3D20[3 * v524];
                    if ( !GetModuleHandleExW(0, (LPCWSTR)v118, v526) )
                      break;
                    v527 = &v118[2 * v525];
                    if ( *(_WORD *)*v526 == 23117
                      && (v530 = *((int *)*v526 + 15), (unsigned int)v530 < 0x10000000)
                      && (v531 = (char *)*v526 + v530, v531 >= (char *)*v526)
                      && *(_DWORD *)v531 == 17744 )
                    {
                      v529 = v1192;
                      if ( ((*((_WORD *)v531 + 12) - 267) & 0xFEFF) != 0 )
                      {
                        v528 = -1073741811;
                      }
                      else
                      {
                        v528 = 0;
                        *(__int64 *)((char *)&qword_1800A3D20[v1192 + 1] + 4) = *((_QWORD *)v531 + 17);
                        LODWORD(qword_1800A3D20[v529 + 1]) = *((_DWORD *)v531 + 20);
                      }
                    }
                    else
                    {
                      v528 = -1073741701;
                      v529 = v1192;
                    }
                    v532 = *(_DWORD *)(v527 + 2);
                    v1193 = v532;
                    v118 = v527 + 6;
                    v533 = 0;
                    for ( LODWORD(Size) = 0; v533 < v532; v529 = v1192 )
                    {
                      v534 = -1;
                      do
                        ++v534;
                      while ( v118[v534] );
                      if ( v528 >= 0 )
                      {
                        v535 = GetProcAddress((HMODULE)qword_1800A3D20[v529], v118);
                        if ( !v535 )
                          goto LABEL_675;
                        off_1800A3550[(unsigned int)v1194] = v535;
                        v533 = Size;
                        v532 = v1193;
                      }
                      v118 += v534 + 1;
                      LODWORD(v1194) = v1194 + 1;
                      LODWORD(Size) = ++v533;
                    }
                    v524 = (_DWORD)v1221 + 1;
                    LODWORD(v1221) = (_DWORD)v1221 + 1;
                    if ( !*v118 )
                      goto LABEL_675;
                  }
                  v528 = -1073741702;
LABEL_675:
                  v536 = (void *)pcchLength;
                  LODWORD(v118) = 0;
                  if ( !pcchLength )
                    goto LABEL_679;
                }
                else
                {
                  v528 = 0;
                  v536 = v118;
                  LODWORD(v118) = 0;
                }
                v537 = GetProcessHeap();
                HeapFree(v537, 0, v536);
LABEL_679:
                if ( v528 < 0 )
                {
LABEL_647:
                  for ( n = 0; n != 4; ++n )
                  {
                    v523 = (HMODULE)qword_1800A3D20[3 * n];
                    if ( v523 )
                      FreeLibrary(v523);
                  }
                  memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                  memcpy_0(off_1800A3550, off_180085080, 0x170u);
LABEL_682:
                  _InterlockedExchange(&dword_1800A4720, 0);
                  memset_0(&v1266, 0, 0x70u);
                  v1230 = 0;
                  LOWORD(v1199) = (v435 >> 4) & 0xF;
                  WORD1(v1199) = (v435 >> 8) & 0xF;
                  WORD2(v1199) = (v435 >> 12) & 0xF;
                  v1192 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3648[0])(0, 0, 1027);
                  LODWORD(v1197) = 0xFFFFFF;
                  if ( !v1192 )
                  {
                    v538 = GetLastError();
                    v539 = v538;
                    if ( v538 > 0 )
                      v539 = (unsigned __int16)v538 | 0x80070000;
                    if ( v539 >= 0 )
                      v539 = -2147467259;
LABEL_886:
                    while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                      ;
                    v647 = dword_1800A471C;
                    if ( dword_1800A471C > 0 )
                    {
                      --dword_1800A471C;
                      if ( v647 == 1 )
                      {
                        for ( ii = 0; ii != 4; ++ii )
                        {
                          v649 = (HMODULE)qword_1800A3D20[3 * ii];
                          if ( v649 )
                            FreeLibrary(v649);
                        }
                        memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                        memcpy_0(off_1800A3550, off_180085080, 0x170u);
                      }
                    }
                    _InterlockedExchange(&dword_1800A4720, 0);
                    SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1222);
                    if ( v539 < 0 )
                    {
LABEL_1113:
                      v784 = v1268;
                      if ( v1268 )
                      {
                        v785 = -1;
                        do
                          ++v785;
                        while ( *((_WORD *)v1268 + v785) );
                        for ( jj = 2 * v785 + 2; jj; --jj )
                          *v784++ = 0;
                        MemoryFree(v1268);
                        v1268 = 0;
                      }
                      v787 = v1269;
                      if ( v1269 )
                      {
                        v788 = -1;
                        do
                          ++v788;
                        while ( *((_WORD *)v1269 + v788) );
                        for ( kk = 2 * v788 + 2; kk; --kk )
                          *v787++ = 0;
                        MemoryFree(v1269);
                        v1269 = 0;
                      }
                      v790 = v1270;
                      if ( v1270 )
                      {
                        v791 = -1;
                        do
                          ++v791;
                        while ( *((_WORD *)v1270 + v791) );
                        v792 = 2 * v791 + 2;
                        if ( v792 )
                        {
                          do
                          {
                            *v790++ = 0;
                            --v792;
                          }
                          while ( v792 );
                          v790 = v1270;
                        }
                        MemoryFree(v790);
                        v1270 = 0;
                      }
                      if ( v1271 )
                      {
                        off_1800A3588();
                        v1271 = 0;
                      }
                      if ( v1272 )
                      {
                        off_1800A3588();
                        v1272 = 0;
                      }
                      if ( v1273 )
                      {
                        off_1800A3588();
                        v1273 = 0;
                      }
                      while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                        ;
                      v793 = dword_1800A471C;
                      if ( dword_1800A471C > 0 )
                      {
                        --dword_1800A471C;
                        if ( v793 == 1 )
                        {
                          for ( mm = 0; mm != 4; ++mm )
                          {
                            v795 = (HMODULE)qword_1800A3D20[3 * mm];
                            if ( v795 )
                              FreeLibrary(v795);
                          }
                          memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                          memcpy_0(off_1800A3550, off_180085080, 0x170u);
                        }
                      }
                      _InterlockedExchange(&dword_1800A4720, 0);
                      v796 = dword_1800A3D18;
                      LODWORD(v1213) = dword_1800A3D18;
                      v797 = qword_1800A4710;
                      v798 = (void *)((unsigned int)off_1800A35E8[0]() - v797);
                      Src = v798;
                      v1352 = 0;
                      v1353 = 0;
                      v1354 = 0;
                      v1355 = 0;
                      v1356 = 0;
                      while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                        ;
                      v799 = dword_1800A471C;
                      if ( dword_1800A471C )
                        goto LABEL_1192;
                      v800 = (const WCHAR *)MemoryAlloc(0x338u);
                      lpModuleName = v800;
                      v801 = 0;
                      if ( !v800 )
                        goto LABEL_1157;
                      v802 = (WCHAR *)v800;
                      v803 = 0;
                      v804 = -1;
                      v805 = 0;
                      v806 = (unsigned __int8 *)qword_18008D3E0;
                      v807 = 103;
                      do
                      {
                        v808 = v806[3] | ((v806[2] | ((v806[1] | (*v806 << 8)) << 8)) << 8);
                        v809 = v806[7] | ((v806[6] | ((v806[5] | (v806[4] << 8)) << 8)) << 8);
                        v806 += 8;
                        v810 = v801 ^ v808;
                        v811 = v805 ^ v809 ^ v801 ^ v808 ^ 0xAC987321;
                        v812 = v810 ^ (__ROR4__(v811, 22) + 4991 * __ROR4__(v811 + 1419157410, 27));
                        v813 = v811 ^ (43881 * __ROR4__(v812 + 133239679, 9) - __ROR4__(v812, 30));
                        v814 = v813
                             ^ (2033 * __ROR4__(v812 ^ (24670 * v813 - (v813 >> 13) - 123127970) ^ 0xAB69, 26)
                              - __ROR4__(v812 ^ (24670 * v813 - (v813 >> 13) - 123127970), 30));
                        v815 = v812 ^ (24670 * v813 - (v813 >> 13) - 123127970) ^ (133239679 - (v814 ^ 0xAB69605E));
                        v816 = v814 ^ (43881 * (v815 ^ 0x137F)) ^ __ROR4__(v815, 6);
                        v817 = v815 ^ (__ROR4__(v816, 30) + 24670 * __ROR4__(v816 + 133239679, 15));
                        v818 = v816 ^ (2033 * __ROR4__(v817 + 1419157410, 14) - __ROR4__(v817, 24));
                        v819 = v817 ^ __ROR4__(v818, 10) ^ (4991 * __ROR4__(v818 ^ 0xAB69605E, 12));
                        v820 = v818 ^ (v819 >> 10) ^ (43881 * (v819 ^ 0x7F1));
                        v821 = v819 ^ (2033 * (__ROR4__(~v820, 5) + 24670));
                        v822 = v821
                             ^ (((v820 ^ (v821 - 2033) ^ 0xAB69605E) >> 2)
                              + 4991 * __ROR4__(v820 ^ (v821 - 2033) ^ 0xAB6967AF, 30));
                        v823 = v820
                             ^ (v821 - 2033)
                             ^ 0xAB69605E
                             ^ (__ROR4__(v822, 25) + 43881 * __ROR4__(v822 - 133239679, 6));
                        v824 = v822 ^ (24670 * (v823 ^ 0x137F) + __ROR4__(v823, 9));
                        v825 = v823 ^ (__ROR4__(v824, 25) + 2033 * __ROR4__(v824 ^ 0xAB69, 27));
                        v826 = v824 ^ v825 ^ 0xAC987321;
                        v827 = v825 ^ (4991 * __ROR4__(v826, 3) - 219010071);
                        v828 = v826 ^ (24670 * __ROR4__(v827 - 133239679, 1) - __ROR4__(v827, 6));
                        v829 = v827 ^ (__ROR4__(v828, 18) + 2033 * __ROR4__(v828 - 1419157410, 29));
                        v830 = v828 ^ (4991 * __ROR4__(v829 - 1419157410, 17) - __ROR4__(v829, 14));
                        v831 = v829 ^ (v830 >> 3) ^ (43881 * (v830 ^ 0x605E));
                        v801 = v830 ^ v803 ^ __ROR4__(v831, 30) ^ (24670 * __ROR4__(v831 ^ 0x7F1137F, 28));
                        v805 = v831 ^ v804;
                        *((_BYTE *)v802 + 3) = v801;
                        *((_BYTE *)v802 + 7) = v831 ^ v804;
                        *((_BYTE *)v802 + 2) = __ROR4__(v801, 8);
                        *((_BYTE *)v802 + 6) = __ROR4__(v831 ^ v804, 8);
                        *((_BYTE *)v802 + 1) = __ROR4__(v801, 16);
                        *((_BYTE *)v802 + 5) = __ROR4__(v831 ^ v804, 16);
                        *(_BYTE *)v802 = __ROR4__(v801, 24);
                        *((_BYTE *)v802 + 4) = __ROR4__(v831 ^ v804, 24);
                        v803 = v808;
                        v804 = v809;
                        v802 += 4;
                        --v807;
                      }
                      while ( v807 );
                      v832 = 0;
                      v833 = 0;
                      v834 = (WCHAR *)lpModuleName;
                      do
                        v833 ^= *((_BYTE *)lpModuleName + v832++);
                      while ( v832 < 0x338 );
                      if ( v833 != 64 )
                      {
                        MemoryFree((void *)lpModuleName);
LABEL_1156:
                        v796 = v1213;
                        LODWORD(v798) = (_DWORD)Src;
LABEL_1157:
                        for ( nn = 0; nn != 4; ++nn )
                        {
                          v836 = (HMODULE)qword_1800A3D20[3 * nn];
                          if ( v836 )
                            FreeLibrary(v836);
                        }
                        memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                        memcpy_0(off_1800A3550, off_180085080, 0x170u);
                        goto LABEL_1193;
                      }
                      LODWORD(v1194) = 0;
                      v837 = 0;
                      LODWORD(v1202) = 0;
                      *((_BYTE *)lpModuleName + 823) = 0;
                      memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                      if ( *(_BYTE *)v834 )
                      {
                        pcchLength = (size_t)v834;
                        while ( 1 )
                        {
                          v838 = -1;
                          do
                            ++v838;
                          while ( v834[v838] );
                          v839 = 3LL * v837;
                          v840 = (HMODULE *)&qword_1800A3D20[v839];
                          if ( !GetModuleHandleExW(0, v834, v840) )
                            break;
                          v841 = &v834[v838];
                          if ( *(_WORD *)*v840 == 23117
                            && (v843 = *((int *)*v840 + 15), (unsigned int)v843 < 0x10000000)
                            && (v844 = (char *)*v840 + v843, v844 >= (char *)*v840)
                            && *(_DWORD *)v844 == 17744 )
                          {
                            if ( ((*((_WORD *)v844 + 12) - 267) & 0xFEFF) != 0 )
                            {
                              v842 = -1073741811;
                            }
                            else
                            {
                              v842 = 0;
                              *(__int64 *)((char *)&qword_1800A3D20[v839 + 1] + 4) = *((_QWORD *)v844 + 17);
                              LODWORD(qword_1800A3D20[v839 + 1]) = *((_DWORD *)v844 + 20);
                            }
                          }
                          else
                          {
                            v842 = -1073741701;
                          }
                          v1193 = *(_DWORD *)(v841 + 1);
                          v834 = v841 + 3;
                          v845 = 0;
                          LODWORD(v1196) = 0;
                          if ( v1193 )
                          {
                            v846 = v1194;
                            v847 = v1193;
                            do
                            {
                              v848 = -1;
                              do
                                ++v848;
                              while ( *((_BYTE *)v834 + v848) );
                              if ( v842 >= 0 )
                              {
                                v849 = GetProcAddress(*v840, (LPCSTR)v834);
                                if ( !v849 )
                                  goto LABEL_1186;
                                off_1800A3550[(unsigned int)v1194] = v849;
                                v845 = v1196;
                                v846 = v1194;
                                v847 = v1193;
                              }
                              v834 = (WCHAR *)((char *)v834 + v848 + 1);
                              LODWORD(v1194) = ++v846;
                              LODWORD(v1196) = ++v845;
                            }
                            while ( v845 < v847 );
                          }
                          v837 = (_DWORD)v1202 + 1;
                          LODWORD(v1202) = (_DWORD)v1202 + 1;
                          if ( !*(_BYTE *)v834 )
                            goto LABEL_1186;
                        }
                        v842 = -1073741702;
LABEL_1186:
                        v834 = (WCHAR *)pcchLength;
                        if ( !pcchLength )
                          goto LABEL_1190;
                      }
                      else
                      {
                        v842 = 0;
                      }
                      v850 = GetProcessHeap();
                      HeapFree(v850, 0, v834);
LABEL_1190:
                      if ( v842 < 0 )
                        goto LABEL_1156;
                      v799 = dword_1800A471C;
                      LODWORD(v798) = (_DWORD)Src;
                      v796 = v1213;
LABEL_1192:
                      dword_1800A471C = v799 + 1;
LABEL_1193:
                      _InterlockedExchange(&dword_1800A4720, 0);
                      LODWORD(v1353) = (_DWORD)v798;
                      v1352 = 1;
                      LODWORD(v1354) = -1721306479;
                      DWORD2(v1353) = 1;
                      LODWORD(v1355) = 1;
                      DWORD2(v1354) = 1;
                      LODWORD(v1356) = v796;
                      DWORD2(v1355) = 1;
                      ((void (__fastcall *)(_QWORD, __int64, __int64, int *))qword_1800A3620)(0, 8225, 4, &v1352);
                      while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
                        ;
                      v851 = dword_1800A471C;
                      v118 = 0;
                      if ( dword_1800A471C > 0 )
                      {
                        --dword_1800A471C;
                        if ( v851 == 1 )
                        {
                          for ( i1 = 0; i1 != 4; ++i1 )
                          {
                            v853 = (HMODULE)qword_1800A3D20[3 * i1];
                            if ( v853 )
                              FreeLibrary(v853);
                          }
                          memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                          memcpy_0(off_1800A3550, off_180085080, 0x170u);
                        }
                      }
                      _InterlockedExchange(&dword_1800A4720, 0);
                      ((void (__fastcall *)(_QWORD, LPVOID))off_1800A36B0[0])(0, v1211);
                      goto LABEL_1203;
                    }
                    Src = 0;
                    v650 = v1230;
                    v1210 = v1230;
                    v1287 = 0;
                    memset_0(v1288, 0, 0x64u);
                    v651 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800A35A0[0])(v1211, 7);
                    if ( v651
                      && ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800A35B8[0])(v651, 104, &v1287) )
                    {
                      if ( v1289 == 32 && v1290 && v1288[0] > 0 )
                        LODWORD(v118) = v1288[1] > 0;
                      v652 = v435 & 0xF;
                      v653 = v652;
                      if ( (_DWORD)v118 )
                      {
LABEL_905:
                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_1800A36A0)(&v1275, v650, HIDWORD(v1210));
                        ((void (__fastcall *)(int *, _QWORD, _QWORD))off_1800A36A0)(&v1279, v650, HIDWORD(v1210));
                        if ( v652 == 1 )
                          Src = (void *)((__int64 (__fastcall *)(_QWORD))off_1800A3578[0])(v1267 == 0 ? 0xB26720 : 0);
LABEL_907:
                        v654 = v1211;
                        LODWORD(v1199) = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800A35D0)(v1211, 1);
                        v655 = 2064;
                        if ( v1266 )
                          v655 = 133138;
                        HIDWORD(dwBytes) = v655;
                        if ( (_DWORD)v118 )
                        {
                          v656 = 0;
                          v1291 = 0;
                          memset_0(v1292, 0, 0x64u);
                          v1312 = 0;
                          memset_0(v1313, 0, 0x64u);
                          v1326 = 0;
                          memset(v1327, 0, 28);
                          v1315 = 0;
                          v1222 = v1268;
                          if ( !v1268 )
                            goto LABEL_1111;
                          v1193 = v1267;
                          v1206 = v1271;
                          v657 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800A35A0[0])(v654, 7);
                          if ( v657 )
                          {
                            if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800A35B8[0])(
                                   v657,
                                   104,
                                   &v1291) )
                            {
                              v1209 = v1293;
                              LODWORD(v1213) = v1292[0];
                              LODWORD(Size) = v1292[1];
                              v656 = 0;
                            }
                            else
                            {
                              v1209 = 0;
                              LODWORD(Size) = 0;
                              LODWORD(v1213) = 0;
                            }
                            v658 = ((__int64 (__fastcall *)(LPVOID))off_1800A3560[0])(v654);
                            v659 = v658;
                            pcchLength = v658;
                            if ( v658 )
                            {
                              v1262 = 0;
                              memset(v1327, 0, 28);
                              LODWORD(v1326) = 40;
                              DWORD1(v1326) = v1277 - v1275;
                              DWORD2(v1326) = v1276 - v1278;
                              HIDWORD(v1326) = 2097153;
                              v660 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800A3568[0])(
                                       v658,
                                       &v1326,
                                       0,
                                       &v1262,
                                       0,
                                       0);
                              v1201 = v660;
                              if ( v660 )
                              {
                                if ( ((unsigned int (__fastcall *)(size_t, __int64, int *))off_1800A35B8[0])(
                                       v660,
                                       104,
                                       &v1312) )
                                {
                                  v1210 = v1314;
                                }
                                else
                                {
                                  v1210 = 0;
                                }
                                DWORD2(v1315) = v1277 - v1275;
                                HIDWORD(v1315) = v1278 - v1276;
                                ((void (__fastcall *)(size_t, size_t))off_1800A35C8)(v659, v1201);
                                ((void (__fastcall *)(size_t, __int64))off_1800A35D0)(v659, 1);
                                v1203 = (LPVOID)((__int64 (__fastcall *)(size_t, size_t))off_1800A35C8)(v659, v1206);
                                v663 = off_1800A3638[0];
                                v664 = ((__int64 (__fastcall *)(_QWORD))off_1800A35C0[0])(0);
                                ((void (__fastcall *)(size_t, __int128 *, __int64))v663)(pcchLength, &v1315, v664);
                                v659 = pcchLength;
                                ((void (__fastcall *)(size_t, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800A3628)(
                                  pcchLength,
                                  v1222,
                                  0xFFFFFFFFLL,
                                  &v1315,
                                  HIDWORD(dwBytes),
                                  0);
                                v665 = 0;
                                if ( v652 == 1 )
                                {
                                  if ( v1193 )
                                  {
                                    v666 = ((__int64 (__fastcall *)(__int64))off_1800A3668[0])(8);
                                    v665 = 0;
                                  }
                                  else
                                  {
                                    v666 = 0xFFFFFF;
                                  }
                                }
                                else
                                {
                                  v666 = -5723992;
                                }
                                LODWORD(v1194) = v666;
                                v667 = -v1275;
                                if ( v1275 >= 0 )
                                  v667 = 0;
                                v668 = 0;
                                if ( v1275 >= 0 )
                                  v668 = v1275;
                                v669 = -v1276;
                                if ( v1276 >= 0 )
                                {
                                  v669 = 0;
                                  v665 = v1276;
                                }
                                v670 = (int)v1213;
                                v671 = DWORD2(v1315) - v667;
                                if ( DWORD2(v1315) - v667 >= (int)v1213 - v668 )
                                  v671 = v1213 - v668;
                                v1193 = v671;
                                v672 = HIDWORD(v1315) - v669;
                                if ( HIDWORD(v1315) - v669 >= (int)Size - v665 )
                                  v672 = Size - v665;
                                LODWORD(v1204) = v672;
                                if ( v671 > 0 && v672 > 0 )
                                {
                                  v673 = (char *)(v1210 + 4 * (v667 + (__int64)(v669 * DWORD2(v1315))));
                                  v1222 = v673;
                                  v674 = &v1209[2 * v668 + 2 * (__int64)(v665 * (int)v1213)];
                                  v1209 = v674;
                                  v675 = v1194;
                                  LODWORD(v1196) = (unsigned int)v1194 >> 8;
                                  LODWORD(v1202) = WORD1(v1194);
                                  LODWORD(v1213) = 0;
                                  v1206 = 4LL * SDWORD2(v1315);
                                  v1192 = 4 * v670;
                                  v676 = v1193;
                                  do
                                  {
                                    v677 = (unsigned __int8 *)v673;
                                    v1210 = (SIZE_T)v673;
                                    v678 = v674;
                                    v679 = 0;
                                    LODWORD(v1194) = 0;
                                    v680 = v1196;
                                    v681 = (char)v1202;
                                    do
                                    {
                                      v682 = ~(unsigned __int8)((*v677 + v677[2] + 2 * (unsigned int)v677[1]) >> 2);
                                      if ( (unsigned __int8)((*v677 + v677[2] + 2 * (unsigned int)v677[1]) >> 2) != 0xFF )
                                      {
                                        v683 = *((unsigned __int8 *)v678 + 2);
                                        v684 = v682;
                                        v685 = (int)((unsigned __int64)(2155905153LL * v682 * (v675 - v683)) >> 32) >> 7;
                                        *((_BYTE *)v678 + 2) = v683 + (v685 < 0) + v685;
                                        *((_BYTE *)v678 + 1) -= v684 * (v680 - *((_BYTE *)v678 + 1));
                                        *(_BYTE *)v678 -= v684 * (v681 - *(_BYTE *)v678);
                                        *((_BYTE *)v678 + 3) += v684 * (255 - *((unsigned __int8 *)v678 + 3)) / 255;
                                        v677 = (unsigned __int8 *)v1210;
                                        v679 = v1194;
                                      }
                                      v677 += 4;
                                      v1210 = (SIZE_T)v677;
                                      v678 += 2;
                                      LODWORD(v1194) = ++v679;
                                    }
                                    while ( v679 < v676 );
                                    v673 = (char *)v1222 + v1206;
                                    v1222 = (char *)v1222 + v1206;
                                    v674 = (unsigned __int16 *)((char *)v1209 + v1192);
                                    v1209 = (unsigned __int16 *)((char *)v1209 + v1192);
                                    LODWORD(v1213) = v1213 + 1;
                                  }
                                  while ( (int)v1213 < (int)v1204 );
                                  v80 = dwBytes;
                                  v659 = pcchLength;
                                }
                                ((void (__fastcall *)(size_t))off_1800A3588)(v1201);
                                v662 = 0;
                                if ( v1203 )
                                  ((void (__fastcall *)(size_t, LPVOID))off_1800A35C8)(v659, v1203);
                              }
                              else
                              {
                                v661 = GetLastError();
                                v656 = v661;
                                v662 = 0;
                                if ( v661 > 0 )
                                  v656 = (unsigned __int16)v661 | 0x80070000;
                                if ( v656 >= 0 )
                                  v656 = -2147467259;
                              }
                              ((void (__fastcall *)(size_t))off_1800A3580[0])(v659);
                              if ( v656 < 0 )
                                goto LABEL_1111;
                              v1294 = 0;
                              memset_0(v1295, 0, 0x64u);
                              v1303 = 0;
                              memset_0(v1304, 0, 0x64u);
                              v1328 = 0;
                              memset(v1329, 0, 28);
                              v1318 = 0;
                              pcchLength = (size_t)v1269;
                              if ( !v1269 )
                                goto LABEL_1111;
                              v1193 = v1267;
                              v1206 = (size_t)v1272;
                              v686 = v1211;
                              v687 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800A35A0[0])(v1211, 7);
                              if ( v687 )
                              {
                                if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800A35B8[0])(
                                       v687,
                                       104,
                                       &v1294) )
                                {
                                  v1209 = v1296;
                                  LODWORD(v1194) = v1295[0];
                                  LODWORD(v1213) = v1295[1];
                                  v686 = v1211;
                                }
                                else
                                {
                                  v1209 = 0;
                                  LODWORD(v1213) = 0;
                                  LODWORD(v1194) = 0;
                                }
                                v688 = (void *)((__int64 (__fastcall *)(LPVOID))off_1800A3560[0])(v686);
                                v689 = v688;
                                v1222 = v688;
                                if ( v688 )
                                {
                                  v1261 = 0;
                                  memset(v1329, 0, 28);
                                  LODWORD(v1328) = 40;
                                  DWORD1(v1328) = v1281 - v1279;
                                  DWORD2(v1328) = v1280 - v1282;
                                  HIDWORD(v1328) = 2097153;
                                  v690 = ((__int64 (__fastcall *)(void *, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800A3568[0])(
                                           v688,
                                           &v1328,
                                           0,
                                           &v1261,
                                           0,
                                           0);
                                  v691 = v690;
                                  v1201 = v690;
                                  if ( v690 )
                                  {
                                    if ( ((unsigned int (__fastcall *)(size_t, __int64, int *))off_1800A35B8[0])(
                                           v690,
                                           104,
                                           &v1303) )
                                    {
                                      v1210 = v1305;
                                    }
                                    else
                                    {
                                      v1210 = 0;
                                    }
                                    DWORD2(v1318) = v1281 - v1279;
                                    HIDWORD(v1318) = v1282 - v1280;
                                    ((void (__fastcall *)(void *, size_t))off_1800A35C8)(v689, v691);
                                    ((void (__fastcall *)(void *, __int64))off_1800A35D0)(v689, 1);
                                    v1192 = ((__int64 (__fastcall *)(void *, size_t))off_1800A35C8)(v689, v1206);
                                    v693 = off_1800A3638[0];
                                    v694 = ((__int64 (__fastcall *)(_QWORD))off_1800A35C0[0])(0);
                                    ((void (__fastcall *)(void *, __int128 *, __int64))v693)(v689, &v1318, v694);
                                    ((void (__fastcall *)(void *, size_t, __int64, __int128 *, _DWORD, _QWORD))off_1800A3628)(
                                      v689,
                                      pcchLength,
                                      0xFFFFFFFFLL,
                                      &v1318,
                                      HIDWORD(dwBytes),
                                      0);
                                    if ( v653 == 1 )
                                    {
                                      if ( v1193 )
                                        LODWORD(v1197) = ((__int64 (__fastcall *)(__int64))off_1800A3668[0])(8);
                                    }
                                    else
                                    {
                                      LODWORD(v1197) = -5723992;
                                    }
                                    v695 = -v1279;
                                    if ( v1279 >= 0 )
                                      v695 = 0;
                                    v696 = 0;
                                    if ( v1279 >= 0 )
                                      v696 = v1279;
                                    v697 = -v1280;
                                    if ( v1280 >= 0 )
                                      v697 = 0;
                                    v698 = 0;
                                    if ( v1280 >= 0 )
                                      v698 = v1280;
                                    v699 = DWORD2(v1318) - v695;
                                    if ( DWORD2(v1318) - v695 >= (int)v1194 - v696 )
                                      v699 = v1194 - v696;
                                    v700 = HIDWORD(v1318) - v697;
                                    if ( HIDWORD(v1318) - v697 >= (int)v1213 - v698 )
                                      v700 = v1213 - v698;
                                    LODWORD(v1202) = v700;
                                    if ( v699 > 0 && v700 > 0 )
                                    {
                                      v701 = v1210 + 4 * (v695 + (__int64)(v697 * DWORD2(v1318)));
                                      v702 = &v1209[2 * v696 + 2 * (__int64)(v698 * (int)v1194)];
                                      v1209 = v702;
                                      v1193 = (unsigned int)v1197 >> 8;
                                      LODWORD(v1196) = WORD1(v1197);
                                      LODWORD(v1213) = 0;
                                      v1206 = 4LL * SDWORD2(v1318);
                                      pcchLength = 4LL * (int)v1194;
                                      do
                                      {
                                        v703 = (unsigned __int8 *)v701;
                                        v1210 = v701;
                                        v704 = v702;
                                        v705 = 0;
                                        LODWORD(v1194) = 0;
                                        v706 = v1193;
                                        v707 = v1196;
                                        v708 = v1197;
                                        do
                                        {
                                          v709 = ~(unsigned __int8)((*v703 + v703[2] + 2 * (unsigned int)v703[1]) >> 2);
                                          if ( (unsigned __int8)((*v703 + v703[2] + 2 * (unsigned int)v703[1]) >> 2) != 0xFF )
                                          {
                                            v710 = *((unsigned __int8 *)v704 + 2);
                                            v711 = v709;
                                            v712 = (int)((unsigned __int64)(2155905153LL * v709 * (v708 - v710)) >> 32) >> 7;
                                            *((_BYTE *)v704 + 2) = v710 + (v712 < 0) + v712;
                                            *((_BYTE *)v704 + 1) -= v711 * (v706 - *((_BYTE *)v704 + 1));
                                            *(_BYTE *)v704 -= v711 * (v707 - *(_BYTE *)v704);
                                            *((_BYTE *)v704 + 3) += v711 * (255 - *((unsigned __int8 *)v704 + 3)) / 255;
                                            v703 = (unsigned __int8 *)v1210;
                                            v705 = v1194;
                                          }
                                          v703 += 4;
                                          v1210 = (SIZE_T)v703;
                                          v704 += 2;
                                          LODWORD(v1194) = ++v705;
                                        }
                                        while ( v705 < v699 );
                                        v701 += v1206;
                                        v702 = (unsigned __int16 *)((char *)v1209 + pcchLength);
                                        v1209 = (unsigned __int16 *)((char *)v1209 + pcchLength);
                                        LODWORD(v1213) = v1213 + 1;
                                      }
                                      while ( (int)v1213 < (int)v1202 );
                                      v80 = dwBytes;
                                      v689 = v1222;
                                    }
                                    ((void (__fastcall *)(size_t))off_1800A3588)(v1201);
                                    if ( v1192 )
                                      ((void (__fastcall *)(void *, unsigned __int64))off_1800A35C8)(v689, v1192);
                                  }
                                  else
                                  {
                                    v662 = GetLastError();
                                    v692 = v662 < 0;
                                    if ( v662 > 0 )
                                    {
                                      v662 = (unsigned __int16)v662 | 0x80070000;
                                      v692 = v662 < 0;
                                    }
                                    if ( !v692 )
                                      v662 = -2147467259;
                                  }
                                  ((void (__fastcall *)(void *))off_1800A3580[0])(v689);
                                  if ( v662 < 0 )
                                    goto LABEL_1111;
                                  v1203 = 0;
                                  v713 = 0;
                                  v714 = v1211;
LABEL_1104:
                                  ((void (__fastcall *)(LPVOID, _QWORD))off_1800A35D0)(v714, (unsigned int)v1199);
                                  v717 = v1203;
                                  if ( !v713 )
                                    goto LABEL_1109;
                                  goto LABEL_1108;
                                }
                              }
                            }
                          }
LABEL_1001:
                          GetLastError();
                          goto LABEL_1111;
                        }
                        v715 = 0;
                        if ( v1267 || (v716 = -64, v653 == 1) )
                          v716 = -1;
                        LOWORD(Size) = 0;
                        BYTE2(Size) = v716;
                        BYTE3(Size) = 1;
                        v717 = (void *)((__int64 (__fastcall *)(LPVOID))off_1800A3560[0])(v654);
                        v1203 = v717;
                        if ( !v717 )
                          goto LABEL_1001;
                        if ( v653 == 1 )
                        {
                          v718 = 0;
                          LODWORD(v1204) = 0;
                          v719 = v1281 - v1279;
                          if ( v1281 - v1279 <= v1277 - v1275 )
                            v719 = v1277 - v1275;
                          LODWORD(v1194) = v719;
                          v720 = v1282 - v1276;
                          LODWORD(v1213) = v1282 - v1276;
                          if ( v1266 )
                          {
                            v715 = v1275 + v719 - v1277;
                            v721 = v1279 + v719 - v1281;
                          }
                          else
                          {
                            v721 = 0;
                          }
                          LODWORD(v1221) = v721;
                          v722 = v1277 - v1275 + v715;
                          LODWORD(v1216) = v1278 - v1276;
                          v1212 = v721 + v1281 - v1279;
                          v1193 = v1280 - v1276;
                          LODWORD(v1208) = v1282 - v1276;
                          v717 = v1203;
                        }
                        else
                        {
                          v719 = DWORD2(v1230);
                          LODWORD(v1194) = DWORD2(v1230);
                          v720 = HIDWORD(v1230);
                          LODWORD(v1213) = HIDWORD(v1230);
                          v715 = v1275;
                          v718 = v1276;
                          LODWORD(v1204) = v1276;
                          v722 = v1277;
                          LODWORD(v1216) = v1278;
                          LODWORD(v1221) = v1279;
                          v1193 = v1280;
                          v1212 = v1281;
                          LODWORD(v1208) = v1282;
                        }
                        LODWORD(v1215) = v722;
                        v1256 = 0;
                        memset(&v1322[4], 0, 28);
                        v1322[0] = 40;
                        v1322[1] = v719;
                        v1322[2] = -v720;
                        v1322[3] = 2097153;
                        v723 = ((__int64 (__fastcall *)(void *, _DWORD *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800A3568[0])(
                                 v717,
                                 v1322,
                                 0,
                                 &v1256,
                                 0,
                                 0);
                        v1192 = v723;
                        if ( !v723 )
                        {
                          GetLastError();
LABEL_1110:
                          ((void (__fastcall *)(void *))off_1800A3580[0])(v717);
LABEL_1111:
                          if ( Src )
                            ((void (__fastcall *)(void *))off_1800A3588)(Src);
                          goto LABEL_1113;
                        }
                        ((void (__fastcall *)(void *, unsigned __int64))off_1800A35C8)(v717, v723);
                        if ( v653 == 1 && Src )
                        {
                          v1319 = 0;
                          v1320 = v1194;
                          v1321 = v1213;
                          ((void (__fastcall *)(void *, __int64 *))off_1800A3638[0])(v717, &v1319);
                        }
                        v1297 = 0;
                        memset_0(v1298, 0, 0x64u);
                        v1306 = 0;
                        memset_0(v1307, 0, 0x64u);
                        v1330 = 0;
                        memset(v1331, 0, 28);
                        v1316 = 0;
                        pcchLength = (size_t)v1268;
                        if ( v1268 )
                        {
                          LODWORD(v1198) = v1267;
                          v1206 = v1271;
                          v724 = ((__int64 (__fastcall *)(void *, __int64))off_1800A35A0[0])(v717, 7);
                          if ( !v724
                            || (!((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800A35B8[0])(
                                   v724,
                                   104,
                                   &v1297)
                              ? (v1209 = 0, LODWORD(v1196) = 0, LODWORD(v1202) = 0)
                              : (v1209 = v1299, LODWORD(v1202) = v1298[0], LODWORD(v1196) = v1298[1]),
                                v725 = ((__int64 (__fastcall *)(void *))off_1800A3560[0])(v717),
                                (v1201 = v725) == 0) )
                          {
LABEL_1017:
                            GetLastError();
                            goto LABEL_1107;
                          }
                          LODWORD(v1216) = v1216 - v718;
                          v726 = (_DWORD)v1215 - v715;
                          v727 = 0;
                          v1254 = 0;
                          memset(v1331, 0, 28);
                          LODWORD(v1330) = 40;
                          DWORD1(v1330) = (_DWORD)v1215 - v715;
                          DWORD2(v1330) = -(int)v1216;
                          HIDWORD(v1330) = 2097153;
                          v728 = (void *)((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800A3568[0])(
                                           v725,
                                           &v1330,
                                           0,
                                           &v1254,
                                           0,
                                           0);
                          v1222 = v728;
                          if ( v728 )
                          {
                            if ( ((unsigned int (__fastcall *)(void *, __int64, int *))off_1800A35B8[0])(
                                   v728,
                                   104,
                                   &v1306) )
                            {
                              v1210 = v1308;
                            }
                            else
                            {
                              v1210 = 0;
                            }
                            *((_QWORD *)&v1316 + 1) = __PAIR64__(v1216, v726);
                            v731 = v1201;
                            ((void (__fastcall *)(size_t, void *))off_1800A35C8)(v1201, v1222);
                            ((void (__fastcall *)(size_t, __int64))off_1800A35D0)(v731, 1);
                            lpModuleName = (LPCWSTR)((__int64 (__fastcall *)(size_t, size_t))off_1800A35C8)(v731, v1206);
                            v732 = off_1800A3638[0];
                            v733 = ((__int64 (__fastcall *)(_QWORD))off_1800A35C0[0])(0);
                            ((void (__fastcall *)(size_t, __int128 *, __int64))v732)(v1201, &v1316, v733);
                            v734 = v1201;
                            ((void (__fastcall *)(size_t, size_t, __int64, __int128 *, _DWORD, _QWORD))off_1800A3628)(
                              v1201,
                              pcchLength,
                              0xFFFFFFFFLL,
                              &v1316,
                              HIDWORD(dwBytes),
                              0);
                            if ( v653 == 1 )
                            {
                              if ( (_DWORD)v1198 )
                                v735 = ((__int64 (__fastcall *)(__int64))off_1800A3668[0])(8);
                              else
                                v735 = 0xFFFFFF;
                            }
                            else
                            {
                              v735 = -5723992;
                            }
                            LODWORD(v1216) = v735;
                            v736 = -v715;
                            if ( v715 >= 0 )
                              v736 = 0;
                            v737 = 0;
                            if ( v715 >= 0 )
                              v737 = v715;
                            v738 = v1204;
                            if ( (v1204 & 0x80000000) == 0LL )
                            {
                              v739 = 0;
                            }
                            else
                            {
                              v739 = -(int)v1204;
                              v738 = 0;
                            }
                            v740 = (int)v1202;
                            v741 = DWORD2(v1316) - v736;
                            if ( DWORD2(v1316) - v736 >= (int)v1202 - v737 )
                              v741 = (_DWORD)v1202 - v737;
                            LODWORD(v1215) = v741;
                            v742 = HIDWORD(v1316) - v739;
                            if ( HIDWORD(v1316) - v739 >= (int)v1196 - v738 )
                              v742 = v1196 - v738;
                            LODWORD(v1207) = v742;
                            if ( v741 > 0 && v742 > 0 )
                            {
                              v743 = v1210 + 4 * (v736 + (__int64)(DWORD2(v1316) * v739));
                              pcchLength = v743;
                              v744 = &v1209[2 * v737 + 2 * (__int64)((int)v1202 * v738)];
                              v1209 = v744;
                              v745 = v1216;
                              LODWORD(v1198) = (unsigned int)v1216 >> 8;
                              LODWORD(v1204) = WORD1(v1216);
                              LODWORD(v1202) = 0;
                              v1206 = 4LL * SDWORD2(v1316);
                              v1237 = (void *)(4 * v740);
                              do
                              {
                                v746 = (unsigned __int8 *)v743;
                                v1210 = v743;
                                v747 = v744;
                                v748 = 0;
                                LODWORD(v1196) = 0;
                                v749 = (char)v1198;
                                v750 = v1204;
                                do
                                {
                                  v751 = ~(unsigned __int8)((*v746 + v746[2] + 2 * (unsigned int)v746[1]) >> 2);
                                  if ( (unsigned __int8)((*v746 + v746[2] + 2 * (unsigned int)v746[1]) >> 2) != 0xFF )
                                  {
                                    v752 = *((unsigned __int8 *)v747 + 2);
                                    v753 = (unsigned __int8)~((*v746 + v746[2] + 2 * (unsigned int)v746[1]) >> 2);
                                    v754 = (int)((unsigned __int64)(2155905153LL * v751 * (v745 - v752)) >> 32) >> 7;
                                    *((_BYTE *)v747 + 2) = v752 + (v754 < 0) + v754;
                                    *((_BYTE *)v747 + 1) -= v753 * (v749 - *((_BYTE *)v747 + 1));
                                    *(_BYTE *)v747 -= v753 * (v750 - *(_BYTE *)v747);
                                    *((_BYTE *)v747 + 3) += v753 * (255 - *((unsigned __int8 *)v747 + 3)) / 255;
                                    v741 = (int)v1215;
                                    v746 = (unsigned __int8 *)v1210;
                                    v748 = v1196;
                                  }
                                  v746 += 4;
                                  v1210 = (SIZE_T)v746;
                                  v747 += 2;
                                  LODWORD(v1196) = ++v748;
                                }
                                while ( v748 < v741 );
                                v743 = v1206 + pcchLength;
                                pcchLength += v1206;
                                v744 = (unsigned __int16 *)((char *)v1209 + (_QWORD)v1237);
                                v1209 = (unsigned __int16 *)((char *)v1209 + (_QWORD)v1237);
                                LODWORD(v1202) = (_DWORD)v1202 + 1;
                              }
                              while ( (int)v1202 < (int)v1207 );
                              v80 = dwBytes;
                            }
                            ((void (__fastcall *)(void *))off_1800A3588)(v1222);
                            v730 = 0;
                            if ( lpModuleName )
                              ((void (__fastcall *)(size_t, LPCWSTR))off_1800A35C8)(v734, lpModuleName);
                          }
                          else
                          {
                            v729 = GetLastError();
                            v727 = v729;
                            v730 = 0;
                            if ( v729 > 0 )
                              v727 = (unsigned __int16)v729 | 0x80070000;
                            if ( v727 >= 0 )
                              v727 = -2147467259;
                          }
                          ((void (__fastcall *)(size_t))off_1800A3580[0])(v1201);
                          if ( v727 < 0 )
                          {
LABEL_1106:
                            v717 = v1203;
                            goto LABEL_1107;
                          }
                          v1300 = 0;
                          memset_0(v1301, 0, 0x64u);
                          v1309 = 0;
                          memset_0(v1310, 0, 0x64u);
                          v1332 = 0;
                          memset(v1333, 0, 28);
                          v1317 = 0;
                          v1237 = v1269;
                          v717 = v1203;
                          if ( v1269 )
                          {
                            LODWORD(v1207) = v1267;
                            lpModuleName = v1272;
                            v755 = ((__int64 (__fastcall *)(LPVOID, __int64))off_1800A35A0[0])(v1203, 7);
                            if ( v755 )
                            {
                              if ( ((unsigned int (__fastcall *)(__int64, __int64, int *))off_1800A35B8[0])(
                                     v755,
                                     104,
                                     &v1300) )
                              {
                                v730 = v1302;
                                LODWORD(v1196) = v1301[0];
                                LODWORD(v1202) = v1301[1];
                              }
                              else
                              {
                                LODWORD(v1202) = 0;
                                LODWORD(v1196) = 0;
                              }
                              v1209 = v730;
                              v756 = ((__int64 (__fastcall *)(void *))off_1800A3560[0])(v717);
                              v757 = v756;
                              pcchLength = v756;
                              if ( v756 )
                              {
                                v758 = v1193;
                                LODWORD(v1208) = v1208 - v1193;
                                v1212 -= (unsigned int)v1221;
                                v759 = 0;
                                v1255 = 0;
                                memset(v1333, 0, 28);
                                LODWORD(v1332) = 40;
                                DWORD1(v1332) = v1212;
                                DWORD2(v1332) = -(int)v1208;
                                HIDWORD(v1332) = 2097153;
                                v760 = ((__int64 (__fastcall *)(size_t, __int128 *, _QWORD, __int64 *, _QWORD, _DWORD))off_1800A3568[0])(
                                         v756,
                                         &v1332,
                                         0,
                                         &v1255,
                                         0,
                                         0);
                                v1201 = v760;
                                if ( v760 )
                                {
                                  if ( ((unsigned int (__fastcall *)(size_t, __int64, int *))off_1800A35B8[0])(
                                         v760,
                                         104,
                                         &v1309) )
                                  {
                                    v1210 = v1311;
                                  }
                                  else
                                  {
                                    v1210 = 0;
                                  }
                                  *((_QWORD *)&v1317 + 1) = __PAIR64__(v1208, v1212);
                                  ((void (__fastcall *)(size_t, size_t))off_1800A35C8)(v757, v1201);
                                  ((void (__fastcall *)(size_t, __int64))off_1800A35D0)(v757, 1);
                                  v1206 = ((__int64 (__fastcall *)(size_t, LPCWSTR))off_1800A35C8)(v757, lpModuleName);
                                  v762 = off_1800A3638[0];
                                  v763 = ((__int64 (__fastcall *)(_QWORD))off_1800A35C0[0])(0);
                                  ((void (__fastcall *)(size_t, __int128 *, __int64))v762)(pcchLength, &v1317, v763);
                                  v757 = pcchLength;
                                  ((void (__fastcall *)(size_t, void *, __int64, __int128 *, _DWORD, _QWORD))off_1800A3628)(
                                    pcchLength,
                                    v1237,
                                    0xFFFFFFFFLL,
                                    &v1317,
                                    HIDWORD(dwBytes),
                                    0);
                                  if ( v653 == 1 )
                                  {
                                    if ( (_DWORD)v1207 )
                                      LODWORD(v1197) = ((__int64 (__fastcall *)(__int64))off_1800A3668[0])(8);
                                  }
                                  else
                                  {
                                    LODWORD(v1197) = -5723992;
                                  }
                                  v764 = -(int)v1221;
                                  if ( (int)v1221 >= 0 )
                                    v764 = 0;
                                  v765 = 0;
                                  if ( (int)v1221 >= 0 )
                                    v765 = (int)v1221;
                                  if ( v758 >= 0 )
                                  {
                                    v766 = 0;
                                  }
                                  else
                                  {
                                    v766 = -v758;
                                    v758 = 0;
                                  }
                                  v767 = (int)v1196;
                                  v768 = DWORD2(v1317) - v764;
                                  if ( DWORD2(v1317) - v764 >= (int)v1196 - v765 )
                                    v768 = v1196 - v765;
                                  LODWORD(v1207) = v768;
                                  v769 = HIDWORD(v1317) - v766;
                                  if ( HIDWORD(v1317) - v766 >= (int)v1202 - v758 )
                                    v769 = (_DWORD)v1202 - v758;
                                  LODWORD(v1204) = v769;
                                  if ( v768 > 0 && v769 > 0 )
                                  {
                                    v770 = (char *)(v1210 + 4 * (v764 + (__int64)(DWORD2(v1317) * v766)));
                                    v1222 = v770;
                                    v771 = &v1209[2 * v765 + 2 * (__int64)((int)v1196 * v758)];
                                    v1209 = v771;
                                    LODWORD(v1198) = (unsigned int)v1197 >> 8;
                                    LODWORD(v1202) = WORD1(v1197);
                                    LODWORD(v1196) = 0;
                                    lpModuleName = (LPCWSTR)(4LL * SDWORD2(v1317));
                                    v1237 = (void *)(4 * v767);
                                    v772 = (int)v1207;
                                    v773 = (unsigned int)v1197 >> 8;
                                    do
                                    {
                                      v774 = (unsigned __int8 *)v770;
                                      v1210 = (SIZE_T)v770;
                                      v775 = v771;
                                      v776 = 0;
                                      v1193 = 0;
                                      v777 = (char)v1202;
                                      v778 = v1197;
                                      do
                                      {
                                        v779 = ~(unsigned __int8)((*v774 + v774[2] + 2 * (unsigned int)v774[1]) >> 2);
                                        if ( (unsigned __int8)((*v774 + v774[2] + 2 * (unsigned int)v774[1]) >> 2) != 0xFF )
                                        {
                                          v780 = *((unsigned __int8 *)v775 + 2);
                                          v781 = v779;
                                          v782 = (int)((unsigned __int64)(2155905153LL * v779 * (v778 - v780)) >> 32) >> 7;
                                          *((_BYTE *)v775 + 2) = v780 + (v782 < 0) + v782;
                                          *((_BYTE *)v775 + 1) -= v781 * (v773 - *((_BYTE *)v775 + 1));
                                          *(_BYTE *)v775 -= v781 * (v777 - *(_BYTE *)v775);
                                          *((_BYTE *)v775 + 3) += v781 * (255 - *((unsigned __int8 *)v775 + 3)) / 255;
                                          v774 = (unsigned __int8 *)v1210;
                                          v776 = v1193;
                                        }
                                        v774 += 4;
                                        v1210 = (SIZE_T)v774;
                                        v775 += 2;
                                        v1193 = ++v776;
                                      }
                                      while ( v776 < v772 );
                                      v770 = (char *)v1222 + (_QWORD)lpModuleName;
                                      v1222 = (char *)v1222 + (_QWORD)lpModuleName;
                                      v771 = (unsigned __int16 *)((char *)v1209 + (_QWORD)v1237);
                                      v1209 = (unsigned __int16 *)((char *)v1209 + (_QWORD)v1237);
                                      LODWORD(v1196) = v1196 + 1;
                                    }
                                    while ( (int)v1196 < (int)v1204 );
                                    v80 = dwBytes;
                                    v757 = pcchLength;
                                  }
                                  ((void (__fastcall *)(size_t))off_1800A3588)(v1201);
                                  if ( v1206 )
                                    ((void (__fastcall *)(size_t, size_t))off_1800A35C8)(v757, v1206);
                                }
                                else
                                {
                                  v761 = GetLastError();
                                  v759 = v761;
                                  if ( v761 > 0 )
                                    v759 = (unsigned __int16)v761 | 0x80070000;
                                  if ( v759 >= 0 )
                                    v759 = -2147467259;
                                }
                                ((void (__fastcall *)(size_t))off_1800A3580[0])(v757);
                                if ( v759 >= 0 )
                                {
                                  v783 = v653 == 1;
                                  v714 = v1211;
                                  if ( v783 )
                                    ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, int))off_1800A3550[0])(
                                      v1211,
                                      (unsigned int)v1275,
                                      (unsigned int)v1276,
                                      (unsigned int)v1194,
                                      v1213,
                                      v1203,
                                      0,
                                      0,
                                      13369376);
                                  else
                                    ((void (__fastcall *)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))off_1800A3590[0])(
                                      v1211,
                                      (unsigned int)v1230,
                                      DWORD1(v1230),
                                      (unsigned int)v1194,
                                      v1213,
                                      v1203,
                                      0,
                                      0,
                                      v1194,
                                      v1213,
                                      Size);
                                  v713 = v1192;
                                  goto LABEL_1104;
                                }
                                goto LABEL_1106;
                              }
                            }
                            goto LABEL_1017;
                          }
                        }
LABEL_1107:
                        v713 = v1192;
LABEL_1108:
                        ((void (__fastcall *)(unsigned __int64))off_1800A3588)(v713);
LABEL_1109:
                        if ( !v717 )
                          goto LABEL_1111;
                        goto LABEL_1110;
                      }
                    }
                    else
                    {
                      v653 = v435 & 0xF;
                      v652 = v653;
                    }
                    if ( v652 != 1 )
                      goto LABEL_907;
                    goto LABEL_905;
                  }
                  v540 = 0;
                  pcchLength = 0;
                  v1210 = 0;
                  v539 = 0;
                  v1245 = 0;
                  v1201 = 0;
                  memset(v1264, 0, sizeof(v1264));
                  Src = 0;
                  v1229 = 0;
                  v1207 = 0;
                  v1232 = 0;
                  if ( !((unsigned int (__fastcall *)(__int64, unsigned int *, _QWORD, unsigned int *))off_1800A35F0[0])(
                          8,
                          &v1229,
                          0,
                          &v1232) )
                  {
                    v539 = GetLastError();
                    v541 = v539 < 0;
                    if ( v539 > 0 )
                    {
                      v539 = (unsigned __int16)v539 | 0x80070000;
                      v541 = v539 < 0;
                    }
                    if ( !v541 )
                      v539 = -2147467259;
                    goto LABEL_711;
                  }
                  v542 = MemoryAlloc(2LL * v1232);
                  SP<unsigned long,SP_MEM<unsigned long>>::operator=(&Src, v542);
                  v543 = (char *)Src;
                  if ( Src )
                  {
                    v544 = MemoryAlloc(4LL * (v1229 + 1));
                    SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1207, v544);
                    v118 = v1207;
                    if ( v1207 )
                    {
                      if ( ((unsigned int (__fastcall *)(__int64, unsigned int *, char *, unsigned int *))off_1800A35F0[0])(
                             8,
                             &v1229,
                             v543,
                             &v1232) )
                      {
                        if ( v1229 )
                        {
                          for ( i2 = 0; i2 < v1229; ++i2 )
                          {
                            *(_DWORD *)v118 = ((__int64 (__fastcall *)(char *, _QWORD))off_1800A3600[0])(v543, 0);
                            v547 = -1;
                            do
                              ++v547;
                            while ( *(_WORD *)&v543[2 * v547] );
                            v543 += 2 * v547 + 2;
                            v118 += 4;
                          }
                        }
                        *(_DWORD *)v118 = 1033;
                        v540 = (SIZE_T)v1207;
                        v1207 = 0;
                        v1210 = v540;
                        LODWORD(v118) = v1229 + 1;
                      }
                      else
                      {
                        v539 = GetLastError();
                        v545 = v539 < 0;
                        if ( v539 > 0 )
                        {
                          v539 = (unsigned __int16)v539 | 0x80070000;
                          v545 = v539 < 0;
                        }
                        if ( !v545 )
                          v539 = -2147467259;
                        v540 = pcchLength;
                        LODWORD(v118) = pcchLength;
                      }
LABEL_711:
                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1207);
                      SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&Src);
                      if ( v539 < 0 )
                      {
                        Src = 0;
                        v1209 = 0;
                        pcchLength = 0;
                      }
                      else
                      {
                        v548 = 0;
                        LODWORD(v1194) = 0;
                        v549 = 0;
                        if ( (_DWORD)v118 )
                        {
                          while ( 2 )
                          {
                            for ( i3 = 0; i3 < 0x26; ++i3 )
                            {
                              if ( *(_DWORD *)(v540 + 4LL * v549) == dword_18008D2B0[i3] )
                              {
                                v548 = i3;
                                LODWORD(v1194) = i3;
                                goto LABEL_719;
                              }
                            }
                            if ( ++v549 < (unsigned int)v118 )
                              continue;
                            break;
                          }
                        }
LABEL_719:
                        v551 = v548;
                        memset(v1337, 0, sizeof(v1337));
                        LODWORD(Size) = 0;
                        if ( ((unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64))off_1800A35F8[0])(
                               (unsigned int)dword_18008D2B0[v548],
                               v1357,
                               85)
                          && ((int (__fastcall *)(_BYTE *, __int64, _OWORD *, __int64))off_1800A35E0[0])(
                               v1357,
                               88,
                               v1337,
                               16) > 0 )
                        {
                          LODWORD(Size) = (HIDWORD(v1337[0]) >> 27) & 1;
                        }
                        memset_0(v1265, 0, 0x98u);
                        v552 = L"Segoe UI Light";
                        for ( i4 = 0; i4 != 19; ++i4 )
                        {
                          v1265[i4] = v552;
                          v554 = -1;
                          do
                            ++v554;
                          while ( v552[v554] );
                          v552 += v554 + 1;
                        }
                        Src = (void *)v1265[*((unsigned __int8 *)qword_18008D350 + 3 * v551)];
                        v1209 = (unsigned __int16 *)v1265[*((unsigned __int8 *)qword_18008D350 + 3 * v551 + 1)];
                        pcchLength = v1265[*((unsigned __int8 *)qword_18008D350 + 3 * v551 + 2)];
                        v555 = MemoryAlloc(0x1C90u);
                        v556 = v555;
                        if ( v555 )
                        {
                          v557 = (unsigned __int8 *)qword_18008B610;
                          v558 = v555;
                          v559 = 0;
                          v560 = -1;
                          v561 = 0;
                          v562 = 0;
                          v563 = 914;
                          do
                          {
                            v564 = v557[3] | ((v557[2] | (((*v557 << 8) | v557[1]) << 8)) << 8);
                            v565 = v557[7] | ((v557[6] | ((v557[5] | (v557[4] << 8)) << 8)) << 8);
                            v557 += 8;
                            v566 = v562 ^ v564;
                            v567 = v562 ^ v564 ^ v561 ^ v565 ^ 0xAC987321;
                            v568 = v566 ^ (__ROR4__(v567, 22) + 4991 * __ROR4__(v567 + 1419157410, 27));
                            v569 = v567 ^ (43881 * __ROR4__(v568 + 133239679, 9) - __ROR4__(v568, 30));
                            v570 = v569
                                 ^ (2033 * __ROR4__(v568 ^ (24670 * v569 - (v569 >> 13) - 123127970) ^ 0xAB69, 26)
                                  - __ROR4__(v568 ^ (24670 * v569 - (v569 >> 13) - 123127970), 30));
                            v571 = v568 ^ (24670 * v569 - (v569 >> 13) - 123127970) ^ (133239679 - (v570 ^ 0xAB69605E));
                            v572 = v570 ^ (43881 * (v571 ^ 0x137F)) ^ __ROR4__(v571, 6);
                            v573 = v571 ^ (__ROR4__(v572, 30) + 24670 * __ROR4__(v572 + 133239679, 15));
                            v574 = v572 ^ (2033 * __ROR4__(v573 + 1419157410, 14) - __ROR4__(v573, 24));
                            v575 = v573 ^ __ROR4__(v574, 10) ^ (4991 * __ROR4__(v574 ^ 0xAB69605E, 12));
                            v576 = v574 ^ (v575 >> 10) ^ (43881 * (v575 ^ 0x7F1));
                            v577 = v575 ^ (2033 * (__ROR4__(~v576, 5) + 24670));
                            v578 = v577
                                 ^ (((v576 ^ (v577 - 2033) ^ 0xAB69605E) >> 2)
                                  + 4991 * __ROR4__(v576 ^ (v577 - 2033) ^ 0xAB6967AF, 30));
                            v579 = v576
                                 ^ (v577 - 2033)
                                 ^ 0xAB69605E
                                 ^ (__ROR4__(v578, 25) + 43881 * __ROR4__(v578 - 133239679, 6));
                            v580 = v578 ^ (24670 * (v579 ^ 0x137F) + __ROR4__(v579, 9));
                            v581 = v579 ^ (__ROR4__(v580, 25) + 2033 * __ROR4__(v580 ^ 0xAB69, 27));
                            v582 = v580 ^ v581 ^ 0xAC987321;
                            v583 = v581 ^ (4991 * __ROR4__(v582, 3) - 219010071);
                            v584 = v582 ^ (24670 * __ROR4__(v583 - 133239679, 1) - __ROR4__(v583, 6));
                            v585 = v583 ^ (__ROR4__(v584, 18) + 2033 * __ROR4__(v584 - 1419157410, 29));
                            v586 = v584 ^ (4991 * __ROR4__(v585 - 1419157410, 17) - __ROR4__(v585, 14));
                            v587 = v585 ^ (v586 >> 3) ^ (43881 * (v586 ^ 0x605E));
                            v562 = v586 ^ v559 ^ __ROR4__(v587, 30) ^ (24670 * __ROR4__(v587 ^ 0x7F1137F, 28));
                            v561 = v587 ^ v560;
                            v558[3] = v562;
                            v558[7] = v587 ^ v560;
                            v558[2] = __ROR4__(v562, 8);
                            v558[6] = __ROR4__(v587 ^ v560, 8);
                            v558[1] = __ROR4__(v562, 16);
                            v558[5] = __ROR4__(v587 ^ v560, 16);
                            *v558 = __ROR4__(v562, 24);
                            v558[4] = __ROR4__(v587 ^ v560, 24);
                            v559 = v564;
                            v560 = v565;
                            v558 += 8;
                            --v563;
                          }
                          while ( v563 );
                          v588 = 0;
                          v589 = 0;
                          LOBYTE(v435) = v1213;
                          v590 = 7312;
                          do
                          {
                            v591 = _mm_xor_ps((__m128)_mm_loadu_si128((const __m128i *)&v556[v588]), v589);
                            v589 = v591;
                            v588 += 16LL;
                          }
                          while ( v588 < 0x1C90 );
                          v592 = _mm_xor_ps(v591, (__m128)_mm_srli_si128((__m128i)v591, 8));
                          v593 = _mm_xor_ps(v592, (__m128)_mm_srli_si128((__m128i)v592, 4));
                          v594 = _mm_xor_ps(v593, (__m128)_mm_srli_si128((__m128i)v593, 2));
                          if ( (unsigned __int8)_mm_cvtsi128_si32((__m128i)_mm_xor_ps(
                                                                             v594,
                                                                             (__m128)_mm_srli_si128((__m128i)v594, 1))) == 127 )
                          {
                            v1245 = v556;
                            v1231 = 7312;
                            v539 = 0;
                            v595 = 0;
                            v596 = v1194;
                            do
                            {
                              for ( i5 = 0; i5 < 0x26; ++i5 )
                              {
                                if ( v596 == i5 )
                                  *((_QWORD *)v1264 + v595) = v556;
                                v598 = -1;
                                do
                                  ++v598;
                                while ( v556[v598] );
                                v556 += v598 + 1;
                              }
                              ++v595;
                            }
                            while ( v595 < 6 );
                            v599 = MemoryAlloc(0x18u);
                            SP<unsigned long,SP_MEM<unsigned long>>::operator=(&v1201, v599);
                            v600 = (void **)v1201;
                            if ( v1201 )
                            {
                              *(_OWORD *)v1201 = 0;
                              v600[2] = 0;
                              v601 = 0;
                              LODWORD(v1194) = 0;
                              while ( 2 )
                              {
                                v602 = 0;
                                v1206 = v601;
                                while ( *((_WORD *)&v1199 + v601) != word_18008D3C8[v602] )
                                {
                                  if ( ++v602 >= 6 )
                                    goto LABEL_756;
                                }
                                v603 = *((_QWORD *)v1264 + v602);
                                v604 = -1;
                                do
                                  ++v604;
                                while ( *(_BYTE *)(v604 + v603) );
                                v605 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, _QWORD, _DWORD))off_1800A3610[0])(
                                         65001,
                                         0,
                                         v603,
                                         (unsigned int)(v604 + 1),
                                         0,
                                         0);
                                v1193 = v605;
                                if ( !v605 )
                                  goto LABEL_758;
                                v606 = MemoryAlloc(2LL * v605);
                                v600[v1206] = v606;
                                if ( !v606 )
                                {
                                  v590 = v1231;
                                  goto LABEL_764;
                                }
                                v607 = -1;
                                do
                                  ++v607;
                                while ( *(_BYTE *)(v607 + v603) );
                                if ( !((unsigned int (__fastcall *)(__int64, _QWORD, __int64, _QWORD, void *, unsigned int))off_1800A3610[0])(
                                        65001,
                                        0,
                                        v603,
                                        (unsigned int)(v607 + 1),
                                        v606,
                                        v1193) )
                                {
LABEL_758:
                                  v608 = GetLastError();
                                  v539 = v608;
                                  if ( v608 > 0 )
                                    v539 = (unsigned __int16)v608 | 0x80070000;
                                  if ( v539 >= 0 )
                                    v539 = -2147467259;
                                  v590 = v1231;
                                  goto LABEL_765;
                                }
                                v601 = v1194;
LABEL_756:
                                LODWORD(v1194) = ++v601;
                                if ( v601 < 3 )
                                  continue;
                                break;
                              }
                              v1201 = 0;
                              v1222 = v600;
                              v1266 = Size;
                              v590 = v1231;
LABEL_778:
                              v613 = v1245;
                              if ( v1245 && v590 )
                              {
                                do
                                {
                                  *v613++ = 0;
                                  --v590;
                                }
                                while ( v590 );
                              }
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1201);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1245);
                              SP<unsigned short *,SP_MEM<unsigned short *>>::Reset(&v1210);
                              LODWORD(v118) = 0;
                              if ( v539 < 0 )
                                goto LABEL_885;
                              v1268 = *v600;
                              v1269 = v600[1];
                              v1270 = v600[2];
                              v1263 = 0;
                              LODWORD(v1263) = 16;
                              if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, __int128 *, _QWORD))off_1800A36B8)(
                                                    66,
                                                    0,
                                                    &v1263,
                                                    0) )
                              {
                                v614 = GetLastError();
                                v539 = v614;
                                if ( v614 > 0 )
                                  v539 = (unsigned __int16)v614 | 0x80070000;
                                if ( v539 >= 0 )
                                  v539 = -2147467259;
                                v1267 = 0;
                                goto LABEL_885;
                              }
                              v1267 = BYTE4(v1263) & 1;
                              v615 = v435 & 0xF;
                              v616 = 42;
                              LODWORD(v1208) = 42;
                              if ( v615 != 1 )
                              {
                                if ( (v435 & 0xF) == 2 )
                                {
                                  LODWORD(v1216) = 15;
                                  v1212 = 11;
                                }
                                else
                                {
                                  if ( (v435 & 0xF) != 3 )
                                  {
                                    v616 = 0;
                                    v1212 = 0;
LABEL_795:
                                    LODWORD(v1216) = v616;
                                    goto LABEL_796;
                                  }
                                  LODWORD(v1216) = 225;
                                  v1212 = 225;
                                }
LABEL_796:
                                memset_0(v1347, 0, 0xDCu);
                                v1348 = 220;
                                if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *))off_1800A3630[0])(
                                       0,
                                       0xFFFFFFFFLL,
                                       v1347) )
                                {
                                  v617 = v1349;
                                  v618 = v1350;
                                  LODWORD(v1194) = v1351;
                                  if ( v1349 < 0x60u )
                                    v617 = 96;
                                }
                                else
                                {
                                  v618 = 0;
                                  LODWORD(v1194) = 0;
                                  v617 = 96;
                                }
                                HIDWORD(dwBytes) = v617;
                                v619 = pcchLength;
                                if ( v615 == 1 )
                                  v619 = (size_t)Src;
                                v1206 = v619;
                                memset_0(v1344, 0, 0x5Cu);
                                v1210 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3648[0])(0, 0, 1027);
                                if ( !v1210 )
                                  goto LABEL_851;
                                v1344[0] = -((int (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                              (unsigned int)v1216,
                                              v617,
                                              72);
                                v1344[4] = 400;
                                v1345 = 5;
                                StringCchCopyW(v1346, 0x20u, (const unsigned __int16 *)v1206);
                                v620 = ((__int64 (__fastcall *)(_DWORD *))off_1800A3570[0])(v1344);
                                if ( v620 )
                                {
                                  v539 = 0;
                                  v1271 = v620;
                                }
                                else
                                {
                                  v539 = GetLastError();
                                  v621 = v539 < 0;
                                  if ( v539 > 0 )
                                  {
                                    v539 = (unsigned __int16)v539 | 0x80070000;
                                    v621 = v539 < 0;
                                  }
                                  if ( !v621 )
                                    v539 = -2147467259;
                                }
                                ((void (__fastcall *)(_QWORD, SIZE_T))off_1800A36B0[0])(0, v1210);
                                if ( v539 < 0 )
                                  goto LABEL_884;
                                v622 = (const unsigned __int16 *)pcchLength;
                                if ( v615 == 1 )
                                  v622 = (const unsigned __int16 *)Src;
                                memset_0(v1338, 0, 0x5Cu);
                                v1206 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3648[0])(0, 0, 1027);
                                if ( !v1206 )
                                  goto LABEL_851;
                                v1338[0] = -((int (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                              v1212,
                                              HIDWORD(dwBytes),
                                              72);
                                v1338[4] = 400;
                                v1339 = 5;
                                StringCchCopyW(v1340, 0x20u, v622);
                                v623 = ((__int64 (__fastcall *)(_DWORD *))off_1800A3570[0])(v1338);
                                if ( v623 )
                                {
                                  v539 = 0;
                                  v1272 = (const WCHAR *)v623;
                                }
                                else
                                {
                                  v539 = GetLastError();
                                  v624 = v539 < 0;
                                  if ( v539 > 0 )
                                  {
                                    v539 = (unsigned __int16)v539 | 0x80070000;
                                    v624 = v539 < 0;
                                  }
                                  if ( !v624 )
                                    v539 = -2147467259;
                                }
                                ((void (__fastcall *)(_QWORD, size_t))off_1800A36B0[0])(0, v1206);
                                if ( v539 < 0 )
                                  goto LABEL_884;
                                if ( v615 != 1 )
                                {
                                  if ( v615 == 2 )
                                  {
                                    v618 /= 4;
                                    goto LABEL_828;
                                  }
                                  if ( v615 != 3 )
                                  {
                                    v618 = 0;
LABEL_828:
                                    v625 = 0;
                                    goto LABEL_830;
                                  }
                                }
                                v625 = v1194;
LABEL_830:
                                *((_QWORD *)&v1230 + 1) = __PAIR64__(v625, v618);
                                if ( v615 == 1 )
                                {
                                  v626 = 150;
                                  LODWORD(v1216) = 32;
                                }
                                else
                                {
                                  v626 = 0;
                                  if ( (unsigned int)(v615 - 2) < 2 )
                                  {
                                    LODWORD(v1208) = 0;
                                    LODWORD(v1216) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v1216) = 0;
                                    LODWORD(v1208) = 0;
                                  }
                                }
                                LODWORD(v1194) = v626;
                                v627 = v618 - v626;
                                v1281 = v627;
                                v1277 = v627;
                                v628 = v1268;
                                v1206 = ((__int64 (__fastcall *)(unsigned __int64, size_t, _QWORD))off_1800A35C8)(
                                          v1192,
                                          v1271,
                                          0);
                                v1193 = ((__int64 (__fastcall *)(unsigned __int64, void *, __int64, int *, int, _QWORD))off_1800A3628)(
                                          v1192,
                                          v628,
                                          0xFFFFFFFFLL,
                                          &v1275,
                                          3152,
                                          0);
                                v539 = v1193 == 0 ? 0x80004005 : 0;
                                if ( v1206 )
                                  ((void (__fastcall *)(unsigned __int64, size_t))off_1800A35C8)(v1192, v1206);
                                if ( v1193 )
                                {
                                  v629 = v1269;
                                  v1206 = ((__int64 (__fastcall *)(unsigned __int64, const WCHAR *))off_1800A35C8)(
                                            v1192,
                                            v1272);
                                  v1193 = ((__int64 (__fastcall *)(unsigned __int64, void *, __int64, int *, int, _QWORD))off_1800A3628)(
                                            v1192,
                                            v629,
                                            0xFFFFFFFFLL,
                                            &v1279,
                                            3152,
                                            0);
                                  v539 = v1193 == 0 ? 0x80004005 : 0;
                                  if ( v1206 )
                                    ((void (__fastcall *)(unsigned __int64, size_t))off_1800A35C8)(v1192, v1206);
                                  if ( v1193 )
                                  {
                                    if ( v615 == 2 || v615 == 3 )
                                    {
                                      v627 = v1281;
                                      if ( v1277 > v1281 )
                                        v627 = v1277;
                                    }
                                    v539 = 0;
                                    if ( v1266 )
                                    {
                                      ((void (__fastcall *)(int *, _QWORD, _QWORD))off_1800A36A0)(
                                        &v1275,
                                        (unsigned int)(v627 - v1277),
                                        (unsigned int)v1208);
                                      v630 = (unsigned int)(v627 - v1281);
                                    }
                                    else
                                    {
                                      ((void (__fastcall *)(int *, _QWORD, _QWORD))off_1800A36A0)(
                                        &v1275,
                                        (unsigned int)v1194,
                                        (unsigned int)v1208);
                                      v630 = (unsigned int)v1194;
                                    }
                                    ((void (__fastcall *)(int *, __int64, _QWORD))off_1800A36A0)(
                                      &v1279,
                                      v630,
                                      (unsigned int)(v1278 + v1216));
                                    if ( (unsigned int)(v615 - 2) <= 1 )
                                    {
                                      *((_QWORD *)&v1230 + 1) = __PAIR64__(v1282, v627);
                                      v1274 = -5723992;
                                      goto LABEL_871;
                                    }
                                    if ( v615 != 1 )
                                      goto LABEL_871;
                                    v1274 = 0xFFFFFF;
                                    memset_0(v1341, 0, 0x5Cu);
                                    v1206 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3648[0])(
                                              0,
                                              0,
                                              1027);
                                    if ( !v1206 )
                                    {
LABEL_851:
                                      v631 = GetLastError();
                                      v539 = v631;
                                      LODWORD(v118) = 0;
                                      if ( v631 > 0 )
                                        v539 = (unsigned __int16)v631 | 0x80070000;
                                      if ( v539 >= 0 )
                                        v539 = -2147467259;
                                      goto LABEL_885;
                                    }
                                    v1341[0] = -((int (__fastcall *)(__int64, _QWORD))off_1800A3608[0])(
                                                  11,
                                                  HIDWORD(dwBytes));
                                    v1341[4] = 400;
                                    v1342 = 5;
                                    StringCchCopyW(v1343, 0x20u, v1209);
                                    v632 = ((__int64 (__fastcall *)(_DWORD *))off_1800A3570[0])(v1341);
                                    if ( v632 )
                                    {
                                      v1273 = v632;
                                    }
                                    else
                                    {
                                      v539 = GetLastError();
                                      v633 = v539 < 0;
                                      if ( v539 > 0 )
                                      {
                                        v539 = (unsigned __int16)v539 | 0x80070000;
                                        v633 = v539 < 0;
                                      }
                                      if ( !v633 )
                                        v539 = -2147467259;
                                    }
                                    ((void (__fastcall *)(_QWORD, size_t))off_1800A36B0[0])(0, v1206);
                                    if ( v539 >= 0 )
                                    {
                                      v1285 = v627;
                                      v634 = v1270;
                                      v635 = ((__int64 (__fastcall *)(unsigned __int64, __int64))off_1800A35C8)(
                                               v1192,
                                               v1273);
                                      v636 = ((__int64 (__fastcall *)(unsigned __int64, void *, __int64, unsigned int *, int, _QWORD))off_1800A3628)(
                                               v1192,
                                               v634,
                                               0xFFFFFFFFLL,
                                               &v1283,
                                               1120,
                                               0);
                                      v1193 = v636;
                                      v539 = v636 == 0 ? 0x80004005 : 0;
                                      if ( v635 )
                                      {
                                        ((void (__fastcall *)(unsigned __int64, __int64))off_1800A35C8)(v1192, v635);
                                        v636 = v1193;
                                      }
                                      if ( v636 )
                                      {
                                        v637 = v1285 + 24;
                                        if ( (int)(v1285 + 24) < 90 )
                                          v637 = 90;
                                        v1285 = v637;
                                        v1286 = 32;
                                        v638 = HIDWORD(dwBytes);
                                        v1283 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                                  v1283,
                                                  HIDWORD(dwBytes),
                                                  96);
                                        v1284 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                                  v1284,
                                                  v638,
                                                  96);
                                        v1285 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                                  v1285,
                                                  v638,
                                                  96);
                                        v1286 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))off_1800A3608[0])(
                                                  v1286,
                                                  v638,
                                                  96);
                                        off_1800A36A0((ATL::CRegObject *)&v1283);
LABEL_871:
                                        v639 = HIDWORD(v1230);
                                        v640 = DWORD2(v1230);
                                        v641 = v615 - 1;
                                        if ( v641 )
                                        {
                                          v642 = v641 - 1;
                                          if ( v642 )
                                          {
                                            if ( v642 == 1 )
                                            {
                                              v1334 = 0;
                                              v1335 = 0;
                                              v1336 = 0;
                                              v643 = ((__int64 (__fastcall *)(_QWORD, __int64))off_1800A3698[0])(0, 1);
                                              LODWORD(v1334) = 40;
                                              LODWORD(v118) = 0;
                                              if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_1800A3658)(
                                                                   v643,
                                                                   &v1334) )
                                              {
                                                ((void (__fastcall *)(_QWORD, char *))off_1800A3690[0])(
                                                  0,
                                                  (char *)&v1335 + 4);
                                                ((void (__fastcall *)(_QWORD, char *))off_1800A3690[0])(
                                                  0,
                                                  (char *)&v1335 + 12);
                                                LODWORD(v1230) = 50 * (HIDWORD(v1335) - v640) / 100;
                                                DWORD1(v1230) = 50 * ((int)v1336 - v639) / 100;
                                              }
                                              goto LABEL_882;
                                            }
                                          }
                                          else
                                          {
                                            v644 = v1266;
                                            v1323 = 0;
                                            v1324 = 0;
                                            v1325 = 0;
                                            v645 = ((__int64 (__fastcall *)(_QWORD, __int64))off_1800A3698[0])(0, 1);
                                            LODWORD(v1323) = 40;
                                            if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int128 *))off_1800A3658)(
                                                                 v645,
                                                                 &v1323) )
                                            {
                                              ((void (__fastcall *)(_QWORD, char *))off_1800A3690[0])(
                                                0,
                                                (char *)&v1324 + 4);
                                              ((void (__fastcall *)(_QWORD, char *))off_1800A3690[0])(
                                                0,
                                                (char *)&v1324 + 12);
                                              if ( v644 )
                                                v646 = DWORD1(v1324) + 5 * HIDWORD(v1324) / 100;
                                              else
                                                v646 = 95 * (HIDWORD(v1324) - v640) / 100;
                                              LODWORD(v1230) = v646;
                                              DWORD1(v1230) = 95 * ((int)v1325 - v639) / 100;
                                            }
                                          }
                                          LODWORD(v118) = 0;
                                        }
                                        else
                                        {
                                          LODWORD(v118) = 0;
                                          *(_QWORD *)&v1230 = 0;
                                        }
LABEL_882:
                                        v539 = 0;
LABEL_885:
                                        ((void (__fastcall *)(_QWORD, unsigned __int64))off_1800A36B0[0])(0, v1192);
                                        goto LABEL_886;
                                      }
                                    }
                                  }
                                }
LABEL_884:
                                LODWORD(v118) = 0;
                                goto LABEL_885;
                              }
                              v1212 = 11;
                              goto LABEL_795;
                            }
LABEL_764:
                            v539 = -2147024882;
LABEL_765:
                            if ( v600 )
                            {
                              for ( i6 = 0; i6 != 3; ++i6 )
                              {
                                v610 = v600[i6];
                                if ( v610 )
                                {
                                  v611 = -1;
                                  do
                                    ++v611;
                                  while ( *(_WORD *)&v610[2 * v611] );
                                  for ( i7 = 2 * v611 + 2; i7; --i7 )
                                    *v610++ = 0;
                                  MemoryFree(v600[i6]);
                                }
                              }
                              v590 = v1231;
                            }
LABEL_777:
                            v600 = (void **)v1203;
                            goto LABEL_778;
                          }
                          MemoryFree(v556);
                          v539 = -1073425151;
                        }
                        else
                        {
                          v539 = -2147024882;
                        }
                      }
                      v590 = 0;
                      goto LABEL_777;
                    }
                    v540 = pcchLength;
                    LODWORD(v118) = pcchLength;
                  }
                  else
                  {
                    v540 = 0;
                  }
                  v539 = -2147024882;
                  goto LABEL_711;
                }
                v487 = dword_1800A471C;
LABEL_681:
                dword_1800A471C = v487 + 1;
                goto LABEL_682;
              }
              v436 = dword_1800A471C;
LABEL_635:
              dword_1800A471C = v436 + 1;
              goto LABEL_636;
            }
            v889 = v1193;
LABEL_1593:
            while ( _InterlockedCompareExchange(&dword_1800A4720, 1, 0) )
              ;
            v1174 = dword_1800A471C;
            if ( dword_1800A471C > 0 )
            {
              --dword_1800A471C;
              if ( v1174 == 1 )
              {
                for ( i8 = 0; i8 != 4; ++i8 )
                {
                  v1176 = (HMODULE)qword_1800A3D20[3 * i8];
                  if ( v1176 )
                    FreeLibrary(v1176);
                }
                memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
                memcpy_0(off_1800A3550, off_180085080, 0x170u);
              }
            }
            _InterlockedExchange(&dword_1800A4720, 0);
            SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1222);
            if ( v80 >= 0 )
            {
              if ( v889 == 4 )
              {
                v80 = 0;
                v1177 = *v1243;
LABEL_1614:
                SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v1243);
                if ( v80 >= 0 && v1177 )
                {
                  v1178 = hMenu;
                }
                else
                {
                  v1178 = hMenu;
                  SubMenu = GetSubMenu(hMenu, 0);
                  v1180 = SubMenu;
                  if ( SubMenu )
                  {
                    DeleteMenu(SubMenu, 0xA22Bu, 0);
                    DeleteMenu(v1180, 1u, 0x400u);
                  }
                }
                v1181 = (struct IModularWindow **)v1257;
                v1182 = (TweakerModeControl *)((char *)v1257 + 168);
                Base::ResourceString::ResourceString((Base::ResourceString *)v1259, 0x36CFu);
                Base::ResourceString::ResourceString((Base::ResourceString *)v1258, 0x36D0u);
                v1183 = GetSubMenu(v1178, 0);
                OpenWithHelper::InitializePrivate(v1182, v1183, 65000, 1);
                Base::String::~String((Base::String *)v1258);
                Base::String::~String((Base::String *)v1259);
                v1244 = 0;
                v1184 = (*((__int64 (__fastcall **)(struct IModularWindow **, struct IDataObject **))*v1181 + 9))(
                          v1181,
                          &v1244);
                if ( v1184 < 0 )
                {
                  Base::Throw((Base *)(unsigned int)v1184, v1185);
                  __debugbreak();
                }
                OpenWithHelper::SetSelection(v1182, v1244, v1181[18]);
                v1186 = (HWND *)llVal;
                v1188 = ModularWindow::ContextMenu::DisplayContextMenu(
                          v1181[20],
                          (const struct tagPOINT *)(llVal + 8),
                          v1187);
                v1189 = v1188;
                if ( v1188 )
                {
                  if ( !OpenWithHelper::ProcessCommand(v1182, *v1186, v1188) )
                    ModularWindow::ContextMenu::ProcessCommand(v1181[20], v1189);
                }
                ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v1244);
                return;
              }
            }
            else
            {
              switch ( v80 )
              {
                case -805306316:
                  v80 = -1073418222;
LABEL_1610:
                  v1177 = v1238;
                  goto LABEL_1614;
                case -805306139:
                case -1073425151:
                  v80 = -1073418201;
                  goto LABEL_1610;
                case -805306306:
                  v80 = -1073418200;
                  goto LABEL_1610;
              }
              if ( v80 != -2147024774 )
                goto LABEL_1610;
            }
            v80 = -1073418210;
            goto LABEL_1610;
          }
          if ( v48 && !wcscmp_0(v48, L"WinSta0") && v49 && !wcscmp_0(v49, L"Default") )
          {
            v1242 = 0;
            CurrentProcess = GetCurrentProcess();
            if ( !(unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v1242) )
            {
              LastError = GetLastError();
              v74 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v74 = LastError < 0;
              }
              if ( !v74 )
                LastError = -2147467259;
              goto LABEL_104;
            }
            if ( (v1242 & 0xF) == 0 )
              v50 = 1;
          }
        }
        else
        {
          LastError = 0;
        }
        v51 = v50;
        goto LABEL_104;
      }
      LODWORD(v1194) = 0;
      v44 = 0;
      v8[823] = 0;
      memset_0(qword_1800A3D20, 0, sizeof(qword_1800A3D20));
      v45 = v8;
      if ( *v8 )
      {
        while ( 1 )
        {
          v55 = -1;
          do
            ++v55;
          while ( *(_WORD *)&v8[2 * v55] );
          v56 = (HMODULE *)&qword_1800A3D20[3 * v44];
          if ( !GetModuleHandleExW(0, (LPCWSTR)v8, v56) )
            break;
          v57 = &v8[2 * v55];
          if ( *(_WORD *)*v56 == 23117
            && (v58 = *((int *)*v56 + 15), (unsigned int)v58 < 0x10000000)
            && (v59 = (char *)*v56 + v58, v59 >= (char *)*v56)
            && *(_DWORD *)v59 == 17744 )
          {
            if ( ((*((_WORD *)v59 + 12) - 267) & 0xFEFF) != 0 )
            {
              v46 = -1073741811;
            }
            else
            {
              v46 = 0;
              *(__int64 *)((char *)&qword_1800A3D20[3 * v44 + 1] + 4) = *((_QWORD *)v59 + 17);
              LODWORD(qword_1800A3D20[3 * v44 + 1]) = *((_DWORD *)v59 + 20);
            }
          }
          else
          {
            v46 = -1073741701;
          }
          v60 = *(_DWORD *)(v57 + 2);
          LODWORD(v1196) = v60;
          v8 = v57 + 6;
          for ( i9 = 0; i9 < v60; ++i9 )
          {
            v62 = -1;
            do
              ++v62;
            while ( v8[v62] );
            if ( v46 >= 0 )
            {
              v63 = GetProcAddress(*v56, v8);
              if ( !v63 )
                goto LABEL_25;
              off_1800A3550[(unsigned int)v1194] = v63;
              v60 = v1196;
            }
            v8 += v62 + 1;
            LODWORD(v1194) = v1194 + 1;
          }
          ++v44;
          if ( !*v8 )
            goto LABEL_25;
        }
        v46 = -1073741702;
      }
      else
      {
        v46 = 0;
      }
LABEL_25:
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v45);
      if ( v46 < 0 )
        goto LABEL_18;
      v7 = dword_1800A471C;
    }
    dword_1800A471C = v7 + 1;
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x18004c870  mov     [rsp-8+arg_10], rbx
0x18004c875  push    rbp
0x18004c876  push    rsi
0x18004c877  push    rdi
0x18004c878  push    r12
0x18004c87a  push    r13
0x18004c87c  push    r14
0x18004c87e  push    r15
0x18004c880  lea     rbp, [rsp-0E40h]
0x18004c888  sub     rsp, 0F40h
0x18004c88f  mov     rax, cs:__security_cookie
0x18004c896  xor     rax, rsp
0x18004c899  mov     [rbp+0E70h+var_40], rax
0x18004c8a0  mov     r15, rcx
0x18004c8a3  mov     [rbp+0E70h+var_CD8], rcx
0x18004c8aa  test    rdx, rdx
0x18004c8ad  jz      loc_180056FA1
0x18004c8b3  mov     eax, 4000h
0x18004c8b8  cmp     [rdx], ax
0x18004c8bb  jnz     loc_180056F95
0x18004c8c1  mov     rax, [rdx+8]
0x18004c8c5  mov     [rbp+0E70h+var_CC0], rax
0x18004c8cc  mov     rsi, [rcx+0A0h]
0x18004c8d3  mov     r14, [rax]
0x18004c8d6  mov     rcx, [rsi+8]; hWnd
0x18004c8da  call    cs:__imp_IsWindow
0x18004c8e0  test    eax, eax
0x18004c8e2  jnz     short loc_18004C936
0x18004c8e4  xor     eax, eax
0x18004c8e6  mov     ebx, eax
0x18004c8e8  mov     edi, eax
0x18004c8ea  cmp     cs:qword_1800A2FA0, rax
0x18004c8f1  jnz     short loc_18004C8FA
0x18004c8f3  mov     cs:qword_1800A2FA0, rax
0x18004c8fa  lea     r9, [rsi+40h]
0x18004c8fe  lea     r8, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VContextMenu@ModularWindow@@VCWindow@ATL@@V?$CWinTraits@$0ECAAAAAA@$0BAAAA@@4@@ATL@@SAAEAU_ATL_WNDCLASSINFOW@3@XZ@4U43@A; ATL::_ATL_WNDCLASSINFOW `ATL::CWindowImpl<ModularWindow::ContextMenu,ATL::CWindow,ATL::CWinTraits<1107296256,65536>>::GetWndClassInfo(void)'::`2'::wc
0x18004c905  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamW@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOW@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamW@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamW)
0x18004c90a  mov     word ptr [rsp+0F70h+var_F38], ax
0x18004c90f  mov     [rsp+0F70h+var_F40], rbx
0x18004c914  mov     dword ptr [rsp+0F70h+var_F48], 10000h
0x18004c91c  mov     dword ptr [rsp+0F70h+var_F50], 42000000h
0x18004c924  xor     r9d, r9d
0x18004c927  mov     r8, rdi
0x18004c92a  mov     rdx, r14
0x18004c92d  mov     rcx, rsi
0x18004c930  call    ?Create@?$CWindowImplBaseT@V?$CTrackBarCtrlT@VCWindow@ATL@@@WTL@@V?$CWinTraits@$0FGAAAAAA@$0A@@ATL@@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x18004c935  nop
0x18004c936  mov     rcx, [r15+0A0h]; this
0x18004c93d  call    ?LoadContextMenu@ContextMenu@ModularWindow@@QEAAPEAUHMENU__@@I@Z; ModularWindow::ContextMenu::LoadContextMenu(uint)
0x18004c942  mov     [rbp+0E70h+hMenu], rax
0x18004c949  test    rax, rax
0x18004c94c  jz      loc_180056F6B
0x18004c952  xor     eax, eax
0x18004c954  mov     [rbp+0E70h+var_D98], eax
0x18004c95a  mov     [rbp+0E70h+var_D80], rax
0x18004c961  mov     [rsp+0F70h+var_F00], eax
0x18004c965  mov     [rbp+0E70h+var_E10], rax
0x18004c969  lea     esi, [rax+1]
0x18004c96c  jmp     short loc_18004C970
0x18004c96e  xor     eax, eax
0x18004c970  lock cmpxchg cs:dword_1800A4720, esi
0x18004c978  jnz     short loc_18004C96E
0x18004c97a  or      ebx, 0FFFFFFFFh
0x18004c97d  mov     [rbp+0E70h+var_E08], ebx
0x18004c980  mov     r14d, 60h ; '`'
0x18004c986  lea     r15, qword_1800A3D20
0x18004c98d  lea     r12, off_1800A3550
0x18004c994  mov     eax, cs:dword_1800A471C
0x18004c99a  test    eax, eax
0x18004c99c  jnz     loc_18004CDB4
0x18004c9a2  mov     ecx, 338h; unsigned __int64
0x18004c9a7  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18004c9ac  mov     rdi, rax
0x18004c9af  xor     eax, eax
0x18004c9b1  test    rdi, rdi
0x18004c9b4  jz      loc_18004CD1C
0x18004c9ba  lea     rsi, qword_18008D3E0
0x18004c9c1  mov     r14, rdi
0x18004c9c4  mov     r12d, eax
0x18004c9c7  mov     r13d, ebx
0x18004c9ca  mov     r10d, eax
0x18004c9cd  mov     r8d, eax
0x18004c9d0  mov     ecx, 0AB69605Eh
0x18004c9d5  lea     r15d, [rax+67h]
0x18004c9d9  movzx   ebx, byte ptr [rsi]
0x18004c9dc  shl     ebx, 8
0x18004c9df  movzx   eax, byte ptr [rsi+1]
0x18004c9e3  or      ebx, eax
0x18004c9e5  shl     ebx, 8
0x18004c9e8  movzx   eax, byte ptr [rsi+2]
0x18004c9ec  or      ebx, eax
0x18004c9ee  shl     ebx, 8
0x18004c9f1  movzx   eax, byte ptr [rsi+3]
0x18004c9f5  or      ebx, eax
0x18004c9f7  movzx   r11d, byte ptr [rsi+4]
0x18004c9fc  shl     r11d, 8
0x18004ca00  movzx   eax, byte ptr [rsi+5]
0x18004ca04  or      r11d, eax
0x18004ca07  shl     r11d, 8
0x18004ca0b  movzx   eax, byte ptr [rsi+6]
0x18004ca0f  or      r11d, eax
0x18004ca12  shl     r11d, 8
0x18004ca16  movzx   eax, byte ptr [rsi+7]
0x18004ca1a  or      r11d, eax
0x18004ca1d  lea     rsi, [rsi+8]
0x18004ca21  mov     edx, ebx
0x18004ca23  xor     edx, r8d
0x18004ca26  mov     r8d, r11d
0x18004ca29  xor     r8d, r10d
0x18004ca2c  xor     r8d, edx
0x18004ca2f  xor     r8d, 0AC987321h
0x18004ca36  lea     eax, [r8+54969FA2h]
0x18004ca3d  ror     eax, 1Bh
0x18004ca40  imul    r9d, eax, 137Fh
0x18004ca47  mov     eax, r8d
0x18004ca4a  ror     eax, 16h
0x18004ca4d  add     r9d, eax
0x18004ca50  xor     r9d, edx
0x18004ca53  lea     eax, [r9+7F1137Fh]
0x18004ca5a  ror     eax, 9
0x18004ca5d  imul    r10d, eax, 0AB69h
0x18004ca64  mov     eax, r9d
0x18004ca67  ror     eax, 1Eh
0x18004ca6a  sub     r10d, eax
0x18004ca6d  xor     r10d, r8d
0x18004ca70  mov     eax, r10d
0x18004ca73  shr     eax, 0Dh
0x18004ca76  imul    edx, r10d, 605Eh
0x18004ca7d  sub     edx, eax
0x18004ca7f  sub     edx, 756C8A2h
0x18004ca85  xor     edx, r9d
0x18004ca88  mov     eax, edx
0x18004ca8a  xor     eax, 0AB69h
0x18004ca8f  ror     eax, 1Ah
0x18004ca92  imul    r8d, eax, 7F1h
0x18004ca99  mov     eax, edx
0x18004ca9b  ror     eax, 1Eh
0x18004ca9e  sub     r8d, eax
0x18004caa1  xor     r8d, r10d
0x18004caa4  mov     eax, r8d
0x18004caa7  xor     eax, ecx
0x18004caa9  mov     r9d, 7F1137Fh
0x18004caaf  sub     r9d, eax
0x18004cab2  xor     r9d, edx
0x18004cab5  mov     r10d, r9d
0x18004cab8  ror     r10d, 6
0x18004cabc  mov     eax, r9d
0x18004cabf  xor     eax, 137Fh
0x18004cac4  imul    edx, eax, 0AB69h
0x18004caca  xor     r10d, edx
0x18004cacd  xor     r10d, r8d
0x18004cad0  lea     eax, [r10+7F1137Fh]
0x18004cad7  ror     eax, 0Fh
0x18004cada  imul    edx, eax, 605Eh
0x18004cae0  mov     eax, r10d
0x18004cae3  ror     eax, 1Eh
0x18004cae6  add     edx, eax
0x18004cae8  xor     edx, r9d
0x18004caeb  lea     eax, [rdx+54969FA2h]
0x18004caf1  ror     eax, 0Eh
0x18004caf4  imul    r8d, eax, 7F1h
0x18004cafb  mov     eax, edx
0x18004cafd  ror     eax, 18h
0x18004cb00  sub     r8d, eax
0x18004cb03  xor     r8d, r10d
0x18004cb06  mov     eax, r8d
0x18004cb09  xor     eax, ecx
0x18004cb0b  ror     eax, 0Ch
0x18004cb0e  imul    r9d, eax, 137Fh
0x18004cb15  mov     eax, r8d
0x18004cb18  ror     eax, 0Ah
0x18004cb1b  xor     r9d, eax
0x18004cb1e  xor     r9d, edx
0x18004cb21  mov     eax, r9d
0x18004cb24  mov     r10d, 7F1h
0x18004cb2a  xor     eax, r10d
0x18004cb2d  imul    edx, eax, 0AB69h
0x18004cb33  mov     eax, r9d
0x18004cb36  shr     eax, 0Ah
0x18004cb39  xor     edx, eax
0x18004cb3b  xor     edx, r8d
0x18004cb3e  mov     eax, edx
0x18004cb40  not     eax
0x18004cb42  ror     eax, 5
0x18004cb45  add     eax, 605Eh
0x18004cb4a  imul    r8d, eax, 7F1h
0x18004cb51  xor     r8d, r9d
0x18004cb54  lea     r9d, [r8-7F1h]
0x18004cb5b  xor     r9d, edx
0x18004cb5e  xor     r9d, ecx
0x18004cb61  mov     eax, r9d
0x18004cb64  xor     eax, r10d
0x18004cb67  ror     eax, 1Eh
0x18004cb6a  imul    r10d, eax, 137Fh
0x18004cb71  mov     eax, r9d
0x18004cb74  shr     eax, 2
0x18004cb77  add     r10d, eax
0x18004cb7a  xor     r10d, r8d
0x18004cb7d  lea     eax, [r10-7F1137Fh]
0x18004cb84  ror     eax, 6
0x18004cb87  imul    r8d, eax, 0AB69h
0x18004cb8e  mov     eax, r10d
0x18004cb91  ror     eax, 19h
0x18004cb94  add     r8d, eax
0x18004cb97  xor     r8d, r9d
0x18004cb9a  mov     r9d, r8d
0x18004cb9d  ror     r9d, 9
0x18004cba1  mov     eax, r8d
0x18004cba4  xor     eax, 137Fh
0x18004cba9  imul    edx, eax, 605Eh
0x18004cbaf  add     r9d, edx
0x18004cbb2  xor     r9d, r10d
0x18004cbb5  mov     eax, r9d
0x18004cbb8  xor     eax, 0AB69h
0x18004cbbd  ror     eax, 1Bh
0x18004cbc0  imul    edx, eax, 7F1h
0x18004cbc6  mov     eax, r9d
0x18004cbc9  ror     eax, 19h
0x18004cbcc  add     edx, eax
0x18004cbce  xor     edx, r8d
0x18004cbd1  mov     r8d, edx
0x18004cbd4  xor     r8d, r9d
0x18004cbd7  xor     r8d, 0AC987321h
0x18004cbde  mov     eax, r8d
0x18004cbe1  ror     eax, 3
0x18004cbe4  imul    r9d, eax, 137Fh
0x18004cbeb  sub     r9d, 0D0DD417h
0x18004cbf2  xor     r9d, edx
0x18004cbf5  lea     eax, [r9-7F1137Fh]
0x18004cbfc  ror     eax, 1
0x18004cbfe  imul    edx, eax, 605Eh
0x18004cc04  mov     eax, r9d
0x18004cc07  ror     eax, 6
0x18004cc0a  sub     edx, eax
0x18004cc0c  xor     edx, r8d
0x18004cc0f  lea     eax, [rdx-54969FA2h]
0x18004cc15  ror     eax, 1Dh
0x18004cc18  imul    r8d, eax, 7F1h
0x18004cc1f  mov     eax, edx
0x18004cc21  ror     eax, 12h
0x18004cc24  add     r8d, eax
0x18004cc27  xor     r8d, r9d
0x18004cc2a  lea     eax, [r8-54969FA2h]
0x18004cc31  ror     eax, 11h
0x18004cc34  imul    r9d, eax, 137Fh
0x18004cc3b  mov     eax, r8d
0x18004cc3e  ror     eax, 0Eh
0x18004cc41  sub     r9d, eax
0x18004cc44  xor     r9d, edx
0x18004cc47  mov     eax, r9d
0x18004cc4a  xor     eax, 605Eh
0x18004cc4f  imul    r10d, eax, 0AB69h
0x18004cc56  mov     eax, r9d
0x18004cc59  shr     eax, 3
0x18004cc5c  xor     r10d, eax
0x18004cc5f  xor     r10d, r8d
0x18004cc62  mov     eax, r10d
0x18004cc65  xor     eax, 7F1137Fh
0x18004cc6a  ror     eax, 1Ch
0x18004cc6d  imul    r8d, eax, 605Eh
0x18004cc74  mov     eax, r10d
0x18004cc77  ror     eax, 1Eh
0x18004cc7a  xor     r8d, eax
0x18004cc7d  xor     r8d, r9d
0x18004cc80  xor     r8d, r12d
0x18004cc83  xor     r10d, r13d
0x18004cc86  mov     [r14+3], r8b
0x18004cc8a  mov     [r14+7], r10b
0x18004cc8e  mov     eax, r8d
0x18004cc91  ror     eax, 8
0x18004cc94  mov     [r14+2], al
0x18004cc98  mov     eax, r10d
0x18004cc9b  ror     eax, 8
0x18004cc9e  mov     [r14+6], al
0x18004cca2  mov     eax, r8d
0x18004cca5  ror     eax, 10h
0x18004cca8  mov     [r14+1], al
0x18004ccac  mov     eax, r10d
0x18004ccaf  ror     eax, 10h
0x18004ccb2  mov     [r14+5], al
0x18004ccb6  mov     eax, r8d
0x18004ccb9  ror     eax, 18h
0x18004ccbc  mov     [r14], al
0x18004ccbf  mov     eax, r10d
0x18004ccc2  ror     eax, 18h
0x18004ccc5  mov     [r14+4], al
0x18004ccc9  mov     r12d, ebx
0x18004cccc  mov     r13d, r11d
0x18004cccf  lea     r14, [r14+8]
0x18004ccd3  sub     r15, 1
0x18004ccd7  jnz     loc_18004C9D9
0x18004ccdd  xor     eax, eax
0x18004ccdf  mov     cl, al
0x18004cce1  lea     esi, [rax+1]
0x18004cce4  xor     cl, [rdi+rax]
0x18004cce7  add     rax, rsi
0x18004ccea  cmp     rax, 338h
0x18004ccf0  jb      short loc_18004CCE4
0x18004ccf2  movzx   eax, cl
0x18004ccf5  cmp     rax, cs:qword_18008D718
  ... truncated ...
```
